# BUFFER::ReallocStorage(ulong)

- ea: `0x180003024`
- end: `0x1800030af`
- name: `?ReallocStorage@BUFFER@@AEAA_NK@Z`
- size: `139`
- prototype: `bool(BUFFER *__hidden this, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b90`
- `0x180001d7c`
- `0x18000224c`
- `0x180002330`
- `0x18000260c`
- `0x1800030b8`
- `0x180003164`
- `0x180003278`
- `0x1800033ac`

## callees

- `0x180003024`
- `0x180003605`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x180003052`
- `KERNEL32!HeapReAlloc` at `0x180003052`
- `KERNEL32!GetProcessHeap` at `0x180003041`
- `KERNEL32!GetProcessHeap` at `0x18000305a`
- `KERNEL32!GetProcessHeap` at `0x180003041`
- `KERNEL32!GetProcessHeap` at `0x18000305a`
- `KERNEL32!HeapAlloc` at `0x180003068`
- `KERNEL32!HeapAlloc` at `0x180003068`
- `KERNEL32!SetLastError` at `0x180003079`
- `KERNEL32!SetLastError` at `0x180003079`

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
0x180003024  push    rbx
0x180003026  push    rbp
0x180003027  push    rsi
0x180003028  push    rdi
0x180003029  sub     rsp, 28h
0x18000302d  mov     rdi, rcx
0x180003030  mov     esi, edx
0x180003032  cmp     edx, [rcx+28h]
0x180003035  jbe     short loc_1800030A4
0x180003037  cmp     byte ptr [rcx+2Ch], 0
0x18000303b  jz      short loc_18000305A
0x18000303d  mov     rbx, [rcx+20h]
0x180003041  call    cs:__imp_GetProcessHeap
0x180003047  mov     r9d, esi; dwBytes
0x18000304a  mov     r8, rbx; lpMem
0x18000304d  mov     rcx, rax; hHeap
0x180003050  xor     edx, edx; dwFlags
0x180003052  call    cs:__imp_HeapReAlloc
0x180003058  jmp     short loc_18000306E
0x18000305a  call    cs:__imp_GetProcessHeap
0x180003060  mov     r8, rsi; dwBytes
0x180003063  xor     edx, edx; dwFlags
0x180003065  mov     rcx, rax; hHeap
0x180003068  call    cs:__imp_HeapAlloc
0x18000306e  mov     rbx, rax
0x180003071  test    rax, rax
0x180003074  jnz     short loc_180003083
0x180003076  lea     ecx, [rax+8]; dwErrCode
0x180003079  call    cs:__imp_SetLastError
0x18000307f  xor     al, al
0x180003081  jmp     short loc_1800030A6
0x180003083  cmp     byte ptr [rdi+2Ch], 0
0x180003087  jnz     short loc_18000309D
0x180003089  mov     r8d, [rdi+28h]; Size
0x18000308d  mov     rcx, rbx; void *
0x180003090  mov     rdx, [rdi+20h]; Src
0x180003094  call    memcpy_0
0x180003099  mov     byte ptr [rdi+2Ch], 1
0x18000309d  mov     [rdi+20h], rbx
0x1800030a1  mov     [rdi+28h], esi
0x1800030a4  mov     al, 1
0x1800030a6  add     rsp, 28h
0x1800030aa  pop     rdi
0x1800030ab  pop     rsi
0x1800030ac  pop     rbp
0x1800030ad  pop     rbx
0x1800030ae  retn
```
