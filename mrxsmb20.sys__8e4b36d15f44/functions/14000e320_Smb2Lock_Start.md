# Smb2Lock_Start

- ea: `0x14000e320`
- end: `0x14000e6f2`
- name: `Smb2Lock_Start`
- size: `978`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000e320`
- `0x14000e700`
- `0x14001fd20`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000e64e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000e64e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000e4e4`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000e4e4`
- `rdbss!RxLockEnumerator` at `0x14000e410`
- `rdbss!RxLockEnumerator` at `0x14000e480`
- `rdbss!RxLockEnumerator` at `0x14000e410`
- `rdbss!RxLockEnumerator` at `0x14000e480`
- `rdbss!RxFreeMdl` at `0x14000e6cb`
- `rdbss!RxFreeMdl` at `0x14000e6cb`
- `rdbss!RxAllocateMdl2` at `0x14000e630`
- `rdbss!RxAllocateMdl2` at `0x14000e630`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14000e6b6`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14000e6b6`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14000e68c`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14000e68c`

## pseudocode

```c
__int64 __fastcall Smb2Lock_Start(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // rsi
  __int64 v4; // r14
  bool v5; // r12
  __int64 v6; // r15
  char v7; // r11
  __int64 v8; // rdi
  struct _MRX_SRV_OPEN_ *v9; // rcx
  __int64 v10; // rcx
  struct _MDL *v11; // rsi
  unsigned __int16 *v12; // r13
  int v13; // eax
  int v14; // ecx
  int v15; // ecx
  int v16; // r8d
  bool v17; // sf
  __int64 v18; // rax
  unsigned int v19; // ebp
  _QWORD *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  struct _MDL *Mdl2; // rax
  int *v25; // [rsp+28h] [rbp-60h]
  int v26; // [rsp+90h] [rbp+8h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+98h] [rbp+10h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+A0h] [rbp+18h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v3 = *(_QWORD *)(v1 + 72);
  v4 = *(_QWORD *)(v3 + 48);
  v5 = (unsigned __int16)(*(_WORD *)(v1 + 520) - 2) <= 1u && (*(_DWORD *)(v1 + 544) & 1) == 0;
  v6 = a1 + 2448;
  SmbCeBuildSmb2Header(a1, a1 + 2448, 64);
  *(_WORD *)(v6 + 12) = 10;
  *(_QWORD *)(a1 + 2512) = 65584;
  LODWORD(v8) = 0;
  *(_OWORD *)(a1 + 2520) = *(_OWORD *)(v4 + 28);
  if ( *(_BYTE *)(a1 + 1028) )
  {
    v9 = *(struct _MRX_SRV_OPEN_ **)(v3 + 32);
    LOBYTE(v26) = 0;
    v25 = &v26;
    Interval.LowPart = 0;
    FileOffset.QuadPart = 0;
    if ( RxLockEnumerator(v9, (PVOID *)v3, &FileOffset, (PLARGE_INTEGER)(a1 + 2536), (PBOOLEAN)(a1 + 2544)) )
    {
      do
      {
        v10 = 3LL * (unsigned int)v8;
        v8 = (unsigned int)(v8 + 1);
        *(_DWORD *)(a1 + 8 * v10 + 2552) = (((_BYTE)v26 != 0) + 1) | 0x10;
        v25 = &v26;
      }
      while ( RxLockEnumerator(
                *(PMRX_SRV_OPEN *)(v3 + 32),
                (PVOID *)v3,
                &FileOffset,
                (PLARGE_INTEGER)(a1 + 2536 + 24 * v8),
                (PBOOLEAN)(a1 + 2544 + 24 * v8)) );
    }
    goto LABEL_34;
  }
  v11 = 0;
  if ( (v7 & 0x40) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 4LL) & 1) != 0 )
  {
    v26 = 20;
    v12 = (unsigned __int16 *)(a1 + 1030);
    while ( 1 )
    {
      if ( (_DWORD)v8 == -1073741507 )
      {
        Interval.QuadPart = -5000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      v13 = Smb2ReserveOperationSequenceBucket(v4, a1 + 1030, v5);
      LODWORD(v8) = v13;
      if ( v5 || v13 != -1073741507 )
        break;
      if ( --v26 < 0 )
        goto LABEL_41;
    }
    if ( v13 )
    {
LABEL_39:
      v17 = (int)v8 < 0;
      goto LABEL_40;
    }
  }
  else
  {
    v12 = (unsigned __int16 *)(a1 + 1030);
  }
  v14 = *(unsigned __int16 *)(v1 + 520);
  if ( v14 == 3 )
  {
    v16 = 2;
  }
  else
  {
    v15 = v14 - 2;
    if ( v15 )
    {
      if ( (unsigned int)(v15 - 2) >= 2 )
      {
        LODWORD(v8) = -1073741822;
LABEL_41:
        RxFreeMdl(v11);
        return (unsigned int)v8;
      }
      v16 = 4;
    }
    else
    {
      v16 = 1;
    }
  }
  v17 = (int)v8 < 0;
  if ( !(_DWORD)v8 )
  {
    *(_DWORD *)(a1 + 2516) = *v12;
    if ( (*(_DWORD *)(v1 + 544) & 1) != 0 )
      v16 |= 0x10u;
    if ( *(_WORD *)(v1 + 520) != 5 )
    {
      LOWORD(v8) = 1;
      *(_QWORD *)(a1 + 2536) = *(_QWORD *)(v1 + 552);
      v18 = *(_QWORD *)(v1 + 536);
      v19 = 112;
      *(_QWORD *)(a1 + 2544) = v18;
      *(_DWORD *)(a1 + 2552) = v16;
      *(_DWORD *)(a1 + 2556) = 0;
LABEL_35:
      *(_WORD *)(a1 + 2514) = v8;
      Mdl2 = (struct _MDL *)RxAllocateMdl2(v6, v19, 0, 0, 0);
      v11 = Mdl2;
      if ( !Mdl2 )
      {
        LODWORD(v8) = -1073741670;
        goto LABEL_41;
      }
      MmBuildMdlForNonPagedPool(Mdl2);
      LODWORD(v25) = 0;
      LODWORD(v8) = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1032, a1, v11, v19, 0, v25, 0, 0, 0, 4);
      if ( !(_DWORD)v8 )
      {
        *(_QWORD *)(a1 + 1120) = v6;
        v11 = 0;
        *(_QWORD *)(a1 + 1744) = 0;
        LODWORD(v8) = SmbCseSubmitBufferContext(a1 + 1032);
      }
      goto LABEL_39;
    }
    v20 = *(_QWORD **)(v1 + 536);
    for ( LODWORD(v8) = 0; v20; v20 = (_QWORD *)*v20 )
    {
      v21 = (unsigned int)v8;
      LODWORD(v8) = v8 + 1;
      v22 = a1 + 24 * v21;
      *(_QWORD *)(v22 + 2536) = v20[2];
      *(_QWORD *)(v22 + 2544) = v20[3];
      *(_DWORD *)(v22 + 2552) = v16;
      *(_DWORD *)(v22 + 2556) = 0;
    }
LABEL_34:
    v19 = 24 * v8 + 88;
    goto LABEL_35;
  }
