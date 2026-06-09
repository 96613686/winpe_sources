# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001b6ac`
- end: `0x18001b886`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b5c0`

## callees

- `0x180017a38`
- `0x180017d34`
- `0x180019e38`
- `0x18001b0bc`
- `0x18001b6ac`
- `0x18001c1dc`
- `0x18001c910`
- `0x18001cbb4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001b81c`
- `msvcrt!memmove_s` at `0x18001b81c`

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
  __int16 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+32h] [rbp-3Eh]
  int v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h]
  __int16 v27; // [rsp+50h] [rbp-20h] BYREF
  char v28; // [rsp+52h] [rbp-1Eh]
  unsigned int v29; // [rsp+54h] [rbp-1Ch]
  __int16 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  void *v32; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    v22 = *((_WORD *)this + 1);
    v23 = *((_BYTE *)this + 4);
    v25 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    v24 = 0;
    v26 = 0;
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
      v15 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v22, a2, a3);
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
                                  v34,
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
    v24 = 1;
    v25 = a3;
    *(_QWORD *)&v26 = 0;
    *((_QWORD *)&v26 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v27 = *((_WORD *)this + 3);
    v28 = *((_BYTE *)this + 8);
    v29 = v13;
    v30 = v14;
    v31 = 0;
    v32 = v34;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( v23 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v22, v24 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
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
0x18001b6ac  mov     [rsp-38h+arg_8], rbx
0x18001b6b1  mov     [rsp-38h+arg_18], r9
0x18001b6b6  push    rbp
0x18001b6b7  push    rsi
0x18001b6b8  push    rdi
0x18001b6b9  push    r12
0x18001b6bb  push    r13
0x18001b6bd  push    r14
0x18001b6bf  push    r15
0x18001b6c1  mov     rbp, rsp
0x18001b6c4  sub     rsp, 70h
0x18001b6c8  mov     rdi, [rcx+18h]
0x18001b6cc  mov     r14, r8
0x18001b6cf  mov     r15, rdx
0x18001b6d2  mov     rbx, rcx
0x18001b6d5  test    rdi, rdi
0x18001b6d8  jz      loc_18001B86C
0x18001b6de  movzx   eax, word ptr [rcx+2]
0x18001b6e2  add     rdi, 0Ah
0x18001b6e6  mov     [rbp+var_40], ax
0x18001b6ea  xorps   xmm0, xmm0
0x18001b6ed  mov     al, [rcx+4]
0x18001b6f0  mov     [rbp+var_3E], al
0x18001b6f3  xor     eax, eax
0x18001b6f5  mov     [rbp+var_38], ax
0x18001b6f9  xor     sil, sil
0x18001b6fc  mov     [rbp+arg_0], rdi
0x18001b700  mov     [rbp+var_3C], 0
0x18001b707  movdqu  [rbp+var_30], xmm0
0x18001b70c  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b710  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001b714  lea     rcx, [rbp+var_40]; this
0x18001b718  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001b71d  mov     r12d, [rbp+arg_28]
0x18001b721  mov     r13, [rbp+arg_20]
0x18001b725  test    al, al
0x18001b727  jz      short loc_18001B790
0x18001b729  mov     r8, r14; unsigned __int64
0x18001b72c  lea     rcx, [rbp+var_40]; this
0x18001b730  mov     rdx, r15; void *
0x18001b733  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001b738  test    eax, eax
0x18001b73a  js      short loc_18001B782
0x18001b73c  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001b740  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001b744  mov     rcx, rbx; this
0x18001b747  jz      short loc_18001B757
0x18001b749  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001b74e  mov     rdi, rax
0x18001b751  mov     [rbp+arg_0], rax
0x18001b755  jmp     short loc_18001B70C
0x18001b757  mov     r9, [rbp+arg_18]; void *
0x18001b75b  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001b760  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001b765  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001b76a  mov     [rbp+arg_0], rax
0x18001b76e  mov     rdi, rax
0x18001b771  test    rax, rax
0x18001b774  jnz     short loc_18001B77D
0x18001b776  mov     al, 1
0x18001b778  jmp     loc_18001B86E
0x18001b77d  mov     sil, 1
0x18001b780  jmp     short loc_18001B786
0x18001b782  mov     [rbp+arg_0], rdi
0x18001b786  xor     r8d, r8d
0x18001b789  test    sil, sil
0x18001b78c  jnz     short loc_18001B7BC
0x18001b78e  jmp     short loc_18001B798
0x18001b790  mov     rdi, [rbp+arg_0]
0x18001b794  mov     [rbx+20h], rdi
0x18001b798  lea     rcx, [rbp+var_40]; this
0x18001b79c  mov     [rbp+var_3C], 1
0x18001b7a3  mov     [rbp+var_38], r14w
0x18001b7a8  mov     qword ptr [rbp+var_30], 0
0x18001b7b0  mov     qword ptr [rbp+var_30+8], r15
0x18001b7b4  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001b7b9  mov     r8, rax
0x18001b7bc  movzx   ecx, word ptr [rbx+6]
0x18001b7c0  mov     rax, [rbp+arg_18]
0x18001b7c4  mov     [rbp+var_20], cx
0x18001b7c8  mov     cl, [rbx+8]
0x18001b7cb  mov     [rbp+var_1E], cl
0x18001b7ce  lea     rcx, [rbp+var_20]; this
0x18001b7d2  mov     [rbp+var_1C], r12d
0x18001b7d6  mov     [rbp+var_18], r13w
0x18001b7db  mov     [rbp+var_10], 0
0x18001b7e3  mov     [rbp+var_8], rax
0x18001b7e7  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001b7ec  mov     rdx, [rbx+28h]
0x18001b7f0  mov     r9, [rbx+20h]
0x18001b7f4  mov     rcx, rdx
0x18001b7f7  sub     rcx, r9
0x18001b7fa  lea     r14, [rax+r8]
0x18001b7fe  cmp     r9, rdx
0x18001b801  sbb     rax, rax
0x18001b804  and     rax, rcx
0x18001b807  cmp     rax, r14
0x18001b80a  jb      short loc_18001B86C
0x18001b80c  sub     rdx, r14
0x18001b80f  lea     rcx, [r14+rdi]; Destination
0x18001b813  sub     rdx, rdi; DestinationSize
0x18001b816  sub     r9, rdi; SourceSize
0x18001b819  mov     r8, rdi; Source
0x18001b81c  call    cs:__imp_memmove_s
0x18001b822  add     [rbx+20h], r14
0x18001b826  test    sil, sil
0x18001b829  jnz     short loc_18001B83E
0x18001b82b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b82f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001b833  lea     rcx, [rbp+var_40]; this
0x18001b837  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001b83c  jmp     short loc_18001B852
0x18001b83e  cmp     [rbp+var_3E], 0
0x18001b842  jz      short loc_18001B852
0x18001b844  mov     edx, [rbp+var_3C]
0x18001b847  lea     rcx, [rbp+var_40]; this
0x18001b84b  inc     edx; unsigned int
0x18001b84d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001b852  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001b856  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001b85a  lea     rcx, [rbp+var_20]; this
0x18001b85e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001b863  mov     byte ptr [rbx+38h], 1
0x18001b867  jmp     loc_18001B776
0x18001b86c  xor     al, al
0x18001b86e  mov     rbx, [rsp+70h+arg_8]
0x18001b876  add     rsp, 70h
0x18001b87a  pop     r15
0x18001b87c  pop     r14
0x18001b87e  pop     r13
0x18001b880  pop     r12
0x18001b882  pop     rdi
0x18001b883  pop     rsi
0x18001b884  pop     rbp
0x18001b885  retn
```
