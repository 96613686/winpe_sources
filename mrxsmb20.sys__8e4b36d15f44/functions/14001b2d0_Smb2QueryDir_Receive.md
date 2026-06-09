# Smb2QueryDir_Receive

- ea: `0x14001b2d0`
- end: `0x14001b4b8`
- name: `Smb2QueryDir_Receive`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x14001b2d0`
- `0x14001c040`
- `0x1400372c0`

## import_xrefs

- `mrxsmb!RDR_PERF_ENTER` at `0x14001b2f6`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001b2f6`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001b368`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001b368`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001b3db`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001b3db`

## pseudocode

```c
__int64 __fastcall Smb2QueryDir_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  unsigned int v7; // r14d
  __int64 v9; // rcx
  __int64 v10; // rdi
  unsigned int v12; // r15d
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // rcx

  v7 = *(_DWORD *)(a3 + 16);
  v9 = a2 + 880;
  v10 = a2;
  LOBYTE(a2) = 35;
  v12 = 0;
  RDR_PERF_ENTER(v9, a2);
  if ( v7 )
  {
    *a6 = a5;
    goto LABEL_14;
  }
  if ( a4 < 0x48 )
  {
    v7 = -1073741629;
    *a6 = a5;
    goto LABEL_14;
  }
  v13 = *(unsigned __int16 *)(a7 + 66);
  if ( v13 < 0x48 )
  {
    v7 = -1073741629;
    *a6 = a5;
    goto LABEL_14;
  }
  if ( v13 > a5 || (v14 = *(unsigned int *)(a7 + 68), (unsigned int)v14 > a5) || (unsigned int)v14 + v13 > a5 )
  {
    *a6 = a5;
LABEL_18:
    v7 = -1073741629;
    goto LABEL_14;
  }
  if ( !(_DWORD)v14 || (unsigned int)v14 > *(_DWORD *)(v10 + 744) )
  {
    *a6 = a5;
    goto LABEL_18;
  }
  if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v14) + 64) & 1) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                    * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                   % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                               + 1488LL))
                                                    + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                    + 84));
  *(_DWORD *)(v10 + 748) = *(_DWORD *)(a7 + 68);
  v15 = *(_DWORD *)(a7 + 68);
  v16 = *(unsigned __int16 *)(a7 + 66);
  if ( (unsigned int)v16 + v15 > a4 )
  {
    v12 = -1073741802;
    *a6 = v16;
  }
  else
  {
    memmove(*(void **)(a1 + 1736), (const void *)(a7 + v16), v15);
    *a6 = a5;
    if ( *(_BYTE *)(a1 + 2412) )
    {
      SmbCeUpdateExchangeStatus(a1, 3225485313LL);
      _InterlockedOr((volatile signed __int32 *)(a1 + 68), 0x10000u);
    }
  }
LABEL_14:
  SmbCseUpdateBufferContextStatus(v10, v7);
  return v12;
}

```

## disassembly