LABEL_40:
  if ( v17 )
    goto LABEL_41;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e320  push    rbx
0x14000e322  push    rbp
0x14000e323  push    rsi
0x14000e324  push    r12
0x14000e326  push    r13
0x14000e328  push    r14
0x14000e32a  push    r15
0x14000e32c  sub     rsp, 50h
0x14000e330  mov     rbp, [rcx+30h]
0x14000e334  mov     rbx, rcx
0x14000e337  mov     rsi, [rbp+48h]
0x14000e33b  movzx   eax, word ptr [rbp+208h]
0x14000e342  sub     ax, 2
0x14000e346  mov     r14, [rsi+30h]
0x14000e34a  mov     r11d, [r14+8]
0x14000e34e  cmp     ax, 1
0x14000e352  ja      short loc_14000E363
0x14000e354  mov     eax, [rbp+220h]
0x14000e35a  test    al, 1
0x14000e35c  jnz     short loc_14000E363
0x14000e35e  mov     r12b, 1
0x14000e361  jmp     short loc_14000E366
0x14000e363  xor     r12b, r12b
0x14000e366  lea     r15, [rcx+990h]
0x14000e36d  mov     [rsp+88h+arg_18], rdi
0x14000e375  mov     rdx, r15
0x14000e378  mov     r8d, 40h ; '@'
0x14000e37e  call    SmbCeBuildSmb2Header
0x14000e383  mov     word ptr [r15+0Ch], 0Ah
0x14000e38a  xor     r13d, r13d
0x14000e38d  mov     edx, 1
0x14000e392  mov     qword ptr [rbx+9D0h], 10030h
0x14000e39d  mov     edi, r13d
0x14000e3a0  movups  xmm0, xmmword ptr [r14+1Ch]
0x14000e3a5  movups  xmmword ptr [rbx+9D8h], xmm0
0x14000e3ac  cmp     [rbx+404h], r13b
0x14000e3b3  jz      loc_14000E495
0x14000e3b9  mov     rcx, [rsi+20h]; SrvOpen
0x14000e3bd  lea     rax, [rsp+88h+Interval]
0x14000e3c5  mov     [rsp+88h+var_58], rax
0x14000e3ca  lea     r12, [rbx+9E8h]
0x14000e3d1  lea     rax, [rsp+88h+arg_0]
0x14000e3d9  mov     byte ptr [rsp+88h+arg_0], r13b
0x14000e3e1  mov     [rsp+88h+var_60], rax
0x14000e3e6  lea     r14, [rbx+9F0h]
0x14000e3ed  mov     r9, r12; LockRange
0x14000e3f0  mov     [rsp+88h+IsLockExclusive], r14; IsLockExclusive
0x14000e3f5  lea     r8, [rsp+88h+FileOffset]; FileOffset
0x14000e3fd  mov     dword ptr [rsp+88h+Interval], r13d
0x14000e405  mov     rdx, rsi; ContinuationHandle
0x14000e408  mov     qword ptr [rsp+88h+FileOffset], r13
0x14000e410  call    cs:__imp_RxLockEnumerator
0x14000e417  nop     dword ptr [rax+rax+00h]
0x14000e41c  test    al, al
0x14000e41e  jz      loc_14000E60F
0x14000e424  cmp     byte ptr [rsp+88h+arg_0], r13b
0x14000e42c  lea     r8, [rsp+88h+FileOffset]; FileOffset
0x14000e434  mov     eax, edi
0x14000e436  mov     rdx, rsi; ContinuationHandle
0x14000e439  lea     rcx, [rax+rax*2]
0x14000e43d  mov     eax, r13d
0x14000e440  setnz   al
0x14000e443  inc     edi
0x14000e445  inc     eax
0x14000e447  or      eax, 10h
0x14000e44a  mov     [rbx+rcx*8+9F8h], eax
0x14000e451  lea     rcx, [rdi+rdi*2]
0x14000e455  lea     rax, [r14+rcx*8]
0x14000e459  lea     r9, [r12+rcx*8]; LockRange
0x14000e45d  lea     rcx, [rsp+88h+Interval]
0x14000e465  mov     [rsp+88h+var_58], rcx
0x14000e46a  lea     rcx, [rsp+88h+arg_0]
0x14000e472  mov     [rsp+88h+var_60], rcx
0x14000e477  mov     rcx, [rsi+20h]; SrvOpen
0x14000e47b  mov     [rsp+88h+IsLockExclusive], rax; IsLockExclusive
0x14000e480  call    cs:__imp_RxLockEnumerator
0x14000e487  nop     dword ptr [rax+rax+00h]
0x14000e48c  test    al, al
0x14000e48e  jnz     short loc_14000E424
0x14000e490  jmp     loc_14000E60F
0x14000e495  mov     rsi, r13
0x14000e498  test    r11b, 40h
0x14000e49c  jnz     short loc_14000E4B2
0x14000e49e  mov     rax, [rbx+48h]
0x14000e4a2  mov     ecx, [rax+4]
0x14000e4a5  test    dl, cl
0x14000e4a7  jnz     short loc_14000E4B2
0x14000e4a9  lea     r13, [rbx+406h]
0x14000e4b0  jmp     short loc_14000E529
0x14000e4b2  mov     [rsp+88h+arg_0], 14h
0x14000e4bd  lea     r13, [rbx+406h]
0x14000e4c4  cmp     edi, 0C000013Dh
0x14000e4ca  jnz     short loc_14000E4F0
0x14000e4cc  lea     r8, [rsp+88h+Interval]; Interval
0x14000e4d4  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFB3B4C0h
0x14000e4e0  xor     edx, edx; Alertable
0x14000e4e2  xor     ecx, ecx; WaitMode
0x14000e4e4  call    cs:__imp_KeDelayExecutionThread
0x14000e4eb  nop     dword ptr [rax+rax+00h]
0x14000e4f0  movzx   r8d, r12b
0x14000e4f4  mov     rdx, r13
0x14000e4f7  mov     rcx, r14
0x14000e4fa  call    Smb2ReserveOperationSequenceBucket
0x14000e4ff  mov     edi, eax
0x14000e501  test    r12b, r12b
0x14000e504  jnz     short loc_14000E51C
0x14000e506  cmp     eax, 0C000013Dh
0x14000e50b  jnz     short loc_14000E51C
0x14000e50d  sub     [rsp+88h+arg_0], 1
0x14000e515  jns     short loc_14000E4C4
0x14000e517  jmp     loc_14000E6C8
0x14000e51c  test    eax, eax
0x14000e51e  jnz     loc_14000E6C4
0x14000e524  mov     edx, 1
0x14000e529  movzx   ecx, word ptr [rbp+208h]
0x14000e530  cmp     ecx, 3
0x14000e533  jz      short loc_14000E55B
0x14000e535  sub     ecx, 2
0x14000e538  jz      short loc_14000E556
0x14000e53a  sub     ecx, 2
0x14000e53d  jz      short loc_14000E54E
0x14000e53f  cmp     ecx, 1
0x14000e542  jz      short loc_14000E54E
0x14000e544  mov     edi, 0C0000002h
0x14000e549  jmp     loc_14000E6C8
0x14000e54e  mov     r8d, 4
0x14000e554  jmp     short loc_14000E561
0x14000e556  mov     r8d, edx
0x14000e559  jmp     short loc_14000E561
0x14000e55b  mov     r8d, 2
0x14000e561  test    edi, edi
0x14000e563  jnz     loc_14000E6C6
0x14000e569  movzx   eax, word ptr [r13+0]
0x14000e56e  mov     [rbx+9D4h], eax
0x14000e574  mov     eax, [rbp+220h]
0x14000e57a  test    al, 1
0x14000e57c  jz      short loc_14000E582
0x14000e57e  or      r8d, 10h
0x14000e582  xor     r13d, r13d
0x14000e585  cmp     word ptr [rbp+208h], 5
0x14000e58d  jz      short loc_14000E5C3
0x14000e58f  mov     rax, [rbp+228h]
0x14000e596  movzx   edi, dx
0x14000e599  mov     [rbx+9E8h], rax
0x14000e5a0  mov     rax, [rbp+218h]
0x14000e5a7  mov     ebp, 70h ; 'p'
0x14000e5ac  mov     [rbx+9F0h], rax
0x14000e5b3  mov     [rbx+9F8h], r8d
0x14000e5ba  mov     [rbx+9FCh], r13d
0x14000e5c1  jmp     short loc_14000E619
0x14000e5c3  mov     r9, [rbp+218h]
0x14000e5ca  mov     edi, r13d
0x14000e5cd  test    r9, r9
0x14000e5d0  jz      short loc_14000E60F
0x14000e5d2  mov     ecx, edi
0x14000e5d4  inc     edi
0x14000e5d6  lea     rax, [rcx+rcx*2]
0x14000e5da  lea     rdx, [rbx+rax*8]
0x14000e5de  mov     rax, [r9+10h]
0x14000e5e2  mov     [rdx+9E8h], rax
0x14000e5e9  lea     rcx, [rcx+rcx*2]
0x14000e5ed  mov     rax, [r9+18h]
0x14000e5f1  mov     [rbx+rcx*8+9F0h], rax
0x14000e5f9  mov     [rdx+9F8h], r8d
0x14000e600  mov     [rdx+9FCh], r13d
0x14000e607  mov     r9, [r9]
0x14000e60a  test    r9, r9
0x14000e60d  jnz     short loc_14000E5D2
0x14000e60f  lea     eax, [rdi+rdi*2]
0x14000e612  lea     ebp, ds:58h[rax*8]
0x14000e619  xor     r9d, r9d
0x14000e61c  mov     [rbx+9D2h], di
0x14000e623  xor     r8d, r8d
0x14000e626  mov     [rsp+88h+IsLockExclusive], r13
0x14000e62b  mov     edx, ebp
0x14000e62d  mov     rcx, r15
0x14000e630  call    cs:__imp_RxAllocateMdl2
0x14000e637  nop     dword ptr [rax+rax+00h]
0x14000e63c  mov     rsi, rax
0x14000e63f  test    rax, rax
0x14000e642  jnz     short loc_14000E64B
0x14000e644  mov     edi, 0C000009Ah
0x14000e649  jmp     short loc_14000E6C8
0x14000e64b  mov     rcx, rsi; MemoryDescriptorList
0x14000e64e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000e655  nop     dword ptr [rax+rax+00h]
0x14000e65a  mov     [rsp+88h+var_40], 4
0x14000e662  lea     rcx, [rbx+408h]
0x14000e669  mov     [rsp+88h+var_48], r13w
0x14000e66f  mov     r9d, ebp
0x14000e672  mov     [rsp+88h+var_50], r13d
0x14000e677  mov     r8, rsi
0x14000e67a  mov     [rsp+88h+var_58], r13
0x14000e67f  mov     rdx, rbx
0x14000e682  mov     dword ptr [rsp+88h+var_60], r13d
0x14000e687  mov     [rsp+88h+IsLockExclusive], r13
0x14000e68c  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14000e693  nop     dword ptr [rax+rax+00h]
0x14000e698  mov     edi, eax
0x14000e69a  test    eax, eax
0x14000e69c  jnz     short loc_14000E6C4
0x14000e69e  lea     rcx, [rbx+408h]
0x14000e6a5  mov     [rbx+460h], r15
0x14000e6ac  mov     rsi, r13
0x14000e6af  mov     [rbx+6D0h], r13
0x14000e6b6  call    cs:__imp_SmbCseSubmitBufferContext
0x14000e6bd  nop     dword ptr [rax+rax+00h]
0x14000e6c2  mov     edi, eax
0x14000e6c4  test    edi, edi
0x14000e6c6  jns     short loc_14000E6D7
0x14000e6c8  mov     rcx, rsi
0x14000e6cb  call    cs:__imp_RxFreeMdl
0x14000e6d2  nop     dword ptr [rax+rax+00h]
0x14000e6d7  mov     eax, edi
0x14000e6d9  mov     rdi, [rsp+88h+arg_18]
0x14000e6e1  add     rsp, 50h
0x14000e6e5  pop     r15
0x14000e6e7  pop     r14
0x14000e6e9  pop     r13
0x14000e6eb  pop     r12
0x14000e6ed  pop     rsi
0x14000e6ee  pop     rbp
0x14000e6ef  pop     rbx
0x14000e6f0  retn
```
