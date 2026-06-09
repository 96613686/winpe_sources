# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001ee70`
- end: `0x18001eea4`
- name: `??_G?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x18001ec38`
- `0x18001ee70`

## pseudocode

```c
Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001ee70  mov     [rsp+arg_0], rbx
0x18001ee75  push    rdi
0x18001ee76  sub     rsp, 20h
0x18001ee7a  mov     ebx, edx
0x18001ee7c  mov     rdi, rcx
0x18001ee7f  call    ??1?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>(void)
0x18001ee84  test    bl, 1
0x18001ee87  jz      short loc_18001EE96
0x18001ee89  mov     edx, 90h; unsigned __int64
0x18001ee8e  mov     rcx, rdi; void *
0x18001ee91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ee96  mov     rbx, [rsp+28h+arg_0]
0x18001ee9b  mov     rax, rdi
0x18001ee9e  add     rsp, 20h
0x18001eea2  pop     rdi
0x18001eea3  retn
```
