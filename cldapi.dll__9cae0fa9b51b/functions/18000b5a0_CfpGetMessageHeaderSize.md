# CfpGetMessageHeaderSize

- ea: `0x18000b5a0`
- end: `0x18000b5ce`
- name: `CfpGetMessageHeaderSize`
- size: `46`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a6b4`
- `0x18000a81c`
- `0x18000a9a0`
- `0x18000ac50`
- `0x18000adb0`
- `0x18000af58`
- `0x18000b0d8`
- `0x18000b248`

## callees

- `0x18000b5a0`

## pseudocode

```c
__int64 __fastcall CfpGetMessageHeaderSize(__int64 a1)
{
  __int64 result; // rax
  _DWORD *v2; // rdx

  result = 232;
  if ( *(_DWORD *)a1 >= 0x20u && *(_QWORD *)(a1 + 24) )
    result = 362;
  if ( *(_DWORD *)a1 >= 0x28u )
  {
    v2 = *(_DWORD **)(a1 + 32);
    if ( v2 )
      return *v2 + (((_DWORD)result + 3) & 0xFFFFFFFC);
  }
  return result;
}

```

## disassembly

```asm
0x18000b5a0  cmp     dword ptr [rcx], 20h ; ' '
0x18000b5a3  mov     eax, 0E8h
0x18000b5a8  jb      short loc_18000B5B7
0x18000b5aa  cmp     qword ptr [rcx+18h], 0
0x18000b5af  mov     edx, 16Ah
0x18000b5b4  cmovnz  eax, edx
0x18000b5b7  cmp     dword ptr [rcx], 28h ; '('
0x18000b5ba  jb      short locret_18000B5CD
0x18000b5bc  mov     rdx, [rcx+20h]
0x18000b5c0  test    rdx, rdx
0x18000b5c3  jz      short locret_18000B5CD
0x18000b5c5  add     eax, 3
0x18000b5c8  and     eax, 0FFFFFFFCh
0x18000b5cb  add     eax, [rdx]
0x18000b5cd  retn
```
