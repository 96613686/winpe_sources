# acmdDriverOpen

- ea: `0x180006c60`
- end: `0x180006cc8`
- name: `acmdDriverOpen`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006760`

## callees

- `0x180006c60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006c88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006c88`

## pseudocode

```c
__int64 __fastcall acmdDriverOpen(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 1;
  if ( a2[1] != 1667528033 )
    return 0;
  result = (__int64)LocalAlloc(0x40u, 0x20u);
  if ( !result )
  {
    a2[5] = 7;
    return 0;
  }
  *(_DWORD *)result = a2[1];
  *(_QWORD *)(result + 8) = 0;
  *(_QWORD *)(result + 16) = 0;
  *(_DWORD *)(result + 24) = a2[3];
  *(_DWORD *)(result + 28) = a2[4];
  a2[5] = 0;
  return result;
}

```

## disassembly

```asm
0x180006c60  push    rbx
0x180006c62  sub     rsp, 20h
0x180006c66  mov     rbx, rdx
0x180006c69  test    rdx, rdx
0x180006c6c  jnz     short loc_180006C75
0x180006c6e  mov     eax, 1
0x180006c73  jmp     short loc_180006CC2
0x180006c75  cmp     dword ptr [rdx+4], 63647561h
0x180006c7c  jnz     short loc_180006C9D
0x180006c7e  mov     edx, 20h ; ' '; uBytes
0x180006c83  mov     ecx, 40h ; '@'; uFlags
0x180006c88  call    cs:__imp_LocalAlloc
0x180006c8e  mov     rcx, rax
0x180006c91  test    rax, rax
0x180006c94  jnz     short loc_180006CA1
0x180006c96  mov     dword ptr [rbx+14h], 7
0x180006c9d  xor     eax, eax
0x180006c9f  jmp     short loc_180006CC2
0x180006ca1  mov     eax, [rbx+4]
0x180006ca4  xor     edx, edx
0x180006ca6  mov     [rcx], eax
0x180006ca8  mov     [rcx+8], rdx
0x180006cac  mov     [rcx+10h], rdx
0x180006cb0  mov     eax, [rbx+0Ch]
0x180006cb3  mov     [rcx+18h], eax
0x180006cb6  mov     eax, [rbx+10h]
0x180006cb9  mov     [rcx+1Ch], eax
0x180006cbc  mov     rax, rcx
0x180006cbf  mov     [rbx+14h], edx
0x180006cc2  add     rsp, 20h
0x180006cc6  pop     rbx
0x180006cc7  retn
```
