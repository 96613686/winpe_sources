# NlUpdateTrustList(_NL_INIT_TRUSTLIST_CONTEXT *,_DOMAIN_INFO *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,uchar,ulong,ulong,ulong,_GUID *,ulong *,_CLIENT_SESSION * *)

- ea: `0x18006f6b0`
- end: `0x18006fd41`
- name: `?NlUpdateTrustList@@YAJPEAU_NL_INIT_TRUSTLIST_CONTEXT@@PEAU_DOMAIN_INFO@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@EKKKPEAU_GUID@@PEAKPEAPEAU_CLIENT_SESSION@@@Z`
- size: `1681`
- prototype: `int(struct _NL_INIT_TRUSTLIST_CONTEXT *, struct _DOMAIN_INFO *, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *, unsigned __int8, unsigned int, unsigned int, unsigned int, struct _GUID *, unsigned int *, struct _CLIENT_SESSION **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18006834c`
- `0x18006a67c`

## callees

- `0x18000c440`
- `0x18000de8c`
- `0x18000e0e0`
- `0x18000e910`
- `0x18000ed00`
- `0x180040f18`
- `0x180041f80`
- `0x18006891c`
- `0x18006c784`
- `0x18006f12c`
- `0x18006f6b0`
- `0x180089328`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f8bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f8bd`
- `ntdll!RtlEqualDomainName` at `0x18006fa64`
- `ntdll!RtlEqualDomainName` at `0x18006fa64`
- `ntdll!RtlEqualSid` at `0x18006f952`
- `ntdll!RtlEqualSid` at `0x18006fa36`
- `ntdll!RtlEqualSid` at `0x18006f952`
- `ntdll!RtlEqualSid` at `0x18006fa36`
- `ntdll!RtlLengthSid` at `0x18006f902`
- `ntdll!RtlLengthSid` at `0x18006f9cf`
- `ntdll!RtlLengthSid` at `0x18006f902`
- `ntdll!RtlLengthSid` at `0x18006f9cf`

## string_xrefs

- `0x18006f788`: `NlUpdateTrustList: %wZ: trust is not outbound (ignored)\n`
- `0x18006f7ab`: `NlUpdateTrustList: %wZ: trust has no SID (ignored)\n`
- `0x18006f7e4`: `NlUpdateTrustList: %wZ: trust type is neither NT4 nor NT 5 (%ld) (ignored)\n`
- `0x18006f80f`: `NlUpdateTrustList: %wZ: trust is KERB only (ignored)\n`
- `0x18006f84e`: `NlUpdateTrustList: %wZ: Netbios domain name is too long.\n`
- `0x18006f87c`: `NlUpdateTrustList: %wZ: DNS domain name is too long (ignored)\n`
- `0x18006fafb`: `NlUpdateTrustList: All parameters are NULL (ignored)\n`
- `0x18006fb29`: `NlUpdateTrustList: Similar trusts have different netbios names: %wZ %wZ\n`
- `0x18006fac4`: `NlUpdateTrustList: Similar trusts have different DNS names: %wZ %wZ\n`
- `0x18006fc41`: `NlUpdateTrustList: Added to local trust list\n`
- `0x18006fb72`: `NlUpdateTrustList: Deleted from local trust list\n`
- `0x18006fcad`: `NlUpdateTrustList: Already in trust list\n`

## pseudocode

```c
__int64 __fastcall NlUpdateTrustList(
        struct _NL_INIT_TRUSTLIST_CONTEXT *a1,
        struct _DOMAIN_INFO *a2,
        struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        struct _GUID *a8,
        unsigned int *a9,
        struct _CLIENT_SESSION **a10)
{
  struct _CLIENT_SESSION **v10; // r15
  struct _DOMAIN_INFO *v11; // r14
  unsigned __int64 v12; // r13
  char v13; // dl
  struct _UNICODE_STRING *v14; // rsi
  char v15; // r8
  struct _UNICODE_STRING *v16; // rdi
  void *v17; // r12
  int v18; // eax
  char v19; // al
  __m128i v20; // xmm6
  unsigned __int64 v21; // rbx
  unsigned __int16 *v22; // rax
  ULONG v23; // eax
  __int64 Length; // rbx
  unsigned __int64 v25; // rbx
  ULONG v26; // eax
  __int64 ClientSession; // rbx
  char *v28; // r15
  __int64 v29; // rsi
  BOOL v30; // r14d
  void *v31; // rcx
  unsigned int v32; // esi
  unsigned int updated; // edi
  __int64 *v34; // rax
  unsigned __int16 *v35; // r8
  struct _CLIENT_SESSION *v36; // rdx
  __int64 v37; // rax
  char v39; // [rsp+48h] [rbp-99h]
  unsigned int v41; // [rsp+4Ch] [rbp-95h]
  int v42; // [rsp+50h] [rbp-91h]
  struct _UNICODE_STRING *v43; // [rsp+60h] [rbp-81h]
  void *v44; // [rsp+68h] [rbp-79h]
  unsigned __int16 *v48[3]; // [rsp+90h] [rbp-51h] BYREF
  _WORD v49[16]; // [rsp+A8h] [rbp-39h] BYREF

