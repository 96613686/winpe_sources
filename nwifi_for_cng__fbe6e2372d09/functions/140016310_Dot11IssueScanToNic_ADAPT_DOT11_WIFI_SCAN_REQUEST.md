# Dot11IssueScanToNic(_ADAPT *,DOT11_WIFI_SCAN_REQUEST *)

- ea: `0x140016310`
- end: `0x140016506`
- name: `?Dot11IssueScanToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_SCAN_REQUEST@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(struct _ADAPT *, struct DOT11_WIFI_SCAN_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400559bc`

## callees

- `0x1400160d0`
- `0x140016310`
- `0x14001650c`
- `0x140055844`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016397`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016397`
- `ntoskrnl!ExAllocatePool2` at `0x1400163ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400163ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016486`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400164ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016486`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400164ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016497`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016497`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164cb`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140016418`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140016418`

## pseudocode

```c
__int64 __fastcall Dot11IssueScanToNic(struct _ADAPT *a1, struct DOT11_WIFI_SCAN_REQUEST *a2)
{
  size_t v2; // rsi
  const void *v4; // r14
  unsigned int v5; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  char *v8; // rbp
  unsigned int v9; // ebx
  struct DOT11_NDIS_REQUEST *v10; // rsi
  struct DOT11_NDIS_REQUEST *v11; // rsi
  void *v13; // [rsp+38h] [rbp-20h]
  int v14; // [rsp+60h] [rbp+8h] BYREF
  struct DOT11_NDIS_REQUEST *v15; // [rsp+68h] [rbp+10h] BYREF

  v2 = *((unsigned int *)a2 + 4);
  v4 = (const void *)*((_QWORD *)a2 + 4);
  a1->ScanModule.pOutstandingInNic = a2;
  v15 = 0;
  _InterlockedIncrement((volatile signed __int32 *)&a1->ScanModule.uNumOutstandingScannings);
  v5 = v2 + 16;
  if ( (unsigned int)v2 >= 0xFFFFFFF0 )
    goto LABEL_28;
  if ( v5 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v5 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v5 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v5 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v5, 1751741303);
LABEL_12:
  if ( !Pool2 )
  {
LABEL_28:
    v9 = -1073741670;
LABEL_29:
    a1->ScanModule.pOutstandingInNic = 0;
    _InterlockedDecrement((volatile signed __int32 *)&a1->ScanModule.uNumOutstandingScannings);
    return v9;
  }
  Pool2[2] = 1751741303;
  v8 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memmove(Pool2 + 4, v4, v2);
  v14 = Dot11AllocAndBuildNdisRequest(
          &v15,
          1u,
          0xD01030Bu,
          v2,
          v8,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))Dot11ScanOidCompletion,
          v8,
          v13);
  v9 = v14;
  if ( v14 )
  {
    v11 = v15;
LABEL_20:
    if ( v8 )
    {
      if ( *((_QWORD *)v8 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v8 - 2), v8 - 16);
      else
        ExFreePoolWithTag(v8 - 16, *((_DWORD *)v8 - 2));
    }
    if ( v11 )
    {
      if ( v11[-1].pCompletion )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v11[-1].pCompletion, &v11[-1].pCompletion);
      else
        ExFreePoolWithTag(&v11[-1].pCompletion, (ULONG)v11[-1].pVElan);
    }
    goto LABEL_29;
  }
  NdisGetSystemUpTimeEx(&a1->ScanModule.liScanningTimestamp);
  v10 = v15;
  Dot11Request(&v14, a1, v15->Request);
  v9 = v14;
  if ( v14 != 259 )
  {
    Dot11FreeScanOidRequest(v10);
    v8 = 0;
    v11 = 0;
    if ( v9 == 1076035585 )
      v9 = 0;
    if ( v9 )
      goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x140016310  mov     [rsp+arg_10], rbx
0x140016315  mov     [rsp+arg_18], rbp
0x14001631a  push    rsi
0x14001631b  push    rdi
0x14001631c  push    r14
0x14001631e  sub     rsp, 40h
0x140016322  mov     esi, [rdx+10h]
0x140016325  mov     rdi, rcx
0x140016328  mov     r14, [rdx+20h]
0x14001632c  mov     [rcx+0A8h], rdx
0x140016333  mov     [rsp+58h+arg_8], 0
0x14001633c  lock inc dword ptr [rcx+0A0h]
0x140016343  lea     eax, [rsi+10h]
0x140016346  cmp     eax, 10h
0x140016349  jb      loc_1400164D9
0x14001634f  mov     ecx, 40h ; '@'
0x140016354  mov     ebp, 68697377h
0x140016359  cmp     eax, ecx
0x14001635b  ja      short loc_140016366
0x14001635d  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140016364  jmp     short loc_140016394
0x140016366  cmp     eax, 100h
0x14001636b  ja      short loc_140016376
0x14001636d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140016374  jmp     short loc_140016394
0x140016376  cmp     eax, 400h
0x14001637b  ja      short loc_140016386
0x14001637d  lea     rbx, Lookaside
0x140016384  jmp     short loc_140016394
0x140016386  cmp     eax, 800h
0x14001638b  ja      short loc_1400163A5
0x14001638d  lea     rbx, stru_1400B31C0
0x140016394  mov     rcx, rbx; Lookaside
0x140016397  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001639e  nop     dword ptr [rax+rax+00h]
0x1400163a3  jmp     short loc_1400163B8
0x1400163a5  xor     ebx, ebx
0x1400163a7  mov     edx, eax
0x1400163a9  mov     r8d, ebp
0x1400163ac  call    cs:__imp_ExAllocatePool2
0x1400163b3  nop     dword ptr [rax+rax+00h]
0x1400163b8  test    rax, rax
0x1400163bb  jz      loc_1400164D9
0x1400163c1  mov     [rax+8], ebp
0x1400163c4  mov     r8, rsi; Size
0x1400163c7  lea     rbp, [rax+10h]
0x1400163cb  mov     [rax], rbx
0x1400163ce  mov     rcx, rbp; void *
0x1400163d1  mov     rdx, r14; Src
0x1400163d4  call    memmove
0x1400163d9  lea     rax, ?Dot11ScanOidCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; Dot11ScanOidCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x1400163e0  mov     [rsp+58h+var_28], rbp; void *
0x1400163e5  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x1400163ea  lea     rcx, [rsp+58h+arg_8]; struct DOT11_NDIS_REQUEST **
0x1400163ef  mov     r9d, esi; unsigned int
0x1400163f2  mov     [rsp+58h+var_38], rbp; void *
0x1400163f7  mov     edx, 1; unsigned int
0x1400163fc  mov     r8d, 0D01030Bh; unsigned int
0x140016402  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140016407  mov     [rsp+58h+arg_0], eax
0x14001640b  mov     ebx, eax
0x14001640d  test    eax, eax
0x14001640f  jnz     short loc_14001646A
0x140016411  lea     rcx, [rdi+0C8h]; pSystemUpTime
0x140016418  call    cs:__imp_NdisGetSystemUpTimeEx
0x14001641f  nop     dword ptr [rax+rax+00h]
0x140016424  mov     rsi, [rsp+58h+arg_8]
0x140016429  lea     rcx, [rsp+58h+arg_0]; int *
0x14001642e  mov     rdx, rdi; struct _ADAPT *
0x140016431  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140016435  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14001643a  mov     ebx, [rsp+58h+arg_0]
0x14001643e  cmp     ebx, 103h
0x140016444  jz      loc_1400164F0
0x14001644a  mov     rcx, rsi
0x14001644d  call    Dot11FreeScanOidRequest
0x140016452  xor     eax, eax
0x140016454  xor     ebp, ebp
0x140016456  xor     esi, esi
0x140016458  cmp     ebx, 40230001h
0x14001645e  cmovz   ebx, eax
0x140016461  test    ebx, ebx
0x140016463  jnz     short loc_14001646F
0x140016465  jmp     loc_1400164F0
0x14001646a  mov     rsi, [rsp+58h+arg_8]
0x14001646f  test    rbp, rbp
0x140016472  jz      short loc_1400164A3
0x140016474  lea     rcx, [rbp-10h]; P
0x140016478  mov     rax, [rcx]
0x14001647b  test    rax, rax
0x14001647e  jz      short loc_140016494
0x140016480  mov     rdx, rcx; Entry
0x140016483  mov     rcx, rax; Lookaside
0x140016486  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001648d  nop     dword ptr [rax+rax+00h]
0x140016492  jmp     short loc_1400164A3
0x140016494  mov     edx, [rcx+8]; Tag
0x140016497  call    cs:__imp_ExFreePoolWithTag
0x14001649e  nop     dword ptr [rax+rax+00h]
0x1400164a3  test    rsi, rsi
0x1400164a6  jz      short loc_1400164DE
0x1400164a8  lea     rcx, [rsi-10h]; P
0x1400164ac  mov     rax, [rcx]
0x1400164af  test    rax, rax
0x1400164b2  jz      short loc_1400164C8
0x1400164b4  mov     rdx, rcx; Entry
0x1400164b7  mov     rcx, rax; Lookaside
0x1400164ba  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400164c1  nop     dword ptr [rax+rax+00h]
0x1400164c6  jmp     short loc_1400164DE
0x1400164c8  mov     edx, [rcx+8]; Tag
0x1400164cb  call    cs:__imp_ExFreePoolWithTag
0x1400164d2  nop     dword ptr [rax+rax+00h]
0x1400164d7  jmp     short loc_1400164DE
0x1400164d9  mov     ebx, 0C000009Ah
0x1400164de  mov     qword ptr [rdi+0A8h], 0
0x1400164e9  lock dec dword ptr [rdi+0A0h]
0x1400164f0  mov     rbp, [rsp+58h+arg_18]
0x1400164f5  mov     eax, ebx
0x1400164f7  mov     rbx, [rsp+58h+arg_10]
0x1400164fc  add     rsp, 40h
0x140016500  pop     r14
0x140016502  pop     rdi
0x140016503  pop     rsi
0x140016504  retn
```
