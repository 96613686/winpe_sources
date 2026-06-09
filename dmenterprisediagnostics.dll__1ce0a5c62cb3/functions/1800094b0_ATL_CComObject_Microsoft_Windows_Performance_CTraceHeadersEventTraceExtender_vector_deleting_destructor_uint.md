# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800094b0`
- end: `0x1800094e4`
- name: `??_E?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x180009014`
- `0x1800094b0`

## pseudocode

```c
Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800094b0  mov     [rsp+arg_0], rbx
0x1800094b5  push    rdi
0x1800094b6  sub     rsp, 20h
0x1800094ba  mov     ebx, edx
0x1800094bc  mov     rdi, rcx
0x1800094bf  call    ??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)
0x1800094c4  test    bl, 1
0x1800094c7  jz      short loc_1800094D6
0x1800094c9  mov     edx, 20h ; ' '; unsigned __int64
0x1800094ce  mov     rcx, rdi; void *
0x1800094d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800094d6  mov     rbx, [rsp+28h+arg_0]
0x1800094db  mov     rax, rdi
0x1800094de  add     rsp, 20h
0x1800094e2  pop     rdi
0x1800094e3  retn
```
