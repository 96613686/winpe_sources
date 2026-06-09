# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001d7d0`
- end: `0x18001d805`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x18001d2fc`
- `0x18001d7d0`

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
0x18001d7d0  mov     [rsp+arg_0], rbx
0x18001d7d5  push    rdi
0x18001d7d6  sub     rsp, 20h
0x18001d7da  mov     ebx, edx
0x18001d7dc  mov     rdi, rcx
0x18001d7df  call    ??1?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>(void)
0x18001d7e4  test    bl, 1
0x18001d7e7  jz      short loc_18001D7F6
0x18001d7e9  mov     edx, 180h; unsigned __int64
0x18001d7ee  mov     rcx, rdi; void *
0x18001d7f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d7f6  mov     rbx, [rsp+28h+arg_0]
0x18001d7fb  mov     rax, rdi
0x18001d7fe  add     rsp, 20h
0x18001d802  pop     rdi
0x18001d803  retn
```
