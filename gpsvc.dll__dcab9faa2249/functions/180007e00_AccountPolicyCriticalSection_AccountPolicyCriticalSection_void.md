# AccountPolicyCriticalSection::~AccountPolicyCriticalSection(void)

- ea: `0x180007e00`
- end: `0x18000823b`
- name: `??1AccountPolicyCriticalSection@@QEAA@XZ`
- size: `1083`
- prototype: `void __fastcall(AccountPolicyCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180006f70`
- `0x180007c7c`
- `0x180007cb0`

## callees

- `0x180007e00`
- `0x180065208`
- `0x180075ec0`
- `0x18007d304`
- `0x18007d6f0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ebd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ed5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007fa7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007fc3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ebd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ed5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007fa7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007fc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f31`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f31`

## string_xrefs

- `0x180008171`: `Deleting sidString <%ws>`
- `0x1800081a1`: `Deleting sidString <%ws>`

## pseudocode

```c
void __fastcall AccountPolicyCriticalSection::~AccountPolicyCriticalSection(AccountPolicyCriticalSection *this)
{
  __int64 v2; // rcx
  void **v3; // rdi
  void **v4; // rsi
  _QWORD **v5; // rcx
  _QWORD *v6; // rcx
  void **v7; // rsi
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  _QWORD *v9; // rsi
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  void **v11; // r14
  _QWORD **v12; // rcx
  _QWORD *v13; // rcx
  void **v14; // r14
  __int64 v15; // rcx
  void **v16; // rdi
  void **v17; // rsi
  _QWORD **v18; // rcx
  _QWORD *v19; // rcx
  void **v20; // rsi
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  _QWORD *v22; // rsi
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  void **v24; // r14
  _QWORD **v25; // rcx
  _QWORD *v26; // rcx
  void **v27; // r14
  _QWORD **v28; // rcx
  _QWORD *v29; // rcx
  _QWORD **v30; // rcx
  _QWORD *v31; // rcx
  _QWORD **v32; // rcx
  _QWORD *v33; // rcx
  _QWORD **v34; // rcx
  _QWORD *v35; // rcx
  _QWORD *v36; // rdi
  _QWORD *v37; // rdi
  _QWORD *v38; // rdi
  _QWORD *v39; // rdi
  _QWORD *v40; // rdi
  _QWORD *v41; // rdi
  _QWORD *v42; // rdi
  _QWORD *v43; // rdi

  if ( *(_QWORD *)this )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Deleting sidString <%ws>");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Deleting sidString <%ws>");
      }
    }
    LocalFree(*(HLOCAL *)this);
    *(_QWORD *)this = 0;
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Deleting machine");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Deleting machine");
    }
  }
  SysFreeString(*((BSTR *)this + 25));
  v3 = (void **)*((_QWORD *)this + 24);
  if ( v3 )
  {
    std::_List_node<_POLICY_SECTION_CONTEXT *,void *>::_Free_non_head<STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>>>(
      v2,
      *v3);
    operator delete(*v3);
    operator delete(v3);
  }
  v4 = (void **)*((_QWORD *)this + 23);
  if ( v4 )
  {
    v5 = (_QWORD **)*v4;
    **((_QWORD **)*v4 + 1) = 0;
    v6 = *v5;
    if ( v6 )
    {
      do
      {
        v40 = (_QWORD *)*v6;
        operator delete(v6);
        v6 = v40;
      }
      while ( v40 );
    }
    operator delete(*v4);
    operator delete(v4);
  }
  v7 = (void **)*((_QWORD *)this + 22);
  if ( v7 )
  {
    v30 = (_QWORD **)*v7;
    **((_QWORD **)*v7 + 1) = 0;
    v31 = *v30;
    if ( v31 )
    {
      do
      {
        v41 = (_QWORD *)*v31;
        operator delete(v31);
        v31 = v41;
      }
      while ( v41 );
    }
    operator delete(*v7);
    operator delete(v7);
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 21);
  if ( v8 )
    DeleteCriticalSection(v8);
  v9 = (_QWORD *)*((_QWORD *)this + 14);
  if ( v9 )
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)v9[9];
    if ( v10 )
      DeleteCriticalSection(v10);
    v11 = (void **)v9[3];
    if ( v11 )
    {
      v12 = (_QWORD **)*v11;
      **((_QWORD **)*v11 + 1) = 0;
      v13 = *v12;
      if ( v13 )
      {
        do
        {
          v37 = (_QWORD *)*v13;
          operator delete(v13);
          v13 = v37;
        }
        while ( v37 );
      }
      operator delete(*v11);
      operator delete(v11);
    }
    v14 = (void **)v9[2];
    if ( v14 )
    {
      v34 = (_QWORD **)*v14;
      **((_QWORD **)*v14 + 1) = 0;
      v35 = *v34;
      if ( v35 )
      {
        do
        {
          v36 = (_QWORD *)*v35;
          operator delete(v35);
          v35 = v36;
        }
        while ( v36 );
      }
      operator delete(*v14);
      operator delete(v14);
    }
    operator delete(v9);
  }
  *((_QWORD *)this + 14) = 0;
  SysFreeString(*((BSTR *)this + 13));
  v16 = (void **)*((_QWORD *)this + 12);
  if ( v16 )
  {
    std::_List_node<_POLICY_SECTION_CONTEXT *,void *>::_Free_non_head<STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>>>(
      v15,
      *v16);
    operator delete(*v16);
    operator delete(v16);
  }
  v17 = (void **)*((_QWORD *)this + 11);
  if ( v17 )
  {
    v18 = (_QWORD **)*v17;
    **((_QWORD **)*v17 + 1) = 0;
    v19 = *v18;
    if ( v19 )
    {
      do
      {
        v42 = (_QWORD *)*v19;
        operator delete(v19);
        v19 = v42;
      }
      while ( v42 );
    }
    operator delete(*v17);
    operator delete(v17);
  }
  v20 = (void **)*((_QWORD *)this + 10);
  if ( v20 )
  {
    v32 = (_QWORD **)*v20;
    **((_QWORD **)*v20 + 1) = 0;
    v33 = *v32;
    if ( v33 )
    {
      do
      {
        v43 = (_QWORD *)*v33;
        operator delete(v33);
        v33 = v43;
      }
      while ( v43 );
    }
    operator delete(*v20);
    operator delete(v20);
  }
  v21 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 9);
  if ( v21 )
    DeleteCriticalSection(v21);
  v22 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v22 )
  {
    v23 = (struct _RTL_CRITICAL_SECTION *)v22[9];
    if ( v23 )
      DeleteCriticalSection(v23);
    v24 = (void **)v22[3];
    if ( v24 )
    {
      v25 = (_QWORD **)*v24;
      **((_QWORD **)*v24 + 1) = 0;
      v26 = *v25;
      if ( v26 )
      {
        do
        {
          v38 = (_QWORD *)*v26;
          operator delete(v26);
          v26 = v38;
        }
        while ( v38 );
      }
      operator delete(*v24);
      operator delete(v24);
    }
    v27 = (void **)v22[2];
    if ( v27 )
    {
      v28 = (_QWORD **)*v27;
      **((_QWORD **)*v27 + 1) = 0;
      v29 = *v28;
      if ( v29 )
      {
        do
        {
          v39 = (_QWORD *)*v29;
          operator delete(v29);
          v29 = v39;
        }
        while ( v39 );
      }
      operator delete(*v27);
      operator delete(v27);
    }
    operator delete(v22);
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180007e00  push    rbx
0x180007e02  push    rbp
0x180007e03  push    rsi
0x180007e04  push    rdi
0x180007e05  push    r14
0x180007e07  sub     rsp, 20h
0x180007e0b  mov     rbx, rcx
0x180007e0e  mov     r8, [rcx]
0x180007e11  xor     ebp, ebp
0x180007e13  test    r8, r8
0x180007e16  jz      loc_1800080E9
0x180007e1c  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x180007e22  jnz     loc_180008165
0x180007e28  mov     rcx, [rbx]; hMem
0x180007e2b  call    cs:__imp_LocalFree
0x180007e31  mov     [rbx], rbp
0x180007e34  mov     rcx, [rbx+0C8h]; bstrString
0x180007e3b  call    cs:__imp_SysFreeString
0x180007e41  mov     rdi, [rbx+0C0h]
0x180007e48  test    rdi, rdi
0x180007e4b  jz      short loc_180007E6A
0x180007e4d  mov     rdx, [rdi]
0x180007e50  call    ??$_Free_non_head@V?$STLWrap_allocator@U?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@@@@?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@SAXAEAV?$STLWrap_allocator@U?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@@@PEAU01@@Z; std::_List_node<_POLICY_SECTION_CONTEXT *,void *>::_Free_non_head<STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>>>(STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>> &,std::_List_node<_POLICY_SECTION_CONTEXT *,void *> *)
0x180007e55  mov     rcx, [rdi]; Block
0x180007e58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e5d  mov     edx, 10h
0x180007e62  mov     rcx, rdi; Block
0x180007e65  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007e6a  mov     rsi, [rbx+0B8h]
0x180007e71  test    rsi, rsi
0x180007e74  jz      short loc_180007EA1
0x180007e76  mov     rcx, [rsi]
0x180007e79  mov     rax, [rcx+8]
0x180007e7d  mov     [rax], rbp
0x180007e80  mov     rcx, [rcx]; Block
0x180007e83  test    rcx, rcx
0x180007e86  jnz     loc_1800081E7
0x180007e8c  mov     rcx, [rsi]; Block
0x180007e8f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e94  mov     edx, 10h
0x180007e99  mov     rcx, rsi; Block
0x180007e9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007ea1  mov     rsi, [rbx+0B0h]
0x180007ea8  test    rsi, rsi
0x180007eab  jnz     loc_18000804D
0x180007eb1  mov     rcx, [rbx+0A8h]; lpCriticalSection
0x180007eb8  test    rcx, rcx
0x180007ebb  jz      short loc_180007EC3
0x180007ebd  call    cs:__imp_DeleteCriticalSection
0x180007ec3  mov     rsi, [rbx+70h]
0x180007ec7  test    rsi, rsi
0x180007eca  jz      short loc_180007F29
0x180007ecc  mov     rcx, [rsi+48h]; lpCriticalSection
0x180007ed0  test    rcx, rcx
0x180007ed3  jz      short loc_180007EDB
0x180007ed5  call    cs:__imp_DeleteCriticalSection
0x180007edb  mov     r14, [rsi+18h]
0x180007edf  test    r14, r14
0x180007ee2  jz      short loc_180007F0F
0x180007ee4  mov     rcx, [r14]
0x180007ee7  mov     rax, [rcx+8]
0x180007eeb  mov     [rax], rbp
0x180007eee  mov     rcx, [rcx]; Block
0x180007ef1  test    rcx, rcx
0x180007ef4  jnz     loc_180008120
0x180007efa  mov     rcx, [r14]; Block
0x180007efd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f02  mov     edx, 10h
0x180007f07  mov     rcx, r14; Block
0x180007f0a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007f0f  mov     r14, [rsi+10h]
0x180007f13  test    r14, r14
0x180007f16  jnz     loc_1800080AD
0x180007f1c  mov     edx, 50h ; 'P'
0x180007f21  mov     rcx, rsi; Block
0x180007f24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007f29  mov     [rbx+70h], rbp
0x180007f2d  mov     rcx, [rbx+68h]; bstrString
0x180007f31  call    cs:__imp_SysFreeString
0x180007f37  mov     rdi, [rbx+60h]
0x180007f3b  test    rdi, rdi
0x180007f3e  jz      short loc_180007F5D
0x180007f40  mov     rdx, [rdi]
0x180007f43  call    ??$_Free_non_head@V?$STLWrap_allocator@U?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@@@@?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@SAXAEAV?$STLWrap_allocator@U?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@@@PEAU01@@Z; std::_List_node<_POLICY_SECTION_CONTEXT *,void *>::_Free_non_head<STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>>>(STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>> &,std::_List_node<_POLICY_SECTION_CONTEXT *,void *> *)
0x180007f48  mov     rcx, [rdi]; Block
0x180007f4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f50  mov     edx, 10h
0x180007f55  mov     rcx, rdi; Block
0x180007f58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007f5d  mov     rsi, [rbx+58h]
0x180007f61  test    rsi, rsi
0x180007f64  jz      short loc_180007F91
0x180007f66  mov     rcx, [rsi]
0x180007f69  mov     rax, [rcx+8]
0x180007f6d  mov     [rax], rbp
0x180007f70  mov     rcx, [rcx]; Block
0x180007f73  test    rcx, rcx
0x180007f76  jnz     loc_180008211
0x180007f7c  mov     rcx, [rsi]; Block
0x180007f7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f84  mov     edx, 10h
0x180007f89  mov     rcx, rsi; Block
0x180007f8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007f91  mov     rsi, [rbx+50h]
0x180007f95  test    rsi, rsi
0x180007f98  jnz     loc_18000807D
0x180007f9e  mov     rcx, [rbx+48h]; lpCriticalSection
0x180007fa2  test    rcx, rcx
0x180007fa5  jz      short loc_180007FAD
0x180007fa7  call    cs:__imp_DeleteCriticalSection
0x180007fad  mov     rsi, [rbx+10h]
0x180007fb1  test    rsi, rsi
0x180007fb4  jz      loc_18000803E
0x180007fba  mov     rcx, [rsi+48h]; lpCriticalSection
0x180007fbe  test    rcx, rcx
0x180007fc1  jz      short loc_180007FC9
0x180007fc3  call    cs:__imp_DeleteCriticalSection
0x180007fc9  mov     r14, [rsi+18h]
0x180007fcd  test    r14, r14
0x180007fd0  jz      short loc_180007FFD
0x180007fd2  mov     rcx, [r14]
0x180007fd5  mov     rax, [rcx+8]
0x180007fd9  mov     [rax], rbp
0x180007fdc  mov     rcx, [rcx]; Block
0x180007fdf  test    rcx, rcx
0x180007fe2  jnz     loc_180008135
0x180007fe8  mov     rcx, [r14]; Block
0x180007feb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007ff0  mov     edx, 10h
0x180007ff5  mov     rcx, r14; Block
0x180007ff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007ffd  mov     r14, [rsi+10h]
0x180008001  test    r14, r14
0x180008004  jz      short loc_180008031
0x180008006  mov     rcx, [r14]
0x180008009  mov     rax, [rcx+8]
0x18000800d  mov     [rax], rbp
0x180008010  mov     rcx, [rcx]; Block
0x180008013  test    rcx, rcx
0x180008016  jnz     loc_180008150
0x18000801c  mov     rcx, [r14]; Block
0x18000801f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008024  mov     edx, 10h
0x180008029  mov     rcx, r14; Block
0x18000802c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008031  mov     edx, 50h ; 'P'
0x180008036  mov     rcx, rsi; Block
0x180008039  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000803e  mov     [rbx+10h], rbp
0x180008042  add     rsp, 20h
0x180008046  pop     r14
0x180008048  pop     rdi
0x180008049  pop     rsi
0x18000804a  pop     rbp
0x18000804b  pop     rbx
0x18000804c  retn
0x18000804d  mov     rcx, [rsi]
0x180008050  mov     rax, [rcx+8]
0x180008054  mov     [rax], rbp
0x180008057  mov     rcx, [rcx]; Block
0x18000805a  test    rcx, rcx
0x18000805d  jnz     loc_1800081FC
0x180008063  mov     rcx, [rsi]; Block
0x180008066  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000806b  mov     edx, 10h
0x180008070  mov     rcx, rsi; Block
0x180008073  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008078  jmp     loc_180007EB1
0x18000807d  mov     rcx, [rsi]
0x180008080  mov     rax, [rcx+8]
0x180008084  mov     [rax], rbp
0x180008087  mov     rcx, [rcx]; Block
0x18000808a  test    rcx, rcx
0x18000808d  jnz     loc_180008226
0x180008093  mov     rcx, [rsi]; Block
0x180008096  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000809b  mov     edx, 10h
0x1800080a0  mov     rcx, rsi; Block
0x1800080a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800080a8  jmp     loc_180007F9E
0x1800080ad  mov     rcx, [r14]
0x1800080b0  mov     rax, [rcx+8]
0x1800080b4  mov     [rax], rbp
0x1800080b7  mov     rcx, [rcx]; Block
0x1800080ba  test    rcx, rcx
0x1800080bd  jz      short loc_1800080CF
0x1800080bf  mov     rdi, [rcx]
0x1800080c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800080c7  mov     rcx, rdi
0x1800080ca  test    rdi, rdi
0x1800080cd  jnz     short loc_1800080BF
0x1800080cf  mov     rcx, [r14]; Block
0x1800080d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800080d7  mov     edx, 10h
0x1800080dc  mov     rcx, r14; Block
0x1800080df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800080e4  jmp     loc_180007F1C
0x1800080e9  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x1800080ef  jz      loc_180007E34
0x1800080f5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800080fc  test    rax, rax
0x1800080ff  jz      loc_1800081B7
0x180008105  lea     rdx, aDeletingMachin; "Deleting machine"
0x18000810c  mov     ecx, 4
0x180008111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008116  jmp     loc_180007E34
0x180008120  mov     rdi, [rcx]
0x180008123  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008128  mov     rcx, rdi
0x18000812b  test    rdi, rdi
0x18000812e  jnz     short loc_180008120
0x180008130  jmp     loc_180007EFA
0x180008135  mov     rdi, [rcx]
0x180008138  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000813d  mov     rcx, rdi
0x180008140  test    rdi, rdi
0x180008143  jnz     short loc_180008135
0x180008145  jmp     loc_180007FE8
0x180008150  mov     rdi, [rcx]
0x180008153  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008158  mov     rcx, rdi
0x18000815b  test    rdi, rdi
0x18000815e  jnz     short loc_180008150
0x180008160  jmp     loc_18000801C
0x180008165  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000816c  test    rax, rax
0x18000816f  jz      short loc_180008187
0x180008171  lea     rdx, aDeletingSidstr; "Deleting sidString <%ws>"
0x180008178  mov     ecx, 4
0x18000817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008182  jmp     loc_180007E28
0x180008187  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18000818e  jz      loc_180007E28
0x180008194  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000819b  jz      loc_180007E28
0x1800081a1  lea     rdx, aDeletingSidstr; "Deleting sidString <%ws>"
0x1800081a8  mov     ecx, 4; unsigned int
0x1800081ad  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800081b2  jmp     loc_180007E28
0x1800081b7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x1800081be  jz      loc_180007E34
0x1800081c4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800081cb  jz      loc_180007E34
0x1800081d1  lea     rdx, aDeletingMachin; "Deleting machine"
0x1800081d8  mov     ecx, 4; unsigned int
0x1800081dd  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800081e2  jmp     loc_180007E34
0x1800081e7  mov     rdi, [rcx]
0x1800081ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800081ef  mov     rcx, rdi
0x1800081f2  test    rdi, rdi
0x1800081f5  jnz     short loc_1800081E7
0x1800081f7  jmp     loc_180007E8C
0x1800081fc  mov     rdi, [rcx]
0x1800081ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008204  mov     rcx, rdi
0x180008207  test    rdi, rdi
0x18000820a  jnz     short loc_1800081FC
0x18000820c  jmp     loc_180008063
0x180008211  mov     rdi, [rcx]
0x180008214  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008219  mov     rcx, rdi
0x18000821c  test    rdi, rdi
0x18000821f  jnz     short loc_180008211
0x180008221  jmp     loc_180007F7C
0x180008226  mov     rdi, [rcx]
0x180008229  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000822e  mov     rcx, rdi
0x180008231  test    rdi, rdi
0x180008234  jnz     short loc_180008226
0x180008236  jmp     loc_180008093
```
