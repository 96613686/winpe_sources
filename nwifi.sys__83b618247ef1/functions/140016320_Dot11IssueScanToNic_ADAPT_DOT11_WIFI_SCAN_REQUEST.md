# Dot11IssueScanToNic(_ADAPT *,DOT11_WIFI_SCAN_REQUEST *)

- ea: `0x140016320`
- end: `0x140016516`
- name: `?Dot11IssueScanToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_SCAN_REQUEST@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(struct _ADAPT *, struct DOT11_WIFI_SCAN_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005419c`

## callees

- `0x1400160e0`
- `0x140016320`
- `0x14001651c`
- `0x140054024`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400163a7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400163a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400163bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400163bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016496`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400164ca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016496`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400164ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164db`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140016428`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140016428`

## pseudocode

```c
__int64 __fastcall Dot11IssueScanToNic(struct _ADAPT *a1, struct DOT11_WIFI_SCAN_REQUEST *a2, __int64 a3, __int64 a4)
{
  size_t v4; // rsi
  const void *v6; // r14
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  char *v10; // rbp
  unsigned int v11; // ebx
  struct DOT11_NDIS_REQUEST *v12; // rsi
  struct DOT11_NDIS_REQUEST *v13; // rsi
  void *v15; // [rsp+38h] [rbp-20h]
  int v16; // [rsp+60h] [rbp+8h] BYREF
  struct DOT11_NDIS_REQUEST *v17; // [rsp+68h] [rbp+10h] BYREF

  v4 = *((unsigned int *)a2 + 4);
  v6 = (const void *)*((_QWORD *)a2 + 4);
  a1->ScanModule.pOutstandingInNic = a2;
  v17 = 0;
  _InterlockedIncrement((volatile signed __int32 *)&a1->ScanModule.uNumOutstandingScannings);
  v7 = v4 + 16;
  if ( (unsigned int)v4 >= 0xFFFFFFF0 )
    goto LABEL_28;
  if ( v7 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v7 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v7 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v7 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v7, 1751741303, a4);
LABEL_12:
  if ( !Pool2 )
  {
LABEL_28:
    v11 = -1073741670;
LABEL_29:
    a1->ScanModule.pOutstandingInNic = 0;
    _InterlockedDecrement((volatile signed __int32 *)&a1->ScanModule.uNumOutstandingScannings);
    return v11;
  }
  Pool2[2] = 1751741303;
  v10 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memmove(Pool2 + 4, v6, v4);
  v16 = Dot11AllocAndBuildNdisRequest(
          &v17,
          1u,
          0xD01030Bu,
          v4,
          v10,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))Dot11ScanOidCompletion,
          v10,
          v15);
  v11 = v16;
  if ( v16 )
  {
    v13 = v17;
LABEL_20:
    if ( v10 )
    {
      if ( *((_QWORD *)v10 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 - 2), v10 - 16);
      else
        ExFreePoolWithTag(v10 - 16, *((_DWORD *)v10 - 2));
    }
    if ( v13 )
    {
      if ( v13[-1].pCompletion )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v13[-1].pCompletion, &v13[-1].pCompletion);
      else
        ExFreePoolWithTag(&v13[-1].pCompletion, (ULONG)v13[-1].pVElan);
    }
    goto LABEL_29;
  }
  NdisGetSystemUpTimeEx(&a1->ScanModule.liScanningTimestamp);
  v12 = v17;
  Dot11Request(&v16, a1, v17->Request);
  v11 = v16;
  if ( v16 != 259 )
  {
    Dot11FreeScanOidRequest(v12);
    v10 = 0;
    v13 = 0;
    if ( v11 == 1076035585 )
      v11 = 0;
    if ( v11 )
      goto LABEL_20;
  }
  return v11;
}

