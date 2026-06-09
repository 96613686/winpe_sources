# L2TPAddHostRoute

- ea: `0x1400100d0`
- end: `0x140010299`
- name: `L2TPAddHostRoute`
- size: `457`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140001850`
- `0x140003050`
- `0x1400031ec`
- `0x1400100d0`
- `0x1400102a0`
- `0x140018d0c`
- `0x14001c050`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010282`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010282`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010126`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010126`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001022b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001022b`

## pseudocode

```c
void __fastcall L2TPAddHostRoute(PVOID Entry, __int64 a2)
{
  PDEVICE_OBJECT v4; // rcx
  _QWORD **v5; // rdi
  _QWORD *v6; // rdx
  _QWORD *v7; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids);
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  if ( (*(_DWORD *)(a2 + 120) & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids);
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids);
    }
    if ( !(unsigned __int8)TransportAddHostRoute(v4, a2 + 48) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids, a2);
      }
      ScheduleTunnelWork(a2, 0, (__int64)FsmCloseTunnel, 2, 4, 0, 0, 0);
      return;
    }
  }
  SetFlags(a2 + 120, 16);
  *(_BYTE *)(a2 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v5 = (_QWORD **)(a2 + 128);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == v5 )
      break;
    if ( (_QWORD **)v6[1] != v5 || (v7 = (_QWORD *)*v6, *(_QWORD **)(*v6 + 8LL) != v6) )
      __fastfail(3u);
    *v5 = v7;
    v7[1] = v5;
    v6[1] = v6;
    *v6 = v6;
    FsmOpenCall(a2, v6 - 12);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
}

```

## disassembly

```asm
0x1400100d0  push    rbx
0x1400100d2  push    rsi
0x1400100d3  push    rdi
0x1400100d4  push    r15
0x1400100d6  sub     rsp, 58h
0x1400100da  mov     rbx, rdx
0x1400100dd  mov     rdi, rcx
0x1400100e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400100e7  lea     r15, WPP_GLOBAL_Control
0x1400100ee  mov     esi, 4
0x1400100f3  cmp     rcx, r15
0x1400100f6  jz      short loc_140010118
0x1400100f8  mov     eax, [rcx+2Ch]
0x1400100fb  test    al, 40h
0x1400100fd  jz      short loc_140010118
0x1400100ff  cmp     [rcx+29h], sil
0x140010103  jb      short loc_140010118
0x140010105  mov     rcx, [rcx+18h]
0x140010109  lea     edx, [rsi+6]
0x14001010c  lea     r8, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids
0x140010113  call    WPP_SF_
0x140010118  mov     rcx, [rbx+18h]
0x14001011c  mov     rdx, rdi; Entry
0x14001011f  add     rcx, 3C0h; Lookaside
0x140010126  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001012d  nop     dword ptr [rax+rax+00h]
0x140010132  mov     eax, [rbx+78h]
0x140010135  test    sil, al
0x140010138  jnz     loc_1400101EB
0x14001013e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010145  cmp     rcx, r15
0x140010148  jz      short loc_14001016C
0x14001014a  mov     eax, [rcx+2Ch]
0x14001014d  test    al, 40h
0x14001014f  jz      short loc_14001016C
0x140010151  cmp     [rcx+29h], sil
0x140010155  jb      short loc_14001016C
0x140010157  mov     rcx, [rcx+18h]
0x14001015b  lea     r8, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids
0x140010162  mov     edx, 0Bh
0x140010167  call    WPP_SF_
0x14001016c  lea     rdx, [rbx+30h]
0x140010170  call    TransportAddHostRoute
0x140010175  test    al, al
0x140010177  jnz     loc_140010219
0x14001017d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010184  cmp     rcx, r15
0x140010187  jz      short loc_1400101AE
0x140010189  mov     eax, [rcx+2Ch]
0x14001018c  test    al, 40h
0x14001018e  jz      short loc_1400101AE
0x140010190  cmp     [rcx+29h], sil
0x140010194  jb      short loc_1400101AE
0x140010196  mov     rcx, [rcx+18h]
0x14001019a  lea     r8, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids
0x1400101a1  mov     edx, 0Ch
0x1400101a6  mov     r9, rbx
0x1400101a9  call    WPP_SF_q
0x1400101ae  mov     [rsp+78h+var_38], 0
0x1400101b3  lea     r8, FsmCloseTunnel
0x1400101ba  mov     [rsp+78h+var_40], 0
0x1400101bf  mov     r9d, 2
0x1400101c5  mov     [rsp+78h+var_48], 0
0x1400101ce  xor     edx, edx
0x1400101d0  mov     [rsp+78h+var_50], 0
0x1400101d9  mov     rcx, rbx
0x1400101dc  mov     [rsp+78h+var_58], rsi
0x1400101e1  call    ScheduleTunnelWork
0x1400101e6  jmp     loc_14001028E
0x1400101eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400101f2  cmp     rcx, r15
0x1400101f5  jz      short loc_140010219
0x1400101f7  mov     eax, [rcx+2Ch]
0x1400101fa  test    al, 40h
0x1400101fc  jz      short loc_140010219
0x1400101fe  cmp     [rcx+29h], sil
0x140010202  jb      short loc_140010219
0x140010204  mov     rcx, [rcx+18h]
0x140010208  lea     r8, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids
0x14001020f  mov     edx, 0Dh
0x140010214  call    WPP_SF_
0x140010219  mov     edx, 10h
0x14001021e  lea     rcx, [rbx+78h]
0x140010222  call    SetFlags
0x140010227  lea     rcx, [rbx+20h]; SpinLock
0x14001022b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010232  nop     dword ptr [rax+rax+00h]
0x140010237  mov     [rbx+28h], al
0x14001023a  lea     rdi, [rbx+80h]
0x140010241  mov     rdx, [rdi]
0x140010244  cmp     rdx, rdi
0x140010247  jz      short loc_14001027B
0x140010249  cmp     [rdx+8], rdi
0x14001024d  jnz     short loc_140010274
0x14001024f  mov     rax, [rdx]
0x140010252  cmp     [rax+8], rdx
0x140010256  jnz     short loc_140010274
0x140010258  mov     [rdi], rax
0x14001025b  mov     rcx, rbx
0x14001025e  mov     [rax+8], rdi
0x140010262  mov     [rdx+8], rdx
0x140010266  mov     [rdx], rdx
0x140010269  add     rdx, 0FFFFFFFFFFFFFFA0h
0x14001026d  call    FsmOpenCall
0x140010272  jmp     short loc_140010241
0x140010274  mov     ecx, 3
0x140010279  int     29h; Win8: RtlFailFast(ecx)
0x14001027b  mov     dl, [rbx+28h]; NewIrql
0x14001027e  lea     rcx, [rbx+20h]; SpinLock
0x140010282  call    cs:__imp_KeReleaseSpinLock
0x140010289  nop     dword ptr [rax+rax+00h]
0x14001028e  add     rsp, 58h
0x140010292  pop     r15
0x140010294  pop     rdi
0x140010295  pop     rsi
0x140010296  pop     rbx
0x140010297  retn
```
