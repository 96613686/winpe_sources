# Dfdll::CBuffer<ushort>::GetElementAddress(uint,void * &)

- ea: `0x180002f60`
- end: `0x180002f86`
- name: `?GetElementAddress@?$CBuffer@G@Dfdll@@UEAAJIAEAPEAX@Z`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f60`

## pseudocode

```c
__int64 __fastcall Dfdll::CBuffer<unsigned short>::GetElementAddress(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 v4; // rcx

  if ( a2 >= *(_DWORD *)(a1 + 16) )
    return 2147942487LL;
  v4 = *(_QWORD *)(a1 + 8);
  if ( !v4 )
    return 2147942413LL;
  result = 0;
  *a3 = v4 + 2LL * a2;
  return result;
}

```

## disassembly

```asm
0x180002f60  cmp     edx, [rcx+10h]
0x180002f63  jb      short loc_180002F6B
0x180002f65  mov     eax, 80070057h
0x180002f6a  retn
0x180002f6b  mov     rcx, [rcx+8]
0x180002f6f  test    rcx, rcx
0x180002f72  jnz     short loc_180002F7A
0x180002f74  mov     eax, 8007000Dh
0x180002f79  retn
0x180002f7a  mov     eax, edx
0x180002f7c  lea     rcx, [rcx+rax*2]
0x180002f80  xor     eax, eax
0x180002f82  mov     [r8], rcx
0x180002f85  retn
```
