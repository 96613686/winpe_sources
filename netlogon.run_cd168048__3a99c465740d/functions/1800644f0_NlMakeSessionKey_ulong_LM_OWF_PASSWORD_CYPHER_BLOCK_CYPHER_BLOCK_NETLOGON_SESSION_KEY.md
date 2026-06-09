# NlMakeSessionKey(ulong,_LM_OWF_PASSWORD *,_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *)

- ea: `0x1800644f0`
- end: `0x180064914`
- name: `?NlMakeSessionKey@@YAJKPEAU_LM_OWF_PASSWORD@@PEAU_CYPHER_BLOCK@@1PEAU_NETLOGON_SESSION_KEY@@@Z`
- size: `1060`
- prototype: `int(unsigned int, struct _LM_OWF_PASSWORD *, struct _CYPHER_BLOCK *, struct _CYPHER_BLOCK *, struct _NETLOGON_SESSION_KEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180038f68`
- `0x180061b40`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x1800644f0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800645b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006461f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800645b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006461f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800648ba`
- `bcrypt!BCryptHashData` at `0x18006467e`
- `bcrypt!BCryptHashData` at `0x1800646a2`
- `bcrypt!BCryptHashData` at `0x18006467e`
- `bcrypt!BCryptHashData` at `0x1800646a2`
- `bcrypt!BCryptFinishHash` at `0x1800646c6`
- `bcrypt!BCryptFinishHash` at `0x1800646c6`
- `bcrypt!BCryptDestroyHash` at `0x180064892`
- `bcrypt!BCryptDestroyHash` at `0x180064892`
- `bcrypt!BCryptCreateHash` at `0x180064657`
- `bcrypt!BCryptCreateHash` at `0x180064657`
- `bcrypt!BCryptGetProperty` at `0x18006458a`
- `bcrypt!BCryptGetProperty` at `0x1800645fb`
- `bcrypt!BCryptGetProperty` at `0x18006458a`
- `bcrypt!BCryptGetProperty` at `0x1800645fb`
- `CRYPTBASE!SystemFunction001` at `0x180064816`
- `CRYPTBASE!SystemFunction001` at `0x180064847`
- `CRYPTBASE!SystemFunction001` at `0x180064816`
- `CRYPTBASE!SystemFunction001` at `0x180064847`
- `cryptdll!CDLocateCheckSum` at `0x18006471a`
- `cryptdll!CDLocateCheckSum` at `0x18006471a`

## string_xrefs

- `0x18006475c`: `Check->CheckSumSize <= sizeof(LocalChecksum)`
- `0x1800646e8`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x180064755`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`

## pseudocode

```c
__int64 __fastcall NlMakeSessionKey(
        int a1,
        struct _LM_OWF_PASSWORD *a2,
        struct _CYPHER_BLOCK *a3,
        struct _CYPHER_BLOCK *a4,
        struct _NETLOGON_SESSION_KEY *a5)
{
  __int64 v7; // r14
  UCHAR *v8; // r12
  UCHAR *v9; // rsi
  NTSTATUS Property; // eax
  NTSTATUS v11; // ebx
  NTSTATUS v12; // eax
  char *v13; // r9
  __int128 v14; // xmm0
  int v15; // eax
  char *v16; // r9
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int128 *v20; // rax
  __int64 v21; // rcx
  int *v22; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-41h] BYREF
  UCHAR v25[4]; // [rsp+44h] [rbp-3Dh] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v27; // [rsp+50h] [rbp-31h] BYREF
  __int64 v28; // [rsp+58h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-21h] BYREF
  PUCHAR pbInput; // [rsp+68h] [rbp-19h]
  int v31; // [rsp+70h] [rbp-11h] BYREF
  __int16 v32; // [rsp+74h] [rbp-Dh]
  CHAR v33; // [rsp+76h] [rbp-Bh]
  __int128 v34; // [rsp+78h] [rbp-9h] BYREF
  __int128 v35; // [rsp+88h] [rbp+7h] BYREF

  pbInput = (PUCHAR)a4;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v7 = 16;
  v28 = 0;
  v8 = 0;
  v27 = 0;
  v9 = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v25 = 0;
  pcbResult = 0;
  *(_OWORD *)a5 = 0;
  v34 = 0;
  if ( (a1 & 0x1000000) != 0 )
  {
    Property = BCryptGetProperty(NlGlobalSha256Handle, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v11 = Property;
    if ( pcbResult != 4 )
    {
LABEL_3:
      v11 = -1073741595;
      goto LABEL_29;
    }
    if ( Property < 0 )
      goto LABEL_29;
    v8 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
    if ( !v8 )
      goto LABEL_6;
    v12 = BCryptGetProperty(NlGlobalSha256Handle, L"HashDigestLength", v25, 4u, &pcbResult, 0);
    v11 = v12;
    if ( pcbResult != 4 )
      goto LABEL_3;
    if ( v12 < 0 )
      goto LABEL_29;
    v9 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v25);
    if ( !v9 )
    {
LABEL_6:
      v11 = -1073741670;
      goto LABEL_29;
    }
    v11 = BCryptCreateHash(NlGlobalSha256Handle, &phHash, v8, *(ULONG *)pbOutput, (PUCHAR)a2, 0x10u, 0);
    if ( v11 >= 0 )
    {
      v11 = BCryptHashData(phHash, (PUCHAR)a3, 8u, 0);
      if ( v11 >= 0 )
      {
        v11 = BCryptHashData(phHash, pbInput, 8u, 0);
        if ( v11 >= 0 )
        {
          v11 = BCryptFinishHash(phHash, v9, *(ULONG *)v25, 0);
          if ( v11 >= 0 )
          {
            if ( *(_DWORD *)v25 < 0x10u )
              NlAssertFailed(
                "HashSize >= sizeof(*SessionKey)",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiauth.cxx",
                0xC9u,
                v13);
            v14 = *(_OWORD *)v9;
            goto LABEL_26;
          }
        }
      }
    }
  }
  else
  {
    if ( (a1 & 0x4000) != 0 )
    {
      v35 = 0;
      v15 = CDLocateCheckSum(4294967159LL, &v27);
      v11 = v15;
      if ( v15 < 0 )
      {
        NlPrintRoutine(0x100u, L"NlMakeSessionKey: Failed to load checksum routines: 0x%x\n", (unsigned int)v15);
        goto LABEL_29;
      }
      v17 = v27;
      if ( *(_DWORD *)(v27 + 4) > 0x10u )
      {
        NlAssertFailed(
          "Check->CheckSumSize <= sizeof(LocalChecksum)",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiauth.cxx",
          0xDFu,
          v16);
        v17 = v27;
      }
      v18 = (*(__int64 (__fastcall **)(struct _LM_OWF_PASSWORD *, __int64, _QWORD, __int64 *))(v17 + 48))(
              a2,
              16,
              0,
              &v28);
      v11 = v18;
      if ( v18 < 0 )
      {
        NlPrintRoutine(0x100u, L"NlMakeSessionKey: Failed to initialize checksum routines: 0x%x\n", (unsigned int)v18);
        goto LABEL_29;
      }
      (*(void (__fastcall **)(__int64, __int64, struct _CYPHER_BLOCK *))(v27 + 24))(v28, 8, a3);
      (*(void (__fastcall **)(__int64, __int64, PUCHAR))(v27 + 24))(v28, 8, pbInput);
      (*(void (__fastcall **)(__int64, __int128 *))(v27 + 32))(v28, &v35);
      v14 = v35;
LABEL_26:
      *(_OWORD *)a5 = v14;
      goto LABEL_29;
    }
    *(_DWORD *)a5 = *(_DWORD *)a3->data + *(_DWORD *)a4->data;
    *((_DWORD *)a5 + 1) = *(_DWORD *)&a3->data[4] + *(_DWORD *)&a4->data[4];
    v31 = *(_DWORD *)a2->data[0].data;
    v32 = *(_WORD *)&a2->data[0].data[4];
    v33 = a2->data[0].data[6];
    v11 = SystemFunction001(a5, &v31, &v34);
    if ( v11 >= 0 )
    {
      v31 = *(_DWORD *)&a2->data[1].data[1];
      v32 = *(_WORD *)&a2->data[1].data[5];
      v33 = a2->data[1].data[7];
      v11 = SystemFunction001(&v34, &v31, a5);
    }
  }
