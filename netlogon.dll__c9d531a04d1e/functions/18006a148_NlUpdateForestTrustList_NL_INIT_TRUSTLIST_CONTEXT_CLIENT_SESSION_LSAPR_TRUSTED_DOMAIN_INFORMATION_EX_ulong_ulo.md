# NlUpdateForestTrustList(_NL_INIT_TRUSTLIST_CONTEXT *,_CLIENT_SESSION *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,ulong,ulong,ulong,_GUID *,ulong *)

- ea: `0x18006a148`
- end: `0x18006a424`
- name: `?NlUpdateForestTrustList@@YAJPEAU_NL_INIT_TRUSTLIST_CONTEXT@@PEAU_CLIENT_SESSION@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@KKKPEAU_GUID@@PEAK@Z`
- size: `732`
- prototype: `__int64 __usercall@<rax>(struct _NL_INIT_TRUSTLIST_CONTEXT *@<rcx>, struct _CLIENT_SESSION *@<rdx>, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800639e0`
- `0x18006a694`

## callees

- `0x18000d710`
- `0x18003e71c`
- `0x18006a148`
- `0x1800822bc`
- `0x180083180`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x18006a255`
- `ntdll!RtlEqualDomainName` at `0x18006a255`
- `ntdll!RtlEqualSid` at `0x18006a21a`
- `ntdll!RtlEqualSid` at `0x18006a21a`
- `ntdll!RtlInitUnicodeString` at `0x18006a1ae`
- `ntdll!RtlInitUnicodeString` at `0x18006a247`
- `ntdll!RtlInitUnicodeString` at `0x18006a281`
- `ntdll!RtlInitUnicodeString` at `0x18006a1ae`
- `ntdll!RtlInitUnicodeString` at `0x18006a247`
- `ntdll!RtlInitUnicodeString` at `0x18006a281`

## string_xrefs

- `0x18006a3c2`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006a2b6`: `NlUpdateForestTrustList: Similar trusts have different netbios names: %wZ %wZ\n`
- `0x18006a2a4`: `NlUpdateForestTrustList: Similar trusts have different DNS names: %wZ %wZ\n`

## pseudocode

