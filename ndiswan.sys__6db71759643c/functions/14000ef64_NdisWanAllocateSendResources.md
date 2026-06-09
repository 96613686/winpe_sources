# NdisWanAllocateSendResources

- ea: `0x14000ef64`
- end: `0x14000f16b`
- name: `NdisWanAllocateSendResources`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000f2d0`

## callees

- `0x14000a2c0`
- `0x14000ef64`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000efd9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000efd9`
- `ntoskrnl!InitializeSListHead` at `0x14000f0ae`
- `ntoskrnl!InitializeSListHead` at `0x14000f0ae`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f0cb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f0cb`
- `NDIS!NdisAllocateMemory` at `0x14000f048`
- `NDIS!NdisAllocateMemory` at `0x14000f048`
- `NDIS!NdisGetVersion` at `0x14000efa5`
- `NDIS!NdisGetVersion` at `0x14000efa5`

## pseudocode

```c
__int64 __fastcall NdisWanAllocateSendResources(__int64 a1)
{
  UINT v2; // r8d
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned __int64 v5; // rsi
  __int64 v6; // r14
  unsigned __int64 v7; // rdi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // edi
  struct _SLIST_ENTRY *v12; // rax
  __int64 result; // rax
  PVOID VirtualAddress; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a1 + 188);
  v3 = (*(_DWORD *)(a1 + 176) + *(_DWORD *)(a1 + 180) + *(_DWORD *)(a1 + 168) + 119) & 0xFFFFFFF8;
  *(_DWORD *)(a1 + 256) = v3;
  if ( !v2 )
  {
    NdisGetVersion();
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 320), 0, 0, 0x200u, v3, 0x526E6157u, 0);
LABEL_13:
    result = 0;
    *(_DWORD *)(a1 + 20) |= 8u;
    return result;
  }
  VirtualAddress = 0;
  v4 = *(_DWORD *)(a1 + 172) + glMaxMTU / (unsigned int)glMinFragSize;
  *(_DWORD *)(a1 + 260) = v4;
  v5 = *(unsigned int *)(a1 + 184) * (unsigned __int64)(v4 + 1);
  if ( v5 > 0xFFFFFFFF )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225626LL;
    }
    v9 = 43;
LABEL_22:
    v10 = 0xFFFFFFFFLL;
    goto LABEL_23;
  }
  v6 = v3;
  v7 = v3 * (unsigned __int64)(unsigned int)v5;
  if ( v7 > 0xFFFFFFFF )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return 3221225626LL;
    }
    v9 = 44;
    goto LABEL_22;
  }
  NdisAllocateMemory(&VirtualAddress, v7, v2, *(NDIS_PHYSICAL_ADDRESS *)(a1 + 192));
  if ( VirtualAddress )
  {
    *(_QWORD *)(a1 + 320) = VirtualAddress;
    *(_DWORD *)(a1 + 328) = v7;
    InitializeSListHead((PSLIST_HEADER)(a1 + 336));
    v11 = 0;
    if ( (_DWORD)v5 )
    {
      v12 = (struct _SLIST_ENTRY *)VirtualAddress;
      do
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 336), v12);
        ++v11;
        v12 = (struct _SLIST_ENTRY *)((char *)VirtualAddress + v6);
        VirtualAddress = (char *)VirtualAddress + v6;
      }
      while ( v11 < (unsigned int)v5 );
    }
    goto LABEL_13;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v9 = 45;
    v10 = (unsigned int)v7;
LABEL_23:
    WPP_SF_d(v8->AttachedDevice, v9, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, v10);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000ef64  mov     [rsp+arg_8], rbx