```

## disassembly

```asm
0x140016320  mov     [rsp+arg_10], rbx
0x140016325  mov     [rsp+arg_18], rbp
0x14001632a  push    rsi
0x14001632b  push    rdi
0x14001632c  push    r14
0x14001632e  sub     rsp, 40h
0x140016332  mov     esi, [rdx+10h]
0x140016335  mov     rdi, rcx
0x140016338  mov     r14, [rdx+20h]
0x14001633c  mov     [rcx+0A8h], rdx
0x140016343  mov     [rsp+58h+arg_8], 0
0x14001634c  lock inc dword ptr [rcx+0A0h]
0x140016353  lea     eax, [rsi+10h]
0x140016356  cmp     eax, 10h
0x140016359  jb      loc_1400164E9
0x14001635f  mov     ecx, 40h ; '@'
0x140016364  mov     ebp, 68697377h
0x140016369  cmp     eax, ecx
0x14001636b  ja      short loc_140016376
0x14001636d  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140016374  jmp     short loc_1400163A4
0x140016376  cmp     eax, 100h
0x14001637b  ja      short loc_140016386
0x14001637d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140016384  jmp     short loc_1400163A4
0x140016386  cmp     eax, 400h
0x14001638b  ja      short loc_140016396
0x14001638d  lea     rbx, Lookaside
0x140016394  jmp     short loc_1400163A4
0x140016396  cmp     eax, 800h
0x14001639b  ja      short loc_1400163B5
0x14001639d  lea     rbx, stru_1400B0180
0x1400163a4  mov     rcx, rbx; Lookaside
0x1400163a7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400163ae  nop     dword ptr [rax+rax+00h]
0x1400163b3  jmp     short loc_1400163C8
0x1400163b5  xor     ebx, ebx
0x1400163b7  mov     edx, eax
0x1400163b9  mov     r8d, ebp
0x1400163bc  call    cs:__imp_ExAllocatePool2
0x1400163c3  nop     dword ptr [rax+rax+00h]
0x1400163c8  test    rax, rax
0x1400163cb  jz      loc_1400164E9
0x1400163d1  mov     [rax+8], ebp
0x1400163d4  mov     r8, rsi; Size
0x1400163d7  lea     rbp, [rax+10h]
0x1400163db  mov     [rax], rbx
0x1400163de  mov     rcx, rbp; void *
0x1400163e1  mov     rdx, r14; Src
0x1400163e4  call    memmove
0x1400163e9  lea     rax, ?Dot11ScanOidCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; Dot11ScanOidCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x1400163f0  mov     [rsp+58h+var_28], rbp; void *
0x1400163f5  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x1400163fa  lea     rcx, [rsp+58h+arg_8]; struct DOT11_NDIS_REQUEST **
0x1400163ff  mov     r9d, esi; unsigned int
0x140016402  mov     [rsp+58h+var_38], rbp; void *
0x140016407  mov     edx, 1; unsigned int
0x14001640c  mov     r8d, 0D01030Bh; unsigned int
0x140016412  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140016417  mov     [rsp+58h+arg_0], eax
0x14001641b  mov     ebx, eax
0x14001641d  test    eax, eax
0x14001641f  jnz     short loc_14001647A
0x140016421  lea     rcx, [rdi+0C8h]; pSystemUpTime
0x140016428  call    cs:__imp_NdisGetSystemUpTimeEx
0x14001642f  nop     dword ptr [rax+rax+00h]
0x140016434  mov     rsi, [rsp+58h+arg_8]
0x140016439  lea     rcx, [rsp+58h+arg_0]; int *
0x14001643e  mov     rdx, rdi; struct _ADAPT *
0x140016441  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140016445  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14001644a  mov     ebx, [rsp+58h+arg_0]
0x14001644e  cmp     ebx, 103h
0x140016454  jz      loc_140016500
0x14001645a  mov     rcx, rsi
0x14001645d  call    Dot11FreeScanOidRequest
0x140016462  xor     eax, eax
0x140016464  xor     ebp, ebp
0x140016466  xor     esi, esi
0x140016468  cmp     ebx, 40230001h
0x14001646e  cmovz   ebx, eax
0x140016471  test    ebx, ebx
0x140016473  jnz     short loc_14001647F
0x140016475  jmp     loc_140016500
0x14001647a  mov     rsi, [rsp+58h+arg_8]
0x14001647f  test    rbp, rbp
0x140016482  jz      short loc_1400164B3
0x140016484  lea     rcx, [rbp-10h]; P
0x140016488  mov     rax, [rcx]
0x14001648b  test    rax, rax
0x14001648e  jz      short loc_1400164A4
0x140016490  mov     rdx, rcx; Entry
0x140016493  mov     rcx, rax; Lookaside
0x140016496  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001649d  nop     dword ptr [rax+rax+00h]
0x1400164a2  jmp     short loc_1400164B3
0x1400164a4  mov     edx, [rcx+8]; Tag
0x1400164a7  call    cs:__imp_ExFreePoolWithTag
0x1400164ae  nop     dword ptr [rax+rax+00h]
0x1400164b3  test    rsi, rsi
0x1400164b6  jz      short loc_1400164EE
0x1400164b8  lea     rcx, [rsi-10h]; P
0x1400164bc  mov     rax, [rcx]
0x1400164bf  test    rax, rax
0x1400164c2  jz      short loc_1400164D8
0x1400164c4  mov     rdx, rcx; Entry
0x1400164c7  mov     rcx, rax; Lookaside
0x1400164ca  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400164d1  nop     dword ptr [rax+rax+00h]
0x1400164d6  jmp     short loc_1400164EE
0x1400164d8  mov     edx, [rcx+8]; Tag
0x1400164db  call    cs:__imp_ExFreePoolWithTag
0x1400164e2  nop     dword ptr [rax+rax+00h]
0x1400164e7  jmp     short loc_1400164EE
0x1400164e9  mov     ebx, 0C000009Ah
0x1400164ee  mov     qword ptr [rdi+0A8h], 0
0x1400164f9  lock dec dword ptr [rdi+0A0h]
0x140016500  mov     rbp, [rsp+58h+arg_18]
0x140016505  mov     eax, ebx
0x140016507  mov     rbx, [rsp+58h+arg_10]
0x14001650c  add     rsp, 40h
0x140016510  pop     r14
0x140016512  pop     rdi
0x140016513  pop     rsi
0x140016514  retn
```
