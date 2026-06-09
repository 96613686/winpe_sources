# NatProcessCreateTicket

- ea: `0x14001e1f0`
- end: `0x14001e4db`
- name: `NatProcessCreateTicket`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000bc50`
- `0x14000ccc8`
- `0x140013550`
- `0x14001e1f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001e3b9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001e3b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e2d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e354`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e3da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e469`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e2d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e354`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e3da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e469`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001e3a9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001e3a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e27f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e27f`

## pseudocode

```c
__int64 __fastcall NatProcessCreateTicket(unsigned int *a1, __int64 a2)
{
  char v4; // al
  KIRQL v5; // bp
  __int64 v6; // rax
  __int64 v7; // rdi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int StaticPortMapping; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  if ( *a1 - 1 > 0xFFFFFFFD
    || (v4 = *((_BYTE *)a1 + 4), v4 != 6) && v4 != 17
    || !*((_WORD *)a1 + 3)
    || !*((_WORD *)a1 + 6)
    || !a1[4] )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v9 = 77;
LABEL_50:
    WPP_SF_d(v8->AttachedDevice, v9, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    return 3221225485LL;
  }
  v5 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  v6 = NatLookupInterface(*a1, 0);
  v7 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    }
    KeReleaseSpinLock(&InterfaceLock, v5);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v9 = 79;
    goto LABEL_50;
  }
  if ( *(_QWORD *)(v6 + 40) != a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225506LL);
    }
    KeReleaseSpinLock(&InterfaceLock, v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225506LL);
    }
    return 3221225506LL;
  }
  if ( *(int *)(v6 + 56) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    }
    KeReleaseSpinLock(&InterfaceLock, v5);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v9 = 83;
    goto LABEL_50;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v6 + 16));
  KeReleaseSpinLockFromDpcLevel(&InterfaceLock);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v7 + 24));
  StaticPortMapping = NatCreateStaticPortMapping(v7, (__int64)(a1 + 1));
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 24), v5);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 16), 0xFFFFFFFF) == 1 )
    NatCleanupInterface((PVOID)v7);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, StaticPortMapping);
  }
  return StaticPortMapping;
}

