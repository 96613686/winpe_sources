# ProvStateContext::CreateContext(IMVEngine *,std::unique_ptr<ProvStateContext,std::default_delete<ProvStateContext>> &)

- ea: `0x180035d8c`
- end: `0x180035eb4`
- name: `?CreateContext@ProvStateContext@@SAJPEAUIMVEngine@@AEAV?$unique_ptr@VProvStateContext@@U?$default_delete@VProvStateContext@@@std@@@std@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(__int64, ProvStateContext **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800165e0`

## callees

- `0x1800021b4`
- `0x1800113a8`
- `0x180020b74`
- `0x180020c34`
- `0x180035d8c`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180035db9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035e7e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035e99`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035db9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035e7e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035e99`

## pseudocode

```c
__int64 __fastcall ProvStateContext::CreateContext(__int64 a1, ProvStateContext **a2)
{
  ProvStateContext *v4; // rbx
  ProvStateContext *v5; // rax
  ProvStateContext *v6; // rdi
  __int64 v7; // rcx
  ProvStateContext *v8; // rbx
  char v10; // [rsp+20h] [rbp-28h] BYREF

  v4 = *a2;
  if ( *a2 )
  {
    ProvStateContext::~ProvStateContext(*a2);
    operator delete(v4);
    *a2 = 0;
  }
  v5 = (ProvStateContext *)operator new(0x60u);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 7) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 6) = 0;
    *((_QWORD *)v5 + 7) = 0;
    *((_QWORD *)v5 + 6) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode();
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 8) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode();
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 10) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>>::_Buyheadnode();
  }
  else
  {
    v6 = 0;
  }
  if ( *((_QWORD *)v6 + 1) != a1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v7 = *((_QWORD *)v6 + 1);
    *((_QWORD *)v6 + 1) = a1;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( a2 == (ProvStateContext **)&v10 )
  {
    if ( v6 )
    {
      ProvStateContext::~ProvStateContext(v6);
      operator delete(v6);
    }
  }
  else
  {
    v8 = *a2;
    if ( v6 != *a2 )
    {
      if ( v8 )
      {
        ProvStateContext::~ProvStateContext(*a2);
        operator delete(v8);
      }
      *a2 = v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180035d8c  mov     [rsp+arg_10], rbx
0x180035d91  mov     [rsp+arg_18], rbp
0x180035d96  push    rsi
0x180035d97  push    rdi
0x180035d98  push    r14
0x180035d9a  sub     rsp, 30h
0x180035d9e  mov     rsi, rdx
0x180035da1  mov     r14, rcx
0x180035da4  mov     rbx, [rdx]
0x180035da7  xor     ebp, ebp
0x180035da9  test    rbx, rbx
0x180035dac  jz      short loc_180035DC2
0x180035dae  mov     rcx, rbx; this
0x180035db1  call    ??1ProvStateContext@@QEAA@XZ; ProvStateContext::~ProvStateContext(void)
0x180035db6  mov     rcx, rbx
0x180035db9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180035dbf  mov     [rsi], rbp
0x180035dc2  mov     ecx, 60h ; '`'; Size
0x180035dc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035dcc  mov     rdi, rax
0x180035dcf  mov     [rsp+48h+arg_0], rax
0x180035dd4  test    rax, rax
0x180035dd7  jz      short loc_180035E24
0x180035dd9  mov     [rax], rbp
0x180035ddc  mov     [rax+8], rbp
0x180035de0  mov     [rax+10h], rbp
0x180035de4  mov     [rax+1Ch], ebp
0x180035de7  mov     [rax+20h], rbp
0x180035deb  mov     [rax+28h], rbp
0x180035def  mov     [rax+30h], rbp
0x180035df3  mov     [rax+38h], rbp
0x180035df7  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode(void)
0x180035dfc  mov     [rdi+30h], rax
0x180035e00  mov     [rdi+40h], rbp
0x180035e04  mov     [rdi+48h], rbp
0x180035e08  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,long>>>::_Buyheadnode(void)
0x180035e0d  mov     [rdi+40h], rax
0x180035e11  mov     [rdi+50h], rbp
0x180035e15  mov     [rdi+58h], rbp
0x180035e19  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>>::_Buyheadnode(void)
0x180035e1e  mov     [rdi+50h], rax
0x180035e22  jmp     short loc_180035E27
0x180035e24  mov     rdi, rbp
0x180035e27  cmp     [rdi+8], r14
0x180035e2b  jz      short loc_180035E5C
0x180035e2d  test    r14, r14
0x180035e30  jz      short loc_180035E42
0x180035e32  mov     rax, [r14]
0x180035e35  mov     rcx, r14
0x180035e38  mov     rax, [rax+8]
0x180035e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e41  nop
0x180035e42  mov     rcx, [rdi+8]
0x180035e46  mov     [rdi+8], r14
0x180035e4a  test    rcx, rcx
0x180035e4d  jz      short loc_180035E5C
0x180035e4f  mov     rax, [rcx]
0x180035e52  mov     rax, [rax+10h]
0x180035e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e5b  nop
0x180035e5c  lea     rax, [rsp+48h+var_28]
0x180035e61  cmp     rsi, rax
0x180035e64  jz      short loc_180035E89
0x180035e66  mov     rbx, [rsi]
0x180035e69  cmp     rdi, rbx
0x180035e6c  jz      short loc_180035E9F
0x180035e6e  test    rbx, rbx
0x180035e71  jz      short loc_180035E84
0x180035e73  mov     rcx, rbx; this
0x180035e76  call    ??1ProvStateContext@@QEAA@XZ; ProvStateContext::~ProvStateContext(void)
0x180035e7b  mov     rcx, rbx
0x180035e7e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180035e84  mov     [rsi], rdi
0x180035e87  jmp     short loc_180035E9F
0x180035e89  test    rdi, rdi
0x180035e8c  jz      short loc_180035E9F
0x180035e8e  mov     rcx, rdi; this
0x180035e91  call    ??1ProvStateContext@@QEAA@XZ; ProvStateContext::~ProvStateContext(void)
0x180035e96  mov     rcx, rdi
0x180035e99  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180035e9f  xor     eax, eax
0x180035ea1  mov     rbx, [rsp+48h+arg_10]
0x180035ea6  mov     rbp, [rsp+48h+arg_18]
0x180035eab  add     rsp, 30h
0x180035eaf  pop     r14
0x180035eb1  pop     rdi
0x180035eb2  pop     rsi
0x180035eb3  retn
```
