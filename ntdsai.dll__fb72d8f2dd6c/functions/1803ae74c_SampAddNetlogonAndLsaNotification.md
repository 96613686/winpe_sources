# SampAddNetlogonAndLsaNotification

- ea: `0x1803ae74c`
- end: `0x1803aed3a`
- name: `SampAddNetlogonAndLsaNotification`
- size: `1518`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, int, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18027d914`
- `0x1803b04fc`

## callees

- `0x1800067d0`
- `0x18000dc7c`
- `0x18001e090`
- `0x180021aa3`
- `0x180022690`
- `0x1800f80e0`
- `0x1800f8280`
- `0x1800f9c9c`
- `0x1801059c8`
- `0x18010d09c`
- `0x1801d2a7c`
- `0x1801d2c68`
- `0x1801de8ec`
- `0x1801e3bf8`
- `0x1803ae74c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1803aec44`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1803aec44`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803ae79c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803ae79c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1803aec2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1803aec2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803aec7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803aecbd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803aec7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803aecbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803aec4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803aecd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803aec4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803aecd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803aecdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803aecdb`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803aeb3d`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803aeb5e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803aeb3d`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803aeb5e`
- `ntdll!RtlEqualSid` at `0x1803aeb53`
- `ntdll!RtlEqualSid` at `0x1803aeb53`
- `ntdll!RtlLengthSid` at `0x1803aec89`
- `ntdll!RtlLengthSid` at `0x1803aec89`
- `SAMSRV!SampFlagsToAccountControl` at `0x1803aea29`
- `SAMSRV!SampFlagsToAccountControl` at `0x1803aea29`
- `SAMSRV!SampNetLogonNotificationRequired` at `0x1803ae882`
- `SAMSRV!SampNetLogonNotificationRequired` at `0x1803ae882`

## pseudocode

