# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x1800123c0`
- end: `0x1800123f5`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x180011c3c`
- `0x1800123c0`

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
0x1800123c0  mov     [rsp+arg_0], rbx
0x1800123c5  push    rdi
0x1800123c6  sub     rsp, 20h
0x1800123ca  mov     ebx, edx
0x1800123cc  mov     rdi, rcx
0x1800123cf  call    ??1?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>(void)
0x1800123d4  test    bl, 1
0x1800123d7  jz      short loc_1800123E6
0x1800123d9  mov     edx, 1A8h; unsigned __int64
0x1800123de  mov     rcx, rdi; void *
0x1800123e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800123e6  mov     rbx, [rsp+28h+arg_0]
0x1800123eb  mov     rax, rdi
0x1800123ee  add     rsp, 20h
0x1800123f2  pop     rdi
0x1800123f3  retn
```
