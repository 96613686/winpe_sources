# DrEnumerateConnections

- ea: `0x140019220`
- end: `0x14001971a`
- name: `DrEnumerateConnections`
- size: `1274`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x14000327c`
- `0x140003ee0`
- `0x1400064b0`
- `0x140011bfc`
- `0x140011c60`
- `0x140011ce4`
- `0x1400189b8`
- `0x140019220`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400193ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400193ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001948e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001948e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400196ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400196ad`
- `ntoskrnl!IoGetRequestorSessionId` at `0x1400192c8`
- `ntoskrnl!IoGetRequestorSessionId` at `0x1400192c8`
- `ntoskrnl!ProbeForWrite` at `0x140019333`
- `ntoskrnl!ProbeForWrite` at `0x140019349`
- `ntoskrnl!ProbeForWrite` at `0x140019333`
- `ntoskrnl!ProbeForWrite` at `0x140019349`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400194ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400194ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400196a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400196a1`
- `rdbss!RxPrefixTableEndLookup` at `0x14001967c`
- `rdbss!RxPrefixTableEndLookup` at `0x14001967c`
- `rdbss!RxPrefixTableLookupNextObject` at `0x1400195c5`
- `rdbss!RxPrefixTableLookupNextObject` at `0x1400195c5`
- `rdbss!RxPrefixTableLookupFirstObject` at `0x1400194ea`
- `rdbss!RxPrefixTableLookupFirstObject` at `0x1400194ea`

## pseudocode

```c
__int64 __fastcall DrEnumerateConnections(__int64 a1)
{
  char *v1; // r15
  SIZE_T v2; // rsi
  __int64 v3; // r12
  IRP *v4; // rax
  _DWORD *v5; // r13
  NTSTATUS RequestorSessionId; // edi
  char *v7; // r14
  char *Pool2; // rax
  unsigned int *v10; // rcx
  unsigned int ULongFromUser; // eax
  int v12; // eax
  unsigned int v13; // r13d
  __int64 i; // rax
  __int64 v15; // r15
  struct _RX_CONTEXT *v16; // rcx
  _DWORD *v17; // r15
  _DWORD *v18; // rcx
  char v19; // [rsp+40h] [rbp-B8h]
  char v20; // [rsp+41h] [rbp-B7h]
  int v21; // [rsp+4Ch] [rbp-ACh]
  __int64 v22; // [rsp+50h] [rbp-A8h]
  unsigned int v23[2]; // [rsp+58h] [rbp-A0h] BYREF
  char *v24; // [rsp+60h] [rbp-98h]
  _DWORD *v25; // [rsp+68h] [rbp-90h]
  char *v26; // [rsp+70h] [rbp-88h]
  char *v27; // [rsp+78h] [rbp-80h]
  SIZE_T v28; // [rsp+80h] [rbp-78h]
  __int64 v29; // [rsp+88h] [rbp-70h]
  _BYTE v30[104]; // [rsp+90h] [rbp-68h] BYREF
  unsigned int Length; // [rsp+100h] [rbp+8h]
  ULONG pSessionId; // [rsp+108h] [rbp+10h] BYREF
  char *v33; // [rsp+110h] [rbp+18h] BYREF
  char *v34; // [rsp+118h] [rbp+20h] BYREF

  v1 = *(char **)(a1 + 560);
  v26 = v1;
  v2 = *(unsigned int *)(a1 + 572);
  v34 = v1;
  v33 = &v1[v2];
  pSessionId = 0;
  memset(v30, 0, 48);
  if ( !(_DWORD)v2 )
  {
    v34 = 0;
    v33 = 0;
  }
  if ( (*(_BYTE *)(a1 + 540) & 3) != 3 )
    return 3221225488LL;
  v3 = a1 + 40;
  v4 = *(IRP **)(a1 + 40);
  if ( v4->MdlAddress )
    return 3221225488LL;
  v5 = *(_DWORD **)(a1 + 552);
  v25 = v5;
  Length = *(_DWORD *)(a1 + 568);
  RequestorSessionId = IoGetRequestorSessionId(v4, &pSessionId);
  if ( RequestorSessionId < 0 )
    return 3221225488LL;
  if ( !v5 || !v1 )
    return 3221225485LL;
  v27 = v1;
  v28 = v2;
  v29 = v3;
  v7 = 0;
  v24 = 0;
  v20 = 0;
  v19 = 0;
  if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
  {
    ProbeForWrite(v5, Length, 1u);
    ProbeForWrite(v1, v2, 1u);
    if ( (unsigned int)v2 > 0xA0000 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
          (unsigned int)v2);
      return 3221225485LL;
    }
    if ( (_DWORD)v2 )
    {
      Pool2 = (char *)ExAllocatePool2(64, v2, 1917088324);
      v7 = Pool2;
      v24 = Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      v34 = Pool2;
      v33 = &Pool2[v2];
    }
  }
  if ( Length >= 0x18 )
  {
    *(_QWORD *)v23 = 0;
    if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
      RtlReadULongFromUser(v5);
    v10 = v5 + 5;
    if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
      ULongFromUser = RtlReadULongFromUser(v10);
    else
      ULongFromUser = *v10;
    v23[1] = ULongFromUser;
    if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
      v12 = RtlReadULongFromUser(v5 + 1);
    else
      v12 = v5[1];
    v21 = v12;
    if ( v12 == pSessionId )
    {
      v13 = 0;
      v22 = 0;
      v23[0] = 0;
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24), 1u);
      v20 = 1;
      v19 = 1;
      for ( i = RxPrefixTableLookupFirstObject(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData, 0, 0, 60178, v30);
            ;
            i = RxPrefixTableLookupNextObject(v30) )
      {
        v15 = i;
        if ( !i )
          break;
        v16 = (struct _RX_CONTEXT *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_DZddd(
            WPP_GLOBAL_Control->AttachedDevice,
            38,
            i + 224,
            *(_DWORD *)(i + 352),
            i + 224,
            *(_DWORD *)(i + 204),
            *(_DWORD *)(i + 88),
            *(_BYTE *)(i + 192));
        if ( *(_DWORD *)(v15 + 352) >= v23[1]
          && *(_DWORD *)(v15 + 204) == 3
          && v21 == *(_DWORD *)(v15 + 88)
          && *(_BYTE *)(v15 + 192) == 1 )
        {
          ++HIDWORD(v22);
          if ( DrPackConnectEntry(v16, &v34, &v33, (struct _V_NET_ROOT *)v15, v23) )
          {
            v13 = v22 + 1;
            LODWORD(v22) = v22 + 1;
          }
          else
          {
            RequestorSessionId = -1073741789;
            v13 = v22;
          }
        }
      }
      v17 = v25;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v25 + 2, v13);
      else
        v25[2] = v13;
      v18 = v17 + 3;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v18, HIDWORD(v22));
      else
        *v18 = HIDWORD(v22);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v17 + 4, v23[0]);
      else
        v17[4] = v23[0];
      v1 = v26;
    }
    else
    {
      RequestorSessionId = -1073741811;
    }
  }
  else
  {
    RequestorSessionId = -1073741789;
  }
  if ( v19 )
    RxPrefixTableEndLookup(v30);
  if ( v20 )
  {
    ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24));
    KeLeaveCriticalRegion();
  }
  if ( v7 )
  {
    if ( RequestorSessionId >= 0 )
    {
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlCopyToUser(v1, v7, v2);
      else
        RtlCopyVolatileMemory(v1, v7, v2);
    }
    ExFreePoolWithTag(v7, 0);
  }
  return (unsigned int)RequestorSessionId;
}

