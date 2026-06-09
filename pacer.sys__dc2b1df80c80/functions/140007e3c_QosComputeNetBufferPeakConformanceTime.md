# QosComputeNetBufferPeakConformanceTime

- ea: `0x140007e3c`
- end: `0x140007eaa`
- name: `QosComputeNetBufferPeakConformanceTime`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007260`

## callees

- `0x140007e3c`

## pseudocode

```c
__int64 __fastcall QosComputeNetBufferPeakConformanceTime(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4)
{
  unsigned __int64 v4; // rbx
  unsigned int v5; // r10d
  unsigned int v6; // esi
  __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  unsigned int v13; // eax

  v4 = *(_QWORD *)(a4 + 8);
  v5 = 0;
  v6 = 0;
  if ( a2 )
  {
    v9 = 0;
    do
    {
      v10 = v4;
      v11 = 32 * v9;
      v12 = *(_QWORD *)(32 * v9 + a4);
      *(_QWORD *)(32 * v9 + a4 + 8) = v4;
      if ( v4 <= v12 )
        v10 = v12;
      v13 = v5 + 1;
      *(_QWORD *)(v11 + a4 + 16) = v10;
      if ( v10 > a3 )
        v13 = v5;
      ++v6;
      v5 = v13;
      ++v9;
      v4 += 1000000 * (unsigned __int64)*(unsigned int *)(v11 + a4 + 28) / a1;
    }
    while ( v6 < a2 );
  }
  return v5;
}

```

## disassembly

```asm
0x140007e3c  push    rbx
0x140007e3e  push    rbp
0x140007e3f  push    rsi
0x140007e40  push    rdi
0x140007e41  mov     rbx, [r9+8]
0x140007e45  xor     r10d, r10d
0x140007e48  xor     esi, esi
0x140007e4a  mov     r11d, edx
0x140007e4d  mov     rbp, rcx
0x140007e50  test    edx, edx
0x140007e52  jz      short loc_140007EA1
0x140007e54  xor     edi, edi
0x140007e56  mov     rdx, rdi
0x140007e59  mov     rcx, rbx
0x140007e5c  shl     rdx, 5
0x140007e60  mov     rax, [rdx+r9]
0x140007e64  cmp     rbx, rax
0x140007e67  mov     [rdx+r9+8], rbx
0x140007e6c  cmovbe  rcx, rax
0x140007e70  lea     eax, [r10+1]
0x140007e74  cmp     rcx, r8
0x140007e77  mov     [rdx+r9+10h], rcx
0x140007e7c  cmova   eax, r10d
0x140007e80  inc     esi
0x140007e82  mov     r10d, eax
0x140007e85  inc     rdi
0x140007e88  mov     eax, [rdx+r9+1Ch]
0x140007e8d  xor     edx, edx
0x140007e8f  imul    rax, 0F4240h
0x140007e96  div     rbp
0x140007e99  add     rbx, rax
0x140007e9c  cmp     esi, r11d
0x140007e9f  jb      short loc_140007E56
0x140007ea1  mov     eax, r10d
0x140007ea4  pop     rdi
0x140007ea5  pop     rsi
0x140007ea6  pop     rbp
0x140007ea7  pop     rbx
0x140007ea8  retn
```
