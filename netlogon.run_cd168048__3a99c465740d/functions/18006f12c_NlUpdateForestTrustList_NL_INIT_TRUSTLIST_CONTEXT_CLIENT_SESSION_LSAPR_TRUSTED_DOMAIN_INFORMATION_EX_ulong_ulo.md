# NlUpdateForestTrustList(_NL_INIT_TRUSTLIST_CONTEXT *,_CLIENT_SESSION *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,ulong,ulong,ulong,_GUID *,ulong *)

- ea: `0x18006f12c`
- end: `0x18006f427`
- name: `?NlUpdateForestTrustList@@YAJPEAU_NL_INIT_TRUSTLIST_CONTEXT@@PEAU_CLIENT_SESSION@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@KKKPEAU_GUID@@PEAK@Z`
- size: `763`
- prototype: `__int64 __usercall@<rax>(struct _NL_INIT_TRUSTLIST_CONTEXT *@<rcx>, struct _CLIENT_SESSION *@<rdx>, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18006834c`
- `0x18006f6b0`

## callees

- `0x18000dd00`
- `0x180040f18`
- `0x18006f12c`
- `0x180088374`
- `0x180089328`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x18006f24b`
- `ntdll!RtlEqualDomainName` at `0x18006f24b`
- `ntdll!RtlEqualSid` at `0x18006f204`
- `ntdll!RtlEqualSid` at `0x18006f204`
- `ntdll!RtlInitUnicodeString` at `0x18006f192`
- `ntdll!RtlInitUnicodeString` at `0x18006f237`
- `ntdll!RtlInitUnicodeString` at `0x18006f27d`
- `ntdll!RtlInitUnicodeString` at `0x18006f192`
- `ntdll!RtlInitUnicodeString` at `0x18006f237`
- `ntdll!RtlInitUnicodeString` at `0x18006f27d`

## string_xrefs

- `0x18006f3c4`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006f2b8`: `NlUpdateForestTrustList: Similar trusts have different netbios names: %wZ %wZ\n`
- `0x18006f2a6`: `NlUpdateForestTrustList: Similar trusts have different DNS names: %wZ %wZ\n`

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
        0x1A5Du,
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
0x18006f12c  mov     [rsp-8+arg_10], rbx
0x18006f131  mov     [rsp-8+arg_18], r9d
0x18006f136  push    rbp
0x18006f137  push    rsi
0x18006f138  push    rdi
0x18006f139  push    r12
0x18006f13b  push    r13
0x18006f13d  push    r14
0x18006f13f  push    r15
0x18006f141  lea     rbp, [rsp-7]
0x18006f146  sub     rsp, 0A0h
0x18006f14d  mov     rsi, r8
0x18006f150  xorps   xmm0, xmm0
0x18006f153  xor     r8d, r8d
0x18006f156  xorps   xmm1, xmm1
0x18006f159  mov     [rbp+37h+arg_8], r8
0x18006f15d  mov     r15, rdx
0x18006f160  mov     [rbp+37h+arg_0], r8d
0x18006f164  mov     rdi, rcx
0x18006f167  lea     r14, [rsi+2Ch]
0x18006f16b  mov     [rbp+37h+var_68], r14
0x18006f16f  movups  xmmword ptr [rbp+37h+DomainName1.Length], xmm0
0x18006f173  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm1
0x18006f177  test    rdx, rdx
0x18006f17a  jnz     short loc_18006F1B0
0x18006f17c  cmp     dword ptr [r14], 2
0x18006f180  jnz     short loc_18006F18C
0x18006f182  movups  xmm0, xmmword ptr [rsi]
0x18006f185  movdqu  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18006f18a  jmp     short loc_18006F1A1
0x18006f18c  xor     edx, edx; SourceString
0x18006f18e  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18006f192  call    cs:__imp_RtlInitUnicodeString
0x18006f199  nop     dword ptr [rax+rax+00h]
0x18006f19e  xor     r8d, r8d
0x18006f1a1  movups  xmm0, xmmword ptr [rsi+10h]
0x18006f1a5  mov     rdx, [rsi+20h]
0x18006f1a9  movdqu  xmmword ptr [rbp+37h+DomainName1.Length], xmm0
0x18006f1ae  jmp     short loc_18006F1D0
0x18006f1b0  movups  xmm0, xmmword ptr [rdx+98h]
0x18006f1b7  mov     [rbp+37h+var_68], r14
0x18006f1bb  movups  xmm1, xmmword ptr [rdx+70h]
0x18006f1bf  mov     rdx, [rdx+108h]; Sid2
0x18006f1c6  movdqu  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18006f1cb  movdqu  xmmword ptr [rbp+37h+DomainName1.Length], xmm1
0x18006f1d0  mov     [rbp+37h+var_70], rdx
0x18006f1d4  mov     r13d, r8d
0x18006f1d7  mov     r12, [rbp+37h+arg_38]
0x18006f1db  cmp     r13d, [rdi+24h]
0x18006f1df  jnb     loc_18006F2FD
0x18006f1e5  mov     eax, r13d
0x18006f1e8  mov     r14d, r8d
0x18006f1eb  imul    rbx, rax, 38h ; '8'
0x18006f1ef  add     rbx, [rdi]
0x18006f1f2  mov     [rbp+37h+arg_8], rbx
0x18006f1f6  test    rdx, rdx
0x18006f1f9  jz      short loc_18006F21D
0x18006f1fb  mov     rcx, [rbx+20h]; Sid1
0x18006f1ff  test    rcx, rcx
0x18006f202  jz      short loc_18006F21D
0x18006f204  call    cs:__imp_RtlEqualSid
0x18006f20b  nop     dword ptr [rax+rax+00h]
0x18006f210  xor     r8d, r8d
0x18006f213  test    al, al
0x18006f215  lea     eax, [r8+1]
0x18006f219  cmovnz  r14d, eax
0x18006f21d  cmp     [rbp+37h+DomainName1.Length], r8w
0x18006f222  jz      short loc_18006F262
0x18006f224  mov     rdx, [rbx]; SourceString
0x18006f227  test    rdx, rdx
0x18006f22a  jz      short loc_18006F262
0x18006f22c  xorps   xmm0, xmm0
0x18006f22f  lea     rcx, [rbp+37h+DomainName2]; DestinationString
0x18006f233  movups  xmmword ptr [rbp+37h+DomainName2.Length], xmm0
0x18006f237  call    cs:__imp_RtlInitUnicodeString
0x18006f23e  nop     dword ptr [rax+rax+00h]
0x18006f243  lea     rdx, [rbp+37h+DomainName2]; DomainName2
0x18006f247  lea     rcx, [rbp+37h+DomainName1]; DomainName1
0x18006f24b  call    cs:__imp_RtlEqualDomainName
0x18006f252  nop     dword ptr [rax+rax+00h]
0x18006f257  xor     r8d, r8d
0x18006f25a  test    al, al
0x18006f25c  jz      short loc_18006F2AF
0x18006f25e  lea     r14d, [r8+1]
0x18006f262  cmp     [rbp+37h+DestinationString.Length], r8w
0x18006f267  jz      short loc_18006F2DA
0x18006f269  mov     rdx, [rbx+8]; SourceString
0x18006f26d  test    rdx, rdx
0x18006f270  jz      short loc_18006F2DA
0x18006f272  xorps   xmm0, xmm0
0x18006f275  lea     rcx, [rbp+37h+DomainName2]; DestinationString
0x18006f279  movups  xmmword ptr [rbp+37h+DomainName2.Length], xmm0
0x18006f27d  call    cs:__imp_RtlInitUnicodeString
0x18006f284  nop     dword ptr [rax+rax+00h]
0x18006f289  lea     rdx, [rbp+37h+DomainName2]; struct _UNICODE_STRING *
0x18006f28d  lea     rcx, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x18006f291  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006f296  xor     r8d, r8d
0x18006f299  test    eax, eax
0x18006f29b  jnz     short loc_18006F2EF
0x18006f29d  test    r14d, r14d
0x18006f2a0  jz      short loc_18006F2DF
0x18006f2a2  lea     r9, [rbp+37h+DestinationString]
0x18006f2a6  lea     r8, aNlupdateforest_0; "NlUpdateForestTrustList: Similar trusts"...
0x18006f2ad  jmp     short loc_18006F2BF
0x18006f2af  test    r14d, r14d
0x18006f2b2  jz      short loc_18006F262
0x18006f2b4  lea     r9, [rbp+37h+DomainName1]
0x18006f2b8  lea     r8, aNlupdateforest; "NlUpdateForestTrustList: Similar trusts"...
0x18006f2bf  lea     rax, [rbp+37h+DomainName2]
0x18006f2c3  mov     rdx, r15; struct _CLIENT_SESSION *
0x18006f2c6  mov     ecx, 100h; unsigned int
0x18006f2cb  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18006f2d0  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006f2d5  xor     r8d, r8d
0x18006f2d8  jmp     short loc_18006F2DF
0x18006f2da  test    r14d, r14d
0x18006f2dd  jnz     short loc_18006F2EF
0x18006f2df  mov     rdx, [rbp+37h+var_70]
0x18006f2e3  inc     r13d
0x18006f2e6  mov     [rbp+37h+arg_8], r8
0x18006f2ea  jmp     loc_18006F1D7
0x18006f2ef  test    r12, r12
0x18006f2f2  jz      short loc_18006F2F8
0x18006f2f4  mov     [r12], r13d
0x18006f2f8  test    rbx, rbx
0x18006f2fb  jnz     short loc_18006F370
0x18006f2fd  mov     r14, [rbp+37h+var_68]
0x18006f301  lea     rax, [rbp+37h+arg_8]
0x18006f305  mov     [rsp+0D0h+var_80], rax; struct _DS_DOMAIN_TRUSTSW **
0x18006f30a  lea     rdx, [rbp+37h+DomainName1]; struct _UNICODE_STRING *
0x18006f30e  lea     rax, [rbp+37h+arg_0]
0x18006f312  xor     r9d, r9d; unsigned int
0x18006f315  mov     [rsp+0D0h+var_88], rax; unsigned int *
0x18006f31a  mov     rcx, rdi; struct _BUFFER_DESCRIPTOR *
0x18006f31d  mov     rax, [rbp+37h+var_70]
0x18006f321  mov     [rsp+0D0h+var_90], r8; struct _GUID *
0x18006f326  mov     [rsp+0D0h+Sid], rax; Sid
0x18006f32b  mov     eax, [r14]
0x18006f32e  mov     [rsp+0D0h+var_A0], r8d; unsigned int
0x18006f333  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x18006f337  mov     [rsp+0D0h+var_B0], r8d; unsigned int
0x18006f33c  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x18006f340  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x18006f345  xor     r8d, r8d
0x18006f348  test    eax, eax
0x18006f34a  js      loc_18006F40B
0x18006f350  mov     eax, [rbp+37h+arg_0]
0x18006f353  add     [rdi+20h], eax
0x18006f356  test    r12, r12
0x18006f359  jz      short loc_18006F362
0x18006f35b  mov     eax, [rdi+24h]
0x18006f35e  mov     [r12], eax
0x18006f362  mov     rbx, [rbp+37h+arg_8]
0x18006f366  mov     edx, 1
0x18006f36b  add     [rdi+24h], edx
0x18006f36e  jmp     short loc_18006F379
0x18006f370  mov     r14, [rbp+37h+var_68]
0x18006f374  mov     edx, 1
0x18006f379  mov     eax, [rbp+37h+arg_20]
0x18006f37c  or      [rbx+10h], eax
0x18006f37f  mov     ecx, [rbp+37h+arg_18]
0x18006f382  mov     eax, [rbx+10h]
0x18006f385  bt      ecx, 0Eh
0x18006f389  jnb     short loc_18006F390
0x18006f38b  or      eax, edx
0x18006f38d  mov     [rbx+10h], eax
0x18006f390  test    cl, 10h
0x18006f393  jz      short loc_18006F3AC
0x18006f395  test    byte ptr [rsi+28h], 2
0x18006f399  jz      short loc_18006F3A1
0x18006f39b  or      eax, 2
0x18006f39e  mov     [rbx+10h], eax
0x18006f3a1  test    [rsi+28h], dl
0x18006f3a4  jz      short loc_18006F3AC
0x18006f3a6  or      eax, 20h
0x18006f3a9  mov     [rbx+10h], eax
0x18006f3ac  mov     edi, [rbp+37h+arg_28]
0x18006f3af  test    edi, edi
0x18006f3b1  jz      short loc_18006F3DD
0x18006f3b3  cmp     [rbx+14h], r8d
0x18006f3b7  jz      short loc_18006F3DA
0x18006f3b9  cmp     [rbx+14h], edi
0x18006f3bc  jz      short loc_18006F3DA
0x18006f3be  mov     r8d, 1A5Dh; unsigned int
0x18006f3c4  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006f3cb  lea     rcx, aTrusteddomainP; "TrustedDomain->ParentIndex == 0 || Trus"...
0x18006f3d2  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006f3d7  xor     r8d, r8d
0x18006f3da  mov     [rbx+14h], edi
0x18006f3dd  mov     eax, [r14]
0x18006f3e0  mov     [rbx+18h], eax
0x18006f3e3  mov     eax, [rsi+30h]
0x18006f3e6  or      [rbx+1Ch], eax
0x18006f3e9  mov     rax, [rbp+37h+arg_30]
0x18006f3ed  test    rax, rax
0x18006f3f0  jz      short loc_18006F3FA
0x18006f3f2  movups  xmm0, xmmword ptr [rax]
0x18006f3f5  movdqu  xmmword ptr [rbx+28h], xmm0
0x18006f3fa  mov     eax, [rbx+10h]
0x18006f3fd  and     eax, 5
0x18006f400  cmp     al, 5
0x18006f402  jnz     short loc_18006F408
0x18006f404  mov     [rbx+14h], r8d
0x18006f408  mov     eax, r8d
0x18006f40b  mov     rbx, [rsp+0D0h+arg_10]
0x18006f413  add     rsp, 0A0h
0x18006f41a  pop     r15
0x18006f41c  pop     r14
0x18006f41e  pop     r13
0x18006f420  pop     r12
0x18006f422  pop     rdi
0x18006f423  pop     rsi
0x18006f424  pop     rbp
0x18006f425  retn
```
