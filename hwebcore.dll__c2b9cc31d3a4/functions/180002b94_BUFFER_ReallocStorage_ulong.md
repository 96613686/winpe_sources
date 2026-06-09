# BUFFER::ReallocStorage(ulong)

- ea: `0x180002b94`
- end: `0x180002c42`
- name: `?ReallocStorage@BUFFER@@AEAA_NK@Z`
- size: `174`
- prototype: `bool(BUFFER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002224`
- `0x180002c48`

## callees

- `0x180002b94`
- `0x180002d96`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002bee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002bee`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180002bcc`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180002bcc`

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
0x180002b94  push    rbx
0x180002b96  push    rbp
0x180002b97  push    rsi
0x180002b98  push    rdi
0x180002b99  sub     rsp, 28h
0x180002b9d  mov     rdi, rcx
0x180002ba0  mov     esi, edx
0x180002ba2  cmp     edx, [rcx+28h]
0x180002ba5  jbe     loc_180002C36
0x180002bab  cmp     byte ptr [rcx+2Ch], 0
0x180002baf  jz      short loc_180002BDA
0x180002bb1  mov     rbx, [rcx+20h]
0x180002bb5  call    cs:__imp_GetProcessHeap
0x180002bbc  nop     dword ptr [rax+rax+00h]
0x180002bc1  mov     r9d, esi; dwBytes
0x180002bc4  mov     r8, rbx; lpMem
0x180002bc7  mov     rcx, rax; hHeap
0x180002bca  xor     edx, edx; dwFlags
0x180002bcc  call    cs:__imp_HeapReAlloc
0x180002bd3  nop     dword ptr [rax+rax+00h]
0x180002bd8  jmp     short loc_180002BFA
0x180002bda  call    cs:__imp_GetProcessHeap
0x180002be1  nop     dword ptr [rax+rax+00h]
0x180002be6  mov     r8, rsi; dwBytes
0x180002be9  xor     edx, edx; dwFlags
0x180002beb  mov     rcx, rax; hHeap
0x180002bee  call    cs:__imp_HeapAlloc
0x180002bf5  nop     dword ptr [rax+rax+00h]
0x180002bfa  mov     rbx, rax
0x180002bfd  test    rax, rax
0x180002c00  jnz     short loc_180002C15
0x180002c02  lea     ecx, [rax+8]; dwErrCode
0x180002c05  call    cs:__imp_SetLastError
0x180002c0c  nop     dword ptr [rax+rax+00h]
0x180002c11  xor     al, al
0x180002c13  jmp     short loc_180002C38
0x180002c15  cmp     byte ptr [rdi+2Ch], 0
0x180002c19  jnz     short loc_180002C2F
0x180002c1b  mov     r8d, [rdi+28h]; Size
0x180002c1f  mov     rcx, rbx; void *
0x180002c22  mov     rdx, [rdi+20h]; Src
0x180002c26  call    memcpy_0
0x180002c2b  mov     byte ptr [rdi+2Ch], 1
0x180002c2f  mov     [rdi+20h], rbx
0x180002c33  mov     [rdi+28h], esi
0x180002c36  mov     al, 1
0x180002c38  add     rsp, 28h
0x180002c3c  pop     rdi
0x180002c3d  pop     rsi
0x180002c3e  pop     rbp
0x180002c3f  pop     rbx
0x180002c40  retn
```
