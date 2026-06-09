# Dot11InitMem(void)

- ea: `0x140055d18`
- end: `0x140055e64`
- name: `?Dot11InitMem@@YAHXZ`
- size: `332`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400bb4d4`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055d6c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055db1`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055df6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055e3b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055d6c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055db1`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055df6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140055e3b`
- `NDIS!NdisGetVersion` at `0x140055d29`
- `NDIS!NdisGetVersion` at `0x140055d78`
- `NDIS!NdisGetVersion` at `0x140055dbd`
- `NDIS!NdisGetVersion` at `0x140055e02`
- `NDIS!NdisGetVersion` at `0x140055d29`
- `NDIS!NdisGetVersion` at `0x140055d78`
- `NDIS!NdisGetVersion` at `0x140055dbd`
- `NDIS!NdisGetVersion` at `0x140055e02`

## pseudocode

```c
__int64 Dot11InitMem(void)
{
  UINT Version; // eax
  UINT v1; // eax
  UINT v2; // eax
  UINT v3; // eax
  __int64 result; // rax

  Version = NdisGetVersion();
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue,
    0,
    0,
    Version >= 0x6001E ? 0x200 : 0,
    0x40u,
    0x746D6777u,
    0);
  v1 = NdisGetVersion();
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead,
    0,
    0,
    v1 >= 0x6001E ? 0x200 : 0,
    0x100u,
    0x756D6777u,
    0);
  v2 = NdisGetVersion();
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, v2 >= 0x6001E ? 0x200 : 0, 0x400u, 0x766D6777u, 0);
  v3 = NdisGetVersion();
  ExInitializeNPagedLookasideList(&stru_1400B0180, 0, 0, v3 >= 0x6001E ? 0x200 : 0, 0x800u, 0x776D6777u, 0);
  result = 0;
  dword_1400B0200 = 1;
  return result;
}

```

## disassembly

```asm
0x140055d18  mov     [rsp+arg_0], rbx
0x140055d1d  mov     [rsp+arg_8], rsi
0x140055d22  push    rdi
0x140055d23  sub     rsp, 40h
0x140055d27  xor     ebx, ebx
0x140055d29  call    cs:__imp_NdisGetVersion
0x140055d30  nop     dword ptr [rax+rax+00h]
0x140055d35  mov     [rsp+48h+Depth], bx; Depth
0x140055d3a  lea     rcx, WPP_MAIN_CB.DeviceQueue; Lookaside
0x140055d41  mov     esi, 6001Eh
0x140055d46  mov     [rsp+48h+Tag], 746D6777h; Tag
0x140055d4e  cmp     eax, esi
0x140055d50  mov     [rsp+48h+Size], 40h ; '@'; Size
0x140055d59  mov     edi, 200h
0x140055d5e  sbb     r9d, r9d
0x140055d61  xor     r8d, r8d; Free
0x140055d64  not     r9d
0x140055d67  xor     edx, edx; Allocate
0x140055d69  and     r9d, edi; Flags
0x140055d6c  call    cs:__imp_ExInitializeNPagedLookasideList
0x140055d73  nop     dword ptr [rax+rax+00h]
0x140055d78  call    cs:__imp_NdisGetVersion
0x140055d7f  nop     dword ptr [rax+rax+00h]
0x140055d84  mov     [rsp+48h+Depth], bx; Depth
0x140055d89  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x140055d90  cmp     eax, esi
0x140055d92  mov     [rsp+48h+Tag], 756D6777h; Tag
0x140055d9a  mov     [rsp+48h+Size], 100h; Size
0x140055da3  sbb     r9d, r9d
0x140055da6  xor     r8d, r8d; Free
0x140055da9  not     r9d
0x140055dac  xor     edx, edx; Allocate
0x140055dae  and     r9d, edi; Flags
0x140055db1  call    cs:__imp_ExInitializeNPagedLookasideList
0x140055db8  nop     dword ptr [rax+rax+00h]
0x140055dbd  call    cs:__imp_NdisGetVersion
0x140055dc4  nop     dword ptr [rax+rax+00h]
0x140055dc9  mov     [rsp+48h+Depth], bx; Depth
0x140055dce  lea     rcx, Lookaside; Lookaside
0x140055dd5  cmp     eax, esi
0x140055dd7  mov     [rsp+48h+Tag], 766D6777h; Tag
0x140055ddf  mov     [rsp+48h+Size], 400h; Size
0x140055de8  sbb     r9d, r9d
0x140055deb  xor     r8d, r8d; Free
0x140055dee  not     r9d
0x140055df1  xor     edx, edx; Allocate
0x140055df3  and     r9d, edi; Flags
0x140055df6  call    cs:__imp_ExInitializeNPagedLookasideList
0x140055dfd  nop     dword ptr [rax+rax+00h]
0x140055e02  call    cs:__imp_NdisGetVersion
0x140055e09  nop     dword ptr [rax+rax+00h]
0x140055e0e  mov     [rsp+48h+Depth], bx; Depth
0x140055e13  lea     rcx, stru_1400B0180; Lookaside
0x140055e1a  cmp     eax, esi
0x140055e1c  mov     [rsp+48h+Tag], 776D6777h; Tag
0x140055e24  mov     [rsp+48h+Size], 800h; Size
0x140055e2d  sbb     r9d, r9d
0x140055e30  xor     r8d, r8d; Free
0x140055e33  not     r9d
0x140055e36  xor     edx, edx; Allocate
0x140055e38  and     r9d, edi; Flags
0x140055e3b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140055e42  nop     dword ptr [rax+rax+00h]
0x140055e47  mov     rbx, [rsp+48h+arg_0]
0x140055e4c  xor     eax, eax
0x140055e4e  mov     rsi, [rsp+48h+arg_8]
0x140055e53  mov     cs:dword_1400B0200, 1
0x140055e5d  add     rsp, 40h
0x140055e61  pop     rdi
0x140055e62  retn
```
