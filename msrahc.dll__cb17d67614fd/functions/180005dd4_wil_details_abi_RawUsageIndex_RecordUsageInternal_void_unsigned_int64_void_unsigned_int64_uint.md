# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005dd4`
- end: `0x180005fb8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x180003bd4`
- `0x180003f14`
- `0x1800047e8`
- `0x180005830`
- `0x180005dd4`
- `0x180006960`
- `0x180007218`
- `0x180007518`

## import_xrefs

- `msvcrt!memmove_s` at `0x180005f16`
- `msvcrt!memmove_s` at `0x180005f16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  char *v11; // rdi
  unsigned __int8 *v12; // r8
  char v13; // r14
  int v14; // eax
  unsigned __int8 *v15; // rax
  char v17; // cl
  unsigned __int64 Size; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rsi
  const void *v24; // [rsp+30h] [rbp-48h] BYREF
  __int16 v25; // [rsp+38h] [rbp-40h]
  __int128 v26; // [rsp+40h] [rbp-38h]
  __int16 v27; // [rsp+50h] [rbp-28h] BYREF
  char v28; // [rsp+52h] [rbp-26h]
  unsigned int v29; // [rsp+54h] [rbp-24h]
  __int16 v30; // [rsp+58h] [rbp-20h]
  __int64 v31; // [rsp+60h] [rbp-18h]
  void *v32; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    LOWORD(v24) = *((_WORD *)this + 1);
    BYTE2(v24) = *((_BYTE *)this + 4);
    v25 = 0;
    v13 = 0;
    Source = v11;
    HIDWORD(v24) = 0;
    v26 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 **)&Source,
              v12) )
      {
        v11 = (char *)Source;
        *((_QWORD *)this + 4) = Source;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare(&v24, a2, a3);
      if ( v14 < 0 )
      {
        Source = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 *)Source);
      v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
      v11 = (char *)v15;
      Source = v15;
    }
    Source = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               (struct wil::details_abi::UsageIndexProperty *)&v24,
               (unsigned __int8 *)Source,
               a4,
               a5,
               a6);
    v11 = (char *)Source;
    if ( !Source )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      HIDWORD(v24) = 1;
      v25 = a3;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v27 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v29 = a6;
    v28 = v17;
    v30 = a5;
    v31 = 0;
    v32 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( BYTE2(v24) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v24,
            HIDWORD(v24) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
        (unsigned __int8 **)&Source,
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
0x180005dd4  push    rbp
0x180005dd6  push    rbx
0x180005dd7  push    rsi
0x180005dd8  push    rdi
0x180005dd9  push    r12
0x180005ddb  push    r13
0x180005ddd  push    r14
0x180005ddf  push    r15
0x180005de1  mov     rbp, rsp
0x180005de4  sub     rsp, 78h
0x180005de8  mov     rdi, [rcx+18h]
0x180005dec  mov     r13, r9
0x180005def  mov     r15, r8
0x180005df2  mov     r12, rdx
0x180005df5  mov     rbx, rcx
0x180005df8  test    rdi, rdi
0x180005dfb  jz      loc_180005FA5
0x180005e01  movzx   eax, word ptr [rcx+2]
0x180005e05  add     rdi, 0Ah
0x180005e09  mov     r8, [rcx+20h]
0x180005e0d  xorps   xmm0, xmm0
0x180005e10  mov     [rbp+var_48], ax
0x180005e14  mov     al, [rcx+4]
0x180005e17  mov     [rbp+var_46], al
0x180005e1a  xor     eax, eax
0x180005e1c  mov     [rbp+var_40], ax
0x180005e20  xor     r14b, r14b
0x180005e23  mov     [rbp+Source], rdi
0x180005e27  mov     [rbp+var_44], 0
0x180005e2e  movdqu  [rbp+var_38], xmm0
0x180005e33  jmp     short loc_180005E6D
0x180005e35  mov     r8, r15; unsigned __int64
0x180005e38  lea     rcx, [rbp+var_48]; this
0x180005e3c  mov     rdx, r12; void *
0x180005e3f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180005e44  test    eax, eax
0x180005e46  js      loc_180005F68
0x180005e4c  mov     r8, [rbp+Source]; unsigned __int8 *
0x180005e50  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180005e54  jz      loc_180005F38
0x180005e5a  mov     rcx, rbx; this
0x180005e5d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180005e62  mov     r8, [rbx+20h]; unsigned __int8 *
0x180005e66  mov     rdi, rax
0x180005e69  mov     [rbp+Source], rax
0x180005e6d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180005e71  lea     rcx, [rbp+var_48]; this
0x180005e75  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180005e7a  mov     sil, al
0x180005e7d  test    al, al
0x180005e7f  jnz     short loc_180005E35
0x180005e81  mov     rdi, [rbp+Source]
0x180005e85  mov     [rbx+20h], rdi
0x180005e89  xor     r8d, r8d
0x180005e8c  test    r14b, r14b
0x180005e8f  jnz     short loc_180005EB1
0x180005e91  lea     rcx, [rbp+var_48]; this
0x180005e95  mov     [rbp+var_44], 1
0x180005e9c  mov     [rbp+var_40], r15w
0x180005ea1  mov     qword ptr [rbp+var_38], r8
0x180005ea5  mov     qword ptr [rbp+var_38+8], r12
0x180005ea9  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180005eae  mov     r8, rax
0x180005eb1  movzx   ecx, word ptr [rbx+6]
0x180005eb5  mov     eax, [rbp+arg_28]
0x180005eb8  mov     [rbp+var_28], cx
0x180005ebc  mov     cl, [rbx+8]
0x180005ebf  mov     [rbp+var_24], eax
0x180005ec2  mov     rax, [rbp+arg_20]
0x180005ec6  mov     [rbp+var_26], cl
0x180005ec9  lea     rcx, [rbp+var_28]; this
0x180005ecd  mov     [rbp+var_20], ax
0x180005ed1  mov     [rbp+var_18], 0
0x180005ed9  mov     [rbp+var_10], r13
0x180005edd  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180005ee2  mov     rdx, [rbx+28h]
0x180005ee6  mov     r9, [rbx+20h]
0x180005eea  mov     rcx, rdx
0x180005eed  sub     rcx, r9
0x180005ef0  lea     rsi, [rax+r8]
0x180005ef4  cmp     r9, rdx
0x180005ef7  sbb     rax, rax
0x180005efa  and     rax, rcx
0x180005efd  cmp     rax, rsi
0x180005f00  jb      loc_180005FA5
0x180005f06  sub     rdx, rsi
0x180005f09  lea     rcx, [rsi+rdi]; Destination
0x180005f0d  sub     rdx, rdi; DestinationSize
0x180005f10  sub     r9, rdi; SourceSize
0x180005f13  mov     r8, rdi; Source
0x180005f16  call    cs:__imp_memmove_s
0x180005f1c  add     [rbx+20h], rsi
0x180005f20  test    r14b, r14b
0x180005f23  jnz     short loc_180005F7A
0x180005f25  mov     r8, [rbx+20h]; unsigned __int8 *
0x180005f29  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180005f2d  lea     rcx, [rbp+var_48]; this
0x180005f31  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180005f36  jmp     short loc_180005F8E
0x180005f38  mov     ecx, [rbp+arg_28]
0x180005f3b  mov     r9, r13; void *
0x180005f3e  mov     [rsp+78h+var_50], ecx; unsigned int
0x180005f42  mov     rcx, [rbp+arg_20]
0x180005f46  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180005f4b  mov     rcx, rbx; this
0x180005f4e  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180005f53  mov     [rbp+Source], rax
0x180005f57  mov     rdi, rax
0x180005f5a  test    rax, rax
0x180005f5d  jnz     short loc_180005F63
0x180005f5f  mov     al, 1
0x180005f61  jmp     short loc_180005FA7
0x180005f63  mov     r14b, 1
0x180005f66  jmp     short loc_180005F6C
0x180005f68  mov     [rbp+Source], rdi
0x180005f6c  test    sil, sil
0x180005f6f  jnz     loc_180005E89
0x180005f75  jmp     loc_180005E85
0x180005f7a  cmp     [rbp+var_46], 0
0x180005f7e  jz      short loc_180005F8E
0x180005f80  mov     edx, [rbp+var_44]
0x180005f83  lea     rcx, [rbp+var_48]; this
0x180005f87  inc     edx; unsigned int
0x180005f89  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180005f8e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180005f92  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180005f96  lea     rcx, [rbp+var_28]; this
0x180005f9a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180005f9f  mov     byte ptr [rbx+38h], 1
0x180005fa3  jmp     short loc_180005F5F
0x180005fa5  xor     al, al
0x180005fa7  add     rsp, 78h
0x180005fab  pop     r15
0x180005fad  pop     r14
0x180005faf  pop     r13
0x180005fb1  pop     r12
0x180005fb3  pop     rdi
0x180005fb4  pop     rsi
0x180005fb5  pop     rbx
0x180005fb6  pop     rbp
0x180005fb7  retn
```
