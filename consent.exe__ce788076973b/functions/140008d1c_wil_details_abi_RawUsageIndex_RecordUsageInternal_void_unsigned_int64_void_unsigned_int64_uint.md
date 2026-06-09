# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140008d1c`
- end: `0x140008fd1`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `693`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008c20`
- `0x14000fa30`

## callees

- `0x140008d1c`
- `0x140008fe0`
- `0x140009ec0`
- `0x140014dfc`
- `0x14001795c`
- `0x140017c98`
- `0x140017dd0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008dbd`
- `msvcrt!memcpy_s` at `0x140008df6`
- `msvcrt!memcpy_s` at `0x140008e2b`
- `msvcrt!memcpy_s` at `0x140008dbd`
- `msvcrt!memcpy_s` at `0x140008df6`
- `msvcrt!memcpy_s` at `0x140008e2b`
- `msvcrt!memmove_s` at `0x140008f6b`
- `msvcrt!memmove_s` at `0x140008f6b`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v8; // rdi
  char v9; // r8
  unsigned __int8 *v10; // rcx
  unsigned __int64 v11; // r14
  unsigned int v12; // r13d
  unsigned __int64 v13; // r12
  unsigned __int8 *v14; // rsi
  unsigned __int16 v15; // ax
  unsigned __int8 *v16; // r15
  int v17; // eax
  unsigned __int8 *v18; // rax
  void *v19; // rsi
  unsigned __int8 *InsertionPointOrIncrement; // rax
  __int64 v21; // r9
  char v23; // r14
  unsigned __int64 v24; // r8
  unsigned __int64 Size; // rax
  __int64 v26; // rdx
  char v27; // cl
  __int64 v28; // rax
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rsi
  unsigned __int64 v31; // r9
  unsigned __int8 *v32; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int8 *v33; // [rsp+40h] [rbp-41h]
  const void *v34; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int16 v35; // [rsp+50h] [rbp-31h] BYREF
  __int128 v36; // [rsp+58h] [rbp-29h]
  __int16 v37; // [rsp+68h] [rbp-19h] BYREF
  char v38; // [rsp+6Ah] [rbp-17h]
  unsigned int v39; // [rsp+6Ch] [rbp-15h]
  __int16 v40; // [rsp+70h] [rbp-11h]
  __int64 v41; // [rsp+78h] [rbp-9h]
  void *v42; // [rsp+80h] [rbp-1h]
  unsigned __int16 Destination; // [rsp+D8h] [rbp+57h] BYREF
  void *v44; // [rsp+E0h] [rbp+5Fh]
  unsigned __int64 v45; // [rsp+E8h] [rbp+67h]
  void *v46; // [rsp+F0h] [rbp+6Fh]

  v46 = a4;
  v45 = a3;
  v44 = a2;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v8 = (unsigned __int8 *)(v6 + 10);
  v9 = *((_BYTE *)this + 4);
  LOWORD(v34) = *((_WORD *)this + 1);
  v10 = v8;
  BYTE2(v34) = v9;
  v36 = 0;
  HIDWORD(v34) = 0;
  v35 = 0;
  while ( 1 )
  {
    v11 = *((_QWORD *)this + 4);
    v12 = a6;
    v13 = a5;
    v33 = v8;
    v32 = v8;
    if ( v9 == 1 )
    {
      v14 = v10 + 2;
      if ( (unsigned __int64)(v10 + 2) > v11 )
        goto LABEL_22;
      Destination = 0;
      *(_QWORD *)&v36 = v10;
      memcpy_s(&Destination, 2u, v10, 2u);
      HIDWORD(v34) = Destination;
    }
    else if ( v9 == 2 )
    {
      v14 = v10 + 4;
      if ( (unsigned __int64)(v10 + 4) > v11 )
        goto LABEL_22;
      *(_QWORD *)&v36 = v10;
      memcpy_s((char *)&v34 + 4, 4u, v10, 4u);
    }
    else
    {
      v14 = v10;
    }
    v15 = (unsigned __int16)v34;
    v35 = (unsigned __int16)v34;
    if ( !(_WORD)v34 )
    {
      if ( (unsigned __int64)(v14 + 2) > v11 )
        goto LABEL_22;
      memcpy_s(&v35, 2u, v14, 2u);
      v15 = v35;
      v14 += 2;
    }
    v16 = &v14[v15];
    if ( (unsigned __int64)v16 > v11 )
    {
LABEL_22:
      *((_QWORD *)this + 4) = v8;
      goto LABEL_23;
    }
    *((_QWORD *)&v36 + 1) = v14;
    v17 = wil::details_abi::UsageIndexProperty::Compare(&v34, v44, v45);
    if ( v17 < 0 )
    {
      v8 = v33;
      v32 = v33;
LABEL_23:
      v35 = v45;
      v23 = 0;
      *((_QWORD *)&v36 + 1) = v44;
      HIDWORD(v34) = 1;
      *(_QWORD *)&v36 = 0;
      Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v34);
      v19 = v46;
      v24 = Size;
      goto LABEL_24;
    }
    if ( !v17 )
      break;
    v18 = wil::details_abi::RawUsageIndex::SkipValues(this, (struct wil::details_abi::UsageIndexProperty *)&v34, v16);
    v9 = BYTE2(v34);
    v8 = v18;
    v10 = v18;
  }
  v19 = v46;
  InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                this,
                                (struct wil::details_abi::UsageIndexProperty *)&v34,
                                v16,
                                v46,
                                v13,
                                v12);
  v21 = 0;
  v32 = InsertionPointOrIncrement;
  v8 = InsertionPointOrIncrement;
  if ( !InsertionPointOrIncrement )
    return 1;
  v23 = 1;
  v24 = 0;
LABEL_24:
  v26 = *((unsigned __int16 *)this + 3);
  v27 = *((_BYTE *)this + 8);
  v37 = v26;
  v38 = v27;
  v39 = v12;
  v40 = v13;
  v41 = v21;
  v42 = v19;
  if ( (_WORD)v26 )
    v28 = v26;
  else
    v28 = (unsigned __int16)v13 + 2LL;
  if ( v27 == 1 )
  {
    v28 += 2;
  }
  else if ( v27 == 2 )
  {
    v28 += 4;
  }
  v29 = *((_QWORD *)this + 5);
  v30 = v28 + v24;
  v31 = *((_QWORD *)this + 4);
  if ( ((v29 - v31) & -(__int64)(v31 < v29)) >= v28 + v24 )
  {
    memmove_s(&v8[v30], v29 - v30 - (_QWORD)v8, v8, v31 - (_QWORD)v8);
    *((_QWORD *)this + 4) += v30;
    if ( v23 )
    {
      if ( BYTE2(v34) )
        wil::details_abi::UsageIndexProperty::UpdateCount(
          (wil::details_abi::UsageIndexProperty *)&v34,
          HIDWORD(v34) + 1);
    }
    else
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v34,
        &v32,
        *((unsigned __int8 **)this + 4));
    }
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v37,
      &v32,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140008d1c  mov     rax, rsp
0x140008d1f  mov     [rax+20h], r9
0x140008d23  mov     [rax+18h], r8
0x140008d27  mov     [rax+10h], rdx
0x140008d2b  push    rbp
0x140008d2c  push    rbx
0x140008d2d  push    rsi
0x140008d2e  push    rdi
0x140008d2f  push    r12
0x140008d31  push    r13
0x140008d33  push    r14
0x140008d35  push    r15
0x140008d37  lea     rbp, [rax-4Fh]
0x140008d3b  sub     rsp, 88h
0x140008d42  mov     rdi, [rcx+18h]
0x140008d46  xor     r9d, r9d
0x140008d49  mov     rbx, rcx
0x140008d4c  test    rdi, rdi
0x140008d4f  jz      loc_140008FBB
0x140008d55  movzx   eax, word ptr [rcx+2]
0x140008d59  add     rdi, 0Ah
0x140008d5d  mov     r8b, [rcx+4]
0x140008d61  xorps   xmm0, xmm0
0x140008d64  mov     [rbp+47h+var_80], ax
0x140008d68  mov     rcx, rdi
0x140008d6b  mov     [rbp+47h+var_7E], r8b
0x140008d6f  movdqu  [rbp+47h+var_70], xmm0
0x140008d74  mov     [rbp+47h+var_7C], r9d
0x140008d78  mov     [rbp+47h+var_78], r9w
0x140008d7d  mov     r14, [rbx+20h]
0x140008d81  mov     r13d, [rbp+47h+arg_28]
0x140008d85  mov     r12, [rbp+47h+arg_20]
0x140008d89  mov     [rbp+47h+var_88], rdi
0x140008d8d  mov     [rbp+47h+var_90], rdi
0x140008d91  cmp     r8b, 1
0x140008d95  jnz     short loc_140008DCF
0x140008d97  lea     rsi, [rcx+2]
0x140008d9b  cmp     rsi, r14
0x140008d9e  ja      loc_140008EC4
0x140008da4  mov     [rbp+47h+Destination], r9w
0x140008da9  mov     r8, rcx; Source
0x140008dac  mov     r9d, 2; SourceSize
0x140008db2  mov     qword ptr [rbp+47h+var_70], rcx
0x140008db6  mov     edx, r9d; DestinationSize
0x140008db9  lea     rcx, [rbp+47h+Destination]; Destination
0x140008dbd  call    cs:__imp_memcpy_s
0x140008dc3  movzx   eax, [rbp+47h+Destination]
0x140008dc7  mov     [rbp+47h+var_7C], eax
0x140008dca  xor     r9d, r9d
0x140008dcd  jmp     short loc_140008E01
0x140008dcf  cmp     r8b, 2
0x140008dd3  jnz     short loc_140008DFE
0x140008dd5  lea     rsi, [rcx+4]
0x140008dd9  cmp     rsi, r14
0x140008ddc  ja      loc_140008EC4
0x140008de2  mov     r9d, 4; SourceSize
0x140008de8  mov     qword ptr [rbp+47h+var_70], rcx
0x140008dec  mov     r8, rcx; Source
0x140008def  mov     edx, r9d; DestinationSize
0x140008df2  lea     rcx, [rbp+47h+var_7C]; Destination
0x140008df6  call    cs:__imp_memcpy_s
0x140008dfc  jmp     short loc_140008DCA
0x140008dfe  mov     rsi, rcx
0x140008e01  movzx   eax, [rbp+47h+var_80]
0x140008e05  mov     [rbp+47h+var_78], ax
0x140008e09  test    ax, ax
0x140008e0c  jnz     short loc_140008E3B
0x140008e0e  lea     r15, [rsi+2]
0x140008e12  cmp     r15, r14
0x140008e15  ja      loc_140008EC4
0x140008e1b  mov     r9d, 2; SourceSize
0x140008e21  lea     rcx, [rbp+47h+var_78]; Destination
0x140008e25  mov     edx, r9d; DestinationSize
0x140008e28  mov     r8, rsi; Source
0x140008e2b  call    cs:__imp_memcpy_s
0x140008e31  movzx   eax, [rbp+47h+var_78]
0x140008e35  xor     r9d, r9d
0x140008e38  mov     rsi, r15
0x140008e3b  movzx   r15d, ax
0x140008e3f  add     r15, rsi
0x140008e42  cmp     r15, r14
0x140008e45  ja      short loc_140008EC4
0x140008e47  mov     r8, [rbp+47h+arg_10]; unsigned __int64
0x140008e4b  lea     rcx, [rbp+47h+var_80]; this
0x140008e4f  mov     rdx, [rbp+47h+arg_8]; void *
0x140008e53  mov     qword ptr [rbp+47h+var_70+8], rsi
0x140008e57  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x140008e5c  xor     r9d, r9d
0x140008e5f  test    eax, eax
0x140008e61  js      short loc_140008EBA
0x140008e63  mov     r8, r15; unsigned __int8 *
0x140008e66  lea     rdx, [rbp+47h+var_80]; struct wil::details_abi::UsageIndexProperty *
0x140008e6a  mov     rcx, rbx; this
0x140008e6d  jz      short loc_140008E86
0x140008e6f  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x140008e74  mov     r8b, [rbp+47h+var_7E]
0x140008e78  mov     rdi, rax
0x140008e7b  mov     rcx, rax
0x140008e7e  xor     r9d, r9d
0x140008e81  jmp     loc_140008D7D
0x140008e86  mov     rsi, [rbp+47h+arg_18]
0x140008e8a  mov     r9, rsi; void *
0x140008e8d  mov     [rsp+28h], r13d; unsigned int
0x140008e92  mov     [rsp+0C0h+var_A0], r12; unsigned __int64
0x140008e97  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140008e9c  xor     r9d, r9d
0x140008e9f  mov     [rbp+47h+var_90], rax
0x140008ea3  mov     rdi, rax
0x140008ea6  test    rax, rax
0x140008ea9  jnz     short loc_140008EB2
0x140008eab  mov     al, 1
0x140008ead  jmp     loc_140008FBD
0x140008eb2  mov     r14b, 1
0x140008eb5  mov     r8, r9
0x140008eb8  jmp     short loc_140008EF6
0x140008eba  mov     rdi, [rbp+47h+var_88]
0x140008ebe  mov     [rbp+47h+var_90], rdi
0x140008ec2  jmp     short loc_140008EC8
0x140008ec4  mov     [rbx+20h], rdi
0x140008ec8  mov     rax, [rbp+47h+arg_10]
0x140008ecc  lea     rcx, [rbp+47h+var_80]; this
0x140008ed0  mov     [rbp+47h+var_78], ax
0x140008ed4  mov     r14b, r9b
0x140008ed7  mov     rax, [rbp+47h+arg_8]
0x140008edb  mov     qword ptr [rbp+47h+var_70+8], rax
0x140008edf  mov     [rbp+47h+var_7C], 1
0x140008ee6  mov     qword ptr [rbp+47h+var_70], r9
0x140008eea  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140008eef  mov     rsi, [rbp+47h+arg_18]
0x140008ef3  mov     r8, rax
0x140008ef6  movzx   edx, word ptr [rbx+6]
0x140008efa  mov     cl, [rbx+8]
0x140008efd  mov     [rbp+47h+var_60], dx
0x140008f01  mov     [rbp+47h+var_5E], cl
0x140008f04  mov     [rbp+47h+var_5C], r13d
0x140008f08  mov     [rbp+47h+var_58], r12w
0x140008f0d  mov     [rbp+47h+var_50], r9
0x140008f11  mov     [rbp+47h+var_48], rsi
0x140008f15  test    dx, dx
0x140008f18  jnz     short loc_140008F24
0x140008f1a  movzx   eax, r12w
0x140008f1e  add     rax, 2
0x140008f22  jmp     short loc_140008F27
0x140008f24  mov     rax, rdx
0x140008f27  cmp     cl, 1
0x140008f2a  jnz     short loc_140008F32
0x140008f2c  add     rax, 2
0x140008f30  jmp     short loc_140008F3B
0x140008f32  cmp     cl, 2
0x140008f35  jnz     short loc_140008F3B
0x140008f37  add     rax, 4
0x140008f3b  mov     rdx, [rbx+28h]
0x140008f3f  lea     rsi, [rax+r8]
0x140008f43  mov     r9, [rbx+20h]
0x140008f47  mov     rcx, rdx
0x140008f4a  sub     rcx, r9
0x140008f4d  cmp     r9, rdx
0x140008f50  sbb     rax, rax
0x140008f53  and     rax, rcx
0x140008f56  cmp     rax, rsi
0x140008f59  jb      short loc_140008FBB
0x140008f5b  sub     rdx, rsi
0x140008f5e  lea     rcx, [rsi+rdi]; Destination
0x140008f62  sub     rdx, rdi; DestinationSize
0x140008f65  sub     r9, rdi; SourceSize
0x140008f68  mov     r8, rdi; Source
0x140008f6b  call    cs:__imp_memmove_s
0x140008f71  add     [rbx+20h], rsi
0x140008f75  test    r14b, r14b
0x140008f78  jnz     short loc_140008F8D
0x140008f7a  mov     r8, [rbx+20h]; unsigned __int8 *
0x140008f7e  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x140008f82  lea     rcx, [rbp+47h+var_80]; this
0x140008f86  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140008f8b  jmp     short loc_140008FA1
0x140008f8d  cmp     [rbp+47h+var_7E], 0
0x140008f91  jz      short loc_140008FA1
0x140008f93  mov     edx, [rbp+47h+var_7C]
0x140008f96  lea     rcx, [rbp+47h+var_80]; this
0x140008f9a  inc     edx; unsigned int
0x140008f9c  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x140008fa1  mov     r8, [rbx+20h]; unsigned __int8 *
0x140008fa5  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x140008fa9  lea     rcx, [rbp+47h+var_60]; this
0x140008fad  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140008fb2  mov     byte ptr [rbx+38h], 1
0x140008fb6  jmp     loc_140008EAB
0x140008fbb  xor     al, al
0x140008fbd  add     rsp, 88h
0x140008fc4  pop     r15
0x140008fc6  pop     r14
0x140008fc8  pop     r13
0x140008fca  pop     r12
0x140008fcc  pop     rdi
0x140008fcd  pop     rsi
0x140008fce  pop     rbx
0x140008fcf  pop     rbp
0x140008fd0  retn
```
