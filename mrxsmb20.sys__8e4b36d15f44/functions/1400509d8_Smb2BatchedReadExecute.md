# Smb2BatchedReadExecute

- ea: `0x1400509d8`
- end: `0x140050b8a`
- name: `Smb2BatchedReadExecute`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400506bc`

## callees

- `0x140021970`
- `0x14002fb78`
- `0x1400509d8`

## import_xrefs

- `mrxsmb!SmbCeInitiateExchange` at `0x140050b65`
- `mrxsmb!SmbCeInitiateExchange` at `0x140050b65`
- `mrxsmb!SmbCeInitializeExchange` at `0x140050a95`
- `mrxsmb!SmbCeInitializeExchange` at `0x140050a95`

## pseudocode

```c
__int64 __fastcall Smb2BatchedReadExecute(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rax
  __int64 v7; // r11
  int v9; // r15d
  __int64 v10; // rsi
  __int64 v11; // r13
  __int64 v12; // r12
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // edi
  __int64 result; // rax
  __int64 v17; // rax
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF
  __int64 v22; // [rsp+88h] [rbp+48h]
  unsigned int v23; // [rsp+90h] [rbp+50h]

  v23 = a3;
  v22 = a2;
  v5 = *(_QWORD *)(a1 + 72);
  v7 = *(_QWORD *)(a1 + 56);
  v9 = *(_DWORD *)(a4 + 12);
  v21 = 0;
  v10 = *(_QWORD *)(v7 + 120);
  v11 = *(_QWORD *)(v7 + 136);
  v12 = *(_QWORD *)(*(_QWORD *)(v5 + 40) + 40LL);
  v13 = *(_QWORD *)(v12 + 416);
  if ( (*(_DWORD *)(v13 + 4) & 8) == 0 )
  {
    v14 = *(_QWORD *)(v13 + 384);
    if ( *(_QWORD *)(v14 + 576) )
    {
      if ( (*(_DWORD *)(v14 + 4) & 1) != 0 && (*(_BYTE *)(v13 + 4) & 3) == 0 )
        Smb2TryToEstablishMultipleChannelsImpl((PVOID)v13);
    }
  }
  v15 = ((unsigned int)(*(_DWORD *)(a4 + 12) - 1) >> 16) + 1;
  result = SmbCeInitializeExchange(&v21, a1, 0, 0, 0, v12, 8 * v15 + 2496, &ReadDispatch);
  if ( !(_DWORD)result )
  {
    v17 = *(_QWORD *)(a1 + 856);
    if ( v17 )
      *(_DWORD *)(v17 + 408) = v9;
    v18 = (_QWORD *)v21;
    v19 = a5;
    *(_QWORD *)(v21 + 2456) = v22;
    v20 = 16LL * v23 + 8;
    v18[308] = a4;
    v18[310] = v19;
    v18[309] = v19 + v20;
    *(_DWORD *)(v21 + 64) = 1;
    if ( v15 > 1 )
      _InterlockedOr((volatile signed __int32 *)(v21 + 68), 0x1000u);
    if ( (*(_BYTE *)(a1 + 522) & 8) != 0 )
      _InterlockedOr((volatile signed __int32 *)(v21 + 68), 0x40000u);
    *(_DWORD *)(v21 + 1044) = v15;
    *(_BYTE *)(v21 + 1040) = *(_BYTE *)(v10 + 77);
    InitializeReadExchangeBlockState(v21);
    if ( *(_BYTE *)(v10 + 77) == 1 )
      _InterlockedOr((volatile signed __int32 *)(v21 + 68), 0x40u);
    *(_QWORD *)(v21 + 504) = *(_QWORD *)(v11 + 96);
    return SmbCeInitiateExchange(v21);
  }
  return result;
}

