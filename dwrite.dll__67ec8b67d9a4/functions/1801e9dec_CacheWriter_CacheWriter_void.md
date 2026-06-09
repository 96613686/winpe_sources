# CacheWriter::~CacheWriter(void)

- ea: `0x1801e9dec`
- end: `0x1801e9e46`
- name: `??1CacheWriter@@UEAA@XZ`
- size: `90`
- prototype: `void __fastcall(CacheWriter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18012c91c`
- `0x1801e9db0`

## callees

- `0x1801e9dec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801e9e03`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801e9e03`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801e9e18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801e9e18`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801e9e3e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801e9e3e`

## pseudocode

```c
void __fastcall CacheWriter::~CacheWriter(CacheWriter *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CacheWriter::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( *((_BYTE *)this + 24) )
      UnmapViewOfFile(v2);
    else
      VirtualFree(v2, 0, 0x8000u);
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &ICacheReference::`vftable';
}

```

## disassembly

```asm
0x1801e9dec  push    rbx
0x1801e9dee  sub     rsp, 20h
0x1801e9df2  lea     rax, ??_7CacheWriter@@6B@; const CacheWriter::`vftable'
0x1801e9df9  mov     rbx, rcx
0x1801e9dfc  mov     [rcx], rax
0x1801e9dff  add     rcx, 20h ; ' '; lpCriticalSection
0x1801e9e03  call    cs:__imp_DeleteCriticalSection
0x1801e9e09  mov     rcx, [rbx+10h]; lpAddress
0x1801e9e0d  test    rcx, rcx
0x1801e9e10  jz      short loc_1801E9E26
0x1801e9e12  cmp     byte ptr [rbx+18h], 0
0x1801e9e16  jz      short loc_1801E9E36
0x1801e9e18  call    cs:__imp_UnmapViewOfFile
0x1801e9e1e  mov     qword ptr [rbx+10h], 0
0x1801e9e26  lea     rax, ??_7ICacheReference@@6B@; const ICacheReference::`vftable'
0x1801e9e2d  mov     [rbx], rax
0x1801e9e30  add     rsp, 20h
0x1801e9e34  pop     rbx
0x1801e9e35  retn
0x1801e9e36  xor     edx, edx; dwSize
0x1801e9e38  mov     r8d, 8000h; dwFreeType
0x1801e9e3e  call    cs:__imp_VirtualFree
0x1801e9e44  jmp     short loc_1801E9E1E
```
