# MDIDecompressGlobal

- ea: `0x1800051d0`
- end: `0x180005329`
- name: `MDIDecompressGlobal`
- size: `345`
- prototype: `__int64 __fastcall(__int64, _WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004e64`

## callees

- `0x1800051d0`
- `0x180005330`
- `0x180005380`
- `0x1800058e4`
- `0x180015c9c`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall MDIDecompressGlobal(__int64 a1, _WORD *a2)
{
  int v4; // ecx
  int v5; // ecx
  __int64 v6; // r10
  int v7; // ecx
  unsigned int v8; // r8d
  __int64 v9; // r10
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  unsigned int v18; // ecx
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // [rsp+40h] [rbp+8h] BYREF

  v4 = *(_WORD *)(a1 + 266) & 0xF;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v11 = v5 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
        {
          v16 = *(_QWORD **)a1;
          **(_QWORD **)a1 = 6;
          goto LABEL_12;
        }
        v12 = (unsigned __int16)*a2;
        v13 = *(_QWORD *)(a1 + 120);
        v14 = *(_QWORD *)(a1 + 112);
        v15 = *(_QWORD *)(a1 + 96);
        v23 = v12;
        v10 = LDIDecompress(v15, v14, *(unsigned __int16 *)(*(_QWORD *)(a1 + 136) + 4LL), v13, (__int64)&v23);
      }
      else
      {
        v19 = (unsigned __int16)*a2;
        v20 = *(_QWORD *)(a1 + 120);
        v21 = *(_QWORD *)(a1 + 112);
        v22 = *(_QWORD *)(a1 + 96);
        v23 = v19;
        v10 = QDIDecompress(v22, v21, *(unsigned __int16 *)(*(_QWORD *)(a1 + 136) + 4LL), v20, (__int64)&v23);
      }
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 96);
      v23 = *(_DWORD *)(a1 + 236);
      if ( *(_DWORD *)v6 != 1128875085 )
        goto LABEL_11;
      v7 = *(_DWORD *)(v6 + 16);
      v8 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 136) + 4LL);
      if ( v8 > v7 + 12
        || (unsigned int)NFM_Prepare(*(_QWORD *)(v6 + 24), *(_QWORD *)(a1 + 112), v8, *(_QWORD *)(a1 + 120), v7) )
      {
        goto LABEL_11;
      }
      v10 = NFM_Decompress(*(_QWORD *)(v9 + 24), &v23);
    }
    if ( v10 )
    {
LABEL_11:
      v16 = *(_QWORD **)a1;
      **(_QWORD **)a1 = 7;
LABEL_12:
      *((_DWORD *)v16 + 2) = 1;
      return 0;
    }
    *a2 = v23;
  }
  else
  {
    v18 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 136) + 4LL);
    if ( v18 > *(_DWORD *)(a1 + 236) )
      goto LABEL_11;
    *a2 = v18;
    memcpy_0(*(void **)(a1 + 120), *(const void **)(a1 + 112), v18);
  }
  return 1;
}

```

## disassembly

```asm
0x1800051d0  mov     [rsp+arg_8], rbx
0x1800051d5  push    rdi
0x1800051d6  sub     rsp, 30h
0x1800051da  mov     rbx, rcx
0x1800051dd  mov     rdi, rdx
0x1800051e0  movzx   ecx, word ptr [rcx+10Ah]
0x1800051e7  and     ecx, 0Fh
0x1800051ea  jz      loc_1800052C2
0x1800051f0  sub     ecx, 1
0x1800051f3  jnz     short loc_180005251
0x1800051f5  mov     r10, [rbx+60h]
0x1800051f9  mov     eax, [rbx+0ECh]
0x1800051ff  mov     [rsp+38h+arg_0], eax
0x180005203  cmp     dword ptr [r10], 4349444Dh
0x18000520a  jnz     loc_180005295
0x180005210  mov     rax, [rbx+88h]
0x180005217  mov     ecx, [r10+10h]
0x18000521b  movzx   r8d, word ptr [rax+4]
0x180005220  lea     eax, [rcx+0Ch]
0x180005223  cmp     r8d, eax
0x180005226  ja      short loc_180005295
0x180005228  mov     r9, [rbx+78h]
0x18000522c  mov     rdx, [rbx+70h]
0x180005230  mov     dword ptr [rsp+38h+var_18], ecx
0x180005234  mov     rcx, [r10+18h]
0x180005238  call    NFM_Prepare
0x18000523d  test    eax, eax
0x18000523f  jnz     short loc_180005295
0x180005241  mov     rcx, [r10+18h]
0x180005245  lea     rdx, [rsp+38h+arg_0]
0x18000524a  call    NFM_Decompress
0x18000524f  jmp     short loc_180005291
0x180005251  sub     ecx, 1
0x180005254  jz      loc_1800052F6
0x18000525a  cmp     ecx, 1
0x18000525d  jnz     loc_1800052EA
0x180005263  movzx   eax, word ptr [rdx]
0x180005266  mov     r9, [rbx+78h]
0x18000526a  mov     rdx, [rbx+70h]
0x18000526e  mov     rcx, [rbx+60h]
0x180005272  mov     [rsp+38h+arg_0], eax
0x180005276  mov     rax, [rbx+88h]
0x18000527d  movzx   r8d, word ptr [rax+4]
0x180005282  lea     rax, [rsp+38h+arg_0]
0x180005287  mov     [rsp+38h+var_18], rax
0x18000528c  call    LDIDecompress
0x180005291  test    eax, eax
0x180005293  jz      short loc_1800052B3
0x180005295  mov     rax, [rbx]
0x180005298  mov     qword ptr [rax], 7
0x18000529f  mov     dword ptr [rax+8], 1
0x1800052a6  xor     eax, eax
0x1800052a8  mov     rbx, [rsp+38h+arg_8]
0x1800052ad  add     rsp, 30h
0x1800052b1  pop     rdi
0x1800052b2  retn
0x1800052b3  movzx   eax, word ptr [rsp+38h+arg_0]
0x1800052b8  mov     [rdi], ax
0x1800052bb  mov     eax, 1
0x1800052c0  jmp     short loc_1800052A8
0x1800052c2  mov     rax, [rbx+88h]
0x1800052c9  movzx   ecx, word ptr [rax+4]
0x1800052cd  cmp     ecx, [rbx+0ECh]
0x1800052d3  ja      short loc_180005295
0x1800052d5  mov     [rdx], cx
0x1800052d8  mov     r8d, ecx; Size
0x1800052db  mov     rdx, [rbx+70h]; Src
0x1800052df  mov     rcx, [rbx+78h]; void *
0x1800052e3  call    memcpy_0
0x1800052e8  jmp     short loc_1800052BB
0x1800052ea  mov     rax, [rbx]
0x1800052ed  mov     qword ptr [rax], 6
0x1800052f4  jmp     short loc_18000529F
0x1800052f6  movzx   eax, word ptr [rdx]
0x1800052f9  mov     r9, [rbx+78h]
0x1800052fd  mov     rdx, [rbx+70h]
0x180005301  mov     rcx, [rbx+60h]
0x180005305  mov     [rsp+38h+arg_0], eax
0x180005309  mov     rax, [rbx+88h]
0x180005310  movzx   r8d, word ptr [rax+4]
0x180005315  lea     rax, [rsp+38h+arg_0]
0x18000531a  mov     [rsp+38h+var_18], rax
0x18000531f  call    QDIDecompress
0x180005324  jmp     loc_180005291
```
