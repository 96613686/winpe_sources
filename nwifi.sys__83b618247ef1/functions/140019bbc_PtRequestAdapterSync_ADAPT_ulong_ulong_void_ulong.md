# PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)

- ea: `0x140019bbc`
- end: `0x140019e2e`
- name: `?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z`
- size: `626`
- prototype: `__int64 __fastcall(struct _ADAPT *, unsigned int, unsigned int, void *, unsigned int)`
- caller_count: `93`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400143e8`
- `0x140014b90`
- `0x14001667c`
- `0x140019494`
- `0x140019648`
- `0x1400197b0`
- `0x140019ad0`
- `0x14001e830`
- `0x1400210c8`
- `0x140023ab0`
- `0x1400337f4`
- `0x140034274`
- `0x140036c48`
- `0x140038f84`
- `0x14003bd08`
- `0x1400562e0`
- `0x1400564f8`
- `0x140056660`
- `0x140056740`
- `0x140056f08`
- `0x1400571c0`
- `0x1400605f0`
- `0x1400622ec`
- `0x1400627c8`
- `0x140062e30`
- `0x1400638d8`
- `0x1400639cc`
- `0x140063bdc`
- `0x140063cfc`
- `0x1400640f8`
- `0x140064630`
- `0x140064760`
- `0x140067b64`
- `0x140067cf4`
- `0x140067de0`
- `0x140068be0`
- `0x140068fb4`
- `0x140069274`
- `0x14006a240`
- `0x14006aa40`
- `0x14006ad80`
- `0x14006b000`
- `0x14006b090`
- `0x14006bfc0`
- `0x14006c0b0`
- `0x14006c1c0`
- `0x14006c230`
- `0x14006c490`
- `0x14006c580`
- `0x14006c860`

## callees

- `0x14000addc`
- `0x1400160e0`
- `0x1400165c4`
- `0x140019bbc`
- `0x140038e50`
- `0x140038ebc`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140019c0d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140019c0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019d1d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019dfd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019d1d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019dfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019d31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019d31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e0e`
- `NDIS!NdisResetEvent` at `0x140019d42`
- `NDIS!NdisResetEvent` at `0x140019d42`
- `NDIS!NdisWaitEvent` at `0x140019c99`
- `NDIS!NdisWaitEvent` at `0x140019c99`
- `NDIS!NdisInitializeEvent` at `0x140019bf7`
- `NDIS!NdisInitializeEvent` at `0x140019bf7`
- `NDIS!NdisMSleep` at `0x140019d06`
- `NDIS!NdisMSleep` at `0x140019d06`

## pseudocode

```c
__int64 __fastcall PtRequestAdapterSync(struct _ADAPT *a1, unsigned int a2, unsigned int a3, void *a4, unsigned int a5)
{
  unsigned int v6; // r15d
  char *v10; // rax
  ULONG *v11; // rdi
  char *v12; // r14
  struct _NDIS_OID_REQUEST *v13; // r8
  unsigned int v14; // ebx
  int v15; // ecx
  _VELAN *pActiveVElan; // rax
  GUID *v17; // r8
  int v19; // [rsp+40h] [rbp-68h] BYREF
  struct _NDIS_EVENT Event; // [rsp+48h] [rbp-60h] BYREF

  memset(&Event, 0, sizeof(Event));
  v6 = 0;
  NdisInitializeEvent(&Event);
  while ( 1 )
  {
    v10 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
    v11 = (ULONG *)v10;
    if ( !v10 )
    {
      v12 = 0;
      v14 = -1073741670;
      goto LABEL_18;
    }
    v12 = v10 + 16;
    *(_QWORD *)v10 = &Lookaside;
    *((_DWORD *)v10 + 2) = 1919513463;
    Dot11BuildNdisRequest(
      (struct DOT11_NDIS_REQUEST *)(v10 + 16),
      a2,
      a3,
      a5,
      a4,
      (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))PtCompleteBlockingRequest,
      &Event,
      0);
    v13 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)v12 + 1);
    v19 = 0;
    Dot11Request(&v19, a1, v13);
    v14 = v19;
    if ( v19 == 259 )
    {
      NdisWaitEvent(&Event, 0);
      v14 = *(_DWORD *)v12;
    }
    if ( v14 != -1073676271 )
      break;
    if ( v6 >= 0x32 )
      goto LABEL_18;
    ++v6;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_Dqd(WPP_GLOBAL_Control->AttachedDevice, 14, 3221291025LL, a3, a1, -1073676271);
    }
    NdisMSleep(0x186A0u);
    if ( *(_QWORD *)v11 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v11, v11);
    else
      ExFreePoolWithTag(v11, v11[2]);
    NdisResetEvent(&Event);
  }
  if ( !v14 )
    goto LABEL_27;
LABEL_18:
  v15 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    WPP_SF_dqD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids, v14, a1, a3);
  }
  if ( (byte_1400AF802 & 0x10) != 0 )
  {
    if ( !a1 || (pActiveVElan = a1->pActiveVElan, LODWORD(v17) = (_DWORD)pActiveVElan + 4920, !pActiveVElan) )
      v17 = &`InterfaceGuidFromAdapter'::`2'::gNull;
    McTemplateK0pqq_EtwWriteTransfer(v15, (unsigned int)RequestAdapterSync, (_DWORD)v17, (_DWORD)a1, a3, v14);
  }
