# NlUpdateTrustList(_NL_INIT_TRUSTLIST_CONTEXT *,_DOMAIN_INFO *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,uchar,ulong,ulong,ulong,_GUID *,ulong *,_CLIENT_SESSION * *)

- ea: `0x18006a694`
- end: `0x18006ad00`
- name: `?NlUpdateTrustList@@YAJPEAU_NL_INIT_TRUSTLIST_CONTEXT@@PEAU_DOMAIN_INFO@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@EKKKPEAU_GUID@@PEAKPEAPEAU_CLIENT_SESSION@@@Z`
- size: `1644`
- prototype: `int(struct _NL_INIT_TRUSTLIST_CONTEXT *, struct _DOMAIN_INFO *, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *, unsigned __int8, unsigned int, unsigned int, unsigned int, struct _GUID *, unsigned int *, struct _CLIENT_SESSION **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800639e0`
- `0x180065aa8`

## callees

- `0x18000bd98`
- `0x18000d874`
- `0x18000da94`
- `0x18000e270`
- `0x18000e660`
- `0x18003e71c`
- `0x18003f648`
- `0x180063f6c`
- `0x1800679fc`
- `0x18006a148`
- `0x18006a694`
- `0x180083180`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006a8a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006a8a1`
- `ntdll!RtlEqualDomainName` at `0x18006aa2a`
- `ntdll!RtlEqualDomainName` at `0x18006aa2a`
- `ntdll!RtlEqualSid` at `0x18006a92a`
- `ntdll!RtlEqualSid` at `0x18006aa02`
- `ntdll!RtlEqualSid` at `0x18006a92a`
- `ntdll!RtlEqualSid` at `0x18006aa02`
- `ntdll!RtlLengthSid` at `0x18006a8e0`
- `ntdll!RtlLengthSid` at `0x18006a9a1`
- `ntdll!RtlLengthSid` at `0x18006a8e0`
- `ntdll!RtlLengthSid` at `0x18006a9a1`

## string_xrefs

- `0x18006a76c`: `NlUpdateTrustList: %wZ: trust is not outbound (ignored)\n`
- `0x18006a78f`: `NlUpdateTrustList: %wZ: trust has no SID (ignored)\n`
- `0x18006a7c8`: `NlUpdateTrustList: %wZ: trust type is neither NT4 nor NT 5 (%ld) (ignored)\n`
- `0x18006a7f3`: `NlUpdateTrustList: %wZ: trust is KERB only (ignored)\n`
- `0x18006a832`: `NlUpdateTrustList: %wZ: Netbios domain name is too long.\n`
- `0x18006a860`: `NlUpdateTrustList: %wZ: DNS domain name is too long (ignored)\n`
- `0x18006aabb`: `NlUpdateTrustList: All parameters are NULL (ignored)\n`
- `0x18006aae9`: `NlUpdateTrustList: Similar trusts have different netbios names: %wZ %wZ\n`
- `0x18006aa84`: `NlUpdateTrustList: Similar trusts have different DNS names: %wZ %wZ\n`
- `0x18006ac01`: `NlUpdateTrustList: Added to local trust list\n`
- `0x18006ab32`: `NlUpdateTrustList: Deleted from local trust list\n`
- `0x18006ac6d`: `NlUpdateTrustList: Already in trust list\n`

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
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 v27; // rbx
  ULONG v28; // eax
  struct _CLIENT_SESSION *ClientSession; // rbx
  char *v30; // r15
  char *v31; // rsi
  BOOL v32; // r14d
  void *v33; // rcx
  unsigned int v34; // esi
  unsigned int updated; // edi
  struct _CLIENT_SESSION **v36; // rax
  unsigned __int16 *v37; // r8
  struct _CLIENT_SESSION *v38; // rdx
  char *v39; // rax
  char v41; // [rsp+48h] [rbp-99h]
  unsigned int v43; // [rsp+4Ch] [rbp-95h]
  int v44; // [rsp+50h] [rbp-91h]
  struct _UNICODE_STRING *v45; // [rsp+60h] [rbp-81h]
  void *v46; // [rsp+68h] [rbp-79h]
  unsigned __int16 *v50[3]; // [rsp+90h] [rbp-51h] BYREF
  _WORD v51[16]; // [rsp+A8h] [rbp-39h] BYREF

  v10 = a10;
  v11 = a2;
  v12 = (unsigned __int64)a3;
  v13 = 0;
  v14 = 0;
  v15 = a5;
  v41 = 0;
  v43 = a5;
  v45 = 0;
  if ( a10 )
    *a10 = 0;
  v44 = 4;
  v16 = (struct _UNICODE_STRING *)((v12 + 16) & -(__int64)(*(_WORD *)(v12 + 16) != 0));
  if ( *(_DWORD *)(v12 + 44) == 2 )
  {
    v15 = a5 | 4;
    v43 = a5 | 4;
    v14 = (struct _UNICODE_STRING *)(v12 & -(__int64)(*(_WORD *)v12 != 0));
    v45 = v14;
  }
  v17 = *(void **)(v12 + 32);
  v46 = v17;
  if ( (v15 & 0x10) != 0 )
  {
    if ( (*(_BYTE *)(v12 + 40) & 2) == 0 )
    {
      NlPrintDomRoutine(2u, v11, L"NlUpdateTrustList: %wZ: trust is not outbound (ignored)\n", v16);
      v13 = 1;
      v41 = 1;
    }
    if ( !v17 )
    {
      NlPrintDomRoutine(0x100u, v11, L"NlUpdateTrustList: %wZ: trust has no SID (ignored)\n", v16);
      v13 = 1;
      v41 = 1;
    }
  }
  v18 = *(_DWORD *)(v12 + 44);
  if ( v18 != 1 )
  {
    if ( v18 == 2 )
    {
      v44 = 3;
    }
    else
    {
      v44 = 0;
      NlPrintDomRoutine(
        0x100u,
        v11,
        L"NlUpdateTrustList: %wZ: trust type is neither NT4 nor NT 5 (%ld) (ignored)\n",
        v16,
        *(_DWORD *)(v12 + 44));
      v13 = 1;
      v41 = 1;
    }
  }
  if ( (*(_BYTE *)(v12 + 48) & 2) != 0 )
  {
    NlPrintDomRoutine(2u, v11, L"NlUpdateTrustList: %wZ: trust is KERB only (ignored)\n", v16);
LABEL_16:
    v41 = 1;
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
    v50[0] = (unsigned __int16 *)((char *)v11 + 72);
    *(_OWORD *)&v50[1] = 0;
    v21 = (unsigned __int16)_mm_cvtsi128_si32(v20);
    v22 = (unsigned __int16 *)LocalAlloc(0, v21 + 2);
    v50[1] = v22;
    if ( v22 )
    {
      memcpy_0(v22, (const void *)_mm_srli_si128(v20, 8).m128i_i64[0], (unsigned int)v21);
      v50[1][v21 >> 1] = 0;
    }
    v23 = 0;
    v50[2] = 0;
    if ( v17 )
      v23 = RtlLengthSid(v17);
    NlpWriteEventlog(0x158Du, 1u, 0, v50, 2u, (unsigned __int8 *)v17, v23);
    goto LABEL_16;
  }
  v41 = v13;
LABEL_31:
  if ( v17 && RtlEqualSid(v17, *((PSID *)v11 + 23)) )
  {
    memset(v50, 0, sizeof(v50));
    if ( v16 && (Length = v16->Length, (unsigned __int64)(Length + 2) <= 0x20) )
    {
      memcpy_0(v51, v16->Buffer, v16->Length);
      v27 = Length & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v27 >= 0x20 )
        _report_rangecheckfailure(v26, v25);
      *(_WORD *)((char *)v51 + v27) = 0;
    }
    else
    {
      v51[0] = 0;
    }
    v50[2] = 0;
    v50[0] = (unsigned __int16 *)((char *)v11 + 72);
    v50[1] = v51;
    v28 = RtlLengthSid(v17);
    NlpWriteEventlog(0x158Cu, 1u, 0, v50, 2u, (unsigned __int8 *)v17, v28);
    ClientSession = 0;
  }
  else
  {
    ClientSession = 0;
    if ( !v17 && !v16 && !v14 )
    {
      NlPrintDomRoutine(0x100u, v11, L"NlUpdateTrustList: All parameters are NULL (ignored)\n");
      v34 = v43;
      goto LABEL_68;
    }
  }
  v30 = (char *)v11 + 448;
  v31 = (char *)*((_QWORD *)v11 + 56);
  if ( v31 == (char *)v11 + 448 )
    goto LABEL_63;
  do
  {
    v32 = 0;
    if ( v17 )
    {
      v33 = (void *)*((_QWORD *)v31 + 33);
      if ( v33 )
        v32 = RtlEqualSid(v33, v17) != 0;
    }
    if ( v16 && *((_WORD *)v31 + 56) )
    {
      if ( RtlEqualDomainName(v16, (PUNICODE_STRING)v31 + 7) )
      {
        v32 = 1;
      }
      else if ( v32 )
      {
        NlPrintCsRoutine(
          0x100u,
          (struct _CLIENT_SESSION *)v31,
          L"NlUpdateTrustList: Similar trusts have different netbios names: %wZ %wZ\n",
          v16,
          v31 + 112);
        goto LABEL_61;
      }
    }
    ClientSession = (struct _CLIENT_SESSION *)v31;
    if ( v45 && *((_WORD *)v31 + 76) )
    {
      if ( (unsigned int)NlEqualDnsNameU(v45, (struct _UNICODE_STRING *)(v31 + 152)) )
        break;
      if ( v32 )
        NlPrintCsRoutine(
          0x100u,
          (struct _CLIENT_SESSION *)v31,
          L"NlUpdateTrustList: Similar trusts have different DNS names: %wZ %wZ\n",
          v45,
          v31 + 152);
    }
    else if ( v32 )
    {
      break;
    }
    v17 = v46;
LABEL_61:
    v31 = *(char **)v31;
    ClientSession = 0;
  }
  while ( v31 != v30 );
  v12 = (unsigned __int64)a3;
  v11 = a2;
  v17 = v46;
LABEL_63:
  if ( v41 )
  {
    if ( ClientSession )
    {
      NlPrintCsRoutine(0x200u, ClientSession, L"NlUpdateTrustList: Deleted from local trust list\n");
      NlFreeClientSession(ClientSession);
      ClientSession = 0;
    }
    v34 = v43;
LABEL_67:
    v10 = a10;
  }
  else
  {
    if ( ClientSession )
    {
      v34 = v43;
      if ( !(unsigned int)NlSetNamesClientSession(ClientSession, v16, v45, v17, 0) )
        goto LABEL_67;
      *((_DWORD *)ClientSession + 73) &= ~0x800u;
      v38 = ClientSession;
      *((_DWORD *)ClientSession + 73) |= v43;
      if ( a4 )
        *((_DWORD *)ClientSession + 74) = *(_DWORD *)(v12 + 48);
      v37 = L"NlUpdateTrustList: Already in trust list\n";
    }
    else
    {
      v34 = v43;
      ClientSession = (struct _CLIENT_SESSION *)NlAllocateClientSession(
                                                  v11,
                                                  v16,
                                                  v45,
                                                  v17,
                                                  0,
                                                  v43 | 0x8000,
                                                  v44,
                                                  *(_DWORD *)(v12 + 48));
      if ( !ClientSession )
        goto LABEL_67;
      v36 = (struct _CLIENT_SESSION **)*((_QWORD *)v30 + 1);
      if ( *v36 != (struct _CLIENT_SESSION *)v30 )
        __fastfail(3u);
      *(_QWORD *)ClientSession = v30;
      v37 = L"NlUpdateTrustList: Added to local trust list\n";
      *((_QWORD *)ClientSession + 1) = v36;
      v38 = ClientSession;
      *v36 = ClientSession;
      *((_QWORD *)v30 + 1) = ClientSession;
      ++*((_DWORD *)v11 + 116);
    }
    ++*((_DWORD *)ClientSession + 82);
    NlPrintCsRoutine(0x200u, v38, v37);
    if ( (*((_BYTE *)ClientSession + 292) & 0x10) != 0 && !*((_QWORD *)ClientSession + 38) )
    {
      ++*((_DWORD *)ClientSession + 82);
      *((_QWORD *)ClientSession + 38) = ClientSession;
    }
    v10 = a10;
    if ( *(_DWORD *)(v12 + 44) == 2 )
      v39 = (char *)ClientSession + 152;
    else
      v39 = (char *)ClientSession + 112;
    *((_QWORD *)ClientSession + 24) = v39;
  }
LABEL_68:
  updated = NlUpdateForestTrustList(
              a1,
              ClientSession,
              (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)v12,
              v34,
              a7,
              a6,
              a8,
              a9);
  if ( ClientSession )
  {
    if ( v10 )
      *v10 = ClientSession;
    else
      NlUnrefClientSession(ClientSession);
  }
  return updated;
}

```

