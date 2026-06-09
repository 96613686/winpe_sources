# FindHeaderValue

- ea: `0x1800080e0`
- end: `0x180008286`
- name: `FindHeaderValue`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008040`
- `0x1800080e0`
- `0x1800086f0`

## import_xrefs

- `DMCmnUtils!InvStrCmpNIW` at `0x180008209`
- `DMCmnUtils!InvStrCmpNIW` at `0x180008209`
- `DMCmnUtils!CopyString` at `0x180008256`
- `DMCmnUtils!CopyString` at `0x180008256`

## pseudocode

```c
__int64 __fastcall FindHeaderValue(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  const unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // rax
  __int64 v7; // r9
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // r15
  const unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  unsigned __int16 v15; // ax
  __int64 v16; // r8
  int v17; // eax
  int v19; // [rsp+20h] [rbp-20h] BYREF
  const unsigned __int16 *v20; // [rsp+28h] [rbp-18h] BYREF
  const unsigned __int16 *v21; // [rsp+30h] [rbp-10h] BYREF
  const unsigned __int16 *v22; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v23; // [rsp+88h] [rbp+48h] BYREF
  int v24; // [rsp+98h] [rbp+58h] BYREF

  v22 = a1;
  v20 = a1;
  v23 = 0;
  v5 = a1;
  if ( a2 )
  {
    v6 = a2;
    v7 = 0x7FFFFFFF;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v7;
    }
    while ( v7 );
    v8 = v7 == 0 ? 0x80070057 : 0;
    v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
    if ( v7 )
    {
      *a3 = 0;
      if ( a1 )
      {
        v10 = 0x7FFFFFFF;
        v11 = v5;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v10;
        }
        while ( v10 );
        v8 = v10 == 0 ? 0x80070057 : 0;
        if ( v10 )
        {
          v12 = &v5[(0x7FFFFFFF - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64)];
          while ( (unsigned int)FindEndOfHeader(&v22, v12, &v23) )
          {
            v13 = v5;
            v14 = 0;
            if ( v23 )
            {
              while ( 1 )
              {
                v15 = *v13++;
                if ( v15 == 58 )
                  break;
                v14 = (unsigned int)(v14 + 1);
                if ( (unsigned int)v14 >= v23 )
                  goto LABEL_19;
              }
              v21 = v13;
              v24 = v13 - v5 - 1;
              v19 = v23 - v24;
              if ( (unsigned int)Trim(&v20, &v24, v14) )
              {
                if ( v24 == v9 && !InvStrCmpNIW(v20, a2, v9) )
                {
                  v17 = Trim(&v21, &v19, v16);
                  return (unsigned int)CopyString(v21, v17 != 0 ? v19 : 0, a3);
                }
              }
            }
LABEL_19:
            v5 = v22;
            v20 = v22;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x1800080e0  mov     [rsp-38h+arg_10], rbx
0x1800080e5  mov     [rsp-38h+arg_0], rcx
0x1800080ea  push    rbp
0x1800080eb  push    rsi
0x1800080ec  push    rdi
0x1800080ed  push    r12
0x1800080ef  push    r13
0x1800080f1  push    r14
0x1800080f3  push    r15
0x1800080f5  mov     rbp, rsp
0x1800080f8  sub     rsp, 40h
0x1800080fc  xor     r13d, r13d
0x1800080ff  mov     [rbp+var_18], rcx
0x180008103  mov     [rbp+arg_8], r13d
0x180008107  mov     r12, r8
0x18000810a  mov     r14, rdx
0x18000810d  mov     rdi, rcx
0x180008110  test    rdx, rdx
0x180008113  jz      loc_180008266
0x180008119  mov     r10d, 7FFFFFFFh
0x18000811f  mov     rax, rdx
0x180008122  mov     r9d, r10d
0x180008125  cmp     [rax], r13w
0x180008129  jz      short loc_180008135
0x18000812b  add     rax, 2
0x18000812f  sub     r9, 1
0x180008133  jnz     short loc_180008125
0x180008135  mov     rax, r9
0x180008138  mov     edx, 80070057h
0x18000813d  neg     rax
0x180008140  mov     rcx, r10
0x180008143  mov     rax, r9
0x180008146  sbb     ebx, ebx
0x180008148  sub     rcx, r9
0x18000814b  not     ebx
0x18000814d  and     ebx, edx
0x18000814f  neg     rax
0x180008152  sbb     rsi, rsi
0x180008155  and     rsi, rcx
0x180008158  test    r9, r9
0x18000815b  jz      loc_18000826B
0x180008161  mov     [r8], r13
0x180008164  test    rdi, rdi
0x180008167  jz      loc_18000826B
0x18000816d  mov     rcx, r10
0x180008170  mov     rax, rdi
0x180008173  cmp     [rax], r13w
0x180008177  jz      short loc_180008183
0x180008179  add     rax, 2
0x18000817d  sub     rcx, 1
0x180008181  jnz     short loc_180008173
0x180008183  mov     rax, rcx
0x180008186  neg     rax
0x180008189  mov     rax, rcx
0x18000818c  sbb     ebx, ebx
0x18000818e  sub     r10, rcx
0x180008191  not     ebx
0x180008193  and     ebx, edx
0x180008195  neg     rax
0x180008198  sbb     rdx, rdx
0x18000819b  and     rdx, r10
0x18000819e  test    rcx, rcx
0x1800081a1  jz      loc_18000826B
0x1800081a7  lea     r15, [rdi+rdx*2]
0x1800081ab  jmp     short loc_180008221
0x1800081ad  mov     edx, [rbp+arg_8]
0x1800081b0  mov     rcx, rdi
0x1800081b3  mov     r8d, r13d
0x1800081b6  test    edx, edx
0x1800081b8  jz      short loc_180008219
0x1800081ba  movzx   eax, word ptr [rcx]
0x1800081bd  add     rcx, 2
0x1800081c1  cmp     ax, 3Ah ; ':'
0x1800081c5  jz      short loc_1800081D1
0x1800081c7  inc     r8d
0x1800081ca  cmp     r8d, edx
0x1800081cd  jb      short loc_1800081BA
0x1800081cf  jmp     short loc_180008219
0x1800081d1  mov     [rbp+var_10], rcx
0x1800081d5  sub     rcx, rdi
0x1800081d8  sar     rcx, 1
0x1800081db  lea     eax, [rcx-1]
0x1800081de  sub     edx, eax
0x1800081e0  mov     [rbp+arg_18], eax
0x1800081e3  mov     [rbp+var_20], edx
0x1800081e6  lea     rcx, [rbp+var_18]
0x1800081ea  lea     rdx, [rbp+arg_18]
0x1800081ee  call    Trim
0x1800081f3  test    eax, eax
0x1800081f5  jz      short loc_180008219
0x1800081f7  mov     eax, [rbp+arg_18]
0x1800081fa  cmp     rax, rsi
0x1800081fd  jnz     short loc_180008219
0x1800081ff  mov     rcx, [rbp+var_18]
0x180008203  mov     r8, rsi
0x180008206  mov     rdx, r14
0x180008209  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180008210  nop     dword ptr [rax+rax+00h]
0x180008215  test    eax, eax
0x180008217  jz      short loc_18000823B
0x180008219  mov     rdi, [rbp+arg_0]
0x18000821d  mov     [rbp+var_18], rdi
0x180008221  lea     r8, [rbp+arg_8]
0x180008225  mov     rdx, r15
0x180008228  lea     rcx, [rbp+arg_0]
0x18000822c  call    FindEndOfHeader
0x180008231  test    eax, eax
0x180008233  jnz     loc_1800081AD
0x180008239  jmp     short loc_18000826B
0x18000823b  lea     rdx, [rbp+var_20]
0x18000823f  lea     rcx, [rbp+var_10]
0x180008243  call    Trim
0x180008248  mov     rcx, [rbp+var_10]
0x18000824c  neg     eax
0x18000824e  mov     r8, r12
0x180008251  sbb     edx, edx
0x180008253  and     edx, [rbp+var_20]
0x180008256  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000825d  nop     dword ptr [rax+rax+00h]
0x180008262  mov     ebx, eax
0x180008264  jmp     short loc_18000826B
0x180008266  mov     ebx, 80070057h
0x18000826b  mov     eax, ebx
0x18000826d  mov     rbx, [rsp+40h+arg_10]
0x180008275  add     rsp, 40h
0x180008279  pop     r15
0x18000827b  pop     r14
0x18000827d  pop     r13
0x18000827f  pop     r12
0x180008281  pop     rdi
0x180008282  pop     rsi
0x180008283  pop     rbp
0x180008284  retn
```
