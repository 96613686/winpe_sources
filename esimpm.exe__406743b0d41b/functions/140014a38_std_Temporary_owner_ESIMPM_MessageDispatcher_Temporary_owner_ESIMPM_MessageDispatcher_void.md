# std::_Temporary_owner<ESIMPM::MessageDispatcher>::~_Temporary_owner<ESIMPM::MessageDispatcher>(void)

- ea: `0x140014a38`
- end: `0x140014a6b`
- name: `??1?$_Temporary_owner@VMessageDispatcher@ESIMPM@@@std@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x14003c7f5`

## callees

- `0x140003244`
- `0x140014a38`
- `0x140014abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140014a4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140014a4a`

## pseudocode

```c
void __fastcall std::_Temporary_owner<ESIMPM::MessageDispatcher>::~_Temporary_owner<ESIMPM::MessageDispatcher>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
    std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(v1);
    operator delete((void *)v1);
  }
}

```

## disassembly

```asm
0x140014a38  push    rbx
0x140014a3a  sub     rsp, 20h
0x140014a3e  mov     rbx, [rcx]
0x140014a41  test    rbx, rbx
0x140014a44  jz      short loc_140014A65
0x140014a46  lea     rcx, [rbx+10h]; lpCriticalSection
0x140014a4a  call    cs:__imp_DeleteCriticalSection
0x140014a50  mov     rcx, rbx
0x140014a53  call    ??1?$list@V?$shared_ptr@VMessage@ESIMPM@@@std@@V?$allocator@V?$shared_ptr@VMessage@ESIMPM@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(void)
0x140014a58  mov     edx, 98h
0x140014a5d  mov     rcx, rbx; Block
0x140014a60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014a65  add     rsp, 20h
0x140014a69  pop     rbx
0x140014a6a  retn
```
