# HvSocketListenerProcessPendingConnectionsList

- ea: `0x14001b578`
- end: `0x14001b714`
- name: `HvSocketListenerProcessPendingConnectionsList`
- size: `412`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140021550`

## callees

- `0x1400059b8`
- `0x1400099dc`
- `0x14000a048`
- `0x14000a2c8`
- `0x14000bfe0`
- `0x14001b578`
- `0x14001d728`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001b679`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b679`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b663`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b663`
- `ntoskrnl!PsGetProcessId` at `0x14001b6d6`
- `ntoskrnl!PsGetProcessId` at `0x14001b6d6`

## pseudocode

```c
char __fastcall HvSocketListenerProcessPendingConnectionsList(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // rsi
  char result; // al
  __int64 v6; // r14
  __int64 v7; // r15
  _OWORD *v8; // r12
  PVOID v9; // rbx
  int v10; // ebp
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  void (__fastcall *v14)(PVOID); // rax
  struct _KPROCESS *v15; // rcx
  unsigned int ProcessId; // eax
  PVOID Entry; // [rsp+68h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 336) == 0;
  v4 = a1;
  Entry = 0;
  if ( v2 )
  {
    result = dword_140013058;
    if ( (unsigned int)dword_140013058 > 4 )
      return HvsocketTraceEndpointGuidMessage("ListenEventDispatch is NULL.", a2, a2 + 156);
  }
  else
  {
    v6 = a2 + 392;
    v7 = a2 + 156;
    v8 = (_OWORD *)(a2 + 376);
    while ( 1 )
    {
      result = HvSocketGetPendingInboundConnection(a1, v8, v7, v6, (__int64)&Entry);
      if ( !result )
        break;
      v9 = Entry;
      v10 = HvSocketAcceptIncomingConnection(a2, (__int64)Entry);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketListenerProcessPendingConnectionsList",
          297,
          (_DWORD)v9,
          *((_QWORD *)v9 + 1),
          (__int64)"Dereference object");
      v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)v9 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v12 = v11 <= 1;
      v13 = v11 - 1;
      if ( v12 )
      {
        if ( v13 )
          __fastfail(0xEu);
        v14 = (void (__fastcall *)(PVOID))*((_QWORD *)v9 + 10);
        if ( v14 )
          v14(v9);
        if ( *((_DWORD *)v9 + 22) == 1 )
        {
          ExFreePoolWithTag(v9, 0x69706E56u);
        }
        else if ( *((_DWORD *)v9 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v9 + 12), v9);
        }
      }
      if ( v10 == -1073741801 )
      {
        result = dword_140013058;
        if ( (unsigned int)dword_140013058 > 2 )
        {
          v15 = *(struct _KPROCESS **)(a2 + 272);
          if ( v15 )
            ProcessId = (unsigned int)PsGetProcessId(v15);
          else
            ProcessId = 0;
          return HvsocketTraceULongError("HvSocketListenerProcessPendingConnectionsList", 303, 3221225495LL, ProcessId);
        }
        return result;
      }
      a1 = v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b578  mov     [rsp+arg_0], rbx
