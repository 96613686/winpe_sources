# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18000f600`
- end: `0x18000f635`
- name: `??_E?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x18000f5a8`
- `0x18000f600`

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
0x18000f600  mov     [rsp+arg_0], rbx
0x18000f605  push    rdi
0x18000f606  sub     rsp, 20h
0x18000f60a  mov     ebx, edx
0x18000f60c  mov     rdi, rcx
0x18000f60f  call    ??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)
0x18000f614  test    bl, 1
0x18000f617  jz      short loc_18000F626
0x18000f619  mov     edx, 20h ; ' '; unsigned __int64
0x18000f61e  mov     rcx, rdi; void *
0x18000f621  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f626  mov     rbx, [rsp+28h+arg_0]
0x18000f62b  mov     rax, rdi
0x18000f62e  add     rsp, 20h
0x18000f632  pop     rdi
0x18000f633  retn
```
