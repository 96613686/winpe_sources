# LsapDbLookupIsolatedDomainName(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)

- ea: `0x180038618`
- end: `0x18003889a`
- name: `?LsapDbLookupIsolatedDomainName@@YAJKPEAU_LSAPR_UNICODE_STRING@@PEAU_LSAPR_TRUST_INFORMATION@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK4@Z`
- size: `642`
- prototype: `int(unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_TRUST_INFORMATION *, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800388a0`

## callees

- `0x180038618`
- `0x180039400`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003868d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800386de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800387db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003868d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800386de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800387db`
- `ntdll!RtlEqualDomainName` at `0x180038727`
- `ntdll!RtlEqualDomainName` at `0x180038727`
- `ntdll!RtlCopySid` at `0x180038808`
- `ntdll!RtlCopySid` at `0x180038808`
- `ntdll!RtlLengthSid` at `0x1800387c6`
- `ntdll!RtlLengthSid` at `0x1800387c6`
- `DNSAPI!DnsNameCompare_W` at `0x180038744`
- `DNSAPI!DnsNameCompare_W` at `0x180038744`

## pseudocode

```c
__int64 __fastcall LsapDbLookupIsolatedDomainName(
        unsigned int a1,
        struct _UNICODE_STRING *a2,
        struct _LSAPR_TRUST_INFORMATION *a3,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a4,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  __int64 v7; // r10
  WCHAR *v8; // rax
  void *v10; // r8
  char v11; // r12
  unsigned __int64 Length; // rdx
  int v13; // r15d
  WCHAR *v14; // rax
  WCHAR *Buffer; // rbx
  char v16; // si
  int v17; // r13d
  WCHAR *v18; // rax
  WCHAR *v19; // rdi
  bool v20; // r14
  ULONG v21; // esi
  void *v22; // rdx
  _QWORD v24[2]; // [rsp+20h] [rbp-50h] BYREF
  PSID Sid; // [rsp+30h] [rbp-40h]
  void *Src[2]; // [rsp+38h] [rbp-38h]
  struct _UNICODE_STRING DomainName2; // [rsp+48h] [rbp-28h] BYREF
  __int128 v28; // [rsp+58h] [rbp-18h]

  v7 = *(_QWORD *)a3;
  v8 = (WCHAR *)*((_QWORD *)a3 + 1);
  v10 = (void *)*((_QWORD *)a3 + 2);
  v11 = 0;
  Length = a2->Length;
  v13 = -1073741709;
  *(_QWORD *)&DomainName2.Length = v7;
  DomainName2.Buffer = v8;
  *(_OWORD *)Src = 0;
  v28 = (unsigned __int64)v10;
  v24[0] = v7;
  v24[1] = v8;
  Sid = v10;
  if ( a2->MaximumLength <= (unsigned __int16)Length || (Buffer = a2->Buffer, Buffer[Length >> 1]) )
  {
    v14 = (WCHAR *)LocalAlloc(0x40u, Length + 2);
    Buffer = v14;
    if ( !v14 )
      return (unsigned int)v13;
    v16 = 1;
    memcpy_0(v14, a2->Buffer, a2->Length);
    Buffer[(unsigned __int64)a2->Length >> 1] = 0;
  }
  else
  {
    v16 = 0;
  }
  v17 = 0;
  if ( WORD1(Src[0]) <= LOWORD(Src[0])
    || (v19 = (WCHAR *)Src[1], *((_WORD *)Src[1] + ((unsigned __int64)LOWORD(Src[0]) >> 1))) )
  {
    v18 = (WCHAR *)LocalAlloc(0x40u, LOWORD(Src[0]) + 2LL);
    v19 = v18;
    if ( v18 )
    {
      v11 = 1;
      memcpy_0(v18, Src[1], LOWORD(Src[0]));
      v19[(unsigned __int64)LOWORD(Src[0]) >> 1] = 0;
    }
    else
    {
      v17 = -1073741801;
    }
  }
  v20 = v17 >= 0 && (RtlEqualDomainName(a2, &DomainName2) || DnsNameCompare_W(Buffer, v19));
  if ( v16 )
    LocalFree(Buffer);
  if ( v11 )
    LocalFree(v19);
  if ( v20 )
  {
    v13 = LsapDbLookupAddListReferencedDomains(a4, v24, *((_QWORD *)a5 + 1) + 16LL + 24LL * a1);
    if ( v13 >= 0 )
    {
      *(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL * a1) = 3;
      v21 = RtlLengthSid(Sid);
      *(_QWORD *)(*((_QWORD *)a5 + 1) + 24LL * a1 + 8) = LocalAlloc(0x40u, v21);
      v22 = *(void **)(*((_QWORD *)a5 + 1) + 24LL * a1 + 8);
      if ( v22 )
      {
        RtlCopySid(v21, v22, Sid);
        v13 = 0;
        ++*a6;
        --*a7;
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180038618  mov     [rsp-38h+arg_8], rbx
0x18003861d  mov     [rsp-38h+arg_18], r9
0x180038622  mov     [rsp-38h+arg_0], ecx
0x180038626  push    rbp
0x180038627  push    rsi
0x180038628  push    rdi
0x180038629  push    r12
0x18003862b  push    r13
0x18003862d  push    r14
0x18003862f  push    r15
0x180038631  mov     rbp, rsp
0x180038634  sub     rsp, 70h
0x180038638  mov     r10, [r8]
0x18003863b  xorps   xmm0, xmm0
0x18003863e  mov     rax, [r8+8]
0x180038642  mov     r14, rdx
0x180038645  mov     r8, [r8+10h]
0x180038649  xor     r12d, r12d
0x18003864c  movzx   edx, word ptr [rdx]
0x18003864f  mov     r15d, 0C0000073h
0x180038655  movups  xmmword ptr [rbp+DomainName2.Length], xmm0
0x180038659  mov     qword ptr [rbp+DomainName2.Length], r10
0x18003865d  movups  [rbp+var_18], xmm0
0x180038661  mov     [rbp+DomainName2.Buffer], rax
0x180038665  movups  xmmword ptr [rbp+Src], xmm0
0x180038669  mov     qword ptr [rbp+var_18], r8
0x18003866d  mov     [rbp+var_50], r10
0x180038671  mov     [rbp+var_48], rax
0x180038675  mov     [rbp+Sid], r8
0x180038679  cmp     [r14+2], dx
0x18003867e  ja      loc_18003883F
0x180038684  add     rdx, 2; uBytes
0x180038688  mov     ecx, 40h ; '@'; uFlags
0x18003868d  call    cs:__imp_LocalAlloc
0x180038694  nop     dword ptr [rax+rax+00h]
0x180038699  mov     rbx, rax
0x18003869c  test    rax, rax
0x18003869f  jz      loc_180038823
0x1800386a5  movzx   r8d, word ptr [r14]; Size
0x1800386a9  mov     rcx, rax; void *
0x1800386ac  mov     rdx, [r14+8]; Src
0x1800386b0  mov     sil, 1
0x1800386b3  call    memcpy_0
0x1800386b8  movzx   ecx, word ptr [r14]
0x1800386bc  shr     rcx, 1
0x1800386bf  mov     [rbx+rcx*2], r12w
0x1800386c4  movzx   edx, word ptr [rbp+Src]
0x1800386c8  mov     r13d, r12d
0x1800386cb  cmp     word ptr [rbp+Src+2], dx
0x1800386cf  ja      loc_18003885C
0x1800386d5  add     rdx, 2; uBytes
0x1800386d9  mov     ecx, 40h ; '@'; uFlags
0x1800386de  call    cs:__imp_LocalAlloc
0x1800386e5  nop     dword ptr [rax+rax+00h]
0x1800386ea  mov     rdi, rax
0x1800386ed  test    rax, rax
0x1800386f0  jz      loc_180038887
0x1800386f6  movzx   r8d, word ptr [rbp+Src]; Size
0x1800386fb  mov     rcx, rax; void *
0x1800386fe  mov     rdx, [rbp+Src+8]; Src
0x180038702  mov     r12b, 1
0x180038705  call    memcpy_0
0x18003870a  movzx   ecx, word ptr [rbp+Src]
0x18003870e  shr     rcx, 1
0x180038711  xor     eax, eax
0x180038713  mov     [rdi+rcx*2], ax
0x180038717  test    r13d, r13d
0x18003871a  js      loc_18003887F
0x180038720  lea     rdx, [rbp+DomainName2]; DomainName2
0x180038724  mov     rcx, r14; DomainName1
0x180038727  call    cs:__imp_RtlEqualDomainName
0x18003872e  nop     dword ptr [rax+rax+00h]
0x180038733  xor     r13d, r13d
0x180038736  test    al, al
0x180038738  jnz     loc_180038877
0x18003873e  mov     rdx, rdi; pName2
0x180038741  mov     rcx, rbx; pName1
0x180038744  call    cs:__imp_DnsNameCompare_W
0x18003874b  nop     dword ptr [rax+rax+00h]
0x180038750  test    eax, eax
0x180038752  jnz     loc_180038877
0x180038758  mov     r14b, r13b
0x18003875b  test    sil, sil
0x18003875e  jz      short loc_18003876F
0x180038760  mov     rcx, rbx; hMem
0x180038763  call    cs:__imp_LocalFree
0x18003876a  nop     dword ptr [rax+rax+00h]
0x18003876f  test    r12b, r12b
0x180038772  jz      short loc_180038783
0x180038774  mov     rcx, rdi; hMem
0x180038777  call    cs:__imp_LocalFree
0x18003877e  nop     dword ptr [rax+rax+00h]
0x180038783  test    r14b, r14b
0x180038786  jz      loc_180038823
0x18003878c  mov     eax, [rbp+arg_0]
0x18003878f  lea     rdx, [rbp+var_50]
0x180038793  mov     rdi, [rbp+arg_20]
0x180038797  mov     rcx, [rbp+arg_18]
0x18003879b  lea     rbx, [rax+rax*2]
0x18003879f  mov     r8, [rdi+8]
0x1800387a3  add     r8, 10h
0x1800387a7  lea     r8, [r8+rbx*8]
0x1800387ab  call    LsapDbLookupAddListReferencedDomains
0x1800387b0  mov     r15d, eax
0x1800387b3  test    eax, eax
0x1800387b5  js      short loc_180038823
0x1800387b7  mov     rax, [rdi+8]
0x1800387bb  mov     dword ptr [rax+rbx*8], 3
0x1800387c2  mov     rcx, [rbp+Sid]; Sid
0x1800387c6  call    cs:__imp_RtlLengthSid
0x1800387cd  nop     dword ptr [rax+rax+00h]
0x1800387d2  mov     edx, eax; uBytes
0x1800387d4  mov     ecx, 40h ; '@'; uFlags
0x1800387d9  mov     esi, eax
0x1800387db  call    cs:__imp_LocalAlloc
0x1800387e2  nop     dword ptr [rax+rax+00h]
0x1800387e7  mov     rcx, [rdi+8]
0x1800387eb  mov     [rcx+rbx*8+8], rax
0x1800387f0  mov     rcx, [rdi+8]
0x1800387f4  mov     rdx, [rcx+rbx*8+8]; DestinationSid
0x1800387f9  test    rdx, rdx
0x1800387fc  jz      loc_180038892
0x180038802  mov     r8, [rbp+Sid]; SourceSid
0x180038806  mov     ecx, esi; DestinationSidLength
0x180038808  call    cs:__imp_RtlCopySid
0x18003880f  nop     dword ptr [rax+rax+00h]
0x180038814  mov     rax, [rbp+arg_28]
0x180038818  mov     r15d, r13d
0x18003881b  inc     dword ptr [rax]
0x18003881d  mov     rax, [rbp+arg_30]
0x180038821  dec     dword ptr [rax]
0x180038823  mov     rbx, [rsp+70h+arg_8]
0x18003882b  mov     eax, r15d
0x18003882e  add     rsp, 70h
0x180038832  pop     r15
0x180038834  pop     r14
0x180038836  pop     r13
0x180038838  pop     r12
0x18003883a  pop     rdi
0x18003883b  pop     rsi
0x18003883c  pop     rbp
0x18003883d  retn
0x18003883f  mov     rbx, [r14+8]
0x180038843  mov     rax, rdx
0x180038846  shr     rax, 1
0x180038849  cmp     [rbx+rax*2], r12w
0x18003884e  jnz     loc_180038684
0x180038854  mov     sil, r12b
0x180038857  jmp     loc_1800386C4
0x18003885c  mov     rdi, [rbp+Src+8]
0x180038860  mov     rax, rdx
0x180038863  shr     rax, 1
0x180038866  xor     ecx, ecx
0x180038868  cmp     [rdi+rax*2], cx
0x18003886c  jnz     loc_1800386D5
0x180038872  jmp     loc_180038717
0x180038877  mov     r14b, 1
0x18003887a  jmp     loc_18003875B
0x18003887f  xor     r13d, r13d
0x180038882  jmp     loc_180038758
0x180038887  mov     r13d, 0C0000017h
0x18003888d  jmp     loc_180038717
0x180038892  mov     r15d, 0C0000017h
0x180038898  jmp     short loc_180038823
```
