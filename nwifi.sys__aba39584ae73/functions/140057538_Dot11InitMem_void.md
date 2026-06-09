# Dot11InitMem(void)

- ea: `0x140057538`
- end: `0x140057684`
- name: `?Dot11InitMem@@YAHXZ`
- size: `332`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400be4d4`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005758c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400575d1`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140057616`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005765b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005758c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400575d1`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140057616`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005765b`
- `NDIS!NdisGetVersion` at `0x140057549`
- `NDIS!NdisGetVersion` at `0x140057598`
- `NDIS!NdisGetVersion` at `0x1400575dd`
- `NDIS!NdisGetVersion` at `0x140057622`
- `NDIS!NdisGetVersion` at `0x140057549`
- `NDIS!NdisGetVersion` at `0x140057598`
- `NDIS!NdisGetVersion` at `0x1400575dd`
- `NDIS!NdisGetVersion` at `0x140057622`

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
  ExInitializeNPagedLookasideList(&stru_1400B31C0, 0, 0, v3 >= 0x6001E ? 0x200 : 0, 0x800u, 0x776D6777u, 0);
  result = 0;
  dword_1400B3240 = 1;
  return result;
}

```

## disassembly

```asm
0x140057538  mov     [rsp+arg_0], rbx
0x14005753d  mov     [rsp+arg_8], rsi
0x140057542  push    rdi
0x140057543  sub     rsp, 40h
0x140057547  xor     ebx, ebx
0x140057549  call    cs:__imp_NdisGetVersion
0x140057550  nop     dword ptr [rax+rax+00h]
0x140057555  mov     [rsp+48h+Depth], bx; Depth
0x14005755a  lea     rcx, WPP_MAIN_CB.DeviceQueue; Lookaside
0x140057561  mov     esi, 6001Eh
0x140057566  mov     [rsp+48h+Tag], 746D6777h; Tag
0x14005756e  cmp     eax, esi
0x140057570  mov     [rsp+48h+Size], 40h ; '@'; Size
0x140057579  mov     edi, 200h
0x14005757e  sbb     r9d, r9d
0x140057581  xor     r8d, r8d; Free
0x140057584  not     r9d
0x140057587  xor     edx, edx; Allocate
0x140057589  and     r9d, edi; Flags
0x14005758c  call    cs:__imp_ExInitializeNPagedLookasideList
0x140057593  nop     dword ptr [rax+rax+00h]
0x140057598  call    cs:__imp_NdisGetVersion
0x14005759f  nop     dword ptr [rax+rax+00h]
0x1400575a4  mov     [rsp+48h+Depth], bx; Depth
0x1400575a9  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x1400575b0  cmp     eax, esi
0x1400575b2  mov     [rsp+48h+Tag], 756D6777h; Tag
0x1400575ba  mov     [rsp+48h+Size], 100h; Size
0x1400575c3  sbb     r9d, r9d
0x1400575c6  xor     r8d, r8d; Free
0x1400575c9  not     r9d
0x1400575cc  xor     edx, edx; Allocate
0x1400575ce  and     r9d, edi; Flags
0x1400575d1  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400575d8  nop     dword ptr [rax+rax+00h]
0x1400575dd  call    cs:__imp_NdisGetVersion
0x1400575e4  nop     dword ptr [rax+rax+00h]
0x1400575e9  mov     [rsp+48h+Depth], bx; Depth
0x1400575ee  lea     rcx, Lookaside; Lookaside
0x1400575f5  cmp     eax, esi
0x1400575f7  mov     [rsp+48h+Tag], 766D6777h; Tag
0x1400575ff  mov     [rsp+48h+Size], 400h; Size
0x140057608  sbb     r9d, r9d
0x14005760b  xor     r8d, r8d; Free
0x14005760e  not     r9d
0x140057611  xor     edx, edx; Allocate
0x140057613  and     r9d, edi; Flags
0x140057616  call    cs:__imp_ExInitializeNPagedLookasideList
0x14005761d  nop     dword ptr [rax+rax+00h]
0x140057622  call    cs:__imp_NdisGetVersion
0x140057629  nop     dword ptr [rax+rax+00h]
0x14005762e  mov     [rsp+48h+Depth], bx; Depth
0x140057633  lea     rcx, stru_1400B31C0; Lookaside
0x14005763a  cmp     eax, esi
0x14005763c  mov     [rsp+48h+Tag], 776D6777h; Tag
0x140057644  mov     [rsp+48h+Size], 800h; Size
0x14005764d  sbb     r9d, r9d
0x140057650  xor     r8d, r8d; Free
0x140057653  not     r9d
0x140057656  xor     edx, edx; Allocate
0x140057658  and     r9d, edi; Flags
0x14005765b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140057662  nop     dword ptr [rax+rax+00h]
0x140057667  mov     rbx, [rsp+48h+arg_0]
0x14005766c  xor     eax, eax
0x14005766e  mov     rsi, [rsp+48h+arg_8]
0x140057673  mov     cs:dword_1400B3240, 1
0x14005767d  add     rsp, 40h
0x140057681  pop     rdi
0x140057682  retn
```
