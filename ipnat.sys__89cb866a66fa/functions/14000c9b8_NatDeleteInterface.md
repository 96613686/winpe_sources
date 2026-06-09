# NatDeleteInterface

- ea: `0x14000c9b8`
- end: `0x14000cbe6`
- name: `NatDeleteInterface`
- size: `558`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140002b38`
- `0x14000c8b0`

## callees

- `0x1400021bc`
- `0x14000bc50`
- `0x14000c9b8`
- `0x14000ccc8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000caa2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cb6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000caa2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cb6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca0b`

## pseudocode

```c
__int64 __fastcall NatDeleteInterface(unsigned int a1, __int64 a2)
{
  KIRQL v4; // di
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, a1);
  }
  v4 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  v5 = (_QWORD *)NatLookupInterface(a1, 0);
  v6 = v5;
  if ( !v5 || v5[5] != a2 )
  {
    KeReleaseSpinLock(&InterfaceLock, v4);
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v10;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 3221225485LL);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v10;
    }
    v12 = 43;
    goto LABEL_34;
  }
  v7 = *v5;
  if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v8 = (_QWORD *)v5[1], (_QWORD *)*v8 != v6) )
    __fastfail(3u);
  *v8 = v7;
  *(_QWORD *)(v7 + 8) = v8;
  v9 = 3LL * (v6[4] & 0xF);
  LODWORD(InterfaceCache[v9]) = 0;
  InterfaceCache[v9 + 1] = 0;
  InterfaceCache[v9 + 2] = 0;
  *((_DWORD *)v6 + 14) |= 0x80000000;
  if ( (v6[7] & 0x10) != 0 )
    _InterlockedDecrement(&FirewalledInterfaceCount);
  KeReleaseSpinLock(&InterfaceLock, v4);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 4, 0xFFFFFFFF) > 1 )
  {
    v10 = 259;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v10;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 259);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v10;
    }
    v12 = 45;