```c
__int64 __fastcall SampAddNetlogonAndLsaNotification(
        char *Src,
        unsigned int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v8; // r12
  unsigned int *Value; // rax
  unsigned int *v13; // rdi
  int v14; // eax
  char *v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 *v25; // rax
  bool v26; // zf
  void *v28; // rbx
  _OWORD *v29; // r12
  PUCHAR v30; // rax
  BOOLEAN v31; // bl
  PUCHAR v32; // rax
  __int64 v33; // rax
  __int128 v34; // xmm1
  void *v35; // rax
  int v36; // r15d
  int v37; // r15d
  HANDLE CurrentThread; // rax
  ULONG v39; // eax
  __int64 *v40; // rax
  unsigned int v41; // [rsp+40h] [rbp-99h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-95h] BYREF
  unsigned int Size; // [rsp+48h] [rbp-91h] BYREF
  int Size_4; // [rsp+4Ch] [rbp-8Dh] BYREF
  void *Srca; // [rsp+50h] [rbp-89h] BYREF
  __int64 v46; // [rsp+58h] [rbp-81h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-79h] BYREF
  int v48; // [rsp+68h] [rbp-71h] BYREF
  const void *TokenInformation[12]; // [rsp+70h] [rbp-69h] BYREF

  v8 = a2;
  TokenHandle = 0;
  ReturnLength = 0;
  Srca = 0;
  v46 = 0;
  Value = (unsigned int *)TlsGetValue(dwTSindex);
  Size_4 = 0;
  v13 = Value;
  v48 = 0;
  if ( a3 )
  {
    if ( *((_DWORD *)Src + 13) )
    {
      if ( (unsigned int)DSNameToBlockName(Value, Src, &v46, 1) )
      {
        DoSetNamError(2006, (_DWORD)Src, 8335, 0, 521476763);
        return v13[1390];
      }
      if ( (unsigned int)NCLGetNCInfoByBlockName(v46, 0, &Srca) )
        return v13[1390];
      v28 = Srca;
      if ( !Srca
        || !(unsigned int)NameMatched(Srca, qword_18052B2C0)
        && (!qword_18052B2F0 || !(unsigned int)NameMatched(v28, qword_18052B2F0)) )
      {
        return v13[1390];
      }
      v29 = Src + 24;
    }
    else
    {
      if ( !*((_DWORD *)Src + 1) )
        return v13[1390];
      v29 = Src + 24;
      v30 = RtlSubAuthorityCountSid(Src + 24);
      --*v30;
      v31 = RtlEqualSid((char *)qword_18052B2C0 + 24, Src + 24);
      v32 = RtlSubAuthorityCountSid(Src + 24);
      ++*v32;
      if ( !v31 )
        return v13[1390];
    }
    v33 = THAlloc_((_DWORD)v13, 1, 128, 1, 0, 521476813);
    *(_OWORD *)(v33 + 20) = *v29;
    v21 = v33;
    v34 = *(_OWORD *)((char *)v29 + 12);
    *(_DWORD *)(v33 + 16) = a4;
    *(_DWORD *)(v33 + 8) = a3;
    *(_OWORD *)(v33 + 32) = v34;
    *(_DWORD *)(v33 + 12) = 2;
    v35 = (void *)THAlloc_((_DWORD)v13, 1, *(_DWORD *)Src, 1, 0, 521476825);
    *(_QWORD *)(v21 + 96) = v35;
    memcpy_0(v35, Src, 2LL * *((unsigned int *)Src + 13) + 58);
    v36 = a3 - 655378;
    if ( (!v36 || (v37 = v36 - 10) == 0 || v37 == 6) && (v13[1401] & 0x100) == 0 && !ImpersonateAnyClient() )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        ReturnLength = 84;
        if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength)
          && (v39 = RtlLengthSid((PSID)TokenInformation[0]),
              memcpy_0((void *)(v21 + 60), TokenInformation[0], v39),
              ReturnLength = 84,
              GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x54u, &ReturnLength)) )
        {
          *(const void **)(v21 + 88) = TokenInformation[1];
        }
        else
        {
          GetLastError();
        }
        CloseHandle(TokenHandle);
      }
      else
      {
        GetLastError();
      }
      UnImpersonateAnyClient();
    }
    v40 = (__int64 *)*((_QWORD *)v13 + 707);
    if ( v40 )
      *v40 = v21;
    v26 = *((_QWORD *)v13 + 708) == 0;
    goto LABEL_63;
  }
  Srca = 0;
  Size = 0;
  if ( dsaInitPhase != 1 )
    return 0;
  if ( !gfRunningInsideLsa )
    return 0;
  v14 = *(_DWORD *)&ClassMappingTable[48 * v8 + 4];
  if ( !v14 || v14 == 1 && !*((_DWORD *)Src + 1) )
    return 0;
  if ( *((_DWORD *)Src + 1) )
  {
    v15 = Src + 24;
    Size = *((_DWORD *)Src + 1);
    Srca = Src + 24;
    goto LABEL_13;
  }
  v16 = DBGetAttVal(*((_QWORD *)v13 + 697), 1, 589970, 0, (__int64)&Size, (__int64)&Srca);
  if ( !v16 )
  {
    v15 = (char *)Srca;
LABEL_13:
    if ( !a6
      && !(unsigned __int8)SampNetLogonNotificationRequired(v15, *(unsigned int *)&ClassMappingTable[48 * v8 + 4])
      || a4 != 3 && (unsigned int)dbIsObjDeleted(*((_QWORD *)v13 + 697), *(_QWORD *)(*((_QWORD *)v13 + 697) + 64LL)) )
    {
      return v13[1390];
    }
    if ( *(_DWORD *)&ClassMappingTable[48 * v8 + 4] == 2 )
    {
      if ( (unsigned int)DBGetAttVal_ConstantBuffer(
                           *((_QWORD *)v13 + 697),
                           1,
                           590574,
                           0,
                           4,
                           (__int64)&v48,
                           (__int64)&Size_4) )
      {
        v18 = 521476590;
        goto LABEL_32;
      }
      if ( (Size_4 & 0x34) != 0 )
        v8 = (unsigned int)(v8 + 1);
    }
    v21 = THAlloc_((_DWORD)v13, 1, 128, 1, 0, 521476607);
    memcpy_0((void *)(v21 + 20), Srca, Size);
    *(_DWORD *)(v21 + 104) = a6;
    *(_DWORD *)(v21 + 108) = a7;
    *(_DWORD *)(v21 + 8) = v8;
    *(_DWORD *)(v21 + 16) = a4;
    *(_DWORD *)(v21 + 12) = 1;
    *(_DWORD *)(v21 + 112) = a5;
    *(_DWORD *)(v21 + 116) = Size_4;
    *(_DWORD *)(v21 + 120) = a8;
    if ( *(_DWORD *)&ClassMappingTable[48 * v8 + 4] == 1 )
    {
LABEL_24:
      if ( *(_DWORD *)&ClassMappingTable[48 * v8 + 4] != 4 )
      {
LABEL_28:
        v25 = (__int64 *)*((_QWORD *)v13 + 707);
        if ( v25 )
          *v25 = v21;
        v26 = *((_QWORD *)v13 + 708) == 0;
LABEL_63:
        *((_QWORD *)v13 + 707) = v21;
        if ( v26 )
          *((_QWORD *)v13 + 708) = v21;
        return v13[1390];
      }
      v24 = *((_QWORD *)v13 + 697);
      v41 = 0;
      if ( !(unsigned int)DBGetSingleValue(v24, 589832, &v41, 4, 0) )
      {
        if ( (int)SampFlagsToAccountControl(v41, &v41) >= 0 )
          *(_DWORD *)(v21 + 56) = v41;
        goto LABEL_28;
      }
      v18 = 521476710;
      goto LABEL_32;
    }
    v22 = *((_QWORD *)v13 + 697);
    v46 = 0;
    v41 = 0;
    if ( !(unsigned int)DBGetAttVal(v22, 1, 590045, 0, (__int64)&v41, (__int64)&v46) )
    {
      v23 = THAlloc_((_DWORD)v13, 1, 16, 1, 0, 521476649);
      *(_WORD *)v23 = v41;
      *(_WORD *)(v23 + 2) = v41;
      *(_QWORD *)(v23 + 8) = v46;
      *(_QWORD *)(v21 + 48) = v23;
      goto LABEL_24;
    }
    v18 = 521476675;
LABEL_32:
    v19 = 0;
    v17 = 5001;
    v20 = 8;
    goto LABEL_11;
  }
  v17 = 5012;
  v18 = 521476512;
  v19 = v16;
  v20 = 8316;
LABEL_11:
  DoSetSvcError(v17, v20, v19, v18);
  return v13[1390];
}

```

