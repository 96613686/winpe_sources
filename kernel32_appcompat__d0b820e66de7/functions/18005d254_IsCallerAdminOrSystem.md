# IsCallerAdminOrSystem

- ea: `0x18005d254`
- end: `0x18005d46c`
- name: `IsCallerAdminOrSystem`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180026ad0`

## callees

- `0x18005d254`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005d349`
- `ntdll!RtlNtStatusToDosError` at `0x18005d409`
- `ntdll!RtlNtStatusToDosError` at `0x18005d349`
- `ntdll!RtlNtStatusToDosError` at `0x18005d409`
- `ntdll!RtlSetLastWin32Error` at `0x18005d32e`
- `ntdll!RtlSetLastWin32Error` at `0x18005d357`
- `ntdll!RtlSetLastWin32Error` at `0x18005d3ed`
- `ntdll!RtlSetLastWin32Error` at `0x18005d417`
- `ntdll!RtlSetLastWin32Error` at `0x18005d32e`
- `ntdll!RtlSetLastWin32Error` at `0x18005d357`
- `ntdll!RtlSetLastWin32Error` at `0x18005d3ed`
- `ntdll!RtlSetLastWin32Error` at `0x18005d417`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005d2fc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005d3bb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005d2fc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18005d3bb`
- `ntdll!RtlFreeSid` at `0x18005d36f`
- `ntdll!RtlFreeSid` at `0x18005d443`
- `ntdll!RtlFreeSid` at `0x18005d36f`
- `ntdll!RtlFreeSid` at `0x18005d443`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d2ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d2ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005d429`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005d429`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005d28b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005d28b`

## string_xrefs

