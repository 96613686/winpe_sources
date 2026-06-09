# OleCreatePictureIndirect

- ea: `0x18003ec20`
- end: `0x18003ec60`
- name: `OleCreatePictureIndirect`
- size: `64`
- prototype: `HRESULT __stdcall(LPPICTDESC lpPictDesc, const IID *const riid, BOOL fOwn, LPVOID *lplpvObj)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003ec20`
- `0x18004e87c`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreatePictureIndirectExt` at `0x18003ec4a`
- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreatePictureIndirectExt` at `0x18003ec4a`

## pseudocode

```c
HRESULT __stdcall OleCreatePictureIndirect(LPPICTDESC lpPictDesc, const IID *const riid, BOOL fOwn, LPVOID *lplpvObj)
{
  if ( (unsigned __int8)IsMonikerLoadTypeLibPresent() )
    return OleCreatePictureIndirectExt(lpPictDesc, riid, fOwn, lplpvObj);
  else
    return -2147467263;
}

```

## disassembly

```asm
0x18003ec20  push    rbx
0x18003ec22  push    rbp
0x18003ec23  push    rsi
0x18003ec24  push    rdi
0x18003ec25  sub     rsp, 28h
0x18003ec29  mov     rbx, r9
0x18003ec2c  mov     edi, r8d
0x18003ec2f  mov     rsi, rdx
0x18003ec32  mov     rbp, rcx
0x18003ec35  call    IsMonikerLoadTypeLibPresent
0x18003ec3a  test    al, al
0x18003ec3c  jz      short loc_18003EC59
0x18003ec3e  mov     r9, rbx
0x18003ec41  mov     r8d, edi
0x18003ec44  mov     rdx, rsi
0x18003ec47  mov     rcx, rbp
0x18003ec4a  call    cs:__imp_OleCreatePictureIndirectExt
0x18003ec50  add     rsp, 28h
0x18003ec54  pop     rdi
0x18003ec55  pop     rsi
0x18003ec56  pop     rbp
0x18003ec57  pop     rbx
0x18003ec58  retn
0x18003ec59  mov     eax, 80004001h
0x18003ec5e  jmp     short loc_18003EC50
```
