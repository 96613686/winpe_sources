# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180018b30`
- end: `0x180018b64`
- name: `??_G?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x1800186ec`
- `0x180018b30`

## pseudocode

```c
Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180018b30  mov     [rsp+arg_0], rbx
0x180018b35  push    rdi
0x180018b36  sub     rsp, 20h
0x180018b3a  mov     ebx, edx
0x180018b3c  mov     rdi, rcx
0x180018b3f  call    ??1?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>(void)
0x180018b44  test    bl, 1
0x180018b47  jz      short loc_180018B56
0x180018b49  mov     edx, 0B8h; unsigned __int64
0x180018b4e  mov     rcx, rdi; void *
0x180018b51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018b56  mov     rbx, [rsp+28h+arg_0]
0x180018b5b  mov     rax, rdi
0x180018b5e  add     rsp, 20h
0x180018b62  pop     rdi
0x180018b63  retn
```