LABEL_34:
    WPP_SF_d(v11->AttachedDevice, v12, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, v10);
    return v10;
  }
  NatCleanupInterface(v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c9b8  push    rbx
0x14000c9ba  push    rsi
0x14000c9bb  push    rdi
0x14000c9bc  push    r14
0x14000c9be  push    r15
0x14000c9c0  sub     rsp, 20h
0x14000c9c4  mov     rsi, rdx
0x14000c9c7  mov     ebx, ecx
0x14000c9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9d0  lea     r14, WPP_GLOBAL_Control
0x14000c9d7  lea     r15, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c9de  cmp     rcx, r14
0x14000c9e1  jz      short loc_14000CA04
0x14000c9e3  mov     eax, [rcx+2Ch]
0x14000c9e6  test    al, 1
0x14000c9e8  jz      short loc_14000CA04
0x14000c9ea  cmp     byte ptr [rcx+29h], 6
0x14000c9ee  jb      short loc_14000CA04
0x14000c9f0  mov     rcx, [rcx+18h]
0x14000c9f4  mov     edx, 29h ; ')'
0x14000c9f9  mov     r9d, ebx
0x14000c9fc  mov     r8, r15
0x14000c9ff  call    WPP_SF_d
0x14000ca04  lea     rcx, InterfaceLock; SpinLock
0x14000ca0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ca12  nop     dword ptr [rax+rax+00h]
0x14000ca17  xor     edx, edx
0x14000ca19  mov     ecx, ebx
0x14000ca1b  mov     dil, al
0x14000ca1e  call    NatLookupInterface
0x14000ca23  mov     rbx, rax
0x14000ca26  test    rax, rax
0x14000ca29  jz      loc_14000CB61
0x14000ca2f  cmp     [rax+28h], rsi
0x14000ca33  jnz     loc_14000CB61
0x14000ca39  mov     rcx, [rax]
0x14000ca3c  cmp     [rcx+8], rax
0x14000ca40  jnz     loc_14000CB5A
0x14000ca46  mov     rax, [rax+8]
0x14000ca4a  cmp     [rax], rbx
0x14000ca4d  jnz     loc_14000CB5A
0x14000ca53  mov     [rax], rcx
0x14000ca56  mov     [rcx+8], rax
0x14000ca5a  mov     eax, [rbx+20h]
0x14000ca5d  mov     r8, cs:off_14002F058
0x14000ca64  and     eax, 0Fh
0x14000ca67  lea     rdx, [rax+rax*2]
0x14000ca6b  mov     dword ptr [r8+rdx*8], 0
0x14000ca73  mov     qword ptr [r8+rdx*8+8], 0
0x14000ca7c  mov     qword ptr [r8+rdx*8+10h], 0
0x14000ca85  bts     dword ptr [rbx+38h], 1Fh
0x14000ca8a  mov     eax, [rbx+38h]
0x14000ca8d  test    al, 10h
0x14000ca8f  jz      short loc_14000CA98
0x14000ca91  lock dec cs:FirewalledInterfaceCount
0x14000ca98  mov     dl, dil; NewIrql
0x14000ca9b  lea     rcx, InterfaceLock; SpinLock
0x14000caa2  call    cs:__imp_KeReleaseSpinLock
0x14000caa9  nop     dword ptr [rax+rax+00h]
0x14000caae  or      eax, 0FFFFFFFFh
0x14000cab1  lock xadd [rbx+10h], eax
0x14000cab6  sub     eax, 1
0x14000cab9  jle     short loc_14000CB21
0x14000cabb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cac2  mov     ebx, 103h
0x14000cac7  cmp     rcx, r14
0x14000caca  jz      loc_14000CBD7
0x14000cad0  mov     eax, [rcx+2Ch]
0x14000cad3  test    al, 1
0x14000cad5  jz      short loc_14000CAF1
0x14000cad7  cmp     byte ptr [rcx+29h], 2
0x14000cadb  jb      short loc_14000CAF1
0x14000cadd  mov     rcx, [rcx+18h]
0x14000cae1  mov     edx, 2Ch ; ','
0x14000cae6  mov     r9d, ebx
0x14000cae9  mov     r8, r15
0x14000caec  call    WPP_SF_d
0x14000caf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000caf8  cmp     rcx, r14
0x14000cafb  jz      loc_14000CBD7
0x14000cb01  mov     edx, [rcx+2Ch]
0x14000cb04  test    dl, 1
0x14000cb07  jz      loc_14000CBD7
0x14000cb0d  cmp     byte ptr [rcx+29h], 6
0x14000cb11  jb      loc_14000CBD7
0x14000cb17  mov     edx, 2Dh ; '-'
0x14000cb1c  jmp     loc_14000CBC8
0x14000cb21  mov     rcx, rbx; P
0x14000cb24  call    NatCleanupInterface
0x14000cb29  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb30  cmp     rcx, r14
0x14000cb33  jz      short loc_14000CB56
0x14000cb35  mov     eax, [rcx+2Ch]
0x14000cb38  test    al, 1
0x14000cb3a  jz      short loc_14000CB56
0x14000cb3c  cmp     byte ptr [rcx+29h], 6
0x14000cb40  jb      short loc_14000CB56
0x14000cb42  mov     rcx, [rcx+18h]
0x14000cb46  mov     edx, 2Eh ; '.'
0x14000cb4b  xor     r9d, r9d
0x14000cb4e  mov     r8, r15
0x14000cb51  call    WPP_SF_d
0x14000cb56  xor     eax, eax
0x14000cb58  jmp     short loc_14000CBD9
0x14000cb5a  mov     ecx, 3
0x14000cb5f  int     29h; Win8: RtlFailFast(ecx)
0x14000cb61  mov     dl, dil; NewIrql
0x14000cb64  lea     rcx, InterfaceLock; SpinLock
0x14000cb6b  call    cs:__imp_KeReleaseSpinLock
0x14000cb72  nop     dword ptr [rax+rax+00h]
0x14000cb77  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb7e  mov     ebx, 0C000000Dh
0x14000cb83  cmp     rcx, r14
0x14000cb86  jz      short loc_14000CBD7
0x14000cb88  mov     eax, [rcx+2Ch]
0x14000cb8b  test    al, 1
0x14000cb8d  jz      short loc_14000CBA9
0x14000cb8f  cmp     byte ptr [rcx+29h], 2
0x14000cb93  jb      short loc_14000CBA9
0x14000cb95  mov     rcx, [rcx+18h]
0x14000cb99  mov     edx, 2Ah ; '*'
0x14000cb9e  mov     r9d, ebx
0x14000cba1  mov     r8, r15
0x14000cba4  call    WPP_SF_d
0x14000cba9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbb0  cmp     rcx, r14
0x14000cbb3  jz      short loc_14000CBD7
0x14000cbb5  mov     edx, [rcx+2Ch]
0x14000cbb8  test    dl, 1
0x14000cbbb  jz      short loc_14000CBD7
0x14000cbbd  cmp     byte ptr [rcx+29h], 6
0x14000cbc1  jb      short loc_14000CBD7
0x14000cbc3  mov     edx, 2Bh ; '+'
0x14000cbc8  mov     rcx, [rcx+18h]
0x14000cbcc  mov     r9d, ebx
0x14000cbcf  mov     r8, r15
0x14000cbd2  call    WPP_SF_d
0x14000cbd7  mov     eax, ebx
0x14000cbd9  add     rsp, 20h
0x14000cbdd  pop     r15
0x14000cbdf  pop     r14
0x14000cbe1  pop     rdi
0x14000cbe2  pop     rsi
0x14000cbe3  pop     rbx
0x14000cbe4  retn
```
