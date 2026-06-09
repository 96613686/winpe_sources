# DoLineUpToProtocol

- ea: `0x14000e400`
- end: `0x14000e8a4`
- name: `DoLineUpToProtocol`
- size: `1188`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007364`
- `0x14002c3f4`

## callees

- `0x14000176c`
- `0x14000a290`
- `0x14000e400`
- `0x14000ec48`
- `0x140010f7c`
- `0x1400161f0`
- `0x140016400`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000e77d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e81d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e77d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e81d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e723`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e7b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e723`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e7b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e836`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e836`
- `ntoskrnl!ExAllocatePool2` at `0x14000e497`
- `ntoskrnl!ExAllocatePool2` at `0x14000e497`
- `NDIS!NdisResetEvent` at `0x14000e636`
- `NDIS!NdisResetEvent` at `0x14000e6eb`
- `NDIS!NdisResetEvent` at `0x14000e636`
- `NDIS!NdisResetEvent` at `0x14000e6eb`
- `NDIS!NdisWaitEvent` at `0x14000e627`
- `NDIS!NdisWaitEvent` at `0x14000e6db`
- `NDIS!NdisWaitEvent` at `0x14000e627`
- `NDIS!NdisWaitEvent` at `0x14000e6db`
- `NDIS!NdisInitializeEvent` at `0x14000e5b8`
- `NDIS!NdisInitializeEvent` at `0x14000e67f`
- `NDIS!NdisInitializeEvent` at `0x14000e5b8`
- `NDIS!NdisInitializeEvent` at `0x14000e67f`
- `NDIS!NdisMIndicateStatusEx` at `0x14000e5fe`
- `NDIS!NdisMIndicateStatusEx` at `0x14000e6c3`
- `NDIS!NdisMIndicateStatusEx` at `0x14000e5fe`
- `NDIS!NdisMIndicateStatusEx` at `0x14000e6c3`

## pseudocode

```c
__int64 __fastcall DoLineUpToProtocol(__int64 a1, char a2)
{
  __int64 v2; // r15
  __int64 v4; // rsi
  ULONG v5; // r13d
  unsigned int *Pool2; // rax
  unsigned int *v7; // rbx
  int v8; // r14d
  int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // ecx
  void *v12; // rcx
  void *v13; // rcx
  unsigned int v14; // eax
  void *v15; // rcx
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rax
  int v19; // r15d
  const void *v20; // rdx
  _NDIS_STATUS_INDICATION StatusIndication; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v24[28]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 Event_12; // [rsp+BCh] [rbp+3h]
  int Event_20; // [rsp+C4h] [rbp+Bh]

  v2 = *(_QWORD *)(a1 + 56);
  v4 = *(_QWORD *)(a1 + 64);
  memset(&StatusIndication, 0, sizeof(StatusIndication));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  v5 = *(_DWORD *)(a1 + 328) + 642;
  Pool2 = (unsigned int *)ExAllocatePool2(64, v5, 1282302327);
  v7 = Pool2;
  if ( Pool2 )
  {
    v8 = 0;
    *Pool2 = 8 * *(_DWORD *)(v4 + 336) / 0x64u;
    v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 88) + 72LL) + 124LL);
    if ( (unsigned int)(v9 - 8) <= 1 || (unsigned int)(v9 - 13) <= 2 )
      v10 = *(_DWORD *)(a1 + 220);
    else
      v10 = *(_DWORD *)(a1 + 216);
    v7[1] = v10;
    v11 = *(_DWORD *)(v4 + 352);
    if ( v10 > v11 )
      v7[1] = v11;
    v7[2] = 2;
    v12 = (void *)((unsigned __int64)(v7 + 30) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_WORD *)v7 + 6) = *(_WORD *)(v4 + 164);
    *((_WORD *)v7 + 20) = *(_WORD *)(a1 + 212);
    *((_WORD *)v7 + 24) = *(_WORD *)(a1 + 272);
    *((_WORD *)v7 + 25) = 514;
    *((_QWORD *)v7 + 7) = v12;
    if ( *(_WORD *)(a1 + 272) )
      memmove(v12, *(const void **)(a1 + 280), *(unsigned __int16 *)(a1 + 272));
    v13 = (void *)(((unsigned __int64)v7 + 634) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)v7 + 4) = v13;
    *(unsigned int *)((char *)v7 + 14) = *(_DWORD *)(a1 + 244);
    *((_WORD *)v7 + 9) = *(_WORD *)(a1 + 248);
    v7[5] = *(_DWORD *)(a1 + 250);
    *((_WORD *)v7 + 12) = *(_WORD *)(a1 + 254);
    v7[7] = *(_DWORD *)(a1 + 328);
    v14 = *(_DWORD *)(a1 + 328);
    if ( v14 )
      memmove(v13, *(const void **)(a1 + 336), v14);
    NdisInitializeEvent((PNDIS_EVENT)v7 + 3);
    *((_BYTE *)v7 + 64) = 0;
    v7[25] = *(_DWORD *)(v4 + 1788);
    StatusIndication.Header = (NDIS_OBJECT_HEADER)7340440;
    StatusIndication.SourceHandle = *(NDIS_HANDLE *)(v2 + 40);
    StatusIndication.PortNumber = 0;
    StatusIndication.StatusCode = 1073807368;
    StatusIndication.StatusBuffer = v7;
    StatusIndication.StatusBufferSize = v5;
    NdisMIndicateStatusEx(*(NDIS_HANDLE *)(v2 + 40), &StatusIndication);
    if ( *((_BYTE *)v7 + 64) )
    {
      if ( a2 )
      {
        NdisWaitEvent((PNDIS_EVENT)v7 + 3, 0);
        NdisResetEvent((PNDIS_EVENT)v7 + 3);
        v8 = v7[24];
        if ( v8 < 0 )
        {
          *(_DWORD *)v24 = *(unsigned int *)((char *)v7 + 14);
          *(_WORD *)&v24[4] = *((_WORD *)v7 + 9);
          *(_DWORD *)&v24[6] = v7[5];
          *(_WORD *)&v24[10] = *((_WORD *)v7 + 12);
          *(_OWORD *)&v24[12] = 0;
          Event_12 = 0;
          Event_20 = 0;
          NdisInitializeEvent((PNDIS_EVENT)&v24[16]);
          StatusIndication.Header = (NDIS_OBJECT_HEADER)7340440;
          StatusIndication.SourceHandle = *(NDIS_HANDLE *)(v2 + 40);
          StatusIndication.StatusBuffer = v24;
          StatusIndication.PortNumber = 0;
          StatusIndication.StatusCode = 1073807369;
          StatusIndication.StatusBufferSize = 12;
          v15 = *(void **)(v2 + 40);
          v24[12] = 0;
          NdisMIndicateStatusEx(v15, &StatusIndication);
          if ( v24[12] )
          {
            NdisWaitEvent((PNDIS_EVENT)&v24[16], 0);
            NdisResetEvent((PNDIS_EVENT)&v24[16]);
          }
          ExFreePoolWithTag(v7, 0);
          return (unsigned int)v8;
        }
      }
    }
    memset(v24, 0, 20);
    *(_BYTE *)(v4 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 1768));
    *(_WORD *)v24 = *(_WORD *)(a1 + 212);
    GetProtocolInfo(v24);
    v16 = 0;
    v17 = 4 * *(_DWORD *)&v24[8];
    if ( *(_DWORD *)&v24[16] >= (unsigned int)(4 * *(_DWORD *)&v24[8]) )
      v17 = *(_DWORD *)&v24[16];
    do
    {
      v18 = 3 * v16++;
      *(_DWORD *)(a1 + 16 * v18 + 132) = v17;
    }
    while ( v16 != 2 );
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 1768), *(_BYTE *)(v4 + 1776));
    SendAdapterIndexCompartmentIdToMiniport(v4, v7[26], *(unsigned int *)(v4 + 2440));
    if ( !*(_DWORD *)(a1 + 240) )
    {
      v19 = *(unsigned int *)((char *)v7 + 22);
      if ( v19 )
      {
        *(_BYTE *)(v4 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 1768));
        *(_DWORD *)(a1 + 250) = v7[5];
        *(_WORD *)(a1 + 254) = *((_WORD *)v7 + 12);
        *(_DWORD *)(a1 + 240) = v19;
        if ( *((_WORD *)v7 + 24) )
          NdisWanStringToNdisString((PUNICODE_STRING)(a1 + 288), *((const WCHAR **)v7 + 7));
        v20 = (const void *)*((_QWORD *)v7 + 4);
        if ( v20 )
          memmove(*(void **)(a1 + 336), v20, *(unsigned int *)(a1 + 328));
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 1768), *(_BYTE *)(v4 + 1776));
      }
      else
      {
        v8 = 603;
      }
    }
    ExFreePoolWithTag(v7, 0);
  }
  else
  {
    v8 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e400  push    rbp
0x14000e402  push    rbx
0x14000e403  push    rsi
0x14000e404  push    rdi
0x14000e405  push    r12
0x14000e407  push    r13
0x14000e409  push    r14
0x14000e40b  push    r15
0x14000e40d  lea     rbp, [rsp-1Fh]
0x14000e412  sub     rsp, 0D8h
0x14000e419  mov     rax, cs:__security_cookie
0x14000e420  xor     rax, rsp
0x14000e423  mov     [rbp+57h+var_48], rax
0x14000e427  mov     r15, [rcx+38h]
0x14000e42b  mov     rdi, rcx
0x14000e42e  mov     rsi, [rcx+40h]
0x14000e432  lea     rcx, [rsp+110h+StatusIndication]; void *
0x14000e437  mov     [rsp+110h+var_F0], dl
0x14000e43b  xor     edx, edx; Val
0x14000e43d  lea     r8d, [rdx+70h]; Size
0x14000e441  call    memset
0x14000e446  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e44d  lea     rax, WPP_GLOBAL_Control
0x14000e454  mov     ebx, 40h ; '@'
0x14000e459  cmp     rcx, rax
0x14000e45c  jz      short loc_14000E47D
0x14000e45e  mov     eax, [rcx+2Ch]
0x14000e461  test    al, 4
0x14000e463  jz      short loc_14000E47D
0x14000e465  cmp     byte ptr [rcx+29h], 5
0x14000e469  jb      short loc_14000E47D
0x14000e46b  mov     rcx, [rcx+18h]
0x14000e46f  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000e476  mov     edx, ebx
0x14000e478  call    WPP_SF_
0x14000e47d  mov     r13d, [rdi+148h]
0x14000e484  mov     r8d, 4C6E6177h
0x14000e48a  add     r13d, 282h
0x14000e491  mov     rcx, rbx
0x14000e494  mov     edx, r13d
0x14000e497  call    cs:__imp_ExAllocatePool2
0x14000e49e  nop     dword ptr [rax+rax+00h]
0x14000e4a3  xor     r12d, r12d
0x14000e4a6  mov     rbx, rax
0x14000e4a9  test    rax, rax
0x14000e4ac  jz      loc_14000E844
0x14000e4b2  mov     ecx, [rsi+150h]
0x14000e4b8  mov     eax, 51EB851Fh
0x14000e4bd  shl     ecx, 3
0x14000e4c0  mov     r14d, r12d
0x14000e4c3  mul     ecx
0x14000e4c5  shr     edx, 5
0x14000e4c8  mov     [rbx], edx
0x14000e4ca  mov     rax, [rsi+58h]
0x14000e4ce  mov     rcx, [rax+48h]
0x14000e4d2  mov     edx, [rcx+7Ch]
0x14000e4d5  lea     eax, [rdx-8]
0x14000e4d8  cmp     eax, 1
0x14000e4db  jbe     short loc_14000E4ED
0x14000e4dd  lea     eax, [rdx-0Dh]
0x14000e4e0  cmp     eax, 2
0x14000e4e3  jbe     short loc_14000E4ED
0x14000e4e5  mov     eax, [rdi+0D8h]
0x14000e4eb  jmp     short loc_14000E4F3
0x14000e4ed  mov     eax, [rdi+0DCh]
0x14000e4f3  mov     [rbx+4], eax
0x14000e4f6  mov     ecx, [rsi+160h]
0x14000e4fc  cmp     eax, ecx
0x14000e4fe  jbe     short loc_14000E503
0x14000e500  mov     [rbx+4], ecx
0x14000e503  mov     dword ptr [rbx+8], 2
0x14000e50a  lea     rcx, [rbx+78h]
0x14000e50e  movzx   eax, word ptr [rsi+0A4h]
0x14000e515  and     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000e519  mov     [rbx+0Ch], ax
0x14000e51d  movzx   eax, word ptr [rdi+0D4h]
0x14000e524  mov     [rbx+28h], ax
0x14000e528  movzx   eax, word ptr [rdi+110h]
0x14000e52f  mov     [rbx+30h], ax
0x14000e533  mov     word ptr [rbx+32h], 202h
0x14000e539  mov     [rbx+38h], rcx
0x14000e53d  movzx   eax, word ptr [rdi+110h]
0x14000e544  test    ax, ax
0x14000e547  jz      short loc_14000E558
0x14000e549  mov     rdx, [rdi+118h]; Src
0x14000e550  mov     r8d, eax; Size
0x14000e553  call    memmove
0x14000e558  lea     rcx, [rbx+27Ah]
0x14000e55f  and     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000e563  mov     [rbx+20h], rcx
0x14000e567  mov     eax, [rdi+0F4h]
0x14000e56d  mov     [rbx+0Eh], eax
0x14000e570  movzx   eax, word ptr [rdi+0F8h]
0x14000e577  mov     [rbx+12h], ax
0x14000e57b  mov     eax, [rdi+0FAh]
0x14000e581  mov     [rbx+14h], eax
0x14000e584  movzx   eax, word ptr [rdi+0FEh]
0x14000e58b  mov     [rbx+18h], ax
0x14000e58f  mov     eax, [rdi+148h]
0x14000e595  mov     [rbx+1Ch], eax
0x14000e598  mov     eax, [rdi+148h]
0x14000e59e  test    eax, eax
0x14000e5a0  jz      short loc_14000E5B1
0x14000e5a2  mov     rdx, [rdi+150h]; Src
0x14000e5a9  mov     r8d, eax; Size
0x14000e5ac  call    memmove
0x14000e5b1  lea     r12, [rbx+48h]
0x14000e5b5  mov     rcx, r12; Event
0x14000e5b8  call    cs:__imp_NdisInitializeEvent
0x14000e5bf  nop     dword ptr [rax+rax+00h]
0x14000e5c4  mov     [rbx+40h], r14b
0x14000e5c8  lea     rdx, [rsp+110h+StatusIndication]; StatusIndication
0x14000e5cd  mov     eax, [rsi+6FCh]
0x14000e5d3  mov     [rbx+64h], eax
0x14000e5d6  mov     dword ptr [rsp+110h+StatusIndication.Header.Type], 700198h
0x14000e5de  mov     rax, [r15+28h]
0x14000e5e2  mov     [rsp+110h+StatusIndication.SourceHandle], rax
0x14000e5e7  mov     [rbp+57h+StatusIndication.PortNumber], r14d
0x14000e5eb  mov     [rbp+57h+StatusIndication.StatusCode], 40010008h
0x14000e5f2  mov     [rbp+57h+StatusIndication.StatusBuffer], rbx
0x14000e5f6  mov     [rbp+57h+StatusIndication.StatusBufferSize], r13d
0x14000e5fa  mov     rcx, [r15+28h]; MiniportAdapterHandle
0x14000e5fe  call    cs:__imp_NdisMIndicateStatusEx
0x14000e605  nop     dword ptr [rax+rax+00h]
0x14000e60a  xor     r13d, r13d
0x14000e60d  cmp     [rbx+40h], r13b
0x14000e611  jz      loc_14000E70D
0x14000e617  cmp     [rsp+110h+var_F0], r13b
0x14000e61c  jz      loc_14000E70D
0x14000e622  xor     edx, edx; MsToWait
0x14000e624  mov     rcx, r12; Event
0x14000e627  call    cs:__imp_NdisWaitEvent
0x14000e62e  nop     dword ptr [rax+rax+00h]
0x14000e633  mov     rcx, r12; Event
0x14000e636  call    cs:__imp_NdisResetEvent
0x14000e63d  nop     dword ptr [rax+rax+00h]
0x14000e642  mov     r14d, [rbx+60h]
0x14000e646  test    r14d, r14d
0x14000e649  jns     loc_14000E70D
0x14000e64f  mov     eax, [rbx+0Eh]
0x14000e652  lea     rcx, [rbp+57h+Event]; Event
0x14000e656  mov     dword ptr [rbp+57h+var_70], eax
0x14000e659  xorps   xmm0, xmm0
0x14000e65c  movzx   eax, word ptr [rbx+12h]
0x14000e660  mov     word ptr [rbp+57h+var_70+4], ax
0x14000e664  mov     eax, [rbx+14h]
0x14000e667  mov     dword ptr [rbp+57h+var_70+6], eax
0x14000e66a  movzx   eax, word ptr [rbx+18h]
0x14000e66e  mov     word ptr [rbp+57h+var_70+0Ah], ax
0x14000e672  movdqu  xmmword ptr [rbp-0Dh], xmm0
0x14000e677  mov     [rbp+57h+Event.Event.Header.WaitListHead.Flink+4], r13
0x14000e67b  mov     dword ptr [rbp+57h+Event.Event.Header.WaitListHead.Blink+4], r13d
0x14000e67f  call    cs:__imp_NdisInitializeEvent
0x14000e686  nop     dword ptr [rax+rax+00h]
0x14000e68b  mov     dword ptr [rsp+110h+StatusIndication.Header.Type], 700198h
0x14000e693  lea     rdx, [rsp+110h+StatusIndication]; StatusIndication
0x14000e698  mov     rax, [r15+28h]
0x14000e69c  mov     [rsp+110h+StatusIndication.SourceHandle], rax
0x14000e6a1  lea     rax, [rbp+57h+var_70]
0x14000e6a5  mov     [rbp+57h+StatusIndication.StatusBuffer], rax
0x14000e6a9  mov     [rbp+57h+StatusIndication.PortNumber], r13d
0x14000e6ad  mov     [rbp+57h+StatusIndication.StatusCode], 40010009h
0x14000e6b4  mov     [rbp+57h+StatusIndication.StatusBufferSize], 0Ch
0x14000e6bb  mov     rcx, [r15+28h]; MiniportAdapterHandle
0x14000e6bf  mov     byte ptr [rbp+57h+var_70+0Ch], r13b
0x14000e6c3  call    cs:__imp_NdisMIndicateStatusEx
0x14000e6ca  nop     dword ptr [rax+rax+00h]
0x14000e6cf  cmp     byte ptr [rbp+57h+var_70+0Ch], r13b
0x14000e6d3  jz      short loc_14000E6F7
0x14000e6d5  xor     edx, edx; MsToWait
0x14000e6d7  lea     rcx, [rbp+57h+Event]; Event
0x14000e6db  call    cs:__imp_NdisWaitEvent
0x14000e6e2  nop     dword ptr [rax+rax+00h]
0x14000e6e7  lea     rcx, [rbp+57h+Event]; Event
0x14000e6eb  call    cs:__imp_NdisResetEvent
0x14000e6f2  nop     dword ptr [rax+rax+00h]
0x14000e6f7  xor     edx, edx; Tag
0x14000e6f9  mov     rcx, rbx; P
0x14000e6fc  call    cs:__imp_ExFreePoolWithTag
0x14000e703  nop     dword ptr [rax+rax+00h]
0x14000e708  jmp     loc_14000E880
0x14000e70d  xorps   xmm0, xmm0
0x14000e710  lea     r12, [rsi+6E8h]
0x14000e717  xor     eax, eax
0x14000e719  mov     rcx, r12; SpinLock
0x14000e71c  movups  [rbp+57h+var_70], xmm0
0x14000e720  mov     dword ptr [rbp+57h+Event.Event.Header], eax
0x14000e723  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e72a  nop     dword ptr [rax+rax+00h]
0x14000e72f  mov     [rsi+6F0h], al
0x14000e735  lea     rcx, [rbp+57h+var_70]
0x14000e739  movzx   eax, word ptr [rdi+0D4h]
0x14000e740  mov     word ptr [rbp+57h+var_70], ax
0x14000e744  call    GetProtocolInfo
0x14000e749  mov     eax, dword ptr [rbp+57h+var_70+8]
0x14000e74c  mov     rcx, r13
0x14000e74f  lea     edx, ds:0[rax*4]
0x14000e756  cmp     dword ptr [rbp+57h+Event.Event.Header], edx
0x14000e759  cmovnb  edx, dword ptr [rbp+57h+Event.Event.Header]
0x14000e75d  lea     rax, [rcx+rcx*2]
0x14000e761  inc     rcx
0x14000e764  add     rax, rax
0x14000e767  mov     [rdi+rax*8+84h], edx
0x14000e76e  cmp     rcx, 2
0x14000e772  jnz     short loc_14000E75D
0x14000e774  mov     dl, [rsi+6F0h]; NewIrql
0x14000e77a  mov     rcx, r12; SpinLock
0x14000e77d  call    cs:__imp_KeReleaseSpinLock
0x14000e784  nop     dword ptr [rax+rax+00h]
0x14000e789  mov     r8d, [rsi+988h]
0x14000e790  mov     rcx, rsi
0x14000e793  mov     edx, [rbx+68h]
0x14000e796  call    SendAdapterIndexCompartmentIdToMiniport
0x14000e79b  cmp     [rdi+0F0h], r13d
0x14000e7a2  jnz     loc_14000E831
0x14000e7a8  mov     r15d, [rbx+16h]
0x14000e7ac  test    r15d, r15d
0x14000e7af  jz      short loc_14000E82B
0x14000e7b1  mov     rcx, r12; SpinLock
0x14000e7b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e7bb  nop     dword ptr [rax+rax+00h]
0x14000e7c0  mov     [rsi+6F0h], al
0x14000e7c6  mov     eax, [rbx+14h]
0x14000e7c9  mov     [rdi+0FAh], eax
0x14000e7cf  movzx   eax, word ptr [rbx+18h]
0x14000e7d3  mov     [rdi+0FEh], ax
0x14000e7da  mov     [rdi+0F0h], r15d
0x14000e7e1  cmp     [rbx+30h], r13w
0x14000e7e6  jz      short loc_14000E7F8
0x14000e7e8  mov     rdx, [rbx+38h]
0x14000e7ec  lea     rcx, [rdi+120h]; DestinationString
0x14000e7f3  call    NdisWanStringToNdisString
0x14000e7f8  mov     rdx, [rbx+20h]; Src
0x14000e7fc  test    rdx, rdx
0x14000e7ff  jz      short loc_14000E814
0x14000e801  mov     r8d, [rdi+148h]; Size
0x14000e808  mov     rcx, [rdi+150h]; void *
0x14000e80f  call    memmove
0x14000e814  mov     dl, [rsi+6F0h]; NewIrql
0x14000e81a  mov     rcx, r12; SpinLock
0x14000e81d  call    cs:__imp_KeReleaseSpinLock
0x14000e824  nop     dword ptr [rax+rax+00h]
0x14000e829  jmp     short loc_14000E831
0x14000e82b  mov     r14d, 25Bh
0x14000e831  xor     edx, edx; Tag
0x14000e833  mov     rcx, rbx; P
0x14000e836  call    cs:__imp_ExFreePoolWithTag
0x14000e83d  nop     dword ptr [rax+rax+00h]
0x14000e842  jmp     short loc_14000E84A
0x14000e844  mov     r14d, 0C000009Ah
0x14000e84a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e851  lea     rax, WPP_GLOBAL_Control
0x14000e858  cmp     rcx, rax
0x14000e85b  jz      short loc_14000E880
0x14000e85d  mov     edx, [rcx+2Ch]
0x14000e860  test    dl, 4
0x14000e863  jz      short loc_14000E880
0x14000e865  cmp     byte ptr [rcx+29h], 5
0x14000e869  jb      short loc_14000E880
0x14000e86b  mov     rcx, [rcx+18h]
0x14000e86f  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000e876  mov     edx, 41h ; 'A'
0x14000e87b  call    WPP_SF_
0x14000e880  mov     eax, r14d
0x14000e883  mov     rcx, [rbp+57h+var_48]
0x14000e887  xor     rcx, rsp; StackCookie
0x14000e88a  call    __security_check_cookie
0x14000e88f  add     rsp, 0D8h
0x14000e896  pop     r15
0x14000e898  pop     r14
0x14000e89a  pop     r13
0x14000e89c  pop     r12
0x14000e89e  pop     rdi
0x14000e89f  pop     rsi
0x14000e8a0  pop     rbx
0x14000e8a1  pop     rbp
0x14000e8a2  retn
```
