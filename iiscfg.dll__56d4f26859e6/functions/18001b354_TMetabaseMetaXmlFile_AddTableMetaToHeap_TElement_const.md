# TMetabaseMetaXmlFile::AddTableMetaToHeap(TElement const &)

- ea: `0x18001b354`
- end: `0x18001b622`
- name: `?AddTableMetaToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@@Z`
- size: `718`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TElement *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001c240`

## callees

- `0x180019128`
- `0x18001a2e0`
- `0x18001b188`
- `0x18001b354`
- `0x18001c814`
- `0x18001dd08`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!_wtol` at `0x18001b400`
- `msvcrt!_wtol` at `0x18001b439`
- `msvcrt!_wtol` at `0x18001b400`
- `msvcrt!_wtol` at `0x18001b439`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddTableMetaToHeap(TMetabaseMetaXmlFile *this, const struct TElement *a2)
{
  TMetabaseMetaXmlFile *v4; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // rax
  TMetabaseMetaXmlFile *v6; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v7; // rax
  __int64 (__fastcall *v8)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  TMetabaseMetaXmlFile *v9; // rcx
  const wchar_t *v10; // rcx
  unsigned int v11; // eax
  __int64 (__fastcall *v12)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  TMetabaseMetaXmlFile *v13; // rcx
  const wchar_t *v14; // rcx
  unsigned int v15; // eax
  TMetabaseMetaXmlFile *v16; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v17; // rax
  TMetabaseMetaXmlFile *v18; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v19; // rax
  TMetabaseMetaXmlFile *v20; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v21; // rax
  __int64 (__fastcall *v22)(TMetabaseMetaXmlFile *, __int64); // rbx
  TMetabaseMetaXmlFile *v23; // rcx
  __int64 v24; // rdx
  TMetabaseMetaXmlFile *v25; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v26; // rax
  TMetabaseMetaXmlFile *v27; // rcx
  __int64 v28; // rdx
  int v29; // r14d
  void (***v30)(_QWORD, const wchar_t *, ...); // rdi
  void (*v31)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v32; // rax
  TMetabaseMetaXmlFile *v33; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v34; // rax
  TMetabaseMetaXmlFile *v35; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v36; // rax
  int v37; // eax
  unsigned int v38; // edx
  int v39; // [rsp+20h] [rbp-49h] BYREF
  unsigned int v40; // [rsp+24h] [rbp-45h]
  _DWORD v41[26]; // [rsp+28h] [rbp-41h] BYREF

  memset_0(v41, 0, 0x64u);
  v39 = *((_DWORD *)this + 635);
  v40 = *((_DWORD *)this + 636);
  Attribute = TMetabaseMetaXmlFile::GetAttribute(v4, a2, (TMetabaseMetaXmlFile *)((char *)this + 664));
  v41[0] = TMetabaseMetaXmlFile::AddStringToHeap(
             this,
             (const struct TMetabaseMetaXmlFile::TAttr *)((char *)Attribute + 16));
  v7 = TMetabaseMetaXmlFile::GetAttribute(v6, a2, (TMetabaseMetaXmlFile *)((char *)this + 696));
  v41[1] = TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v7 + 16));
  v8 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
  v10 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                       v9,
                                       a2,
                                       (TMetabaseMetaXmlFile *)((char *)this + 312))
                         + 3);
  if ( v10 )
    v11 = _wtol(v10);
  else
    v11 = 0;
  v41[2] = v8(this, v11);
  v12 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
  v14 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                       v13,
                                       a2,
                                       (TMetabaseMetaXmlFile *)((char *)this + 456))
                         + 3);
  if ( v14 )
    v15 = _wtol(v14);
  else
    v15 = 0;
  v41[3] = v12(this, v15);
  v17 = TMetabaseMetaXmlFile::GetAttribute(v16, a2, (TMetabaseMetaXmlFile *)((char *)this + 616));
  v41[4] = TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v17 + 16));
  v19 = TMetabaseMetaXmlFile::GetAttribute(v18, a2, (TMetabaseMetaXmlFile *)((char *)this + 632));
  v41[5] = TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v19 + 16));
  v41[6] = 0;
  v21 = TMetabaseMetaXmlFile::GetAttribute(v20, a2, (TMetabaseMetaXmlFile *)((char *)this + 600));
  v22 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL);
  v23 = this;
  if ( *((_QWORD *)v21 + 1) )
  {
    v24 = (unsigned int)TMetabaseMetaXmlFile::StringToFlagValue(
                          this,
                          (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v21 + 16),
                          L"TABLEMETA",
                          9);
    v23 = this;
  }
  else
  {
    v24 = 0;
  }
  v41[7] = v22(v23, v24);
  v26 = TMetabaseMetaXmlFile::GetAttribute(v25, a2, (TMetabaseMetaXmlFile *)((char *)this + 712));
  v27 = this;
  if ( *((_QWORD *)v26 + 1) )
  {
    v29 = TMetabaseMetaXmlFile::StringToFlagValue(
            this,
            (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v26 + 16),
            L"TABLEMETA",
            10);
    if ( (v29 & 0x504) != 0 )
    {
      v30 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 322);
      v31 = **v30;
      v32 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(this, v40);
      v31(
        v30,
        L"Warning - Table (%s) - Some TableMeta::MetaFlagsEx should be inferred (resetting these flags).  The following fl"
         "ags should NOT be specified by the user.  These flags are inferred:fTABLEMETA_ISCONTAINED | fTABLEMETA_EXTENDED"
         " | fTABLEMETA_USERDEFINED\n",
        v32);
      v29 &= 0xFFFFFAFB;
    }
    v27 = this;
    v28 = v29 | 0x400u;
  }
  else
  {
    v28 = 1024;
  }
  v41[8] = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL))(v27, v28);
  v34 = TMetabaseMetaXmlFile::GetAttribute(v33, a2, (TMetabaseMetaXmlFile *)((char *)this + 360));
  v41[12] = TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v34 + 16));
  v36 = TMetabaseMetaXmlFile::GetAttribute(v35, a2, (TMetabaseMetaXmlFile *)((char *)this + 408));
  v41[13] = TMetabaseMetaXmlFile::AddStringToHeap(this, (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v36 + 16));
  v37 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, int *, __int64))(*(_QWORD *)this + 112LL))(this, &v39, 1);
  v38 = v40;
  *((_DWORD *)this + 637) = v37;
  TMetabaseMetaXmlFile::AddServerWiringMetaToHeap(this, v38, 0);
  *((_DWORD *)this + 643) = 0;
  *((_DWORD *)this + 634) = 0;
  TMetabaseMetaXmlFile::AddColumnMetaByReference(this);
}

