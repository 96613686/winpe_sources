# HalpTimerClockArm

- ea: `0x140408d20`
- end: `0x140408e9b`
- name: `HalpTimerClockArm`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140513fc4`

## callees

- `0x140241bf0`
- `0x1402c2750`
- `0x140408d20`
- `0x14041a390`
- `0x1404cfd54`
- `0x140513fc4`
- `0x14053a530`
- `0x1406e8590`

## string_xrefs

- `0x140408dac`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x14071196e`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x140711a93`: `minkernel\hals\lib\timers\common\timersup.c`

## pseudocode

```c
__int64 __fastcall HalpTimerClockArm(int a1, ULONG_PTR a2, unsigned __int64 *a3)
{
  struct _KPRCB *CurrentPrcb; // rcx
  ULONGLONG v6; // rbx
  ULONG_PTR v7; // rsi
  int v8; // eax
  unsigned __int64 v9; // rdi
  NTSTATUS v10; // r10d
  unsigned int v12; // ecx
  unsigned __int64 v13; // rbp
  __int64 v14; // r9
  __int64 v15; // r11
  ULONGLONG v16; // rax
  __int64 InternalData; // rax
  __int64 v18; // r9
  __int64 v19; // r11
  int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // r9
  __int64 v23; // r11
  ULONGLONG v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // r11
  int v29; // eax
  ULONGLONG pullResult; // [rsp+58h] [rbp+10h] BYREF
  ULONGLONG v31; // [rsp+68h] [rbp+20h] BYREF

  CurrentPrcb = KeGetCurrentPrcb();
  v6 = a2;
  if ( a2 > HalpTimerMaxIncrement )
    KeBugCheckEx(0x5Cu, 0x113u, 0x25u, a2, 0);
  v7 = HalpClockTimer;
  if ( a2 < (unsigned int)HalpTimerMinIncrement )
    v6 = (unsigned int)HalpTimerMinIncrement;
  if ( (CurrentPrcb->PendingTickFlags & 2) != 0 )
    HalpTimerSwitchToNormalClock(0);
  v8 = *(_DWORD *)(v7 + 224);
  if ( a1 == 1 )
  {
    v9 = 0;
    v31 = 0;
    pullResult = 0;
    if ( (v8 & 0x20) != 0 )
    {
      v10 = RtlULongLongMult(*(_QWORD *)(v7 + 192), v6, &pullResult);
      if ( v10 >= 0 )
      {
        if ( pullResult + 9999999 < pullResult )
        {
          v10 = -1073741675;
        }
        else
        {
          v12 = *(_DWORD *)(v7 + 220);
          if ( v12 >= 0x40 || (pullResult + 9999999) / 0x989680 < 1LL << v12 )
          {
            if ( RtlULongLongMult((pullResult + 9999999) / 0x989680, 0x2540BE400uLL, &v31) >= 0 )
              v16 = v31 / *(_QWORD *)(v7 + 192);
            else
              v16 = HalpTimerScaleCounter(v15, *(_QWORD *)(v7 + 192), v14);
            *(_QWORD *)(v7 + 16) = v15;
            *(_DWORD *)(v7 + 52) = 1;
            v9 = v16 / 0x3E8;
            InternalData = HalpTimerGetInternalData(v7);
            v20 = guard_dispatch_icall_no_overrides(InternalData, 3, v19, v18);
            v10 = v20;
            if ( v20 < 0 )
              HalpTimerSetProblemEx(v7, 18, v20, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 810);
          }
          else
          {
            v10 = -1073741811;
          }
        }
      }
    }
    else
    {
      HalpTimerSetProblemEx(v7, 17, 0, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 699);
      v10 = -1073741637;
    }
  }
  else
  {
    v31 = 0;
    v13 = 0;
    pullResult = 0;
    if ( (v8 & 0x50) != 0 )
    {
      v10 = RtlULongLongMult(*(_QWORD *)(v7 + 192), v6, &pullResult);
      if ( v10 >= 0 )
      {
        v21 = *(_DWORD *)(v7 + 220);
        if ( v21 >= 0x40 || pullResult / 0x989680 < 1LL << v21 )
        {
          if ( RtlULongLongMult(pullResult / 0x989680, 0x2540BE400uLL, &v31) >= 0 )
            v24 = v31 / *(_QWORD *)(v7 + 192);
          else
            v24 = HalpTimerScaleCounter(v23, *(_QWORD *)(v7 + 192), v22);
          *(_QWORD *)(v7 + 16) = v23;
          *(_DWORD *)(v7 + 52) = 1;
          v13 = v24 / 0x3E8;
          v25 = HalpTimerGetInternalData(v7);
          v29 = guard_dispatch_icall_no_overrides(v25, v26, v28, v27);
          v10 = v29;
          if ( v29 < 0 )
            HalpTimerSetProblemEx(v7, 18, v29, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 810);
        }
        else
        {
          v10 = -1073741811;
        }
      }
    }
    else
    {
      HalpTimerSetProblemEx(v7, 17, 0, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 711);
    }
    v9 = v13;
  }
  *a3 = v9;
  if ( v10 < 0 )
    KeBugCheckEx(0x5Cu, 0x110u, v7, HalpTimerLastProblem, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140408d20  push    rbx
0x140408d22  push    rdi
0x140408d23  push    r14
0x140408d25  sub     rsp, 30h
0x140408d29  mov     edi, ecx
0x140408d2b  mov     r14, r8
0x140408d2e  mov     rcx, gs:20h
0x140408d37  mov     rbx, rdx
0x140408d3a  cmp     rdx, cs:HalpTimerMaxIncrement
0x140408d41  jbe     short loc_140408D63
0x140408d43  xor     edi, edi
0x140408d45  mov     r9, rdx; BugCheckParameter3
0x140408d48  mov     edx, 113h; BugCheckParameter1
0x140408d4d  mov     [rsp+48h+BugCheckParameter4], rdi; BugCheckParameter4
0x140408d52  mov     ecx, 5Ch ; '\'; BugCheckCode
0x140408d57  mov     r8d, 25h ; '%'; BugCheckParameter2
0x140408d5d  call    KeBugCheckEx
0x140408d63  mov     eax, cs:HalpTimerMinIncrement
0x140408d69  cmp     rbx, rax
0x140408d6c  mov     [rsp+48h+arg_10], rsi
0x140408d71  mov     rsi, cs:HalpClockTimer
0x140408d78  cmovb   rbx, rax
0x140408d7c  test    byte ptr [rcx+22h], 2
0x140408d80  jz      short loc_140408D89
0x140408d82  xor     ecx, ecx
0x140408d84  call    HalpTimerSwitchToNormalClock
0x140408d89  mov     eax, [rsi+0E0h]
0x140408d8f  cmp     edi, 1
0x140408d92  jnz     loc_140408E65
0x140408d98  xor     edi, edi
0x140408d9a  mov     [rsp+48h+arg_18], rdi
0x140408d9f  mov     [rsp+48h+pullResult], rdi
0x140408da4  test    al, 20h
0x140408da6  jnz     loc_1407118B8
0x140408dac  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140408db3  mov     dword ptr [rsp+48h+BugCheckParameter4], 2BBh
0x140408dbb  xor     r8d, r8d
0x140408dbe  mov     edx, 11h
0x140408dc3  mov     rcx, rsi
0x140408dc6  call    HalpTimerSetProblemEx
0x140408dcb  mov     r10d, 0C00000BBh
0x140408dd1  jmp     short loc_140408DD9
0x140408dd3  mov     r10d, 0C0000095h
0x140408dd9  mov     [r14], rdi
0x140408ddc  test    r10d, r10d
0x140408ddf  jns     short loc_140408E03
0x140408de1  movsxd  r9, cs:HalpTimerLastProblem; BugCheckParameter3
0x140408de8  mov     r8, rsi; BugCheckParameter2
0x140408deb  movsxd  rax, r10d
0x140408dee  mov     edx, 110h; BugCheckParameter1
0x140408df3  mov     ecx, 5Ch ; '\'; BugCheckCode
0x140408df8  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x140408dfd  call    KeBugCheckEx
0x140408e03  mov     rsi, [rsp+48h+arg_10]
0x140408e08  mov     eax, r10d
0x140408e0b  add     rsp, 30h
0x140408e0f  pop     r14
0x140408e11  pop     rdi
0x140408e12  pop     rbx
0x140408e13  retn
0x140408e15  mov     rax, [rsp+48h+pullResult]
0x140408e1a  lea     rcx, [rax+98967Fh]
0x140408e21  cmp     rcx, rax
0x140408e24  jb      short loc_140408DD3
0x140408e26  mov     rax, 0D6BF94D5E57A42BDh
0x140408e30  mul     rcx
0x140408e33  mov     ecx, [rsi+0DCh]
0x140408e39  mov     r11, rdx
0x140408e3c  shr     r11, 17h
0x140408e40  cmp     ecx, 40h ; '@'
0x140408e43  jnb     loc_1407118DC
0x140408e49  mov     eax, 1
0x140408e4e  shl     rax, cl
0x140408e51  cmp     r11, rax
0x140408e54  jb      loc_1407118DC
0x140408e5a  mov     r10d, 0C000000Dh
0x140408e60  jmp     loc_140408DD9
0x140408e65  xor     edi, edi
0x140408e67  mov     [rsp+48h+arg_0], rbp
0x140408e6c  mov     [rsp+48h+arg_18], rdi
0x140408e71  mov     ebp, edi
0x140408e73  mov     [rsp+48h+pullResult], rdi
0x140408e78  test    al, 50h
0x140408e7a  jnz     loc_140711993
0x140408e80  mov     r10d, 0C00000BBh
0x140408e86  mov     dword ptr [rsp+48h+BugCheckParameter4], 2C7h
0x140408e8e  xor     r8d, r8d
0x140408e91  mov     edx, 11h
0x140408e96  jmp     loc_140711A93
0x1407118b8  mov     rcx, [rsi+0C0h]; ullMultiplicand
0x1407118bf  lea     r8, [rsp+48h+pullResult]; pullResult
0x1407118c4  mov     rdx, rbx; ullMultiplier
0x1407118c7  call    RtlULongLongMult
0x1407118cc  mov     r10d, eax
0x1407118cf  test    eax, eax
0x1407118d1  js      loc_140408DD9
0x1407118d7  jmp     loc_140408E15
0x1407118dc  mov     r9, 2540BE400h
0x1407118e6  lea     r8, [rsp+48h+arg_18]; pullResult
0x1407118eb  mov     rdx, r9; ullMultiplier
0x1407118ee  mov     rcx, r11; ullMultiplicand
0x1407118f1  call    RtlULongLongMult
0x1407118f6  test    eax, eax
0x1407118f8  jns     short loc_14071190E
0x1407118fa  mov     rdx, [rsi+0C0h]
0x140711901  mov     r8, r9
0x140711904  mov     rcx, r11
0x140711907  call    HalpTimerScaleCounter
0x14071190c  jmp     short loc_14071191C
0x14071190e  mov     rax, [rsp+48h+arg_18]
0x140711913  xor     edx, edx
0x140711915  div     qword ptr [rsi+0C0h]
0x14071191c  mov     rdi, rax
0x14071191f  mov     [rsi+10h], r11
0x140711923  mov     rax, 624DD2F1A9FBE77h
0x14071192d  mov     dword ptr [rsi+34h], 1
0x140711934  mul     rdi
0x140711937  mov     rcx, rsi
0x14071193a  sub     rdi, rdx
0x14071193d  shr     rdi, 1
0x140711940  add     rdi, rdx
0x140711943  shr     rdi, 9
0x140711947  call    HalpTimerGetInternalData
0x14071194c  mov     rcx, rax
0x14071194f  mov     r8, r11
0x140711952  mov     rax, [rsi+80h]
0x140711959  mov     edx, 3
0x14071195e  call    _guard_dispatch_icall_no_overrides
0x140711963  mov     r10d, eax
0x140711966  test    eax, eax
0x140711968  jns     loc_140408DD9
0x14071196e  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140711975  mov     dword ptr [rsp+48h+BugCheckParameter4], 32Ah
0x14071197d  mov     r8d, eax
0x140711980  mov     edx, 12h
0x140711985  mov     rcx, rsi
0x140711988  call    HalpTimerSetProblemEx
0x14071198d  nop
0x14071198e  jmp     loc_140408DD9
0x140711993  mov     rcx, [rsi+0C0h]; ullMultiplicand
0x14071199a  lea     r8, [rsp+48h+pullResult]; pullResult
0x14071199f  mov     rdx, rbx; ullMultiplier
0x1407119a2  call    RtlULongLongMult
0x1407119a7  mov     r10d, eax
0x1407119aa  test    eax, eax
0x1407119ac  js      loc_140711AA2
0x1407119b2  mov     ecx, [rsi+0DCh]
0x1407119b8  mov     rax, 0D6BF94D5E57A42BDh
0x1407119c2  mul     [rsp+48h+pullResult]
0x1407119c7  mov     r11, rdx
0x1407119ca  shr     r11, 17h
0x1407119ce  cmp     ecx, 40h ; '@'
0x1407119d1  jnb     short loc_1407119EB
0x1407119d3  mov     eax, 1
0x1407119d8  shl     rax, cl
0x1407119db  cmp     r11, rax
0x1407119de  jb      short loc_1407119EB
0x1407119e0  mov     r10d, 0C000000Dh
0x1407119e6  jmp     loc_140711AA2
0x1407119eb  mov     r9, 2540BE400h
0x1407119f5  lea     r8, [rsp+48h+arg_18]; pullResult
0x1407119fa  mov     rdx, r9; ullMultiplier
0x1407119fd  mov     rcx, r11; ullMultiplicand
0x140711a00  call    RtlULongLongMult
0x140711a05  test    eax, eax
0x140711a07  jns     short loc_140711A1D
0x140711a09  mov     rdx, [rsi+0C0h]
0x140711a10  mov     r8, r9
0x140711a13  mov     rcx, r11
0x140711a16  call    HalpTimerScaleCounter
0x140711a1b  jmp     short loc_140711A2B
0x140711a1d  mov     rax, [rsp+48h+arg_18]
0x140711a22  xor     edx, edx
0x140711a24  div     qword ptr [rsi+0C0h]
0x140711a2b  mov     rbp, rax
0x140711a2e  mov     [rsi+10h], r11
0x140711a32  mov     dword ptr [rsi+34h], 1
0x140711a39  mov     rax, 624DD2F1A9FBE77h
0x140711a43  mul     rbp
0x140711a46  mov     eax, [rsi+0E0h]
0x140711a4c  mov     rcx, rsi
0x140711a4f  sub     rbp, rdx
0x140711a52  shr     rbp, 1
0x140711a55  add     rbp, rdx
0x140711a58  shr     rbp, 9
0x140711a5c  test    al, 40h
0x140711a5e  setnz   dil
0x140711a62  lea     edx, [rdi+1]
0x140711a65  call    HalpTimerGetInternalData
0x140711a6a  mov     rcx, rax
0x140711a6d  mov     r8, r11
0x140711a70  mov     rax, [rsi+80h]
0x140711a77  call    _guard_dispatch_icall_no_overrides
0x140711a7c  mov     r10d, eax
0x140711a7f  test    eax, eax
0x140711a81  jns     short loc_140711AA2
0x140711a83  mov     dword ptr [rsp+48h+BugCheckParameter4], 32Ah
0x140711a8b  mov     r8d, eax
0x140711a8e  mov     edx, 12h
0x140711a93  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140711a9a  mov     rcx, rsi
0x140711a9d  call    HalpTimerSetProblemEx
0x140711aa2  mov     rdi, rbp
0x140711aa5  mov     rbp, [rsp+48h+arg_0]
0x140711aaa  jmp     loc_140408DD9
```
