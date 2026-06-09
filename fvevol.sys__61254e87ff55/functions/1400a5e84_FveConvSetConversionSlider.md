# FveConvSetConversionSlider

- ea: `0x1400a5e84`
- end: `0x1400a643c`
- name: `FveConvSetConversionSlider`
- size: `1464`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400a5490`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x1400a38f4`
- `0x1400a3ab4`
- `0x1400a5258`
- `0x1400a5dc4`
- `0x1400a5e84`
- `0x1400b7850`
- `0x1400b7b94`
- `0x1400b99e4`
- `0x1400bf70c`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400a6283`
- `ntoskrnl!KeReadStateEvent` at `0x1400a6283`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400a6274`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400a6274`
- `ntoskrnl!KeClearEvent` at `0x1400a6212`
- `ntoskrnl!KeClearEvent` at `0x1400a6212`
- `ntoskrnl!KeSetEvent` at `0x1400a6234`
- `ntoskrnl!KeSetEvent` at `0x1400a6234`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5f96`
- `ntoskrnl!KeBugCheckEx` at `0x1400a6161`
- `ntoskrnl!KeBugCheckEx` at `0x1400a619b`
- `ntoskrnl!KeBugCheckEx` at `0x1400a63e1`
- `ntoskrnl!KeBugCheckEx` at `0x1400a5f96`
- `ntoskrnl!KeBugCheckEx` at `0x1400a6161`
- `ntoskrnl!KeBugCheckEx` at `0x1400a619b`
- `ntoskrnl!KeBugCheckEx` at `0x1400a63e1`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
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
        WPP_SF_(v18->AttachedDevice, v19, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
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
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
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
                WPP_8d48425948c73b66a608165fe5646329_Traceguids,
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1400a5e84  push    rbp
0x1400a5e86  push    rbx
0x1400a5e87  push    rsi
0x1400a5e88  push    rdi
0x1400a5e89  push    r12
0x1400a5e8b  push    r13
0x1400a5e8d  push    r14
0x1400a5e8f  push    r15
0x1400a5e91  lea     rbp, [rsp-18h]
0x1400a5e96  sub     rsp, 118h
0x1400a5e9d  xorps   xmm0, xmm0
0x1400a5ea0  mov     [rbp+50h+arg_8], 0
0x1400a5ea8  movups  xmmword ptr [rsp+150h+Object], xmm0
0x1400a5ead  mov     r13, r9
0x1400a5eb0  mov     [rsp+150h+var_108], 0
0x1400a5eb9  mov     r12d, r8d
0x1400a5ebc  mov     [rsp+150h+pullResult], 0
0x1400a5ec5  mov     rdi, rdx
0x1400a5ec8  mov     [rsp+150h+var_F0], 0
0x1400a5ed1  mov     r15, rcx
0x1400a5ed4  mov     [rsp+150h+var_E8], 0
0x1400a5edd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5ee4  lea     rax, WPP_GLOBAL_Control
0x1400a5eeb  cmp     rcx, rax
0x1400a5eee  jz      short loc_1400A5F12
0x1400a5ef0  mov     eax, [rcx+2Ch]
0x1400a5ef3  test    al, 2
0x1400a5ef5  jz      short loc_1400A5F12
0x1400a5ef7  cmp     byte ptr [rcx+29h], 5
0x1400a5efb  jb      short loc_1400A5F12
0x1400a5efd  mov     rcx, [rcx+18h]
0x1400a5f01  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a5f08  mov     edx, 8Dh
0x1400a5f0d  call    WPP_SF_
0x1400a5f12  mov     rax, [rdi+48h]
0x1400a5f16  mov     [rsp+150h+var_110], rax
0x1400a5f1b  test    r12d, r12d
0x1400a5f1e  jnz     loc_1400A63EE
0x1400a5f24  mov     rcx, [rdi+40h]
0x1400a5f28  cmp     rcx, rax
0x1400a5f2b  ja      loc_1400A63C9
0x1400a5f31  mov     rbx, [r15+410h]
0x1400a5f38  xor     esi, esi
0x1400a5f3a  cmp     [rdi+4], sil
0x1400a5f3e  jz      short loc_1400A5FB1
0x1400a5f40  cmp     rbx, rcx
0x1400a5f43  jb      short loc_1400A5F4E
0x1400a5f45  cmp     rbx, rax
0x1400a5f48  jb      loc_1400A63EE
0x1400a5f4e  mov     rdx, [rdi+50h]
0x1400a5f52  mov     r14, rbx
0x1400a5f55  mov     r9, [r15+418h]
0x1400a5f5c  add     rdx, rbx
0x1400a5f5f  mov     [rsp+150h+var_F8], rbx
0x1400a5f64  cmp     rdx, r9
0x1400a5f67  ja      short loc_1400A5FAA
0x1400a5f69  cmp     rdx, rbx
0x1400a5f6c  jb      short loc_1400A5FAA
0x1400a5f6e  lea     r8, [rsp+150h+var_110]
0x1400a5f73  mov     rcx, r15
0x1400a5f76  call    FveTpAlignUp
0x1400a5f7b  movsxd  rsi, eax
0x1400a5f7e  test    eax, eax
0x1400a5f80  jns     short loc_1400A5FA3
0x1400a5f82  xor     r9d, r9d; BugCheckParameter3
0x1400a5f85  mov     [rsp+150h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400a5f8a  xor     r8d, r8d; BugCheckParameter2
0x1400a5f8d  mov     ecx, 120h; BugCheckCode
0x1400a5f92  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a5f96  call    cs:__imp_KeBugCheckEx
0x1400a5fa3  mov     r9, [rsp+150h+var_110]
0x1400a5fa8  jmp     short loc_1400A5FE3
0x1400a5faa  mov     [rsp+150h+var_110], r9
0x1400a5faf  jmp     short loc_1400A5FE3
0x1400a5fb1  cmp     rbx, rcx
0x1400a5fb4  jbe     short loc_1400A5FBF
0x1400a5fb6  cmp     rbx, rax
0x1400a5fb9  jbe     loc_1400A63EE
0x1400a5fbf  mov     rax, [rdi+50h]
0x1400a5fc3  cmp     rbx, rax
0x1400a5fc6  jbe     short loc_1400A5FD0
0x1400a5fc8  mov     r14, rbx
0x1400a5fcb  sub     r14, rax
0x1400a5fce  jmp     short loc_1400A5FD3
0x1400a5fd0  xor     r14d, r14d
0x1400a5fd3  mov     r9, rbx
0x1400a5fd6  mov     [rsp+150h+var_110], rbx
0x1400a5fdb  mov     rbx, r14
0x1400a5fde  mov     [rsp+150h+var_F8], r14
0x1400a5fe3  mov     rax, [rdi+128h]
0x1400a5fea  cmp     rbx, rax
0x1400a5fed  jnz     short loc_1400A605C
0x1400a5fef  cmp     r9, rax
0x1400a5ff2  jnz     short loc_1400A605C
0x1400a5ff4  mov     [rdi+200h], rax
0x1400a5ffb  mov     r12d, 1
0x1400a6001  mov     [rdi+208h], rax
0x1400a6008  mov     [rdi+40h], rax
0x1400a600c  mov     [rdi+48h], rax
0x1400a6010  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6017  lea     rbx, WPP_GLOBAL_Control
0x1400a601e  cmp     rcx, rbx
0x1400a6021  jz      short loc_1400A6045
0x1400a6023  mov     eax, [rcx+2Ch]
0x1400a6026  test    al, 2
0x1400a6028  jz      short loc_1400A6045
0x1400a602a  cmp     byte ptr [rcx+29h], 5
0x1400a602e  jb      short loc_1400A6045
0x1400a6030  mov     edx, 8Eh
0x1400a6035  mov     rcx, [rcx+18h]
0x1400a6039  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a6040  call    WPP_SF_
0x1400a6045  mov     r8b, r12b
0x1400a6048  mov     [rdi+1B0h], r12b
0x1400a604f  mov     rdx, rdi
0x1400a6052  mov     rcx, r15
0x1400a6055  call    FveConvResumeRangeIo
0x1400a605a  jmp     short loc_1400A60B6
0x1400a605c  mov     dl, [rdi+4]
0x1400a605f  lea     rax, [rsp+150h+pullResult]
0x1400a6064  mov     byte ptr [rsp+150h+WaitBlockArray], 0
0x1400a6069  mov     r8, r14
0x1400a606c  mov     [rsp+150h+Timeout], rax
0x1400a6071  mov     rcx, r15
0x1400a6074  lea     rax, [rsp+150h+var_108]
0x1400a6079  mov     qword ptr [rsp+150h+Alertable], rax
0x1400a607e  lea     rax, [rbp+50h+arg_8]
0x1400a6082  mov     [rsp+150h+BugCheckParameter4], rax
0x1400a6087  call    FveGetUpperRangeEx
0x1400a608c  test    al, al
0x1400a608e  jz      short loc_1400A60C3
0x1400a6090  mov     rcx, [rbp+50h+arg_8]
0x1400a6094  mov     rax, [rsp+150h+var_108]
0x1400a6099  mov     [rdi+200h], rcx
0x1400a60a0  mov     [rdi+208h], rax
0x1400a60a7  mov     [rdi+40h], rcx
0x1400a60ab  mov     [rdi+48h], rax
0x1400a60af  lea     rbx, WPP_GLOBAL_Control
0x1400a60b6  test    esi, esi
0x1400a60b8  jns     loc_1400A63F5
0x1400a60be  jmp     loc_1400A635F
0x1400a60c3  cmp     byte ptr [r13+0], 0
0x1400a60c8  jz      short loc_1400A60DB
0x1400a60ca  mov     rcx, [rbp+50h+arg_20]
0x1400a60d1  call    FvepReleaseDevFveLock
0x1400a60d6  mov     byte ptr [r13+0], 0
0x1400a60db  mov     r8b, [rdi+4]; int
0x1400a60df  lea     rax, [rsp+150h+pullResult]
0x1400a60e4  mov     qword ptr [rsp+150h+Alertable], rax; pullResult
0x1400a60e9  lea     rbx, [rdi+250h]
0x1400a60f0  lea     rax, [rsp+150h+var_108]
0x1400a60f5  mov     rdx, rbx; int
0x1400a60f8  lea     r9, [rbp+50h+arg_8]; int
0x1400a60fc  mov     [rsp+150h+BugCheckParameter4], rax; __int64
0x1400a6101  mov     rcx, r15; int
0x1400a6104  call    FveConvAlignConversionSliderToClusters
0x1400a6109  mov     dl, [rdi+4]; int
0x1400a610c  lea     rax, [rsp+150h+pullResult]
0x1400a6111  lea     r9, [rsp+150h+var_108]; int
0x1400a6116  mov     [rsp+150h+BugCheckParameter4], rax; pullResult
0x1400a611b  lea     r8, [rbp+50h+arg_8]; int
0x1400a611f  mov     rcx, r15; int
0x1400a6122  call    FveConvAlignConversionSliderToBootBlock
0x1400a6127  mov     r8, [rsp+150h+pullResult]
0x1400a612c  lea     rax, [rsp+150h+var_E8]
0x1400a6131  mov     rdx, [rbp+50h+arg_8]
0x1400a6135  lea     r9, [rsp+150h+var_F0]
0x1400a613a  mov     rcx, rbx
0x1400a613d  mov     [rsp+150h+BugCheckParameter4], rax
0x1400a6142  call    FveFsAlignVolumeRangeToClusters
0x1400a6147  test    eax, eax
0x1400a6149  jns     short loc_1400A616E
0x1400a614b  xor     r9d, r9d; BugCheckParameter3
0x1400a614e  cdqe
0x1400a6150  xor     r8d, r8d; BugCheckParameter2
0x1400a6153  mov     [rsp+150h+BugCheckParameter4], rax; BugCheckParameter4
0x1400a6158  mov     ecx, 120h; BugCheckCode
0x1400a615d  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a6161  call    cs:__imp_KeBugCheckEx
0x1400a616e  mov     r8, [rsp+150h+var_E8]
0x1400a6173  mov     rcx, r15
0x1400a6176  mov     rdx, [rsp+150h+var_F0]
0x1400a617b  call    FveConvPrepareUsedBitmap
0x1400a6180  movsxd  rsi, eax
0x1400a6183  test    eax, eax
0x1400a6185  jns     short loc_1400A61A8
0x1400a6187  xor     r9d, r9d; BugCheckParameter3
0x1400a618a  mov     [rsp+150h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400a618f  xor     r8d, r8d; BugCheckParameter2
0x1400a6192  mov     ecx, 120h; BugCheckCode
0x1400a6197  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a619b  call    cs:__imp_KeBugCheckEx
0x1400a61a8  mov     r9, [rsp+150h+var_108]
0x1400a61ad  lea     rax, [rsp+150h+var_F0]
0x1400a61b2  mov     r8, [rbp+50h+arg_8]
0x1400a61b6  mov     rcx, r15
0x1400a61b9  mov     dl, [rdi+4]
0x1400a61bc  mov     [rsp+150h+Timeout], rax
0x1400a61c1  lea     rax, [rsp+150h+var_110]
0x1400a61c6  mov     qword ptr [rsp+150h+Alertable], rax
0x1400a61cb  lea     rax, [rsp+150h+var_F8]
0x1400a61d0  mov     [rsp+150h+BugCheckParameter4], rax
0x1400a61d5  call    FveGetLowerRange
0x1400a61da  test    al, al
0x1400a61dc  jnz     loc_1400A63C9
0x1400a61e2  xor     r8d, r8d
0x1400a61e5  mov     rdx, rdi
0x1400a61e8  mov     rcx, r15
0x1400a61eb  call    FveConvResumeRangeIo
0x1400a61f0  mov     r14, [rsp+150h+var_F8]
0x1400a61f5  lea     rbx, [rdi+1E8h]
0x1400a61fc  mov     r13, [rsp+150h+var_110]
0x1400a6201  mov     rcx, rbx; Event
0x1400a6204  mov     [rdi+200h], r14
0x1400a620b  mov     [rdi+208h], r13
0x1400a6212  call    cs:__imp_KeClearEvent
0x1400a6219  nop     dword ptr [rax+rax+00h]
0x1400a621e  lea     rcx, [rdi+1D0h]; Event
0x1400a6225  mov     dword ptr [rdi+210h], 0
0x1400a622f  xor     r8d, r8d; Wait
0x1400a6232  xor     edx, edx; Increment
0x1400a6234  call    cs:__imp_KeSetEvent
0x1400a623b  nop     dword ptr [rax+rax+00h]
0x1400a6240  xor     eax, eax
0x1400a6242  mov     [rsp+150h+Object], rbx
0x1400a6247  mov     [rsp+150h+WaitBlockArray], rax; WaitBlockArray
0x1400a624c  lea     rbx, [rdi+1B8h]
0x1400a6253  mov     [rsp+150h+Timeout], rax; Timeout
0x1400a6258  lea     rdx, [rsp+150h+Object]; Object
0x1400a625d  mov     [rsp+150h+Alertable], al; Alertable
0x1400a6261  xor     r9d, r9d; WaitReason
0x1400a6264  lea     r8d, [rax+1]; WaitType
0x1400a6268  mov     [rsp+150h+Object+8], rbx
0x1400a626d  lea     ecx, [rax+2]; Count
0x1400a6270  mov     byte ptr [rsp+150h+BugCheckParameter4], al; WaitMode
0x1400a6274  call    cs:__imp_KeWaitForMultipleObjects
0x1400a627b  nop     dword ptr [rax+rax+00h]
0x1400a6280  mov     rcx, rbx; Event
0x1400a6283  call    cs:__imp_KeReadStateEvent
0x1400a628a  nop     dword ptr [rax+rax+00h]
0x1400a628f  test    eax, eax
0x1400a6291  jz      short loc_1400A62DF
0x1400a6293  mov     r12d, 3
0x1400a6299  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a62a0  lea     rbx, WPP_GLOBAL_Control
0x1400a62a7  cmp     rcx, rbx
0x1400a62aa  jz      loc_1400A60B6
0x1400a62b0  mov     eax, [rcx+2Ch]
0x1400a62b3  test    al, 2
0x1400a62b5  jz      loc_1400A60B6
0x1400a62bb  cmp     byte ptr [rcx+29h], 5
0x1400a62bf  jb      loc_1400A60B6
0x1400a62c5  mov     rcx, [rcx+18h]
0x1400a62c9  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x1400a62d0  mov     edx, 8Fh
0x1400a62d5  call    WPP_SF_
0x1400a62da  jmp     loc_1400A60B6
0x1400a62df  mov     esi, [rdi+210h]
0x1400a62e5  test    esi, esi
0x1400a62e7  js      short loc_1400A6358
0x1400a62e9  mov     rdx, [rdi+40h]
0x1400a62ed  cmp     rdx, r14
0x1400a62f0  jnz     loc_1400A60AF
0x1400a62f6  mov     rcx, [rdi+48h]
0x1400a62fa  cmp     rcx, r13
0x1400a62fd  jnz     loc_1400A60AF
0x1400a6303  mov     rax, [rdi+128h]
0x1400a630a  cmp     rdx, rax
0x1400a630d  jnz     loc_1400A60AF
0x1400a6313  cmp     rcx, rax
0x1400a6316  jnz     loc_1400A60AF
0x1400a631c  mov     r12d, 1
0x1400a6322  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6329  lea     rbx, WPP_GLOBAL_Control
0x1400a6330  cmp     rcx, rbx
0x1400a6333  jz      loc_1400A6045
0x1400a6339  mov     eax, [rcx+2Ch]
0x1400a633c  test    al, 2
0x1400a633e  jz      loc_1400A6045
0x1400a6344  cmp     byte ptr [rcx+29h], 5
0x1400a6348  jb      loc_1400A6045
0x1400a634e  mov     edx, 90h
0x1400a6353  jmp     loc_1400A6035
0x1400a6358  lea     rbx, WPP_GLOBAL_Control
0x1400a635f  xor     edx, edx; Val
0x1400a6361  lea     rcx, [rbp+50h+var_D0]; void *
0x1400a6365  mov     r8d, 90h; Size
0x1400a636b  call    memset
0x1400a6370  mov     r8b, 1
0x1400a6373  lea     rdx, [rbp+50h+var_D0]
0x1400a6377  mov     rcx, r15
0x1400a637a  call    FvepAcquireDevFveLock
0x1400a637f  mov     r12d, 2
0x1400a6385  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a638c  cmp     rcx, rbx
0x1400a638f  jz      short loc_1400A63B7
0x1400a6391  mov     eax, [rcx+2Ch]
0x1400a6394  test    r12b, al
0x1400a6397  jz      short loc_1400A63B7
0x1400a6399  cmp     [rcx+29h], r12b
  ... truncated ...
```
