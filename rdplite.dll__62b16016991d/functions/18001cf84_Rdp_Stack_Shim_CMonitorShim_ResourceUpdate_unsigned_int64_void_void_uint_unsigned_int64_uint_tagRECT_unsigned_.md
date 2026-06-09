# Rdp::Stack::Shim::CMonitorShim::ResourceUpdate(unsigned __int64,void *,void *,uint,unsigned __int64,uint,tagRECT *,unsigned __int64,uint,uchar const *)

- ea: `0x18001cf84`
- end: `0x18001d095`
- name: `?ResourceUpdate@CMonitorShim@Shim@Stack@Rdp@@QEAAX_KPEAX1I0IPEAUtagRECT@@0IPEBE@Z`
- size: `273`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *this, const char *, void *, void *, unsigned int, unsigned __int64, unsigned int, struct tagRECT *, unsigned __int64, unsigned int, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bb08`

## callees

- `0x18000f30c`
- `0x18000fc30`
- `0x1800109dc`
- `0x18001cf84`
- `0x18001f41c`
- `0x180021640`
- `0x180021b78`

## string_xrefs

- `0x18001d057`: `Dropping ResourceUpdate request for frame processor (%p)`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::ResourceUpdate(
        Rdp::Stack::Shim::CMonitorShim *this,
        const char *a2,
        void *a3,
        void *a4,
        unsigned int a5,
        unsigned __int64 a6,
        unsigned int a7,
        struct tagRECT *a8,
        unsigned __int64 a9,
        unsigned int a10,
        const unsigned __int8 *a11)
{
  Rdp::Stack::Shim::CFrameProcessorShim *v15; // rcx
  _BYTE v16[40]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v18; // [rsp+80h] [rbp+8h] BYREF
  const char *v19; // [rsp+88h] [rbp+10h] BYREF

  v19 = a2;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v16, (char *)this + 144);
  std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::find(
    (char *)this + 80,
    &v18,
    &v19);
  if ( v18 == *((_QWORD *)this + 11) )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
      (const char *)0x80070490LL,
      (int)"Dropping ResourceUpdate request for frame processor (%p)",
      a2);
  }
  else
  {
    v15 = *(Rdp::Stack::Shim::CFrameProcessorShim **)(v18 + 24);
    if ( *((_BYTE *)v15 + 314) )
      Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync(v15, a3, a4, a5, a6, a7, a8, a9, a10, a11);
    else
      Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame(v15, a3, a4, a5, a6, a7, a8, a9, a10, a11);
  }
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v16);
}

```

## disassembly

```asm
0x18001cf84  mov     [rsp+arg_10], rbx
0x18001cf89  mov     [rsp+arg_8], rdx
0x18001cf8e  push    rbp
0x18001cf8f  push    rsi
0x18001cf90  push    rdi
0x18001cf91  sub     rsp, 60h
0x18001cf95  mov     rsi, r9
0x18001cf98  mov     rbp, r8
0x18001cf9b  mov     rdi, rdx
0x18001cf9e  mov     rbx, rcx
0x18001cfa1  lea     rdx, [rcx+90h]
0x18001cfa8  lea     rcx, [rsp+78h+var_28]
0x18001cfad  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001cfb2  nop
0x18001cfb3  lea     rcx, [rbx+50h]
0x18001cfb7  lea     r8, [rsp+78h+arg_8]
0x18001cfbf  lea     rdx, [rsp+78h+arg_0]
0x18001cfc7  call    ?find@?$_Hash@V?$_Umap_traits@_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::find(unsigned __int64 const &)
0x18001cfcc  mov     rax, [rsp+78h+arg_0]
0x18001cfd4  cmp     rax, [rbx+58h]
0x18001cfd8  jz      short loc_18001D04D
0x18001cfda  mov     rcx, [rax+18h]; this
0x18001cfde  mov     rax, [rsp+78h+arg_50]
0x18001cfe6  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x18001cfee  mov     r8, rsi; void *
0x18001cff1  mov     rdx, rbp; void *
0x18001cff4  mov     [rsp+78h+var_30], rax; unsigned __int8 *
0x18001cff9  mov     eax, [rsp+78h+arg_48]
0x18001d000  mov     [rsp+78h+var_38], eax; unsigned int
0x18001d004  mov     rax, [rsp+78h+arg_40]
0x18001d00c  mov     [rsp+78h+var_40], rax; unsigned __int64
0x18001d011  mov     rax, [rsp+78h+arg_38]
0x18001d019  mov     [rsp+78h+var_48], rax; struct tagRECT *
0x18001d01e  mov     eax, [rsp+78h+arg_30]
0x18001d025  mov     dword ptr [rsp+78h+var_50], eax; unsigned int
0x18001d029  mov     rax, [rsp+78h+arg_28]
0x18001d031  mov     [rsp+78h+var_58], rax; unsigned __int64
0x18001d036  cmp     byte ptr [rcx+13Ah], 0
0x18001d03d  jz      short loc_18001D046
0x18001d03f  call    ?ProcessFrameAsync@CFrameProcessorShim@Shim@Stack@Rdp@@AEAAXPEAX0I_KIPEAUtagRECT@@1IPEBE@Z; Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync(void *,void *,uint,unsigned __int64,uint,tagRECT *,unsigned __int64,uint,uchar const *)
0x18001d044  jmp     short loc_18001D07B
0x18001d046  call    ?ProcessFrame@CFrameProcessorShim@Shim@Stack@Rdp@@AEAAXPEAX0I_KIPEAUtagRECT@@1IPEBE@Z; Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame(void *,void *,uint,unsigned __int64,uint,tagRECT *,unsigned __int64,uint,uchar const *)
0x18001d04b  jmp     short loc_18001D07B
0x18001d04d  mov     rcx, [rsp+78h]; this
0x18001d052  mov     [rsp+78h+var_50], rdi; char *
0x18001d057  lea     rax, aDroppingResour; "Dropping ResourceUpdate request for fra"...
0x18001d05e  mov     [rsp+78h+var_58], rax; int
0x18001d063  mov     r9d, 80070490h; char *
0x18001d069  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001d070  mov     edx, 1B5h; void *
0x18001d075  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d07a  nop
0x18001d07b  lea     rcx, [rsp+78h+var_28]
0x18001d080  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001d085  mov     rbx, [rsp+78h+arg_10]
0x18001d08d  add     rsp, 60h
0x18001d091  pop     rdi
0x18001d092  pop     rsi
0x18001d093  pop     rbp
0x18001d094  retn
```
