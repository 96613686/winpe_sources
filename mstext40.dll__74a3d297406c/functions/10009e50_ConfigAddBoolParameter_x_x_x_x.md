# ConfigAddBoolParameter(x,x,x,x)

- ea: `0x10009e50`
- end: `0x10009e94`
- name: `_ConfigAddBoolParameter@16`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10015240`

## callees

- `0x10009e50`
- `0x1000b070`

## pseudocode

```c
int __stdcall ConfigAddBoolParameter(int a1, int a2, int a3, int a4)
{
  _DWORD *v4; // eax
  _DWORD *v5; // edx
  int result; // eax

  v4 = MemAllocate(32);
  v5 = v4;
  if ( !v4 )
    return -1;
  *((_BYTE *)v4 + 4) = 2;
  *((_BYTE *)v4 + 5) = (*(_BYTE *)(a1 + 4))++;
  v4[2] = a2;
  v4[3] = a3;
  v4[4] = a4;
  *v4 = *(_DWORD *)a1;
  result = 0;
  *(_DWORD *)a1 = v5;
  return result;
}

```

## disassembly

```asm
0x10009e50  push    20h ; ' '; Size
0x10009e52  call    _MemAllocate@4; MemAllocate(x)
0x10009e57  mov     edx, eax
0x10009e59  test    edx, edx
0x10009e5b  jnz     short loc_10009E63
0x10009e5d  or      eax, 0FFFFFFFFh
0x10009e60  retn    10h
0x10009e63  mov     ecx, [esp+arg_0]
0x10009e67  mov     byte ptr [edx+4], 2
0x10009e6b  mov     al, [ecx+4]
0x10009e6e  mov     [edx+5], al
0x10009e71  inc     byte ptr [ecx+4]
0x10009e74  mov     eax, [esp+arg_4]
0x10009e78  mov     [edx+8], eax
0x10009e7b  mov     eax, [esp+arg_8]
0x10009e7f  mov     [edx+0Ch], eax
0x10009e82  mov     eax, [esp+arg_C]
0x10009e86  mov     [edx+10h], eax
0x10009e89  mov     eax, [ecx]
0x10009e8b  mov     [edx], eax
0x10009e8d  xor     eax, eax
0x10009e8f  mov     [ecx], edx
0x10009e91  retn    10h
```
