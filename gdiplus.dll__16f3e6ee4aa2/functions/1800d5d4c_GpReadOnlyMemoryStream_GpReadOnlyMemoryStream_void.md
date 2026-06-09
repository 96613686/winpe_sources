# GpReadOnlyMemoryStream::~GpReadOnlyMemoryStream(void)

- ea: `0x1800d5d4c`
- end: `0x1800d5dd7`
- name: `??1GpReadOnlyMemoryStream@@UEAA@XZ`
- size: `139`
- prototype: `void __fastcall(GpReadOnlyMemoryStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d5d10`

## callees

- `0x18001ec80`
- `0x1800d5d4c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5db7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5db7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d5dcf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d5dcf`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800d5dc7`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800d5dc7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800d5daf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800d5daf`

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
0x1800d5d4c  push    rbx
0x1800d5d4e  sub     rsp, 20h
0x1800d5d52  lea     rax, ??_7GpReadOnlyMemoryStream@@6B@; const GpReadOnlyMemoryStream::`vftable'
0x1800d5d59  mov     rbx, rcx
0x1800d5d5c  mov     [rcx], rax
0x1800d5d5f  mov     rcx, [rcx+18h]; hMem
0x1800d5d63  test    rcx, rcx
0x1800d5d66  jz      short loc_1800D5D7F
0x1800d5d68  mov     edx, [rbx+28h]
0x1800d5d6b  sub     edx, 1
0x1800d5d6e  jz      short loc_1800D5DCF
0x1800d5d70  sub     edx, 1
0x1800d5d73  jz      short loc_1800D5DBF
0x1800d5d75  sub     edx, 1
0x1800d5d78  jz      short loc_1800D5DB7
0x1800d5d7a  cmp     edx, 1
0x1800d5d7d  jz      short loc_1800D5DAF
0x1800d5d7f  mov     rcx, [rbx+30h]; hObject
0x1800d5d83  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d5d87  jz      short loc_1800D5D8F
0x1800d5d89  call    cs:__imp_CloseHandle
0x1800d5d8f  mov     rcx, [rbx+38h]
0x1800d5d93  test    rcx, rcx
0x1800d5d96  jnz     short loc_1800D5DA8
0x1800d5d98  lea     rax, ??_7?$IUnknownBase@UIStream@@@@6B@; const IUnknownBase<IStream>::`vftable'
0x1800d5d9f  mov     [rbx], rax
0x1800d5da2  add     rsp, 20h
0x1800d5da6  pop     rbx
0x1800d5da7  retn
0x1800d5da8  call    GpFree
0x1800d5dad  jmp     short loc_1800D5D98
0x1800d5daf  call    cs:__imp_UnmapViewOfFile
0x1800d5db5  jmp     short loc_1800D5D7F
0x1800d5db7  call    cs:__imp_CoTaskMemFree
0x1800d5dbd  jmp     short loc_1800D5D7F
0x1800d5dbf  xor     edx, edx; dwSize
0x1800d5dc1  mov     r8d, 8000h; dwFreeType
0x1800d5dc7  call    cs:__imp_VirtualFree
0x1800d5dcd  jmp     short loc_1800D5D7F
0x1800d5dcf  call    cs:__imp_GlobalFree
0x1800d5dd5  jmp     short loc_1800D5D7F
```
