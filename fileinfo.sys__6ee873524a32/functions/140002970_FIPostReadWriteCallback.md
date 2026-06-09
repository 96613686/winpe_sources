# FIPostReadWriteCallback

- ea: `0x140002970`
- end: `0x140002a72`
- name: `FIPostReadWriteCallback`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001570`
- `0x140002970`

## import_xrefs

- `ntoskrnl!PfFileInfoNotify` at `0x140002a5a`
- `ntoskrnl!PfFileInfoNotify` at `0x140002a5a`

## pseudocode

```c
__int64 __fastcall FIPostReadWriteCallback(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v4; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  __int128 *v11; // [rsp+30h] [rbp-38h]
  __int128 v12; // [rsp+38h] [rbp-30h] BYREF
  __int128 v13; // [rsp+48h] [rbp-20h]
  struct _KTHREAD *CurrentThread; // [rsp+58h] [rbp-10h]

  v4 = *(_QWORD *)(a2 + 32);
  v11 = 0;
  CurrentThread = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  if ( *(_QWORD *)(qword_140009A00 + 24) )
    FIETWLogOperationEnd(a1);
  if ( (a4 & 1) == 0 && *(int *)(a1 + 24) >= 0 )
  {
    if ( *(_QWORD *)(a1 + 32) )
    {
      v7 = *(_QWORD *)(a1 + 16);
      if ( (*(_BYTE *)(v7 + 5) & 6) != 6 && (*(_DWORD *)v7 & 3) == 0 && (*(_DWORD *)(v4 + 80) & 8) == 0 )
      {
        *((_QWORD *)&v10 + 1) = 1;
        v11 = &v12;
        *(_QWORD *)&v10 = 0x40000000FLL;
        *(_QWORD *)&v12 = v4;
        *((_QWORD *)&v13 + 1) = *(_QWORD *)(v4 + 24);
        CurrentThread = *(struct _KTHREAD **)(a1 + 8);
        if ( !CurrentThread )
          CurrentThread = KeGetCurrentThread();
        *(_QWORD *)&v13 = *(unsigned int *)(a1 + 32);
        v8 = *(_QWORD *)(a1 + 16);
        if ( *(_BYTE *)(v8 + 4) != 3 )
          DWORD1(v13) = 1;
        *((_QWORD *)&v12 + 1) = *(_QWORD *)(v8 + 40);
        PfFileInfoNotify(&v10);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140002970  push    rbp
0x140002972  push    rbx
0x140002973  push    rsi
0x140002974  push    rdi
0x140002975  mov     rbp, rsp
0x140002978  sub     rsp, 68h
0x14000297c  mov     rdi, [rdx+20h]
0x140002980  xor     eax, eax
0x140002982  mov     [rbp+var_38], rax
0x140002986  xorps   xmm1, xmm1
0x140002989  mov     [rbp+var_10], rax
0x14000298d  xorps   xmm0, xmm0
0x140002990  mov     rax, cs:qword_140009A00
0x140002997  mov     esi, r9d
0x14000299a  movups  [rbp+var_48], xmm0
0x14000299e  mov     rbx, rcx
0x1400029a1  movups  [rbp+var_30], xmm1
0x1400029a5  movups  [rbp+var_20], xmm1
0x1400029a9  mov     rdx, [rax+18h]
0x1400029ad  test    rdx, rdx
0x1400029b0  jz      short loc_1400029B7
0x1400029b2  call    FIETWLogOperationEnd
0x1400029b7  mov     edx, 1
0x1400029bc  test    dl, sil
0x1400029bf  jnz     loc_140002A66
0x1400029c5  cmp     dword ptr [rbx+18h], 0
0x1400029c9  jl      loc_140002A66
0x1400029cf  cmp     qword ptr [rbx+20h], 0
0x1400029d4  jz      loc_140002A66
0x1400029da  mov     rcx, [rbx+10h]
0x1400029de  mov     al, [rcx+5]
0x1400029e1  and     al, 6
0x1400029e3  cmp     al, 6
0x1400029e5  jz      short loc_140002A66
0x1400029e7  mov     eax, [rcx]
0x1400029e9  test    al, 3
0x1400029eb  jnz     short loc_140002A66
0x1400029ed  mov     eax, [rdi+50h]
0x1400029f0  test    al, 8
0x1400029f2  jnz     short loc_140002A66
0x1400029f4  lea     rax, [rbp+var_30]
0x1400029f8  mov     qword ptr [rbp+var_48+8], rdx
0x1400029fc  mov     [rbp+var_38], rax
0x140002a00  mov     dword ptr [rbp+var_48], 0Fh
0x140002a07  mov     dword ptr [rbp+var_48+4], 4
0x140002a0e  mov     qword ptr [rbp+var_30], rdi
0x140002a12  mov     rax, [rdi+18h]
0x140002a16  mov     qword ptr [rbp+var_20+8], rax
0x140002a1a  mov     rax, [rbx+8]
0x140002a1e  mov     [rbp+var_10], rax
0x140002a22  test    rax, rax
0x140002a25  jnz     short loc_140002A34
0x140002a27  mov     rax, gs:188h
0x140002a30  mov     [rbp+var_10], rax
0x140002a34  mov     eax, [rbx+20h]
0x140002a37  mov     dword ptr [rbp+var_20], eax
0x140002a3a  mov     rax, [rbx+10h]
0x140002a3e  cmp     byte ptr [rax+4], 3
0x140002a42  mov     dword ptr [rbp+var_20+4], 0
0x140002a49  jz      short loc_140002A4E
0x140002a4b  mov     dword ptr [rbp+var_20+4], edx
0x140002a4e  mov     rax, [rax+28h]
0x140002a52  lea     rcx, [rbp+var_48]
0x140002a56  mov     qword ptr [rbp+var_30+8], rax
0x140002a5a  call    cs:__imp_PfFileInfoNotify
0x140002a61  nop     dword ptr [rax+rax+00h]
0x140002a66  xor     eax, eax
0x140002a68  add     rsp, 68h
0x140002a6c  pop     rdi
0x140002a6d  pop     rsi
0x140002a6e  pop     rbx
0x140002a6f  pop     rbp
0x140002a70  retn
```
