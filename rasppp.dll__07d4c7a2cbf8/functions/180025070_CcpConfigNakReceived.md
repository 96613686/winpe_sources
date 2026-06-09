# CcpConfigNakReceived

- ea: `0x180025070`
- end: `0x1800251af`
- name: `CcpConfigNakReceived`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180024b08`
- `0x180025070`

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
0x180025070  mov     [rsp+arg_8], rbx
0x180025075  mov     [rsp+arg_10], rbp
0x18002507a  push    rsi
0x18002507b  push    rdi
0x18002507c  push    r14
0x18002507e  sub     rsp, 30h
0x180025082  movzx   r8d, byte ptr [rdx+2]
0x180025087  lea     rsi, [rdx+4]
0x18002508b  movzx   r14d, byte ptr [rdx+3]
0x180025090  xor     edi, edi
0x180025092  mov     rbx, rcx
0x180025095  shl     r8d, 8
0x180025099  add     r14d, 0FFFFFFFCh
0x18002509d  mov     [rsp+48h+arg_0], edi
0x1800250a1  xor     ecx, ecx
0x1800250a3  add     r14d, r8d
0x1800250a6  cmp     r14d, 2
0x1800250aa  jb      loc_180025157
0x1800250b0  movzx   eax, byte ptr [rsi+1]
0x1800250b4  sub     r14d, eax
0x1800250b7  js      loc_180025150
0x1800250bd  movzx   ebp, byte ptr [rsi]
0x1800250c0  cmp     ebp, ecx
0x1800250c2  jb      loc_180025150
0x1800250c8  lea     rdx, [rbx+20h]
0x1800250cc  mov     [rsp+48h+var_28], 0
0x1800250d4  lea     r9, [rsp+48h+arg_0]
0x1800250d9  mov     r8, rsi
0x1800250dc  mov     rcx, rbx
0x1800250df  call    CcpCheckOption
0x1800250e4  test    eax, eax
0x1800250e6  jnz     loc_18002519C
0x1800250ec  mov     al, [rsi]
0x1800250ee  mov     ecx, ebp
0x1800250f0  test    al, al
0x1800250f2  jz      short loc_18002512C
0x1800250f4  cmp     al, 12h
0x1800250f6  jz      short loc_180025112
0x1800250f8  cmp     [rsp+48h+arg_0], 4
0x1800250fd  jnz     short loc_180025106
0x1800250ff  and     dword ptr [rbx+194h], 0FFFFFFFBh
0x180025106  cmp     [rsp+48h+arg_0], 2
0x18002510b  jnz     short loc_180025144
0x18002510d  or      edi, 4
0x180025110  jmp     short loc_180025144
0x180025112  cmp     [rsp+48h+arg_0], 4
0x180025117  jnz     short loc_180025120
0x180025119  and     dword ptr [rbx+194h], 0FFFFFFFEh
0x180025120  cmp     [rsp+48h+arg_0], 2
0x180025125  jnz     short loc_180025144
0x180025127  or      edi, 1
0x18002512a  jmp     short loc_180025144
0x18002512c  cmp     [rsp+48h+arg_0], 4
0x180025131  jnz     short loc_18002513A
0x180025133  and     dword ptr [rbx+194h], 0FFFFFFFDh
0x18002513a  cmp     [rsp+48h+arg_0], 2
0x18002513f  jnz     short loc_180025144
0x180025141  or      edi, 2
0x180025144  movzx   eax, byte ptr [rsi+1]
0x180025148  add     rsi, rax
0x18002514b  jmp     loc_1800250A6
0x180025150  mov     eax, 2D2h
0x180025155  jmp     short loc_18002519C
0x180025157  cmp     dword ptr [rbx+194h], 0
0x18002515e  jnz     short loc_180025166
0x180025160  cmp     dword ptr [rbx+10h], 0
0x180025164  jmp     short loc_18002518E
0x180025166  test    dil, 2
0x18002516a  jz      short loc_180025178
0x18002516c  mov     dword ptr [rbx+194h], 2
0x180025176  jmp     short loc_18002519A
0x180025178  test    dil, 4
0x18002517c  jz      short loc_18002518A
0x18002517e  mov     dword ptr [rbx+194h], 4
0x180025188  jmp     short loc_18002519A
0x18002518a  test    dil, 1
0x18002518e  jz      short loc_18002519A
0x180025190  mov     dword ptr [rbx+194h], 1
0x18002519a  xor     eax, eax
0x18002519c  mov     rbx, [rsp+48h+arg_8]
0x1800251a1  mov     rbp, [rsp+48h+arg_10]
0x1800251a6  add     rsp, 30h
0x1800251aa  pop     r14
0x1800251ac  pop     rdi
0x1800251ad  pop     rsi
0x1800251ae  retn
```
