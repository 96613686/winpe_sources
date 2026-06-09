# GpReadOnlyMemoryStream::~GpReadOnlyMemoryStream(void)

- ea: `0x1800c202c`
- end: `0x1800c20d8`
- name: `??1GpReadOnlyMemoryStream@@UEAA@XZ`
- size: `172`
- prototype: `void __fastcall(GpReadOnlyMemoryStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1ff0`

## callees

- `0x18001f950`
- `0x1800c202c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c2083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c20a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c20a6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c20ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c20ca`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800c2098`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800c2098`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800c20bc`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800c20bc`

## pseudocode

```c
void __fastcall GpReadOnlyMemoryStream::~GpReadOnlyMemoryStream(GpReadOnlyMemoryStream *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &GpReadOnlyMemoryStream::`vftable';
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    switch ( *((_DWORD *)this + 10) )
    {
      case 1:
        GlobalFree(v2);
        break;
      case 2:
        VirtualFree(v2, 0, 0x8000u);
        break;
      case 3:
        CoTaskMemFree(v2);
        break;
      case 4:
        UnmapViewOfFile(v2);
        break;
    }
  }
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 != (void *)-1LL )
    CloseHandle(v3);
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
    GpFree(v4);
  *(_QWORD *)this = &IUnknownBase<IStream>::`vftable';
}

```

## disassembly

```asm
0x1800c202c  push    rbx
0x1800c202e  sub     rsp, 20h
0x1800c2032  lea     rax, ??_7GpReadOnlyMemoryStream@@6B@; const GpReadOnlyMemoryStream::`vftable'
0x1800c2039  mov     rbx, rcx
0x1800c203c  mov     [rcx], rax
0x1800c203f  mov     rcx, [rcx+18h]; hMem
0x1800c2043  test    rcx, rcx
0x1800c2046  jz      short loc_1800C205F
0x1800c2048  mov     edx, [rbx+28h]
0x1800c204b  sub     edx, 1
0x1800c204e  jz      short loc_1800C20CA
0x1800c2050  sub     edx, 1
0x1800c2053  jz      short loc_1800C20B4
0x1800c2055  sub     edx, 1
0x1800c2058  jz      short loc_1800C20A6
0x1800c205a  cmp     edx, 1
0x1800c205d  jz      short loc_1800C2098
0x1800c205f  mov     rcx, [rbx+30h]; hObject
0x1800c2063  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c2067  jnz     short loc_1800C2083
0x1800c2069  mov     rcx, [rbx+38h]
0x1800c206d  test    rcx, rcx
0x1800c2070  jnz     short loc_1800C2091
0x1800c2072  lea     rax, ??_7?$IUnknownBase@UIStream@@@@6B@; const IUnknownBase<IStream>::`vftable'
0x1800c2079  mov     [rbx], rax
0x1800c207c  add     rsp, 20h
0x1800c2080  pop     rbx
0x1800c2081  retn
0x1800c2083  call    cs:__imp_CloseHandle
0x1800c208a  nop     dword ptr [rax+rax+00h]
0x1800c208f  jmp     short loc_1800C2069
0x1800c2091  call    GpFree
0x1800c2096  jmp     short loc_1800C2072
0x1800c2098  call    cs:__imp_UnmapViewOfFile
0x1800c209f  nop     dword ptr [rax+rax+00h]
0x1800c20a4  jmp     short loc_1800C205F
0x1800c20a6  call    cs:__imp_CoTaskMemFree
0x1800c20ad  nop     dword ptr [rax+rax+00h]
0x1800c20b2  jmp     short loc_1800C205F
0x1800c20b4  xor     edx, edx; dwSize
0x1800c20b6  mov     r8d, 8000h; dwFreeType
0x1800c20bc  call    cs:__imp_VirtualFree
0x1800c20c3  nop     dword ptr [rax+rax+00h]
0x1800c20c8  jmp     short loc_1800C205F
0x1800c20ca  call    cs:__imp_GlobalFree
0x1800c20d1  nop     dword ptr [rax+rax+00h]
0x1800c20d6  jmp     short loc_1800C205F
```
