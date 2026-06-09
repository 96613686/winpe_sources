# BindToServer

- ea: `0x180008938`
- end: `0x180008a14`
- name: `BindToServer`
- size: `220`
- prototype: `HRESULT __fastcall(struct _GUID *, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007928`

## callees

- `0x180007a7c`
- `0x180008938`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008978`
- `KERNEL32!GetLastError` at `0x180008978`
- `KERNEL32!FreeLibrary` at `0x1800089b6`
- `KERNEL32!FreeLibrary` at `0x1800089b6`
- `KERNEL32!GetProcAddress` at `0x18000899a`
- `KERNEL32!GetProcAddress` at `0x18000899a`
- `KERNEL32!LoadLibraryExW` at `0x180008967`
- `KERNEL32!LoadLibraryExW` at `0x180008967`
- `ole32!CoCreateInstance` at `0x1800089cd`
- `ole32!CoCreateInstance` at `0x1800089cd`

## string_xrefs

- `0x180008960`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall BindToServer(struct _GUID *a1, struct _GUID *a2, void **a3)
{
  HMODULE Library; // rbx
  signed int LastError; // eax
  signed int v8; // ecx
  FARPROC ProcAddress; // rax
  HRESULT result; // eax

  Library = LoadLibraryExW(L"user32.dll", 0, 8u);
  if ( Library )
    goto LABEL_5;
  LastError = GetLastError();
  v8 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v8 = LastError;
  if ( v8 >= 0 )
  {
LABEL_5:
    ProcAddress = GetProcAddress(Library, "AllowSetForegroundWindow");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64))ProcAddress)(0xFFFFFFFFLL);
    if ( Library )
      FreeLibrary(Library);
  }
  result = CoCreateInstance(a1, 0, 4u, a2, a3);
  if ( result && result != -2147221232 && result != -2147467262 )
  {
    result = StartServer(a1, a2, a3);
    if ( result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008938  mov     rax, rsp
0x18000893b  mov     [rax+8], rbx
0x18000893f  mov     [rax+10h], rbp
0x180008943  mov     [rax+18h], rsi
0x180008947  mov     [rax+20h], rdi
0x18000894b  push    r14
0x18000894d  sub     rsp, 30h
0x180008951  mov     rdi, r8
0x180008954  mov     rsi, rdx
0x180008957  mov     rbp, rcx
0x18000895a  xor     edx, edx; hFile
0x18000895c  lea     r8d, [rdx+8]; dwFlags
0x180008960  lea     rcx, LibFileName; "user32.dll"
0x180008967  call    cs:__imp_LoadLibraryExW
0x18000896d  mov     rbx, rax
0x180008970  xor     r14d, r14d
0x180008973  test    rax, rax
0x180008976  jnz     short loc_180008990
0x180008978  call    cs:__imp_GetLastError
0x18000897e  movzx   ecx, ax
0x180008981  or      ecx, 80070000h
0x180008987  test    eax, eax
0x180008989  cmovle  ecx, eax
0x18000898c  test    ecx, ecx
0x18000898e  js      short loc_1800089BC
0x180008990  lea     rdx, aAllowsetforegr; "AllowSetForegroundWindow"
0x180008997  mov     rcx, rbx; hModule
0x18000899a  call    cs:__imp_GetProcAddress
0x1800089a0  test    rax, rax
0x1800089a3  jz      short loc_1800089AE
0x1800089a5  or      ecx, 0FFFFFFFFh
0x1800089a8  call    cs:__guard_dispatch_icall_fptr
0x1800089ae  test    rbx, rbx
0x1800089b1  jz      short loc_1800089BC
0x1800089b3  mov     rcx, rbx; hLibModule
0x1800089b6  call    cs:__imp_FreeLibrary
0x1800089bc  mov     [rsp+38h+ppv], rdi; ppv
0x1800089c1  mov     r9, rsi; riid
0x1800089c4  xor     edx, edx; pUnkOuter
0x1800089c6  lea     r8d, [rdx+4]; dwClsContext
0x1800089ca  mov     rcx, rbp; rclsid
0x1800089cd  call    cs:__imp_CoCreateInstance
0x1800089d3  test    eax, eax
0x1800089d5  jz      short loc_1800089F9
0x1800089d7  cmp     eax, 80040110h
0x1800089dc  jz      short loc_1800089F9
0x1800089de  cmp     eax, 80004002h
0x1800089e3  jz      short loc_1800089F9
0x1800089e5  mov     r8, rdi; void **
0x1800089e8  mov     rdx, rsi; struct _GUID *
0x1800089eb  mov     rcx, rbp; struct _GUID *
0x1800089ee  call    ?StartServer@@YAJAEBU_GUID@@0PEAPEAX@Z; StartServer(_GUID const &,_GUID const &,void * *)
0x1800089f3  test    eax, eax
0x1800089f5  cmovns  eax, r14d
0x1800089f9  mov     rbx, [rsp+38h+arg_0]
0x1800089fe  mov     rbp, [rsp+38h+arg_8]
0x180008a03  mov     rsi, [rsp+38h+arg_10]
0x180008a08  mov     rdi, [rsp+38h+arg_18]
0x180008a0d  add     rsp, 30h
0x180008a11  pop     r14
0x180008a13  retn
```
