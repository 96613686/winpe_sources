# NatDeleteAnyAssociatedDynamicTicket

- ea: `0x14001d490`
- end: `0x14001d596`
- name: `NatDeleteAnyAssociatedDynamicTicket`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002260`

## callees

- `0x14000218c`
- `0x14001d490`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d524`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d524`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d549`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d549`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d4da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d4da`

## pseudocode

```c
void __fastcall NatDeleteAnyAssociatedDynamicTicket(PVOID a1)
{
  KIRQL v2; // al
  PVOID *v3; // rbx
  KIRQL v4; // si
  PVOID v5; // rdx
  PVOID *v6; // rax
  PVOID *v7; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc(&DynamicTicketLock);
  v3 = (PVOID *)DynamicTicketList;
  v4 = v2;
  while ( v3 != &DynamicTicketList )
  {
    if ( v3[4] == a1 )
    {
      v5 = *v3;
      if ( *((PVOID **)*v3 + 1) != v3 || (v6 = (PVOID *)v3[1], *v6 != v3) )
        __fastfail(3u);
      *v6 = v5;
      v7 = v3;
      *((_QWORD *)v5 + 1) = v6;
      v3 = v6;
      ExFreePoolWithTag(v7, 0);
      _InterlockedDecrement(&DynamicTicketCount);
    }
    v3 = (PVOID *)*v3;
  }
  KeReleaseSpinLock(&DynamicTicketLock, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
}

```

## disassembly

```asm
0x14001d490  push    rbx
0x14001d492  push    rbp
0x14001d493  push    rsi
0x14001d494  push    rdi
0x14001d495  push    r14
0x14001d497  sub     rsp, 20h
0x14001d49b  mov     rdi, rcx
0x14001d49e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d4a5  lea     rbp, WPP_GLOBAL_Control
0x14001d4ac  cmp     rcx, rbp
0x14001d4af  jz      short loc_14001D4D3
0x14001d4b1  mov     eax, [rcx+2Ch]
0x14001d4b4  test    al, 1
0x14001d4b6  jz      short loc_14001D4D3
0x14001d4b8  cmp     byte ptr [rcx+29h], 6
0x14001d4bc  jb      short loc_14001D4D3
0x14001d4be  mov     rcx, [rcx+18h]
0x14001d4c2  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d4c9  mov     edx, 28h ; '('
0x14001d4ce  call    WPP_SF_
0x14001d4d3  lea     rcx, DynamicTicketLock; SpinLock
0x14001d4da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001d4e1  nop     dword ptr [rax+rax+00h]
0x14001d4e6  mov     rbx, cs:DynamicTicketList
0x14001d4ed  lea     r14, DynamicTicketList
0x14001d4f4  mov     sil, al
0x14001d4f7  jmp     short loc_14001D53A
0x14001d4f9  cmp     [rbx+20h], rdi
0x14001d4fd  jnz     short loc_14001D537
0x14001d4ff  mov     rdx, [rbx]
0x14001d502  cmp     [rdx+8], rbx
0x14001d506  jnz     loc_14001D58F
0x14001d50c  mov     rax, [rbx+8]
0x14001d510  cmp     [rax], rbx
0x14001d513  jnz     short loc_14001D58F
0x14001d515  mov     [rax], rdx
0x14001d518  mov     rcx, rbx; P
0x14001d51b  mov     [rdx+8], rax
0x14001d51f  mov     rbx, rax
0x14001d522  xor     edx, edx; Tag
0x14001d524  call    cs:__imp_ExFreePoolWithTag
0x14001d52b  nop     dword ptr [rax+rax+00h]
0x14001d530  lock dec cs:DynamicTicketCount
0x14001d537  mov     rbx, [rbx]
0x14001d53a  cmp     rbx, r14
0x14001d53d  jnz     short loc_14001D4F9
0x14001d53f  mov     dl, sil; NewIrql
0x14001d542  lea     rcx, DynamicTicketLock; SpinLock
0x14001d549  call    cs:__imp_KeReleaseSpinLock
0x14001d550  nop     dword ptr [rax+rax+00h]
0x14001d555  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d55c  cmp     rcx, rbp
0x14001d55f  jz      short loc_14001D583
0x14001d561  mov     eax, [rcx+2Ch]
0x14001d564  test    al, 1
0x14001d566  jz      short loc_14001D583
0x14001d568  cmp     byte ptr [rcx+29h], 6
0x14001d56c  jb      short loc_14001D583
0x14001d56e  mov     rcx, [rcx+18h]
0x14001d572  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d579  mov     edx, 29h ; ')'
0x14001d57e  call    WPP_SF_
0x14001d583  add     rsp, 20h
0x14001d587  pop     r14
0x14001d589  pop     rdi
0x14001d58a  pop     rsi
0x14001d58b  pop     rbp
0x14001d58c  pop     rbx
0x14001d58d  retn
0x14001d58f  mov     ecx, 3
0x14001d594  int     29h; Win8: RtlFailFast(ecx)
```
