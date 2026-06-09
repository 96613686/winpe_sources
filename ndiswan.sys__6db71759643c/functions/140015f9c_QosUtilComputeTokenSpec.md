# QosUtilComputeTokenSpec

- ea: `0x140015f9c`
- end: `0x140015ffc`
- name: `QosUtilComputeTokenSpec`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400097f8`
- `0x14001554c`

## callees

- `0x140015f9c`

## pseudocode

```c
signed __int64 __fastcall QosUtilComputeTokenSpec(signed __int64 *a1, __int64 a2)
{
  signed __int64 v2; // r8
  unsigned __int64 v3; // r8
  signed __int64 result; // rax
  signed __int64 v5; // rdx

  v2 = a1[2];
  if ( v2 == -1 )
    v3 = 0;
  else
    v3 = a2 * v2 / 0x3E8uLL / 0x3E8;
  result = *a1;
  v5 = *a1 + v3;
  if ( v5 < *a1 || (*a1 = v5, v5 > a1[1]) )
  {
    result = a1[1];
    *a1 = result;
  }
  return result;
}

```

## disassembly

```asm
0x140015f9c  mov     r8, [rcx+10h]
0x140015fa0  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140015fa4  jz      short loc_140015FDC
0x140015fa6  imul    r8, rdx
0x140015faa  mov     r9, 624DD2F1A9FBE77h
0x140015fb4  mov     rax, r9
0x140015fb7  mul     r8
0x140015fba  mov     rax, r9
0x140015fbd  sub     r8, rdx
0x140015fc0  shr     r8, 1
0x140015fc3  add     r8, rdx
0x140015fc6  shr     r8, 9
0x140015fca  mul     r8
0x140015fcd  sub     r8, rdx
0x140015fd0  shr     r8, 1
0x140015fd3  add     r8, rdx
0x140015fd6  shr     r8, 9
0x140015fda  jmp     short loc_140015FDF
0x140015fdc  xor     r8d, r8d
0x140015fdf  mov     rax, [rcx]
0x140015fe2  lea     rdx, [rax+r8]
0x140015fe6  cmp     rdx, rax
0x140015fe9  jl      short loc_140015FF4
0x140015feb  mov     [rcx], rdx
0x140015fee  cmp     rdx, [rcx+8]
0x140015ff2  jle     short locret_140015FFB
0x140015ff4  mov     rax, [rcx+8]
0x140015ff8  mov     [rcx], rax
0x140015ffb  retn
```
