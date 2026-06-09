# FDIReadCFDATAEntry

- ea: `0x180004f94`
- end: `0x18000512f`
- name: `FDIReadCFDATAEntry`
- size: `411`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004e64`

## callees

- `0x180004f94`
- `0x180005140`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall FDIReadCFDATAEntry(__int64 a1, unsigned int a2)
{
  __int64 v3; // rdi
  int v4; // eax
  int v5; // eax
  __int64 v6; // r14
  int v7; // ebp
  unsigned int v8; // eax
  int v9; // r8d
  _QWORD *v11; // rax
  __int16 v12; // ax
  __int64 v13; // rax

  v3 = a2;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 32))(
         *(_QWORD *)(a1 + 208),
         *(_QWORD *)(a1 + 136),
         *(unsigned int *)(a1 + 256));
  if ( v4 )
  {
    if ( *(_DWORD *)(a1 + 256) == v4
      && *(unsigned __int16 *)(*(_QWORD *)(a1 + 136) + 4LL) + (unsigned int)v3 <= *(_DWORD *)(a1 + 240)
      && (v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(a1 + 32))(*(_QWORD *)(a1 + 208), v3 + *(_QWORD *)(a1 + 112)),
          v6 = *(_QWORD *)(a1 + 136),
          v7 = *(unsigned __int16 *)(v6 + 4),
          v7 == v5)
      && (!*(_DWORD *)v6
       || (v8 = CSUMCompute(v3 + *(_QWORD *)(a1 + 112), *(unsigned __int16 *)(v6 + 4), 0),
           (unsigned int)CSUMCompute(v6 + 4, (unsigned int)(*(_DWORD *)(a1 + 256) - 4), v8) == *(_DWORD *)v6)) )
    {
      *(_WORD *)(v6 + 4) = v3 + v7;
      if ( (_DWORD)v3 || (v9 = 0, !*(_WORD *)(*(_QWORD *)(a1 + 136) + 6LL)) )
        v9 = 1;
      if ( !*(_QWORD *)(a1 + 80) )
        return 1;
      *(_DWORD *)(a1 + 2136) = 2;
      *(_QWORD *)(a1 + 2144) = *(_QWORD *)(a1 + 104);
      v12 = *(_WORD *)(a1 + 256) - 8;
      *(_WORD *)(a1 + 2160) = v12;
      v13 = v12 ? *(_QWORD *)(a1 + 136) + 8LL : 0LL;
      *(_QWORD *)(a1 + 2152) = v13;
      *(_QWORD *)(a1 + 2168) = v3 + *(_QWORD *)(a1 + 112);
      *(_WORD *)(a1 + 2176) = *(_WORD *)(*(_QWORD *)(a1 + 136) + 4LL);
      *(_DWORD *)(a1 + 2180) = v9;
      *(_WORD *)(a1 + 2184) = v3;
      if ( (*(unsigned int (**)(void))(a1 + 80))() != -1 )
        return 1;
      v11 = *(_QWORD **)a1;
      **(_QWORD **)a1 = 11;
    }
    else
    {
      v11 = *(_QWORD **)a1;
      **(_QWORD **)a1 = 4;
    }
  }
  else
  {
    v11 = *(_QWORD **)a1;
    **(_QWORD **)a1 = 12;
  }
  *((_DWORD *)v11 + 2) = 1;
  return 0;
}

```

## disassembly

