# CLR_HOSTING_LEGACY::Initialize(ushort const *)

- ea: `0x180003e28`
- end: `0x180003ee5`
- name: `?Initialize@CLR_HOSTING_LEGACY@@QEAAJPEBG@Z`
- size: `189`
- prototype: `__int64 __fastcall(HMODULE *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003afc`

## callees

- `0x180003e28`
- `0x180005010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003e57`
- `KERNEL32!GetLastError` at `0x180003e57`
- `KERNEL32!GetProcAddress` at `0x180003e4c`
- `KERNEL32!GetProcAddress` at `0x180003eb1`
- `KERNEL32!GetProcAddress` at `0x180003e4c`
- `KERNEL32!GetProcAddress` at `0x180003eb1`

## string_xrefs

- `0x180003eaa`: `ClrCreateManagedInstance`

## pseudocode

```c
__int64 __fastcall CLR_HOSTING_LEGACY::Initialize(HMODULE *this, const unsigned __int16 *a2)
{
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  FARPROC v7; // rax
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = 0;
  ProcAddress = GetProcAddress(this[2], "CorBindToRuntimeEx");
  if ( !ProcAddress )
    goto LABEL_2;
  v6 = ((__int64 (__fastcall *)(const unsigned __int16 *, const wchar_t *, __int64, GUID *, GUID *, __int64 *))ProcAddress)(
         a2,
         L"svr",
         139286,
         &CLSID_CLRRuntimeHost,
         &IID_ICLRRuntimeHost,
         &v9);
  if ( v6 < 0 )
    goto LABEL_7;
  v7 = GetProcAddress(this[2], "ClrCreateManagedInstance");
  if ( v7 )
  {
    this[3] = (HMODULE)v7;
    v6 = 0;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_7:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003e28  mov     [rsp+arg_8], rbx
0x180003e2d  push    rdi
0x180003e2e  sub     rsp, 40h
0x180003e32  mov     rbx, rdx
0x180003e35  mov     [rsp+48h+arg_0], 0
0x180003e3e  mov     rdi, rcx
0x180003e41  lea     rdx, aCorbindtorunti; "CorBindToRuntimeEx"
0x180003e48  mov     rcx, [rcx+10h]; hModule
0x180003e4c  call    cs:__imp_GetProcAddress
0x180003e52  test    rax, rax
0x180003e55  jnz     short loc_180003E6E
0x180003e57  call    cs:__imp_GetLastError
0x180003e5d  mov     ebx, eax
0x180003e5f  test    eax, eax
0x180003e61  jle     short loc_180003EC2
0x180003e63  movzx   ebx, ax
0x180003e66  or      ebx, 80070000h
0x180003e6c  jmp     short loc_180003EC2
0x180003e6e  lea     rcx, [rsp+48h+arg_0]
0x180003e73  mov     r8d, 22016h
0x180003e79  mov     [rsp+48h+var_20], rcx
0x180003e7e  lea     r9, CLSID_CLRRuntimeHost
0x180003e85  lea     rcx, IID_ICLRRuntimeHost
0x180003e8c  mov     [rsp+48h+var_28], rcx
0x180003e91  lea     rdx, aSvr; "svr"
0x180003e98  mov     rcx, rbx
0x180003e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea0  mov     ebx, eax
0x180003ea2  test    eax, eax
0x180003ea4  js      short loc_180003EC2
0x180003ea6  mov     rcx, [rdi+10h]; hModule
0x180003eaa  lea     rdx, aClrcreatemanag; "ClrCreateManagedInstance"
0x180003eb1  call    cs:__imp_GetProcAddress
0x180003eb7  test    rax, rax
0x180003eba  jz      short loc_180003E57
0x180003ebc  mov     [rdi+18h], rax
0x180003ec0  xor     ebx, ebx
0x180003ec2  mov     rcx, [rsp+48h+arg_0]
0x180003ec7  test    rcx, rcx
0x180003eca  jz      short loc_180003ED8
0x180003ecc  mov     rax, [rcx]
0x180003ecf  mov     rax, [rax+10h]
0x180003ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed8  mov     eax, ebx
0x180003eda  mov     rbx, [rsp+48h+arg_8]
0x180003edf  add     rsp, 40h
0x180003ee3  pop     rdi
0x180003ee4  retn
```
