# QosLineComputeControlInterval

- ea: `0x140002484`
- end: `0x1400024f9`
- name: `QosLineComputeControlInterval`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001d40`
- `0x140001fec`
- `0x1400020f0`
- `0x1400039d8`
- `0x140003ab0`

## callees

- `0x140002484`

## pseudocode

```c
__int64 __fastcall QosLineComputeControlInterval(__int64 a1)
{
  unsigned __int64 v1; // rax
  __int64 result; // rax
  unsigned int v3; // r8d
  unsigned int v4; // r9d
  unsigned int v5; // edx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 <= 0xC80000 )
  {
    v4 = 10000;
    v3 = 1;
    *(_DWORD *)(a1 + 116) = 10000;
    result = 10000;
  }
  else if ( v1 > 0x8000000 )
  {
    result = 500;
    v3 = 10;
    *(_DWORD *)(a1 + 116) = 500;
    v4 = 12500;
  }
  else
  {
    *(_DWORD *)(a1 + 116) = 1000;
    result = 5000;
    v3 = 1;
    v4 = 7000;
  }
  v5 = *(_DWORD *)(a1 + 104);
  if ( v5 > 0xA )
  {
    if ( v5 >= 0x1E )
      result = v4 / v3;
    *(_DWORD *)(a1 + 116) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140002484  mov     rax, [rcx+8]
0x140002488  cmp     rax, 0C80000h
0x14000248e  jbe     short loc_1400024C4
0x140002490  cmp     rax, 8000000h
0x140002496  ja      short loc_1400024D9
0x140002498  mov     dword ptr [rcx+74h], 3E8h
0x14000249f  mov     eax, 1388h
0x1400024a4  mov     r8d, 1
0x1400024aa  mov     r9d, 1B58h
0x1400024b0  mov     edx, [rcx+68h]
0x1400024b3  cmp     edx, 0Ah
0x1400024b6  ja      short loc_1400024BA
0x1400024b8  retn
0x1400024ba  cmp     edx, 1Eh
0x1400024bd  jnb     short loc_1400024EF
0x1400024bf  mov     [rcx+74h], eax
0x1400024c2  retn
0x1400024c4  mov     r9d, 2710h
0x1400024ca  mov     r8d, 1
0x1400024d0  mov     [rcx+74h], r9d
0x1400024d4  mov     eax, r9d
0x1400024d7  jmp     short loc_1400024B0
0x1400024d9  mov     eax, 1F4h
0x1400024de  mov     r8d, 0Ah
0x1400024e4  mov     [rcx+74h], eax
0x1400024e7  mov     r9d, 30D4h
0x1400024ed  jmp     short loc_1400024B0
0x1400024ef  xor     edx, edx
0x1400024f1  mov     eax, r9d
0x1400024f4  div     r8d
0x1400024f7  jmp     short loc_1400024BF
```
