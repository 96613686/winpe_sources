# Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame(IUnknown *)

- ea: `0x1800220b0`
- end: `0x1800221c8`
- name: `?ReleaseFrame@AsyncFrameBufferPool@CFrameProcessorShim@Shim@Stack@Rdp@@QEAA?AU?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@PEAUIUnknown@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021580`
- `0x180021b78`

## callees

- `0x18000a0e4`
- `0x18000cef0`
- `0x18000f30c`
- `0x18000fc30`
- `0x18001c408`
- `0x18001c500`
- `0x18001effc`
- `0x1800220b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // r8
  unsigned __int64 appended; // rax
  __int64 *v8; // rbx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  const char *v17; // [rsp+28h] [rbp-60h]
  _BYTE v18[16]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v19[64]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v21; // [rsp+A0h] [rbp+18h] BYREF

  v21 = a3;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v18, a1);
  appended = std::_Fnv1a_append_bytes(v5, (const unsigned __int8 *const)&v21, v6);
  v8 = *(__int64 **)(std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
                       a1 + 10,
                       v19,
                       &v21,
                       appended)
                   + 8);
  if ( !v8 )
    v8 = (__int64 *)a1[11];
  if ( v8 == (__int64 *)a1[11] )
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\EncodingShim/FrameProcessorShim.h",
      (const char *)0x80070490LL,
      (int)"Unable to find pending frame buffer",
      v17);
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    a2,
    v8[3]);
  a2[1] = v8[4];
  v11 = std::_Fnv1a_append_bytes(v9, (const unsigned __int8 *const)v8 + 16, v10);
  v12 = 2 * (v11 & a1[16]);
  v13 = a1[13];
  if ( *(__int64 **)(v13 + 16 * (v11 & a1[16]) + 8) == v8 )
  {
    if ( *(__int64 **)(v13 + 16 * (v11 & a1[16])) == v8 )
    {
      v14 = a1[11];
      *(_QWORD *)(v13 + 8 * v12) = v14;
    }
    else
    {
      v14 = v8[1];
    }
    *(_QWORD *)(v13 + 8 * v12 + 8) = v14;
  }
  else if ( *(__int64 **)(v13 + 16 * (v11 & a1[16])) == v8 )
  {
    *(_QWORD *)(v13 + 16 * (v11 & a1[16])) = *v8;
  }
  v15 = *v8;
  --a1[12];
  *(_QWORD *)v8[1] = v15;
  *(_QWORD *)(v15 + 8) = v8[1];
  std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>>>(
    v15,
    v8);
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v18);
  return a2;
}

```

## disassembly

```asm
0x1800220b0  mov     [rsp+arg_10], r8
0x1800220b5  push    rbx
0x1800220b6  push    rbp
0x1800220b7  push    rsi
0x1800220b8  push    rdi
0x1800220b9  sub     rsp, 68h
0x1800220bd  mov     rbp, rdx
0x1800220c0  mov     rdi, rcx
0x1800220c3  mov     rdx, rcx
0x1800220c6  lea     rcx, [rsp+88h+var_50]
0x1800220cb  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800220d0  nop
0x1800220d1  lea     rdx, [rsp+88h+arg_10]; unsigned __int8 *
0x1800220d9  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x1800220de  mov     r9, rax
0x1800220e1  lea     r8, [rsp+88h+arg_10]
0x1800220e9  lea     rdx, [rsp+88h+var_40]
0x1800220ee  lea     rcx, [rdi+50h]
0x1800220f2  call    ??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)
0x1800220f7  mov     rbx, [rax+8]
0x1800220fb  test    rbx, rbx
0x1800220fe  jnz     short loc_180022104
0x180022100  mov     rbx, [rdi+58h]
0x180022104  cmp     rbx, [rdi+58h]
0x180022108  jnz     short loc_180022136
0x18002210a  mov     rcx, [rsp+88h]; this
0x180022112  lea     rax, aUnableToFindPe; "Unable to find pending frame buffer"
0x180022119  mov     qword ptr [rsp+88h+var_68], rax; int
0x18002211e  mov     r9d, 80070490h; char *
0x180022124  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002212b  mov     edx, 97h; void *
0x180022130  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022136  mov     rdx, [rbx+18h]
0x18002213a  mov     rcx, rbp
0x18002213d  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180022142  mov     rax, [rbx+20h]
0x180022146  mov     [rbp+8], rax
0x18002214a  lea     rdx, [rbx+10h]; unsigned __int8 *
0x18002214e  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180022153  mov     rcx, [rdi+80h]
0x18002215a  and     rcx, rax
0x18002215d  add     rcx, rcx
0x180022160  mov     rdx, [rdi+68h]
0x180022164  cmp     [rdx+rcx*8+8], rbx
0x180022169  jnz     short loc_180022186
0x18002216b  cmp     [rdx+rcx*8], rbx
0x18002216f  jnz     short loc_18002217B
0x180022171  mov     rax, [rdi+58h]
0x180022175  mov     [rdx+rcx*8], rax
0x180022179  jmp     short loc_18002217F
0x18002217b  mov     rax, [rbx+8]
0x18002217f  mov     [rdx+rcx*8+8], rax
0x180022184  jmp     short loc_180022193
0x180022186  cmp     [rdx+rcx*8], rbx
0x18002218a  jnz     short loc_180022193
0x18002218c  mov     rax, [rbx]
0x18002218f  mov     [rdx+rcx*8], rax
0x180022193  mov     rcx, [rbx]
0x180022196  dec     qword ptr [rdi+60h]
0x18002219a  mov     rax, [rbx+8]
0x18002219e  mov     [rax], rcx
0x1800221a1  mov     rax, [rbx+8]
0x1800221a5  mov     [rcx+8], rax
0x1800221a9  mov     rdx, rbx
0x1800221ac  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>>>(std::allocator<std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *>> &,std::_List_node<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>,void *> *)
0x1800221b1  nop
0x1800221b2  lea     rcx, [rsp+88h+var_50]
0x1800221b7  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x1800221bc  mov     rax, rbp
0x1800221bf  add     rsp, 68h
0x1800221c3  pop     rdi
0x1800221c4  pop     rsi
0x1800221c5  pop     rbp
0x1800221c6  pop     rbx
0x1800221c7  retn
```
