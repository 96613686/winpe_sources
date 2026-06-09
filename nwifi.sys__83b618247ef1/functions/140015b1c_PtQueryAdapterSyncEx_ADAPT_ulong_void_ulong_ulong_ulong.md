# PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)

- ea: `0x140015b1c`
- end: `0x140015e2c`
- name: `?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z`
- size: `784`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `23`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013c8c`
- `0x1400143e8`
- `0x140014668`
- `0x140014b90`
- `0x140014de0`
- `0x140033538`
- `0x1400336ac`
- `0x140038710`
- `0x1400389c8`
- `0x14003cefc`
- `0x14003d09c`
- `0x1400607d4`
- `0x1400640a4`
- `0x1400640f8`
- `0x14006a2f0`
- `0x14006a360`
- `0x14006b580`
- `0x14006b780`
- `0x1400716b0`
- `0x14007ace0`
- `0x140086e00`
- `0x1400879a0`
- `0x140087ff0`

## callees

- `0x14000addc`
- `0x140015b1c`
- `0x1400160e0`
- `0x140038e50`
- `0x140038ebc`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015b82`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015b82`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015d08`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015df4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015d08`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015df4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015e05`
- `NDIS!NdisResetEvent` at `0x140015d2e`
- `NDIS!NdisResetEvent` at `0x140015d2e`
- `NDIS!NdisWaitEvent` at `0x140015c48`
- `NDIS!NdisWaitEvent` at `0x140015c48`
- `NDIS!NdisInitializeEvent` at `0x140015b5c`
- `NDIS!NdisInitializeEvent` at `0x140015b5c`
- `NDIS!NdisMSleep` at `0x140015cf1`
- `NDIS!NdisMSleep` at `0x140015cf1`

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
  if ( (byte_1400AF802 & 8) != 0 )
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
0x140015b1c  mov     rax, rsp
0x140015b1f  mov     [rax+8], rbx
0x140015b23  mov     [rax+20h], r9d
0x140015b27  mov     [rax+18h], r8
0x140015b2b  push    rbp
0x140015b2c  push    rsi
0x140015b2d  push    rdi
0x140015b2e  push    r12
0x140015b30  push    r13
0x140015b32  push    r14
0x140015b34  push    r15
0x140015b36  sub     rsp, 50h
0x140015b3a  mov     dword ptr [rax-50h], 0
0x140015b41  mov     rsi, rcx
0x140015b44  xor     eax, eax
0x140015b46  lea     rcx, [rsp+88h+Event]; Event
0x140015b4b  xorps   xmm0, xmm0
0x140015b4e  mov     dword ptr [rsp+88h+Event.Event.Header.WaitListHead.Blink+4], eax
0x140015b52  xor     r15d, r15d
0x140015b55  mov     ebp, edx
0x140015b57  movups  xmmword ptr [rsp+88h+Event.Event.Header.SignalState], xmm0
0x140015b5c  call    cs:__imp_NdisInitializeEvent
0x140015b63  nop     dword ptr [rax+rax+00h]
0x140015b68  mov     r12, [rsp+88h+arg_28]
0x140015b70  mov     r13, [rsp+88h+arg_20]
0x140015b78  lea     rbx, Lookaside
0x140015b7f  mov     rcx, rbx; Lookaside
0x140015b82  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015b89  nop     dword ptr [rax+rax+00h]
0x140015b8e  mov     r14, rax
0x140015b91  test    rax, rax
0x140015b94  jz      loc_140015D48
0x140015b9a  lea     rdi, [rax+10h]
0x140015b9e  mov     [rax], rbx
0x140015ba1  mov     dword ptr [rax+8], 72697377h
0x140015ba8  lea     rbx, [rdi+10h]
0x140015bac  mov     rcx, rbx; void *
0x140015baf  mov     [rdi+8], rbx
0x140015bb3  xor     edx, edx; Val
0x140015bb5  mov     qword ptr [rdi+108h], 0
0x140015bc0  mov     r8d, 0F8h; Size
0x140015bc6  call    memset
0x140015bcb  mov     rax, [rsp+88h+arg_10]
0x140015bd3  xor     ecx, ecx
0x140015bd5  mov     [rdi+38h], rax
0x140015bd9  mov     rdx, rsi; struct _ADAPT *
0x140015bdc  mov     eax, [rsp+88h+arg_18]
0x140015be3  mov     [rdi+40h], eax
0x140015be6  lea     rax, ?PtCompleteBlockingRequest@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; PtCompleteBlockingRequest(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140015bed  mov     [rdi+14h], ecx
0x140015bf0  mov     byte ptr [rbx], 96h
0x140015bf3  mov     byte ptr [rdi+11h], 1
0x140015bf7  mov     word ptr [rdi+12h], 0ECh
0x140015bfd  mov     [rdi+0E8h], rdi
0x140015c04  mov     [rdi+30h], ebp
0x140015c07  mov     [rdi+120h], rax
0x140015c0e  lea     rax, [rsp+88h+Event]
0x140015c13  mov     [rdi], ecx
0x140015c15  mov     [rdi+118h], rcx
0x140015c1c  mov     [rdi+110h], rax
0x140015c23  mov     r8, [rdi+8]; struct _NDIS_OID_REQUEST *
0x140015c27  mov     [rsp+88h+var_58], ecx
0x140015c2b  lea     rcx, [rsp+88h+var_58]; int *
0x140015c30  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140015c35  mov     ebx, [rsp+88h+var_58]
0x140015c39  cmp     ebx, 103h
0x140015c3f  jnz     short loc_140015C56
0x140015c41  xor     edx, edx; MsToWait
0x140015c43  lea     rcx, [rsp+88h+Event]; Event
0x140015c48  call    cs:__imp_NdisWaitEvent
0x140015c4f  nop     dword ptr [rax+rax+00h]
0x140015c54  mov     ebx, [rdi]
0x140015c56  test    r12, r12
0x140015c59  jz      short loc_140015C83
0x140015c5b  mov     rax, [rdi+8]
0x140015c5f  mov     ecx, [rax+38h]
0x140015c62  mov     [r12], ecx
0x140015c66  cmp     ebx, 0C0010014h
0x140015c6c  jz      short loc_140015C7E
0x140015c6e  cmp     ebx, 0C0010016h
0x140015c74  jz      short loc_140015C7E
0x140015c76  cmp     ebx, 80000005h
0x140015c7c  jnz     short loc_140015C83
0x140015c7e  mov     ebx, 80000005h
0x140015c83  test    r13, r13
0x140015c86  jz      short loc_140015C93
0x140015c88  mov     rax, [rdi+8]
0x140015c8c  mov     ecx, [rax+34h]
0x140015c8f  mov     [r13+0], ecx
0x140015c93  mov     r8d, 0C0010011h
0x140015c99  cmp     ebx, r8d
0x140015c9c  jnz     loc_140015D3F
0x140015ca2  cmp     r15d, 32h ; '2'
0x140015ca6  jnb     loc_140015D5B
0x140015cac  inc     r15d
0x140015caf  mov     rcx, cs:WPP_GLOBAL_Control
0x140015cb6  lea     rax, WPP_GLOBAL_Control
0x140015cbd  cmp     rcx, rax
0x140015cc0  jz      short loc_140015CEC
0x140015cc2  cmp     byte ptr [rcx+29h], 3
0x140015cc6  jb      short loc_140015CEC
0x140015cc8  test    dword ptr [rcx+2Ch], 100h
0x140015ccf  jz      short loc_140015CEC
0x140015cd1  mov     rcx, [rcx+18h]
0x140015cd5  mov     edx, 0Ch
0x140015cda  mov     [rsp+88h+var_60], r8d
0x140015cdf  mov     r9d, ebp
0x140015ce2  mov     [rsp+88h+var_68], rsi
0x140015ce7  call    WPP_SF_Dqd
0x140015cec  mov     ecx, 186A0h; MicrosecondsToSleep
0x140015cf1  call    cs:__imp_NdisMSleep
0x140015cf8  nop     dword ptr [rax+rax+00h]
0x140015cfd  mov     rcx, [r14]; Lookaside
0x140015d00  test    rcx, rcx
0x140015d03  jz      short loc_140015D16
0x140015d05  mov     rdx, r14; Entry
0x140015d08  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015d0f  nop     dword ptr [rax+rax+00h]
0x140015d14  jmp     short loc_140015D29
0x140015d16  mov     edx, [r14+8]; Tag
0x140015d1a  mov     rcx, r14; P
0x140015d1d  call    cs:__imp_ExFreePoolWithTag
0x140015d24  nop     dword ptr [rax+rax+00h]
0x140015d29  lea     rcx, [rsp+88h+Event]; Event
0x140015d2e  call    cs:__imp_NdisResetEvent
0x140015d35  nop     dword ptr [rax+rax+00h]
0x140015d3a  jmp     loc_140015B78
0x140015d3f  test    ebx, ebx
0x140015d41  jnz     short loc_140015D4F
0x140015d43  jmp     loc_140015DDD
0x140015d48  xor     edi, edi
0x140015d4a  mov     ebx, 0C000009Ah
0x140015d4f  cmp     ebx, 80000005h
0x140015d55  jz      loc_140015DDD
0x140015d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d62  lea     rax, WPP_GLOBAL_Control
0x140015d69  cmp     rcx, rax
0x140015d6c  jz      short loc_140015D9E
0x140015d6e  cmp     byte ptr [rcx+29h], 3
0x140015d72  jb      short loc_140015D9E
0x140015d74  test    dword ptr [rcx+2Ch], 100h
0x140015d7b  jz      short loc_140015D9E
0x140015d7d  mov     rcx, [rcx+18h]
0x140015d81  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140015d88  mov     edx, 0Dh
0x140015d8d  mov     [rsp+88h+var_60], ebp
0x140015d91  mov     r9d, ebx
0x140015d94  mov     [rsp+88h+var_68], rsi
0x140015d99  call    WPP_SF_dqD
0x140015d9e  test    cs:byte_1400AF802, 8
0x140015da5  jz      short loc_140015DDD
0x140015da7  test    rsi, rsi
0x140015daa  jz      short loc_140015DBF
0x140015dac  mov     rax, [rsi+80h]
0x140015db3  lea     r8, [rax+1338h]
0x140015dba  test    rax, rax
0x140015dbd  jnz     short loc_140015DC6
0x140015dbf  lea     r8, ?gNull@?1??InterfaceGuidFromAdapter@@YAPEBU_GUID@@PEAU_ADAPT@@@Z@4U2@B; _GUID const `InterfaceGuidFromAdapter(_ADAPT *)'::`2'::gNull
0x140015dc6  mov     [rsp+88h+var_60], ebx
0x140015dca  lea     rdx, QueryAdapterSync
0x140015dd1  mov     r9, rsi
0x140015dd4  mov     dword ptr [rsp+88h+var_68], ebp
0x140015dd8  call    McTemplateK0pqq_EtwWriteTransfer
0x140015ddd  test    rdi, rdi
0x140015de0  jz      short loc_140015E11
0x140015de2  lea     rcx, [rdi-10h]; P
0x140015de6  mov     rax, [rcx]
0x140015de9  test    rax, rax
0x140015dec  jz      short loc_140015E02
0x140015dee  mov     rdx, rcx; Entry
0x140015df1  mov     rcx, rax; Lookaside
0x140015df4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015dfb  nop     dword ptr [rax+rax+00h]
0x140015e00  jmp     short loc_140015E11
0x140015e02  mov     edx, [rcx+8]; Tag
0x140015e05  call    cs:__imp_ExFreePoolWithTag
0x140015e0c  nop     dword ptr [rax+rax+00h]
0x140015e11  mov     eax, ebx
0x140015e13  mov     rbx, [rsp+88h+arg_0]
0x140015e1b  add     rsp, 50h
0x140015e1f  pop     r15
0x140015e21  pop     r14
0x140015e23  pop     r13
0x140015e25  pop     r12
0x140015e27  pop     rdi
0x140015e28  pop     rsi
0x140015e29  pop     rbp
0x140015e2a  retn
```
