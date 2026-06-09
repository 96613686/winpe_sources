# LsaDbpDsForestProcessTrustBlob(_LSAPDS_FOREST_TRUST_BLOB *,_LSAPR_TREE_TRUST_INFO *,_LIST_ENTRY *,_LIST_ENTRY *,_UNICODE_STRING *,_LSAPR_TREE_TRUST_INFO * *)

- ea: `0x18002c898`
- end: `0x18002cb4c`
- name: `?LsaDbpDsForestProcessTrustBlob@@YAJPEAU_LSAPDS_FOREST_TRUST_BLOB@@PEAU_LSAPR_TREE_TRUST_INFO@@PEAU_LIST_ENTRY@@2PEAU_UNICODE_STRING@@PEAPEAU2@@Z`
- size: `692`
- prototype: `__int64 __fastcall(struct _LSAPDS_FOREST_TRUST_BLOB *, struct _LSAPR_TREE_TRUST_INFO *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, PCUNICODE_STRING String2, struct _LSAPR_TREE_TRUST_INFO **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c40c`
- `0x18002c898`

## callees

- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x18002c898`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002c9b7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002c9b7`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002ca36`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002ca36`
- `ntdll!RtlEqualUnicodeString` at `0x18002ca84`
- `ntdll!RtlEqualUnicodeString` at `0x18002ca84`

## pseudocode

