# WFDIssueDiscoverToNic(_ADAPT *,DOT11_WIFI_WFD_DISCOVER_REQUEST *)

- ea: `0x140054c14`
- end: `0x140054e0b`
- name: `?WFDIssueDiscoverToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_WFD_DISCOVER_REQUEST@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(struct _ADAPT *, struct DOT11_WIFI_WFD_DISCOVER_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140054e14`

## callees

- `0x1400160e0`
- `0x14001651c`
- `0x140054024`
- `0x140054c14`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054c9b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054c9b`
- `ntoskrnl!ExAllocatePool2` at `0x140054cb0`
- `ntoskrnl!ExAllocatePool2` at `0x140054cb0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054d8b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054dbf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054d8b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054dbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054dd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054d9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054dd0`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140054d1c`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140054d1c`

## pseudocode

```c
__int64 __fastcall WFDIssueDiscoverToNic(
        struct _ADAPT *a1,
        struct DOT11_WIFI_WFD_DISCOVER_REQUEST *a2,
        __int64 a3,
        __int64 a4)
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
  Pool2 = (_DWORD *)ExAllocatePool2(64, v7, 879326071, a4);
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
  Pool2[2] = 879326071;
  v10 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memmove(Pool2 + 4, v6, v4);
  v16 = Dot11AllocAndBuildNdisRequest(
          &v17,
          1u,
          0xE050105u,
          v4,
          v10,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))WFDDiscoverOidCompletion,
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
0x140054c14  mov     [rsp+arg_10], rbx
0x140054c19  mov     [rsp+arg_18], rbp
0x140054c1e  push    rsi
0x140054c1f  push    rdi
0x140054c20  push    r14
0x140054c22  sub     rsp, 40h
0x140054c26  mov     esi, [rdx+10h]
0x140054c29  mov     rdi, rcx
0x140054c2c  mov     r14, [rdx+20h]
0x140054c30  mov     [rcx+0A8h], rdx
0x140054c37  mov     [rsp+58h+arg_8], 0
0x140054c40  lock inc dword ptr [rcx+0A0h]
0x140054c47  lea     eax, [rsi+10h]
0x140054c4a  cmp     eax, 10h
0x140054c4d  jb      loc_140054DDE
0x140054c53  mov     ecx, 40h ; '@'
0x140054c58  mov     ebp, 34697377h
0x140054c5d  cmp     eax, ecx
0x140054c5f  ja      short loc_140054C6A
0x140054c61  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140054c68  jmp     short loc_140054C98
0x140054c6a  cmp     eax, 100h
0x140054c6f  ja      short loc_140054C7A
0x140054c71  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140054c78  jmp     short loc_140054C98
0x140054c7a  cmp     eax, 400h
0x140054c7f  ja      short loc_140054C8A
0x140054c81  lea     rbx, Lookaside
0x140054c88  jmp     short loc_140054C98
0x140054c8a  cmp     eax, 800h
0x140054c8f  ja      short loc_140054CA9
0x140054c91  lea     rbx, stru_1400B0180
0x140054c98  mov     rcx, rbx; Lookaside
0x140054c9b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140054ca2  nop     dword ptr [rax+rax+00h]
0x140054ca7  jmp     short loc_140054CBC
0x140054ca9  xor     ebx, ebx
0x140054cab  mov     edx, eax
0x140054cad  mov     r8d, ebp
0x140054cb0  call    cs:__imp_ExAllocatePool2
0x140054cb7  nop     dword ptr [rax+rax+00h]
0x140054cbc  test    rax, rax
0x140054cbf  jz      loc_140054DDE
0x140054cc5  mov     [rax+8], ebp
0x140054cc8  mov     r8, rsi; Size
0x140054ccb  lea     rbp, [rax+10h]
0x140054ccf  mov     [rax], rbx
0x140054cd2  mov     rcx, rbp; void *
0x140054cd5  mov     rdx, r14; Src
0x140054cd8  call    memmove
0x140054cdd  lea     rax, ?WFDDiscoverOidCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; WFDDiscoverOidCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140054ce4  mov     [rsp+58h+var_28], rbp; void *
0x140054ce9  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x140054cee  lea     rcx, [rsp+58h+arg_8]; struct DOT11_NDIS_REQUEST **
0x140054cf3  mov     r9d, esi; unsigned int
0x140054cf6  mov     [rsp+58h+var_38], rbp; void *
0x140054cfb  mov     edx, 1; unsigned int
0x140054d00  mov     r8d, 0E050105h; unsigned int
0x140054d06  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140054d0b  mov     [rsp+58h+arg_0], eax
0x140054d0f  mov     ebx, eax
0x140054d11  test    eax, eax
0x140054d13  jnz     short loc_140054D6F
0x140054d15  lea     rcx, [rdi+0C8h]; pSystemUpTime
0x140054d1c  call    cs:__imp_NdisGetSystemUpTimeEx
0x140054d23  nop     dword ptr [rax+rax+00h]
0x140054d28  mov     rsi, [rsp+58h+arg_8]
0x140054d2d  lea     rcx, [rsp+58h+arg_0]; int *
0x140054d32  mov     rdx, rdi; struct _ADAPT *
0x140054d35  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140054d39  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140054d3e  mov     ebx, [rsp+58h+arg_0]
0x140054d42  cmp     ebx, 103h
0x140054d48  jz      loc_140054DF5
0x140054d4e  mov     rcx, rsi
0x140054d51  call    Dot11FreeScanOidRequest
0x140054d56  xor     eax, eax
0x140054d58  xor     ebp, ebp
0x140054d5a  xor     esi, esi
0x140054d5c  cmp     ebx, 40230001h
0x140054d62  cmovz   ebx, eax
0x140054d65  test    ebx, ebx
0x140054d67  jz      loc_140054DF5
0x140054d6d  jmp     short loc_140054D74
0x140054d6f  mov     rsi, [rsp+58h+arg_8]
0x140054d74  test    rbp, rbp
0x140054d77  jz      short loc_140054DA8
0x140054d79  lea     rcx, [rbp-10h]; P
0x140054d7d  mov     rax, [rcx]
0x140054d80  test    rax, rax
0x140054d83  jz      short loc_140054D99
0x140054d85  mov     rdx, rcx; Entry
0x140054d88  mov     rcx, rax; Lookaside
0x140054d8b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054d92  nop     dword ptr [rax+rax+00h]
0x140054d97  jmp     short loc_140054DA8
0x140054d99  mov     edx, [rcx+8]; Tag
0x140054d9c  call    cs:__imp_ExFreePoolWithTag
0x140054da3  nop     dword ptr [rax+rax+00h]
0x140054da8  test    rsi, rsi
0x140054dab  jz      short loc_140054DE3
0x140054dad  lea     rcx, [rsi-10h]; P
0x140054db1  mov     rax, [rcx]
0x140054db4  test    rax, rax
0x140054db7  jz      short loc_140054DCD
0x140054db9  mov     rdx, rcx; Entry
0x140054dbc  mov     rcx, rax; Lookaside
0x140054dbf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054dc6  nop     dword ptr [rax+rax+00h]
0x140054dcb  jmp     short loc_140054DE3
0x140054dcd  mov     edx, [rcx+8]; Tag
0x140054dd0  call    cs:__imp_ExFreePoolWithTag
0x140054dd7  nop     dword ptr [rax+rax+00h]
0x140054ddc  jmp     short loc_140054DE3
0x140054dde  mov     ebx, 0C000009Ah
0x140054de3  mov     qword ptr [rdi+0A8h], 0
0x140054dee  lock dec dword ptr [rdi+0A0h]
0x140054df5  mov     rbp, [rsp+58h+arg_18]
0x140054dfa  mov     eax, ebx
0x140054dfc  mov     rbx, [rsp+58h+arg_10]
0x140054e01  add     rsp, 40h
0x140054e05  pop     r14
0x140054e07  pop     rdi
0x140054e08  pop     rsi
0x140054e09  retn
```
