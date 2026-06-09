# _lambda_87eb30269204c6baa5bbb9a9fab650b6_::operator()

- ea: `0x180025484`
- end: `0x1800255d5`
- name: `_lambda_87eb30269204c6baa5bbb9a9fab650b6_::operator()`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180025344`

## callees

- `0x1800215a4`
- `0x1800253b8`
- `0x180025484`
- `0x18002568c`
- `0x1800256c4`
- `0x18002b6d8`
- `0x18002b748`
- `0x18002ba18`
- `0x18002bb9c`
- `0x18002bc88`
- `0x18002be64`
- `0x18002c1a0`
- `0x18002c3b8`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002555b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002555b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall lambda_87eb30269204c6baa5bbb9a9fab650b6_::operator()(__int64 **a1)
{
  __int64 *v1; // rcx
  __int64 v2; // rax
  int v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  struct _NETSETUP_ENVIRONMENT *v6; // rdx
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdi
  void *v11; // rcx
  bool v12; // zf
  LPVOID pv; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v14[8]; // [rsp+28h] [rbp-31h] BYREF
  void **p_pv; // [rsp+30h] [rbp-29h] BYREF
  void **v16; // [rsp+38h] [rbp-21h] BYREF
  char v17; // [rsp+40h] [rbp-19h]
  _BYTE v18[8]; // [rsp+48h] [rbp-11h] BYREF
  _QWORD *v19; // [rsp+50h] [rbp-9h] BYREF
  char v20; // [rsp+70h] [rbp+17h]
  _BYTE v21[8]; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD *v22; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  pv = 0;
  v1 = *a1;
  v2 = *v1;
  p_pv = &pv;
  v16 = 0;
  v17 = 1;
  v3 = (*(__int64 (__fastcall **)(__int64 *, void ***))(v2 + 32))(v1, &v16);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v4, v5, (const char *)(unsigned int)v3, (int)pv);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  NetSetup2::Transaction::Transaction((NetSetup2::Transaction *)v14, v6);
  NetSetup2::details::TransactionBase::GetNetworkInterfaceById(v14, v21, pv);
  NetSetup2::NetworkInterface::TryGetMuxAbove(v21, v18);
  if ( v20 )
  {
    NetSetup2::Mux::RemoveMember((NetSetup2::Mux *)v18, (struct NetSetup2::NetworkInterface *)v21);
    v7 = NetSetup2::Mux::EnumerateMembers((__int64)v18, &p_pv);
    v9 = *v7;
    v10 = v7[1];
    if ( p_pv )
    {
      std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(v8, p_pv, v16);
      operator delete(p_pv);
    }
    if ( v9 == v10 )
      NetSetup2::ActiveObject::Delete((NetSetup2::ActiveObject *)v18);
    NetSetup2::details::TransactionBase::Commit((NetSetup2::details::TransactionBase *)v14);
    if ( v20 )
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v19);
  }
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v22);
  NetSetup2::Transaction::~Transaction((NetSetup2::Transaction *)v14);
  v11 = pv;
  v12 = pv == 0;
  pv = 0;
  if ( !v12 )
    CoTaskMemFree(v11);
}

```

## disassembly

