# GdiConvertMetaFilePict

- ea: `0x18008dff0`
- end: `0x18008e07a`
- name: `GdiConvertMetaFilePict`
- size: `138`
- prototype: `__int64 __fastcall(HGLOBAL hMem)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180024fb8`
- `0x18008dff0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008e062`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008e062`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008e006`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008e006`
- `GDI32!GdiSetLastError` at `0x18008e02f`
- `GDI32!GdiSetLastError` at `0x18008e02f`
- `win32u!NtGdiCreateServerMetaFile` at `0x18008e056`
- `win32u!NtGdiCreateServerMetaFile` at `0x18008e056`

## pseudocode

```c
__int64 __fastcall GdiConvertMetaFilePict(HGLOBAL hMem)
{
  unsigned int *v2; // rax
  unsigned int *v3; // rbx
  __int64 v4; // rax
  __int64 ServerMetaFile; // rbx

  if ( gbDisableMetaFiles )
    return 0;
  v2 = (unsigned int *)GlobalLock(hMem);
  v3 = v2;
  if ( !v2 )
    return 0;
  v4 = pvClientObjGet(*((_QWORD *)v2 + 2), 2490368);
  if ( v4 )
  {
    ServerMetaFile = NtGdiCreateServerMetaFile(
                       1599096397,
                       (unsigned int)(2 * *(_DWORD *)(v4 + 10)),
                       *(_QWORD *)(v4 + 40),
                       *v3,
                       v3[1],
                       v3[2]);
  }
  else
  {
    ServerMetaFile = 0;
    GdiSetLastError(6);
  }
  GlobalUnlock(hMem);
  return ServerMetaFile;
}

```

## disassembly

```asm
0x18008dff0  mov     [rsp+arg_0], rbx
0x18008dff5  push    rdi
0x18008dff6  sub     rsp, 30h
0x18008dffa  cmp     cs:gbDisableMetaFiles, 0
0x18008e001  mov     rdi, rcx
0x18008e004  jnz     short loc_18008E06D
0x18008e006  call    cs:__imp_GlobalLock
0x18008e00c  mov     rbx, rax
0x18008e00f  test    rax, rax
0x18008e012  jz      short loc_18008E06D
0x18008e014  mov     rcx, [rax+10h]
0x18008e018  mov     edx, 260000h
0x18008e01d  call    pvClientObjGet
0x18008e022  mov     r8, rax
0x18008e025  test    rax, rax
0x18008e028  jnz     short loc_18008E037
0x18008e02a  xor     ebx, ebx
0x18008e02c  lea     ecx, [rax+6]
0x18008e02f  call    cs:__imp_GdiSetLastError
0x18008e035  jmp     short loc_18008E05F
0x18008e037  mov     edx, [rax+0Ah]
0x18008e03a  mov     ecx, 5F50464Dh
0x18008e03f  mov     eax, [rbx+8]
0x18008e042  add     edx, edx
0x18008e044  mov     r9d, [rbx]
0x18008e047  mov     r8, [r8+28h]
0x18008e04b  mov     [rsp+38h+var_10], eax
0x18008e04f  mov     eax, [rbx+4]
0x18008e052  mov     [rsp+38h+var_18], eax
0x18008e056  call    cs:__imp_NtGdiCreateServerMetaFile
0x18008e05c  mov     rbx, rax
0x18008e05f  mov     rcx, rdi; hMem
0x18008e062  call    cs:__imp_GlobalUnlock
0x18008e068  mov     rax, rbx
0x18008e06b  jmp     short loc_18008E06F
0x18008e06d  xor     eax, eax
0x18008e06f  mov     rbx, [rsp+38h+arg_0]
0x18008e074  add     rsp, 30h
0x18008e078  pop     rdi
0x18008e079  retn
```
