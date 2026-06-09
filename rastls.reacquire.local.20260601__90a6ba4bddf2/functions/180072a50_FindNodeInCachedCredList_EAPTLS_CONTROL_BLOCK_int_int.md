# FindNodeInCachedCredList(_EAPTLS_CONTROL_BLOCK *,int,int)

- ea: `0x180072a50`
- end: `0x180072dfb`
- name: `?FindNodeInCachedCredList@@YAPEAU_EAPTLS_CACHED_CREDS@@PEAU_EAPTLS_CONTROL_BLOCK@@HH@Z`
- size: `939`
- prototype: `struct _EAPTLS_CACHED_CREDS *__fastcall(struct _EAPTLS_CONTROL_BLOCK *, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025564`
- `0x1800542a0`
- `0x1800725cc`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180020320`
- `0x18002f38c`
- `0x1800356f4`
- `0x180038270`
- `0x180038e40`
- `0x180072a50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180072c19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180072c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072d92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072c9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072c9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072dcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072d72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072d72`

## pseudocode

```c
struct _EAPTLS_CACHED_CREDS *__fastcall FindNodeInCachedCredList(
        struct _EAPTLS_CONTROL_BLOCK *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  int v5; // r13d
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
  unsigned int *v7; // r12
  int v8; // edx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  _DWORD *v13; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v19; // [rsp+30h] [rbp-39h]
  DWORD ReturnLength; // [rsp+34h] [rbp-35h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-31h] BYREF
  __int128 TokenInformation; // [rsp+40h] [rbp-29h] BYREF
  __int128 v23; // [rsp+50h] [rbp-19h]
  __int128 v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+70h] [rbp+7h]

  v3 = g_pCachedCreds;
  v19 = a2;
  v5 = a3;
  v25 = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v23 = 0;
  v24 = 0;
  v6 = WPP_GLOBAL_Control;
  v7 = (unsigned int *)((char *)a1 + 4);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *v7, a2, a3);
    v6 = WPP_GLOBAL_Control;
  }
  v8 = *v7;
  if ( (*v7 & 4) != 0 )
  {
    if ( v6 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_56;
    v9 = 16;
    goto LABEL_6;
  }
  if ( (v8 & 0x400000) != 0 )
  {
    if ( v6 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_56;
    v9 = 17;
LABEL_6:
    WPP_SF_(*((_QWORD *)v6 + 2), v9, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids);
    goto LABEL_56;
  }
  if ( (v8 & 0x4000) != 0 )
    v10 = 2;
  else
    v10 = (v8 & 0x10000) != 0 ? 4 : 1;
  v11 = v10 | (16 * (*v7 & 1)) | ((*v7 & 0x400) != 0 ? 0x40 : 0) | ((*v7 & 0x1000 | (*v7 >> 1) & 0x4000) >> 9);
  if ( (v8 & 1) == 0 )
  {
    v12 = *((_QWORD *)a1 + 68);
    if ( v12 && (*(_BYTE *)(v12 + 8) & 1) == 0 )
      v11 |= 0x80u;
    if ( (v8 & 0x4000) != 0 && (v8 & 0x400) == 0 && v12 )
    {
      if ( (*(_BYTE *)(v12 + 8) & 0x20) != 0 )
      {
        v11 |= 0x100u;
      }
      else if ( (*(_DWORD *)(v12 + 8) & 0x200) != 0 )
      {
        v11 |= 0x200u;
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
    v11 |= *((_DWORD *)a1 + 158) != 0 ? 0x400 : 0;
  if ( !v3 )
    goto LABEL_57;
  while ( 1 )
  {
    v13 = v3 + 4;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids,
        (unsigned int)*v13);
    if ( (v11 & 0x10) == 0 && (unsigned int)_o__wcsicmp((char *)v3 + 92, (char *)a1 + 16) )
      goto LABEL_49;
    if ( v19 )
      break;
    if ( (v11 & 2) == 0 || (v11 & 0x10) != 0 )
    {
      if ( *v13 != v11 )
        goto LABEL_49;
      if ( !*((_DWORD *)v3 + 2) )
        goto LABEL_49;
      v17 = *((_QWORD *)a1 + 71);
      if ( !v17 || memcmp_0((char *)v3 + 12, (const void *)(v17 + 20), *((unsigned int *)v3 + 2)) )
        goto LABEL_49;
      goto LABEL_48;
    }
    if ( *v13 == v11 )
      goto LABEL_38;
LABEL_49:
    v3 = (_QWORD *)*v3;
    if ( !v3 )
      goto LABEL_57;
  }
  v11 |= 0x20u;
  if ( *v13 != v11 || !*((_QWORD *)a1 + 71) )
    goto LABEL_49;
LABEL_48:
  if ( !v3[7] )
    goto LABEL_49;
LABEL_38:
  if ( (*(_BYTE *)v7 & 1) == 0 && v5 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        v16 = 19;
        goto LABEL_43;
      }
      goto LABEL_56;
    }
    v25 = 0;
    TokenInformation = 0;
    v23 = 0;
    v24 = 0;
    if ( GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
    {
      if ( *((_QWORD *)&TokenInformation + 1) != v3[10] )
      {
        RemoveNodeFromCachedCredList(v3);
        goto LABEL_56;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        v16 = 20;
LABEL_43:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids, LastError);
      }
LABEL_56:
      v3 = 0;
    }
  }
LABEL_57:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (struct _EAPTLS_CACHED_CREDS *)v3;
}

```

## disassembly

```asm
0x180072a50  push    rbp
0x180072a52  push    rbx
0x180072a53  push    rsi
0x180072a54  push    rdi
0x180072a55  push    r12
0x180072a57  push    r13
0x180072a59  push    r14
0x180072a5b  push    r15
0x180072a5d  lea     rbp, [rsp-1Fh]
0x180072a62  sub     rsp, 88h
0x180072a69  mov     rax, cs:__security_cookie
0x180072a70  xor     rax, rsp
0x180072a73  mov     [rbp+57h+var_48], rax
0x180072a77  mov     rbx, cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x180072a7e  xorps   xmm0, xmm0
0x180072a81  mov     r15, rcx
0x180072a84  mov     [rbp+57h+var_90], edx
0x180072a87  xor     ecx, ecx
0x180072a89  mov     r13d, r8d
0x180072a8c  mov     [rbp+57h+var_50], rcx
0x180072a90  mov     [rbp+57h+var_8C], ecx
0x180072a93  mov     [rbp+57h+TokenHandle], rcx
0x180072a97  movups  [rbp+57h+TokenInformation], xmm0
0x180072a9b  movups  [rbp+57h+var_70], xmm0
0x180072a9f  movups  [rbp+57h+var_60], xmm0
0x180072aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180072aaa  lea     r14, WPP_GLOBAL_Control
0x180072ab1  lea     r12, [r15+4]
0x180072ab5  cmp     rcx, r14
0x180072ab8  jz      short loc_180072AD7
0x180072aba  mov     r9d, [r12]
0x180072abe  mov     rcx, [rcx+10h]
0x180072ac2  mov     [rsp+0C0h+var_98], r8d
0x180072ac7  mov     dword ptr [rsp+0C0h+ReturnLength], edx
0x180072acb  call    WPP_SF_Ddd
0x180072ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ad7  mov     edx, [r12]
0x180072adb  test    dl, 4
0x180072ade  jz      short loc_180072B03
0x180072ae0  cmp     rcx, r14
0x180072ae3  jz      loc_180072DC0
0x180072ae9  mov     edx, 10h
0x180072aee  mov     rcx, [rcx+10h]
0x180072af2  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x180072af9  call    WPP_SF_
0x180072afe  jmp     loc_180072DC0
0x180072b03  bt      edx, 16h
0x180072b07  jnb     short loc_180072B19
0x180072b09  cmp     rcx, r14
0x180072b0c  jz      loc_180072DC0
0x180072b12  mov     edx, 11h
0x180072b17  jmp     short loc_180072AEE
0x180072b19  mov     r10d, 4000h
0x180072b1f  mov     edi, edx
0x180072b21  shr     edi, 1
0x180072b23  mov     eax, edx
0x180072b25  and     edi, r10d
0x180072b28  and     eax, 1000h
0x180072b2d  or      edi, eax
0x180072b2f  mov     r9d, edx
0x180072b32  shr     edi, 9
0x180072b35  mov     esi, 400h
0x180072b3a  and     r9d, esi
0x180072b3d  mov     r8d, edx
0x180072b40  and     r8d, 1
0x180072b44  mov     eax, r9d
0x180072b47  neg     eax
0x180072b49  mov     eax, r8d
0x180072b4c  sbb     ecx, ecx
0x180072b4e  shl     eax, 4
0x180072b51  and     ecx, 40h
0x180072b54  or      edi, ecx
0x180072b56  mov     ecx, edx
0x180072b58  or      edi, eax
0x180072b5a  and     ecx, r10d
0x180072b5d  jz      short loc_180072B66
0x180072b5f  mov     eax, 2
0x180072b64  jmp     short loc_180072B75
0x180072b66  and     edx, 10000h
0x180072b6c  neg     edx
0x180072b6e  sbb     eax, eax
0x180072b70  and     eax, 3
0x180072b73  inc     eax
0x180072b75  or      edi, eax
0x180072b77  test    r8d, r8d
0x180072b7a  jnz     short loc_180072BB8
0x180072b7c  mov     rax, [r15+220h]
0x180072b83  test    rax, rax
0x180072b86  jz      short loc_180072B92
0x180072b88  test    byte ptr [rax+8], 1
0x180072b8c  jnz     short loc_180072B92
0x180072b8e  bts     edi, 7
0x180072b92  test    ecx, ecx
0x180072b94  jz      short loc_180072BB8
0x180072b96  test    r9d, r9d
0x180072b99  jnz     short loc_180072BB8
0x180072b9b  test    rax, rax
0x180072b9e  jz      short loc_180072BB8
0x180072ba0  test    byte ptr [rax+8], 20h
0x180072ba4  jz      short loc_180072BAC
0x180072ba6  bts     edi, 8
0x180072baa  jmp     short loc_180072BB8
0x180072bac  mov     ecx, 200h
0x180072bb1  test    [rax+8], ecx
0x180072bb4  jz      short loc_180072BB8
0x180072bb6  or      edi, ecx
0x180072bb8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x180072bbf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x180072bc4  test    al, al
0x180072bc6  jz      short loc_180072BD7
0x180072bc8  xor     eax, eax
0x180072bca  cmp     eax, [r15+278h]
0x180072bd1  sbb     eax, eax
0x180072bd3  and     eax, esi
0x180072bd5  or      edi, eax
0x180072bd7  test    rbx, rbx
0x180072bda  jz      loc_180072DC2
0x180072be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180072be7  lea     rsi, [rbx+20h]
0x180072beb  cmp     rcx, r14
0x180072bee  jz      short loc_180072C08
0x180072bf0  mov     r9d, [rsi]
0x180072bf3  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x180072bfa  mov     rcx, [rcx+10h]
0x180072bfe  mov     edx, 12h
0x180072c03  call    WPP_SF_d
0x180072c08  mov     r14d, edi
0x180072c0b  and     r14d, 10h
0x180072c0f  jnz     short loc_180072C2D
0x180072c11  lea     rdx, [r15+10h]
0x180072c15  lea     rcx, [rbx+5Ch]
0x180072c19  call    cs:__imp__o__wcsicmp
0x180072c20  nop     dword ptr [rax+rax+00h]
0x180072c25  test    eax, eax
0x180072c27  jnz     loc_180072D2A
0x180072c2d  cmp     [rbp+57h+var_90], 0
0x180072c31  jz      short loc_180072C51
0x180072c33  or      edi, 20h
0x180072c36  cmp     [rsi], edi
0x180072c38  jnz     loc_180072D2A
0x180072c3e  cmp     qword ptr [r15+238h], 0
0x180072c46  jz      loc_180072D2A
0x180072c4c  jmp     loc_180072D1F
0x180072c51  test    dil, 2
0x180072c55  jz      loc_180072CF4
0x180072c5b  test    r14d, r14d
0x180072c5e  jnz     loc_180072CF4
0x180072c64  cmp     [rsi], edi
0x180072c66  jnz     loc_180072D2A
0x180072c6c  test    byte ptr [r12], 1
0x180072c71  jnz     loc_180072DC2
0x180072c77  test    r13d, r13d
0x180072c7a  jz      loc_180072DC2
0x180072c80  call    cs:__imp_GetCurrentThread
0x180072c87  nop     dword ptr [rax+rax+00h]
0x180072c8c  mov     edx, 8; DesiredAccess
0x180072c91  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180072c95  mov     rcx, rax; ThreadHandle
0x180072c98  lea     r8d, [rdx-7]; OpenAsSelf
0x180072c9c  call    cs:__imp_OpenThreadToken
0x180072ca3  nop     dword ptr [rax+rax+00h]
0x180072ca8  test    eax, eax
0x180072caa  jnz     loc_180072D42
0x180072cb0  lea     rax, WPP_GLOBAL_Control
0x180072cb7  cmp     cs:WPP_GLOBAL_Control, rax
0x180072cbe  jz      loc_180072DC0
0x180072cc4  call    cs:__imp_GetLastError
0x180072ccb  nop     dword ptr [rax+rax+00h]
0x180072cd0  mov     edx, 13h
0x180072cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180072cdc  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x180072ce3  mov     r9d, eax
0x180072ce6  mov     rcx, [rcx+10h]
0x180072cea  call    WPP_SF_d
0x180072cef  jmp     loc_180072DC0
0x180072cf4  cmp     [rsi], edi
0x180072cf6  jnz     short loc_180072D2A
0x180072cf8  cmp     dword ptr [rbx+8], 0
0x180072cfc  jz      short loc_180072D2A
0x180072cfe  mov     rdx, [r15+238h]
0x180072d05  test    rdx, rdx
0x180072d08  jz      short loc_180072D2A
0x180072d0a  mov     r8d, [rbx+8]; Size
0x180072d0e  lea     rcx, [rbx+0Ch]; Buf1
0x180072d12  add     rdx, 14h; Buf2
0x180072d16  call    memcmp_0
0x180072d1b  test    eax, eax
0x180072d1d  jnz     short loc_180072D2A
0x180072d1f  cmp     qword ptr [rbx+38h], 0
0x180072d24  jnz     loc_180072C6C
0x180072d2a  mov     rbx, [rbx]
0x180072d2d  test    rbx, rbx
0x180072d30  jz      loc_180072DC2
0x180072d36  lea     r14, WPP_GLOBAL_Control
0x180072d3d  jmp     loc_180072BE0
0x180072d42  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180072d46  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180072d4a  xorps   xmm0, xmm0
0x180072d4d  xor     eax, eax
0x180072d4f  mov     r9d, 38h ; '8'; TokenInformationLength
0x180072d55  mov     [rbp+57h+var_50], rax
0x180072d59  lea     rax, [rbp+57h+var_8C]
0x180072d5d  movups  [rbp+57h+TokenInformation], xmm0
0x180072d61  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180072d66  lea     edx, [r9-2Eh]; TokenInformationClass
0x180072d6a  movups  [rbp+57h+var_70], xmm0
0x180072d6e  movups  [rbp+57h+var_60], xmm0
0x180072d72  call    cs:__imp_GetTokenInformation
0x180072d79  nop     dword ptr [rax+rax+00h]
0x180072d7e  test    eax, eax
0x180072d80  jnz     short loc_180072DA8
0x180072d82  lea     rax, WPP_GLOBAL_Control
0x180072d89  cmp     cs:WPP_GLOBAL_Control, rax
0x180072d90  jz      short loc_180072DC0
0x180072d92  call    cs:__imp_GetLastError
0x180072d99  nop     dword ptr [rax+rax+00h]
0x180072d9e  mov     edx, 14h
0x180072da3  jmp     loc_180072CD5
0x180072da8  mov     eax, [rbx+50h]
0x180072dab  cmp     dword ptr [rbp+57h+TokenInformation+8], eax
0x180072dae  jnz     short loc_180072DB8
0x180072db0  mov     eax, [rbx+54h]
0x180072db3  cmp     dword ptr [rbp+57h+TokenInformation+0Ch], eax
0x180072db6  jz      short loc_180072DC2
0x180072db8  mov     rcx, rbx; hMem
0x180072dbb  call    ?RemoveNodeFromCachedCredList@@YAKPEAU_EAPTLS_CACHED_CREDS@@@Z; RemoveNodeFromCachedCredList(_EAPTLS_CACHED_CREDS *)
0x180072dc0  xor     ebx, ebx
0x180072dc2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180072dc6  test    rcx, rcx
0x180072dc9  jz      short loc_180072DD7
0x180072dcb  call    cs:__imp_CloseHandle
0x180072dd2  nop     dword ptr [rax+rax+00h]
0x180072dd7  mov     rax, rbx
0x180072dda  mov     rcx, [rbp+57h+var_48]
0x180072dde  xor     rcx, rsp; StackCookie
0x180072de1  call    __security_check_cookie
0x180072de6  add     rsp, 88h
0x180072ded  pop     r15
0x180072def  pop     r14
0x180072df1  pop     r13
0x180072df3  pop     r12
0x180072df5  pop     rdi
0x180072df6  pop     rsi
0x180072df7  pop     rbx
0x180072df8  pop     rbp
0x180072df9  retn
```
