# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000dc00`
- end: `0x18000ddda`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000db0c`

## callees

- `0x18000ad68`
- `0x18000dc00`
- `0x180012478`
- `0x18001278c`
- `0x180014218`
- `0x180014cf0`
- `0x1800152a0`
- `0x180015678`

## import_xrefs

- `ntdll!memmove_s` at `0x18000dd70`
- `ntdll!memmove_s` at `0x18000dd70`

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
0x18000dc00  mov     [rsp-38h+arg_8], rbx
0x18000dc05  mov     [rsp-38h+arg_18], r9
0x18000dc0a  push    rbp
0x18000dc0b  push    rsi
0x18000dc0c  push    rdi
0x18000dc0d  push    r12
0x18000dc0f  push    r13
0x18000dc11  push    r14
0x18000dc13  push    r15
0x18000dc15  mov     rbp, rsp
0x18000dc18  sub     rsp, 70h
0x18000dc1c  mov     rdi, [rcx+18h]
0x18000dc20  mov     r14, r8
0x18000dc23  mov     r15, rdx
0x18000dc26  mov     rbx, rcx
0x18000dc29  test    rdi, rdi
0x18000dc2c  jz      loc_18000DDC0
0x18000dc32  movzx   eax, word ptr [rcx+2]
0x18000dc36  add     rdi, 0Ah
0x18000dc3a  mov     [rbp+var_40], ax
0x18000dc3e  xorps   xmm0, xmm0
0x18000dc41  mov     al, [rcx+4]
0x18000dc44  mov     [rbp+var_3E], al
0x18000dc47  xor     eax, eax
0x18000dc49  mov     [rbp+var_38], ax
0x18000dc4d  xor     sil, sil
0x18000dc50  mov     [rbp+arg_0], rdi
0x18000dc54  mov     [rbp+var_3C], 0
0x18000dc5b  movdqu  [rbp+var_30], xmm0
0x18000dc60  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000dc64  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000dc68  lea     rcx, [rbp+var_40]; this
0x18000dc6c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000dc71  mov     r12d, [rbp+arg_28]
0x18000dc75  mov     r13, [rbp+arg_20]
0x18000dc79  test    al, al
0x18000dc7b  jz      short loc_18000DCE4
0x18000dc7d  mov     r8, r14; unsigned __int64
0x18000dc80  lea     rcx, [rbp+var_40]; this
0x18000dc84  mov     rdx, r15; void *
0x18000dc87  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18000dc8c  test    eax, eax
0x18000dc8e  js      short loc_18000DCD6
0x18000dc90  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18000dc94  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18000dc98  mov     rcx, rbx; this
0x18000dc9b  jz      short loc_18000DCAB
0x18000dc9d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18000dca2  mov     rdi, rax
0x18000dca5  mov     [rbp+arg_0], rax
0x18000dca9  jmp     short loc_18000DC60
0x18000dcab  mov     r9, [rbp+arg_18]; void *
0x18000dcaf  mov     [rsp+70h+var_48], r12d; unsigned int
0x18000dcb4  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18000dcb9  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000dcbe  mov     [rbp+arg_0], rax
0x18000dcc2  mov     rdi, rax
0x18000dcc5  test    rax, rax
0x18000dcc8  jnz     short loc_18000DCD1
0x18000dcca  mov     al, 1
0x18000dccc  jmp     loc_18000DDC2
0x18000dcd1  mov     sil, 1
0x18000dcd4  jmp     short loc_18000DCDA
0x18000dcd6  mov     [rbp+arg_0], rdi
0x18000dcda  xor     r8d, r8d
0x18000dcdd  test    sil, sil
0x18000dce0  jnz     short loc_18000DD10
0x18000dce2  jmp     short loc_18000DCEC
0x18000dce4  mov     rdi, [rbp+arg_0]
0x18000dce8  mov     [rbx+20h], rdi
0x18000dcec  lea     rcx, [rbp+var_40]; this
0x18000dcf0  mov     [rbp+var_3C], 1
0x18000dcf7  mov     [rbp+var_38], r14w
0x18000dcfc  mov     qword ptr [rbp+var_30], 0
0x18000dd04  mov     qword ptr [rbp+var_30+8], r15
0x18000dd08  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000dd0d  mov     r8, rax
0x18000dd10  movzx   ecx, word ptr [rbx+6]
0x18000dd14  mov     rax, [rbp+arg_18]
0x18000dd18  mov     [rbp+var_20], cx
0x18000dd1c  mov     cl, [rbx+8]
0x18000dd1f  mov     [rbp+var_1E], cl
0x18000dd22  lea     rcx, [rbp+var_20]; this
0x18000dd26  mov     [rbp+var_1C], r12d
0x18000dd2a  mov     [rbp+var_18], r13w
0x18000dd2f  mov     [rbp+var_10], 0
0x18000dd37  mov     [rbp+var_8], rax
0x18000dd3b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000dd40  mov     rdx, [rbx+28h]
0x18000dd44  mov     r9, [rbx+20h]
0x18000dd48  mov     rcx, rdx
0x18000dd4b  sub     rcx, r9
0x18000dd4e  lea     r14, [rax+r8]
0x18000dd52  cmp     r9, rdx
0x18000dd55  sbb     rax, rax
0x18000dd58  and     rax, rcx
0x18000dd5b  cmp     rax, r14
0x18000dd5e  jb      short loc_18000DDC0
0x18000dd60  sub     rdx, r14
0x18000dd63  lea     rcx, [r14+rdi]; Destination
0x18000dd67  sub     rdx, rdi; DestinationSize
0x18000dd6a  sub     r9, rdi; SourceSize
0x18000dd6d  mov     r8, rdi; Source
0x18000dd70  call    cs:__imp_memmove_s
0x18000dd76  add     [rbx+20h], r14
0x18000dd7a  test    sil, sil
0x18000dd7d  jnz     short loc_18000DD92
0x18000dd7f  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000dd83  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000dd87  lea     rcx, [rbp+var_40]; this
0x18000dd8b  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000dd90  jmp     short loc_18000DDA6
0x18000dd92  cmp     [rbp+var_3E], 0
0x18000dd96  jz      short loc_18000DDA6
0x18000dd98  mov     edx, [rbp+var_3C]
0x18000dd9b  lea     rcx, [rbp+var_40]; this
0x18000dd9f  inc     edx; unsigned int
0x18000dda1  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000dda6  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000ddaa  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000ddae  lea     rcx, [rbp+var_20]; this
0x18000ddb2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000ddb7  mov     byte ptr [rbx+38h], 1
0x18000ddbb  jmp     loc_18000DCCA
0x18000ddc0  xor     al, al
0x18000ddc2  mov     rbx, [rsp+70h+arg_8]
0x18000ddca  add     rsp, 70h
0x18000ddce  pop     r15
0x18000ddd0  pop     r14
0x18000ddd2  pop     r13
0x18000ddd4  pop     r12
0x18000ddd6  pop     rdi
0x18000ddd7  pop     rsi
0x18000ddd8  pop     rbp
0x18000ddd9  retn
```
