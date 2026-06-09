# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180011788`
- end: `0x18001196c`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011694`

## callees

- `0x180010454`
- `0x180010ad0`
- `0x180010ccc`
- `0x180011258`
- `0x180011788`
- `0x180011d58`
- `0x180012144`
- `0x1800122b4`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800118ca`
- `msvcrt!memmove_s` at `0x1800118ca`

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
0x180011788  push    rbp
0x18001178a  push    rbx
0x18001178b  push    rsi
0x18001178c  push    rdi
0x18001178d  push    r12
0x18001178f  push    r13
0x180011791  push    r14
0x180011793  push    r15
0x180011795  mov     rbp, rsp
0x180011798  sub     rsp, 78h
0x18001179c  mov     rdi, [rcx+18h]
0x1800117a0  mov     r13, r9
0x1800117a3  mov     r15, r8
0x1800117a6  mov     r12, rdx
0x1800117a9  mov     rbx, rcx
0x1800117ac  test    rdi, rdi
0x1800117af  jz      loc_180011959
0x1800117b5  movzx   eax, word ptr [rcx+2]
0x1800117b9  add     rdi, 0Ah
0x1800117bd  mov     r8, [rcx+20h]
0x1800117c1  xorps   xmm0, xmm0
0x1800117c4  mov     [rbp+var_48], ax
0x1800117c8  mov     al, [rcx+4]
0x1800117cb  mov     [rbp+var_46], al
0x1800117ce  xor     eax, eax
0x1800117d0  mov     [rbp+var_40], ax
0x1800117d4  xor     r14b, r14b
0x1800117d7  mov     [rbp+Source], rdi
0x1800117db  mov     [rbp+var_44], 0
0x1800117e2  movdqu  [rbp+var_38], xmm0
0x1800117e7  jmp     short loc_180011821
0x1800117e9  mov     r8, r15; unsigned __int64
0x1800117ec  lea     rcx, [rbp+var_48]; this
0x1800117f0  mov     rdx, r12; void *
0x1800117f3  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800117f8  test    eax, eax
0x1800117fa  js      loc_18001191C
0x180011800  mov     r8, [rbp+Source]; unsigned __int8 *
0x180011804  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180011808  jz      loc_1800118EC
0x18001180e  mov     rcx, rbx; this
0x180011811  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180011816  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001181a  mov     rdi, rax
0x18001181d  mov     [rbp+Source], rax
0x180011821  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180011825  lea     rcx, [rbp+var_48]; this
0x180011829  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001182e  mov     sil, al
0x180011831  test    al, al
0x180011833  jnz     short loc_1800117E9
0x180011835  mov     rdi, [rbp+Source]
0x180011839  mov     [rbx+20h], rdi
0x18001183d  xor     r8d, r8d
0x180011840  test    r14b, r14b
0x180011843  jnz     short loc_180011865
0x180011845  lea     rcx, [rbp+var_48]; this
0x180011849  mov     [rbp+var_44], 1
0x180011850  mov     [rbp+var_40], r15w
0x180011855  mov     qword ptr [rbp+var_38], r8
0x180011859  mov     qword ptr [rbp+var_38+8], r12
0x18001185d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180011862  mov     r8, rax
0x180011865  movzx   ecx, word ptr [rbx+6]
0x180011869  mov     eax, [rbp+arg_28]
0x18001186c  mov     [rbp+var_28], cx
0x180011870  mov     cl, [rbx+8]
0x180011873  mov     [rbp+var_24], eax
0x180011876  mov     rax, [rbp+arg_20]
0x18001187a  mov     [rbp+var_26], cl
0x18001187d  lea     rcx, [rbp+var_28]; this
0x180011881  mov     [rbp+var_20], ax
0x180011885  mov     [rbp+var_18], 0
0x18001188d  mov     [rbp+var_10], r13
0x180011891  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180011896  mov     rdx, [rbx+28h]
0x18001189a  mov     r9, [rbx+20h]
0x18001189e  mov     rcx, rdx
0x1800118a1  sub     rcx, r9
0x1800118a4  lea     rsi, [rax+r8]
0x1800118a8  cmp     r9, rdx
0x1800118ab  sbb     rax, rax
0x1800118ae  and     rax, rcx
0x1800118b1  cmp     rax, rsi
0x1800118b4  jb      loc_180011959
0x1800118ba  sub     rdx, rsi
0x1800118bd  lea     rcx, [rsi+rdi]; Destination
0x1800118c1  sub     rdx, rdi; DestinationSize
0x1800118c4  sub     r9, rdi; SourceSize
0x1800118c7  mov     r8, rdi; Source
0x1800118ca  call    cs:__imp_memmove_s
0x1800118d0  add     [rbx+20h], rsi
0x1800118d4  test    r14b, r14b
0x1800118d7  jnz     short loc_18001192E
0x1800118d9  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800118dd  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800118e1  lea     rcx, [rbp+var_48]; this
0x1800118e5  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800118ea  jmp     short loc_180011942
0x1800118ec  mov     ecx, [rbp+arg_28]
0x1800118ef  mov     r9, r13; void *
0x1800118f2  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800118f6  mov     rcx, [rbp+arg_20]
0x1800118fa  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800118ff  mov     rcx, rbx; this
0x180011902  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180011907  mov     [rbp+Source], rax
0x18001190b  mov     rdi, rax
0x18001190e  test    rax, rax
0x180011911  jnz     short loc_180011917
0x180011913  mov     al, 1
0x180011915  jmp     short loc_18001195B
0x180011917  mov     r14b, 1
0x18001191a  jmp     short loc_180011920
0x18001191c  mov     [rbp+Source], rdi
0x180011920  test    sil, sil
0x180011923  jnz     loc_18001183D
0x180011929  jmp     loc_180011839
0x18001192e  cmp     [rbp+var_46], 0
0x180011932  jz      short loc_180011942
0x180011934  mov     edx, [rbp+var_44]
0x180011937  lea     rcx, [rbp+var_48]; this
0x18001193b  inc     edx; unsigned int
0x18001193d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180011942  mov     r8, [rbx+20h]; unsigned __int8 *
0x180011946  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001194a  lea     rcx, [rbp+var_28]; this
0x18001194e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180011953  mov     byte ptr [rbx+38h], 1
0x180011957  jmp     short loc_180011913
0x180011959  xor     al, al
0x18001195b  add     rsp, 78h
0x18001195f  pop     r15
0x180011961  pop     r14
0x180011963  pop     r13
0x180011965  pop     r12
0x180011967  pop     rdi
0x180011968  pop     rsi
0x180011969  pop     rbx
0x18001196a  pop     rbp
0x18001196b  retn
```
