# HidpFdoReleasePoFxPowerReferenceWithTag

- ea: `0x180003f40`
- end: `0x18000438d`
- name: `HidpFdoReleasePoFxPowerReferenceWithTag`
- size: `1101`
- prototype: ``
- caller_count: `13`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003190`
- `0x180003900`
- `0x1800039c0`
- `0x180004c00`
- `0x180006ac8`
- `0x18000ce08`
- `0x18000ef30`
- `0x180012090`
- `0x18001320c`
- `0x1800132e4`
- `0x180017fa0`
- `0x180019464`
- `0x180024810`

## callees

- `0x180003f40`
- `0x18000ec10`
- `0x180012e6c`
- `0x18001cabc`
- `0x18001e944`
- `0x180024e88`
- `0x180025420`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x180004370`
- `ntoskrnl!PoFxIdleComponent` at `0x180004370`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180003fbe`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x1800040e2`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180004210`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180003fbe`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x1800040e2`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x180004210`

## pseudocode

```c
__int64 __fastcall HidpFdoReleasePoFxPowerReferenceWithTag(__int64 a1, int a2)
{
  int v2; // esi
  int v4; // edi
  int v6; // edx
  int v7; // r8d
  int v8; // edi
  int v9; // edx
  bool v10; // r8
  int v11; // edx
  int v12; // r8d

  v2 = a2;
  if ( a2 == 8 )
  {
    v4 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 1876));
    if ( v4 < 0 )
      return HidpDbgBreak("A PoFx reference is being released for IO even though none are pending");
    if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( !v4 )
        HidpFdoSleepstudyHelperComponentInactiveSafe(a1, a1 + 2160);
    }
    else if ( !v4 && *(_QWORD *)(a1 + 2160) )
    {
      SleepstudyHelper_ComponentInactive();
    }
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qLDqDLlll(WPP_GLOBAL_Control->AttachedDevice, v6, v7, *(_QWORD *)(a1 + 672));
    }
  }
  else if ( a2 == 4 )
  {
    v8 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 1872));
    if ( v8 < 0 )
      return HidpDbgBreak("A PoFx reference is being released for ResetIdleTimer even though none are pending");
    if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( !v8 )
        HidpFdoSleepstudyHelperComponentInactiveSafe(a1, a1 + 2152);
    }
    else if ( !v8 && *(_QWORD *)(a1 + 2152) )
    {
      SleepstudyHelper_ComponentInactive();
    }
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    v10 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v9 || v10 )
      WPP_RECORDER_AND_TRACE_SF_qLDDLlll(WPP_GLOBAL_Control->AttachedDevice, v9, v10, *(_QWORD *)(a1 + 672), 5);
  }
  else
  {
    if ( a2 == 16 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)(a1 + 1880)) < 0 )
        return HidpDbgBreak("A PoFx reference is being released for client request even though none are pending");
    }
    else
    {
      if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( v2 == 1 )
          HidpFdoSleepstudyHelperComponentInactiveSafe(a1, a1 + 2168);
      }
      else if ( v2 == 1 && *(_QWORD *)(a1 + 2168) )
      {
        SleepstudyHelper_ComponentInactive();
      }
      LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
      if ( (_BYTE)v11 || (_BYTE)v12 )
        WPP_RECORDER_AND_TRACE_SF_qLDD(WPP_GLOBAL_Control->AttachedDevice, v11, v12, *(_QWORD *)(a1 + 672));
      a2 = ~v2;
      _m_prefetchw((const void *)(a1 + 1868));
      if ( (v2 & _InterlockedAnd((volatile signed __int32 *)(a1 + 1868), ~v2)) != v2 )
        return HidpDbgBreak("A PoFx is being released for a reason for which there is none pending");
    }
    LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qLDDLlll(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *(_QWORD *)(a1 + 672),
        4);
  }
  return PoFxIdleComponent(*(_QWORD *)(a1 + 696), 0, 2);
}

```

## disassembly