  v10 = a10;
  v11 = a2;
  v12 = (unsigned __int64)a3;
  v13 = 0;
  v14 = 0;
  v15 = a5;
  v39 = 0;
  v41 = a5;
  v43 = 0;
  if ( a10 )
    *a10 = 0;
  v42 = 4;
  v16 = (struct _UNICODE_STRING *)((v12 + 16) & -(__int64)(*(_WORD *)(v12 + 16) != 0));
  if ( *(_DWORD *)(v12 + 44) == 2 )
  {
    v15 = a5 | 4;
    v41 = a5 | 4;
    v14 = (struct _UNICODE_STRING *)(v12 & -(__int64)(*(_WORD *)v12 != 0));
    v43 = v14;
  }
  v17 = *(void **)(v12 + 32);
  v44 = v17;
  if ( (v15 & 0x10) != 0 )
  {
    if ( (*(_BYTE *)(v12 + 40) & 2) == 0 )
    {
      NlPrintDomRoutine(2u, v11, L"NlUpdateTrustList: %wZ: trust is not outbound (ignored)\n", v16);
      v13 = 1;
      v39 = 1;
    }
    if ( !v17 )
    {
      NlPrintDomRoutine(0x100u, v11, L"NlUpdateTrustList: %wZ: trust has no SID (ignored)\n", v16);
      v13 = 1;
      v39 = 1;
    }
  }
  v18 = *(_DWORD *)(v12 + 44);
  if ( v18 != 1 )
  {
    if ( v18 == 2 )
    {
      v42 = 3;
    }
    else
    {
      v42 = 0;
      NlPrintDomRoutine(
        0x100u,
        v11,
        L"NlUpdateTrustList: %wZ: trust type is neither NT4 nor NT 5 (%ld) (ignored)\n",
        v16,
        *(_DWORD *)(v12 + 44));
      v13 = 1;
      v39 = 1;
    }
  }
  if ( (*(_BYTE *)(v12 + 48) & 2) != 0 )
  {
    NlPrintDomRoutine(2u, v11, L"NlUpdateTrustList: %wZ: trust is KERB only (ignored)\n", v16);
LABEL_16:
    v39 = 1;
    goto LABEL_31;
  }
  if ( !v13 )
  {
    v19 = 0;
    v20 = 0;
    if ( v16 && v16->Length > 0x1Eu )
    {
      NlPrintDomRoutine(0x100u, v11, L"NlUpdateTrustList: %wZ: Netbios domain name is too long.\n", v16);
      v20 = *(__m128i *)v16;
      v19 = 1;
    }
    if ( v14 && v14->Length > 0x1FEu )
    {
      NlPrintDomRoutine(0x100u, v11, L"NlUpdateTrustList: %wZ: DNS domain name is too long (ignored)\n", v14);
      v20 = *(__m128i *)v14;
      v19 = 1;
    }
    if ( !v19 )
      goto LABEL_31;
    v48[0] = (unsigned __int16 *)((char *)v11 + 72);
    *(_OWORD *)&v48[1] = 0;
    v21 = (unsigned __int16)_mm_cvtsi128_si32(v20);
    v22 = (unsigned __int16 *)LocalAlloc(0, v21 + 2);
    v48[1] = v22;
    if ( v22 )
    {
      memcpy_0(v22, (const void *)_mm_srli_si128(v20, 8).m128i_i64[0], (unsigned int)v21);
      v48[1][v21 >> 1] = 0;
    }
    v23 = 0;
    v48[2] = 0;
    if ( v17 )
      v23 = RtlLengthSid(v17);
    NlpWriteEventlog(0x158Du, 1u, 0, v48, 2u, (unsigned __int8 *)v17, v23);
    goto LABEL_16;
  }
  v39 = v13;
LABEL_31:
  if ( v17 && RtlEqualSid(v17, *((PSID *)v11 + 23)) )
  {
    memset(v48, 0, sizeof(v48));
    if ( v16 && (Length = v16->Length, (unsigned __int64)(Length + 2) <= 0x20) )
    {
      memcpy_0(v49, v16->Buffer, v16->Length);
      v25 = Length & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v25 >= 0x20 )
        _report_rangecheckfailure();
      *(_WORD *)((char *)v49 + v25) = 0;
    }
    else
    {
      v49[0] = 0;
    }
    v48[2] = 0;
    v48[0] = (unsigned __int16 *)((char *)v11 + 72);
    v48[1] = v49;
    v26 = RtlLengthSid(v17);
    NlpWriteEventlog(0x158Cu, 1u, 0, v48, 2u, (unsigned __int8 *)v17, v26);
    ClientSession = 0;
  }
  else
  {
    ClientSession = 0;
    if ( !v17 && !v16 && !v14 )
    {
      NlPrintDomRoutine(0x100u, v11, L"NlUpdateTrustList: All parameters are NULL (ignored)\n");
      v32 = v41;
      goto LABEL_68;
    }
  }
  v28 = (char *)v11 + 448;
  v29 = *((_QWORD *)v11 + 56);
  if ( (struct _DOMAIN_INFO *)v29 == (struct _DOMAIN_INFO *)((char *)v11 + 448) )
    goto LABEL_63;
  do
  {
    v30 = 0;
    if ( v17 )
    {
      v31 = *(void **)(v29 + 264);
      if ( v31 )
        v30 = RtlEqualSid(v31, v17) != 0;
    }
    if ( v16 && *(_WORD *)(v29 + 112) )
    {
      if ( RtlEqualDomainName(v16, (PUNICODE_STRING)(v29 + 112)) )
      {
        v30 = 1;
      }
      else if ( v30 )
      {
        NlPrintCsRoutine(
          0x100u,
          (struct _CLIENT_SESSION *)v29,
          L"NlUpdateTrustList: Similar trusts have different netbios names: %wZ %wZ\n",
          v16,
          v29 + 112);
        goto LABEL_61;
      }
    }
    ClientSession = v29;
    if ( v43 && *(_WORD *)(v29 + 152) )
    {
      if ( (unsigned int)NlEqualDnsNameU(v43, (struct _UNICODE_STRING *)(v29 + 152)) )
        break;
      if ( v30 )
        NlPrintCsRoutine(
          0x100u,
          (struct _CLIENT_SESSION *)v29,
          L"NlUpdateTrustList: Similar trusts have different DNS names: %wZ %wZ\n",
          v43,
          v29 + 152);
    }
    else if ( v30 )
    {
      break;
    }
    v17 = v44;
LABEL_61:
    v29 = *(_QWORD *)v29;
    ClientSession = 0;
  }
  while ( (char *)v29 != v28 );
  v12 = (unsigned __int64)a3;
  v11 = a2;
  v17 = v44;
