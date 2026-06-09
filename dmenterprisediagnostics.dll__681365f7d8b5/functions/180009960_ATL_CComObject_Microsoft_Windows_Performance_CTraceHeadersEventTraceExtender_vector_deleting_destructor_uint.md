# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180009960`
- end: `0x180009995`
- name: `??_E?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x180009494`
- `0x180009960`

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
0x180009960  mov     [rsp+arg_0], rbx
0x180009965  push    rdi
0x180009966  sub     rsp, 20h
0x18000996a  mov     ebx, edx
0x18000996c  mov     rdi, rcx
0x18000996f  call    ??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)
0x180009974  test    bl, 1
0x180009977  jz      short loc_180009986
0x180009979  mov     edx, 20h ; ' '; unsigned __int64
0x18000997e  mov     rcx, rdi; void *
0x180009981  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009986  mov     rbx, [rsp+28h+arg_0]
0x18000998b  mov     rax, rdi
0x18000998e  add     rsp, 20h
0x180009992  pop     rdi
0x180009993  retn
```