```

## disassembly

```asm
0x140019220  mov     r11, rsp
0x140019223  push    rsi
0x140019224  push    rdi
0x140019225  push    r12
0x140019227  push    r13
0x140019229  push    r14
0x14001922b  push    r15
0x14001922d  sub     rsp, 0C8h
0x140019234  mov     r15, [rcx+230h]
0x14001923b  mov     [rsp+0F8h+var_88], r15
0x140019240  mov     esi, [rcx+23Ch]
0x140019246  mov     [r11+20h], r15
0x14001924a  lea     rax, [rsi+r15]
0x14001924e  mov     [r11+18h], rax
0x140019252  mov     dword ptr [r11+10h], 0
0x14001925a  xorps   xmm0, xmm0
0x14001925d  movups  xmmword ptr [r11-68h], xmm0
0x140019262  movups  xmmword ptr [r11-58h], xmm0
0x140019267  movups  xmmword ptr [r11-48h], xmm0
0x14001926c  test    esi, esi
0x14001926e  jnz     short loc_140019280
0x140019270  mov     qword ptr [r11+20h], 0
0x140019278  mov     qword ptr [r11+18h], 0
0x140019280  mov     eax, [rcx+21Ch]
0x140019286  and     eax, 3
0x140019289  cmp     al, 3
0x14001928b  jnz     loc_140019702
0x140019291  lea     r12, [rcx+28h]
0x140019295  mov     rax, [r12]
0x140019299  cmp     qword ptr [rax+8], 0
0x14001929e  jnz     loc_140019702
0x1400192a4  mov     r13, [rcx+228h]
0x1400192ab  mov     [rsp+0F8h+var_90], r13
0x1400192b0  mov     ecx, [rcx+238h]
0x1400192b6  mov     dword ptr [rsp+0F8h+Length], ecx
0x1400192bd  lea     rdx, [rsp+0F8h+pSessionId]; pSessionId
0x1400192c5  mov     rcx, rax; Irp
0x1400192c8  call    cs:__imp_IoGetRequestorSessionId
0x1400192cf  nop     dword ptr [rax+rax+00h]
0x1400192d4  mov     edi, eax
0x1400192d6  test    eax, eax
0x1400192d8  js      loc_140019702
0x1400192de  test    r13, r13
0x1400192e1  jz      loc_14001938F
0x1400192e7  test    r15, r15
0x1400192ea  jz      loc_14001938F
0x1400192f0  mov     [rsp+0F8h+var_80], r15
0x1400192f5  mov     [rsp+0F8h+var_78], rsi
0x1400192fd  mov     [rsp+0F8h+var_70], r12
0x140019305  xor     r14d, r14d
0x140019308  mov     [rsp+0F8h+var_98], r14
0x14001930d  mov     [rsp+0F8h+var_B7], r14b
0x140019312  mov     [rsp+0F8h+var_B8], r14b
0x140019317  mov     rax, [r12]
0x14001931b  cmp     [rax+40h], r14b
0x14001931f  jz      loc_1400193EE
0x140019325  mov     edx, dword ptr [rsp+0F8h+Length]; Length
0x14001932c  lea     r8d, [r14+1]; Alignment
0x140019330  mov     rcx, r13; Address
0x140019333  call    cs:__imp_ProbeForWrite
0x14001933a  nop     dword ptr [rax+rax+00h]
0x14001933f  lea     r8d, [r14+1]; Alignment
0x140019343  mov     rdx, rsi; Length
0x140019346  mov     rcx, r15; Address
0x140019349  call    cs:__imp_ProbeForWrite
0x140019350  nop     dword ptr [rax+rax+00h]
0x140019355  nop
0x140019356  cmp     esi, 0A0000h
0x14001935c  jbe     short loc_140019399
0x14001935e  lea     rax, WPP_GLOBAL_Control
0x140019365  mov     rcx, cs:WPP_GLOBAL_Control
0x14001936c  cmp     rcx, rax
0x14001936f  jz      short loc_14001938F
0x140019371  cmp     byte ptr [rcx+29h], 2
0x140019375  jb      short loc_14001938F
0x140019377  mov     edx, 25h ; '%'
0x14001937c  mov     r9d, esi
0x14001937f  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x140019386  mov     rcx, [rcx+18h]
0x14001938a  call    WPP_SF_d
0x14001938f  mov     eax, 0C000000Dh
0x140019394  jmp     loc_140019707
0x140019399  test    esi, esi
0x14001939b  jz      short loc_1400193EE
0x14001939d  mov     r8d, 72447244h
0x1400193a3  mov     rdx, rsi
0x1400193a6  mov     ecx, 40h ; '@'
0x1400193ab  call    cs:__imp_ExAllocatePool2
0x1400193b2  nop     dword ptr [rax+rax+00h]
0x1400193b7  mov     r14, rax
0x1400193ba  mov     [rsp+0F8h+var_98], rax
0x1400193bf  test    rax, rax
0x1400193c2  jnz     short loc_1400193CE
0x1400193c4  mov     eax, 0C000009Ah
0x1400193c9  jmp     loc_140019707
0x1400193ce  mov     [rsp+0F8h+arg_18], rax
0x1400193d6  lea     rax, [rsi+rax]
0x1400193da  mov     [rsp+0F8h+arg_10], rax
0x1400193e2  jmp     short loc_1400193EE
0x1400193e4  mov     eax, 0C000000Dh
0x1400193e9  jmp     loc_140019707
0x1400193ee  cmp     dword ptr [rsp+0F8h+Length], 18h
0x1400193f6  jnb     short loc_140019406
0x1400193f8  mov     edi, 0C0000023h
0x1400193fd  mov     [rsp+0F8h+var_B4], edi
0x140019401  jmp     loc_14001966D
0x140019406  xorps   xmm0, xmm0
0x140019409  xor     eax, eax
0x14001940b  movups  [rsp+0F8h+var_B0], xmm0
0x140019410  mov     qword ptr [rsp+0F8h+var_A0], rax
0x140019415  mov     rax, [r12]
0x140019419  cmp     byte ptr [rax+40h], 0
0x14001941d  jz      short loc_140019429
0x14001941f  mov     rcx, r13
0x140019422  call    RtlReadULongFromUser
0x140019427  jmp     short loc_14001942D
0x140019429  mov     eax, [r13+0]
0x14001942d  mov     dword ptr [rsp+0F8h+var_B0], eax
0x140019431  lea     rcx, [r13+14h]
0x140019435  mov     rax, [r12]
0x140019439  cmp     byte ptr [rax+40h], 0
0x14001943d  jz      short loc_140019446
0x14001943f  call    RtlReadULongFromUser
0x140019444  jmp     short loc_140019448
0x140019446  mov     eax, [rcx]
0x140019448  mov     [rsp+0F8h+var_A0+4], eax
0x14001944c  mov     rax, [r12]
0x140019450  cmp     byte ptr [rax+40h], 0
0x140019454  jz      short loc_140019461
0x140019456  lea     rcx, [r13+4]
0x14001945a  call    RtlReadULongFromUser
0x14001945f  jmp     short loc_140019465
0x140019461  mov     eax, [r13+4]
0x140019465  mov     dword ptr [rsp+0F8h+var_B0+4], eax
0x140019469  cmp     eax, [rsp+0F8h+pSessionId]
0x140019470  jz      short loc_140019480
0x140019472  mov     edi, 0C000000Dh
0x140019477  mov     [rsp+0F8h+var_B4], edi
0x14001947b  jmp     loc_14001966D
0x140019480  xor     r13d, r13d
0x140019483  mov     qword ptr [rsp+0F8h+var_B0+8], r13
0x140019488  xor     eax, eax
0x14001948a  mov     [rsp+0F8h+var_A0], eax
0x14001948e  call    cs:__imp_KeEnterCriticalRegion
0x140019495  nop     dword ptr [rax+rax+00h]
0x14001949a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400194a1  mov     rcx, [rax+1F8h]
0x1400194a8  add     rcx, 18h; Resource
0x1400194ac  mov     dl, 1; Wait
0x1400194ae  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400194b5  nop     dword ptr [rax+rax+00h]
0x1400194ba  mov     [rsp+0F8h+var_B7], 1
0x1400194bf  mov     [rsp+0F8h+var_B8], 1
0x1400194c4  mov     r9d, 0EB12h
0x1400194ca  lea     rax, [rsp+0F8h+var_68]
0x1400194d2  mov     [rsp+0F8h+var_D8], rax
0x1400194d7  xor     r8d, r8d
0x1400194da  xor     edx, edx
0x1400194dc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400194e3  mov     rcx, [rcx+1F8h]
0x1400194ea  call    cs:__imp_RxPrefixTableLookupFirstObject
0x1400194f1  nop     dword ptr [rax+rax+00h]
0x1400194f6  mov     r15, rax
0x1400194f9  lea     rax, WPP_GLOBAL_Control
0x140019500  test    r15, r15
0x140019503  jz      loc_1400195E6
0x140019509  mov     rcx, cs:WPP_GLOBAL_Control
0x140019510  cmp     rcx, rax
0x140019513  jz      short loc_14001955B
0x140019515  cmp     byte ptr [rcx+29h], 4
0x140019519  jb      short loc_14001955B
0x14001951b  movzx   eax, byte ptr [r15+0C0h]
0x140019523  lea     r8, [r15+0E0h]
0x14001952a  mov     edx, 26h ; '&'
0x14001952f  mov     [rsp+0F8h+var_C0], eax
0x140019533  mov     eax, [r15+58h]
0x140019537  mov     [rsp+0F8h+var_C8], eax
0x14001953b  mov     eax, [r15+0CCh]
0x140019542  mov     [rsp+0F8h+var_D0], eax
0x140019546  mov     [rsp+0F8h+var_D8], r8
0x14001954b  mov     r9d, [r15+160h]
0x140019552  mov     rcx, [rcx+18h]
0x140019556  call    WPP_SF_DZddd
0x14001955b  mov     eax, [rsp+0F8h+var_A0+4]
0x14001955f  cmp     [r15+160h], eax
0x140019566  jb      short loc_1400195BD
0x140019568  cmp     dword ptr [r15+0CCh], 3
0x140019570  jnz     short loc_1400195BD
0x140019572  mov     eax, [r15+58h]
0x140019576  cmp     dword ptr [rsp+0F8h+var_B0+4], eax
0x14001957a  jnz     short loc_1400195BD
0x14001957c  cmp     byte ptr [r15+0C0h], 1
0x140019584  jnz     short loc_1400195BD
0x140019586  inc     dword ptr [rsp+0F8h+var_B0+0Ch]
0x14001958a  lea     rax, [rsp+0F8h+var_A0]
0x14001958f  mov     [rsp+0F8h+var_D8], rax; unsigned int *
0x140019594  mov     r9, r15; struct _V_NET_ROOT *
0x140019597  lea     r8, [rsp+0F8h+arg_10]; char **
0x14001959f  lea     rdx, [rsp+0F8h+arg_18]; char **
0x1400195a7  call    ?DrPackConnectEntry@@YAEPEAU_RX_CONTEXT@@PEAPEAD1PEAU_V_NET_ROOT@@PEAK@Z; DrPackConnectEntry(_RX_CONTEXT *,char * *,char * *,_V_NET_ROOT *,ulong *)
0x1400195ac  test    al, al
0x1400195ae  jz      short loc_1400195D6
0x1400195b0  mov     r13d, dword ptr [rsp+0F8h+var_B0+8]
0x1400195b5  inc     r13d
0x1400195b8  mov     dword ptr [rsp+0F8h+var_B0+8], r13d
0x1400195bd  lea     rcx, [rsp+0F8h+var_68]
0x1400195c5  call    cs:__imp_RxPrefixTableLookupNextObject
0x1400195cc  nop     dword ptr [rax+rax+00h]
0x1400195d1  jmp     loc_1400194F6
0x1400195d6  mov     edi, 0C0000023h
0x1400195db  mov     [rsp+0F8h+var_B4], edi
0x1400195df  mov     r13d, dword ptr [rsp+0F8h+var_B0+8]
0x1400195e4  jmp     short loc_1400195BD
0x1400195e6  mov     r15, [rsp+0F8h+var_90]
0x1400195eb  mov     rax, [r12]
0x1400195ef  cmp     byte ptr [rax+40h], 0
0x1400195f3  jz      short loc_140019603
0x1400195f5  mov     edx, r13d
0x1400195f8  lea     rcx, [r15+8]
0x1400195fc  call    RtlWriteULongToUser
0x140019601  jmp     short loc_140019607
0x140019603  mov     [r15+8], r13d
0x140019607  lea     rcx, [r15+0Ch]
0x14001960b  mov     rax, [r12]
0x14001960f  cmp     byte ptr [rax+40h], 0
0x140019613  jz      short loc_140019620
0x140019615  mov     edx, dword ptr [rsp+0F8h+var_B0+0Ch]
0x140019619  call    RtlWriteULongToUser
0x14001961e  jmp     short loc_140019626
0x140019620  mov     eax, dword ptr [rsp+0F8h+var_B0+0Ch]
0x140019624  mov     [rcx], eax
0x140019626  mov     edx, [rsp+0F8h+var_A0]
0x14001962a  mov     rax, [r12]
0x14001962e  cmp     byte ptr [rax+40h], 0
0x140019632  jz      short loc_14001963F
0x140019634  lea     rcx, [r15+10h]
0x140019638  call    RtlWriteULongToUser
0x14001963d  jmp     short loc_140019643
0x14001963f  mov     [r15+10h], edx
0x140019643  mov     r15, [rsp+0F8h+var_88]
0x140019648  jmp     short loc_14001966D
0x14001964a  mov     edi, 0C000000Dh
0x14001964f  mov     [rsp+0F8h+var_B4], edi
0x140019653  mov     r15, [rsp+0F8h+var_80]
0x140019658  mov     r14, [rsp+0F8h+var_98]
0x14001965d  mov     rsi, [rsp+0F8h+var_78]
0x140019665  mov     r12, [rsp+0F8h+var_70]
0x14001966d  cmp     [rsp+0F8h+var_B8], 0
0x140019672  jz      short loc_140019688
0x140019674  lea     rcx, [rsp+0F8h+var_68]
0x14001967c  call    cs:__imp_RxPrefixTableEndLookup
0x140019683  nop     dword ptr [rax+rax+00h]
0x140019688  cmp     [rsp+0F8h+var_B7], 0
0x14001968d  jz      short loc_1400196B9
0x14001968f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140019696  mov     rcx, [rax+1F8h]
0x14001969d  add     rcx, 18h; Resource
0x1400196a1  call    cs:__imp_ExReleaseResourceLite
0x1400196a8  nop     dword ptr [rax+rax+00h]
0x1400196ad  call    cs:__imp_KeLeaveCriticalRegion
0x1400196b4  nop     dword ptr [rax+rax+00h]
0x1400196b9  test    r14, r14
0x1400196bc  jz      short loc_1400196FE
0x1400196be  test    edi, edi
0x1400196c0  js      short loc_1400196ED
0x1400196c2  mov     rax, [r12]
0x1400196c6  mov     r8, rsi; Size
0x1400196c9  mov     rdx, r14; Src
0x1400196cc  mov     rcx, r15; void *
0x1400196cf  cmp     byte ptr [rax+40h], 0
0x1400196d3  jz      short loc_1400196DC
0x1400196d5  call    RtlCopyToUser
0x1400196da  jmp     short loc_1400196E1
0x1400196dc  call    RtlCopyVolatileMemory
0x1400196e1  jmp     short loc_1400196ED
0x1400196e3  mov     edi, 0C000000Dh
0x1400196e8  mov     r14, [rsp+0F8h+var_98]
0x1400196ed  xor     edx, edx; Tag
0x1400196ef  mov     rcx, r14; P
0x1400196f2  call    cs:__imp_ExFreePoolWithTag
0x1400196f9  nop     dword ptr [rax+rax+00h]
0x1400196fe  mov     eax, edi
0x140019700  jmp     short loc_140019707
0x140019702  mov     eax, 0C0000010h
0x140019707  add     rsp, 0C8h
0x14001970e  pop     r15
0x140019710  pop     r14
0x140019712  pop     r13
0x140019714  pop     r12
0x140019716  pop     rdi
0x140019717  pop     rsi
0x140019718  retn
```
