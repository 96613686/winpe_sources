# NtVdm64CreateProcessInternalW

- ea: `0x18005d9a0`
- end: `0x18005dba3`
- name: `NtVdm64CreateProcessInternalW`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180017530`
- `0x180043e44`
- `0x18005d9a0`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005db6f`
- `ntdll!RtlSetLastWin32Error` at `0x18005db6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005daab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005daab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005db61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005db61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005da89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005da89`

## string_xrefs

- `0x18005da77`: `NtVdm64.Dll`
- `0x18005daa1`: `NtVdm64CreateProcessInternalW`

## pseudocode

```c
__int64 __fastcall NtVdm64CreateProcessInternalW(
        __int64 a1,
        const WCHAR *a2,
        const wchar_t *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  unsigned int v12; // r14d
  wchar_t *v14; // rdi
  HRESULT v17; // eax
  ULONG LastErrorValue; // ebx
  HMODULE Library; // rax
  HMODULE v20; // rsi
  FARPROC ProcAddress; // rax
  unsigned int v22; // eax
  wchar_t pszDest[264]; // [rsp+A0h] [rbp-268h] BYREF

  v12 = 0;
  v14 = (wchar_t *)a3;
  if ( a3 >= NtCurrentTeb()->StaticUnicodeBuffer && a3 < (const wchar_t *)NtCurrentTeb()->Padding3 )
  {
    v17 = StringCchCopyW(pszDest, 0x105u, a3);
    if ( v17 < 0 )
    {
      LastErrorValue = (unsigned __int16)v17;
      goto LABEL_12;
    }
    v14 = pszDest;
  }
  LastErrorValue = 193;
  Library = LoadLibraryExW(L"NtVdm64.Dll", 0, 0x800u);
  v20 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NtVdm64CreateProcessInternalW");
    if ( ProcAddress )
    {
      v22 = ((__int64 (__fastcall *)(__int64, const WCHAR *, wchar_t *, __int64, __int64, int, int, __int64, __int64, __int64, __int64, __int64))ProcAddress)(
              a1,
              a2,
              v14,
              a4,
              a5,
              a6,
              a7,
              a8,
              a9,
              a10,
              a11,
              a12);
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      v12 = v22;
      if ( v22 || LastErrorValue == 216 )
        Upload16BitUTCData(a2);
    }
    FreeLibrary(v20);
  }
LABEL_12:
  RtlSetLastWin32Error(LastErrorValue);
  return v12;
}

```

## disassembly