0x14001b57d  mov     [rsp+arg_10], rbp
0x14001b582  push    rsi
0x14001b583  push    rdi
0x14001b584  push    r12
0x14001b586  push    r14
0x14001b588  push    r15
0x14001b58a  sub     rsp, 30h
0x14001b58e  cmp     qword ptr [rdx+150h], 0
0x14001b596  mov     rdi, rdx
0x14001b599  mov     rsi, rcx
0x14001b59c  mov     [rsp+58h+Entry], 0
0x14001b5a5  jnz     short loc_14001B5CE
0x14001b5a7  mov     eax, cs:dword_140013058
0x14001b5ad  cmp     eax, 4
0x14001b5b0  jbe     loc_14001B6FC
0x14001b5b6  lea     r8, [rdx+9Ch]
0x14001b5bd  lea     rcx, aListeneventdis; "ListenEventDispatch is NULL."
0x14001b5c4  call    HvsocketTraceEndpointGuidMessage
0x14001b5c9  jmp     loc_14001B6FC
0x14001b5ce  lea     r14, [rdx+188h]
0x14001b5d5  lea     r15, [rdx+9Ch]
0x14001b5dc  lea     r12, [rdx+178h]
0x14001b5e3  jmp     loc_14001B699
0x14001b5e8  mov     rbx, [rsp+58h+Entry]
0x14001b5ed  mov     rcx, rdi
0x14001b5f0  mov     rdx, rbx
0x14001b5f3  call    HvSocketAcceptIncomingConnection
0x14001b5f8  mov     ecx, cs:dword_140013058
0x14001b5fe  mov     ebp, eax
0x14001b600  cmp     ecx, 5
0x14001b603  jbe     short loc_14001B629
0x14001b605  mov     r9, [rbx+8]
0x14001b609  lea     rax, aDereferenceObj; "Dereference object"
0x14001b610  mov     r8, rbx
0x14001b613  mov     [rsp+58h+var_38], rax
0x14001b618  mov     edx, 129h
0x14001b61d  lea     rcx, aHvsocketlisten; "HvSocketListenerProcessPendingConnectio"...
0x14001b624  call    HvsocketTraceReferenceCount
0x14001b629  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b62d  lock xadd [rbx+8], rax
0x14001b633  sub     rax, 1
0x14001b637  jg      short loc_14001B68E
0x14001b639  test    rax, rax
0x14001b63c  jnz     short loc_14001B687
0x14001b63e  mov     rax, [rbx+50h]
0x14001b642  test    rax, rax
0x14001b645  jz      short loc_14001B64F
0x14001b647  mov     rcx, rbx
0x14001b64a  call    _guard_dispatch_icall
0x14001b64f  mov     ecx, [rbx+58h]
0x14001b652  sub     ecx, 1
0x14001b655  jz      short loc_14001B671
0x14001b657  cmp     ecx, 1
0x14001b65a  jnz     short loc_14001B68E
0x14001b65c  mov     rcx, [rbx+60h]; Lookaside
0x14001b660  mov     rdx, rbx; Entry
0x14001b663  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b66a  nop     dword ptr [rax+rax+00h]
0x14001b66f  jmp     short loc_14001B68E
0x14001b671  mov     edx, 69706E56h; Tag
0x14001b676  mov     rcx, rbx; P
0x14001b679  call    cs:__imp_ExFreePoolWithTag
0x14001b680  nop     dword ptr [rax+rax+00h]
0x14001b685  jmp     short loc_14001B68E
0x14001b687  mov     ecx, 0Eh
0x14001b68c  int     29h; Win8: RtlFailFast(ecx)
0x14001b68e  cmp     ebp, 0C0000017h
0x14001b694  jz      short loc_14001B6BB
0x14001b696  mov     rcx, rsi
0x14001b699  lea     rax, [rsp+58h+Entry]
0x14001b69e  mov     r9, r14
0x14001b6a1  mov     r8, r15
0x14001b6a4  mov     [rsp+58h+var_38], rax
0x14001b6a9  mov     rdx, r12
0x14001b6ac  call    HvSocketGetPendingInboundConnection
0x14001b6b1  test    al, al
0x14001b6b3  jnz     loc_14001B5E8
0x14001b6b9  jmp     short loc_14001B6FC
0x14001b6bb  mov     eax, cs:dword_140013058
0x14001b6c1  cmp     eax, 2
0x14001b6c4  jbe     short loc_14001B6FC
0x14001b6c6  mov     rcx, [rdi+110h]; Process
0x14001b6cd  test    rcx, rcx
0x14001b6d0  jnz     short loc_14001B6D6
0x14001b6d2  xor     eax, eax
0x14001b6d4  jmp     short loc_14001B6E2
0x14001b6d6  call    cs:__imp_PsGetProcessId
0x14001b6dd  nop     dword ptr [rax+rax+00h]
0x14001b6e2  mov     r9d, eax
0x14001b6e5  lea     rcx, aHvsocketlisten; "HvSocketListenerProcessPendingConnectio"...
0x14001b6ec  mov     edx, 12Fh
0x14001b6f1  mov     r8d, 0C0000017h
0x14001b6f7  call    HvsocketTraceULongError
0x14001b6fc  mov     rbx, [rsp+58h+arg_0]
0x14001b701  mov     rbp, [rsp+58h+arg_10]
0x14001b706  add     rsp, 30h
0x14001b70a  pop     r15
0x14001b70c  pop     r14
0x14001b70e  pop     r12
0x14001b710  pop     rdi
0x14001b711  pop     rsi
0x14001b712  retn
```
