# PunycodeToUnicodeHost

- ea: `0x180078d6c`
- end: `0x180078ec6`
- name: `PunycodeToUnicodeHost`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180083740`

## callees

- `0x180078d6c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180078e9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180078e9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078e06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e73`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180078dd0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180078dd0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180078e3b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180078e3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180078e8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180078e8b`

## string_xrefs

- `0x180078dc9`: `normaliz.dll`

## pseudocode

```c
__int64 __fastcall PunycodeToUnicodeHost(_WORD *a1, __int64 a2, BSTR *a3)
{
  signed int v5; // ebx
  __int64 v6; // rsi
  HMODULE LibraryA; // rax
  HMODULE v8; // r14
  signed int v9; // eax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // r15
  signed int v12; // eax
  __int64 v13; // r13
  BSTR v14; // rax
  int v15; // eax
  signed int LastError; // eax

  if ( a1 )
  {
    if ( a3 )
    {
      LODWORD(v6) = 0;
      v5 = 0;
      if ( *a1 )
      {
        v6 = -1;
        do
          ++v6;
        while ( a1[v6] );
      }
      *a3 = 0;
      if ( !(_DWORD)v6 )
        goto LABEL_27;
      LibraryA = LoadLibraryA("normaliz.dll");
      v8 = LibraryA;
      if ( LibraryA )
      {
        ProcAddress = GetProcAddress(LibraryA, "IdnToUnicode");
        v11 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress;
        if ( ProcAddress )
        {
          v12 = ((__int64 (__fastcall *)(__int64, _WORD *, _QWORD))ProcAddress)(2, a1, (unsigned int)v6);
          v13 = v12;
          if ( v12 > 0 )
          {
            v14 = SysAllocStringLen(0, v12);
            *a3 = v14;
            if ( v14 )
            {
              v15 = v11(2, a1, (unsigned int)v6, v14, (int)v13 + 1);
              (*a3)[v13] = 0;
              if ( !v15 )
              {
                LastError = GetLastError();
                v5 = LastError;
                if ( LastError > 0 )
                  v5 = (unsigned __int16)LastError | 0x80070000;
                SysFreeString(*a3);
                *a3 = 0;
              }
            }
            else
            {
              v5 = -2147024882;
            }
          }
        }
        FreeLibrary(v8);
      }
      else
      {
        v9 = GetLastError();
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
      }
      if ( v5 >= 0 )
      {
LABEL_27:
        if ( !*a3 )
          return (unsigned int)-2147467259;
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180078d6c  push    rbx
0x180078d6e  push    rbp
0x180078d6f  push    rsi
0x180078d70  push    rdi
0x180078d71  push    r12
0x180078d73  push    r13
0x180078d75  push    r14
0x180078d77  push    r15
0x180078d79  sub     rsp, 38h
0x180078d7d  xor     r12d, r12d
0x180078d80  mov     rdi, r8
0x180078d83  mov     rbp, rcx
0x180078d86  test    rcx, rcx
0x180078d89  jnz     short loc_180078D95
0x180078d8b  mov     ebx, 80070057h
0x180078d90  jmp     loc_180078EB3
0x180078d95  test    rdi, rdi
0x180078d98  jnz     short loc_180078DA4
0x180078d9a  mov     ebx, 80004003h
0x180078d9f  jmp     loc_180078EB3
0x180078da4  mov     esi, r12d
0x180078da7  mov     ebx, r12d
0x180078daa  cmp     r12w, [rcx]
0x180078dae  jz      short loc_180078DBE
0x180078db0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180078db4  inc     rsi
0x180078db7  cmp     [rcx+rsi*2], r12w
0x180078dbc  jnz     short loc_180078DB4
0x180078dbe  mov     [r8], r12
0x180078dc1  test    esi, esi
0x180078dc3  jz      loc_180078EA8
0x180078dc9  lea     rcx, aNormalizDll; "normaliz.dll"
0x180078dd0  call    cs:__imp_LoadLibraryA
0x180078dd6  mov     r14, rax
0x180078dd9  test    rax, rax
0x180078ddc  jnz     short loc_180078DFC
0x180078dde  call    cs:__imp_GetLastError
0x180078de4  mov     ebx, eax
0x180078de6  test    eax, eax
0x180078de8  jle     loc_180078EA4
0x180078dee  movzx   ebx, ax
0x180078df1  or      ebx, 80070000h
0x180078df7  jmp     loc_180078EA4
0x180078dfc  lea     rdx, aIdntounicode; "IdnToUnicode"
0x180078e03  mov     rcx, r14; hModule
0x180078e06  call    cs:__imp_GetProcAddress
0x180078e0c  mov     r15, rax
0x180078e0f  test    rax, rax
0x180078e12  jz      loc_180078E9B
0x180078e18  xor     r9d, r9d
0x180078e1b  mov     [rsp+78h+var_58], r12d
0x180078e20  mov     r8d, esi
0x180078e23  mov     rdx, rbp
0x180078e26  lea     ecx, [r9+2]
0x180078e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e2f  movsxd  r13, eax
0x180078e32  test    eax, eax
0x180078e34  jle     short loc_180078E9B
0x180078e36  mov     edx, r13d; ui
0x180078e39  xor     ecx, ecx; strIn
0x180078e3b  call    cs:__imp_SysAllocStringLen
0x180078e41  mov     [rdi], rax
0x180078e44  mov     r9, rax
0x180078e47  test    rax, rax
0x180078e4a  jz      short loc_180078E96
0x180078e4c  lea     eax, [r13+1]
0x180078e50  mov     r8d, esi
0x180078e53  mov     [rsp+78h+var_58], eax
0x180078e57  mov     rdx, rbp
0x180078e5a  mov     rax, r15
0x180078e5d  mov     ecx, 2
0x180078e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e67  mov     rcx, [rdi]
0x180078e6a  mov     [rcx+r13*2], r12w
0x180078e6f  test    eax, eax
0x180078e71  jnz     short loc_180078E9B
0x180078e73  call    cs:__imp_GetLastError
0x180078e79  mov     ebx, eax
0x180078e7b  test    eax, eax
0x180078e7d  jle     short loc_180078E88
0x180078e7f  movzx   ebx, ax
0x180078e82  or      ebx, 80070000h
0x180078e88  mov     rcx, [rdi]; bstrString
0x180078e8b  call    cs:__imp_SysFreeString
0x180078e91  mov     [rdi], r12
0x180078e94  jmp     short loc_180078E9B
0x180078e96  mov     ebx, 8007000Eh
0x180078e9b  mov     rcx, r14; hLibModule
0x180078e9e  call    cs:__imp_FreeLibrary
0x180078ea4  test    ebx, ebx
0x180078ea6  js      short loc_180078EB3
0x180078ea8  cmp     [rdi], r12
0x180078eab  mov     eax, 80004005h
0x180078eb0  cmovz   ebx, eax
0x180078eb3  mov     eax, ebx
0x180078eb5  add     rsp, 38h
0x180078eb9  pop     r15
0x180078ebb  pop     r14
0x180078ebd  pop     r13
0x180078ebf  pop     r12
0x180078ec1  pop     rdi
0x180078ec2  pop     rsi
0x180078ec3  pop     rbp
0x180078ec4  pop     rbx
0x180078ec5  retn
```
