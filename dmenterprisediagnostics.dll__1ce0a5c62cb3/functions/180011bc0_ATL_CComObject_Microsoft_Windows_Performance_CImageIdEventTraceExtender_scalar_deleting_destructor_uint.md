# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180011bc0`
- end: `0x180011bf4`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x180011480`
- `0x180011bc0`

## pseudocode

```c
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180011bc0  mov     [rsp+arg_0], rbx
0x180011bc5  push    rdi
0x180011bc6  sub     rsp, 20h
0x180011bca  mov     ebx, edx
0x180011bcc  mov     rdi, rcx
0x180011bcf  call    ??1?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>(void)
0x180011bd4  test    bl, 1
0x180011bd7  jz      short loc_180011BE6
0x180011bd9  mov     edx, 1A8h; unsigned __int64
0x180011bde  mov     rcx, rdi; void *
0x180011be1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011be6  mov     rbx, [rsp+28h+arg_0]
0x180011beb  mov     rax, rdi
0x180011bee  add     rsp, 20h
0x180011bf2  pop     rdi
0x180011bf3  retn
```
