# I_StreamOpenToUnprotect

- ea: `0x180002550`
- end: `0x180002606`
- name: `I_StreamOpenToUnprotect`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002400`
- `0x18001d460`

## callees

- `0x180002550`
- `0x180003a50`
- `0x18000d02c`
- `0x18001f175`

## string_xrefs

- `0x180002595`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`

## pseudocode

```c
__int64 __fastcall I_StreamOpenToUnprotect(int a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v6; // rax
  int v7; // edx
  int v8; // r8d
  _QWORD *v9; // rbx
  unsigned int v10; // ebx

  v6 = (_QWORD *)I_DefaultExtrenalAlloc(209);
  v9 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0xD1u);
    *v9 = 192;
    v9[1] = &NCryptDefaultAllocPara;
    v9[20] = v9 + 24;
    v9[7] = a2;
    *((_DWORD *)v9 + 16) = a1;
    *a3 = v9;
    return 0;
  }
  else
  {
    v10 = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
        94);
  }
  return v10;
}

```

## disassembly

```asm
0x180002550  push    rbx
0x180002552  push    rbp
0x180002553  push    rsi
0x180002554  push    rdi
0x180002555  sub     rsp, 48h
0x180002559  mov     ebp, ecx
0x18000255b  mov     rdi, r8
0x18000255e  mov     ecx, 0D1h
0x180002563  mov     rsi, rdx
0x180002566  call    I_DefaultExtrenalAlloc
0x18000256b  mov     rbx, rax
0x18000256e  test    rax, rax
0x180002571  jnz     short loc_1800025BF
0x180002573  mov     ebx, 8009000Eh
0x180002578  mov     rcx, cs:WPP_GLOBAL_Control
0x18000257f  lea     rax, WPP_GLOBAL_Control
0x180002586  cmp     rcx, rax
0x180002589  jz      short loc_1800025FB
0x18000258b  test    byte ptr [rcx+1Ch], 1
0x18000258f  jz      short loc_1800025FB
0x180002591  mov     rcx, [rcx+10h]
0x180002595  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000259c  mov     [rsp+68h+var_38], 15Eh
0x1800025a4  lea     r9, aStatus; "Status"
0x1800025ab  mov     [rsp+68h+var_40], rax
0x1800025b0  mov     [rsp+68h+var_48], 8009000Eh
0x1800025b8  call    WPP_SF_sDsd
0x1800025bd  jmp     short loc_1800025FB
0x1800025bf  xor     edx, edx; Val
0x1800025c1  mov     r8d, 0D1h; Size
0x1800025c7  mov     rcx, rbx; void *
0x1800025ca  call    memset_0
0x1800025cf  lea     rax, NCryptDefaultAllocPara
0x1800025d6  mov     qword ptr [rbx], 0C0h
0x1800025dd  mov     [rbx+8], rax
0x1800025e1  lea     rax, [rbx+0C0h]
0x1800025e8  mov     [rbx+0A0h], rax
0x1800025ef  mov     [rbx+38h], rsi
0x1800025f3  mov     [rbx+40h], ebp
0x1800025f6  mov     [rdi], rbx
0x1800025f9  xor     ebx, ebx
0x1800025fb  mov     eax, ebx
0x1800025fd  add     rsp, 48h
0x180002601  pop     rdi
0x180002602  pop     rsi
0x180002603  pop     rbp
0x180002604  pop     rbx
0x180002605  retn
```
