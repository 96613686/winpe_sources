# GetEapCredentialsInputType

- ea: `0x180007288`
- end: `0x180007849`
- name: `GetEapCredentialsInputType`
- size: `1473`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180001a80`
- `0x180005b90`

## callees

- `0x1800056d4`
- `0x180007288`
- `0x180007850`
- `0x180007f6c`
- `0x180008330`
- `0x180008518`
- `0x180008540`
- `0x1800085cc`
- `0x180008638`

## import_xrefs

- `eappcfg!EapHostPeerQueryCredentialInputFields` at `0x1800073d9`
- `eappcfg!EapHostPeerQueryCredentialInputFields` at `0x1800073d9`
- `eappcfg!EapHostPeerFreeMemory` at `0x1800077d4`
- `eappcfg!EapHostPeerFreeMemory` at `0x1800077e3`
- `eappcfg!EapHostPeerFreeMemory` at `0x1800077f4`
- `eappcfg!EapHostPeerFreeMemory` at `0x1800077d4`
- `eappcfg!EapHostPeerFreeMemory` at `0x1800077e3`
- `eappcfg!EapHostPeerFreeMemory` at `0x1800077f4`

## pseudocode

```c
__int64 __fastcall GetEapCredentialsInputType(
        unsigned int a1,
        const BYTE *a2,
        const GUID *a3,
        _DWORD *a4,
        __int64 a5,
        unsigned int cchDest,
        STRSAFE_LPWSTR pszDest)
{
  DWORD v8; // edi
  _QWORD *v11; // r10
  DWORD v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r9
  DWORD EapMethodTypeFromEapType; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // eax
  int v20; // ebx
  int v21; // edi
  int v22; // r12d
  int v23; // r13d
  __int64 v24; // rsi
  EAP_CONFIG_INPUT_FIELD_DATA *pFields; // rdi
  EAP_CONFIG_INPUT_FIELD_TYPE Type; // ecx
  __int32 v27; // ecx
  __int32 v28; // ecx
  int v29; // ecx
  int v30; // ecx
  __int64 v31; // rdx
  const wchar_t *pwszData; // r8
  __int64 i; // rdi
  int pbEapConnData; // [rsp+20h] [rbp-61h]
  int pEapConfigInputFieldArray; // [rsp+28h] [rbp-59h]
  int ppEapError; // [rsp+30h] [rbp-51h]
  int v38; // [rsp+40h] [rbp-41h]
  int v39; // [rsp+44h] [rbp-3Dh]
  EAP_ERROR *pEapError; // [rsp+50h] [rbp-31h] BYREF
  EAP_CONFIG_INPUT_FIELD_ARRAY v41; // [rsp+58h] [rbp-29h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+70h] [rbp-11h] BYREF
  int v44; // [rsp+F0h] [rbp+6Fh]

  v8 = (unsigned int)a3;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, a3, a1);
    v11 = WPP_GLOBAL_Control;
  }
  pEapError = 0;
  eapMethodType = 0;
  v41 = 0;
  if ( !a4 )
  {
    v12 = 87;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 2u )
    {
      v13 = 34;
LABEL_10:
      v14 = v12;
LABEL_11:
      WPP_SF_d(v11[2], v13, a3, v14);
LABEL_107:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_108;
    }
    goto LABEL_108;
  }
  if ( pszDest )
  {
    *pszDest = 0;
    v11 = WPP_GLOBAL_Control;
  }
  *a4 = 0;
  if ( !a1 )
  {
    v12 = 0;
    v15 = 2;
    goto LABEL_103;
  }
  EapMethodTypeFromEapType = RasGetEapMethodTypeFromEapType(a1, &eapMethodType);
  v12 = EapMethodTypeFromEapType;
  if ( EapMethodTypeFromEapType )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 35;
      v14 = EapMethodTypeFromEapType;
      goto LABEL_11;
    }
    goto LABEL_108;
  }
  v12 = EapHostPeerQueryCredentialInputFields(0, &eapMethodType, 0, v8, a2, &v41, &pEapError);
  RasFreeEapConfigErrorMemory(pEapError);
  if ( !v12 )
  {
    v11 = WPP_GLOBAL_Control;
    v19 = 0;
    v20 = 0;
    v39 = 0;
    v21 = 0;
    v44 = 0;
    v22 = 0;
    v38 = 0;
    v23 = 0;
    v24 = 0;
    if ( !v41.dwNumberOfFields )
    {
LABEL_47:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        LOBYTE(v17) = v20 != 0;
        LOBYTE(ppEapError) = v20 != 0;
        LOBYTE(pEapConfigInputFieldArray) = v19 != 0;
        LOBYTE(pbEapConnData) = v23 != 0;
        LOBYTE(v18) = v22 != 0;
        WPP_SF_cccc(v11[2], v17, a3, v18, pbEapConnData, pEapConfigInputFieldArray, ppEapError);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v22 && v23 || v39 && v20 )
        v15 = 2;
      else
        v15 = v21 != 0;
LABEL_103:
      *a4 = v15;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        WPP_SF_d(v11[2], 49, a3, v15);
        goto LABEL_107;
      }
      goto LABEL_108;
    }
    while ( 1 )
    {
      pFields = v41.pFields;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        WPP_SF_dd(
          v11[2],
          v17,
          &WPP_ef60fab923f6309b270ef1145867690a_Traceguids,
          (unsigned int)v41.pFields[v24].Type,
          v24);
        v11 = WPP_GLOBAL_Control;
      }
      Type = pFields[v24].Type;
      if ( Type )
      {
        v27 = Type - 1;
        if ( !v27 )
        {
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
          {
            WPP_SF_(v11[2], 43, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
          v19 = v39;
          v20 = 1;
          v21 = v38;
          v44 = 1;
          goto LABEL_46;
        }
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( !v29 )
          {
            if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
            {
              WPP_SF_(v11[2], 40, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
              v11 = WPP_GLOBAL_Control;
            }
            v23 = 1;
            goto LABEL_43;
          }
          v30 = v29 - 1;
          if ( !v30 )
          {
            if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
            {
              WPP_SF_(v11[2], 46, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
              v11 = WPP_GLOBAL_Control;
            }
            v19 = v39;
            v21 = 1;
            v38 = 1;
            goto LABEL_45;
          }
          if ( v30 == 3 )
          {
            if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
            {
              WPP_SF_(v11[2], 44, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
              v11 = WPP_GLOBAL_Control;
            }
            if ( pszDest )
            {
              pwszData = pFields[v24].pwszData;
              if ( pwszData )
                goto LABEL_62;
            }
            if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 2) == 0 || *((_BYTE *)v11 + 25) < 5u )
              goto LABEL_43;
            v31 = 45;
          }
          else
          {
            if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 2) == 0 || *((_BYTE *)v11 + 25) < 5u )
              goto LABEL_43;
            v31 = 47;
          }
        }
        else
        {
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
          {
            WPP_SF_(v11[2], 38, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
          v22 = 1;
          if ( pszDest )
          {
            pwszData = pFields[v24].pwszData;
            if ( pwszData )
              goto LABEL_62;
          }
          if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 2) == 0 || *((_BYTE *)v11 + 25) < 5u )
            goto LABEL_43;
          v31 = 39;
        }
      }
      else
      {
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        {
          WPP_SF_(v11[2], 41, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
          v11 = WPP_GLOBAL_Control;
        }
        v19 = 1;
        v39 = 1;
        if ( pszDest )
        {
          pwszData = pFields[v24].pwszData;
          if ( pwszData )
          {
LABEL_62:
            StringCchCopyW(pszDest, cchDest, pwszData);
            goto LABEL_42;
          }
        }
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 2) == 0 || *((_BYTE *)v11 + 25) < 5u )
          goto LABEL_44;
        v31 = 42;
      }
      WPP_SF_(v11[2], v31, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
LABEL_42:
      v11 = WPP_GLOBAL_Control;
LABEL_43:
      v19 = v39;
LABEL_44:
      v21 = v38;
LABEL_45:
      v20 = v44;
LABEL_46:
      v24 = (unsigned int)(v24 + 1);
      a3 = &WPP_ef60fab923f6309b270ef1145867690a_Traceguids;
      if ( (unsigned int)v24 >= v41.dwNumberOfFields )
        goto LABEL_47;
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 36;
    goto LABEL_10;
  }
