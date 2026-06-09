# GetCallbackPrivilegeFromRequest

- ea: `0x180023cec`
- end: `0x180023d83`
- name: `GetCallbackPrivilegeFromRequest`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002369c`

## callees

- `0x180023cec`

## pseudocode

```c
__int64 __fastcall GetCallbackPrivilegeFromRequest(unsigned __int8 *a1, _DWORD *a2)
{
  _BYTE *v2; // r10
  int v3; // r9d
  __int64 v4; // rax

  v2 = a1 + 4;
  v3 = (a1[2] << 8) + a1[3] - 4;
  *a2 = 0;
  while ( v3 > 0 )
  {
    if ( v2[1] < 2u || (unsigned __int8)v2[1] > v3 || (unsigned int)v3 < 2 )
      return 722;
    switch ( *v2 )
    {
      case 1:
        *a2 |= 1u;
        break;
      case 2:
        *a2 |= 4u;
        break;
      case 3:
        *a2 |= 2u;
        break;
    }
    v4 = (unsigned __int8)v2[1];
    v3 -= v4;
    v2 += v4;
  }
  if ( (*(_BYTE *)a2 & 4) != 0 )
  {
    *a2 = 4;
    return 0;
  }
  if ( (*(_BYTE *)a2 & 2) != 0 )
  {
    *a2 = 2;
    return 0;
  }
  if ( (*(_BYTE *)a2 & 1) != 0 )
  {
    *a2 = 1;
    return 0;
  }
  return 722;
}

```

## disassembly

```asm
0x180023cec  movzx   r8d, byte ptr [rcx+2]
0x180023cf1  lea     r10, [rcx+4]
0x180023cf5  movzx   r9d, byte ptr [rcx+3]
0x180023cfa  shl     r8d, 8
0x180023cfe  add     r9d, 0FFFFFFFCh
0x180023d02  add     r9d, r8d
0x180023d05  mov     dword ptr [rdx], 0
0x180023d0b  mov     r8d, 2
0x180023d11  test    r9d, r9d
0x180023d14  jle     short loc_180023D58
0x180023d16  cmp     [r10+1], r8b
0x180023d1a  jb      short loc_180023D7D
0x180023d1c  movzx   eax, byte ptr [r10+1]
0x180023d21  cmp     eax, r9d
0x180023d24  jg      short loc_180023D7D
0x180023d26  cmp     r9d, r8d
0x180023d29  jb      short loc_180023D7D
0x180023d2b  movzx   ecx, byte ptr [r10]
0x180023d2f  sub     ecx, 1
0x180023d32  jz      short loc_180023D48
0x180023d34  sub     ecx, 1
0x180023d37  jz      short loc_180023D43
0x180023d39  cmp     ecx, 1
0x180023d3c  jnz     short loc_180023D4B
0x180023d3e  or      [rdx], r8d
0x180023d41  jmp     short loc_180023D4B
0x180023d43  or      dword ptr [rdx], 4
0x180023d46  jmp     short loc_180023D4B
0x180023d48  or      dword ptr [rdx], 1
0x180023d4b  movzx   eax, byte ptr [r10+1]
0x180023d50  sub     r9d, eax
0x180023d53  add     r10, rax
0x180023d56  jmp     short loc_180023D11
0x180023d58  test    byte ptr [rdx], 4
0x180023d5b  jz      short loc_180023D65
0x180023d5d  mov     dword ptr [rdx], 4
0x180023d63  jmp     short loc_180023D7A
0x180023d65  test    [rdx], r8b
0x180023d68  jz      short loc_180023D6F
0x180023d6a  mov     [rdx], r8d
0x180023d6d  jmp     short loc_180023D7A
0x180023d6f  test    byte ptr [rdx], 1
0x180023d72  jz      short loc_180023D7D
0x180023d74  mov     dword ptr [rdx], 1
0x180023d7a  xor     eax, eax
0x180023d7c  retn
0x180023d7d  mov     eax, 2D2h
0x180023d82  retn
```
