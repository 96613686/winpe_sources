# SessionDisconnectInd

- ea: `0x140017db4`
- end: `0x140018039`
- name: `SessionDisconnectInd`
- size: `645`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d370`
- `0x14000da70`
- `0x14000e840`
- `0x14001127c`
- `0x14001138c`
- `0x14001291c`
- `0x140014210`
- `0x140015904`
- `0x14001737c`
- `0x1400174a8`
- `0x140018040`
- `0x1400185c8`
- `0x14001898c`

## callees

- `0x140003818`
- `0x140003bf4`
- `0x140007350`
- `0x14000e700`
- `0x1400133b0`
- `0x1400157dc`
- `0x140015bdc`
- `0x140016ebc`
- `0x140017ab8`
- `0x140017db4`
- `0x140019b64`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017de7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017de7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017ec1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017ec1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f3e`

## string_xrefs

- `0x140017fce`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
_UNKNOWN **__fastcall SessionDisconnectInd(__int64 a1, char a2, unsigned int a3, char a4)
{
  KSPIN_LOCK *v4; // rsi
  const char *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  char v12; // bl
  int v13; // edx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rbx
  __int64 v17; // rax
  _UNKNOWN **result; // rax
  __int128 v19; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-10h] BYREF

  v4 = (KSPIN_LOCK *)(a1 + 56);
  v19 = 0;
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = RfcommStateTxt(*(_DWORD *)(a1 + 48));
    WPP_RECORDER_SF_qss(WPP_GLOBAL_Control->DeviceExtension, v10, 3, 31, v11, a1, (__int64)v9, v10);
  }
  *((_QWORD *)&v19 + 1) = &v19;
  *(_QWORD *)&v19 = &v19;
  if ( !a4 )
    ListDrainLocked(&v19, a1 + 96);
  if ( *(_DWORD *)(a1 + 48) == 5 )
  {
    KeReleaseSpinLock(v4, *(_BYTE *)(a1 + 64));
  }
  else
  {
    if ( *(_DWORD *)(a1 + 48) == 6 )
    {
      KeReleaseSpinLock(v4, *(_BYTE *)(a1 + 64));
      goto LABEL_19;
    }
    v20[1] = v20;
    v20[0] = v20;
    ListDrainLocked(v20, a1 + 80);
    v12 = RfcommSetState(a1, 5);
    KeReleaseSpinLock(v4, *(_BYTE *)(a1 + 64));
    if ( v12 )
      RfcommStartTimer(*(_QWORD *)(a1 + 72));
    while ( 1 )
    {
      v14 = (_QWORD *)v20[0];
      if ( (_QWORD *)v20[0] == v20 )
        break;
      if ( *(_QWORD **)(v20[0] + 8LL) != v20
        || (v15 = *(_QWORD *)v20[0], *(_QWORD *)(*(_QWORD *)v20[0] + 8LL) != v20[0]) )
      {
LABEL_23:
        __fastfail(3u);
      }
      v20[0] = *(_QWORD *)v20[0];
      *(_QWORD *)(v15 + 8) = v20;
      v14[1] = v14;
      *v14 = v14;
      ChannelDisconnectInd(v14, 2, a3);
    }
  }
  if ( a2 && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 480), 1, 0) && (int)BrbpDisconnect(a1) < 0 )
  {
    _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 480), 0, 1);
    SessionDisconnect(a1);
  }
