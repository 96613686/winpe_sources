# GetPinFromUserProperties(_EAPTLS_USER_PROPERTIES *,ushort * *,ulong *,void *)

- ea: `0x18005f1f0`
- end: `0x18005f545`
- name: `?GetPinFromUserProperties@@YAKPEAU_EAPTLS_USER_PROPERTIES@@PEAPEAGPEAKPEAX@Z`
- size: `853`
- prototype: `unsigned int(struct _EAPTLS_USER_PROPERTIES *, unsigned __int16 **, unsigned int *, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055208`
- `0x18005c0c0`
- `0x18005c31c`

## callees

- `0x180005010`
- `0x1800370bc`
- `0x18005ed88`
- `0x18005f1f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f492`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005f492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f33b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f33b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f467`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f371`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f453`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f371`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f453`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f4cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f4fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f4cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f4fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005f2d8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005f2d8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005f3e4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005f3e4`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18005f28f`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18005f28f`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005f324`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005f3bf`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005f324`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005f3bf`

## pseudocode

```c
__int64 __fastcall GetPinFromUserProperties(
        struct _EAPTLS_USER_PROPERTIES *a1,
        unsigned __int16 **a2,
        unsigned int *a3,
        void *a4)
{
  WCHAR *v5; // rsi
  unsigned int PinLengthInBytes; // eax
  __int64 v8; // r10
  unsigned __int8 v9; // r8
  unsigned int *v10; // r9
  DWORD InfoFromCredBuffer; // eax
  WCHAR *v12; // r14
  DWORD v13; // ebx
  __int64 v14; // r15
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rax
  WCHAR *v18; // rdx
  __int64 i; // rax
  WCHAR *v20; // rcx
  __int64 j; // rax
  unsigned __int16 **pcchMaxChars; // [rsp+20h] [rbp-40h]
  unsigned int *v24; // [rsp+28h] [rbp-38h]
  unsigned __int16 **v25; // [rsp+30h] [rbp-30h]
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+50h] [rbp-10h] BYREF
  DWORD cchProtectedCredentials; // [rsp+54h] [rbp-Ch] BYREF
  LPWSTR pszProtectedCredentials; // [rsp+58h] [rbp-8h] BYREF
  DWORD v29; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 **v30; // [rsp+A8h] [rbp+48h]

  v30 = a2;
  pszProtectedCredentials = 0;
  v5 = 0;
  cchProtectedCredentials = 0;
  pProtectionType = CredUnprotected;
  v29 = 0;
  PinLengthInBytes = GetPinLengthInBytes(a1);
  InfoFromCredBuffer = GetInfoFromCredBuffer(
                         PinLengthInBytes,
                         *(unsigned __int8 **)(v8 + 56),
                         v9,
                         v10,
                         pcchMaxChars,
                         v24,
                         v25,
                         &cchProtectedCredentials,
                         &pszProtectedCredentials);
  v12 = pszProtectedCredentials;
  v13 = InfoFromCredBuffer;
  v14 = cchProtectedCredentials;
  if ( InfoFromCredBuffer )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v16 = 22;
    goto LABEL_4;
  }
  if ( !CredIsProtectedW(pszProtectedCredentials, &pProtectionType) )
  {
    v29 = v14;
    v17 = (WCHAR *)LocalAlloc(0x40u, 2 * v14);
    v5 = v17;
    if ( !v17 )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 29;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
    _o_wcscpy_s(v17, v29, v12);
    goto LABEL_31;
  }
  cchProtectedCredentials = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids,
      (unsigned int)pProtectionType);
  if ( pProtectionType == CredTrustedProtection && !RevertToSelf() )
  {
    InfoFromCredBuffer = GetLastError();
    v13 = InfoFromCredBuffer;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v16 = 24;
LABEL_4:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, InfoFromCredBuffer);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( CredUnprotectW(0, v12, v14, 0, &v29) || v29 )
  {
    cchProtectedCredentials = v29;
    v5 = (WCHAR *)LocalAlloc(0x40u, 2LL * v29);
    if ( !v5 )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 26;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
    if ( !CredUnprotectW(0, v12, v14, v5, &cchProtectedCredentials) || cchProtectedCredentials > v29 )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 27;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
    if ( pProtectionType == CredTrustedProtection && !ImpersonateLoggedOnUser(a4) )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 28;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
LABEL_31:
    *v30 = v5;
    *a3 = v29;
    goto LABEL_32;
  }
  InfoFromCredBuffer = GetLastError();
  v13 = InfoFromCredBuffer;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v16 = 25;
    goto LABEL_4;
  }
LABEL_32:
  if ( v12 )
  {
    v18 = v12;
    for ( i = 2 * v14; i; --i )
    {
      *(_BYTE *)v18 = 0;
      v18 = (WCHAR *)((char *)v18 + 1);
    }
    LocalFree(v12);
  }
  if ( v13 && v5 )
  {
    v20 = v5;
    for ( j = 2LL * v29; j; --j )
    {
      *(_BYTE *)v20 = 0;
      v20 = (WCHAR *)((char *)v20 + 1);
    }
    LocalFree(v5);
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18005f1f0  mov     [rsp-38h+arg_10], rbx
0x18005f1f5  mov     [rsp-38h+arg_8], rdx
0x18005f1fa  push    rbp
0x18005f1fb  push    rsi
0x18005f1fc  push    rdi
0x18005f1fd  push    r12
0x18005f1ff  push    r13
0x18005f201  push    r14
0x18005f203  push    r15
0x18005f205  mov     rbp, rsp
0x18005f208  sub     rsp, 60h
0x18005f20c  xor     edi, edi
0x18005f20e  mov     r12, r9
0x18005f211  mov     [rbp+pszProtectedCredentials], rdi
0x18005f215  mov     esi, edi
0x18005f217  mov     [rbp+cchProtectedCredentials], edi
0x18005f21a  mov     r13, r8
0x18005f21d  mov     [rbp+pProtectionType], edi
0x18005f220  mov     r10, rcx
0x18005f223  mov     [rbp+arg_0], edi
0x18005f226  call    ?GetPinLengthInBytes@@YAKPEBU_EAPTLS_USER_PROPERTIES@@@Z; GetPinLengthInBytes(_EAPTLS_USER_PROPERTIES const *)
0x18005f22b  mov     rdx, [r10+38h]; unsigned __int8 *
0x18005f22f  mov     ecx, eax; unsigned int
0x18005f231  lea     rax, [rbp+pszProtectedCredentials]
0x18005f235  mov     [rsp+60h+var_20], rax; unsigned __int16 **
0x18005f23a  lea     rax, [rbp+cchProtectedCredentials]
0x18005f23e  mov     [rsp+60h+var_28], rax; unsigned int *
0x18005f243  call    ?GetInfoFromCredBuffer@@YAKKPEAEEPEAKPEAPEAG1212@Z; GetInfoFromCredBuffer(ulong,uchar *,uchar,ulong *,ushort * *,ulong *,ushort * *,ulong *,ushort * *)
0x18005f248  mov     r14, [rbp+pszProtectedCredentials]
0x18005f24c  mov     ebx, eax
0x18005f24e  mov     r15d, [rbp+cchProtectedCredentials]
0x18005f252  test    eax, eax
0x18005f254  jz      short loc_18005F288
0x18005f256  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f25d  lea     rdi, WPP_GLOBAL_Control
0x18005f264  cmp     rcx, rdi
0x18005f267  jz      loc_18005F4AC
0x18005f26d  lea     edx, [rsi+16h]
0x18005f270  mov     rcx, [rcx+10h]
0x18005f274  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005f27b  mov     r9d, eax
0x18005f27e  call    WPP_SF_d
0x18005f283  jmp     loc_18005F4AC
0x18005f288  lea     rdx, [rbp+pProtectionType]; pProtectionType
0x18005f28c  mov     rcx, r14; pszProtectedCredentials
0x18005f28f  call    cs:__imp_CredIsProtectedW
0x18005f296  nop     dword ptr [rax+rax+00h]
0x18005f29b  lea     rdi, WPP_GLOBAL_Control
0x18005f2a2  test    eax, eax
0x18005f2a4  jz      loc_18005F444
0x18005f2aa  mov     [rbp+cchProtectedCredentials], esi
0x18005f2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f2b4  cmp     rcx, rdi
0x18005f2b7  jz      short loc_18005F2D2
0x18005f2b9  mov     r9d, [rbp+pProtectionType]
0x18005f2bd  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005f2c4  mov     rcx, [rcx+10h]
0x18005f2c8  mov     edx, 17h
0x18005f2cd  call    WPP_SF_d
0x18005f2d2  cmp     [rbp+pProtectionType], 2
0x18005f2d6  jnz     short loc_18005F310
0x18005f2d8  call    cs:__imp_RevertToSelf
0x18005f2df  nop     dword ptr [rax+rax+00h]
0x18005f2e4  test    eax, eax
0x18005f2e6  jnz     short loc_18005F310
0x18005f2e8  call    cs:__imp_GetLastError
0x18005f2ef  nop     dword ptr [rax+rax+00h]
0x18005f2f4  mov     ebx, eax
0x18005f2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f2fd  cmp     rcx, rdi
0x18005f300  jz      loc_18005F4AC
0x18005f306  mov     edx, 18h
0x18005f30b  jmp     loc_18005F270
0x18005f310  lea     rax, [rbp+arg_0]
0x18005f314  xor     r9d, r9d; pszCredentials
0x18005f317  mov     r8d, r15d; cchProtectedCredentials
0x18005f31a  mov     [rsp+60h+pcchMaxChars], rax; pcchMaxChars
0x18005f31f  mov     rdx, r14; pszProtectedCredentials
0x18005f322  xor     ecx, ecx; fAsSelf
0x18005f324  call    cs:__imp_CredUnprotectW
0x18005f32b  nop     dword ptr [rax+rax+00h]
0x18005f330  mov     ecx, [rbp+arg_0]
0x18005f333  test    eax, eax
0x18005f335  jnz     short loc_18005F363
0x18005f337  test    ecx, ecx
0x18005f339  jnz     short loc_18005F363
0x18005f33b  call    cs:__imp_GetLastError
0x18005f342  nop     dword ptr [rax+rax+00h]
0x18005f347  mov     ebx, eax
0x18005f349  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f350  cmp     rcx, rdi
0x18005f353  jz      loc_18005F4AC
0x18005f359  mov     edx, 19h
0x18005f35e  jmp     loc_18005F270
0x18005f363  mov     rdx, rcx
0x18005f366  mov     [rbp+cchProtectedCredentials], ecx
0x18005f369  add     rdx, rdx; uBytes
0x18005f36c  mov     ecx, 40h ; '@'; uFlags
0x18005f371  call    cs:__imp_LocalAlloc
0x18005f378  nop     dword ptr [rax+rax+00h]
0x18005f37d  mov     rsi, rax
0x18005f380  test    rax, rax
0x18005f383  jnz     short loc_18005F3AB
0x18005f385  call    cs:__imp_GetLastError
0x18005f38c  nop     dword ptr [rax+rax+00h]
0x18005f391  mov     ebx, eax
0x18005f393  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f39a  cmp     rcx, rdi
0x18005f39d  jz      loc_18005F4AC
0x18005f3a3  lea     edx, [rsi+1Ah]
0x18005f3a6  jmp     loc_18005F270
0x18005f3ab  lea     rax, [rbp+cchProtectedCredentials]
0x18005f3af  mov     r9, rsi; pszCredentials
0x18005f3b2  mov     r8d, r15d; cchProtectedCredentials
0x18005f3b5  mov     [rsp+60h+pcchMaxChars], rax; pcchMaxChars
0x18005f3ba  mov     rdx, r14; pszProtectedCredentials
0x18005f3bd  xor     ecx, ecx; fAsSelf
0x18005f3bf  call    cs:__imp_CredUnprotectW
0x18005f3c6  nop     dword ptr [rax+rax+00h]
0x18005f3cb  test    eax, eax
0x18005f3cd  jz      short loc_18005F420
0x18005f3cf  mov     eax, [rbp+arg_0]
0x18005f3d2  cmp     [rbp+cchProtectedCredentials], eax
0x18005f3d5  ja      short loc_18005F420
0x18005f3d7  cmp     [rbp+pProtectionType], 2
0x18005f3db  jnz     loc_18005F49E
0x18005f3e1  mov     rcx, r12; hToken
0x18005f3e4  call    cs:__imp_ImpersonateLoggedOnUser
0x18005f3eb  nop     dword ptr [rax+rax+00h]
0x18005f3f0  test    eax, eax
0x18005f3f2  jnz     loc_18005F49E
0x18005f3f8  call    cs:__imp_GetLastError
0x18005f3ff  nop     dword ptr [rax+rax+00h]
0x18005f404  mov     ebx, eax
0x18005f406  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f40d  cmp     rcx, rdi
0x18005f410  jz      loc_18005F4AC
0x18005f416  mov     edx, 1Ch
0x18005f41b  jmp     loc_18005F270
0x18005f420  call    cs:__imp_GetLastError
0x18005f427  nop     dword ptr [rax+rax+00h]
0x18005f42c  mov     ebx, eax
0x18005f42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f435  cmp     rcx, rdi
0x18005f438  jz      short loc_18005F4AC
0x18005f43a  mov     edx, 1Bh
0x18005f43f  jmp     loc_18005F270
0x18005f444  mov     rdx, r15
0x18005f447  mov     [rbp+arg_0], r15d
0x18005f44b  add     rdx, rdx; uBytes
0x18005f44e  mov     ecx, 40h ; '@'; uFlags
0x18005f453  call    cs:__imp_LocalAlloc
0x18005f45a  nop     dword ptr [rax+rax+00h]
0x18005f45f  mov     rsi, rax
0x18005f462  test    rax, rax
0x18005f465  jnz     short loc_18005F489
0x18005f467  call    cs:__imp_GetLastError
0x18005f46e  nop     dword ptr [rax+rax+00h]
0x18005f473  mov     ebx, eax
0x18005f475  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f47c  cmp     rcx, rdi
0x18005f47f  jz      short loc_18005F4AC
0x18005f481  lea     edx, [rsi+1Dh]
0x18005f484  jmp     loc_18005F270
0x18005f489  mov     edx, [rbp+arg_0]
0x18005f48c  mov     r8, r14
0x18005f48f  mov     rcx, rax
0x18005f492  call    cs:__imp__o_wcscpy_s
0x18005f499  nop     dword ptr [rax+rax+00h]
0x18005f49e  mov     rax, [rbp+arg_8]
0x18005f4a2  mov     [rax], rsi
0x18005f4a5  mov     eax, [rbp+arg_0]
0x18005f4a8  mov     [r13+0], eax
0x18005f4ac  test    r14, r14
0x18005f4af  jz      short loc_18005F4D7
0x18005f4b1  mov     rax, r15
0x18005f4b4  mov     rdx, r14
0x18005f4b7  add     rax, rax
0x18005f4ba  jz      short loc_18005F4C8
0x18005f4bc  mov     byte ptr [rdx], 0
0x18005f4bf  inc     rdx
0x18005f4c2  sub     rax, 1
0x18005f4c6  jnz     short loc_18005F4BC
0x18005f4c8  mov     rcx, r14; hMem
0x18005f4cb  call    cs:__imp_LocalFree
0x18005f4d2  nop     dword ptr [rax+rax+00h]
0x18005f4d7  test    ebx, ebx
0x18005f4d9  jz      short loc_18005F506
0x18005f4db  test    rsi, rsi
0x18005f4de  jz      short loc_18005F506
0x18005f4e0  mov     eax, [rbp+arg_0]
0x18005f4e3  mov     rcx, rsi
0x18005f4e6  add     rax, rax
0x18005f4e9  jz      short loc_18005F4F7
0x18005f4eb  mov     byte ptr [rcx], 0
0x18005f4ee  inc     rcx
0x18005f4f1  sub     rax, 1
0x18005f4f5  jnz     short loc_18005F4EB
0x18005f4f7  mov     rcx, rsi; hMem
0x18005f4fa  call    cs:__imp_LocalFree
0x18005f501  nop     dword ptr [rax+rax+00h]
0x18005f506  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f50d  cmp     rcx, rdi
0x18005f510  jz      short loc_18005F52A
0x18005f512  mov     rcx, [rcx+10h]
0x18005f516  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005f51d  mov     edx, 1Eh
0x18005f522  mov     r9d, ebx
0x18005f525  call    WPP_SF_d
0x18005f52a  mov     eax, ebx
0x18005f52c  mov     rbx, [rsp+60h+arg_10]
0x18005f534  add     rsp, 60h
0x18005f538  pop     r15
0x18005f53a  pop     r14
0x18005f53c  pop     r13
0x18005f53e  pop     r12
0x18005f540  pop     rdi
0x18005f541  pop     rsi
0x18005f542  pop     rbp
0x18005f543  retn
```
