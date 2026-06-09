# tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)

- ea: `0x140004fa0`
- end: `0x140004fd0`
- name: `??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004f5c`

## callees

- `0x1400050a0`
- `0x140005480`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004fb0`
- `KERNEL32!DeleteCriticalSection` at `0x140004fb0`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(a1 + 240);
  tip2::test_state::~test_state((tip2::test_state *)(a1 + 8));
}

```

## disassembly

```asm
0x140004fa0  push    rbx
0x140004fa2  sub     rsp, 20h
0x140004fa6  mov     rbx, rcx
0x140004fa9  add     rcx, 0C0h; lpCriticalSection
0x140004fb0  call    cs:__imp_DeleteCriticalSection
0x140004fb6  lea     rcx, [rbx+0F0h]
0x140004fbd  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x140004fc2  lea     rcx, [rbx+8]; this
0x140004fc6  add     rsp, 20h
0x140004fca  pop     rbx
0x140004fcb  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
