# Smb2ChangeNotify_Receive

- ea: `0x14001e2c0`
- end: `0x14001e461`
- name: `Smb2ChangeNotify_Receive`
- size: `417`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001e2c0`
- `0x1400372c0`

## import_xrefs

- `mrxsmb!SmbCeUpdateExchangeHistory` at `0x14001e402`
- `mrxsmb!SmbCeUpdateExchangeHistory` at `0x14001e402`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e33e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e33e`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001e3a6`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001e3a6`

## pseudocode

```c
__int64 __fastcall Smb2ChangeNotify_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int v7; // edi
  unsigned int v9; // r14d
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // rcx

  v7 = *(_DWORD *)(a3 + 16);
  v9 = 0;
  if ( ((v7 + 0x80000000) & 0x80000000) != 0 || v7 == -2147483643 )
  {
    if ( a4 < 0x48 )
    {
      LODWORD(v15) = a5;
      v7 = -1073741629;
      goto LABEL_12;
    }
    v12 = *(_DWORD *)(a7 + 68);
    if ( v12 > *(_DWORD *)(a2 + 744) )
    {
      LODWORD(v15) = a5;
      v7 = -1073741629;
      goto LABEL_12;
    }
    v13 = *(unsigned __int16 *)(a7 + 66);
    if ( (unsigned int)v13 > a5 || v12 > a5 || (unsigned int)v13 + v12 > a5 )
    {
      v7 = -1073741629;
    }
    else
    {
      if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v13) + 64) & 1) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                        * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                       % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                               + 424LL)
                                                                                   + 1488LL))
                                                        + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                        + 84));
      *(_DWORD *)(a2 + 748) = *(_DWORD *)(a7 + 68);
      v14 = *(_DWORD *)(a7 + 68);
      v15 = *(unsigned __int16 *)(a7 + 66);
      if ( (unsigned int)v15 + v14 > a4 )
      {
        v9 = -1073741802;
        goto LABEL_12;
      }
      memmove(*(void **)(a1 + 1736), (const void *)(a7 + v15), v14);
    }
    LODWORD(v15) = a5;
  }
  else
  {
    LODWORD(v15) = a5;
  }
LABEL_12:
  *a6 = v15;
  SmbCseUpdateBufferContextStatus(a2, v7);
  if ( v7 && v7 != 259 )
  {
    _InterlockedExchange64((volatile __int64 *)(a1 + 16), v7);
    SmbCeUpdateExchangeHistory(a1, v7);
  }
  return v9;
}

```

## disassembly

