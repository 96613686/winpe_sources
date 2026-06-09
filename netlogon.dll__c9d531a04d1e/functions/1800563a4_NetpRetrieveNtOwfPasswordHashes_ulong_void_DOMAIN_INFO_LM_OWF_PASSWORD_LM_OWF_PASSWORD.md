# NetpRetrieveNtOwfPasswordHashes(ulong,void *,_DOMAIN_INFO *,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *)

- ea: `0x1800563a4`
- end: `0x18005663b`
- name: `?NetpRetrieveNtOwfPasswordHashes@@YAKKPEAXPEAU_DOMAIN_INFO@@PEAU_LM_OWF_PASSWORD@@2@Z`
- size: `663`
- prototype: `__int64 __fastcall(unsigned int, void *, struct _DOMAIN_INFO *, struct _LM_OWF_PASSWORD *, struct _LM_OWF_PASSWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005b270`
- `0x18005b500`

## callees

- `0x180007b50`
- `0x18000bd98`
- `0x18000d710`
- `0x1800354d8`
- `0x1800563a4`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800564ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800564ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800565f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800565f9`
- `ntdll!RtlLengthSid` at `0x1800563ef`
- `ntdll!RtlLengthSid` at `0x1800563ef`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180056617`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180056617`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005660d`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005660d`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x18005642e`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x18005642e`

## string_xrefs

- `0x1800565cc`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x180056598`: `NetpRetrieveNtOwfPasswordHashes: Can't NlGetIncomingPassword for %wZ 0x%lx.\n`

## pseudocode

```c
__int64 __fastcall NetpRetrieveNtOwfPasswordHashes(
        unsigned int a1,
        void *a2,
        struct _DOMAIN_INFO *a3,
        struct _LM_OWF_PASSWORD *a4,
        struct _LM_OWF_PASSWORD *a5)
{
  __int16 v8; // ax
  __int64 v9; // rcx
  int v10; // eax
  NTSTATUS v11; // ebx
  unsigned int v12; // ebx
  int v13; // eax
  _WORD *v14; // rax
  _WORD *v15; // r14
  unsigned __int64 v16; // r12
  unsigned int v17; // ecx
  __int64 v18; // r9
  int IncomingPassword; // eax
  char *v20; // r9
  NTSTATUS v21; // ebx
  __int64 v23; // [rsp+20h] [rbp-41h]
  __int64 v24; // [rsp+20h] [rbp-41h]
  _QWORD v25[2]; // [rsp+70h] [rbp+Fh] BYREF
  __int128 v26; // [rsp+80h] [rbp+1Fh] BYREF
  int v27; // [rsp+C8h] [rbp+67h] BYREF
  __int64 v28; // [rsp+D0h] [rbp+6Fh] BYREF

  v25[0] = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25[1] = a2;
  v8 = RtlLengthSid(a2);
  v9 = *((_QWORD *)a3 + 47);
  LOWORD(v25[0]) = v8;
  WORD1(v25[0]) = v8;
  v10 = SamIGetUserLogonInformationEx(v9, 136, v25, 1048577, &v28, &v26, 0);
  v11 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v23) = v10;
    NlPrintDomRoutine(
      0x100u,
      a3,
      L"NetpRetrieveNtOwfPasswordHashes: Account %ld: Cannot SamIGetUserLogonInfo 0x%lx\n",
      a1,
      v23);
    if ( v11 != -1073741275 && v11 != -1073741772 )
    {
      if ( v11 == -1073741702 )
        v11 = -1073741604;
      v12 = NetpNtStatusToApiStatus(v11);
      goto LABEL_25;
    }
LABEL_9:
    v12 = 1317;
    goto LABEL_25;
  }
  v13 = *(_DWORD *)(v28 + 280);
  if ( (v13 & 0x1C0) == 0 )
  {
    NlPrintDomRoutine(0x100u, a3, L"NetpRetrieveNtOwfPasswordHashes: Account %ld isn't a machine account\n", a1);
    goto LABEL_9;
  }
  if ( (v13 & 1) != 0 )
  {
    NlPrintDomRoutine(0x100u, a3, L"NetpRetrieveNtOwfPasswordHashes: Account %ld is disabled\n", a1);
    goto LABEL_9;
  }
  v14 = LocalAlloc(0, *(unsigned __int16 *)(v28 + 48) + 2LL);
  v15 = v14;
  if ( v14 )
  {
    memcpy_0(v14, *(const void **)(v28 + 56), *(unsigned __int16 *)(v28 + 48));
    v16 = (unsigned __int64)a5;
    v15[(unsigned __int64)*(unsigned __int16 *)(v28 + 48) >> 1] = 0;
    v17 = *(_DWORD *)(v28 + 280);
    v18 = v17;
    if ( (v17 & 0x40) != 0 )
      v18 = 64;
    if ( (v17 & 0x400) != 0 )
      v18 = 1024;
    IncomingPassword = NlGetIncomingPassword(
                         a3,
                         v15,
                         0,
                         v18,
                         1,
                         a4,
                         v16 & -(__int64)((*(_DWORD *)(v28 + 280) & 0x40) != 0),
                         &v27,
                         0,
                         0,
                         0,
                         0,
                         0);
    v21 = IncomingPassword;
    if ( IncomingPassword >= 0 )
    {
      v12 = 0;
      if ( a1 != v27 )
        NlAssertFailed("Rid == AccountRid", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx", 0x2A4Fu, v20);
      if ( (*(_BYTE *)(v28 + 280) & 0x40) == 0 )
        *(struct _LM_OWF_PASSWORD *)v16 = *a4;
    }
    else
    {
      LODWORD(v24) = IncomingPassword;
      NlPrintDomRoutine(
        0x100u,
        a3,
        L"NetpRetrieveNtOwfPasswordHashes: Can't NlGetIncomingPassword for %wZ 0x%lx.\n",
        v28 + 48,
        v24);
      v12 = NetpNtStatusToApiStatus(v21);
    }
    LocalFree(v15);
  }
  else
  {
    v12 = 8;
  }
LABEL_25:
  if ( v28 )
    SamIFree_SAMPR_USER_INFO_BUFFER(v28, 21);
  SamIFreeSidAndAttributesList(&v26);
  return v12;
}

```

