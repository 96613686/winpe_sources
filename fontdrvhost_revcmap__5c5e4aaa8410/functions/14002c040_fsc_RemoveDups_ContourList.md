# fsc_RemoveDups(ContourList *)

- ea: `0x14002c040`
- end: `0x14002c19e`
- name: `?fsc_RemoveDups@@YAXPEAUContourList@@@Z`
- size: `350`
- prototype: `void __fastcall(struct ContourList *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002a840`

## callees

- `0x14002c040`

## pseudocode

```c
void __fastcall fsc_RemoveDups(struct ContourList *a1)
{
  unsigned __int16 i; // bp
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r14
  __int64 v7; // r11
  __int16 v8; // r9
  int *v9; // rax
  int *v10; // r10
  bool v11; // zf
  int v12; // ecx
  int v13; // edx
  __int64 v14; // r9
  __int16 v15; // di
  __int64 v16; // rsi

  for ( i = 0; i < *(_WORD *)a1; ++i )
  {
    v3 = *((_QWORD *)a1 + 1);
    v4 = *((_QWORD *)a1 + 3);
    v5 = *((_QWORD *)a1 + 4);
    v6 = *(__int16 *)(v3 + 2LL * i);
    v7 = *(__int16 *)(*((_QWORD *)a1 + 2) + 2LL * i);
    v8 = *(_WORD *)(v3 + 2LL * i);
    v9 = (int *)(v4 + 4 * v6);
    v10 = (int *)(v5 + 4 * v6);
    v11 = (_WORD)v6 == (unsigned __int16)v7;
    if ( (__int16)v6 < (__int16)v7 )
    {
      do
      {
        v12 = *v9++;
        v13 = *v10++;
        if ( *v9 == v12 && *v10 == v13 )
        {
          v15 = v8;
          if ( v8 > (__int16)v6 )
          {
            v16 = v8;
            do
            {
              --v16;
              --v15;
              *(_DWORD *)(*((_QWORD *)a1 + 3) + 4 * v16 + 4) = *(_DWORD *)(*((_QWORD *)a1 + 3) + 4 * v16);
              *(_DWORD *)(*((_QWORD *)a1 + 4) + 4 * v16 + 4) = *(_DWORD *)(*((_QWORD *)a1 + 4) + 4 * v16);
              *(_BYTE *)(*((_QWORD *)a1 + 5) + v16 + 1) = *(_BYTE *)(*((_QWORD *)a1 + 5) + v16);
            }
            while ( v15 > (__int16)v6 );
          }
          LOWORD(v6) = v6 + 1;
          *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * i) = v6;
          *(_BYTE *)(*((_QWORD *)a1 + 5) + v8 + 1LL) |= 1u;
        }
        ++v8;
      }
      while ( v8 < (__int16)v7 );
      v3 = *((_QWORD *)a1 + 1);
      v11 = (_WORD)v6 == (unsigned __int16)v7;
      v4 = *((_QWORD *)a1 + 3);
      v5 = *((_QWORD *)a1 + 4);
    }
    if ( !v11 )
    {
      v14 = 4LL * (__int16)v6;
      if ( *v9 == *(_DWORD *)(v14 + v4) && *v10 == *(_DWORD *)(v14 + v5) )
      {
        ++*(_WORD *)(v3 + 2LL * i);
        *(_BYTE *)(*((_QWORD *)a1 + 5) + v7) |= 1u;
      }
    }
  }
}

```

## disassembly

