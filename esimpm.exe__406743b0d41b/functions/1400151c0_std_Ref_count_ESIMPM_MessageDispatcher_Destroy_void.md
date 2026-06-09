# std::_Ref_count<ESIMPM::MessageDispatcher>::_Destroy(void)

- ea: `0x1400151c0`
- end: `0x1400151f4`
- name: `?_Destroy@?$_Ref_count@VMessageDispatcher@ESIMPM@@@std@@EEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x140003244`
- `0x140014abc`
- `0x1400151c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400151d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400151d3`

## pseudocode

```c
void __fastcall std::_Ref_count<ESIMPM::MessageDispatcher>::_Destroy(__int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 16);
  if ( v1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
    std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(v1);
    operator delete((void *)v1);
  }
}

```

## disassembly

```asm
0x1400151c0  push    rbx
0x1400151c2  sub     rsp, 20h
0x1400151c6  mov     rbx, [rcx+10h]
0x1400151ca  test    rbx, rbx
0x1400151cd  jz      short loc_1400151EE
0x1400151cf  lea     rcx, [rbx+10h]; lpCriticalSection
0x1400151d3  call    cs:__imp_DeleteCriticalSection
0x1400151d9  mov     rcx, rbx
0x1400151dc  call    ??1?$list@V?$shared_ptr@VMessage@ESIMPM@@@std@@V?$allocator@V?$shared_ptr@VMessage@ESIMPM@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(void)
0x1400151e1  mov     edx, 98h
0x1400151e6  mov     rcx, rbx; Block
0x1400151e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400151ee  add     rsp, 20h
0x1400151f2  pop     rbx
0x1400151f3  retn
```
