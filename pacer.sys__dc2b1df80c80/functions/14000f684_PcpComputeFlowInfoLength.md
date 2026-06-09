# PcpComputeFlowInfoLength

- ea: `0x14000f684`
- end: `0x14000f6cd`
- name: `PcpComputeFlowInfoLength`
- size: `73`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e0b0`
- `0x14000e464`

## callees

- `0x14000f684`

## pseudocode

```c
__int64 __fastcall PcpComputeFlowInfoLength(__int64 a1)
{
  __int64 *v1; // r8
  unsigned int v2; // edx
  __int64 *v3; // rcx
  bool v4; // zf
  int v5; // eax

  if ( (unsigned __int8)*(_DWORD *)(a1 + 48) == 1 )
  {
    v1 = (__int64 *)(a1 + 568);
    v2 = *(_DWORD *)(a1 + 608) + 16 * *(_DWORD *)(a1 + 584);
    v3 = *(__int64 **)(a1 + 568);
    while ( v3 != v1 )
    {
      v4 = *((_WORD *)v3 + 22) == 2;
      v5 = 48;
      v3 = (__int64 *)*v3;
      if ( !v4 )
        v5 = 96;
      v2 += v5;
    }
  }
  else
  {
    return *(unsigned int *)(a1 + 608);
  }
  return v2;
}

```

## disassembly

```asm
0x14000f684  mov     eax, [rcx+30h]
0x14000f687  cmp     al, 1
0x14000f689  jnz     short loc_14000F6C4
0x14000f68b  mov     edx, [rcx+248h]
0x14000f691  lea     r8, [rcx+238h]
0x14000f698  shl     edx, 4
0x14000f69b  add     edx, [rcx+260h]
0x14000f6a1  mov     rcx, [r8]
0x14000f6a4  jmp     short loc_14000F6BD
0x14000f6a6  cmp     word ptr [rcx+2Ch], 2
0x14000f6ab  mov     eax, 30h ; '0'
0x14000f6b0  mov     rcx, [rcx]
0x14000f6b3  lea     r9d, [rax+30h]
0x14000f6b7  cmovnz  eax, r9d
0x14000f6bb  add     edx, eax
0x14000f6bd  cmp     rcx, r8
0x14000f6c0  jnz     short loc_14000F6A6
0x14000f6c2  jmp     short loc_14000F6CA
0x14000f6c4  mov     edx, [rcx+260h]
0x14000f6ca  mov     eax, edx
0x14000f6cc  retn
```
