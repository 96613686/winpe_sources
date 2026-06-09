# HacConstructFakeDirectory

- ea: `0x14001f904`
- end: `0x14001f9c6`
- name: `HacConstructFakeDirectory`
- size: `194`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000be20`
- `0x140025484`

## callees

- `0x14003b0c0`

## pseudocode

```c
__int64 __fastcall HacConstructFakeDirectory(__int64 a1)
{
  __int64 result; // rax

  *(_WORD *)(a1 + 48) |= 0x8000u;
  *(_QWORD *)(a1 + 120) = MEMORY[0xFFFFF78000000014];
  *(_DWORD *)(a1 + 216) = 0;
  memset((void *)(a1 + 220), 255, 0x40u);
  *(_DWORD *)(a1 + 132) = 365;
  *(_DWORD *)(a1 + 128) = 2;
  *(_DWORD *)(a1 + 136) = 2;
  *(_DWORD *)(a1 + 140) = -2;
  *(_DWORD *)(a1 + 144) = -2;
  result = 0xFFFFFFFFLL;
  *(_QWORD *)(a1 + 176) = 0xFFFFFFFFLL;
  *(_QWORD *)(a1 + 184) = 0xFFFFFFFFLL;
  *(_QWORD *)(a1 + 152) = 64;
  *(_QWORD *)(a1 + 160) = 64;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  return result;
}

```

## disassembly

```asm
0x14001f904  mov     [rsp+arg_0], rbx
0x14001f909  push    rdi
0x14001f90a  sub     rsp, 20h
0x14001f90e  mov     eax, 8000h
0x14001f913  mov     rbx, rcx
0x14001f916  or      [rcx+30h], ax
0x14001f91a  mov     edi, 40h ; '@'
0x14001f91f  mov     rax, 0FFFFF78000000014h
0x14001f929  mov     r8d, edi; Size
0x14001f92c  mov     edx, 0FFh; Val
0x14001f931  mov     rax, [rax]
0x14001f934  mov     [rcx+78h], rax
0x14001f938  mov     dword ptr [rcx+0D8h], 0
0x14001f942  add     rcx, 0DCh; void *
0x14001f949  call    memset
0x14001f94e  lea     eax, [rdi-3Eh]
0x14001f951  mov     dword ptr [rbx+84h], 16Dh
0x14001f95b  mov     [rbx+80h], eax
0x14001f961  mov     [rbx+88h], eax
0x14001f967  mov     eax, 0FFFFFFFEh
0x14001f96c  mov     [rbx+8Ch], eax
0x14001f972  mov     [rbx+90h], eax
0x14001f978  mov     eax, 0FFFFFFFFh
0x14001f97d  mov     [rbx+0B0h], rax
0x14001f984  mov     [rbx+0B8h], rax
0x14001f98b  mov     [rbx+98h], rdi
0x14001f992  mov     [rbx+0A0h], rdi
0x14001f999  mov     qword ptr [rbx+0C0h], 0
0x14001f9a4  mov     qword ptr [rbx+0C8h], 0
0x14001f9af  mov     qword ptr [rbx+0D0h], 0
0x14001f9ba  mov     rbx, [rsp+28h+arg_0]
0x14001f9bf  add     rsp, 20h
0x14001f9c3  pop     rdi
0x14001f9c4  retn
```
