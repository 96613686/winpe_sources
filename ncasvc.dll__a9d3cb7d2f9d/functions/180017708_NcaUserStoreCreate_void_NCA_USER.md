# NcaUserStoreCreate(void *,NCA_USER_ * *)

- ea: `0x180017708`
- end: `0x180017bc1`
- name: `?NcaUserStoreCreate@@YAKPEAXPEAPEAUNCA_USER_@@@Z`
- size: `1209`
- prototype: `__int64 __fastcall(void *, struct NCA_USER_ **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007780`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x1800074c4`
- `0x1800174e4`
- `0x180017708`
- `0x180017bc8`
- `0x180017c78`
- `0x180018354`
- `0x180018fd4`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001777a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001777a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001790f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001790f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800178a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800178ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800178a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800178ff`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017965`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017965`

## pseudocode

```c
__int64 __fastcall NcaUserStoreCreate(void *a1, struct NCA_USER_ **a2)
{
  struct NCA_USER_ **v2; // rsi
  struct NCA_USER_ *v4; // rbx
  struct _TOKEN_USER *v5; // r14
  __int64 v6; // r13
  unsigned int ThreadToken; // eax
  unsigned int EvColls; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  struct NCA_USER_ *i; // r14
  struct _TOKEN_USER *v13; // rax
  PVOID *v14; // rcx
  struct NCA_USER_ *v15; // r15
  BOOL v16; // r14d
  struct NCA_USER_ *j; // rax
  unsigned int v18; // eax
  int v19; // edx
  struct NCA_USER_ **v20; // rax
  int v22; // [rsp+30h] [rbp-20h] BYREF
  struct _TOKEN_USER *v23; // [rsp+38h] [rbp-18h]
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  struct NCA_USER_ *v25; // [rsp+48h] [rbp-8h] BYREF
  int v27; // [rsp+A0h] [rbp+50h] BYREF
  DWORD TokenInformationLength; // [rsp+A8h] [rbp+58h] BYREF

  v2 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_f6fba97516d23319eaec26e747470e80_Traceguids);
  v4 = 0;
  TokenHandle = 0;
  v5 = 0;
  v25 = 0;
  v23 = 0;
  v22 = 0;
  v6 = 0;
  v27 = 0;
  TokenInformationLength = 0;
  EnterCriticalSection(&gNcaUserStore);
  ThreadToken = NcaGetThreadToken(a1, &TokenHandle);
  EvColls = ThreadToken;
  if ( !ThreadToken )
  {
    ThreadToken = NcaIsNonSystemUser(TokenHandle, &v27);
    EvColls = ThreadToken;
    if ( ThreadToken )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_11;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_10;
      v10 = 22;
LABEL_8:
      v11 = ThreadToken;
LABEL_9:
      WPP_SF_d(v9[2], v10, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, v11);
      goto LABEL_10;
    }
    if ( v27 || !qword_180029588 )
    {
      GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
      v13 = (struct _TOKEN_USER *)NcaAlloc(TokenInformationLength);
      v23 = v13;
      v5 = v13;
      if ( !v13 )
      {
        EvColls = 14;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_10;
        v10 = 23;
        v11 = 14;
        goto LABEL_9;
      }
      if ( !GetTokenInformation(TokenHandle, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
      {
        ThreadToken = GetLastError();
        EvColls = ThreadToken;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_10;
        v10 = 24;
        goto LABEL_8;
      }
      for ( i = qword_180029570; ; i = *(struct NCA_USER_ **)i )
      {
        v6 = 0;
        if ( i == (struct NCA_USER_ *)&qword_180029570 )
          break;
        v6 = (__int64)i;
        if ( EqualSid(*((PSID *)i + 3), v23->User.Sid) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_f6fba97516d23319eaec26e747470e80_Traceguids);
          goto LABEL_39;
        }
      }
    }
    else
    {
      v6 = qword_180029588;
      i = (struct NCA_USER_ *)qword_180029588;
LABEL_39:
      _InterlockedAdd((volatile signed __int32 *)i + 18, 1u);
      if ( v6 )
      {
        v5 = v23;
        v2 = a2;
        goto LABEL_11;
      }
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_f6fba97516d23319eaec26e747470e80_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v27 )
    {
      v15 = 0;
      if ( qword_180029588 )
      {
        v16 = *(_DWORD *)(qword_180029588 + 56) == 0;
LABEL_55:
        v18 = NcaUserStoreCreateHelper(v23, TokenHandle, v16, &v25, &v22);
        EvColls = v18;
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, v18);
          v4 = v25;
        }
        else
        {
          v4 = v25;
          if ( v22 )
            _InterlockedAdd((volatile signed __int32 *)v25 + 18, 1u);
          if ( !v27 )
          {
            qword_180029588 = (__int64)v4;
            *((_DWORD *)v4 + 13) = 1;
          }
          if ( !v16 )
          {
            if ( v27 )
            {
              v19 = *((_DWORD *)v4 + 4);
              *((_DWORD *)v4 + 14) = 1;
              *((_DWORD *)v4 + 4) = *(_DWORD *)(qword_180029588 + 20);
              *((_DWORD *)v4 + 5) = *(_DWORD *)(qword_180029588 + 20);
              *(_QWORD *)(qword_180029588 + 64) = v4;
              *(_DWORD *)(qword_180029588 + 16) = v19;
              *(_DWORD *)(qword_180029588 + 56) = 0;
            }
            else
            {
              *(_QWORD *)(qword_180029588 + 64) = v15;
              *(_DWORD *)(qword_180029588 + 20) = *((_DWORD *)v15 + 5);
            }
          }
          v20 = (struct NCA_USER_ **)qword_180029578;
          if ( *(struct NCA_USER_ ***)qword_180029578 != &qword_180029570 )
            __fastfail(3u);
          *(_QWORD *)v4 = &qword_180029570;
          *((_QWORD *)v4 + 1) = v20;
          *v20 = v4;
          qword_180029578 = (__int64)v4;
        }
        v5 = v23;
        goto LABEL_10;
      }
    }
    else
    {
      for ( j = qword_180029570; ; j = *(struct NCA_USER_ **)j )
      {
        v15 = 0;
        if ( j == (struct NCA_USER_ *)&qword_180029570 )
          break;
        v15 = j;
        if ( !*((_DWORD *)j + 13) )
        {
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
            WPP_SF_(v14[2], 27, WPP_f6fba97516d23319eaec26e747470e80_Traceguids);
          v16 = 0;
          goto LABEL_55;
        }
      }
    }
    v16 = 1;
    goto LABEL_55;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_10:
      v2 = a2;
      goto LABEL_11;
    }
    v10 = 21;
    goto LABEL_8;
  }
LABEL_11:
  LeaveCriticalSection(&gNcaUserStore);
  if ( !EvColls && v22 )
  {
    EvColls = NcaUserStoreCreateEvColls(v4);
    NcaUserStoreRemove(v4);
  }
  NcaFree(v5);
  if ( EvColls )
  {
    if ( TokenHandle )
      NcaCloseHandle(TokenHandle);
  }
  else
  {
    if ( v6 )
      v4 = (struct NCA_USER_ *)v6;
    *v2 = v4;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, EvColls);
  return EvColls;
}

```

