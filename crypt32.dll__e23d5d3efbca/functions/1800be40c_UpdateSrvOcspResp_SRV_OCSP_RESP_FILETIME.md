# UpdateSrvOcspResp(_SRV_OCSP_RESP *,_FILETIME *)

- ea: `0x1800be40c`
- end: `0x1800be825`
- name: `?UpdateSrvOcspResp@@YAHPEAU_SRV_OCSP_RESP@@PEAU_FILETIME@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(struct _SRV_OCSP_RESP *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800ab390`
- `0x1800c7018`

## callees

- `0x180028d60`
- `0x180097b00`
- `0x1800b7300`
- `0x1800be40c`
- `0x1800c66d0`
- `0x1800c6794`
- `0x1800c6c78`
- `0x1800c71b0`
- `0x1800c7474`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be727`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be746`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be80b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be746`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800be80b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be600`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800be5f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800be5f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800be71a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800be71a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800be49a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800be52e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800be49a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800be52e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800be769`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800be769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be738`

## pseudocode

```c
__int64 __fastcall UpdateSrvOcspResp(struct _SRV_OCSP_RESP *a1, struct _FILETIME *a2)
{
  unsigned int v3; // r12d
  const wchar_t *v4; // rsi
  const CERT_SERVER_OCSP_RESPONSE_CONTEXT *v5; // r15
  const FILETIME *v6; // rbx
  const FILETIME *v7; // r14
  struct _FILETIME *v8; // rcx
  struct _SRV_OCSP_RESP_ELE *SrvOcspRespEle; // rax
  const CERT_SERVER_OCSP_RESPONSE_CONTEXT *v10; // r13
  const FILETIME *v11; // rax
  int v12; // r14d
  struct _FILETIME *v13; // r15
  unsigned int v14; // ecx
  int v15; // r14d
  DWORD LastError; // edx
  void (__fastcall *v17)(_QWORD, const CERT_SERVER_OCSP_RESPONSE_CONTEXT *, BYTE *, BYTE *, _QWORD, DWORD); // rax
  BYTE *pbEncodedOcspResponse; // r9
  unsigned int v19; // edx
  unsigned int v20; // ecx
  __int64 v21; // rax
  int v22; // edx
  HANDLE v23; // rbx
  DWORD v24; // r14d
  BOOL v25; // r15d
  int v26; // ecx
  int v28; // [rsp+40h] [rbp-38h]
  FILETIME v29; // [rsp+48h] [rbp-30h] BYREF
  struct _FILETIME v30; // [rsp+50h] [rbp-28h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-20h] BYREF
  FILETIME v32; // [rsp+60h] [rbp-18h] BYREF
  const FILETIME *v33; // [rsp+68h] [rbp-10h]
  int hMem; // [rsp+C0h] [rbp+48h]
  DWORD dwErrCode; // [rsp+D0h] [rbp+58h]

  hMem = 1;
  dwErrCode = 0;
  v3 = 0;
  v29 = 0;
  v4 = 0;
  v32 = 0;
  Token = 0;
  v28 = ImpersonateToken(*((HANDLE *)a1 + 13), &Token);
  do
  {
    if ( ++v3 > 3 )
    {
      LODWORD(v10) = hMem;
      goto LABEL_57;
    }
    v5 = (const CERT_SERVER_OCSP_RESPONSE_CONTEXT *)*((_QWORD *)a1 + 9);
    v6 = 0;
    v30 = 0;
    if ( !v5
      || (v6 = (const FILETIME *)*((_QWORD *)v5[1].pbEncodedOcspResponse + 3),
          v7 = v6 + 7,
          v29 = v6[6],
          v32 = v6[7],
          *((_DWORD *)a1 + 17))
      || CompareFileTime(a2, v6 + 7) >= 0 )
    {
      v8 = a2;
      v7 = v6 + 7;
    }
    else
    {
      v8 = &v30;
      v30 = (struct _FILETIME)(*(_QWORD *)v7 + 10000000LL);
    }
    SrvOcspRespEle = RetrieveSrvOcspRespEle(
                       *((const struct _CERT_CHAIN_CONTEXT **)a1 + 10),
                       *((const struct _CERT_CONTEXT **)a1 + 11),
                       *((const struct _CERT_CONTEXT **)a1 + 12),
                       a2,
                       v8,
                       *((_DWORD *)a1 + 32),
                       *((const unsigned __int16 **)a1 + 17),
                       *((_DWORD *)a1 + 17));
    v10 = (const CERT_SERVER_OCSP_RESPONSE_CONTEXT *)SrvOcspRespEle;
    if ( !SrvOcspRespEle )
    {
      if ( v3 == 1 )
      {
        dwErrCode = GetLastError();
        hMem = 0;
LABEL_16:
        v12 = 0;
        goto LABEL_17;
      }
LABEL_15:
      LODWORD(v10) = hMem;
      goto LABEL_16;
    }
    v11 = *(const FILETIME **)(*((_QWORD *)SrvOcspRespEle + 4) + 24LL);
    v33 = v11;
    if ( !*((_DWORD *)a1 + 17) && v6 && CompareFileTime(v11 + 7, v7) <= 0 )
      goto LABEL_14;
    if ( (*((_DWORD *)a1 + 32) & 2) != 0 )
    {
      hMem = WriteOcspRespToFile(*((_QWORD *)a1 + 17), *((_QWORD *)a1 + 11), v10);
      v15 = hMem;
      if ( !hMem )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
        goto LABEL_25;
      }
    }
    else
    {
      v15 = hMem;
    }
    LastError = dwErrCode;
LABEL_25:
    v17 = (void (__fastcall *)(_QWORD, const CERT_SERVER_OCSP_RESPONSE_CONTEXT *, BYTE *, BYTE *, _QWORD, DWORD))*((_QWORD *)a1 + 18);
    if ( v17 )
    {
      if ( v5 )
        pbEncodedOcspResponse = v5[1].pbEncodedOcspResponse;
      else
        pbEncodedOcspResponse = 0;
      v17(
        *((_QWORD *)a1 + 10),
        v10,
        v10[1].pbEncodedOcspResponse,
        pbEncodedOcspResponse,
        *((_QWORD *)a1 + 19),
        LastError);
    }
    if ( !v15 )
    {
LABEL_14:
      CertFreeServerOcspResponseContext(v10);
      goto LABEL_15;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
    *((_QWORD *)a1 + 9) = v10;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
    if ( v5 )
      CertFreeServerOcspResponseContext(v5);
    v6 = v33;
    v12 = 1;
    LODWORD(v10) = hMem;
    *((_DWORD *)a1 + 28) = 0;
    *((_DWORD *)a1 + 17) = 0;
LABEL_17:
    if ( *((_DWORD *)a1 + 17) || !v6 )
    {
      v13 = a2;
      v14 = 0;
    }
    else
    {
      v13 = a2;
      v14 = I_CryptSubtractFileTimes(&v6[7], a2);
    }
    v19 = dword_180157E0C;
    if ( (*((_DWORD *)a1 + 32) & 1) != 0 && dword_180157E0C > 0xE10 )
      v19 = dword_180157E0C - 300;
    if ( v14 >= v19 )
    {
      v20 = v19;
      goto LABEL_46;
    }
  }
  while ( v12 && v14 && v3 < 3 );
  if ( v14 < 0x1C20 )
    v20 = v14 >> 1;
  else
    v20 = v14 - 3600;
LABEL_46:
  if ( v20 )
  {
    if ( v20 < dword_180157E10 )
    {
      v4 = L"REASON_OCSP_RESPONSE_NOT_FRESH";
      v21 = *(_QWORD *)&v6[7] + 10000000LL * dword_180157E14;
    }
    else
    {
      v21 = *(_QWORD *)&v6[7] - 10000000LL * v20;
    }
    *(_QWORD *)((char *)a1 + 116) = v21;
  }
  else
  {
    ++*((_DWORD *)a1 + 28);
    v22 = 6;
    if ( (unsigned int)(*((_DWORD *)a1 + 28) - 1) <= 5 )
      v22 = *((_DWORD *)a1 + 28);
    *(_QWORD *)((char *)a1 + 116) = *(_QWORD *)v13
                                  + 10000000LL
                                  * *((unsigned int *)&rgdwSrvOcspRespRetrySeconds + (unsigned int)(v22 - 1));
    if ( v29 )
      v4 = L"REASON_OCSP_RESPONSE_NOT_FRESH";
    else
      v4 = L"REASON_OCSP_RESPONSE_RETRIEVAL_ERROR";
  }
LABEL_57:
  if ( v28 )
  {
    v23 = Token;
    v24 = 0;
    v25 = SetThreadToken(0, Token);
    if ( !v25 )
      v24 = GetLastError();
    if ( v23 )
      CloseHandle(v23);
    if ( !v25 )
      SetLastError(v24);
  }
  if ( v4 )
  {
    InitOnceExecuteOnce(&stru_18015D570, EventRegisterSchannelInitOnceCallback, 0, 0);
    if ( dword_18015D568 )
    {
      if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)a1 + 31) <= 7 )
      {
        HasOcspAIAUrl(*((PCCERT_CONTEXT *)a1 + 11));
        if ( (SchannelEnableBits & 2) != 0 )
          McTemplateU0zzmmqbr4_EventWriteTransfer(
            v26,
            *(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL),
            (_DWORD)v4,
            (unsigned int)&szPassword,
            (__int64)&v29,
            (__int64)&v32,
            *(_DWORD *)(*((_QWORD *)a1 + 11) + 16LL),
            *(_QWORD *)(*((_QWORD *)a1 + 11) + 8LL));
      }
    }
  }
  else
  {
    *((_DWORD *)a1 + 31) = 0;
  }
  if ( !(_DWORD)v10 )
    SetLastError(dwErrCode);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800be40c  mov     [rsp-40h+lpFileTime1], rdx
0x1800be411  push    rbp
0x1800be412  push    rbx
0x1800be413  push    rsi
0x1800be414  push    rdi
0x1800be415  push    r12
0x1800be417  push    r13
0x1800be419  push    r14
0x1800be41b  push    r15
0x1800be41d  mov     rbp, rsp
0x1800be420  sub     rsp, 78h
0x1800be424  mov     rdi, rcx
0x1800be427  mov     dword ptr [rbp+hMem], 1
0x1800be42e  xor     ecx, ecx
0x1800be430  lea     rdx, [rbp+Token]; void **
0x1800be434  mov     [rbp+dwErrCode], ecx
0x1800be437  xor     r12d, r12d
0x1800be43a  mov     [rbp+var_30], rcx
0x1800be43e  xor     esi, esi
0x1800be440  mov     [rbp+var_18], rcx
0x1800be444  mov     [rbp+Token], rcx
0x1800be448  mov     rcx, [rdi+68h]; Token
0x1800be44c  call    ?ImpersonateToken@@YAHPEAXPEAPEAX@Z; ImpersonateToken(void *,void * *)
0x1800be451  mov     [rbp+var_38], eax
0x1800be454  inc     r12d
0x1800be457  cmp     r12d, 3
0x1800be45b  ja      loc_1800BE704
0x1800be461  mov     r15, [rdi+48h]
0x1800be465  xor     ebx, ebx
0x1800be467  mov     r13, [rbp+lpFileTime1]
0x1800be46b  mov     qword ptr [rbp+var_28.dwLowDateTime], rbx
0x1800be46f  test    r15, r15
0x1800be472  jz      short loc_1800BE4B7
0x1800be474  mov     rax, [r15+20h]
0x1800be478  mov     rbx, [rax+18h]
0x1800be47c  lea     r14, [rbx+38h]
0x1800be480  mov     rax, [rbx+30h]
0x1800be484  mov     [rbp+var_30], rax
0x1800be488  mov     rax, [r14]
0x1800be48b  mov     [rbp+var_18], rax
0x1800be48f  cmp     [rdi+44h], esi
0x1800be492  jnz     short loc_1800BE4B7
0x1800be494  mov     rdx, r14; lpFileTime2
0x1800be497  mov     rcx, r13; lpFileTime1
0x1800be49a  call    cs:__imp_CompareFileTime
0x1800be4a0  test    eax, eax
0x1800be4a2  jns     short loc_1800BE4B7
0x1800be4a4  mov     rax, [r14]
0x1800be4a7  lea     rcx, [rbp+var_28]
0x1800be4ab  add     rax, 989680h
0x1800be4b1  mov     qword ptr [rbp+var_28.dwLowDateTime], rax
0x1800be4b5  jmp     short loc_1800BE4BE
0x1800be4b7  mov     rcx, r13
0x1800be4ba  lea     r14, [rbx+38h]
0x1800be4be  mov     eax, [rdi+44h]
0x1800be4c1  mov     r9, r13; struct _FILETIME *
0x1800be4c4  mov     r8, [rdi+60h]; struct _CERT_CONTEXT *
0x1800be4c8  mov     rdx, [rdi+58h]; struct _CERT_CONTEXT *
0x1800be4cc  mov     [rsp+78h+var_40], eax; int
0x1800be4d0  mov     rax, [rdi+88h]
0x1800be4d7  mov     [rsp+78h+var_48], rax; unsigned __int16 *
0x1800be4dc  mov     eax, [rdi+80h]
0x1800be4e2  mov     [rsp+78h+var_50], eax; unsigned int
0x1800be4e6  mov     [rsp+78h+var_58], rcx; struct _FILETIME *
0x1800be4eb  mov     rcx, [rdi+50h]; struct _CERT_CHAIN_CONTEXT *
0x1800be4ef  call    ?RetrieveSrvOcspRespEle@@YAPEAU_SRV_OCSP_RESP_ELE@@PEBU_CERT_CHAIN_CONTEXT@@PEBU_CERT_CONTEXT@@1PEAU_FILETIME@@2KPEBGH@Z; RetrieveSrvOcspRespEle(_CERT_CHAIN_CONTEXT const *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_FILETIME *,_FILETIME *,ulong,ushort const *,int)
0x1800be4f4  mov     r13, rax
0x1800be4f7  test    rax, rax
0x1800be4fa  jnz     short loc_1800BE511
0x1800be4fc  cmp     r12d, 1
0x1800be500  jnz     short loc_1800BE540
0x1800be502  call    cs:__imp_GetLastError
0x1800be508  mov     [rbp+dwErrCode], eax
0x1800be50b  mov     dword ptr [rbp+hMem], r13d
0x1800be50f  jmp     short loc_1800BE544
0x1800be511  mov     rax, [rax+20h]
0x1800be515  mov     rax, [rax+18h]
0x1800be519  mov     [rbp+var_10], rax
0x1800be51d  cmp     [rdi+44h], esi
0x1800be520  jnz     short loc_1800BE570
0x1800be522  test    rbx, rbx
0x1800be525  jz      short loc_1800BE570
0x1800be527  lea     rcx, [rax+38h]; lpFileTime1
0x1800be52b  mov     rdx, r14; lpFileTime2
0x1800be52e  call    cs:__imp_CompareFileTime
0x1800be534  test    eax, eax
0x1800be536  jg      short loc_1800BE570
0x1800be538  mov     rcx, r13; pServerOcspResponseContext
0x1800be53b  call    CertFreeServerOcspResponseContext
0x1800be540  mov     r13d, dword ptr [rbp+hMem]
0x1800be544  mov     r14d, esi
0x1800be547  cmp     [rdi+44h], esi
0x1800be54a  jnz     loc_1800BE62C
0x1800be550  test    rbx, rbx
0x1800be553  jz      loc_1800BE62C
0x1800be559  mov     r15, [rbp+lpFileTime1]
0x1800be55d  lea     rcx, [rbx+38h]
0x1800be561  mov     rdx, r15
0x1800be564  call    I_CryptSubtractFileTimes
0x1800be569  mov     ecx, eax
0x1800be56b  jmp     loc_1800BE632
0x1800be570  mov     eax, [rdi+80h]
0x1800be576  test    al, 2
0x1800be578  jz      short loc_1800BE5A4
0x1800be57a  mov     rdx, [rdi+58h]
0x1800be57e  mov     r8, r13
0x1800be581  mov     rcx, [rdi+88h]
0x1800be588  call    WriteOcspRespToFile
0x1800be58d  mov     dword ptr [rbp+hMem], eax
0x1800be590  mov     r14d, eax
0x1800be593  test    eax, eax
0x1800be595  jnz     short loc_1800BE5A8
0x1800be597  call    cs:__imp_GetLastError
0x1800be59d  mov     edx, eax
0x1800be59f  mov     [rbp+dwErrCode], eax
0x1800be5a2  jmp     short loc_1800BE5AB
0x1800be5a4  mov     r14d, dword ptr [rbp+hMem]
0x1800be5a8  mov     edx, [rbp+dwErrCode]
0x1800be5ab  mov     rax, [rdi+90h]
0x1800be5b2  test    rax, rax
0x1800be5b5  jz      short loc_1800BE5E5
0x1800be5b7  mov     rcx, [rdi+98h]
0x1800be5be  test    r15, r15
0x1800be5c1  jnz     short loc_1800BE5C8
0x1800be5c3  xor     r9d, r9d
0x1800be5c6  jmp     short loc_1800BE5CC
0x1800be5c8  mov     r9, [r15+20h]
0x1800be5cc  mov     r8, [r13+20h]
0x1800be5d0  mov     [rsp+78h+var_50], edx
0x1800be5d4  mov     rdx, r13
0x1800be5d7  mov     [rsp+78h+var_58], rcx
0x1800be5dc  mov     rcx, [rdi+50h]
0x1800be5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5e5  test    r14d, r14d
0x1800be5e8  jz      loc_1800BE538
0x1800be5ee  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800be5f2  call    cs:__imp_EnterCriticalSection
0x1800be5f8  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800be5fc  mov     [rdi+48h], r13
0x1800be600  call    cs:__imp_LeaveCriticalSection
0x1800be606  test    r15, r15
0x1800be609  jz      short loc_1800BE613
0x1800be60b  mov     rcx, r15; pServerOcspResponseContext
0x1800be60e  call    CertFreeServerOcspResponseContext
0x1800be613  mov     rbx, [rbp+var_10]
0x1800be617  mov     r14d, 1
0x1800be61d  mov     r13d, dword ptr [rbp+hMem]
0x1800be621  mov     [rdi+70h], esi
0x1800be624  mov     [rdi+44h], esi
0x1800be627  jmp     loc_1800BE547
0x1800be62c  mov     r15, [rbp+lpFileTime1]
0x1800be630  xor     ecx, ecx
0x1800be632  mov     eax, [rdi+80h]
0x1800be638  mov     edx, cs:dword_180157E0C
0x1800be63e  test    al, 1
0x1800be640  jz      short loc_1800BE650
0x1800be642  cmp     edx, 0E10h
0x1800be648  jbe     short loc_1800BE650
0x1800be64a  add     edx, 0FFFFFED4h
0x1800be650  cmp     ecx, edx
0x1800be652  jnb     short loc_1800BE67B
0x1800be654  test    r14d, r14d
0x1800be657  jz      short loc_1800BE667
0x1800be659  test    ecx, ecx
0x1800be65b  jz      short loc_1800BE667
0x1800be65d  cmp     r12d, 3
0x1800be661  jb      loc_1800BE454
0x1800be667  cmp     ecx, 1C20h
0x1800be66d  jb      short loc_1800BE677
0x1800be66f  add     ecx, 0FFFFF1F0h
0x1800be675  jmp     short loc_1800BE67D
0x1800be677  shr     ecx, 1
0x1800be679  jmp     short loc_1800BE67D
0x1800be67b  mov     ecx, edx
0x1800be67d  test    ecx, ecx
0x1800be67f  jz      short loc_1800BE6B9
0x1800be681  cmp     ecx, cs:dword_180157E10
0x1800be687  jb      short loc_1800BE69B
0x1800be689  mov     eax, ecx
0x1800be68b  imul    rcx, rax, 989680h
0x1800be692  mov     rax, [rbx+38h]
0x1800be696  sub     rax, rcx
0x1800be699  jmp     short loc_1800BE6B3
0x1800be69b  mov     eax, cs:dword_180157E14
0x1800be6a1  lea     rsi, aReasonOcspResp_0; "REASON_OCSP_RESPONSE_NOT_FRESH"
0x1800be6a8  imul    rax, 989680h
0x1800be6af  add     rax, [rbx+38h]
0x1800be6b3  mov     [rdi+74h], rax
0x1800be6b7  jmp     short loc_1800BE708
0x1800be6b9  inc     dword ptr [rdi+70h]
0x1800be6bc  mov     edx, 6
0x1800be6c1  mov     ecx, [rdi+70h]
0x1800be6c4  lea     eax, [rcx-1]
0x1800be6c7  cmp     eax, 5
0x1800be6ca  lea     rax, ?rgdwSrvOcspRespRetrySeconds@@3PAKA; ulong near * rgdwSrvOcspRespRetrySeconds
0x1800be6d1  cmovbe  edx, ecx
0x1800be6d4  lea     ecx, [rdx-1]
0x1800be6d7  mov     eax, [rax+rcx*4]
0x1800be6da  imul    rcx, rax, 989680h
0x1800be6e1  add     rcx, [r15]
0x1800be6e4  mov     [rdi+74h], rcx
0x1800be6e8  cmp     dword ptr [rbp+var_30], esi
0x1800be6eb  jnz     short loc_1800BE6FB
0x1800be6ed  cmp     dword ptr [rbp+var_30+4], esi
0x1800be6f0  jnz     short loc_1800BE6FB
0x1800be6f2  lea     rsi, aReasonOcspResp; "REASON_OCSP_RESPONSE_RETRIEVAL_ERROR"
0x1800be6f9  jmp     short loc_1800BE708
0x1800be6fb  lea     rsi, aReasonOcspResp_0; "REASON_OCSP_RESPONSE_NOT_FRESH"
0x1800be702  jmp     short loc_1800BE708
0x1800be704  mov     r13d, dword ptr [rbp+hMem]
0x1800be708  cmp     [rbp+var_38], 0
0x1800be70c  jz      short loc_1800BE74C
0x1800be70e  mov     rbx, [rbp+Token]
0x1800be712  xor     ecx, ecx; Thread
0x1800be714  mov     rdx, rbx; Token
0x1800be717  xor     r14d, r14d
0x1800be71a  call    cs:__imp_SetThreadToken
0x1800be720  mov     r15d, eax
0x1800be723  test    eax, eax
0x1800be725  jnz     short loc_1800BE730
0x1800be727  call    cs:__imp_GetLastError
0x1800be72d  mov     r14d, eax
0x1800be730  test    rbx, rbx
0x1800be733  jz      short loc_1800BE73E
0x1800be735  mov     rcx, rbx; hObject
0x1800be738  call    cs:__imp_CloseHandle
0x1800be73e  test    r15d, r15d
0x1800be741  jnz     short loc_1800BE74C
0x1800be743  mov     ecx, r14d; dwErrCode
0x1800be746  call    cs:__imp_SetLastError
0x1800be74c  test    rsi, rsi
0x1800be74f  jz      loc_1800BE7FC
0x1800be755  xor     r9d, r9d; Context
0x1800be758  lea     rdx, _EventRegisterSchannelInitOnceCallback; InitFn
0x1800be75f  xor     r8d, r8d; Parameter
0x1800be762  lea     rcx, stru_18015D570; InitOnce
0x1800be769  call    cs:__imp_InitOnceExecuteOnce
0x1800be76f  cmp     cs:dword_18015D568, 0
0x1800be776  jz      loc_1800BE803
0x1800be77c  mov     eax, 1
0x1800be781  lock xadd [rdi+7Ch], eax
0x1800be786  inc     eax
0x1800be788  cmp     eax, 7
0x1800be78b  ja      short loc_1800BE803
0x1800be78d  mov     rcx, [rdi+58h]; pCertContext
0x1800be791  lea     rdx, [rbp+hMem]
0x1800be795  mov     [rbp+hMem], 0
0x1800be79d  call    _HasOcspAIAUrl
0x1800be7a2  test    cs:SchannelEnableBits, 2
0x1800be7a9  mov     rbx, [rbp+hMem]
0x1800be7ad  jz      short loc_1800BE7ED
0x1800be7af  mov     rax, [rdi+58h]
0x1800be7b3  lea     r9, szPassword
0x1800be7ba  test    rbx, rbx
0x1800be7bd  mov     r8, rsi
0x1800be7c0  cmovnz  r9, rbx
0x1800be7c4  mov     rdx, [rax+8]
0x1800be7c8  mov     r10d, [rax+10h]
0x1800be7cc  lea     rax, [rbp+var_18]
0x1800be7d0  mov     qword ptr [rsp+78h+var_40], rdx
0x1800be7d5  mov     dword ptr [rsp+78h+var_48], r10d
0x1800be7da  mov     qword ptr [rsp+78h+var_50], rax
0x1800be7df  lea     rax, [rbp+var_30]
0x1800be7e3  mov     [rsp+78h+var_58], rax
0x1800be7e8  call    McTemplateU0zzmmqbr4_EventWriteTransfer
0x1800be7ed  test    rbx, rbx
0x1800be7f0  jz      short loc_1800BE803
0x1800be7f2  mov     rcx, rbx; hMem
0x1800be7f5  call    PkiDefaultCryptFree
0x1800be7fa  jmp     short loc_1800BE803
0x1800be7fc  mov     dword ptr [rdi+7Ch], 0
0x1800be803  test    r13d, r13d
0x1800be806  jnz     short loc_1800BE811
0x1800be808  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x1800be80b  call    cs:__imp_SetLastError
0x1800be811  mov     eax, r13d
0x1800be814  add     rsp, 78h
0x1800be818  pop     r15
0x1800be81a  pop     r14
0x1800be81c  pop     r13
0x1800be81e  pop     r12
0x1800be820  pop     rdi
0x1800be821  pop     rsi
0x1800be822  pop     rbx
0x1800be823  pop     rbp
0x1800be824  retn
```
