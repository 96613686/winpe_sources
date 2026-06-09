# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18001b740`
- end: `0x18001b775`
- name: `??_E?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x18001b4dc`
- `0x18001b740`

## pseudocode

```c
Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001b740  mov     [rsp+arg_0], rbx
0x18001b745  push    rdi
0x18001b746  sub     rsp, 20h
0x18001b74a  mov     ebx, edx
0x18001b74c  mov     rdi, rcx
0x18001b74f  call    ??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)
0x18001b754  test    bl, 1
0x18001b757  jz      short loc_18001B766
0x18001b759  mov     edx, 0B0h; unsigned __int64
0x18001b75e  mov     rcx, rdi; void *
0x18001b761  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b766  mov     rbx, [rsp+28h+arg_0]
0x18001b76b  mov     rax, rdi
0x18001b76e  add     rsp, 20h
0x18001b772  pop     rdi
0x18001b773  retn
```