LABEL_108:
  if ( v41.pFields )
  {
    for ( i = 0; (unsigned int)i < v41.dwNumberOfFields; i = (unsigned int)(i + 1) )
    {
      EapHostPeerFreeMemory((BYTE *)v41.pFields[i].pwszData);
      EapHostPeerFreeMemory((BYTE *)v41.pFields[i].pwszLabel);
    }
    EapHostPeerFreeMemory((BYTE *)v41.pFields);
    v11 = WPP_GLOBAL_Control;
    v41.pFields = 0;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 50, a3, v12);
  return MapEapHostErrorToRasError(v12);
}

```

## disassembly

```asm
0x180007288  mov     [rsp-8+arg_18], r9
0x18000728d  push    rbp
0x18000728e  push    rbx
0x18000728f  push    rsi
0x180007290  push    rdi
0x180007291  push    r12
0x180007293  push    r13
0x180007295  push    r14
0x180007297  push    r15
0x180007299  lea     rbp, [rsp-7]
0x18000729e  sub     rsp, 88h
0x1800072a5  mov     r14, r9
0x1800072a8  mov     edi, r8d
0x1800072ab  mov     rsi, rdx
0x1800072ae  mov     ebx, ecx
0x1800072b0  mov     r10, cs:WPP_GLOBAL_Control
0x1800072b7  lea     r12, WPP_GLOBAL_Control
0x1800072be  cmp     r10, r12
0x1800072c1  jz      short loc_1800072E9
0x1800072c3  test    byte ptr [r10+1Ch], 2
0x1800072c8  jz      short loc_1800072E9
0x1800072ca  cmp     byte ptr [r10+19h], 6
0x1800072cf  jb      short loc_1800072E9
0x1800072d1  mov     r9d, ecx
0x1800072d4  mov     edx, 21h ; '!'
0x1800072d9  mov     rcx, [r10+10h]
0x1800072dd  call    WPP_SF_d
0x1800072e2  mov     r10, cs:WPP_GLOBAL_Control
0x1800072e9  mov     [rbp+3Fh+pEapError], 0
0x1800072f1  xorps   xmm0, xmm0
0x1800072f4  xorps   xmm1, xmm1
0x1800072f7  movups  xmmword ptr [rbp+3Fh+eapMethodType.eapType.type], xmm0
0x1800072fb  movups  xmmword ptr [rbp+3Fh+var_68.dwVersion], xmm1
0x1800072ff  test    r14, r14
0x180007302  jnz     short loc_18000733E
0x180007304  mov     r14d, 57h ; 'W'
0x18000730a  cmp     r10, r12
0x18000730d  jz      loc_1800077B9
0x180007313  test    byte ptr [r10+1Ch], 2
0x180007318  jz      loc_1800077B9
0x18000731e  cmp     byte ptr [r10+19h], 2
0x180007323  jb      loc_1800077B9
0x180007329  lea     edx, [r14-35h]
0x18000732d  mov     r9d, r14d
0x180007330  mov     rcx, [r10+10h]
0x180007334  call    WPP_SF_d
0x180007339  jmp     loc_1800077B2
0x18000733e  mov     r15, [rbp+3Fh+pszDest]
0x180007342  test    r15, r15
0x180007345  jz      short loc_180007354
0x180007347  xor     eax, eax
0x180007349  mov     [r15], ax
0x18000734d  mov     r10, cs:WPP_GLOBAL_Control
0x180007354  mov     dword ptr [r14], 0
0x18000735b  test    ebx, ebx
0x18000735d  jnz     short loc_18000736B
0x18000735f  xor     r14d, r14d
0x180007362  lea     r9d, [rbx+2]
0x180007366  jmp     loc_18000778A
0x18000736b  lea     rdx, [rbp+3Fh+eapMethodType]
0x18000736f  mov     ecx, ebx
0x180007371  call    RasGetEapMethodTypeFromEapType
0x180007376  mov     r14d, eax
0x180007379  test    eax, eax
0x18000737b  jz      short loc_1800073AD
0x18000737d  mov     r10, cs:WPP_GLOBAL_Control
0x180007384  cmp     r10, r12
0x180007387  jz      loc_1800077B9
0x18000738d  test    byte ptr [r10+1Ch], 2
0x180007392  jz      loc_1800077B9
0x180007398  cmp     byte ptr [r10+19h], 2
0x18000739d  jb      loc_1800077B9
0x1800073a3  mov     edx, 23h ; '#'
0x1800073a8  mov     r9d, eax
0x1800073ab  jmp     short loc_180007330
0x1800073ad  movaps  xmm0, xmmword ptr [rbp+3Fh+eapMethodType.eapType.type]
0x1800073b1  lea     rax, [rbp+3Fh+pEapError]
0x1800073b5  mov     qword ptr [rsp+0C0h+ppEapError], rax; ppEapError
0x1800073ba  lea     rdx, [rbp+3Fh+eapMethodType]; eapMethodType
0x1800073be  lea     rax, [rbp+3Fh+var_68]
0x1800073c2  movdqa  xmmword ptr [rbp+3Fh+eapMethodType.eapType.type], xmm0
0x1800073c7  mov     [rsp+0C0h+pEapConfigInputFieldArray], rax; pEapConfigInputFieldArray
0x1800073cc  mov     r9d, edi; dwEapConnDataSize
0x1800073cf  xor     r8d, r8d; dwFlags
0x1800073d2  mov     [rsp+0C0h+pbEapConnData], rsi; pbEapConnData
0x1800073d7  xor     ecx, ecx; hUserImpersonationToken
0x1800073d9  call    cs:__imp_EapHostPeerQueryCredentialInputFields
0x1800073df  mov     rcx, [rbp+3Fh+pEapError]; pEapError
0x1800073e3  mov     r14d, eax
0x1800073e6  mov     [rbp+3Fh+var_78], eax
0x1800073e9  call    RasFreeEapConfigErrorMemory
0x1800073ee  test    r14d, r14d
0x1800073f1  jz      short loc_180007423
0x1800073f3  mov     r10, cs:WPP_GLOBAL_Control
0x1800073fa  cmp     r10, r12
0x1800073fd  jz      loc_1800077B9
0x180007403  test    byte ptr [r10+1Ch], 2
0x180007408  jz      loc_1800077B9
0x18000740e  cmp     byte ptr [r10+19h], 2
0x180007413  jb      loc_1800077B9
0x180007419  mov     edx, 24h ; '$'
0x18000741e  jmp     loc_18000732D
0x180007423  mov     r10, cs:WPP_GLOBAL_Control
0x18000742a  xor     eax, eax
0x18000742c  xor     ebx, ebx
0x18000742e  mov     [rbp+3Fh+var_7C], eax
0x180007431  xor     edi, edi
0x180007433  mov     [rbp+3Fh+arg_20], ebx
0x180007436  xor     r12d, r12d
0x180007439  mov     [rbp+3Fh+var_80], edi
0x18000743c  xor     r13d, r13d
0x18000743f  xor     esi, esi
0x180007441  cmp     [rbp+3Fh+var_68.dwNumberOfFields], eax
0x180007444  jbe     loc_180007513
0x18000744a  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007451  lea     r14, WPP_GLOBAL_Control
0x180007458  mov     rdi, [rbp+3Fh+var_68.pFields]
0x18000745c  lea     rbx, [rsi+rsi*4]
0x180007460  cmp     r10, r14
0x180007463  jz      short loc_180007493
0x180007465  test    byte ptr [r10+1Ch], 2
0x18000746a  jz      short loc_180007493
0x18000746c  cmp     byte ptr [r10+19h], 5
0x180007471  jb      short loc_180007493
0x180007473  mov     r9d, [rdi+rbx*8+4]
0x180007478  mov     rcx, [r10+10h]
0x18000747c  mov     dword ptr [rsp+0C0h+pbEapConnData], esi
0x180007480  call    WPP_SF_dd
0x180007485  mov     r10, cs:WPP_GLOBAL_Control
0x18000748c  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007493  mov     ecx, [rdi+rbx*8+4]
0x180007497  test    ecx, ecx
0x180007499  jz      loc_18000770E
0x18000749f  sub     ecx, 1
0x1800074a2  jz      loc_1800076D3
0x1800074a8  sub     ecx, 1
0x1800074ab  jz      loc_180007669
0x1800074b1  sub     ecx, 1
0x1800074b4  jz      loc_180007636
0x1800074ba  sub     ecx, 1
0x1800074bd  jz      loc_1800075FE
0x1800074c3  cmp     ecx, 3
0x1800074c6  jz      loc_180007587
0x1800074cc  cmp     r10, r14
0x1800074cf  jz      short loc_1800074F4
0x1800074d1  test    byte ptr [r10+1Ch], 2
0x1800074d6  jz      short loc_1800074F4
0x1800074d8  cmp     byte ptr [r10+19h], 5
0x1800074dd  jb      short loc_1800074F4
0x1800074df  mov     edx, 2Fh ; '/'
0x1800074e4  mov     rcx, [r10+10h]
0x1800074e8  call    WPP_SF_
0x1800074ed  mov     r10, cs:WPP_GLOBAL_Control
0x1800074f4  mov     eax, [rbp+3Fh+var_7C]
0x1800074f7  mov     edi, [rbp+3Fh+var_80]
0x1800074fa  mov     ebx, [rbp+3Fh+arg_20]
0x1800074fd  inc     esi
0x1800074ff  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007506  cmp     esi, [rbp+3Fh+var_68.dwNumberOfFields]
0x180007509  jb      loc_180007458
0x18000750f  mov     r14d, [rbp+3Fh+var_78]
0x180007513  lea     rcx, WPP_GLOBAL_Control
0x18000751a  cmp     r10, rcx
0x18000751d  jz      short loc_180007560
0x18000751f  test    byte ptr [r10+1Ch], 2
0x180007524  jz      short loc_180007560
0x180007526  cmp     byte ptr [r10+19h], 5
0x18000752b  jb      short loc_180007560
0x18000752d  test    ebx, ebx
0x18000752f  setnz   dl
0x180007532  test    eax, eax
0x180007534  mov     byte ptr [rsp+0C0h+ppEapError], dl
0x180007538  setnz   cl
0x18000753b  test    r13d, r13d
0x18000753e  mov     byte ptr [rsp+0C0h+pEapConfigInputFieldArray], cl
0x180007542  mov     rcx, [r10+10h]
0x180007546  setnz   al
0x180007549  test    r12d, r12d
0x18000754c  mov     byte ptr [rsp+0C0h+pbEapConnData], al
0x180007550  setnz   r9b
0x180007554  call    WPP_SF_cccc
0x180007559  mov     r10, cs:WPP_GLOBAL_Control
0x180007560  test    r12d, r12d
0x180007563  jz      short loc_18000756A
0x180007565  test    r13d, r13d
0x180007568  jnz     short loc_18000757C
0x18000756a  cmp     [rbp+3Fh+var_7C], 0
0x18000756e  jz      loc_18000777A
0x180007574  test    ebx, ebx
0x180007576  jz      loc_18000777A
0x18000757c  mov     r9d, 2
0x180007582  jmp     loc_180007783
0x180007587  cmp     r10, r14
0x18000758a  jz      short loc_1800075AF
0x18000758c  test    byte ptr [r10+1Ch], 2
0x180007591  jz      short loc_1800075AF
0x180007593  cmp     byte ptr [r10+19h], 5
0x180007598  jb      short loc_1800075AF
0x18000759a  mov     rcx, [r10+10h]
0x18000759e  mov     edx, 2Ch ; ','
0x1800075a3  call    WPP_SF_
0x1800075a8  mov     r10, cs:WPP_GLOBAL_Control
0x1800075af  test    r15, r15
0x1800075b2  jz      short loc_1800075CE
0x1800075b4  mov     r8, [rdi+rbx*8+18h]; pszSrc
0x1800075b9  test    r8, r8
0x1800075bc  jz      short loc_1800075CE
0x1800075be  mov     edx, dword ptr [rbp+3Fh+cchDest]; cchDest
0x1800075c1  mov     rcx, r15; pszDest
0x1800075c4  call    StringCchCopyW
0x1800075c9  jmp     loc_1800074ED
0x1800075ce  cmp     r10, r14
0x1800075d1  jz      loc_1800074F4
0x1800075d7  test    byte ptr [r10+1Ch], 2
0x1800075dc  jz      loc_1800074F4
0x1800075e2  cmp     byte ptr [r10+19h], 5
0x1800075e7  jb      loc_1800074F4
0x1800075ed  mov     edx, 2Dh ; '-'
0x1800075f2  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x1800075f9  jmp     loc_1800074E4
0x1800075fe  cmp     r10, r14
0x180007601  jz      short loc_180007626
0x180007603  test    byte ptr [r10+1Ch], 2
0x180007608  jz      short loc_180007626
0x18000760a  cmp     byte ptr [r10+19h], 5
0x18000760f  jb      short loc_180007626
0x180007611  mov     rcx, [r10+10h]
0x180007615  mov     edx, 2Eh ; '.'
0x18000761a  call    WPP_SF_
0x18000761f  mov     r10, cs:WPP_GLOBAL_Control
0x180007626  mov     eax, [rbp+3Fh+var_7C]
0x180007629  mov     edi, 1
0x18000762e  mov     [rbp+3Fh+var_80], edi
0x180007631  jmp     loc_1800074FA
0x180007636  cmp     r10, r14
0x180007639  jz      short loc_18000765E
0x18000763b  test    byte ptr [r10+1Ch], 2
0x180007640  jz      short loc_18000765E
0x180007642  cmp     byte ptr [r10+19h], 5
0x180007647  jb      short loc_18000765E
0x180007649  mov     rcx, [r10+10h]
0x18000764d  mov     edx, 28h ; '('
0x180007652  call    WPP_SF_
0x180007657  mov     r10, cs:WPP_GLOBAL_Control
0x18000765e  mov     r13d, 1
0x180007664  jmp     loc_1800074F4
0x180007669  cmp     r10, r14
0x18000766c  jz      short loc_180007691
0x18000766e  test    byte ptr [r10+1Ch], 2
0x180007673  jz      short loc_180007691
0x180007675  cmp     byte ptr [r10+19h], 5
0x18000767a  jb      short loc_180007691
0x18000767c  mov     rcx, [r10+10h]
0x180007680  mov     edx, 26h ; '&'
0x180007685  call    WPP_SF_
0x18000768a  mov     r10, cs:WPP_GLOBAL_Control
0x180007691  mov     r12d, 1
0x180007697  test    r15, r15
0x18000769a  jz      short loc_1800076AA
0x18000769c  mov     r8, [rdi+rbx*8+18h]
0x1800076a1  test    r8, r8
0x1800076a4  jnz     loc_1800075BE
0x1800076aa  cmp     r10, r14
0x1800076ad  jz      loc_1800074F4
0x1800076b3  test    byte ptr [r10+1Ch], 2
0x1800076b8  jz      loc_1800074F4
0x1800076be  cmp     byte ptr [r10+19h], 5
0x1800076c3  jb      loc_1800074F4
0x1800076c9  mov     edx, 27h ; '''
0x1800076ce  jmp     loc_1800075F2
0x1800076d3  cmp     r10, r14
0x1800076d6  jz      short loc_1800076FB
0x1800076d8  test    byte ptr [r10+1Ch], 2
0x1800076dd  jz      short loc_1800076FB
0x1800076df  cmp     byte ptr [r10+19h], 5
0x1800076e4  jb      short loc_1800076FB
0x1800076e6  mov     rcx, [r10+10h]
0x1800076ea  mov     edx, 2Bh ; '+'
0x1800076ef  call    WPP_SF_
0x1800076f4  mov     r10, cs:WPP_GLOBAL_Control
0x1800076fb  mov     eax, [rbp+3Fh+var_7C]
0x1800076fe  mov     ebx, 1
0x180007703  mov     edi, [rbp+3Fh+var_80]
0x180007706  mov     [rbp+3Fh+arg_20], ebx
0x180007709  jmp     loc_1800074FD
0x18000770e  cmp     r10, r14
0x180007711  jz      short loc_180007736
0x180007713  test    byte ptr [r10+1Ch], 2
0x180007718  jz      short loc_180007736
0x18000771a  cmp     byte ptr [r10+19h], 5
0x18000771f  jb      short loc_180007736
0x180007721  mov     rcx, [r10+10h]
0x180007725  mov     edx, 29h ; ')'
0x18000772a  call    WPP_SF_
0x18000772f  mov     r10, cs:WPP_GLOBAL_Control
0x180007736  mov     eax, 1
0x18000773b  mov     [rbp+3Fh+var_7C], eax
0x18000773e  test    r15, r15
0x180007741  jz      short loc_180007751
0x180007743  mov     r8, [rdi+rbx*8+18h]
  ... truncated ...
```
