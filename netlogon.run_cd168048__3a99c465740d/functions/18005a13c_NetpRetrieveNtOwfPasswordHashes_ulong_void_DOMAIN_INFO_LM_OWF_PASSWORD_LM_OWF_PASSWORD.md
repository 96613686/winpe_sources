# NetpRetrieveNtOwfPasswordHashes(ulong,void *,_DOMAIN_INFO *,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *)

- ea: `0x18005a13c`
- end: `0x18005a3f8`
- name: `?NetpRetrieveNtOwfPasswordHashes@@YAKKPEAXPEAU_DOMAIN_INFO@@PEAU_LM_OWF_PASSWORD@@2@Z`
- size: `700`
- prototype: `unsigned int(unsigned int, void *, struct _DOMAIN_INFO *, struct _LM_OWF_PASSWORD *, struct _LM_OWF_PASSWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005f4c0`
- `0x18005f750`

## callees

- `0x180007e90`
- `0x18000c440`
- `0x18000dd00`
- `0x1800374dc`
- `0x18005a13c`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005a26e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005a26e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a3a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a3a3`
- `ntdll!RtlLengthSid` at `0x18005a187`
- `ntdll!RtlLengthSid` at `0x18005a187`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18005a3cd`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18005a3cd`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005a3bd`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005a3bd`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x18005a1cc`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x18005a1cc`

## string_xrefs

- `0x18005a376`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005a342`: `NetpRetrieveNtOwfPasswordHashes: Can't NlGetIncomingPassword for %wZ 0x%lx.\n`

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
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  unsigned __int64 v16; // r12
  int v17; // ecx
  int v18; // r9d
  int IncomingPassword; // eax
  char *v20; // r9
  NTSTATUS v21; // ebx
  __int64 v23; // [rsp+20h] [rbp-41h]
  __int64 v24; // [rsp+20h] [rbp-41h]
  _QWORD v25[2]; // [rsp+70h] [rbp+Fh] BYREF
  __int128 v26; // [rsp+80h] [rbp+1Fh] BYREF
  unsigned int v27; // [rsp+C8h] [rbp+67h] BYREF
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
  v14 = (unsigned __int16 *)LocalAlloc(0, *(unsigned __int16 *)(v28 + 48) + 2LL);
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
                         (__int64)a3,
                         v15,
                         0,
                         v18,
                         1,
                         a4,
                         (char *)(v16 & -(__int64)((*(_DWORD *)(v28 + 280) & 0x40) != 0)),
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
        NlAssertFailed("Rid == AccountRid", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx", 0x2A51u, v20);
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
0x18005a13c  mov     [rsp-8+arg_0], rbx
0x18005a141  mov     [rsp-8+arg_18], rsi
0x18005a146  push    rbp
0x18005a147  push    rdi
0x18005a148  push    r12
0x18005a14a  push    r14
0x18005a14c  push    r15
0x18005a14e  lea     rbp, [rsp-2Fh]
0x18005a153  sub     rsp, 90h
0x18005a15a  mov     esi, ecx
0x18005a15c  mov     [rbp+4Fh+var_40], 0
0x18005a164  xorps   xmm0, xmm0
0x18005a167  mov     [rbp+4Fh+arg_10], 0
0x18005a16f  mov     rcx, rdx; Sid
0x18005a172  mov     [rbp+4Fh+arg_8], 0
0x18005a179  movups  [rbp+4Fh+var_30], xmm0
0x18005a17d  mov     r15, r9
0x18005a180  mov     [rbp+4Fh+var_38], rdx
0x18005a184  mov     rdi, r8
0x18005a187  call    cs:__imp_RtlLengthSid
0x18005a18e  nop     dword ptr [rax+rax+00h]
0x18005a193  mov     rcx, [rdi+178h]
0x18005a19a  lea     r8, [rbp+4Fh+var_40]
0x18005a19e  mov     word ptr [rbp+4Fh+var_40], ax
0x18005a1a2  mov     r9d, 100001h
0x18005a1a8  mov     word ptr [rbp+4Fh+var_40+2], ax
0x18005a1ac  mov     edx, 88h
0x18005a1b1  lea     rax, [rbp+4Fh+var_30]
0x18005a1b5  mov     [rsp+0B0h+var_80], 0
0x18005a1be  mov     [rsp+0B0h+var_88], rax
0x18005a1c3  lea     rax, [rbp+4Fh+arg_10]
0x18005a1c7  mov     [rsp+0B0h+var_90], rax
0x18005a1cc  call    cs:__imp_SamIGetUserLogonInformationEx
0x18005a1d3  nop     dword ptr [rax+rax+00h]
0x18005a1d8  mov     ebx, eax
0x18005a1da  test    eax, eax
0x18005a1dc  jns     short loc_18005A225
0x18005a1de  mov     r9d, esi
0x18005a1e1  mov     dword ptr [rsp+0B0h+var_90], eax
0x18005a1e5  lea     r8, aNetpretrievent_0; "NetpRetrieveNtOwfPasswordHashes: Accoun"...
0x18005a1ec  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a1ef  mov     ecx, 100h; unsigned int
0x18005a1f4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a1f9  cmp     ebx, 0C0000225h
0x18005a1ff  jz      short loc_18005A24D
0x18005a201  cmp     ebx, 0C0000034h
0x18005a207  jz      short loc_18005A24D
0x18005a209  cmp     ebx, 0C000007Ah
0x18005a20f  mov     eax, 0C00000DCh
0x18005a214  cmovz   ebx, eax
0x18005a217  mov     ecx, ebx; Status
0x18005a219  call    NetpNtStatusToApiStatus
0x18005a21e  mov     ebx, eax
0x18005a220  jmp     loc_18005A3AF
0x18005a225  mov     rcx, [rbp+4Fh+arg_10]
0x18005a229  mov     eax, [rcx+118h]
0x18005a22f  test    eax, 1C0h
0x18005a234  jnz     short loc_18005A257
0x18005a236  lea     r8, aNetpretrievent_2; "NetpRetrieveNtOwfPasswordHashes: Accoun"...
0x18005a23d  mov     r9d, esi
0x18005a240  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a243  mov     ecx, 100h; unsigned int
0x18005a248  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a24d  mov     ebx, 525h
0x18005a252  jmp     loc_18005A3AF
0x18005a257  test    al, 1
0x18005a259  jz      short loc_18005A264
0x18005a25b  lea     r8, aNetpretrievent; "NetpRetrieveNtOwfPasswordHashes: Accoun"...
0x18005a262  jmp     short loc_18005A23D
0x18005a264  movzx   edx, word ptr [rcx+30h]
0x18005a268  xor     ecx, ecx; uFlags
0x18005a26a  add     rdx, 2; uBytes
0x18005a26e  call    cs:__imp_LocalAlloc
0x18005a275  nop     dword ptr [rax+rax+00h]
0x18005a27a  mov     r14, rax
0x18005a27d  test    rax, rax
0x18005a280  jnz     short loc_18005A28A
0x18005a282  lea     ebx, [rax+8]
0x18005a285  jmp     loc_18005A3AF
0x18005a28a  mov     rdx, [rbp+4Fh+arg_10]
0x18005a28e  mov     rcx, r14; void *
0x18005a291  movzx   r8d, word ptr [rdx+30h]; Size
0x18005a296  mov     rdx, [rdx+38h]; Src
0x18005a29a  call    memcpy_0
0x18005a29f  mov     rax, [rbp+4Fh+arg_10]
0x18005a2a3  mov     edx, 40h ; '@'
0x18005a2a8  mov     r12, [rbp+4Fh+arg_20]
0x18005a2ac  mov     [rsp+0B0h+var_50], 0
0x18005a2b5  mov     [rsp+0B0h+var_58], 0
0x18005a2be  movzx   ecx, word ptr [rax+30h]
0x18005a2c2  xor     eax, eax
0x18005a2c4  shr     rcx, 1
0x18005a2c7  mov     [rsp+0B0h+var_60], 0
0x18005a2d0  mov     [rsp+0B0h+var_68], 0
0x18005a2d9  mov     [rsp+0B0h+var_70], 0
0x18005a2e2  mov     [r14+rcx*2], ax
0x18005a2e7  mov     rax, [rbp+4Fh+arg_10]
0x18005a2eb  mov     ecx, [rax+118h]
0x18005a2f1  mov     eax, ecx
0x18005a2f3  and     eax, edx
0x18005a2f5  mov     r9d, ecx
0x18005a2f8  cmovnz  r9d, edx
0x18005a2fc  mov     edx, 400h
0x18005a301  test    edx, ecx
0x18005a303  lea     rcx, [rbp+4Fh+arg_8]
0x18005a307  mov     [rsp+0B0h+var_78], rcx
0x18005a30c  mov     rcx, rdi
0x18005a30f  cmovnz  r9d, edx
0x18005a313  neg     eax
0x18005a315  mov     rdx, r14
0x18005a318  sbb     rax, rax
0x18005a31b  xor     r8d, r8d
0x18005a31e  and     rax, r12
0x18005a321  mov     [rsp+0B0h+var_80], rax
0x18005a326  mov     [rsp+0B0h+var_88], r15
0x18005a32b  mov     dword ptr [rsp+0B0h+var_90], 1
0x18005a333  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x18005a338  mov     ebx, eax
0x18005a33a  test    eax, eax
0x18005a33c  jns     short loc_18005A369
0x18005a33e  mov     r9, [rbp+4Fh+arg_10]
0x18005a342  lea     r8, aNetpretrievent_1; "NetpRetrieveNtOwfPasswordHashes: Can't "...
0x18005a349  add     r9, 30h ; '0'
0x18005a34d  mov     dword ptr [rsp+0B0h+var_90], eax
0x18005a351  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a354  mov     ecx, 100h; unsigned int
0x18005a359  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a35e  mov     ecx, ebx; Status
0x18005a360  call    NetpNtStatusToApiStatus
0x18005a365  mov     ebx, eax
0x18005a367  jmp     short loc_18005A3A0
0x18005a369  xor     ebx, ebx
0x18005a36b  cmp     esi, [rbp+4Fh+arg_8]
0x18005a36e  jz      short loc_18005A389
0x18005a370  mov     r8d, 2A51h; unsigned int
0x18005a376  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005a37d  lea     rcx, aRidAccountrid; "Rid == AccountRid"
0x18005a384  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005a389  mov     rax, [rbp+4Fh+arg_10]
0x18005a38d  test    byte ptr [rax+118h], 40h
0x18005a394  jnz     short loc_18005A3A0
0x18005a396  movups  xmm0, xmmword ptr [r15]
0x18005a39a  movdqu  xmmword ptr [r12], xmm0
0x18005a3a0  mov     rcx, r14; hMem
0x18005a3a3  call    cs:__imp_LocalFree
0x18005a3aa  nop     dword ptr [rax+rax+00h]
0x18005a3af  mov     rcx, [rbp+4Fh+arg_10]
0x18005a3b3  test    rcx, rcx
0x18005a3b6  jz      short loc_18005A3C9
0x18005a3b8  mov     edx, 15h
0x18005a3bd  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x18005a3c4  nop     dword ptr [rax+rax+00h]
0x18005a3c9  lea     rcx, [rbp+4Fh+var_30]
0x18005a3cd  call    cs:__imp_SamIFreeSidAndAttributesList
0x18005a3d4  nop     dword ptr [rax+rax+00h]
0x18005a3d9  lea     r11, [rsp+0B0h+var_20]
0x18005a3e1  mov     eax, ebx
0x18005a3e3  mov     rbx, [r11+30h]
0x18005a3e7  mov     rsi, [r11+48h]
0x18005a3eb  mov     rsp, r11
0x18005a3ee  pop     r15
0x18005a3f0  pop     r14
0x18005a3f2  pop     r12
0x18005a3f4  pop     rdi
0x18005a3f5  pop     rbp
0x18005a3f6  retn
```
