# EventLogger::`vector deleting destructor'(uint)

- ea: `0x180002ca0`
- end: `0x180002cde`
- name: `??_EEventLogger@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(EventLogger *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001f70`
- `0x180002ca0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002cca`
- `ole32!CoTaskMemFree` at `0x180002cca`

## pseudocode

```c
EventLogger *__fastcall EventLogger::`vector deleting destructor'(EventLogger *this, char a2)
{
  *(_QWORD *)this = &EventLogger::`vftable';
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((char *)this + 16);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180002ca0  mov     [rsp+arg_0], rbx
0x180002ca5  push    rdi
0x180002ca6  sub     rsp, 20h
0x180002caa  lea     rax, ??_7EventLogger@@6B@; const EventLogger::`vftable'
0x180002cb1  mov     rdi, rcx
0x180002cb4  mov     [rcx], rax
0x180002cb7  mov     ebx, edx
0x180002cb9  add     rcx, 10h
0x180002cbd  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180002cc2  test    bl, 1
0x180002cc5  jz      short loc_180002CD0
0x180002cc7  mov     rcx, rdi; pv
0x180002cca  call    cs:__imp_CoTaskMemFree
0x180002cd0  mov     rbx, [rsp+28h+arg_0]
0x180002cd5  mov     rax, rdi
0x180002cd8  add     rsp, 20h
0x180002cdc  pop     rdi
0x180002cdd  retn
```
