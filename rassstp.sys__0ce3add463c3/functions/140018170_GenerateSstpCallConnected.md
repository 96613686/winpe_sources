# GenerateSstpCallConnected

- ea: `0x140018170`
- end: `0x1400182d3`
- name: `GenerateSstpCallConnected`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400161b0`
- `0x1400169a4`

## callees

- `0x140006240`
- `0x140018114`
- `0x140018170`

## pseudocode

```c
char __fastcall GenerateSstpCallConnected(
        _WORD *a1,
        __int64 a2,
        unsigned __int16 *a3,
        char a4,
        __int128 *a5,
        __int16 a6,
        _OWORD *a7,
        _QWORD *a8,
        __int16 *a9)
{
  char result; // al
  __int16 *v13; // rcx
  _QWORD *v14; // r15
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  __int16 v17; // dx
  __int128 v18; // xmm0
  __int64 v19; // r14
  _DWORD v20[40]; // [rsp+30h] [rbp-71h] BYREF
  __int16 v21; // [rsp+F8h] [rbp+57h] BYREF

  result = 0;
  v21 = 0;
  if ( !a4 )
  {
    *a1 = 272;
    a1[2] = 1024;
    *a3 = 8;
    a1[3] = 0;
    a1[1] = __ROR2__(*a3, 8);
    return 1;
  }
  if ( a4 == 3 )
    return result;
  memset(v20, 0, 0x64u);
  v13 = a9;
  v14 = a8;
  *a1 = 272;
  a1[2] = 1024;
  *v13 = 0;
  *v14 = 0;
  *a3 = 8;
  v15 = a7;
  a1[3] = 256;
  HIBYTE(v20[0]) = a4;
  v16 = v15[1];
  *(_OWORD *)&v20[1] = *v15;
  *(_OWORD *)&v20[5] = v16;
  if ( a4 == 1 )
  {
    v17 = 20;
    if ( a6 != 20 )
      return 0;
    v18 = *a5;
    v20[13] = *((_DWORD *)a5 + 4);
    goto LABEL_11;
  }
  v19 = 0;
  if ( a4 == 2 )
  {
    v17 = 32;
    if ( a6 != 32 )
      return 0;
    v18 = *a5;
    *(_OWORD *)&v20[13] = a5[1];
LABEL_11:
    v19 = 34;
    *v13 = v17;
    *(_OWORD *)&v20[9] = v18;
  }
  result = GenerateSstpAttribute(3, v20, 0x64u, (__int64)a1 + *a3, 4095 - *a3, &v21);
  if ( !result )
    return result;
  *a3 += v21;
  a1[1] = __ROR2__(*a3, 8);
  *v14 = &a1[v19 + 6];
  return 1;
}

