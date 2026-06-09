# PtCallAdapterSync(_ADAPT *,ulong,ulong,ulong,void *,ulong *,ulong *)

- ea: `0x140015e34`
- end: `0x140016037`
- name: `?PtCallAdapterSync@@YAHPEAU_ADAPT@@KKKPEAXPEAK2@Z`
- size: `515`
- prototype: `__int64 __fastcall(struct _ADAPT *, unsigned int, unsigned int, unsigned int, void *, unsigned int *, unsigned int *)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140014960`
- `0x140014afc`
- `0x140015450`
- `0x14001589c`
- `0x140033380`
- `0x1400337f4`
- `0x1400574f0`
- `0x14007eb54`

## callees

- `0x14000addc`
- `0x140015e34`
- `0x140016040`
- `0x1400160e0`
- `0x140038ebc`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015e7b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015e7b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016001`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016001`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016012`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016012`
- `NDIS!NdisWaitEvent` at `0x140015ef9`
- `NDIS!NdisWaitEvent` at `0x140015ef9`
- `NDIS!NdisInitializeEvent` at `0x140015e65`
- `NDIS!NdisInitializeEvent` at `0x140015e65`

## pseudocode

```c
__int64 __fastcall PtCallAdapterSync(
        struct _ADAPT *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  char *v11; // rax
  char *v12; // rdi
  unsigned int v13; // ebx
  struct _NDIS_OID_REQUEST *v14; // r8
  int v15; // ecx
  _VELAN *pActiveVElan; // rax
  GUID *v17; // r8
  void (*v19)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *); // [rsp+28h] [rbp-60h]
  void *v20; // [rsp+38h] [rbp-50h]
  int v21; // [rsp+40h] [rbp-48h] BYREF
  struct _NDIS_EVENT Event; // [rsp+48h] [rbp-40h] BYREF

  memset(&Event, 0, sizeof(Event));
  NdisInitializeEvent(&Event);
  v11 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
  if ( !v11 )
  {
    v12 = 0;
    v13 = -1073741670;
LABEL_13:
    v15 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_dqD(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids, v13, a1, a2);
    }
    if ( (v13 != -2147483643 || a2 != 234946937) && (byte_1400AF802 & 0x10) != 0 )
    {
      if ( !a1 || (pActiveVElan = a1->pActiveVElan, LODWORD(v17) = (_DWORD)pActiveVElan + 4920, !pActiveVElan) )
        v17 = &`InterfaceGuidFromAdapter'::`2'::gNull;
      McTemplateK0pqq_EtwWriteTransfer(v15, (unsigned int)CallAdapterSync, (_DWORD)v17, (_DWORD)a1, a2, v13);
    }
    goto LABEL_24;
  }
  *(_QWORD *)v11 = &Lookaside;
  v12 = v11 + 16;
  *((_DWORD *)v11 + 2) = 1919513463;
  Dot11BuildNdisMethod((struct DOT11_NDIS_REQUEST *)(v11 + 16), a2, a3, a4, a5, v19, &Event, v20);
  v14 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)v12 + 1);
  v21 = 0;
  Dot11Request(&v21, a1, v14);
  v13 = v21;
  if ( v21 == 259 )
  {
    NdisWaitEvent(&Event, 0);
    v13 = *(_DWORD *)v12;
  }
  if ( a7 )
  {
    *a7 = *(_DWORD *)(*((_QWORD *)v12 + 1) + 68LL);
    if ( v13 == -1073676268 || v13 == -1073676266 || v13 == -2147483643 )
      v13 = -2147483643;
  }
  if ( a6 )
    *a6 = *(_DWORD *)(*((_QWORD *)v12 + 1) + 60LL);
  if ( v13 )
    goto LABEL_13;