```

## disassembly

```asm
0x14001e1f0  push    rbx
0x14001e1f2  push    rbp
0x14001e1f3  push    rsi
0x14001e1f4  push    rdi
0x14001e1f5  push    r12
0x14001e1f7  push    r13
0x14001e1f9  push    r14
0x14001e1fb  sub     rsp, 20h
0x14001e1ff  mov     r14, rdx
0x14001e202  mov     rbx, rcx
0x14001e205  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e20c  lea     r12, WPP_GLOBAL_Control
0x14001e213  lea     r13, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001e21a  cmp     rcx, r12
0x14001e21d  jz      short loc_14001E23D
0x14001e21f  mov     eax, [rcx+2Ch]
0x14001e222  test    al, 1
0x14001e224  jz      short loc_14001E23D
0x14001e226  cmp     byte ptr [rcx+29h], 6
0x14001e22a  jb      short loc_14001E23D
0x14001e22c  mov     rcx, [rcx+18h]
0x14001e230  mov     edx, 4Ch ; 'L'
0x14001e235  mov     r8, r13
0x14001e238  call    WPP_SF_
0x14001e23d  mov     eax, [rbx]
0x14001e23f  dec     eax
0x14001e241  cmp     eax, 0FFFFFFFDh
0x14001e244  ja      loc_14001E495
0x14001e24a  mov     al, [rbx+4]
0x14001e24d  cmp     al, 6
0x14001e24f  jz      short loc_14001E259
0x14001e251  cmp     al, 11h
0x14001e253  jnz     loc_14001E495
0x14001e259  xor     eax, eax
0x14001e25b  cmp     ax, [rbx+6]
0x14001e25f  jz      loc_14001E495
0x14001e265  cmp     ax, [rbx+0Ch]
0x14001e269  jz      loc_14001E495
0x14001e26f  cmp     [rbx+10h], eax
0x14001e272  jz      loc_14001E495
0x14001e278  lea     rcx, InterfaceLock; SpinLock
0x14001e27f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001e286  nop     dword ptr [rax+rax+00h]
0x14001e28b  mov     ecx, [rbx]
0x14001e28d  xor     edx, edx
0x14001e28f  mov     bpl, al
0x14001e292  call    NatLookupInterface
0x14001e297  mov     rdi, rax
0x14001e29a  test    rax, rax
0x14001e29d  jnz     short loc_14001E312
0x14001e29f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2a6  cmp     rcx, r12
0x14001e2a9  jz      short loc_14001E2CD
0x14001e2ab  mov     eax, [rcx+2Ch]
0x14001e2ae  test    al, 1
0x14001e2b0  jz      short loc_14001E2CD
0x14001e2b2  cmp     byte ptr [rcx+29h], 2
0x14001e2b6  jb      short loc_14001E2CD
0x14001e2b8  mov     rcx, [rcx+18h]
0x14001e2bc  lea     edx, [rdi+4Eh]
0x14001e2bf  mov     r9d, 0C000000Dh
0x14001e2c5  mov     r8, r13
0x14001e2c8  call    WPP_SF_d
0x14001e2cd  mov     dl, bpl; NewIrql
0x14001e2d0  lea     rcx, InterfaceLock; SpinLock
0x14001e2d7  call    cs:__imp_KeReleaseSpinLock
0x14001e2de  nop     dword ptr [rax+rax+00h]
0x14001e2e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2ea  cmp     rcx, r12
0x14001e2ed  jz      loc_14001E4C6
0x14001e2f3  mov     eax, [rcx+2Ch]
0x14001e2f6  test    al, 1
0x14001e2f8  jz      loc_14001E4C6
0x14001e2fe  cmp     byte ptr [rcx+29h], 6
0x14001e302  jb      loc_14001E4C6
0x14001e308  mov     edx, 4Fh ; 'O'
0x14001e30d  jmp     loc_14001E4B4
0x14001e312  cmp     [rax+28h], r14
0x14001e316  jz      short loc_14001E394
0x14001e318  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e31f  mov     ebx, 0C0000022h
0x14001e324  cmp     rcx, r12
0x14001e327  jz      short loc_14001E34A
0x14001e329  mov     eax, [rcx+2Ch]
0x14001e32c  test    al, 1
0x14001e32e  jz      short loc_14001E34A
0x14001e330  cmp     byte ptr [rcx+29h], 2
0x14001e334  jb      short loc_14001E34A
0x14001e336  mov     rcx, [rcx+18h]
0x14001e33a  mov     edx, 50h ; 'P'
0x14001e33f  mov     r9d, ebx
0x14001e342  mov     r8, r13
0x14001e345  call    WPP_SF_d
0x14001e34a  mov     dl, bpl; NewIrql
0x14001e34d  lea     rcx, InterfaceLock; SpinLock
0x14001e354  call    cs:__imp_KeReleaseSpinLock
0x14001e35b  nop     dword ptr [rax+rax+00h]
0x14001e360  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e367  cmp     rcx, r12
0x14001e36a  jz      short loc_14001E38D
0x14001e36c  mov     eax, [rcx+2Ch]
0x14001e36f  test    al, 1
0x14001e371  jz      short loc_14001E38D
0x14001e373  cmp     byte ptr [rcx+29h], 6
0x14001e377  jb      short loc_14001E38D
0x14001e379  mov     rcx, [rcx+18h]
0x14001e37d  mov     edx, 51h ; 'Q'
0x14001e382  mov     r9d, ebx
0x14001e385  mov     r8, r13
0x14001e388  call    WPP_SF_d
0x14001e38d  mov     eax, ebx
0x14001e38f  jmp     loc_14001E4CB
0x14001e394  cmp     dword ptr [rax+38h], 0
0x14001e398  jl      loc_14001E42F
0x14001e39e  lock inc dword ptr [rax+10h]
0x14001e3a2  lea     rcx, InterfaceLock; SpinLock
0x14001e3a9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001e3b0  nop     dword ptr [rax+rax+00h]
0x14001e3b5  lea     rcx, [rdi+18h]; SpinLock
0x14001e3b9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001e3c0  nop     dword ptr [rax+rax+00h]
0x14001e3c5  lea     rdx, [rbx+4]
0x14001e3c9  mov     rcx, rdi
0x14001e3cc  call    NatCreateStaticPortMapping
0x14001e3d1  mov     dl, bpl; NewIrql
0x14001e3d4  lea     rcx, [rdi+18h]; SpinLock
0x14001e3d8  mov     esi, eax
0x14001e3da  call    cs:__imp_KeReleaseSpinLock
0x14001e3e1  nop     dword ptr [rax+rax+00h]
0x14001e3e6  or      eax, 0FFFFFFFFh
0x14001e3e9  lock xadd [rdi+10h], eax
0x14001e3ee  cmp     eax, 1
0x14001e3f1  jnz     short loc_14001E3FB
0x14001e3f3  mov     rcx, rdi; P
0x14001e3f6  call    NatCleanupInterface
0x14001e3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e402  cmp     rcx, r12
0x14001e405  jz      short loc_14001E428
0x14001e407  mov     eax, [rcx+2Ch]
0x14001e40a  test    al, 1
0x14001e40c  jz      short loc_14001E428
0x14001e40e  cmp     byte ptr [rcx+29h], 6
0x14001e412  jb      short loc_14001E428
0x14001e414  mov     rcx, [rcx+18h]
0x14001e418  mov     edx, 54h ; 'T'
0x14001e41d  mov     r9d, esi
0x14001e420  mov     r8, r13
0x14001e423  call    WPP_SF_d
0x14001e428  mov     eax, esi
0x14001e42a  jmp     loc_14001E4CB
0x14001e42f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e436  cmp     rcx, r12
0x14001e439  jz      short loc_14001E45F
0x14001e43b  mov     eax, [rcx+2Ch]
0x14001e43e  test    al, 1
0x14001e440  jz      short loc_14001E45F
0x14001e442  cmp     byte ptr [rcx+29h], 2
0x14001e446  jb      short loc_14001E45F
0x14001e448  mov     rcx, [rcx+18h]
0x14001e44c  mov     edx, 52h ; 'R'
0x14001e451  mov     r9d, 0C000000Dh
0x14001e457  mov     r8, r13
0x14001e45a  call    WPP_SF_d
0x14001e45f  mov     dl, bpl; NewIrql
0x14001e462  lea     rcx, InterfaceLock; SpinLock
0x14001e469  call    cs:__imp_KeReleaseSpinLock
0x14001e470  nop     dword ptr [rax+rax+00h]
0x14001e475  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e47c  cmp     rcx, r12
0x14001e47f  jz      short loc_14001E4C6
0x14001e481  mov     eax, [rcx+2Ch]
0x14001e484  test    al, 1
0x14001e486  jz      short loc_14001E4C6
0x14001e488  cmp     byte ptr [rcx+29h], 6
0x14001e48c  jb      short loc_14001E4C6
0x14001e48e  mov     edx, 53h ; 'S'
0x14001e493  jmp     short loc_14001E4B4
0x14001e495  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e49c  cmp     rcx, r12
0x14001e49f  jz      short loc_14001E4C6
0x14001e4a1  mov     edx, [rcx+2Ch]
0x14001e4a4  test    dl, 1
0x14001e4a7  jz      short loc_14001E4C6
0x14001e4a9  cmp     byte ptr [rcx+29h], 6
0x14001e4ad  jb      short loc_14001E4C6
0x14001e4af  mov     edx, 4Dh ; 'M'
0x14001e4b4  mov     rcx, [rcx+18h]
0x14001e4b8  mov     r9d, 0C000000Dh
0x14001e4be  mov     r8, r13
0x14001e4c1  call    WPP_SF_d
0x14001e4c6  mov     eax, 0C000000Dh
0x14001e4cb  add     rsp, 20h
0x14001e4cf  pop     r14
0x14001e4d1  pop     r13
0x14001e4d3  pop     r12
0x14001e4d5  pop     rdi
0x14001e4d6  pop     rsi
0x14001e4d7  pop     rbp
0x14001e4d8  pop     rbx
0x14001e4d9  retn
```
