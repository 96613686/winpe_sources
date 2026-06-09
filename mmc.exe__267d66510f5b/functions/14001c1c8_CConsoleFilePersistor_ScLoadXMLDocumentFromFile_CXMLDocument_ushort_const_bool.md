# CConsoleFilePersistor::ScLoadXMLDocumentFromFile(CXMLDocument &,ushort const *,bool)

- ea: `0x14001c1c8`
- end: `0x14001c3fc`
- name: `?ScLoadXMLDocumentFromFile@CConsoleFilePersistor@@CA?AVSC@mmcerror@@AEAVCXMLDocument@@PEBG_N@Z`
- size: `564`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001b758`
- `0x140041d3c`
- `0x1400e073c`

## callees

- `0x14001c1c8`
- `0x14003ce40`
- `0x140043f4c`
- `0x140054a70`
- `0x1400577e4`
- `0x1400e0448`
- `0x1400f3010`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c23f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c2ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c3b1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c3e5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c23f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c2ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c3b1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c3e5`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c249`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c290`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c2f8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c33a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c382`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c249`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c290`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c2f8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c33a`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c382`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001c1ed`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001c2d4`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001c1ed`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001c2d4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001c286`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001c330`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001c286`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001c330`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c25a`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c34b`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c3a6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c3c6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c25a`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c34b`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c3a6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c3c6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c234`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c2e3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c399`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c234`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c2e3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c399`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14001c1ff`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14001c1ff`
- `ole32!CreateStreamOnHGlobal` at `0x14001c27a`
- `ole32!CreateStreamOnHGlobal` at `0x14001c27a`

## string_xrefs

- `0x14001c1f4`: `CConsoleFilePersistor::ScLoadXMLDocumentFromFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall CConsoleFilePersistor::ScLoadXMLDocumentFromFile(
        mmcerror::SC *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        char a4)
{
  __int64 v8; // rax
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // eax
  const struct mmcerror::SC *v12; // rdx
  LPSTREAM ppstm; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v15[24]; // [rsp+28h] [rbp-41h] BYREF
  HGLOBAL hGlobal; // [rsp+40h] [rbp-29h] BYREF
  __int64 v17; // [rsp+48h] [rbp-21h]
  int v18; // [rsp+50h] [rbp-19h]
  __int64 v19; // [rsp+58h] [rbp-11h]
  _BYTE v20[24]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v21[64]; // [rsp+80h] [rbp+17h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v15, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v15, L"CConsoleFilePersistor::ScLoadXMLDocumentFromFile");
  hGlobal = 0;
  v17 = 0;
  v18 = 0;
  v8 = ScReadDataFromFile(v21, a3, &hGlobal);
  mmcerror::SC::operator=(v15, v8);
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
  {
    mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v15);
    goto LABEL_21;
  }
  ppstm = 0;
  v9 = CreateStreamOnHGlobal(hGlobal, 1, &ppstm);
  mmcerror::SC::operator=(v15, v9);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
    goto LABEL_19;
  v19 = (unsigned int)v17;
  hGlobal = 0;
  v17 = 0;
  v18 = 0;
  v10 = 0;
  if ( !ppstm )
    v10 = -2147418113;
  mmcerror::SC::SC((mmcerror::SC *)v21, v10);
  mmcerror::SC::operator=(v15, v21);
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
  {
LABEL_19:
    mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v15);
LABEL_20:
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&ppstm);
    goto LABEL_21;
  }
  if ( !ppstm )
    _com_issue_error(-2147467261);
  v11 = (*(__int64 (__fastcall **)(LPSTREAM, __int64))(*(_QWORD *)ppstm + 48LL))(ppstm, v19);
  mmcerror::SC::operator=(v15, v11);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v15) )
  {
    CXMLDocument::ScLoad(a2, (mmcerror::SC *)v20, (__int64)ppstm, a4);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v20) )
    {
      if ( !a4 )
        mmcerror::SC::operator=(v15, v20);
      v12 = (const struct mmcerror::SC *)v20;
    }
    else
    {
      v12 = (const struct mmcerror::SC *)v15;
    }
    mmcerror::SC::SC(a1, v12);
    mmcerror::SC::~SC((mmcerror::SC *)v20);
    goto LABEL_20;
  }
  mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v15);
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_21:
  CXMLAutoBinary::~CXMLAutoBinary((CXMLAutoBinary *)&hGlobal);
  mmcerror::SC::~SC((mmcerror::SC *)v15);
  return a1;
}

```

