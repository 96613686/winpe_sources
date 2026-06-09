# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18001ac90`
- end: `0x18001acc4`
- name: `??_E?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x18001aa28`
- `0x18001ac90`

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
0x18001ac90  mov     [rsp+arg_0], rbx
0x18001ac95  push    rdi
0x18001ac96  sub     rsp, 20h
0x18001ac9a  mov     ebx, edx
0x18001ac9c  mov     rdi, rcx
0x18001ac9f  call    ??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)
0x18001aca4  test    bl, 1
0x18001aca7  jz      short loc_18001ACB6
0x18001aca9  mov     edx, 0B0h; unsigned __int64
0x18001acae  mov     rcx, rdi; void *
0x18001acb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001acb6  mov     rbx, [rsp+28h+arg_0]
0x18001acbb  mov     rax, rdi
0x18001acbe  add     rsp, 20h
0x18001acc2  pop     rdi
0x18001acc3  retn
```
