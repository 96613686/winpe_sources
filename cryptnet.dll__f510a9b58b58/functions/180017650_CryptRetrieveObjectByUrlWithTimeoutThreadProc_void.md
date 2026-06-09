# CryptRetrieveObjectByUrlWithTimeoutThreadProc(void *)

- ea: `0x180017650`
- end: `0x180017aae`
- name: `?CryptRetrieveObjectByUrlWithTimeoutThreadProc@@YAKPEAX@Z`
- size: `1118`
- prototype: `void __fastcall __noreturn(const wchar_t **Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180005940`
- `0x180007c00`
- `0x18000a990`
- `0x18000bb78`
- `0x18000be30`
- `0x180017650`
- `0x180017ac0`
- `0x180026552`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800179cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800179cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177c4`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800177ee`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800177ee`
- `CRYPT32!I_CertDiagControl` at `0x180017685`
- `CRYPT32!I_CertDiagControl` at `0x180017741`
- `CRYPT32!I_CertDiagControl` at `0x18001786a`
- `CRYPT32!I_CertDiagControl` at `0x1800179c2`
- `CRYPT32!I_CertDiagControl` at `0x180017685`
- `CRYPT32!I_CertDiagControl` at `0x180017741`
- `CRYPT32!I_CertDiagControl` at `0x18001786a`
- `CRYPT32!I_CertDiagControl` at `0x1800179c2`
- `CRYPT32!CertCloseStore` at `0x180017a74`
- `CRYPT32!CertCloseStore` at `0x180017a74`
- `CRYPT32!CertFreeCTLContext` at `0x180017a42`
- `CRYPT32!CertFreeCTLContext` at `0x180017a42`
- `CRYPT32!CertFreeCertificateContext` at `0x180017a2e`
- `CRYPT32!CertFreeCertificateContext` at `0x180017a2e`
- `CRYPT32!CertFreeCRLContext` at `0x180017a56`
- `CRYPT32!CertFreeCRLContext` at `0x180017a56`
- `CRYPT32!CryptMemFree` at `0x180017a82`
- `CRYPT32!CryptMemFree` at `0x180017a8d`
- `CRYPT32!CryptMemFree` at `0x180017a98`
- `CRYPT32!CryptMemFree` at `0x180017aa3`
- `CRYPT32!CryptMemFree` at `0x180017a82`
- `CRYPT32!CryptMemFree` at `0x180017a8d`
- `CRYPT32!CryptMemFree` at `0x180017a98`
- `CRYPT32!CryptMemFree` at `0x180017aa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800176f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800176f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017751`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017830`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001798b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017830`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001798b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180017780`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180017780`

## string_xrefs

- `0x180017840`: `PendingNetworkRetrievalComplete`
- `0x180017878`: `CRYPTNET.DLL --> CryptRetrieveObjectByUrl, pending completed for : %S\n`

## pseudocode

```c
void __fastcall __noreturn CryptRetrieveObjectByUrlWithTimeoutThreadProc(const wchar_t **Parameter)
{
  __int64 v2; // r15
  _DWORD *v3; // rdi
  unsigned int *v4; // r12
  char **v5; // rsi
  bool v6; // zf
  HMODULE v7; // r13
  DWORD v8; // edi
  const wchar_t *v9; // rcx
  CERT_CONTEXT *v10; // rdi
  char *v11; // rsi
  const wchar_t *v12; // rcx
  wchar_t *v13; // rcx
  wchar_t *v14; // rcx
  wchar_t *v15; // rcx
  const wchar_t **v16; // rcx
  const wchar_t *v17; // rcx
  int v18; // r14d
  unsigned int v19; // r12d
  __int64 v20; // rax
  SIZE_T v21; // rsi
  const wchar_t **v22; // rax
  const wchar_t **v23; // rdi
  _QWORD v24[2]; // [rsp+50h] [rbp-29h] BYREF
  const wchar_t *v25; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+68h] [rbp-11h]
  int v27; // [rsp+6Ch] [rbp-Dh]
  __int128 v28; // [rsp+70h] [rbp-9h]
  __int128 v29; // [rsp+80h] [rbp+7h]
  DWORD dwErrCode; // [rsp+E0h] [rbp+67h] BYREF
  int v31; // [rsp+E8h] [rbp+6Fh] BYREF
  int v32; // [rsp+F0h] [rbp+77h]
  __int64 v33; // [rsp+F8h] [rbp+7Fh] BYREF

  v31 = *((_DWORD *)Parameter + 6);
  v33 = 0;
  I_CertDiagControl(7, &v31, &v33);
  v2 = v33;
  v3 = operator new(0x30u);
  if ( v3 )
  {
    v3[2] = 1;
    *(_QWORD *)v3 = &CObjectRetrievalManager::`vftable';
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 5) = 0;
  }
  else
  {
    v3 = 0;
  }
  v4 = (unsigned int *)Parameter + 7;
  v5 = (char **)(Parameter + 2);
  if ( v3 )
  {
    *((_DWORD *)Parameter + 56) = CObjectRetrievalManager::RetrieveObjectByUrl(
                                    (CObjectRetrievalManager *)v3,
                                    *Parameter,
                                    *v5,
                                    *((_DWORD *)Parameter + 6),
                                    *v4,
                                    (struct _CRYPT_BLOB_ARRAY **)Parameter + 4,
                                    0,
                                    0,
                                    0,
                                    (struct _CRYPT_RETRIEVE_AUX_INFO *)(Parameter + 5));
    *((_DWORD *)Parameter + 57) = GetLastError();
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
  }
  else
  {
    *((_DWORD *)Parameter + 57) = -2147024882;
    *((_DWORD *)Parameter + 56) = 0;
  }
  EnterCriticalSection(&CrobuCriticalSection);
  v6 = *((_DWORD *)Parameter + 62) == 1;
  v7 = (HMODULE)Parameter[29];
  Parameter[29] = 0;
  if ( v6 )
  {
    v8 = 0;
    if ( v2 )
    {
      v24[1] = Parameter[34];
      dwErrCode = 0;
      v24[0] = v2;
      I_CertDiagControl(9, v24, &dwErrCode);
      v8 = dwErrCode;
    }
    SetEvent((HANDLE)Parameter[30]);
    *((_DWORD *)Parameter + 62) = 2;
    if ( !v8 )
    {
      LeaveCriticalSection(&CrobuCriticalSection);
      goto LABEL_10;
    }
    v17 = *Parameter;
    v18 = *((_DWORD *)Parameter + 56);
    v19 = *v4;
    dwErrCode = *((_DWORD *)Parameter + 57);
    v24[0] = *v5;
    v32 = *((_DWORD *)Parameter + 6);
    if ( v17 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v17[v20] );
    }
    else
    {
      LODWORD(v20) = 0;
    }
    v21 = (unsigned int)(2 * v20 + 2);
    v22 = (const wchar_t **)PkiNonzeroAlloc(v21);
    v23 = v22;
    if ( v22 )
      memcpy_0(v22, *Parameter, (unsigned int)v21);
    *((_DWORD *)Parameter + 70) = 1;
    LeaveCriticalSection(&CrobuCriticalSection);
    v27 = 3;
    v26 = 0;
    v25 = L"NetworkRetrievalHasNestedEvents";
    v28 = 0;
    v29 = 0;
    I_CertDiagControl(11, &v25, 0);
    SetLastError(dwErrCode);
    CryptDiagRetrieveObjectByUrlEnd(v2, v18, (_DWORD)v23, v24[0], v32, v19, 0, 0);
    v16 = v23;
LABEL_29:
    operator delete(v16);
LABEL_10:
    if ( v7 )
      FreeLibraryAndExitThread(v7, 0);
    ExitThread(0);
  }
  v9 = Parameter[32];
  v10 = (CERT_CONTEXT *)Parameter[4];
  v11 = *v5;
  if ( v9 )
    *((_QWORD *)v9 + 33) = Parameter[33];
  v12 = Parameter[33];
  if ( v12 )
    *((_QWORD *)v12 + 32) = Parameter[32];
  else
    pCrobuPendingHead = (struct _CROBU_ENTRY *)Parameter[32];
  LeaveCriticalSection(&CrobuCriticalSection);
  v26 = 54;
  v27 = 3;
  v25 = L"PendingNetworkRetrievalComplete";
  v28 = 0;
  v29 = 0;
  I_CertDiagControl(11, &v25, 0);
  if ( v2 )
  {
    SetLastError(*((_DWORD *)Parameter + 57));
    CryptDiagRetrieveObjectByUrlEnd(
      v2,
      *((_DWORD *)Parameter + 56),
      (unsigned int)*Parameter,
      (_DWORD)v11,
      *((_DWORD *)Parameter + 6),
      *v4,
      (__int64)v10,
      (__int64)(Parameter + 5));
  }
  I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> CryptRetrieveObjectByUrl, pending completed for : %S\n", *Parameter);
  if ( !v10 )
  {
LABEL_22:
    v13 = (wchar_t *)Parameter[24];
    if ( v13 )
      CryptMemFree(v13);
    v14 = (wchar_t *)Parameter[25];
    if ( v14 )
      CryptMemFree(v14);
    v15 = (wchar_t *)Parameter[26];
    if ( v15 )
      CryptMemFree(v15);
    v16 = Parameter;
    goto LABEL_29;
  }
  if ( !v11 || v11 == (char *)6 )
  {
    CryptMemFree(v10);
    goto LABEL_22;
  }
  if ( ((_BYTE)Parameter[3] & 1) == 0 )
  {
    if ( v11 == (char *)1 )
    {
      CertFreeCertificateContext(v10);
      goto LABEL_22;
    }
    if ( v11 == (char *)3 )
    {
      CertFreeCTLContext((PCCTL_CONTEXT)v10);
      goto LABEL_22;
    }
    if ( v11 == (char *)2 )
    {
      CertFreeCRLContext((PCCRL_CONTEXT)v10);
      goto LABEL_22;
    }
    if ( (unsigned __int64)(v11 - 4) > 1 )
      goto LABEL_22;
  }
  CertCloseStore(v10, 0);
  goto LABEL_22;
}

```

## disassembly

```asm
0x180017650  push    rbp
0x180017652  push    rbx
0x180017653  push    rsi
0x180017654  push    rdi
0x180017655  push    r12
0x180017657  push    r13
0x180017659  push    r14
0x18001765b  push    r15
0x18001765d  lea     rbp, [rsp-1Fh]
0x180017662  sub     rsp, 98h
0x180017669  mov     eax, [rcx+18h]
0x18001766c  lea     r8, [rbp+57h+arg_18]
0x180017670  xor     r13d, r13d
0x180017673  mov     [rbp+57h+arg_8], eax
0x180017676  mov     rbx, rcx
0x180017679  mov     [rbp+57h+arg_18], r13
0x18001767d  lea     rdx, [rbp+57h+arg_8]
0x180017681  lea     ecx, [r13+7]
0x180017685  call    cs:__imp_I_CertDiagControl
0x18001768b  mov     r15, [rbp+57h+arg_18]
0x18001768f  lea     ecx, [r13+30h]; uBytes
0x180017693  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017698  mov     rdi, rax
0x18001769b  test    rax, rax
0x18001769e  jz      loc_1800177E4
0x1800176a4  lea     rax, ??_7CObjectRetrievalManager@@6B@; const CObjectRetrievalManager::`vftable'
0x1800176ab  mov     dword ptr [rdi+8], 1
0x1800176b2  mov     [rdi], rax
0x1800176b5  mov     [rdi+10h], r13
0x1800176b9  mov     [rdi+18h], r13
0x1800176bd  mov     [rdi+20h], r13
0x1800176c1  mov     [rdi+28h], r13
0x1800176c5  lea     r14, [rbx+20h]
0x1800176c9  lea     r12, [rbx+1Ch]
0x1800176cd  lea     rsi, [rbx+10h]
0x1800176d1  test    rdi, rdi
0x1800176d4  jnz     loc_180017787
0x1800176da  mov     dword ptr [rbx+0E4h], 8007000Eh
0x1800176e4  mov     [rbx+0E0h], r13d
0x1800176eb  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800176f2  call    cs:__imp_EnterCriticalSection
0x1800176f8  cmp     dword ptr [rbx+0F8h], 1
0x1800176ff  mov     r13, [rbx+0E8h]
0x180017706  mov     qword ptr [rbx+0E8h], 0
0x180017711  jnz     loc_1800177F5
0x180017717  xor     r14d, r14d
0x18001771a  mov     edi, r14d
0x18001771d  test    r15, r15
0x180017720  jz      short loc_18001774A
0x180017722  mov     rax, [rbx+110h]
0x180017729  lea     r8, [rbp+57h+dwErrCode]
0x18001772d  lea     rdx, [rbp+57h+var_80]
0x180017731  mov     [rbp+57h+var_78], rax
0x180017735  lea     ecx, [r14+9]
0x180017739  mov     [rbp+57h+dwErrCode], r14d
0x18001773d  mov     [rbp+57h+var_80], r15
0x180017741  call    cs:__imp_I_CertDiagControl
0x180017747  mov     edi, [rbp+57h+dwErrCode]
0x18001774a  mov     rcx, [rbx+0F0h]; hEvent
0x180017751  call    cs:__imp_SetEvent
0x180017757  mov     dword ptr [rbx+0F8h], 2
0x180017761  test    edi, edi
0x180017763  jnz     loc_180017918
0x180017769  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017770  call    cs:__imp_LeaveCriticalSection
0x180017776  test    r13, r13
0x180017779  jz      short loc_1800177EC
0x18001777b  xor     edx, edx; dwExitCode
0x18001777d  mov     rcx, r13; hLibModule
0x180017780  call    cs:__imp_FreeLibraryAndExitThread
0x180017786  int     3; Trap to Debugger
0x180017787  mov     r9d, [rbx+18h]; unsigned int
0x18001778b  lea     rax, [rbx+28h]
0x18001778f  mov     r8, [rsi]; char *
0x180017792  mov     rcx, rdi; this
0x180017795  mov     rdx, [rbx]; unsigned __int16 *
0x180017798  mov     [rsp+0D0h+var_88], rax; struct _CRYPT_RETRIEVE_AUX_INFO *
0x18001779d  mov     eax, [r12]
0x1800177a1  mov     [rsp+0D0h+var_90], r13; struct _CERT_CONTEXT *
0x1800177a6  mov     [rsp+0D0h+var_98], r13; struct _CRYPT_CREDENTIALS *
0x1800177ab  mov     [rsp+0D0h+var_A0], r13; void *
0x1800177b0  mov     [rsp+0D0h+var_A8], r14; struct _CRYPT_BLOB_ARRAY **
0x1800177b5  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x1800177b9  call    ?RetrieveObjectByUrl@CObjectRetrievalManager@@QEAAHPEBGPEBDKKPEAPEAXPEAXPEAU_CRYPT_CREDENTIALS@@3PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z; CObjectRetrievalManager::RetrieveObjectByUrl(ushort const *,char const *,ulong,ulong,void * *,void *,_CRYPT_CREDENTIALS *,void *,_CRYPT_RETRIEVE_AUX_INFO *)
0x1800177be  mov     [rbx+0E0h], eax
0x1800177c4  call    cs:__imp_GetLastError
0x1800177ca  mov     [rbx+0E4h], eax
0x1800177d0  mov     rcx, rdi
0x1800177d3  mov     rax, [rdi]
0x1800177d6  mov     rax, [rax+8]
0x1800177da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177df  jmp     loc_1800176EB
0x1800177e4  mov     rdi, r13
0x1800177e7  jmp     loc_1800176C5
0x1800177ec  xor     ecx, ecx; dwExitCode
0x1800177ee  call    cs:__imp_ExitThread
0x1800177f5  mov     rcx, [rbx+100h]
0x1800177fc  mov     rdi, [r14]
0x1800177ff  mov     rsi, [rsi]
0x180017802  test    rcx, rcx
0x180017805  jnz     loc_180017A01
0x18001780b  mov     rcx, [rbx+108h]
0x180017812  mov     rax, [rbx+100h]
0x180017819  test    rcx, rcx
0x18001781c  jz      loc_1800178CA
0x180017822  mov     [rcx+100h], rax
0x180017829  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017830  call    cs:__imp_LeaveCriticalSection
0x180017836  xor     r8d, r8d
0x180017839  mov     [rbp+57h+var_68], 36h ; '6'
0x180017840  lea     rax, aPendingnetwork; "PendingNetworkRetrievalComplete"
0x180017847  mov     [rbp+57h+var_64], 3
0x18001784e  xorps   xmm0, xmm0
0x180017851  mov     [rbp+57h+var_70], rax
0x180017855  xorps   xmm1, xmm1
0x180017858  lea     rdx, [rbp+57h+var_70]
0x18001785c  lea     ecx, [r8+0Bh]
0x180017860  movdqu  [rbp+57h+var_60], xmm0
0x180017865  movdqu  [rbp+57h+var_50], xmm1
0x18001786a  call    cs:__imp_I_CertDiagControl
0x180017870  test    r15, r15
0x180017873  jnz     short loc_1800178D6
0x180017875  mov     rdx, [rbx]
0x180017878  lea     rcx, aCryptnetDllCry_1; "CRYPTNET.DLL --> CryptRetrieveObjectByU"...
0x18001787f  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x180017884  test    rdi, rdi
0x180017887  jnz     loc_180017A14
0x18001788d  mov     rcx, [rbx+0C0h]; pv
0x180017894  test    rcx, rcx
0x180017897  jnz     loc_180017A8D
0x18001789d  mov     rcx, [rbx+0C8h]; pv
0x1800178a4  test    rcx, rcx
0x1800178a7  jnz     loc_180017A98
0x1800178ad  mov     rcx, [rbx+0D0h]; pv
0x1800178b4  test    rcx, rcx
0x1800178b7  jnz     loc_180017AA3
0x1800178bd  mov     rcx, rbx; hMem
0x1800178c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800178c5  jmp     loc_180017776
0x1800178ca  mov     cs:?pCrobuPendingHead@@3PEAU_CROBU_ENTRY@@EA, rax; _CROBU_ENTRY * pCrobuPendingHead
0x1800178d1  jmp     loc_180017829
0x1800178d6  mov     ecx, [rbx+0E4h]; dwErrCode
0x1800178dc  call    cs:__imp_SetLastError
0x1800178e2  mov     r8, [rbx]
0x1800178e5  lea     rax, [rbx+28h]
0x1800178e9  mov     edx, [rbx+0E0h]
0x1800178ef  mov     r9, rsi
0x1800178f2  mov     [rsp+0D0h+var_98], rax
0x1800178f7  mov     rcx, r15
0x1800178fa  mov     eax, [r12]
0x1800178fe  mov     [rsp+0D0h+var_A0], rdi
0x180017903  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180017907  mov     eax, [rbx+18h]
0x18001790a  mov     [rsp+0D0h+var_B0], eax
0x18001790e  call    CryptDiagRetrieveObjectByUrlEnd
0x180017913  jmp     loc_180017875
0x180017918  mov     eax, [rbx+0E4h]
0x18001791e  xor     edx, edx
0x180017920  mov     rcx, [rbx]
0x180017923  mov     r14d, [rbx+0E0h]
0x18001792a  mov     r12d, [r12]
0x18001792e  mov     [rbp+57h+dwErrCode], eax
0x180017931  mov     rax, [rsi]
0x180017934  mov     [rbp+57h+var_80], rax
0x180017938  mov     eax, [rbx+18h]
0x18001793b  mov     [rbp+57h+arg_10], eax
0x18001793e  test    rcx, rcx
0x180017941  jz      short loc_180017952
0x180017943  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017947  inc     rax
0x18001794a  cmp     [rcx+rax*2], dx
0x18001794e  jnz     short loc_180017947
0x180017950  jmp     short loc_180017954
0x180017952  mov     eax, edx
0x180017954  lea     eax, ds:2[rax*2]
0x18001795b  mov     ecx, eax; uBytes
0x18001795d  mov     esi, eax
0x18001795f  call    PkiNonzeroAlloc
0x180017964  mov     rdi, rax
0x180017967  test    rax, rax
0x18001796a  jz      short loc_18001797A
0x18001796c  mov     rdx, [rbx]; Src
0x18001796f  mov     r8d, esi; Size
0x180017972  mov     rcx, rax; void *
0x180017975  call    memcpy_0
0x18001797a  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017981  mov     dword ptr [rbx+118h], 1
0x18001798b  call    cs:__imp_LeaveCriticalSection
0x180017991  xor     ebx, ebx
0x180017993  mov     [rbp+57h+var_64], 3
0x18001799a  lea     rax, aNetworkretriev; "NetworkRetrievalHasNestedEvents"
0x1800179a1  mov     [rbp+57h+var_68], ebx
0x1800179a4  xorps   xmm0, xmm0
0x1800179a7  mov     [rbp+57h+var_70], rax
0x1800179ab  xorps   xmm1, xmm1
0x1800179ae  lea     rdx, [rbp+57h+var_70]
0x1800179b2  lea     ecx, [rbx+0Bh]
0x1800179b5  xor     r8d, r8d
0x1800179b8  movdqu  [rbp+57h+var_60], xmm0
0x1800179bd  movdqu  [rbp+57h+var_50], xmm1
0x1800179c2  call    cs:__imp_I_CertDiagControl
0x1800179c8  mov     ecx, [rbp+57h+dwErrCode]; dwErrCode
0x1800179cb  call    cs:__imp_SetLastError
0x1800179d1  mov     eax, [rbp+57h+arg_10]
0x1800179d4  mov     r8, rdi
0x1800179d7  mov     r9, [rbp+57h+var_80]
0x1800179db  mov     edx, r14d
0x1800179de  mov     [rsp+0D0h+var_98], rbx
0x1800179e3  mov     rcx, r15
0x1800179e6  mov     [rsp+0D0h+var_A0], rbx
0x1800179eb  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x1800179f0  mov     [rsp+0D0h+var_B0], eax
0x1800179f4  call    CryptDiagRetrieveObjectByUrlEnd
0x1800179f9  mov     rcx, rdi
0x1800179fc  jmp     loc_1800178C0
0x180017a01  mov     rax, [rbx+108h]
0x180017a08  mov     [rcx+108h], rax
0x180017a0f  jmp     loc_18001780B
0x180017a14  test    rsi, rsi
0x180017a17  jz      short loc_180017A7F
0x180017a19  cmp     rsi, 6
0x180017a1d  jz      short loc_180017A7F
0x180017a1f  test    byte ptr [rbx+18h], 1
0x180017a23  jnz     short loc_180017A6F
0x180017a25  cmp     rsi, 1
0x180017a29  jnz     short loc_180017A39
0x180017a2b  mov     rcx, rdi; pCertContext
0x180017a2e  call    cs:__imp_CertFreeCertificateContext
0x180017a34  jmp     loc_18001788D
0x180017a39  cmp     rsi, 3
0x180017a3d  jnz     short loc_180017A4D
0x180017a3f  mov     rcx, rdi; pCtlContext
0x180017a42  call    cs:__imp_CertFreeCTLContext
0x180017a48  jmp     loc_18001788D
0x180017a4d  cmp     rsi, 2
0x180017a51  jnz     short loc_180017A61
0x180017a53  mov     rcx, rdi; pCrlContext
0x180017a56  call    cs:__imp_CertFreeCRLContext
0x180017a5c  jmp     loc_18001788D
0x180017a61  lea     rax, [rsi-4]
0x180017a65  cmp     rax, 1
0x180017a69  ja      loc_18001788D
0x180017a6f  xor     edx, edx; dwFlags
0x180017a71  mov     rcx, rdi; hCertStore
0x180017a74  call    cs:__imp_CertCloseStore
0x180017a7a  jmp     loc_18001788D
0x180017a7f  mov     rcx, rdi; pv
0x180017a82  call    cs:__imp_CryptMemFree
0x180017a88  jmp     loc_18001788D
0x180017a8d  call    cs:__imp_CryptMemFree
0x180017a93  jmp     loc_18001789D
0x180017a98  call    cs:__imp_CryptMemFree
0x180017a9e  jmp     loc_1800178AD
0x180017aa3  call    cs:__imp_CryptMemFree
0x180017aa9  jmp     loc_1800178BD
```
