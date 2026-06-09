# SmbPseExchangeStart_Locks

- ea: `0x140034bf0`
- end: `0x140035021`
- name: `SmbPseExchangeStart_Locks`
- size: `1073`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000ebd8`
- `0x140033fa8`
- `0x140034058`
- `0x140034470`
- `0x140034bf0`
- `0x140045d50`
- `0x140046120`
- `0x140046a50`
- `0x14004ee60`
- `0x14004f820`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x140034f3a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140034f3a`
- `ntoskrnl!IoFreeMdl` at `0x140034f91`
- `ntoskrnl!IoFreeMdl` at `0x140034f91`
- `rdbss!RxLowIoCompletion` at `0x140034fbe`
- `rdbss!RxLowIoCompletion` at `0x140034fbe`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeStart_Locks(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v5; // rcx
  __int64 v6; // r13
  bool v7; // r12
  char v8; // bp
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  unsigned int v15; // edi
  __int16 *v16; // rcx
  __int16 v17; // ax
  __int16 v18; // ax
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rax
  unsigned int v24; // [rsp+70h] [rbp+8h]

  v2 = a1 + 888;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL);
  if ( v5 )
    v6 = *(_QWORD *)(v5 + 48);
  else
    v6 = 0;
  v7 = *(_DWORD *)(a1 + 364) == 6 || (*(_DWORD *)(a2 + 120) & 0x1000) == 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids);
  v9 = ++*(_DWORD *)(a1 + 372);
  *(_WORD *)(a1 + 384) |= 4u;
  v24 = v9;
LABEL_67:
  while ( 2 )
  {
    v10 = 2;
    do
    {
      while ( 1 )
      {
        if ( !*(_BYTE *)(a1 + 387) )
        {
          *(_BYTE *)(a1 + 387) = 1;
          if ( !v7 )
            *(_QWORD *)(a1 + 424) = SmbPseExchangeStart_Locks;
          MRxSmbSetInitialSMB(v2);
          v10 = 2;
          *(_QWORD *)(a1 + 472) = *(_QWORD *)(a2 + 536);
          break;
        }
        if ( *(_BYTE *)(a1 + 387) == 1 )
          break;
        if ( *(_BYTE *)(a1 + 387) == 2 )
          goto LABEL_45;
      }
      v11 = *(_DWORD *)(a1 + 364);
      v12 = MRxSmbLockSendOptions;
      *(_BYTE *)(a1 + 387) = 2;
      *(_DWORD *)(a1 + 392) = v12;
      v13 = v11 - 5;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 != 1 )
            goto LABEL_68;
          if ( !v8 )
          {
            v15 = MRxSmbBuildLockAssert(v2, 2);
            if ( v15 )
              goto LABEL_57;
          }
          if ( *(_BYTE *)(a1 + 530) && !*(_DWORD *)(a1 + 504) )
          {
            *(_DWORD *)(a1 + 72) |= 1u;
            *(_WORD *)(a1 + 384) |= 0x80u;
            v16 = *(__int16 **)(a1 + 472);
            *(_DWORD *)(a1 + 392) = 0x10000000;
            *(_WORD *)(a1 + 64) = -1;
            v17 = *v16;
            if ( *(_BYTE *)(v6 + 10) == 3 )
              v18 = v17 | 0x102;
            else
              v18 = v17 | 2;
            *v16 = v18;
          }
        }
        else if ( !v8 )
        {
          v15 = MRxSmbBuildFlush(v2, 2);
          if ( v15 )
            goto LABEL_57;
        }
      }
      else
      {
        if ( *(_WORD *)(a2 + 520) == 2 || *(_WORD *)(a2 + 520) == 3 || *(_WORD *)(a2 + 520) == 4 )
        {
          *(_QWORD *)(a1 + 472) = 0;
        }
        else
        {
          if ( *(_WORD *)(a2 + 520) != 5 )
          {
LABEL_68:
            v15 = -1073741822;
            goto LABEL_58;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids,
              *(_QWORD *)(a1 + 472));
          }
        }
        if ( !v8 )
        {
          v15 = MRxSmbBuildLocksAndX(v2, v10);
          if ( v15 )
            goto LABEL_57;
        }
      }
      v15 = SmbPseOrdinaryExchange((PVOID)a1);
      if ( v15 == 259 )
        goto LABEL_71;
      v8 = 0;
      v10 = 2;
