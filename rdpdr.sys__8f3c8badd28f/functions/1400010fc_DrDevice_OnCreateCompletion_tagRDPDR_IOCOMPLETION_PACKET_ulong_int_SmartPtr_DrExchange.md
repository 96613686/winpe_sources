# DrDevice::OnCreateCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x1400010fc`
- end: `0x140001306`
- name: `?OnCreateCompletion@DrDevice@@QEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140022ab0`

## callees

- `0x1400010fc`
- `0x140001310`
- `0x140001660`
- `0x1400016a0`
- `0x140001830`
- `0x14000324c`
- `0x1400032c0`
- `0x140003940`
- `0x1400117e0`
- `0x140016420`
- `0x140024020`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400011a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400011a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400011d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400011d3`

## pseudocode

```c
__int64 __fastcall DrDevice::OnCreateCompletion(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, __int64 a5)
{
  RefCount *v5; // rdi
  RefCount *v6; // rbx
  _QWORD *v11; // rbp
  unsigned int v12; // ebx
  KIRQL v13; // bl
  unsigned __int64 v14; // rdx
  void *v15; // rax
  unsigned int v16; // r9d
  RefCount *v18; // [rsp+30h] [rbp-58h] BYREF
  RefCount *v19[10]; // [rsp+38h] [rbp-50h] BYREF

  v5 = 0;
  v6 = 0;
  v18 = 0;
  v19[0] = 0;
  v11 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)a5 + 32LL) + 48LL);
  if ( a3 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v12 = -1073741434;
    if ( v11 )
      DrDevice::CompleteBusyExchange(a1, a5, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, a5);
    *a4 = 0;
    goto LABEL_21;
  }
  if ( v11 )
  {
    v13 = KeAcquireSpinLockRaiseToDpc(&DrSpinLock);
    SmartPtr<DrDevice>::operator=(&v18, *(_QWORD *)(v11[82] + 40LL));
    KeReleaseSpinLock(&DrSpinLock, v13);
    v15 = TopObj::operator new(0xD8u, v14);
    if ( v15 )
      v15 = (void *)DrFile::DrFile(v15, &v18, *(unsigned int *)(a2 + 16));
    SmartPtr<VirtualChannel>::operator=(v19, v15);
    v6 = v19[0];
    if ( !v19[0] )
    {
      v12 = -1073741670;
      DrDevice::CompleteBusyExchange(a1, a5, -1073741670, 0);
LABEL_21:
      SmartPtr<DrFile>::~SmartPtr<DrFile>(v19);
      SmartPtr<DrFile>::~SmartPtr<DrFile>(&v18);
      goto LABEL_28;
    }
    _InterlockedIncrement((volatile signed __int32 *)v19[0] + 4);
    *(_QWORD *)(v11[8] + 64LL) = v6;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        74,
        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
        *(unsigned int *)(a2 + 12),
        *(unsigned __int8 *)(a2 + 20));
    if ( a3 < 0x15 )
    {
      v11[75] = 0;
      v16 = 0;
    }
    else
    {
      v11[75] = *(unsigned __int8 *)(a2 + 20);
      v16 = *(unsigned __int8 *)(a2 + 20);
    }
    DrDevice::CompleteBusyExchange(a1, a5, *(_DWORD *)(a2 + 12), v16);
    v5 = v18;
  }
  else
  {
    DrDevice::DiscardBusyExchange(a1, a5);
  }
  if ( v6 )
    RefCount::Release(v6);
  if ( v5 )
    RefCount::Release(v5);
  v12 = 0;
LABEL_28:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return v12;
}

