# FILTER_POOL_ITEM::CreateMemPoolItem(ulong)

- ea: `0x18000a9d8`
- end: `0x18000aa4a`
- name: `?CreateMemPoolItem@FILTER_POOL_ITEM@@SAPEAV1@K@Z`
- size: `114`
- prototype: `struct FILTER_POOL_ITEM *__fastcall(SIZE_T uBytes)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a710`

## callees

- `0x180007160`
- `0x1800088bc`
- `0x18000a9d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa0b`

## pseudocode

```c
struct FILTER_POOL_ITEM *__fastcall FILTER_POOL_ITEM::CreateMemPoolItem(SIZE_T uBytes)
{
  unsigned int v1; // edi
  FILTER_POOL_ITEM *v2; // rax
  FILTER_POOL_ITEM *v3; // rbx
  HLOCAL v4; // rax
  unsigned int v5; // edx

  v1 = uBytes;
  v2 = (FILTER_POOL_ITEM *)operator new(0x20u);
  v3 = v2;
  if ( v2 )
  {
    *(_DWORD *)v2 = 1179668300;
    *((_QWORD *)v2 + 3) = 0;
    v4 = LocalAlloc(0x40u, v1);
    *((_QWORD *)v3 + 3) = v4;
    if ( v4 )
      return v3;
    SetLastError(8u);
    FILTER_POOL_ITEM::`scalar deleting destructor'(v3, v5);
  }
  else
  {
    SetLastError(8u);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a9d8  mov     [rsp+arg_0], rbx
0x18000a9dd  push    rdi
0x18000a9de  sub     rsp, 20h
0x18000a9e2  mov     edi, ecx
0x18000a9e4  mov     ecx, 20h ; ' '; Size
0x18000a9e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9ee  mov     rbx, rax
0x18000a9f1  test    rax, rax
0x18000a9f4  jz      short loc_18000AA32
0x18000a9f6  mov     edx, edi; uBytes
0x18000a9f8  mov     dword ptr [rax], 46504F4Ch
0x18000a9fe  mov     ecx, 40h ; '@'; uFlags
0x18000aa03  mov     qword ptr [rax+18h], 0
0x18000aa0b  call    cs:__imp_LocalAlloc
0x18000aa11  mov     [rbx+18h], rax
0x18000aa15  test    rax, rax
0x18000aa18  jnz     short loc_18000AA2D
0x18000aa1a  lea     ecx, [rax+8]; dwErrCode
0x18000aa1d  call    cs:__imp_SetLastError
0x18000aa23  mov     rcx, rbx; this
0x18000aa26  call    ??_GFILTER_POOL_ITEM@@QEAAPEAXI@Z; FILTER_POOL_ITEM::`scalar deleting destructor'(uint)
0x18000aa2b  jmp     short loc_18000AA3D
0x18000aa2d  mov     rax, rbx
0x18000aa30  jmp     short loc_18000AA3F
0x18000aa32  mov     ecx, 8; dwErrCode
0x18000aa37  call    cs:__imp_SetLastError
0x18000aa3d  xor     eax, eax
0x18000aa3f  mov     rbx, [rsp+28h+arg_0]
0x18000aa44  add     rsp, 20h
0x18000aa48  pop     rdi
0x18000aa49  retn
```