```

## disassembly

```asm
0x140018170  push    rbp
0x140018172  push    rbx
0x140018173  push    rsi
0x140018174  push    rdi
0x140018175  push    r14
0x140018177  push    r15
0x140018179  lea     rbp, [rsp-7]
0x14001817e  sub     rsp, 0A8h
0x140018185  xor     eax, eax
0x140018187  mov     sil, r9b
0x14001818a  mov     [rbp+2Fh+arg_18], ax
0x14001818e  mov     rdi, r8
0x140018191  mov     rbx, rcx
0x140018194  test    r9b, r9b
0x140018197  jnz     short loc_1400181BF
0x140018199  mov     word ptr [rcx], 110h
0x14001819e  mov     word ptr [rcx+4], 400h
0x1400181a4  mov     word ptr [r8], 8
0x1400181aa  mov     [rcx+6], ax
0x1400181ae  movzx   eax, word ptr [r8]
0x1400181b2  ror     ax, 8
0x1400181b6  mov     [rcx+2], ax
0x1400181ba  jmp     loc_1400182C0
0x1400181bf  cmp     sil, 3
0x1400181c3  jz      loc_1400182C2
0x1400181c9  xor     edx, edx; Val
0x1400181cb  lea     rcx, [rbp+2Fh+var_A0]; void *
0x1400181cf  lea     r8d, [rdx+64h]; Size
0x1400181d3  call    memset
0x1400181d8  mov     rcx, [rbp+2Fh+arg_40]
0x1400181dc  xor     eax, eax
0x1400181de  mov     r15, [rbp+2Fh+arg_38]
0x1400181e2  mov     word ptr [rbx], 110h
0x1400181e7  mov     word ptr [rbx+4], 400h
0x1400181ed  mov     [rcx], ax
0x1400181f0  mov     qword ptr [r15], 0
0x1400181f7  mov     word ptr [rdi], 8
0x1400181fc  mov     rax, [rbp+2Fh+arg_30]
0x140018200  mov     word ptr [rbx+6], 100h
0x140018206  mov     [rbp+2Fh+var_9D], sil
0x14001820a  movups  xmm0, xmmword ptr [rax]
0x14001820d  movups  xmm1, xmmword ptr [rax+10h]
0x140018211  movups  [rbp+2Fh+var_9C], xmm0
0x140018215  movups  [rbp+2Fh+var_8C], xmm1
0x140018219  cmp     sil, 1
0x14001821d  jnz     short loc_140018240
0x14001821f  mov     edx, 14h
0x140018224  cmp     [rbp+2Fh+arg_28], dx
0x140018228  jz      short loc_140018231
0x14001822a  xor     al, al
0x14001822c  jmp     loc_1400182C2
0x140018231  mov     rax, [rbp+2Fh+arg_20]
0x140018235  movups  xmm0, xmmword ptr [rax]
0x140018238  mov     eax, [rax+10h]
0x14001823b  mov     dword ptr [rbp+2Fh+var_6C], eax
0x14001823e  jmp     short loc_140018262
0x140018240  xor     r14d, r14d
0x140018243  cmp     sil, 2
0x140018247  jnz     short loc_14001826F
0x140018249  lea     edx, [r14+20h]
0x14001824d  cmp     [rbp+2Fh+arg_28], dx
0x140018251  jnz     short loc_14001822A
0x140018253  mov     rax, [rbp+2Fh+arg_20]
0x140018257  movups  xmm1, xmmword ptr [rax+10h]
0x14001825b  movups  xmm0, xmmword ptr [rax]
0x14001825e  movups  [rbp+2Fh+var_6C], xmm1
0x140018262  mov     r14d, 44h ; 'D'
0x140018268  mov     [rcx], dx
0x14001826b  movups  [rbp+2Fh+var_7C], xmm0
0x14001826f  movzx   r9d, word ptr [rdi]
0x140018273  lea     rdx, [rbp+2Fh+arg_18]
0x140018277  mov     [rsp+0D0h+var_A8], rdx
0x14001827c  mov     r8d, 64h ; 'd'
0x140018282  mov     eax, 0FFFh
0x140018287  lea     rdx, [rbp+2Fh+var_A0]
0x14001828b  sub     ax, r9w
0x14001828f  add     r9, rbx
0x140018292  mov     [rsp+0D0h+var_B0], ax
0x140018297  lea     ecx, [r8-61h]
0x14001829b  call    GenerateSstpAttribute
0x1400182a0  test    al, al
0x1400182a2  jz      short loc_1400182C2
0x1400182a4  movzx   eax, [rbp+2Fh+arg_18]
0x1400182a8  add     [rdi], ax
0x1400182ab  movzx   eax, word ptr [rdi]
0x1400182ae  ror     ax, 8
0x1400182b2  mov     [rbx+2], ax
0x1400182b6  lea     rax, [rbx+0Ch]
0x1400182ba  add     rax, r14
0x1400182bd  mov     [r15], rax
0x1400182c0  mov     al, 1
0x1400182c2  add     rsp, 0A8h
0x1400182c9  pop     r15
0x1400182cb  pop     r14
0x1400182cd  pop     rdi
0x1400182ce  pop     rsi
0x1400182cf  pop     rbx
0x1400182d0  pop     rbp
0x1400182d1  retn
```