## disassembly

```asm
0x18006a694  mov     rax, rsp
0x18006a697  mov     [rax+20h], rbx
0x18006a69b  push    rbp
0x18006a69c  push    rsi
0x18006a69d  push    rdi
0x18006a69e  push    r12
0x18006a6a0  push    r13
0x18006a6a2  push    r14
0x18006a6a4  push    r15
0x18006a6a6  lea     rbp, [rax-3Fh]
0x18006a6aa  sub     rsp, 0E0h
0x18006a6b1  movaps  xmmword ptr [rax-48h], xmm6
0x18006a6b5  mov     rax, cs:__security_cookie
0x18006a6bc  xor     rax, rsp
0x18006a6bf  mov     [rbp+37h+var_50], rax
0x18006a6c3  mov     r15, [rbp+37h+arg_48]
0x18006a6ca  mov     r14, rdx
0x18006a6cd  mov     rax, [rbp+37h+arg_40]
0x18006a6d4  mov     r13, r8
0x18006a6d7  mov     byte ptr [rsp+110h+var_D0+1], r9b
0x18006a6dc  xor     r9d, r9d
0x18006a6df  mov     [rbp+37h+var_A0], rdx
0x18006a6e3  mov     dl, r9b
0x18006a6e6  mov     [rbp+37h+var_A8], r8
0x18006a6ea  mov     esi, r9d
0x18006a6ed  mov     r8d, [rbp+37h+arg_20]
0x18006a6f1  mov     byte ptr [rsp+110h+var_D0], dl
0x18006a6f5  mov     [rbp+37h+var_90], rcx
0x18006a6f9  mov     [rsp+110h+var_CC], r8d
0x18006a6fe  mov     [rbp+37h+var_98], rax
0x18006a702  mov     [rsp+110h+var_C0], r15
0x18006a707  mov     [rsp+110h+var_B8], r9
0x18006a70c  test    r15, r15
0x18006a70f  jz      short loc_18006A714
0x18006a711  mov     [r15], r9
0x18006a714  lea     rcx, [r13+10h]
0x18006a718  mov     ebx, 4
0x18006a71d  movzx   eax, word ptr [rcx]
0x18006a720  neg     ax
0x18006a723  mov     dword ptr [rsp+110h+var_C8], ebx
0x18006a727  sbb     rdi, rdi
0x18006a72a  and     rdi, rcx
0x18006a72d  cmp     dword ptr [r13+2Ch], 2
0x18006a732  jnz     short loc_18006A74F
0x18006a734  movzx   eax, word ptr [r13+0]
0x18006a739  or      r8d, ebx
0x18006a73c  neg     ax
0x18006a73f  mov     [rsp+110h+var_CC], r8d
0x18006a744  sbb     rsi, rsi
0x18006a747  and     rsi, r13
0x18006a74a  mov     [rsp+110h+var_B8], rsi
0x18006a74f  mov     r12, [r13+20h]
0x18006a753  mov     ebx, 1
0x18006a758  mov     [rbp+37h+var_B0], r12
0x18006a75c  test    r8b, 10h
0x18006a760  jz      short loc_18006A7AC
0x18006a762  test    byte ptr [r13+28h], 2
0x18006a767  jnz     short loc_18006A787
0x18006a769  mov     r9, rdi
0x18006a76c  lea     r8, aNlupdatetrustl_5; "NlUpdateTrustList: %wZ: trust is not ou"...
0x18006a773  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006a776  lea     ecx, [rbx+1]; unsigned int
0x18006a779  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006a77e  mov     dl, bl
0x18006a780  mov     byte ptr [rsp+110h+var_D0], bl
0x18006a784  xor     r9d, r9d
0x18006a787  test    r12, r12
0x18006a78a  jnz     short loc_18006A7AC
0x18006a78c  mov     r9, rdi
0x18006a78f  lea     r8, aNlupdatetrustl_6; "NlUpdateTrustList: %wZ: trust has no SI"...
0x18006a796  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006a799  mov     ecx, 100h; unsigned int
0x18006a79e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006a7a3  mov     dl, bl
0x18006a7a5  mov     byte ptr [rsp+110h+var_D0], bl
0x18006a7a9  xor     r9d, r9d
0x18006a7ac  mov     eax, [r13+2Ch]
0x18006a7b0  cmp     eax, ebx
0x18006a7b2  jz      short loc_18006A7E9
0x18006a7b4  cmp     eax, 2
0x18006a7b7  jnz     short loc_18006A7C3
0x18006a7b9  mov     dword ptr [rsp+110h+var_C8], 3
0x18006a7c1  jmp     short loc_18006A7E9
0x18006a7c3  mov     dword ptr [rsp+110h+var_C8], r9d
0x18006a7c8  lea     r8, aNlupdatetrustl_8; "NlUpdateTrustList: %wZ: trust type is n"...
0x18006a7cf  mov     r9, rdi
0x18006a7d2  mov     dword ptr [rsp+110h+var_F0], eax
0x18006a7d6  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006a7d9  mov     ecx, 100h; unsigned int
0x18006a7de  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006a7e3  mov     dl, bl
0x18006a7e5  mov     byte ptr [rsp+110h+var_D0], bl
0x18006a7e9  test    byte ptr [r13+30h], 2
0x18006a7ee  jz      short loc_18006A813
0x18006a7f0  mov     r9, rdi
0x18006a7f3  lea     r8, aNlupdatetrustl; "NlUpdateTrustList: %wZ: trust is KERB o"...
0x18006a7fa  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006a7fd  mov     ecx, 2; unsigned int
0x18006a802  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006a807  mov     byte ptr [rsp+110h+var_D0], bl
0x18006a80b  xor     r8d, r8d
0x18006a80e  jmp     loc_18006A917
0x18006a813  xor     r8d, r8d
0x18006a816  test    dl, dl
0x18006a818  jnz     loc_18006A913
0x18006a81e  mov     al, r8b
0x18006a821  xorps   xmm6, xmm6
0x18006a824  test    rdi, rdi
0x18006a827  jz      short loc_18006A84E
0x18006a829  cmp     word ptr [rdi], 1Eh
0x18006a82d  jbe     short loc_18006A84E
0x18006a82f  mov     r9, rdi
0x18006a832  lea     r8, aNlupdatetrustl_4; "NlUpdateTrustList: %wZ: Netbios domain "...
0x18006a839  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006a83c  mov     ecx, 100h; unsigned int
0x18006a841  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006a846  movups  xmm6, xmmword ptr [rdi]
0x18006a849  mov     al, bl
0x18006a84b  xor     r8d, r8d
0x18006a84e  test    rsi, rsi
0x18006a851  jz      short loc_18006A87C
0x18006a853  mov     ecx, 1FEh
0x18006a858  cmp     [rsi], cx
0x18006a85b  jbe     short loc_18006A87C
0x18006a85d  mov     r9, rsi
0x18006a860  lea     r8, aNlupdatetrustl_2; "NlUpdateTrustList: %wZ: DNS domain name"...
0x18006a867  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006a86a  mov     ecx, 100h; unsigned int
0x18006a86f  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006a874  movups  xmm6, xmmword ptr [rsi]
0x18006a877  mov     al, bl
0x18006a879  xor     r8d, r8d
0x18006a87c  test    al, al
0x18006a87e  jz      loc_18006A917
0x18006a884  lea     rax, [r14+48h]
0x18006a888  xorps   xmm0, xmm0
0x18006a88b  mov     [rbp+37h+var_88], rax
0x18006a88f  xor     ecx, ecx; uFlags
0x18006a891  movd    eax, xmm6
0x18006a895  movdqu  xmmword ptr [rbp+37h+var_88+8], xmm0
0x18006a89a  movzx   ebx, ax
0x18006a89d  lea     rdx, [rbx+2]; uBytes
0x18006a8a1  call    cs:__imp_LocalAlloc
0x18006a8a7  mov     [rbp+37h+var_88+8], rax
0x18006a8ab  test    rax, rax
0x18006a8ae  jz      short loc_18006A8D2
0x18006a8b0  psrldq  xmm6, 8
0x18006a8b5  mov     r8d, ebx; Size
0x18006a8b8  movq    rdx, xmm6; Src
0x18006a8bd  mov     rcx, rax; void *
0x18006a8c0  call    memcpy_0
0x18006a8c5  mov     rax, [rbp+37h+var_88+8]
0x18006a8c9  shr     rbx, 1
0x18006a8cc  xor     ecx, ecx
0x18006a8ce  mov     [rax+rbx*2], cx
0x18006a8d2  xor     eax, eax
0x18006a8d4  mov     [rbp+37h+var_78], rax
0x18006a8d8  test    r12, r12
0x18006a8db  jz      short loc_18006A8E6
0x18006a8dd  mov     rcx, r12; Sid
0x18006a8e0  call    cs:__imp_RtlLengthSid
0x18006a8e6  mov     dword ptr [rsp+110h+var_E0], eax; unsigned int
0x18006a8ea  lea     r9, [rbp+37h+var_88]; unsigned __int16 **
0x18006a8ee  xor     r8d, r8d; unsigned int
0x18006a8f1  mov     [rsp+110h+var_E8], r12; unsigned __int8 *
0x18006a8f6  mov     ecx, 158Dh; unsigned int
0x18006a8fb  mov     dword ptr [rsp+110h+var_F0], 2; unsigned int
0x18006a903  lea     ebx, [r8+1]
0x18006a907  mov     edx, ebx; unsigned int
0x18006a909  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006a90e  jmp     loc_18006A807
0x18006a913  mov     byte ptr [rsp+110h+var_D0], dl
0x18006a917  test    r12, r12
0x18006a91a  jz      loc_18006AA9D
0x18006a920  mov     rdx, [r14+0B8h]; Sid2
0x18006a927  mov     rcx, r12; Sid1
0x18006a92a  call    cs:__imp_RtlEqualSid
0x18006a930  xor     r8d, r8d
0x18006a933  test    al, al
0x18006a935  jz      loc_18006AA9D
0x18006a93b  xor     eax, eax
0x18006a93d  xorps   xmm0, xmm0
0x18006a940  mov     [rbp+37h+var_78], rax
0x18006a944  movups  xmmword ptr [rbp+37h+var_88], xmm0
0x18006a948  test    rdi, rdi
0x18006a94b  jz      short loc_18006A985
0x18006a94d  movzx   ebx, word ptr [rdi]
0x18006a950  lea     rax, [rbx+2]
0x18006a954  cmp     rax, 20h ; ' '
0x18006a958  ja      short loc_18006A985
0x18006a95a  mov     rdx, [rdi+8]; Src
0x18006a95e  lea     rcx, [rbp+37h+var_70]; void *
0x18006a962  mov     r8d, ebx; Size
0x18006a965  call    memcpy_0
0x18006a96a  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006a96e  cmp     rbx, 20h ; ' '
0x18006a972  jnb     short loc_18006A97F
0x18006a974  xor     r8d, r8d
0x18006a977  mov     [rbp+rbx+37h+var_70], r8w
0x18006a97d  jmp     short loc_18006A98A
0x18006a97f  call    __report_rangecheckfailure
0x18006a985  mov     [rbp+37h+var_70], r8w
0x18006a98a  lea     rax, [r14+48h]
0x18006a98e  mov     [rbp+37h+var_78], r8
0x18006a992  mov     [rbp+37h+var_88], rax
0x18006a996  mov     rcx, r12; Sid
0x18006a999  lea     rax, [rbp+37h+var_70]
0x18006a99d  mov     [rbp+37h+var_88+8], rax
0x18006a9a1  call    cs:__imp_RtlLengthSid
0x18006a9a7  mov     dword ptr [rsp+110h+var_E0], eax; unsigned int
0x18006a9ab  xor     r8d, r8d; unsigned int
0x18006a9ae  mov     [rsp+110h+var_E8], r12; unsigned __int8 *
0x18006a9b3  lea     r9, [rbp+37h+var_88]; unsigned __int16 **
0x18006a9b7  mov     ecx, 158Ch; unsigned int
0x18006a9bc  mov     dword ptr [rsp+110h+var_F0], 2; unsigned int
0x18006a9c4  lea     edx, [r8+1]; unsigned int
0x18006a9c8  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006a9cd  xor     r8d, r8d
0x18006a9d0  mov     ebx, r8d
0x18006a9d3  lea     r15, [r14+1C0h]
0x18006a9da  mov     rsi, [r15]
0x18006a9dd  cmp     rsi, r15
0x18006a9e0  jz      loc_18006AB26
0x18006a9e6  mov     r13, [rsp+110h+var_B8]
0x18006a9eb  mov     r14d, r8d
0x18006a9ee  test    r12, r12
0x18006a9f1  jz      short loc_18006AA15
0x18006a9f3  mov     rcx, [rsi+108h]; Sid1
0x18006a9fa  test    rcx, rcx
0x18006a9fd  jz      short loc_18006AA15
0x18006a9ff  mov     rdx, r12; Sid2
0x18006aa02  call    cs:__imp_RtlEqualSid
0x18006aa08  xor     r8d, r8d
0x18006aa0b  test    al, al
0x18006aa0d  lea     eax, [r8+1]
0x18006aa11  cmovnz  r14d, eax
0x18006aa15  test    rdi, rdi
0x18006aa18  jz      short loc_18006AA3F
0x18006aa1a  lea     rbx, [rsi+70h]
0x18006aa1e  cmp     [rbx], r8w
0x18006aa22  jz      short loc_18006AA3F
0x18006aa24  mov     rdx, rbx; DomainName2
0x18006aa27  mov     rcx, rdi; DomainName1
0x18006aa2a  call    cs:__imp_RtlEqualDomainName
0x18006aa30  xor     r8d, r8d
0x18006aa33  test    al, al
0x18006aa35  jz      loc_18006AAD8
0x18006aa3b  lea     r14d, [r8+1]
0x18006aa3f  mov     rbx, rsi
0x18006aa42  test    r13, r13
0x18006aa45  jz      loc_18006AB02
0x18006aa4b  lea     r12, [rsi+98h]
0x18006aa52  cmp     [r12], r8w
0x18006aa57  jz      loc_18006AB02
0x18006aa5d  mov     rdx, r12; struct _UNICODE_STRING *
0x18006aa60  mov     rcx, r13; struct _UNICODE_STRING *
0x18006aa63  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006aa68  xor     r8d, r8d
0x18006aa6b  test    eax, eax
0x18006aa6d  jnz     loc_18006AB1A
0x18006aa73  test    r14d, r14d
0x18006aa76  jz      loc_18006AB07
0x18006aa7c  mov     r9, r13
0x18006aa7f  mov     [rsp+110h+var_F0], r12
0x18006aa84  lea     r8, aNlupdatetrustl_7; "NlUpdateTrustList: Similar trusts have "...
0x18006aa8b  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006aa8e  mov     ecx, 100h; unsigned int
0x18006aa93  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006aa98  xor     r8d, r8d
0x18006aa9b  jmp     short loc_18006AB07
0x18006aa9d  mov     rbx, r8
0x18006aaa0  test    r12, r12
0x18006aaa3  jnz     loc_18006A9D3
0x18006aaa9  test    rdi, rdi
0x18006aaac  jnz     loc_18006A9D3
0x18006aab2  test    rsi, rsi
0x18006aab5  jnz     loc_18006A9D3
0x18006aabb  lea     r8, aNlupdatetrustl_1; "NlUpdateTrustList: All parameters are N"...
0x18006aac2  mov     rdx, r14; struct _DOMAIN_INFO *
0x18006aac5  mov     ecx, 100h; unsigned int
0x18006aaca  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006aacf  mov     esi, [rsp+110h+var_CC]
0x18006aad3  jmp     loc_18006AB59
0x18006aad8  test    r14d, r14d
0x18006aadb  jz      loc_18006AA3F
0x18006aae1  mov     r9, rdi
0x18006aae4  mov     [rsp+110h+var_F0], rbx
0x18006aae9  lea     r8, aNlupdatetrustl_9; "NlUpdateTrustList: Similar trusts have "...
0x18006aaf0  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006aaf3  mov     ecx, 100h; unsigned int
0x18006aaf8  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006aafd  xor     r8d, r8d
0x18006ab00  jmp     short loc_18006AB0B
0x18006ab02  test    r14d, r14d
0x18006ab05  jnz     short loc_18006AB1A
0x18006ab07  mov     r12, [rbp+37h+var_B0]
0x18006ab0b  mov     rsi, [rsi]
0x18006ab0e  mov     rbx, r8
0x18006ab11  cmp     rsi, r15
0x18006ab14  jnz     loc_18006A9EB
  ... truncated ...
```
