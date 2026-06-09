# HalpTimerClockArm

- ea: `0x140420560`
- end: `0x1404206db`
- name: `HalpTimerClockArm`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14051a1c4`

## callees

- `0x1402834d0`
- `0x1403a4a00`
- `0x140420560`
- `0x140430d30`
- `0x1404df454`
- `0x14051a1c4`
- `0x140541bf0`
- `0x1406eb0e0`

## string_xrefs

- `0x1404205ec`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x140714a66`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x140714b8b`: `minkernel\hals\lib\timers\common\timersup.c`

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
0x140420560  push    rbx
0x140420562  push    rdi
0x140420563  push    r14
0x140420565  sub     rsp, 30h
0x140420569  mov     edi, ecx
0x14042056b  mov     r14, r8
0x14042056e  mov     rcx, gs:20h
0x140420577  mov     rbx, rdx
0x14042057a  cmp     rdx, cs:HalpTimerMaxIncrement
0x140420581  jbe     short loc_1404205A3
0x140420583  xor     edi, edi
0x140420585  mov     r9, rdx; BugCheckParameter3
0x140420588  mov     edx, 113h; BugCheckParameter1
0x14042058d  mov     [rsp+48h+BugCheckParameter4], rdi; BugCheckParameter4
0x140420592  mov     ecx, 5Ch ; '\'; BugCheckCode
0x140420597  mov     r8d, 25h ; '%'; BugCheckParameter2
0x14042059d  call    KeBugCheckEx
0x1404205a3  mov     eax, cs:HalpTimerMinIncrement
0x1404205a9  cmp     rbx, rax
0x1404205ac  mov     [rsp+48h+arg_10], rsi
0x1404205b1  mov     rsi, cs:HalpClockTimer
0x1404205b8  cmovb   rbx, rax
0x1404205bc  test    byte ptr [rcx+22h], 2
0x1404205c0  jz      short loc_1404205C9
0x1404205c2  xor     ecx, ecx
0x1404205c4  call    HalpTimerSwitchToNormalClock
0x1404205c9  mov     eax, [rsi+0E0h]
0x1404205cf  cmp     edi, 1
0x1404205d2  jnz     loc_1404206A5
0x1404205d8  xor     edi, edi
0x1404205da  mov     [rsp+48h+arg_18], rdi
0x1404205df  mov     [rsp+48h+pullResult], rdi
0x1404205e4  test    al, 20h
0x1404205e6  jnz     loc_1407149B0
0x1404205ec  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x1404205f3  mov     dword ptr [rsp+48h+BugCheckParameter4], 2BBh
0x1404205fb  xor     r8d, r8d
0x1404205fe  mov     edx, 11h
0x140420603  mov     rcx, rsi
0x140420606  call    HalpTimerSetProblemEx
0x14042060b  mov     r10d, 0C00000BBh
0x140420611  jmp     short loc_140420619
0x140420613  mov     r10d, 0C0000095h
0x140420619  mov     [r14], rdi
0x14042061c  test    r10d, r10d
0x14042061f  jns     short loc_140420643
0x140420621  movsxd  r9, cs:HalpTimerLastProblem; BugCheckParameter3
0x140420628  mov     r8, rsi; BugCheckParameter2
0x14042062b  movsxd  rax, r10d
0x14042062e  mov     edx, 110h; BugCheckParameter1
0x140420633  mov     ecx, 5Ch ; '\'; BugCheckCode
0x140420638  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x14042063d  call    KeBugCheckEx
0x140420643  mov     rsi, [rsp+48h+arg_10]
0x140420648  mov     eax, r10d
0x14042064b  add     rsp, 30h
0x14042064f  pop     r14
0x140420651  pop     rdi
0x140420652  pop     rbx
0x140420653  retn
0x140420655  mov     rax, [rsp+48h+pullResult]
0x14042065a  lea     rcx, [rax+98967Fh]
0x140420661  cmp     rcx, rax
0x140420664  jb      short loc_140420613
0x140420666  mov     rax, 0D6BF94D5E57A42BDh
0x140420670  mul     rcx
0x140420673  mov     ecx, [rsi+0DCh]
0x140420679  mov     r11, rdx
0x14042067c  shr     r11, 17h
0x140420680  cmp     ecx, 40h ; '@'
0x140420683  jnb     loc_1407149D4
0x140420689  mov     eax, 1
0x14042068e  shl     rax, cl
0x140420691  cmp     r11, rax
0x140420694  jb      loc_1407149D4
0x14042069a  mov     r10d, 0C000000Dh
0x1404206a0  jmp     loc_140420619
0x1404206a5  xor     edi, edi
0x1404206a7  mov     [rsp+48h+arg_0], rbp
0x1404206ac  mov     [rsp+48h+arg_18], rdi
0x1404206b1  mov     ebp, edi
0x1404206b3  mov     [rsp+48h+pullResult], rdi
0x1404206b8  test    al, 50h
0x1404206ba  jnz     loc_140714A8B
0x1404206c0  mov     r10d, 0C00000BBh
0x1404206c6  mov     dword ptr [rsp+48h+BugCheckParameter4], 2C7h
0x1404206ce  xor     r8d, r8d
0x1404206d1  mov     edx, 11h
0x1404206d6  jmp     loc_140714B8B
0x1407149b0  mov     rcx, [rsi+0C0h]; ullMultiplicand
0x1407149b7  lea     r8, [rsp+48h+pullResult]; pullResult
0x1407149bc  mov     rdx, rbx; ullMultiplier
0x1407149bf  call    RtlULongLongMult
0x1407149c4  mov     r10d, eax
0x1407149c7  test    eax, eax
0x1407149c9  js      loc_140420619
0x1407149cf  jmp     loc_140420655
0x1407149d4  mov     r9, 2540BE400h
0x1407149de  lea     r8, [rsp+48h+arg_18]; pullResult
0x1407149e3  mov     rdx, r9; ullMultiplier
0x1407149e6  mov     rcx, r11; ullMultiplicand
0x1407149e9  call    RtlULongLongMult
0x1407149ee  test    eax, eax
0x1407149f0  jns     short loc_140714A06
0x1407149f2  mov     rdx, [rsi+0C0h]
0x1407149f9  mov     r8, r9
0x1407149fc  mov     rcx, r11
0x1407149ff  call    HalpTimerScaleCounter
0x140714a04  jmp     short loc_140714A14
0x140714a06  mov     rax, [rsp+48h+arg_18]
0x140714a0b  xor     edx, edx
0x140714a0d  div     qword ptr [rsi+0C0h]
0x140714a14  mov     rdi, rax
0x140714a17  mov     [rsi+10h], r11
0x140714a1b  mov     rax, 624DD2F1A9FBE77h
0x140714a25  mov     dword ptr [rsi+34h], 1
0x140714a2c  mul     rdi
0x140714a2f  mov     rcx, rsi
0x140714a32  sub     rdi, rdx
0x140714a35  shr     rdi, 1
0x140714a38  add     rdi, rdx
0x140714a3b  shr     rdi, 9
0x140714a3f  call    HalpTimerGetInternalData
0x140714a44  mov     rcx, rax
0x140714a47  mov     r8, r11
0x140714a4a  mov     rax, [rsi+80h]
0x140714a51  mov     edx, 3
0x140714a56  call    _guard_dispatch_icall_no_overrides
0x140714a5b  mov     r10d, eax
0x140714a5e  test    eax, eax
0x140714a60  jns     loc_140420619
0x140714a66  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140714a6d  mov     dword ptr [rsp+48h+BugCheckParameter4], 32Ah
0x140714a75  mov     r8d, eax
0x140714a78  mov     edx, 12h
0x140714a7d  mov     rcx, rsi
0x140714a80  call    HalpTimerSetProblemEx
0x140714a85  nop
0x140714a86  jmp     loc_140420619
0x140714a8b  mov     rcx, [rsi+0C0h]; ullMultiplicand
0x140714a92  lea     r8, [rsp+48h+pullResult]; pullResult
0x140714a97  mov     rdx, rbx; ullMultiplier
0x140714a9a  call    RtlULongLongMult
0x140714a9f  mov     r10d, eax
0x140714aa2  test    eax, eax
0x140714aa4  js      loc_140714B9A
0x140714aaa  mov     ecx, [rsi+0DCh]
0x140714ab0  mov     rax, 0D6BF94D5E57A42BDh
0x140714aba  mul     [rsp+48h+pullResult]
0x140714abf  mov     r11, rdx
0x140714ac2  shr     r11, 17h
0x140714ac6  cmp     ecx, 40h ; '@'
0x140714ac9  jnb     short loc_140714AE3
0x140714acb  mov     eax, 1
0x140714ad0  shl     rax, cl
0x140714ad3  cmp     r11, rax
0x140714ad6  jb      short loc_140714AE3
0x140714ad8  mov     r10d, 0C000000Dh
0x140714ade  jmp     loc_140714B9A
0x140714ae3  mov     r9, 2540BE400h
0x140714aed  lea     r8, [rsp+48h+arg_18]; pullResult
0x140714af2  mov     rdx, r9; ullMultiplier
0x140714af5  mov     rcx, r11; ullMultiplicand
0x140714af8  call    RtlULongLongMult
0x140714afd  test    eax, eax
0x140714aff  jns     short loc_140714B15
0x140714b01  mov     rdx, [rsi+0C0h]
0x140714b08  mov     r8, r9
0x140714b0b  mov     rcx, r11
0x140714b0e  call    HalpTimerScaleCounter
0x140714b13  jmp     short loc_140714B23
0x140714b15  mov     rax, [rsp+48h+arg_18]
0x140714b1a  xor     edx, edx
0x140714b1c  div     qword ptr [rsi+0C0h]
0x140714b23  mov     rbp, rax
0x140714b26  mov     [rsi+10h], r11
0x140714b2a  mov     dword ptr [rsi+34h], 1
0x140714b31  mov     rax, 624DD2F1A9FBE77h
0x140714b3b  mul     rbp
0x140714b3e  mov     eax, [rsi+0E0h]
0x140714b44  mov     rcx, rsi
0x140714b47  sub     rbp, rdx
0x140714b4a  shr     rbp, 1
0x140714b4d  add     rbp, rdx
0x140714b50  shr     rbp, 9
0x140714b54  test    al, 40h
0x140714b56  setnz   dil
0x140714b5a  lea     edx, [rdi+1]
0x140714b5d  call    HalpTimerGetInternalData
0x140714b62  mov     rcx, rax
0x140714b65  mov     r8, r11
0x140714b68  mov     rax, [rsi+80h]
0x140714b6f  call    _guard_dispatch_icall_no_overrides
0x140714b74  mov     r10d, eax
0x140714b77  test    eax, eax
0x140714b79  jns     short loc_140714B9A
0x140714b7b  mov     dword ptr [rsp+48h+BugCheckParameter4], 32Ah
0x140714b83  mov     r8d, eax
0x140714b86  mov     edx, 12h
0x140714b8b  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140714b92  mov     rcx, rsi
0x140714b95  call    HalpTimerSetProblemEx
0x140714b9a  mov     rdi, rbp
0x140714b9d  mov     rbp, [rsp+48h+arg_0]
0x140714ba2  jmp     loc_140420619
```