```

## disassembly

```asm
0x1400509d8  mov     [rsp-38h+arg_18], rbx
0x1400509dd  mov     [rsp-38h+arg_10], r8d
0x1400509e2  mov     [rsp-38h+arg_8], rdx
0x1400509e7  push    rbp
0x1400509e8  push    rsi
0x1400509e9  push    rdi
0x1400509ea  push    r12
0x1400509ec  push    r13
0x1400509ee  push    r14
0x1400509f0  push    r15
0x1400509f2  mov     rbp, rsp
0x1400509f5  sub     rsp, 40h
0x1400509f9  mov     rax, [rcx+48h]
0x1400509fd  mov     rbx, rcx
0x140050a00  mov     r11, [rcx+38h]
0x140050a04  mov     r14, r9
0x140050a07  mov     r15d, [r9+0Ch]
0x140050a0b  mov     [rbp+arg_0], 0
0x140050a13  mov     r10, [rax+28h]
0x140050a17  mov     rsi, [r11+78h]
0x140050a1b  mov     r13, [r11+88h]
0x140050a22  mov     r12, [r10+28h]
0x140050a26  mov     rcx, [r12+1A0h]; pContext
0x140050a2e  mov     eax, [rcx+4]
0x140050a31  test    al, 8
0x140050a33  jnz     short loc_140050A58
0x140050a35  mov     rax, [rcx+180h]
0x140050a3c  cmp     qword ptr [rax+240h], 0
0x140050a44  jz      short loc_140050A58
0x140050a46  mov     eax, [rax+4]
0x140050a49  test    al, 1
0x140050a4b  jz      short loc_140050A58
0x140050a4d  test    byte ptr [rcx+4], 3
0x140050a51  jnz     short loc_140050A58
0x140050a53  call    Smb2TryToEstablishMultipleChannelsImpl
0x140050a58  mov     edi, [r14+0Ch]
0x140050a5c  lea     rcx, ReadDispatch
0x140050a63  mov     [rsp+40h+var_8], rcx
0x140050a68  dec     edi
0x140050a6a  shr     edi, 10h
0x140050a6d  lea     rcx, [rbp+arg_0]
0x140050a71  inc     edi
0x140050a73  xor     r9d, r9d
0x140050a76  xor     r8d, r8d
0x140050a79  mov     rdx, rbx
0x140050a7c  lea     eax, ds:9C0h[rdi*8]
0x140050a83  mov     [rsp+40h+var_10], eax
0x140050a87  mov     [rsp+40h+var_18], r12
0x140050a8c  mov     [rsp+40h+var_20], 0
0x140050a95  call    cs:__imp_SmbCeInitializeExchange
0x140050a9c  nop     dword ptr [rax+rax+00h]
0x140050aa1  test    eax, eax
0x140050aa3  jnz     loc_140050B71
0x140050aa9  mov     rax, [rbx+358h]
0x140050ab0  test    rax, rax
0x140050ab3  jz      short loc_140050ABC
0x140050ab5  mov     [rax+198h], r15d
0x140050abc  mov     rdx, [rbp+arg_0]
0x140050ac0  mov     rax, [rbp+arg_8]
0x140050ac4  mov     rcx, [rbp+arg_20]
0x140050ac8  mov     [rdx+998h], rax
0x140050acf  mov     eax, [rbp+arg_10]
0x140050ad2  shl     rax, 4
0x140050ad6  add     rax, 8
0x140050ada  mov     [rdx+9A0h], r14
0x140050ae1  add     rax, rcx
0x140050ae4  mov     [rdx+9B0h], rcx
0x140050aeb  mov     [rdx+9A8h], rax
0x140050af2  mov     rax, [rbp+arg_0]
0x140050af6  mov     dword ptr [rax+40h], 1
0x140050afd  cmp     edi, 1
0x140050b00  jbe     short loc_140050B0E
0x140050b02  mov     rax, [rbp+arg_0]
0x140050b06  lock or dword ptr [rax+44h], 1000h
0x140050b0e  test    byte ptr [rbx+20Ah], 8
0x140050b15  jz      short loc_140050B23
0x140050b17  mov     rax, [rbp+arg_0]
0x140050b1b  lock or dword ptr [rax+44h], 40000h
0x140050b23  mov     rax, [rbp+arg_0]
0x140050b27  mov     [rax+414h], edi
0x140050b2d  mov     cl, [rsi+4Dh]
0x140050b30  mov     rax, [rbp+arg_0]
0x140050b34  mov     [rax+410h], cl
0x140050b3a  mov     rcx, [rbp+arg_0]
0x140050b3e  call    InitializeReadExchangeBlockState
0x140050b43  cmp     byte ptr [rsi+4Dh], 1
0x140050b47  jnz     short loc_140050B52
0x140050b49  mov     rax, [rbp+arg_0]
0x140050b4d  lock or dword ptr [rax+44h], 40h
0x140050b52  mov     rcx, [r13+60h]
0x140050b56  mov     rax, [rbp+arg_0]
0x140050b5a  mov     [rax+1F8h], rcx
0x140050b61  mov     rcx, [rbp+arg_0]
0x140050b65  call    cs:__imp_SmbCeInitiateExchange
0x140050b6c  nop     dword ptr [rax+rax+00h]
0x140050b71  mov     rbx, [rsp+40h+arg_18]
0x140050b79  add     rsp, 40h
0x140050b7d  pop     r15
0x140050b7f  pop     r14
0x140050b81  pop     r13
0x140050b83  pop     r12
0x140050b85  pop     rdi
0x140050b86  pop     rsi
0x140050b87  pop     rbp
0x140050b88  retn
```
