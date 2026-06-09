# ProcessCommandLineOption

- ea: `0x1800071d0`
- end: `0x1800072eb`
- name: `ProcessCommandLineOption`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006e90`

## callees

- `0x180006708`
- `0x180006890`
- `0x1800071d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007225`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007225`

## pseudocode

```c
__int64 __fastcall ProcessCommandLineOption(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned int a5, __int64 a6)
{
  unsigned int v6; // ebx
  int v7; // edi
  __int64 v8; // rbp
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  int Number; // eax
  __int64 v17; // rdx
  __int64 v19; // [rsp+60h] [rbp+18h]

  v19 = a3;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( a2 > 0 )
  {
    while ( 1 )
    {
      if ( v7 )
        return v6;
      v12 = *(_QWORD *)(a1 + 24 * v8);
      if ( !v12 )
        return (unsigned int)-2147024809;
      if ( !(unsigned int)_o__wcsicmp(a3, v12) )
      {
        v13 = *(_DWORD *)(a1 + 24 * v8 + 8);
        if ( v13 )
        {
          if ( v13 == 1 )
          {
            v15 = *(_QWORD *)(a1 + 24 * v8 + 16);
            if ( v15 + 8 > (unsigned __int64)a5 )
              return (unsigned int)-2147467259;
            Number = GetNumber(a6, a4 + v15);
          }
          else
          {
            if ( v13 != 2 )
              goto LABEL_16;
            v17 = *(_QWORD *)(a1 + 24 * v8 + 16);
            if ( v17 + 16 > (unsigned __int64)a5 )
              return (unsigned int)-2147467259;
            Number = GetString(a6, a4 + v17);
          }
          v6 = Number;
          if ( Number < 0 )
            return v6;
          v7 = 1;
        }
        else
        {
          v14 = *(_QWORD *)(a1 + 24 * v8 + 16);
          if ( v14 + 4 > (unsigned __int64)a5 )
            return (unsigned int)-2147467259;
          v7 = 1;
          *(_DWORD *)(v14 + a4) = 1;
        }
      }
LABEL_16:
      v8 = (unsigned int)(v8 + 1);
      if ( (int)v8 >= a2 )
      {
        if ( v7 )
          return v6;
        return (unsigned int)-2147467259;
      }
      a3 = v19;
    }
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1800071d0  mov     [rsp+arg_0], rbx
0x1800071d5  mov     [rsp+arg_8], rbp
0x1800071da  mov     [rsp+arg_10], r8
0x1800071df  push    rsi
0x1800071e0  push    rdi
0x1800071e1  push    r12
0x1800071e3  push    r13
0x1800071e5  push    r14
0x1800071e7  sub     rsp, 20h
0x1800071eb  xor     ebx, ebx
0x1800071ed  xor     edi, edi
0x1800071ef  xor     ebp, ebp
0x1800071f1  mov     r12, r9
0x1800071f4  mov     r13d, edx
0x1800071f7  mov     r14, rcx
0x1800071fa  test    edx, edx
0x1800071fc  jle     loc_1800072C5
0x180007202  test    edi, edi
0x180007204  jnz     loc_1800072CA
0x18000720a  lea     rsi, ds:0[rbp*2]
0x180007212  add     rsi, rbp
0x180007215  mov     rdx, [r14+rsi*8]
0x180007219  test    rdx, rdx
0x18000721c  jz      loc_1800072E4
0x180007222  mov     rcx, r8
0x180007225  call    cs:__imp__o__wcsicmp
0x18000722c  nop     dword ptr [rax+rax+00h]
0x180007231  test    eax, eax
0x180007233  jnz     short loc_1800072B0
0x180007235  mov     eax, [r14+rsi*8+8]
0x18000723a  test    eax, eax
0x18000723c  jnz     short loc_18000725B
0x18000723e  mov     rdx, [r14+rsi*8+10h]
0x180007243  mov     eax, [rsp+48h+arg_20]
0x180007247  lea     rcx, [rdx+4]
0x18000724b  cmp     rcx, rax
0x18000724e  ja      short loc_1800072C5
0x180007250  mov     edi, 1
0x180007255  mov     [rdx+r12], edi
0x180007259  jmp     short loc_1800072B0
0x18000725b  cmp     eax, 1
0x18000725e  jnz     short loc_180007281
0x180007260  mov     rdx, [r14+rsi*8+10h]
0x180007265  mov     eax, [rsp+48h+arg_20]
0x180007269  lea     rcx, [rdx+8]
0x18000726d  cmp     rcx, rax
0x180007270  ja      short loc_1800072C5
0x180007272  mov     rcx, [rsp+48h+arg_28]
0x180007277  add     rdx, r12
0x18000727a  call    GetNumber
0x18000727f  jmp     short loc_1800072A5
0x180007281  cmp     eax, 2
0x180007284  jnz     short loc_1800072B0
0x180007286  mov     rdx, [r14+rsi*8+10h]
0x18000728b  mov     eax, [rsp+48h+arg_20]
0x18000728f  lea     rcx, [rdx+10h]
0x180007293  cmp     rcx, rax
0x180007296  ja      short loc_1800072C5
0x180007298  mov     rcx, [rsp+48h+arg_28]
0x18000729d  add     rdx, r12
0x1800072a0  call    GetString
0x1800072a5  mov     ebx, eax
0x1800072a7  test    eax, eax
0x1800072a9  js      short loc_1800072CA
0x1800072ab  mov     edi, 1
0x1800072b0  inc     ebp
0x1800072b2  cmp     ebp, r13d
0x1800072b5  jge     short loc_1800072C1
0x1800072b7  mov     r8, [rsp+48h+arg_10]
0x1800072bc  jmp     loc_180007202
0x1800072c1  test    edi, edi
0x1800072c3  jnz     short loc_1800072CA
0x1800072c5  mov     ebx, 80004005h
0x1800072ca  mov     rbp, [rsp+48h+arg_8]
0x1800072cf  mov     eax, ebx
0x1800072d1  mov     rbx, [rsp+48h+arg_0]
0x1800072d6  add     rsp, 20h
0x1800072da  pop     r14
0x1800072dc  pop     r13
0x1800072de  pop     r12
0x1800072e0  pop     rdi
0x1800072e1  pop     rsi
0x1800072e2  retn
0x1800072e4  mov     ebx, 80070057h
0x1800072e9  jmp     short loc_1800072CA
```
