# FREB_XML_SERIALIZER::AllocateMemory(ulong)

- ea: `0x180009690`
- end: `0x18000972b`
- name: `?AllocateMemory@FREB_XML_SERIALIZER@@QEAAPEAEK@Z`
- size: `155`
- prototype: `char *__fastcall(FREB_XML_SERIALIZER *this, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000927c`
- `0x1800092e0`
- `0x180009360`
- `0x180009458`
- `0x1800094bc`

## callees

- `0x180009690`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096a8`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800096fb`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800096fb`

## pseudocode

```c
char *__fastcall FREB_XML_SERIALIZER::AllocateMemory(FREB_XML_SERIALIZER *this, unsigned int a2)
{
  char *v2; // rsi
  unsigned int v4; // r14d
  __int64 v5; // rbp
  HANDLE ProcessHeap; // rax
  __int64 v7; // r9
  __int64 v8; // rcx
  char *v10; // rdi
  void *v11; // r8
  char *v12; // rax
  __int64 v13; // rcx

  v2 = (char *)*((_QWORD *)this + 1);
  v4 = *((_DWORD *)this + 4);
  v5 = a2;
  ProcessHeap = GetProcessHeap();
  v7 = *((unsigned int *)this + 5);
  v8 = *((unsigned int *)this + 6);
  if ( (unsigned __int64)(v5 + v7 + v8) > 0xFFFFFFFF )
    return 0;
  v10 = 0;
  if ( (unsigned int)(v8 + v5) > *((_DWORD *)this + 4) )
  {
    v11 = (void *)*((_QWORD *)this + 1);
    v4 = v5 + v8 + v7;
    if ( v11 )
      v12 = (char *)HeapReAlloc(ProcessHeap, 8u, v11, v4);
    else
      v12 = (char *)HeapAlloc(ProcessHeap, 8u, v4);
    v2 = v12;
  }
  if ( v2 )
  {
    v13 = *((unsigned int *)this + 6);
    *((_QWORD *)this + 1) = v2;
    *((_DWORD *)this + 4) = v4;
    v10 = &v2[v13];
    *((_DWORD *)this + 6) = v5 + v13;
  }
  return v10;
}

```

## disassembly

```asm
0x180009690  push    rbx
0x180009692  push    rbp
0x180009693  push    rsi
0x180009694  push    rdi
0x180009695  push    r14
0x180009697  sub     rsp, 20h
0x18000969b  mov     rsi, [rcx+8]
0x18000969f  mov     rbx, rcx
0x1800096a2  mov     r14d, [rcx+10h]
0x1800096a6  mov     ebp, edx
0x1800096a8  call    cs:__imp_GetProcessHeap
0x1800096ae  mov     r9d, [rbx+14h]
0x1800096b2  mov     r10, rax
0x1800096b5  mov     ecx, [rbx+18h]
0x1800096b8  mov     eax, 0FFFFFFFFh
0x1800096bd  lea     r8, [r9+rcx]
0x1800096c1  add     r8, rbp
0x1800096c4  cmp     r8, rax
0x1800096c7  jbe     short loc_1800096CD
0x1800096c9  xor     eax, eax
0x1800096cb  jmp     short loc_180009720
0x1800096cd  xor     edi, edi
0x1800096cf  lea     eax, [rcx+rbp]
0x1800096d2  cmp     eax, [rbx+10h]
0x1800096d5  jbe     short loc_180009704
0x1800096d7  mov     r8, [rbx+8]; lpMem
0x1800096db  lea     r14d, [rcx+r9]
0x1800096df  add     r14d, ebp
0x1800096e2  lea     edx, [rdi+8]; dwFlags
0x1800096e5  mov     r9d, r14d; dwBytes
0x1800096e8  mov     rcx, r10; hHeap
0x1800096eb  test    r8, r8
0x1800096ee  jnz     short loc_1800096FB
0x1800096f0  mov     r8d, r9d; dwBytes
0x1800096f3  call    cs:__imp_HeapAlloc
0x1800096f9  jmp     short loc_180009701
0x1800096fb  call    cs:__imp_HeapReAlloc
0x180009701  mov     rsi, rax
0x180009704  test    rsi, rsi
0x180009707  jz      short loc_18000971D
0x180009709  mov     ecx, [rbx+18h]
0x18000970c  mov     [rbx+8], rsi
0x180009710  mov     [rbx+10h], r14d
0x180009714  lea     rdi, [rsi+rcx]
0x180009718  add     ecx, ebp
0x18000971a  mov     [rbx+18h], ecx
0x18000971d  mov     rax, rdi
0x180009720  add     rsp, 20h
0x180009724  pop     r14
0x180009726  pop     rdi
0x180009727  pop     rsi
0x180009728  pop     rbp
0x180009729  pop     rbx
0x18000972a  retn
```
