# TdiClientAcceptWithPolicy

- ea: `0x140006f68`
- end: `0x1400070bf`
- name: `TdiClientAcceptWithPolicy`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140005f2c`

## callees

- `0x140006bc0`
- `0x140006f68`
- `0x14000a380`
- `0x140018d08`
- `0x14001a4f8`
- `0x14001e74c`
- `0x14001f2ac`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140006fd5`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140006fd5`
- `ntoskrnl!ExAllocatePool2` at `0x140006f97`
- `ntoskrnl!ExAllocatePool2` at `0x140006f97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000708a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000708a`

## string_xrefs

- `0x140006fc7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140006ff7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140007031`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiClientAcceptWithPolicy(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  _QWORD *Pool2; // rbx
  NTSTATUS v6; // edi
  __int64 result; // rax

  v2 = *(_QWORD *)(a2 + 80);
  if ( !(unsigned __int8)BthServicePolicyEnabled() )
    return TdiClientAccept(a1, a2);
  Pool2 = (_QWORD *)ExAllocatePool2(64, 64, 1835230802);
  if ( !Pool2 )
  {
    v6 = -1073741670;
    return ChannelCompleteAccept(a1, 0, 0, (unsigned int)v6);
  }
  v6 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(v2 + 40),
         TdiPortToServiceClassIdCallback,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c",
         0x4D8u,
         0x20u);
  if ( v6 < 0 )
  {
    ExFreePoolWithTag(Pool2, 0x6D636652u);
    return ChannelCompleteAccept(a1, 0, 0, (unsigned int)v6);
  }
  Pool2[5] = a1;
  Pool2[6] = a2;
  *Pool2 = v2;
  *((_WORD *)Pool2 + 18) = 257;
  Pool2[1] = 0;
  *((_DWORD *)Pool2 + 8) = *(_DWORD *)(a2 + 112);
  RefObj_AddRefEx(a1 + 24, 1145652818, 1257, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  RefObj_AddRefEx(a2 + 24, 1145652818, 1258, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  result = BthPortToServiceClassIdList(*(PDEVICE_OBJECT *)(v2 + 88), (__int64)Pool2);
  if ( (int)result < 0 )
    return TdiPortToServiceClassIdCallback((unsigned int)result, Pool2, 0, 0);
  return result;
}

```

## disassembly

```asm
0x140006f68  push    rbx
0x140006f6a  push    rbp
0x140006f6b  push    rsi
0x140006f6c  push    rdi
0x140006f6d  push    r14
0x140006f6f  sub     rsp, 50h
0x140006f73  mov     r14, [rdx+50h]
0x140006f77  mov     rsi, rdx
0x140006f7a  mov     rbp, rcx
0x140006f7d  call    BthServicePolicyEnabled
0x140006f82  test    al, al
0x140006f84  jz      loc_1400070A8
0x140006f8a  mov     ecx, 40h ; '@'
0x140006f8f  mov     r8d, 6D636652h
0x140006f95  mov     edx, ecx
0x140006f97  call    cs:__imp_ExAllocatePool2
0x140006f9e  nop     dword ptr [rax+rax+00h]
0x140006fa3  mov     rbx, rax
0x140006fa6  test    rax, rax
0x140006fa9  jnz     short loc_140006FB5
0x140006fab  mov     edi, 0C000009Ah
0x140006fb0  jmp     loc_140007096
0x140006fb5  lea     rcx, [r14+28h]; RemoveLock
0x140006fb9  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140006fc1  mov     r9d, 4D8h; Line
0x140006fc7  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006fce  lea     rdx, TdiPortToServiceClassIdCallback; Tag
0x140006fd5  call    cs:__imp_IoAcquireRemoveLockEx
0x140006fdc  nop     dword ptr [rax+rax+00h]
0x140006fe1  mov     edi, eax
0x140006fe3  test    eax, eax
0x140006fe5  js      loc_140007082
0x140006feb  mov     [rbx+28h], rbp
0x140006fef  lea     rcx, [rbp+18h]
0x140006ff3  mov     [rbx+30h], rsi
0x140006ff7  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006ffe  mov     [rbx], r14
0x140007001  mov     edi, 44494652h
0x140007006  mov     word ptr [rbx+24h], 101h
0x14000700c  mov     edx, edi
0x14000700e  mov     qword ptr [rbx+8], 0
0x140007016  mov     r8d, 4E9h
0x14000701c  mov     eax, [rsi+70h]
0x14000701f  mov     [rbx+20h], eax
0x140007022  call    RefObj_AddRefEx
0x140007027  lea     rcx, [rsi+18h]
0x14000702b  mov     r8d, 4EAh
0x140007031  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140007038  mov     edx, edi
0x14000703a  call    RefObj_AddRefEx
0x14000703f  movups  xmm0, xmmword ptr [rbx+8]
0x140007043  mov     r9b, [rbx+25h]
0x140007047  lea     r8, [rsp+78h+var_48]
0x14000704c  movups  xmm1, xmmword ptr [rbx+14h]
0x140007050  mov     rdx, [r14+50h]
0x140007054  mov     rcx, [r14+58h]; DeviceObject
0x140007058  movaps  [rsp+78h+var_48], xmm0
0x14000705d  movups  [rsp+78h+var_48+0Ch], xmm1
0x140007062  mov     qword ptr [rsp+78h+RemlockSize], rbx; __int64
0x140007067  call    BthPortToServiceClassIdList
0x14000706c  test    eax, eax
0x14000706e  jns     short loc_1400070B3
0x140007070  xor     r9d, r9d
0x140007073  xor     r8d, r8d
0x140007076  mov     rdx, rbx
0x140007079  mov     ecx, eax
0x14000707b  call    TdiPortToServiceClassIdCallback
0x140007080  jmp     short loc_1400070B3
0x140007082  mov     edx, 6D636652h; Tag
0x140007087  mov     rcx, rbx; P
0x14000708a  call    cs:__imp_ExFreePoolWithTag
0x140007091  nop     dword ptr [rax+rax+00h]
0x140007096  mov     r9d, edi
0x140007099  xor     r8d, r8d
0x14000709c  xor     edx, edx
0x14000709e  mov     rcx, rbp
0x1400070a1  call    ChannelCompleteAccept
0x1400070a6  jmp     short loc_1400070B3
0x1400070a8  mov     rdx, rsi
0x1400070ab  mov     rcx, rbp
0x1400070ae  call    TdiClientAccept
0x1400070b3  add     rsp, 50h
0x1400070b7  pop     r14
0x1400070b9  pop     rdi
0x1400070ba  pop     rsi
0x1400070bb  pop     rbp
0x1400070bc  pop     rbx
0x1400070bd  retn
```