LABEL_45:
      v15 = *(_DWORD *)(a1 + 40);
      *(_BYTE *)(a1 + 387) = 1;
      if ( v15 == -1069481983 )
      {
        SmbCeUninitializeExchangeTransport(a1);
        SmbCeReconnect(*(PVOID *)(a1 + 88));
        v15 = v19;
        if ( !v19 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids, a1);
          }
          *(_DWORD *)(a1 + 40) = 0;
          v15 = SmbCeInitializeExchangeTransport(a1);
          if ( !v15 )
          {
            v8 = 1;
            goto LABEL_67;
          }
        }
        goto LABEL_57;
      }
      if ( *(_DWORD *)(a1 + 364) == 5 )
      {
        v21 = *(__int64 **)(a1 + 472);
        if ( v21 )
        {
          v22 = *v21;
          *(_QWORD *)(a1 + 472) = v22;
          if ( v22 )
          {
            if ( !v15 )
              goto LABEL_66;
          }
        }
        goto LABEL_57;
      }
      if ( *(_DWORD *)(a1 + 364) == 6 )
        goto LABEL_57;
    }
    while ( *(_DWORD *)(a1 + 364) != 7 );
    if ( !*(_BYTE *)(a1 + 530) || *(_DWORD *)(a1 + 504) )
    {
LABEL_66:
      MRxSmbSetInitialSMB(v2);
      continue;
    }
    break;
  }
LABEL_57:
  if ( v15 == 259 )
    goto LABEL_71;
LABEL_58:
  if ( v24 > 1 )
  {
    v20 = *(_QWORD *)(a1 + 376);
    if ( v20 )
    {
      if ( _bittest16((const signed __int16 *)(a1 + 384), 9u) )
      {
        if ( (*(_BYTE *)(v20 + 10) & 0x20) != 0 )
          MmUnmapLockedPages(*(PVOID *)(v20 + 24), *(PMDL *)(a1 + 376));
      }
      else
      {
        IoFreeMdl((PMDL)v20);
        *(_QWORD *)(a1 + 376) = 0;
        *(_WORD *)(a1 + 384) &= ~0x10u;
      }
    }
    *(_DWORD *)(a2 + 176) = v15;
    RxLowIoCompletion((PRX_CONTEXT)a2);
    SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)a1);
    v15 = 259;
  }
