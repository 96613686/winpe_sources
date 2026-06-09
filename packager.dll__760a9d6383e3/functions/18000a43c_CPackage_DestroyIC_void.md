# CPackage::_DestroyIC(void)

- ea: `0x18000a43c`
- end: `0x18000a46c`
- name: `?_DestroyIC@CPackage@@IEAAXXZ`
- size: `48`
- prototype: `void __fastcall(CPackage *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000710c`
- `0x1800073b8`
- `0x180007b28`
- `0x180008c8c`

## callees

- `0x18000a43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a460`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a460`
- `USER32!DestroyIcon` at `0x18000a456`
- `USER32!DestroyIcon` at `0x18000a456`

## pseudocode

```c
void __fastcall CPackage::_DestroyIC(CPackage *this)
{
  HICON *v2; // rcx
  HICON v3; // rcx

  v2 = (HICON *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    v3 = *v2;
    if ( v3 )
      DestroyIcon(v3);
    GlobalFree(*((HGLOBAL *)this + 12));
  }
}

```

## disassembly

```asm
0x18000a43c  push    rbx
0x18000a43e  sub     rsp, 20h
0x18000a442  mov     rbx, rcx
0x18000a445  mov     rcx, [rcx+60h]
0x18000a449  test    rcx, rcx
0x18000a44c  jz      short loc_18000A466
0x18000a44e  mov     rcx, [rcx]; hIcon
0x18000a451  test    rcx, rcx
0x18000a454  jz      short loc_18000A45C
0x18000a456  call    cs:__imp_DestroyIcon
0x18000a45c  mov     rcx, [rbx+60h]; hMem
0x18000a460  call    cs:__imp_GlobalFree
0x18000a466  add     rsp, 20h
0x18000a46a  pop     rbx
0x18000a46b  retn
```