LABEL_19:
  while ( 1 )
  {
    v16 = (_QWORD *)v19;
    if ( (__int128 *)v19 == &v19 )
      break;
    if ( *(__int128 **)(v19 + 8) != &v19 )
      goto LABEL_23;
    v17 = *(_QWORD *)v19;
    if ( *(_QWORD *)(*(_QWORD *)v19 + 8LL) != (_QWORD)v19 )
      goto LABEL_23;
    *(_QWORD *)&v19 = *(_QWORD *)v19;
    *(_QWORD *)(v17 + 8) = &v19;
    v16[1] = v16;
    *v16 = v16;
    TdiCompleteConnect((__int64)(v16 - 35), a3);
    RefObj_ReleaseEx(v16 - 32, 1313754947, 935, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
  }
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (_UNKNOWN **)WPP_RECORDER_SF_(
                          WPP_GLOBAL_Control->DeviceExtension,
                          v13,
                          3,
                          32,
                          (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140017db4  mov     [rsp-28h+arg_0], rbx
0x140017db9  mov     [rsp-28h+arg_8], rsi
0x140017dbe  push    rbp
0x140017dbf  push    rdi
0x140017dc0  push    r12
0x140017dc2  push    r14
0x140017dc4  push    r15
0x140017dc6  mov     rbp, rsp
0x140017dc9  sub     rsp, 60h
0x140017dcd  lea     rsi, [rcx+38h]
0x140017dd1  mov     rdi, rcx
0x140017dd4  xorps   xmm0, xmm0
0x140017dd7  mov     rcx, rsi; SpinLock
0x140017dda  mov     r14b, r9b
0x140017ddd  mov     r12d, r8d
0x140017de0  mov     r15b, dl
0x140017de3  movups  [rbp+var_20], xmm0
0x140017de7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017dee  nop     dword ptr [rax+rax+00h]
0x140017df3  mov     [rdi+40h], al
0x140017df6  lea     rax, WPP_RECORDER_INITIALIZED
0x140017dfd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017e04  lea     r8, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140017e0b  jz      short loc_140017E58
0x140017e0d  mov     ecx, [rdi+30h]
0x140017e10  lea     rax, asc_140022D68; " "
0x140017e17  test    r15b, r15b
0x140017e1a  lea     rdx, aBrbdisconnect; "BrbDisconnect"
0x140017e21  cmovz   rdx, rax
0x140017e25  call    RfcommStateTxt
0x140017e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e31  mov     r9d, 1Fh
0x140017e37  mov     [rsp+60h+var_28], rdx
0x140017e3c  mov     [rsp+60h+var_30], rax
0x140017e41  mov     [rsp+60h+var_38], rdi
0x140017e46  mov     rcx, [rcx+40h]
0x140017e4a  mov     [rsp+60h+var_40], r8
0x140017e4f  lea     r8d, [r9-1Ch]
0x140017e53  call    WPP_RECORDER_SF_qss
0x140017e58  lea     rax, [rbp+var_20]
0x140017e5c  mov     qword ptr [rbp+var_20+8], rax
0x140017e60  lea     rax, [rbp+var_20]
0x140017e64  mov     qword ptr [rbp+var_20], rax
0x140017e68  test    r14b, r14b
0x140017e6b  jnz     short loc_140017E7A
0x140017e6d  lea     rdx, [rdi+60h]
0x140017e71  lea     rcx, [rbp+var_20]
0x140017e75  call    ListDrainLocked
0x140017e7a  mov     ecx, [rdi+30h]
0x140017e7d  sub     ecx, 5
0x140017e80  jz      loc_140017F38
0x140017e86  cmp     ecx, 1
0x140017e89  jz      loc_140017F24
0x140017e8f  lea     rax, [rbp+var_10]
0x140017e93  mov     [rbp+var_8], rax
0x140017e97  lea     rdx, [rdi+50h]
0x140017e9b  lea     rax, [rbp+var_10]
0x140017e9f  lea     rcx, [rbp+var_10]
0x140017ea3  mov     [rbp+var_10], rax
0x140017ea7  call    ListDrainLocked
0x140017eac  mov     rcx, rdi
0x140017eaf  mov     edx, 5
0x140017eb4  call    RfcommSetState
0x140017eb9  mov     dl, [rdi+40h]; NewIrql
0x140017ebc  mov     rcx, rsi; SpinLock
0x140017ebf  mov     bl, al
0x140017ec1  call    cs:__imp_KeReleaseSpinLock
0x140017ec8  nop     dword ptr [rax+rax+00h]
0x140017ecd  test    bl, bl
0x140017ecf  jz      short loc_140017EDA
0x140017ed1  mov     rcx, [rdi+48h]
0x140017ed5  call    RfcommStartTimer
0x140017eda  mov     rcx, [rbp+var_10]
0x140017ede  lea     rax, [rbp+var_10]
0x140017ee2  cmp     rcx, rax
0x140017ee5  jz      short loc_140017F4A
0x140017ee7  lea     rax, [rbp+var_10]
0x140017eeb  cmp     [rcx+8], rax
0x140017eef  jnz     loc_140017FE2
0x140017ef5  mov     rax, [rcx]
0x140017ef8  cmp     [rax+8], rcx
0x140017efc  jnz     loc_140017FE2
0x140017f02  mov     [rbp+var_10], rax
0x140017f06  lea     rdx, [rbp+var_10]
0x140017f0a  mov     [rax+8], rdx
0x140017f0e  mov     r8d, r12d
0x140017f11  mov     edx, 2
0x140017f16  mov     [rcx+8], rcx
0x140017f1a  mov     [rcx], rcx
0x140017f1d  call    ChannelDisconnectInd
0x140017f22  jmp     short loc_140017EDA
0x140017f24  mov     dl, [rdi+40h]; NewIrql
0x140017f27  mov     rcx, rsi; SpinLock
0x140017f2a  call    cs:__imp_KeReleaseSpinLock
0x140017f31  nop     dword ptr [rax+rax+00h]
0x140017f36  jmp     short loc_140017F80
0x140017f38  mov     dl, [rdi+40h]; NewIrql
0x140017f3b  mov     rcx, rsi; SpinLock
0x140017f3e  call    cs:__imp_KeReleaseSpinLock
0x140017f45  nop     dword ptr [rax+rax+00h]
0x140017f4a  test    r15b, r15b
0x140017f4d  jz      short loc_140017F80
0x140017f4f  mov     ebx, 1
0x140017f54  xor     eax, eax
0x140017f56  lock cmpxchg [rdi+1E0h], ebx
0x140017f5e  jnz     short loc_140017F80
0x140017f60  mov     rcx, rdi
0x140017f63  call    BrbpDisconnect
0x140017f68  test    eax, eax
0x140017f6a  jns     short loc_140017F80
0x140017f6c  xor     ecx, ecx
0x140017f6e  mov     eax, ebx
0x140017f70  lock cmpxchg [rdi+1E0h], ecx
0x140017f78  mov     rcx, rdi
0x140017f7b  call    SessionDisconnect
0x140017f80  mov     rbx, qword ptr [rbp+var_20]
0x140017f84  lea     rax, [rbp+var_20]
0x140017f88  cmp     rbx, rax
0x140017f8b  jz      short loc_140017FE9
0x140017f8d  lea     rax, [rbp+var_20]
0x140017f91  cmp     [rbx+8], rax
0x140017f95  jnz     short loc_140017FE2
0x140017f97  mov     rax, [rbx]
0x140017f9a  cmp     [rax+8], rbx
0x140017f9e  jnz     short loc_140017FE2
0x140017fa0  mov     qword ptr [rbp+var_20], rax
0x140017fa4  lea     rcx, [rbp+var_20]
0x140017fa8  mov     [rax+8], rcx
0x140017fac  mov     edx, r12d
0x140017faf  lea     rcx, [rbx-118h]
0x140017fb6  mov     [rbx+8], rbx
0x140017fba  mov     [rbx], rbx
0x140017fbd  call    TdiCompleteConnect
0x140017fc2  lea     rcx, [rbx-100h]
0x140017fc9  mov     edx, 4E4E4F43h
0x140017fce  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140017fd5  mov     r8d, 3A7h
0x140017fdb  call    RefObj_ReleaseEx
0x140017fe0  jmp     short loc_140017F80
0x140017fe2  mov     ecx, 3
0x140017fe7  int     29h; Win8: RtlFailFast(ecx)
0x140017fe9  lea     rax, WPP_RECORDER_INITIALIZED
0x140017ff0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017ff7  jz      short loc_14001801F
0x140017ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140018000  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140018007  mov     r9d, 20h ; ' '
0x14001800d  mov     [rsp+60h+var_40], rax
0x140018012  mov     rcx, [rcx+40h]
0x140018016  lea     r8d, [r9-1Dh]
0x14001801a  call    WPP_RECORDER_SF_
0x14001801f  lea     r11, [rsp+60h+var_s0]
0x140018024  mov     rbx, [r11+30h]
0x140018028  mov     rsi, [r11+38h]
0x14001802c  mov     rsp, r11
0x14001802f  pop     r15
0x140018031  pop     r14
0x140018033  pop     r12
0x140018035  pop     rdi
0x140018036  pop     rbp
0x140018037  retn
```
