# utils::CThreadPool::ThreadEntry(void *)

- ea: `0x18000f360`
- end: `0x18000f3f4`
- name: `?ThreadEntry@CThreadPool@utils@@CAIPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(utils::CThreadPool::WorkItemWrapper *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180008ac8`
- `0x18000f20c`
- `0x18000f360`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f3ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f3ba`

## pseudocode

```c
__int64 __fastcall utils::CThreadPool::ThreadEntry(utils::CThreadPool::WorkItemWrapper *a1)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1453a8e99c5333089a3beba4797e1efb_Traceguids);
  (***(void (__fastcall ****)(_QWORD))a1)(*(_QWORD *)a1);
  utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(a1);
  operator delete(a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_1453a8e99c5333089a3beba4797e1efb_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000f360  mov     [rsp+arg_8], rbx
0x18000f365  push    rdi
0x18000f366  sub     rsp, 20h
0x18000f36a  mov     rbx, rcx
0x18000f36d  lea     rdi, WPP_GLOBAL_Control
0x18000f374  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f37b  cmp     rcx, rdi
0x18000f37e  jz      short loc_18000F39B
0x18000f380  test    byte ptr [rcx+1Ch], 8
0x18000f384  jz      short loc_18000F39B
0x18000f386  mov     edx, 0Eh
0x18000f38b  lea     r8, WPP_1453a8e99c5333089a3beba4797e1efb_Traceguids
0x18000f392  mov     rcx, [rcx+10h]
0x18000f396  call    WPP_SF_
0x18000f39b  mov     [rsp+28h+arg_0], rbx
0x18000f3a0  mov     rcx, [rbx]
0x18000f3a3  mov     rax, [rcx]
0x18000f3a6  mov     rax, [rax]
0x18000f3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3ae  nop
0x18000f3af  mov     rcx, rbx; this
0x18000f3b2  call    ??1WorkItemWrapper@CThreadPool@utils@@QEAA@XZ; utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(void)
0x18000f3b7  mov     rcx, rbx
0x18000f3ba  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3c7  cmp     rcx, rdi
0x18000f3ca  jz      short loc_18000F3E7
0x18000f3cc  test    byte ptr [rcx+1Ch], 8
0x18000f3d0  jz      short loc_18000F3E7
0x18000f3d2  mov     edx, 0Fh
0x18000f3d7  lea     r8, WPP_1453a8e99c5333089a3beba4797e1efb_Traceguids
0x18000f3de  mov     rcx, [rcx+10h]
0x18000f3e2  call    WPP_SF_
0x18000f3e7  xor     eax, eax
0x18000f3e9  mov     rbx, [rsp+28h+arg_8]
0x18000f3ee  add     rsp, 20h
0x18000f3f2  pop     rdi
0x18000f3f3  retn
```
