# MRxSmbNotifyChangeDirectory

- ea: `0x140030bb0`
- end: `0x140030e17`
- name: `MRxSmbNotifyChangeDirectory`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000f48c`
- `0x140030bb0`
- `0x1400381d0`
- `0x14004b5f0`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140030c59`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140030c59`
- `ntoskrnl!ExAllocatePool2` at `0x140030c39`
- `ntoskrnl!ExAllocatePool2` at `0x140030c39`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140030c6e`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140030c6e`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x140030cb3`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x140030cb3`

## pseudocode

```c
__int64 __fastcall MRxSmbNotifyChangeDirectory(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rdx
  __int64 Pool2; // r15
  __int64 v5; // r14
  unsigned int v6; // ebx
  bool v7; // bp
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // eax

  v1 = *(_QWORD *)(a1 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 120) + 32LL) + 32LL);
  if ( (*(_DWORD *)(v3 + 420) & 0x40000) == 0 || *(_BYTE *)(v3 + 508) )
    return 3221225659LL;
  Pool2 = ExAllocatePool2(66, 152, 1665559891);
  if ( Pool2 )
  {
    v5 = *(_QWORD *)(a1 + 64);
    if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v1 + 8)) )
    {
      v7 = 0;
    }
    else
    {
      v6 = RxAcquireExclusiveFcbResourceInMRx(0);
      v7 = v6 == 0;
      if ( v6 )
      {
LABEL_16:
        if ( !v6 )
        {
          v8 = *(_QWORD *)(v5 + 32);
          v9 = 0;
          if ( v8 )
            v9 = *(_QWORD *)(v8 + 48);
          *(_QWORD *)(Pool2 + 8) = a1;
          *(_DWORD *)Pool2 = 2;
          *(_DWORD *)(Pool2 + 16) = *(_DWORD *)(a1 + 540);
          *(_WORD *)(Pool2 + 20) = *(_WORD *)(v9 + 8);
          *(_BYTE *)(Pool2 + 22) = *(_BYTE *)(a1 + 536);
          *(_BYTE *)(Pool2 + 23) = 0;
          v10 = *(_QWORD *)(a1 + 552);
          v11 = *(_DWORD *)(a1 + 544);
          *(_OWORD *)(Pool2 + 24) = RxDefaultTransactionOptions;
          *(_QWORD *)(Pool2 + 40) = qword_14001F6B0;
          *(_DWORD *)(Pool2 + 24) = 67108868;
          *(_DWORD *)(Pool2 + 40) = 0;
          *(_QWORD *)(Pool2 + 72) = MRxSmbNotifyChangeDirectoryCompletion;
          *(_QWORD *)(Pool2 + 56) = 1;
          *(_QWORD *)(Pool2 + 64) = Pool2;
          *(_QWORD *)(Pool2 + 104) = 0;
          *(_QWORD *)(Pool2 + 112) = 0;
          *(_QWORD *)(Pool2 + 128) = 0;
          *(_QWORD *)(Pool2 + 136) = 0;
          *(_QWORD *)(Pool2 + 144) = 0;
          *(_WORD *)(Pool2 + 26) |= 0x100u;
          SmbCeTransact(a1, Pool2 + 24, (struct _MDL *)(Pool2 + 16), 8u, 0, 0, 0, 0, v10, v11, 0, 0, 0, 0, Pool2 + 48);
          v6 = MRxSmbNotifyChangeDirectorySynchronousCompletion((volatile signed __int32 *)Pool2);
        }
        goto LABEL_21;
      }
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v5 + 32) + 72LL) & 0x404) != 0 )
      v6 = -1073741528;
    else
      v6 = MRxSmbDeferredCreate(a1);
    if ( v7 )
      RxReleaseFcbResourceInMRx(0);
    goto LABEL_16;
  }
  v6 = -1073741670;
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x140030bb0  push    rbx
0x140030bb2  push    rbp
0x140030bb3  push    rsi
0x140030bb4  push    rdi
0x140030bb5  push    r12
0x140030bb7  push    r13
0x140030bb9  push    r14
0x140030bbb  push    r15
0x140030bbd  sub     rsp, 88h
0x140030bc4  mov     rdi, [rcx+38h]
0x140030bc8  mov     rsi, rcx
0x140030bcb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030bd2  lea     rax, WPP_GLOBAL_Control
0x140030bd9  mov     r13d, 400h
0x140030bdf  cmp     rcx, rax
0x140030be2  jz      short loc_140030BFF
0x140030be4  test    [rcx+2Ch], r13d
0x140030be8  jz      short loc_140030BFF
0x140030bea  mov     rcx, [rcx+18h]
0x140030bee  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x140030bf5  mov     edx, 0Dh
0x140030bfa  call    WPP_SF_
0x140030bff  mov     rax, [rdi+78h]
0x140030c03  mov     rcx, [rax+20h]
0x140030c07  mov     rdx, [rcx+20h]
0x140030c0b  test    dword ptr [rdx+1A4h], 40000h
0x140030c15  jz      loc_140030DFD
0x140030c1b  xor     r12d, r12d
0x140030c1e  cmp     [rdx+1FCh], r12b
0x140030c25  jnz     loc_140030DFD
0x140030c2b  mov     edx, 98h
0x140030c30  mov     r8d, 63466D53h
0x140030c36  lea     ecx, [rdx-56h]
0x140030c39  call    cs:__imp_ExAllocatePool2
0x140030c40  nop     dword ptr [rax+rax+00h]
0x140030c45  mov     r15, rax
0x140030c48  test    rax, rax
0x140030c4b  jz      loc_140030DC3
0x140030c51  mov     rcx, [rdi+8]; Resource
0x140030c55  mov     r14, [rsi+40h]
0x140030c59  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140030c60  nop     dword ptr [rax+rax+00h]
0x140030c65  test    al, al
0x140030c67  jnz     short loc_140030C88
0x140030c69  mov     rdx, rdi
0x140030c6c  xor     ecx, ecx; Fcb
0x140030c6e  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x140030c75  nop     dword ptr [rax+rax+00h]
0x140030c7a  test    eax, eax
0x140030c7c  mov     ebx, eax
0x140030c7e  setz    bpl
0x140030c82  test    eax, eax
0x140030c84  jz      short loc_140030C8B
0x140030c86  jmp     short loc_140030CBF
0x140030c88  mov     bpl, r12b
0x140030c8b  mov     rax, [r14+20h]
0x140030c8f  test    dword ptr [rax+48h], 404h
0x140030c96  jnz     short loc_140030CA4
0x140030c98  mov     rcx, rsi
0x140030c9b  call    MRxSmbDeferredCreate
0x140030ca0  mov     ebx, eax
0x140030ca2  jmp     short loc_140030CA9
0x140030ca4  mov     ebx, 0C0000128h
0x140030ca9  test    bpl, bpl
0x140030cac  jz      short loc_140030CBF
0x140030cae  mov     rdx, rdi
0x140030cb1  xor     ecx, ecx; Fcb
0x140030cb3  call    cs:__imp_RxReleaseFcbResourceInMRx
0x140030cba  nop     dword ptr [rax+rax+00h]
0x140030cbf  test    ebx, ebx
0x140030cc1  jnz     loc_140030DC8
0x140030cc7  mov     rax, [r14+20h]
0x140030ccb  mov     rcx, r12
0x140030cce  test    rax, rax
0x140030cd1  jz      short loc_140030CD7
0x140030cd3  mov     rcx, [rax+30h]
0x140030cd7  mov     [r15+8], rsi
0x140030cdb  lea     r8, [r15+30h]
0x140030cdf  mov     dword ptr [r15], 2
0x140030ce6  lea     rdx, [r15+18h]
0x140030cea  mov     eax, [rsi+21Ch]
0x140030cf0  lea     r9, MRxSmbNotifyChangeDirectoryCompletion
0x140030cf7  mov     [r15+10h], eax
0x140030cfb  movzx   eax, word ptr [rcx+8]
0x140030cff  mov     [r15+14h], ax
0x140030d04  mov     al, [rsi+218h]
0x140030d0a  mov     [r15+16h], al
0x140030d0e  mov     [r15+17h], r12b
0x140030d12  mov     rcx, [rsi+228h]
0x140030d19  mov     eax, [rsi+220h]
0x140030d1f  movups  xmm0, cs:RxDefaultTransactionOptions
0x140030d26  mov     [rsp+0C8h+var_58], r8
0x140030d2b  mov     [rsp+0C8h+var_60], r12d
0x140030d30  movups  xmmword ptr [rdx], xmm0
0x140030d33  mov     [rsp+0C8h+var_68], r12
0x140030d38  movsd   xmm1, cs:qword_14001F6B0
0x140030d40  movsd   qword ptr [rdx+10h], xmm1
0x140030d45  mov     dword ptr [rdx], 4000004h
0x140030d4b  mov     [rdx+10h], r12d
0x140030d4f  mov     [r8+18h], r9
0x140030d53  mov     r9d, 100h
0x140030d59  mov     qword ptr [r8+8], 1
0x140030d61  mov     [r8+10h], r15
0x140030d65  mov     [rsp+0C8h+var_70], r12d
0x140030d6a  mov     [rsp+0C8h+var_78], r12
0x140030d6f  mov     [rsp+0C8h+var_80], eax
0x140030d73  mov     [rsp+0C8h+var_88], rcx
0x140030d78  mov     rcx, rsi
0x140030d7b  mov     [r8+38h], r12
0x140030d7f  mov     [r8+40h], r12
0x140030d83  mov     [r8+50h], r12
0x140030d87  mov     [r8+58h], r12
0x140030d8b  mov     [r8+60h], r12
0x140030d8f  lea     r8, [r15+10h]
0x140030d93  or      [rdx+2], r9w
0x140030d98  mov     r9d, 8
0x140030d9e  mov     [rsp+0C8h+var_90], r12d
0x140030da3  mov     [rsp+0C8h+var_98], r12
0x140030da8  mov     [rsp+0C8h+var_A0], r12d
0x140030dad  mov     [rsp+0C8h+var_A8], r12
0x140030db2  call    _SmbCeTransact
0x140030db7  mov     rcx, r15; P
0x140030dba  call    MRxSmbNotifyChangeDirectorySynchronousCompletion
0x140030dbf  mov     ebx, eax
0x140030dc1  jmp     short loc_140030DC8
0x140030dc3  mov     ebx, 0C000009Ah
0x140030dc8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030dcf  lea     rax, WPP_GLOBAL_Control
0x140030dd6  cmp     rcx, rax
0x140030dd9  jz      short loc_140030DF9
0x140030ddb  test    [rcx+2Ch], r13d
0x140030ddf  jz      short loc_140030DF9
0x140030de1  mov     rcx, [rcx+18h]
0x140030de5  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x140030dec  mov     edx, 0Eh
0x140030df1  mov     r9d, ebx
0x140030df4  call    WPP_SF_d
0x140030df9  mov     eax, ebx
0x140030dfb  jmp     short loc_140030E02
0x140030dfd  mov     eax, 0C00000BBh
0x140030e02  add     rsp, 88h
0x140030e09  pop     r15
0x140030e0b  pop     r14
0x140030e0d  pop     r13
0x140030e0f  pop     r12
0x140030e11  pop     rdi
0x140030e12  pop     rsi
0x140030e13  pop     rbp
0x140030e14  pop     rbx
0x140030e15  retn
```