```

## disassembly

```asm
0x1400010fc  push    rbx
0x1400010fe  push    rbp
0x1400010ff  push    rsi
0x140001100  push    rdi
0x140001101  push    r12
0x140001103  push    r13
0x140001105  push    r14
0x140001107  push    r15
0x140001109  sub     rsp, 48h
0x14000110d  mov     rsi, [rsp+88h+arg_20]
0x140001115  xor     edi, edi
0x140001117  xor     ebx, ebx
0x140001119  mov     [rsp+88h+var_58], rdi
0x14000111e  mov     [rsp+88h+var_50], rbx
0x140001123  mov     r12, r9
0x140001126  mov     r13d, r8d
0x140001129  mov     r14, rdx
0x14000112c  mov     rax, [rsi]
0x14000112f  mov     r15, rcx
0x140001132  mov     r10, [rax+20h]
0x140001136  mov     rbp, [r10+30h]
0x14000113a  cmp     r8d, 14h
0x14000113e  jnb     short loc_140001197
0x140001140  mov     rcx, cs:WPP_GLOBAL_Control
0x140001147  lea     rax, WPP_GLOBAL_Control
0x14000114e  cmp     rcx, rax
0x140001151  jz      short loc_14000116C
0x140001153  cmp     byte ptr [rcx+29h], 2
0x140001157  jb      short loc_14000116C
0x140001159  mov     rcx, [rcx+18h]
0x14000115d  lea     edx, [rdi+49h]
0x140001160  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140001167  call    WPP_SF_
0x14000116c  mov     ebx, 0C0000186h
0x140001171  mov     rdx, rsi
0x140001174  mov     rcx, r15
0x140001177  test    rbp, rbp
0x14000117a  jz      short loc_140001189
0x14000117c  xor     r9d, r9d
0x14000117f  mov     r8d, ebx
0x140001182  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140001187  jmp     short loc_14000118E
0x140001189  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x14000118e  mov     [r12], edi
0x140001192  jmp     loc_1400012B0
0x140001197  test    rbp, rbp
0x14000119a  jz      loc_1400012C6
0x1400011a0  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x1400011a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400011ae  nop     dword ptr [rax+rax+00h]
0x1400011b3  mov     rdx, [rbp+290h]
0x1400011ba  lea     rcx, [rsp+88h+var_58]
0x1400011bf  mov     bl, al
0x1400011c1  mov     rdx, [rdx+28h]
0x1400011c5  call    ??4?$SmartPtr@VDrDevice@@@@QEAAAEAV0@PEAVDrDevice@@@Z; SmartPtr<DrDevice>::operator=(DrDevice *)
0x1400011ca  mov     dl, bl; NewIrql
0x1400011cc  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x1400011d3  call    cs:__imp_KeReleaseSpinLock
0x1400011da  nop     dword ptr [rax+rax+00h]
0x1400011df  mov     ecx, 0D8h; unsigned __int64
0x1400011e4  call    ??2TopObj@@SAPEAX_K0@Z; TopObj::operator new(unsigned __int64,unsigned __int64)
0x1400011e9  test    rax, rax
0x1400011ec  jz      short loc_1400011FF
0x1400011ee  mov     r8d, [r14+10h]
0x1400011f2  lea     rdx, [rsp+88h+var_58]
0x1400011f7  mov     rcx, rax
0x1400011fa  call    ??0DrFile@@QEAA@AEAV?$SmartPtr@VDrDevice@@@@K@Z; DrFile::DrFile(SmartPtr<DrDevice> &,ulong)
0x1400011ff  mov     rdx, rax
0x140001202  lea     rcx, [rsp+88h+var_50]
0x140001207  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x14000120c  mov     rbx, [rsp+88h+var_50]
0x140001211  test    rbx, rbx
0x140001214  jz      loc_14000129A
0x14000121a  lock inc dword ptr [rbx+10h]
0x14000121e  mov     rax, [rbp+40h]
0x140001222  mov     [rax+40h], rbx
0x140001226  mov     rcx, cs:WPP_GLOBAL_Control
0x14000122d  lea     rax, WPP_GLOBAL_Control
0x140001234  cmp     rcx, rax
0x140001237  jz      short loc_140001261
0x140001239  cmp     byte ptr [rcx+29h], 5
0x14000123d  jb      short loc_140001261
0x14000123f  movzx   eax, byte ptr [r14+14h]
0x140001244  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14000124b  mov     r9d, [r14+0Ch]
0x14000124f  mov     edx, 4Ah ; 'J'
0x140001254  mov     rcx, [rcx+18h]
0x140001258  mov     [rsp+88h+var_68], eax
0x14000125c  call    WPP_SF_dd
0x140001261  cmp     r13d, 15h
0x140001265  jb      short loc_14000127A
0x140001267  movzx   eax, byte ptr [r14+14h]
0x14000126c  mov     [rbp+258h], rax
0x140001273  movzx   r9d, byte ptr [r14+14h]
0x140001278  jmp     short loc_140001284
0x14000127a  mov     [rbp+258h], rdi
0x140001281  xor     r9d, r9d
0x140001284  mov     r8d, [r14+0Ch]
0x140001288  mov     rdx, rsi
0x14000128b  mov     rcx, r15
0x14000128e  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140001293  mov     rdi, [rsp+88h+var_58]
0x140001298  jmp     short loc_1400012CE
0x14000129a  mov     ebx, 0C000009Ah
0x14000129f  xor     r9d, r9d
0x1400012a2  mov     r8d, ebx
0x1400012a5  mov     rdx, rsi
0x1400012a8  mov     rcx, r15
0x1400012ab  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400012b0  lea     rcx, [rsp+88h+var_50]
0x1400012b5  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400012ba  lea     rcx, [rsp+88h+var_58]
0x1400012bf  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400012c4  jmp     short loc_1400012EA
0x1400012c6  mov     rdx, rsi
0x1400012c9  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x1400012ce  test    rbx, rbx
0x1400012d1  jz      short loc_1400012DB
0x1400012d3  mov     rcx, rbx; this
0x1400012d6  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400012db  test    rdi, rdi
0x1400012de  jz      short loc_1400012E8
0x1400012e0  mov     rcx, rdi; this
0x1400012e3  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400012e8  xor     ebx, ebx
0x1400012ea  mov     rcx, rsi
0x1400012ed  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400012f2  mov     eax, ebx
0x1400012f4  add     rsp, 48h
0x1400012f8  pop     r15
0x1400012fa  pop     r14
0x1400012fc  pop     r13
0x1400012fe  pop     r12
0x140001300  pop     rdi
0x140001301  pop     rsi
0x140001302  pop     rbp
0x140001303  pop     rbx
0x140001304  retn
```
