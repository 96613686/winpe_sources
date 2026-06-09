# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180034b1c`
- end: `0x180034cf6`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034a28`

## callees

- `0x1800328f8`
- `0x180032bbc`
- `0x1800334dc`
- `0x1800345b8`
- `0x180034b1c`
- `0x180035414`
- `0x180035da0`
- `0x180036118`

## import_xrefs

- `msvcrt!memmove_s` at `0x180034c8c`
- `msvcrt!memmove_s` at `0x180034c8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180034b1c  mov     [rsp-38h+arg_8], rbx
0x180034b21  mov     [rsp-38h+arg_18], r9
0x180034b26  push    rbp
0x180034b27  push    rsi
0x180034b28  push    rdi
0x180034b29  push    r12
0x180034b2b  push    r13
0x180034b2d  push    r14
0x180034b2f  push    r15
0x180034b31  mov     rbp, rsp
0x180034b34  sub     rsp, 70h
0x180034b38  mov     rdi, [rcx+18h]
0x180034b3c  mov     r14, r8
0x180034b3f  mov     r15, rdx
0x180034b42  mov     rbx, rcx
0x180034b45  test    rdi, rdi
0x180034b48  jz      loc_180034CDC
0x180034b4e  movzx   eax, word ptr [rcx+2]
0x180034b52  add     rdi, 0Ah
0x180034b56  mov     [rbp+var_40], ax
0x180034b5a  xorps   xmm0, xmm0
0x180034b5d  mov     al, [rcx+4]
0x180034b60  mov     [rbp+var_3E], al
0x180034b63  xor     eax, eax
0x180034b65  mov     [rbp+var_38], ax
0x180034b69  xor     sil, sil
0x180034b6c  mov     [rbp+arg_0], rdi
0x180034b70  mov     [rbp+var_3C], 0
0x180034b77  movdqu  [rbp+var_30], xmm0
0x180034b7c  mov     r8, [rbx+20h]; unsigned __int8 *
0x180034b80  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180034b84  lea     rcx, [rbp+var_40]; this
0x180034b88  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180034b8d  mov     r12d, [rbp+arg_28]
0x180034b91  mov     r13, [rbp+arg_20]
0x180034b95  test    al, al
0x180034b97  jz      short loc_180034C00
0x180034b99  mov     r8, r14; unsigned __int64
0x180034b9c  lea     rcx, [rbp+var_40]; this
0x180034ba0  mov     rdx, r15; void *
0x180034ba3  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180034ba8  test    eax, eax
0x180034baa  js      short loc_180034BF2
0x180034bac  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180034bb0  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180034bb4  mov     rcx, rbx; this
0x180034bb7  jz      short loc_180034BC7
0x180034bb9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180034bbe  mov     rdi, rax
0x180034bc1  mov     [rbp+arg_0], rax
0x180034bc5  jmp     short loc_180034B7C
0x180034bc7  mov     r9, [rbp+arg_18]; void *
0x180034bcb  mov     [rsp+70h+var_48], r12d; unsigned int
0x180034bd0  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180034bd5  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180034bda  mov     [rbp+arg_0], rax
0x180034bde  mov     rdi, rax
0x180034be1  test    rax, rax
0x180034be4  jnz     short loc_180034BED
0x180034be6  mov     al, 1
0x180034be8  jmp     loc_180034CDE
0x180034bed  mov     sil, 1
0x180034bf0  jmp     short loc_180034BF6
0x180034bf2  mov     [rbp+arg_0], rdi
0x180034bf6  xor     r8d, r8d
0x180034bf9  test    sil, sil
0x180034bfc  jnz     short loc_180034C2C
0x180034bfe  jmp     short loc_180034C08
0x180034c00  mov     rdi, [rbp+arg_0]
0x180034c04  mov     [rbx+20h], rdi
0x180034c08  lea     rcx, [rbp+var_40]; this
0x180034c0c  mov     [rbp+var_3C], 1
0x180034c13  mov     [rbp+var_38], r14w
0x180034c18  mov     qword ptr [rbp+var_30], 0
0x180034c20  mov     qword ptr [rbp+var_30+8], r15
0x180034c24  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180034c29  mov     r8, rax
0x180034c2c  movzx   ecx, word ptr [rbx+6]
0x180034c30  mov     rax, [rbp+arg_18]
0x180034c34  mov     [rbp+var_20], cx
0x180034c38  mov     cl, [rbx+8]
0x180034c3b  mov     [rbp+var_1E], cl
0x180034c3e  lea     rcx, [rbp+var_20]; this
0x180034c42  mov     [rbp+var_1C], r12d
0x180034c46  mov     [rbp+var_18], r13w
0x180034c4b  mov     [rbp+var_10], 0
0x180034c53  mov     [rbp+var_8], rax
0x180034c57  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180034c5c  mov     rdx, [rbx+28h]
0x180034c60  mov     r9, [rbx+20h]
0x180034c64  mov     rcx, rdx
0x180034c67  sub     rcx, r9
0x180034c6a  lea     r14, [rax+r8]
0x180034c6e  cmp     r9, rdx
0x180034c71  sbb     rax, rax
0x180034c74  and     rax, rcx
0x180034c77  cmp     rax, r14
0x180034c7a  jb      short loc_180034CDC
0x180034c7c  sub     rdx, r14
0x180034c7f  lea     rcx, [r14+rdi]; Destination
0x180034c83  sub     rdx, rdi; DestinationSize
0x180034c86  sub     r9, rdi; SourceSize
0x180034c89  mov     r8, rdi; Source
0x180034c8c  call    cs:__imp_memmove_s
0x180034c92  add     [rbx+20h], r14
0x180034c96  test    sil, sil
0x180034c99  jnz     short loc_180034CAE
0x180034c9b  mov     r8, [rbx+20h]; unsigned __int8 *
0x180034c9f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180034ca3  lea     rcx, [rbp+var_40]; this
0x180034ca7  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180034cac  jmp     short loc_180034CC2
0x180034cae  cmp     [rbp+var_3E], 0
0x180034cb2  jz      short loc_180034CC2
0x180034cb4  mov     edx, [rbp+var_3C]
0x180034cb7  lea     rcx, [rbp+var_40]; this
0x180034cbb  inc     edx; unsigned int
0x180034cbd  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180034cc2  mov     r8, [rbx+20h]; unsigned __int8 *
0x180034cc6  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180034cca  lea     rcx, [rbp+var_20]; this
0x180034cce  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180034cd3  mov     byte ptr [rbx+38h], 1
0x180034cd7  jmp     loc_180034BE6
0x180034cdc  xor     al, al
0x180034cde  mov     rbx, [rsp+70h+arg_8]
0x180034ce6  add     rsp, 70h
0x180034cea  pop     r15
0x180034cec  pop     r14
0x180034cee  pop     r13
0x180034cf0  pop     r12
0x180034cf2  pop     rdi
0x180034cf3  pop     rsi
0x180034cf4  pop     rbp
0x180034cf5  retn
```
