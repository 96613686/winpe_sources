# wil::details::lambda_call__ESIMPM::MessageDispatcher::_Start_::_3_::_lambda_1___::_lambda_call__ESIMPM::MessageDispatcher::_Start_::_3_::_lambda_1___

- ea: `0x140014a74`
- end: `0x140014ab4`
- name: `wil::details::lambda_call__ESIMPM::MessageDispatcher::_Start_::_3_::_lambda_1___::_lambda_call__ESIMPM::MessageDispatcher::_Start_::_3_::_lambda_1___`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x14003c7e3`

## callees

- `0x140003244`
- `0x140014a74`
- `0x140014abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140014a93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140014a93`

## pseudocode

```c
void __fastcall wil::details::lambda_call__ESIMPM::MessageDispatcher::_Start_::_3_::_lambda_1___::_lambda_call__ESIMPM::MessageDispatcher::_Start_::_3_::_lambda_1___(
        __int64 a1)
{
  __int64 *v1; // rax
  __int64 v2; // rbx

  if ( *(_BYTE *)(a1 + 8) )
  {
    v1 = *(__int64 **)a1;
    *(_BYTE *)(a1 + 8) = 0;
    v2 = *v1;
    if ( *v1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
      std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(v2);
      operator delete((void *)v2);
    }
  }
}

```

## disassembly

```asm
0x140014a74  push    rbx
0x140014a76  sub     rsp, 20h
0x140014a7a  cmp     byte ptr [rcx+8], 0
0x140014a7e  jz      short loc_140014AAE
0x140014a80  mov     rax, [rcx]
0x140014a83  mov     byte ptr [rcx+8], 0
0x140014a87  mov     rbx, [rax]
0x140014a8a  test    rbx, rbx
0x140014a8d  jz      short loc_140014AAE
0x140014a8f  lea     rcx, [rbx+10h]; lpCriticalSection
0x140014a93  call    cs:__imp_DeleteCriticalSection
0x140014a99  mov     rcx, rbx
0x140014a9c  call    ??1?$list@V?$shared_ptr@VMessage@ESIMPM@@@std@@V?$allocator@V?$shared_ptr@VMessage@ESIMPM@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(void)
0x140014aa1  mov     edx, 98h
0x140014aa6  mov     rcx, rbx; Block
0x140014aa9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014aae  add     rsp, 20h
0x140014ab2  pop     rbx
0x140014ab3  retn
```
