# CtlConnectCompleteCallback

- ea: `0x1400122b0`
- end: `0x1400125cd`
- name: `CtlConnectCompleteCallback`
- size: `797`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x140001a70`
- `0x1400028f0`
- `0x140003d58`
- `0x140003e08`
- `0x140003e38`
- `0x140004204`
- `0x140004248`
- `0x140004508`
- `0x140004db8`
- `0x1400076d0`
- `0x140007710`
- `0x140010250`
- `0x140011c00`
- `0x1400122b0`
- `0x1400131e4`
- `0x1400157f4`
- `0x14001587c`
- `0x14001c414`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001237a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001237a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001235e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001235e`

## pseudocode

```c
__int64 __fastcall CtlConnectCompleteCallback(__int64 a1, __int64 a2, unsigned int a3)
{
  int v6; // r9d
  KIRQL v7; // al
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  int StringFromSockAddr; // eax
  unsigned int LocalAddress; // eax
  int v11; // ebx
  struct _DEVICE_OBJECT *v12; // rbx
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rbx
  __int64 v17; // rax
  __int128 v19; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-90h]
  _BYTE v21[80]; // [rsp+50h] [rbp-88h] BYREF

  if ( a1 && *(_DWORD *)(a1 + 32) == 1414550608 )
  {
    v6 = *(_DWORD *)(a1 + 48);
    if ( v6 == 2 )
    {
      if ( !a3 )
      {
        v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
        *(_QWORD *)(a1 + 136) = a2;
        *(_BYTE *)(a1 + 104) = v7;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v7);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
            StringFromSockAddr = GetStringFromSockAddr(a1 + 368, v21);
            WPP_SF_sq(
              (_DWORD)AttachedDevice,
              72,
              (unsigned int)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids,
              StringFromSockAddr,
              a1);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
          }
        }
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
        LocalAddress = GetLocalAddress(*(_QWORD *)(a1 + 136), a1 + 536);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            74,
            WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids,
            LocalAddress);
        }
        v11 = 0;
        goto LABEL_35;
      }
      v19 = 0;
      v20 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v12 = WPP_GLOBAL_Control->AttachedDevice;
        v13 = GetStringFromSockAddr(a1 + 368, v21);
        WPP_SF_sqD((_DWORD)v12, v14, v15, v13, a1, a3);
      }
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
      v19 = 0u;
      LODWORD(v20) = 1297436229;
      while ( 1 )
      {
        v17 = EnumListEntry(a1 + 56, &v19, *(_QWORD *)(a1 + 40) + 8LL, 0);
        if ( !v17 )
          break;
        v16 = v17 - 16;
        if ( v17 != 16 && *(_DWORD *)(v16 + 48) == 1129337936 )
        {
          CallEventConnectFailure(v17 - 16, a3);
          DereferenceRefCount(v16);
        }
      }
      EnumComplete(&v19, *(_QWORD *)(a1 + 40) + 8LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(a1 + 24))(a1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, a1, v6);
      }
      CtlSetState(a1, 7);
      CtlCleanup(a1, 0);
    }
    v11 = -1073741823;
LABEL_35:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a1 + 24))(a1);
    if ( v11 >= 0 )
      ScheduleWorkItem(ScheduleAddHostRoute, a1, 0, 0);
    return (unsigned int)v11;
  }
  v11 = -1073741823;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, a1);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400122b0  push    rbx
0x1400122b2  push    rbp
0x1400122b3  push    rsi
0x1400122b4  push    rdi
0x1400122b5  sub     rsp, 0B8h
0x1400122bc  mov     rax, cs:__security_cookie
0x1400122c3  xor     rax, rsp
0x1400122c6  mov     [rsp+0D8h+var_38], rax
0x1400122ce  mov     ebp, r8d
0x1400122d1  mov     rsi, rdx
0x1400122d4  mov     rdi, rcx
0x1400122d7  test    rcx, rcx
0x1400122da  jz      loc_140012571
0x1400122e0  cmp     dword ptr [rcx+20h], 54505450h
0x1400122e7  jnz     loc_140012571
0x1400122ed  mov     r9d, [rcx+30h]
0x1400122f1  cmp     r9d, 2
0x1400122f5  jz      short loc_140012352
0x1400122f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122fe  lea     rsi, WPP_GLOBAL_Control
0x140012305  cmp     rcx, rsi
0x140012308  jz      short loc_140012334
0x14001230a  mov     eax, [rcx+2Ch]
0x14001230d  test    al, 2
0x14001230f  jz      short loc_140012334
0x140012311  cmp     byte ptr [rcx+29h], 1
0x140012315  jb      short loc_140012334
0x140012317  mov     rcx, [rcx+18h]
0x14001231b  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140012322  mov     dword ptr [rsp+0D8h+var_B8], r9d
0x140012327  mov     edx, 47h ; 'G'
0x14001232c  mov     r9, rdi
0x14001232f  call    WPP_SF_qd
0x140012334  xor     r9d, r9d
0x140012337  mov     rcx, rdi
0x14001233a  lea     edx, [r9+7]
0x14001233e  call    CtlSetState
0x140012343  xor     edx, edx
0x140012345  mov     rcx, rdi
0x140012348  call    CtlCleanup
0x14001234d  jmp     loc_140012538
0x140012352  test    ebp, ebp
0x140012354  jnz     loc_140012453
0x14001235a  add     rcx, 60h ; '`'; SpinLock
0x14001235e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012365  nop     dword ptr [rax+rax+00h]
0x14001236a  lea     rcx, [rdi+60h]; SpinLock
0x14001236e  mov     [rdi+88h], rsi
0x140012375  mov     dl, al; NewIrql
0x140012377  mov     [rdi+68h], al
0x14001237a  call    cs:__imp_KeReleaseSpinLock
0x140012381  nop     dword ptr [rax+rax+00h]
0x140012386  mov     rbx, cs:WPP_GLOBAL_Control
0x14001238d  lea     rsi, WPP_GLOBAL_Control
0x140012394  cmp     rbx, rsi
0x140012397  jz      short loc_140012403
0x140012399  mov     eax, [rbx+2Ch]
0x14001239c  test    al, 2
0x14001239e  jz      short loc_1400123D5
0x1400123a0  cmp     byte ptr [rbx+29h], 2
0x1400123a4  jb      short loc_1400123D5
0x1400123a6  mov     rbx, [rbx+18h]
0x1400123aa  lea     rcx, [rdi+170h]
0x1400123b1  lea     rdx, [rsp+0D8h+var_88]
0x1400123b6  call    GetStringFromSockAddr
0x1400123bb  mov     r9, rax
0x1400123be  mov     [rsp+0D8h+var_B8], rdi
0x1400123c3  lea     edx, [rbp+48h]
0x1400123c6  mov     rcx, rbx
0x1400123c9  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x1400123d0  call    WPP_SF_sq
0x1400123d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123dc  cmp     rcx, rsi
0x1400123df  jz      short loc_140012403
0x1400123e1  mov     eax, [rcx+2Ch]
0x1400123e4  test    al, 8
0x1400123e6  jz      short loc_140012403
0x1400123e8  cmp     byte ptr [rcx+29h], 1
0x1400123ec  jb      short loc_140012403
0x1400123ee  mov     rcx, [rcx+18h]
0x1400123f2  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x1400123f9  mov     edx, 49h ; 'I'
0x1400123fe  call    WPP_SF_
0x140012403  lock inc dword ptr [rdi+10h]
0x140012407  mov     rcx, [rdi+88h]
0x14001240e  lea     rdx, [rdi+218h]
0x140012415  call    GetLocalAddress
0x14001241a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012421  cmp     rcx, rsi
0x140012424  jz      short loc_14001244C
0x140012426  mov     edx, [rcx+2Ch]
0x140012429  test    dl, 8
0x14001242c  jz      short loc_14001244C
0x14001242e  cmp     byte ptr [rcx+29h], 1
0x140012432  jb      short loc_14001244C
0x140012434  mov     rcx, [rcx+18h]
0x140012438  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x14001243f  mov     edx, 4Ah ; 'J'
0x140012444  mov     r9d, eax
0x140012447  call    WPP_SF_d
0x14001244c  xor     ebx, ebx
0x14001244e  jmp     loc_14001253D
0x140012453  xorps   xmm0, xmm0
0x140012456  xor     eax, eax
0x140012458  movups  [rsp+0D8h+var_A0], xmm0
0x14001245d  mov     [rsp+0D8h+var_90], rax
0x140012462  mov     rbx, cs:WPP_GLOBAL_Control
0x140012469  lea     rsi, WPP_GLOBAL_Control
0x140012470  cmp     rbx, rsi
0x140012473  jz      short loc_1400124AB
0x140012475  mov     eax, [rbx+2Ch]
0x140012478  test    al, 2
0x14001247a  jz      short loc_1400124AB
0x14001247c  cmp     byte ptr [rbx+29h], 1
0x140012480  jb      short loc_1400124AB
0x140012482  mov     rbx, [rbx+18h]
0x140012486  lea     rdx, [rsp+0D8h+var_88]
0x14001248b  add     rcx, 170h
0x140012492  call    GetStringFromSockAddr
0x140012497  mov     r9, rax
0x14001249a  mov     [rsp+0D8h+var_B0], ebp
0x14001249e  mov     rcx, rbx
0x1400124a1  mov     [rsp+0D8h+var_B8], rdi
0x1400124a6  call    WPP_SF_sqD
0x1400124ab  lock inc dword ptr [rdi+10h]
0x1400124af  mov     qword ptr [rsp+0D8h+var_A0+8], 0
0x1400124b8  mov     qword ptr [rsp+0D8h+var_A0], 0
0x1400124c1  mov     dword ptr [rsp+0D8h+var_90], 4D554E45h
0x1400124c9  jmp     short loc_1400124EF
0x1400124cb  lea     rbx, [rax-10h]
0x1400124cf  test    rbx, rbx
0x1400124d2  jz      short loc_1400124EF
0x1400124d4  cmp     dword ptr [rbx+30h], 43505450h
0x1400124db  jnz     short loc_1400124EF
0x1400124dd  mov     edx, ebp
0x1400124df  mov     rcx, rbx
0x1400124e2  call    CallEventConnectFailure
0x1400124e7  mov     rcx, rbx
0x1400124ea  call    DereferenceRefCount
0x1400124ef  mov     r8, [rdi+28h]
0x1400124f3  lea     rdx, [rsp+0D8h+var_A0]
0x1400124f8  add     r8, 8
0x1400124fc  lea     rcx, [rdi+38h]
0x140012500  xor     r9d, r9d
0x140012503  call    EnumListEntry
0x140012508  test    rax, rax
0x14001250b  jnz     short loc_1400124CB
0x14001250d  mov     rdx, [rdi+28h]
0x140012511  lea     rcx, [rsp+0D8h+var_A0]
0x140012516  add     rdx, 8
0x14001251a  call    EnumComplete
0x14001251f  or      eax, 0FFFFFFFFh
0x140012522  lock xadd [rdi+10h], eax
0x140012527  cmp     eax, 1
0x14001252a  jnz     short loc_140012538
0x14001252c  mov     rax, [rdi+18h]
0x140012530  mov     rcx, rdi
0x140012533  call    _guard_dispatch_icall
0x140012538  mov     ebx, 0C0000001h
0x14001253d  or      eax, 0FFFFFFFFh
0x140012540  lock xadd [rdi+10h], eax
0x140012545  cmp     eax, 1
0x140012548  jnz     short loc_140012556
0x14001254a  mov     rax, [rdi+18h]
0x14001254e  mov     rcx, rdi
0x140012551  call    _guard_dispatch_icall
0x140012556  test    ebx, ebx
0x140012558  js      short loc_1400125AE
0x14001255a  xor     r9d, r9d
0x14001255d  lea     rcx, ScheduleAddHostRoute
0x140012564  xor     r8d, r8d
0x140012567  mov     rdx, rdi
0x14001256a  call    ScheduleWorkItem
0x14001256f  jmp     short loc_1400125AE
0x140012571  mov     ebx, 0C0000001h
0x140012576  mov     rcx, cs:WPP_GLOBAL_Control
0x14001257d  lea     rsi, WPP_GLOBAL_Control
0x140012584  cmp     rcx, rsi
0x140012587  jz      short loc_1400125AE
0x140012589  mov     eax, [rcx+2Ch]
0x14001258c  test    al, 2
0x14001258e  jz      short loc_1400125AE
0x140012590  cmp     byte ptr [rcx+29h], 1
0x140012594  jb      short loc_1400125AE
0x140012596  mov     rcx, [rcx+18h]
0x14001259a  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x1400125a1  mov     edx, 4Ch ; 'L'
0x1400125a6  mov     r9, rdi
0x1400125a9  call    WPP_SF_q
0x1400125ae  mov     eax, ebx
0x1400125b0  mov     rcx, [rsp+0D8h+var_38]
0x1400125b8  xor     rcx, rsp; StackCookie
0x1400125bb  call    __security_check_cookie
0x1400125c0  add     rsp, 0B8h
0x1400125c7  pop     rdi
0x1400125c8  pop     rsi
0x1400125c9  pop     rbp
0x1400125ca  pop     rbx
0x1400125cb  retn
```