LABEL_71:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x140034bf0  push    rbx
0x140034bf2  push    rbp
0x140034bf3  push    rsi
0x140034bf4  push    rdi
0x140034bf5  push    r12
0x140034bf7  push    r13
0x140034bf9  push    r14
0x140034bfb  push    r15
0x140034bfd  sub     rsp, 28h
0x140034c01  mov     rax, [rdx+40h]
0x140034c05  lea     r15, [rcx+378h]
0x140034c0c  mov     rbx, rcx
0x140034c0f  mov     r14, rdx
0x140034c12  mov     rcx, [rax+20h]
0x140034c16  test    rcx, rcx
0x140034c19  jnz     short loc_140034C20
0x140034c1b  xor     r13d, r13d
0x140034c1e  jmp     short loc_140034C24
0x140034c20  mov     r13, [rcx+30h]
0x140034c24  cmp     dword ptr [rbx+16Ch], 6
0x140034c2b  jz      short loc_140034C3B
0x140034c2d  test    dword ptr [rdx+78h], 1000h
0x140034c34  jz      short loc_140034C3B
0x140034c36  xor     r12b, r12b
0x140034c39  jmp     short loc_140034C3E
0x140034c3b  mov     r12b, 1
0x140034c3e  xor     bpl, bpl
0x140034c41  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140034c48  lea     rdi, WPP_GLOBAL_Control
0x140034c4f  cmp     rcx, rdi
0x140034c52  jz      short loc_140034C72
0x140034c54  test    dword ptr [rcx+2Ch], 400h
0x140034c5b  jz      short loc_140034C72
0x140034c5d  mov     rcx, [rcx+18h]
0x140034c61  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x140034c68  mov     edx, 14h
0x140034c6d  call    WPP_SF_
0x140034c72  inc     dword ptr [rbx+174h]
0x140034c78  mov     eax, [rbx+174h]
0x140034c7e  or      word ptr [rbx+180h], 4
0x140034c86  mov     [rsp+68h+arg_0], eax
0x140034c8a  jmp     loc_140034F76
0x140034c8f  lea     rdi, WPP_GLOBAL_Control
0x140034c96  movzx   ecx, byte ptr [rbx+183h]
0x140034c9d  test    ecx, ecx
0x140034c9f  jz      short loc_140034CB0
0x140034ca1  sub     ecx, 1
0x140034ca4  jz      short loc_140034CE5
0x140034ca6  cmp     ecx, 1
0x140034ca9  jnz     short loc_140034C96
0x140034cab  jmp     loc_140034E49
0x140034cb0  mov     byte ptr [rbx+183h], 1
0x140034cb7  test    r12b, r12b
0x140034cba  jnz     short loc_140034CCA
0x140034cbc  lea     rax, SmbPseExchangeStart_Locks
0x140034cc3  mov     [rbx+1A8h], rax
0x140034cca  mov     rcx, r15
0x140034ccd  call    MRxSmbSetInitialSMB
0x140034cd2  mov     rax, [r14+218h]
0x140034cd9  mov     edx, 2
0x140034cde  mov     [rbx+1D8h], rax
0x140034ce5  mov     ecx, [rbx+16Ch]
0x140034ceb  mov     eax, cs:MRxSmbLockSendOptions
0x140034cf1  mov     [rbx+183h], dl
0x140034cf7  mov     [rbx+188h], eax
0x140034cfd  sub     ecx, 5
0x140034d00  jz      loc_140034DAF
0x140034d06  sub     ecx, 1
0x140034d09  jz      loc_140034D91
0x140034d0f  cmp     ecx, 1
0x140034d12  jnz     loc_140034F80
0x140034d18  test    bpl, bpl
0x140034d1b  jnz     short loc_140034D32
0x140034d1d  mov     rcx, r15
0x140034d20  call    MRxSmbBuildLockAssert
0x140034d25  mov     edi, eax
0x140034d27  test    eax, eax
0x140034d29  jnz     loc_140034EF0
0x140034d2f  lea     edx, [rax+2]
0x140034d32  cmp     byte ptr [rbx+212h], 0
0x140034d39  mov     esi, 9
0x140034d3e  jz      loc_140034E26
0x140034d44  cmp     dword ptr [rbx+1F8h], 0
0x140034d4b  jnz     loc_140034E26
0x140034d51  or      dword ptr [rbx+48h], 1
0x140034d55  lea     eax, [rsi+77h]
0x140034d58  or      [rbx+180h], ax
0x140034d5f  mov     rcx, [rbx+1D8h]
0x140034d66  mov     dword ptr [rbx+188h], 10000000h
0x140034d70  mov     word ptr [rbx+40h], 0FFFFh
0x140034d76  cmp     byte ptr [r13+0Ah], 3
0x140034d7b  movzx   eax, word ptr [rcx]
0x140034d7e  jnz     short loc_140034D86
0x140034d80  or      ax, 102h
0x140034d84  jmp     short loc_140034D89
0x140034d86  or      ax, dx
0x140034d89  mov     [rcx], ax
0x140034d8c  jmp     loc_140034E26
0x140034d91  test    bpl, bpl
0x140034d94  jnz     short loc_140034DA8
0x140034d96  mov     rcx, r15
0x140034d99  call    MRxSmbBuildFlush
0x140034d9e  mov     edi, eax
0x140034da0  test    eax, eax
0x140034da2  jnz     loc_140034EF0
0x140034da8  mov     esi, 0Ah
0x140034dad  jmp     short loc_140034E26
0x140034daf  movzx   ecx, word ptr [r14+208h]
0x140034db7  mov     esi, 8
0x140034dbc  sub     ecx, edx
0x140034dbe  jz      short loc_140034E04
0x140034dc0  sub     ecx, 1
0x140034dc3  jz      short loc_140034E04
0x140034dc5  sub     ecx, 1
0x140034dc8  jz      short loc_140034E04
0x140034dca  cmp     ecx, 1
0x140034dcd  jnz     loc_140034F80
0x140034dd3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140034dda  cmp     rcx, rdi
0x140034ddd  jz      short loc_140034E0F
0x140034ddf  test    dword ptr [rcx+2Ch], 400h
0x140034de6  jz      short loc_140034E0F
0x140034de8  mov     r9, [rbx+1D8h]
0x140034def  lea     edx, [rsi+0Dh]
0x140034df2  mov     rcx, [rcx+18h]
0x140034df6  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x140034dfd  call    WPP_SF_q
0x140034e02  jmp     short loc_140034E0F
0x140034e04  mov     qword ptr [rbx+1D8h], 0
0x140034e0f  test    bpl, bpl
0x140034e12  jnz     short loc_140034E26
0x140034e14  mov     rcx, r15
0x140034e17  call    MRxSmbBuildLocksAndX
0x140034e1c  mov     edi, eax
0x140034e1e  test    eax, eax
0x140034e20  jnz     loc_140034EF0
0x140034e26  mov     r8d, esi
0x140034e29  mov     rdx, r14
0x140034e2c  mov     rcx, rbx; pContext
0x140034e2f  call    SmbPseOrdinaryExchange
0x140034e34  mov     edi, eax
0x140034e36  cmp     eax, 103h
0x140034e3b  jz      loc_140034FD9
0x140034e41  xor     bpl, bpl
0x140034e44  mov     edx, 2
0x140034e49  mov     edi, [rbx+28h]
0x140034e4c  mov     byte ptr [rbx+183h], 1
0x140034e53  cmp     edi, 0C0410001h
0x140034e59  jnz     short loc_140034EC1
0x140034e5b  mov     rcx, rbx
0x140034e5e  call    SmbCeUninitializeExchangeTransport
0x140034e63  mov     rcx, [rbx+58h]; Context
0x140034e67  call    SmbCeReconnect
0x140034e6c  mov     edi, eax
0x140034e6e  test    eax, eax
0x140034e70  jnz     short loc_140034EF0
0x140034e72  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140034e79  lea     rsi, WPP_GLOBAL_Control
0x140034e80  cmp     rcx, rsi
0x140034e83  jz      short loc_140034EA4
0x140034e85  test    dword ptr [rcx+2Ch], 200h
0x140034e8c  jz      short loc_140034EA4
0x140034e8e  mov     rcx, [rcx+18h]
0x140034e92  lea     edx, [rax+16h]
0x140034e95  mov     r9, rbx
0x140034e98  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x140034e9f  call    WPP_SF_q
0x140034ea4  mov     rcx, rbx
0x140034ea7  mov     dword ptr [rbx+28h], 0
0x140034eae  call    SmbCeInitializeExchangeTransport
0x140034eb3  mov     edi, eax
0x140034eb5  test    eax, eax
0x140034eb7  jnz     short loc_140034EF7
0x140034eb9  mov     bpl, 1
0x140034ebc  jmp     loc_140034F6F
0x140034ec1  mov     ecx, [rbx+16Ch]
0x140034ec7  sub     ecx, 5
0x140034eca  jz      short loc_140034F48
0x140034ecc  sub     ecx, 1
0x140034ecf  jz      short loc_140034EF0
0x140034ed1  cmp     ecx, 1
0x140034ed4  jnz     loc_140034C8F
0x140034eda  cmp     byte ptr [rbx+212h], 0
0x140034ee1  jz      loc_140034F67
0x140034ee7  cmp     dword ptr [rbx+1F8h], 0
0x140034eee  jnz     short loc_140034F67
0x140034ef0  lea     rsi, WPP_GLOBAL_Control
0x140034ef7  cmp     edi, 103h
0x140034efd  jz      loc_140034FE0
0x140034f03  cmp     [rsp+68h+arg_0], 1
0x140034f08  jbe     loc_140034FE0
0x140034f0e  mov     rcx, [rbx+178h]; Mdl
0x140034f15  test    rcx, rcx
0x140034f18  jz      loc_140034FB4
0x140034f1e  bt      word ptr [rbx+180h], 9
0x140034f27  jnb     short loc_140034F91
0x140034f29  test    byte ptr [rcx+0Ah], 20h
0x140034f2d  jz      loc_140034FB4
0x140034f33  mov     rdx, rcx; MemoryDescriptorList
0x140034f36  mov     rcx, [rcx+18h]; BaseAddress
0x140034f3a  call    cs:__imp_MmUnmapLockedPages
0x140034f41  nop     dword ptr [rax+rax+00h]
0x140034f46  jmp     short loc_140034FB4
0x140034f48  mov     rax, [rbx+1D8h]
0x140034f4f  test    rax, rax
0x140034f52  jz      short loc_140034EF0
0x140034f54  mov     rax, [rax]
0x140034f57  mov     [rbx+1D8h], rax
0x140034f5e  test    rax, rax
0x140034f61  jz      short loc_140034EF0
0x140034f63  test    edi, edi
0x140034f65  jnz     short loc_140034EF0
0x140034f67  mov     rcx, r15
0x140034f6a  call    MRxSmbSetInitialSMB
0x140034f6f  lea     rdi, WPP_GLOBAL_Control
0x140034f76  mov     edx, 2
0x140034f7b  jmp     loc_140034C96
0x140034f80  mov     edi, 0C0000002h
0x140034f85  lea     rsi, WPP_GLOBAL_Control
0x140034f8c  jmp     loc_140034F03
0x140034f91  call    cs:__imp_IoFreeMdl
0x140034f98  nop     dword ptr [rax+rax+00h]
0x140034f9d  mov     eax, 0FFEFh
0x140034fa2  mov     qword ptr [rbx+178h], 0
0x140034fad  and     [rbx+180h], ax
0x140034fb4  mov     rcx, r14; RxContext
0x140034fb7  mov     [r14+0B0h], edi
0x140034fbe  call    cs:__imp_RxLowIoCompletion
0x140034fc5  nop     dword ptr [rax+rax+00h]
0x140034fca  mov     rcx, rbx; pContext
0x140034fcd  call    SmbPseFinalizeOrdinaryExchange
0x140034fd2  mov     edi, 103h
0x140034fd7  jmp     short loc_140034FE0
0x140034fd9  lea     rsi, WPP_GLOBAL_Control
0x140034fe0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140034fe7  cmp     rcx, rsi
0x140034fea  jz      short loc_14003500D
0x140034fec  test    dword ptr [rcx+2Ch], 400h
0x140034ff3  jz      short loc_14003500D
0x140034ff5  mov     rcx, [rcx+18h]
0x140034ff9  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x140035000  mov     edx, 17h
0x140035005  mov     r9d, edi
0x140035008  call    WPP_SF_d
0x14003500d  mov     eax, edi
0x14003500f  add     rsp, 28h
0x140035013  pop     r15
0x140035015  pop     r14
0x140035017  pop     r13
0x140035019  pop     r12
0x14003501b  pop     rdi
0x14003501c  pop     rsi
0x14003501d  pop     rbp
0x14003501e  pop     rbx
0x14003501f  retn
```
