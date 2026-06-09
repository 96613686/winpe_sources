# NatCreateDirector

- ea: `0x14000115c`
- end: `0x140001477`
- name: `NatCreateDirector`
- size: `795`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140002b38`
- `0x140019b50`

## callees

- `0x14000115c`
- `0x140001c90`
- `0x14000218c`
- `0x140002200`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400012b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400012b7`
- `ntoskrnl!ExAllocatePool2` at `0x140001243`
- `ntoskrnl!ExAllocatePool2` at `0x140001243`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001391`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001391`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001349`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001349`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000131a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000131a`

## pseudocode

```c
__int64 __fastcall NatCreateDirector(__int64 a1)
{
  bool v2; // zf
  __int64 Pool2; // rax
  _QWORD *v5; // rdi
  KIRQL v6; // si
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
  }
  v2 = *(_QWORD *)(a1 + 24) == 0;
  v9 = 0;
  *(_QWORD *)(a1 + 56) = 0;
  if ( !v2 || *(_QWORD *)(a1 + 32) || *(_QWORD *)(a1 + 40) || *(_QWORD *)(a1 + 48) )
  {
    Pool2 = ExAllocatePool2(64, 96, 1148477774);
    v5 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 24));
      *((_DWORD *)v5 + 5) = 1;
      *((_DWORD *)v5 + 12) = *(_DWORD *)(a1 + 4);
      *((_DWORD *)v5 + 4) = *(unsigned __int16 *)(a1 + 10) | (*(unsigned __int8 *)(a1 + 8) << 16);
      v5[5] = v5 + 4;
      v5[4] = v5 + 4;
      v5[7] = *(_QWORD *)(a1 + 16);
      v5[9] = *(_QWORD *)(a1 + 32);
      v5[10] = *(_QWORD *)(a1 + 40);
      v5[8] = *(_QWORD *)(a1 + 24);
      v5[11] = *(_QWORD *)(a1 + 48);
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
      if ( NatLookupDirector(*((unsigned int *)v5 + 4), &v9) )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine, v6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids,
            *(unsigned __int8 *)(a1 + 8),
            *(unsigned __int16 *)(a1 + 10));
        }
        ExFreePoolWithTag(v5, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
        }
        return 3221225473LL;
      }
      else
      {
        v7 = v9;
        v8 = *(_QWORD **)(v9 + 8);
        if ( *v8 != v9 )
          __fastfail(3u);
        v5[1] = v8;
        *v5 = v7;
        *v8 = v5;
        *(_QWORD *)(v7 + 8) = v5;
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine, v6);
        _InterlockedIncrement((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1);
        *(_QWORD *)(a1 + 56) = v5;
        *(_QWORD *)(a1 + 64) = NatDirectorQueryInfoSession;
        *(_QWORD *)(a1 + 72) = NatDirectorDeregister;
        *(_QWORD *)(a1 + 80) = &NatDirectorDissociateSession;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
        }
        return 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
        }
      }
      return 3221225495LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
      }
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000115c  mov     [rsp+arg_8], rbx
0x140001161  mov     [rsp+arg_10], rsi
0x140001166  push    rdi
0x140001167  push    r12
0x140001169  push    r14
0x14000116b  sub     rsp, 30h
0x14000116f  mov     rbx, rcx
0x140001172  mov     rcx, cs:WPP_GLOBAL_Control
0x140001179  lea     r12, WPP_GLOBAL_Control
0x140001180  lea     r14, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids
0x140001187  cmp     rcx, r12
0x14000118a  jz      short loc_1400011AA
0x14000118c  mov     eax, [rcx+2Ch]
0x14000118f  test    al, 1
0x140001191  jz      short loc_1400011AA
0x140001193  cmp     byte ptr [rcx+29h], 6
0x140001197  jb      short loc_1400011AA
0x140001199  mov     rcx, [rcx+18h]
0x14000119d  mov     edx, 0Ch
0x1400011a2  mov     r8, r14
0x1400011a5  call    WPP_SF_
0x1400011aa  cmp     qword ptr [rbx+18h], 0
0x1400011af  mov     [rsp+48h+arg_0], 0
0x1400011b8  mov     qword ptr [rbx+38h], 0
0x1400011c0  jnz     short loc_140001235
0x1400011c2  cmp     qword ptr [rbx+20h], 0
0x1400011c7  jnz     short loc_140001235
0x1400011c9  cmp     qword ptr [rbx+28h], 0
0x1400011ce  jnz     short loc_140001235
0x1400011d0  cmp     qword ptr [rbx+30h], 0
0x1400011d5  jnz     short loc_140001235
0x1400011d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011de  cmp     rcx, r12
0x1400011e1  jz      short loc_14000122B
0x1400011e3  mov     eax, [rcx+2Ch]
0x1400011e6  test    al, 1
0x1400011e8  jz      short loc_140001201
0x1400011ea  cmp     byte ptr [rcx+29h], 2
0x1400011ee  jb      short loc_140001201
0x1400011f0  mov     rcx, [rcx+18h]
0x1400011f4  mov     edx, 0Dh
0x1400011f9  mov     r8, r14
0x1400011fc  call    WPP_SF_
0x140001201  mov     rcx, cs:WPP_GLOBAL_Control
0x140001208  cmp     rcx, r12
0x14000120b  jz      short loc_14000122B
0x14000120d  mov     eax, [rcx+2Ch]
0x140001210  test    al, 1
0x140001212  jz      short loc_14000122B
0x140001214  cmp     byte ptr [rcx+29h], 6
0x140001218  jb      short loc_14000122B
0x14000121a  mov     rcx, [rcx+18h]
0x14000121e  mov     edx, 0Eh
0x140001223  mov     r8, r14
0x140001226  call    WPP_SF_
0x14000122b  mov     eax, 0C000000Dh
0x140001230  jmp     loc_140001462
0x140001235  mov     edx, 60h ; '`'
0x14000123a  mov     r8d, 4474614Eh
0x140001240  lea     ecx, [rdx-20h]
0x140001243  call    cs:__imp_ExAllocatePool2
0x14000124a  nop     dword ptr [rax+rax+00h]
0x14000124f  mov     rdi, rax
0x140001252  test    rax, rax
0x140001255  jnz     short loc_1400012B3
0x140001257  mov     rcx, cs:WPP_GLOBAL_Control
0x14000125e  cmp     rcx, r12
0x140001261  jz      short loc_1400012A9
0x140001263  mov     eax, [rcx+2Ch]
0x140001266  test    al, 1
0x140001268  jz      short loc_14000127F
0x14000126a  cmp     byte ptr [rcx+29h], 2
0x14000126e  jb      short loc_14000127F
0x140001270  mov     rcx, [rcx+18h]
0x140001274  lea     edx, [rdi+0Fh]
0x140001277  mov     r8, r14
0x14000127a  call    WPP_SF_
0x14000127f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001286  cmp     rcx, r12
0x140001289  jz      short loc_1400012A9
0x14000128b  mov     eax, [rcx+2Ch]
0x14000128e  test    al, 1
0x140001290  jz      short loc_1400012A9
0x140001292  cmp     byte ptr [rcx+29h], 6
0x140001296  jb      short loc_1400012A9
0x140001298  mov     rcx, [rcx+18h]
0x14000129c  mov     edx, 10h
0x1400012a1  mov     r8, r14
0x1400012a4  call    WPP_SF_
0x1400012a9  mov     eax, 0C0000017h
0x1400012ae  jmp     loc_140001462
0x1400012b3  lea     rcx, [rax+18h]; SpinLock
0x1400012b7  call    cs:__imp_KeInitializeSpinLock
0x1400012be  nop     dword ptr [rax+rax+00h]
0x1400012c3  mov     dword ptr [rdi+14h], 1
0x1400012ca  mov     eax, [rbx+4]
0x1400012cd  mov     [rdi+30h], eax
0x1400012d0  movzx   ecx, byte ptr [rbx+8]
0x1400012d4  movzx   eax, word ptr [rbx+0Ah]
0x1400012d8  shl     ecx, 10h
0x1400012db  or      ecx, eax
0x1400012dd  lea     rax, [rdi+20h]
0x1400012e1  mov     [rdi+10h], ecx
0x1400012e4  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x1400012eb  mov     [rax+8], rax
0x1400012ef  mov     [rax], rax
0x1400012f2  mov     rax, [rbx+10h]
0x1400012f6  mov     [rdi+38h], rax
0x1400012fa  mov     rax, [rbx+20h]
0x1400012fe  mov     [rdi+48h], rax
0x140001302  mov     rax, [rbx+28h]
0x140001306  mov     [rdi+50h], rax
0x14000130a  mov     rax, [rbx+18h]
0x14000130e  mov     [rdi+40h], rax
0x140001312  mov     rax, [rbx+30h]
0x140001316  mov     [rdi+58h], rax
0x14000131a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001321  nop     dword ptr [rax+rax+00h]
0x140001326  mov     ecx, [rdi+10h]
0x140001329  lea     rdx, [rsp+48h+arg_0]
0x14000132e  mov     sil, al
0x140001331  call    NatLookupDirector
0x140001336  test    rax, rax
0x140001339  jz      loc_1400013D1
0x14000133f  mov     dl, sil; NewIrql
0x140001342  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x140001349  call    cs:__imp_KeReleaseSpinLock
0x140001350  nop     dword ptr [rax+rax+00h]
0x140001355  mov     rcx, cs:WPP_GLOBAL_Control
0x14000135c  cmp     rcx, r12
0x14000135f  jz      short loc_14000138C
0x140001361  mov     eax, [rcx+2Ch]
0x140001364  test    al, 1
0x140001366  jz      short loc_14000138C
0x140001368  cmp     byte ptr [rcx+29h], 2
0x14000136c  jb      short loc_14000138C
0x14000136e  movzx   eax, word ptr [rbx+0Ah]
0x140001372  mov     edx, 11h
0x140001377  movzx   r9d, byte ptr [rbx+8]
0x14000137c  mov     r8, r14
0x14000137f  mov     rcx, [rcx+18h]
0x140001383  mov     [rsp+48h+var_28], eax
0x140001387  call    WPP_SF_dd
0x14000138c  xor     edx, edx; Tag
0x14000138e  mov     rcx, rdi; P
0x140001391  call    cs:__imp_ExFreePoolWithTag
0x140001398  nop     dword ptr [rax+rax+00h]
0x14000139d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400013a4  cmp     rcx, r12
0x1400013a7  jz      short loc_1400013C7
0x1400013a9  mov     eax, [rcx+2Ch]
0x1400013ac  test    al, 1
0x1400013ae  jz      short loc_1400013C7
0x1400013b0  cmp     byte ptr [rcx+29h], 6
0x1400013b4  jb      short loc_1400013C7
0x1400013b6  mov     rcx, [rcx+18h]
0x1400013ba  mov     edx, 12h
0x1400013bf  mov     r8, r14
0x1400013c2  call    WPP_SF_
0x1400013c7  mov     eax, 0C0000001h
0x1400013cc  jmp     loc_140001462
0x1400013d1  mov     rax, [rsp+48h+arg_0]
0x1400013d6  mov     rcx, [rax+8]
0x1400013da  cmp     [rcx], rax
0x1400013dd  jz      short loc_1400013E6
0x1400013df  mov     ecx, 3
0x1400013e4  int     29h; Win8: RtlFailFast(ecx)
0x1400013e6  mov     [rdi+8], rcx
0x1400013ea  mov     dl, sil; NewIrql
0x1400013ed  mov     [rdi], rax
0x1400013f0  mov     [rcx], rdi
0x1400013f3  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x1400013fa  mov     [rax+8], rdi
0x1400013fe  call    cs:__imp_KeReleaseSpinLock
0x140001405  nop     dword ptr [rax+rax+00h]
0x14000140a  lock inc dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x140001411  lea     rax, NatDirectorQueryInfoSession
0x140001418  mov     [rbx+38h], rdi
0x14000141c  mov     [rbx+40h], rax
0x140001420  lea     rax, NatDirectorDeregister
0x140001427  mov     [rbx+48h], rax
0x14000142b  lea     rax, NatDirectorDissociateSession
0x140001432  mov     [rbx+50h], rax
0x140001436  mov     rcx, cs:WPP_GLOBAL_Control
0x14000143d  cmp     rcx, r12
0x140001440  jz      short loc_140001460
0x140001442  mov     eax, [rcx+2Ch]
0x140001445  test    al, 1
0x140001447  jz      short loc_140001460
0x140001449  cmp     byte ptr [rcx+29h], 6
0x14000144d  jb      short loc_140001460
0x14000144f  mov     rcx, [rcx+18h]
0x140001453  mov     edx, 13h
0x140001458  mov     r8, r14
0x14000145b  call    WPP_SF_
0x140001460  xor     eax, eax
0x140001462  mov     rbx, [rsp+48h+arg_8]
0x140001467  mov     rsi, [rsp+48h+arg_10]
0x14000146c  add     rsp, 30h
0x140001470  pop     r14
0x140001472  pop     r12
0x140001474  pop     rdi
0x140001475  retn
```
