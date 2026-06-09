# PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)

- ea: `0x140015b0c`
- end: `0x140015e1c`
- name: `?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z`
- size: `784`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `23`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013c7c`
- `0x1400143d8`
- `0x140014658`
- `0x140014b80`
- `0x140014dd0`
- `0x140033758`
- `0x1400338cc`
- `0x140038930`
- `0x140038be8`
- `0x14003d11c`
- `0x14003d2bc`
- `0x140062004`
- `0x1400658d4`
- `0x140065928`
- `0x14006bb20`
- `0x14006bb90`
- `0x14006cdb0`
- `0x14006cfb0`
- `0x140072ee0`
- `0x14007c510`
- `0x140088630`
- `0x1400891d0`
- `0x140089820`

## callees

- `0x14000adcc`
- `0x140015b0c`
- `0x1400160d0`
- `0x140039070`
- `0x1400390dc`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015b72`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015b72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015cf8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015de4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015cf8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015df5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015df5`
- `NDIS!NdisResetEvent` at `0x140015d1e`
- `NDIS!NdisResetEvent` at `0x140015d1e`
- `NDIS!NdisWaitEvent` at `0x140015c38`
- `NDIS!NdisWaitEvent` at `0x140015c38`
- `NDIS!NdisInitializeEvent` at `0x140015b4c`
- `NDIS!NdisInitializeEvent` at `0x140015b4c`
- `NDIS!NdisMSleep` at `0x140015ce1`
- `NDIS!NdisMSleep` at `0x140015ce1`

## pseudocode

```c
__int64 __fastcall PtQueryAdapterSyncEx(
        struct _ADAPT *a1,
        unsigned int a2,
        void *a3,
        int a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int v7; // r15d
  char *v9; // rax
  ULONG *v10; // r14
  char *v11; // rdi
  _BYTE *v12; // rbx
  struct _NDIS_OID_REQUEST *v13; // r8
  unsigned int v14; // ebx
  int v15; // ecx
  _VELAN *pActiveVElan; // rax
  GUID *v17; // r8
  int v19; // [rsp+30h] [rbp-58h] BYREF
  _NDIS_EVENT Event; // [rsp+38h] [rbp-50h] BYREF

  memset(&Event, 0, sizeof(Event));
  v7 = 0;
  NdisInitializeEvent(&Event);
  while ( 1 )
  {
    v9 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
    v10 = (ULONG *)v9;
    if ( !v9 )
    {
      v11 = 0;
      v14 = -1073741670;
      goto LABEL_25;
    }
    v11 = v9 + 16;
    *(_QWORD *)v9 = &Lookaside;
    *((_DWORD *)v9 + 2) = 1919513463;
    v12 = v9 + 32;
    *((_QWORD *)v9 + 3) = v9 + 32;
    *((_QWORD *)v9 + 35) = 0;
    memset(v9 + 32, 0, 0xF8u);
    *((_QWORD *)v11 + 7) = a3;
    *((_DWORD *)v11 + 16) = a4;
    *((_DWORD *)v11 + 5) = 0;
    *v12 = -106;
    v11[17] = 1;
    *((_WORD *)v11 + 9) = 236;
    *((_QWORD *)v11 + 29) = v11;
    *((_DWORD *)v11 + 12) = a2;
    *((_QWORD *)v11 + 36) = PtCompleteBlockingRequest;
    *(_DWORD *)v11 = 0;
    *((_QWORD *)v11 + 35) = 0;
    *((_QWORD *)v11 + 34) = &Event;
    v13 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)v11 + 1);
    v19 = 0;
    Dot11Request(&v19, a1, v13);
    v14 = v19;
    if ( v19 == 259 )
    {
      NdisWaitEvent(&Event, 0);
      v14 = *(_DWORD *)v11;
    }
    if ( a6 )
    {
      *a6 = *(_DWORD *)(*((_QWORD *)v11 + 1) + 56LL);
      if ( v14 == -1073676268 || v14 == -1073676266 || v14 == -2147483643 )
        v14 = -2147483643;
    }
    if ( a5 )
      *a5 = *(_DWORD *)(*((_QWORD *)v11 + 1) + 52LL);
    if ( v14 != -1073676271 )
      break;
    if ( v7 >= 0x32 )
      goto LABEL_26;
    ++v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_Dqd(WPP_GLOBAL_Control->AttachedDevice, 12, 3221291025LL, a2, a1, -1073676271);
    }
    NdisMSleep(0x186A0u);
    if ( *(_QWORD *)v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, v10);
    else
      ExFreePoolWithTag(v10, v10[2]);
    NdisResetEvent(&Event);
  }
  if ( !v14 )
    goto LABEL_35;
