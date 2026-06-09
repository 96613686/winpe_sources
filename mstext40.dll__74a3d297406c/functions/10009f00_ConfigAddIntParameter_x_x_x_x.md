# ConfigAddIntParameter(x,x,x,x)

- ea: `0x10009f00`
- end: `0x10009f44`
- name: `_ConfigAddIntParameter@16`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10015240`

## callees

- `0x10009f00`
- `0x1000b070`

## pseudocode

```c
int __stdcall ConfigAddIntParameter(int a1, int a2, int a3, int a4)
{
  _DWORD *v4; // eax
  _DWORD *v5; // edx
  int result; // eax

  v4 = MemAllocate(32);
  v5 = v4;
  if ( !v4 )
    return -1;
  *((_BYTE *)v4 + 4) = 1;
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
0x10009f00  push    20h ; ' '; Size
0x10009f02  call    _MemAllocate@4; MemAllocate(x)
0x10009f07  mov     edx, eax
0x10009f09  test    edx, edx
0x10009f0b  jnz     short loc_10009F13
0x10009f0d  or      eax, 0FFFFFFFFh
0x10009f10  retn    10h
0x10009f13  mov     ecx, [esp+arg_0]
0x10009f17  mov     byte ptr [edx+4], 1
0x10009f1b  mov     al, [ecx+4]
0x10009f1e  mov     [edx+5], al
0x10009f21  inc     byte ptr [ecx+4]
0x10009f24  mov     eax, [esp+arg_4]
0x10009f28  mov     [edx+8], eax
0x10009f2b  mov     eax, [esp+arg_8]
0x10009f2f  mov     [edx+0Ch], eax
0x10009f32  mov     eax, [esp+arg_C]
0x10009f36  mov     [edx+10h], eax
0x10009f39  mov     eax, [ecx]
0x10009f3b  mov     [edx], eax
0x10009f3d  xor     eax, eax
0x10009f3f  mov     [ecx], edx
0x10009f41  retn    10h
```
