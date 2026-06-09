# WFDIssueDiscoverToNic(_ADAPT *,DOT11_WIFI_WFD_DISCOVER_REQUEST *)

- ea: `0x140056434`
- end: `0x14005662b`
- name: `?WFDIssueDiscoverToNic@@YAHPEAU_ADAPT@@PEAUDOT11_WIFI_WFD_DISCOVER_REQUEST@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(struct _ADAPT *, struct DOT11_WIFI_WFD_DISCOVER_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056634`

## callees

- `0x1400160d0`
- `0x14001650c`
- `0x140055844`
- `0x140056434`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400564bb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400564bb`
- `ntoskrnl!ExAllocatePool2` at `0x1400564d0`
- `ntoskrnl!ExAllocatePool2` at `0x1400564d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400565ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400565df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400565ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400565df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400565bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400565f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400565bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400565f0`
- `NDIS!NdisGetSystemUpTimeEx` at `0x14005653c`
- `NDIS!NdisGetSystemUpTimeEx` at `0x14005653c`

## pseudocode

```c
__int64 __fastcall WFDIssueDiscoverToNic(struct _ADAPT *a1, struct DOT11_WIFI_WFD_DISCOVER_REQUEST *a2)
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
  Pool2 = (_DWORD *)ExAllocatePool2(64, v5, 879326071);
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
  Pool2[2] = 879326071;
  v8 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memmove(Pool2 + 4, v4, v2);
  v14 = Dot11AllocAndBuildNdisRequest(
          &v15,
          1u,
          0xE050105u,
          v2,
          v8,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))WFDDiscoverOidCompletion,
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
0x140056434  mov     [rsp+arg_10], rbx
0x140056439  mov     [rsp+arg_18], rbp
0x14005643e  push    rsi
0x14005643f  push    rdi
0x140056440  push    r14
0x140056442  sub     rsp, 40h
0x140056446  mov     esi, [rdx+10h]
0x140056449  mov     rdi, rcx
0x14005644c  mov     r14, [rdx+20h]
0x140056450  mov     [rcx+0A8h], rdx
0x140056457  mov     [rsp+58h+arg_8], 0
0x140056460  lock inc dword ptr [rcx+0A0h]
0x140056467  lea     eax, [rsi+10h]
0x14005646a  cmp     eax, 10h
0x14005646d  jb      loc_1400565FE
0x140056473  mov     ecx, 40h ; '@'
0x140056478  mov     ebp, 34697377h
0x14005647d  cmp     eax, ecx
0x14005647f  ja      short loc_14005648A
0x140056481  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140056488  jmp     short loc_1400564B8
0x14005648a  cmp     eax, 100h
0x14005648f  ja      short loc_14005649A
0x140056491  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140056498  jmp     short loc_1400564B8
0x14005649a  cmp     eax, 400h
0x14005649f  ja      short loc_1400564AA
0x1400564a1  lea     rbx, Lookaside
0x1400564a8  jmp     short loc_1400564B8
0x1400564aa  cmp     eax, 800h
0x1400564af  ja      short loc_1400564C9
0x1400564b1  lea     rbx, stru_1400B31C0
0x1400564b8  mov     rcx, rbx; Lookaside
0x1400564bb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400564c2  nop     dword ptr [rax+rax+00h]
0x1400564c7  jmp     short loc_1400564DC
0x1400564c9  xor     ebx, ebx
0x1400564cb  mov     edx, eax
0x1400564cd  mov     r8d, ebp
0x1400564d0  call    cs:__imp_ExAllocatePool2
0x1400564d7  nop     dword ptr [rax+rax+00h]
0x1400564dc  test    rax, rax
0x1400564df  jz      loc_1400565FE
0x1400564e5  mov     [rax+8], ebp
0x1400564e8  mov     r8, rsi; Size
0x1400564eb  lea     rbp, [rax+10h]
0x1400564ef  mov     [rax], rbx
0x1400564f2  mov     rcx, rbp; void *
0x1400564f5  mov     rdx, r14; Src
0x1400564f8  call    memmove
0x1400564fd  lea     rax, ?WFDDiscoverOidCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; WFDDiscoverOidCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140056504  mov     [rsp+58h+var_28], rbp; void *
0x140056509  mov     [rsp+58h+var_30], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x14005650e  lea     rcx, [rsp+58h+arg_8]; struct DOT11_NDIS_REQUEST **
0x140056513  mov     r9d, esi; unsigned int
0x140056516  mov     [rsp+58h+var_38], rbp; void *
0x14005651b  mov     edx, 1; unsigned int
0x140056520  mov     r8d, 0E050105h; unsigned int
0x140056526  call    ?Dot11AllocAndBuildNdisRequest@@YAHPEAPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@PEAU1@@Z11@Z; Dot11AllocAndBuildNdisRequest(DOT11_NDIS_REQUEST * *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x14005652b  mov     [rsp+58h+arg_0], eax
0x14005652f  mov     ebx, eax
0x140056531  test    eax, eax
0x140056533  jnz     short loc_14005658F
0x140056535  lea     rcx, [rdi+0C8h]; pSystemUpTime
0x14005653c  call    cs:__imp_NdisGetSystemUpTimeEx
0x140056543  nop     dword ptr [rax+rax+00h]
0x140056548  mov     rsi, [rsp+58h+arg_8]
0x14005654d  lea     rcx, [rsp+58h+arg_0]; int *
0x140056552  mov     rdx, rdi; struct _ADAPT *
0x140056555  mov     r8, [rsi+8]; struct _NDIS_OID_REQUEST *
0x140056559  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x14005655e  mov     ebx, [rsp+58h+arg_0]
0x140056562  cmp     ebx, 103h
0x140056568  jz      loc_140056615
0x14005656e  mov     rcx, rsi
0x140056571  call    Dot11FreeScanOidRequest
0x140056576  xor     eax, eax
0x140056578  xor     ebp, ebp
0x14005657a  xor     esi, esi
0x14005657c  cmp     ebx, 40230001h
0x140056582  cmovz   ebx, eax
0x140056585  test    ebx, ebx
0x140056587  jz      loc_140056615
0x14005658d  jmp     short loc_140056594
0x14005658f  mov     rsi, [rsp+58h+arg_8]
0x140056594  test    rbp, rbp
0x140056597  jz      short loc_1400565C8
0x140056599  lea     rcx, [rbp-10h]; P
0x14005659d  mov     rax, [rcx]
0x1400565a0  test    rax, rax
0x1400565a3  jz      short loc_1400565B9
0x1400565a5  mov     rdx, rcx; Entry
0x1400565a8  mov     rcx, rax; Lookaside
0x1400565ab  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400565b2  nop     dword ptr [rax+rax+00h]
0x1400565b7  jmp     short loc_1400565C8
0x1400565b9  mov     edx, [rcx+8]; Tag
0x1400565bc  call    cs:__imp_ExFreePoolWithTag
0x1400565c3  nop     dword ptr [rax+rax+00h]
0x1400565c8  test    rsi, rsi
0x1400565cb  jz      short loc_140056603
0x1400565cd  lea     rcx, [rsi-10h]; P
0x1400565d1  mov     rax, [rcx]
0x1400565d4  test    rax, rax
0x1400565d7  jz      short loc_1400565ED
0x1400565d9  mov     rdx, rcx; Entry
0x1400565dc  mov     rcx, rax; Lookaside
0x1400565df  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400565e6  nop     dword ptr [rax+rax+00h]
0x1400565eb  jmp     short loc_140056603
0x1400565ed  mov     edx, [rcx+8]; Tag
0x1400565f0  call    cs:__imp_ExFreePoolWithTag
0x1400565f7  nop     dword ptr [rax+rax+00h]
0x1400565fc  jmp     short loc_140056603
0x1400565fe  mov     ebx, 0C000009Ah
0x140056603  mov     qword ptr [rdi+0A8h], 0
0x14005660e  lock dec dword ptr [rdi+0A0h]
0x140056615  mov     rbp, [rsp+58h+arg_18]
0x14005661a  mov     eax, ebx
0x14005661c  mov     rbx, [rsp+58h+arg_10]
0x140056621  add     rsp, 40h
0x140056625  pop     r14
0x140056627  pop     rdi
0x140056628  pop     rsi
0x140056629  retn
```