0x14000ef69  mov     [rsp+arg_10], rbp
0x14000ef6e  push    rsi
0x14000ef6f  push    rdi
0x14000ef70  push    r14
0x14000ef72  sub     rsp, 40h
0x14000ef76  mov     edx, [rcx+0B4h]
0x14000ef7c  mov     rbx, rcx
0x14000ef7f  add     edx, [rcx+0B0h]
0x14000ef85  mov     edi, [rcx+0A8h]
0x14000ef8b  mov     r8d, [rcx+0BCh]; MemoryFlags
0x14000ef92  add     edi, 77h ; 'w'
0x14000ef95  add     edi, edx
0x14000ef97  and     edi, 0FFFFFFF8h
0x14000ef9a  mov     [rcx+100h], edi
0x14000efa0  test    r8d, r8d
0x14000efa3  jnz     short loc_14000EFEA
0x14000efa5  call    cs:__imp_NdisGetVersion
0x14000efac  nop     dword ptr [rax+rax+00h]
0x14000efb1  xor     eax, eax
0x14000efb3  mov     edx, edi
0x14000efb5  mov     [rsp+58h+Depth], ax; Depth
0x14000efba  lea     rcx, [rbx+140h]; Lookaside
0x14000efc1  mov     [rsp+58h+Tag], 526E6157h; Tag
0x14000efc9  mov     r9d, 200h; Flags
0x14000efcf  mov     [rsp+58h+Size], rdx; Size
0x14000efd4  xor     r8d, r8d; Free
0x14000efd7  xor     edx, edx; Allocate
0x14000efd9  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000efe0  nop     dword ptr [rax+rax+00h]
0x14000efe5  jmp     loc_14000F0EA
0x14000efea  mov     eax, cs:glMaxMTU
0x14000eff0  xor     edx, edx
0x14000eff2  div     cs:glMinFragSize
0x14000eff8  mov     [rsp+58h+VirtualAddress], 0
0x14000f001  add     eax, [rcx+0ACh]
0x14000f007  mov     [rcx+104h], eax
0x14000f00d  lea     esi, [rax+1]
0x14000f010  mov     eax, [rcx+0B8h]
0x14000f016  imul    rsi, rax
0x14000f01a  mov     eax, 0FFFFFFFFh
0x14000f01f  cmp     rsi, rax
0x14000f022  ja      loc_14000F119
0x14000f028  mov     r14d, edi
0x14000f02b  mov     edi, esi
0x14000f02d  imul    rdi, r14
0x14000f031  cmp     rdi, rax
0x14000f034  ja      loc_14000F0F2
0x14000f03a  mov     r9, [rcx+0C0h]; HighestAcceptableAddress
0x14000f041  mov     edx, edi; Length
0x14000f043  lea     rcx, [rsp+58h+VirtualAddress]; VirtualAddress
0x14000f048  call    cs:__imp_NdisAllocateMemory
0x14000f04f  nop     dword ptr [rax+rax+00h]
0x14000f054  mov     rax, [rsp+58h+VirtualAddress]
0x14000f059  test    rax, rax
0x14000f05c  jnz     short loc_14000F097
0x14000f05e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f065  lea     rax, WPP_GLOBAL_Control
0x14000f06c  cmp     rcx, rax
0x14000f06f  jz      loc_14000F152
0x14000f075  mov     eax, [rcx+2Ch]
0x14000f078  test    al, 40h
0x14000f07a  jz      loc_14000F152
0x14000f080  cmp     byte ptr [rcx+29h], 2
0x14000f084  jb      loc_14000F152
0x14000f08a  mov     edx, 2Dh ; '-'
0x14000f08f  mov     r9d, edi
0x14000f092  jmp     loc_14000F142
0x14000f097  lea     rbp, [rbx+150h]
0x14000f09e  mov     [rbx+140h], rax
0x14000f0a5  mov     rcx, rbp; SListHead
0x14000f0a8  mov     [rbx+148h], edi
0x14000f0ae  call    cs:__imp_InitializeSListHead
0x14000f0b5  nop     dword ptr [rax+rax+00h]
0x14000f0ba  xor     edi, edi
0x14000f0bc  test    esi, esi
0x14000f0be  jz      short loc_14000F0EA
0x14000f0c0  mov     rax, [rsp+58h+VirtualAddress]
0x14000f0c5  mov     rdx, rax; ListEntry
0x14000f0c8  mov     rcx, rbp; ListHead
0x14000f0cb  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000f0d2  nop     dword ptr [rax+rax+00h]
0x14000f0d7  mov     rax, [rsp+58h+VirtualAddress]
0x14000f0dc  inc     edi
0x14000f0de  add     rax, r14
0x14000f0e1  mov     [rsp+58h+VirtualAddress], rax
0x14000f0e6  cmp     edi, esi
0x14000f0e8  jb      short loc_14000F0C5
0x14000f0ea  xor     eax, eax
0x14000f0ec  or      dword ptr [rbx+14h], 8
0x14000f0f0  jmp     short loc_14000F157
0x14000f0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0f9  lea     rax, WPP_GLOBAL_Control
0x14000f100  cmp     rcx, rax
0x14000f103  jz      short loc_14000F152
0x14000f105  mov     eax, [rcx+2Ch]
0x14000f108  test    al, 40h
0x14000f10a  jz      short loc_14000F152
0x14000f10c  cmp     byte ptr [rcx+29h], 2
0x14000f110  jb      short loc_14000F152
0x14000f112  mov     edx, 2Ch ; ','
0x14000f117  jmp     short loc_14000F13E
0x14000f119  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f120  lea     rax, WPP_GLOBAL_Control
0x14000f127  cmp     rcx, rax
0x14000f12a  jz      short loc_14000F152
0x14000f12c  mov     eax, [rcx+2Ch]
0x14000f12f  test    al, 40h
0x14000f131  jz      short loc_14000F152
0x14000f133  cmp     byte ptr [rcx+29h], 2
0x14000f137  jb      short loc_14000F152
0x14000f139  mov     edx, 2Bh ; '+'
0x14000f13e  or      r9d, 0FFFFFFFFh
0x14000f142  mov     rcx, [rcx+18h]
0x14000f146  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000f14d  call    WPP_SF_d
0x14000f152  mov     eax, 0C000009Ah
0x14000f157  mov     rbx, [rsp+58h+arg_8]
0x14000f15c  mov     rbp, [rsp+58h+arg_10]
0x14000f161  add     rsp, 40h
0x14000f165  pop     r14
0x14000f167  pop     rdi
0x14000f168  pop     rsi
0x14000f169  retn
```