```

## disassembly

```asm
0x18001b354  mov     [rsp-8+arg_10], rbx
0x18001b359  push    rbp
0x18001b35a  push    rsi
0x18001b35b  push    rdi
0x18001b35c  push    r14
0x18001b35e  push    r15
0x18001b360  lea     rbp, [rsp-37h]
0x18001b365  sub     rsp, 0A0h
0x18001b36c  mov     rax, cs:__security_cookie
0x18001b373  xor     rax, rsp
0x18001b376  mov     [rbp+57h+var_30], rax
0x18001b37a  mov     r15, rdx
0x18001b37d  mov     rsi, rcx
0x18001b380  xor     edx, edx; Val
0x18001b382  lea     rcx, [rbp+57h+var_98]; void *
0x18001b386  lea     r8d, [rdx+64h]; Size
0x18001b38a  call    memset_0
0x18001b38f  mov     eax, [rsi+9ECh]
0x18001b395  lea     r8, [rsi+298h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b39c  mov     [rbp+57h+var_A0], eax
0x18001b39f  mov     rdx, r15; struct TElement *
0x18001b3a2  mov     eax, [rsi+9F0h]
0x18001b3a8  mov     [rbp+57h+var_9C], eax
0x18001b3ab  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b3b0  mov     rcx, rsi; this
0x18001b3b3  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b3b7  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b3bc  lea     r8, [rsi+2B8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b3c3  mov     [rbp+57h+var_98], eax
0x18001b3c6  mov     rdx, r15; struct TElement *
0x18001b3c9  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b3ce  mov     rcx, rsi; this
0x18001b3d1  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b3d5  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b3da  mov     [rbp+57h+var_94], eax
0x18001b3dd  lea     r8, [rsi+138h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b3e4  mov     rax, [rsi]
0x18001b3e7  mov     rdx, r15; struct TElement *
0x18001b3ea  mov     rbx, [rax+10h]
0x18001b3ee  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b3f3  mov     rcx, [rax+18h]; String
0x18001b3f7  test    rcx, rcx
0x18001b3fa  jnz     short loc_18001B400
0x18001b3fc  xor     eax, eax
0x18001b3fe  jmp     short loc_18001B406
0x18001b400  call    cs:__imp__wtol
0x18001b406  mov     edx, eax
0x18001b408  mov     rcx, rsi
0x18001b40b  mov     rax, rbx
0x18001b40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b413  mov     [rbp+57h+var_90], eax
0x18001b416  lea     r8, [rsi+1C8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b41d  mov     rax, [rsi]
0x18001b420  mov     rdx, r15; struct TElement *
0x18001b423  mov     rbx, [rax+10h]
0x18001b427  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b42c  mov     rcx, [rax+18h]; String
0x18001b430  test    rcx, rcx
0x18001b433  jnz     short loc_18001B439
0x18001b435  xor     eax, eax
0x18001b437  jmp     short loc_18001B43F
0x18001b439  call    cs:__imp__wtol
0x18001b43f  mov     edx, eax
0x18001b441  mov     rcx, rsi
0x18001b444  mov     rax, rbx
0x18001b447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b44c  lea     r8, [rsi+268h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b453  mov     [rbp+57h+var_8C], eax
0x18001b456  mov     rdx, r15; struct TElement *
0x18001b459  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b45e  mov     rcx, rsi; this
0x18001b461  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b465  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b46a  lea     r8, [rsi+278h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b471  mov     [rbp+57h+var_88], eax
0x18001b474  mov     rdx, r15; struct TElement *
0x18001b477  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b47c  mov     rcx, rsi; this
0x18001b47f  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b483  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b488  lea     r8, [rsi+258h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b48f  mov     [rbp+57h+var_84], eax
0x18001b492  mov     rdx, r15; struct TElement *
0x18001b495  mov     [rbp+57h+var_80], 0
0x18001b49c  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b4a1  mov     rcx, [rsi]
0x18001b4a4  cmp     qword ptr [rax+8], 0
0x18001b4a9  mov     rbx, [rcx+10h]
0x18001b4ad  mov     rcx, rsi; this
0x18001b4b0  jz      short loc_18001B4CF
0x18001b4b2  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b4b6  mov     r9d, 9; unsigned int
0x18001b4bc  lea     r8, aTablemeta; "TABLEMETA"
0x18001b4c3  call    ?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z; TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)
0x18001b4c8  mov     edx, eax
0x18001b4ca  mov     rcx, rsi
0x18001b4cd  jmp     short loc_18001B4D1
0x18001b4cf  xor     edx, edx
0x18001b4d1  mov     rax, rbx
0x18001b4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4d9  lea     r8, [rsi+2C8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b4e0  mov     [rbp+57h+var_7C], eax
0x18001b4e3  mov     rdx, r15; struct TElement *
0x18001b4e6  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b4eb  mov     rcx, rsi; this
0x18001b4ee  cmp     qword ptr [rax+8], 0
0x18001b4f3  jnz     short loc_18001B4FC
0x18001b4f5  mov     edx, 400h
0x18001b4fa  jmp     short loc_18001B565
0x18001b4fc  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b500  mov     r9d, 0Ah; unsigned int
0x18001b506  lea     r8, aTablemeta; "TABLEMETA"
0x18001b50d  call    ?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z; TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)
0x18001b512  mov     r14d, eax
0x18001b515  test    eax, 504h
0x18001b51a  jz      short loc_18001B55A
0x18001b51c  mov     rdi, [rsi+0A10h]
0x18001b523  mov     edx, [rbp+57h+var_9C]
0x18001b526  mov     rcx, [rdi]
0x18001b529  mov     rbx, [rcx]
0x18001b52c  mov     rcx, [rsi]
0x18001b52f  mov     rax, [rcx+90h]
0x18001b536  mov     rcx, rsi
0x18001b539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b53e  mov     r8, rax
0x18001b541  lea     rdx, aWarningTableSS; "Warning - Table (%s) - Some TableMeta::"...
0x18001b548  mov     rax, rbx
0x18001b54b  mov     rcx, rdi
0x18001b54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b553  and     r14d, 0FFFFFAFBh
0x18001b55a  bts     r14d, 0Ah
0x18001b55f  mov     rcx, rsi
0x18001b562  mov     edx, r14d
0x18001b565  mov     rax, [rsi]
0x18001b568  mov     rax, [rax+10h]
0x18001b56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b571  lea     r8, [rsi+168h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b578  mov     [rbp+57h+var_78], eax
0x18001b57b  mov     rdx, r15; struct TElement *
0x18001b57e  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b583  mov     rcx, rsi; this
0x18001b586  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b58a  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b58f  lea     r8, [rsi+198h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b596  mov     [rbp+57h+var_68], eax
0x18001b599  mov     rdx, r15; struct TElement *
0x18001b59c  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001b5a1  mov     rcx, rsi; this
0x18001b5a4  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001b5a8  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001b5ad  mov     [rbp+57h+var_64], eax
0x18001b5b0  lea     rdx, [rbp+57h+var_A0]
0x18001b5b4  mov     rax, [rsi]
0x18001b5b7  mov     r8d, 1
0x18001b5bd  mov     rcx, rsi
0x18001b5c0  mov     rax, [rax+70h]
0x18001b5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5c9  mov     edx, [rbp+57h+var_9C]; unsigned int
0x18001b5cc  xor     r8d, r8d; bool
0x18001b5cf  mov     rcx, rsi; this
0x18001b5d2  mov     [rsi+9F4h], eax
0x18001b5d8  call    ?AddServerWiringMetaToHeap@TMetabaseMetaXmlFile@@AEAAXK_N@Z; TMetabaseMetaXmlFile::AddServerWiringMetaToHeap(ulong,bool)
0x18001b5dd  mov     edx, [rsi+9E4h]; unsigned int
0x18001b5e3  mov     rcx, rsi; this
0x18001b5e6  mov     dword ptr [rsi+0A0Ch], 0
0x18001b5f0  mov     dword ptr [rsi+9E8h], 0
0x18001b5fa  call    ?AddColumnMetaByReference@TMetabaseMetaXmlFile@@AEAAXK@Z; TMetabaseMetaXmlFile::AddColumnMetaByReference(ulong)
0x18001b5ff  mov     rcx, [rbp+57h+var_30]
0x18001b603  xor     rcx, rsp; StackCookie
0x18001b606  call    __security_check_cookie
0x18001b60b  mov     rbx, [rsp+0C0h+arg_10]
0x18001b613  add     rsp, 0A0h
0x18001b61a  pop     r15
0x18001b61c  pop     r14
0x18001b61e  pop     rdi
0x18001b61f  pop     rsi
0x18001b620  pop     rbp
0x18001b621  retn
```
