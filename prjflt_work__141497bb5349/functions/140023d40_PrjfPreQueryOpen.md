# PrjfPreQueryOpen

- ea: `0x140023d40`
- end: `0x140023d60`
- name: `PrjfPreQueryOpen`
- size: `32`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140023d40`

## pseudocode

```c
__int64 __fastcall PrjfPreQueryOpen(__int64 a1)
{
  int v1; // ecx

  v1 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
  if ( ((v1 - 68) & 0xFFFFFFFD) != 0 )
    return v1 != 77 ? 6 : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x140023d40  mov     rax, [rcx+10h]
0x140023d44  mov     ecx, [rax+30h]
0x140023d47  lea     eax, [rcx-44h]
0x140023d4a  test    eax, 0FFFFFFFDh
0x140023d4f  jz      short loc_140023D5D
0x140023d51  sub     ecx, 4Dh ; 'M'
0x140023d54  neg     ecx
0x140023d56  sbb     eax, eax
0x140023d58  and     eax, 6
0x140023d5b  retn
0x140023d5d  xor     eax, eax
0x140023d5f  retn
```