LABEL_27:
  if ( v12 )
  {
    if ( *((_QWORD *)v12 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
    else
      ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
  }
  return v14;
}

```

## disassembly

```asm
0x140019bbc  push    rbx
0x140019bbe  push    rbp
0x140019bbf  push    rsi
0x140019bc0  push    rdi
0x140019bc1  push    r12
0x140019bc3  push    r13
0x140019bc5  push    r14
0x140019bc7  push    r15
0x140019bc9  sub     rsp, 68h
0x140019bcd  mov     rsi, rcx
0x140019bd0  mov     dword ptr [rsp+0A8h+Event.Event.Header.___u0], 0
0x140019bd8  xorps   xmm0, xmm0
0x140019bdb  lea     rcx, [rsp+0A8h+Event]; Event
0x140019be0  xor     eax, eax
0x140019be2  xor     r15d, r15d
0x140019be5  movups  xmmword ptr [rsp+0A8h+Event.Event.Header.SignalState], xmm0
0x140019bea  mov     dword ptr [rsp+0A8h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140019bee  mov     r12, r9
0x140019bf1  mov     ebp, r8d
0x140019bf4  mov     r13d, edx
0x140019bf7  call    cs:__imp_NdisInitializeEvent
0x140019bfe  nop     dword ptr [rax+rax+00h]
0x140019c03  lea     rbx, Lookaside
0x140019c0a  mov     rcx, rbx; Lookaside
0x140019c0d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140019c14  nop     dword ptr [rax+rax+00h]
0x140019c19  mov     rdi, rax
0x140019c1c  test    rax, rax
0x140019c1f  jz      loc_140019D5C
0x140019c25  mov     r9d, [rsp+0A8h+arg_20]; unsigned int
0x140019c2d  lea     r14, [rax+10h]
0x140019c31  mov     [rax], rbx
0x140019c34  mov     r8d, ebp; unsigned int
0x140019c37  mov     dword ptr [rax+8], 72697377h
0x140019c3e  mov     edx, r13d; unsigned int
0x140019c41  mov     [rsp+0A8h+var_70], 0; void *
0x140019c4a  lea     rax, [rsp+0A8h+Event]
0x140019c4f  mov     [rsp+0A8h+var_78], rax; void *
0x140019c54  mov     rcx, r14; struct DOT11_NDIS_REQUEST *
0x140019c57  lea     rax, ?PtCompleteBlockingRequest@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; PtCompleteBlockingRequest(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140019c5e  mov     [rsp+0A8h+var_80], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x140019c63  mov     [rsp+0A8h+var_88], r12; void *
0x140019c68  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140019c6d  mov     r8, [r14+8]; struct _NDIS_OID_REQUEST *
0x140019c71  lea     rcx, [rsp+0A8h+var_68]; int *
0x140019c76  mov     rdx, rsi; struct _ADAPT *
0x140019c79  mov     [rsp+0A8h+var_68], 0
0x140019c81  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140019c86  mov     ebx, [rsp+0A8h+var_68]
0x140019c8a  cmp     ebx, 103h
0x140019c90  jnz     short loc_140019CA8
0x140019c92  xor     edx, edx; MsToWait
0x140019c94  lea     rcx, [rsp+0A8h+Event]; Event
0x140019c99  call    cs:__imp_NdisWaitEvent
0x140019ca0  nop     dword ptr [rax+rax+00h]
0x140019ca5  mov     ebx, [r14]
0x140019ca8  mov     r8d, 0C0010011h
0x140019cae  cmp     ebx, r8d
0x140019cb1  jnz     loc_140019D53
0x140019cb7  cmp     r15d, 32h ; '2'
0x140019cbb  jnb     loc_140019D64
0x140019cc1  inc     r15d
0x140019cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ccb  lea     rax, WPP_GLOBAL_Control
0x140019cd2  cmp     rcx, rax
0x140019cd5  jz      short loc_140019D01
0x140019cd7  cmp     byte ptr [rcx+29h], 3
0x140019cdb  jb      short loc_140019D01
0x140019cdd  test    dword ptr [rcx+2Ch], 100h
0x140019ce4  jz      short loc_140019D01
0x140019ce6  mov     rcx, [rcx+18h]
0x140019cea  mov     edx, 0Eh
0x140019cef  mov     dword ptr [rsp+0A8h+var_80], r8d
0x140019cf4  mov     r9d, ebp
0x140019cf7  mov     [rsp+0A8h+var_88], rsi
0x140019cfc  call    WPP_SF_Dqd
0x140019d01  mov     ecx, 186A0h; MicrosecondsToSleep
0x140019d06  call    cs:__imp_NdisMSleep
0x140019d0d  nop     dword ptr [rax+rax+00h]
0x140019d12  mov     rcx, [rdi]; Lookaside
0x140019d15  test    rcx, rcx
0x140019d18  jz      short loc_140019D2B
0x140019d1a  mov     rdx, rdi; Entry
0x140019d1d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019d24  nop     dword ptr [rax+rax+00h]
0x140019d29  jmp     short loc_140019D3D
0x140019d2b  mov     edx, [rdi+8]; Tag
0x140019d2e  mov     rcx, rdi; P
0x140019d31  call    cs:__imp_ExFreePoolWithTag
0x140019d38  nop     dword ptr [rax+rax+00h]
0x140019d3d  lea     rcx, [rsp+0A8h+Event]; Event
0x140019d42  call    cs:__imp_NdisResetEvent
0x140019d49  nop     dword ptr [rax+rax+00h]
0x140019d4e  jmp     loc_140019C03
0x140019d53  test    ebx, ebx
0x140019d55  jnz     short loc_140019D64
0x140019d57  jmp     loc_140019DE6
0x140019d5c  xor     r14d, r14d
0x140019d5f  mov     ebx, 0C000009Ah
0x140019d64  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d6b  lea     rax, WPP_GLOBAL_Control
0x140019d72  cmp     rcx, rax
0x140019d75  jz      short loc_140019DA7
0x140019d77  cmp     byte ptr [rcx+29h], 3
0x140019d7b  jb      short loc_140019DA7
0x140019d7d  test    dword ptr [rcx+2Ch], 100h
0x140019d84  jz      short loc_140019DA7
0x140019d86  mov     rcx, [rcx+18h]
0x140019d8a  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140019d91  mov     edx, 0Fh
0x140019d96  mov     dword ptr [rsp+0A8h+var_80], ebp
0x140019d9a  mov     r9d, ebx
0x140019d9d  mov     [rsp+0A8h+var_88], rsi
0x140019da2  call    WPP_SF_dqD
0x140019da7  test    cs:byte_1400AF802, 10h
0x140019dae  jz      short loc_140019DE6
0x140019db0  test    rsi, rsi
0x140019db3  jz      short loc_140019DC8
0x140019db5  mov     rax, [rsi+80h]
0x140019dbc  lea     r8, [rax+1338h]
0x140019dc3  test    rax, rax
0x140019dc6  jnz     short loc_140019DCF
0x140019dc8  lea     r8, ?gNull@?1??InterfaceGuidFromAdapter@@YAPEBU_GUID@@PEAU_ADAPT@@@Z@4U2@B; _GUID const `InterfaceGuidFromAdapter(_ADAPT *)'::`2'::gNull
0x140019dcf  mov     dword ptr [rsp+0A8h+var_80], ebx
0x140019dd3  lea     rdx, RequestAdapterSync
0x140019dda  mov     r9, rsi
0x140019ddd  mov     dword ptr [rsp+0A8h+var_88], ebp
0x140019de1  call    McTemplateK0pqq_EtwWriteTransfer
0x140019de6  test    r14, r14
0x140019de9  jz      short loc_140019E1A
0x140019deb  lea     rcx, [r14-10h]; P
0x140019def  mov     rax, [rcx]
0x140019df2  test    rax, rax
0x140019df5  jz      short loc_140019E0B
0x140019df7  mov     rdx, rcx; Entry
0x140019dfa  mov     rcx, rax; Lookaside
0x140019dfd  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019e04  nop     dword ptr [rax+rax+00h]
0x140019e09  jmp     short loc_140019E1A
0x140019e0b  mov     edx, [rcx+8]; Tag
0x140019e0e  call    cs:__imp_ExFreePoolWithTag
0x140019e15  nop     dword ptr [rax+rax+00h]
0x140019e1a  mov     eax, ebx
0x140019e1c  add     rsp, 68h
0x140019e20  pop     r15
0x140019e22  pop     r14
0x140019e24  pop     r13
0x140019e26  pop     r12
0x140019e28  pop     rdi
0x140019e29  pop     rsi
0x140019e2a  pop     rbp
0x140019e2b  pop     rbx
0x140019e2c  retn
```