- `0x18005d27c`: `advapi32.dll`
- `0x18005d2a3`: `CheckTokenMembership`

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
0x18005d254  push    rbp
0x18005d256  push    rbx
0x18005d257  push    rsi
0x18005d258  push    rdi
0x18005d259  push    r14
0x18005d25b  mov     rbp, rsp
0x18005d25e  sub     rsp, 80h
0x18005d265  mov     rax, cs:__security_cookie
0x18005d26c  xor     rax, rsp
0x18005d26f  mov     [rbp+var_8], rax
0x18005d273  xor     r14d, r14d
0x18005d276  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x18005d27c  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18005d283  mov     [rbp+var_18], r14
0x18005d287  mov     dword ptr [rbp+IdentifierAuthority.Value], r14d
0x18005d28b  call    cs:__imp_LoadLibraryW
0x18005d292  nop     dword ptr [rax+rax+00h]
0x18005d297  mov     rdi, rax
0x18005d29a  test    rax, rax
0x18005d29d  jz      loc_18005D437
0x18005d2a3  lea     rdx, aChecktokenmemb_0; "CheckTokenMembership"
0x18005d2aa  mov     rcx, rax; hModule
0x18005d2ad  call    cs:__imp_GetProcAddress
0x18005d2b4  nop     dword ptr [rax+rax+00h]
0x18005d2b9  mov     rsi, rax
0x18005d2bc  test    rax, rax
0x18005d2bf  jz      loc_18005D423
0x18005d2c5  lea     rax, [rbp+var_18]
0x18005d2c9  mov     r9d, 220h; SubAuthority1
0x18005d2cf  mov     [rsp+80h+Sid], rax; Sid
0x18005d2d4  lea     r8d, [r14+20h]; SubAuthority0
0x18005d2d8  mov     [rsp+80h+SubAuthority7], r14d; SubAuthority7
0x18005d2dd  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18005d2e1  mov     [rsp+80h+SubAuthority6], r14d; SubAuthority6
0x18005d2e6  mov     dl, 2; SubAuthorityCount
0x18005d2e8  mov     [rsp+80h+SubAuthority5], r14d; SubAuthority5
0x18005d2ed  mov     [rsp+80h+SubAuthority4], r14d; SubAuthority4
0x18005d2f2  mov     [rsp+80h+SubAuthority3], r14d; SubAuthority3
0x18005d2f7  mov     [rsp+80h+SubAuthority2], r14d; SubAuthority2
0x18005d2fc  call    cs:__imp_RtlAllocateAndInitializeSid
0x18005d303  nop     dword ptr [rax+rax+00h]
0x18005d308  test    eax, eax
0x18005d30a  js      short loc_18005D347
0x18005d30c  mov     rdx, [rbp+var_18]
0x18005d310  lea     r8, [rbp+var_20]
0x18005d314  xor     ecx, ecx
0x18005d316  mov     [rbp+var_20], r14d
0x18005d31a  mov     rax, rsi
0x18005d31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d322  test    eax, eax
0x18005d324  jz      short loc_18005D363
0x18005d326  cmp     [rbp+var_20], r14d
0x18005d32a  jz      short loc_18005D340
0x18005d32c  xor     ecx, ecx; LastError
0x18005d32e  call    cs:__imp_RtlSetLastWin32Error
0x18005d335  nop     dword ptr [rax+rax+00h]
0x18005d33a  lea     ebx, [r14+1]
0x18005d33e  jmp     short loc_18005D366
0x18005d340  mov     ecx, 5
0x18005d345  jmp     short loc_18005D357
0x18005d347  mov     ecx, eax; Status
0x18005d349  call    cs:__imp_RtlNtStatusToDosError
0x18005d350  nop     dword ptr [rax+rax+00h]
0x18005d355  mov     ecx, eax; LastError
0x18005d357  call    cs:__imp_RtlSetLastWin32Error
0x18005d35e  nop     dword ptr [rax+rax+00h]
0x18005d363  mov     ebx, r14d
0x18005d366  mov     rcx, [rbp+var_18]; Sid
0x18005d36a  test    rcx, rcx
0x18005d36d  jz      short loc_18005D37F
0x18005d36f  call    cs:__imp_RtlFreeSid
0x18005d376  nop     dword ptr [rax+rax+00h]
0x18005d37b  mov     [rbp+var_18], r14
0x18005d37f  test    ebx, ebx
0x18005d381  jnz     loc_18005D426
0x18005d387  lea     rax, [rbp+var_18]
0x18005d38b  xor     r9d, r9d; SubAuthority1
0x18005d38e  mov     [rsp+80h+Sid], rax; Sid
0x18005d393  lea     r8d, [rbx+12h]; SubAuthority0
0x18005d397  mov     [rsp+80h+SubAuthority7], r14d; SubAuthority7
0x18005d39c  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18005d3a0  mov     [rsp+80h+SubAuthority6], r14d; SubAuthority6
0x18005d3a5  mov     dl, 1; SubAuthorityCount
0x18005d3a7  mov     [rsp+80h+SubAuthority5], r14d; SubAuthority5
0x18005d3ac  mov     [rsp+80h+SubAuthority4], r14d; SubAuthority4
0x18005d3b1  mov     [rsp+80h+SubAuthority3], r14d; SubAuthority3
0x18005d3b6  mov     [rsp+80h+SubAuthority2], r14d; SubAuthority2
0x18005d3bb  call    cs:__imp_RtlAllocateAndInitializeSid
0x18005d3c2  nop     dword ptr [rax+rax+00h]
0x18005d3c7  test    eax, eax
0x18005d3c9  js      short loc_18005D407
0x18005d3cb  mov     rdx, [rbp+var_18]
0x18005d3cf  lea     r8, [rbp+var_20]
0x18005d3d3  xor     ecx, ecx
0x18005d3d5  mov     [rbp+var_20], r14d
0x18005d3d9  mov     rax, rsi
0x18005d3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3e1  test    eax, eax
0x18005d3e3  jz      short loc_18005D423
0x18005d3e5  cmp     [rbp+var_20], r14d
0x18005d3e9  jz      short loc_18005D400
0x18005d3eb  xor     ecx, ecx; LastError
0x18005d3ed  call    cs:__imp_RtlSetLastWin32Error
0x18005d3f4  nop     dword ptr [rax+rax+00h]
0x18005d3f9  mov     ebx, 1
0x18005d3fe  jmp     short loc_18005D426
0x18005d400  mov     ecx, 5
0x18005d405  jmp     short loc_18005D417
0x18005d407  mov     ecx, eax; Status
0x18005d409  call    cs:__imp_RtlNtStatusToDosError
0x18005d410  nop     dword ptr [rax+rax+00h]
0x18005d415  mov     ecx, eax; LastError
0x18005d417  call    cs:__imp_RtlSetLastWin32Error
0x18005d41e  nop     dword ptr [rax+rax+00h]
0x18005d423  mov     ebx, r14d
0x18005d426  mov     rcx, rdi; hLibModule
0x18005d429  call    cs:__imp_FreeLibrary
0x18005d430  nop     dword ptr [rax+rax+00h]
0x18005d435  jmp     short loc_18005D43A
0x18005d437  mov     ebx, r14d
0x18005d43a  mov     rcx, [rbp+var_18]; Sid
0x18005d43e  test    rcx, rcx
0x18005d441  jz      short loc_18005D44F
0x18005d443  call    cs:__imp_RtlFreeSid
0x18005d44a  nop     dword ptr [rax+rax+00h]
0x18005d44f  mov     eax, ebx
0x18005d451  mov     rcx, [rbp+var_8]
0x18005d455  xor     rcx, rsp; StackCookie
0x18005d458  call    __security_check_cookie
0x18005d45d  add     rsp, 80h
0x18005d464  pop     r14
0x18005d466  pop     rdi
0x18005d467  pop     rsi
0x18005d468  pop     rbx
0x18005d469  pop     rbp
0x18005d46a  retn
```
