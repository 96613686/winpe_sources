# OMutex::Open(bool)

- ea: `0x18001c2b0`
- end: `0x18001c314`
- name: `?Open@OMutex@@QEAA_N_N@Z`
- size: `100`
- prototype: `bool __fastcall(OMutex *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001be5c`

## callees

- `0x18001c2b0`
- `0x18001c7d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c2ec`
- `KERNEL32!GetLastError` at `0x18001c2ec`
- `KERNEL32!OpenMutexW` at `0x18001c2d5`
- `KERNEL32!OpenMutexW` at `0x18001c2d5`

## string_xrefs

- `0x18001c2f6`: `Mutex '%s' already opened`

## pseudocode

```c
char __fastcall OMutex::Open(OMutex *this, int a2, __int64 a3, int a4)
{
  const WCHAR *v4; // r8
  HANDLE v6; // rax

  v4 = (const WCHAR *)((char *)this + 32);
  if ( *((_QWORD *)this + 1) )
  {
    Mso::Logging::MsoSendTraceTag<std::wstring>(
      524908239,
      a2,
      (_DWORD)v4,
      a4,
      (__int64)L"Mutex '%s' already opened",
      (char *)this + 32);
    return 1;
  }
  if ( *((_QWORD *)this + 7) > 7u )
    v4 = *(const WCHAR **)v4;
  v6 = OpenMutexW(0x100000u, 0, v4);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    return 1;
  GetLastError();
  return 0;
}

```

## disassembly

```asm
0x18001c2b0  push    rbx
0x18001c2b2  sub     rsp, 40h
0x18001c2b6  cmp     qword ptr [rcx+8], 0
0x18001c2bb  lea     r8, [rcx+20h]
0x18001c2bf  mov     rbx, rcx
0x18001c2c2  jnz     short loc_18001C2F6
0x18001c2c4  cmp     qword ptr [r8+18h], 7
0x18001c2c9  jbe     short loc_18001C2CE
0x18001c2cb  mov     r8, [r8]; lpName
0x18001c2ce  xor     edx, edx; bInheritHandle
0x18001c2d0  mov     ecx, 100000h; dwDesiredAccess
0x18001c2d5  call    cs:__imp_OpenMutexW
0x18001c2db  mov     [rbx+8], rax
0x18001c2df  test    rax, rax
0x18001c2e2  jz      short loc_18001C2EC
0x18001c2e4  mov     al, 1
0x18001c2e6  add     rsp, 40h
0x18001c2ea  pop     rbx
0x18001c2eb  retn
0x18001c2ec  call    cs:__imp_GetLastError
0x18001c2f2  xor     al, al
0x18001c2f4  jmp     short loc_18001C2E6
0x18001c2f6  lea     rax, aMutexSAlreadyO; "Mutex '%s' already opened"
0x18001c2fd  mov     [rsp+48h+var_20], r8
0x18001c302  mov     ecx, 1F4976CFh
0x18001c307  mov     [rsp+48h+var_28], rax
0x18001c30c  call    ??$MsoSendTraceTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Logging::MsoSendTraceTag<std::wstring>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,std::wstring const &)
0x18001c311  jmp     short loc_18001C2E4
```