LABEL_24:
  if ( v12 )
  {
    if ( *((_QWORD *)v12 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
    else
      ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
  }
  if ( v13 == 259 )
    return 0;
  return v13;
}

```

## disassembly

```asm
0x140015e34  push    rbx
0x140015e36  push    rbp
0x140015e37  push    rsi
0x140015e38  push    rdi
0x140015e39  push    r14
0x140015e3b  sub     rsp, 60h
0x140015e3f  mov     rsi, rcx
0x140015e42  mov     dword ptr [rsp+88h+Event.Event.Header.___u0], 0
0x140015e4a  xorps   xmm0, xmm0
0x140015e4d  lea     rcx, [rsp+88h+Event]; Event
0x140015e52  xor     eax, eax
0x140015e54  mov     ebx, r9d
0x140015e57  movups  xmmword ptr [rsp+88h+Event.Event.Header.SignalState], xmm0
0x140015e5c  mov     dword ptr [rsp+88h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140015e60  mov     r14d, r8d
0x140015e63  mov     ebp, edx
0x140015e65  call    cs:__imp_NdisInitializeEvent
0x140015e6c  nop     dword ptr [rax+rax+00h]
0x140015e71  lea     rdi, Lookaside
0x140015e78  mov     rcx, rdi; Lookaside
0x140015e7b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015e82  nop     dword ptr [rax+rax+00h]
0x140015e87  test    rax, rax
0x140015e8a  jnz     short loc_140015E98
0x140015e8c  xor     edi, edi
0x140015e8e  mov     ebx, 0C000009Ah
0x140015e93  jmp     loc_140015F58
0x140015e98  mov     [rax], rdi
0x140015e9b  mov     r9d, ebx; unsigned int
0x140015e9e  lea     rdi, [rax+10h]
0x140015ea2  mov     dword ptr [rax+8], 72697377h
0x140015ea9  lea     rax, [rsp+88h+Event]
0x140015eae  mov     r8d, r14d; unsigned int
0x140015eb1  mov     [rsp+88h+var_58], rax; void *
0x140015eb6  mov     edx, ebp; unsigned int
0x140015eb8  mov     rax, [rsp+88h+arg_20]
0x140015ec0  mov     rcx, rdi; struct DOT11_NDIS_REQUEST *
0x140015ec3  mov     [rsp+88h+var_68], rax; void *
0x140015ec8  call    ?Dot11BuildNdisMethod@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisMethod(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140015ecd  mov     r8, [rdi+8]; struct _NDIS_OID_REQUEST *
0x140015ed1  lea     rcx, [rsp+88h+var_48]; int *
0x140015ed6  mov     rdx, rsi; struct _ADAPT *
0x140015ed9  mov     [rsp+88h+var_48], 0
0x140015ee1  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140015ee6  mov     ebx, [rsp+88h+var_48]
0x140015eea  cmp     ebx, 103h
0x140015ef0  jnz     short loc_140015F07
0x140015ef2  xor     edx, edx; MsToWait
0x140015ef4  lea     rcx, [rsp+88h+Event]; Event
0x140015ef9  call    cs:__imp_NdisWaitEvent
0x140015f00  nop     dword ptr [rax+rax+00h]
0x140015f05  mov     ebx, [rdi]
0x140015f07  mov     rdx, [rsp+88h+arg_30]
0x140015f0f  test    rdx, rdx
0x140015f12  jz      short loc_140015F3A
0x140015f14  mov     rax, [rdi+8]
0x140015f18  mov     ecx, [rax+44h]
0x140015f1b  mov     [rdx], ecx
0x140015f1d  cmp     ebx, 0C0010014h
0x140015f23  jz      short loc_140015F35
0x140015f25  cmp     ebx, 0C0010016h
0x140015f2b  jz      short loc_140015F35
0x140015f2d  cmp     ebx, 80000005h
0x140015f33  jnz     short loc_140015F3A
0x140015f35  mov     ebx, 80000005h
0x140015f3a  mov     rdx, [rsp+88h+arg_28]
0x140015f42  test    rdx, rdx
0x140015f45  jz      short loc_140015F50
0x140015f47  mov     rax, [rdi+8]
0x140015f4b  mov     ecx, [rax+3Ch]
0x140015f4e  mov     [rdx], ecx
0x140015f50  test    ebx, ebx
0x140015f52  jz      loc_140015FEA
0x140015f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f5f  lea     rax, WPP_GLOBAL_Control
0x140015f66  cmp     rcx, rax
0x140015f69  jz      short loc_140015F9B
0x140015f6b  cmp     byte ptr [rcx+29h], 3
0x140015f6f  jb      short loc_140015F9B
0x140015f71  test    dword ptr [rcx+2Ch], 100h
0x140015f78  jz      short loc_140015F9B
0x140015f7a  mov     rcx, [rcx+18h]
0x140015f7e  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140015f85  mov     edx, 12h
0x140015f8a  mov     dword ptr [rsp+88h+var_60], ebp
0x140015f8e  mov     r9d, ebx
0x140015f91  mov     [rsp+88h+var_68], rsi
0x140015f96  call    WPP_SF_dqD
0x140015f9b  cmp     ebx, 80000005h
0x140015fa1  jnz     short loc_140015FAB
0x140015fa3  cmp     ebp, 0E010179h
0x140015fa9  jz      short loc_140015FEA
0x140015fab  test    cs:byte_1400AF802, 10h
0x140015fb2  jz      short loc_140015FEA
0x140015fb4  test    rsi, rsi
0x140015fb7  jz      short loc_140015FCC
0x140015fb9  mov     rax, [rsi+80h]
0x140015fc0  lea     r8, [rax+1338h]
0x140015fc7  test    rax, rax
0x140015fca  jnz     short loc_140015FD3
0x140015fcc  lea     r8, ?gNull@?1??InterfaceGuidFromAdapter@@YAPEBU_GUID@@PEAU_ADAPT@@@Z@4U2@B; _GUID const `InterfaceGuidFromAdapter(_ADAPT *)'::`2'::gNull
0x140015fd3  mov     dword ptr [rsp+88h+var_60], ebx
0x140015fd7  lea     rdx, CallAdapterSync
0x140015fde  mov     r9, rsi
0x140015fe1  mov     dword ptr [rsp+88h+var_68], ebp
0x140015fe5  call    McTemplateK0pqq_EtwWriteTransfer
0x140015fea  test    rdi, rdi
0x140015fed  jz      short loc_14001601E
0x140015fef  lea     rcx, [rdi-10h]; P
0x140015ff3  mov     rax, [rcx]
0x140015ff6  test    rax, rax
0x140015ff9  jz      short loc_14001600F
0x140015ffb  mov     rdx, rcx; Entry
0x140015ffe  mov     rcx, rax; Lookaside
0x140016001  call    cs:__imp_ExFreeToNPagedLookasideList
0x140016008  nop     dword ptr [rax+rax+00h]
0x14001600d  jmp     short loc_14001601E
0x14001600f  mov     edx, [rcx+8]; Tag
0x140016012  call    cs:__imp_ExFreePoolWithTag
0x140016019  nop     dword ptr [rax+rax+00h]
0x14001601e  xor     ecx, ecx
0x140016020  cmp     ebx, 103h
0x140016026  cmovz   ebx, ecx
0x140016029  mov     eax, ebx
0x14001602b  add     rsp, 60h
0x14001602f  pop     r14
0x140016031  pop     rdi
0x140016032  pop     rsi
0x140016033  pop     rbp
0x140016034  pop     rbx
0x140016035  retn
```
