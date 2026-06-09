# PxCmOidRequestComplete

- ea: `0x140002200`
- end: `0x1400022cd`
- name: `PxCmOidRequestComplete`
- size: `205`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001d54`
- `0x140002200`
- `0x140007940`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002271`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002271`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002261`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002261`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002296`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002296`
- `NDIS!NdisSetEvent` at `0x1400022b5`
- `NDIS!NdisSetEvent` at `0x1400022b5`

## pseudocode

```c
void __fastcall PxCmOidRequestComplete(KSPIN_LOCK *P, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  int v7; // eax
  KIRQL v8; // al
  bool v9; // zf

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, P, a2);
  v7 = *(_DWORD *)(a4 + 240);
  if ( (v7 & 1) != 0 )
  {
    *(_DWORD *)(a4 + 240) = v7 & 0xFFFFFFFE;
    ExFreePoolWithTag((PVOID)a4, 0);
    v8 = KeAcquireSpinLockRaiseToDpc(P + 11);
    v9 = (*((_DWORD *)P + 5))-- == 1;
    *((_BYTE *)P + 96) = v8;
    if ( v9 )
      DoDerefCmAfWork(P);
    else
      KeReleaseSpinLock(P + 11, v8);
  }
  else
  {
    *(_DWORD *)(a4 + 272) = a5;
    NdisSetEvent((PNDIS_EVENT)(a4 + 248));
  }
}

```

## disassembly

```asm
0x140002200  mov     [rsp+arg_8], rbx
0x140002205  push    rdi
0x140002206  sub     rsp, 30h
0x14000220a  mov     rbx, r9
0x14000220d  mov     rax, rdx
0x140002210  mov     rdi, rcx
0x140002213  mov     rcx, cs:WPP_GLOBAL_Control
0x14000221a  lea     rdx, WPP_GLOBAL_Control
0x140002221  cmp     rcx, rdx
0x140002224  jz      short loc_140002249
0x140002226  cmp     byte ptr [rcx+29h], 4
0x14000222a  jb      short loc_140002249
0x14000222c  mov     rcx, [rcx+18h]
0x140002230  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x140002237  mov     edx, 1Ah
0x14000223c  mov     [rsp+38h+var_18], rax
0x140002241  mov     r9, rdi
0x140002244  call    WPP_SF_qq
0x140002249  mov     eax, [rbx+0F0h]
0x14000224f  test    al, 1
0x140002251  jz      short loc_1400022A4
0x140002253  and     eax, 0FFFFFFFEh
0x140002256  xor     edx, edx; Tag
0x140002258  mov     rcx, rbx; P
0x14000225b  mov     [rbx+0F0h], eax
0x140002261  call    cs:__imp_ExFreePoolWithTag
0x140002268  nop     dword ptr [rax+rax+00h]
0x14000226d  lea     rcx, [rdi+58h]; SpinLock
0x140002271  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002278  nop     dword ptr [rax+rax+00h]
0x14000227d  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x140002281  mov     [rdi+60h], al
0x140002284  jnz     short loc_140002290
0x140002286  mov     rcx, rdi; P
0x140002289  call    DoDerefCmAfWork
0x14000228e  jmp     short loc_1400022C1
0x140002290  mov     dl, al; NewIrql
0x140002292  lea     rcx, [rdi+58h]; SpinLock
0x140002296  call    cs:__imp_KeReleaseSpinLock
0x14000229d  nop     dword ptr [rax+rax+00h]
0x1400022a2  jmp     short loc_1400022C1
0x1400022a4  mov     eax, [rsp+38h+arg_20]
0x1400022a8  lea     rcx, [rbx+0F8h]; Event
0x1400022af  mov     [rbx+110h], eax
0x1400022b5  call    cs:__imp_NdisSetEvent
0x1400022bc  nop     dword ptr [rax+rax+00h]
0x1400022c1  mov     rbx, [rsp+38h+arg_8]
0x1400022c6  add     rsp, 30h
0x1400022ca  pop     rdi
0x1400022cb  retn
```
