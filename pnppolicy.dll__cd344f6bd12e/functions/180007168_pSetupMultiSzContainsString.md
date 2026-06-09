# pSetupMultiSzContainsString

- ea: `0x180007168`
- end: `0x1800071f0`
- name: `pSetupMultiSzContainsString`
- size: `136`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001da8`

## callees

- `0x180007168`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800071be`
- `KERNEL32!CompareStringW` at `0x1800071be`

## pseudocode

```c
__int64 __fastcall pSetupMultiSzContainsString(PCNZWCH lpString1, PCNZWCH lpString2)
{
  unsigned int v3; // ebp
  __int64 v4; // rsi
  const WCHAR *v5; // rdi
  __int64 cchCount2; // rbx

  v3 = 0;
  v4 = -1;
  v5 = lpString1;
  do
    ++v4;
  while ( lpString2[v4] );
  if ( *lpString1 )
  {
    while ( 1 )
    {
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( v5[cchCount2] );
      if ( (_DWORD)cchCount2 == (_DWORD)v4 && CompareStringW(0x7Fu, 1u, v5, cchCount2, lpString2, cchCount2) == 2 )
        break;
      v5 += (int)cchCount2 + 1;
      if ( !*v5 )
        return v3;
    }
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180007168  push    rbx
0x18000716a  push    rbp
0x18000716b  push    rsi
0x18000716c  push    rdi
0x18000716d  push    r14
0x18000716f  push    r15
0x180007171  sub     rsp, 38h
0x180007175  xor     r15d, r15d
0x180007178  mov     r14, rdx
0x18000717b  mov     ebp, r15d
0x18000717e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007182  mov     rdi, rcx
0x180007185  inc     rsi
0x180007188  cmp     [rdx+rsi*2], r15w
0x18000718d  jnz     short loc_180007185
0x18000718f  cmp     [rcx], r15w
0x180007193  jz      short loc_1800071E1
0x180007195  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007199  inc     rbx
0x18000719c  cmp     [rdi+rbx*2], r15w
0x1800071a1  jnz     short loc_180007199
0x1800071a3  cmp     ebx, esi
0x1800071a5  jnz     short loc_1800071C9
0x1800071a7  mov     edx, 1; dwCmpFlags
0x1800071ac  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x1800071b0  mov     r9d, ebx; cchCount1
0x1800071b3  mov     [rsp+68h+lpString2], r14; lpString2
0x1800071b8  mov     r8, rdi; lpString1
0x1800071bb  lea     ecx, [rdx+7Eh]; Locale
0x1800071be  call    cs:__imp_CompareStringW
0x1800071c4  cmp     eax, 2
0x1800071c7  jz      short loc_1800071DC
0x1800071c9  movsxd  rax, ebx
0x1800071cc  lea     rdi, [rdi+rax*2]
0x1800071d0  add     rdi, 2
0x1800071d4  cmp     [rdi], r15w
0x1800071d8  jnz     short loc_180007195
0x1800071da  jmp     short loc_1800071E1
0x1800071dc  mov     ebp, 1
0x1800071e1  mov     eax, ebp
0x1800071e3  add     rsp, 38h
0x1800071e7  pop     r15
0x1800071e9  pop     r14
0x1800071eb  pop     rdi
0x1800071ec  pop     rsi
0x1800071ed  pop     rbp
0x1800071ee  pop     rbx
0x1800071ef  retn
```
