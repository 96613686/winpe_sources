# IsCallerAdminOrSystem

- ea: `0x180057cac`
- end: `0x180057e75`
- name: `IsCallerAdminOrSystem`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180028b80`

## callees

- `0x180057cac`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180057d89`
- `ntdll!RtlNtStatusToDosError` at `0x180057e2b`
- `ntdll!RtlNtStatusToDosError` at `0x180057d89`
- `ntdll!RtlNtStatusToDosError` at `0x180057e2b`
- `ntdll!RtlSetLastWin32Error` at `0x180057d74`
- `ntdll!RtlSetLastWin32Error` at `0x180057d91`
- `ntdll!RtlSetLastWin32Error` at `0x180057e15`
- `ntdll!RtlSetLastWin32Error` at `0x180057e33`
- `ntdll!RtlSetLastWin32Error` at `0x180057d74`
- `ntdll!RtlSetLastWin32Error` at `0x180057d91`
- `ntdll!RtlSetLastWin32Error` at `0x180057e15`
- `ntdll!RtlSetLastWin32Error` at `0x180057e33`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180057d48`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180057de9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180057d48`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180057de9`
- `ntdll!RtlFreeSid` at `0x180057da3`
- `ntdll!RtlFreeSid` at `0x180057e53`
- `ntdll!RtlFreeSid` at `0x180057da3`
- `ntdll!RtlFreeSid` at `0x180057e53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057cff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057cff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057e3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057e3f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180057ce3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180057ce3`

## string_xrefs

- `0x180057cd4`: `advapi32.dll`
- `0x180057cf5`: `CheckTokenMembership`

## pseudocode

```c
__int64 IsCallerAdminOrSystem()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rdi
  FARPROC ProcAddress; // rsi
  int v3; // eax
  unsigned int v4; // ebx
  ULONG v5; // ecx
  int v6; // eax
  ULONG v7; // ecx
  int v9; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  LibraryW = LoadLibraryW(L"advapi32.dll");
  v1 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "CheckTokenMembership");
    if ( !ProcAddress )
      goto LABEL_21;
    v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
    if ( v3 < 0 )
    {
      v5 = RtlNtStatusToDosError(v3);
    }
    else
    {
      v9 = 0;
      if ( !((unsigned int (__fastcall *)(_QWORD, PSID, int *))ProcAddress)(0, Sid, &v9) )
      {
LABEL_10:
        v4 = 0;
        goto LABEL_11;
      }
      if ( v9 )
      {
        RtlSetLastWin32Error(0);
        v4 = 1;
LABEL_11:
        if ( Sid )
        {
          RtlFreeSid(Sid);
          Sid = 0;
        }
        if ( v4 )
          goto LABEL_22;
        v6 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
        if ( v6 < 0 )
        {
          v7 = RtlNtStatusToDosError(v6);
LABEL_20:
          RtlSetLastWin32Error(v7);
          goto LABEL_21;
        }
        v9 = 0;
        if ( ((unsigned int (__fastcall *)(_QWORD, PSID, int *))ProcAddress)(0, Sid, &v9) )
        {
          if ( v9 )
          {
            RtlSetLastWin32Error(0);
            v4 = 1;
LABEL_22:
            FreeLibrary(v1);
            goto LABEL_24;
          }
          v7 = 5;
          goto LABEL_20;
        }
LABEL_21:
        v4 = 0;
        goto LABEL_22;
      }
      v5 = 5;
    }
    RtlSetLastWin32Error(v5);
    goto LABEL_10;
  }
  v4 = 0;
LABEL_24:
  if ( Sid )
    RtlFreeSid(Sid);
  return v4;
}

