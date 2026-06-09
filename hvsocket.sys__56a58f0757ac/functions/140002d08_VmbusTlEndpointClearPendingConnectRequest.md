# VmbusTlEndpointClearPendingConnectRequest

- ea: `0x140002d08`
- end: `0x140002e40`
- name: `VmbusTlEndpointClearPendingConnectRequest`
- size: `312`
- prototype: `void __fastcall(char *P)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400023b0`
- `0x140020b80`

## callees

- `0x140002d08`
- `0x1400058d0`
- `0x140009834`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002e2d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002e17`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002e17`

## pseudocode

```c
void __fastcall VmbusTlEndpointClearPendingConnectRequest(char *P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  signed __int64 v5; // rax
  signed __int64 v6; // rax
  void (__fastcall *v7)(char *); // rax

  *((_QWORD *)P + 84) = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlEndpointClearPendingConnectRequest",
      186,
      (__int64)P,
      *((_QWORD *)P + 38),
      (const int *)"Client outbound connect request (deref)");
  v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 38, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    if ( (unsigned int)dword_140013058 > 4 )
      HvsocketTraceEndpointEvent(
        (const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.",
        (__int64)P,
        9);
    VmbusTlQueueEndpointAction(P, P + 200, 9);
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlEndpointClearPendingConnectRequest",
      187,
      (__int64)P,
      *((_QWORD *)P + 1),
      (const int *)"Dereference object");
  v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v5 <= 1;
  v6 = v5 - 1;
  if ( v3 )
  {
    if ( v6 )
      __fastfail(0xEu);
    v7 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
    if ( v7 )
      v7(P);
    if ( *((_DWORD *)P + 22) == 1 )
    {
      ExFreePoolWithTag(P, 0x69706E56u);
    }
    else if ( *((_DWORD *)P + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
    }
  }
}

```

## disassembly

```asm
0x140002d08  push    rbx
0x140002d0a  sub     rsp, 30h
0x140002d0e  mov     qword ptr [rcx+2A0h], 0
0x140002d19  mov     rbx, rcx
0x140002d1c  mov     eax, cs:dword_140013058
0x140002d22  cmp     eax, 5
0x140002d25  jbe     short loc_140002D4E
0x140002d27  mov     r9, [rcx+130h]
0x140002d2e  lea     rax, aClientOutbound_0; "Client outbound connect request (deref)"
0x140002d35  mov     r8, rcx
0x140002d38  mov     [rsp+38h+var_18], rax
0x140002d3d  lea     rcx, aVmbustlendpoin; "VmbusTlEndpointClearPendingConnectReque"...
0x140002d44  mov     edx, 0BAh
0x140002d49  call    HvsocketTraceReferenceCount
0x140002d4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002d52  lock xadd [rbx+130h], rax
0x140002d5b  sub     rax, 1
0x140002d5f  jg      short loc_140002DA5
0x140002d61  test    rax, rax
0x140002d64  jz      short loc_140002D6F
0x140002d66  mov     ecx, 0Eh
0x140002d6b  int     29h; Win8: RtlFailFast(ecx)
0x140002d6d  jmp     short loc_140002DA5
0x140002d6f  mov     eax, cs:dword_140013058
0x140002d75  cmp     eax, 4
0x140002d78  jbe     short loc_140002D8F
0x140002d7a  mov     r8d, 9
0x140002d80  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140002d87  mov     rdx, rbx
0x140002d8a  call    HvsocketTraceEndpointEvent
0x140002d8f  xor     r9d, r9d
0x140002d92  lea     rdx, [rbx+0C8h]
0x140002d99  mov     rcx, rbx
0x140002d9c  lea     r8d, [r9+9]
0x140002da0  call    VmbusTlQueueEndpointAction
0x140002da5  mov     eax, cs:dword_140013058
0x140002dab  cmp     eax, 5
0x140002dae  jbe     short loc_140002DD4
0x140002db0  mov     r9, [rbx+8]
0x140002db4  lea     rax, aDereferenceObj; "Dereference object"
0x140002dbb  mov     r8, rbx
0x140002dbe  mov     [rsp+38h+var_18], rax
0x140002dc3  mov     edx, 0BBh
0x140002dc8  lea     rcx, aVmbustlendpoin; "VmbusTlEndpointClearPendingConnectReque"...
0x140002dcf  call    HvsocketTraceReferenceCount
0x140002dd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002dd8  lock xadd [rbx+8], rax
0x140002dde  sub     rax, 1
0x140002de2  jg      short loc_140002E39
0x140002de4  test    rax, rax
0x140002de7  jz      short loc_140002DF2
0x140002de9  mov     ecx, 0Eh
0x140002dee  int     29h; Win8: RtlFailFast(ecx)
0x140002df0  jmp     short loc_140002E39
0x140002df2  mov     rax, [rbx+50h]
0x140002df6  test    rax, rax
0x140002df9  jz      short loc_140002E03
0x140002dfb  mov     rcx, rbx
0x140002dfe  call    _guard_dispatch_icall
0x140002e03  mov     ecx, [rbx+58h]
0x140002e06  sub     ecx, 1
0x140002e09  jz      short loc_140002E25
0x140002e0b  cmp     ecx, 1
0x140002e0e  jnz     short loc_140002E39
0x140002e10  mov     rcx, [rbx+60h]; Lookaside
0x140002e14  mov     rdx, rbx; Entry
0x140002e17  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002e1e  nop     dword ptr [rax+rax+00h]
0x140002e23  jmp     short loc_140002E39
0x140002e25  mov     edx, 69706E56h; Tag
0x140002e2a  mov     rcx, rbx; P
0x140002e2d  call    cs:__imp_ExFreePoolWithTag
0x140002e34  nop     dword ptr [rax+rax+00h]
0x140002e39  add     rsp, 30h
0x140002e3d  pop     rbx
0x140002e3e  retn
```
