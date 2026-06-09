# ConfigAddStrParameter(x,x,x,x,x)

- ea: `0x10009f50`
- end: `0x10009f9b`
- name: `_ConfigAddStrParameter@20`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10015240`

## callees

- `0x10009f50`
- `0x1000b070`

## pseudocode

```c
int __stdcall ConfigAddStrParameter(int a1, int a2, int a3, int a4, int a5)
{
  _DWORD *v5; // eax
  _DWORD *v6; // edx
  int result; // eax

  v5 = MemAllocate(32);
  v6 = v5;
  if ( !v5 )
    return -1;
  *((_BYTE *)v5 + 4) = 0;
  *((_BYTE *)v5 + 5) = (*(_BYTE *)(a1 + 4))++;
  v5[2] = a2;
  v5[4] = a4;
  v5[3] = a3;
  v5[5] = a5;
  *v5 = *(_DWORD *)a1;
  result = 0;
  *(_DWORD *)a1 = v6;
  return result;
}

```

## disassembly

```asm
0x10009f50  push    20h ; ' '; Size
0x10009f52  call    _MemAllocate@4; MemAllocate(x)
0x10009f57  mov     edx, eax
0x10009f59  test    edx, edx
0x10009f5b  jnz     short loc_10009F63
0x10009f5d  or      eax, 0FFFFFFFFh
0x10009f60  retn    14h
0x10009f63  mov     ecx, [esp+arg_0]
0x10009f67  mov     byte ptr [edx+4], 0
0x10009f6b  mov     al, [ecx+4]
0x10009f6e  mov     [edx+5], al
0x10009f71  inc     byte ptr [ecx+4]
0x10009f74  mov     eax, [esp+arg_4]
0x10009f78  mov     [edx+8], eax
0x10009f7b  mov     eax, [esp+arg_C]
0x10009f7f  mov     [edx+10h], eax
0x10009f82  mov     eax, [esp+arg_8]
0x10009f86  mov     [edx+0Ch], eax
0x10009f89  mov     eax, [esp+arg_10]
0x10009f8d  mov     [edx+14h], eax
0x10009f90  mov     eax, [ecx]
0x10009f92  mov     [edx], eax
0x10009f94  xor     eax, eax
0x10009f96  mov     [ecx], edx
0x10009f98  retn    14h
```
