# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180009430`
- end: `0x180009464`
- name: `??_E?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x180008fa8`
- `0x180009430`

## pseudocode

```c
Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009430  mov     [rsp+arg_0], rbx
0x180009435  push    rdi
0x180009436  sub     rsp, 20h
0x18000943a  mov     ebx, edx
0x18000943c  mov     rdi, rcx
0x18000943f  call    ??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)
0x180009444  test    bl, 1
0x180009447  jz      short loc_180009456
0x180009449  mov     edx, 28h ; '('; unsigned __int64
0x18000944e  mov     rcx, rdi; void *
0x180009451  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009456  mov     rbx, [rsp+28h+arg_0]
0x18000945b  mov     rax, rdi
0x18000945e  add     rsp, 20h
0x180009462  pop     rdi
0x180009463  retn
```