## disassembly

```asm
0x1800563a4  mov     [rsp-8+arg_0], rbx
0x1800563a9  mov     [rsp-8+arg_18], rsi
0x1800563ae  push    rbp
0x1800563af  push    rdi
0x1800563b0  push    r12
0x1800563b2  push    r14
0x1800563b4  push    r15
0x1800563b6  lea     rbp, [rsp-2Fh]
0x1800563bb  sub     rsp, 90h
0x1800563c2  mov     esi, ecx
0x1800563c4  mov     [rbp+4Fh+var_40], 0
0x1800563cc  xorps   xmm0, xmm0
0x1800563cf  mov     [rbp+4Fh+arg_10], 0
0x1800563d7  mov     rcx, rdx; Sid
0x1800563da  mov     [rbp+4Fh+arg_8], 0
0x1800563e1  movups  [rbp+4Fh+var_30], xmm0
0x1800563e5  mov     r15, r9
0x1800563e8  mov     [rbp+4Fh+var_38], rdx
0x1800563ec  mov     rdi, r8
0x1800563ef  call    cs:__imp_RtlLengthSid
0x1800563f5  mov     rcx, [rdi+178h]
0x1800563fc  lea     r8, [rbp+4Fh+var_40]
0x180056400  mov     word ptr [rbp+4Fh+var_40], ax
0x180056404  mov     r9d, 100001h
0x18005640a  mov     word ptr [rbp+4Fh+var_40+2], ax
0x18005640e  mov     edx, 88h
0x180056413  lea     rax, [rbp+4Fh+var_30]
0x180056417  mov     [rsp+0B0h+var_80], 0
0x180056420  mov     [rsp+0B0h+var_88], rax
0x180056425  lea     rax, [rbp+4Fh+arg_10]
0x180056429  mov     [rsp+0B0h+var_90], rax
0x18005642e  call    cs:__imp_SamIGetUserLogonInformationEx
0x180056434  mov     ebx, eax
0x180056436  test    eax, eax
0x180056438  jns     short loc_180056481
0x18005643a  mov     r9d, esi
0x18005643d  mov     dword ptr [rsp+0B0h+var_90], eax
0x180056441  lea     r8, aNetpretrievent_0; "NetpRetrieveNtOwfPasswordHashes: Accoun"...
0x180056448  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005644b  mov     ecx, 100h; unsigned int
0x180056450  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056455  cmp     ebx, 0C0000225h
0x18005645b  jz      short loc_1800564A9
0x18005645d  cmp     ebx, 0C0000034h
0x180056463  jz      short loc_1800564A9
0x180056465  cmp     ebx, 0C000007Ah
0x18005646b  mov     eax, 0C00000DCh
0x180056470  cmovz   ebx, eax
0x180056473  mov     ecx, ebx; Status
0x180056475  call    NetpNtStatusToApiStatus
0x18005647a  mov     ebx, eax
0x18005647c  jmp     loc_1800565FF
0x180056481  mov     rcx, [rbp+4Fh+arg_10]
0x180056485  mov     eax, [rcx+118h]
0x18005648b  test    eax, 1C0h
0x180056490  jnz     short loc_1800564B3
0x180056492  lea     r8, aNetpretrievent_2; "NetpRetrieveNtOwfPasswordHashes: Accoun"...
0x180056499  mov     r9d, esi
0x18005649c  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005649f  mov     ecx, 100h; unsigned int
0x1800564a4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800564a9  mov     ebx, 525h
0x1800564ae  jmp     loc_1800565FF
0x1800564b3  test    al, 1
0x1800564b5  jz      short loc_1800564C0
0x1800564b7  lea     r8, aNetpretrievent; "NetpRetrieveNtOwfPasswordHashes: Accoun"...
0x1800564be  jmp     short loc_180056499
0x1800564c0  movzx   edx, word ptr [rcx+30h]
0x1800564c4  xor     ecx, ecx; uFlags
0x1800564c6  add     rdx, 2; uBytes
0x1800564ca  call    cs:__imp_LocalAlloc
0x1800564d0  mov     r14, rax
0x1800564d3  test    rax, rax
0x1800564d6  jnz     short loc_1800564E0
0x1800564d8  lea     ebx, [rax+8]
0x1800564db  jmp     loc_1800565FF
0x1800564e0  mov     rdx, [rbp+4Fh+arg_10]
0x1800564e4  mov     rcx, r14; void *
0x1800564e7  movzx   r8d, word ptr [rdx+30h]; Size
0x1800564ec  mov     rdx, [rdx+38h]; Src
0x1800564f0  call    memcpy_0
0x1800564f5  mov     rax, [rbp+4Fh+arg_10]
0x1800564f9  mov     edx, 40h ; '@'
0x1800564fe  mov     r12, [rbp+4Fh+arg_20]
0x180056502  mov     [rsp+0B0h+var_50], 0
0x18005650b  mov     [rsp+0B0h+var_58], 0
0x180056514  movzx   ecx, word ptr [rax+30h]
0x180056518  xor     eax, eax
0x18005651a  shr     rcx, 1
0x18005651d  mov     [rsp+0B0h+var_60], 0
0x180056526  mov     [rsp+0B0h+var_68], 0
0x18005652f  mov     [rsp+0B0h+var_70], 0
0x180056538  mov     [r14+rcx*2], ax
0x18005653d  mov     rax, [rbp+4Fh+arg_10]
0x180056541  mov     ecx, [rax+118h]
0x180056547  mov     eax, ecx
0x180056549  and     eax, edx
0x18005654b  mov     r9d, ecx
0x18005654e  cmovnz  r9d, edx
0x180056552  mov     edx, 400h
0x180056557  test    edx, ecx
0x180056559  lea     rcx, [rbp+4Fh+arg_8]
0x18005655d  mov     [rsp+0B0h+var_78], rcx
0x180056562  mov     rcx, rdi
0x180056565  cmovnz  r9d, edx
0x180056569  neg     eax
0x18005656b  mov     rdx, r14
0x18005656e  sbb     rax, rax
0x180056571  xor     r8d, r8d
0x180056574  and     rax, r12
0x180056577  mov     [rsp+0B0h+var_80], rax
0x18005657c  mov     [rsp+0B0h+var_88], r15
0x180056581  mov     dword ptr [rsp+0B0h+var_90], 1
0x180056589  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x18005658e  mov     ebx, eax
0x180056590  test    eax, eax
0x180056592  jns     short loc_1800565BF
0x180056594  mov     r9, [rbp+4Fh+arg_10]
0x180056598  lea     r8, aNetpretrievent_1; "NetpRetrieveNtOwfPasswordHashes: Can't "...
0x18005659f  add     r9, 30h ; '0'
0x1800565a3  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800565a7  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800565aa  mov     ecx, 100h; unsigned int
0x1800565af  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800565b4  mov     ecx, ebx; Status
0x1800565b6  call    NetpNtStatusToApiStatus
0x1800565bb  mov     ebx, eax
0x1800565bd  jmp     short loc_1800565F6
0x1800565bf  xor     ebx, ebx
0x1800565c1  cmp     esi, [rbp+4Fh+arg_8]
0x1800565c4  jz      short loc_1800565DF
0x1800565c6  mov     r8d, 2A4Fh; unsigned int
0x1800565cc  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800565d3  lea     rcx, aRidAccountrid; "Rid == AccountRid"
0x1800565da  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800565df  mov     rax, [rbp+4Fh+arg_10]
0x1800565e3  test    byte ptr [rax+118h], 40h
0x1800565ea  jnz     short loc_1800565F6
0x1800565ec  movups  xmm0, xmmword ptr [r15]
0x1800565f0  movdqu  xmmword ptr [r12], xmm0
0x1800565f6  mov     rcx, r14; hMem
0x1800565f9  call    cs:__imp_LocalFree
0x1800565ff  mov     rcx, [rbp+4Fh+arg_10]
0x180056603  test    rcx, rcx
0x180056606  jz      short loc_180056613
0x180056608  mov     edx, 15h
0x18005660d  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x180056613  lea     rcx, [rbp+4Fh+var_30]
0x180056617  call    cs:__imp_SamIFreeSidAndAttributesList
0x18005661d  lea     r11, [rsp+0B0h+var_20]
0x180056625  mov     eax, ebx
0x180056627  mov     rbx, [r11+30h]
0x18005662b  mov     rsi, [r11+48h]
0x18005662f  mov     rsp, r11
0x180056632  pop     r15
0x180056634  pop     r14
0x180056636  pop     r12
0x180056638  pop     rdi
0x180056639  pop     rbp
0x18005663a  retn
```
