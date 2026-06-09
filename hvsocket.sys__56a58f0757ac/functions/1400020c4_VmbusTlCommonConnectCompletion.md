# VmbusTlCommonConnectCompletion

- ea: `0x1400020c4`
- end: `0x140002275`
- name: `VmbusTlCommonConnectCompletion`
- size: `433`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400023b0`

## callees

- `0x1400020c4`
- `0x140003bc8`
- `0x140003ee8`
- `0x140004354`
- `0x1400058d0`
- `0x140009834`
- `0x140009b84`
- `0x14000a048`
- `0x14000b86c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400020d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400020d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002208`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002241`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002208`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002241`

## string_xrefs

- `0x14000216e`: `VmbusTlCommonConnectCompletion`

## pseudocode

```c
void __fastcall VmbusTlCommonConnectCompletion(__int64 a1, int a2)
{
  KSPIN_LOCK *v2; // rsi
  __int64 v5; // rdx
  KIRQL v6; // bp
  __int64 v7; // r8
  __int64 v8; // r9
  bool v9; // zf
  signed __int64 v10; // rax
  bool v11; // cc
  signed __int64 v12; // rax
  __int64 v13; // rcx

  v2 = (KSPIN_LOCK *)(a1 + 72);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  if ( (*(_DWORD *)(a1 + 516) & 0x40) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  *(_DWORD *)(a1 + 516) |= 0x40u;
  *(_DWORD *)(a1 + 952) = a2;
  if ( a2 >= 0 )
  {
    if ( *(_DWORD *)(a1 + 920) != 1 )
    {
      if ( *(_BYTE *)(a1 + 533) )
      {
        VmbusTlIndicateDisconnectEventToClient(a1);
        v9 = (*(_DWORD *)(a1 + 528) & 0x800) == 0;
        *(_BYTE *)(a1 + 533) = 0;
        if ( !v9 )
        {
          if ( (unsigned int)dword_140013058 > 5 )
            HvsocketTraceReferenceCount(
              (const int *)"VmbusTlCommonConnectCompletion",
              601,
              a1,
              *(_QWORD *)(a1 + 304),
              (const int *)"Connection reference. (deref)");
          v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
          v11 = v10 <= 1;
          v12 = v10 - 1;
          if ( v11 )
          {
            if ( v12 )
              __fastfail(0xEu);
            if ( (unsigned int)dword_140013058 > 4 )
              HvsocketTraceEndpointEvent(
                (const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.",
                a1,
                9);
            VmbusTlQueueEndpointAction(a1, a1 + 200, 9);
          }
        }
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceEndpointMessage((const int *)"Endpoint connected, but aborted.", a1, v7, v8);
        goto LABEL_19;
      }
      *(_DWORD *)(a1 + 920) = 1;
    }
    LOBYTE(v5) = 1;
    VmbusTlpActivateDeliveryQueue(a1, v5);
LABEL_19:
    KeReleaseSpinLock(v2, v6);
    return;
  }
  HvSocketCompleteDisconnectRequest(a1, 0xC0000184, a1 + 544);
  HvSocketCompleteDisconnectRequest(a1, 0, a1 + 608);
  KeReleaseSpinLock(v2, v6);
  v13 = *(_QWORD *)(a1 + 112);
  if ( (*(_DWORD *)(a1 + 516) & 2) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 1248));
  else
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 1256));
}

```

## disassembly

