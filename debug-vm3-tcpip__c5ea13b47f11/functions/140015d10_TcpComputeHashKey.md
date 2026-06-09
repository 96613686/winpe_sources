# TcpComputeHashKey

- ea: `0x140015d10`
- end: `0x140015eca`
- name: `TcpComputeHashKey`
- size: `442`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140016890`
- `0x140032ff0`
- `0x140077d8c`
- `0x1400ac600`
- `0x1401155ac`
- `0x14012c6f0`
- `0x140160fcc`

## callees

- `0x140015d10`

## import_xrefs

- `NETIO!RtlComputeToeplitzHash` at `0x140015d52`
- `NETIO!RtlComputeToeplitzHash` at `0x140015d85`
- `NETIO!RtlComputeToeplitzHash` at `0x140015dad`
- `NETIO!RtlComputeToeplitzHash` at `0x140015de7`
- `NETIO!RtlComputeToeplitzHash` at `0x140015dfa`
- `NETIO!RtlComputeToeplitzHash` at `0x140015e29`
- `NETIO!RtlComputeToeplitzHash` at `0x140015e7d`
- `NETIO!RtlComputeToeplitzHash` at `0x140015eb0`
- `NETIO!RtlComputeToeplitzHash` at `0x140015d52`
- `NETIO!RtlComputeToeplitzHash` at `0x140015d85`
- `NETIO!RtlComputeToeplitzHash` at `0x140015dad`
- `NETIO!RtlComputeToeplitzHash` at `0x140015de7`
- `NETIO!RtlComputeToeplitzHash` at `0x140015dfa`
- `NETIO!RtlComputeToeplitzHash` at `0x140015e29`
- `NETIO!RtlComputeToeplitzHash` at `0x140015e7d`
- `NETIO!RtlComputeToeplitzHash` at `0x140015eb0`

## pseudocode

```c
__int64 __fastcall TcpComputeHashKey(__int64 a1, __int64 a2, __int64 a3, __int16 a4, __int16 a5, __int16 a6)
{
  __int64 v6; // rdi
  __int64 v9; // r8
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r9
  int v13; // ebx
  __int16 v15; // si
  __int64 v16; // r9
  int v17; // eax
  __int64 v18; // r9
  __int16 v19; // [rsp+40h] [rbp+8h] BYREF
  __int16 v20; // [rsp+58h] [rbp+20h] BYREF

  v20 = a4;
  v6 = *(_QWORD *)(a2 + 48);
  if ( !v6 )
    LODWORD(v6) = RtlComputeToeplitzHash(
                    TcpToeplitzHashContext,
                    **(_QWORD **)(a2 + 16),
                    *(unsigned __int16 *)(a1 + 72),
                    *(unsigned __int16 *)(a1 + 72));
  v9 = *(unsigned __int16 *)(a1 + 72);
  if ( *(_WORD *)(a1 + 24) == 23 )
  {
    v10 = v6 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, a3, v9, 0);
    if ( (_BYTE)a6 )
    {
      v11 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v20, 2, 32);
      v12 = 34;
      goto LABEL_6;
    }
  }
  else
  {
    v10 = v6 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, a3, v9, 0);
    if ( (_BYTE)a6 )
    {
      v11 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v20, 2, 8);
      v12 = 10;
LABEL_6:
      v13 = v10 ^ v11 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, &a5, 2, v12);
      return v13 | 0x80000000;
    }
  }
  v15 = *(_WORD *)(a1 + 24);
  v19 = a5;
  v16 = 32;
  a6 = v20;
  if ( v15 != 23 )
    v16 = 8;
  v17 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &a6, 2, v16);
  v18 = 34;
  if ( v15 != 23 )
    v18 = 10;
  v13 = (v17 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, &v19, 2, v18)) & 0x7FFFFFC0 ^ v10;
  return v13 | 0x80000000;
}

