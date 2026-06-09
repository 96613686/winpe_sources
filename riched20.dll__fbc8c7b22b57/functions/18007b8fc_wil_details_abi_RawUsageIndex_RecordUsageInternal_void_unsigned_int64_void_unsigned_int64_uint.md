# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18007b8fc`
- end: `0x18007bae7`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `491`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007b808`

## callees

- `0x1800787cc`
- `0x180078dec`
- `0x180079a08`
- `0x18007b008`
- `0x18007b8fc`
- `0x18007c598`
- `0x18007cd68`
- `0x18007d138`

## import_xrefs

- `msvcrt!memmove_s` at `0x18007ba3e`
- `msvcrt!memmove_s` at `0x18007ba3e`

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
0x18007b8fc  push    rbp
0x18007b8fe  push    rbx
0x18007b8ff  push    rsi
0x18007b900  push    rdi
0x18007b901  push    r12
0x18007b903  push    r13
0x18007b905  push    r14
0x18007b907  push    r15
0x18007b909  mov     rbp, rsp
0x18007b90c  sub     rsp, 78h
0x18007b910  mov     rdi, [rcx+18h]
0x18007b914  mov     r13, r9
0x18007b917  mov     r15, r8
0x18007b91a  mov     r12, rdx
0x18007b91d  mov     rbx, rcx
0x18007b920  test    rdi, rdi
0x18007b923  jz      loc_18007BAD3
0x18007b929  movzx   eax, word ptr [rcx+2]
0x18007b92d  add     rdi, 0Ah
0x18007b931  mov     r8, [rcx+20h]
0x18007b935  xorps   xmm0, xmm0
0x18007b938  mov     [rbp+var_48], ax
0x18007b93c  mov     al, [rcx+4]
0x18007b93f  mov     [rbp+var_46], al
0x18007b942  xor     eax, eax
0x18007b944  mov     [rbp+var_40], ax
0x18007b948  xor     r14b, r14b
0x18007b94b  mov     [rbp+Source], rdi
0x18007b94f  mov     [rbp+var_44], 0
0x18007b956  movdqu  [rbp+var_38], xmm0
0x18007b95b  jmp     short loc_18007B995
0x18007b95d  mov     r8, r15; unsigned __int64
0x18007b960  lea     rcx, [rbp+var_48]; this
0x18007b964  mov     rdx, r12; void *
0x18007b967  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18007b96c  test    eax, eax
0x18007b96e  js      loc_18007BA96
0x18007b974  mov     r8, [rbp+Source]; unsigned __int8 *
0x18007b978  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x18007b97c  jz      loc_18007BA66
0x18007b982  mov     rcx, rbx; this
0x18007b985  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18007b98a  mov     r8, [rbx+20h]; unsigned __int8 *
0x18007b98e  mov     rdi, rax
0x18007b991  mov     [rbp+Source], rax
0x18007b995  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18007b999  lea     rcx, [rbp+var_48]; this
0x18007b99d  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18007b9a2  mov     sil, al
0x18007b9a5  test    al, al
0x18007b9a7  jnz     short loc_18007B95D
0x18007b9a9  mov     rdi, [rbp+Source]
0x18007b9ad  mov     [rbx+20h], rdi
0x18007b9b1  xor     r8d, r8d
0x18007b9b4  test    r14b, r14b
0x18007b9b7  jnz     short loc_18007B9D9
0x18007b9b9  lea     rcx, [rbp+var_48]; this
0x18007b9bd  mov     [rbp+var_44], 1
0x18007b9c4  mov     [rbp+var_40], r15w
0x18007b9c9  mov     qword ptr [rbp+var_38], r8
0x18007b9cd  mov     qword ptr [rbp+var_38+8], r12
0x18007b9d1  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18007b9d6  mov     r8, rax
0x18007b9d9  movzx   ecx, word ptr [rbx+6]
0x18007b9dd  mov     eax, [rbp+arg_28]
0x18007b9e0  mov     [rbp+var_28], cx
0x18007b9e4  mov     cl, [rbx+8]
0x18007b9e7  mov     [rbp+var_24], eax
0x18007b9ea  mov     rax, [rbp+arg_20]
0x18007b9ee  mov     [rbp+var_26], cl
0x18007b9f1  lea     rcx, [rbp+var_28]; this
0x18007b9f5  mov     [rbp+var_20], ax
0x18007b9f9  mov     [rbp+var_18], 0
0x18007ba01  mov     [rbp+var_10], r13
0x18007ba05  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18007ba0a  mov     rdx, [rbx+28h]
0x18007ba0e  mov     r9, [rbx+20h]
0x18007ba12  mov     rcx, rdx
0x18007ba15  sub     rcx, r9
0x18007ba18  lea     rsi, [rax+r8]
0x18007ba1c  cmp     r9, rdx
0x18007ba1f  sbb     rax, rax
0x18007ba22  and     rax, rcx
0x18007ba25  cmp     rax, rsi
0x18007ba28  jb      loc_18007BAD3
0x18007ba2e  sub     rdx, rsi
0x18007ba31  lea     rcx, [rsi+rdi]; Destination
0x18007ba35  sub     rdx, rdi; DestinationSize
0x18007ba38  sub     r9, rdi; SourceSize
0x18007ba3b  mov     r8, rdi; Source
0x18007ba3e  call    cs:__imp_memmove_s
0x18007ba45  nop     dword ptr [rax+rax+00h]
0x18007ba4a  add     [rbx+20h], rsi
0x18007ba4e  test    r14b, r14b
0x18007ba51  jnz     short loc_18007BAA8
0x18007ba53  mov     r8, [rbx+20h]; unsigned __int8 *
0x18007ba57  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18007ba5b  lea     rcx, [rbp+var_48]; this
0x18007ba5f  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18007ba64  jmp     short loc_18007BABC
0x18007ba66  mov     ecx, [rbp+arg_28]
0x18007ba69  mov     r9, r13; void *
0x18007ba6c  mov     [rsp+78h+var_50], ecx; unsigned int
0x18007ba70  mov     rcx, [rbp+arg_20]
0x18007ba74  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18007ba79  mov     rcx, rbx; this
0x18007ba7c  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18007ba81  mov     [rbp+Source], rax
0x18007ba85  mov     rdi, rax
0x18007ba88  test    rax, rax
0x18007ba8b  jnz     short loc_18007BA91
0x18007ba8d  mov     al, 1
0x18007ba8f  jmp     short loc_18007BAD5
0x18007ba91  mov     r14b, 1
0x18007ba94  jmp     short loc_18007BA9A
0x18007ba96  mov     [rbp+Source], rdi
0x18007ba9a  test    sil, sil
0x18007ba9d  jnz     loc_18007B9B1
0x18007baa3  jmp     loc_18007B9AD
0x18007baa8  cmp     [rbp+var_46], 0
0x18007baac  jz      short loc_18007BABC
0x18007baae  mov     edx, [rbp+var_44]
0x18007bab1  lea     rcx, [rbp+var_48]; this
0x18007bab5  inc     edx; unsigned int
0x18007bab7  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18007babc  mov     r8, [rbx+20h]; unsigned __int8 *
0x18007bac0  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18007bac4  lea     rcx, [rbp+var_28]; this
0x18007bac8  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18007bacd  mov     byte ptr [rbx+38h], 1
0x18007bad1  jmp     short loc_18007BA8D
0x18007bad3  xor     al, al
0x18007bad5  add     rsp, 78h
0x18007bad9  pop     r15
0x18007badb  pop     r14
0x18007badd  pop     r13
0x18007badf  pop     r12
0x18007bae1  pop     rdi
0x18007bae2  pop     rsi
0x18007bae3  pop     rbx
0x18007bae4  pop     rbp
0x18007bae5  retn
```