LABEL_29:
  if ( v28 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64 *))(v27 + 40))(&v28);
    v11 = v19;
    if ( v19 < 0 )
      NlPrintRoutine(0x100u, L"NlMakeSessionKey: Failed to finish checksum: 0x%x\n", (unsigned int)v19);
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v8 )
    LocalFree(v8);
  if ( v9 )
    LocalFree(v9);
  v20 = &v34;
  do
  {
    *(_BYTE *)v20 = 0;
    v20 = (__int128 *)((char *)v20 + 1);
    --v7;
  }
  while ( v7 );
  v21 = 7;
  v22 = &v31;
  do
  {
    *(_BYTE *)v22 = 0;
    v22 = (int *)((char *)v22 + 1);
    --v21;
  }
  while ( v21 );
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800644f0  mov     [rsp-8+arg_0], rbx
0x1800644f5  push    rbp
0x1800644f6  push    rsi
0x1800644f7  push    rdi
0x1800644f8  push    r12
0x1800644fa  push    r13
0x1800644fc  push    r14
0x1800644fe  push    r15
0x180064500  lea     rbp, [rsp-1Fh]
0x180064505  sub     rsp, 0A0h
0x18006450c  mov     rax, cs:__security_cookie
0x180064513  xor     rax, rsp
0x180064516  mov     [rbp+4Fh+var_38], rax
0x18006451a  mov     r15, [rbp+4Fh+arg_20]
0x18006451e  xor     eax, eax
0x180064520  mov     [rbp+4Fh+pbInput], r9
0x180064524  xorps   xmm0, xmm0
0x180064527  mov     [rbp+4Fh+var_60], eax
0x18006452a  mov     r13, r8
0x18006452d  mov     [rbp+4Fh+var_5C], ax
0x180064531  mov     rdi, rdx
0x180064534  mov     [rbp+4Fh+var_5A], al
0x180064537  lea     r14d, [rax+10h]
0x18006453b  mov     [rbp+4Fh+var_78], rax
0x18006453f  mov     r12d, eax
0x180064542  mov     [rbp+4Fh+var_80], rax
0x180064546  mov     esi, eax
0x180064548  mov     [rbp+4Fh+phHash], rax
0x18006454c  mov     dword ptr [rbp+4Fh+pbOutput], eax
0x18006454f  mov     dword ptr [rbp+4Fh+var_8C], eax
0x180064552  mov     [rbp+4Fh+var_90], eax
0x180064555  movups  xmmword ptr [r15], xmm0
0x180064559  movups  [rbp+4Fh+var_58], xmm0
0x18006455d  bt      ecx, 18h
0x180064561  jnb     loc_180064703
0x180064567  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x18006456e  lea     r9d, [rsi+4]; cbOutput
0x180064572  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x180064576  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x18006457a  lea     rax, [rbp+4Fh+var_90]
0x18006457e  lea     rdx, aObjectlength; "ObjectLength"
0x180064585  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18006458a  call    cs:__imp_BCryptGetProperty
0x180064591  nop     dword ptr [rax+rax+00h]
0x180064596  cmp     [rbp+4Fh+var_90], 4
0x18006459a  mov     ebx, eax
0x18006459c  jz      short loc_1800645A8
0x18006459e  mov     ebx, 0C00000E5h
0x1800645a3  jmp     loc_180064855
0x1800645a8  test    eax, eax
0x1800645aa  js      loc_180064855
0x1800645b0  mov     edx, dword ptr [rbp+4Fh+pbOutput]; uBytes
0x1800645b3  mov     ecx, 40h ; '@'; uFlags
0x1800645b8  call    cs:__imp_LocalAlloc
0x1800645bf  nop     dword ptr [rax+rax+00h]
0x1800645c4  mov     r12, rax
0x1800645c7  test    rax, rax
0x1800645ca  jnz     short loc_1800645D6
0x1800645cc  mov     ebx, 0C000009Ah
0x1800645d1  jmp     loc_180064855
0x1800645d6  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x1800645dd  lea     rax, [rbp+4Fh+var_90]
0x1800645e1  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x1800645e5  lea     r8, [rbp+4Fh+var_8C]; pbOutput
0x1800645e9  mov     r9d, 4; cbOutput
0x1800645ef  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x1800645f4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800645fb  call    cs:__imp_BCryptGetProperty
0x180064602  nop     dword ptr [rax+rax+00h]
0x180064607  cmp     [rbp+4Fh+var_90], 4
0x18006460b  mov     ebx, eax
0x18006460d  jnz     short loc_18006459E
0x18006460f  test    eax, eax
0x180064611  js      loc_180064855
0x180064617  mov     edx, dword ptr [rbp+4Fh+var_8C]; uBytes
0x18006461a  mov     ecx, 40h ; '@'; uFlags
0x18006461f  call    cs:__imp_LocalAlloc
0x180064626  nop     dword ptr [rax+rax+00h]
0x18006462b  mov     rsi, rax
0x18006462e  test    rax, rax
0x180064631  jz      short loc_1800645CC
0x180064633  mov     r9d, dword ptr [rbp+4Fh+pbOutput]; cbHashObject
0x180064637  lea     rdx, [rbp+4Fh+phHash]; phHash
0x18006463b  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hAlgorithm
0x180064642  mov     r8, r12; pbHashObject
0x180064645  mov     [rsp+0D0h+var_A0], 0; dwFlags
0x18006464d  mov     [rsp+0D0h+dwFlags], r14d; cbSecret
0x180064652  mov     [rsp+0D0h+pcbResult], rdi; pbSecret
0x180064657  call    cs:__imp_BCryptCreateHash
0x18006465e  nop     dword ptr [rax+rax+00h]
0x180064663  mov     ebx, eax
0x180064665  test    eax, eax
0x180064667  js      loc_180064855
0x18006466d  mov     rcx, [rbp+4Fh+phHash]; hHash
0x180064671  xor     r9d, r9d; dwFlags
0x180064674  mov     rdx, r13; pbInput
0x180064677  lea     edi, [r9+8]
0x18006467b  mov     r8d, edi; cbInput
0x18006467e  call    cs:__imp_BCryptHashData
0x180064685  nop     dword ptr [rax+rax+00h]
0x18006468a  mov     ebx, eax
0x18006468c  test    eax, eax
0x18006468e  js      loc_180064855
0x180064694  mov     rdx, [rbp+4Fh+pbInput]; pbInput
0x180064698  xor     r9d, r9d; dwFlags
0x18006469b  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18006469f  mov     r8d, edi; cbInput
0x1800646a2  call    cs:__imp_BCryptHashData
0x1800646a9  nop     dword ptr [rax+rax+00h]
0x1800646ae  mov     ebx, eax
0x1800646b0  test    eax, eax
0x1800646b2  js      loc_180064855
0x1800646b8  mov     r8d, dword ptr [rbp+4Fh+var_8C]; cbOutput
0x1800646bc  xor     r9d, r9d; dwFlags
0x1800646bf  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800646c3  mov     rdx, rsi; pbOutput
0x1800646c6  call    cs:__imp_BCryptFinishHash
0x1800646cd  nop     dword ptr [rax+rax+00h]
0x1800646d2  mov     ebx, eax
0x1800646d4  test    eax, eax
0x1800646d6  js      loc_180064855
0x1800646dc  cmp     dword ptr [rbp+4Fh+var_8C], r14d
0x1800646e0  jnb     short loc_1800646FB
0x1800646e2  mov     r8d, 0C9h; unsigned int
0x1800646e8  lea     rdx, aOnecoreDsNetap_25; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800646ef  lea     rcx, aHashsizeSizeof; "HashSize >= sizeof(*SessionKey)"
0x1800646f6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800646fb  movups  xmm0, xmmword ptr [rsi]
0x1800646fe  jmp     loc_1800647DC
0x180064703  bt      ecx, 0Eh
0x180064707  jnb     loc_1800647E3
0x18006470d  lea     rdx, [rbp+4Fh+var_80]
0x180064711  mov     ecx, 0FFFFFF77h
0x180064716  movups  [rbp+4Fh+var_48], xmm0
0x18006471a  call    cs:__imp_CDLocateCheckSum
0x180064721  nop     dword ptr [rax+rax+00h]
0x180064726  mov     ebx, eax
0x180064728  test    eax, eax
0x18006472a  jns     short loc_180064745
0x18006472c  lea     rdx, aNlmakesessionk_1; "NlMakeSessionKey: Failed to load checks"...
0x180064733  mov     r8d, eax
0x180064736  mov     ecx, 100h; unsigned int
0x18006473b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180064740  jmp     loc_180064855
0x180064745  mov     rax, [rbp+4Fh+var_80]
0x180064749  cmp     [rax+4], r14d
0x18006474d  jbe     short loc_18006476C
0x18006474f  mov     r8d, 0DFh; unsigned int
0x180064755  lea     rdx, aOnecoreDsNetap_25; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006475c  lea     rcx, aCheckChecksums; "Check->CheckSumSize <= sizeof(LocalChec"...
0x180064763  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180064768  mov     rax, [rbp+4Fh+var_80]
0x18006476c  mov     rax, [rax+30h]
0x180064770  lea     r9, [rbp+4Fh+var_78]
0x180064774  xor     r8d, r8d
0x180064777  mov     edx, r14d
0x18006477a  mov     rcx, rdi
0x18006477d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064782  mov     ebx, eax
0x180064784  test    eax, eax
0x180064786  jns     short loc_180064791
0x180064788  lea     rdx, aNlmakesessionk_0; "NlMakeSessionKey: Failed to initialize "...
0x18006478f  jmp     short loc_180064733
0x180064791  mov     rax, [rbp+4Fh+var_80]
0x180064795  mov     edi, 8
0x18006479a  mov     rcx, [rbp+4Fh+var_78]
0x18006479e  mov     r8, r13
0x1800647a1  mov     edx, edi
0x1800647a3  mov     rax, [rax+18h]
0x1800647a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800647ac  mov     rax, [rbp+4Fh+var_80]
0x1800647b0  mov     edx, edi
0x1800647b2  mov     r8, [rbp+4Fh+pbInput]
0x1800647b6  mov     rcx, [rbp+4Fh+var_78]
0x1800647ba  mov     rax, [rax+18h]
0x1800647be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800647c3  mov     rax, [rbp+4Fh+var_80]
0x1800647c7  lea     rdx, [rbp+4Fh+var_48]
0x1800647cb  mov     rcx, [rbp+4Fh+var_78]
0x1800647cf  mov     rax, [rax+20h]
0x1800647d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800647d8  movups  xmm0, [rbp+4Fh+var_48]
0x1800647dc  movdqu  xmmword ptr [r15], xmm0
0x1800647e1  jmp     short loc_180064855
0x1800647e3  mov     eax, [r9]
0x1800647e6  mov     rcx, r15
0x1800647e9  add     eax, [r8]
0x1800647ec  mov     [r15], eax
0x1800647ef  mov     eax, [r9+4]
0x1800647f3  add     eax, [r8+4]
0x1800647f7  lea     r8, [rbp+4Fh+var_58]
0x1800647fb  mov     [r15+4], eax
0x1800647ff  mov     eax, [rdx]
0x180064801  mov     [rbp+4Fh+var_60], eax
0x180064804  movzx   eax, word ptr [rdx+4]
0x180064808  mov     [rbp+4Fh+var_5C], ax
0x18006480c  mov     al, [rdx+6]
0x18006480f  lea     rdx, [rbp+4Fh+var_60]
0x180064813  mov     [rbp+4Fh+var_5A], al
0x180064816  call    cs:__imp_SystemFunction001
0x18006481d  nop     dword ptr [rax+rax+00h]
0x180064822  mov     ebx, eax
0x180064824  test    eax, eax
0x180064826  js      short loc_180064855
0x180064828  mov     eax, [rdi+9]
0x18006482b  lea     rdx, [rbp+4Fh+var_60]
0x18006482f  mov     [rbp+4Fh+var_60], eax
0x180064832  lea     rcx, [rbp+4Fh+var_58]
0x180064836  movzx   eax, word ptr [rdi+0Dh]
0x18006483a  mov     r8, r15
0x18006483d  mov     [rbp+4Fh+var_5C], ax
0x180064841  mov     al, [rdi+0Fh]
0x180064844  mov     [rbp+4Fh+var_5A], al
0x180064847  call    cs:__imp_SystemFunction001
0x18006484e  nop     dword ptr [rax+rax+00h]
0x180064853  mov     ebx, eax
0x180064855  xor     r15d, r15d
0x180064858  cmp     [rbp+4Fh+var_78], r15
0x18006485c  jz      short loc_180064889
0x18006485e  mov     rax, [rbp+4Fh+var_80]
0x180064862  lea     rcx, [rbp+4Fh+var_78]
0x180064866  mov     rax, [rax+28h]
0x18006486a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006486f  mov     ebx, eax
0x180064871  test    eax, eax
0x180064873  jns     short loc_180064889
0x180064875  mov     r8d, eax
0x180064878  lea     rdx, aNlmakesessionk; "NlMakeSessionKey: Failed to finish chec"...
0x18006487f  mov     ecx, 100h; unsigned int
0x180064884  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180064889  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18006488d  test    rcx, rcx
0x180064890  jz      short loc_18006489E
0x180064892  call    cs:__imp_BCryptDestroyHash
0x180064899  nop     dword ptr [rax+rax+00h]
0x18006489e  test    r12, r12
0x1800648a1  jz      short loc_1800648B2
0x1800648a3  mov     rcx, r12; hMem
0x1800648a6  call    cs:__imp_LocalFree
0x1800648ad  nop     dword ptr [rax+rax+00h]
0x1800648b2  test    rsi, rsi
0x1800648b5  jz      short loc_1800648C6
0x1800648b7  mov     rcx, rsi; hMem
0x1800648ba  call    cs:__imp_LocalFree
0x1800648c1  nop     dword ptr [rax+rax+00h]
0x1800648c6  lea     rax, [rbp+4Fh+var_58]
0x1800648ca  mov     [rax], r15b
0x1800648cd  inc     rax
0x1800648d0  sub     r14, 1
0x1800648d4  jnz     short loc_1800648CA
0x1800648d6  lea     ecx, [r14+7]
0x1800648da  lea     rax, [rbp+4Fh+var_60]
0x1800648de  mov     [rax], r15b
0x1800648e1  inc     rax
0x1800648e4  sub     rcx, 1
0x1800648e8  jnz     short loc_1800648DE
0x1800648ea  mov     eax, ebx
0x1800648ec  mov     rcx, [rbp+4Fh+var_38]
0x1800648f0  xor     rcx, rsp; StackCookie
0x1800648f3  call    __security_check_cookie
0x1800648f8  mov     rbx, [rsp+0D0h+arg_0]
0x180064900  add     rsp, 0A0h
0x180064907  pop     r15
0x180064909  pop     r14
0x18006490b  pop     r13
0x18006490d  pop     r12
0x18006490f  pop     rdi
0x180064910  pop     rsi
0x180064911  pop     rbp
0x180064912  retn
```
