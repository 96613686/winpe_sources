# LsapDbLookupIsolatedDomainNameEx(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)

- ea: `0x180039660`
- end: `0x180039afe`
- name: `?LsapDbLookupIsolatedDomainNameEx@@YAJKPEAU_LSAPR_UNICODE_STRING@@PEAU_LSAPR_TRUST_INFORMATION_EX@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK4@Z`
- size: `1182`
- prototype: `__int64 __fastcall(unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_TRUST_INFORMATION_EX *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800388a0`

## callees

- `0x180039660`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039af0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039af0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800396d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039739`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039864`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800398ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039918`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003998a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800396d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039739`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039864`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800398ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039918`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003998a`
- `ntdll!RtlEqualDomainName` at `0x18003978c`
- `ntdll!RtlEqualDomainName` at `0x18003978c`
- `ntdll!RtlCopySid` at `0x1800399ba`
- `ntdll!RtlCopySid` at `0x1800399ba`
- `ntdll!RtlCopyUnicodeString` at `0x1800398eb`
- `ntdll!RtlCopyUnicodeString` at `0x1800398eb`
- `ntdll!RtlLengthSid` at `0x180039903`
- `ntdll!RtlLengthSid` at `0x180039975`
- `ntdll!RtlLengthSid` at `0x180039903`
- `ntdll!RtlLengthSid` at `0x180039975`
- `ntdll!RtlEqualSid` at `0x180039a56`
- `ntdll!RtlEqualSid` at `0x180039a56`
- `DNSAPI!DnsNameCompare_W` at `0x1800397a9`
- `DNSAPI!DnsNameCompare_W` at `0x1800397a9`

## pseudocode

```c
__int64 __fastcall LsapDbLookupIsolatedDomainNameEx(
        unsigned int a1,
        struct _UNICODE_STRING *a2,
        struct _LSAPR_TRUST_INFORMATION_EX *a3,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a4,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  unsigned __int64 Length; // rdx
  unsigned int v10; // ebx
  WCHAR *v11; // rax
  WCHAR *Buffer; // rdi
  char v13; // r15
  unsigned __int64 v14; // rdx
  const void **v15; // r12
  char v16; // r13
  HLOCAL v17; // rsi
  int v18; // eax
  bool v19; // r12
  int v20; // ebx
  PSID v21; // rdi
  int v22; // r15d
  __int64 v23; // r12
  __int64 v24; // rsi
  unsigned int v25; // ebx
  unsigned int v26; // edi
  HLOCAL v27; // rax
  HLOCAL v28; // r12
  void *v29; // r15
  __int64 v30; // r15
  PSID v31; // rbx
  ULONG v32; // edi
  HLOCAL v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  ULONG v36; // ebx
  void *v37; // rdx
  void *v39; // rcx
  struct _UNICODE_STRING *DomainName2; // [rsp+28h] [rbp-38h]
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-30h] BYREF
  PSID Sid; // [rsp+40h] [rbp-20h]
  _BYTE DestinationString[24]; // [rsp+48h] [rbp-18h] BYREF
  struct _LSAPR_TRUST_INFORMATION_EX *v46; // [rsp+B0h] [rbp+50h]
  __int64 v47; // [rsp+B0h] [rbp+50h]

  v46 = a3;
  Length = a2->Length;
  SourceString = (UNICODE_STRING)*((_OWORD *)a3 + 1);
  v10 = -1073741709;
  Sid = (PSID)*((_QWORD *)a3 + 4);
  DomainName2 = (struct _UNICODE_STRING *)((char *)a3 + 16);
  if ( a2->MaximumLength <= (unsigned __int16)Length || (Buffer = a2->Buffer, Buffer[Length >> 1]) )
  {
    v11 = (WCHAR *)LocalAlloc(0x40u, Length + 2);
    Buffer = v11;
    if ( !v11 )
      return v10;
    v13 = 1;
    memcpy_0(v11, a2->Buffer, a2->Length);
    a3 = v46;
    Buffer[(unsigned __int64)a2->Length >> 1] = 0;
  }
  else
  {
    v13 = 0;
  }
  v14 = *(unsigned __int16 *)a3;
  v15 = (const void **)((char *)a3 + 8);
  v16 = 0;
  if ( *((_WORD *)a3 + 1) <= (unsigned __int16)v14 || (v17 = (HLOCAL)*v15, *((_WORD *)*v15 + (v14 >> 1))) )
  {
    v17 = LocalAlloc(0x40u, v14 + 2);
    if ( v17 )
    {
      v16 = 1;
      memcpy_0(v17, *v15, *(unsigned __int16 *)v46);
      v18 = 0;
      *((_WORD *)v17 + ((unsigned __int64)*(unsigned __int16 *)v46 >> 1)) = 0;
    }
    else
    {
      v18 = -1073741801;
    }
  }
  else
  {
    v18 = 0;
  }
  v19 = v18 >= 0 && (RtlEqualDomainName(a2, DomainName2) || DnsNameCompare_W(Buffer, (PCWSTR)v17));
  if ( v13 )
    LocalFree(Buffer);
  if ( v16 )
    LocalFree(v17);
  if ( v19 )
  {
    memset(DestinationString, 0, sizeof(DestinationString));
    if ( !a4 )
    {
      v10 = -1073741811;
LABEL_48:
      if ( *(_QWORD *)&DestinationString[8] )
        LocalFree(*(HLOCAL *)&DestinationString[8]);
      if ( *(_QWORD *)&DestinationString[16] )
        LocalFree(*(HLOCAL *)&DestinationString[16]);
      return v10;
    }
    v20 = 0;
    v21 = Sid;
    v22 = *(_DWORD *)a4;
    v23 = *((_QWORD *)a4 + 1);
    v24 = 24LL * a1;
    v47 = *((_QWORD *)a5 + 1);
    *(_DWORD *)(v24 + v47 + 16) = -1;
    while ( v20 < v22 && v21 )
    {
      v39 = *(void **)(v23 + 24LL * v20 + 16);
      if ( v39 && RtlEqualSid(v39, v21) )
      {
        *(_DWORD *)(v24 + v47 + 16) = v20;
        goto LABEL_33;
      }
      ++v20;
    }
    v25 = *((_DWORD *)a4 + 4);
    if ( *(_DWORD *)a4 >= v25 )
    {
      v26 = v25 + 32;
      if ( v25 < v25 + 32 )
      {
        v27 = LocalAlloc(0x40u, 24 * v26);
        v28 = v27;
        if ( !v27 )
          goto LABEL_53;
        v29 = (void *)*((_QWORD *)a4 + 1);
        if ( v29 )
        {
          memcpy_0(v27, *((const void **)a4 + 1), 24 * v25);
          LocalFree(v29);
        }
        *((_QWORD *)a4 + 1) = v28;
        *((_DWORD *)a4 + 4) = v26;
      }
    }
    v30 = *(unsigned int *)a4;
    *(UNICODE_STRING *)DestinationString = SourceString;
    if ( SourceString.Buffer )
    {
      if ( SourceString.MaximumLength )
      {
        *(_QWORD *)&DestinationString[8] = LocalAlloc(0x40u, SourceString.MaximumLength);
        if ( !*(_QWORD *)&DestinationString[8] )
          goto LABEL_53;
        RtlCopyUnicodeString((PUNICODE_STRING)DestinationString, &SourceString);
      }
      else
      {
        *(_QWORD *)&DestinationString[8] = 0;
      }
    }
    v31 = Sid;
    if ( !Sid )
      goto LABEL_32;
    v32 = RtlLengthSid(Sid);
    v33 = LocalAlloc(0x40u, v32);
    *(_QWORD *)&DestinationString[16] = v33;
    if ( v33 )
    {
      memcpy_0(v33, v31, v32);
LABEL_32:
      v34 = *((_QWORD *)a4 + 1);
      v35 = 3 * v30;
      *(_OWORD *)(v34 + 8 * v35) = *(_OWORD *)DestinationString;
      *(_QWORD *)(v34 + 8 * v35 + 16) = *(_QWORD *)&DestinationString[16];
      *(_DWORD *)(v24 + v47 + 16) = v30;
      ++*(_DWORD *)a4;
LABEL_33:
      *(_DWORD *)(v24 + *((_QWORD *)a5 + 1)) = 3;
      v36 = RtlLengthSid(Sid);
      *(_QWORD *)(*((_QWORD *)a5 + 1) + v24 + 8) = LocalAlloc(0x40u, v36);
      v37 = *(void **)(*((_QWORD *)a5 + 1) + v24 + 8);
      if ( v37 )
      {
        RtlCopySid(v36, v37, Sid);
        v10 = 0;
        ++*a6;
        --*a7;
      }
      else
      {
        return (unsigned int)-1073741801;
      }
      return v10;
    }
LABEL_53:
    v10 = -1073741670;
    goto LABEL_48;
  }
  return v10;
}