```

## disassembly

```asm
0x140015d10  mov     [rsp+arg_8], rbx
0x140015d15  mov     [rsp+arg_18], r9w
0x140015d1b  push    rbp
0x140015d1c  push    rsi
0x140015d1d  push    rdi
0x140015d1e  sub     rsp, 20h
0x140015d22  mov     rdi, [rdx+30h]
0x140015d26  mov     rbp, r8
0x140015d29  mov     rsi, rcx
0x140015d2c  test    rdi, rdi
0x140015d2f  jz      loc_140015DD1
0x140015d35  movzx   r8d, word ptr [rsi+48h]
0x140015d3a  lea     rcx, TcpToeplitzHashContext
0x140015d41  xor     r9d, r9d
0x140015d44  mov     rdx, rbp
0x140015d47  cmp     word ptr [rsi+18h], 17h
0x140015d4c  jz      loc_140015DFA
0x140015d52  call    cs:__imp_RtlComputeToeplitzHash
0x140015d59  nop     dword ptr [rax+rax+00h]
0x140015d5e  mov     ebx, eax
0x140015d60  xor     ebx, edi
0x140015d62  cmp     byte ptr [rsp+38h+arg_28], 0
0x140015d67  jz      loc_140015E40
0x140015d6d  mov     r9d, 8
0x140015d73  lea     rdx, [rsp+38h+arg_18]
0x140015d78  mov     r8d, 2
0x140015d7e  lea     rcx, TcpToeplitzHashContext
0x140015d85  call    cs:__imp_RtlComputeToeplitzHash
0x140015d8c  nop     dword ptr [rax+rax+00h]
0x140015d91  mov     r9d, 0Ah
0x140015d97  mov     edi, eax
0x140015d99  lea     rdx, [rsp+38h+arg_20]
0x140015d9e  mov     r8d, 2
0x140015da4  lea     rcx, TcpToeplitzHashContext
0x140015dab  xor     edi, ebx
0x140015dad  call    cs:__imp_RtlComputeToeplitzHash
0x140015db4  nop     dword ptr [rax+rax+00h]
0x140015db9  mov     ebx, eax
0x140015dbb  xor     ebx, edi
0x140015dbd  bts     ebx, 1Fh
0x140015dc1  mov     eax, ebx
0x140015dc3  mov     rbx, [rsp+38h+arg_8]
0x140015dc8  add     rsp, 20h
0x140015dcc  pop     rdi
0x140015dcd  pop     rsi
0x140015dce  pop     rbp
0x140015dcf  retn
0x140015dd1  movzx   r8d, word ptr [rcx+48h]
0x140015dd6  lea     rcx, TcpToeplitzHashContext
0x140015ddd  mov     rdx, [rdx+10h]
0x140015de1  mov     r9d, r8d
0x140015de4  mov     rdx, [rdx]
0x140015de7  call    cs:__imp_RtlComputeToeplitzHash
0x140015dee  nop     dword ptr [rax+rax+00h]
0x140015df3  mov     edi, eax
0x140015df5  jmp     loc_140015D35
0x140015dfa  call    cs:__imp_RtlComputeToeplitzHash
0x140015e01  nop     dword ptr [rax+rax+00h]
0x140015e06  mov     ebx, eax
0x140015e08  xor     ebx, edi
0x140015e0a  cmp     byte ptr [rsp+38h+arg_28], 0
0x140015e0f  jz      short loc_140015E40
0x140015e11  mov     r9d, 20h ; ' '
0x140015e17  lea     rdx, [rsp+38h+arg_18]
0x140015e1c  mov     r8d, 2
0x140015e22  lea     rcx, TcpToeplitzHashContext
0x140015e29  call    cs:__imp_RtlComputeToeplitzHash
0x140015e30  nop     dword ptr [rax+rax+00h]
0x140015e35  mov     r9d, 22h ; '"'
0x140015e3b  jmp     loc_140015D97
0x140015e40  movzx   eax, [rsp+38h+arg_20]
0x140015e45  lea     rdx, [rsp+38h+arg_28]
0x140015e4a  movzx   esi, word ptr [rsi+18h]
0x140015e4e  lea     rcx, TcpToeplitzHashContext
0x140015e55  mov     [rsp+38h+arg_0], ax
0x140015e5a  mov     r9d, 20h ; ' '
0x140015e60  movzx   eax, [rsp+38h+arg_18]
0x140015e65  cmp     si, 17h
0x140015e69  mov     [rsp+38h+arg_28], ax
0x140015e6e  mov     r8d, 2
0x140015e74  mov     eax, 8
0x140015e79  cmovnz  r9d, eax
0x140015e7d  call    cs:__imp_RtlComputeToeplitzHash
0x140015e84  nop     dword ptr [rax+rax+00h]
0x140015e89  mov     r9d, 22h ; '"'
0x140015e8f  lea     rdx, [rsp+38h+arg_0]
0x140015e94  mov     edi, eax
0x140015e96  lea     rcx, TcpToeplitzHashContext
0x140015e9d  mov     eax, 0Ah
0x140015ea2  cmp     si, 17h
0x140015ea6  mov     r8d, 2
0x140015eac  cmovnz  r9d, eax
0x140015eb0  call    cs:__imp_RtlComputeToeplitzHash
0x140015eb7  nop     dword ptr [rax+rax+00h]
0x140015ebc  xor     eax, edi
0x140015ebe  and     eax, 7FFFFFC0h
0x140015ec3  xor     ebx, eax
0x140015ec5  jmp     loc_140015DBD
```
