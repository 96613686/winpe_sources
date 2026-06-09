# GetCallbackPrivilegeFromRequest

- ea: `0x180024a6c`
- end: `0x180024b04`
- name: `GetCallbackPrivilegeFromRequest`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800243c8`

## callees

- `0x180024a6c`

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
0x180024a6c  movzx   r8d, byte ptr [rcx+2]
0x180024a71  lea     r10, [rcx+4]
0x180024a75  movzx   r9d, byte ptr [rcx+3]
0x180024a7a  shl     r8d, 8
0x180024a7e  add     r9d, 0FFFFFFFCh
0x180024a82  add     r9d, r8d
0x180024a85  mov     dword ptr [rdx], 0
0x180024a8b  mov     r8d, 2
0x180024a91  test    r9d, r9d
0x180024a94  jle     short loc_180024AD8
0x180024a96  cmp     [r10+1], r8b
0x180024a9a  jb      short loc_180024AFE
0x180024a9c  movzx   eax, byte ptr [r10+1]
0x180024aa1  cmp     eax, r9d
0x180024aa4  jg      short loc_180024AFE
0x180024aa6  cmp     r9d, r8d
0x180024aa9  jb      short loc_180024AFE
0x180024aab  movzx   ecx, byte ptr [r10]
0x180024aaf  sub     ecx, 1
0x180024ab2  jz      short loc_180024AC8
0x180024ab4  sub     ecx, 1
0x180024ab7  jz      short loc_180024AC3
0x180024ab9  cmp     ecx, 1
0x180024abc  jnz     short loc_180024ACB
0x180024abe  or      [rdx], r8d
0x180024ac1  jmp     short loc_180024ACB
0x180024ac3  or      dword ptr [rdx], 4
0x180024ac6  jmp     short loc_180024ACB
0x180024ac8  or      dword ptr [rdx], 1
0x180024acb  movzx   eax, byte ptr [r10+1]
0x180024ad0  sub     r9d, eax
0x180024ad3  add     r10, rax
0x180024ad6  jmp     short loc_180024A91
0x180024ad8  test    byte ptr [rdx], 4
0x180024adb  jz      short loc_180024AE5
0x180024add  mov     dword ptr [rdx], 4
0x180024ae3  jmp     short loc_180024AFA
0x180024ae5  test    [rdx], r8b
0x180024ae8  jz      short loc_180024AEF
0x180024aea  mov     [rdx], r8d
0x180024aed  jmp     short loc_180024AFA
0x180024aef  test    byte ptr [rdx], 1
0x180024af2  jz      short loc_180024AFE
0x180024af4  mov     dword ptr [rdx], 1
0x180024afa  xor     eax, eax
0x180024afc  retn
0x180024afe  mov     eax, 2D2h
0x180024b03  retn
```