LABEL_63:
  if ( v39 )
  {
    if ( ClientSession )
    {
      NlPrintCsRoutine(
        0x200u,
        (struct _CLIENT_SESSION *)ClientSession,
        L"NlUpdateTrustList: Deleted from local trust list\n");
      NlFreeClientSession((struct _CLIENT_SESSION *)ClientSession);
      ClientSession = 0;
    }
    v32 = v41;
LABEL_67:
    v10 = a10;
  }
  else
  {
    if ( ClientSession )
    {
      v32 = v41;
      if ( !(unsigned int)NlSetNamesClientSession((struct _CLIENT_SESSION *)ClientSession, v16, v43, v17, 0) )
        goto LABEL_67;
      *(_DWORD *)(ClientSession + 292) &= ~0x800u;
      v36 = (struct _CLIENT_SESSION *)ClientSession;
      *(_DWORD *)(ClientSession + 292) |= v41;
      if ( a4 )
        *(_DWORD *)(ClientSession + 296) = *(_DWORD *)(v12 + 48);
      v35 = L"NlUpdateTrustList: Already in trust list\n";
    }
    else
    {
      v32 = v41;
      ClientSession = NlAllocateClientSession(v11, v16, v43, v17, 0, v41 | 0x8000, v42, *(_DWORD *)(v12 + 48));
      if ( !ClientSession )
        goto LABEL_67;
      v34 = (__int64 *)*((_QWORD *)v28 + 1);
      if ( (char *)*v34 != v28 )
        __fastfail(3u);
      *(_QWORD *)ClientSession = v28;
      v35 = L"NlUpdateTrustList: Added to local trust list\n";
      *(_QWORD *)(ClientSession + 8) = v34;
      v36 = (struct _CLIENT_SESSION *)ClientSession;
      *v34 = ClientSession;
      *((_QWORD *)v28 + 1) = ClientSession;
      ++*((_DWORD *)v11 + 116);
    }
    ++*(_DWORD *)(ClientSession + 328);
    NlPrintCsRoutine(0x200u, v36, v35);
    if ( (*(_BYTE *)(ClientSession + 292) & 0x10) != 0 && !*(_QWORD *)(ClientSession + 304) )
    {
      ++*(_DWORD *)(ClientSession + 328);
      *(_QWORD *)(ClientSession + 304) = ClientSession;
    }
    v10 = a10;
    if ( *(_DWORD *)(v12 + 44) == 2 )
      v37 = ClientSession + 152;
    else
      v37 = ClientSession + 112;
    *(_QWORD *)(ClientSession + 192) = v37;
  }
