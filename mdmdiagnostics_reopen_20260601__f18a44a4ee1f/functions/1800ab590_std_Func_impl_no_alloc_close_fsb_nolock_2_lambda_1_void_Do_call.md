# std::_Func_impl_no_alloc___close_fsb_nolock_::_2_::_lambda_1__void_::_Do_call

- ea: `0x1800ab590`
- end: `0x1800ab6ec`
- name: `std::_Func_impl_no_alloc___close_fsb_nolock_::_2_::_lambda_1__void_::_Do_call`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180016c80`
- `0x180016d2f`
- `0x180019588`
- `0x180019ede`
- `0x18001af10`
- `0x18001b000`
- `0x18001b0a0`
- `0x18001b180`
- `0x18001b2b0`
- `0x1800a9eed`
- `0x1800ab590`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab673`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800ab5ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800ab5ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab5fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab5fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Func_impl_no_alloc___close_fsb_nolock_::_2_::_lambda_1__void_::_Do_call(__int64 a1)
{
  bool v2; // bp
  __int64 v3; // rbx
  DWORD CurrentThreadId; // esi
  __int64 v5; // rcx
  __int64 v7; // rbx
  DWORD LastError; // eax
  _QWORD *system_error; // rbx
  __int128 v10; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v11[88]; // [rsp+30h] [rbp-58h] BYREF

  v2 = 0;
  v3 = *(_QWORD *)(a1 + 8);
  CurrentThreadId = pplx::details::platform::GetCurrentThreadId();
  if ( *(_DWORD *)(v3 + 140) == CurrentThreadId )
  {
    ++*(_DWORD *)(v3 + 136);
  }
  else
  {
    pplx::details::critical_section_impl::lock((LPCRITICAL_SECTION)(v3 + 72));
    *(_DWORD *)(v3 + 140) = CurrentThreadId;
    *(_DWORD *)(v3 + 136) = 1;
  }
  v5 = *(_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(v5 + 144) != -1 )
  {
    CloseThreadpoolIo(*(PTP_IO *)(v5 + 152));
    v2 = CloseHandle(*(HANDLE *)(*(_QWORD *)(a1 + 8) + 144LL));
  }
  operator delete(*(void **)(*(_QWORD *)(a1 + 8) + 32LL));
  if ( (*(_DWORD *)(v3 + 136))-- == 1 )
  {
    *(_DWORD *)(v3 + 140) = -1;
    pplx::details::critical_section_impl::unlock((LPCRITICAL_SECTION)(v3 + 72));
  }
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
  {
    pplx::details::critical_section_impl::~critical_section_impl((LPCRITICAL_SECTION)(v7 + 72));
    operator delete((void *)v7);
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
  }
  else
  {
    LastError = GetLastError();
    system_error = (_QWORD *)utility::details::create_system_error(v11, LastError);
    v10 = 0;
    __ExceptionPtrCreate(&v10);
    __ExceptionPtrCopyException(&v10, system_error, &TI4_AVsystem_error_std__);
    *system_error = &std::exception::`vftable';
    o___std_exception_destroy_0(system_error + 1);
    (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16), &v10);
    __ExceptionPtrDestroy(&v10);
  }
}

```

## disassembly

```asm
0x1800ab590  push    rbx
0x1800ab592  push    rbp
0x1800ab593  push    rsi
0x1800ab594  push    rdi
0x1800ab595  sub     rsp, 68h
0x1800ab599  mov     rdi, rcx
0x1800ab59c  xor     bpl, bpl
0x1800ab59f  mov     rbx, [rcx+8]
0x1800ab5a3  call    ?GetCurrentThreadId@platform@details@pplx@@YAJXZ; pplx::details::platform::GetCurrentThreadId(void)
0x1800ab5a8  mov     esi, eax
0x1800ab5aa  mov     edx, [rbx+8Ch]
0x1800ab5b0  cmp     edx, eax
0x1800ab5b2  jnz     short loc_1800AB5BC
0x1800ab5b4  inc     dword ptr [rbx+88h]
0x1800ab5ba  jmp     short loc_1800AB5D5
0x1800ab5bc  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800ab5c0  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x1800ab5c5  mov     [rbx+8Ch], esi
0x1800ab5cb  mov     dword ptr [rbx+88h], 1
0x1800ab5d5  mov     rcx, [rdi+8]
0x1800ab5d9  cmp     qword ptr [rcx+90h], 0FFFFFFFFFFFFFFFFh
0x1800ab5e1  jz      short loc_1800AB607
0x1800ab5e3  mov     rcx, [rcx+98h]; pio
0x1800ab5ea  call    cs:__imp_CloseThreadpoolIo
0x1800ab5f0  mov     rcx, [rdi+8]
0x1800ab5f4  mov     rcx, [rcx+90h]; hObject
0x1800ab5fb  call    cs:__imp_CloseHandle
0x1800ab601  test    eax, eax
0x1800ab603  setnz   bpl
0x1800ab607  mov     rcx, [rdi+8]
0x1800ab60b  mov     edx, 1
0x1800ab610  mov     rcx, [rcx+20h]; Block
0x1800ab614  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab619  nop
0x1800ab61a  sub     dword ptr [rbx+88h], 1
0x1800ab621  jnz     short loc_1800AB637
0x1800ab623  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x1800ab62d  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800ab631  call    ?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x1800ab636  nop
0x1800ab637  mov     rbx, [rdi+8]
0x1800ab63b  test    rbx, rbx
0x1800ab63e  jz      short loc_1800AB656
0x1800ab640  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800ab644  call    ??1critical_section_impl@details@pplx@@QEAA@XZ; pplx::details::critical_section_impl::~critical_section_impl(void)
0x1800ab649  mov     edx, 0A0h
0x1800ab64e  mov     rcx, rbx; Block
0x1800ab651  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab656  test    bpl, bpl
0x1800ab659  jz      short loc_1800AB673
0x1800ab65b  mov     rcx, [rdi+10h]
0x1800ab65f  mov     rax, [rcx]
0x1800ab662  mov     rax, [rax+8]
0x1800ab666  add     rsp, 68h
0x1800ab66a  pop     rdi
0x1800ab66b  pop     rsi
0x1800ab66c  pop     rbp
0x1800ab66d  pop     rbx
0x1800ab66e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab673  call    cs:__imp_GetLastError
0x1800ab679  mov     edx, eax
0x1800ab67b  lea     rcx, [rsp+88h+var_58]
0x1800ab680  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800ab685  mov     rbx, rax
0x1800ab688  xorps   xmm0, xmm0
0x1800ab68b  movdqu  [rsp+88h+var_68], xmm0
0x1800ab691  lea     rcx, [rsp+88h+var_68]; void *
0x1800ab696  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800ab69b  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800ab6a2  mov     rdx, rbx; void *
0x1800ab6a5  lea     rcx, [rsp+88h+var_68]; void *
0x1800ab6aa  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800ab6af  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800ab6b6  mov     [rbx], rax
0x1800ab6b9  lea     rcx, [rbx+8]
0x1800ab6bd  call    _o___std_exception_destroy_0
0x1800ab6c2  nop
0x1800ab6c3  mov     rcx, [rdi+10h]
0x1800ab6c7  mov     rax, [rcx]
0x1800ab6ca  lea     rdx, [rsp+88h+var_68]
0x1800ab6cf  mov     rax, [rax+10h]
0x1800ab6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab6d8  nop
0x1800ab6d9  lea     rcx, [rsp+88h+var_68]; void *
0x1800ab6de  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800ab6e3  add     rsp, 68h
0x1800ab6e7  pop     rdi
0x1800ab6e8  pop     rsi
0x1800ab6e9  pop     rbp
0x1800ab6ea  pop     rbx
0x1800ab6eb  retn
```