```asm
0x14001b2d0  push    rbp
0x14001b2d2  push    rdi
0x14001b2d3  push    r13
0x14001b2d5  push    r14
0x14001b2d7  push    r15
0x14001b2d9  sub     rsp, 20h
0x14001b2dd  mov     r14d, [r8+10h]
0x14001b2e1  mov     r13, rcx
0x14001b2e4  lea     rcx, [rdx+370h]
0x14001b2eb  mov     rdi, rdx
0x14001b2ee  mov     dl, 23h ; '#'
0x14001b2f0  mov     ebp, r9d
0x14001b2f3  xor     r15d, r15d
0x14001b2f6  call    cs:__imp_RDR_PERF_ENTER
0x14001b2fd  nop     dword ptr [rax+rax+00h]
0x14001b302  test    r14d, r14d
0x14001b305  jnz     loc_14001B3F8
0x14001b30b  cmp     ebp, 48h ; 'H'
0x14001b30e  jb      loc_14001B45B
0x14001b314  mov     [rsp+48h+arg_8], rbx
0x14001b319  mov     rbx, [rsp+48h+arg_30]
0x14001b321  movzx   eax, word ptr [rbx+42h]
0x14001b325  cmp     eax, 48h ; 'H'
0x14001b328  jb      loc_14001B471
0x14001b32e  mov     [rsp+48h+arg_10], rsi
0x14001b333  mov     esi, [rsp+48h+arg_20]
0x14001b337  cmp     eax, esi
0x14001b339  ja      loc_14001B449
0x14001b33f  mov     ecx, [rbx+44h]
0x14001b342  cmp     ecx, esi
0x14001b344  ja      loc_14001B449
0x14001b34a  add     eax, ecx
0x14001b34c  cmp     eax, esi
0x14001b34e  ja      loc_14001B449
0x14001b354  test    ecx, ecx
0x14001b356  jz      loc_14001B4AF
0x14001b35c  cmp     ecx, [rdi+2E8h]
0x14001b362  ja      loc_14001B4AF
0x14001b368  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001b36f  nop     dword ptr [rax+rax+00h]
0x14001b374  test    byte ptr [rax+40h], 1
0x14001b378  jnz     loc_14001B414
0x14001b37e  mov     eax, [rbx+44h]
0x14001b381  mov     [rdi+2ECh], eax
0x14001b387  mov     edx, [rbx+44h]
0x14001b38a  movzx   ecx, word ptr [rbx+42h]
0x14001b38e  lea     eax, [rcx+rdx]
0x14001b391  cmp     eax, ebp
0x14001b393  ja      short loc_14001B405
0x14001b395  mov     r8d, edx; Size
0x14001b398  lea     rdx, [rbx+rcx]; Src
0x14001b39c  mov     rcx, [r13+6C8h]; void *
0x14001b3a3  call    memmove
0x14001b3a8  mov     rax, [rsp+48h+arg_28]
0x14001b3ad  mov     [rax], esi
0x14001b3af  cmp     [r13+96Ch], r15b
0x14001b3b6  jnz     loc_14001B487
0x14001b3bc  mov     rsi, [rsp+48h+arg_10]
0x14001b3c1  mov     rbx, [rsp+48h+arg_8]
0x14001b3c6  mov     dword ptr [rsp+48h+arg_0], r14d
0x14001b3cb  mov     rcx, rdi
0x14001b3ce  mov     dword ptr [rsp+48h+arg_0+4], 0
0x14001b3d6  mov     rdx, [rsp+48h+arg_0]
0x14001b3db  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001b3e2  nop     dword ptr [rax+rax+00h]
0x14001b3e7  mov     eax, r15d
0x14001b3ea  add     rsp, 20h
0x14001b3ee  pop     r15
0x14001b3f0  pop     r14
0x14001b3f2  pop     r13
0x14001b3f4  pop     rdi
0x14001b3f5  pop     rbp
0x14001b3f6  retn
0x14001b3f8  mov     rcx, [rsp+48h+arg_28]
0x14001b3fd  mov     eax, [rsp+48h+arg_20]
0x14001b401  mov     [rcx], eax
0x14001b403  jmp     short loc_14001B3C6
0x14001b405  mov     rax, [rsp+48h+arg_28]
0x14001b40a  mov     r15d, 0C0000016h
0x14001b410  mov     [rax], ecx
0x14001b412  jmp     short loc_14001B3BC
0x14001b414  mov     rax, [r13+58h]
0x14001b418  xor     edx, edx
0x14001b41a  mov     r8, [rax+1A8h]
0x14001b421  mov     eax, gs:1A4h
0x14001b429  div     dword ptr [r8+5D0h]
0x14001b430  mov     rax, [r8+5C8h]
0x14001b437  lea     rdx, [rdx+rdx*2]
0x14001b43b  shl     rdx, 6
0x14001b43f  lock inc dword ptr [rdx+rax+54h]
0x14001b444  jmp     loc_14001B37E
0x14001b449  mov     rcx, [rsp+48h+arg_28]
0x14001b44e  mov     [rcx], esi
0x14001b450  mov     r14d, 0C00000C3h
0x14001b456  jmp     loc_14001B3BC
0x14001b45b  mov     rcx, [rsp+48h+arg_28]
0x14001b460  mov     r14d, 0C00000C3h
0x14001b466  mov     eax, [rsp+48h+arg_20]
0x14001b46a  mov     [rcx], eax
0x14001b46c  jmp     loc_14001B3C6
0x14001b471  mov     rcx, [rsp+48h+arg_28]
0x14001b476  mov     r14d, 0C00000C3h
0x14001b47c  mov     eax, [rsp+48h+arg_20]
0x14001b480  mov     [rcx], eax
0x14001b482  jmp     loc_14001B3C1
0x14001b487  mov     dword ptr [rsp+48h+arg_0], 0C0410001h
0x14001b48f  mov     rcx, r13
0x14001b492  mov     dword ptr [rsp+48h+arg_0+4], r15d
0x14001b497  mov     rdx, [rsp+48h+arg_0]
0x14001b49c  call    SmbCeUpdateExchangeStatus
0x14001b4a1  lock or dword ptr [r13+44h], 10000h
0x14001b4aa  jmp     loc_14001B3BC
0x14001b4af  mov     rax, [rsp+48h+arg_28]
0x14001b4b4  mov     [rax], esi
0x14001b4b6  jmp     short loc_14001B450
```
