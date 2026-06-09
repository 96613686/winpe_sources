# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001b170`
- end: `0x18001b34a`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b07c`

## callees

- `0x18001b170`
- `0x180021348`
- `0x18002160c`
- `0x180021ee8`
- `0x180022d1c`
- `0x180023930`
- `0x180023e44`
- `0x1800241c8`

## import_xrefs

- `ntdll!memmove_s` at `0x18001b2e0`
- `ntdll!memmove_s` at `0x18001b2e0`

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
  char v11; // si
  bool v12; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r13
  int v15; // eax
  unsigned __int64 Size; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  const void *v22; // [rsp+30h] [rbp-40h] BYREF
  __int16 v23; // [rsp+38h] [rbp-38h]
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int16 v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+52h] [rbp-1Eh]
  unsigned int v27; // [rsp+54h] [rbp-1Ch]
  __int16 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  void *v30; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v32; // [rsp+C8h] [rbp+58h]

  v32 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    LOWORD(v22) = *((_WORD *)this + 1);
    BYTE2(v22) = *((_BYTE *)this + 4);
    v23 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    HIDWORD(v22) = 0;
    v24 = 0;
    while ( 1 )
    {
      v12 = wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v22,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4));
      v13 = a6;
      v14 = a5;
      if ( !v12 )
      {
        v10 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v15 = wil::details_abi::UsageIndexProperty::Compare(&v22, a2, a3);
      if ( v15 < 0 )
      {
        InsertionPointOrIncrement = v10;
        goto LABEL_11;
      }
      if ( !v15 )
        break;
      v10 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v22,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v10;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v22,
                                  InsertionPointOrIncrement,
                                  v32,
                                  v14,
                                  v13);
    v10 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v11 = 1;
LABEL_11:
    if ( v11 )
      goto LABEL_15;
LABEL_14:
    HIDWORD(v22) = 1;
    v23 = a3;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v25 = *((_WORD *)this + 3);
    v26 = *((_BYTE *)this + 8);
    v27 = v13;
    v28 = v14;
    v29 = 0;
    v30 = v32;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v25);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( BYTE2(v22) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v22,
            HIDWORD(v22) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v25,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b170  mov     [rsp-38h+arg_8], rbx
0x18001b175  mov     [rsp-38h+arg_18], r9
0x18001b17a  push    rbp
0x18001b17b  push    rsi
0x18001b17c  push    rdi
0x18001b17d  push    r12
0x18001b17f  push    r13
0x18001b181  push    r14
0x18001b183  push    r15
0x18001b185  mov     rbp, rsp
0x18001b188  sub     rsp, 70h
0x18001b18c  mov     rdi, [rcx+18h]
0x18001b190  mov     r14, r8
0x18001b193  mov     r15, rdx
0x18001b196  mov     rbx, rcx
0x18001b199  test    rdi, rdi
0x18001b19c  jz      loc_18001B330
0x18001b1a2  movzx   eax, word ptr [rcx+2]
0x18001b1a6  add     rdi, 0Ah
0x18001b1aa  mov     [rbp+var_40], ax
0x18001b1ae  xorps   xmm0, xmm0
0x18001b1b1  mov     al, [rcx+4]
0x18001b1b4  mov     [rbp+var_3E], al
0x18001b1b7  xor     eax, eax
0x18001b1b9  mov     [rbp+var_38], ax
0x18001b1bd  xor     sil, sil
0x18001b1c0  mov     [rbp+arg_0], rdi
0x18001b1c4  mov     [rbp+var_3C], 0
0x18001b1cb  movdqu  [rbp+var_30], xmm0
0x18001b1d0  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b1d4  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001b1d8  lea     rcx, [rbp+var_40]; this
0x18001b1dc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001b1e1  mov     r12d, [rbp+arg_28]
0x18001b1e5  mov     r13, [rbp+arg_20]
0x18001b1e9  test    al, al
0x18001b1eb  jz      short loc_18001B254
0x18001b1ed  mov     r8, r14; unsigned __int64
0x18001b1f0  lea     rcx, [rbp+var_40]; this
0x18001b1f4  mov     rdx, r15; void *
0x18001b1f7  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001b1fc  test    eax, eax
0x18001b1fe  js      short loc_18001B246
0x18001b200  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001b204  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001b208  mov     rcx, rbx; this
0x18001b20b  jz      short loc_18001B21B
0x18001b20d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001b212  mov     rdi, rax
0x18001b215  mov     [rbp+arg_0], rax
0x18001b219  jmp     short loc_18001B1D0
0x18001b21b  mov     r9, [rbp+arg_18]; void *
0x18001b21f  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001b224  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001b229  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001b22e  mov     [rbp+arg_0], rax
0x18001b232  mov     rdi, rax
0x18001b235  test    rax, rax
0x18001b238  jnz     short loc_18001B241
0x18001b23a  mov     al, 1
0x18001b23c  jmp     loc_18001B332
0x18001b241  mov     sil, 1
0x18001b244  jmp     short loc_18001B24A
0x18001b246  mov     [rbp+arg_0], rdi
0x18001b24a  xor     r8d, r8d
0x18001b24d  test    sil, sil
0x18001b250  jnz     short loc_18001B280
0x18001b252  jmp     short loc_18001B25C
0x18001b254  mov     rdi, [rbp+arg_0]
0x18001b258  mov     [rbx+20h], rdi
0x18001b25c  lea     rcx, [rbp+var_40]; this
0x18001b260  mov     [rbp+var_3C], 1
0x18001b267  mov     [rbp+var_38], r14w
0x18001b26c  mov     qword ptr [rbp+var_30], 0
0x18001b274  mov     qword ptr [rbp+var_30+8], r15
0x18001b278  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001b27d  mov     r8, rax
0x18001b280  movzx   ecx, word ptr [rbx+6]
0x18001b284  mov     rax, [rbp+arg_18]
0x18001b288  mov     [rbp+var_20], cx
0x18001b28c  mov     cl, [rbx+8]
0x18001b28f  mov     [rbp+var_1E], cl
0x18001b292  lea     rcx, [rbp+var_20]; this
0x18001b296  mov     [rbp+var_1C], r12d
0x18001b29a  mov     [rbp+var_18], r13w
0x18001b29f  mov     [rbp+var_10], 0
0x18001b2a7  mov     [rbp+var_8], rax
0x18001b2ab  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001b2b0  mov     rdx, [rbx+28h]
0x18001b2b4  mov     r9, [rbx+20h]
0x18001b2b8  mov     rcx, rdx
0x18001b2bb  sub     rcx, r9
0x18001b2be  lea     r14, [rax+r8]
0x18001b2c2  cmp     r9, rdx
0x18001b2c5  sbb     rax, rax
0x18001b2c8  and     rax, rcx
0x18001b2cb  cmp     rax, r14
0x18001b2ce  jb      short loc_18001B330
0x18001b2d0  sub     rdx, r14
0x18001b2d3  lea     rcx, [r14+rdi]; Destination
0x18001b2d7  sub     rdx, rdi; DestinationSize
0x18001b2da  sub     r9, rdi; SourceSize
0x18001b2dd  mov     r8, rdi; Source
0x18001b2e0  call    cs:__imp_memmove_s
0x18001b2e6  add     [rbx+20h], r14
0x18001b2ea  test    sil, sil
0x18001b2ed  jnz     short loc_18001B302
0x18001b2ef  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b2f3  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001b2f7  lea     rcx, [rbp+var_40]; this
0x18001b2fb  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001b300  jmp     short loc_18001B316
0x18001b302  cmp     [rbp+var_3E], 0
0x18001b306  jz      short loc_18001B316
0x18001b308  mov     edx, [rbp+var_3C]
0x18001b30b  lea     rcx, [rbp+var_40]; this
0x18001b30f  inc     edx; unsigned int
0x18001b311  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001b316  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b31a  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001b31e  lea     rcx, [rbp+var_20]; this
0x18001b322  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001b327  mov     byte ptr [rbx+38h], 1
0x18001b32b  jmp     loc_18001B23A
0x18001b330  xor     al, al
0x18001b332  mov     rbx, [rsp+70h+arg_8]
0x18001b33a  add     rsp, 70h
0x18001b33e  pop     r15
0x18001b340  pop     r14
0x18001b342  pop     r13
0x18001b344  pop     r12
0x18001b346  pop     rdi
0x18001b347  pop     rsi
0x18001b348  pop     rbp
0x18001b349  retn
```
