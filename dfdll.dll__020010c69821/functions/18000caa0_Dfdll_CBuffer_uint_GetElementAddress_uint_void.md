# Dfdll::CBuffer<uint>::GetElementAddress(uint,void * &)

- ea: `0x18000caa0`
- end: `0x18000cac6`
- name: `?GetElementAddress@?$CBuffer@I@Dfdll@@UEAAJIAEAPEAX@Z`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000caa0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBuffer<unsigned int>::GetElementAddress(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 v4; // rcx

  if ( a2 >= *(_DWORD *)(a1 + 16) )
    return 2147942487LL;
  v4 = *(_QWORD *)(a1 + 8);
  if ( !v4 )
    return 2147942413LL;
  result = 0;
  *a3 = v4 + 4LL * a2;
  return result;
}

```

## disassembly

```asm
0x18000caa0  cmp     edx, [rcx+10h]
0x18000caa3  jb      short loc_18000CAAB
0x18000caa5  mov     eax, 80070057h
0x18000caaa  retn
0x18000caab  mov     rcx, [rcx+8]
0x18000caaf  test    rcx, rcx
0x18000cab2  jnz     short loc_18000CABA
0x18000cab4  mov     eax, 8007000Dh
0x18000cab9  retn
0x18000caba  mov     eax, edx
0x18000cabc  lea     rcx, [rcx+rax*4]
0x18000cac0  xor     eax, eax
0x18000cac2  mov     [r8], rcx
0x18000cac5  retn
```