```asm
0x180004f94  push    rbx
0x180004f96  push    rbp
0x180004f97  push    rsi
0x180004f98  push    rdi
0x180004f99  push    r12
0x180004f9b  push    r14
0x180004f9d  push    r15
0x180004f9f  sub     rsp, 20h
0x180004fa3  mov     r8d, [rcx+100h]
0x180004faa  mov     rbx, rcx
0x180004fad  mov     edi, edx
0x180004faf  mov     rdx, [rcx+88h]
0x180004fb6  mov     rcx, [rcx+0D0h]
0x180004fbd  mov     rax, [rbx+20h]
0x180004fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc6  xor     r12d, r12d
0x180004fc9  test    eax, eax
0x180004fcb  jz      loc_1800050A3
0x180004fd1  cmp     [rbx+100h], eax
0x180004fd7  jnz     loc_180005086
0x180004fdd  mov     rax, [rbx+88h]
0x180004fe4  movzx   r8d, word ptr [rax+4]
0x180004fe9  lea     eax, [r8+rdi]
0x180004fed  cmp     eax, [rbx+0F0h]
0x180004ff3  ja      loc_180005086
0x180004ff9  mov     rdx, [rbx+70h]
0x180004ffd  mov     rcx, [rbx+0D0h]
0x180005004  add     rdx, rdi
0x180005007  mov     rax, [rbx+20h]
0x18000500b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005010  mov     r14, [rbx+88h]
0x180005017  lea     rsi, [r14+4]
0x18000501b  movzx   ebp, word ptr [rsi]
0x18000501e  cmp     ebp, eax
0x180005020  jnz     short loc_180005086
0x180005022  cmp     [r14], r12d
0x180005025  jz      short loc_180005051
0x180005027  mov     rcx, [rbx+70h]
0x18000502b  xor     r8d, r8d
0x18000502e  add     rcx, rdi
0x180005031  mov     edx, ebp
0x180005033  call    CSUMCompute
0x180005038  mov     edx, [rbx+100h]
0x18000503e  mov     r8d, eax
0x180005041  sub     edx, 4
0x180005044  mov     rcx, rsi
0x180005047  call    CSUMCompute
0x18000504c  cmp     eax, [r14]
0x18000504f  jnz     short loc_180005086
0x180005051  lea     eax, [rdi+rbp]
0x180005054  mov     [rsi], ax
0x180005057  test    edi, edi
0x180005059  jnz     short loc_18000509B
0x18000505b  mov     rax, [rbx+88h]
0x180005062  mov     r8d, r12d
0x180005065  cmp     [rax+6], r12w
0x18000506a  jz      short loc_18000509B
0x18000506c  cmp     [rbx+50h], r12
0x180005070  jnz     short loc_1800050AF
0x180005072  mov     eax, 1
0x180005077  add     rsp, 20h
0x18000507b  pop     r15
0x18000507d  pop     r14
0x18000507f  pop     r12
0x180005081  pop     rdi
0x180005082  pop     rsi
0x180005083  pop     rbp
0x180005084  pop     rbx
0x180005085  retn
0x180005086  mov     rax, [rbx]
0x180005089  mov     qword ptr [rax], 4
0x180005090  mov     dword ptr [rax+8], 1
0x180005097  xor     eax, eax
0x180005099  jmp     short loc_180005077
0x18000509b  mov     r8d, 1
0x1800050a1  jmp     short loc_18000506C
0x1800050a3  mov     rax, [rbx]
0x1800050a6  mov     qword ptr [rax], 0Ch
0x1800050ad  jmp     short loc_180005090
0x1800050af  lea     rcx, [rbx+858h]
0x1800050b6  mov     edx, 8
0x1800050bb  mov     dword ptr [rcx], 2
0x1800050c1  mov     rax, [rbx+68h]
0x1800050c5  mov     [rcx+8], rax
0x1800050c9  movzx   eax, word ptr [rbx+100h]
0x1800050d0  sub     ax, dx
0x1800050d3  mov     [rcx+18h], ax
0x1800050d7  jz      short loc_1800050E5
0x1800050d9  mov     rax, [rbx+88h]
0x1800050e0  add     rax, rdx
0x1800050e3  jmp     short loc_1800050E8
0x1800050e5  mov     rax, r12
0x1800050e8  mov     [rcx+10h], rax
0x1800050ec  mov     rdx, [rbx+70h]
0x1800050f0  add     rdx, rdi
0x1800050f3  mov     [rcx+20h], rdx
0x1800050f7  mov     rax, [rbx+88h]
0x1800050fe  movzx   edx, word ptr [rax+4]
0x180005102  mov     [rcx+28h], dx
0x180005106  mov     [rcx+2Ch], r8d
0x18000510a  mov     [rcx+30h], di
0x18000510e  mov     rax, [rbx+50h]
0x180005112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005117  cmp     eax, 0FFFFFFFFh
0x18000511a  jnz     loc_180005072
0x180005120  mov     rax, [rbx]
0x180005123  mov     qword ptr [rax], 0Bh
0x18000512a  jmp     loc_180005090
```
