# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140019cd8`
- end: `0x140019eb2`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140019be4`

## callees

- `0x1400179a4`
- `0x140017e10`
- `0x140018684`
- `0x140019730`
- `0x140019cd8`
- `0x14001a9fc`
- `0x14001b0f0`
- `0x14001b39c`

## import_xrefs

- `msvcrt!memmove_s` at `0x140019e48`
- `msvcrt!memmove_s` at `0x140019e48`

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
0x140019cd8  mov     [rsp-38h+arg_8], rbx
0x140019cdd  mov     [rsp-38h+arg_18], r9
0x140019ce2  push    rbp
0x140019ce3  push    rsi
0x140019ce4  push    rdi
0x140019ce5  push    r12
0x140019ce7  push    r13
0x140019ce9  push    r14
0x140019ceb  push    r15
0x140019ced  mov     rbp, rsp
0x140019cf0  sub     rsp, 70h
0x140019cf4  mov     rdi, [rcx+18h]
0x140019cf8  mov     r14, r8
0x140019cfb  mov     r15, rdx
0x140019cfe  mov     rbx, rcx
0x140019d01  test    rdi, rdi
0x140019d04  jz      loc_140019E98
0x140019d0a  movzx   eax, word ptr [rcx+2]
0x140019d0e  add     rdi, 0Ah
0x140019d12  mov     [rbp+var_40], ax
0x140019d16  xorps   xmm0, xmm0
0x140019d19  mov     al, [rcx+4]
0x140019d1c  mov     [rbp+var_3E], al
0x140019d1f  xor     eax, eax
0x140019d21  mov     [rbp+var_38], ax
0x140019d25  xor     sil, sil
0x140019d28  mov     [rbp+arg_0], rdi
0x140019d2c  mov     [rbp+var_3C], 0
0x140019d33  movdqu  [rbp+var_30], xmm0
0x140019d38  mov     r8, [rbx+20h]; unsigned __int8 *
0x140019d3c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x140019d40  lea     rcx, [rbp+var_40]; this
0x140019d44  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140019d49  mov     r12d, [rbp+arg_28]
0x140019d4d  mov     r13, [rbp+arg_20]
0x140019d51  test    al, al
0x140019d53  jz      short loc_140019DBC
0x140019d55  mov     r8, r14; unsigned __int64
0x140019d58  lea     rcx, [rbp+var_40]; this
0x140019d5c  mov     rdx, r15; void *
0x140019d5f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x140019d64  test    eax, eax
0x140019d66  js      short loc_140019DAE
0x140019d68  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x140019d6c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x140019d70  mov     rcx, rbx; this
0x140019d73  jz      short loc_140019D83
0x140019d75  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x140019d7a  mov     rdi, rax
0x140019d7d  mov     [rbp+arg_0], rax
0x140019d81  jmp     short loc_140019D38
0x140019d83  mov     r9, [rbp+arg_18]; void *
0x140019d87  mov     [rsp+70h+var_48], r12d; unsigned int
0x140019d8c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x140019d91  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140019d96  mov     [rbp+arg_0], rax
0x140019d9a  mov     rdi, rax
0x140019d9d  test    rax, rax
0x140019da0  jnz     short loc_140019DA9
0x140019da2  mov     al, 1
0x140019da4  jmp     loc_140019E9A
0x140019da9  mov     sil, 1
0x140019dac  jmp     short loc_140019DB2
0x140019dae  mov     [rbp+arg_0], rdi
0x140019db2  xor     r8d, r8d
0x140019db5  test    sil, sil
0x140019db8  jnz     short loc_140019DE8
0x140019dba  jmp     short loc_140019DC4
0x140019dbc  mov     rdi, [rbp+arg_0]
0x140019dc0  mov     [rbx+20h], rdi
0x140019dc4  lea     rcx, [rbp+var_40]; this
0x140019dc8  mov     [rbp+var_3C], 1
0x140019dcf  mov     [rbp+var_38], r14w
0x140019dd4  mov     qword ptr [rbp+var_30], 0
0x140019ddc  mov     qword ptr [rbp+var_30+8], r15
0x140019de0  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140019de5  mov     r8, rax
0x140019de8  movzx   ecx, word ptr [rbx+6]
0x140019dec  mov     rax, [rbp+arg_18]
0x140019df0  mov     [rbp+var_20], cx
0x140019df4  mov     cl, [rbx+8]
0x140019df7  mov     [rbp+var_1E], cl
0x140019dfa  lea     rcx, [rbp+var_20]; this
0x140019dfe  mov     [rbp+var_1C], r12d
0x140019e02  mov     [rbp+var_18], r13w
0x140019e07  mov     [rbp+var_10], 0
0x140019e0f  mov     [rbp+var_8], rax
0x140019e13  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140019e18  mov     rdx, [rbx+28h]
0x140019e1c  mov     r9, [rbx+20h]
0x140019e20  mov     rcx, rdx
0x140019e23  sub     rcx, r9
0x140019e26  lea     r14, [rax+r8]
0x140019e2a  cmp     r9, rdx
0x140019e2d  sbb     rax, rax
0x140019e30  and     rax, rcx
0x140019e33  cmp     rax, r14
0x140019e36  jb      short loc_140019E98
0x140019e38  sub     rdx, r14
0x140019e3b  lea     rcx, [r14+rdi]; Destination
0x140019e3f  sub     rdx, rdi; DestinationSize
0x140019e42  sub     r9, rdi; SourceSize
0x140019e45  mov     r8, rdi; Source
0x140019e48  call    cs:__imp_memmove_s
0x140019e4e  add     [rbx+20h], r14
0x140019e52  test    sil, sil
0x140019e55  jnz     short loc_140019E6A
0x140019e57  mov     r8, [rbx+20h]; unsigned __int8 *
0x140019e5b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x140019e5f  lea     rcx, [rbp+var_40]; this
0x140019e63  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140019e68  jmp     short loc_140019E7E
0x140019e6a  cmp     [rbp+var_3E], 0
0x140019e6e  jz      short loc_140019E7E
0x140019e70  mov     edx, [rbp+var_3C]
0x140019e73  lea     rcx, [rbp+var_40]; this
0x140019e77  inc     edx; unsigned int
0x140019e79  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x140019e7e  mov     r8, [rbx+20h]; unsigned __int8 *
0x140019e82  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x140019e86  lea     rcx, [rbp+var_20]; this
0x140019e8a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140019e8f  mov     byte ptr [rbx+38h], 1
0x140019e93  jmp     loc_140019DA2
0x140019e98  xor     al, al
0x140019e9a  mov     rbx, [rsp+70h+arg_8]
0x140019ea2  add     rsp, 70h
0x140019ea6  pop     r15
0x140019ea8  pop     r14
0x140019eaa  pop     r13
0x140019eac  pop     r12
0x140019eae  pop     rdi
0x140019eaf  pop     rsi
0x140019eb0  pop     rbp
0x140019eb1  retn
```
