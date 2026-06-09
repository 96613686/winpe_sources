# NatDeleteDynamicTicket

- ea: `0x14001d59c`
- end: `0x14001d7a5`
- name: `NatDeleteDynamicTicket`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14001d59c`
- `0x14001df0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d741`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d741`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d660`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d6f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d757`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d660`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d6f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d757`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d600`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d600`

## pseudocode

```c
__int64 __fastcall NatDeleteDynamicTicket(unsigned __int8 *a1, __int64 a2)
{
  unsigned int v4; // ebx
  KIRQL v5; // si
  _QWORD *v6; // rax
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  char v13; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  v4 = *((unsigned __int16 *)a1 + 1) | (*a1 << 16);
  v5 = KeAcquireSpinLockRaiseToDpc(&DynamicTicketLock);
  v6 = (_QWORD *)NatLookupDynamicTicket(v4, &v13);
  if ( !v6 )
  {
    v7 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
    }
    KeReleaseSpinLock(&DynamicTicketLock, v5);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v7;
    }
    v9 = 44;
LABEL_14:
    WPP_SF_d(v8->AttachedDevice, v9, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, v7);
    return v7;
  }
  if ( v6[4] != a2 )
  {
    v7 = -1073741790;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225506LL);
    }
    KeReleaseSpinLock(&DynamicTicketLock, v5);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v7;
    }
    v9 = 46;
    goto LABEL_14;
  }
  v11 = *v6;
  if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v12 = (_QWORD *)v6[1], (_QWORD *)*v12 != v6) )
    __fastfail(3u);
  *v12 = v11;
  *(_QWORD *)(v11 + 8) = v12;
  ExFreePoolWithTag(v6, 0);
  KeReleaseSpinLock(&DynamicTicketLock, v5);
  _InterlockedDecrement(&DynamicTicketCount);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001d59c  mov     [rsp+arg_8], rbx
0x14001d5a1  mov     [rsp+arg_10], rsi
0x14001d5a6  push    rdi
0x14001d5a7  push    r14
0x14001d5a9  push    r15
0x14001d5ab  sub     rsp, 20h
0x14001d5af  mov     rdi, rdx
0x14001d5b2  mov     rsi, rcx
0x14001d5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5bc  lea     r15, WPP_GLOBAL_Control
0x14001d5c3  lea     r14, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d5ca  cmp     rcx, r15
0x14001d5cd  jz      short loc_14001D5ED
0x14001d5cf  mov     eax, [rcx+2Ch]
0x14001d5d2  test    al, 1
0x14001d5d4  jz      short loc_14001D5ED
0x14001d5d6  cmp     byte ptr [rcx+29h], 6
0x14001d5da  jb      short loc_14001D5ED
0x14001d5dc  mov     rcx, [rcx+18h]
0x14001d5e0  mov     edx, 2Ah ; '*'
0x14001d5e5  mov     r8, r14
0x14001d5e8  call    WPP_SF_
0x14001d5ed  movzx   ebx, byte ptr [rsi]
0x14001d5f0  lea     rcx, DynamicTicketLock; SpinLock
0x14001d5f7  movzx   eax, word ptr [rsi+2]
0x14001d5fb  shl     ebx, 10h
0x14001d5fe  or      ebx, eax
0x14001d600  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001d607  nop     dword ptr [rax+rax+00h]
0x14001d60c  lea     rdx, [rsp+38h+arg_0]
0x14001d611  mov     ecx, ebx
0x14001d613  mov     sil, al
0x14001d616  call    NatLookupDynamicTicket
0x14001d61b  test    rax, rax
0x14001d61e  jnz     loc_14001D6B1
0x14001d624  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d62b  mov     ebx, 0C0000001h
0x14001d630  cmp     rcx, r15
0x14001d633  jz      short loc_14001D656
0x14001d635  mov     eax, [rcx+2Ch]
0x14001d638  test    al, 1
0x14001d63a  jz      short loc_14001D656
0x14001d63c  cmp     byte ptr [rcx+29h], 2
0x14001d640  jb      short loc_14001D656
0x14001d642  mov     rcx, [rcx+18h]
0x14001d646  mov     edx, 2Bh ; '+'
0x14001d64b  mov     r9d, ebx
0x14001d64e  mov     r8, r14
0x14001d651  call    WPP_SF_d
0x14001d656  mov     dl, sil; NewIrql
0x14001d659  lea     rcx, DynamicTicketLock; SpinLock
0x14001d660  call    cs:__imp_KeReleaseSpinLock
0x14001d667  nop     dword ptr [rax+rax+00h]
0x14001d66c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d673  cmp     rcx, r15
0x14001d676  jz      short loc_14001D69A
0x14001d678  mov     edx, [rcx+2Ch]
0x14001d67b  test    dl, 1
0x14001d67e  jz      short loc_14001D69A
0x14001d680  cmp     byte ptr [rcx+29h], 6
0x14001d684  jb      short loc_14001D69A
0x14001d686  mov     edx, 2Ch ; ','
0x14001d68b  mov     rcx, [rcx+18h]
0x14001d68f  mov     r9d, ebx
0x14001d692  mov     r8, r14
0x14001d695  call    WPP_SF_d
0x14001d69a  mov     eax, ebx
0x14001d69c  mov     rbx, [rsp+38h+arg_8]
0x14001d6a1  mov     rsi, [rsp+38h+arg_10]
0x14001d6a6  add     rsp, 20h
0x14001d6aa  pop     r15
0x14001d6ac  pop     r14
0x14001d6ae  pop     rdi
0x14001d6af  retn
0x14001d6b1  cmp     [rax+20h], rdi
0x14001d6b5  jz      short loc_14001D723
0x14001d6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6be  mov     ebx, 0C0000022h
0x14001d6c3  cmp     rcx, r15
0x14001d6c6  jz      short loc_14001D6E9
0x14001d6c8  mov     eax, [rcx+2Ch]
0x14001d6cb  test    al, 1
0x14001d6cd  jz      short loc_14001D6E9
0x14001d6cf  cmp     byte ptr [rcx+29h], 2
0x14001d6d3  jb      short loc_14001D6E9
0x14001d6d5  mov     rcx, [rcx+18h]
0x14001d6d9  mov     edx, 2Dh ; '-'
0x14001d6de  mov     r9d, ebx
0x14001d6e1  mov     r8, r14
0x14001d6e4  call    WPP_SF_d
0x14001d6e9  mov     dl, sil; NewIrql
0x14001d6ec  lea     rcx, DynamicTicketLock; SpinLock
0x14001d6f3  call    cs:__imp_KeReleaseSpinLock
0x14001d6fa  nop     dword ptr [rax+rax+00h]
0x14001d6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d706  cmp     rcx, r15
0x14001d709  jz      short loc_14001D69A
0x14001d70b  mov     edx, [rcx+2Ch]
0x14001d70e  test    dl, 1
0x14001d711  jz      short loc_14001D69A
0x14001d713  cmp     byte ptr [rcx+29h], 6
0x14001d717  jb      short loc_14001D69A
0x14001d719  mov     edx, 2Eh ; '.'
0x14001d71e  jmp     loc_14001D68B
0x14001d723  mov     rcx, [rax]
0x14001d726  cmp     [rcx+8], rax
0x14001d72a  jnz     short loc_14001D79E
0x14001d72c  mov     rdx, [rax+8]
0x14001d730  cmp     [rdx], rax
0x14001d733  jnz     short loc_14001D79E
0x14001d735  mov     [rdx], rcx
0x14001d738  mov     [rcx+8], rdx
0x14001d73c  xor     edx, edx; Tag
0x14001d73e  mov     rcx, rax; P
0x14001d741  call    cs:__imp_ExFreePoolWithTag
0x14001d748  nop     dword ptr [rax+rax+00h]
0x14001d74d  mov     dl, sil; NewIrql
0x14001d750  lea     rcx, DynamicTicketLock; SpinLock
0x14001d757  call    cs:__imp_KeReleaseSpinLock
0x14001d75e  nop     dword ptr [rax+rax+00h]
0x14001d763  lock dec cs:DynamicTicketCount
0x14001d76a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d771  cmp     rcx, r15
0x14001d774  jz      short loc_14001D797
0x14001d776  mov     eax, [rcx+2Ch]
0x14001d779  test    al, 1
0x14001d77b  jz      short loc_14001D797
0x14001d77d  cmp     byte ptr [rcx+29h], 6
0x14001d781  jb      short loc_14001D797
0x14001d783  mov     rcx, [rcx+18h]
0x14001d787  mov     edx, 2Fh ; '/'
0x14001d78c  xor     r9d, r9d
0x14001d78f  mov     r8, r14
0x14001d792  call    WPP_SF_d
0x14001d797  xor     eax, eax
0x14001d799  jmp     loc_14001D69C
0x14001d79e  mov     ecx, 3
0x14001d7a3  int     29h; Win8: RtlFailFast(ecx)
```
