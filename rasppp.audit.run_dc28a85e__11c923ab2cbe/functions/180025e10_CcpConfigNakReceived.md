# CcpConfigNakReceived

- ea: `0x180025e10`
- end: `0x180025f50`
- name: `CcpConfigNakReceived`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800258b0`
- `0x180025e10`

## pseudocode

```c
__int64 __fastcall CcpConfigNakReceived(_DWORD *a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rsi
  int v3; // edi
  int v5; // r8d
  int v6; // r14d
  unsigned int v7; // ecx
  int v8; // r14d
  unsigned int v9; // ebp
  __int64 result; // rax
  bool v11; // zf
  int v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2 + 4;
  v3 = 0;
  v5 = a2[2] << 8;
  v6 = a2[3] - 4;
  v12 = 0;
  v7 = 0;
  v8 = v5 + v6;
  while ( (unsigned int)v8 >= 2 )
  {
    v8 -= v2[1];
    if ( v8 < 0 )
      return 722;
    v9 = *v2;
    if ( v9 < v7 )
      return 722;
    result = CcpCheckOption(a1, (__int64)(a1 + 8), v2, &v12, 0);
    if ( (_DWORD)result )
      return result;
    v7 = v9;
    if ( *v2 )
    {
      if ( *v2 == 18 )
      {
        if ( v12 == 4 )
          a1[101] &= ~1u;
        if ( v12 == 2 )
          v3 |= 1u;
      }
      else
      {
        if ( v12 == 4 )
          a1[101] &= ~4u;
        if ( v12 == 2 )
          v3 |= 4u;
      }
    }
    else
    {
      if ( v12 == 4 )
        a1[101] &= ~2u;
      if ( v12 == 2 )
        v3 |= 2u;
    }
    v2 += v2[1];
  }
  if ( !a1[101] )
  {
    v11 = a1[4] == 0;
    goto LABEL_29;
  }
  if ( (v3 & 2) != 0 )
  {
    a1[101] = 2;
  }
  else
  {
    if ( (v3 & 4) == 0 )
    {
      v11 = (v3 & 1) == 0;
LABEL_29:
      if ( !v11 )
        a1[101] = 1;
      return 0;
    }
    a1[101] = 4;
  }
  return 0;
}

```

## disassembly

```asm
0x180025e10  mov     [rsp+arg_8], rbx
0x180025e15  mov     [rsp+arg_10], rbp
0x180025e1a  push    rsi
0x180025e1b  push    rdi
0x180025e1c  push    r14
0x180025e1e  sub     rsp, 30h
0x180025e22  movzx   r8d, byte ptr [rdx+2]
0x180025e27  lea     rsi, [rdx+4]
0x180025e2b  movzx   r14d, byte ptr [rdx+3]
0x180025e30  xor     edi, edi
0x180025e32  mov     rbx, rcx
0x180025e35  shl     r8d, 8
0x180025e39  add     r14d, 0FFFFFFFCh
0x180025e3d  mov     [rsp+48h+arg_0], edi
0x180025e41  xor     ecx, ecx
0x180025e43  add     r14d, r8d
0x180025e46  cmp     r14d, 2
0x180025e4a  jb      loc_180025EF7
0x180025e50  movzx   eax, byte ptr [rsi+1]
0x180025e54  sub     r14d, eax
0x180025e57  js      loc_180025EF0
0x180025e5d  movzx   ebp, byte ptr [rsi]
0x180025e60  cmp     ebp, ecx
0x180025e62  jb      loc_180025EF0
0x180025e68  lea     rdx, [rbx+20h]
0x180025e6c  mov     [rsp+48h+var_28], 0
0x180025e74  lea     r9, [rsp+48h+arg_0]
0x180025e79  mov     r8, rsi
0x180025e7c  mov     rcx, rbx
0x180025e7f  call    CcpCheckOption
0x180025e84  test    eax, eax
0x180025e86  jnz     loc_180025F3C
0x180025e8c  mov     al, [rsi]
0x180025e8e  mov     ecx, ebp
0x180025e90  test    al, al
0x180025e92  jz      short loc_180025ECC
0x180025e94  cmp     al, 12h
0x180025e96  jz      short loc_180025EB2
0x180025e98  cmp     [rsp+48h+arg_0], 4
0x180025e9d  jnz     short loc_180025EA6
0x180025e9f  and     dword ptr [rbx+194h], 0FFFFFFFBh
0x180025ea6  cmp     [rsp+48h+arg_0], 2
0x180025eab  jnz     short loc_180025EE4
0x180025ead  or      edi, 4
0x180025eb0  jmp     short loc_180025EE4
0x180025eb2  cmp     [rsp+48h+arg_0], 4
0x180025eb7  jnz     short loc_180025EC0
0x180025eb9  and     dword ptr [rbx+194h], 0FFFFFFFEh
0x180025ec0  cmp     [rsp+48h+arg_0], 2
0x180025ec5  jnz     short loc_180025EE4
0x180025ec7  or      edi, 1
0x180025eca  jmp     short loc_180025EE4
0x180025ecc  cmp     [rsp+48h+arg_0], 4
0x180025ed1  jnz     short loc_180025EDA
0x180025ed3  and     dword ptr [rbx+194h], 0FFFFFFFDh
0x180025eda  cmp     [rsp+48h+arg_0], 2
0x180025edf  jnz     short loc_180025EE4
0x180025ee1  or      edi, 2
0x180025ee4  movzx   eax, byte ptr [rsi+1]
0x180025ee8  add     rsi, rax
0x180025eeb  jmp     loc_180025E46
0x180025ef0  mov     eax, 2D2h
0x180025ef5  jmp     short loc_180025F3C
0x180025ef7  cmp     dword ptr [rbx+194h], 0
0x180025efe  jnz     short loc_180025F06
0x180025f00  cmp     dword ptr [rbx+10h], 0
0x180025f04  jmp     short loc_180025F2E
0x180025f06  test    dil, 2
0x180025f0a  jz      short loc_180025F18
0x180025f0c  mov     dword ptr [rbx+194h], 2
0x180025f16  jmp     short loc_180025F3A
0x180025f18  test    dil, 4
0x180025f1c  jz      short loc_180025F2A
0x180025f1e  mov     dword ptr [rbx+194h], 4
0x180025f28  jmp     short loc_180025F3A
0x180025f2a  test    dil, 1
0x180025f2e  jz      short loc_180025F3A
0x180025f30  mov     dword ptr [rbx+194h], 1
0x180025f3a  xor     eax, eax
0x180025f3c  mov     rbx, [rsp+48h+arg_8]
0x180025f41  mov     rbp, [rsp+48h+arg_10]
0x180025f46  add     rsp, 30h
0x180025f4a  pop     r14
0x180025f4c  pop     rdi
0x180025f4d  pop     rsi
0x180025f4e  retn
```
