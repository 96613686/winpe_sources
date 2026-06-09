# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x1800094f0`
- end: `0x180009524`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x180009054`
- `0x1800094f0`

## pseudocode

```c
void *__fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800094f0  mov     [rsp+arg_0], rbx
0x1800094f5  push    rdi
0x1800094f6  sub     rsp, 20h
0x1800094fa  mov     ebx, edx
0x1800094fc  mov     rdi, rcx
0x1800094ff  call    ??1?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void)
0x180009504  test    bl, 1
0x180009507  jz      short loc_180009516
0x180009509  mov     edx, 0C0h; unsigned __int64
0x18000950e  mov     rcx, rdi; void *
0x180009511  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009516  mov     rbx, [rsp+28h+arg_0]
0x18000951b  mov     rax, rdi
0x18000951e  add     rsp, 20h
0x180009522  pop     rdi
0x180009523  retn
```
