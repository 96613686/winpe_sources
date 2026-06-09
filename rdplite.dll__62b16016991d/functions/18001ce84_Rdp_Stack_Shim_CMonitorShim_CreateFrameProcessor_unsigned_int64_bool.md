# Rdp::Stack::Shim::CMonitorShim::CreateFrameProcessor(unsigned __int64,bool)

- ea: `0x18001ce84`
- end: `0x18001cf7c`
- name: `?CreateFrameProcessor@CMonitorShim@Shim@Stack@Rdp@@QEAAX_K_N@Z`
- size: `248`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb08`

## callees

- `0x180003714`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000cea4`
- `0x18000f30c`
- `0x18000fc30`
- `0x18001c408`
- `0x18001c52c`
- `0x18001c858`
- `0x18001effc`
- `0x1800224e4`

## string_xrefs

- `0x18001cee1`: `Frame processor is already created`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::CreateFrameProcessor(
        Rdp::Stack::Shim::CMonitorShim *this,
        unsigned __int64 a2,
        bool a3)
{
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r8
  unsigned __int64 appended; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  const char *v11[2]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  Rdp::Stack::Shim::CFrameProcessorShim *v14; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int64 v15; // [rsp+78h] [rbp+28h] BYREF

  v15 = a2;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v11, (char *)this + 144);
  appended = std::_Fnv1a_append_bytes(v6, (const unsigned __int8 *const)&v15, v7);
  v9 = std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
         (char *)this + 80,
         v12,
         &v15,
         appended);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xFB,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)0x8000FFFFLL,
    *(_QWORD *)(v9 + 8) != 0,
    (bool)"Frame processor is already created",
    v11[0]);
  v14 = (Rdp::Stack::Shim::CFrameProcessorShim *)operator new(0x140u);
  v10 = Rdp::Stack::Shim::CFrameProcessorShim::CFrameProcessorShim(v14, this, a2, a3);
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    &v14,
    v10);
  std::unordered_map<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>::_Insert_or_assign<unsigned __int64 const &,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy> &>(
    (char *)this + 80,
    v12,
    &v15,
    &v14);
  Rdp::Stack::Shim::CFrameProcessorShim::Start(v14);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v14);
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v11);
}

```

## disassembly

```asm
0x18001ce84  mov     [rsp-18h+arg_10], rbx
0x18001ce89  mov     [rsp-18h+arg_18], rsi
0x18001ce8e  mov     [rsp-18h+arg_8], rdx
0x18001ce93  push    rbp
0x18001ce94  push    rdi
0x18001ce95  push    r14
0x18001ce97  mov     rbp, rsp
0x18001ce9a  sub     rsp, 50h
0x18001ce9e  mov     dil, r8b
0x18001cea1  mov     rsi, rdx
0x18001cea4  mov     rbx, rcx
0x18001cea7  lea     rdx, [rcx+90h]
0x18001ceae  lea     rcx, [rbp+var_20]
0x18001ceb2  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001ceb7  nop
0x18001ceb8  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x18001cebc  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001cec1  mov     r9, rax
0x18001cec4  lea     r8, [rbp+arg_8]
0x18001cec8  lea     rdx, [rbp+var_10]
0x18001cecc  lea     rcx, [rbx+50h]
0x18001ced0  call    ??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)
0x18001ced5  cmp     qword ptr [rax+8], 0
0x18001ceda  setnz   al
0x18001cedd  mov     rcx, [rbp+18h]; this
0x18001cee1  lea     rdx, aFrameProcessor_0; "Frame processor is already created"
0x18001cee8  mov     qword ptr [rsp+50h+var_28], rdx; bool
0x18001ceed  mov     [rsp+50h+var_30], al; char
0x18001cef1  mov     r9d, 8000FFFFh; char *
0x18001cef7  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001cefe  mov     edx, 0FBh; void *
0x18001cf03  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001cf08  mov     ecx, 140h; Size
0x18001cf0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cf12  mov     [rbp+arg_0], rax
0x18001cf16  mov     r9b, dil; bool
0x18001cf19  mov     r8, rsi; unsigned __int64
0x18001cf1c  mov     rdx, rbx; struct Rdp::Stack::Shim::CMonitorShim *
0x18001cf1f  mov     rcx, rax; this
0x18001cf22  call    ??0CFrameProcessorShim@Shim@Stack@Rdp@@QEAA@PEAVCMonitorShim@123@_K_N@Z; Rdp::Stack::Shim::CFrameProcessorShim::CFrameProcessorShim(Rdp::Stack::Shim::CMonitorShim *,unsigned __int64,bool)
0x18001cf27  nop
0x18001cf28  mov     rdx, rax
0x18001cf2b  lea     rcx, [rbp+arg_0]
0x18001cf2f  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001cf34  nop
0x18001cf35  lea     r9, [rbp+arg_0]
0x18001cf39  lea     r8, [rbp+arg_8]
0x18001cf3d  lea     rdx, [rbp+var_10]
0x18001cf41  lea     rcx, [rbx+50h]
0x18001cf45  call    ??$_Insert_or_assign@AEB_KAEAV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$unordered_map@_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@4@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEB_KAEAV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; std::unordered_map<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>::_Insert_or_assign<unsigned __int64 const &,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy> &>(unsigned __int64 const &,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy> &)
0x18001cf4a  mov     rcx, [rbp+arg_0]; this
0x18001cf4e  call    ?Start@CFrameProcessorShim@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CFrameProcessorShim::Start(void)
0x18001cf53  nop
0x18001cf54  lea     rcx, [rbp+arg_0]
0x18001cf58  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001cf5d  nop
0x18001cf5e  lea     rcx, [rbp+var_20]
0x18001cf62  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001cf67  lea     r11, [rsp+50h+var_s0]
0x18001cf6c  mov     rbx, [r11+30h]
0x18001cf70  mov     rsi, [r11+38h]
0x18001cf74  mov     rsp, r11
0x18001cf77  pop     r14
0x18001cf79  pop     rdi
0x18001cf7a  pop     rbp
0x18001cf7b  retn
```
