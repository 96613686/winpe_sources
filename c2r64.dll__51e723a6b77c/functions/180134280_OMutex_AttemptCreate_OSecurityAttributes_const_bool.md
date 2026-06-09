# OMutex::AttemptCreate(OSecurityAttributes const &,bool)

- ea: `0x180134280`
- end: `0x180134341`
- name: `?AttemptCreate@OMutex@@QEAA_NAEBVOSecurityAttributes@@_N@Z`
- size: `193`
- prototype: `bool __fastcall(OMutex *__hidden this, const struct OSecurityAttributes *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001be5c`

## callees

- `0x18001c7d4`
- `0x180132ea0`
- `0x180134280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801342e1`
- `KERNEL32!GetLastError` at `0x1801342e1`
- `KERNEL32!CreateMutexW` at `0x1801342d7`
- `KERNEL32!CreateMutexW` at `0x1801342d7`

## string_xrefs

- `0x18013429e`: `Mutex '%s' already created`
- `0x180134323`: `Failed to create the mutex %s: LastError: 0x%x`

## pseudocode

```c
char __fastcall OMutex::AttemptCreate(OMutex *this, const struct OSecurityAttributes *a2, char a3, int a4)
{
  const WCHAR **v4; // rbx
  const WCHAR *v7; // r8
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  DWORD LastError; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(LastError) = a3;
  v4 = (const WCHAR **)((char *)this + 32);
  if ( *((_QWORD *)this + 1) )
  {
    Mso::Logging::MsoSendTraceTag<std::wstring>(
      524908242,
      (_DWORD)a2,
      a3,
      a4,
      (__int64)L"Mutex '%s' already created",
      v4);
    return 1;
  }
  v7 = (const WCHAR *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) > 7u )
    v7 = *v4;
  *((_QWORD *)this + 1) = CreateMutexW((LPSECURITY_ATTRIBUTES)((char *)a2 + 16), 0, v7);
  LastError = GetLastError();
  if ( LastError == 183 )
    Mso::Logging::MsoSendTraceTag<std::wstring>(
      524908241,
      v8,
      (_BYTE)v9,
      v10,
      (__int64)L"Got handle to existing mutex %s",
      v4);
  if ( *((_QWORD *)this + 1) )
    return 1;
  Mso::Logging::MsoSendTraceTag<std::wstring,unsigned long>(
    524908240,
    v8,
    v9,
    v10,
    (__int64)L"Failed to create the mutex %s: LastError: 0x%x",
    v4,
    &LastError);
  return 0;
}

```

## disassembly

```asm
0x180134280  mov     r11, rsp
0x180134283  mov     [r11+8], rbx
0x180134287  mov     [r11+18h], r8b
0x18013428b  push    rdi
0x18013428c  sub     rsp, 40h
0x180134290  cmp     qword ptr [rcx+8], 0
0x180134295  lea     rbx, [rcx+20h]
0x180134299  mov     rdi, rcx
0x18013429c  jz      short loc_1801342C4
0x18013429e  lea     rax, aMutexSAlreadyC; "Mutex '%s' already created"
0x1801342a5  mov     [r11-20h], rbx
0x1801342a9  mov     ecx, 1F4976D2h
0x1801342ae  mov     [r11-28h], rax
0x1801342b2  call    ??$MsoSendTraceTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Logging::MsoSendTraceTag<std::wstring>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,std::wstring const &)
0x1801342b7  mov     al, 1
0x1801342b9  mov     rbx, [rsp+48h+arg_0]
0x1801342be  add     rsp, 40h
0x1801342c2  pop     rdi
0x1801342c3  retn
0x1801342c4  cmp     qword ptr [rbx+18h], 7
0x1801342c9  mov     r8, rbx
0x1801342cc  jbe     short loc_1801342D1
0x1801342ce  mov     r8, [rbx]; lpName
0x1801342d1  lea     rcx, [rdx+10h]; lpMutexAttributes
0x1801342d5  xor     edx, edx; bInitialOwner
0x1801342d7  call    cs:__imp_CreateMutexW
0x1801342dd  mov     [rdi+8], rax
0x1801342e1  call    cs:__imp_GetLastError
0x1801342e7  mov     [rsp+48h+arg_10], eax
0x1801342eb  cmp     eax, 0B7h
0x1801342f0  jnz     short loc_18013430D
0x1801342f2  lea     rax, aGotHandleToExi; "Got handle to existing mutex %s"
0x1801342f9  mov     [rsp+48h+var_20], rbx
0x1801342fe  mov     ecx, 1F4976D1h
0x180134303  mov     [rsp+48h+var_28], rax
0x180134308  call    ??$MsoSendTraceTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Logging::MsoSendTraceTag<std::wstring>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,std::wstring const &)
0x18013430d  cmp     qword ptr [rdi+8], 0
0x180134312  jnz     short loc_1801342B7
0x180134314  lea     rax, [rsp+48h+arg_10]
0x180134319  mov     ecx, 1F4976D0h
0x18013431e  mov     [rsp+48h+var_18], rax
0x180134323  lea     rax, aFailedToCreate_13; "Failed to create the mutex %s: LastErro"...
0x18013432a  mov     [rsp+48h+var_20], rbx
0x18013432f  mov     [rsp+48h+var_28], rax
0x180134334  call    ??$MsoSendTraceTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; Mso::Logging::MsoSendTraceTag<std::wstring,ulong>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,std::wstring const &,ulong const &)
0x180134339  xor     al, al
0x18013433b  jmp     loc_1801342B9
```
