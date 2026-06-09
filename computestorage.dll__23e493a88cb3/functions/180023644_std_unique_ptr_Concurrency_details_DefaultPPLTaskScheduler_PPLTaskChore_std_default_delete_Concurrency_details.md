# std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore,std::default_delete<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>>(void)

- ea: `0x180023644`
- end: `0x180023677`
- name: `??1?$unique_ptr@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@U?$default_delete@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@@std@@@std@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(Concurrency::details **, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180044734`

## callees

- `0x180002b74`
- `0x180023644`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180023655`
- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180023655`

## pseudocode

```c
void __fastcall std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>(
        Concurrency::details **a1,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  Concurrency::details *v2; // rbx

  v2 = *a1;
  if ( *a1 )
  {
    Concurrency::details::_Release_chore(*a1, a2);
    operator delete(v2, 0x28u);
  }
}

```

## disassembly

```asm
0x180023644  push    rbx
0x180023646  sub     rsp, 20h
0x18002364a  mov     rbx, [rcx]
0x18002364d  test    rbx, rbx
0x180023650  jz      short loc_180023670
0x180023652  mov     rcx, rbx
0x180023655  call    cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z; Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)
0x18002365c  nop     dword ptr [rax+rax+00h]
0x180023661  nop
0x180023662  mov     edx, 28h ; '('; unsigned __int64
0x180023667  mov     rcx, rbx; void *
0x18002366a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002366f  nop
0x180023670  add     rsp, 20h
0x180023674  pop     rbx
0x180023675  retn
```
