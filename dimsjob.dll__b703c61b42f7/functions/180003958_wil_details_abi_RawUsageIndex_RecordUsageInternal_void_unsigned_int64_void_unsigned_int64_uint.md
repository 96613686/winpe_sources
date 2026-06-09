# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180003958`
- end: `0x180003b32`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003864`

## callees

- `0x180003958`
- `0x180005fa4`
- `0x180006250`
- `0x180006b64`
- `0x180007ff0`
- `0x180008dfc`
- `0x1800095cc`
- `0x18000987c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180003ac8`
- `msvcrt!memmove_s` at `0x180003ac8`

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
0x180003958  mov     [rsp-38h+arg_8], rbx
0x18000395d  mov     [rsp-38h+arg_18], r9
0x180003962  push    rbp
0x180003963  push    rsi
0x180003964  push    rdi
0x180003965  push    r12
0x180003967  push    r13
0x180003969  push    r14
0x18000396b  push    r15
0x18000396d  mov     rbp, rsp
0x180003970  sub     rsp, 70h
0x180003974  mov     rdi, [rcx+18h]
0x180003978  mov     r14, r8
0x18000397b  mov     r15, rdx
0x18000397e  mov     rbx, rcx
0x180003981  test    rdi, rdi
0x180003984  jz      loc_180003B18
0x18000398a  movzx   eax, word ptr [rcx+2]
0x18000398e  add     rdi, 0Ah
0x180003992  mov     [rbp+var_40], ax
0x180003996  xorps   xmm0, xmm0
0x180003999  mov     al, [rcx+4]
0x18000399c  mov     [rbp+var_3E], al
0x18000399f  xor     eax, eax
0x1800039a1  mov     [rbp+var_38], ax
0x1800039a5  xor     sil, sil
0x1800039a8  mov     [rbp+arg_0], rdi
0x1800039ac  mov     [rbp+var_3C], 0
0x1800039b3  movdqu  [rbp+var_30], xmm0
0x1800039b8  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800039bc  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800039c0  lea     rcx, [rbp+var_40]; this
0x1800039c4  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800039c9  mov     r12d, [rbp+arg_28]
0x1800039cd  mov     r13, [rbp+arg_20]
0x1800039d1  test    al, al
0x1800039d3  jz      short loc_180003A3C
0x1800039d5  mov     r8, r14; unsigned __int64
0x1800039d8  lea     rcx, [rbp+var_40]; this
0x1800039dc  mov     rdx, r15; void *
0x1800039df  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800039e4  test    eax, eax
0x1800039e6  js      short loc_180003A2E
0x1800039e8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800039ec  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800039f0  mov     rcx, rbx; this
0x1800039f3  jz      short loc_180003A03
0x1800039f5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800039fa  mov     rdi, rax
0x1800039fd  mov     [rbp+arg_0], rax
0x180003a01  jmp     short loc_1800039B8
0x180003a03  mov     r9, [rbp+arg_18]; void *
0x180003a07  mov     [rsp+70h+var_48], r12d; unsigned int
0x180003a0c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180003a11  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180003a16  mov     [rbp+arg_0], rax
0x180003a1a  mov     rdi, rax
0x180003a1d  test    rax, rax
0x180003a20  jnz     short loc_180003A29
0x180003a22  mov     al, 1
0x180003a24  jmp     loc_180003B1A
0x180003a29  mov     sil, 1
0x180003a2c  jmp     short loc_180003A32
0x180003a2e  mov     [rbp+arg_0], rdi
0x180003a32  xor     r8d, r8d
0x180003a35  test    sil, sil
0x180003a38  jnz     short loc_180003A68
0x180003a3a  jmp     short loc_180003A44
0x180003a3c  mov     rdi, [rbp+arg_0]
0x180003a40  mov     [rbx+20h], rdi
0x180003a44  lea     rcx, [rbp+var_40]; this
0x180003a48  mov     [rbp+var_3C], 1
0x180003a4f  mov     [rbp+var_38], r14w
0x180003a54  mov     qword ptr [rbp+var_30], 0
0x180003a5c  mov     qword ptr [rbp+var_30+8], r15
0x180003a60  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180003a65  mov     r8, rax
0x180003a68  movzx   ecx, word ptr [rbx+6]
0x180003a6c  mov     rax, [rbp+arg_18]
0x180003a70  mov     [rbp+var_20], cx
0x180003a74  mov     cl, [rbx+8]
0x180003a77  mov     [rbp+var_1E], cl
0x180003a7a  lea     rcx, [rbp+var_20]; this
0x180003a7e  mov     [rbp+var_1C], r12d
0x180003a82  mov     [rbp+var_18], r13w
0x180003a87  mov     [rbp+var_10], 0
0x180003a8f  mov     [rbp+var_8], rax
0x180003a93  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180003a98  mov     rdx, [rbx+28h]
0x180003a9c  mov     r9, [rbx+20h]
0x180003aa0  mov     rcx, rdx
0x180003aa3  sub     rcx, r9
0x180003aa6  lea     r14, [rax+r8]
0x180003aaa  cmp     r9, rdx
0x180003aad  sbb     rax, rax
0x180003ab0  and     rax, rcx
0x180003ab3  cmp     rax, r14
0x180003ab6  jb      short loc_180003B18
0x180003ab8  sub     rdx, r14
0x180003abb  lea     rcx, [r14+rdi]; Destination
0x180003abf  sub     rdx, rdi; DestinationSize
0x180003ac2  sub     r9, rdi; SourceSize
0x180003ac5  mov     r8, rdi; Source
0x180003ac8  call    cs:__imp_memmove_s
0x180003ace  add     [rbx+20h], r14
0x180003ad2  test    sil, sil
0x180003ad5  jnz     short loc_180003AEA
0x180003ad7  mov     r8, [rbx+20h]; unsigned __int8 *
0x180003adb  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180003adf  lea     rcx, [rbp+var_40]; this
0x180003ae3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180003ae8  jmp     short loc_180003AFE
0x180003aea  cmp     [rbp+var_3E], 0
0x180003aee  jz      short loc_180003AFE
0x180003af0  mov     edx, [rbp+var_3C]
0x180003af3  lea     rcx, [rbp+var_40]; this
0x180003af7  inc     edx; unsigned int
0x180003af9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180003afe  mov     r8, [rbx+20h]; unsigned __int8 *
0x180003b02  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180003b06  lea     rcx, [rbp+var_20]; this
0x180003b0a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180003b0f  mov     byte ptr [rbx+38h], 1
0x180003b13  jmp     loc_180003A22
0x180003b18  xor     al, al
0x180003b1a  mov     rbx, [rsp+70h+arg_8]
0x180003b22  add     rsp, 70h
0x180003b26  pop     r15
0x180003b28  pop     r14
0x180003b2a  pop     r13
0x180003b2c  pop     r12
0x180003b2e  pop     rdi
0x180003b2f  pop     rsi
0x180003b30  pop     rbp
0x180003b31  retn
```
