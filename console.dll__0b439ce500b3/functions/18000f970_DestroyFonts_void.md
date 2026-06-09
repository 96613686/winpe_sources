# DestroyFonts(void)

- ea: `0x18000f970`
- end: `0x18000fa38`
- name: `?DestroyFonts@@YAXXZ`
- size: `200`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000752c`

## callees

- `0x18000f970`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9f9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000f998`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000f998`

## pseudocode

```c
void DestroyFonts(void)
{
  HGDIOBJ *v0; // rbx
  __int64 i; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v3; // rdi
  _QWORD *v4; // rbx
  HANDLE v5; // rax

  v0 = (HGDIOBJ *)FontInfo;
  if ( FontInfo )
  {
    for ( i = 0; (unsigned int)i < NumberOfFonts; i = (unsigned int)(i + 1) )
    {
      DeleteObject(v0[5 * i]);
      v0 = (HGDIOBJ *)FontInfo;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
    FontInfo = 0;
    NumberOfFonts = 0;
  }
  v3 = gpFaceNames;
  if ( gpFaceNames )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v3);
      v3 = v4;
    }
    while ( v4 );
  }
  gpFaceNames = 0;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_0], rbx
0x18000f975  push    rdi
0x18000f976  sub     rsp, 20h
0x18000f97a  mov     rbx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000f981  test    rbx, rbx
0x18000f984  jz      short loc_18000F9EA
0x18000f986  xor     edi, edi
0x18000f988  cmp     cs:?NumberOfFonts@@3KA, edi; ulong NumberOfFonts
0x18000f98e  jbe     short loc_18000F9B5
0x18000f990  lea     rcx, [rdi+rdi*4]
0x18000f994  mov     rcx, [rbx+rcx*8]; ho
0x18000f998  call    cs:__imp_DeleteObject
0x18000f99f  nop     dword ptr [rax+rax+00h]
0x18000f9a4  mov     rbx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000f9ab  inc     edi
0x18000f9ad  cmp     edi, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000f9b3  jb      short loc_18000F990
0x18000f9b5  call    cs:__imp_GetProcessHeap
0x18000f9bc  nop     dword ptr [rax+rax+00h]
0x18000f9c1  mov     r8, rbx; lpMem
0x18000f9c4  xor     edx, edx; dwFlags
0x18000f9c6  mov     rcx, rax; hHeap
0x18000f9c9  call    cs:__imp_HeapFree
0x18000f9d0  nop     dword ptr [rax+rax+00h]
0x18000f9d5  mov     cs:?FontInfo@@3PEAU_FONT_INFO@@EA, 0; _FONT_INFO * FontInfo
0x18000f9e0  mov     cs:?NumberOfFonts@@3KA, 0; ulong NumberOfFonts
0x18000f9ea  mov     rdi, cs:?gpFaceNames@@3PEAUtagFACENODE@@EA; tagFACENODE * gpFaceNames
0x18000f9f1  test    rdi, rdi
0x18000f9f4  jz      short loc_18000FA21
0x18000f9f6  mov     rbx, [rdi]
0x18000f9f9  call    cs:__imp_GetProcessHeap
0x18000fa00  nop     dword ptr [rax+rax+00h]
0x18000fa05  mov     r8, rdi; lpMem
0x18000fa08  xor     edx, edx; dwFlags
0x18000fa0a  mov     rcx, rax; hHeap
0x18000fa0d  call    cs:__imp_HeapFree
0x18000fa14  nop     dword ptr [rax+rax+00h]
0x18000fa19  mov     rdi, rbx
0x18000fa1c  test    rbx, rbx
0x18000fa1f  jnz     short loc_18000F9F6
0x18000fa21  mov     rbx, [rsp+28h+arg_0]
0x18000fa26  mov     cs:?gpFaceNames@@3PEAUtagFACENODE@@EA, 0; tagFACENODE * gpFaceNames
0x18000fa31  add     rsp, 20h
0x18000fa35  pop     rdi
0x18000fa36  retn
```
