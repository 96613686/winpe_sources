# BUFFER::ReallocStorage(ulong)

- ea: `0x1800029c0`
- end: `0x180002a4b`
- name: `?ReallocStorage@BUFFER@@AEAA_NK@Z`
- size: `139`
- prototype: `bool(BUFFER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002154`
- `0x180002a54`

## callees

- `0x1800029c0`
- `0x180002b96`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002a04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002a04`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800029ee`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800029ee`

## pseudocode

```c
char __fastcall BUFFER::ReallocStorage(BUFFER *this, unsigned int a2)
{
  SIZE_T v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rax
  HANDLE v7; // rax
  void *v8; // rbx

  v3 = a2;
  if ( a2 > *((_DWORD *)this + 10) )
  {
    if ( *((_BYTE *)this + 44) )
    {
      v4 = (void *)*((_QWORD *)this + 4);
      ProcessHeap = GetProcessHeap();
      v6 = HeapReAlloc(ProcessHeap, 0, v4, (unsigned int)v3);
    }
    else
    {
      v7 = GetProcessHeap();
      v6 = HeapAlloc(v7, 0, v3);
    }
    v8 = v6;
    if ( !v6 )
    {
      SetLastError(8u);
      return 0;
    }
    if ( !*((_BYTE *)this + 44) )
    {
      memcpy_0(v6, *((const void **)this + 4), *((unsigned int *)this + 10));
      *((_BYTE *)this + 44) = 1;
    }
    *((_QWORD *)this + 4) = v8;
    *((_DWORD *)this + 10) = v3;
  }
  return 1;
}

```

## disassembly

```asm
0x1800029c0  push    rbx
0x1800029c2  push    rbp
0x1800029c3  push    rsi
0x1800029c4  push    rdi
0x1800029c5  sub     rsp, 28h
0x1800029c9  mov     rdi, rcx
0x1800029cc  mov     esi, edx
0x1800029ce  cmp     edx, [rcx+28h]
0x1800029d1  jbe     short loc_180002A40
0x1800029d3  cmp     byte ptr [rcx+2Ch], 0
0x1800029d7  jz      short loc_1800029F6
0x1800029d9  mov     rbx, [rcx+20h]
0x1800029dd  call    cs:__imp_GetProcessHeap
0x1800029e3  mov     r9d, esi; dwBytes
0x1800029e6  mov     r8, rbx; lpMem
0x1800029e9  mov     rcx, rax; hHeap
0x1800029ec  xor     edx, edx; dwFlags
0x1800029ee  call    cs:__imp_HeapReAlloc
0x1800029f4  jmp     short loc_180002A0A
0x1800029f6  call    cs:__imp_GetProcessHeap
0x1800029fc  mov     r8, rsi; dwBytes
0x1800029ff  xor     edx, edx; dwFlags
0x180002a01  mov     rcx, rax; hHeap
0x180002a04  call    cs:__imp_HeapAlloc
0x180002a0a  mov     rbx, rax
0x180002a0d  test    rax, rax
0x180002a10  jnz     short loc_180002A1F
0x180002a12  lea     ecx, [rax+8]; dwErrCode
0x180002a15  call    cs:__imp_SetLastError
0x180002a1b  xor     al, al
0x180002a1d  jmp     short loc_180002A42
0x180002a1f  cmp     byte ptr [rdi+2Ch], 0
0x180002a23  jnz     short loc_180002A39
0x180002a25  mov     r8d, [rdi+28h]; Size
0x180002a29  mov     rcx, rbx; void *
0x180002a2c  mov     rdx, [rdi+20h]; Src
0x180002a30  call    memcpy_0
0x180002a35  mov     byte ptr [rdi+2Ch], 1
0x180002a39  mov     [rdi+20h], rbx
0x180002a3d  mov     [rdi+28h], esi
0x180002a40  mov     al, 1
0x180002a42  add     rsp, 28h
0x180002a46  pop     rdi
0x180002a47  pop     rsi
0x180002a48  pop     rbp
0x180002a49  pop     rbx
0x180002a4a  retn
```
