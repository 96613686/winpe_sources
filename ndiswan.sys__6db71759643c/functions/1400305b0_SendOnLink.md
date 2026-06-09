# SendOnLink

- ea: `0x1400305b0`
- end: `0x140030935`
- name: `SendOnLink`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140002770`

## callees

- `0x140002e40`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a744`
- `0x14002e20c`
- `0x1400305b0`
- `0x140030940`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140030631`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003070b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030747`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400307db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400307fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003086d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030631`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003070b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030747`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400307db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400307fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003086d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400305fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003071e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030781`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003080f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400305fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003071e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030781`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003080f`
- `NDIS!NdisCoSendNetBufferLists` at `0x140030772`
- `NDIS!NdisCoSendNetBufferLists` at `0x140030772`

## pseudocode

```c
__int64 __fastcall SendOnLink(__int64 a1)
{
  __int64 v1; // rbx
  struct _NET_BUFFER_LIST *v3; // r15
  unsigned int v4; // r12d
  __int64 v5; // rdi
  __int64 v6; // rbp
  KIRQL v7; // al
  __int64 v8; // r9
  PNET_BUFFER FirstNetBuffer; // rax
  int i; // ecx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  KSPIN_LOCK *v15; // rdi
  KIRQL *v16; // rbp
  KIRQL v17; // al
  KSPIN_LOCK *v18; // rcx
  bool v19; // zf

  v1 = *(_QWORD *)(a1 + 40);
  v3 = *(struct _NET_BUFFER_LIST **)(a1 + 80);
  v4 = 0;
  v5 = *(_QWORD *)(v1 + 72);
  v6 = *(_QWORD *)(v1 + 80);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids, v1, v3);
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 504));
  v8 = *(unsigned int *)(v5 + 24);
  *(_BYTE *)(v5 + 512) = v7;
  if ( (_DWORD)v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids, v8);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 504), *(_BYTE *)(v5 + 512));
    v15 = (KSPIN_LOCK *)(v6 + 1768);
    v16 = (KIRQL *)(v6 + 1776);
    KeReleaseSpinLock(v15, *v16);
    *(_BYTE *)(v1 + 744) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 736));
    CompleteSendDesc(a1, -1071448022);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v1 + 72) + 32LL));
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 504), *(_BYTE *)(v5 + 512));
    *(_DWORD *)(a1 + 28) |= 2u;
    if ( *(_DWORD *)(v1 + 208) == ++*(_DWORD *)(v1 + 212) )
    {
      *(_BYTE *)(v1 + 201) = 0;
      --*(_DWORD *)(v6 + 156);
    }
    FirstNetBuffer = v3->FirstNetBuffer;
    for ( i = 0; FirstNetBuffer; FirstNetBuffer = (PNET_BUFFER)FirstNetBuffer->Link.Alignment )
    {
      v4 += FirstNetBuffer->DataLength;
      ++i;
    }
    *(_DWORD *)(v1 + 588) += i;
    *(_DWORD *)(v6 + 1620) += i;
    v11 = v4 + ((unsigned __int64)*(unsigned int *)(v1 + 696) << 32) + *(unsigned int *)(v1 + 580);
    *(_DWORD *)(v1 + 580) += v4;
    *(_DWORD *)(v1 + 696) = HIDWORD(v11);
    v12 = v4 + ((unsigned __int64)*(unsigned int *)(v6 + 1728) << 32) + *(unsigned int *)(v6 + 1612);
    *(_DWORD *)(v6 + 1612) += v4;
    *(_DWORD *)(v6 + 1728) = HIDWORD(v12);
    v13 = MEMORY[0xFFFFF78000000008];
    v14 = *(_QWORD *)(v6 + 2496);
    if ( (unsigned __int64)(MEMORY[0xFFFFF78000000008] - v14) >= 0x989680 )
    {
      *(_QWORD *)(v6 + 2472) = *(_QWORD *)(v6 + 2488);
      *(_QWORD *)(v6 + 2480) = v14;
      *(_QWORD *)(v6 + 2488) = v12;
      *(_QWORD *)(v6 + 2496) = v13;
    }
    v15 = (KSPIN_LOCK *)(v6 + 1768);
    v16 = (KIRQL *)(v6 + 1776);
    KeReleaseSpinLock(v15, *v16);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 736));
    ++*(_DWORD *)(v1 + 32);
    v18 = (KSPIN_LOCK *)(v1 + 736);
    v19 = *(_DWORD *)(v1 + 20) == 2;
    *(_BYTE *)(v1 + 744) = v17;
    if ( v19 )
    {
      KeReleaseSpinLock(v18, v17);
      if ( gbSniffLink && qword_14001E2D8 )
        IndicatePromiscuousSendNBL(v1, v3);
      v3->SourceHandle = *(NDIS_HANDLE *)(v1 + 56);
      NdisCoSendNetBufferLists(*(NDIS_HANDLE *)(v1 + 56), v3, 0);
    }
    else
    {
      KeReleaseSpinLock(v18, v17);
      v3->Status = 0;
      ProtoCoSendNetBufferListChainComplete(*(_QWORD *)(v1 + 40), v3, 0);
    }
  }
  *v16 = KeAcquireSpinLockRaiseToDpc(v15);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x1400305b0  push    rbx
