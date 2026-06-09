# TlmiInitializeProviderGlobalData

- ea: `0x180019bec`
- end: `0x180019d4d`
- name: `TlmiInitializeProviderGlobalData`
- size: `353`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012b08`
- `0x18001ac80`

## callees

- `0x180019bec`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019c3e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019c5d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019c3e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180019c5d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019c13`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019c13`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019d34`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019d34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ca6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ca6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019cbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019cbd`

## pseudocode

```c
char __fastcall TlmiInitializeProviderGlobalData(const wchar_t *Src, const wchar_t *a2)
{
  char result; // al
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned int v7; // eax
  size_t v8; // r15
  size_t v9; // r14
  HANDLE ProcessHeap; // rax
  char *v11; // rax

  result = byte_18002A938;
  if ( !byte_18002A938 )
  {
    RtlAcquireSRWLockExclusive(&qword_18002A940);
    if ( !byte_18002A938 )
    {
      if ( Src )
        v5 = wcsnlen(Src, 0xFFu);
      else
        v5 = 0;
      v6 = v5;
      if ( a2 )
        v7 = wcsnlen(a2, 0xFFu);
      else
        v7 = 0;
      if ( (unsigned __int64)(2 * v6 - 3) <= 0x1FA && 2 * (unsigned __int64)v7 - 3 <= 0x1FA )
      {
        v8 = 2LL * v7 + 2;
        v9 = 2 * v6 + 2;
        ProcessHeap = GetProcessHeap();
        v11 = (char *)HeapAlloc(ProcessHeap, 8u, v8 + v9);
        if ( v11 )
        {
          lpMem = v11;
          qword_18002A960 = &v11[v9];
          memcpy_0(v11, Src, v9);
          memcpy_0(qword_18002A960, a2, v8);
          HIWORD(dword_18002A948) = 2 * v6 + 2;
          LOWORD(dword_18002A948) = 2 * v6;
          LOWORD(dword_18002A958) = v8 - 2;
          HIWORD(dword_18002A958) = v8;
          byte_18002A938 = 1;
        }
      }
    }
    return RtlReleaseSRWLockExclusive(&qword_18002A940);
  }
  return result;
}

```

## disassembly

```asm
0x180019bec  push    rbx
0x180019bee  push    rsi
0x180019bef  push    rdi
0x180019bf0  push    r14
0x180019bf2  push    r15
0x180019bf4  sub     rsp, 20h
0x180019bf8  mov     al, cs:byte_18002A938
0x180019bfe  mov     rsi, rdx
0x180019c01  mov     rdi, rcx
0x180019c04  test    al, al
0x180019c06  jnz     loc_180019D40
0x180019c0c  lea     rcx, qword_18002A940
0x180019c13  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180019c1a  nop     dword ptr [rax+rax+00h]
0x180019c1f  mov     al, cs:byte_18002A938
0x180019c25  test    al, al
0x180019c27  jnz     loc_180019D2D
0x180019c2d  test    rdi, rdi
0x180019c30  jnz     short loc_180019C36
0x180019c32  xor     eax, eax
0x180019c34  jmp     short loc_180019C4A
0x180019c36  mov     edx, 0FFh; MaxCount
0x180019c3b  mov     rcx, rdi; Source
0x180019c3e  call    cs:__imp_wcsnlen
0x180019c45  nop     dword ptr [rax+rax+00h]
0x180019c4a  mov     ebx, eax
0x180019c4c  test    rsi, rsi
0x180019c4f  jnz     short loc_180019C55
0x180019c51  xor     eax, eax
0x180019c53  jmp     short loc_180019C69
0x180019c55  mov     edx, 0FFh; MaxCount
0x180019c5a  mov     rcx, rsi; Source
0x180019c5d  call    cs:__imp_wcsnlen
0x180019c64  nop     dword ptr [rax+rax+00h]
0x180019c69  lea     rcx, ds:0FFFFFFFFFFFFFFFDh[rbx*2]
0x180019c71  mov     edx, 1FAh
0x180019c76  cmp     rcx, rdx
0x180019c79  ja      loc_180019D2D
0x180019c7f  mov     ecx, eax
0x180019c81  lea     rax, ds:0FFFFFFFFFFFFFFFDh[rcx*2]
0x180019c89  cmp     rax, rdx
0x180019c8c  ja      loc_180019D2D
0x180019c92  lea     r15, ds:2[rcx*2]
0x180019c9a  lea     r14, ds:2[rbx*2]
0x180019ca2  lea     rbx, [r15+r14]
0x180019ca6  call    cs:__imp_GetProcessHeap
0x180019cad  nop     dword ptr [rax+rax+00h]
0x180019cb2  mov     r8, rbx; dwBytes
0x180019cb5  mov     edx, 8; dwFlags
0x180019cba  mov     rcx, rax; hHeap
0x180019cbd  call    cs:__imp_HeapAlloc
0x180019cc4  nop     dword ptr [rax+rax+00h]
0x180019cc9  test    rax, rax
0x180019ccc  jz      short loc_180019D2D
0x180019cce  lea     rcx, [r14+rax]
0x180019cd2  mov     cs:lpMem, rax
0x180019cd9  mov     cs:qword_18002A960, rcx
0x180019ce0  mov     r8, r14; Size
0x180019ce3  mov     rcx, rax; void *
0x180019ce6  mov     rdx, rdi; Src
0x180019ce9  call    memcpy_0
0x180019cee  mov     rcx, cs:qword_18002A960; void *
0x180019cf5  mov     r8, r15; Size
0x180019cf8  mov     rdx, rsi; Src
0x180019cfb  call    memcpy_0
0x180019d00  lea     eax, [r14-2]
0x180019d04  mov     word ptr cs:dword_18002A948+2, r14w
0x180019d0c  mov     word ptr cs:dword_18002A948, ax
0x180019d13  lea     eax, [r15-2]
0x180019d17  mov     word ptr cs:dword_18002A958, ax
0x180019d1e  mov     word ptr cs:dword_18002A958+2, r15w
0x180019d26  mov     cs:byte_18002A938, 1
0x180019d2d  lea     rcx, qword_18002A940
0x180019d34  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180019d3b  nop     dword ptr [rax+rax+00h]
0x180019d40  add     rsp, 20h
0x180019d44  pop     r15
0x180019d46  pop     r14
0x180019d48  pop     rdi
0x180019d49  pop     rsi
0x180019d4a  pop     rbx
0x180019d4b  retn
```
