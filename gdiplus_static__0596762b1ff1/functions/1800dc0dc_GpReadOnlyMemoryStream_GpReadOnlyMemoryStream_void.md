# GpReadOnlyMemoryStream::~GpReadOnlyMemoryStream(void)

- ea: `0x1800dc0dc`
- end: `0x1800dc186`
- name: `??1GpReadOnlyMemoryStream@@UEAA@XZ`
- size: `170`
- prototype: `void __fastcall(GpReadOnlyMemoryStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800dc0a0`

## callees

- `0x180010bd0`
- `0x1800dc0dc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc154`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc178`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc178`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800dc16a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800dc16a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800dc146`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800dc146`

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
0x1800dc0dc  push    rbx
0x1800dc0de  sub     rsp, 20h
0x1800dc0e2  lea     rax, ??_7GpReadOnlyMemoryStream@@6B@; const GpReadOnlyMemoryStream::`vftable'
0x1800dc0e9  mov     rbx, rcx
0x1800dc0ec  mov     [rcx], rax
0x1800dc0ef  mov     rcx, [rcx+18h]; hMem
0x1800dc0f3  test    rcx, rcx
0x1800dc0f6  jz      short loc_1800DC10F
0x1800dc0f8  mov     edx, [rbx+28h]
0x1800dc0fb  sub     edx, 1
0x1800dc0fe  jz      short loc_1800DC178
0x1800dc100  sub     edx, 1
0x1800dc103  jz      short loc_1800DC162
0x1800dc105  sub     edx, 1
0x1800dc108  jz      short loc_1800DC154
0x1800dc10a  cmp     edx, 1
0x1800dc10d  jz      short loc_1800DC146
0x1800dc10f  mov     rcx, [rbx+30h]; hObject
0x1800dc113  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dc117  jz      short loc_1800DC125
0x1800dc119  call    cs:__imp_CloseHandle
0x1800dc120  nop     dword ptr [rax+rax+00h]
0x1800dc125  mov     rcx, [rbx+38h]
0x1800dc129  test    rcx, rcx
0x1800dc12c  jnz     short loc_1800DC13F
0x1800dc12e  lea     rax, ??_7?$IUnknownBase@UIStream@@@@6B@; const IUnknownBase<IStream>::`vftable'
0x1800dc135  mov     [rbx], rax
0x1800dc138  add     rsp, 20h
0x1800dc13c  pop     rbx
0x1800dc13d  retn
0x1800dc13f  call    GpFree
0x1800dc144  jmp     short loc_1800DC12E
0x1800dc146  call    cs:__imp_UnmapViewOfFile
0x1800dc14d  nop     dword ptr [rax+rax+00h]
0x1800dc152  jmp     short loc_1800DC10F
0x1800dc154  call    cs:__imp_CoTaskMemFree
0x1800dc15b  nop     dword ptr [rax+rax+00h]
0x1800dc160  jmp     short loc_1800DC10F
0x1800dc162  xor     edx, edx; dwSize
0x1800dc164  mov     r8d, 8000h; dwFreeType
0x1800dc16a  call    cs:__imp_VirtualFree
0x1800dc171  nop     dword ptr [rax+rax+00h]
0x1800dc176  jmp     short loc_1800DC10F
0x1800dc178  call    cs:__imp_GlobalFree
0x1800dc17f  nop     dword ptr [rax+rax+00h]
0x1800dc184  jmp     short loc_1800DC10F
```
