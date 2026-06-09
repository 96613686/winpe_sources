# QosUtilComputeTokenSpec

- ea: `0x140007ef0`
- end: `0x140007f50`
- name: `QosUtilComputeTokenSpec`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004c58`
- `0x140007260`
- `0x140009860`

## callees

- `0x140007ef0`

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
0x140007ef0  mov     r8, [rcx+10h]
0x140007ef4  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140007ef8  jz      short loc_140007F30
0x140007efa  imul    r8, rdx
0x140007efe  mov     r9, 624DD2F1A9FBE77h
0x140007f08  mov     rax, r9
0x140007f0b  mul     r8
0x140007f0e  mov     rax, r9
0x140007f11  sub     r8, rdx
0x140007f14  shr     r8, 1
0x140007f17  add     r8, rdx
0x140007f1a  shr     r8, 9
0x140007f1e  mul     r8
0x140007f21  sub     r8, rdx
0x140007f24  shr     r8, 1
0x140007f27  add     r8, rdx
0x140007f2a  shr     r8, 9
0x140007f2e  jmp     short loc_140007F33
0x140007f30  xor     r8d, r8d
0x140007f33  mov     rax, [rcx]
0x140007f36  lea     rdx, [rax+r8]
0x140007f3a  cmp     rdx, rax
0x140007f3d  jl      short loc_140007F48
0x140007f3f  mov     [rcx], rdx
0x140007f42  cmp     rdx, [rcx+8]
0x140007f46  jle     short locret_140007F4F
0x140007f48  mov     rax, [rcx+8]
0x140007f4c  mov     [rcx], rax
0x140007f4f  retn
```