```c
__int64 __fastcall NlUpdateForestTrustList(
        struct _NL_INIT_TRUSTLIST_CONTEXT *a1,
        struct _CLIENT_SESSION *a2,
        struct _UNICODE_STRING *a3,
        char *a4,
        unsigned int a5,
        unsigned int a6,
        struct _GUID *a7,
        unsigned int *a8)
{
  void *v11; // rdx
  struct _UNICODE_STRING v12; // xmm0
  struct _UNICODE_STRING v13; // xmm1
  unsigned int i; // r13d
  unsigned int *v15; // r12
  BOOL v16; // r14d
  struct _DS_DOMAIN_TRUSTSW *v17; // rbx
  PSID DomainSid; // rcx
  const WCHAR *NetbiosDomainName; // rdx
  const WCHAR *DnsDomainName; // rdx
  unsigned int *v21; // r14
  __int64 result; // rax
  char v23; // cl
  ULONG Flags; // eax
  unsigned int v25; // edi
  PSID Sid; // [rsp+60h] [rbp-39h]
  unsigned int *v27; // [rsp+68h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING DomainName2; // [rsp+90h] [rbp-9h] BYREF
  unsigned int v31; // [rsp+E0h] [rbp+47h] BYREF
  struct _DS_DOMAIN_TRUSTSW *v32; // [rsp+E8h] [rbp+4Fh] BYREF
  int v33; // [rsp+F8h] [rbp+5Fh]

  v33 = (int)a4;
  v32 = 0;
  v31 = 0;
  v27 = (unsigned int *)&a3[2].Buffer + 1;
  DomainName1 = 0;
  DestinationString = 0;
  if ( a2 )
  {
    v12 = *(struct _UNICODE_STRING *)((char *)a2 + 152);
    v27 = (unsigned int *)&a3[2].Buffer + 1;
    v13 = (struct _UNICODE_STRING)*((_OWORD *)a2 + 7);
    v11 = (void *)*((_QWORD *)a2 + 33);
    DestinationString = v12;
    DomainName1 = v13;
  }
  else
  {
    if ( HIDWORD(a3[2].Buffer) == 2 )
      DestinationString = *a3;
    else
      RtlInitUnicodeString(&DestinationString, 0);
    v11 = *(void **)&a3[2].Length;
    DomainName1 = a3[1];
  }
  Sid = v11;
  for ( i = 0; ; ++i )
  {
    v15 = a8;
    if ( i >= *((_DWORD *)a1 + 9) )
      break;
    v16 = 0;
    v17 = (struct _DS_DOMAIN_TRUSTSW *)(*(_QWORD *)a1 + 56LL * i);
    v32 = v17;
    if ( v11 )
    {
      DomainSid = v17->DomainSid;
      if ( DomainSid )
        v16 = RtlEqualSid(DomainSid, v11) != 0;
    }
    if ( DomainName1.Length )
    {
      NetbiosDomainName = v17->NetbiosDomainName;
      if ( v17->NetbiosDomainName )
      {
        DomainName2 = 0;
        RtlInitUnicodeString(&DomainName2, NetbiosDomainName);
        if ( RtlEqualDomainName(&DomainName1, &DomainName2) )
        {
          v16 = 1;
        }
        else if ( v16 )
        {
          NlPrintCsRoutine(
            0x100u,
            a2,
            L"NlUpdateForestTrustList: Similar trusts have different netbios names: %wZ %wZ\n",
            &DomainName1,
            &DomainName2);
          goto LABEL_24;
        }
      }
    }
    if ( DestinationString.Length && (DnsDomainName = v17->DnsDomainName) != 0 )
    {
      DomainName2 = 0;
      RtlInitUnicodeString(&DomainName2, DnsDomainName);
      if ( (unsigned int)NlEqualDnsNameU(&DestinationString, &DomainName2) )
        goto LABEL_25;
      if ( v16 )
        NlPrintCsRoutine(
          0x100u,
          a2,
          L"NlUpdateForestTrustList: Similar trusts have different DNS names: %wZ %wZ\n",
          &DestinationString,
          &DomainName2);
    }
    else if ( v16 )
    {
LABEL_25:
      if ( v15 )
        *v15 = i;
      if ( v17 )
      {
        v21 = v27;
        goto LABEL_33;
      }
      break;
    }
LABEL_24:
    v11 = Sid;
    v32 = 0;
  }
  v21 = v27;
  result = NlAllocateForestTrustListEntry(a1, &DomainName1, &DestinationString, 0, 0, *v27, 0, Sid, 0, &v31, &v32);
  if ( (int)result < 0 )
    return result;
  *((_DWORD *)a1 + 8) += v31;
  if ( v15 )
    *v15 = *((_DWORD *)a1 + 9);
  v17 = v32;
  ++*((_DWORD *)a1 + 9);
LABEL_33:
  v17->Flags |= a5;
  v23 = v33;
  Flags = v17->Flags;
  if ( (v33 & 0x4000) != 0 )
  {
    Flags |= 1u;
    v17->Flags = Flags;
  }
  if ( (v23 & 0x10) != 0 )
  {
    if ( ((__int64)a3[2].Buffer & 2) != 0 )
    {
      Flags |= 2u;
      v17->Flags = Flags;
    }
    if ( ((__int64)a3[2].Buffer & 1) != 0 )
      v17->Flags = Flags | 0x20;
  }
  v25 = a6;
  if ( a6 )
  {
    if ( v17->ParentIndex && v17->ParentIndex != a6 )
      NlAssertFailed(
        "TrustedDomain->ParentIndex == 0 || TrustedDomain->ParentIndex == ParentIndex",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
        6749,
        a4);
    v17->ParentIndex = v25;
  }
  v17->TrustType = *v21;
  v17->TrustAttributes |= *(_DWORD *)&a3[3].Length;
  if ( a7 )
    v17->DomainGuid = *a7;
  if ( (v17->Flags & 5) == 5 )
    v17->ParentIndex = 0;
  return 0;
}

```

