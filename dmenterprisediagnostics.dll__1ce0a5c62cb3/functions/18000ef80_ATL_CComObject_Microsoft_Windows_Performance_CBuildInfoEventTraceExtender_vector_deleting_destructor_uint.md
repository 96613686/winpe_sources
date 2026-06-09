# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18000ef80`
- end: `0x18000efb4`
- name: `??_E?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x18000ef34`
- `0x18000ef80`

## pseudocode

```c
Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ef80  mov     [rsp+arg_0], rbx
0x18000ef85  push    rdi
0x18000ef86  sub     rsp, 20h
0x18000ef8a  mov     ebx, edx
0x18000ef8c  mov     rdi, rcx
0x18000ef8f  call    ??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)
0x18000ef94  test    bl, 1
0x18000ef97  jz      short loc_18000EFA6
0x18000ef99  mov     edx, 20h ; ' '; unsigned __int64
0x18000ef9e  mov     rcx, rdi; void *
0x18000efa1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000efa6  mov     rbx, [rsp+28h+arg_0]
0x18000efab  mov     rax, rdi
0x18000efae  add     rsp, 20h
0x18000efb2  pop     rdi
0x18000efb3  retn
```
