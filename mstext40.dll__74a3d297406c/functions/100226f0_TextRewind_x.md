# TextRewind(x)

- ea: `0x100226f0`
- end: `0x1002273f`
- name: `_TextRewind@4`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1001f830`

## callees

- `0x100226f0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x10022701`
- `KERNEL32!SetFilePointer` at `0x10022701`

## pseudocode

```c
int __stdcall TextRewind(int a1)
{
  DWORD v1; // eax
  int result; // eax

  v1 = SetFilePointer(*(HANDLE *)(a1 + 528), 0, 0, 0);
  if ( v1 == -1 )
    return -1022;
  *(_DWORD *)(a1 + 8848) = v1;
  result = 0;
  *(_DWORD *)(a1 + 8852) = 0;
  *(_DWORD *)(a1 + 8760) = 0;
  *(_DWORD *)(a1 + 11956) = 0;
  return result;
}

```

## disassembly

```asm
0x100226f0  push    esi
0x100226f1  mov     esi, [esp+4+arg_0]
0x100226f5  push    0; dwMoveMethod
0x100226f7  push    0; lpDistanceToMoveHigh
0x100226f9  push    0; lDistanceToMove
0x100226fb  push    dword ptr [esi+210h]; hFile
0x10022701  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10022707  cmp     eax, 0FFFFFFFFh
0x1002270a  jnz     short loc_10022715
0x1002270c  mov     eax, 0FFFFFC02h
0x10022711  pop     esi
0x10022712  retn    4
0x10022715  mov     [esi+2290h], eax
0x1002271b  xor     eax, eax
0x1002271d  mov     dword ptr [esi+2294h], 0
0x10022727  mov     dword ptr [esi+2238h], 0
0x10022731  mov     dword ptr [esi+2EB4h], 0
0x1002273b  pop     esi
0x1002273c  retn    4
```