0x1400305b2  push    rbp
0x1400305b3  push    rsi
0x1400305b4  push    rdi
0x1400305b5  push    r12
0x1400305b7  push    r13
0x1400305b9  push    r14
0x1400305bb  push    r15
0x1400305bd  sub     rsp, 38h
0x1400305c1  mov     rbx, [rcx+28h]
0x1400305c5  mov     rsi, rcx
0x1400305c8  mov     r15, [rcx+50h]
0x1400305cc  xor     r12d, r12d
0x1400305cf  mov     rdi, [rbx+48h]
0x1400305d3  mov     rbp, [rbx+50h]
0x1400305d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400305de  lea     r13, WPP_GLOBAL_Control
0x1400305e5  cmp     rcx, r13
0x1400305e8  jz      short loc_1400305F5
0x1400305ea  mov     eax, [rcx+2Ch]
0x1400305ed  test    al, 8
0x1400305ef  jnz     loc_140030898
0x1400305f5  lea     rcx, [rdi+1F8h]; SpinLock
0x1400305fc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030603  nop     dword ptr [rax+rax+00h]
0x140030608  mov     r9d, [rdi+18h]
0x14003060c  mov     [rdi+200h], al
0x140030612  test    r9d, r9d
0x140030615  jnz     loc_1400307BD
0x14003061b  mov     rax, [rbx+48h]
0x14003061f  lock inc dword ptr [rax+20h]
0x140030623  movzx   edx, byte ptr [rdi+200h]; NewIrql
0x14003062a  lea     rcx, [rdi+1F8h]; SpinLock
0x140030631  call    cs:__imp_KeReleaseSpinLock
0x140030638  nop     dword ptr [rax+rax+00h]
0x14003063d  or      dword ptr [rsi+1Ch], 2
0x140030641  inc     dword ptr [rbx+0D4h]
0x140030647  mov     eax, [rbx+0D4h]
0x14003064d  cmp     [rbx+0D0h], eax
0x140030653  jz      loc_14003085B
0x140030659  mov     rax, [r15+8]
0x14003065d  xor     ecx, ecx
0x14003065f  test    rax, rax
0x140030662  jz      short loc_140030672
0x140030664  add     r12d, [rax+18h]
0x140030668  inc     ecx
0x14003066a  mov     rax, [rax]
0x14003066d  test    rax, rax
0x140030670  jnz     short loc_140030664
0x140030672  add     [rbx+24Ch], ecx
0x140030678  add     [rbp+654h], ecx
0x14003067e  mov     rcx, 0FFFFF78000000008h
0x140030688  mov     eax, [rbx+2B8h]
0x14003068e  mov     edx, [rbx+244h]
0x140030694  shl     rax, 20h
0x140030698  mov     r8d, r12d
0x14003069b  add     rax, r8
0x14003069e  add     rdx, rax
0x1400306a1  mov     [rbx+244h], edx
0x1400306a7  shr     rdx, 20h
0x1400306ab  mov     [rbx+2B8h], edx
0x1400306b1  mov     eax, [rbp+6C0h]
0x1400306b7  mov     edx, [rbp+64Ch]
0x1400306bd  shl     rax, 20h
0x1400306c1  add     rax, r8
0x1400306c4  add     rdx, rax
0x1400306c7  mov     rax, rdx
0x1400306ca  mov     [rbp+64Ch], edx
0x1400306d0  shr     rax, 20h
0x1400306d4  mov     [rbp+6C0h], eax
0x1400306da  mov     rcx, [rcx]
0x1400306dd  mov     r8, [rbp+9C0h]
0x1400306e4  mov     rax, rcx
0x1400306e7  sub     rax, r8
0x1400306ea  cmp     rax, 989680h
0x1400306f0  jnb     loc_140030833
0x1400306f6  lea     rdi, [rbp+6E8h]
0x1400306fd  add     rbp, 6F0h
0x140030704  mov     rcx, rdi; SpinLock
0x140030707  movzx   edx, byte ptr [rbp+0]; NewIrql
0x14003070b  call    cs:__imp_KeReleaseSpinLock
0x140030712  nop     dword ptr [rax+rax+00h]
0x140030717  lea     rcx, [rbx+2E0h]; SpinLock
0x14003071e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030725  nop     dword ptr [rax+rax+00h]
0x14003072a  inc     dword ptr [rbx+20h]
0x14003072d  lea     rcx, [rbx+2E0h]; SpinLock
0x140030734  cmp     dword ptr [rbx+14h], 2
0x140030738  movzx   edx, al; NewIrql
0x14003073b  mov     [rbx+2E8h], al
0x140030741  jnz     loc_14003086D
0x140030747  call    cs:__imp_KeReleaseSpinLock
0x14003074e  nop     dword ptr [rax+rax+00h]
0x140030753  cmp     cs:gbSniffLink, 0
0x14003075a  jnz     loc_1400308F3
0x140030760  mov     rax, [rbx+38h]
0x140030764  xor     r8d, r8d; SendFlags
0x140030767  mov     [r15+78h], rax
0x14003076b  mov     rdx, r15; NetBufferLists
0x14003076e  mov     rcx, [rbx+38h]; NdisVcHandle
0x140030772  call    cs:__imp_NdisCoSendNetBufferLists
0x140030779  nop     dword ptr [rax+rax+00h]
0x14003077e  mov     rcx, rdi; SpinLock
0x140030781  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030788  nop     dword ptr [rax+rax+00h]
0x14003078d  mov     [rbp+0], al
0x140030790  mov     rcx, cs:WPP_GLOBAL_Control
0x140030797  cmp     rcx, r13
0x14003079a  jz      short loc_1400307A8
0x14003079c  mov     edx, [rcx+2Ch]
0x14003079f  test    dl, 8
0x1400307a2  jnz     loc_140030911
0x1400307a8  mov     eax, r12d
0x1400307ab  add     rsp, 38h
0x1400307af  pop     r15
0x1400307b1  pop     r14
0x1400307b3  pop     r13
0x1400307b5  pop     r12
0x1400307b7  pop     rdi
0x1400307b8  pop     rsi
0x1400307b9  pop     rbp
0x1400307ba  pop     rbx
0x1400307bb  retn
0x1400307bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307c4  cmp     rcx, r13
0x1400307c7  jnz     loc_1400308C4
0x1400307cd  movzx   edx, byte ptr [rdi+200h]; NewIrql
0x1400307d4  lea     rcx, [rdi+1F8h]; SpinLock
0x1400307db  call    cs:__imp_KeReleaseSpinLock
0x1400307e2  nop     dword ptr [rax+rax+00h]
0x1400307e7  lea     rdi, [rbp+6E8h]
0x1400307ee  add     rbp, 6F0h
0x1400307f5  mov     rcx, rdi; SpinLock
0x1400307f8  movzx   edx, byte ptr [rbp+0]; NewIrql
0x1400307fc  call    cs:__imp_KeReleaseSpinLock
0x140030803  nop     dword ptr [rax+rax+00h]
0x140030808  lea     rcx, [rbx+2E0h]; SpinLock
0x14003080f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030816  nop     dword ptr [rax+rax+00h]
0x14003081b  mov     edx, 0C023002Ah
0x140030820  mov     rcx, rsi
0x140030823  mov     [rbx+2E8h], al
0x140030829  call    CompleteSendDesc
0x14003082e  jmp     loc_14003077E
0x140030833  mov     rax, [rbp+9B8h]
0x14003083a  mov     [rbp+9A8h], rax
0x140030841  mov     [rbp+9B0h], r8
0x140030848  mov     [rbp+9B8h], rdx
0x14003084f  mov     [rbp+9C0h], rcx
0x140030856  jmp     loc_1400306F6
0x14003085b  mov     [rbx+0C9h], r12b
0x140030862  dec     dword ptr [rbp+9Ch]
0x140030868  jmp     loc_140030659
0x14003086d  call    cs:__imp_KeReleaseSpinLock
0x140030874  nop     dword ptr [rax+rax+00h]
0x140030879  mov     dword ptr [r15+8Ch], 0
0x140030884  xor     r8d, r8d
0x140030887  mov     rcx, [rbx+28h]
0x14003088b  mov     rdx, r15
0x14003088e  call    ProtoCoSendNetBufferListChainComplete
0x140030893  jmp     loc_14003077E
0x140030898  cmp     byte ptr [rcx+29h], 5
0x14003089c  jb      loc_1400305F5
0x1400308a2  mov     rcx, [rcx+18h]
0x1400308a6  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x1400308ad  mov     edx, 21h ; '!'
0x1400308b2  mov     [rsp+78h+var_58], r15
0x1400308b7  mov     r9, rbx
0x1400308ba  call    WPP_SF_qq
0x1400308bf  jmp     loc_1400305F5
0x1400308c4  mov     eax, [rcx+2Ch]
0x1400308c7  test    al, 10h
0x1400308c9  jz      loc_1400307CD
0x1400308cf  cmp     byte ptr [rcx+29h], 5
0x1400308d3  jb      loc_1400307CD
0x1400308d9  mov     rcx, [rcx+18h]
0x1400308dd  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x1400308e4  mov     edx, 22h ; '"'
0x1400308e9  call    WPP_SF_d
0x1400308ee  jmp     loc_1400307CD
0x1400308f3  cmp     cs:qword_14001E2D8, 0
0x1400308fb  jz      loc_140030760
0x140030901  mov     rdx, r15
0x140030904  mov     rcx, rbx
0x140030907  call    IndicatePromiscuousSendNBL
0x14003090c  jmp     loc_140030760
0x140030911  cmp     byte ptr [rcx+29h], 5
0x140030915  jb      loc_1400307A8
0x14003091b  mov     rcx, [rcx+18h]
0x14003091f  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140030926  mov     edx, 23h ; '#'
0x14003092b  call    WPP_SF_
0x140030930  jmp     loc_1400307A8
```
