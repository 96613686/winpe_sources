# SetSmoothGrey8(x,x)

- ea: `0x1000e03d`
- end: `0x1000e119`
- name: `_SetSmoothGrey8@8`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1000e2f0`
- `0x1000e870`

## pseudocode

```c
char __fastcall SetSmoothGrey8(unsigned __int8 *a1, _BYTE *a2)
{
  char result; // al

  *a2 = GreyDwordDither[4 * *a1];
  a2[1] = byte_10003809[4 * *a1];
  a2[4] = byte_1000380A[4 * *a1];
  a2[5] = byte_1000380B[4 * *a1];
  a2[2] = GreyDwordDither[4 * a1[1]];
  a2[3] = byte_10003809[4 * a1[1]];
  a2[6] = byte_1000380A[4 * a1[1]];
  a2[7] = byte_1000380B[4 * a1[1]];
  a2[8] = GreyDwordDither[4 * a1[2]];
  a2[9] = byte_10003809[4 * a1[2]];
  a2[12] = byte_1000380A[4 * a1[2]];
  a2[13] = byte_1000380B[4 * a1[2]];
  a2[10] = GreyDwordDither[4 * a1[3]];
  a2[11] = byte_10003809[4 * a1[3]];
  a2[14] = byte_1000380A[4 * a1[3]];
  result = byte_1000380B[4 * a1[3]];
  a2[15] = result;
  return result;
}

```

## disassembly

```asm
0x1000e03d  movzx   eax, byte ptr [ecx]
0x1000e040  mov     al, ds:_GreyDwordDither[eax*4]
0x1000e047  mov     [edx], al
0x1000e049  movzx   eax, byte ptr [ecx]
0x1000e04c  mov     al, ds:byte_10003809[eax*4]
0x1000e053  mov     [edx+1], al
0x1000e056  movzx   eax, byte ptr [ecx]
0x1000e059  mov     al, ds:byte_1000380A[eax*4]
0x1000e060  mov     [edx+4], al
0x1000e063  movzx   eax, byte ptr [ecx]
0x1000e066  mov     al, ds:byte_1000380B[eax*4]
0x1000e06d  mov     [edx+5], al
0x1000e070  movzx   eax, byte ptr [ecx+1]
0x1000e074  mov     al, ds:_GreyDwordDither[eax*4]
0x1000e07b  mov     [edx+2], al
0x1000e07e  movzx   eax, byte ptr [ecx+1]
0x1000e082  mov     al, ds:byte_10003809[eax*4]
0x1000e089  mov     [edx+3], al
0x1000e08c  movzx   eax, byte ptr [ecx+1]
0x1000e090  mov     al, ds:byte_1000380A[eax*4]
0x1000e097  mov     [edx+6], al
0x1000e09a  movzx   eax, byte ptr [ecx+1]
0x1000e09e  mov     al, ds:byte_1000380B[eax*4]
0x1000e0a5  mov     [edx+7], al
0x1000e0a8  movzx   eax, byte ptr [ecx+2]
0x1000e0ac  mov     al, ds:_GreyDwordDither[eax*4]
0x1000e0b3  mov     [edx+8], al
0x1000e0b6  movzx   eax, byte ptr [ecx+2]
0x1000e0ba  mov     al, ds:byte_10003809[eax*4]
0x1000e0c1  mov     [edx+9], al
0x1000e0c4  movzx   eax, byte ptr [ecx+2]
0x1000e0c8  mov     al, ds:byte_1000380A[eax*4]
0x1000e0cf  mov     [edx+0Ch], al
0x1000e0d2  movzx   eax, byte ptr [ecx+2]
0x1000e0d6  mov     al, ds:byte_1000380B[eax*4]
0x1000e0dd  mov     [edx+0Dh], al
0x1000e0e0  movzx   eax, byte ptr [ecx+3]
0x1000e0e4  mov     al, ds:_GreyDwordDither[eax*4]
0x1000e0eb  mov     [edx+0Ah], al
0x1000e0ee  movzx   eax, byte ptr [ecx+3]
0x1000e0f2  mov     al, ds:byte_10003809[eax*4]
0x1000e0f9  mov     [edx+0Bh], al
0x1000e0fc  movzx   eax, byte ptr [ecx+3]
0x1000e100  mov     al, ds:byte_1000380A[eax*4]
0x1000e107  mov     [edx+0Eh], al
0x1000e10a  movzx   eax, byte ptr [ecx+3]
0x1000e10e  mov     al, ds:byte_1000380B[eax*4]
0x1000e115  mov     [edx+0Fh], al
0x1000e118  retn
```