## disassembly

```asm
0x1803ae74c  mov     [rsp-8+arg_10], rbx
0x1803ae751  push    rbp
0x1803ae752  push    rsi
0x1803ae753  push    rdi
0x1803ae754  push    r12
0x1803ae756  push    r13
0x1803ae758  push    r14
0x1803ae75a  push    r15
0x1803ae75c  lea     rbp, [rsp-7]
0x1803ae761  sub     rsp, 0E0h
0x1803ae768  mov     rax, cs:__security_cookie
0x1803ae76f  xor     rax, rsp
0x1803ae772  mov     [rbp+37h+var_40], rax
0x1803ae776  xor     ebx, ebx
0x1803ae778  mov     r12d, edx
0x1803ae77b  mov     r14, rcx
0x1803ae77e  mov     [rbp+37h+TokenHandle], rbx
0x1803ae782  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1803ae788  mov     r13d, r9d
0x1803ae78b  mov     [rsp+110h+var_CC], ebx
0x1803ae78f  mov     r15d, r8d
0x1803ae792  mov     [rsp+110h+Src], rbx
0x1803ae797  mov     [rsp+110h+var_B8], rbx
0x1803ae79c  call    cs:__imp_TlsGetValue
0x1803ae7a2  mov     dword ptr [rsp+110h+Size+4], ebx
0x1803ae7a6  mov     rdi, rax
0x1803ae7a9  mov     [rbp+37h+var_A8], ebx
0x1803ae7ac  test    r15d, r15d
0x1803ae7af  jnz     loc_1803AEA83
0x1803ae7b5  xor     r15d, r15d
0x1803ae7b8  lea     esi, [rbx+1]
0x1803ae7bb  cmp     cs:dsaInitPhase, esi
0x1803ae7c1  mov     [rsp+110h+Src], r15
0x1803ae7c6  mov     dword ptr [rsp+110h+Size], r15d
0x1803ae7cb  jnz     loc_1803AEA7C
0x1803ae7d1  cmp     cs:gfRunningInsideLsa, r15d
0x1803ae7d8  jz      loc_1803AEA7C
0x1803ae7de  lea     rbx, [r12+r12*2]
0x1803ae7e2  add     rbx, rbx
0x1803ae7e5  lea     rdx, ClassMappingTable
0x1803ae7ec  mov     eax, [rdx+rbx*8+4]
0x1803ae7f0  test    eax, eax
0x1803ae7f2  jz      loc_1803AEA7C
0x1803ae7f8  cmp     eax, esi
0x1803ae7fa  jnz     short loc_1803AE806
0x1803ae7fc  cmp     [r14+4], r15d
0x1803ae800  jz      loc_1803AEA7C
0x1803ae806  mov     eax, [r14+4]
0x1803ae80a  test    eax, eax
0x1803ae80c  jz      short loc_1803AE81D
0x1803ae80e  lea     rcx, [r14+18h]
0x1803ae812  mov     dword ptr [rsp+110h+Size], eax
0x1803ae816  mov     [rsp+110h+Src], rcx
0x1803ae81b  jmp     short loc_1803AE875
0x1803ae81d  mov     rcx, [rdi+15C8h]
0x1803ae824  lea     rax, [rsp+110h+Src]
0x1803ae829  mov     [rsp+110h+var_E8], rax
0x1803ae82e  xor     r9d, r9d
0x1803ae831  lea     rax, [rsp+110h+Size]
0x1803ae836  mov     r8d, 90092h
0x1803ae83c  mov     edx, esi
0x1803ae83e  mov     [rsp+110h+ReturnLength], rax
0x1803ae843  call    DBGetAttVal
0x1803ae848  test    eax, eax
0x1803ae84a  jz      short loc_1803AE869
0x1803ae84c  mov     ecx, 1394h
0x1803ae851  mov     r9d, 1F1519A0h
0x1803ae857  mov     r8d, eax
0x1803ae85a  mov     edx, 207Ch
0x1803ae85f  call    DoSetSvcError
0x1803ae864  jmp     loc_1803AED0D
0x1803ae869  mov     rcx, [rsp+110h+Src]
0x1803ae86e  lea     rdx, ClassMappingTable
0x1803ae875  mov     r14d, [rbp+37h+arg_28]
0x1803ae879  test    r14d, r14d
0x1803ae87c  jnz     short loc_1803AE890
0x1803ae87e  mov     edx, [rdx+rbx*8+4]
0x1803ae882  call    cs:__imp_SampNetLogonNotificationRequired
0x1803ae888  test    al, al
0x1803ae88a  jz      loc_1803AED0D
0x1803ae890  cmp     r13d, 3
0x1803ae894  jz      short loc_1803AE8AE
0x1803ae896  mov     rcx, [rdi+15C8h]
0x1803ae89d  mov     rdx, [rcx+40h]
0x1803ae8a1  call    dbIsObjDeleted
0x1803ae8a6  test    eax, eax
0x1803ae8a8  jnz     loc_1803AED0D
0x1803ae8ae  lea     rax, ClassMappingTable
0x1803ae8b5  cmp     dword ptr [rax+rbx*8+4], 2
0x1803ae8ba  jnz     short loc_1803AE900
0x1803ae8bc  mov     rcx, [rdi+15C8h]
0x1803ae8c3  lea     rax, [rsp+110h+Size+4]
0x1803ae8c8  mov     [rsp+110h+var_E0], rax
0x1803ae8cd  xor     r9d, r9d
0x1803ae8d0  lea     rax, [rbp+37h+var_A8]
0x1803ae8d4  mov     r8d, 902EEh
0x1803ae8da  mov     [rsp+110h+var_E8], rax
0x1803ae8df  mov     edx, esi
0x1803ae8e1  mov     dword ptr [rsp+110h+ReturnLength], 4
0x1803ae8e9  call    DBGetAttVal_ConstantBuffer
0x1803ae8ee  test    eax, eax
0x1803ae8f0  jnz     loc_1803AEA55
0x1803ae8f6  test    byte ptr [rsp+110h+Size+4], 34h
0x1803ae8fb  jz      short loc_1803AE900
0x1803ae8fd  add     r12d, esi
0x1803ae900  mov     dword ptr [rsp+110h+var_E8], 1F1519FFh
0x1803ae908  mov     r9d, esi
0x1803ae90b  mov     r8d, 80h
0x1803ae911  mov     dword ptr [rsp+110h+ReturnLength], r15d
0x1803ae916  mov     rdx, rsi
0x1803ae919  mov     rcx, rdi
0x1803ae91c  call    THAlloc_
0x1803ae921  mov     r8d, dword ptr [rsp+110h+Size]; Size
0x1803ae926  mov     rbx, rax
0x1803ae929  mov     rdx, [rsp+110h+Src]; Src
0x1803ae92e  lea     rcx, [rax+14h]; void *
0x1803ae932  call    memcpy_0
0x1803ae937  mov     ecx, [rbp+37h+arg_30]
0x1803ae93a  mov     eax, [rbp+37h+arg_38]
0x1803ae93d  mov     [rbx+68h], r14d
0x1803ae941  lea     r14, [r12+r12*2]
0x1803ae945  mov     [rbx+6Ch], ecx
0x1803ae948  add     r14, r14
0x1803ae94b  mov     ecx, [rbp+37h+arg_20]
0x1803ae94e  mov     [rbx+8], r12d
0x1803ae952  lea     r12, ClassMappingTable
0x1803ae959  mov     [rbx+10h], r13d
0x1803ae95d  mov     [rbx+0Ch], esi
0x1803ae960  mov     [rbx+70h], ecx
0x1803ae963  mov     ecx, dword ptr [rsp+110h+Size+4]
0x1803ae967  mov     [rbx+74h], ecx
0x1803ae96a  mov     [rbx+78h], eax
0x1803ae96d  cmp     [r12+r14*8+4], esi
0x1803ae972  jz      short loc_1803AE9EE
0x1803ae974  mov     rcx, [rdi+15C8h]
0x1803ae97b  lea     rax, [rsp+110h+var_B8]
0x1803ae980  mov     [rsp+110h+var_E8], rax
0x1803ae985  xor     r9d, r9d
0x1803ae988  lea     rax, [rsp+110h+var_D0]
0x1803ae98d  mov     [rsp+110h+var_B8], r15
0x1803ae992  mov     r8d, 900DDh
0x1803ae998  mov     [rsp+110h+ReturnLength], rax
0x1803ae99d  mov     edx, esi
0x1803ae99f  mov     [rsp+110h+var_D0], r15d
0x1803ae9a4  call    DBGetAttVal
0x1803ae9a9  test    eax, eax
0x1803ae9ab  jnz     loc_1803AEA6C
0x1803ae9b1  mov     dword ptr [rsp+110h+var_E8], 1F151A29h
0x1803ae9b9  lea     r8d, [rax+10h]
0x1803ae9bd  mov     r9d, esi
0x1803ae9c0  mov     dword ptr [rsp+110h+ReturnLength], r15d
0x1803ae9c5  mov     rdx, rsi
0x1803ae9c8  mov     rcx, rdi
0x1803ae9cb  call    THAlloc_
0x1803ae9d0  movzx   ecx, word ptr [rsp+110h+var_D0]
0x1803ae9d5  mov     [rax], cx
0x1803ae9d8  movzx   ecx, word ptr [rsp+110h+var_D0]
0x1803ae9dd  mov     [rax+2], cx
0x1803ae9e1  mov     rcx, [rsp+110h+var_B8]
0x1803ae9e6  mov     [rax+8], rcx
0x1803ae9ea  mov     [rbx+30h], rax
0x1803ae9ee  cmp     dword ptr [r12+r14*8+4], 4
0x1803ae9f4  jnz     short loc_1803AEA3A
0x1803ae9f6  mov     rcx, [rdi+15C8h]
0x1803ae9fd  lea     r8, [rsp+110h+var_D0]
0x1803aea02  mov     r9d, 4
0x1803aea08  mov     [rsp+110h+var_D0], r15d
0x1803aea0d  mov     edx, 90008h
0x1803aea12  mov     [rsp+110h+ReturnLength], r15
0x1803aea17  call    DBGetSingleValue
0x1803aea1c  test    eax, eax
0x1803aea1e  jnz     short loc_1803AEA74
0x1803aea20  mov     ecx, [rsp+110h+var_D0]
0x1803aea24  lea     rdx, [rsp+110h+var_D0]
0x1803aea29  call    cs:__imp_SampFlagsToAccountControl
0x1803aea2f  test    eax, eax
0x1803aea31  js      short loc_1803AEA3A
0x1803aea33  mov     eax, [rsp+110h+var_D0]
0x1803aea37  mov     [rbx+38h], eax
0x1803aea3a  mov     rax, [rdi+1618h]
0x1803aea41  test    rax, rax
0x1803aea44  jz      short loc_1803AEA49
0x1803aea46  mov     [rax], rbx
0x1803aea49  cmp     [rdi+1620h], r15
0x1803aea50  jmp     loc_1803AECFD
0x1803aea55  mov     r9d, 1F1519EEh
0x1803aea5b  xor     r8d, r8d
0x1803aea5e  mov     ecx, 1389h
0x1803aea63  lea     edx, [r8+8]
0x1803aea67  jmp     loc_1803AE85F
0x1803aea6c  mov     r9d, 1F151A43h
0x1803aea72  jmp     short loc_1803AEA5B
0x1803aea74  mov     r9d, 1F151A66h
0x1803aea7a  jmp     short loc_1803AEA5B
0x1803aea7c  xor     eax, eax
0x1803aea7e  jmp     loc_1803AED13
0x1803aea83  cmp     [r14+34h], ebx
0x1803aea87  jbe     loc_1803AEB2C
0x1803aea8d  mov     esi, 1
0x1803aea92  lea     r8, [rsp+110h+var_B8]
0x1803aea97  mov     r9d, esi
0x1803aea9a  mov     rdx, r14
0x1803aea9d  mov     rcx, rdi
0x1803aeaa0  call    DSNameToBlockName
0x1803aeaa5  test    eax, eax
0x1803aeaa7  jz      short loc_1803AEACC
0x1803aeaa9  mov     ecx, 7D6h
0x1803aeaae  mov     dword ptr [rsp+110h+ReturnLength], 1F151A9Bh
0x1803aeab6  xor     r9d, r9d
0x1803aeab9  mov     r8d, 208Fh
0x1803aeabf  mov     rdx, r14
0x1803aeac2  call    DoSetNamError
0x1803aeac7  jmp     loc_1803AED0D
0x1803aeacc  mov     rcx, [rsp+110h+var_B8]
0x1803aead1  lea     r8, [rsp+110h+Src]
0x1803aead6  xor     edx, edx
0x1803aead8  call    NCLGetNCInfoByBlockName
0x1803aeadd  test    eax, eax
0x1803aeadf  jnz     loc_1803AED0D
0x1803aeae5  mov     rbx, [rsp+110h+Src]
0x1803aeaea  test    rbx, rbx
0x1803aeaed  jz      loc_1803AED0D
0x1803aeaf3  mov     rdx, cs:qword_18052B2C0
0x1803aeafa  mov     rcx, rbx
0x1803aeafd  call    NameMatched
0x1803aeb02  test    eax, eax
0x1803aeb04  jnz     short loc_1803AEB26
0x1803aeb06  mov     rdx, cs:qword_18052B2F0
0x1803aeb0d  test    rdx, rdx
0x1803aeb10  jz      loc_1803AED0D
0x1803aeb16  mov     rcx, rbx
0x1803aeb19  call    NameMatched
0x1803aeb1e  test    eax, eax
0x1803aeb20  jz      loc_1803AED0D
0x1803aeb26  lea     r12, [r14+18h]
0x1803aeb2a  jmp     short loc_1803AEB74
0x1803aeb2c  cmp     [r14+4], ebx
0x1803aeb30  jbe     loc_1803AED0D
0x1803aeb36  lea     r12, [r14+18h]
0x1803aeb3a  mov     rcx, r12; Sid
0x1803aeb3d  call    cs:__imp_RtlSubAuthorityCountSid
0x1803aeb43  mov     rdx, r12; Sid2
0x1803aeb46  dec     byte ptr [rax]
0x1803aeb48  mov     rcx, cs:qword_18052B2C0
0x1803aeb4f  add     rcx, 18h; Sid1
0x1803aeb53  call    cs:__imp_RtlEqualSid
0x1803aeb59  mov     rcx, r12; Sid
0x1803aeb5c  mov     bl, al
0x1803aeb5e  call    cs:__imp_RtlSubAuthorityCountSid
0x1803aeb64  mov     esi, 1
0x1803aeb69  add     [rax], sil
0x1803aeb6c  test    bl, bl
0x1803aeb6e  jz      loc_1803AED0D
0x1803aeb74  mov     dword ptr [rsp+110h+var_E8], 1F151ACDh
0x1803aeb7c  mov     r9d, esi
0x1803aeb7f  mov     r8d, 80h
0x1803aeb85  mov     dword ptr [rsp+110h+ReturnLength], 0
0x1803aeb8d  mov     rdx, rsi
0x1803aeb90  mov     rcx, rdi
0x1803aeb93  call    THAlloc_
0x1803aeb98  movups  xmm0, xmmword ptr [r12]
0x1803aeb9d  mov     dword ptr [rsp+110h+var_E8], 1F151AD9h
0x1803aeba5  mov     r9d, esi
0x1803aeba8  mov     rdx, rsi
0x1803aebab  mov     dword ptr [rsp+110h+ReturnLength], 0
0x1803aebb3  movups  xmmword ptr [rax+14h], xmm0
0x1803aebb7  mov     rcx, rdi
0x1803aebba  mov     rbx, rax
0x1803aebbd  movups  xmm1, xmmword ptr [r12+0Ch]
0x1803aebc3  mov     [rax+10h], r13d
0x1803aebc7  mov     [rax+8], r15d
0x1803aebcb  movups  xmmword ptr [rax+20h], xmm1
0x1803aebcf  mov     dword ptr [rax+0Ch], 2
0x1803aebd6  mov     r8d, [r14]
0x1803aebd9  call    THAlloc_
0x1803aebde  mov     [rbx+60h], rax
0x1803aebe2  mov     rdx, r14; Src
0x1803aebe5  mov     r8d, [r14+34h]
0x1803aebe9  mov     rcx, rax; void *
0x1803aebec  lea     r8, ds:3Ah[r8*2]; Size
0x1803aebf4  call    memcpy_0
0x1803aebf9  sub     r15d, 0A0012h
0x1803aec00  jz      short loc_1803AEC12
0x1803aec02  sub     r15d, 0Ah
0x1803aec06  jz      short loc_1803AEC12
0x1803aec08  cmp     r15d, 6
0x1803aec0c  jnz     loc_1803AECE6
0x1803aec12  test    dword ptr [rdi+15E4h], 100h
0x1803aec1c  jnz     loc_1803AECE6
0x1803aec22  call    ImpersonateAnyClient
0x1803aec27  test    eax, eax
0x1803aec29  jnz     loc_1803AECE6
0x1803aec2f  call    cs:__imp_GetCurrentThread
0x1803aec35  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x1803aec39  mov     r8d, esi; OpenAsSelf
0x1803aec3c  mov     rcx, rax; ThreadHandle
0x1803aec3f  mov     edx, 8; DesiredAccess
0x1803aec44  call    cs:__imp_OpenThreadToken
0x1803aec4a  test    eax, eax
0x1803aec4c  jnz     short loc_1803AEC59
  ... truncated ...
```