LABEL_25:
  if ( v14 == -2147483643 )
    goto LABEL_35;
LABEL_26:
  v15 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    WPP_SF_dqD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids, v14, a1, a2);
  }
  if ( (byte_1400B2802 & 8) != 0 )
  {
    if ( !a1 || (pActiveVElan = a1->pActiveVElan, LODWORD(v17) = (_DWORD)pActiveVElan + 4920, !pActiveVElan) )
      v17 = &`InterfaceGuidFromAdapter'::`2'::gNull;
    McTemplateK0pqq_EtwWriteTransfer(v15, (unsigned int)QueryAdapterSync, (_DWORD)v17, (_DWORD)a1, a2, v14);
  }
LABEL_35:
  if ( v11 )
  {
    if ( *((_QWORD *)v11 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 16);
    else
      ExFreePoolWithTag(v11 - 16, *((_DWORD *)v11 - 2));
  }
  return v14;
}

```

## disassembly

```asm
0x140015b0c  mov     rax, rsp
0x140015b0f  mov     [rax+8], rbx
0x140015b13  mov     [rax+20h], r9d
0x140015b17  mov     [rax+18h], r8
0x140015b1b  push    rbp
0x140015b1c  push    rsi
0x140015b1d  push    rdi
0x140015b1e  push    r12
0x140015b20  push    r13
0x140015b22  push    r14
0x140015b24  push    r15
0x140015b26  sub     rsp, 50h
0x140015b2a  mov     dword ptr [rax-50h], 0
0x140015b31  mov     rsi, rcx
0x140015b34  xor     eax, eax
0x140015b36  lea     rcx, [rsp+88h+Event]; Event
0x140015b3b  xorps   xmm0, xmm0
0x140015b3e  mov     dword ptr [rsp+88h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140015b42  xor     r15d, r15d
0x140015b45  mov     ebp, edx
0x140015b47  movups  xmmword ptr [rsp+88h+Event.Event.Header.SignalState], xmm0
0x140015b4c  call    cs:__imp_NdisInitializeEvent
0x140015b53  nop     dword ptr [rax+rax+00h]
0x140015b58  mov     r12, [rsp+88h+arg_28]
0x140015b60  mov     r13, [rsp+88h+arg_20]
0x140015b68  lea     rbx, Lookaside
0x140015b6f  mov     rcx, rbx; Lookaside
0x140015b72  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015b79  nop     dword ptr [rax+rax+00h]
0x140015b7e  mov     r14, rax
0x140015b81  test    rax, rax
0x140015b84  jz      loc_140015D38
0x140015b8a  lea     rdi, [rax+10h]
0x140015b8e  mov     [rax], rbx
0x140015b91  mov     dword ptr [rax+8], 72697377h
0x140015b98  lea     rbx, [rdi+10h]
0x140015b9c  mov     rcx, rbx; void *
0x140015b9f  mov     [rdi+8], rbx
0x140015ba3  xor     edx, edx; Val
0x140015ba5  mov     qword ptr [rdi+108h], 0
0x140015bb0  mov     r8d, 0F8h; Size
0x140015bb6  call    memset
0x140015bbb  mov     rax, [rsp+88h+arg_10]
0x140015bc3  xor     ecx, ecx
0x140015bc5  mov     [rdi+38h], rax
0x140015bc9  mov     rdx, rsi; struct _ADAPT *
0x140015bcc  mov     eax, [rsp+88h+arg_18]
0x140015bd3  mov     [rdi+40h], eax
0x140015bd6  lea     rax, ?PtCompleteBlockingRequest@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; PtCompleteBlockingRequest(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140015bdd  mov     [rdi+14h], ecx
0x140015be0  mov     byte ptr [rbx], 96h
0x140015be3  mov     byte ptr [rdi+11h], 1
0x140015be7  mov     word ptr [rdi+12h], 0ECh
0x140015bed  mov     [rdi+0E8h], rdi
0x140015bf4  mov     [rdi+30h], ebp
0x140015bf7  mov     [rdi+120h], rax
0x140015bfe  lea     rax, [rsp+88h+Event]
0x140015c03  mov     [rdi], ecx
0x140015c05  mov     [rdi+118h], rcx
0x140015c0c  mov     [rdi+110h], rax
0x140015c13  mov     r8, [rdi+8]; struct _NDIS_OID_REQUEST *
0x140015c17  mov     [rsp+88h+var_58], ecx
0x140015c1b  lea     rcx, [rsp+88h+var_58]; int *
0x140015c20  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140015c25  mov     ebx, [rsp+88h+var_58]
0x140015c29  cmp     ebx, 103h
0x140015c2f  jnz     short loc_140015C46
0x140015c31  xor     edx, edx; MsToWait
0x140015c33  lea     rcx, [rsp+88h+Event]; Event
0x140015c38  call    cs:__imp_NdisWaitEvent
0x140015c3f  nop     dword ptr [rax+rax+00h]
0x140015c44  mov     ebx, [rdi]
0x140015c46  test    r12, r12
0x140015c49  jz      short loc_140015C73
0x140015c4b  mov     rax, [rdi+8]
0x140015c4f  mov     ecx, [rax+38h]
0x140015c52  mov     [r12], ecx
0x140015c56  cmp     ebx, 0C0010014h
0x140015c5c  jz      short loc_140015C6E
0x140015c5e  cmp     ebx, 0C0010016h
0x140015c64  jz      short loc_140015C6E
0x140015c66  cmp     ebx, 80000005h
0x140015c6c  jnz     short loc_140015C73
0x140015c6e  mov     ebx, 80000005h
0x140015c73  test    r13, r13
0x140015c76  jz      short loc_140015C83
0x140015c78  mov     rax, [rdi+8]
0x140015c7c  mov     ecx, [rax+34h]
0x140015c7f  mov     [r13+0], ecx
0x140015c83  mov     r8d, 0C0010011h
0x140015c89  cmp     ebx, r8d
0x140015c8c  jnz     loc_140015D2F
0x140015c92  cmp     r15d, 32h ; '2'
0x140015c96  jnb     loc_140015D4B
0x140015c9c  inc     r15d
0x140015c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ca6  lea     rax, WPP_GLOBAL_Control
0x140015cad  cmp     rcx, rax
0x140015cb0  jz      short loc_140015CDC
0x140015cb2  cmp     byte ptr [rcx+29h], 3
0x140015cb6  jb      short loc_140015CDC
0x140015cb8  test    dword ptr [rcx+2Ch], 100h
0x140015cbf  jz      short loc_140015CDC
0x140015cc1  mov     rcx, [rcx+18h]
0x140015cc5  mov     edx, 0Ch
0x140015cca  mov     [rsp+88h+var_60], r8d
0x140015ccf  mov     r9d, ebp
0x140015cd2  mov     [rsp+88h+var_68], rsi
0x140015cd7  call    WPP_SF_Dqd
0x140015cdc  mov     ecx, 186A0h; MicrosecondsToSleep
0x140015ce1  call    cs:__imp_NdisMSleep
0x140015ce8  nop     dword ptr [rax+rax+00h]
0x140015ced  mov     rcx, [r14]; Lookaside
0x140015cf0  test    rcx, rcx
0x140015cf3  jz      short loc_140015D06
0x140015cf5  mov     rdx, r14; Entry
0x140015cf8  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015cff  nop     dword ptr [rax+rax+00h]
0x140015d04  jmp     short loc_140015D19
0x140015d06  mov     edx, [r14+8]; Tag
0x140015d0a  mov     rcx, r14; P
0x140015d0d  call    cs:__imp_ExFreePoolWithTag
0x140015d14  nop     dword ptr [rax+rax+00h]
0x140015d19  lea     rcx, [rsp+88h+Event]; Event
0x140015d1e  call    cs:__imp_NdisResetEvent
0x140015d25  nop     dword ptr [rax+rax+00h]
0x140015d2a  jmp     loc_140015B68
0x140015d2f  test    ebx, ebx
0x140015d31  jnz     short loc_140015D3F
0x140015d33  jmp     loc_140015DCD
0x140015d38  xor     edi, edi
0x140015d3a  mov     ebx, 0C000009Ah
0x140015d3f  cmp     ebx, 80000005h
0x140015d45  jz      loc_140015DCD
0x140015d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d52  lea     rax, WPP_GLOBAL_Control
0x140015d59  cmp     rcx, rax
0x140015d5c  jz      short loc_140015D8E
0x140015d5e  cmp     byte ptr [rcx+29h], 3
0x140015d62  jb      short loc_140015D8E
0x140015d64  test    dword ptr [rcx+2Ch], 100h
0x140015d6b  jz      short loc_140015D8E
0x140015d6d  mov     rcx, [rcx+18h]
0x140015d71  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140015d78  mov     edx, 0Dh
0x140015d7d  mov     [rsp+88h+var_60], ebp
0x140015d81  mov     r9d, ebx
0x140015d84  mov     [rsp+88h+var_68], rsi
0x140015d89  call    WPP_SF_dqD
0x140015d8e  test    cs:byte_1400B2802, 8
0x140015d95  jz      short loc_140015DCD
0x140015d97  test    rsi, rsi
0x140015d9a  jz      short loc_140015DAF
0x140015d9c  mov     rax, [rsi+80h]
0x140015da3  lea     r8, [rax+1338h]
0x140015daa  test    rax, rax
0x140015dad  jnz     short loc_140015DB6
0x140015daf  lea     r8, ?gNull@?1??InterfaceGuidFromAdapter@@YAPEBU_GUID@@PEAU_ADAPT@@@Z@4U2@B; _GUID const `InterfaceGuidFromAdapter(_ADAPT *)'::`2'::gNull
0x140015db6  mov     [rsp+88h+var_60], ebx
0x140015dba  lea     rdx, QueryAdapterSync
0x140015dc1  mov     r9, rsi
0x140015dc4  mov     dword ptr [rsp+88h+var_68], ebp
0x140015dc8  call    McTemplateK0pqq_EtwWriteTransfer
0x140015dcd  test    rdi, rdi
0x140015dd0  jz      short loc_140015E01
0x140015dd2  lea     rcx, [rdi-10h]; P
0x140015dd6  mov     rax, [rcx]
0x140015dd9  test    rax, rax
0x140015ddc  jz      short loc_140015DF2
0x140015dde  mov     rdx, rcx; Entry
0x140015de1  mov     rcx, rax; Lookaside
0x140015de4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015deb  nop     dword ptr [rax+rax+00h]
0x140015df0  jmp     short loc_140015E01
0x140015df2  mov     edx, [rcx+8]; Tag
0x140015df5  call    cs:__imp_ExFreePoolWithTag
0x140015dfc  nop     dword ptr [rax+rax+00h]
0x140015e01  mov     eax, ebx
0x140015e03  mov     rbx, [rsp+88h+arg_0]
0x140015e0b  add     rsp, 50h
0x140015e0f  pop     r15
0x140015e11  pop     r14
0x140015e13  pop     r13
0x140015e15  pop     r12
0x140015e17  pop     rdi
0x140015e18  pop     rsi
0x140015e19  pop     rbp
0x140015e1a  retn
```
