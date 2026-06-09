# NlMakeSessionKey(ulong,_LM_OWF_PASSWORD *,_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *)

- ea: `0x18005fff4`
- end: `0x1800603c3`
- name: `?NlMakeSessionKey@@YAJKPEAU_LM_OWF_PASSWORD@@PEAU_CYPHER_BLOCK@@1PEAU_NETLOGON_SESSION_KEY@@@Z`
- size: `975`
- prototype: `int(unsigned int, struct _LM_OWF_PASSWORD *, struct _CYPHER_BLOCK *, struct _CYPHER_BLOCK *, struct _NETLOGON_SESSION_KEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180036df8`
- `0x18005d780`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18005fff4`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800600b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060111`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800600b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060111`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060362`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060362`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060370`
- `bcrypt!BCryptHashData` at `0x180060164`
- `bcrypt!BCryptHashData` at `0x180060182`
- `bcrypt!BCryptHashData` at `0x180060164`
- `bcrypt!BCryptHashData` at `0x180060182`
- `bcrypt!BCryptFinishHash` at `0x1800601a0`
- `bcrypt!BCryptFinishHash` at `0x1800601a0`
- `bcrypt!BCryptDestroyHash` at `0x180060354`
- `bcrypt!BCryptDestroyHash` at `0x180060354`
- `bcrypt!BCryptCreateHash` at `0x180060143`
- `bcrypt!BCryptCreateHash` at `0x180060143`
- `bcrypt!BCryptGetProperty` at `0x18006008e`
- `bcrypt!BCryptGetProperty` at `0x1800600f3`
- `bcrypt!BCryptGetProperty` at `0x18006008e`
- `bcrypt!BCryptGetProperty` at `0x1800600f3`
- `CRYPTBASE!SystemFunction001` at `0x1800602e4`
- `CRYPTBASE!SystemFunction001` at `0x18006030f`
- `CRYPTBASE!SystemFunction001` at `0x1800602e4`
- `CRYPTBASE!SystemFunction001` at `0x18006030f`
- `cryptdll!CDLocateCheckSum` at `0x1800601ee`
- `cryptdll!CDLocateCheckSum` at `0x1800601ee`

## string_xrefs

