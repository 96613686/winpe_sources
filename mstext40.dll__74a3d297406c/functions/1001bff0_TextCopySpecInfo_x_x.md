# TextCopySpecInfo(x,x)

- ea: `0x1001bff0`
- end: `0x1001c05e`
- name: `_TextCopySpecInfo@8`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1000f0e0`
- `0x10010020`

## callees

- `0x1000b070`
- `0x1001bff0`

## pseudocode

```c
_DWORD *__stdcall TextCopySpecInfo(_DWORD *a1, _DWORD *a2)
{
  _DWORD *result; // eax
  _DWORD *v3; // ebp
  _DWORD *i; // ebx

  result = a2;
  qmemcpy(a1, a2, 0x348u);
  a1[2] = 0;
  v3 = 0;
  for ( i = (_DWORD *)a2[2]; i; v3 = result )
  {
    result = MemAllocate(248);
    if ( !result )
      break;
    qmemcpy(result, i, 0xF8u);
    *result = 0;
    if ( v3 )
      *v3 = result;
    else
      a1[2] = result;
    i = (_DWORD *)*i;
  }
  return result;
}

```

## disassembly

```asm
0x1001bff0  mov     edx, [esp+arg_0]
0x1001bff4  mov     ecx, 0D2h
0x1001bff9  mov     eax, [esp+arg_4]
0x1001bffd  push    ebx
0x1001bffe  push    ebp
0x1001bfff  push    esi
0x1001c000  push    edi
0x1001c001  mov     esi, eax
0x1001c003  mov     edi, edx
0x1001c005  rep movsd
0x1001c007  mov     dword ptr [edx+8], 0
0x1001c00e  xor     ebp, ebp
0x1001c010  mov     ebx, [eax+8]
0x1001c013  test    ebx, ebx
0x1001c015  jz      short loc_1001C057
0x1001c017  jmp     short loc_1001C020
0x1001c020  push    0F8h; Size
0x1001c025  call    _MemAllocate@4; MemAllocate(x)
0x1001c02a  test    eax, eax
0x1001c02c  jz      short loc_1001C057
0x1001c02e  mov     ecx, 3Eh ; '>'
0x1001c033  mov     esi, ebx
0x1001c035  mov     edi, eax
0x1001c037  rep movsd
0x1001c039  mov     dword ptr [eax], 0
0x1001c03f  test    ebp, ebp
0x1001c041  jnz     short loc_1001C04C
0x1001c043  mov     ecx, [esp+10h+arg_0]
0x1001c047  mov     [ecx+8], eax
0x1001c04a  jmp     short loc_1001C04F
0x1001c04c  mov     [ebp+0], eax
0x1001c04f  mov     ebx, [ebx]
0x1001c051  mov     ebp, eax
0x1001c053  test    ebx, ebx
0x1001c055  jnz     short loc_1001C020
0x1001c057  pop     edi
0x1001c058  pop     esi
0x1001c059  pop     ebp
0x1001c05a  pop     ebx
0x1001c05b  retn    8
```
