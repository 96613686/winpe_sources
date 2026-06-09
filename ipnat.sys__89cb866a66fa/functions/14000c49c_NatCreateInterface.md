# NatCreateInterface

- ea: `0x14000c49c`
- end: `0x14000c8aa`
- name: `NatCreateInterface`
- size: `1038`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000c49c`
- `0x14000ccc8`
- `0x140028280`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000c75a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000c75a`
- `ntoskrnl!ExAllocatePool2` at `0x14000c521`
- `ntoskrnl!ExAllocatePool2` at `0x14000c69a`
- `ntoskrnl!ExAllocatePool2` at `0x14000c521`
- `ntoskrnl!ExAllocatePool2` at `0x14000c69a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c615`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c615`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c604`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c6bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c7e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c604`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c6bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c7e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c5d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c5d6`

## pseudocode

```c
__int64 __fastcall NatCreateInterface(unsigned int *a1, KSPIN_LOCK a2)
{
  unsigned int v4; // eax
  _DWORD *Pool2; // rdi
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // r14d
  unsigned int v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // ebp
  KIRQL v12; // si
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  KSPIN_LOCK *v15; // rax
  KSPIN_LOCK *v16; // rbx
  KSPIN_LOCK v18; // rax
  KSPIN_LOCK **v19; // rcx
  unsigned int v20; // [rsp+60h] [rbp+8h] BYREF
  KSPIN_LOCK v21; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  v4 = a1[1];
  v21 = 0;
  v20 = 0;
  if ( v4 >= 0x1FFFFFFF )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225485LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 3221225485LL);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v14 = 33;
    goto LABEL_54;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, 8LL * (v4 + 1), 1098146126);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225495LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225495LL;
    }
    v7 = 35;
LABEL_37:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 3221225495LL);
    return 3221225495LL;
  }
  v8 = a1[1];
  v9 = 0;
  if ( v8 )
  {
    do
    {
      v10 = v9++;
      Pool2[2 * v10] = a1[2 * v10 + 7];
      Pool2[2 * v10 + 1] = a1[2 * v10 + 8];
    }
    while ( v9 < a1[1] );
  }
  GetInterfaceMTU(*a1, &v20);
  if ( v20 < 0x44 )
    v20 = 0;
  v11 = *a1;
  v12 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  if ( NatLookupInterface(v11, &v21) )
  {
    KeReleaseSpinLock(&InterfaceLock, v12);
    ExFreePoolWithTag(Pool2, 0);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225485LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, v11);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v14 = 37;
LABEL_54:
    WPP_SF_d(v13->AttachedDevice, v14, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 3221225485LL);
    return 3221225485LL;
  }
  v15 = (KSPIN_LOCK *)ExAllocatePool2(64, 256, 1232363854);
  v16 = v15;
  if ( !v15 )
  {
    KeReleaseSpinLock(&InterfaceLock, v12);
    ExFreePoolWithTag(Pool2, 0);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225495LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225495LL;
    }
    v7 = 39;
    goto LABEL_37;
  }
  memset(v15, 0, 0x100u);
  KeInitializeSpinLock(v16 + 3);
  *((_DWORD *)v16 + 4) = 1;
  *((_DWORD *)v16 + 8) = v11;
  v16[5] = a2;
  v16[15] = (KSPIN_LOCK)Pool2;
  *((_DWORD *)v16 + 28) = v8;
  *((_WORD *)v16 + 54) = v20;
  v16[20] = (KSPIN_LOCK)(v16 + 19);
  v16[19] = (KSPIN_LOCK)(v16 + 19);
  v16[24] = (KSPIN_LOCK)(v16 + 23);
  v16[23] = (KSPIN_LOCK)(v16 + 23);
  v16[22] = (KSPIN_LOCK)(v16 + 21);
  v16[21] = (KSPIN_LOCK)(v16 + 21);
  v18 = v21;
  v16[1] = (KSPIN_LOCK)v16;
  *v16 = (KSPIN_LOCK)v16;
  v19 = *(KSPIN_LOCK ***)(v18 + 8);
  if ( *v19 != (KSPIN_LOCK *)v18 )
    __fastfail(3u);
  v16[1] = (KSPIN_LOCK)v19;
  *v16 = v18;
  *v19 = v16;
  *(_QWORD *)(v18 + 8) = v16;
  KeReleaseSpinLock(&InterfaceLock, v12);
  _InterlockedAdd(&InterfaceCount, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c49c  mov     [rsp+arg_8], rbx
0x14000c4a1  push    rbp
0x14000c4a2  push    rsi
0x14000c4a3  push    rdi
0x14000c4a4  push    r12
0x14000c4a6  push    r13
0x14000c4a8  push    r14
0x14000c4aa  push    r15
0x14000c4ac  sub     rsp, 20h
0x14000c4b0  mov     r15, rdx
0x14000c4b3  mov     rbx, rcx
0x14000c4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4bd  lea     rsi, WPP_GLOBAL_Control
0x14000c4c4  lea     r13, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c4cb  mov     r14b, 6
0x14000c4ce  mov     r12d, 1
0x14000c4d4  cmp     rcx, rsi
0x14000c4d7  jz      short loc_14000C4F8
0x14000c4d9  mov     eax, [rcx+2Ch]
0x14000c4dc  test    r12b, al
0x14000c4df  jz      short loc_14000C4F8
0x14000c4e1  cmp     [rcx+29h], r14b
0x14000c4e5  jb      short loc_14000C4F8
0x14000c4e7  mov     rcx, [rcx+18h]
0x14000c4eb  lea     edx, [r12+1Eh]
0x14000c4f0  mov     r8, r13
0x14000c4f3  call    WPP_SF_
0x14000c4f8  mov     eax, [rbx+4]
0x14000c4fb  xor     ebp, ebp
0x14000c4fd  mov     [rsp+58h+arg_10], rbp
0x14000c502  mov     [rsp+58h+arg_0], ebp
0x14000c506  cmp     eax, 1FFFFFFFh
0x14000c50b  jnb     loc_14000C82D
0x14000c511  lea     edx, [rax+1]
0x14000c514  mov     r8d, 4174614Eh
0x14000c51a  shl     rdx, 3
0x14000c51e  lea     ecx, [rbp+40h]
0x14000c521  call    cs:__imp_ExAllocatePool2
0x14000c528  nop     dword ptr [rax+rax+00h]
0x14000c52d  mov     rdi, rax
0x14000c530  test    rax, rax
0x14000c533  jnz     short loc_14000C592
0x14000c535  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c53c  cmp     rcx, rsi
0x14000c53f  jz      loc_14000C73C
0x14000c545  mov     eax, [rcx+2Ch]
0x14000c548  test    r12b, al
0x14000c54b  jz      short loc_14000C562
0x14000c54d  cmp     byte ptr [rcx+29h], 2
0x14000c551  jb      short loc_14000C562
0x14000c553  mov     rcx, [rcx+18h]
0x14000c557  lea     edx, [rbp+22h]
0x14000c55a  mov     r8, r13
0x14000c55d  call    WPP_SF_
0x14000c562  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c569  cmp     rcx, rsi
0x14000c56c  jz      loc_14000C73C
0x14000c572  mov     eax, [rcx+2Ch]
0x14000c575  test    r12b, al
0x14000c578  jz      loc_14000C73C
0x14000c57e  cmp     [rcx+29h], r14b
0x14000c582  jb      loc_14000C73C
0x14000c588  mov     edx, 23h ; '#'
0x14000c58d  jmp     loc_14000C72A
0x14000c592  mov     r14d, [rbx+4]
0x14000c596  mov     edx, ebp
0x14000c598  test    r14d, r14d
0x14000c59b  jz      short loc_14000C5B6
0x14000c59d  mov     ecx, edx
0x14000c59f  add     edx, r12d
0x14000c5a2  mov     eax, [rbx+rcx*8+1Ch]
0x14000c5a6  mov     [rdi+rcx*8], eax
0x14000c5a9  mov     eax, [rbx+rcx*8+20h]
0x14000c5ad  mov     [rdi+rcx*8+4], eax
0x14000c5b1  cmp     edx, [rbx+4]
0x14000c5b4  jb      short loc_14000C59D
0x14000c5b6  mov     ecx, [rbx]
0x14000c5b8  lea     rdx, [rsp+58h+arg_0]
0x14000c5bd  call    GetInterfaceMTU
0x14000c5c2  cmp     [rsp+58h+arg_0], 44h ; 'D'
0x14000c5c7  jnb     short loc_14000C5CD
0x14000c5c9  mov     [rsp+58h+arg_0], ebp
0x14000c5cd  mov     ebp, [rbx]
0x14000c5cf  lea     rcx, InterfaceLock; SpinLock
0x14000c5d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c5dd  nop     dword ptr [rax+rax+00h]
0x14000c5e2  lea     rdx, [rsp+58h+arg_10]
0x14000c5e7  mov     ecx, ebp
0x14000c5e9  mov     sil, al
0x14000c5ec  call    NatLookupInterface
0x14000c5f1  test    rax, rax
0x14000c5f4  jz      loc_14000C68A
0x14000c5fa  mov     dl, sil; NewIrql
0x14000c5fd  lea     rcx, InterfaceLock; SpinLock
0x14000c604  call    cs:__imp_KeReleaseSpinLock
0x14000c60b  nop     dword ptr [rax+rax+00h]
0x14000c610  xor     edx, edx; Tag
0x14000c612  mov     rcx, rdi; P
0x14000c615  call    cs:__imp_ExFreePoolWithTag
0x14000c61c  nop     dword ptr [rax+rax+00h]
0x14000c621  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c628  lea     rbx, WPP_GLOBAL_Control
0x14000c62f  cmp     rcx, rbx
0x14000c632  jz      loc_14000C88F
0x14000c638  mov     eax, [rcx+2Ch]
0x14000c63b  test    r12b, al
0x14000c63e  jz      short loc_14000C65A
0x14000c640  cmp     byte ptr [rcx+29h], 2
0x14000c644  jb      short loc_14000C65A
0x14000c646  mov     rcx, [rcx+18h]
0x14000c64a  mov     edx, 24h ; '$'
0x14000c64f  mov     r9d, ebp
0x14000c652  mov     r8, r13
0x14000c655  call    WPP_SF_d
0x14000c65a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c661  cmp     rcx, rbx
0x14000c664  jz      loc_14000C88F
0x14000c66a  mov     eax, [rcx+2Ch]
0x14000c66d  test    r12b, al
0x14000c670  jz      loc_14000C88F
0x14000c676  cmp     byte ptr [rcx+29h], 6
0x14000c67a  jb      loc_14000C88F
0x14000c680  mov     edx, 25h ; '%'
0x14000c685  jmp     loc_14000C87D
0x14000c68a  mov     edx, 100h
0x14000c68f  mov     ecx, 40h ; '@'
0x14000c694  mov     r8d, 4974614Eh
0x14000c69a  call    cs:__imp_ExAllocatePool2
0x14000c6a1  nop     dword ptr [rax+rax+00h]
0x14000c6a6  mov     rbx, rax
0x14000c6a9  test    rax, rax
0x14000c6ac  jnz     loc_14000C746
0x14000c6b2  mov     dl, sil; NewIrql
0x14000c6b5  lea     rcx, InterfaceLock; SpinLock
0x14000c6bc  call    cs:__imp_KeReleaseSpinLock
0x14000c6c3  nop     dword ptr [rax+rax+00h]
0x14000c6c8  xor     edx, edx; Tag
0x14000c6ca  mov     rcx, rdi; P
0x14000c6cd  call    cs:__imp_ExFreePoolWithTag
0x14000c6d4  nop     dword ptr [rax+rax+00h]
0x14000c6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6e0  lea     rbx, WPP_GLOBAL_Control
0x14000c6e7  cmp     rcx, rbx
0x14000c6ea  jz      short loc_14000C73C
0x14000c6ec  mov     eax, [rcx+2Ch]
0x14000c6ef  test    r12b, al
0x14000c6f2  jz      short loc_14000C70B
0x14000c6f4  cmp     byte ptr [rcx+29h], 2
0x14000c6f8  jb      short loc_14000C70B
0x14000c6fa  mov     rcx, [rcx+18h]
0x14000c6fe  mov     edx, 26h ; '&'
0x14000c703  mov     r8, r13
0x14000c706  call    WPP_SF_
0x14000c70b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c712  cmp     rcx, rbx
0x14000c715  jz      short loc_14000C73C
0x14000c717  mov     eax, [rcx+2Ch]
0x14000c71a  test    r12b, al
0x14000c71d  jz      short loc_14000C73C
0x14000c71f  cmp     byte ptr [rcx+29h], 6
0x14000c723  jb      short loc_14000C73C
0x14000c725  mov     edx, 27h ; '''
0x14000c72a  mov     rcx, [rcx+18h]
0x14000c72e  mov     r9d, 0C0000017h
0x14000c734  mov     r8, r13
0x14000c737  call    WPP_SF_d
0x14000c73c  mov     eax, 0C0000017h
0x14000c741  jmp     loc_14000C894
0x14000c746  xor     edx, edx; Val
0x14000c748  mov     r8d, 100h; Size
0x14000c74e  mov     rcx, rbx; void *
0x14000c751  call    memset
0x14000c756  lea     rcx, [rbx+18h]; SpinLock
0x14000c75a  call    cs:__imp_KeInitializeSpinLock
0x14000c761  nop     dword ptr [rax+rax+00h]
0x14000c766  mov     [rbx+10h], r12d
0x14000c76a  mov     [rbx+20h], ebp
0x14000c76d  mov     [rbx+28h], r15
0x14000c771  mov     [rbx+78h], rdi
0x14000c775  mov     [rbx+70h], r14d
0x14000c779  movzx   eax, word ptr [rsp+58h+arg_0]
0x14000c77e  mov     [rbx+6Ch], ax
0x14000c782  lea     rax, [rbx+98h]
0x14000c789  mov     [rax+8], rax
0x14000c78d  mov     [rax], rax
0x14000c790  lea     rax, [rbx+0B8h]
0x14000c797  mov     [rax+8], rax
0x14000c79b  mov     [rax], rax
0x14000c79e  lea     rax, [rbx+0A8h]
0x14000c7a5  mov     [rax+8], rax
0x14000c7a9  mov     [rax], rax
0x14000c7ac  mov     rax, [rsp+58h+arg_10]
0x14000c7b1  mov     [rbx+8], rbx
0x14000c7b5  mov     [rbx], rbx
0x14000c7b8  mov     rcx, [rax+8]
0x14000c7bc  cmp     [rcx], rax
0x14000c7bf  jz      short loc_14000C7C8
0x14000c7c1  mov     ecx, 3
0x14000c7c6  int     29h; Win8: RtlFailFast(ecx)
0x14000c7c8  mov     [rbx+8], rcx
0x14000c7cc  mov     dl, sil; NewIrql
0x14000c7cf  mov     [rbx], rax
0x14000c7d2  mov     [rcx], rbx
0x14000c7d5  lea     rcx, InterfaceLock; SpinLock
0x14000c7dc  mov     [rax+8], rbx
0x14000c7e0  call    cs:__imp_KeReleaseSpinLock
0x14000c7e7  nop     dword ptr [rax+rax+00h]
0x14000c7ec  lock add cs:InterfaceCount, r12d
0x14000c7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c7fb  lea     rbx, WPP_GLOBAL_Control
0x14000c802  cmp     rcx, rbx
0x14000c805  jz      short loc_14000C829
0x14000c807  mov     eax, [rcx+2Ch]
0x14000c80a  test    r12b, al
0x14000c80d  jz      short loc_14000C829
0x14000c80f  cmp     byte ptr [rcx+29h], 6
0x14000c813  jb      short loc_14000C829
0x14000c815  mov     rcx, [rcx+18h]
0x14000c819  mov     edx, 28h ; '('
0x14000c81e  xor     r9d, r9d
0x14000c821  mov     r8, r13
0x14000c824  call    WPP_SF_d
0x14000c829  xor     eax, eax
0x14000c82b  jmp     short loc_14000C894
0x14000c82d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c834  cmp     rcx, rsi
0x14000c837  jz      short loc_14000C88F
0x14000c839  mov     eax, [rcx+2Ch]
0x14000c83c  test    r12b, al
0x14000c83f  jz      short loc_14000C85E
0x14000c841  cmp     byte ptr [rcx+29h], 2
0x14000c845  jb      short loc_14000C85E
0x14000c847  mov     rcx, [rcx+18h]
0x14000c84b  mov     edx, 20h ; ' '
0x14000c850  mov     r9d, 0C000000Dh
0x14000c856  mov     r8, r13
0x14000c859  call    WPP_SF_d
0x14000c85e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c865  cmp     rcx, rsi
0x14000c868  jz      short loc_14000C88F
0x14000c86a  mov     edx, [rcx+2Ch]
0x14000c86d  test    r12b, dl
0x14000c870  jz      short loc_14000C88F
0x14000c872  cmp     [rcx+29h], r14b
0x14000c876  jb      short loc_14000C88F
0x14000c878  mov     edx, 21h ; '!'
0x14000c87d  mov     rcx, [rcx+18h]
0x14000c881  mov     r9d, 0C000000Dh
0x14000c887  mov     r8, r13
0x14000c88a  call    WPP_SF_d
0x14000c88f  mov     eax, 0C000000Dh
0x14000c894  mov     rbx, [rsp+58h+arg_8]
0x14000c899  add     rsp, 20h
0x14000c89d  pop     r15
0x14000c89f  pop     r14
0x14000c8a1  pop     r13
0x14000c8a3  pop     r12
0x14000c8a5  pop     rdi
0x14000c8a6  pop     rsi
0x14000c8a7  pop     rbp
0x14000c8a8  retn
```
