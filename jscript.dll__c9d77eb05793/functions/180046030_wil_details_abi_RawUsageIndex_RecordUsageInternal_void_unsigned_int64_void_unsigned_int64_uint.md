# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180046030`
- end: `0x18004623c`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `524`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18004590c`

## callees

- `0x180045a00`
- `0x180046030`
- `0x180046378`
- `0x18004d1a8`
- `0x18005241c`
- `0x18005a394`
- `0x18005a728`
- `0x180094276`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800461d2`
- `msvcrt!memmove_s` at `0x1800461d2`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v10; // rdi
  char v11; // r14
  bool v12; // al
  unsigned int v13; // r12d
  __int64 v14; // r9
  unsigned __int64 v15; // r15
  int v16; // ecx
  unsigned __int8 *InsertionPointOrIncrement; // rax
  unsigned __int64 Size; // r8
  __int64 v20; // rdx
  char v21; // cl
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // r9
  __int16 v26; // [rsp+30h] [rbp-40h] BYREF
  char v27; // [rsp+32h] [rbp-3Eh]
  int v28; // [rsp+34h] [rbp-3Ch]
  unsigned __int16 v29; // [rsp+38h] [rbp-38h]
  void *Buf2[2]; // [rsp+40h] [rbp-30h]
  __int16 v31; // [rsp+50h] [rbp-20h] BYREF
  char v32; // [rsp+52h] [rbp-1Eh]
  unsigned int v33; // [rsp+54h] [rbp-1Ch]
  __int16 v34; // [rsp+58h] [rbp-18h]
  __int64 v35; // [rsp+60h] [rbp-10h]
  void *v36; // [rsp+68h] [rbp-8h]
  unsigned __int8 *v37; // [rsp+B0h] [rbp+40h] BYREF
  void *Buf1; // [rsp+B8h] [rbp+48h]

  Buf1 = a2;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v10 = (unsigned __int8 *)(v6 + 10);
  v26 = *((_WORD *)this + 1);
  v11 = 0;
  v27 = *((_BYTE *)this + 4);
  v37 = v10;
  v28 = 0;
  v29 = 0;
  *(_OWORD *)Buf2 = 0;
  while ( 1 )
  {
    v12 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v26,
            &v37,
            *((unsigned __int8 **)this + 4));
    v13 = a6;
    v14 = 0;
    v15 = a5;
    if ( !v12 )
    {
      v10 = v37;
      *((_QWORD *)this + 4) = v37;
LABEL_17:
      Buf2[1] = Buf1;
      v28 = 1;
      v29 = a3;
      Buf2[0] = 0;
      Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v26);
      goto LABEL_18;
    }
    if ( a3 == v29 )
    {
      v16 = memcmp_0(Buf1, Buf2[1], a3);
      v14 = 0;
    }
    else
    {
      v16 = a3 - v29;
    }
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v26,
                                    v37,
                                    a4,
                                    v15,
                                    v13);
      v14 = 0;
      v37 = InsertionPointOrIncrement;
      v10 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        v11 = 1;
        goto LABEL_14;
      }
      return 1;
    }
    v10 = wil::details_abi::RawUsageIndex::SkipValues(this, (struct wil::details_abi::UsageIndexProperty *)&v26, v37);
    v37 = v10;
  }
  v37 = v10;
LABEL_14:
  Size = 0;
  if ( !v11 )
    goto LABEL_17;
