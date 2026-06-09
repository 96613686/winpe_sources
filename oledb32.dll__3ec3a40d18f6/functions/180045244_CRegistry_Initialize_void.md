# CRegistry::Initialize(void)

- ea: `0x180045244`
- end: `0x180045353`
- name: `?Initialize@CRegistry@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(CRegistry *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004429c`

## callees

- `0x180029560`
- `0x180045244`
- `0x180045420`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180045262`
- `KERNEL32!CreateEventW` at `0x180045262`
- `KERNEL32!GetLastError` at `0x180045306`
- `KERNEL32!GetLastError` at `0x180045306`
- `KERNEL32!CloseHandle` at `0x1800452f6`
- `KERNEL32!CloseHandle` at `0x1800452f6`
- `ADVAPI32!RegOpenKeyExW` at `0x180045297`
- `ADVAPI32!RegOpenKeyExW` at `0x1800452b5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800452d3`
- `ADVAPI32!RegOpenKeyExW` at `0x180045297`
- `ADVAPI32!RegOpenKeyExW` at `0x1800452b5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800452d3`

## string_xrefs

- `0x18004532b`: `<CRegistry::Initialize|Trace|HR> `
- `0x180045275`: `SOFTWARE\Microsoft\DataAccess\RootBinder`

## pseudocode

```c
__int64 __fastcall CRegistry::Initialize(CRegistry *this)
{
  HANDLE EventW; // rax
  unsigned int v3; // ebx
  void *v4; // rcx
  signed int LastError; // eax

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( EventW )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\RootBinder", 0, 0xF003Fu, (PHKEY)this)
      && RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\RootBinder", 0, 0x1Fu, (PHKEY)this)
      && (v3 = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\DataAccess\\RootBinder",
                 0,
                 0x20019u,
                 (PHKEY)this)) != 0 )
    {
      v4 = (void *)*((_QWORD *)this + 1);
      *(_QWORD *)this = 0;
      CloseHandle(v4);
      *((_QWORD *)this + 1) = 0;
    }
    else
    {
      v3 = CRegistry::ResetRootBinderEvent(this);
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83A8[0], 201737, L"<CRegistry::Initialize|Trace|HR> ", v3);
  return v3;
}

```

## disassembly

```asm
0x180045244  mov     [rsp+arg_0], rbx
0x180045249  mov     [rsp+arg_8], rsi
0x18004524e  push    rdi
0x18004524f  sub     rsp, 30h
0x180045253  xor     r9d, r9d; lpName
0x180045256  mov     rdi, rcx
0x180045259  xor     r8d, r8d; bInitialState
0x18004525c  xor     ecx, ecx; lpEventAttributes
0x18004525e  lea     edx, [r9+1]; bManualReset
0x180045262  call    cs:__imp_CreateEventW
0x180045268  mov     [rdi+8], rax
0x18004526c  test    rax, rax
0x18004526f  jz      loc_180045306
0x180045275  lea     rbx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\DataAccess\\RootBi"...
0x18004527c  mov     [rsp+38h+phkResult], rdi; phkResult
0x180045281  mov     rsi, 0FFFFFFFF80000002h
0x180045288  mov     rdx, rbx; lpSubKey
0x18004528b  mov     rcx, rsi; hKey
0x18004528e  mov     r9d, 0F003Fh; samDesired
0x180045294  xor     r8d, r8d; ulOptions
0x180045297  call    cs:__imp_RegOpenKeyExW
0x18004529d  test    eax, eax
0x18004529f  jz      short loc_1800452DF
0x1800452a1  mov     r9d, 1Fh; samDesired
0x1800452a7  mov     [rsp+38h+phkResult], rdi; phkResult
0x1800452ac  xor     r8d, r8d; ulOptions
0x1800452af  mov     rdx, rbx; lpSubKey
0x1800452b2  mov     rcx, rsi; hKey
0x1800452b5  call    cs:__imp_RegOpenKeyExW
0x1800452bb  test    eax, eax
0x1800452bd  jz      short loc_1800452DF
0x1800452bf  mov     r9d, 20019h; samDesired
0x1800452c5  mov     [rsp+38h+phkResult], rdi; phkResult
0x1800452ca  xor     r8d, r8d; ulOptions
0x1800452cd  mov     rdx, rbx; lpSubKey
0x1800452d0  mov     rcx, rsi; hKey
0x1800452d3  call    cs:__imp_RegOpenKeyExW
0x1800452d9  mov     ebx, eax
0x1800452db  test    eax, eax
0x1800452dd  jnz     short loc_1800452EB
0x1800452df  mov     rcx, rdi; this
0x1800452e2  call    ?ResetRootBinderEvent@CRegistry@@QEAAJXZ; CRegistry::ResetRootBinderEvent(void)
0x1800452e7  mov     ebx, eax
0x1800452e9  jmp     short loc_18004531B
0x1800452eb  mov     rcx, [rdi+8]; hObject
0x1800452ef  mov     qword ptr [rdi], 0
0x1800452f6  call    cs:__imp_CloseHandle
0x1800452fc  mov     qword ptr [rdi+8], 0
0x180045304  jmp     short loc_18004531B
0x180045306  call    cs:__imp_GetLastError
0x18004530c  mov     ebx, eax
0x18004530e  test    eax, eax
0x180045310  jle     short loc_18004531B
0x180045312  movzx   ebx, ax
0x180045315  or      ebx, 80070000h
0x18004531b  test    byte ptr cs:_bidGblFlags, 2
0x180045322  jz      short loc_180045341
0x180045324  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004532b  lea     r8, aCregistryIniti; "<CRegistry::Initialize|Trace|HR> "
0x180045332  mov     r9d, ebx
0x180045335  mov     edx, 31409h
0x18004533a  call    _bidTraceHR
0x18004533f  mov     ebx, eax
0x180045341  mov     rsi, [rsp+38h+arg_8]
0x180045346  mov     eax, ebx
0x180045348  mov     rbx, [rsp+38h+arg_0]
0x18004534d  add     rsp, 30h
0x180045351  pop     rdi
0x180045352  retn
```