- `0x18006022a`: `Check->CheckSumSize <= sizeof(LocalChecksum)`
- `0x1800601bc`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`
- `0x180060223`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiauth.cxx`

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
                201,
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
          223,
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
0x18005fff4  mov     [rsp-8+arg_0], rbx
0x18005fff9  push    rbp
0x18005fffa  push    rsi
0x18005fffb  push    rdi
0x18005fffc  push    r12
0x18005fffe  push    r13
0x180060000  push    r14
0x180060002  push    r15
0x180060004  lea     rbp, [rsp-1Fh]
0x180060009  sub     rsp, 0A0h
0x180060010  mov     rax, cs:__security_cookie
0x180060017  xor     rax, rsp
0x18006001a  mov     [rbp+4Fh+var_38], rax
0x18006001e  mov     r15, [rbp+4Fh+arg_20]
0x180060022  xor     eax, eax
0x180060024  mov     [rbp+4Fh+pbInput], r9
0x180060028  xorps   xmm0, xmm0
0x18006002b  mov     [rbp+4Fh+var_60], eax
0x18006002e  mov     r13, r8
0x180060031  mov     [rbp+4Fh+var_5C], ax
0x180060035  mov     rdi, rdx
0x180060038  mov     [rbp+4Fh+var_5A], al
0x18006003b  lea     r14d, [rax+10h]
0x18006003f  mov     [rbp+4Fh+var_78], rax
0x180060043  mov     r12d, eax
0x180060046  mov     [rbp+4Fh+var_80], rax
0x18006004a  mov     esi, eax
0x18006004c  mov     [rbp+4Fh+phHash], rax
0x180060050  mov     dword ptr [rbp+4Fh+pbOutput], eax
0x180060053  mov     dword ptr [rbp+4Fh+var_8C], eax
0x180060056  mov     [rbp+4Fh+var_90], eax
0x180060059  movups  xmmword ptr [r15], xmm0
0x18006005d  movups  [rbp+4Fh+var_58], xmm0
0x180060061  bt      ecx, 18h
0x180060065  jnb     loc_1800601D7
0x18006006b  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x180060072  lea     r9d, [rsi+4]; cbOutput
0x180060076  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x18006007a  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x18006007e  lea     rax, [rbp+4Fh+var_90]
0x180060082  lea     rdx, aObjectlength; "ObjectLength"
0x180060089  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18006008e  call    cs:__imp_BCryptGetProperty
0x180060094  cmp     [rbp+4Fh+var_90], 4
0x180060098  mov     ebx, eax
0x18006009a  jz      short loc_1800600A6
0x18006009c  mov     ebx, 0C00000E5h
0x1800600a1  jmp     loc_180060317
0x1800600a6  test    eax, eax
0x1800600a8  js      loc_180060317
0x1800600ae  mov     edx, dword ptr [rbp+4Fh+pbOutput]; uBytes
0x1800600b1  mov     ecx, 40h ; '@'; uFlags
0x1800600b6  call    cs:__imp_LocalAlloc
0x1800600bc  mov     r12, rax
0x1800600bf  test    rax, rax
0x1800600c2  jnz     short loc_1800600CE
0x1800600c4  mov     ebx, 0C000009Ah
0x1800600c9  jmp     loc_180060317
0x1800600ce  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x1800600d5  lea     rax, [rbp+4Fh+var_90]
0x1800600d9  mov     [rsp+0D0h+dwFlags], esi; dwFlags
0x1800600dd  lea     r8, [rbp+4Fh+var_8C]; pbOutput
0x1800600e1  mov     r9d, 4; cbOutput
0x1800600e7  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x1800600ec  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800600f3  call    cs:__imp_BCryptGetProperty
0x1800600f9  cmp     [rbp+4Fh+var_90], 4
0x1800600fd  mov     ebx, eax
0x1800600ff  jnz     short loc_18006009C
0x180060101  test    eax, eax
0x180060103  js      loc_180060317
0x180060109  mov     edx, dword ptr [rbp+4Fh+var_8C]; uBytes
0x18006010c  mov     ecx, 40h ; '@'; uFlags
0x180060111  call    cs:__imp_LocalAlloc
0x180060117  mov     rsi, rax
0x18006011a  test    rax, rax
0x18006011d  jz      short loc_1800600C4
0x18006011f  mov     r9d, dword ptr [rbp+4Fh+pbOutput]; cbHashObject
0x180060123  lea     rdx, [rbp+4Fh+phHash]; phHash
0x180060127  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hAlgorithm
0x18006012e  mov     r8, r12; pbHashObject
0x180060131  mov     [rsp+0D0h+var_A0], 0; dwFlags
0x180060139  mov     [rsp+0D0h+dwFlags], r14d; cbSecret
0x18006013e  mov     [rsp+0D0h+pcbResult], rdi; pbSecret
0x180060143  call    cs:__imp_BCryptCreateHash
0x180060149  mov     ebx, eax
0x18006014b  test    eax, eax
0x18006014d  js      loc_180060317
0x180060153  mov     rcx, [rbp+4Fh+phHash]; hHash
0x180060157  xor     r9d, r9d; dwFlags
0x18006015a  mov     rdx, r13; pbInput
0x18006015d  lea     edi, [r9+8]
0x180060161  mov     r8d, edi; cbInput
0x180060164  call    cs:__imp_BCryptHashData
0x18006016a  mov     ebx, eax
0x18006016c  test    eax, eax
0x18006016e  js      loc_180060317
0x180060174  mov     rdx, [rbp+4Fh+pbInput]; pbInput
0x180060178  xor     r9d, r9d; dwFlags
0x18006017b  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18006017f  mov     r8d, edi; cbInput
0x180060182  call    cs:__imp_BCryptHashData
0x180060188  mov     ebx, eax
0x18006018a  test    eax, eax
0x18006018c  js      loc_180060317
0x180060192  mov     r8d, dword ptr [rbp+4Fh+var_8C]; cbOutput
0x180060196  xor     r9d, r9d; dwFlags
0x180060199  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18006019d  mov     rdx, rsi; pbOutput
0x1800601a0  call    cs:__imp_BCryptFinishHash
0x1800601a6  mov     ebx, eax
0x1800601a8  test    eax, eax
0x1800601aa  js      loc_180060317
0x1800601b0  cmp     dword ptr [rbp+4Fh+var_8C], r14d
0x1800601b4  jnb     short loc_1800601CF
0x1800601b6  mov     r8d, 0C9h; unsigned int
0x1800601bc  lea     rdx, aOnecoreDsNetap_25; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800601c3  lea     rcx, aHashsizeSizeof; "HashSize >= sizeof(*SessionKey)"
0x1800601ca  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800601cf  movups  xmm0, xmmword ptr [rsi]
0x1800601d2  jmp     loc_1800602AA
0x1800601d7  bt      ecx, 0Eh
0x1800601db  jnb     loc_1800602B1
0x1800601e1  lea     rdx, [rbp+4Fh+var_80]
0x1800601e5  mov     ecx, 0FFFFFF77h
0x1800601ea  movups  [rbp+4Fh+var_48], xmm0
0x1800601ee  call    cs:__imp_CDLocateCheckSum
0x1800601f4  mov     ebx, eax
0x1800601f6  test    eax, eax
0x1800601f8  jns     short loc_180060213
0x1800601fa  lea     rdx, aNlmakesessionk_1; "NlMakeSessionKey: Failed to load checks"...
0x180060201  mov     r8d, eax
0x180060204  mov     ecx, 100h; unsigned int
0x180060209  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006020e  jmp     loc_180060317
0x180060213  mov     rax, [rbp+4Fh+var_80]
0x180060217  cmp     [rax+4], r14d
0x18006021b  jbe     short loc_18006023A
0x18006021d  mov     r8d, 0DFh; unsigned int
0x180060223  lea     rdx, aOnecoreDsNetap_25; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006022a  lea     rcx, aCheckChecksums; "Check->CheckSumSize <= sizeof(LocalChec"...
0x180060231  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180060236  mov     rax, [rbp+4Fh+var_80]
0x18006023a  mov     rax, [rax+30h]
0x18006023e  lea     r9, [rbp+4Fh+var_78]
0x180060242  xor     r8d, r8d
0x180060245  mov     edx, r14d
0x180060248  mov     rcx, rdi
0x18006024b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060250  mov     ebx, eax
0x180060252  test    eax, eax
0x180060254  jns     short loc_18006025F
0x180060256  lea     rdx, aNlmakesessionk_0; "NlMakeSessionKey: Failed to initialize "...
0x18006025d  jmp     short loc_180060201
0x18006025f  mov     rax, [rbp+4Fh+var_80]
0x180060263  mov     edi, 8
0x180060268  mov     rcx, [rbp+4Fh+var_78]
0x18006026c  mov     r8, r13
0x18006026f  mov     edx, edi
0x180060271  mov     rax, [rax+18h]
0x180060275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006027a  mov     rax, [rbp+4Fh+var_80]
0x18006027e  mov     edx, edi
0x180060280  mov     r8, [rbp+4Fh+pbInput]
0x180060284  mov     rcx, [rbp+4Fh+var_78]
0x180060288  mov     rax, [rax+18h]
0x18006028c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060291  mov     rax, [rbp+4Fh+var_80]
0x180060295  lea     rdx, [rbp+4Fh+var_48]
0x180060299  mov     rcx, [rbp+4Fh+var_78]
0x18006029d  mov     rax, [rax+20h]
0x1800602a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602a6  movups  xmm0, [rbp+4Fh+var_48]
0x1800602aa  movdqu  xmmword ptr [r15], xmm0
0x1800602af  jmp     short loc_180060317
0x1800602b1  mov     eax, [r9]
0x1800602b4  mov     rcx, r15
0x1800602b7  add     eax, [r8]
0x1800602ba  mov     [r15], eax
0x1800602bd  mov     eax, [r9+4]
0x1800602c1  add     eax, [r8+4]
0x1800602c5  lea     r8, [rbp+4Fh+var_58]
0x1800602c9  mov     [r15+4], eax
0x1800602cd  mov     eax, [rdx]
0x1800602cf  mov     [rbp+4Fh+var_60], eax
0x1800602d2  movzx   eax, word ptr [rdx+4]
0x1800602d6  mov     [rbp+4Fh+var_5C], ax
0x1800602da  mov     al, [rdx+6]
0x1800602dd  lea     rdx, [rbp+4Fh+var_60]
0x1800602e1  mov     [rbp+4Fh+var_5A], al
0x1800602e4  call    cs:__imp_SystemFunction001
0x1800602ea  mov     ebx, eax
0x1800602ec  test    eax, eax
0x1800602ee  js      short loc_180060317
0x1800602f0  mov     eax, [rdi+9]
0x1800602f3  lea     rdx, [rbp+4Fh+var_60]
0x1800602f7  mov     [rbp+4Fh+var_60], eax
0x1800602fa  lea     rcx, [rbp+4Fh+var_58]
0x1800602fe  movzx   eax, word ptr [rdi+0Dh]
0x180060302  mov     r8, r15
0x180060305  mov     [rbp+4Fh+var_5C], ax
0x180060309  mov     al, [rdi+0Fh]
0x18006030c  mov     [rbp+4Fh+var_5A], al
0x18006030f  call    cs:__imp_SystemFunction001
0x180060315  mov     ebx, eax
0x180060317  xor     r15d, r15d
0x18006031a  cmp     [rbp+4Fh+var_78], r15
0x18006031e  jz      short loc_18006034B
0x180060320  mov     rax, [rbp+4Fh+var_80]
0x180060324  lea     rcx, [rbp+4Fh+var_78]
0x180060328  mov     rax, [rax+28h]
0x18006032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060331  mov     ebx, eax
0x180060333  test    eax, eax
0x180060335  jns     short loc_18006034B
0x180060337  mov     r8d, eax
0x18006033a  lea     rdx, aNlmakesessionk; "NlMakeSessionKey: Failed to finish chec"...
0x180060341  mov     ecx, 100h; unsigned int
0x180060346  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006034b  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18006034f  test    rcx, rcx
0x180060352  jz      short loc_18006035A
0x180060354  call    cs:__imp_BCryptDestroyHash
0x18006035a  test    r12, r12
0x18006035d  jz      short loc_180060368
0x18006035f  mov     rcx, r12; hMem
0x180060362  call    cs:__imp_LocalFree
0x180060368  test    rsi, rsi
0x18006036b  jz      short loc_180060376
0x18006036d  mov     rcx, rsi; hMem
0x180060370  call    cs:__imp_LocalFree
0x180060376  lea     rax, [rbp+4Fh+var_58]
0x18006037a  mov     [rax], r15b
0x18006037d  inc     rax
0x180060380  sub     r14, 1
0x180060384  jnz     short loc_18006037A
0x180060386  lea     ecx, [r14+7]
0x18006038a  lea     rax, [rbp+4Fh+var_60]
0x18006038e  mov     [rax], r15b
0x180060391  inc     rax
0x180060394  sub     rcx, 1
0x180060398  jnz     short loc_18006038E
0x18006039a  mov     eax, ebx
0x18006039c  mov     rcx, [rbp+4Fh+var_38]
0x1800603a0  xor     rcx, rsp; StackCookie
0x1800603a3  call    __security_check_cookie
0x1800603a8  mov     rbx, [rsp+0D0h+arg_0]
0x1800603b0  add     rsp, 0A0h
0x1800603b7  pop     r15
0x1800603b9  pop     r14
0x1800603bb  pop     r13
0x1800603bd  pop     r12
0x1800603bf  pop     rdi
0x1800603c0  pop     rsi
0x1800603c1  pop     rbp
0x1800603c2  retn
```
