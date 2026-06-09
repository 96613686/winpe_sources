# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18002c1e8`
- end: `0x18002c3cc`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c0f4`

## callees

- `0x18002824c`
- `0x180028d24`
- `0x18002a644`
- `0x18002bbc4`
- `0x18002c1e8`
- `0x18002d504`
- `0x18002dd58`
- `0x18002e14c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002c32a`
- `msvcrt!memmove_s` at `0x18002c32a`

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
0x18002c1e8  push    rbp
0x18002c1ea  push    rbx
0x18002c1eb  push    rsi
0x18002c1ec  push    rdi
0x18002c1ed  push    r12
0x18002c1ef  push    r13
0x18002c1f1  push    r14
0x18002c1f3  push    r15
0x18002c1f5  mov     rbp, rsp
0x18002c1f8  sub     rsp, 78h
0x18002c1fc  mov     rdi, [rcx+18h]
0x18002c200  mov     r13, r9
0x18002c203  mov     r15, r8
0x18002c206  mov     r12, rdx
0x18002c209  mov     rbx, rcx
0x18002c20c  test    rdi, rdi
0x18002c20f  jz      loc_18002C3B9
0x18002c215  movzx   eax, word ptr [rcx+2]
0x18002c219  add     rdi, 0Ah
0x18002c21d  mov     r8, [rcx+20h]
0x18002c221  xorps   xmm0, xmm0
0x18002c224  mov     [rbp+var_48], ax
0x18002c228  mov     al, [rcx+4]
0x18002c22b  mov     [rbp+var_46], al
0x18002c22e  xor     eax, eax
0x18002c230  mov     [rbp+var_40], ax
0x18002c234  xor     r14b, r14b
0x18002c237  mov     [rbp+Source], rdi
0x18002c23b  mov     [rbp+var_44], 0
0x18002c242  movdqu  [rbp+var_38], xmm0
0x18002c247  jmp     short loc_18002C281
0x18002c249  mov     r8, r15; unsigned __int64
0x18002c24c  lea     rcx, [rbp+var_48]; this
0x18002c250  mov     rdx, r12; void *
0x18002c253  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18002c258  test    eax, eax
0x18002c25a  js      loc_18002C37C
0x18002c260  mov     r8, [rbp+Source]; unsigned __int8 *
0x18002c264  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18002c268  jz      loc_18002C34C
0x18002c26e  mov     rcx, rbx; this
0x18002c271  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18002c276  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002c27a  mov     rdi, rax
0x18002c27d  mov     [rbp+Source], rax
0x18002c281  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18002c285  lea     rcx, [rbp+var_48]; this
0x18002c289  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002c28e  mov     sil, al
0x18002c291  test    al, al
0x18002c293  jnz     short loc_18002C249
0x18002c295  mov     rdi, [rbp+Source]
0x18002c299  mov     [rbx+20h], rdi
0x18002c29d  xor     r8d, r8d
0x18002c2a0  test    r14b, r14b
0x18002c2a3  jnz     short loc_18002C2C5
0x18002c2a5  lea     rcx, [rbp+var_48]; this
0x18002c2a9  mov     [rbp+var_44], 1
0x18002c2b0  mov     [rbp+var_40], r15w
0x18002c2b5  mov     qword ptr [rbp+var_38], r8
0x18002c2b9  mov     qword ptr [rbp+var_38+8], r12
0x18002c2bd  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18002c2c2  mov     r8, rax
0x18002c2c5  movzx   ecx, word ptr [rbx+6]
0x18002c2c9  mov     eax, [rbp+arg_28]
0x18002c2cc  mov     [rbp+var_28], cx
0x18002c2d0  mov     cl, [rbx+8]
0x18002c2d3  mov     [rbp+var_24], eax
0x18002c2d6  mov     rax, [rbp+arg_20]
0x18002c2da  mov     [rbp+var_26], cl
0x18002c2dd  lea     rcx, [rbp+var_28]; this
0x18002c2e1  mov     [rbp+var_20], ax
0x18002c2e5  mov     [rbp+var_18], 0
0x18002c2ed  mov     [rbp+var_10], r13
0x18002c2f1  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18002c2f6  mov     rdx, [rbx+28h]
0x18002c2fa  mov     r9, [rbx+20h]
0x18002c2fe  mov     rcx, rdx
0x18002c301  sub     rcx, r9
0x18002c304  lea     rsi, [rax+r8]
0x18002c308  cmp     r9, rdx
0x18002c30b  sbb     rax, rax
0x18002c30e  and     rax, rcx
0x18002c311  cmp     rax, rsi
0x18002c314  jb      loc_18002C3B9
0x18002c31a  sub     rdx, rsi
0x18002c31d  lea     rcx, [rsi+rdi]; Destination
0x18002c321  sub     rdx, rdi; DestinationSize
0x18002c324  sub     r9, rdi; SourceSize
0x18002c327  mov     r8, rdi; Source
0x18002c32a  call    cs:__imp_memmove_s
0x18002c330  add     [rbx+20h], rsi
0x18002c334  test    r14b, r14b
0x18002c337  jnz     short loc_18002C38E
0x18002c339  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002c33d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18002c341  lea     rcx, [rbp+var_48]; this
0x18002c345  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002c34a  jmp     short loc_18002C3A2
0x18002c34c  mov     ecx, [rbp+arg_28]
0x18002c34f  mov     r9, r13; void *
0x18002c352  mov     [rsp+78h+var_50], ecx; unsigned int
0x18002c356  mov     rcx, [rbp+arg_20]
0x18002c35a  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18002c35f  mov     rcx, rbx; this
0x18002c362  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18002c367  mov     [rbp+Source], rax
0x18002c36b  mov     rdi, rax
0x18002c36e  test    rax, rax
0x18002c371  jnz     short loc_18002C377
0x18002c373  mov     al, 1
0x18002c375  jmp     short loc_18002C3BB
0x18002c377  mov     r14b, 1
0x18002c37a  jmp     short loc_18002C380
0x18002c37c  mov     [rbp+Source], rdi
0x18002c380  test    sil, sil
0x18002c383  jnz     loc_18002C29D
0x18002c389  jmp     loc_18002C299
0x18002c38e  cmp     [rbp+var_46], 0
0x18002c392  jz      short loc_18002C3A2
0x18002c394  mov     edx, [rbp+var_44]
0x18002c397  lea     rcx, [rbp+var_48]; this
0x18002c39b  inc     edx; unsigned int
0x18002c39d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18002c3a2  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002c3a6  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18002c3aa  lea     rcx, [rbp+var_28]; this
0x18002c3ae  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18002c3b3  mov     byte ptr [rbx+38h], 1
0x18002c3b7  jmp     short loc_18002C373
0x18002c3b9  xor     al, al
0x18002c3bb  add     rsp, 78h
0x18002c3bf  pop     r15
0x18002c3c1  pop     r14
0x18002c3c3  pop     r13
0x18002c3c5  pop     r12
0x18002c3c7  pop     rdi
0x18002c3c8  pop     rsi
0x18002c3c9  pop     rbx
0x18002c3ca  pop     rbp
0x18002c3cb  retn
```
