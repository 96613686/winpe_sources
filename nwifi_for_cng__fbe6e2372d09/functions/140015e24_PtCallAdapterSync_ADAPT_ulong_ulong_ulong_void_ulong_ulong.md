# PtCallAdapterSync(_ADAPT *,ulong,ulong,ulong,void *,ulong *,ulong *)

- ea: `0x140015e24`
- end: `0x140016027`
- name: `?PtCallAdapterSync@@YAHPEAU_ADAPT@@KKKPEAXPEAK2@Z`
- size: `515`
- prototype: `__int64 __fastcall(struct _ADAPT *, unsigned int, unsigned int, unsigned int, void *, unsigned int *, unsigned int *)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140014950`
- `0x140014aec`
- `0x140015440`
- `0x14001588c`
- `0x1400335a0`
- `0x140033a14`
- `0x140058d10`
- `0x140080384`

## callees

- `0x14000adcc`
- `0x140015e24`
- `0x140016030`
- `0x1400160d0`
- `0x1400390dc`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015e6b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015e6b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015ff1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016002`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016002`
- `NDIS!NdisWaitEvent` at `0x140015ee9`
- `NDIS!NdisWaitEvent` at `0x140015ee9`
- `NDIS!NdisInitializeEvent` at `0x140015e55`
- `NDIS!NdisInitializeEvent` at `0x140015e55`

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
    if ( (v13 != -2147483643 || a2 != 234946937) && (byte_1400B2802 & 0x10) != 0 )
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
0x140015e24  push    rbx
0x140015e26  push    rbp
0x140015e27  push    rsi
0x140015e28  push    rdi
0x140015e29  push    r14
0x140015e2b  sub     rsp, 60h
0x140015e2f  mov     rsi, rcx
0x140015e32  mov     dword ptr [rsp+88h+Event.Event.Header.___u0], 0
0x140015e3a  xorps   xmm0, xmm0
0x140015e3d  lea     rcx, [rsp+88h+Event]; Event
0x140015e42  xor     eax, eax
0x140015e44  mov     ebx, r9d
0x140015e47  movups  xmmword ptr [rsp+88h+Event.Event.Header.SignalState], xmm0
0x140015e4c  mov     dword ptr [rsp+88h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140015e50  mov     r14d, r8d
0x140015e53  mov     ebp, edx
0x140015e55  call    cs:__imp_NdisInitializeEvent
0x140015e5c  nop     dword ptr [rax+rax+00h]
0x140015e61  lea     rdi, Lookaside
0x140015e68  mov     rcx, rdi; Lookaside
0x140015e6b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015e72  nop     dword ptr [rax+rax+00h]
0x140015e77  test    rax, rax
0x140015e7a  jnz     short loc_140015E88
0x140015e7c  xor     edi, edi
0x140015e7e  mov     ebx, 0C000009Ah
0x140015e83  jmp     loc_140015F48
0x140015e88  mov     [rax], rdi
0x140015e8b  mov     r9d, ebx; unsigned int
0x140015e8e  lea     rdi, [rax+10h]
0x140015e92  mov     dword ptr [rax+8], 72697377h
0x140015e99  lea     rax, [rsp+88h+Event]
0x140015e9e  mov     r8d, r14d; unsigned int
0x140015ea1  mov     [rsp+88h+var_58], rax; void *
0x140015ea6  mov     edx, ebp; unsigned int
0x140015ea8  mov     rax, [rsp+88h+arg_20]
0x140015eb0  mov     rcx, rdi; struct DOT11_NDIS_REQUEST *
0x140015eb3  mov     [rsp+88h+var_68], rax; void *
0x140015eb8  call    ?Dot11BuildNdisMethod@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisMethod(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140015ebd  mov     r8, [rdi+8]; struct _NDIS_OID_REQUEST *
0x140015ec1  lea     rcx, [rsp+88h+var_48]; int *
0x140015ec6  mov     rdx, rsi; struct _ADAPT *
0x140015ec9  mov     [rsp+88h+var_48], 0
0x140015ed1  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140015ed6  mov     ebx, [rsp+88h+var_48]
0x140015eda  cmp     ebx, 103h
0x140015ee0  jnz     short loc_140015EF7
0x140015ee2  xor     edx, edx; MsToWait
0x140015ee4  lea     rcx, [rsp+88h+Event]; Event
0x140015ee9  call    cs:__imp_NdisWaitEvent
0x140015ef0  nop     dword ptr [rax+rax+00h]
0x140015ef5  mov     ebx, [rdi]
0x140015ef7  mov     rdx, [rsp+88h+arg_30]
0x140015eff  test    rdx, rdx
0x140015f02  jz      short loc_140015F2A
0x140015f04  mov     rax, [rdi+8]
0x140015f08  mov     ecx, [rax+44h]
0x140015f0b  mov     [rdx], ecx
0x140015f0d  cmp     ebx, 0C0010014h
0x140015f13  jz      short loc_140015F25
0x140015f15  cmp     ebx, 0C0010016h
0x140015f1b  jz      short loc_140015F25
0x140015f1d  cmp     ebx, 80000005h
0x140015f23  jnz     short loc_140015F2A
0x140015f25  mov     ebx, 80000005h
0x140015f2a  mov     rdx, [rsp+88h+arg_28]
0x140015f32  test    rdx, rdx
0x140015f35  jz      short loc_140015F40
0x140015f37  mov     rax, [rdi+8]
0x140015f3b  mov     ecx, [rax+3Ch]
0x140015f3e  mov     [rdx], ecx
0x140015f40  test    ebx, ebx
0x140015f42  jz      loc_140015FDA
0x140015f48  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f4f  lea     rax, WPP_GLOBAL_Control
0x140015f56  cmp     rcx, rax
0x140015f59  jz      short loc_140015F8B
0x140015f5b  cmp     byte ptr [rcx+29h], 3
0x140015f5f  jb      short loc_140015F8B
0x140015f61  test    dword ptr [rcx+2Ch], 100h
0x140015f68  jz      short loc_140015F8B
0x140015f6a  mov     rcx, [rcx+18h]
0x140015f6e  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140015f75  mov     edx, 12h
0x140015f7a  mov     dword ptr [rsp+88h+var_60], ebp
0x140015f7e  mov     r9d, ebx
0x140015f81  mov     [rsp+88h+var_68], rsi
0x140015f86  call    WPP_SF_dqD
0x140015f8b  cmp     ebx, 80000005h
0x140015f91  jnz     short loc_140015F9B
0x140015f93  cmp     ebp, 0E010179h
0x140015f99  jz      short loc_140015FDA
0x140015f9b  test    cs:byte_1400B2802, 10h
0x140015fa2  jz      short loc_140015FDA
0x140015fa4  test    rsi, rsi
0x140015fa7  jz      short loc_140015FBC
0x140015fa9  mov     rax, [rsi+80h]
0x140015fb0  lea     r8, [rax+1338h]
0x140015fb7  test    rax, rax
0x140015fba  jnz     short loc_140015FC3
0x140015fbc  lea     r8, ?gNull@?1??InterfaceGuidFromAdapter@@YAPEBU_GUID@@PEAU_ADAPT@@@Z@4U2@B; _GUID const `InterfaceGuidFromAdapter(_ADAPT *)'::`2'::gNull
0x140015fc3  mov     dword ptr [rsp+88h+var_60], ebx
0x140015fc7  lea     rdx, CallAdapterSync
0x140015fce  mov     r9, rsi
0x140015fd1  mov     dword ptr [rsp+88h+var_68], ebp
0x140015fd5  call    McTemplateK0pqq_EtwWriteTransfer
0x140015fda  test    rdi, rdi
0x140015fdd  jz      short loc_14001600E
0x140015fdf  lea     rcx, [rdi-10h]; P
0x140015fe3  mov     rax, [rcx]
0x140015fe6  test    rax, rax
0x140015fe9  jz      short loc_140015FFF
0x140015feb  mov     rdx, rcx; Entry
0x140015fee  mov     rcx, rax; Lookaside
0x140015ff1  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015ff8  nop     dword ptr [rax+rax+00h]
0x140015ffd  jmp     short loc_14001600E
0x140015fff  mov     edx, [rcx+8]; Tag
0x140016002  call    cs:__imp_ExFreePoolWithTag
0x140016009  nop     dword ptr [rax+rax+00h]
0x14001600e  xor     ecx, ecx
0x140016010  cmp     ebx, 103h
0x140016016  cmovz   ebx, ecx
0x140016019  mov     eax, ebx
0x14001601b  add     rsp, 60h
0x14001601f  pop     r14
0x140016021  pop     rdi
0x140016022  pop     rsi
0x140016023  pop     rbp
0x140016024  pop     rbx
0x140016025  retn
```
