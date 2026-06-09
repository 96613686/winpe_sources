# removeRequestFromPriorityQueue

- ea: `0x140003aa8`
- end: `0x140003b32`
- name: `removeRequestFromPriorityQueue`
- size: `138`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a2c`
- `0x140003268`
- `0x140003520`

## callees

- `0x140003aa8`

## pseudocode

```c
signed __int64 __fastcall removeRequestFromPriorityQueue(__int64 a1)
{
  char *v1; // rdx
  __int64 v3; // r10
  _QWORD *v4; // r8
  int v5; // ecx
  signed __int64 result; // rax
  int v7; // r8d

  v1 = g_priorityQueueSw;
  if ( (*(_DWORD *)(a1 + 92) & 1) == 0 )
    v1 = g_priorityQueueHw;
  v3 = *(_QWORD *)(a1 + 136);
  if ( *(_QWORD *)(v3 + 8) != a1 + 136 || (v4 = *(_QWORD **)(a1 + 144), *v4 != a1 + 136) )
    __fastfail(3u);
  v5 = *(_DWORD *)(a1 + 128);
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  --*(_DWORD *)v1;
  result = *(unsigned int *)(a1 + 32);
  g_nBytesInQueues -= result;
  v7 = *((_DWORD *)v1 + 1);
  if ( v5 == v7 )
  {
    if ( *(_DWORD *)v1 )
    {
      while ( 1 )
      {
        result = (signed __int64)&v1[16 * v7 + 8];
        if ( *(_QWORD *)result != result )
          break;
        *((_DWORD *)v1 + 1) = --v7;
      }
    }
    else
    {
      *((_DWORD *)v1 + 1) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003aa8  mov     eax, [rcx+5Ch]
0x140003aab  lea     rdx, g_priorityQueueSw
0x140003ab2  test    al, 1
0x140003ab4  mov     r9, rcx
0x140003ab7  lea     rax, g_priorityQueueHw
0x140003abe  cmovz   rdx, rax
0x140003ac2  lea     rax, [rcx+88h]
0x140003ac9  mov     r10, [rax]
0x140003acc  cmp     [r10+8], rax
0x140003ad0  jnz     short loc_140003B2B
0x140003ad2  mov     r8, [rax+8]
0x140003ad6  cmp     [r8], rax
0x140003ad9  jnz     short loc_140003B2B
0x140003adb  mov     ecx, [rcx+80h]
0x140003ae1  mov     [r8], r10
0x140003ae4  mov     [r10+8], r8
0x140003ae8  dec     dword ptr [rdx]
0x140003aea  mov     eax, [r9+20h]
0x140003aee  sub     cs:g_nBytesInQueues, rax
0x140003af5  mov     r8d, [rdx+4]
0x140003af9  mov     r10d, [rdx]
0x140003afc  cmp     ecx, r8d
0x140003aff  jnz     short locret_140003B29
0x140003b01  test    r10d, r10d
0x140003b04  jz      short loc_140003B22
0x140003b06  mov     eax, r8d
0x140003b09  shl     rax, 4
0x140003b0d  add     rax, 8
0x140003b11  add     rax, rdx
0x140003b14  cmp     [rax], rax
0x140003b17  jnz     short locret_140003B29
0x140003b19  dec     r8d
0x140003b1c  mov     [rdx+4], r8d
0x140003b20  jmp     short loc_140003B06
0x140003b22  mov     dword ptr [rdx+4], 0
0x140003b29  retn
0x140003b2b  mov     ecx, 3
0x140003b30  int     29h; Win8: RtlFailFast(ecx)
```
