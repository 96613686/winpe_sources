# FreeGDIdata(void *,ushort)

- ea: `0x180076438`
- end: `0x1800764be`
- name: `?FreeGDIdata@@YAHPEAXG@Z`
- size: `134`
- prototype: `int __fastcall(void *hData, unsigned __int16 cfFormat)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180076750`

## callees

- `0x180076438`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18007649d`
- `KERNELBASE!GlobalFree` at `0x18007649d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076462`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076462`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007644b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007644b`
- `GDI32!DeleteMetaFile` at `0x180076472`
- `GDI32!DeleteMetaFile` at `0x180076472`
- `GDI32!DeleteObject` at `0x180076486`
- `GDI32!DeleteObject` at `0x180076486`

## pseudocode

```c
__int64 __fastcall FreeGDIdata(void *hData, unsigned __int16 cfFormat)
{
  HMETAFILE *v3; // rdi

  switch ( cfFormat )
  {
    case 3u:
      v3 = (HMETAFILE *)GlobalLock(hData);
      if ( v3 )
      {
        GlobalUnlock(hData);
        DeleteMetaFile(v3[2]);
      }
      goto LABEL_7;
    case 2u:
      DeleteObject(hData);
      return 1;
    case 8u:
LABEL_7:
      GlobalFree(hData);
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180076438  mov     [rsp+arg_0], rbx
0x18007643d  push    rdi
0x18007643e  sub     rsp, 20h
0x180076442  mov     rbx, hData
0x180076445  cmp     cfFormat, 3
0x180076449  jnz     short loc_180076480
0x18007644b  call    cs:__imp_GlobalLock
0x180076452  nop     dword ptr [rax+rax+00h]
0x180076457  mov     rdi, rax
0x18007645a  test    rax, rax
0x18007645d  jz      short loc_18007649A
0x18007645f  mov     hData, rbx; hMem
0x180076462  call    cs:__imp_GlobalUnlock
0x180076469  nop     dword ptr [rax+rax+00h]
0x18007646e  mov     hData, [rdi+10h]; hmf
0x180076472  call    cs:__imp_DeleteMetaFile
0x180076479  nop     dword ptr [rax+rax+00h]
0x18007647e  jmp     short loc_18007649A
0x180076480  cmp     cfFormat, 2
0x180076484  jnz     short loc_180076494
0x180076486  call    cs:__imp_DeleteObject
0x18007648d  nop     dword ptr [rax+rax+00h]
0x180076492  jmp     short loc_1800764A9
0x180076494  cmp     cfFormat, 8
0x180076498  jnz     short loc_1800764B0
0x18007649a  mov     hData, rbx; hMem
0x18007649d  call    cs:__imp_GlobalFree
0x1800764a4  nop     dword ptr [rax+rax+00h]
0x1800764a9  mov     eax, 1
0x1800764ae  jmp     short loc_1800764B2
0x1800764b0  xor     eax, eax
0x1800764b2  mov     rbx, [rsp+28h+arg_0]
0x1800764b7  add     rsp, 20h
0x1800764bb  pop     rdi
0x1800764bc  retn
```