```asm
0x180025484  mov     [rsp-8+arg_8], rbx
0x180025489  mov     [rsp-8+arg_10], rdi
0x18002548e  push    rbp
0x18002548f  lea     rbp, [rsp-57h]
0x180025494  sub     rsp, 0B0h
0x18002549b  mov     rax, cs:__security_cookie
0x1800254a2  xor     rax, rsp
0x1800254a5  mov     [rbp+57h+var_10], rax
0x1800254a9  mov     [rbp+57h+pv], 0
0x1800254b1  mov     rcx, [rcx]
0x1800254b4  mov     rax, [rcx]
0x1800254b7  lea     rdx, [rbp+57h+pv]
0x1800254bb  mov     [rbp+57h+var_80], rdx
0x1800254bf  mov     [rbp+57h+var_78], 0
0x1800254c7  mov     [rbp+57h+var_70], 1
0x1800254cb  lea     rdx, [rbp+57h+var_78]
0x1800254cf  mov     rax, [rax+20h]
0x1800254d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254d8  mov     rcx, [rbp+5Fh]; this
0x1800254dc  test    eax, eax
0x1800254de  jns     short loc_1800254E9
0x1800254e0  mov     r9d, eax; char *
0x1800254e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800254e9  lea     rcx, [rbp+57h+var_80]
0x1800254ed  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800254f2  lea     rcx, [rbp+57h+var_88]; this
0x1800254f6  call    ??0Transaction@NetSetup2@@QEAA@PEAU_NETSETUP_ENVIRONMENT@@@Z; NetSetup2::Transaction::Transaction(_NETSETUP_ENVIRONMENT *)
0x1800254fb  nop
0x1800254fc  mov     r8, [rbp+57h+pv]
0x180025500  lea     rdx, [rbp+57h+var_38]
0x180025504  lea     rcx, [rbp+57h+var_88]
0x180025508  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x18002550d  nop
0x18002550e  lea     rdx, [rbp+57h+var_68]
0x180025512  lea     rcx, [rbp+57h+var_38]
0x180025516  call    ?TryGetMuxAbove@NetworkInterface@NetSetup2@@QEBA?AV?$Optional@VMux@NetSetup2@@@details@2@XZ; NetSetup2::NetworkInterface::TryGetMuxAbove(void)
0x18002551b  nop
0x18002551c  cmp     [rbp+57h+var_40], 0
0x180025520  jnz     short loc_180025524
0x180025522  jmp     short loc_180025589
0x180025524  lea     rdx, [rbp+57h+var_38]; struct NetSetup2::NetworkInterface *
0x180025528  lea     rcx, [rbp+57h+var_68]; this
0x18002552c  call    ?RemoveMember@Mux@NetSetup2@@QEBAXAEAVNetworkInterface@2@@Z; NetSetup2::Mux::RemoveMember(NetSetup2::NetworkInterface &)
0x180025531  lea     rdx, [rbp+57h+var_80]
0x180025535  lea     rcx, [rbp+57h+var_68]
0x180025539  call    ?EnumerateMembers@Mux@NetSetup2@@QEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@XZ; NetSetup2::Mux::EnumerateMembers(void)
0x18002553e  mov     rbx, [rax]
0x180025541  mov     rdi, [rax+8]
0x180025545  mov     rdx, [rbp+57h+var_80]
0x180025549  test    rdx, rdx
0x18002554c  jz      short loc_180025561
0x18002554e  mov     r8, [rbp+57h+var_78]
0x180025552  call    ?_Destroy@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *)
0x180025557  mov     rcx, [rbp+57h+var_80]
0x18002555b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025561  cmp     rbx, rdi
0x180025564  jnz     short loc_18002556F
0x180025566  lea     rcx, [rbp+57h+var_68]; this
0x18002556a  call    ?Delete@ActiveObject@NetSetup2@@QEAAXXZ; NetSetup2::ActiveObject::Delete(void)
0x18002556f  lea     rcx, [rbp+57h+var_88]; this
0x180025573  call    ?Commit@TransactionBase@details@NetSetup2@@QEAAXXZ; NetSetup2::details::TransactionBase::Commit(void)
0x180025578  nop
0x180025579  cmp     [rbp+57h+var_40], 0
0x18002557d  jz      short loc_180025589
0x18002557f  lea     rcx, [rbp+57h+var_60]
0x180025583  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180025588  nop
0x180025589  lea     rcx, [rbp+57h+var_30]
0x18002558d  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180025592  nop
0x180025593  lea     rcx, [rbp+57h+var_88]; this
0x180025597  call    ??1Transaction@NetSetup2@@QEAA@XZ; NetSetup2::Transaction::~Transaction(void)
0x18002559c  nop
0x18002559d  mov     rcx, [rbp+57h+pv]; pv
0x1800255a1  test    rcx, rcx
0x1800255a4  mov     [rbp+57h+pv], 0
0x1800255ac  jz      short loc_1800255B4
0x1800255ae  call    cs:__imp_CoTaskMemFree
0x1800255b4  mov     rcx, [rbp+57h+var_10]
0x1800255b8  xor     rcx, rsp; StackCookie
0x1800255bb  call    __security_check_cookie
0x1800255c0  lea     r11, [rsp+0B0h+var_s0]
0x1800255c8  mov     rbx, [r11+18h]
0x1800255cc  mov     rdi, [r11+20h]
0x1800255d0  mov     rsp, r11
0x1800255d3  pop     rbp
0x1800255d4  retn
```
