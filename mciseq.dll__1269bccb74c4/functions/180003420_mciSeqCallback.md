# mciSeqCallback

- ea: `0x180003420`
- end: `0x180003517`
- name: `mciSeqCallback`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003420`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x1800034d2`
- `USER32!PostThreadMessageW` at `0x180003508`
- `USER32!PostThreadMessageW` at `0x1800034d2`
- `USER32!PostThreadMessageW` at `0x180003508`

## pseudocode

```c
void __fastcall mciSeqCallback(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v5; // edx
  UINT v6; // edx
  __int64 v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int16 v13; // ax

  if ( !a2 )
  {
    *(_WORD *)(a4 + 12) &= 0xFFF9u;
    v6 = 1026;
    *(_WORD *)(a4 + 12) |= 1u;
LABEL_17:
    PostThreadMessageW(*(_DWORD *)(a3 + 304), v6, 0, 0);
    return;
  }
  v5 = a2 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      return;
    v6 = 1024;
    goto LABEL_17;
  }
  v7 = *(unsigned int *)(a3 + 296);
  if ( (_DWORD)v7 != -1 )
  {
    v8 = (_DWORD *)((qword_18000A628[2 * v7] + 16)
                  & ((unsigned __int128)-(__int128)(unsigned __int64)qword_18000A628[2 * v7] >> 64));
    v9 = 0;
    if ( v8 )
    {
      do
      {
        if ( (_DWORD)a4 == v9 )
          break;
        v10 = *((_QWORD *)v8 - 2);
        if ( !v10 )
          return;
        ++v9;
        v8 = (_DWORD *)(v10 + 16);
      }
      while ( v8 );
      if ( v8 )
      {
        v11 = 0;
        v8[2] = *v8;
        do
        {
          v12 = *(_QWORD *)&v8[2 * v11 + 4];
          v13 = *(_WORD *)(v12 + 12);
          if ( (v13 & 1) == 0 )
          {
            *(_WORD *)(v12 + 12) = v13 | 1;
            PostThreadMessageW(*(_DWORD *)(a3 + 304), 0x402u, 0, 0);
          }
          ++v11;
        }
        while ( v11 != 2 );
      }
    }
  }
}

```

## disassembly

```asm
0x180003420  push    rbx
0x180003422  push    rbp
0x180003423  push    rsi
0x180003424  push    rdi
0x180003425  sub     rsp, 28h
0x180003429  mov     rbp, r8
0x18000342c  test    edx, edx
0x18000342e  jz      loc_1800034E3
0x180003434  sub     edx, 1
0x180003437  jz      short loc_18000344C
0x180003439  cmp     edx, 1
0x18000343c  jnz     loc_18000350E
0x180003442  mov     edx, 400h
0x180003447  jmp     loc_1800034FC
0x18000344c  mov     eax, [r8+128h]
0x180003453  cmp     eax, 0FFFFFFFFh
0x180003456  jz      loc_18000350E
0x18000345c  add     rax, rax
0x18000345f  lea     rcx, qword_18000A628
0x180003466  mov     rcx, [rcx+rax*8]
0x18000346a  lea     rax, [rcx+10h]
0x18000346e  neg     rcx
0x180003471  sbb     rbx, rbx
0x180003474  and     rbx, rax
0x180003477  mov     eax, 0
0x18000347c  jz      loc_18000350E
0x180003482  lea     esi, [rax+1]
0x180003485  cmp     r9d, eax
0x180003488  jz      short loc_1800034A0
0x18000348a  test    rbx, rbx
0x18000348d  jz      short loc_18000350E
0x18000348f  mov     rbx, [rbx-10h]
0x180003493  test    rbx, rbx
0x180003496  jz      short loc_18000350E
0x180003498  add     eax, esi
0x18000349a  add     rbx, 10h
0x18000349e  jnz     short loc_180003485
0x1800034a0  test    rbx, rbx
0x1800034a3  jz      short loc_18000350E
0x1800034a5  mov     eax, [rbx]
0x1800034a7  xor     edi, edi
0x1800034a9  mov     [rbx+8], eax
0x1800034ac  mov     rcx, [rbx+rdi*8+10h]
0x1800034b1  movzx   eax, word ptr [rcx+0Ch]
0x1800034b5  test    sil, al
0x1800034b8  jnz     short loc_1800034D8
0x1800034ba  or      ax, si
0x1800034bd  xor     r9d, r9d; lParam
0x1800034c0  mov     [rcx+0Ch], ax
0x1800034c4  xor     r8d, r8d; wParam
0x1800034c7  mov     ecx, [rbp+130h]; idThread
0x1800034cd  mov     edx, 402h; Msg
0x1800034d2  call    cs:__imp_PostThreadMessageW
0x1800034d8  add     rdi, rsi
0x1800034db  cmp     rdi, 2
0x1800034df  jnz     short loc_1800034AC
0x1800034e1  jmp     short loc_18000350E
0x1800034e3  mov     eax, 0FFF9h
0x1800034e8  mov     esi, 1
0x1800034ed  and     [r9+0Ch], ax
0x1800034f2  mov     edx, 402h; Msg
0x1800034f7  or      [r9+0Ch], si
0x1800034fc  mov     ecx, [rbp+130h]; idThread
0x180003502  xor     r9d, r9d; lParam
0x180003505  xor     r8d, r8d; wParam
0x180003508  call    cs:__imp_PostThreadMessageW
0x18000350e  add     rsp, 28h
0x180003512  pop     rdi
0x180003513  pop     rsi
0x180003514  pop     rbp
0x180003515  pop     rbx
0x180003516  retn
```
