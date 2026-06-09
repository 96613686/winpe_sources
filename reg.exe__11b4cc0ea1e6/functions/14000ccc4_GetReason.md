# GetReason

- ea: `0x14000ccc4`
- end: `0x14000cd07`
- name: `GetReason`
- size: `67`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a58`
- `0x14000612c`
- `0x14000dbe8`
- `0x14000dc24`

## callees

- `0x14000ccc4`

## pseudocode

```c
__int64 *GetReason()
{
  __int64 v0; // rax

  if ( !qword_140014218 || *(_DWORD *)qword_140014218 != 9 )
    return &cwszNullString;
  if ( qword_140014218 )
  {
    if ( *(_DWORD *)qword_140014218 == 9 )
    {
      if ( *(_DWORD *)(qword_140014218 + 4) )
      {
        v0 = *(_QWORD *)(qword_140014218 + 8);
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
0x14000ccc4  mov     rax, cs:qword_140014218
0x14000cccb  test    rax, rax
0x14000ccce  jz      short loc_14000CCFF
0x14000ccd0  cmp     dword ptr [rax], 9
0x14000ccd3  jnz     short loc_14000CCFF
0x14000ccd5  test    rax, rax
0x14000ccd8  jz      short loc_14000CCFC
0x14000ccda  cmp     dword ptr [rax], 9
0x14000ccdd  jnz     short loc_14000CCFC
0x14000ccdf  cmp     dword ptr [rax+4], 0
0x14000cce3  jbe     short loc_14000CCFC
0x14000cce5  mov     rax, [rax+8]
0x14000cce9  test    rax, rax
0x14000ccec  jz      short loc_14000CCFC
0x14000ccee  cmp     dword ptr [rax+4], 20000h
0x14000ccf5  jnz     short loc_14000CCFC
0x14000ccf7  mov     rax, [rax+10h]
0x14000ccfb  retn
0x14000ccfc  xor     eax, eax
0x14000ccfe  retn
0x14000ccff  lea     rax, cwszNullString
0x14000cd06  retn
```
