# ATL::CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>::~CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>(void)

- ea: `0x180007bb8`
- end: `0x180007bf7`
- name: `??1?$CCommand@VCDynamicAccessor@ATL@@VCRowset@2@VCNoMultipleResults@2@@ATL@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b4bf`

## callees

- `0x180007b0c`
- `0x180007bb8`
- `0x18000a420`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>::~CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>(
        __int64 a1)
{
  __int64 v2; // rcx

  ATL::CCommandBase::ReleaseCommand((ATL::CCommandBase *)(a1 + 112));
  v2 = *(_QWORD *)(a1 + 112);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::~CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>(a1);
}

```

## disassembly

```asm
0x180007bb8  mov     [rsp+arg_0], rbx
0x180007bbd  push    rdi
0x180007bbe  sub     rsp, 20h
0x180007bc2  mov     rdi, rcx
0x180007bc5  add     rcx, 70h ; 'p'; this
0x180007bc9  call    ?ReleaseCommand@CCommandBase@ATL@@QEAAXXZ; ATL::CCommandBase::ReleaseCommand(void)
0x180007bce  nop
0x180007bcf  mov     rcx, [rdi+70h]
0x180007bd3  test    rcx, rcx
0x180007bd6  jz      short loc_180007BE5
0x180007bd8  mov     rax, [rcx]
0x180007bdb  mov     rax, [rax+10h]
0x180007bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be4  nop
0x180007be5  mov     rcx, rdi
0x180007be8  mov     rbx, [rsp+28h+arg_0]
0x180007bed  add     rsp, 20h
0x180007bf1  pop     rdi
0x180007bf2  jmp     ??1?$CAccessorRowset@VCDynamicAccessor@ATL@@VCRowset@2@@ATL@@QEAA@XZ; ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::~CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>(void)
```
