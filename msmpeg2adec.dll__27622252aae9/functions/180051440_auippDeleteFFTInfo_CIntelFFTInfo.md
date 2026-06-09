# auippDeleteFFTInfo(CIntelFFTInfo *)

- ea: `0x180051440`
- end: `0x180051532`
- name: `?auippDeleteFFTInfo@@YAXPEAUCIntelFFTInfo@@@Z`
- size: `242`
- prototype: `void __fastcall(struct CIntelFFTInfo *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa40`
- `0x18004eba0`
- `0x1800511d0`

## callees

- `0x180051440`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051501`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051515`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051501`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051515`
- `mfperfhelper!__imp_ippsFree` at `0x1800514d0`
- `mfperfhelper!__imp_ippsFree` at `0x1800514f2`
- `mfperfhelper!__imp_ippsFree` at `0x1800514d0`
- `mfperfhelper!__imp_ippsFree` at `0x1800514f2`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x180051483`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x180051483`

## pseudocode

```c
void __fastcall auippDeleteFFTInfo(struct CIntelFFTInfo *Block)
{
  int v2; // ebx
  int v3; // esi
  __int64 v4; // rcx
  _QWORD *v5; // rsi
  int v6; // eax
  int v7; // ebx
  int v8; // ebp

  if ( Block )
  {
    if ( *((_QWORD *)Block + 1) )
    {
      v2 = 0;
      v3 = *((_DWORD *)Block + 1) - *(_DWORD *)Block + 1;
      if ( v3 > 0 )
      {
        do
        {
          v4 = *(_QWORD *)(32LL * (unsigned int)v2 + *((_QWORD *)Block + 1));
          if ( v4 )
            ippsFFTFree_R_32f(v4);
          ++v2;
        }
        while ( v2 < v3 );
      }
    }
    v5 = (_QWORD *)*((_QWORD *)Block + 1);
    if ( v5 )
    {
      v6 = *((_DWORD *)Block + 4);
      if ( v6 == 2 )
      {
        v7 = 0;
        v8 = *((_DWORD *)Block + 1) - *(_DWORD *)Block + 1;
        if ( v8 > 0 )
        {
          do
          {
            if ( v5[4 * (unsigned int)v7 + 2] )
              ippsFree();
            ++v7;
          }
          while ( v7 < v8 );
        }
      }
      else if ( v6 == 1 && v5[2] )
      {
        ippsFree();
      }
      free(v5);
    }
    free(Block);
  }
}

```

## disassembly

```asm
0x180051440  test    rcx, rcx
0x180051443  jz      locret_180051530
0x180051449  push    rdi
0x18005144a  sub     rsp, 20h
0x18005144e  cmp     qword ptr [rcx+8], 0
0x180051453  mov     rdi, rcx
0x180051456  mov     [rsp+28h+arg_10], rsi
0x18005145b  mov     [rsp+28h+arg_0], rbx
0x180051460  jz      short loc_180051495
0x180051462  mov     esi, [rcx+4]
0x180051465  xor     ebx, ebx
0x180051467  sub     esi, [rcx]
0x180051469  inc     esi
0x18005146b  test    esi, esi
0x18005146d  jle     short loc_180051495
0x18005146f  nop
0x180051470  mov     rax, [rdi+8]
0x180051474  mov     ecx, ebx
0x180051476  shl     rcx, 5
0x18005147a  mov     rcx, [rcx+rax]
0x18005147e  test    rcx, rcx
0x180051481  jz      short loc_18005148F
0x180051483  call    cs:__imp_ippsFFTFree_R_32f
0x18005148a  nop     dword ptr [rax+rax+00h]
0x18005148f  inc     ebx
0x180051491  cmp     ebx, esi
0x180051493  jl      short loc_180051470
0x180051495  mov     rsi, [rdi+8]
0x180051499  test    rsi, rsi
0x18005149c  jz      short loc_180051512
0x18005149e  mov     eax, [rdi+10h]
0x1800514a1  mov     [rsp+28h+arg_8], rbp
0x1800514a6  cmp     eax, 2
0x1800514a9  jnz     short loc_1800514E4
0x1800514ab  mov     ebp, [rdi+4]
0x1800514ae  xor     ebx, ebx
0x1800514b0  sub     ebp, [rdi]
0x1800514b2  inc     ebp
0x1800514b4  test    ebp, ebp
0x1800514b6  jle     short loc_1800514FE
0x1800514b8  nop     dword ptr [rax+rax+00000000h]
0x1800514c0  mov     eax, ebx
0x1800514c2  shl     rax, 5
0x1800514c6  mov     rcx, [rax+rsi+10h]
0x1800514cb  test    rcx, rcx
0x1800514ce  jz      short loc_1800514DC
0x1800514d0  call    cs:__imp_ippsFree
0x1800514d7  nop     dword ptr [rax+rax+00h]
0x1800514dc  inc     ebx
0x1800514de  cmp     ebx, ebp
0x1800514e0  jl      short loc_1800514C0
0x1800514e2  jmp     short loc_1800514FE
0x1800514e4  cmp     eax, 1
0x1800514e7  jnz     short loc_1800514FE
0x1800514e9  mov     rcx, [rsi+10h]
0x1800514ed  test    rcx, rcx
0x1800514f0  jz      short loc_1800514FE
0x1800514f2  call    cs:__imp_ippsFree
0x1800514f9  nop     dword ptr [rax+rax+00h]
0x1800514fe  mov     rcx, rsi; Block
0x180051501  call    cs:__imp_free
0x180051508  nop     dword ptr [rax+rax+00h]
0x18005150d  mov     rbp, [rsp+28h+arg_8]
0x180051512  mov     rcx, rdi; Block
0x180051515  call    cs:__imp_free
0x18005151c  nop     dword ptr [rax+rax+00h]
0x180051521  mov     rsi, [rsp+28h+arg_10]
0x180051526  mov     rbx, [rsp+28h+arg_0]
0x18005152b  add     rsp, 20h
0x18005152f  pop     rdi
0x180051530  retn
```
