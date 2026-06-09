# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009288`
- end: `0x18000946c`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009194`

## callees

- `0x180006404`
- `0x180006750`
- `0x1800070dc`
- `0x180008ce4`
- `0x180009288`
- `0x18000a034`
- `0x18000a85c`
- `0x18000ab0c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800093ca`
- `msvcrt!memmove_s` at `0x1800093ca`

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
0x180009288  push    rbp
0x18000928a  push    rbx
0x18000928b  push    rsi
0x18000928c  push    rdi
0x18000928d  push    r12
0x18000928f  push    r13
0x180009291  push    r14
0x180009293  push    r15
0x180009295  mov     rbp, rsp
0x180009298  sub     rsp, 78h
0x18000929c  mov     rdi, [rcx+18h]
0x1800092a0  mov     r13, r9
0x1800092a3  mov     r15, r8
0x1800092a6  mov     r12, rdx
0x1800092a9  mov     rbx, rcx
0x1800092ac  test    rdi, rdi
0x1800092af  jz      loc_180009459
0x1800092b5  movzx   eax, word ptr [rcx+2]
0x1800092b9  add     rdi, 0Ah
0x1800092bd  mov     r8, [rcx+20h]
0x1800092c1  xorps   xmm0, xmm0
0x1800092c4  mov     [rbp+var_48], ax
0x1800092c8  mov     al, [rcx+4]
0x1800092cb  mov     [rbp+var_46], al
0x1800092ce  xor     eax, eax
0x1800092d0  mov     [rbp+var_40], ax
0x1800092d4  xor     r14b, r14b
0x1800092d7  mov     [rbp+Source], rdi
0x1800092db  mov     [rbp+var_44], 0
0x1800092e2  movdqu  [rbp+var_38], xmm0
0x1800092e7  jmp     short loc_180009321
0x1800092e9  mov     r8, r15; unsigned __int64
0x1800092ec  lea     rcx, [rbp+var_48]; this
0x1800092f0  mov     rdx, r12; void *
0x1800092f3  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800092f8  test    eax, eax
0x1800092fa  js      loc_18000941C
0x180009300  mov     r8, [rbp+Source]; unsigned __int8 *
0x180009304  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180009308  jz      loc_1800093EC
0x18000930e  mov     rcx, rbx; this
0x180009311  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180009316  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000931a  mov     rdi, rax
0x18000931d  mov     [rbp+Source], rax
0x180009321  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180009325  lea     rcx, [rbp+var_48]; this
0x180009329  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000932e  mov     sil, al
0x180009331  test    al, al
0x180009333  jnz     short loc_1800092E9
0x180009335  mov     rdi, [rbp+Source]
0x180009339  mov     [rbx+20h], rdi
0x18000933d  xor     r8d, r8d
0x180009340  test    r14b, r14b
0x180009343  jnz     short loc_180009365
0x180009345  lea     rcx, [rbp+var_48]; this
0x180009349  mov     [rbp+var_44], 1
0x180009350  mov     [rbp+var_40], r15w
0x180009355  mov     qword ptr [rbp+var_38], r8
0x180009359  mov     qword ptr [rbp+var_38+8], r12
0x18000935d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180009362  mov     r8, rax
0x180009365  movzx   ecx, word ptr [rbx+6]
0x180009369  mov     eax, [rbp+arg_28]
0x18000936c  mov     [rbp+var_28], cx
0x180009370  mov     cl, [rbx+8]
0x180009373  mov     [rbp+var_24], eax
0x180009376  mov     rax, [rbp+arg_20]
0x18000937a  mov     [rbp+var_26], cl
0x18000937d  lea     rcx, [rbp+var_28]; this
0x180009381  mov     [rbp+var_20], ax
0x180009385  mov     [rbp+var_18], 0
0x18000938d  mov     [rbp+var_10], r13
0x180009391  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180009396  mov     rdx, [rbx+28h]
0x18000939a  mov     r9, [rbx+20h]
0x18000939e  mov     rcx, rdx
0x1800093a1  sub     rcx, r9
0x1800093a4  lea     rsi, [rax+r8]
0x1800093a8  cmp     r9, rdx
0x1800093ab  sbb     rax, rax
0x1800093ae  and     rax, rcx
0x1800093b1  cmp     rax, rsi
0x1800093b4  jb      loc_180009459
0x1800093ba  sub     rdx, rsi
0x1800093bd  lea     rcx, [rsi+rdi]; Destination
0x1800093c1  sub     rdx, rdi; DestinationSize
0x1800093c4  sub     r9, rdi; SourceSize
0x1800093c7  mov     r8, rdi; Source
0x1800093ca  call    cs:__imp_memmove_s
0x1800093d0  add     [rbx+20h], rsi
0x1800093d4  test    r14b, r14b
0x1800093d7  jnz     short loc_18000942E
0x1800093d9  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800093dd  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800093e1  lea     rcx, [rbp+var_48]; this
0x1800093e5  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800093ea  jmp     short loc_180009442
0x1800093ec  mov     ecx, [rbp+arg_28]
0x1800093ef  mov     r9, r13; void *
0x1800093f2  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800093f6  mov     rcx, [rbp+arg_20]
0x1800093fa  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800093ff  mov     rcx, rbx; this
0x180009402  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180009407  mov     [rbp+Source], rax
0x18000940b  mov     rdi, rax
0x18000940e  test    rax, rax
0x180009411  jnz     short loc_180009417
0x180009413  mov     al, 1
0x180009415  jmp     short loc_18000945B
0x180009417  mov     r14b, 1
0x18000941a  jmp     short loc_180009420
0x18000941c  mov     [rbp+Source], rdi
0x180009420  test    sil, sil
0x180009423  jnz     loc_18000933D
0x180009429  jmp     loc_180009339
0x18000942e  cmp     [rbp+var_46], 0
0x180009432  jz      short loc_180009442
0x180009434  mov     edx, [rbp+var_44]
0x180009437  lea     rcx, [rbp+var_48]; this
0x18000943b  inc     edx; unsigned int
0x18000943d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180009442  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009446  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000944a  lea     rcx, [rbp+var_28]; this
0x18000944e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009453  mov     byte ptr [rbx+38h], 1
0x180009457  jmp     short loc_180009413
0x180009459  xor     al, al
0x18000945b  add     rsp, 78h
0x18000945f  pop     r15
0x180009461  pop     r14
0x180009463  pop     r13
0x180009465  pop     r12
0x180009467  pop     rdi
0x180009468  pop     rsi
0x180009469  pop     rbx
0x18000946a  pop     rbp
0x18000946b  retn
```