## disassembly

```asm
0x14001c1c8  push    rbp
0x14001c1ca  push    rbx
0x14001c1cb  push    rsi
0x14001c1cc  push    rdi
0x14001c1cd  push    r14
0x14001c1cf  lea     rbp, [rsp-37h]
0x14001c1d4  sub     rsp, 0A0h
0x14001c1db  mov     sil, r9b
0x14001c1de  mov     rbx, r8
0x14001c1e1  mov     r14, rdx
0x14001c1e4  mov     rdi, rcx
0x14001c1e7  xor     edx, edx
0x14001c1e9  lea     rcx, [rbp+57h+var_98]
0x14001c1ed  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14001c1f3  nop
0x14001c1f4  lea     rdx, aCconsolefilepe_3; "CConsoleFilePersistor::ScLoadXMLDocumen"...
0x14001c1fb  lea     rcx, [rbp+57h+var_98]
0x14001c1ff  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14001c205  mov     [rbp+57h+hGlobal], 0
0x14001c20d  mov     [rbp+57h+var_78], 0
0x14001c215  mov     [rbp+57h+var_70], 0
0x14001c21c  lea     r8, [rbp+57h+hGlobal]
0x14001c220  mov     rdx, rbx
0x14001c223  lea     rcx, [rbp+57h+var_40]
0x14001c227  call    ScReadDataFromFile
0x14001c22c  nop
0x14001c22d  mov     rdx, rax
0x14001c230  lea     rcx, [rbp+57h+var_98]
0x14001c234  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14001c23a  nop
0x14001c23b  lea     rcx, [rbp+57h+var_40]
0x14001c23f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c245  lea     rcx, [rbp+57h+var_98]
0x14001c249  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c24f  test    al, al
0x14001c251  jz      short loc_14001C265
0x14001c253  lea     rdx, [rbp+57h+var_98]
0x14001c257  mov     rcx, rdi
0x14001c25a  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001c260  jmp     loc_14001C3D7
0x14001c265  mov     [rbp+57h+ppstm], 0
0x14001c26d  lea     r8, [rbp+57h+ppstm]; ppstm
0x14001c271  mov     edx, 1; fDeleteOnRelease
0x14001c276  mov     rcx, [rbp+57h+hGlobal]; hGlobal
0x14001c27a  call    cs:__imp_CreateStreamOnHGlobal
0x14001c280  mov     edx, eax
0x14001c282  lea     rcx, [rbp+57h+var_98]
0x14001c286  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14001c28c  lea     rcx, [rbp+57h+var_98]
0x14001c290  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c296  test    al, al
0x14001c298  jnz     loc_14001C3BF
0x14001c29e  mov     eax, dword ptr [rbp+57h+var_78]
0x14001c2a1  mov     dword ptr [rbp+57h+var_68], eax
0x14001c2a4  mov     dword ptr [rbp+57h+var_68+4], 0
0x14001c2ab  mov     [rbp+57h+hGlobal], 0
0x14001c2b3  mov     [rbp+57h+var_78], 0
0x14001c2bb  mov     [rbp+57h+var_70], 0
0x14001c2c2  xor     edx, edx
0x14001c2c4  mov     eax, 8000FFFFh
0x14001c2c9  cmp     [rbp+57h+ppstm], rdx
0x14001c2cd  cmovz   edx, eax
0x14001c2d0  lea     rcx, [rbp+57h+var_40]
0x14001c2d4  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14001c2da  nop
0x14001c2db  lea     rdx, [rbp+57h+var_40]
0x14001c2df  lea     rcx, [rbp+57h+var_98]
0x14001c2e3  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14001c2e9  nop
0x14001c2ea  lea     rcx, [rbp+57h+var_40]
0x14001c2ee  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c2f4  lea     rcx, [rbp+57h+var_98]
0x14001c2f8  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c2fe  test    al, al
0x14001c300  jnz     loc_14001C3BF
0x14001c306  mov     rcx, [rbp+57h+ppstm]
0x14001c30a  test    rcx, rcx
0x14001c30d  jnz     short loc_14001C31A
0x14001c30f  mov     ecx, 80004003h; int
0x14001c314  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001c31a  mov     rax, [rcx]
0x14001c31d  mov     rdx, [rbp+57h+var_68]
0x14001c321  mov     rax, [rax+30h]
0x14001c325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c32a  mov     edx, eax
0x14001c32c  lea     rcx, [rbp+57h+var_98]
0x14001c330  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14001c336  lea     rcx, [rbp+57h+var_98]
0x14001c33a  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c340  test    al, al
0x14001c342  jz      short loc_14001C36A
0x14001c344  lea     rdx, [rbp+57h+var_98]
0x14001c348  mov     rcx, rdi
0x14001c34b  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001c351  nop
0x14001c352  mov     rcx, [rbp+57h+ppstm]
0x14001c356  test    rcx, rcx
0x14001c359  jz      short loc_14001C368
0x14001c35b  mov     rax, [rcx]
0x14001c35e  mov     rax, [rax+10h]
0x14001c362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c367  nop
0x14001c368  jmp     short loc_14001C3D7
0x14001c36a  mov     r9b, sil
0x14001c36d  mov     r8, [rbp+57h+ppstm]
0x14001c371  lea     rdx, [rbp+57h+var_58]
0x14001c375  mov     rcx, r14
0x14001c378  call    ?ScLoad@CXMLDocument@@QEAA?AVSC@mmcerror@@PEAUIStream@@_N@Z; CXMLDocument::ScLoad(IStream *,bool)
0x14001c37d  nop
0x14001c37e  lea     rcx, [rbp+57h+var_58]
0x14001c382  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c388  test    al, al
0x14001c38a  jz      short loc_14001C3B9
0x14001c38c  test    sil, sil
0x14001c38f  jnz     short loc_14001C39F
0x14001c391  lea     rdx, [rbp+57h+var_58]
0x14001c395  lea     rcx, [rbp+57h+var_98]
0x14001c399  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14001c39f  lea     rdx, [rbp+57h+var_58]
0x14001c3a3  mov     rcx, rdi
0x14001c3a6  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001c3ac  nop
0x14001c3ad  lea     rcx, [rbp+57h+var_58]
0x14001c3b1  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c3b7  jmp     short loc_14001C3CD
0x14001c3b9  lea     rdx, [rbp+57h+var_98]
0x14001c3bd  jmp     short loc_14001C3A3
0x14001c3bf  lea     rdx, [rbp+57h+var_98]
0x14001c3c3  mov     rcx, rdi
0x14001c3c6  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001c3cc  nop
0x14001c3cd  lea     rcx, [rbp+57h+ppstm]
0x14001c3d1  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14001c3d6  nop
0x14001c3d7  lea     rcx, [rbp+57h+hGlobal]; this
0x14001c3db  call    ??1CXMLAutoBinary@@QEAA@XZ; CXMLAutoBinary::~CXMLAutoBinary(void)
0x14001c3e0  nop
0x14001c3e1  lea     rcx, [rbp+57h+var_98]
0x14001c3e5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c3eb  mov     rax, rdi
0x14001c3ee  add     rsp, 0A0h
0x14001c3f5  pop     r14
0x14001c3f7  pop     rdi
0x14001c3f8  pop     rsi
0x14001c3f9  pop     rbx
0x14001c3fa  pop     rbp
0x14001c3fb  retn
```
