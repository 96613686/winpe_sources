# CdpClientRead

- ea: `0x14000c5c0`
- end: `0x14000c689`
- name: `CdpClientRead`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a5e0`
- `0x14000ab30`
- `0x14000c5c0`
- `0x14000d440`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000c67b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c67b`
- `ntoskrnl!IofCompleteRequest` at `0x14000c5fd`
- `ntoskrnl!IofCompleteRequest` at `0x14000c5fd`

## pseudocode

```c
__int64 __fastcall CdpClientRead(__int64 a1, __int64 a2)
{
  int ClientTarget; // edi
  int v4; // r8d
  __int128 v6; // [rsp+40h] [rbp-28h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-18h]

  v6 = 0;
  *(_OWORD *)Object = 0;
  ClientTarget = CdpGetClientTarget(a1, a2, &v6);
  if ( ClientTarget >= 0 )
  {
    LOBYTE(v4) = 6;
    CdInitializeIo(a2, LODWORD(Object[0]) + 64, v4, v6, *((__int64 *)&v6 + 1), 0, *(_QWORD *)(a2 + 8));
    ClientTarget = CdAddIoToPipe(a2);
    if ( Object[1] )
      ObfDereferenceObject(Object[1]);
    if ( ClientTarget >= 0 )
      return 259;
  }
  *(_DWORD *)(a2 + 48) = ClientTarget;
  *(_QWORD *)(a2 + 56) = 0;
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)ClientTarget;
}

```

## disassembly

```asm
0x14000c5c0  mov     [rsp+arg_0], rbx
0x14000c5c5  mov     [rsp+arg_8], rsi
0x14000c5ca  push    rdi
0x14000c5cb  sub     rsp, 60h
0x14000c5cf  xorps   xmm0, xmm0
0x14000c5d2  lea     r8, [rsp+68h+var_28]
0x14000c5d7  movups  [rsp+68h+var_28], xmm0
0x14000c5dc  mov     rbx, rdx
0x14000c5df  movups  xmmword ptr [rsp+68h+Object], xmm0
0x14000c5e4  call    CdpGetClientTarget
0x14000c5e9  xor     esi, esi
0x14000c5eb  mov     edi, eax
0x14000c5ed  test    eax, eax
0x14000c5ef  jns     short loc_14000C61C
0x14000c5f1  xor     edx, edx; PriorityBoost
0x14000c5f3  mov     [rbx+30h], edi
0x14000c5f6  mov     rcx, rbx; Irp
0x14000c5f9  mov     [rbx+38h], rsi
0x14000c5fd  call    cs:__imp_IofCompleteRequest
0x14000c604  nop     dword ptr [rax+rax+00h]
0x14000c609  mov     eax, edi
0x14000c60b  mov     rbx, [rsp+68h+arg_0]
0x14000c610  mov     rsi, [rsp+68h+arg_8]
0x14000c615  add     rsp, 60h
0x14000c619  pop     rdi
0x14000c61a  retn
0x14000c61c  mov     rax, [rbx+8]
0x14000c620  mov     r8b, 6
0x14000c623  mov     rdx, [rsp+68h+Object]
0x14000c628  mov     rcx, rbx
0x14000c62b  mov     r9, qword ptr [rsp+68h+var_28]
0x14000c630  add     rdx, 40h ; '@'
0x14000c634  mov     [rsp+68h+var_38], rax
0x14000c639  mov     rax, qword ptr [rsp+68h+var_28+8]
0x14000c63e  mov     [rsp+68h+var_40], rsi
0x14000c643  mov     [rsp+68h+var_48], rax
0x14000c648  call    CdInitializeIo
0x14000c64d  mov     rcx, rbx
0x14000c650  call    CdAddIoToPipe
0x14000c655  mov     rcx, [rsp+68h+Object+8]; Object
0x14000c65a  mov     edi, eax
0x14000c65c  test    rcx, rcx
0x14000c65f  jnz     short loc_14000C67B
0x14000c661  test    edi, edi
0x14000c663  js      short loc_14000C5F1
0x14000c665  mov     rbx, [rsp+68h+arg_0]
0x14000c66a  mov     eax, 103h
0x14000c66f  mov     rsi, [rsp+68h+arg_8]
0x14000c674  add     rsp, 60h
0x14000c678  pop     rdi
0x14000c679  retn
0x14000c67b  call    cs:__imp_ObfDereferenceObject
0x14000c682  nop     dword ptr [rax+rax+00h]
0x14000c687  jmp     short loc_14000C661
```
