# Dfdll::CBuffer<tagVARIANT>::GetElementAddress(uint,void * &)

- ea: `0x180002f90`
- end: `0x180002fba`
- name: `?GetElementAddress@?$CBuffer@UtagVARIANT@@@Dfdll@@UEAAJIAEAPEAX@Z`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f90`

## pseudocode

```c
__int64 __fastcall Dfdll::CBuffer<tagVARIANT>::GetElementAddress(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // rax
  __int64 v5; // rdx

  v3 = a2;
  if ( a2 >= *(_DWORD *)(a1 + 16) )
    return 2147942487LL;
  v5 = *(_QWORD *)(a1 + 8);
  if ( !v5 )
    return 2147942413LL;
  *a3 = v5 + 24 * v3;
  return 0;
}

```

## disassembly

```asm
0x180002f90  mov     eax, edx
0x180002f92  cmp     edx, [rcx+10h]
0x180002f95  jb      short loc_180002F9D
0x180002f97  mov     eax, 80070057h
0x180002f9c  retn
0x180002f9d  mov     rdx, [rcx+8]
0x180002fa1  test    rdx, rdx
0x180002fa4  jnz     short loc_180002FAC
0x180002fa6  mov     eax, 8007000Dh
0x180002fab  retn
0x180002fac  lea     rcx, [rax+rax*2]
0x180002fb0  lea     rax, [rdx+rcx*8]
0x180002fb4  mov     [r8], rax
0x180002fb7  xor     eax, eax
0x180002fb9  retn
```