```asm
0x14001e2c0  push    rdi
0x14001e2c2  push    r13
0x14001e2c4  push    r14
0x14001e2c6  sub     rsp, 20h
0x14001e2ca  mov     edi, [r8+10h]
0x14001e2ce  mov     r13, rcx
0x14001e2d1  mov     ecx, 80000000h
0x14001e2d6  mov     [rsp+38h+arg_10], rsi
0x14001e2db  xor     r14d, r14d
0x14001e2de  mov     [rsp+38h+arg_18], r15
0x14001e2e3  mov     r15d, r9d
0x14001e2e6  mov     rsi, rdx
0x14001e2e9  lea     eax, [rdi+rcx]
0x14001e2ec  test    ecx, eax
0x14001e2ee  jz      loc_14001E3CE
0x14001e2f4  cmp     r15d, 48h ; 'H'
0x14001e2f8  jb      loc_14001E410
0x14001e2fe  mov     [rsp+38h+arg_0], rbx
0x14001e303  mov     rbx, [rsp+38h+arg_30]
0x14001e308  mov     eax, [rbx+44h]
0x14001e30b  cmp     eax, [rdx+2E8h]
0x14001e311  ja      loc_14001E41E
0x14001e317  movzx   ecx, word ptr [rbx+42h]
0x14001e31b  mov     [rsp+38h+arg_8], rbp
0x14001e320  mov     ebp, [rsp+38h+arg_20]
0x14001e324  cmp     ecx, ebp
0x14001e326  ja      loc_14001E3E0
0x14001e32c  cmp     eax, ebp
0x14001e32e  ja      loc_14001E3E0
0x14001e334  add     eax, ecx
0x14001e336  cmp     eax, ebp
0x14001e338  ja      loc_14001E3E0
0x14001e33e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001e345  nop     dword ptr [rax+rax+00h]
0x14001e34a  test    byte ptr [rax+40h], 1
0x14001e34e  jnz     loc_14001E42C
0x14001e354  mov     eax, [rbx+44h]
0x14001e357  mov     [rsi+2ECh], eax
0x14001e35d  mov     edx, [rbx+44h]
0x14001e360  movzx   ecx, word ptr [rbx+42h]
0x14001e364  lea     eax, [rcx+rdx]
0x14001e367  cmp     eax, r15d
0x14001e36a  ja      short loc_14001E3E7
0x14001e36c  mov     r8d, edx; Size
0x14001e36f  lea     rdx, [rbx+rcx]; Src
0x14001e373  mov     rcx, [r13+6C8h]; void *
0x14001e37a  call    memmove
0x14001e37f  mov     ecx, ebp
0x14001e381  mov     rbp, [rsp+38h+arg_8]
0x14001e386  mov     rbx, [rsp+38h+arg_0]
0x14001e38b  mov     rax, [rsp+38h+arg_28]
0x14001e390  mov     dword ptr [rsp+38h+arg_30], edi
0x14001e394  mov     dword ptr [rsp+38h+arg_30+4], 0
0x14001e39c  mov     rdx, [rsp+38h+arg_30]
0x14001e3a1  mov     [rax], ecx
0x14001e3a3  mov     rcx, rsi
0x14001e3a6  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001e3ad  nop     dword ptr [rax+rax+00h]
0x14001e3b2  mov     r15, [rsp+38h+arg_18]
0x14001e3b7  mov     rsi, [rsp+38h+arg_10]
0x14001e3bc  test    edi, edi
0x14001e3be  jnz     short loc_14001E3EF
0x14001e3c0  mov     eax, r14d
0x14001e3c3  add     rsp, 20h
0x14001e3c7  pop     r14
0x14001e3c9  pop     r13
0x14001e3cb  pop     rdi
0x14001e3cc  retn
0x14001e3ce  cmp     edi, 80000005h
0x14001e3d4  jz      loc_14001E2F4
0x14001e3da  mov     ecx, [rsp+38h+arg_20]
0x14001e3de  jmp     short loc_14001E38B
0x14001e3e0  mov     edi, 0C00000C3h
0x14001e3e5  jmp     short loc_14001E37F
0x14001e3e7  mov     r14d, 0C0000016h
0x14001e3ed  jmp     short loc_14001E381
0x14001e3ef  cmp     edi, 103h
0x14001e3f5  jz      short loc_14001E3C0
0x14001e3f7  mov     ecx, edi
0x14001e3f9  xchg    rcx, [r13+10h]
0x14001e3fd  mov     rcx, r13
0x14001e400  mov     edx, edi
0x14001e402  call    cs:__imp_SmbCeUpdateExchangeHistory
0x14001e409  nop     dword ptr [rax+rax+00h]
0x14001e40e  jmp     short loc_14001E3C0
0x14001e410  mov     ecx, [rsp+38h+arg_20]
0x14001e414  mov     edi, 0C00000C3h
0x14001e419  jmp     loc_14001E38B
0x14001e41e  mov     ecx, [rsp+38h+arg_20]
0x14001e422  mov     edi, 0C00000C3h
0x14001e427  jmp     loc_14001E386
0x14001e42c  mov     rax, [r13+58h]
0x14001e430  xor     edx, edx
0x14001e432  mov     r8, [rax+1A8h]
0x14001e439  mov     eax, gs:1A4h
0x14001e441  div     dword ptr [r8+5D0h]
0x14001e448  mov     rax, [r8+5C8h]
0x14001e44f  lea     rdx, [rdx+rdx*2]
0x14001e453  shl     rdx, 6
0x14001e457  lock inc dword ptr [rdx+rax+54h]
0x14001e45c  jmp     loc_14001E354
```
