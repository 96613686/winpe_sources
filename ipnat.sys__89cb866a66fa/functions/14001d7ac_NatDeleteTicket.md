# NatDeleteTicket

- ea: `0x14001d7ac`
- end: `0x14001d882`
- name: `NatDeleteTicket`
- size: `214`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400058c0`
- `0x14000d50c`
- `0x14001379c`
- `0x14001e4e4`
- `0x14001f110`

## callees

- `0x14000218c`
- `0x140006e18`
- `0x1400138fc`
- `0x14001d7ac`

## pseudocode

```c
void __fastcall NatDeleteTicket(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  _InterlockedDecrement(&TicketCount);
  v4 = *a2;
  if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v5 = (_QWORD *)a2[1], (_QWORD *)*v5 != a2) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  v6 = a2[4];
  if ( v6 )
    NatDereferenceAddressPoolEntry(a1, v6);
  NatFreeBlockAndUpdateStateAllocationUsage(&TicketLookasideList, a2, 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
}

```

## disassembly

```asm
0x14001d7ac  mov     [rsp+arg_0], rbx
0x14001d7b1  mov     [rsp+arg_8], rsi
0x14001d7b6  push    rdi
0x14001d7b7  sub     rsp, 20h
0x14001d7bb  mov     rbx, rdx
0x14001d7be  mov     rdi, rcx
0x14001d7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d7c8  lea     rsi, WPP_GLOBAL_Control
0x14001d7cf  cmp     rcx, rsi
0x14001d7d2  jz      short loc_14001D7F6
0x14001d7d4  mov     eax, [rcx+2Ch]
0x14001d7d7  test    al, 1
0x14001d7d9  jz      short loc_14001D7F6
0x14001d7db  cmp     byte ptr [rcx+29h], 6
0x14001d7df  jb      short loc_14001D7F6
0x14001d7e1  mov     rcx, [rcx+18h]
0x14001d7e5  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d7ec  mov     edx, 30h ; '0'
0x14001d7f1  call    WPP_SF_
0x14001d7f6  lock dec cs:TicketCount
0x14001d7fd  mov     rax, [rbx]
0x14001d800  cmp     [rax+8], rbx
0x14001d804  jnz     short loc_14001D87B
0x14001d806  mov     rcx, [rbx+8]
0x14001d80a  cmp     [rcx], rbx
0x14001d80d  jnz     short loc_14001D87B
0x14001d80f  mov     [rcx], rax
0x14001d812  mov     [rax+8], rcx
0x14001d816  mov     rdx, [rbx+20h]
0x14001d81a  test    rdx, rdx
0x14001d81d  jz      short loc_14001D827
0x14001d81f  mov     rcx, rdi
0x14001d822  call    NatDereferenceAddressPoolEntry
0x14001d827  mov     r8d, 40h ; '@'
0x14001d82d  lea     rcx, TicketLookasideList; Lookaside
0x14001d834  mov     rdx, rbx; Entry
0x14001d837  call    NatFreeBlockAndUpdateStateAllocationUsage
0x14001d83c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d843  cmp     rcx, rsi
0x14001d846  jz      short loc_14001D86A
0x14001d848  mov     eax, [rcx+2Ch]
0x14001d84b  test    al, 1
0x14001d84d  jz      short loc_14001D86A
0x14001d84f  cmp     byte ptr [rcx+29h], 6
0x14001d853  jb      short loc_14001D86A
0x14001d855  mov     rcx, [rcx+18h]
0x14001d859  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d860  mov     edx, 31h ; '1'
0x14001d865  call    WPP_SF_
0x14001d86a  mov     rbx, [rsp+28h+arg_0]
0x14001d86f  mov     rsi, [rsp+28h+arg_8]
0x14001d874  add     rsp, 20h
0x14001d878  pop     rdi
0x14001d879  retn
0x14001d87b  mov     ecx, 3
0x14001d880  int     29h; Win8: RtlFailFast(ecx)
```
