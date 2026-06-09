# lldpAllocateBinding

- ea: `0x140012000`
- end: `0x140012180`
- name: `lldpAllocateBinding`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011e30`

## callees

- `0x140004110`
- `0x1400046a4`
- `0x140004800`
- `0x140010560`
- `0x140012000`
- `0x140012640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001201d`
- `ntoskrnl!ExAllocatePool2` at `0x14001201d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012149`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012149`
- `ntoskrnl!KeInitializeEvent` at `0x140012085`
- `ntoskrnl!KeInitializeEvent` at `0x140012085`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x14001211c`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x14001211c`

## pseudocode

```c
__int64 __fastcall lldpAllocateBinding(__int64 a1)
{
  __int64 result; // rax
  _DWORD *v3; // rbx
  int v4; // ebp
  int v5; // ecx
  __int64 v6; // rax
  __int64 v7; // rdi
  void *v8; // rcx

  result = ExAllocatePool2(64, 128, 1346653260);
  v3 = (_DWORD *)result;
  if ( result )
  {
    *(_OWORD *)result = 0;
    v4 = 1;
    *(_OWORD *)(result + 16) = 0;
    *(_OWORD *)(result + 32) = 0;
    *(_OWORD *)(result + 48) = 0;
    *(_OWORD *)(result + 64) = 0;
    *(_OWORD *)(result + 80) = 0;
    *(_OWORD *)(result + 96) = 0;
    *(_OWORD *)(result + 112) = 0;
    *(_DWORD *)result = 1648643148;
    *(_DWORD *)(result + 56) = 1;
    KeInitializeEvent((PRKEVENT)(result + 80), SynchronizationEvent, 0);
    v5 = *(_DWORD *)(a1 + 208);
    v3[9] = *(_DWORD *)(a1 + 212);
    v3[10] = v5;
    v3[11] = *(_DWORD *)(a1 + 36) + 14;
    v3[12] = *(_DWORD *)(a1 + 36);
    while ( 1 )
    {
      v6 = lldpAllocPort((_DWORD)v3, *(_QWORD *)(a1 + 16), *(_DWORD *)(a1 + 176), *(_QWORD *)(a1 + 168), v4);
      v7 = v6;
      if ( !v6 )
        break;
      *(_DWORD *)(v6 + 4) = 0;
      lldpSetPortMacAddress(v6, a1 + 106);
      ++v4;
      *(_QWORD *)(v7 + 40) = *((_QWORD *)v3 + 15);
      *((_QWORD *)v3 + 15) = v7;
      if ( v4 > 3 )
      {
        lldpAddBindingToDriver(v3);
        return (__int64)v3;
      }
    }
    lldpDetachAllPortsFromBinding(v3);
    v8 = (void *)*((_QWORD *)v3 + 2);
    if ( v8 )
    {
      NdisCompleteUnbindAdapterEx(v8);
      *((_QWORD *)v3 + 2) = 0;
    }
    if ( *((_BYTE *)v3 + 32) )
    {
      lldpRemoveBindingFromDriver(v3);
      *((_BYTE *)v3 + 32) = 0;
    }
    *(_BYTE *)v3 = 0;
    ExFreePoolWithTag(v3, 0x50444C4Cu);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140012000  mov     [rsp+arg_18], rbx
0x140012005  push    rsi
0x140012006  sub     rsp, 30h
0x14001200a  mov     rsi, rcx
0x14001200d  mov     edx, 80h
0x140012012  mov     ecx, 40h ; '@'
0x140012017  mov     r8d, 50444C4Ch
0x14001201d  call    cs:__imp_ExAllocatePool2
0x140012024  nop     dword ptr [rax+rax+00h]
0x140012029  mov     rbx, rax
0x14001202c  test    rax, rax
0x14001202f  jnz     short loc_14001203D
0x140012031  mov     rbx, [rsp+38h+arg_18]
0x140012036  add     rsp, 30h
0x14001203a  pop     rsi
0x14001203b  retn
0x14001203d  xorps   xmm0, xmm0
0x140012040  mov     [rsp+38h+arg_0], rbp
0x140012045  movups  xmmword ptr [rax], xmm0
0x140012048  mov     ebp, 1
0x14001204d  mov     [rsp+38h+arg_8], rdi
0x140012052  movups  xmmword ptr [rax+10h], xmm0
0x140012056  lea     rcx, [rax+50h]; Event
0x14001205a  xor     r8d, r8d; State
0x14001205d  movups  xmmword ptr [rax+20h], xmm0
0x140012061  mov     edx, ebp; Type
0x140012063  mov     [rsp+38h+arg_10], r14
0x140012068  movups  xmmword ptr [rax+30h], xmm0
0x14001206c  movups  xmmword ptr [rax+40h], xmm0
0x140012070  movups  xmmword ptr [rax+50h], xmm0
0x140012074  movups  xmmword ptr [rax+60h], xmm0
0x140012078  movups  xmmword ptr [rax+70h], xmm0
0x14001207c  mov     dword ptr [rax], 62444C4Ch
0x140012082  mov     [rax+38h], ebp
0x140012085  call    cs:__imp_KeInitializeEvent
0x14001208c  nop     dword ptr [rax+rax+00h]
0x140012091  mov     eax, [rsi+0D4h]
0x140012097  mov     ecx, [rsi+0D0h]
0x14001209d  mov     [rbx+24h], eax
0x1400120a0  mov     [rbx+28h], ecx
0x1400120a3  mov     eax, [rsi+24h]
0x1400120a6  add     eax, 0Eh
0x1400120a9  mov     [rbx+2Ch], eax
0x1400120ac  xor     r14d, r14d
0x1400120af  mov     eax, [rsi+24h]
0x1400120b2  mov     [rbx+30h], eax
0x1400120b5  mov     r9, [rsi+0A8h]
0x1400120bc  mov     rcx, rbx
0x1400120bf  mov     r8d, [rsi+0B0h]
0x1400120c6  mov     rdx, [rsi+10h]
0x1400120ca  mov     [rsp+38h+var_18], ebp
0x1400120ce  call    lldpAllocPort
0x1400120d3  mov     rdi, rax
0x1400120d6  test    rax, rax
0x1400120d9  jz      short loc_14001210B
0x1400120db  lea     rdx, [rsi+6Ah]
0x1400120df  mov     [rax+4], r14d
0x1400120e3  mov     rcx, rax
0x1400120e6  call    lldpSetPortMacAddress
0x1400120eb  mov     rcx, [rbx+78h]
0x1400120ef  inc     ebp
0x1400120f1  mov     [rdi+28h], rcx
0x1400120f5  mov     [rbx+78h], rdi
0x1400120f9  cmp     ebp, 3
0x1400120fc  jle     short loc_1400120B5
0x1400120fe  mov     rcx, rbx
0x140012101  call    lldpAddBindingToDriver
0x140012106  mov     rax, rbx
0x140012109  jmp     short loc_140012157
0x14001210b  mov     rcx, rbx
0x14001210e  call    lldpDetachAllPortsFromBinding
0x140012113  mov     rcx, [rbx+10h]; UnbindContext
0x140012117  test    rcx, rcx
0x14001211a  jz      short loc_14001212C
0x14001211c  call    cs:__imp_NdisCompleteUnbindAdapterEx
0x140012123  nop     dword ptr [rax+rax+00h]
0x140012128  mov     [rbx+10h], r14
0x14001212c  cmp     [rbx+20h], r14b
0x140012130  jz      short loc_14001213E
0x140012132  mov     rcx, rbx
0x140012135  call    lldpRemoveBindingFromDriver
0x14001213a  mov     [rbx+20h], r14b
0x14001213e  mov     edx, 50444C4Ch; Tag
0x140012143  mov     [rbx], r14b
0x140012146  mov     rcx, rbx; P
0x140012149  call    cs:__imp_ExFreePoolWithTag
0x140012150  nop     dword ptr [rax+rax+00h]
0x140012155  xor     eax, eax
0x140012157  mov     rdi, [rsp+38h+arg_8]
0x14001215c  mov     rbp, [rsp+38h+arg_0]
0x140012161  mov     r14, [rsp+38h+arg_10]
0x140012166  mov     rbx, [rsp+38h+arg_18]
0x14001216b  add     rsp, 30h
0x14001216f  pop     rsi
0x140012170  retn
```