```asm
0x18005d9a0  push    rbx
0x18005d9a2  push    rbp
0x18005d9a3  push    rsi
0x18005d9a4  push    rdi
0x18005d9a5  push    r12
0x18005d9a7  push    r13
0x18005d9a9  push    r14
0x18005d9ab  push    r15
0x18005d9ad  sub     rsp, 2C8h
0x18005d9b4  mov     rax, cs:__security_cookie
0x18005d9bb  xor     rax, rsp
0x18005d9be  mov     [rsp+308h+var_58], rax
0x18005d9c6  mov     rax, [rsp+308h+arg_38]
0x18005d9ce  xor     r14d, r14d
0x18005d9d1  mov     r13, [rsp+308h+arg_20]
0x18005d9d9  mov     r12, r9
0x18005d9dc  mov     [rsp+308h+var_278], rax
0x18005d9e4  mov     rdi, r8
0x18005d9e7  mov     rax, [rsp+308h+arg_40]
0x18005d9ef  mov     rbp, rdx
0x18005d9f2  mov     [rsp+308h+var_280], rax
0x18005d9fa  mov     r15, rcx
0x18005d9fd  mov     rax, [rsp+308h+arg_48]
0x18005da05  mov     [rsp+308h+var_288], rax
0x18005da0d  mov     rax, [rsp+308h+arg_50]
0x18005da15  mov     [rsp+308h+var_290], rax
0x18005da1a  mov     rax, [rsp+308h+arg_58]
0x18005da22  mov     [rsp+308h+var_298], rax
0x18005da27  mov     rax, gs:30h
0x18005da30  add     rax, 1268h
0x18005da36  cmp     r8, rax
0x18005da39  jb      short loc_18005DA75
0x18005da3b  mov     rax, gs:30h
0x18005da44  add     rax, 1472h
0x18005da4a  cmp     r8, rax
0x18005da4d  jnb     short loc_18005DA75
0x18005da4f  mov     edx, 105h; cchDest
0x18005da54  lea     rcx, [rsp+308h+pszDest]; pszDest
0x18005da5c  call    StringCchCopyW
0x18005da61  test    eax, eax
0x18005da63  jns     short loc_18005DA6D
0x18005da65  movzx   ebx, ax
0x18005da68  jmp     loc_18005DB6D
0x18005da6d  lea     rdi, [rsp+308h+pszDest]
0x18005da75  xor     edx, edx; hFile
0x18005da77  lea     rcx, aNtvdm64Dll; "NtVdm64.Dll"
0x18005da7e  mov     r8d, 800h; dwFlags
0x18005da84  mov     ebx, 0C1h
0x18005da89  call    cs:__imp_LoadLibraryExW
0x18005da90  nop     dword ptr [rax+rax+00h]
0x18005da95  mov     rsi, rax
0x18005da98  test    rax, rax
0x18005da9b  jz      loc_18005DB6D
0x18005daa1  lea     rdx, aNtvdm64createp_0; "NtVdm64CreateProcessInternalW"
0x18005daa8  mov     rcx, rax; hModule
0x18005daab  call    cs:__imp_GetProcAddress
0x18005dab2  nop     dword ptr [rax+rax+00h]
0x18005dab7  mov     r10, rax
0x18005daba  test    rax, rax
0x18005dabd  jz      loc_18005DB5E
0x18005dac3  mov     rax, [rsp+308h+var_298]
0x18005dac8  mov     r9, r12
0x18005dacb  mov     [rsp+308h+var_2B0], rax
0x18005dad0  mov     r8, rdi
0x18005dad3  mov     rax, [rsp+308h+var_290]
0x18005dad8  mov     rdx, rbp
0x18005dadb  mov     [rsp+308h+var_2B8], rax
0x18005dae0  mov     rcx, r15
0x18005dae3  mov     rax, [rsp+308h+var_288]
0x18005daeb  mov     [rsp+308h+var_2C0], rax
0x18005daf0  mov     rax, [rsp+308h+var_280]
0x18005daf8  mov     [rsp+308h+var_2C8], rax
0x18005dafd  mov     rax, [rsp+308h+var_278]
0x18005db05  mov     [rsp+308h+var_2D0], rax
0x18005db0a  mov     eax, [rsp+308h+arg_30]
0x18005db11  mov     [rsp+308h+var_2D8], eax
0x18005db15  mov     eax, [rsp+308h+arg_28]
0x18005db1c  mov     [rsp+308h+var_2E0], eax
0x18005db20  mov     rax, r10
0x18005db23  mov     [rsp+308h+var_2E8], r13
0x18005db28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db2d  mov     ebx, gs:68h
0x18005db35  mov     r14d, eax
0x18005db38  test    eax, eax
0x18005db3a  jz      short loc_18005DB43
0x18005db3c  mov     edx, 100h
0x18005db41  jmp     short loc_18005DB50
0x18005db43  cmp     ebx, 0D8h
0x18005db49  jnz     short loc_18005DB5E
0x18005db4b  mov     edx, 20h ; ' '
0x18005db50  xor     r9d, r9d
0x18005db53  xor     r8d, r8d
0x18005db56  mov     rcx, rbp; lpValueName
0x18005db59  call    Upload16BitUTCData
0x18005db5e  mov     rcx, rsi; hLibModule
0x18005db61  call    cs:__imp_FreeLibrary
0x18005db68  nop     dword ptr [rax+rax+00h]
0x18005db6d  mov     ecx, ebx; LastError
0x18005db6f  call    cs:__imp_RtlSetLastWin32Error
0x18005db76  nop     dword ptr [rax+rax+00h]
0x18005db7b  mov     eax, r14d
0x18005db7e  mov     rcx, [rsp+308h+var_58]
0x18005db86  xor     rcx, rsp; StackCookie
0x18005db89  call    __security_check_cookie
0x18005db8e  add     rsp, 2C8h
0x18005db95  pop     r15
0x18005db97  pop     r14
0x18005db99  pop     r13
0x18005db9b  pop     r12
0x18005db9d  pop     rdi
0x18005db9e  pop     rsi
0x18005db9f  pop     rbp
0x18005dba0  pop     rbx
0x18005dba1  retn
```
