# DoDerefCmAfWork

- ea: `0x140007940`
- end: `0x1400079b7`
- name: `DoDerefCmAfWork`
- size: `119`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001680`
- `0x140001e40`
- `0x140001fb0`
- `0x140002100`
- `0x140002200`
- `0x140003940`
- `0x140010240`
- `0x140013770`

## callees

- `0x140001bc8`
- `0x140007940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400079a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007950`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007950`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x140007962`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x140007962`

## pseudocode

```c
void __fastcall DoDerefCmAfWork(PVOID P)
{
  KeReleaseSpinLock((PKSPIN_LOCK)P + 11, *((_BYTE *)P + 96));
  NdisCmCloseAddressFamilyComplete(0, *((NDIS_HANDLE *)P + 3));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids, P);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140007940  push    rbx
0x140007942  sub     rsp, 20h
0x140007946  mov     rbx, rcx
0x140007949  add     rcx, 58h ; 'X'; SpinLock
0x14000794d  mov     dl, [rbx+60h]; NewIrql
0x140007950  call    cs:__imp_KeReleaseSpinLock
0x140007957  nop     dword ptr [rax+rax+00h]
0x14000795c  mov     rdx, [rbx+18h]; NdisAfHandle
0x140007960  xor     ecx, ecx; Status
0x140007962  call    cs:__imp_NdisCmCloseAddressFamilyComplete
0x140007969  nop     dword ptr [rax+rax+00h]
0x14000796e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007975  lea     rax, WPP_GLOBAL_Control
0x14000797c  cmp     rcx, rax
0x14000797f  jz      short loc_14000799F
0x140007981  cmp     byte ptr [rcx+29h], 5
0x140007985  jb      short loc_14000799F
0x140007987  mov     rcx, [rcx+18h]
0x14000798b  lea     r8, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids
0x140007992  mov     edx, 0Dh
0x140007997  mov     r9, rbx
0x14000799a  call    WPP_SF_q
0x14000799f  xor     edx, edx; Tag
0x1400079a1  mov     rcx, rbx; P
0x1400079a4  call    cs:__imp_ExFreePoolWithTag
0x1400079ab  nop     dword ptr [rax+rax+00h]
0x1400079b0  add     rsp, 20h
0x1400079b4  pop     rbx
0x1400079b5  retn
```
