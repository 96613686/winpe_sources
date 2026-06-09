# CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)

- ea: `0x180003fcc`
- end: `0x18000403d`
- name: `?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z`
- size: `113`
- prototype: `__int64 __fastcall(char *Src, size_t Size, char **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005394`

## callees

- `0x180003fcc`
- `0x18000ec56`

## pseudocode

```c
__int64 __fastcall CopyFieldToBuffer(char *Src, size_t Size, char **a3, unsigned int *a4, unsigned int a5)
{
  const char *v5; // r10
  size_t v7; // r8
  _BYTE *v8; // rbx
  __int64 v9; // rdi
  __int64 result; // rax

  v5 = "-";
  v7 = 1;
  if ( (_DWORD)Size )
  {
    v7 = (unsigned int)Size;
    v5 = Src;
  }
  *a4 += v7 + 1;
  if ( *a4 > a5 )
    return 0;
  v8 = *a3;
  v9 = (unsigned int)v7;
  memcpy_0(*a3, v5, v7);
  v8[v9] = 32;
  result = 1;
  *a3 = &v8[v9 + 1];
  return result;
}

```

## disassembly

```asm
0x180003fcc  mov     [rsp+arg_0], rbx
0x180003fd1  mov     [rsp+arg_8], rsi
0x180003fd6  push    rdi
0x180003fd7  sub     rsp, 20h
0x180003fdb  test    edx, edx
0x180003fdd  lea     r10, Src; "-"
0x180003fe4  mov     rsi, r8
0x180003fe7  mov     r8d, 1
0x180003fed  cmovnz  r8d, edx; Size
0x180003ff1  cmovnz  r10, rcx
0x180003ff5  lea     eax, [r8+1]
0x180003ff9  add     [r9], eax
0x180003ffc  mov     ecx, [r9]
0x180003fff  cmp     ecx, [rsp+28h+arg_20]
0x180004003  ja      short loc_18000402B
0x180004005  mov     rbx, [rsi]
0x180004008  mov     rdx, r10; Src
0x18000400b  mov     rcx, rbx; void *
0x18000400e  mov     edi, r8d
0x180004011  call    memcpy_0
0x180004016  lea     rcx, [rbx+1]
0x18000401a  mov     byte ptr [rdi+rbx], 20h ; ' '
0x18000401e  add     rcx, rdi
0x180004021  mov     eax, 1
0x180004026  mov     [rsi], rcx
0x180004029  jmp     short loc_18000402D
0x18000402b  xor     eax, eax
0x18000402d  mov     rbx, [rsp+28h+arg_0]
0x180004032  mov     rsi, [rsp+28h+arg_8]
0x180004037  add     rsp, 20h
0x18000403b  pop     rdi
0x18000403c  retn
```
