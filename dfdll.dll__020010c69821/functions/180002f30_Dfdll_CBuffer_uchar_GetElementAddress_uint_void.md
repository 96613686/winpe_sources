# Dfdll::CBuffer<uchar>::GetElementAddress(uint,void * &)

- ea: `0x180002f30`
- end: `0x180002f54`
- name: `?GetElementAddress@?$CBuffer@E@Dfdll@@UEAAJIAEAPEAX@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f30`

## pseudocode

```c
__int64 __fastcall Dfdll::CBuffer<unsigned char>::GetElementAddress(__int64 a1, unsigned int a2, _QWORD *a3)
{
  if ( a2 >= *(_DWORD *)(a1 + 16) )
    return 2147942487LL;
  if ( !*(_QWORD *)(a1 + 8) )
    return 2147942413LL;
  *a3 = *(_QWORD *)(a1 + 8) + a2;
  return 0;
}

```

## disassembly

```asm
0x180002f30  cmp     edx, [rcx+10h]
0x180002f33  jb      short loc_180002F3B
0x180002f35  mov     eax, 80070057h
0x180002f3a  retn
0x180002f3b  cmp     qword ptr [rcx+8], 0
0x180002f40  jnz     short loc_180002F48
0x180002f42  mov     eax, 8007000Dh
0x180002f47  retn
0x180002f48  mov     eax, edx
0x180002f4a  add     rax, [rcx+8]
0x180002f4e  mov     [r8], rax
0x180002f51  xor     eax, eax
0x180002f53  retn
```