```c
__int64 __fastcall LsaDbpDsForestProcessTrustBlob(
        struct _LSAPDS_FOREST_TRUST_BLOB *a1,
        struct _LSAPR_TREE_TRUST_INFO *a2,
        struct _LIST_ENTRY *a3,
        struct _LIST_ENTRY *a4,
        PCUNICODE_STRING String2,
        struct _LSAPR_TREE_TRUST_INFO **a6)
{
  bool v10; // zf
  __int128 v11; // xmm0
  __int64 v12; // rcx
  struct _LSAPDS_FOREST_TRUST_BLOB **v13; // rax
  struct _LIST_ENTRY *Blink; // rax
  __int64 v15; // r15
  struct _LIST_ENTRY *Flink; // rdi
  char *v17; // rax
  struct _LIST_ENTRY *v18; // r13
  struct _LIST_ENTRY *v19; // rax
  struct _LIST_ENTRY *v20; // rcx
  struct _LSAPDS_FOREST_TRUST_BLOB *v21; // rax
  void *LsaHeap; // rax
  int v23; // ebx
  struct _LSAPDS_FOREST_TRUST_BLOB *v24; // rbx
  __int64 v25; // rdi
  struct _LSAPDS_FOREST_TRUST_BLOB *v26; // r13
  struct _LIST_ENTRY *v27; // rax
  __int64 v28; // rcx
  struct _LSAPDS_FOREST_TRUST_BLOB **v29; // rdx
  struct _LIST_ENTRY *v30; // rcx
  struct _LSAPDS_FOREST_TRUST_BLOB *v32[2]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)v32 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6c9a2cf316993f904ac0f2d2afcb3e00_Traceguids);
  v32[1] = (struct _LSAPDS_FOREST_TRUST_BLOB *)v32;
  v32[0] = (struct _LSAPDS_FOREST_TRUST_BLOB *)v32;
  memset_0(a2, 0, 0x48u);
  *(_OWORD *)a2 = *((_OWORD *)a1 + 1);
  *((_QWORD *)a1 + 3) = 0;
  *((_OWORD *)a2 + 1) = *((_OWORD *)a1 + 2);
  v10 = *((_BYTE *)a1 + 105) == 0;
  *((_QWORD *)a1 + 5) = 0;
  if ( !v10 || *((_BYTE *)a1 + 104) )
    *((_DWORD *)a2 + 14) |= 1u;
  if ( *((_BYTE *)a1 + 106) )
  {
    v11 = *((_OWORD *)a1 + 5);
    *((_DWORD *)a2 + 14) |= 2u;
    *((_OWORD *)a2 + 2) = v11;
  }
  *((_QWORD *)a2 + 6) = *((_QWORD *)a1 + 12);
  *((_QWORD *)a1 + 12) = 0;
  v12 = *(_QWORD *)a1;
  if ( *(struct _LSAPDS_FOREST_TRUST_BLOB **)(*(_QWORD *)a1 + 8LL) != a1
    || (v13 = (struct _LSAPDS_FOREST_TRUST_BLOB **)*((_QWORD *)a1 + 1), *v13 != a1)
    || (*v13 = (struct _LSAPDS_FOREST_TRUST_BLOB *)v12, *(_QWORD *)(v12 + 8) = v13,
                                                        Blink = a4->Blink,
                                                        Blink->Flink != a4) )
  {
LABEL_39:
    __fastfail(3u);
  }
  *(_QWORD *)a1 = a4;
  v15 = 0;
  *((_QWORD *)a1 + 1) = Blink;
  Blink->Flink = (struct _LIST_ENTRY *)a1;
  a4->Blink = (struct _LIST_ENTRY *)a1;
  Flink = a3->Flink;
  if ( a3->Flink == a3 )
    goto LABEL_30;
  v17 = (char *)a1 + 48;
  do
  {
    v18 = Flink->Flink;
    if ( RtlCompareMemory(v17, &Flink[4], 0x10u) == 16 || *((_BYTE *)a1 + 104) && BYTE1(Flink[6].Blink) )
    {
      v19 = Flink->Flink;
      if ( Flink->Flink->Blink != Flink )
        goto LABEL_39;
      v20 = Flink->Blink;
      if ( v20->Flink != Flink )
        goto LABEL_39;
      v20->Flink = v19;
      v19->Blink = v20;
      v21 = v32[1];
      if ( *(struct _LSAPDS_FOREST_TRUST_BLOB ***)v32[1] != v32 )
        goto LABEL_39;
      Flink->Blink = (struct _LIST_ENTRY *)v32[1];
      Flink->Flink = (struct _LIST_ENTRY *)v32;
      v15 = (unsigned int)(v15 + 1);
      *(_QWORD *)v21 = Flink;
      v32[1] = (struct _LSAPDS_FOREST_TRUST_BLOB *)Flink;
    }
    v17 = (char *)a1 + 48;
    Flink = v18;
  }
  while ( v18 != a3 );
  if ( !(_DWORD)v15 )
  {
LABEL_30:
    v23 = 0;
    goto LABEL_35;
  }
  LsaHeap = (void *)LsapAllocateLsaHeap(72 * v15);
  *((_QWORD *)a2 + 8) = LsaHeap;
  if ( !LsaHeap )
  {
    v23 = -1073741670;
    goto LABEL_35;
  }
  *((_DWORD *)a2 + 15) = v15;
  memset_0(LsaHeap, 0, 72 * v15);
  v24 = v32[0];
  v25 = 0;
  while ( 1 )
  {
    v26 = *(struct _LSAPDS_FOREST_TRUST_BLOB **)v24;
    if ( !*a6 && RtlEqualUnicodeString((PCUNICODE_STRING)v24 + 1, String2, 1u) )
      *a6 = a2;
    v23 = LsaDbpDsForestProcessTrustBlob(
            v24,
            (struct _LSAPR_TREE_TRUST_INFO *)(*((_QWORD *)a2 + 8) + 72 * v25),
            a3,
            a4,
            String2,
            a6);
    if ( v23 < 0 )
      break;
    v25 = (unsigned int)(v25 + 1);
    v24 = v26;
    if ( (unsigned int)v25 >= (unsigned int)v15 )
      goto LABEL_30;
  }
LABEL_35:
  while ( (struct _LSAPDS_FOREST_TRUST_BLOB **)v32[0] != v32 )
  {
    v27 = (struct _LIST_ENTRY *)v32[0];
    v28 = *(_QWORD *)v32[0];
    if ( *(struct _LSAPDS_FOREST_TRUST_BLOB **)(*(_QWORD *)v32[0] + 8LL) != v32[0] )
      goto LABEL_39;
    v29 = (struct _LSAPDS_FOREST_TRUST_BLOB **)*((_QWORD *)v32[0] + 1);
    if ( *v29 != v32[0] )
      goto LABEL_39;
    *v29 = (struct _LSAPDS_FOREST_TRUST_BLOB *)v28;
    *(_QWORD *)(v28 + 8) = v29;
    v30 = a4->Blink;
    if ( v30->Flink != a4 )
      goto LABEL_39;
    v27->Flink = a4;
    v27->Blink = v30;
    v30->Flink = v27;
    a4->Blink = v27;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_6c9a2cf316993f904ac0f2d2afcb3e00_Traceguids,
      (unsigned int)v23);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18002c898  mov     [rsp-40h+arg_10], r8
0x18002c89d  push    rbp
0x18002c89e  push    rbx
0x18002c89f  push    rsi
0x18002c8a0  push    rdi
0x18002c8a1  push    r12
0x18002c8a3  push    r13
0x18002c8a5  push    r14
0x18002c8a7  push    r15
0x18002c8a9  mov     rbp, rsp
0x18002c8ac  sub     rsp, 48h
0x18002c8b0  xorps   xmm0, xmm0
0x18002c8b3  mov     r14, r9
0x18002c8b6  movups  xmmword ptr [rbp+var_18], xmm0
0x18002c8ba  mov     r12, r8
0x18002c8bd  mov     rsi, rdx
0x18002c8c0  mov     rbx, rcx
0x18002c8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8ca  test    byte ptr [rcx+1Ch], 8
0x18002c8ce  jz      short loc_18002C8E5
0x18002c8d0  mov     rcx, [rcx+10h]
0x18002c8d4  lea     r8, WPP_6c9a2cf316993f904ac0f2d2afcb3e00_Traceguids
0x18002c8db  mov     edx, 11h
0x18002c8e0  call    WPP_SF_
0x18002c8e5  xor     edx, edx; Val
0x18002c8e7  lea     rax, [rbp+var_18]
0x18002c8eb  mov     [rbp+var_18+8], rax
0x18002c8ef  mov     rcx, rsi; void *
0x18002c8f2  lea     rax, [rbp+var_18]
0x18002c8f6  mov     [rbp+var_18], rax
0x18002c8fa  lea     r8d, [rdx+48h]; Size
0x18002c8fe  call    memset_0
0x18002c903  movups  xmm0, xmmword ptr [rbx+10h]
0x18002c907  movdqu  xmmword ptr [rsi], xmm0
0x18002c90b  mov     qword ptr [rbx+18h], 0
0x18002c913  movups  xmm0, xmmword ptr [rbx+20h]
0x18002c917  movdqu  xmmword ptr [rsi+10h], xmm0
0x18002c91c  cmp     byte ptr [rbx+69h], 0
0x18002c920  mov     qword ptr [rbx+28h], 0
0x18002c928  jnz     short loc_18002C930
0x18002c92a  cmp     byte ptr [rbx+68h], 0
0x18002c92e  jz      short loc_18002C934
0x18002c930  or      dword ptr [rsi+38h], 1
0x18002c934  cmp     byte ptr [rbx+6Ah], 0
0x18002c938  jz      short loc_18002C947
0x18002c93a  movups  xmm0, xmmword ptr [rbx+50h]
0x18002c93e  or      dword ptr [rsi+38h], 2
0x18002c942  movdqu  xmmword ptr [rsi+20h], xmm0
0x18002c947  mov     rax, [rbx+60h]
0x18002c94b  mov     [rsi+30h], rax
0x18002c94f  mov     qword ptr [rbx+60h], 0
0x18002c957  mov     rcx, [rbx]
0x18002c95a  cmp     [rcx+8], rbx
0x18002c95e  jnz     loc_18002CB45
0x18002c964  mov     rax, [rbx+8]
0x18002c968  cmp     [rax], rbx
0x18002c96b  jnz     loc_18002CB45
0x18002c971  mov     [rax], rcx
0x18002c974  mov     [rcx+8], rax
0x18002c978  mov     rax, [r14+8]
0x18002c97c  cmp     [rax], r14
0x18002c97f  jnz     loc_18002CB45
0x18002c985  mov     [rbx], r14
0x18002c988  xor     r15d, r15d
0x18002c98b  mov     [rbx+8], rax
0x18002c98f  mov     [rax], rbx
0x18002c992  mov     [r14+8], rbx
0x18002c996  mov     rdi, [r12]
0x18002c99a  cmp     rdi, r12
0x18002c99d  jz      loc_18002CACB
0x18002c9a3  lea     rax, [rbx+30h]
0x18002c9a7  mov     r13, [rdi]
0x18002c9aa  lea     rdx, [rdi+40h]; Source2
0x18002c9ae  mov     r8d, 10h; Length
0x18002c9b4  mov     rcx, rax; Source1
0x18002c9b7  call    cs:__imp_RtlCompareMemory
0x18002c9bd  cmp     rax, 10h
0x18002c9c1  jz      short loc_18002C9CF
0x18002c9c3  cmp     byte ptr [rbx+68h], 0
0x18002c9c7  jz      short loc_18002CA16
0x18002c9c9  cmp     byte ptr [rdi+69h], 0
0x18002c9cd  jz      short loc_18002CA16
0x18002c9cf  mov     rax, [rdi]
0x18002c9d2  cmp     [rax+8], rdi
0x18002c9d6  jnz     loc_18002CB45
0x18002c9dc  mov     rcx, [rdi+8]
0x18002c9e0  cmp     [rcx], rdi
0x18002c9e3  jnz     loc_18002CB45
0x18002c9e9  mov     [rcx], rax
0x18002c9ec  mov     [rax+8], rcx
0x18002c9f0  lea     rcx, [rbp+var_18]
0x18002c9f4  mov     rax, [rbp+var_18+8]
0x18002c9f8  cmp     [rax], rcx
0x18002c9fb  jnz     loc_18002CB45
0x18002ca01  mov     [rdi+8], rax
0x18002ca05  lea     rcx, [rbp+var_18]
0x18002ca09  mov     [rdi], rcx
0x18002ca0c  inc     r15d
0x18002ca0f  mov     [rax], rdi
0x18002ca12  mov     [rbp+var_18+8], rdi
0x18002ca16  lea     rax, [rbx+30h]
0x18002ca1a  mov     rdi, r13
0x18002ca1d  cmp     r13, r12
0x18002ca20  jnz     short loc_18002C9A7
0x18002ca22  test    r15d, r15d
0x18002ca25  jz      loc_18002CACB
0x18002ca2b  lea     rbx, [r15+r15*8]
0x18002ca2f  shl     rbx, 3
0x18002ca33  mov     rcx, rbx
0x18002ca36  call    cs:__imp_LsapAllocateLsaHeap
0x18002ca3c  mov     [rsi+40h], rax
0x18002ca40  test    rax, rax
0x18002ca43  jnz     short loc_18002CA4F
0x18002ca45  mov     ebx, 0C000009Ah
0x18002ca4a  jmp     loc_18002CB03
0x18002ca4f  mov     r8, rbx; Size
0x18002ca52  mov     [rsi+3Ch], r15d
0x18002ca56  xor     edx, edx; Val
0x18002ca58  mov     rcx, rax; void *
0x18002ca5b  call    memset_0
0x18002ca60  mov     rbx, [rbp+var_18]
0x18002ca64  xor     edi, edi
0x18002ca66  test    r15d, r15d
0x18002ca69  jz      short loc_18002CACB
0x18002ca6b  mov     r12, [rbp+arg_28]
0x18002ca6f  cmp     qword ptr [r12], 0
0x18002ca74  mov     r13, [rbx]
0x18002ca77  jnz     short loc_18002CA92
0x18002ca79  mov     rdx, [rbp+String2]; String2
0x18002ca7d  lea     rcx, [rbx+10h]; String1
0x18002ca81  mov     r8b, 1; CaseInsensitive
0x18002ca84  call    cs:__imp_RtlEqualUnicodeString
0x18002ca8a  test    al, al
0x18002ca8c  jz      short loc_18002CA92
0x18002ca8e  mov     [r12], rsi
0x18002ca92  mov     rax, [rsi+40h]
0x18002ca96  lea     rdx, [rdi+rdi*8]
0x18002ca9a  mov     r8, [rbp+arg_10]; struct _LIST_ENTRY *
0x18002ca9e  mov     r9, r14; struct _LIST_ENTRY *
0x18002caa1  mov     [rsp+48h+var_20], r12; struct _LSAPR_TREE_TRUST_INFO **
0x18002caa6  mov     rcx, rbx; struct _LSAPDS_FOREST_TRUST_BLOB *
0x18002caa9  lea     rdx, [rax+rdx*8]; struct _LSAPR_TREE_TRUST_INFO *
0x18002caad  mov     rax, [rbp+String2]
0x18002cab1  mov     [rsp+48h+var_28], rax; String2
0x18002cab6  call    ?LsaDbpDsForestProcessTrustBlob@@YAJPEAU_LSAPDS_FOREST_TRUST_BLOB@@PEAU_LSAPR_TREE_TRUST_INFO@@PEAU_LIST_ENTRY@@2PEAU_UNICODE_STRING@@PEAPEAU2@@Z; LsaDbpDsForestProcessTrustBlob(_LSAPDS_FOREST_TRUST_BLOB *,_LSAPR_TREE_TRUST_INFO *,_LIST_ENTRY *,_LIST_ENTRY *,_UNICODE_STRING *,_LSAPR_TREE_TRUST_INFO * *)
0x18002cabb  mov     ebx, eax
0x18002cabd  test    eax, eax
0x18002cabf  js      short loc_18002CB03
0x18002cac1  inc     edi
0x18002cac3  mov     rbx, r13
0x18002cac6  cmp     edi, r15d
0x18002cac9  jb      short loc_18002CA6F
0x18002cacb  xor     ebx, ebx
0x18002cacd  jmp     short loc_18002CB03
0x18002cacf  mov     rax, [rbp+var_18]
0x18002cad3  mov     rcx, [rax]
0x18002cad6  cmp     [rcx+8], rax
0x18002cada  jnz     short loc_18002CB45
0x18002cadc  mov     rdx, [rax+8]
0x18002cae0  cmp     [rdx], rax
0x18002cae3  jnz     short loc_18002CB45
0x18002cae5  mov     [rdx], rcx
0x18002cae8  mov     [rcx+8], rdx
0x18002caec  mov     rcx, [r14+8]
0x18002caf0  cmp     [rcx], r14
0x18002caf3  jnz     short loc_18002CB45
0x18002caf5  mov     [rax], r14
0x18002caf8  mov     [rax+8], rcx
0x18002cafc  mov     [rcx], rax
0x18002caff  mov     [r14+8], rax
0x18002cb03  lea     rax, [rbp+var_18]
0x18002cb07  cmp     [rbp+var_18], rax
0x18002cb0b  jnz     short loc_18002CACF
0x18002cb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb14  test    byte ptr [rcx+1Ch], 8
0x18002cb18  jz      short loc_18002CB32
0x18002cb1a  mov     rcx, [rcx+10h]
0x18002cb1e  lea     r8, WPP_6c9a2cf316993f904ac0f2d2afcb3e00_Traceguids
0x18002cb25  mov     edx, 12h
0x18002cb2a  mov     r9d, ebx
0x18002cb2d  call    WPP_SF_d
0x18002cb32  mov     eax, ebx
0x18002cb34  add     rsp, 48h
0x18002cb38  pop     r15
0x18002cb3a  pop     r14
0x18002cb3c  pop     r13
0x18002cb3e  pop     r12
0x18002cb40  pop     rdi
0x18002cb41  pop     rsi
0x18002cb42  pop     rbx
0x18002cb43  pop     rbp
0x18002cb44  retn
0x18002cb45  mov     ecx, 3
0x18002cb4a  int     29h; Win8: RtlFailFast(ecx)
```
