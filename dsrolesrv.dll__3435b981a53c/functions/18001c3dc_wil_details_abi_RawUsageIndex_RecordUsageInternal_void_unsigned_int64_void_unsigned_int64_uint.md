# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001c3dc`
- end: `0x18001c5b6`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c2e8`

## callees

- `0x180019968`
- `0x18001a32c`
- `0x18001ac4c`
- `0x18001be70`
- `0x18001c3dc`
- `0x18001cca0`
- `0x18001d4e0`
- `0x18001d8f8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001c54c`
- `msvcrt!memmove_s` at `0x18001c54c`

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
0x18001c3dc  mov     [rsp-38h+arg_8], rbx
0x18001c3e1  mov     [rsp-38h+arg_18], r9
0x18001c3e6  push    rbp
0x18001c3e7  push    rsi
0x18001c3e8  push    rdi
0x18001c3e9  push    r12
0x18001c3eb  push    r13
0x18001c3ed  push    r14
0x18001c3ef  push    r15
0x18001c3f1  mov     rbp, rsp
0x18001c3f4  sub     rsp, 70h
0x18001c3f8  mov     rdi, [rcx+18h]
0x18001c3fc  mov     r14, r8
0x18001c3ff  mov     r15, rdx
0x18001c402  mov     rbx, rcx
0x18001c405  test    rdi, rdi
0x18001c408  jz      loc_18001C59C
0x18001c40e  movzx   eax, word ptr [rcx+2]
0x18001c412  add     rdi, 0Ah
0x18001c416  mov     [rbp+var_40], ax
0x18001c41a  xorps   xmm0, xmm0
0x18001c41d  mov     al, [rcx+4]
0x18001c420  mov     [rbp+var_3E], al
0x18001c423  xor     eax, eax
0x18001c425  mov     [rbp+var_38], ax
0x18001c429  xor     sil, sil
0x18001c42c  mov     [rbp+arg_0], rdi
0x18001c430  mov     [rbp+var_3C], 0
0x18001c437  movdqu  [rbp+var_30], xmm0
0x18001c43c  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c440  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001c444  lea     rcx, [rbp+var_40]; this
0x18001c448  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001c44d  mov     r12d, [rbp+arg_28]
0x18001c451  mov     r13, [rbp+arg_20]
0x18001c455  test    al, al
0x18001c457  jz      short loc_18001C4C0
0x18001c459  mov     r8, r14; unsigned __int64
0x18001c45c  lea     rcx, [rbp+var_40]; this
0x18001c460  mov     rdx, r15; void *
0x18001c463  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001c468  test    eax, eax
0x18001c46a  js      short loc_18001C4B2
0x18001c46c  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001c470  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001c474  mov     rcx, rbx; this
0x18001c477  jz      short loc_18001C487
0x18001c479  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001c47e  mov     rdi, rax
0x18001c481  mov     [rbp+arg_0], rax
0x18001c485  jmp     short loc_18001C43C
0x18001c487  mov     r9, [rbp+arg_18]; void *
0x18001c48b  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001c490  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001c495  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001c49a  mov     [rbp+arg_0], rax
0x18001c49e  mov     rdi, rax
0x18001c4a1  test    rax, rax
0x18001c4a4  jnz     short loc_18001C4AD
0x18001c4a6  mov     al, 1
0x18001c4a8  jmp     loc_18001C59E
0x18001c4ad  mov     sil, 1
0x18001c4b0  jmp     short loc_18001C4B6
0x18001c4b2  mov     [rbp+arg_0], rdi
0x18001c4b6  xor     r8d, r8d
0x18001c4b9  test    sil, sil
0x18001c4bc  jnz     short loc_18001C4EC
0x18001c4be  jmp     short loc_18001C4C8
0x18001c4c0  mov     rdi, [rbp+arg_0]
0x18001c4c4  mov     [rbx+20h], rdi
0x18001c4c8  lea     rcx, [rbp+var_40]; this
0x18001c4cc  mov     [rbp+var_3C], 1
0x18001c4d3  mov     [rbp+var_38], r14w
0x18001c4d8  mov     qword ptr [rbp+var_30], 0
0x18001c4e0  mov     qword ptr [rbp+var_30+8], r15
0x18001c4e4  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001c4e9  mov     r8, rax
0x18001c4ec  movzx   ecx, word ptr [rbx+6]
0x18001c4f0  mov     rax, [rbp+arg_18]
0x18001c4f4  mov     [rbp+var_20], cx
0x18001c4f8  mov     cl, [rbx+8]
0x18001c4fb  mov     [rbp+var_1E], cl
0x18001c4fe  lea     rcx, [rbp+var_20]; this
0x18001c502  mov     [rbp+var_1C], r12d
0x18001c506  mov     [rbp+var_18], r13w
0x18001c50b  mov     [rbp+var_10], 0
0x18001c513  mov     [rbp+var_8], rax
0x18001c517  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001c51c  mov     rdx, [rbx+28h]
0x18001c520  mov     r9, [rbx+20h]
0x18001c524  mov     rcx, rdx
0x18001c527  sub     rcx, r9
0x18001c52a  lea     r14, [rax+r8]
0x18001c52e  cmp     r9, rdx
0x18001c531  sbb     rax, rax
0x18001c534  and     rax, rcx
0x18001c537  cmp     rax, r14
0x18001c53a  jb      short loc_18001C59C
0x18001c53c  sub     rdx, r14
0x18001c53f  lea     rcx, [r14+rdi]; Destination
0x18001c543  sub     rdx, rdi; DestinationSize
0x18001c546  sub     r9, rdi; SourceSize
0x18001c549  mov     r8, rdi; Source
0x18001c54c  call    cs:__imp_memmove_s
0x18001c552  add     [rbx+20h], r14
0x18001c556  test    sil, sil
0x18001c559  jnz     short loc_18001C56E
0x18001c55b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c55f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001c563  lea     rcx, [rbp+var_40]; this
0x18001c567  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c56c  jmp     short loc_18001C582
0x18001c56e  cmp     [rbp+var_3E], 0
0x18001c572  jz      short loc_18001C582
0x18001c574  mov     edx, [rbp+var_3C]
0x18001c577  lea     rcx, [rbp+var_40]; this
0x18001c57b  inc     edx; unsigned int
0x18001c57d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001c582  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c586  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001c58a  lea     rcx, [rbp+var_20]; this
0x18001c58e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c593  mov     byte ptr [rbx+38h], 1
0x18001c597  jmp     loc_18001C4A6
0x18001c59c  xor     al, al
0x18001c59e  mov     rbx, [rsp+70h+arg_8]
0x18001c5a6  add     rsp, 70h
0x18001c5aa  pop     r15
0x18001c5ac  pop     r14
0x18001c5ae  pop     r13
0x18001c5b0  pop     r12
0x18001c5b2  pop     rdi
0x18001c5b3  pop     rsi
0x18001c5b4  pop     rbp
0x18001c5b5  retn
```