```asm
0x1400020c4  push    rbx
0x1400020c6  push    rbp
0x1400020c7  push    rsi
0x1400020c8  push    rdi
0x1400020c9  sub     rsp, 38h
0x1400020cd  lea     rsi, [rcx+48h]
0x1400020d1  mov     rbx, rcx
0x1400020d4  mov     rcx, rsi; SpinLock
0x1400020d7  mov     edi, edx
0x1400020d9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400020e0  nop     dword ptr [rax+rax+00h]
0x1400020e5  mov     r8d, [rbx+204h]
0x1400020ec  mov     bpl, al
0x1400020ef  test    r8b, 40h
0x1400020f3  jz      short loc_1400020FA
0x1400020f5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400020fa  or      dword ptr [rbx+204h], 40h
0x140002101  mov     [rbx+3B8h], edi
0x140002107  test    edi, edi
0x140002109  js      loc_140002216
0x14000210f  cmp     dword ptr [rbx+398h], 1
0x140002116  jz      loc_1400021F8
0x14000211c  cmp     byte ptr [rbx+215h], 0
0x140002123  jz      loc_1400021EE
0x140002129  mov     rcx, rbx
0x14000212c  call    VmbusTlIndicateDisconnectEventToClient
0x140002131  test    dword ptr [rbx+210h], 800h
0x14000213b  mov     byte ptr [rbx+215h], 0
0x140002142  jz      loc_1400021D2
0x140002148  mov     eax, cs:dword_140013058
0x14000214e  cmp     eax, 5
0x140002151  jbe     short loc_14000217A
0x140002153  mov     r9, [rbx+130h]
0x14000215a  lea     rax, aConnectionRefe; "Connection reference. (deref)"
0x140002161  mov     r8, rbx
0x140002164  mov     [rsp+58h+var_38], rax
0x140002169  mov     edx, 259h
0x14000216e  lea     rcx, aVmbustlcommonc; "VmbusTlCommonConnectCompletion"
0x140002175  call    HvsocketTraceReferenceCount
0x14000217a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000217e  lock xadd [rbx+130h], rax
0x140002187  sub     rax, 1
0x14000218b  jg      short loc_1400021D2
0x14000218d  test    rax, rax
0x140002190  jz      short loc_14000219B
0x140002192  mov     ecx, 0Eh
0x140002197  int     29h; Win8: RtlFailFast(ecx)
0x140002199  jmp     short loc_1400021D2
0x14000219b  mov     eax, cs:dword_140013058
0x1400021a1  mov     edi, 9
0x1400021a6  cmp     eax, 4
0x1400021a9  jbe     short loc_1400021BD
0x1400021ab  mov     r8d, edi
0x1400021ae  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x1400021b5  mov     rdx, rbx
0x1400021b8  call    HvsocketTraceEndpointEvent
0x1400021bd  lea     rdx, [rbx+0C8h]
0x1400021c4  xor     r9d, r9d
0x1400021c7  mov     r8d, edi
0x1400021ca  mov     rcx, rbx
0x1400021cd  call    VmbusTlQueueEndpointAction
0x1400021d2  mov     eax, cs:dword_140013058
0x1400021d8  cmp     eax, 4
0x1400021db  jbe     short loc_140002202
0x1400021dd  mov     rdx, rbx
0x1400021e0  lea     rcx, aEndpointConnec; "Endpoint connected, but aborted."
0x1400021e7  call    HvsocketTraceEndpointMessage
0x1400021ec  jmp     short loc_140002202
0x1400021ee  mov     dword ptr [rbx+398h], 1
0x1400021f8  mov     dl, 1
0x1400021fa  mov     rcx, rbx
0x1400021fd  call    VmbusTlpActivateDeliveryQueue
0x140002202  mov     dl, bpl; NewIrql
0x140002205  mov     rcx, rsi; SpinLock
0x140002208  call    cs:__imp_KeReleaseSpinLock
0x14000220f  nop     dword ptr [rax+rax+00h]
0x140002214  jmp     short loc_14000226B
0x140002216  lea     r8, [rbx+220h]
0x14000221d  mov     edx, 0C0000184h
0x140002222  mov     rcx, rbx
0x140002225  call    HvSocketCompleteDisconnectRequest
0x14000222a  lea     r8, [rbx+260h]
0x140002231  xor     edx, edx
0x140002233  mov     rcx, rbx
0x140002236  call    HvSocketCompleteDisconnectRequest
0x14000223b  mov     dl, bpl; NewIrql
0x14000223e  mov     rcx, rsi; SpinLock
0x140002241  call    cs:__imp_KeReleaseSpinLock
0x140002248  nop     dword ptr [rax+rax+00h]
0x14000224d  mov     eax, [rbx+204h]
0x140002253  mov     rcx, [rbx+70h]
0x140002257  test    al, 2
0x140002259  jz      short loc_140002264
0x14000225b  lock inc dword ptr [rcx+4E0h]
0x140002262  jmp     short loc_14000226B
0x140002264  lock inc dword ptr [rcx+4E8h]
0x14000226b  add     rsp, 38h
0x14000226f  pop     rdi
0x140002270  pop     rsi
0x140002271  pop     rbp
0x140002272  pop     rbx
0x140002273  retn
```
