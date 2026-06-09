# NFMcomp_allocate

- ea: `0x180012328`
- end: `0x18001240e`
- name: `NFMcomp_allocate`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800122c0`
- `0x1800142a8`

## callees

- `0x180012328`
- `0x180012548`
- `0x18001562a`

## pseudocode

```c
_DWORD *__fastcall NFMcomp_allocate(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *Memory; // rax
  _DWORD *v4; // rbx

  Memory = (_DWORD *)NFMcompress_PickAllocRoutineAndAllocateMemory(a1, a2, a3, 12256);
  v4 = Memory;
  if ( Memory )
  {
    memset_0(Memory, 0, 0x2FE0u);
    v4[36] = 257;
    *((_QWORD *)v4 + 17) = dword_18001E880;
    *((_QWORD *)v4 + 15) = v4 + 60;
    *((_QWORD *)v4 + 20) = v4 + 633;
    *((_QWORD *)v4 + 16) = v4 + 694;
    *((_QWORD *)v4 + 21) = v4 + 982;
    v4[37] = 286;
    *((_QWORD *)v4 + 22) = dword_18001E800;
    *((_QWORD *)v4 + 25) = v4 + 1012;
    *((_QWORD *)v4 + 27) = qword_18001E900;
    v4[38] = 15;
    v4[47] = 30;
    v4[48] = 15;
    v4[57] = 19;
    v4[58] = 7;
  }
  return v4;
}

```

## disassembly

```asm
0x180012328  push    rbx
0x18001232a  sub     rsp, 20h
0x18001232e  mov     r9d, 2FE0h
0x180012334  call    NFMcompress_PickAllocRoutineAndAllocateMemory
0x180012339  mov     rbx, rax
0x18001233c  test    rax, rax
0x18001233f  jz      loc_180012405
0x180012345  xor     edx, edx; Val
0x180012347  mov     r8d, 2FE0h; Size
0x18001234d  mov     rcx, rax; void *
0x180012350  call    memset_0
0x180012355  lea     rax, dword_18001E880
0x18001235c  mov     dword ptr [rbx+90h], 101h
0x180012366  mov     [rbx+88h], rax
0x18001236d  lea     rcx, [rbx+0F0h]
0x180012374  lea     rax, [rbx+9E4h]
0x18001237b  mov     [rbx+78h], rcx
0x18001237f  mov     [rbx+0A0h], rax
0x180012386  lea     rcx, [rbx+0AD8h]
0x18001238d  lea     rax, [rbx+0F58h]
0x180012394  mov     [rbx+80h], rcx
0x18001239b  mov     [rbx+0A8h], rax
0x1800123a2  mov     ecx, 0Fh
0x1800123a7  lea     rax, dword_18001E800
0x1800123ae  mov     dword ptr [rbx+94h], 11Eh
0x1800123b8  mov     [rbx+0B0h], rax
0x1800123bf  lea     rax, [rbx+0FD0h]
0x1800123c6  mov     [rbx+0C8h], rax
0x1800123cd  lea     rax, qword_18001E900
0x1800123d4  mov     [rbx+0D8h], rax
0x1800123db  mov     [rbx+98h], ecx
0x1800123e1  mov     dword ptr [rbx+0BCh], 1Eh
0x1800123eb  mov     [rbx+0C0h], ecx
0x1800123f1  mov     dword ptr [rbx+0E4h], 13h
0x1800123fb  mov     dword ptr [rbx+0E8h], 7
0x180012405  mov     rax, rbx
0x180012408  add     rsp, 20h
0x18001240c  pop     rbx
0x18001240d  retn
```
