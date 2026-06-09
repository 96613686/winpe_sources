# GetCheckboxWidth(void)

- ea: `0x18003bac4`
- end: `0x18003bb28`
- name: `?GetCheckboxWidth@@YAJXZ`
- size: `100`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b4b8`
- `0x18003b640`

## callees

- `0x18003bac4`

## import_xrefs

- `GDI32!GetObjectW` at `0x18003bb00`
- `GDI32!GetObjectW` at `0x18003bb00`
- `GDI32!DeleteObject` at `0x18003bb15`
- `GDI32!DeleteObject` at `0x18003bb15`
- `USER32!LoadBitmapW` at `0x18003bada`
- `USER32!LoadBitmapW` at `0x18003bada`

## pseudocode

```c
__int64 GetCheckboxWidth(void)
{
  unsigned int v0; // ebx
  HBITMAP BitmapW; // rax
  HBITMAP v2; // rdi
  _OWORD pv[2]; // [rsp+20h] [rbp-28h] BYREF

  v0 = 13;
  BitmapW = LoadBitmapW(0, (LPCWSTR)0x7FF7);
  v2 = BitmapW;
  if ( BitmapW )
  {
    memset(pv, 0, sizeof(pv));
    GetObjectW(BitmapW, 32, pv);
    v0 = SDWORD1(pv[0]) / 4;
    DeleteObject(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18003bac4  mov     [rsp+arg_0], rbx
0x18003bac9  push    rdi
0x18003baca  sub     rsp, 40h
0x18003bace  mov     edx, 7FF7h; lpBitmapName
0x18003bad3  xor     ecx, ecx; hInstance
0x18003bad5  mov     ebx, 0Dh
0x18003bada  call    cs:__imp_LoadBitmapW
0x18003bae0  mov     rdi, rax
0x18003bae3  test    rax, rax
0x18003bae6  jz      short loc_18003BB1B
0x18003bae8  xorps   xmm0, xmm0
0x18003baeb  lea     r8, [rsp+48h+pv]; pv
0x18003baf0  lea     edx, [rbx+13h]; c
0x18003baf3  mov     rcx, rax; h
0x18003baf6  movups  [rsp+48h+pv], xmm0
0x18003bafb  movups  [rsp+48h+var_18], xmm0
0x18003bb00  call    cs:__imp_GetObjectW
0x18003bb06  mov     eax, dword ptr [rsp+48h+pv+4]
0x18003bb0a  lea     ecx, [rbx-9]
0x18003bb0d  cdq
0x18003bb0e  idiv    ecx
0x18003bb10  mov     rcx, rdi; ho
0x18003bb13  mov     ebx, eax
0x18003bb15  call    cs:__imp_DeleteObject
0x18003bb1b  mov     eax, ebx
0x18003bb1d  mov     rbx, [rsp+48h+arg_0]
0x18003bb22  add     rsp, 40h
0x18003bb26  pop     rdi
0x18003bb27  retn
```
