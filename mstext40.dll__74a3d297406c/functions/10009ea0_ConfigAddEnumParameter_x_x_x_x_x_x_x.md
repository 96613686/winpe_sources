# ConfigAddEnumParameter(x,x,x,x,x,x,x)

- ea: `0x10009ea0`
- end: `0x10009ef9`
- name: `_ConfigAddEnumParameter@28`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10015240`

## callees

- `0x10009ea0`
- `0x1000b070`

## pseudocode

```c
int __stdcall ConfigAddEnumParameter(int a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  _DWORD *v7; // eax
  _DWORD *v8; // edx
  int result; // eax

  v7 = MemAllocate(32);
  v8 = v7;
  if ( !v7 )
    return -1;
  *((_BYTE *)v7 + 4) = 3;
  *((_BYTE *)v7 + 5) = (*(_BYTE *)(a1 + 4))++;
  v7[2] = a2;
  v7[3] = a3;
  v7[4] = a7;
  v7[5] = a4;
  v7[6] = a5;
  v7[7] = a6;
  *v7 = *(_DWORD *)a1;
  result = 0;
  *(_DWORD *)a1 = v8;
  return result;
}

```

## disassembly

```asm
0x10009ea0  push    20h ; ' '; Size
0x10009ea2  call    _MemAllocate@4; MemAllocate(x)
0x10009ea7  mov     edx, eax
0x10009ea9  test    edx, edx
0x10009eab  jnz     short loc_10009EB3
0x10009ead  or      eax, 0FFFFFFFFh
0x10009eb0  retn    1Ch
0x10009eb3  mov     ecx, [esp+arg_0]
0x10009eb7  mov     byte ptr [edx+4], 3
0x10009ebb  mov     al, [ecx+4]
0x10009ebe  mov     [edx+5], al
0x10009ec1  inc     byte ptr [ecx+4]
0x10009ec4  mov     eax, [esp+arg_4]
0x10009ec8  mov     [edx+8], eax
0x10009ecb  mov     eax, [esp+arg_8]
0x10009ecf  mov     [edx+0Ch], eax
0x10009ed2  mov     eax, [esp+arg_18]
0x10009ed6  mov     [edx+10h], eax
0x10009ed9  mov     eax, [esp+arg_C]
0x10009edd  mov     [edx+14h], eax
0x10009ee0  mov     eax, [esp+arg_10]
0x10009ee4  mov     [edx+18h], eax
0x10009ee7  mov     eax, [esp+arg_14]
0x10009eeb  mov     [edx+1Ch], eax
0x10009eee  mov     eax, [ecx]
0x10009ef0  mov     [edx], eax
0x10009ef2  xor     eax, eax
0x10009ef4  mov     [ecx], edx
0x10009ef6  retn    1Ch
```
