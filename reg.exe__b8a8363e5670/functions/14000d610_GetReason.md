# GetReason

- ea: `0x14000d610`
- end: `0x14000d655`
- name: `GetReason`
- size: `69`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c24`
- `0x1400064b0`
- `0x14000e75c`
- `0x14000e798`

## callees

- `0x14000d610`

## pseudocode

```c
__int64 *GetReason()
{
  __int64 v0; // rax

  if ( !qword_140015218 || *(_DWORD *)qword_140015218 != 9 )
    return &cwszNullString;
  if ( qword_140015218 )
  {
    if ( *(_DWORD *)qword_140015218 == 9 )
    {
      if ( *(_DWORD *)(qword_140015218 + 4) )
      {
        v0 = *(_QWORD *)(qword_140015218 + 8);
        if ( v0 )
        {
          if ( *(_DWORD *)(v0 + 4) == 0x20000 )
            return *(__int64 **)(v0 + 16);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d610  mov     rax, cs:qword_140015218
0x14000d617  test    rax, rax
0x14000d61a  jz      short loc_14000D64D
0x14000d61c  cmp     dword ptr [rax], 9
0x14000d61f  jnz     short loc_14000D64D
0x14000d621  test    rax, rax
0x14000d624  jz      short loc_14000D649
0x14000d626  cmp     dword ptr [rax], 9
0x14000d629  jnz     short loc_14000D649
0x14000d62b  cmp     dword ptr [rax+4], 0
0x14000d62f  jbe     short loc_14000D649
0x14000d631  mov     rax, [rax+8]
0x14000d635  test    rax, rax
0x14000d638  jz      short loc_14000D649
0x14000d63a  cmp     dword ptr [rax+4], 20000h
0x14000d641  jnz     short loc_14000D649
0x14000d643  mov     rax, [rax+10h]
0x14000d647  retn
0x14000d649  xor     eax, eax
0x14000d64b  retn
0x14000d64d  lea     rax, cwszNullString
0x14000d654  retn
```