LABEL_68:
  updated = NlUpdateForestTrustList(
              a1,
              (struct _CLIENT_SESSION *)ClientSession,
              (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)v12,
              v32,
              a7,
              a6,
              a8,
              a9);
  if ( ClientSession )
  {
    if ( v10 )
      *v10 = (struct _CLIENT_SESSION *)ClientSession;
    else
      NlUnrefClientSession((HLOCAL)ClientSession);
  }
  return updated;
}

```

## disassembly

```asm
0x18006f6b0  mov     rax, rsp
0x18006f6b3  mov     [rax+20h], rbx
0x18006f6b7  push    rbp
0x18006f6b8  push    rsi
0x18006f6b9  push    rdi
0x18006f6ba  push    r12
0x18006f6bc  push    r13
0x18006f6be  push    r14
0x18006f6c0  push    r15
0x18006f6c2  lea     rbp, [rax-3Fh]
0x18006f6c6  sub     rsp, 0E0h
0x18006f6cd  movaps  xmmword ptr [rax-48h], xmm6
0x18006f6d1  mov     rax, cs:__security_cookie
0x18006f6d8  xor     rax, rsp
0x18006f6db  mov     [rbp+37h+var_50], rax
0x18006f6df  mov     r15, [rbp+37h+arg_48]
0x18006f6e6  mov     r14, rdx
0x18006f6e9  mov     rax, [rbp+37h+arg_40]
0x18006f6f0  mov     r13, r8
0x18006f6f3  mov     byte ptr [rsp+110h+var_D0+1], r9b
0x18006f6f8  xor     r9d, r9d
0x18006f6fb  mov     [rbp+37h+var_A0], rdx
0x18006f6ff  mov     dl, r9b
0x18006f702  mov     [rbp+37h+var_A8], r8
0x18006f706  mov     esi, r9d
0x18006f709  mov     r8d, [rbp+37h+arg_20]
0x18006f70d  mov     byte ptr [rsp+110h+var_D0], dl
0x18006f711  mov     [rbp+37h+var_90], rcx
0x18006f715  mov     [rsp+110h+var_CC], r8d
0x18006f71a  mov     [rbp+37h+var_98], rax
0x18006f71e  mov     [rsp+110h+var_C0], r15
0x18006f723  mov     [rsp+110h+var_B8], r9
0x18006f728  test    r15, r15
0x18006f72b  jz      short loc_18006F730
0x18006f72d  mov     [r15], r9
0x18006f730  lea     rcx, [r13+10h]
0x18006f734  mov     ebx, 4
0x18006f739  movzx   eax, word ptr [rcx]
0x18006f73c  neg     ax
0x18006f73f  mov     dword ptr [rsp+110h+var_C8], ebx
0x18006f743  sbb     rdi, rdi
0x18006f746  and     rdi, rcx
0x18006f749  cmp     dword ptr [r13+2Ch], 2
0x18006f74e  jnz     short loc_18006F76B
0x18006f750  movzx   eax, word ptr [r13+0]
0x18006f755  or      r8d, ebx
0x18006f758  neg     ax
0x18006f75b  mov     [rsp+110h+var_CC], r8d
0x18006f760  sbb     rsi, rsi
0x18006f763  and     rsi, r13
0x18006f766  mov     [rsp+110h+var_B8], rsi
0x18006f76b  mov     r12, [r13+20h]
0x18006f76f  mov     ebx, 1
0x18006f774  mov     [rbp+37h+var_B0], r12
0x18006f778  test    r8b, 10h
0x18006f77c  jz      short loc_18006F7C8
0x18006f77e  test    byte ptr [r13+28h], 2
0x18006f783  jnz     short loc_18006F7A3
0x18006f785  mov     r9, rdi
0x18006f788  lea     r8, aNlupdatetrustl_5; "NlUpdateTrustList: %wZ: trust is not ou"...
0x18006f78f  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006f792  lea     ecx, [rbx+1]; unsigned int
0x18006f795  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006f79a  mov     dl, bl
0x18006f79c  mov     byte ptr [rsp+110h+var_D0], bl
0x18006f7a0  xor     r9d, r9d
0x18006f7a3  test    r12, r12
0x18006f7a6  jnz     short loc_18006F7C8
0x18006f7a8  mov     r9, rdi
0x18006f7ab  lea     r8, aNlupdatetrustl_6; "NlUpdateTrustList: %wZ: trust has no SI"...
0x18006f7b2  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006f7b5  mov     ecx, 100h; unsigned int
0x18006f7ba  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006f7bf  mov     dl, bl
0x18006f7c1  mov     byte ptr [rsp+110h+var_D0], bl
0x18006f7c5  xor     r9d, r9d
0x18006f7c8  mov     eax, [r13+2Ch]
0x18006f7cc  cmp     eax, ebx
0x18006f7ce  jz      short loc_18006F805
0x18006f7d0  cmp     eax, 2
0x18006f7d3  jnz     short loc_18006F7DF
0x18006f7d5  mov     dword ptr [rsp+110h+var_C8], 3
0x18006f7dd  jmp     short loc_18006F805
0x18006f7df  mov     dword ptr [rsp+110h+var_C8], r9d
0x18006f7e4  lea     r8, aNlupdatetrustl_8; "NlUpdateTrustList: %wZ: trust type is n"...
0x18006f7eb  mov     r9, rdi
0x18006f7ee  mov     dword ptr [rsp+110h+var_F0], eax
0x18006f7f2  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006f7f5  mov     ecx, 100h; unsigned int
0x18006f7fa  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006f7ff  mov     dl, bl
0x18006f801  mov     byte ptr [rsp+110h+var_D0], bl
0x18006f805  test    byte ptr [r13+30h], 2
0x18006f80a  jz      short loc_18006F82F
0x18006f80c  mov     r9, rdi
0x18006f80f  lea     r8, aNlupdatetrustl; "NlUpdateTrustList: %wZ: trust is KERB o"...
0x18006f816  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006f819  mov     ecx, 2; unsigned int
0x18006f81e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006f823  mov     byte ptr [rsp+110h+var_D0], bl
0x18006f827  xor     r8d, r8d
0x18006f82a  jmp     loc_18006F93F
0x18006f82f  xor     r8d, r8d
0x18006f832  test    dl, dl
0x18006f834  jnz     loc_18006F93B
0x18006f83a  mov     al, r8b
0x18006f83d  xorps   xmm6, xmm6
0x18006f840  test    rdi, rdi
0x18006f843  jz      short loc_18006F86A
0x18006f845  cmp     word ptr [rdi], 1Eh
0x18006f849  jbe     short loc_18006F86A
0x18006f84b  mov     r9, rdi
0x18006f84e  lea     r8, aNlupdatetrustl_4; "NlUpdateTrustList: %wZ: Netbios domain "...
0x18006f855  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006f858  mov     ecx, 100h; unsigned int
0x18006f85d  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006f862  movups  xmm6, xmmword ptr [rdi]
0x18006f865  mov     al, bl
0x18006f867  xor     r8d, r8d
0x18006f86a  test    rsi, rsi
0x18006f86d  jz      short loc_18006F898
0x18006f86f  mov     ecx, 1FEh
0x18006f874  cmp     [rsi], cx
0x18006f877  jbe     short loc_18006F898
0x18006f879  mov     r9, rsi
0x18006f87c  lea     r8, aNlupdatetrustl_2; "NlUpdateTrustList: %wZ: DNS domain name"...
0x18006f883  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006f886  mov     ecx, 100h; unsigned int
0x18006f88b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006f890  movups  xmm6, xmmword ptr [rsi]
0x18006f893  mov     al, bl
0x18006f895  xor     r8d, r8d
0x18006f898  test    al, al
0x18006f89a  jz      loc_18006F93F
0x18006f8a0  lea     rax, [r14+48h]
0x18006f8a4  xorps   xmm0, xmm0
0x18006f8a7  mov     [rbp+37h+var_88], rax
0x18006f8ab  xor     ecx, ecx; uFlags
0x18006f8ad  movd    eax, xmm6
0x18006f8b1  movdqu  xmmword ptr [rbp+37h+var_88+8], xmm0
0x18006f8b6  movzx   ebx, ax
0x18006f8b9  lea     rdx, [rbx+2]; uBytes
0x18006f8bd  call    cs:__imp_LocalAlloc
0x18006f8c4  nop     dword ptr [rax+rax+00h]
0x18006f8c9  mov     [rbp+37h+var_88+8], rax
0x18006f8cd  test    rax, rax
0x18006f8d0  jz      short loc_18006F8F4
0x18006f8d2  psrldq  xmm6, 8
0x18006f8d7  mov     r8d, ebx; Size
0x18006f8da  movq    rdx, xmm6; Src
0x18006f8df  mov     rcx, rax; void *
0x18006f8e2  call    memcpy_0
0x18006f8e7  mov     rax, [rbp+37h+var_88+8]
0x18006f8eb  shr     rbx, 1
0x18006f8ee  xor     ecx, ecx
0x18006f8f0  mov     [rax+rbx*2], cx
0x18006f8f4  xor     eax, eax
0x18006f8f6  mov     [rbp+37h+var_78], rax
0x18006f8fa  test    r12, r12
0x18006f8fd  jz      short loc_18006F90E
0x18006f8ff  mov     rcx, r12; Sid
0x18006f902  call    cs:__imp_RtlLengthSid
0x18006f909  nop     dword ptr [rax+rax+00h]
0x18006f90e  mov     dword ptr [rsp+110h+var_E0], eax; unsigned int
0x18006f912  lea     r9, [rbp+37h+var_88]; unsigned __int16 **
0x18006f916  xor     r8d, r8d; unsigned int
0x18006f919  mov     [rsp+110h+var_E8], r12; unsigned __int8 *
0x18006f91e  mov     ecx, 158Dh; unsigned int
0x18006f923  mov     dword ptr [rsp+110h+var_F0], 2; unsigned int
0x18006f92b  lea     ebx, [r8+1]
0x18006f92f  mov     edx, ebx; unsigned int
0x18006f931  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006f936  jmp     loc_18006F823
0x18006f93b  mov     byte ptr [rsp+110h+var_D0], dl
0x18006f93f  test    r12, r12
0x18006f942  jz      loc_18006FADD
0x18006f948  mov     rdx, [r14+0B8h]; Sid2
0x18006f94f  mov     rcx, r12; Sid1
0x18006f952  call    cs:__imp_RtlEqualSid
0x18006f959  nop     dword ptr [rax+rax+00h]
0x18006f95e  xor     r8d, r8d
0x18006f961  test    al, al
0x18006f963  jz      loc_18006FADD
0x18006f969  xor     eax, eax
0x18006f96b  xorps   xmm0, xmm0
0x18006f96e  mov     [rbp+37h+var_78], rax
0x18006f972  movups  xmmword ptr [rbp+37h+var_88], xmm0
0x18006f976  test    rdi, rdi
0x18006f979  jz      short loc_18006F9B3
0x18006f97b  movzx   ebx, word ptr [rdi]
0x18006f97e  lea     rax, [rbx+2]
0x18006f982  cmp     rax, 20h ; ' '
0x18006f986  ja      short loc_18006F9B3
0x18006f988  mov     rdx, [rdi+8]; Src
0x18006f98c  lea     rcx, [rbp+37h+var_70]; void *
0x18006f990  mov     r8d, ebx; Size
0x18006f993  call    memcpy_0
0x18006f998  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006f99c  cmp     rbx, 20h ; ' '
0x18006f9a0  jnb     short loc_18006F9AD
0x18006f9a2  xor     r8d, r8d
0x18006f9a5  mov     [rbp+rbx+37h+var_70], r8w
0x18006f9ab  jmp     short loc_18006F9B8
0x18006f9ad  call    __report_rangecheckfailure
0x18006f9b3  mov     [rbp+37h+var_70], r8w
0x18006f9b8  lea     rax, [r14+48h]
0x18006f9bc  mov     [rbp+37h+var_78], r8
0x18006f9c0  mov     [rbp+37h+var_88], rax
0x18006f9c4  mov     rcx, r12; Sid
0x18006f9c7  lea     rax, [rbp+37h+var_70]
0x18006f9cb  mov     [rbp+37h+var_88+8], rax
0x18006f9cf  call    cs:__imp_RtlLengthSid
0x18006f9d6  nop     dword ptr [rax+rax+00h]
0x18006f9db  mov     dword ptr [rsp+110h+var_E0], eax; unsigned int
0x18006f9df  xor     r8d, r8d; unsigned int
0x18006f9e2  mov     [rsp+110h+var_E8], r12; unsigned __int8 *
0x18006f9e7  lea     r9, [rbp+37h+var_88]; unsigned __int16 **
0x18006f9eb  mov     ecx, 158Ch; unsigned int
0x18006f9f0  mov     dword ptr [rsp+110h+var_F0], 2; unsigned int
0x18006f9f8  lea     edx, [r8+1]; unsigned int
0x18006f9fc  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006fa01  xor     r8d, r8d
0x18006fa04  mov     ebx, r8d
0x18006fa07  lea     r15, [r14+1C0h]
0x18006fa0e  mov     rsi, [r15]
0x18006fa11  cmp     rsi, r15
0x18006fa14  jz      loc_18006FB66
0x18006fa1a  mov     r13, [rsp+110h+var_B8]
0x18006fa1f  mov     r14d, r8d
0x18006fa22  test    r12, r12
0x18006fa25  jz      short loc_18006FA4F
0x18006fa27  mov     rcx, [rsi+108h]; Sid1
0x18006fa2e  test    rcx, rcx
0x18006fa31  jz      short loc_18006FA4F
0x18006fa33  mov     rdx, r12; Sid2
0x18006fa36  call    cs:__imp_RtlEqualSid
0x18006fa3d  nop     dword ptr [rax+rax+00h]
0x18006fa42  xor     r8d, r8d
0x18006fa45  test    al, al
0x18006fa47  lea     eax, [r8+1]
0x18006fa4b  cmovnz  r14d, eax
0x18006fa4f  test    rdi, rdi
0x18006fa52  jz      short loc_18006FA7F
0x18006fa54  lea     rbx, [rsi+70h]
0x18006fa58  cmp     [rbx], r8w
0x18006fa5c  jz      short loc_18006FA7F
0x18006fa5e  mov     rdx, rbx; DomainName2
0x18006fa61  mov     rcx, rdi; DomainName1
0x18006fa64  call    cs:__imp_RtlEqualDomainName
0x18006fa6b  nop     dword ptr [rax+rax+00h]
0x18006fa70  xor     r8d, r8d
0x18006fa73  test    al, al
0x18006fa75  jz      loc_18006FB18
0x18006fa7b  lea     r14d, [r8+1]
0x18006fa7f  mov     rbx, rsi
0x18006fa82  test    r13, r13
0x18006fa85  jz      loc_18006FB42
0x18006fa8b  lea     r12, [rsi+98h]
0x18006fa92  cmp     [r12], r8w
0x18006fa97  jz      loc_18006FB42
0x18006fa9d  mov     rdx, r12; struct _UNICODE_STRING *
0x18006faa0  mov     rcx, r13; struct _UNICODE_STRING *
0x18006faa3  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006faa8  xor     r8d, r8d
0x18006faab  test    eax, eax
0x18006faad  jnz     loc_18006FB5A
0x18006fab3  test    r14d, r14d
0x18006fab6  jz      loc_18006FB47
0x18006fabc  mov     r9, r13
0x18006fabf  mov     [rsp+110h+var_F0], r12
0x18006fac4  lea     r8, aNlupdatetrustl_7; "NlUpdateTrustList: Similar trusts have "...
0x18006facb  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006face  mov     ecx, 100h; unsigned int
0x18006fad3  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006fad8  xor     r8d, r8d
0x18006fadb  jmp     short loc_18006FB47
0x18006fadd  mov     rbx, r8
0x18006fae0  test    r12, r12
0x18006fae3  jnz     loc_18006FA07
0x18006fae9  test    rdi, rdi
0x18006faec  jnz     loc_18006FA07
0x18006faf2  test    rsi, rsi
0x18006faf5  jnz     loc_18006FA07
0x18006fafb  lea     r8, aNlupdatetrustl_1; "NlUpdateTrustList: All parameters are N"...
0x18006fb02  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006fb05  mov     ecx, 100h; unsigned int
0x18006fb0a  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006fb0f  mov     esi, [rsp+110h+var_CC]
0x18006fb13  jmp     loc_18006FB99
0x18006fb18  test    r14d, r14d
0x18006fb1b  jz      loc_18006FA7F
0x18006fb21  mov     r9, rdi
0x18006fb24  mov     [rsp+110h+var_F0], rbx
0x18006fb29  lea     r8, aNlupdatetrustl_9; "NlUpdateTrustList: Similar trusts have "...
0x18006fb30  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006fb33  mov     ecx, 100h; unsigned int
0x18006fb38  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006fb3d  xor     r8d, r8d
0x18006fb40  jmp     short loc_18006FB4B
0x18006fb42  test    r14d, r14d
  ... truncated ...
```
