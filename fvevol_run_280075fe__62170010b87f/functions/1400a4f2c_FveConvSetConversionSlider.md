# FveConvSetConversionSlider

- ea: `0x1400a4f2c`
- end: `0x1400a54e4`
- name: `FveConvSetConversionSlider`
- size: `1464`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400a4540`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x1400a29a4`
- `0x1400a2b64`
- `0x1400a4308`
- `0x1400a4e6c`
- `0x1400a4f2c`
- `0x1400b6554`
- `0x1400b6898`
- `0x1400b86b8`
- `0x1400bbc9c`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400a532b`
- `ntoskrnl!KeReadStateEvent` at `0x1400a532b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400a531c`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400a531c`
- `ntoskrnl!KeClearEvent` at `0x1400a52ba`
- `ntoskrnl!KeClearEvent` at `0x1400a52ba`
- `ntoskrnl!KeSetEvent` at `0x1400a52dc`
- `ntoskrnl!KeSetEvent` at `0x1400a52dc`
- `ntoskrnl!KeBugCheckEx` at `0x1400a503e`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5209`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5243`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5489`
- `ntoskrnl!KeBugCheckEx` at `0x1400a503e`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5209`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5243`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5489`

## pseudocode

```c
__int64 __fastcall FveConvSetConversionSlider(__int64 a1, unsigned __int64 a2, __int64 a3, _BYTE *a4, __int64 a5)
{
  unsigned int v6; // r12d
  unsigned __int64 v7; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  int v12; // esi
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r9
  int v15; // eax
  unsigned __int64 v16; // rax
  __int64 v17; // rax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // edx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  unsigned __int64 v27; // r14
  __int64 v28; // r13
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG pullResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  PVOID Object[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[208]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+168h] [rbp+68h] BYREF

  v42 = 0;
  *(_OWORD *)Object = 0;
  v35 = 0;
  v6 = a3;
  pullResult = 0;
  v7 = a2;
  v38 = 0;
  v39 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
  }
  v9 = *(_QWORD *)(v7 + 72);
  v34 = v9;
  if ( !v6 )
  {
    v10 = *(_QWORD *)(v7 + 64);
    if ( v10 <= v9 )
    {
      v11 = *(_QWORD *)(a1 + 1040);
      v12 = 0;
      if ( *(_BYTE *)(v7 + 4) )
      {
        if ( v11 >= v10 && v11 < v9 )
          goto LABEL_61;
        v13 = *(_QWORD *)(a1 + 1040);
        v14 = *(_QWORD *)(a1 + 1048);
        a2 = v11 + *(_QWORD *)(v7 + 80);
        v37 = v13;
        if ( a2 > v14 || a2 < v11 )
        {
          v34 = v14;
        }
        else
        {
          v15 = FveTpAlignUp(a1, a2, &v34);
          v12 = v15;
          if ( v15 < 0 )
            KeBugCheckEx(0x120u, 0xCu, 0, 0, v15);
          v14 = v34;
        }
      }
      else
      {
        if ( v11 > v10 && v11 <= v9 )
          goto LABEL_61;
        v16 = *(_QWORD *)(v7 + 80);
        if ( v11 <= v16 )
          v13 = 0;
        else
          v13 = v11 - v16;
        v14 = *(_QWORD *)(a1 + 1040);
        v34 = v14;
        v11 = v13;
        v37 = v13;
      }
      v17 = *(_QWORD *)(v7 + 296);
      if ( v11 == v17 && v14 == v17 )
      {
        *(_QWORD *)(v7 + 512) = v17;
        v6 = 1;
        *(_QWORD *)(v7 + 520) = v17;
        *(_QWORD *)(v7 + 64) = v17;
        *(_QWORD *)(v7 + 72) = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          goto LABEL_29;
        }
        v19 = 142;
LABEL_28:
        WPP_SF_(v18->AttachedDevice, v19, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
LABEL_29:
        LOBYTE(a3) = 1;
        *(_BYTE *)(v7 + 432) = 1;
        FveConvResumeRangeIo(a1, v7, a3);
        goto LABEL_32;
      }
      LOBYTE(a2) = *(_BYTE *)(v7 + 4);
      if ( (unsigned __int8)FveGetUpperRangeEx(a1, a2, v13, v14, &v42, &v35, &pullResult, 0) )
      {
        v21 = v42;
        v22 = v35;
        *(_QWORD *)(v7 + 512) = v42;
        *(_QWORD *)(v7 + 520) = v22;
        *(_QWORD *)(v7 + 64) = v21;
        *(_QWORD *)(v7 + 72) = v22;
        goto LABEL_32;
      }
      if ( *a4 )
      {
        FvepReleaseDevFveLock(a5);
        *a4 = 0;
      }
      LOBYTE(v20) = *(_BYTE *)(v7 + 4);
      FveConvAlignConversionSliderToClusters(a1, v7 + 592, v20, (int)&v42, (__int64)&v35, &pullResult);
      LOBYTE(v23) = *(_BYTE *)(v7 + 4);
      FveConvAlignConversionSliderToBootBlock(a1, v23, (int)&v42, (int)&v35, &pullResult);
      v24 = FveFsAlignVolumeRangeToClusters((int)v7 + 592, v42, pullResult, (unsigned int)&v38, (__int64)&v39);
      if ( v24 < 0 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, v24);
      v25 = FveConvPrepareUsedBitmap(a1, v38, v39);
      v12 = v25;
      if ( v25 < 0 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, v25);
      LOBYTE(v26) = *(_BYTE *)(v7 + 4);
      if ( !(unsigned __int8)FveGetLowerRange(a1, v26, v42, v35, &v37, &v34, &v38) )
      {
        FveConvResumeRangeIo(a1, v7, 0);
        v27 = v37;
        v28 = v34;
        *(_QWORD *)(v7 + 512) = v37;
        *(_QWORD *)(v7 + 520) = v28;
        KeClearEvent((PRKEVENT)(v7 + 488));
        *(_DWORD *)(v7 + 528) = 0;
        KeSetEvent((PRKEVENT)(v7 + 464), 0, 0);
        Object[0] = (PVOID)(v7 + 488);
        Object[1] = (PVOID)(v7 + 440);
        KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
        if ( KeReadStateEvent((PRKEVENT)(v7 + 440)) )
        {
          v6 = 3;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
          }
        }
        else
        {
          v12 = *(_DWORD *)(v7 + 528);
          if ( v12 < 0 )
          {
LABEL_55:
            memset(v41, 0, 0x90u);
            LOBYTE(v32) = 1;
            FvepAcquireDevFveLock(a1, v41, v32);
            v6 = 2;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                145,
                WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
                (unsigned int)v12);
            }
            *(_DWORD *)(a1 + 1440) = v12;
            FvepReleaseDevFveLock(v41);
            goto LABEL_61;
          }
          v29 = *(_QWORD *)(v7 + 64);
          if ( v29 == v27 )
          {
            v30 = *(_QWORD *)(v7 + 72);
            if ( v30 == v28 )
            {
              v31 = *(_QWORD *)(v7 + 296);
              if ( v29 == v31 && v30 == v31 )
              {
                v6 = 1;
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                {
                  goto LABEL_29;
                }
                v19 = 144;
                goto LABEL_28;
              }
            }
          }
        }
LABEL_32:
        if ( v12 >= 0 )
          goto LABEL_61;
        goto LABEL_55;
      }
    }
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
LABEL_61:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1400a4f2c  push    rbp
0x1400a4f2e  push    rbx
0x1400a4f2f  push    rsi
0x1400a4f30  push    rdi
0x1400a4f31  push    r12
0x1400a4f33  push    r13
0x1400a4f35  push    r14
0x1400a4f37  push    r15
0x1400a4f39  lea     rbp, [rsp-18h]
0x1400a4f3e  sub     rsp, 118h
0x1400a4f45  xorps   xmm0, xmm0
0x1400a4f48  mov     [rbp+50h+arg_8], 0
0x1400a4f50  movups  xmmword ptr [rsp+150h+Object], xmm0
0x1400a4f55  mov     r13, r9
0x1400a4f58  mov     [rsp+150h+var_108], 0
0x1400a4f61  mov     r12d, r8d
0x1400a4f64  mov     [rsp+150h+pullResult], 0
0x1400a4f6d  mov     rdi, rdx
0x1400a4f70  mov     [rsp+150h+var_F0], 0
0x1400a4f79  mov     r15, rcx
0x1400a4f7c  mov     [rsp+150h+var_E8], 0
0x1400a4f85  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4f8c  lea     rax, WPP_GLOBAL_Control
0x1400a4f93  cmp     rcx, rax
0x1400a4f96  jz      short loc_1400A4FBA
0x1400a4f98  mov     eax, [rcx+2Ch]
0x1400a4f9b  test    al, 2
0x1400a4f9d  jz      short loc_1400A4FBA
0x1400a4f9f  cmp     byte ptr [rcx+29h], 5
0x1400a4fa3  jb      short loc_1400A4FBA
0x1400a4fa5  mov     rcx, [rcx+18h]
0x1400a4fa9  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a4fb0  mov     edx, 8Dh
0x1400a4fb5  call    WPP_SF_
0x1400a4fba  mov     rax, [rdi+48h]
0x1400a4fbe  mov     [rsp+150h+var_110], rax
0x1400a4fc3  test    r12d, r12d
0x1400a4fc6  jnz     loc_1400A5496
0x1400a4fcc  mov     rcx, [rdi+40h]
0x1400a4fd0  cmp     rcx, rax
0x1400a4fd3  ja      loc_1400A5471
0x1400a4fd9  mov     rbx, [r15+410h]
0x1400a4fe0  xor     esi, esi
0x1400a4fe2  cmp     [rdi+4], sil
0x1400a4fe6  jz      short loc_1400A5059
0x1400a4fe8  cmp     rbx, rcx
0x1400a4feb  jb      short loc_1400A4FF6
0x1400a4fed  cmp     rbx, rax
0x1400a4ff0  jb      loc_1400A5496
0x1400a4ff6  mov     rdx, [rdi+50h]
0x1400a4ffa  mov     r14, rbx
0x1400a4ffd  mov     r9, [r15+418h]
0x1400a5004  add     rdx, rbx
0x1400a5007  mov     [rsp+150h+var_F8], rbx
0x1400a500c  cmp     rdx, r9
0x1400a500f  ja      short loc_1400A5052
0x1400a5011  cmp     rdx, rbx
0x1400a5014  jb      short loc_1400A5052
0x1400a5016  lea     r8, [rsp+150h+var_110]
0x1400a501b  mov     rcx, r15
0x1400a501e  call    FveTpAlignUp
0x1400a5023  movsxd  rsi, eax
0x1400a5026  test    eax, eax
0x1400a5028  jns     short loc_1400A504B
0x1400a502a  xor     r9d, r9d; BugCheckParameter3
0x1400a502d  mov     [rsp+150h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400a5032  xor     r8d, r8d; BugCheckParameter2
0x1400a5035  mov     ecx, 120h; BugCheckCode
0x1400a503a  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a503e  call    cs:__imp_KeBugCheckEx
0x1400a504b  mov     r9, [rsp+150h+var_110]
0x1400a5050  jmp     short loc_1400A508B
0x1400a5052  mov     [rsp+150h+var_110], r9
0x1400a5057  jmp     short loc_1400A508B
0x1400a5059  cmp     rbx, rcx
0x1400a505c  jbe     short loc_1400A5067
0x1400a505e  cmp     rbx, rax
0x1400a5061  jbe     loc_1400A5496
0x1400a5067  mov     rax, [rdi+50h]
0x1400a506b  cmp     rbx, rax
0x1400a506e  jbe     short loc_1400A5078
0x1400a5070  mov     r14, rbx
0x1400a5073  sub     r14, rax
0x1400a5076  jmp     short loc_1400A507B
0x1400a5078  xor     r14d, r14d
0x1400a507b  mov     r9, rbx
0x1400a507e  mov     [rsp+150h+var_110], rbx
0x1400a5083  mov     rbx, r14
0x1400a5086  mov     [rsp+150h+var_F8], r14
0x1400a508b  mov     rax, [rdi+128h]
0x1400a5092  cmp     rbx, rax
0x1400a5095  jnz     short loc_1400A5104
0x1400a5097  cmp     r9, rax
0x1400a509a  jnz     short loc_1400A5104
0x1400a509c  mov     [rdi+200h], rax
0x1400a50a3  mov     r12d, 1
0x1400a50a9  mov     [rdi+208h], rax
0x1400a50b0  mov     [rdi+40h], rax
0x1400a50b4  mov     [rdi+48h], rax
0x1400a50b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a50bf  lea     rbx, WPP_GLOBAL_Control
0x1400a50c6  cmp     rcx, rbx
0x1400a50c9  jz      short loc_1400A50ED
0x1400a50cb  mov     eax, [rcx+2Ch]
0x1400a50ce  test    al, 2
0x1400a50d0  jz      short loc_1400A50ED
0x1400a50d2  cmp     byte ptr [rcx+29h], 5
0x1400a50d6  jb      short loc_1400A50ED
0x1400a50d8  mov     edx, 8Eh
0x1400a50dd  mov     rcx, [rcx+18h]
0x1400a50e1  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a50e8  call    WPP_SF_
0x1400a50ed  mov     r8b, r12b
0x1400a50f0  mov     [rdi+1B0h], r12b
0x1400a50f7  mov     rdx, rdi
0x1400a50fa  mov     rcx, r15
0x1400a50fd  call    FveConvResumeRangeIo
0x1400a5102  jmp     short loc_1400A515E
0x1400a5104  mov     dl, [rdi+4]
0x1400a5107  lea     rax, [rsp+150h+pullResult]
0x1400a510c  mov     byte ptr [rsp+150h+WaitBlockArray], 0
0x1400a5111  mov     r8, r14
0x1400a5114  mov     [rsp+150h+Timeout], rax
0x1400a5119  mov     rcx, r15
0x1400a511c  lea     rax, [rsp+150h+var_108]
0x1400a5121  mov     qword ptr [rsp+150h+Alertable], rax
0x1400a5126  lea     rax, [rbp+50h+arg_8]
0x1400a512a  mov     [rsp+150h+BugCheckParameter4], rax
0x1400a512f  call    FveGetUpperRangeEx
0x1400a5134  test    al, al
0x1400a5136  jz      short loc_1400A516B
0x1400a5138  mov     rcx, [rbp+50h+arg_8]
0x1400a513c  mov     rax, [rsp+150h+var_108]
0x1400a5141  mov     [rdi+200h], rcx
0x1400a5148  mov     [rdi+208h], rax
0x1400a514f  mov     [rdi+40h], rcx
0x1400a5153  mov     [rdi+48h], rax
0x1400a5157  lea     rbx, WPP_GLOBAL_Control
0x1400a515e  test    esi, esi
0x1400a5160  jns     loc_1400A549D
0x1400a5166  jmp     loc_1400A5407
0x1400a516b  cmp     byte ptr [r13+0], 0
0x1400a5170  jz      short loc_1400A5183
0x1400a5172  mov     rcx, [rbp+50h+arg_20]
0x1400a5179  call    FvepReleaseDevFveLock
0x1400a517e  mov     byte ptr [r13+0], 0
0x1400a5183  mov     r8b, [rdi+4]; int
0x1400a5187  lea     rax, [rsp+150h+pullResult]
0x1400a518c  mov     qword ptr [rsp+150h+Alertable], rax; pullResult
0x1400a5191  lea     rbx, [rdi+250h]
0x1400a5198  lea     rax, [rsp+150h+var_108]
0x1400a519d  mov     rdx, rbx; int
0x1400a51a0  lea     r9, [rbp+50h+arg_8]; int
0x1400a51a4  mov     [rsp+150h+BugCheckParameter4], rax; __int64
0x1400a51a9  mov     rcx, r15; int
0x1400a51ac  call    FveConvAlignConversionSliderToClusters
0x1400a51b1  mov     dl, [rdi+4]; int
0x1400a51b4  lea     rax, [rsp+150h+pullResult]
0x1400a51b9  lea     r9, [rsp+150h+var_108]; int
0x1400a51be  mov     [rsp+150h+BugCheckParameter4], rax; pullResult
0x1400a51c3  lea     r8, [rbp+50h+arg_8]; int
0x1400a51c7  mov     rcx, r15; int
0x1400a51ca  call    FveConvAlignConversionSliderToBootBlock
0x1400a51cf  mov     r8, [rsp+150h+pullResult]
0x1400a51d4  lea     rax, [rsp+150h+var_E8]
0x1400a51d9  mov     rdx, [rbp+50h+arg_8]
0x1400a51dd  lea     r9, [rsp+150h+var_F0]
0x1400a51e2  mov     rcx, rbx
0x1400a51e5  mov     [rsp+150h+BugCheckParameter4], rax
0x1400a51ea  call    FveFsAlignVolumeRangeToClusters
0x1400a51ef  test    eax, eax
0x1400a51f1  jns     short loc_1400A5216
0x1400a51f3  xor     r9d, r9d; BugCheckParameter3
0x1400a51f6  cdqe
0x1400a51f8  xor     r8d, r8d; BugCheckParameter2
0x1400a51fb  mov     [rsp+150h+BugCheckParameter4], rax; BugCheckParameter4
0x1400a5200  mov     ecx, 120h; BugCheckCode
0x1400a5205  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a5209  call    cs:__imp_KeBugCheckEx
0x1400a5216  mov     r8, [rsp+150h+var_E8]
0x1400a521b  mov     rcx, r15
0x1400a521e  mov     rdx, [rsp+150h+var_F0]
0x1400a5223  call    FveConvPrepareUsedBitmap
0x1400a5228  movsxd  rsi, eax
0x1400a522b  test    eax, eax
0x1400a522d  jns     short loc_1400A5250
0x1400a522f  xor     r9d, r9d; BugCheckParameter3
0x1400a5232  mov     [rsp+150h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400a5237  xor     r8d, r8d; BugCheckParameter2
0x1400a523a  mov     ecx, 120h; BugCheckCode
0x1400a523f  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a5243  call    cs:__imp_KeBugCheckEx
0x1400a5250  mov     r9, [rsp+150h+var_108]
0x1400a5255  lea     rax, [rsp+150h+var_F0]
0x1400a525a  mov     r8, [rbp+50h+arg_8]
0x1400a525e  mov     rcx, r15
0x1400a5261  mov     dl, [rdi+4]
0x1400a5264  mov     [rsp+150h+Timeout], rax
0x1400a5269  lea     rax, [rsp+150h+var_110]
0x1400a526e  mov     qword ptr [rsp+150h+Alertable], rax
0x1400a5273  lea     rax, [rsp+150h+var_F8]
0x1400a5278  mov     [rsp+150h+BugCheckParameter4], rax
0x1400a527d  call    FveGetLowerRange
0x1400a5282  test    al, al
0x1400a5284  jnz     loc_1400A5471
0x1400a528a  xor     r8d, r8d
0x1400a528d  mov     rdx, rdi
0x1400a5290  mov     rcx, r15
0x1400a5293  call    FveConvResumeRangeIo
0x1400a5298  mov     r14, [rsp+150h+var_F8]
0x1400a529d  lea     rbx, [rdi+1E8h]
0x1400a52a4  mov     r13, [rsp+150h+var_110]
0x1400a52a9  mov     rcx, rbx; Event
0x1400a52ac  mov     [rdi+200h], r14
0x1400a52b3  mov     [rdi+208h], r13
0x1400a52ba  call    cs:__imp_KeClearEvent
0x1400a52c1  nop     dword ptr [rax+rax+00h]
0x1400a52c6  lea     rcx, [rdi+1D0h]; Event
0x1400a52cd  mov     dword ptr [rdi+210h], 0
0x1400a52d7  xor     r8d, r8d; Wait
0x1400a52da  xor     edx, edx; Increment
0x1400a52dc  call    cs:__imp_KeSetEvent
0x1400a52e3  nop     dword ptr [rax+rax+00h]
0x1400a52e8  xor     eax, eax
0x1400a52ea  mov     [rsp+150h+Object], rbx
0x1400a52ef  mov     [rsp+150h+WaitBlockArray], rax; WaitBlockArray
0x1400a52f4  lea     rbx, [rdi+1B8h]
0x1400a52fb  mov     [rsp+150h+Timeout], rax; Timeout
0x1400a5300  lea     rdx, [rsp+150h+Object]; Object
0x1400a5305  mov     [rsp+150h+Alertable], al; Alertable
0x1400a5309  xor     r9d, r9d; WaitReason
0x1400a530c  lea     r8d, [rax+1]; WaitType
0x1400a5310  mov     [rsp+150h+Object+8], rbx
0x1400a5315  lea     ecx, [rax+2]; Count
0x1400a5318  mov     byte ptr [rsp+150h+BugCheckParameter4], al; WaitMode
0x1400a531c  call    cs:__imp_KeWaitForMultipleObjects
0x1400a5323  nop     dword ptr [rax+rax+00h]
0x1400a5328  mov     rcx, rbx; Event
0x1400a532b  call    cs:__imp_KeReadStateEvent
0x1400a5332  nop     dword ptr [rax+rax+00h]
0x1400a5337  test    eax, eax
0x1400a5339  jz      short loc_1400A5387
0x1400a533b  mov     r12d, 3
0x1400a5341  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5348  lea     rbx, WPP_GLOBAL_Control
0x1400a534f  cmp     rcx, rbx
0x1400a5352  jz      loc_1400A515E
0x1400a5358  mov     eax, [rcx+2Ch]
0x1400a535b  test    al, 2
0x1400a535d  jz      loc_1400A515E
0x1400a5363  cmp     byte ptr [rcx+29h], 5
0x1400a5367  jb      loc_1400A515E
0x1400a536d  mov     rcx, [rcx+18h]
0x1400a5371  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x1400a5378  mov     edx, 8Fh
0x1400a537d  call    WPP_SF_
0x1400a5382  jmp     loc_1400A515E
0x1400a5387  mov     esi, [rdi+210h]
0x1400a538d  test    esi, esi
0x1400a538f  js      short loc_1400A5400
0x1400a5391  mov     rdx, [rdi+40h]
0x1400a5395  cmp     rdx, r14
0x1400a5398  jnz     loc_1400A5157
0x1400a539e  mov     rcx, [rdi+48h]
0x1400a53a2  cmp     rcx, r13
0x1400a53a5  jnz     loc_1400A5157
0x1400a53ab  mov     rax, [rdi+128h]
0x1400a53b2  cmp     rdx, rax
0x1400a53b5  jnz     loc_1400A5157
0x1400a53bb  cmp     rcx, rax
0x1400a53be  jnz     loc_1400A5157
0x1400a53c4  mov     r12d, 1
0x1400a53ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a53d1  lea     rbx, WPP_GLOBAL_Control
0x1400a53d8  cmp     rcx, rbx
0x1400a53db  jz      loc_1400A50ED
0x1400a53e1  mov     eax, [rcx+2Ch]
0x1400a53e4  test    al, 2
0x1400a53e6  jz      loc_1400A50ED
0x1400a53ec  cmp     byte ptr [rcx+29h], 5
0x1400a53f0  jb      loc_1400A50ED
0x1400a53f6  mov     edx, 90h
0x1400a53fb  jmp     loc_1400A50DD
0x1400a5400  lea     rbx, WPP_GLOBAL_Control
0x1400a5407  xor     edx, edx; Val
0x1400a5409  lea     rcx, [rbp+50h+var_D0]; void *
0x1400a540d  mov     r8d, 90h; Size
0x1400a5413  call    memset
0x1400a5418  mov     r8b, 1
0x1400a541b  lea     rdx, [rbp+50h+var_D0]
0x1400a541f  mov     rcx, r15
0x1400a5422  call    FvepAcquireDevFveLock
0x1400a5427  mov     r12d, 2
0x1400a542d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5434  cmp     rcx, rbx
0x1400a5437  jz      short loc_1400A545F
0x1400a5439  mov     eax, [rcx+2Ch]
0x1400a543c  test    r12b, al
0x1400a543f  jz      short loc_1400A545F
0x1400a5441  cmp     [rcx+29h], r12b
  ... truncated ...
```