```

## disassembly

```asm
0x180057cac  push    rbp
0x180057cae  push    rbx
0x180057caf  push    rsi
0x180057cb0  push    rdi
0x180057cb1  push    r14
0x180057cb3  mov     rbp, rsp
0x180057cb6  sub     rsp, 80h
0x180057cbd  mov     rax, cs:__security_cookie
0x180057cc4  xor     rax, rsp
0x180057cc7  mov     [rbp+var_8], rax
0x180057ccb  xor     r14d, r14d
0x180057cce  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180057cd4  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180057cdb  mov     [rbp+var_18], r14
0x180057cdf  mov     dword ptr [rbp+IdentifierAuthority.Value], r14d
0x180057ce3  call    cs:__imp_LoadLibraryW
0x180057ce9  mov     rdi, rax
0x180057cec  test    rax, rax
0x180057cef  jz      loc_180057E47
0x180057cf5  lea     rdx, aChecktokenmemb_0; "CheckTokenMembership"
0x180057cfc  mov     rcx, rax; hModule
0x180057cff  call    cs:__imp_GetProcAddress
0x180057d05  mov     rsi, rax
0x180057d08  test    rax, rax
0x180057d0b  jz      loc_180057E39
0x180057d11  lea     rax, [rbp+var_18]
0x180057d15  mov     r9d, 220h; SubAuthority1
0x180057d1b  mov     [rsp+80h+Sid], rax; Sid
0x180057d20  lea     r8d, [r14+20h]; SubAuthority0
0x180057d24  mov     [rsp+80h+SubAuthority7], r14d; SubAuthority7
0x180057d29  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180057d2d  mov     [rsp+80h+SubAuthority6], r14d; SubAuthority6
0x180057d32  mov     dl, 2; SubAuthorityCount
0x180057d34  mov     [rsp+80h+SubAuthority5], r14d; SubAuthority5
0x180057d39  mov     [rsp+80h+SubAuthority4], r14d; SubAuthority4
0x180057d3e  mov     [rsp+80h+SubAuthority3], r14d; SubAuthority3
0x180057d43  mov     [rsp+80h+SubAuthority2], r14d; SubAuthority2
0x180057d48  call    cs:__imp_RtlAllocateAndInitializeSid
0x180057d4e  test    eax, eax
0x180057d50  js      short loc_180057D87
0x180057d52  mov     rdx, [rbp+var_18]
0x180057d56  lea     r8, [rbp+var_20]
0x180057d5a  xor     ecx, ecx
0x180057d5c  mov     [rbp+var_20], r14d
0x180057d60  mov     rax, rsi
0x180057d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d68  test    eax, eax
0x180057d6a  jz      short loc_180057D97
0x180057d6c  cmp     [rbp+var_20], r14d
0x180057d70  jz      short loc_180057D80
0x180057d72  xor     ecx, ecx; LastError
0x180057d74  call    cs:__imp_RtlSetLastWin32Error
0x180057d7a  lea     ebx, [r14+1]
0x180057d7e  jmp     short loc_180057D9A
0x180057d80  mov     ecx, 5
0x180057d85  jmp     short loc_180057D91
0x180057d87  mov     ecx, eax; Status
0x180057d89  call    cs:__imp_RtlNtStatusToDosError
0x180057d8f  mov     ecx, eax; LastError
0x180057d91  call    cs:__imp_RtlSetLastWin32Error
0x180057d97  mov     ebx, r14d
0x180057d9a  mov     rcx, [rbp+var_18]; Sid
0x180057d9e  test    rcx, rcx
0x180057da1  jz      short loc_180057DAD
0x180057da3  call    cs:__imp_RtlFreeSid
0x180057da9  mov     [rbp+var_18], r14
0x180057dad  test    ebx, ebx
0x180057daf  jnz     loc_180057E3C
0x180057db5  lea     rax, [rbp+var_18]
0x180057db9  xor     r9d, r9d; SubAuthority1
0x180057dbc  mov     [rsp+80h+Sid], rax; Sid
0x180057dc1  lea     r8d, [rbx+12h]; SubAuthority0
0x180057dc5  mov     [rsp+80h+SubAuthority7], r14d; SubAuthority7
0x180057dca  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180057dce  mov     [rsp+80h+SubAuthority6], r14d; SubAuthority6
0x180057dd3  mov     dl, 1; SubAuthorityCount
0x180057dd5  mov     [rsp+80h+SubAuthority5], r14d; SubAuthority5
0x180057dda  mov     [rsp+80h+SubAuthority4], r14d; SubAuthority4
0x180057ddf  mov     [rsp+80h+SubAuthority3], r14d; SubAuthority3
0x180057de4  mov     [rsp+80h+SubAuthority2], r14d; SubAuthority2
0x180057de9  call    cs:__imp_RtlAllocateAndInitializeSid
0x180057def  test    eax, eax
0x180057df1  js      short loc_180057E29
0x180057df3  mov     rdx, [rbp+var_18]
0x180057df7  lea     r8, [rbp+var_20]
0x180057dfb  xor     ecx, ecx
0x180057dfd  mov     [rbp+var_20], r14d
0x180057e01  mov     rax, rsi
0x180057e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e09  test    eax, eax
0x180057e0b  jz      short loc_180057E39
0x180057e0d  cmp     [rbp+var_20], r14d
0x180057e11  jz      short loc_180057E22
0x180057e13  xor     ecx, ecx; LastError
0x180057e15  call    cs:__imp_RtlSetLastWin32Error
0x180057e1b  mov     ebx, 1
0x180057e20  jmp     short loc_180057E3C
0x180057e22  mov     ecx, 5
0x180057e27  jmp     short loc_180057E33
0x180057e29  mov     ecx, eax; Status
0x180057e2b  call    cs:__imp_RtlNtStatusToDosError
0x180057e31  mov     ecx, eax; LastError
0x180057e33  call    cs:__imp_RtlSetLastWin32Error
0x180057e39  mov     ebx, r14d
0x180057e3c  mov     rcx, rdi; hLibModule
0x180057e3f  call    cs:__imp_FreeLibrary
0x180057e45  jmp     short loc_180057E4A
0x180057e47  mov     ebx, r14d
0x180057e4a  mov     rcx, [rbp+var_18]; Sid
0x180057e4e  test    rcx, rcx
0x180057e51  jz      short loc_180057E59
0x180057e53  call    cs:__imp_RtlFreeSid
0x180057e59  mov     eax, ebx
0x180057e5b  mov     rcx, [rbp+var_8]
0x180057e5f  xor     rcx, rsp; StackCookie
0x180057e62  call    __security_check_cookie
0x180057e67  add     rsp, 80h
0x180057e6e  pop     r14
0x180057e70  pop     rdi
0x180057e71  pop     rsi
0x180057e72  pop     rbx
0x180057e73  pop     rbp
0x180057e74  retn
```
