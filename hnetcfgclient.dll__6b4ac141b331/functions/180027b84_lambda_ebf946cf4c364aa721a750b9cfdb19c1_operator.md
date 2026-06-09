# _lambda_ebf946cf4c364aa721a750b9cfdb19c1_::operator()

- ea: `0x180027b84`
- end: `0x180027c9c`
- name: `_lambda_ebf946cf4c364aa721a750b9cfdb19c1_::operator()`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180027b64`

## callees

- `0x180003420`
- `0x18002568c`
- `0x180026b3c`
- `0x180026c18`
- `0x180027b84`
- `0x18002b6d8`
- `0x18002b748`
- `0x18002bd2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027c00`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027c2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027c00`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027c2c`

## string_xrefs

- `0x180027c67`: `onecoreuap\net\homenet\config\client\hncutil.cpp`
- `0x180027c8a`: `onecoreuap\net\homenet\config\client\hncutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall lambda_ebf946cf4c364aa721a750b9cfdb19c1_::operator()(_OWORD **a1, struct _NETSETUP_ENVIRONMENT *a2)
{
  _OWORD *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int128 v6; // [rsp+20h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-20h]
  __int128 v8; // [rsp+38h] [rbp-18h] BYREF
  __int64 v9; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  __int64 v11; // [rsp+68h] [rbp+18h] BYREF

  NetSetup2::Transaction::Transaction((NetSetup2::Transaction *)&v11, a2);
  NetSetup2::details::TransactionBase::GetAllMuxes(&v11, &v8);
  if ( (_QWORD)v8 == *((_QWORD *)&v8 + 1) )
  {
    v5 = wil::verify_hresult<long>(2147500037LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52E,
      (unsigned int)"onecoreuap\\net\\homenet\\config\\client\\hncutil.cpp",
      (const char *)v5,
      v6);
  }
  NetSetup2::Mux::EnumerateVirtualInterfaces(*(_QWORD *)v8, &v6);
  if ( !((__int64)(*((_QWORD *)&v6 + 1) - v6) >> 3) )
  {
    v4 = wil::verify_hresult<long>(2147500037LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53A,
      (unsigned int)"onecoreuap\\net\\homenet\\config\\client\\hncutil.cpp",
      (const char *)v4,
      v6);
  }
  v3 = *a1;
  **a1 = *(_OWORD *)(*(_QWORD *)v6 + 20LL);
  if ( (_QWORD)v6 )
  {
    std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy((__int64)v3, (void **)v6, *((void ***)&v6 + 1));
    operator delete((void *)v6);
    v6 = 0;
    v7 = 0;
  }
  if ( (_QWORD)v8 )
  {
    std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy((__int64)v3, (void **)v8, *((void ***)&v8 + 1));
    operator delete((void *)v8);
    v8 = 0;
    v9 = 0;
  }
  NetSetup2::Transaction::~Transaction((NetSetup2::Transaction *)&v11);
}

```

## disassembly

```asm
0x180027b84  mov     [rsp-8+arg_0], rbx
0x180027b89  push    rbp
0x180027b8a  mov     rbp, rsp
0x180027b8d  sub     rsp, 50h
0x180027b91  mov     rbx, rcx
0x180027b94  lea     rcx, [rbp+arg_8]; this
0x180027b98  call    ??0Transaction@NetSetup2@@QEAA@PEAU_NETSETUP_ENVIRONMENT@@@Z; NetSetup2::Transaction::Transaction(_NETSETUP_ENVIRONMENT *)
0x180027b9d  nop
0x180027b9e  lea     rdx, [rbp+var_18]
0x180027ba2  lea     rcx, [rbp+arg_8]
0x180027ba6  call    ?GetAllMuxes@TransactionBase@details@NetSetup2@@QEAA?AV?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@PEBG@Z; NetSetup2::details::TransactionBase::GetAllMuxes(ushort const *)
0x180027bab  nop
0x180027bac  mov     rcx, qword ptr [rbp+var_18]
0x180027bb0  cmp     rcx, qword ptr [rbp+var_18+8]
0x180027bb4  jz      loc_180027C79
0x180027bba  lea     rdx, [rbp+var_30]
0x180027bbe  mov     rcx, [rcx]
0x180027bc1  call    ?EnumerateVirtualInterfaces@Mux@NetSetup2@@QEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@XZ; NetSetup2::Mux::EnumerateVirtualInterfaces(void)
0x180027bc6  nop
0x180027bc7  mov     rax, qword ptr [rbp+var_30+8]
0x180027bcb  mov     rcx, qword ptr [rbp+var_30]
0x180027bcf  sub     rax, rcx
0x180027bd2  sar     rax, 3
0x180027bd6  cmp     rax, 1
0x180027bda  jb      short loc_180027C56
0x180027bdc  mov     rax, [rcx]
0x180027bdf  mov     rcx, [rbx]
0x180027be2  movups  xmm0, xmmword ptr [rax+14h]
0x180027be6  movdqu  xmmword ptr [rcx], xmm0
0x180027bea  mov     rdx, qword ptr [rbp+var_30]
0x180027bee  test    rdx, rdx
0x180027bf1  jz      short loc_180027C16
0x180027bf3  mov     r8, qword ptr [rbp+var_30+8]
0x180027bf7  call    ?_Destroy@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *)
0x180027bfc  mov     rcx, qword ptr [rbp+var_30]
0x180027c00  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027c06  xorps   xmm0, xmm0
0x180027c09  movdqu  [rbp+var_30], xmm0
0x180027c0e  mov     [rbp+var_20], 0
0x180027c16  mov     rdx, qword ptr [rbp+var_18]
0x180027c1a  test    rdx, rdx
0x180027c1d  jz      short loc_180027C42
0x180027c1f  mov     r8, qword ptr [rbp+var_18+8]
0x180027c23  call    ?_Destroy@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *)
0x180027c28  mov     rcx, qword ptr [rbp+var_18]
0x180027c2c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027c32  xorps   xmm0, xmm0
0x180027c35  movdqu  [rbp+var_18], xmm0
0x180027c3a  mov     [rbp+var_8], 0
0x180027c42  lea     rcx, [rbp+arg_8]; this
0x180027c46  call    ??1Transaction@NetSetup2@@QEAA@XZ; NetSetup2::Transaction::~Transaction(void)
0x180027c4b  mov     rbx, [rsp+50h+arg_0]
0x180027c50  add     rsp, 50h
0x180027c54  pop     rbp
0x180027c55  retn
0x180027c56  mov     ecx, 80004005h
0x180027c5b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180027c60  mov     r9d, eax; char *
0x180027c63  mov     rcx, [rbp+8]; this
0x180027c67  lea     r8, aOnecoreuapNetH; "onecoreuap\\net\\homenet\\config\\clien"...
0x180027c6e  mov     edx, 53Ah; void *
0x180027c73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027c79  mov     ecx, 80004005h
0x180027c7e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180027c83  mov     r9d, eax; char *
0x180027c86  mov     rcx, [rbp+8]; this
0x180027c8a  lea     r8, aOnecoreuapNetH; "onecoreuap\\net\\homenet\\config\\clien"...
0x180027c91  mov     edx, 52Eh; void *
0x180027c96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