```asm
0x14002c040  push    rbx
0x14002c042  push    rbp
0x14002c043  xor     ebp, ebp
0x14002c045  xor     eax, eax
0x14002c047  mov     rbx, rcx
0x14002c04a  cmp     ax, [rcx]
0x14002c04d  jnb     loc_14002C115
0x14002c053  mov     [rsp+10h+arg_0], rsi
0x14002c058  mov     [rsp+10h+arg_8], rdi
0x14002c05d  mov     [rsp+10h+arg_10], r14
0x14002c062  mov     [rsp+10h+arg_18], r15
0x14002c067  nop     word ptr [rax+rax+00000000h]
0x14002c070  mov     rax, [rbx+10h]
0x14002c074  mov     rdi, [rbx+8]
0x14002c078  mov     rdx, [rbx+18h]
0x14002c07c  mov     r8, [rbx+20h]
0x14002c080  movzx   r15d, bp
0x14002c084  movsx   r14, word ptr [rdi+r15*2]
0x14002c089  movsx   r11, word ptr [rax+r15*2]
0x14002c08e  movzx   r9d, r14w
0x14002c092  lea     rcx, ds:0[r14*4]
0x14002c09a  lea     rax, [rdx+rcx]
0x14002c09e  lea     r10, [r8+rcx]
0x14002c0a2  cmp     r14w, r11w
0x14002c0a6  jge     short loc_14002C0DB
0x14002c0a8  nop     dword ptr [rax+rax+00000000h]
0x14002c0b0  mov     ecx, [rax]
0x14002c0b2  add     rax, 4
0x14002c0b6  mov     edx, [r10]
0x14002c0b9  add     r10, 4
0x14002c0bd  cmp     [rax], ecx
0x14002c0bf  jz      short loc_14002C118
0x14002c0c1  inc     r9w
0x14002c0c5  cmp     r9w, r11w
0x14002c0c9  jl      short loc_14002C0B0
0x14002c0cb  mov     rdi, [rbx+8]
0x14002c0cf  cmp     r14w, r11w
0x14002c0d3  mov     rdx, [rbx+18h]
0x14002c0d7  mov     r8, [rbx+20h]
0x14002c0db  jz      short loc_14002C0F5
0x14002c0dd  movsx   rcx, r14w
0x14002c0e1  lea     r9, ds:0[rcx*4]
0x14002c0e9  mov     ecx, [r9+rdx]
0x14002c0ed  cmp     [rax], ecx
0x14002c0ef  jz      loc_14002C17E
0x14002c0f5  inc     bp
0x14002c0f8  cmp     bp, [rbx]
0x14002c0fb  jb      loc_14002C070
0x14002c101  mov     r15, [rsp+10h+arg_18]
0x14002c106  mov     r14, [rsp+10h+arg_10]
0x14002c10b  mov     rdi, [rsp+10h+arg_8]
0x14002c110  mov     rsi, [rsp+10h+arg_0]
0x14002c115  pop     rbp
0x14002c116  pop     rbx
0x14002c117  retn
0x14002c118  cmp     [r10], edx
0x14002c11b  jnz     short loc_14002C0C1
0x14002c11d  movzx   edi, r9w
0x14002c121  cmp     r9w, r14w
0x14002c125  jle     short loc_14002C15F
0x14002c127  movsx   rsi, r9w
0x14002c12b  nop     dword ptr [rax+rax+00h]
0x14002c130  mov     rdx, [rbx+18h]
0x14002c134  lea     rsi, [rsi-1]
0x14002c138  dec     di
0x14002c13b  mov     ecx, [rdx+rsi*4]
0x14002c13e  mov     [rdx+rsi*4+4], ecx
0x14002c142  mov     rdx, [rbx+20h]
0x14002c146  mov     ecx, [rdx+rsi*4]
0x14002c149  mov     [rdx+rsi*4+4], ecx
0x14002c14d  mov     rdx, [rbx+28h]
0x14002c151  movzx   ecx, byte ptr [rdx+rsi]
0x14002c155  mov     [rdx+rsi+1], cl
0x14002c159  cmp     di, r14w
0x14002c15d  jg      short loc_14002C130
0x14002c15f  mov     rcx, [rbx+8]
0x14002c163  inc     r14w
0x14002c167  movsx   rdx, r9w
0x14002c16b  mov     [rcx+r15*2], r14w
0x14002c170  mov     rcx, [rbx+28h]
0x14002c174  or      byte ptr [rcx+rdx+1], 1
0x14002c179  jmp     loc_14002C0C1
0x14002c17e  mov     eax, [r9+r8]
0x14002c182  cmp     [r10], eax
0x14002c185  jnz     loc_14002C0F5
0x14002c18b  inc     word ptr [rdi+r15*2]
0x14002c190  mov     rax, [rbx+28h]
0x14002c194  or      byte ptr [rax+r11], 1
0x14002c199  jmp     loc_14002C0F5
```