```asm
0x180003f40  push    rbx
0x180003f42  push    rbp
0x180003f43  push    rsi
0x180003f44  push    rdi
0x180003f45  push    r14
0x180003f47  push    r15
0x180003f49  sub     rsp, 98h
0x180003f50  mov     r15, r8
0x180003f53  mov     esi, edx
0x180003f55  mov     rbx, rcx
0x180003f58  cmp     edx, 8
0x180003f5b  jnz     loc_18000407C
0x180003f61  mov     edi, 0FFFFFFFFh
0x180003f66  lock xadd [rcx+754h], edi
0x180003f6e  sub     edi, 1
0x180003f71  jns     short loc_180003F90
0x180003f73  lea     rcx, aAPofxReference_1; "A PoFx reference is being released for "...
0x180003f7a  call    HidpDbgBreak
0x180003f7f  add     rsp, 98h
0x180003f86  pop     r15
0x180003f88  pop     r14
0x180003f8a  pop     rdi
0x180003f8b  pop     rsi
0x180003f8c  pop     rbp
0x180003f8d  pop     rbx
0x180003f8e  retn
0x180003f90  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x180003f95  test    eax, eax
0x180003f97  jz      short loc_180003FAE
0x180003f99  test    edi, edi
0x180003f9b  jnz     short loc_180003FCA
0x180003f9d  lea     rdx, [rbx+870h]
0x180003fa4  mov     rcx, rbx
0x180003fa7  call    HidpFdoSleepstudyHelperComponentInactiveSafe
0x180003fac  jmp     short loc_180003FCA
0x180003fae  test    edi, edi
0x180003fb0  jnz     short loc_180003FCA
0x180003fb2  mov     rcx, [rbx+870h]
0x180003fb9  test    rcx, rcx
0x180003fbc  jz      short loc_180003FCA
0x180003fbe  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x180003fc5  nop     dword ptr [rax+rax+00h]
0x180003fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd1  lea     rbp, WPP_GLOBAL_Control
0x180003fd8  cmp     rcx, rbp
0x180003fdb  jz      short loc_180003FF0
0x180003fdd  test    dword ptr [rcx+2Ch], 100h
0x180003fe4  jz      short loc_180003FF0
0x180003fe6  cmp     byte ptr [rcx+29h], 4
0x180003fea  jb      short loc_180003FF0
0x180003fec  mov     dl, 1
0x180003fee  jmp     short loc_180003FF2
0x180003ff0  xor     dl, dl
0x180003ff2  lea     r14, WPP_RECORDER_INITIALIZED
0x180003ff9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180004000  setnz   r8b
0x180004004  test    dl, dl
0x180004006  jnz     short loc_180004011
0x180004008  test    r8b, r8b
0x18000400b  jz      loc_180004361
0x180004011  mov     eax, [rbx+758h]
0x180004017  mov     r9d, [rbx+74Ch]
0x18000401e  mov     rcx, [rcx+18h]
0x180004022  mov     [rsp+0C8h+var_48], eax
0x180004029  mov     eax, [rbx+754h]
0x18000402f  mov     [rsp+0C8h+var_50], eax
0x180004033  mov     eax, [rbx+750h]
0x180004039  mov     [rsp+0C8h+var_58], eax
0x18000403d  mov     rax, [rbx]
0x180004040  mov     [rsp+0C8h+var_60], r9d
0x180004045  mov     [rsp+0C8h+var_68], r9d
0x18000404a  mov     r9, [rbx+2A0h]
0x180004051  mov     [rsp+0C8h+var_70], r15
0x180004056  mov     [rsp+0C8h+var_78], 8
0x18000405e  mov     [rsp+0C8h+var_80], 8
0x180004066  mov     [rsp+0C8h+var_88], rax
0x18000406b  mov     [rsp+0C8h+var_98], 32h ; '2'
0x180004072  call    WPP_RECORDER_AND_TRACE_SF_qLDqDLlll
0x180004077  jmp     loc_180004361
0x18000407c  cmp     esi, 4
0x18000407f  jnz     loc_18000419A
0x180004085  mov     edi, 0FFFFFFFFh
0x18000408a  lock xadd [rcx+750h], edi
0x180004092  sub     edi, 1
0x180004095  jns     short loc_1800040B4
0x180004097  lea     rcx, aAPofxReference_0; "A PoFx reference is being released for "...
0x18000409e  call    HidpDbgBreak
0x1800040a3  add     rsp, 98h
0x1800040aa  pop     r15
0x1800040ac  pop     r14
0x1800040ae  pop     rdi
0x1800040af  pop     rsi
0x1800040b0  pop     rbp
0x1800040b1  pop     rbx
0x1800040b2  retn
0x1800040b4  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x1800040b9  test    eax, eax
0x1800040bb  jz      short loc_1800040D2
0x1800040bd  test    edi, edi
0x1800040bf  jnz     short loc_1800040EE
0x1800040c1  lea     rdx, [rbx+868h]
0x1800040c8  mov     rcx, rbx
0x1800040cb  call    HidpFdoSleepstudyHelperComponentInactiveSafe
0x1800040d0  jmp     short loc_1800040EE
0x1800040d2  test    edi, edi
0x1800040d4  jnz     short loc_1800040EE
0x1800040d6  mov     rcx, [rbx+868h]
0x1800040dd  test    rcx, rcx
0x1800040e0  jz      short loc_1800040EE
0x1800040e2  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x1800040e9  nop     dword ptr [rax+rax+00h]
0x1800040ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040f5  lea     rbp, WPP_GLOBAL_Control
0x1800040fc  cmp     rcx, rbp
0x1800040ff  jz      short loc_180004114
0x180004101  test    dword ptr [rcx+2Ch], 100h
0x180004108  jz      short loc_180004114
0x18000410a  cmp     byte ptr [rcx+29h], 5
0x18000410e  jb      short loc_180004114
0x180004110  mov     dl, 1
0x180004112  jmp     short loc_180004116
0x180004114  xor     dl, dl
0x180004116  lea     r14, WPP_RECORDER_INITIALIZED
0x18000411d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180004124  jz      short loc_180004132
0x180004126  cmp     word ptr [rcx+48h], 0
0x18000412b  jz      short loc_180004132
0x18000412d  mov     r8b, 1
0x180004130  jmp     short loc_180004135
0x180004132  xor     r8b, r8b
0x180004135  test    dl, dl
0x180004137  jnz     short loc_180004142
0x180004139  test    r8b, r8b
0x18000413c  jz      loc_180004361
0x180004142  mov     eax, [rbx+758h]
0x180004148  mov     r9d, [rbx+74Ch]
0x18000414f  mov     [rsp+0C8h+var_50], eax
0x180004153  mov     eax, [rbx+754h]
0x180004159  mov     [rsp+0C8h+var_58], eax
0x18000415d  mov     eax, [rbx+750h]
0x180004163  mov     [rsp+0C8h+var_60], eax
0x180004167  mov     rax, [rbx]
0x18000416a  mov     [rsp+0C8h+var_68], r9d
0x18000416f  mov     dword ptr [rsp+0C8h+var_70], r9d
0x180004174  mov     [rsp+0C8h+var_78], 4
0x18000417c  mov     [rsp+0C8h+var_80], 4
0x180004184  mov     [rsp+0C8h+var_88], rax
0x180004189  mov     [rsp+0C8h+var_98], 33h ; '3'
0x180004190  mov     [rsp+0C8h+var_A8], 5
0x180004195  jmp     loc_180004351
0x18000419a  lea     rbp, WPP_GLOBAL_Control
0x1800041a1  lea     r14, WPP_RECORDER_INITIALIZED
0x1800041a8  cmp     esi, 10h
0x1800041ab  jnz     short loc_1800041E0
0x1800041ad  mov     edi, 0FFFFFFFFh
0x1800041b2  lock xadd [rcx+758h], edi
0x1800041ba  cmp     edi, 1
0x1800041bd  jns     loc_1800042D1
0x1800041c3  lea     rcx, aAPofxReference_2; "A PoFx reference is being released for "...
0x1800041ca  call    HidpDbgBreak
0x1800041cf  add     rsp, 98h
0x1800041d6  pop     r15
0x1800041d8  pop     r14
0x1800041da  pop     rdi
0x1800041db  pop     rsi
0x1800041dc  pop     rbp
0x1800041dd  pop     rbx
0x1800041de  retn
0x1800041e0  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x1800041e5  test    eax, eax
0x1800041e7  jz      short loc_1800041FF
0x1800041e9  cmp     esi, 1
0x1800041ec  jnz     short loc_18000421C
0x1800041ee  lea     rdx, [rbx+878h]
0x1800041f5  mov     rcx, rbx
0x1800041f8  call    HidpFdoSleepstudyHelperComponentInactiveSafe
0x1800041fd  jmp     short loc_18000421C
0x1800041ff  cmp     esi, 1
0x180004202  jnz     short loc_18000421C
0x180004204  mov     rcx, [rbx+878h]
0x18000420b  test    rcx, rcx
0x18000420e  jz      short loc_18000421C
0x180004210  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x180004217  nop     dword ptr [rax+rax+00h]
0x18000421c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004223  cmp     rcx, rbp
0x180004226  jz      short loc_18000423B
0x180004228  test    dword ptr [rcx+2Ch], 100h
0x18000422f  jz      short loc_18000423B
0x180004231  cmp     byte ptr [rcx+29h], 5
0x180004235  jb      short loc_18000423B
0x180004237  mov     dl, 1
0x180004239  jmp     short loc_18000423D
0x18000423b  xor     dl, dl
0x18000423d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180004244  jz      short loc_180004252
0x180004246  cmp     word ptr [rcx+48h], 0
0x18000424b  jz      short loc_180004252
0x18000424d  mov     r8b, 1
0x180004250  jmp     short loc_180004255
0x180004252  xor     r8b, r8b
0x180004255  test    dl, dl
0x180004257  jnz     short loc_18000425E
0x180004259  test    r8b, r8b
0x18000425c  jz      short loc_18000428F
0x18000425e  mov     eax, [rbx+74Ch]
0x180004264  mov     r9, [rbx+2A0h]
0x18000426b  mov     rcx, [rcx+18h]
0x18000426f  mov     dword ptr [rsp+0C8h+var_70], eax
0x180004273  mov     rax, [rbx]
0x180004276  mov     [rsp+0C8h+var_78], esi
0x18000427a  mov     [rsp+0C8h+var_80], esi
0x18000427e  mov     [rsp+0C8h+var_88], rax
0x180004283  mov     [rsp+0C8h+var_98], 31h ; '1'
0x18000428a  call    WPP_RECORDER_AND_TRACE_SF_qLDD
0x18000428f  mov     edx, esi
0x180004291  not     edx
0x180004293  prefetchw byte ptr [rbx+74Ch]
0x18000429a  mov     eax, [rbx+74Ch]
0x1800042a0  mov     ecx, eax
0x1800042a2  and     ecx, edx
0x1800042a4  lock cmpxchg [rbx+74Ch], ecx
0x1800042ac  jnz     short loc_1800042A0
0x1800042ae  and     eax, esi
0x1800042b0  cmp     eax, esi
0x1800042b2  jz      short loc_1800042D1
0x1800042b4  lea     rcx, aAPofxIsBeingRe; "A PoFx is being released for a reason f"...
0x1800042bb  call    HidpDbgBreak
0x1800042c0  add     rsp, 98h
0x1800042c7  pop     r15
0x1800042c9  pop     r14
0x1800042cb  pop     rdi
0x1800042cc  pop     rsi
0x1800042cd  pop     rbp
0x1800042ce  pop     rbx
0x1800042cf  retn
0x1800042d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042d8  cmp     rcx, rbp
0x1800042db  jz      short loc_1800042F0
0x1800042dd  test    dword ptr [rcx+2Ch], 100h
0x1800042e4  jz      short loc_1800042F0
0x1800042e6  cmp     byte ptr [rcx+29h], 4
0x1800042ea  jb      short loc_1800042F0
0x1800042ec  mov     dl, 1
0x1800042ee  jmp     short loc_1800042F2
0x1800042f0  xor     dl, dl
0x1800042f2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800042f9  setnz   r8b
0x1800042fd  test    dl, dl
0x1800042ff  jnz     short loc_180004306
0x180004301  test    r8b, r8b
0x180004304  jz      short loc_180004361
0x180004306  mov     eax, [rbx+758h]
0x18000430c  mov     r9d, [rbx+74Ch]
0x180004313  mov     [rsp+0C8h+var_50], eax
0x180004317  mov     eax, [rbx+754h]
0x18000431d  mov     [rsp+0C8h+var_58], eax
0x180004321  mov     eax, [rbx+750h]
0x180004327  mov     [rsp+0C8h+var_60], eax
0x18000432b  mov     rax, [rbx]
0x18000432e  mov     [rsp+0C8h+var_68], r9d
0x180004333  mov     dword ptr [rsp+0C8h+var_70], r9d
0x180004338  mov     [rsp+0C8h+var_78], esi
0x18000433c  mov     [rsp+0C8h+var_80], esi
0x180004340  mov     [rsp+0C8h+var_88], rax
0x180004345  mov     [rsp+0C8h+var_98], 34h ; '4'
0x18000434c  mov     [rsp+0C8h+var_A8], 4
0x180004351  mov     r9, [rbx+2A0h]
0x180004358  mov     rcx, [rcx+18h]
0x18000435c  call    WPP_RECORDER_AND_TRACE_SF_qLDDLlll
0x180004361  mov     rcx, [rbx+2B8h]
0x180004368  xor     edx, edx
0x18000436a  mov     r8d, 2
0x180004370  call    cs:__imp_PoFxIdleComponent
0x180004377  nop     dword ptr [rax+rax+00h]
0x18000437c  add     rsp, 98h
0x180004383  pop     r15
0x180004385  pop     r14
0x180004387  pop     rdi
0x180004388  pop     rsi
0x180004389  pop     rbp
0x18000438a  pop     rbx
0x18000438b  retn
```