## disassembly

```asm
0x18006a148  mov     [rsp-8+arg_10], rbx
0x18006a14d  mov     [rsp-8+arg_18], r9d
0x18006a152  push    rbp
0x18006a153  push    rsi
0x18006a154  push    rdi
0x18006a155  push    r12
0x18006a157  push    r13
0x18006a159  push    r14
0x18006a15b  push    r15
0x18006a15d  lea     rbp, [rsp-7]
0x18006a162  sub     rsp, 0A0h
0x18006a169  mov     rsi, r8
0x18006a16c  xorps   xmm0, xmm0
0x18006a16f  xor     r8d, r8d
0x18006a172  xorps   xmm1, xmm1
0x18006a175  mov     [rbp+37h+arg_8], r8
0x18006a179  mov     r15, rdx
0x18006a17c  mov     [rbp+37h+arg_0], r8d
0x18006a180  mov     rdi, rcx
0x18006a183  lea     r14, [rsi+2Ch]
0x18006a187  mov     [rbp+37h+var_68], r14
0x18006a18b  movups  xmmword ptr [rbp+37h+DomainName1.Length], xmm0
0x18006a18f  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm1
0x18006a193  test    rdx, rdx
0x18006a196  jnz     short loc_18006A1C6
0x18006a198  cmp     dword ptr [r14], 2
0x18006a19c  jnz     short loc_18006A1A8
0x18006a19e  movups  xmm0, xmmword ptr [rsi]
0x18006a1a1  movdqu  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18006a1a6  jmp     short loc_18006A1B7
0x18006a1a8  xor     edx, edx; SourceString
0x18006a1aa  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18006a1ae  call    cs:__imp_RtlInitUnicodeString
0x18006a1b4  xor     r8d, r8d
0x18006a1b7  movups  xmm0, xmmword ptr [rsi+10h]
0x18006a1bb  mov     rdx, [rsi+20h]
0x18006a1bf  movdqu  xmmword ptr [rbp+37h+DomainName1.Length], xmm0
0x18006a1c4  jmp     short loc_18006A1E6
0x18006a1c6  movups  xmm0, xmmword ptr [rdx+98h]
0x18006a1cd  mov     [rbp+37h+var_68], r14
0x18006a1d1  movups  xmm1, xmmword ptr [rdx+70h]
0x18006a1d5  mov     rdx, [rdx+108h]; Sid2
0x18006a1dc  movdqu  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18006a1e1  movdqu  xmmword ptr [rbp+37h+DomainName1.Length], xmm1
0x18006a1e6  mov     [rbp+37h+var_70], rdx
0x18006a1ea  mov     r13d, r8d
0x18006a1ed  mov     r12, [rbp+37h+arg_38]
0x18006a1f1  cmp     r13d, [rdi+24h]
0x18006a1f5  jnb     loc_18006A2FB
0x18006a1fb  mov     eax, r13d
0x18006a1fe  mov     r14d, r8d
0x18006a201  imul    rbx, rax, 38h ; '8'
0x18006a205  add     rbx, [rdi]
0x18006a208  mov     [rbp+37h+arg_8], rbx
0x18006a20c  test    rdx, rdx
0x18006a20f  jz      short loc_18006A22D
0x18006a211  mov     rcx, [rbx+20h]; Sid1
0x18006a215  test    rcx, rcx
0x18006a218  jz      short loc_18006A22D
0x18006a21a  call    cs:__imp_RtlEqualSid
0x18006a220  xor     r8d, r8d
0x18006a223  test    al, al
0x18006a225  lea     eax, [r8+1]
0x18006a229  cmovnz  r14d, eax
0x18006a22d  cmp     [rbp+37h+DomainName1.Length], r8w
0x18006a232  jz      short loc_18006A266
0x18006a234  mov     rdx, [rbx]; SourceString
0x18006a237  test    rdx, rdx
0x18006a23a  jz      short loc_18006A266
0x18006a23c  xorps   xmm0, xmm0
0x18006a23f  lea     rcx, [rbp+37h+DomainName2]; DestinationString
0x18006a243  movups  xmmword ptr [rbp+37h+DomainName2.Length], xmm0
0x18006a247  call    cs:__imp_RtlInitUnicodeString
0x18006a24d  lea     rdx, [rbp+37h+DomainName2]; DomainName2
0x18006a251  lea     rcx, [rbp+37h+DomainName1]; DomainName1
0x18006a255  call    cs:__imp_RtlEqualDomainName
0x18006a25b  xor     r8d, r8d
0x18006a25e  test    al, al
0x18006a260  jz      short loc_18006A2AD
0x18006a262  lea     r14d, [r8+1]
0x18006a266  cmp     [rbp+37h+DestinationString.Length], r8w
0x18006a26b  jz      short loc_18006A2D8
0x18006a26d  mov     rdx, [rbx+8]; SourceString
0x18006a271  test    rdx, rdx
0x18006a274  jz      short loc_18006A2D8
0x18006a276  xorps   xmm0, xmm0
0x18006a279  lea     rcx, [rbp+37h+DomainName2]; DestinationString
0x18006a27d  movups  xmmword ptr [rbp+37h+DomainName2.Length], xmm0
0x18006a281  call    cs:__imp_RtlInitUnicodeString
0x18006a287  lea     rdx, [rbp+37h+DomainName2]; struct _UNICODE_STRING *
0x18006a28b  lea     rcx, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x18006a28f  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006a294  xor     r8d, r8d
0x18006a297  test    eax, eax
0x18006a299  jnz     short loc_18006A2ED
0x18006a29b  test    r14d, r14d
0x18006a29e  jz      short loc_18006A2DD
0x18006a2a0  lea     r9, [rbp+37h+DestinationString]
0x18006a2a4  lea     r8, aNlupdateforest_0; "NlUpdateForestTrustList: Similar trusts"...
0x18006a2ab  jmp     short loc_18006A2BD
0x18006a2ad  test    r14d, r14d
0x18006a2b0  jz      short loc_18006A266
0x18006a2b2  lea     r9, [rbp+37h+DomainName1]
0x18006a2b6  lea     r8, aNlupdateforest; "NlUpdateForestTrustList: Similar trusts"...
0x18006a2bd  lea     rax, [rbp+37h+DomainName2]
0x18006a2c1  mov     rdx, r15; struct _CLIENT_SESSION *
0x18006a2c4  mov     ecx, 100h; unsigned int
0x18006a2c9  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18006a2ce  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006a2d3  xor     r8d, r8d
0x18006a2d6  jmp     short loc_18006A2DD
0x18006a2d8  test    r14d, r14d
0x18006a2db  jnz     short loc_18006A2ED
0x18006a2dd  mov     rdx, [rbp+37h+var_70]
0x18006a2e1  inc     r13d
0x18006a2e4  mov     [rbp+37h+arg_8], r8
0x18006a2e8  jmp     loc_18006A1ED
0x18006a2ed  test    r12, r12
0x18006a2f0  jz      short loc_18006A2F6
0x18006a2f2  mov     [r12], r13d
0x18006a2f6  test    rbx, rbx
0x18006a2f9  jnz     short loc_18006A36E
0x18006a2fb  mov     r14, [rbp+37h+var_68]
0x18006a2ff  lea     rax, [rbp+37h+arg_8]
0x18006a303  mov     [rsp+0D0h+var_80], rax; struct _DS_DOMAIN_TRUSTSW **
0x18006a308  lea     rdx, [rbp+37h+DomainName1]; struct _UNICODE_STRING *
0x18006a30c  lea     rax, [rbp+37h+arg_0]
0x18006a310  xor     r9d, r9d; unsigned int
0x18006a313  mov     [rsp+0D0h+var_88], rax; unsigned int *
0x18006a318  mov     rcx, rdi; struct _BUFFER_DESCRIPTOR *
0x18006a31b  mov     rax, [rbp+37h+var_70]
0x18006a31f  mov     [rsp+0D0h+var_90], r8; struct _GUID *
0x18006a324  mov     [rsp+0D0h+Sid], rax; Sid
0x18006a329  mov     eax, [r14]
0x18006a32c  mov     [rsp+0D0h+var_A0], r8d; unsigned int
0x18006a331  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x18006a335  mov     [rsp+0D0h+var_B0], r8d; unsigned int
0x18006a33a  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x18006a33e  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x18006a343  xor     r8d, r8d
0x18006a346  test    eax, eax
0x18006a348  js      loc_18006A409
0x18006a34e  mov     eax, [rbp+37h+arg_0]
0x18006a351  add     [rdi+20h], eax
0x18006a354  test    r12, r12
0x18006a357  jz      short loc_18006A360
0x18006a359  mov     eax, [rdi+24h]
0x18006a35c  mov     [r12], eax
0x18006a360  mov     rbx, [rbp+37h+arg_8]
0x18006a364  mov     edx, 1
0x18006a369  add     [rdi+24h], edx
0x18006a36c  jmp     short loc_18006A377
0x18006a36e  mov     r14, [rbp+37h+var_68]
0x18006a372  mov     edx, 1
0x18006a377  mov     eax, [rbp+37h+arg_20]
0x18006a37a  or      [rbx+10h], eax
0x18006a37d  mov     ecx, [rbp+37h+arg_18]
0x18006a380  mov     eax, [rbx+10h]
0x18006a383  bt      ecx, 0Eh
0x18006a387  jnb     short loc_18006A38E
0x18006a389  or      eax, edx
0x18006a38b  mov     [rbx+10h], eax
0x18006a38e  test    cl, 10h
0x18006a391  jz      short loc_18006A3AA
0x18006a393  test    byte ptr [rsi+28h], 2
0x18006a397  jz      short loc_18006A39F
0x18006a399  or      eax, 2
0x18006a39c  mov     [rbx+10h], eax
0x18006a39f  test    [rsi+28h], dl
0x18006a3a2  jz      short loc_18006A3AA
0x18006a3a4  or      eax, 20h
0x18006a3a7  mov     [rbx+10h], eax
0x18006a3aa  mov     edi, [rbp+37h+arg_28]
0x18006a3ad  test    edi, edi
0x18006a3af  jz      short loc_18006A3DB
0x18006a3b1  cmp     [rbx+14h], r8d
0x18006a3b5  jz      short loc_18006A3D8
0x18006a3b7  cmp     [rbx+14h], edi
0x18006a3ba  jz      short loc_18006A3D8
0x18006a3bc  mov     r8d, 1A5Dh; unsigned int
0x18006a3c2  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006a3c9  lea     rcx, aTrusteddomainP; "TrustedDomain->ParentIndex == 0 || Trus"...
0x18006a3d0  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006a3d5  xor     r8d, r8d
0x18006a3d8  mov     [rbx+14h], edi
0x18006a3db  mov     eax, [r14]
0x18006a3de  mov     [rbx+18h], eax
0x18006a3e1  mov     eax, [rsi+30h]
0x18006a3e4  or      [rbx+1Ch], eax
0x18006a3e7  mov     rax, [rbp+37h+arg_30]
0x18006a3eb  test    rax, rax
0x18006a3ee  jz      short loc_18006A3F8
0x18006a3f0  movups  xmm0, xmmword ptr [rax]
0x18006a3f3  movdqu  xmmword ptr [rbx+28h], xmm0
0x18006a3f8  mov     eax, [rbx+10h]
0x18006a3fb  and     eax, 5
0x18006a3fe  cmp     al, 5
0x18006a400  jnz     short loc_18006A406
0x18006a402  mov     [rbx+14h], r8d
0x18006a406  mov     eax, r8d
0x18006a409  mov     rbx, [rsp+0D0h+arg_10]
0x18006a411  add     rsp, 0A0h
0x18006a418  pop     r15
0x18006a41a  pop     r14
0x18006a41c  pop     r13
0x18006a41e  pop     r12
0x18006a420  pop     rdi
0x18006a421  pop     rsi
0x18006a422  pop     rbp
0x18006a423  retn
```
