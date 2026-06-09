# PcpWildcardMatch

- ea: `0x140003864`
- end: `0x14000392c`
- name: `PcpWildcardMatch`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002e80`

## callees

- `0x140003864`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1400038ff`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1400038ff`

## pseudocode

```c
char __fastcall PcpWildcardMatch(unsigned __int16 *a1, unsigned __int16 *a2)
{
  const WCHAR *v2; // r14
  const WCHAR *v3; // rbx
  const WCHAR *v4; // rsi
  const WCHAR *v5; // rdi
  const WCHAR *v6; // rbp
  const WCHAR *v7; // r15

  v2 = 0;
  v3 = (const WCHAR *)*((_QWORD *)a1 + 1);
  v4 = 0;
  v5 = (const WCHAR *)*((_QWORD *)a2 + 1);
  v6 = &v3[(unsigned __int64)*a1 >> 1];
  v7 = &v5[(unsigned __int64)*a2 >> 1];
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v5 >= v7 && v3 >= v6 )
        return 1;
      if ( v3 < v6 && *v3 == 42 )
      {
        while ( 1 )
        {
          if ( ++v3 >= v6 )
            return 1;
          if ( *v3 != 42 )
          {
            v2 = v3;
            v4 = v5 + 1;
            break;
          }
        }
      }
      if ( v5 >= v7 || v3 >= v6 || *v3 != 63 && RtlCompareUnicodeStrings(v3, 1u, v5, 1u, 1u) )
        break;
      ++v3;
      ++v5;
    }
    if ( !v2 || v4 >= v7 )
      return 0;
    v5 = v4;
    v3 = v2;
    ++v4;
  }
}

```

## disassembly

```asm
0x140003864  push    rbx
0x140003866  push    rbp
0x140003867  push    rsi
0x140003868  push    rdi
0x140003869  push    r14
0x14000386b  push    r15
0x14000386d  sub     rsp, 38h
0x140003871  movzx   eax, word ptr [rcx]
0x140003874  xor     r14d, r14d
0x140003877  mov     rbx, [rcx+8]
0x14000387b  xor     esi, esi
0x14000387d  mov     rdi, [rdx+8]
0x140003881  shr     rax, 1
0x140003884  lea     rbp, [rbx+rax*2]
0x140003888  movzx   eax, word ptr [rdx]
0x14000388b  shr     rax, 1
0x14000388e  lea     r15, [rdi+rax*2]
0x140003892  cmp     rdi, r15
0x140003895  jnb     short loc_1400038D5
0x140003897  cmp     rbx, rbp
0x14000389a  jnb     short loc_1400038BB
0x14000389c  cmp     word ptr [rbx], 2Ah ; '*'
0x1400038a0  jnz     short loc_1400038BB
0x1400038a2  add     rbx, 2
0x1400038a6  cmp     rbx, rbp
0x1400038a9  jb      short loc_1400038DC
0x1400038ab  mov     al, 1
0x1400038ad  add     rsp, 38h
0x1400038b1  pop     r15
0x1400038b3  pop     r14
0x1400038b5  pop     rdi
0x1400038b6  pop     rsi
0x1400038b7  pop     rbp
0x1400038b8  pop     rbx
0x1400038b9  retn
0x1400038bb  cmp     rdi, r15
0x1400038be  jnb     short loc_14000390F
0x1400038c0  cmp     rbx, rbp
0x1400038c3  jnb     short loc_14000390F
0x1400038c5  cmp     word ptr [rbx], 3Fh ; '?'
0x1400038c9  jnz     short loc_1400038EB
0x1400038cb  add     rbx, 2
0x1400038cf  add     rdi, 2
0x1400038d3  jmp     short loc_140003892
0x1400038d5  cmp     rbx, rbp
0x1400038d8  jnb     short loc_1400038AB
0x1400038da  jmp     short loc_140003897
0x1400038dc  cmp     word ptr [rbx], 2Ah ; '*'
0x1400038e0  jz      short loc_1400038A2
0x1400038e2  mov     r14, rbx
0x1400038e5  lea     rsi, [rdi+2]
0x1400038e9  jmp     short loc_1400038BB
0x1400038eb  mov     r9d, 1; String2Length
0x1400038f1  mov     [rsp+68h+CaseInSensitive], 1; CaseInSensitive
0x1400038f6  mov     edx, r9d; String1Length
0x1400038f9  mov     r8, rdi; String2
0x1400038fc  mov     rcx, rbx; String1
0x1400038ff  call    cs:__imp_RtlCompareUnicodeStrings
0x140003906  nop     dword ptr [rax+rax+00h]
0x14000390b  test    eax, eax
0x14000390d  jz      short loc_1400038CB
0x14000390f  test    r14, r14
0x140003912  jz      short loc_140003928
0x140003914  cmp     rsi, r15
0x140003917  jnb     short loc_140003928
0x140003919  mov     rdi, rsi
0x14000391c  mov     rbx, r14
0x14000391f  add     rsi, 2
0x140003923  jmp     loc_140003892
0x140003928  xor     al, al
0x14000392a  jmp     short loc_1400038AD
```