## disassembly

```asm
0x180017708  mov     [rsp-38h+arg_8], rdx
0x18001770d  push    rbp
0x18001770e  push    rbx
0x18001770f  push    rsi
0x180017710  push    rdi
0x180017711  push    r13
0x180017713  push    r14
0x180017715  push    r15
0x180017717  mov     rbp, rsp
0x18001771a  sub     rsp, 50h
0x18001771e  mov     rsi, rdx
0x180017721  mov     rdi, rcx
0x180017724  mov     rcx, cs:WPP_GLOBAL_Control
0x18001772b  lea     r15, WPP_GLOBAL_Control
0x180017732  cmp     rcx, r15
0x180017735  jz      short loc_180017752
0x180017737  test    byte ptr [rcx+1Ch], 8
0x18001773b  jz      short loc_180017752
0x18001773d  mov     rcx, [rcx+10h]
0x180017741  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017748  mov     edx, 14h
0x18001774d  call    WPP_SF_
0x180017752  xor     ebx, ebx
0x180017754  mov     [rbp+TokenHandle], 0
0x18001775c  xor     r14d, r14d
0x18001775f  mov     [rbp+var_8], rbx
0x180017763  lea     rcx, ?gNcaUserStore@@3UNCA_USER_STORE_COMPONENT_@@A; lpCriticalSection
0x18001776a  mov     [rbp+var_18], r14
0x18001776e  mov     [rbp+var_20], ebx
0x180017771  xor     r13d, r13d
0x180017774  mov     [rbp+arg_10], ebx
0x180017777  mov     [rbp+TokenInformationLength], ebx
0x18001777a  call    cs:__imp_EnterCriticalSection
0x180017781  nop     dword ptr [rax+rax+00h]
0x180017786  lea     rdx, [rbp+TokenHandle]; void **
0x18001778a  mov     rcx, rdi; void *
0x18001778d  call    ?NcaGetThreadToken@@YAKPEAXPEAPEAX@Z; NcaGetThreadToken(void *,void * *)
0x180017792  mov     edi, eax
0x180017794  test    eax, eax
0x180017796  jz      loc_180017827
0x18001779c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177a3  cmp     rcx, r15
0x1800177a6  jz      short loc_1800177CB
0x1800177a8  lea     esi, [rbx+1]
0x1800177ab  test    [rcx+1Ch], sil
0x1800177af  jz      short loc_1800177C7
0x1800177b1  lea     edx, [rbx+15h]
0x1800177b4  mov     r9d, eax
0x1800177b7  mov     rcx, [rcx+10h]
0x1800177bb  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x1800177c2  call    WPP_SF_d
0x1800177c7  mov     rsi, [rbp+arg_8]
0x1800177cb  lea     r15, WPP_GLOBAL_Control
0x1800177d2  lea     rcx, ?gNcaUserStore@@3UNCA_USER_STORE_COMPONENT_@@A; lpCriticalSection
0x1800177d9  call    cs:__imp_LeaveCriticalSection
0x1800177e0  nop     dword ptr [rax+rax+00h]
0x1800177e5  test    edi, edi
0x1800177e7  jnz     short loc_180017800
0x1800177e9  cmp     [rbp+var_20], edi
0x1800177ec  jz      short loc_180017800
0x1800177ee  mov     rcx, rbx; struct NCA_USER_ *
0x1800177f1  call    ?NcaUserStoreCreateEvColls@@YAKPEAUNCA_USER_@@@Z; NcaUserStoreCreateEvColls(NCA_USER_ *)
0x1800177f6  mov     rcx, rbx; lpMem
0x1800177f9  mov     edi, eax
0x1800177fb  call    ?NcaUserStoreRemove@@YAXPEAUNCA_USER_@@@Z; NcaUserStoreRemove(NCA_USER_ *)
0x180017800  mov     rcx, r14; lpMem
0x180017803  call    NcaFree
0x180017808  test    edi, edi
0x18001780a  jz      loc_180017B7B
0x180017810  mov     rcx, [rbp+TokenHandle]
0x180017814  test    rcx, rcx
0x180017817  jz      loc_180017B85
0x18001781d  call    NcaCloseHandle
0x180017822  jmp     loc_180017B85
0x180017827  mov     rcx, [rbp+TokenHandle]; void *
0x18001782b  lea     rdx, [rbp+arg_10]; int *
0x18001782f  call    ?NcaIsNonSystemUser@@YAKPEAXPEAH@Z; NcaIsNonSystemUser(void *,int *)
0x180017834  mov     edi, eax
0x180017836  test    eax, eax
0x180017838  jz      short loc_18001785D
0x18001783a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017841  cmp     rcx, r15
0x180017844  jz      short loc_1800177CB
0x180017846  mov     esi, 1
0x18001784b  test    [rcx+1Ch], sil
0x18001784f  jz      loc_1800177C7
0x180017855  lea     edx, [rsi+15h]
0x180017858  jmp     loc_1800177B4
0x18001785d  lea     rdx, qword_180029570
0x180017864  mov     esi, 1
0x180017869  cmp     [rbp+arg_10], ebx
0x18001786c  jnz     short loc_18001788C
0x18001786e  mov     rax, cs:qword_180029588
0x180017875  test    rax, rax
0x180017878  jz      short loc_18001788C
0x18001787a  mov     r13, rax
0x18001787d  lea     r15, WPP_GLOBAL_Control
0x180017884  mov     r14, rax
0x180017887  jmp     loc_1800179AF
0x18001788c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180017890  lea     rax, [rbp+TokenInformationLength]
0x180017894  xor     r9d, r9d; TokenInformationLength
0x180017897  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18001789c  xor     r8d, r8d; TokenInformation
0x18001789f  mov     edx, esi; TokenInformationClass
0x1800178a1  call    cs:__imp_GetTokenInformation
0x1800178a8  nop     dword ptr [rax+rax+00h]
0x1800178ad  mov     ecx, [rbp+TokenInformationLength]
0x1800178b0  call    NcaAlloc
0x1800178b5  mov     [rbp+var_18], rax
0x1800178b9  mov     r14, rax
0x1800178bc  test    rax, rax
0x1800178bf  jnz     short loc_1800178E9
0x1800178c1  lea     edi, [rax+0Eh]
0x1800178c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178cb  cmp     rcx, r15
0x1800178ce  jz      loc_1800177C7
0x1800178d4  test    [rcx+1Ch], sil
0x1800178d8  jz      loc_1800177C7
0x1800178de  lea     edx, [rax+17h]
0x1800178e1  mov     r9d, edi
0x1800178e4  jmp     loc_1800177B7
0x1800178e9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800178ed  lea     rax, [rbp+TokenInformationLength]
0x1800178f1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800178f5  mov     r8, r14; TokenInformation
0x1800178f8  mov     edx, esi; TokenInformationClass
0x1800178fa  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800178ff  call    cs:__imp_GetTokenInformation
0x180017906  nop     dword ptr [rax+rax+00h]
0x18001790b  test    eax, eax
0x18001790d  jnz     short loc_180017941
0x18001790f  call    cs:__imp_GetLastError
0x180017916  nop     dword ptr [rax+rax+00h]
0x18001791b  mov     edi, eax
0x18001791d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017924  cmp     rcx, r15
0x180017927  jz      loc_1800177C7
0x18001792d  test    [rcx+1Ch], sil
0x180017931  jz      loc_1800177C7
0x180017937  mov     edx, 18h
0x18001793c  jmp     loc_1800177B4
0x180017941  mov     r14, cs:qword_180029570
0x180017948  mov     r15, [rbp+var_18]
0x18001794c  xor     r13d, r13d
0x18001794f  lea     rdx, qword_180029570
0x180017956  cmp     r14, rdx
0x180017959  jz      short loc_1800179BD
0x18001795b  mov     rdx, [r15]; pSid2
0x18001795e  mov     r13, r14
0x180017961  mov     rcx, [r14+18h]; pSid1
0x180017965  call    cs:__imp_EqualSid
0x18001796c  nop     dword ptr [rax+rax+00h]
0x180017971  test    eax, eax
0x180017973  jnz     short loc_18001797A
0x180017975  mov     r14, [r14]
0x180017978  jmp     short loc_18001794C
0x18001797a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017981  lea     r15, WPP_GLOBAL_Control
0x180017988  cmp     rcx, r15
0x18001798b  jz      short loc_1800179A8
0x18001798d  test    byte ptr [rcx+1Ch], 4
0x180017991  jz      short loc_1800179A8
0x180017993  mov     rcx, [rcx+10h]
0x180017997  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x18001799e  mov     edx, 19h
0x1800179a3  call    WPP_SF_
0x1800179a8  lea     rdx, qword_180029570
0x1800179af  lock add [r14+48h], esi
0x1800179b4  test    r13, r13
0x1800179b7  jnz     loc_180017B6E
0x1800179bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179c4  lea     rbx, WPP_GLOBAL_Control
0x1800179cb  cmp     rcx, rbx
0x1800179ce  jz      short loc_1800179F9
0x1800179d0  test    byte ptr [rcx+1Ch], 4
0x1800179d4  jz      short loc_1800179F9
0x1800179d6  mov     rcx, [rcx+10h]
0x1800179da  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x1800179e1  mov     edx, 1Ah
0x1800179e6  call    WPP_SF_
0x1800179eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179f2  lea     rdx, qword_180029570
0x1800179f9  cmp     [rbp+arg_10], 0
0x1800179fd  jz      short loc_180017A1B
0x1800179ff  mov     rax, cs:qword_180029588
0x180017a06  xor     r15d, r15d
0x180017a09  test    rax, rax
0x180017a0c  jz      short loc_180017A5D
0x180017a0e  xor     r14d, r14d
0x180017a11  cmp     [rax+38h], r14d
0x180017a15  setz    r14b
0x180017a19  jmp     short loc_180017A60
0x180017a1b  mov     rax, cs:qword_180029570
0x180017a22  xor     r15d, r15d
0x180017a25  cmp     rax, rdx
0x180017a28  jz      short loc_180017A5D
0x180017a2a  cmp     dword ptr [rax+34h], 0
0x180017a2e  mov     r15, rax
0x180017a31  jz      short loc_180017A38
0x180017a33  mov     rax, [rax]
0x180017a36  jmp     short loc_180017A22
0x180017a38  cmp     rcx, rbx
0x180017a3b  jz      short loc_180017A58
0x180017a3d  test    byte ptr [rcx+1Ch], 4
0x180017a41  jz      short loc_180017A58
0x180017a43  mov     rcx, [rcx+10h]
0x180017a47  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017a4e  mov     edx, 1Bh
0x180017a53  call    WPP_SF_
0x180017a58  xor     r14d, r14d
0x180017a5b  jmp     short loc_180017A60
0x180017a5d  mov     r14d, esi
0x180017a60  mov     rdx, [rbp+TokenHandle]; void *
0x180017a64  lea     rax, [rbp+var_20]
0x180017a68  mov     rcx, [rbp+var_18]; struct _TOKEN_USER *
0x180017a6c  lea     r9, [rbp+var_8]; struct NCA_USER_ **
0x180017a70  mov     r8d, r14d; int
0x180017a73  mov     [rsp+50h+ReturnLength], rax; int *
0x180017a78  call    ?NcaUserStoreCreateHelper@@YAKPEAU_TOKEN_USER@@PEAXHPEAPEAUNCA_USER_@@PEAH@Z; NcaUserStoreCreateHelper(_TOKEN_USER *,void *,int,NCA_USER_ * *,int *)
0x180017a7d  mov     edi, eax
0x180017a7f  test    eax, eax
0x180017a81  jz      short loc_180017ABA
0x180017a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a8a  cmp     rcx, rbx
0x180017a8d  jz      short loc_180017AAD
0x180017a8f  test    [rcx+1Ch], sil
0x180017a93  jz      short loc_180017AAD
0x180017a95  mov     rcx, [rcx+10h]
0x180017a99  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017aa0  mov     edx, 1Ch
0x180017aa5  mov     r9d, eax
0x180017aa8  call    WPP_SF_d
0x180017aad  mov     rbx, [rbp+var_8]
0x180017ab1  mov     r14, [rbp+var_18]
0x180017ab5  jmp     loc_1800177C7
0x180017aba  cmp     [rbp+var_20], 0
0x180017abe  mov     rbx, [rbp+var_8]
0x180017ac2  jz      short loc_180017AC8
0x180017ac4  lock add [rbx+48h], esi
0x180017ac8  cmp     [rbp+arg_10], 0
0x180017acc  jnz     short loc_180017AD8
0x180017ace  mov     cs:qword_180029588, rbx
0x180017ad5  mov     [rbx+34h], esi
0x180017ad8  test    r14d, r14d
0x180017adb  jnz     short loc_180017B3E
0x180017add  cmp     [rbp+arg_10], r14d
0x180017ae1  jz      short loc_180017B25
0x180017ae3  mov     edx, [rbx+10h]
0x180017ae6  mov     [rbx+38h], esi
0x180017ae9  mov     rax, cs:qword_180029588
0x180017af0  mov     ecx, [rax+14h]
0x180017af3  mov     [rbx+10h], ecx
0x180017af6  mov     rax, cs:qword_180029588
0x180017afd  mov     ecx, [rax+14h]
0x180017b00  mov     [rbx+14h], ecx
0x180017b03  mov     rax, cs:qword_180029588
0x180017b0a  mov     [rax+40h], rbx
0x180017b0e  mov     rax, cs:qword_180029588
0x180017b15  mov     [rax+10h], edx
0x180017b18  mov     rax, cs:qword_180029588
0x180017b1f  mov     [rax+38h], r14d
0x180017b23  jmp     short loc_180017B3E
0x180017b25  mov     rax, cs:qword_180029588
0x180017b2c  mov     [rax+40h], r15
0x180017b30  mov     rax, cs:qword_180029588
0x180017b37  mov     ecx, [r15+14h]
0x180017b3b  mov     [rax+14h], ecx
0x180017b3e  mov     rax, cs:qword_180029578
0x180017b45  lea     rcx, qword_180029570
0x180017b4c  cmp     [rax], rcx
0x180017b4f  jz      short loc_180017B58
0x180017b51  mov     ecx, 3
0x180017b56  int     29h; Win8: RtlFailFast(ecx)
0x180017b58  mov     [rbx], rcx
0x180017b5b  mov     [rbx+8], rax
0x180017b5f  mov     [rax], rbx
0x180017b62  mov     cs:qword_180029578, rbx
0x180017b69  jmp     loc_180017AB1
0x180017b6e  mov     r14, [rbp+var_18]
0x180017b72  mov     rsi, [rbp+arg_8]
0x180017b76  jmp     loc_1800177D2
0x180017b7b  test    r13, r13
0x180017b7e  cmovnz  rbx, r13
0x180017b82  mov     [rsi], rbx
0x180017b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b8c  cmp     rcx, r15
0x180017b8f  jz      short loc_180017BAF
0x180017b91  test    byte ptr [rcx+1Ch], 8
0x180017b95  jz      short loc_180017BAF
0x180017b97  mov     rcx, [rcx+10h]
0x180017b9b  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017ba2  mov     edx, 1Dh
0x180017ba7  mov     r9d, edi
0x180017baa  call    WPP_SF_d
0x180017baf  mov     eax, edi
0x180017bb1  add     rsp, 50h
0x180017bb5  pop     r15
0x180017bb7  pop     r14
0x180017bb9  pop     r13
  ... truncated ...
```
