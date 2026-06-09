# CXML_IStream::ScInitialize(bool &)

- ea: `0x14005daa4`
- end: `0x14005dbb6`
- name: `?ScInitialize@CXML_IStream@@QEAA?AVSC@mmcerror@@AEA_N@Z`
- size: `274`
- prototype: `mmcerror::SC *__fastcall(__int64, mmcerror::SC *, _BYTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001aa90`
- `0x1400e01bc`

## callees

- `0x14001ad8c`
- `0x14003ce40`
- `0x140057b94`
- `0x14005daa4`
- `0x1400f3010`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14005db96`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14005db96`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14005db2c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14005db6c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14005db9f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14005db2c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14005db6c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14005db9f`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14005dacb`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14005dacb`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14005db23`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14005db63`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14005db23`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14005db63`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14005db8a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14005db8a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14005dae4`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14005dae4`
- `ole32!CreateStreamOnHGlobal` at `0x14005db18`
- `ole32!CreateStreamOnHGlobal` at `0x14005db18`

## string_xrefs

- `0x14005dada`: `CXML_IStream::ScInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall CXML_IStream::ScInitialize(__int64 a1, mmcerror::SC *a2, _BYTE *a3)
{
  unsigned int StreamOnHGlobal; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rax
  _BYTE v11[56]; // [rsp+20h] [rbp-38h] BYREF

  mmcerror::SC::SC(a2, 0);
  mmcerror::SC::SetFunctionName(a2, L"CXML_IStream::ScInitialize");
  if ( *(_QWORD *)(a1 + 8) )
  {
    *a3 = 0;
  }
  else
  {
    *a3 = 1;
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)(a1 + 8));
    mmcerror::SC::operator=(a2, StreamOnHGlobal);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(a2) )
    {
      v7 = _com_ptr_t<_com_IIID<IScopeTree,&_GUID const IID_IScopeTree>>::operator->(a1 + 8);
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 48LL))(v7, 0);
      mmcerror::SC::operator=(a2, v8);
      if ( !(unsigned __int8)mmcerror::SC::operator bool(a2) )
      {
        v9 = CXML_IStream::ScSeekBeginning(a1, v11);
        mmcerror::SC::operator=(a2, v9);
        mmcerror::SC::~SC((mmcerror::SC *)v11);
        mmcerror::SC::operator bool(a2);
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x14005daa4  mov     [rsp+arg_10], rbx
0x14005daa9  mov     [rsp+arg_8], rdx
0x14005daae  push    rbp
0x14005daaf  push    rsi
0x14005dab0  push    rdi
0x14005dab1  sub     rsp, 40h
0x14005dab5  mov     rsi, r8
0x14005dab8  mov     rbx, rdx
0x14005dabb  mov     rbp, rcx
0x14005dabe  mov     [rsp+58h+arg_0], 1
0x14005dac6  xor     edx, edx
0x14005dac8  mov     rcx, rbx
0x14005dacb  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14005dad1  nop
0x14005dad2  mov     [rsp+58h+arg_0], 1
0x14005dada  lea     rdx, aCxmlIstreamSci; "CXML_IStream::ScInitialize"
0x14005dae1  mov     rcx, rbx
0x14005dae4  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14005daea  lea     rdi, [rbp+8]
0x14005daee  cmp     qword ptr [rdi], 0
0x14005daf2  jz      short loc_14005DAFC
0x14005daf4  mov     byte ptr [rsi], 0
0x14005daf7  jmp     loc_14005DBA6
0x14005dafc  mov     byte ptr [rsi], 1
0x14005daff  mov     rcx, rdi
0x14005db02  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14005db07  mov     qword ptr [rdi], 0
0x14005db0e  mov     r8, rdi; ppstm
0x14005db11  mov     edx, 1; fDeleteOnRelease
0x14005db16  xor     ecx, ecx; hGlobal
0x14005db18  call    cs:__imp_CreateStreamOnHGlobal
0x14005db1e  mov     edx, eax
0x14005db20  mov     rcx, rbx
0x14005db23  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14005db29  mov     rcx, rbx
0x14005db2c  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14005db32  test    al, al
0x14005db34  jnz     short loc_14005DBA6
0x14005db36  mov     [rsp+58h+arg_18], 0
0x14005db3f  mov     rcx, rdi
0x14005db42  call    ??C?$_com_ptr_t@V?$_com_IIID@UIScopeTree@@$1?IID_IScopeTree@@3U_GUID@@B@@@@QEBAPEAUIScopeTree@@XZ; _com_ptr_t<_com_IIID<IScopeTree,&_GUID const IID_IScopeTree>>::operator->(void)
0x14005db47  mov     r8, rax
0x14005db4a  mov     rcx, [rax]
0x14005db4d  mov     rax, [rcx+30h]
0x14005db51  mov     rdx, [rsp+58h+arg_18]
0x14005db56  mov     rcx, r8
0x14005db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005db5e  mov     edx, eax
0x14005db60  mov     rcx, rbx
0x14005db63  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14005db69  mov     rcx, rbx
0x14005db6c  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14005db72  test    al, al
0x14005db74  jnz     short loc_14005DBA6
0x14005db76  lea     rdx, [rsp+58h+var_38]
0x14005db7b  mov     rcx, rbp
0x14005db7e  call    ?ScSeekBeginning@CXML_IStream@@QEAA?AVSC@mmcerror@@XZ; CXML_IStream::ScSeekBeginning(void)
0x14005db83  nop
0x14005db84  mov     rdx, rax
0x14005db87  mov     rcx, rbx
0x14005db8a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14005db90  nop
0x14005db91  lea     rcx, [rsp+58h+var_38]
0x14005db96  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14005db9c  mov     rcx, rbx
0x14005db9f  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14005dba5  nop
0x14005dba6  mov     rax, rbx
0x14005dba9  mov     rbx, [rsp+58h+arg_10]
0x14005dbae  add     rsp, 40h
0x14005dbb2  pop     rdi
0x14005dbb3  pop     rsi
0x14005dbb4  pop     rbp
0x14005dbb5  retn
```