```

## disassembly

```asm
0x180039660  mov     rax, rsp
0x180039663  mov     [rax+20h], rbx
0x180039667  mov     [rax+18h], r8
0x18003966b  mov     [rax+10h], rdx
0x18003966f  mov     [rax+8], ecx
0x180039672  push    rbp
0x180039673  push    rsi
0x180039674  push    rdi
0x180039675  push    r12
0x180039677  push    r13
0x180039679  push    r14
0x18003967b  push    r15
0x18003967d  mov     rbp, rsp
0x180039680  sub     rsp, 60h
0x180039684  lea     rcx, [r8+10h]
0x180039688  mov     r13, rdx
0x18003968b  movzx   eax, word ptr [rcx]
0x18003968e  mov     r14, r9
0x180039691  movzx   edx, word ptr [rdx]
0x180039694  xor     r9d, r9d
0x180039697  mov     [rbp+SourceString.Length], ax
0x18003969b  mov     ebx, 0C0000073h
0x1800396a0  movzx   eax, word ptr [rcx+2]
0x1800396a4  mov     [rbp+SourceString.MaximumLength], ax
0x1800396a8  mov     eax, [rcx+4]
0x1800396ab  mov     dword ptr [rbp+SourceString+4], eax
0x1800396ae  mov     rax, [rcx+8]
0x1800396b2  mov     [rbp+SourceString.Buffer], rax
0x1800396b6  mov     rax, [r8+20h]
0x1800396ba  mov     [rbp+Sid], rax
0x1800396be  mov     [rbp+DomainName2], rcx
0x1800396c2  cmp     [r13+2], dx
0x1800396c7  ja      loc_180039A11
0x1800396cd  add     rdx, 2; uBytes
0x1800396d1  mov     ecx, 40h ; '@'; uFlags
0x1800396d6  call    cs:__imp_LocalAlloc
0x1800396dd  nop     dword ptr [rax+rax+00h]
0x1800396e2  mov     rdi, rax
0x1800396e5  test    rax, rax
0x1800396e8  jz      loc_1800399D5
0x1800396ee  movzx   r8d, word ptr [r13+0]; Size
0x1800396f3  mov     rcx, rax; void *
0x1800396f6  mov     rdx, [r13+8]; Src
0x1800396fa  mov     r15b, 1
0x1800396fd  call    memcpy_0
0x180039702  movzx   ecx, word ptr [r13+0]
0x180039707  mov     r8, [rbp+arg_10]
0x18003970b  shr     rcx, 1
0x18003970e  xor     r9d, r9d
0x180039711  mov     [rdi+rcx*2], r9w
0x180039716  movzx   edx, word ptr [r8]
0x18003971a  lea     r12, [r8+8]
0x18003971e  mov     r13b, r9b
0x180039721  mov     [rbp+var_40], r9d
0x180039725  cmp     [r8+2], dx
0x18003972a  ja      loc_180039A2E
0x180039730  add     rdx, 2; uBytes
0x180039734  mov     ecx, 40h ; '@'; uFlags
0x180039739  call    cs:__imp_LocalAlloc
0x180039740  nop     dword ptr [rax+rax+00h]
0x180039745  xor     r9d, r9d
0x180039748  mov     rsi, rax
0x18003974b  test    rax, rax
0x18003974e  jz      loc_180039A76
0x180039754  mov     rax, [rbp+arg_10]
0x180039758  mov     rcx, rsi; void *
0x18003975b  mov     rdx, [r12]; Src
0x18003975f  mov     r13b, 1
0x180039762  movzx   r8d, word ptr [rax]; Size
0x180039766  call    memcpy_0
0x18003976b  mov     rax, [rbp+arg_10]
0x18003976f  movzx   ecx, word ptr [rax]
0x180039772  mov     eax, [rbp+var_40]
0x180039775  shr     rcx, 1
0x180039778  xor     r9d, r9d
0x18003977b  mov     [rsi+rcx*2], r9w
0x180039780  test    eax, eax
0x180039782  js      short loc_1800397C0
0x180039784  mov     rdx, [rbp+DomainName2]; DomainName2
0x180039788  mov     rcx, [rbp+DomainName1]; DomainName1
0x18003978c  call    cs:__imp_RtlEqualDomainName
0x180039793  nop     dword ptr [rax+rax+00h]
0x180039798  xor     r9d, r9d
0x18003979b  test    al, al
0x18003979d  jnz     loc_180039A4B
0x1800397a3  mov     rdx, rsi; pName2
0x1800397a6  mov     rcx, rdi; pName1
0x1800397a9  call    cs:__imp_DnsNameCompare_W
0x1800397b0  nop     dword ptr [rax+rax+00h]
0x1800397b5  xor     r9d, r9d
0x1800397b8  test    eax, eax
0x1800397ba  jnz     loc_180039A4B
0x1800397c0  mov     r12b, r9b
0x1800397c3  test    r15b, r15b
0x1800397c6  jz      short loc_1800397DA
0x1800397c8  mov     rcx, rdi; hMem
0x1800397cb  call    cs:__imp_LocalFree
0x1800397d2  nop     dword ptr [rax+rax+00h]
0x1800397d7  xor     r9d, r9d
0x1800397da  test    r13b, r13b
0x1800397dd  jz      short loc_1800397F1
0x1800397df  mov     rcx, rsi; hMem
0x1800397e2  call    cs:__imp_LocalFree
0x1800397e9  nop     dword ptr [rax+rax+00h]
0x1800397ee  xor     r9d, r9d
0x1800397f1  test    r12b, r12b
0x1800397f4  jz      loc_1800399D5
0x1800397fa  mov     qword ptr [rbp+DestinationString.Length], r9
0x1800397fe  xorps   xmm0, xmm0
0x180039801  movdqu  xmmword ptr [rbp+DestinationString.Buffer], xmm0
0x180039806  test    r14, r14
0x180039809  jz      loc_180039A80
0x18003980f  mov     eax, [rbp+arg_0]
0x180039812  mov     ebx, r9d
0x180039815  mov     r13, [rbp+arg_20]
0x180039819  mov     rdi, [rbp+Sid]
0x18003981d  mov     r15d, [r14]
0x180039820  mov     r12, [r14+8]
0x180039824  lea     rcx, [rax+rax*2]
0x180039828  mov     rax, [r13+8]
0x18003982c  lea     rsi, ds:0[rcx*8]
0x180039834  mov     [rbp+arg_10], rax
0x180039838  mov     dword ptr [rsi+rax+10h], 0FFFFFFFFh
0x180039840  cmp     ebx, r15d
0x180039843  jl      loc_1800399F0
0x180039849  mov     ebx, [r14+10h]
0x18003984d  cmp     [r14], ebx
0x180039850  jb      short loc_180039894
0x180039852  lea     edi, [rbx+20h]
0x180039855  cmp     ebx, edi
0x180039857  jnb     short loc_180039894
0x180039859  lea     edx, [rdi+rdi*2]
0x18003985c  mov     ecx, 40h ; '@'; uFlags
0x180039861  shl     edx, 3; uBytes
0x180039864  call    cs:__imp_LocalAlloc
0x18003986b  nop     dword ptr [rax+rax+00h]
0x180039870  xor     r9d, r9d
0x180039873  mov     r12, rax
0x180039876  test    rax, rax
0x180039879  jz      loc_180039AB5
0x18003987f  mov     r15, [r14+8]
0x180039883  test    r15, r15
0x180039886  jnz     loc_180039ABC
0x18003988c  mov     [r14+8], r12
0x180039890  mov     [r14+10h], edi
0x180039894  movzx   eax, [rbp+SourceString.Length]
0x180039898  movzx   ecx, [rbp+SourceString.MaximumLength]
0x18003989c  mov     r15d, [r14]
0x18003989f  mov     [rbp+DestinationString.Length], ax
0x1800398a3  mov     eax, dword ptr [rbp+SourceString+4]
0x1800398a6  mov     dword ptr [rbp+DestinationString+4], eax
0x1800398a9  mov     rax, [rbp+SourceString.Buffer]
0x1800398ad  mov     [rbp+DestinationString.MaximumLength], cx
0x1800398b1  mov     [rbp+DestinationString.Buffer], rax
0x1800398b5  test    rax, rax
0x1800398b8  jz      short loc_1800398F7
0x1800398ba  test    cx, cx
0x1800398bd  jz      loc_180039AAC
0x1800398c3  mov     edx, ecx; uBytes
0x1800398c5  mov     ecx, 40h ; '@'; uFlags
0x1800398ca  call    cs:__imp_LocalAlloc
0x1800398d1  nop     dword ptr [rax+rax+00h]
0x1800398d6  mov     [rbp+DestinationString.Buffer], rax
0x1800398da  test    rax, rax
0x1800398dd  jz      loc_180039AB5
0x1800398e3  lea     rdx, [rbp+SourceString]; SourceString
0x1800398e7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800398eb  call    cs:__imp_RtlCopyUnicodeString
0x1800398f2  nop     dword ptr [rax+rax+00h]
0x1800398f7  mov     rbx, [rbp+Sid]
0x1800398fb  test    rbx, rbx
0x1800398fe  jz      short loc_18003993F
0x180039900  mov     rcx, rbx; Sid
0x180039903  call    cs:__imp_RtlLengthSid
0x18003990a  nop     dword ptr [rax+rax+00h]
0x18003990f  mov     edx, eax; uBytes
0x180039911  mov     ecx, 40h ; '@'; uFlags
0x180039916  mov     edi, eax
0x180039918  call    cs:__imp_LocalAlloc
0x18003991f  nop     dword ptr [rax+rax+00h]
0x180039924  mov     [rbp+hMem], rax
0x180039928  test    rax, rax
0x18003992b  jz      loc_180039AB5
0x180039931  mov     r8d, edi; Size
0x180039934  mov     rdx, rbx; Src
0x180039937  mov     rcx, rax; void *
0x18003993a  call    memcpy_0
0x18003993f  mov     rax, [r14+8]
0x180039943  lea     rdx, [r15+r15*2]
0x180039947  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x18003994b  movups  xmmword ptr [rax+rdx*8], xmm0
0x18003994f  movsd   xmm1, [rbp+hMem]
0x180039954  movsd   qword ptr [rax+rdx*8+10h], xmm1
0x18003995a  mov     rax, [rbp+arg_10]
0x18003995e  mov     [rsi+rax+10h], r15d
0x180039963  inc     dword ptr [r14]
0x180039966  mov     rax, [r13+8]
0x18003996a  mov     dword ptr [rsi+rax], 3
0x180039971  mov     rcx, [rbp+Sid]; Sid
0x180039975  call    cs:__imp_RtlLengthSid
0x18003997c  nop     dword ptr [rax+rax+00h]
0x180039981  mov     edx, eax; uBytes
0x180039983  mov     ecx, 40h ; '@'; uFlags
0x180039988  mov     ebx, eax
0x18003998a  call    cs:__imp_LocalAlloc
0x180039991  nop     dword ptr [rax+rax+00h]
0x180039996  mov     rcx, [r13+8]
0x18003999a  xor     r15d, r15d
0x18003999d  mov     [rcx+rsi+8], rax
0x1800399a2  mov     rcx, [r13+8]
0x1800399a6  mov     rdx, [rcx+rsi+8]; DestinationSid
0x1800399ab  test    rdx, rdx
0x1800399ae  jz      loc_180039AE6
0x1800399b4  mov     r8, [rbp+Sid]; SourceSid
0x1800399b8  mov     ecx, ebx; DestinationSidLength
0x1800399ba  call    cs:__imp_RtlCopySid
0x1800399c1  nop     dword ptr [rax+rax+00h]
0x1800399c6  mov     rax, [rbp+arg_28]
0x1800399ca  mov     ebx, r15d
0x1800399cd  inc     dword ptr [rax]
0x1800399cf  mov     rax, [rbp+arg_30]
0x1800399d3  dec     dword ptr [rax]
0x1800399d5  mov     eax, ebx
0x1800399d7  mov     rbx, [rsp+60h+arg_18]
0x1800399df  add     rsp, 60h
0x1800399e3  pop     r15
0x1800399e5  pop     r14
0x1800399e7  pop     r13
0x1800399e9  pop     r12
0x1800399eb  pop     rdi
0x1800399ec  pop     rsi
0x1800399ed  pop     rbp
0x1800399ee  retn
0x1800399f0  test    rdi, rdi
0x1800399f3  jz      loc_180039849
0x1800399f9  movsxd  rax, ebx
0x1800399fc  lea     rcx, [rax+rax*2]
0x180039a00  mov     rcx, [r12+rcx*8+10h]; Sid1
0x180039a05  test    rcx, rcx
0x180039a08  jnz     short loc_180039A53
0x180039a0a  inc     ebx
0x180039a0c  jmp     loc_180039840
0x180039a11  mov     rdi, [r13+8]
0x180039a15  mov     rax, rdx
0x180039a18  shr     rax, 1
0x180039a1b  cmp     [rdi+rax*2], r9w
0x180039a20  jnz     loc_1800396CD
0x180039a26  mov     r15b, r9b
0x180039a29  jmp     loc_180039716
0x180039a2e  mov     rsi, [r12]
0x180039a32  mov     rax, rdx
0x180039a35  shr     rax, 1
0x180039a38  cmp     [rsi+rax*2], r9w
0x180039a3d  jnz     loc_180039730
0x180039a43  mov     eax, r9d
0x180039a46  jmp     loc_180039780
0x180039a4b  mov     r12b, 1
0x180039a4e  jmp     loc_1800397C3
0x180039a53  mov     rdx, rdi; Sid2
0x180039a56  call    cs:__imp_RtlEqualSid
0x180039a5d  nop     dword ptr [rax+rax+00h]
0x180039a62  xor     r9d, r9d
0x180039a65  test    al, al
0x180039a67  jz      short loc_180039A0A
0x180039a69  mov     rax, [rbp+arg_10]
0x180039a6d  mov     [rsi+rax+10h], ebx
0x180039a71  jmp     loc_180039966
0x180039a76  mov     eax, 0C0000017h
0x180039a7b  jmp     loc_180039780
0x180039a80  mov     ebx, 0C000000Dh
0x180039a85  mov     rcx, [rbp+DestinationString.Buffer]; hMem
0x180039a89  test    rcx, rcx
0x180039a8c  jnz     short loc_180039AF0
0x180039a8e  mov     rcx, [rbp+hMem]; hMem
0x180039a92  test    rcx, rcx
0x180039a95  jz      loc_1800399D5
0x180039a9b  call    cs:__imp_LocalFree
0x180039aa2  nop     dword ptr [rax+rax+00h]
0x180039aa7  jmp     loc_1800399D5
0x180039aac  mov     [rbp+DestinationString.Buffer], r9
0x180039ab0  jmp     loc_1800398F7
0x180039ab5  mov     ebx, 0C000009Ah
0x180039aba  jmp     short loc_180039A85
0x180039abc  lea     r8d, [rbx+rbx*2]
0x180039ac0  mov     rdx, r15; Src
0x180039ac3  shl     r8d, 3; Size
0x180039ac7  mov     rcx, r12; void *
0x180039aca  call    memcpy_0
0x180039acf  mov     rcx, r15; hMem
0x180039ad2  call    cs:__imp_LocalFree
0x180039ad9  nop     dword ptr [rax+rax+00h]
0x180039ade  xor     r9d, r9d
0x180039ae1  jmp     loc_18003988C
0x180039ae6  mov     ebx, 0C0000017h
0x180039aeb  jmp     loc_1800399D5
0x180039af0  call    cs:__imp_LocalFree
0x180039af7  nop     dword ptr [rax+rax+00h]
0x180039afc  jmp     short loc_180039A8E
```