LABEL_18:
  v20 = *((unsigned __int16 *)this + 3);
  v21 = *((_BYTE *)this + 8);
  v31 = v20;
  v32 = v21;
  v33 = v13;
  v34 = v15;
  v35 = v14;
  v36 = a4;
  if ( (_WORD)v20 )
    v22 = v20;
  else
    v22 = (unsigned __int16)v15 + 2LL;
  if ( v21 == 1 )
  {
    v22 += 2;
  }
  else if ( v21 == 2 )
  {
    v22 += 4;
  }
  v23 = *((_QWORD *)this + 5);
  v24 = v22 + Size;
  v25 = *((_QWORD *)this + 4);
  if ( ((v23 - v25) & -(__int64)(v25 < v23)) >= v22 + Size )
  {
    memmove_s(&v10[v24], v23 - v24 - (_QWORD)v10, v10, v25 - (_QWORD)v10);
    *((_QWORD *)this + 4) += v24;
    if ( v11 )
    {
      if ( v27 )
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v26, v28 + 1);
    }
    else
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v26,
        &v37,
        *((unsigned __int8 **)this + 4));
    }
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v31,
      &v37,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180046030  mov     [rsp-38h+arg_10], rbx
0x180046035  mov     [rsp-38h+Buf1], rdx
0x18004603a  push    rbp
0x18004603b  push    rsi
0x18004603c  push    rdi
0x18004603d  push    r12
0x18004603f  push    r13
0x180046041  push    r14
0x180046043  push    r15
0x180046045  mov     rbp, rsp
0x180046048  sub     rsp, 70h
0x18004604c  mov     rdi, [rcx+18h]
0x180046050  mov     rbx, rcx
0x180046053  xor     ecx, ecx
0x180046055  mov     r13, r9
0x180046058  mov     rsi, r8
0x18004605b  test    rdi, rdi
0x18004605e  jz      loc_180046222
0x180046064  movzx   eax, word ptr [rbx+2]
0x180046068  add     rdi, 0Ah
0x18004606c  mov     [rbp+var_40], ax
0x180046070  xorps   xmm0, xmm0
0x180046073  mov     al, [rbx+4]
0x180046076  mov     r14b, cl
0x180046079  mov     [rbp+var_3E], al
0x18004607c  mov     [rbp+arg_0], rdi
0x180046080  mov     [rbp+var_3C], ecx
0x180046083  mov     [rbp+var_38], cx
0x180046087  movdqu  xmmword ptr [rbp+Buf2], xmm0
0x18004608c  mov     r8, [rbx+20h]; unsigned __int8 *
0x180046090  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180046094  lea     rcx, [rbp+var_40]; this
0x180046098  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18004609d  mov     r12d, [rbp+arg_28]
0x1800460a1  xor     r9d, r9d
0x1800460a4  mov     r15, [rbp+arg_20]
0x1800460a8  test    al, al
0x1800460aa  jz      loc_180046132
0x1800460b0  movzx   eax, [rbp+var_38]
0x1800460b4  cmp     rsi, rax
0x1800460b7  jnz     short loc_1800460D0
0x1800460b9  mov     rdx, [rbp+Buf2+8]; Buf2
0x1800460bd  mov     r8, rsi; Size
0x1800460c0  mov     rcx, [rbp+Buf1]; Buf1
0x1800460c4  call    memcmp_0
0x1800460c9  mov     ecx, eax
0x1800460cb  xor     r9d, r9d
0x1800460ce  jmp     short loc_1800460D8
0x1800460d0  movzx   eax, [rbp+var_38]
0x1800460d4  mov     ecx, esi
0x1800460d6  sub     ecx, eax
0x1800460d8  test    ecx, ecx
0x1800460da  js      short loc_180046124
0x1800460dc  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800460e0  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800460e4  mov     rcx, rbx; this
0x1800460e7  jz      short loc_1800460F7
0x1800460e9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800460ee  mov     rdi, rax
0x1800460f1  mov     [rbp+arg_0], rax
0x1800460f5  jmp     short loc_18004608C
0x1800460f7  mov     [rsp+70h+var_48], r12d; unsigned int
0x1800460fc  mov     r9, r13; void *
0x1800460ff  mov     [rsp+70h+var_50], r15; unsigned __int64
0x180046104  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180046109  xor     r9d, r9d
0x18004610c  mov     [rbp+arg_0], rax
0x180046110  mov     rdi, rax
0x180046113  test    rax, rax
0x180046116  jnz     short loc_18004611F
0x180046118  mov     al, 1
0x18004611a  jmp     loc_180046224
0x18004611f  mov     r14b, 1
0x180046122  jmp     short loc_180046128
0x180046124  mov     [rbp+arg_0], rdi
0x180046128  mov     r8, r9
0x18004612b  test    r14b, r14b
0x18004612e  jz      short loc_18004613A
0x180046130  jmp     short loc_18004615D
0x180046132  mov     rdi, [rbp+arg_0]
0x180046136  mov     [rbx+20h], rdi
0x18004613a  mov     rax, [rbp+Buf1]
0x18004613e  lea     rcx, [rbp+var_40]; this
0x180046142  mov     [rbp+Buf2+8], rax
0x180046146  mov     [rbp+var_3C], 1
0x18004614d  mov     [rbp+var_38], si
0x180046151  mov     [rbp+Buf2], r9
0x180046155  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18004615a  mov     r8, rax
0x18004615d  movzx   edx, word ptr [rbx+6]
0x180046161  mov     cl, [rbx+8]
0x180046164  mov     [rbp+var_20], dx
0x180046168  mov     [rbp+var_1E], cl
0x18004616b  mov     [rbp+var_1C], r12d
0x18004616f  mov     [rbp+var_18], r15w
0x180046174  mov     [rbp+var_10], r9
0x180046178  mov     [rbp+var_8], r13
0x18004617c  test    dx, dx
0x18004617f  jnz     short loc_18004618B
0x180046181  movzx   eax, r15w
0x180046185  add     rax, 2
0x180046189  jmp     short loc_18004618E
0x18004618b  mov     rax, rdx
0x18004618e  cmp     cl, 1
0x180046191  jnz     short loc_180046199
0x180046193  add     rax, 2
0x180046197  jmp     short loc_1800461A2
0x180046199  cmp     cl, 2
0x18004619c  jnz     short loc_1800461A2
0x18004619e  add     rax, 4
0x1800461a2  mov     rdx, [rbx+28h]
0x1800461a6  lea     rsi, [rax+r8]
0x1800461aa  mov     r9, [rbx+20h]
0x1800461ae  mov     rcx, rdx
0x1800461b1  sub     rcx, r9
0x1800461b4  cmp     r9, rdx
0x1800461b7  sbb     rax, rax
0x1800461ba  and     rax, rcx
0x1800461bd  cmp     rax, rsi
0x1800461c0  jb      short loc_180046222
0x1800461c2  sub     rdx, rsi
0x1800461c5  lea     rcx, [rsi+rdi]; Destination
0x1800461c9  sub     rdx, rdi; DestinationSize
0x1800461cc  sub     r9, rdi; SourceSize
0x1800461cf  mov     r8, rdi; Source
0x1800461d2  call    cs:__imp_memmove_s
0x1800461d8  add     [rbx+20h], rsi
0x1800461dc  test    r14b, r14b
0x1800461df  jnz     short loc_1800461F4
0x1800461e1  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800461e5  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800461e9  lea     rcx, [rbp+var_40]; this
0x1800461ed  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800461f2  jmp     short loc_180046208
0x1800461f4  cmp     [rbp+var_3E], 0
0x1800461f8  jz      short loc_180046208
0x1800461fa  mov     edx, [rbp+var_3C]
0x1800461fd  lea     rcx, [rbp+var_40]; this
0x180046201  inc     edx; unsigned int
0x180046203  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180046208  mov     r8, [rbx+20h]; unsigned __int8 *
0x18004620c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180046210  lea     rcx, [rbp+var_20]; this
0x180046214  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180046219  mov     byte ptr [rbx+38h], 1
0x18004621d  jmp     loc_180046118
0x180046222  xor     al, al
0x180046224  mov     rbx, [rsp+70h+arg_10]
0x18004622c  add     rsp, 70h
0x180046230  pop     r15
0x180046232  pop     r14
0x180046234  pop     r13
0x180046236  pop     r12
0x180046238  pop     rdi
0x180046239  pop     rsi
0x18004623a  pop     rbp
0x18004623b  retn
```
