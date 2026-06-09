# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005d04`
- end: `0x180005ee8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005c10`

## callees

- `0x180003aac`
- `0x180003de4`
- `0x180004774`
- `0x180005760`
- `0x180005d04`
- `0x180006914`
- `0x1800071fc`
- `0x1800074ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x180005e46`
- `msvcrt!memmove_s` at `0x180005e46`

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
  __int16 v24; // [rsp+30h] [rbp-48h] BYREF
  char v25; // [rsp+32h] [rbp-46h]
  int v26; // [rsp+34h] [rbp-44h]
  __int16 v27; // [rsp+38h] [rbp-40h]
  __int128 v28; // [rsp+40h] [rbp-38h]
  __int16 v29; // [rsp+50h] [rbp-28h] BYREF
  char v30; // [rsp+52h] [rbp-26h]
  unsigned int v31; // [rsp+54h] [rbp-24h]
  __int16 v32; // [rsp+58h] [rbp-20h]
  __int64 v33; // [rsp+60h] [rbp-18h]
  void *v34; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    v24 = *((_WORD *)this + 1);
    v25 = *((_BYTE *)this + 4);
    v27 = 0;
    v13 = 0;
    Source = v11;
    v26 = 0;
    v28 = 0;
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
      v14 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v24, a2, a3);
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
      v26 = 1;
      v27 = a3;
      *(_QWORD *)&v28 = 0;
      *((_QWORD *)&v28 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v29 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v31 = a6;
    v30 = v17;
    v32 = a5;
    v33 = 0;
    v34 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v29);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( v25 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v24, v26 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v29,
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
0x180005d04  push    rbp
0x180005d06  push    rbx
0x180005d07  push    rsi
0x180005d08  push    rdi
0x180005d09  push    r12
0x180005d0b  push    r13
0x180005d0d  push    r14
0x180005d0f  push    r15
0x180005d11  mov     rbp, rsp
0x180005d14  sub     rsp, 78h
0x180005d18  mov     rdi, [rcx+18h]
0x180005d1c  mov     r13, r9
0x180005d1f  mov     r15, r8
0x180005d22  mov     r12, rdx
0x180005d25  mov     rbx, rcx
0x180005d28  test    rdi, rdi
0x180005d2b  jz      loc_180005ED5
0x180005d31  movzx   eax, word ptr [rcx+2]
0x180005d35  add     rdi, 0Ah
0x180005d39  mov     r8, [rcx+20h]
0x180005d3d  xorps   xmm0, xmm0
0x180005d40  mov     [rbp+var_48], ax
0x180005d44  mov     al, [rcx+4]
0x180005d47  mov     [rbp+var_46], al
0x180005d4a  xor     eax, eax
0x180005d4c  mov     [rbp+var_40], ax
0x180005d50  xor     r14b, r14b
0x180005d53  mov     [rbp+Source], rdi
0x180005d57  mov     [rbp+var_44], 0
0x180005d5e  movdqu  [rbp+var_38], xmm0
0x180005d63  jmp     short loc_180005D9D
0x180005d65  mov     r8, r15; unsigned __int64
0x180005d68  lea     rcx, [rbp+var_48]; this
0x180005d6c  mov     rdx, r12; void *
0x180005d6f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180005d74  test    eax, eax
0x180005d76  js      loc_180005E98
0x180005d7c  mov     r8, [rbp+Source]; unsigned __int8 *
0x180005d80  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180005d84  jz      loc_180005E68
0x180005d8a  mov     rcx, rbx; this
0x180005d8d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180005d92  mov     r8, [rbx+20h]; unsigned __int8 *
0x180005d96  mov     rdi, rax
0x180005d99  mov     [rbp+Source], rax
0x180005d9d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180005da1  lea     rcx, [rbp+var_48]; this
0x180005da5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180005daa  mov     sil, al
0x180005dad  test    al, al
0x180005daf  jnz     short loc_180005D65
0x180005db1  mov     rdi, [rbp+Source]
0x180005db5  mov     [rbx+20h], rdi
0x180005db9  xor     r8d, r8d
0x180005dbc  test    r14b, r14b
0x180005dbf  jnz     short loc_180005DE1
0x180005dc1  lea     rcx, [rbp+var_48]; this
0x180005dc5  mov     [rbp+var_44], 1
0x180005dcc  mov     [rbp+var_40], r15w
0x180005dd1  mov     qword ptr [rbp+var_38], r8
0x180005dd5  mov     qword ptr [rbp+var_38+8], r12
0x180005dd9  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180005dde  mov     r8, rax
0x180005de1  movzx   ecx, word ptr [rbx+6]
0x180005de5  mov     eax, [rbp+arg_28]
0x180005de8  mov     [rbp+var_28], cx
0x180005dec  mov     cl, [rbx+8]
0x180005def  mov     [rbp+var_24], eax
0x180005df2  mov     rax, [rbp+arg_20]
0x180005df6  mov     [rbp+var_26], cl
0x180005df9  lea     rcx, [rbp+var_28]; this
0x180005dfd  mov     [rbp+var_20], ax
0x180005e01  mov     [rbp+var_18], 0
0x180005e09  mov     [rbp+var_10], r13
0x180005e0d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180005e12  mov     rdx, [rbx+28h]
0x180005e16  mov     r9, [rbx+20h]
0x180005e1a  mov     rcx, rdx
0x180005e1d  sub     rcx, r9
0x180005e20  lea     rsi, [rax+r8]
0x180005e24  cmp     r9, rdx
0x180005e27  sbb     rax, rax
0x180005e2a  and     rax, rcx
0x180005e2d  cmp     rax, rsi
0x180005e30  jb      loc_180005ED5
0x180005e36  sub     rdx, rsi
0x180005e39  lea     rcx, [rsi+rdi]; Destination
0x180005e3d  sub     rdx, rdi; DestinationSize
0x180005e40  sub     r9, rdi; SourceSize
0x180005e43  mov     r8, rdi; Source
0x180005e46  call    cs:__imp_memmove_s
0x180005e4c  add     [rbx+20h], rsi
0x180005e50  test    r14b, r14b
0x180005e53  jnz     short loc_180005EAA
0x180005e55  mov     r8, [rbx+20h]; unsigned __int8 *
0x180005e59  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180005e5d  lea     rcx, [rbp+var_48]; this
0x180005e61  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180005e66  jmp     short loc_180005EBE
0x180005e68  mov     ecx, [rbp+arg_28]
0x180005e6b  mov     r9, r13; void *
0x180005e6e  mov     [rsp+78h+var_50], ecx; unsigned int
0x180005e72  mov     rcx, [rbp+arg_20]
0x180005e76  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180005e7b  mov     rcx, rbx; this
0x180005e7e  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180005e83  mov     [rbp+Source], rax
0x180005e87  mov     rdi, rax
0x180005e8a  test    rax, rax
0x180005e8d  jnz     short loc_180005E93
0x180005e8f  mov     al, 1
0x180005e91  jmp     short loc_180005ED7
0x180005e93  mov     r14b, 1
0x180005e96  jmp     short loc_180005E9C
0x180005e98  mov     [rbp+Source], rdi
0x180005e9c  test    sil, sil
0x180005e9f  jnz     loc_180005DB9
0x180005ea5  jmp     loc_180005DB5
0x180005eaa  cmp     [rbp+var_46], 0
0x180005eae  jz      short loc_180005EBE
0x180005eb0  mov     edx, [rbp+var_44]
0x180005eb3  lea     rcx, [rbp+var_48]; this
0x180005eb7  inc     edx; unsigned int
0x180005eb9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180005ebe  mov     r8, [rbx+20h]; unsigned __int8 *
0x180005ec2  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180005ec6  lea     rcx, [rbp+var_28]; this
0x180005eca  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180005ecf  mov     byte ptr [rbx+38h], 1
0x180005ed3  jmp     short loc_180005E8F
0x180005ed5  xor     al, al
0x180005ed7  add     rsp, 78h
0x180005edb  pop     r15
0x180005edd  pop     r14
0x180005edf  pop     r13
0x180005ee1  pop     r12
0x180005ee3  pop     rdi
0x180005ee4  pop     rsi
0x180005ee5  pop     rbx
0x180005ee6  pop     rbp
0x180005ee7  retn
```
