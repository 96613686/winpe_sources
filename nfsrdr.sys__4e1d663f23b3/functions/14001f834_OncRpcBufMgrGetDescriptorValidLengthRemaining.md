# OncRpcBufMgrGetDescriptorValidLengthRemaining

- ea: `0x14001f834`
- end: `0x14001f856`
- name: `OncRpcBufMgrGetDescriptorValidLengthRemaining`
- size: `34`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9f0`
- `0x1400150a4`
- `0x140025004`
- `0x140038850`
- `0x14003896c`

## callees

- `0x14001f834`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetDescriptorValidLengthRemaining(_DWORD *a1)
{
  unsigned int v1; // edx
  unsigned int v2; // r8d
  unsigned int v3; // ecx
  __int64 result; // rax

  v1 = a1[16] - a1[14];
  v2 = a1[19];
  if ( v2 < v1 )
    v3 = -1;
  else
    v3 = v2 - v1;
  result = 0;
  if ( v2 >= v1 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x14001f834  mov     edx, [rcx+40h]
0x14001f837  sub     edx, [rcx+38h]
0x14001f83a  mov     r8d, [rcx+4Ch]
0x14001f83e  cmp     r8d, edx
0x14001f841  jb      short loc_14001F84A
0x14001f843  mov     ecx, r8d
0x14001f846  sub     ecx, edx
0x14001f848  jmp     short loc_14001F84D
0x14001f84a  or      ecx, 0FFFFFFFFh
0x14001f84d  xor     eax, eax
0x14001f84f  cmp     r8d, edx
0x14001f852  cmovnb  eax, ecx
0x14001f855  retn
```
