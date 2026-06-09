# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001ccc0`
- end: `0x18001ccf4`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x18001c820`
- `0x18001ccc0`

## pseudocode

```c
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001ccc0  mov     [rsp+arg_0], rbx
0x18001ccc5  push    rdi
0x18001ccc6  sub     rsp, 20h
0x18001ccca  mov     ebx, edx
0x18001cccc  mov     rdi, rcx
0x18001cccf  call    ??1?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>(void)
0x18001ccd4  test    bl, 1
0x18001ccd7  jz      short loc_18001CCE6
0x18001ccd9  mov     edx, 180h; unsigned __int64
0x18001ccde  mov     rcx, rdi; void *
0x18001cce1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cce6  mov     rbx, [rsp+28h+arg_0]
0x18001cceb  mov     rax, rdi
0x18001ccee  add     rsp, 20h
0x18001ccf2  pop     rdi
0x18001ccf3  retn
```
