# ISAMDBAddTask(x)

- ea: `0x10013f40`
- end: `0x10013f8a`
- name: `_ISAMDBAddTask@4`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x100148d0`

## callees

- `0x1000b070`
- `0x10013f40`

## pseudocode

```c
_DWORD *__stdcall ISAMDBAddTask(int a1)
{
  _DWORD *result; // eax
  int v2; // ecx
  int v3; // eax

  result = MemAllocate(36);
  v2 = (int)result;
  if ( result )
  {
    v3 = dword_10040FBC;
    *(_OWORD *)v2 = 0;
    dword_10040FBC = v2;
    *(_OWORD *)(v2 + 16) = 0;
    *(_DWORD *)(v2 + 32) = 0;
    *(_DWORD *)v2 = v3;
    *(_DWORD *)(v2 + 16) = a1;
    result = (_DWORD *)v2;
    *(_DWORD *)(v2 + 20) = 1;
    *(_DWORD *)(v2 + 24) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x10013f40  push    24h ; '$'; Size
0x10013f42  call    _MemAllocate@4; MemAllocate(x)
0x10013f47  mov     ecx, eax
0x10013f49  test    ecx, ecx
0x10013f4b  jnz     short loc_10013F50
0x10013f4d  retn    4
0x10013f50  mov     eax, dword_10040FBC
0x10013f55  xorps   xmm0, xmm0
0x10013f58  movdqu  xmmword ptr [ecx], xmm0
0x10013f5c  mov     dword_10040FBC, ecx
0x10013f62  movdqu  xmmword ptr [ecx+10h], xmm0
0x10013f67  mov     dword ptr [ecx+20h], 0
0x10013f6e  mov     [ecx], eax
0x10013f70  mov     eax, [esp+arg_0]
0x10013f74  mov     [ecx+10h], eax
0x10013f77  mov     eax, ecx
0x10013f79  mov     dword ptr [ecx+14h], 1
0x10013f80  mov     dword ptr [ecx+18h], 1
0x10013f87  retn    4
```
