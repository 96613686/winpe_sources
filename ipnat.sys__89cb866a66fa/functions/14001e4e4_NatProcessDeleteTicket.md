# NatProcessDeleteTicket

- ea: `0x14001e4e4`
- end: `0x14001e86e`
- name: `NatProcessDeleteTicket`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000bc50`
- `0x14000ccc8`
- `0x140011e00`
- `0x1400138fc`
- `0x14001d7ac`
- `0x14001e0f8`
- `0x14001e4e4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001e6b3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001e6b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e5cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e64a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e736`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e7c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e5cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e64a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e736`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e7c5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001e6a3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001e6a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e575`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e575`

## pseudocode

```c
__int64 __fastcall NatProcessDeleteTicket(unsigned int *a1, __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // rsi
  KIRQL v6; // bp
  __int64 v7; // rax
  __int64 v8; // rbx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // edi
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  v4 = *a1 - 1;
  v16 = 0;
  if ( v4 > 0xFFFFFFFD || (v5 = *((unsigned __int8 *)a1 + 4), (_BYTE)v5 != 6) && (_BYTE)v5 != 17 || !*((_WORD *)a1 + 3) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225485LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v10 = 87;
    goto LABEL_58;
  }
  v6 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  v7 = NatLookupInterface(*a1, 0);
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    }
    KeReleaseSpinLock(&InterfaceLock, v6);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v10 = 89;
LABEL_58:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    return 3221225485LL;
  }
  if ( *(_QWORD *)(v7 + 40) == a2 )
  {
    if ( *(int *)(v7 + 56) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
      }
      KeReleaseSpinLock(&InterfaceLock, v6);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 3221225485LL;
      }
      v10 = 93;
      goto LABEL_58;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 16));
    v12 = v5 << 48;
    KeReleaseSpinLockFromDpcLevel(&InterfaceLock);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 24));
    if ( !a1[2] && (int)NatAcquireFromAddressPool(v8, a1[4], 0, &v16) >= 0 )
    {
      v13 = v16;
      a1[2] = *(_DWORD *)(v16 + 52);
      NatDereferenceAddressPoolEntry(v8, v13);
    }
    v14 = NatLookupTicket(
            v8,
            a1[2] | ((*((unsigned __int16 *)a1 + 3) | ((unsigned __int64)*((unsigned __int8 *)a1 + 4) << 16)) << 32),
            v12,
            0);
    if ( v14 )
    {
      NatDeleteTicket(v8, v14);
      v15 = 0;
    }
    else
    {
      v15 = -1073741275;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 24), v6);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 16), 0xFFFFFFFF) == 1 )
      NatCleanupInterface((PVOID)v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, v15);
    }
    return v15;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225506LL);
    }
    KeReleaseSpinLock(&InterfaceLock, v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225506LL);
    }
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x14001e4e4  mov     [rsp+arg_8], rbx
0x14001e4e9  mov     [rsp+arg_10], rbp
0x14001e4ee  push    rsi
0x14001e4ef  push    rdi
0x14001e4f0  push    r12
0x14001e4f2  push    r13
0x14001e4f4  push    r14
0x14001e4f6  sub     rsp, 20h
0x14001e4fa  mov     r14, rdx
0x14001e4fd  mov     rdi, rcx
0x14001e500  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e507  lea     r12, WPP_GLOBAL_Control
0x14001e50e  lea     r13, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001e515  mov     bl, 6
0x14001e517  cmp     rcx, r12
0x14001e51a  jz      short loc_14001E539
0x14001e51c  mov     eax, [rcx+2Ch]
0x14001e51f  test    al, 1
0x14001e521  jz      short loc_14001E539
0x14001e523  cmp     [rcx+29h], bl
0x14001e526  jb      short loc_14001E539
0x14001e528  mov     rcx, [rcx+18h]
0x14001e52c  mov     edx, 55h ; 'U'
0x14001e531  mov     r8, r13
0x14001e534  call    WPP_SF_
0x14001e539  mov     eax, [rdi]
0x14001e53b  dec     eax
0x14001e53d  mov     [rsp+48h+arg_0], 0
0x14001e546  cmp     eax, 0FFFFFFFDh
0x14001e549  ja      loc_14001E7F1
0x14001e54f  movzx   esi, byte ptr [rdi+4]
0x14001e553  cmp     sil, bl
0x14001e556  jz      short loc_14001E562
0x14001e558  cmp     sil, 11h
0x14001e55c  jnz     loc_14001E7F1
0x14001e562  xor     eax, eax
0x14001e564  cmp     ax, [rdi+6]
0x14001e568  jz      loc_14001E7F1
0x14001e56e  lea     rcx, InterfaceLock; SpinLock
0x14001e575  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001e57c  nop     dword ptr [rax+rax+00h]
0x14001e581  mov     ecx, [rdi]
0x14001e583  xor     edx, edx
0x14001e585  mov     bpl, al
0x14001e588  call    NatLookupInterface
0x14001e58d  mov     rbx, rax
0x14001e590  test    rax, rax
0x14001e593  jnz     short loc_14001E608
0x14001e595  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e59c  cmp     rcx, r12
0x14001e59f  jz      short loc_14001E5C3
0x14001e5a1  mov     eax, [rcx+2Ch]
0x14001e5a4  test    al, 1
0x14001e5a6  jz      short loc_14001E5C3
0x14001e5a8  cmp     byte ptr [rcx+29h], 2
0x14001e5ac  jb      short loc_14001E5C3
0x14001e5ae  mov     rcx, [rcx+18h]
0x14001e5b2  lea     edx, [rbx+58h]
0x14001e5b5  mov     r9d, 0C000000Dh
0x14001e5bb  mov     r8, r13
0x14001e5be  call    WPP_SF_d
0x14001e5c3  mov     dl, bpl; NewIrql
0x14001e5c6  lea     rcx, InterfaceLock; SpinLock
0x14001e5cd  call    cs:__imp_KeReleaseSpinLock
0x14001e5d4  nop     dword ptr [rax+rax+00h]
0x14001e5d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5e0  cmp     rcx, r12
0x14001e5e3  jz      loc_14001E851
0x14001e5e9  mov     eax, [rcx+2Ch]
0x14001e5ec  test    al, 1
0x14001e5ee  jz      loc_14001E851
0x14001e5f4  cmp     byte ptr [rcx+29h], 6
0x14001e5f8  jb      loc_14001E851
0x14001e5fe  mov     edx, 59h ; 'Y'
0x14001e603  jmp     loc_14001E83F
0x14001e608  cmp     [rax+28h], r14
0x14001e60c  jz      short loc_14001E68A
0x14001e60e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e615  mov     ebx, 0C0000022h
0x14001e61a  cmp     rcx, r12
0x14001e61d  jz      short loc_14001E640
0x14001e61f  mov     eax, [rcx+2Ch]
0x14001e622  test    al, 1
0x14001e624  jz      short loc_14001E640
0x14001e626  cmp     byte ptr [rcx+29h], 2
0x14001e62a  jb      short loc_14001E640
0x14001e62c  mov     rcx, [rcx+18h]
0x14001e630  mov     edx, 5Ah ; 'Z'
0x14001e635  mov     r9d, ebx
0x14001e638  mov     r8, r13
0x14001e63b  call    WPP_SF_d
0x14001e640  mov     dl, bpl; NewIrql
0x14001e643  lea     rcx, InterfaceLock; SpinLock
0x14001e64a  call    cs:__imp_KeReleaseSpinLock
0x14001e651  nop     dword ptr [rax+rax+00h]
0x14001e656  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e65d  cmp     rcx, r12
0x14001e660  jz      short loc_14001E683
0x14001e662  mov     eax, [rcx+2Ch]
0x14001e665  test    al, 1
0x14001e667  jz      short loc_14001E683
0x14001e669  cmp     byte ptr [rcx+29h], 6
0x14001e66d  jb      short loc_14001E683
0x14001e66f  mov     rcx, [rcx+18h]
0x14001e673  mov     edx, 5Bh ; '['
0x14001e678  mov     r9d, ebx
0x14001e67b  mov     r8, r13
0x14001e67e  call    WPP_SF_d
0x14001e683  mov     eax, ebx
0x14001e685  jmp     loc_14001E856
0x14001e68a  cmp     dword ptr [rax+38h], 0
0x14001e68e  jl      loc_14001E78B
0x14001e694  lock inc dword ptr [rax+10h]
0x14001e698  lea     rcx, InterfaceLock; SpinLock
0x14001e69f  shl     rsi, 30h
0x14001e6a3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001e6aa  nop     dword ptr [rax+rax+00h]
0x14001e6af  lea     rcx, [rbx+18h]; SpinLock
0x14001e6b3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001e6ba  nop     dword ptr [rax+rax+00h]
0x14001e6bf  cmp     dword ptr [rdi+8], 0
0x14001e6c3  jnz     short loc_14001E6EF
0x14001e6c5  mov     edx, [rdi+10h]
0x14001e6c8  lea     r9, [rsp+48h+arg_0]
0x14001e6cd  xor     r8d, r8d
0x14001e6d0  mov     rcx, rbx
0x14001e6d3  call    NatAcquireFromAddressPool
0x14001e6d8  test    eax, eax
0x14001e6da  js      short loc_14001E6EF
0x14001e6dc  mov     rdx, [rsp+48h+arg_0]
0x14001e6e1  mov     rcx, rbx
0x14001e6e4  mov     eax, [rdx+34h]
0x14001e6e7  mov     [rdi+8], eax
0x14001e6ea  call    NatDereferenceAddressPoolEntry
0x14001e6ef  movzx   eax, word ptr [rdi+6]
0x14001e6f3  xor     r9d, r9d
0x14001e6f6  movzx   edx, byte ptr [rdi+4]
0x14001e6fa  mov     r8, rsi
0x14001e6fd  shl     rdx, 10h
0x14001e701  mov     rcx, rbx
0x14001e704  or      rdx, rax
0x14001e707  mov     eax, [rdi+8]
0x14001e70a  shl     rdx, 20h
0x14001e70e  or      rdx, rax
0x14001e711  call    NatLookupTicket
0x14001e716  test    rax, rax
0x14001e719  jz      short loc_14001E72A
0x14001e71b  mov     rdx, rax
0x14001e71e  mov     rcx, rbx
0x14001e721  call    NatDeleteTicket
0x14001e726  xor     edi, edi
0x14001e728  jmp     short loc_14001E72F
0x14001e72a  mov     edi, 0C0000225h
0x14001e72f  mov     dl, bpl; NewIrql
0x14001e732  lea     rcx, [rbx+18h]; SpinLock
0x14001e736  call    cs:__imp_KeReleaseSpinLock
0x14001e73d  nop     dword ptr [rax+rax+00h]
0x14001e742  or      eax, 0FFFFFFFFh
0x14001e745  lock xadd [rbx+10h], eax
0x14001e74a  cmp     eax, 1
0x14001e74d  jnz     short loc_14001E757
0x14001e74f  mov     rcx, rbx; P
0x14001e752  call    NatCleanupInterface
0x14001e757  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e75e  cmp     rcx, r12
0x14001e761  jz      short loc_14001E784
0x14001e763  mov     eax, [rcx+2Ch]
0x14001e766  test    al, 1
0x14001e768  jz      short loc_14001E784
0x14001e76a  cmp     byte ptr [rcx+29h], 6
0x14001e76e  jb      short loc_14001E784
0x14001e770  mov     rcx, [rcx+18h]
0x14001e774  mov     edx, 5Eh ; '^'
0x14001e779  mov     r9d, edi
0x14001e77c  mov     r8, r13
0x14001e77f  call    WPP_SF_d
0x14001e784  mov     eax, edi
0x14001e786  jmp     loc_14001E856
0x14001e78b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e792  cmp     rcx, r12
0x14001e795  jz      short loc_14001E7BB
0x14001e797  mov     eax, [rcx+2Ch]
0x14001e79a  test    al, 1
0x14001e79c  jz      short loc_14001E7BB
0x14001e79e  cmp     byte ptr [rcx+29h], 2
0x14001e7a2  jb      short loc_14001E7BB
0x14001e7a4  mov     rcx, [rcx+18h]
0x14001e7a8  mov     edx, 5Ch ; '\'
0x14001e7ad  mov     r9d, 0C000000Dh
0x14001e7b3  mov     r8, r13
0x14001e7b6  call    WPP_SF_d
0x14001e7bb  mov     dl, bpl; NewIrql
0x14001e7be  lea     rcx, InterfaceLock; SpinLock
0x14001e7c5  call    cs:__imp_KeReleaseSpinLock
0x14001e7cc  nop     dword ptr [rax+rax+00h]
0x14001e7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7d8  cmp     rcx, r12
0x14001e7db  jz      short loc_14001E851
0x14001e7dd  mov     eax, [rcx+2Ch]
0x14001e7e0  test    al, 1
0x14001e7e2  jz      short loc_14001E851
0x14001e7e4  cmp     byte ptr [rcx+29h], 6
0x14001e7e8  jb      short loc_14001E851
0x14001e7ea  mov     edx, 5Dh ; ']'
0x14001e7ef  jmp     short loc_14001E83F
0x14001e7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7f8  cmp     rcx, r12
0x14001e7fb  jz      short loc_14001E851
0x14001e7fd  mov     eax, [rcx+2Ch]
0x14001e800  test    al, 1
0x14001e802  jz      short loc_14001E821
0x14001e804  cmp     byte ptr [rcx+29h], 2
0x14001e808  jb      short loc_14001E821
0x14001e80a  mov     rcx, [rcx+18h]
0x14001e80e  mov     edx, 56h ; 'V'
0x14001e813  mov     r9d, 0C000000Dh
0x14001e819  mov     r8, r13
0x14001e81c  call    WPP_SF_d
0x14001e821  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e828  cmp     rcx, r12
0x14001e82b  jz      short loc_14001E851
0x14001e82d  mov     edx, [rcx+2Ch]
0x14001e830  test    dl, 1
0x14001e833  jz      short loc_14001E851
0x14001e835  cmp     [rcx+29h], bl
0x14001e838  jb      short loc_14001E851
0x14001e83a  mov     edx, 57h ; 'W'
0x14001e83f  mov     rcx, [rcx+18h]
0x14001e843  mov     r9d, 0C000000Dh
0x14001e849  mov     r8, r13
0x14001e84c  call    WPP_SF_d
0x14001e851  mov     eax, 0C000000Dh
0x14001e856  mov     rbx, [rsp+48h+arg_8]
0x14001e85b  mov     rbp, [rsp+48h+arg_10]
0x14001e860  add     rsp, 20h
0x14001e864  pop     r14
0x14001e866  pop     r13
0x14001e868  pop     r12
0x14001e86a  pop     rdi
0x14001e86b  pop     rsi
0x14001e86c  retn
```
