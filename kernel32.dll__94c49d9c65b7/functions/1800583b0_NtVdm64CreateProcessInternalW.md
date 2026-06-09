# NtVdm64CreateProcessInternalW

- ea: `0x1800583b0`
- end: `0x18005859a`
- name: `NtVdm64CreateProcessInternalW`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180019b00`
- `0x1800402f0`
- `0x1800583b0`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005856d`
- `ntdll!RtlSetLastWin32Error` at `0x18005856d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800584b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800584b5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058565`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058565`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180058499`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180058499`

## string_xrefs

- `0x180058487`: `NtVdm64.Dll`
- `0x1800584ab`: `NtVdm64CreateProcessInternalW`

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
0x1800583b0  push    rbx
0x1800583b2  push    rbp
0x1800583b3  push    rsi
0x1800583b4  push    rdi
0x1800583b5  push    r12
0x1800583b7  push    r13
0x1800583b9  push    r14
0x1800583bb  push    r15
0x1800583bd  sub     rsp, 2C8h
0x1800583c4  mov     rax, cs:__security_cookie
0x1800583cb  xor     rax, rsp
0x1800583ce  mov     [rsp+308h+var_58], rax
0x1800583d6  mov     rax, [rsp+308h+arg_38]
0x1800583de  xor     r14d, r14d
0x1800583e1  mov     r13, [rsp+308h+arg_20]
0x1800583e9  mov     r12, r9
0x1800583ec  mov     [rsp+308h+var_278], rax
0x1800583f4  mov     rdi, r8
0x1800583f7  mov     rax, [rsp+308h+arg_40]
0x1800583ff  mov     rbp, rdx
0x180058402  mov     [rsp+308h+var_280], rax
0x18005840a  mov     r15, rcx
0x18005840d  mov     rax, [rsp+308h+arg_48]
0x180058415  mov     [rsp+308h+var_288], rax
0x18005841d  mov     rax, [rsp+308h+arg_50]
0x180058425  mov     [rsp+308h+var_290], rax
0x18005842a  mov     rax, [rsp+308h+arg_58]
0x180058432  mov     [rsp+308h+var_298], rax
0x180058437  mov     rax, gs:30h
0x180058440  add     rax, 1268h
0x180058446  cmp     r8, rax
0x180058449  jb      short loc_180058485
0x18005844b  mov     rax, gs:30h
0x180058454  add     rax, 1472h
0x18005845a  cmp     r8, rax
0x18005845d  jnb     short loc_180058485
0x18005845f  mov     edx, 105h; cchDest
0x180058464  lea     rcx, [rsp+308h+pszDest]; pszDest
0x18005846c  call    StringCchCopyW
0x180058471  test    eax, eax
0x180058473  jns     short loc_18005847D
0x180058475  movzx   ebx, ax
0x180058478  jmp     loc_18005856B
0x18005847d  lea     rdi, [rsp+308h+pszDest]
0x180058485  xor     edx, edx; hFile
0x180058487  lea     rcx, aNtvdm64Dll; "NtVdm64.Dll"
0x18005848e  mov     r8d, 800h; dwFlags
0x180058494  mov     ebx, 0C1h
0x180058499  call    cs:__imp_LoadLibraryExW
0x18005849f  mov     rsi, rax
0x1800584a2  test    rax, rax
0x1800584a5  jz      loc_18005856B
0x1800584ab  lea     rdx, aNtvdm64createp_0; "NtVdm64CreateProcessInternalW"
0x1800584b2  mov     rcx, rax; hModule
0x1800584b5  call    cs:__imp_GetProcAddress
0x1800584bb  mov     r10, rax
0x1800584be  test    rax, rax
0x1800584c1  jz      loc_180058562
0x1800584c7  mov     rax, [rsp+308h+var_298]
0x1800584cc  mov     r9, r12
0x1800584cf  mov     [rsp+308h+var_2B0], rax
0x1800584d4  mov     r8, rdi
0x1800584d7  mov     rax, [rsp+308h+var_290]
0x1800584dc  mov     rdx, rbp
0x1800584df  mov     [rsp+308h+var_2B8], rax
0x1800584e4  mov     rcx, r15
0x1800584e7  mov     rax, [rsp+308h+var_288]
0x1800584ef  mov     [rsp+308h+var_2C0], rax
0x1800584f4  mov     rax, [rsp+308h+var_280]
0x1800584fc  mov     [rsp+308h+var_2C8], rax
0x180058501  mov     rax, [rsp+308h+var_278]
0x180058509  mov     [rsp+308h+var_2D0], rax
0x18005850e  mov     eax, [rsp+308h+arg_30]
0x180058515  mov     [rsp+308h+var_2D8], eax
0x180058519  mov     eax, [rsp+308h+arg_28]
0x180058520  mov     [rsp+308h+var_2E0], eax
0x180058524  mov     rax, r10
0x180058527  mov     [rsp+308h+var_2E8], r13
0x18005852c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058531  mov     ebx, gs:68h
0x180058539  mov     r14d, eax
0x18005853c  test    eax, eax
0x18005853e  jz      short loc_180058547
0x180058540  mov     edx, 100h
0x180058545  jmp     short loc_180058554
0x180058547  cmp     ebx, 0D8h
0x18005854d  jnz     short loc_180058562
0x18005854f  mov     edx, 20h ; ' '
0x180058554  xor     r9d, r9d
0x180058557  xor     r8d, r8d
0x18005855a  mov     rcx, rbp; lpValueName
0x18005855d  call    Upload16BitUTCData
0x180058562  mov     rcx, rsi; hLibModule
0x180058565  call    cs:__imp_FreeLibrary
0x18005856b  mov     ecx, ebx; LastError
0x18005856d  call    cs:__imp_RtlSetLastWin32Error
0x180058573  mov     eax, r14d
0x180058576  mov     rcx, [rsp+308h+var_58]
0x18005857e  xor     rcx, rsp; StackCookie
0x180058581  call    __security_check_cookie
0x180058586  add     rsp, 2C8h
0x18005858d  pop     r15
0x18005858f  pop     r14
0x180058591  pop     r13
0x180058593  pop     r12
0x180058595  pop     rdi
0x180058596  pop     rsi
0x180058597  pop     rbp
0x180058598  pop     rbx
0x180058599  retn
```
