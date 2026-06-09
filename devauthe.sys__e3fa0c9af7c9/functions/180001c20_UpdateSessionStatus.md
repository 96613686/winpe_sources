# UpdateSessionStatus

- ea: `0x180001c20`
- end: `0x180001cea`
- name: `UpdateSessionStatus`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800015f0`
- `0x1800018f0`
- `0x180001980`

## callees

- `0x180001c20`

## pseudocode

```c
char __fastcall UpdateSessionStatus(__int64 a1, char a2)
{
  _DWORD *v2; // r8
  int v3; // eax
  int v4; // eax

  v2 = (_DWORD *)(a1 + 24);
  switch ( *(_BYTE *)(a1 + 32) )
  {
    case 0:
      if ( a1 == -24 )
        break;
      v4 = 0;
LABEL_14:
      *v2 = v4;
      break;
    case 1:
      v4 = *(_DWORD *)(a1 + 1256);
      goto LABEL_14;
    case 2:
      if ( a1 == -40 )
      {
        v3 = 0;
      }
      else
      {
        if ( a1 != -24 )
          *v2 = 0;
        *(_WORD *)v2 = *(unsigned __int8 *)(a1 + 325);
        *(_WORD *)(a1 + 26) = *(unsigned __int8 *)(a1 + 326);
        v3 = 1;
      }
      if ( !v3 )
      {
LABEL_24:
        *(_DWORD *)(a1 + 16) = 7;
        return v3;
      }
      break;
  }
  if ( !*(_BYTE *)(a1 + 32) || *(_BYTE *)(a1 + 32) == 1 )
  {
    LOBYTE(v3) = *(_BYTE *)(a1 + 40);
  }
  else if ( *(_BYTE *)(a1 + 32) != 2 || a1 == -40 )
  {
    LOBYTE(v3) = 3;
  }
  else
  {
    LOBYTE(v3) = *(_BYTE *)(a1 + 40);
  }
  if ( (unsigned __int8)v3 != 1 )
  {
    if ( (unsigned __int8)v3 == 2 )
    {
      *(_DWORD *)(a1 + 16) = 6;
      return v3;
    }
    goto LABEL_24;
  }
  if ( a2 == 1 )
  {
    *(_DWORD *)(a1 + 16) = 3;
  }
  else if ( a2 == 2 )
  {
    *(_DWORD *)(a1 + 16) = 4;
  }
  return v3;
}

```

## disassembly

```asm
0x180001c20  movzx   r9d, byte ptr [rcx+20h]
0x180001c25  lea     r8, [rcx+18h]
0x180001c29  mov     r10b, dl
0x180001c2c  test    r9d, r9d
0x180001c2f  jz      short loc_180001C7E
0x180001c31  sub     r9d, 1
0x180001c35  jz      short loc_180001C76
0x180001c37  cmp     r9d, 1
0x180001c3b  jnz     short loc_180001C88
0x180001c3d  lea     rdx, [rcx+28h]
0x180001c41  test    rdx, rdx
0x180001c44  jnz     short loc_180001C4A
0x180001c46  xor     eax, eax
0x180001c48  jmp     short loc_180001C70
0x180001c4a  test    r8, r8
0x180001c4d  jz      short loc_180001C54
0x180001c4f  xor     eax, eax
0x180001c51  mov     [r8], eax
0x180001c54  movzx   eax, byte ptr [rdx+11Dh]
0x180001c5b  mov     [r8], ax
0x180001c5f  movzx   eax, byte ptr [rdx+11Eh]
0x180001c66  mov     [r8+2], ax
0x180001c6b  mov     eax, 1
0x180001c70  test    eax, eax
0x180001c72  jz      short loc_180001CBB
0x180001c74  jmp     short loc_180001C88
0x180001c76  mov     eax, [rcx+4E8h]
0x180001c7c  jmp     short loc_180001C85
0x180001c7e  test    r8, r8
0x180001c81  jz      short loc_180001C88
0x180001c83  xor     eax, eax
0x180001c85  mov     [r8], eax
0x180001c88  movzx   edx, byte ptr [rcx+20h]
0x180001c8c  test    edx, edx
0x180001c8e  jz      short loc_180001CAB
0x180001c90  sub     edx, 1
0x180001c93  jz      short loc_180001CAB
0x180001c95  cmp     edx, 1
0x180001c98  jz      short loc_180001C9E
0x180001c9a  mov     al, 3
0x180001c9c  jmp     short loc_180001CAE
0x180001c9e  lea     rax, [rcx+28h]
0x180001ca2  test    rax, rax
0x180001ca5  jz      short loc_180001C9A
0x180001ca7  mov     al, [rax]
0x180001ca9  jmp     short loc_180001CAE
0x180001cab  mov     al, [rcx+28h]
0x180001cae  movzx   edx, al
0x180001cb1  sub     edx, 1
0x180001cb4  jz      short loc_180001CCD
0x180001cb6  sub     edx, 1
0x180001cb9  jz      short loc_180001CC4
0x180001cbb  mov     dword ptr [rcx+10h], 7
0x180001cc2  retn
0x180001cc4  mov     dword ptr [rcx+10h], 6
0x180001ccb  retn
0x180001ccd  cmp     r10b, 1
0x180001cd1  jnz     short loc_180001CDC
0x180001cd3  mov     dword ptr [rcx+10h], 3
0x180001cda  retn
0x180001cdc  cmp     r10b, 2
0x180001ce0  jnz     short locret_180001CE9
0x180001ce2  mov     dword ptr [rcx+10h], 4
0x180001ce9  retn
```
