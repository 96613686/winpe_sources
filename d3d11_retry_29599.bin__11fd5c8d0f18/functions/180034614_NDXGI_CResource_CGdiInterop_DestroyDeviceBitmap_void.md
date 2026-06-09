# NDXGI::CResource::CGdiInterop::DestroyDeviceBitmap(void)

- ea: `0x180034614`
- end: `0x180034651`
- name: `?DestroyDeviceBitmap@CGdiInterop@CResource@NDXGI@@AEAAXXZ`
- size: `61`
- prototype: `void __fastcall(NDXGI::CResource::CGdiInterop *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093f4`
- `0x180009950`
- `0x180034404`

## callees

- `0x180034614`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180034626`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18003463d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180034626`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18003463d`

## pseudocode

```c
void __fastcall NDXGI::CResource::CGdiInterop::DestroyDeviceBitmap(NDXGI::CResource::CGdiInterop *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180034614  push    rbx
0x180034616  sub     rsp, 20h
0x18003461a  mov     rbx, rcx
0x18003461d  mov     rcx, [rcx+28h]; ho
0x180034621  test    rcx, rcx
0x180034624  jz      short loc_180034634
0x180034626  call    cs:__imp_DeleteObject
0x18003462c  mov     qword ptr [rbx+28h], 0
0x180034634  mov     rcx, [rbx+20h]; ho
0x180034638  test    rcx, rcx
0x18003463b  jz      short loc_18003464B
0x18003463d  call    cs:__imp_DeleteObject
0x180034643  mov     qword ptr [rbx+20h], 0
0x18003464b  add     rsp, 20h
0x18003464f  pop     rbx
0x180034650  retn
```
