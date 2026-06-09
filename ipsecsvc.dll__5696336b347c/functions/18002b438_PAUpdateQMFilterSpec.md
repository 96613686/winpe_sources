# PAUpdateQMFilterSpec

- ea: `0x18002b438`
- end: `0x18002b4e7`
- name: `PAUpdateQMFilterSpec`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18002b4f0`

## callees

- `0x1800295cc`
- `0x180029f7c`
- `0x18002a6f8`
- `0x18002a868`
- `0x18002b438`
- `0x18002fa6c`
- `0x180030278`

## pseudocode

```c
__int64 __fastcall PAUpdateQMFilterSpec(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int128 v7; // xmm1
  __int64 TxFilterState; // rcx
  __int64 result; // rax
  __int64 TnFilterState; // rcx
  __int128 v12; // [rsp+20h] [rbp-48h] BYREF
  _OWORD v13[3]; // [rsp+30h] [rbp-38h] BYREF

  v7 = *(_OWORD *)(a3 + 24);
  if ( (*(_BYTE *)(a1 + 76) & 3) != 0 )
  {
    v13[0] = *(_OWORD *)(a1 + 8);
    v12 = v7;
    TnFilterState = FindTnFilterState(&v12, v13);
    result = 0;
    if ( TnFilterState )
    {
      if ( *(_QWORD *)(TnFilterState + 48) )
        return result;
      PADeleteTnFilterState(TnFilterState);
    }
    return PAAddTnFilterSpec(a1, a2, a3, a4);
  }
  else
  {
    v12 = *(_OWORD *)(a1 + 8);
    v13[0] = v7;
    TxFilterState = FindTxFilterState(v13, &v12);
    result = 0;
    if ( TxFilterState )
    {
      if ( *(_QWORD *)(TxFilterState + 48) )
        return result;
      PADeleteTxFilterState(TxFilterState);
    }
    return PAAddTxFilterSpec(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x18002b438  mov     rax, rsp
0x18002b43b  push    rbx
0x18002b43c  push    rbp
0x18002b43d  push    rsi
0x18002b43e  push    rdi
0x18002b43f  sub     rsp, 48h
0x18002b443  test    byte ptr [rcx+4Ch], 3
0x18002b447  mov     esi, r9d
0x18002b44a  movups  xmm0, xmmword ptr [rcx+8]
0x18002b44e  mov     rdi, r8
0x18002b451  mov     rbp, rdx
0x18002b454  movups  xmm1, xmmword ptr [r8+18h]
0x18002b459  mov     rbx, rcx
0x18002b45c  jnz     short loc_18002B49D
0x18002b45e  lea     rdx, [rax-48h]
0x18002b462  lea     rcx, [rax-38h]
0x18002b466  movdqu  xmmword ptr [rax-48h], xmm0
0x18002b46b  movdqu  xmmword ptr [rax-38h], xmm1
0x18002b470  call    FindTxFilterState
0x18002b475  mov     rcx, rax
0x18002b478  xor     eax, eax
0x18002b47a  test    rcx, rcx
0x18002b47d  jz      short loc_18002B48A
0x18002b47f  cmp     [rcx+30h], rax
0x18002b483  jnz     short loc_18002B4DE
0x18002b485  call    PADeleteTxFilterState
0x18002b48a  mov     r9d, esi
0x18002b48d  mov     r8, rdi
0x18002b490  mov     rdx, rbp
0x18002b493  mov     rcx, rbx
0x18002b496  call    PAAddTxFilterSpec
0x18002b49b  jmp     short loc_18002B4DE
0x18002b49d  lea     rdx, [rsp+68h+var_38]
0x18002b4a2  lea     rcx, [rsp+68h+var_48]
0x18002b4a7  movdqu  [rsp+68h+var_38], xmm0
0x18002b4ad  movdqu  [rsp+68h+var_48], xmm1
0x18002b4b3  call    FindTnFilterState
0x18002b4b8  mov     rcx, rax
0x18002b4bb  xor     eax, eax
0x18002b4bd  test    rcx, rcx
0x18002b4c0  jz      short loc_18002B4CD
0x18002b4c2  cmp     [rcx+30h], rax
0x18002b4c6  jnz     short loc_18002B4DE
0x18002b4c8  call    PADeleteTnFilterState
0x18002b4cd  mov     r9d, esi
0x18002b4d0  mov     r8, rdi
0x18002b4d3  mov     rdx, rbp
0x18002b4d6  mov     rcx, rbx
0x18002b4d9  call    PAAddTnFilterSpec
0x18002b4de  add     rsp, 48h
0x18002b4e2  pop     rdi
0x18002b4e3  pop     rsi
0x18002b4e4  pop     rbp
0x18002b4e5  pop     rbx
0x18002b4e6  retn
```
