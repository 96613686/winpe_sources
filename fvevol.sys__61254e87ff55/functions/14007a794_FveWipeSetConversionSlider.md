# FveWipeSetConversionSlider

- ea: `0x14007a794`
- end: `0x14007adc8`
- name: `FveWipeSetConversionSlider`
- size: `1588`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140079d40`

## callees

- `0x140006b80`
- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x140023040`
- `0x14007a794`
- `0x1400b99e4`
- `0x1400bf70c`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14007ac56`
- `ntoskrnl!KeReadStateEvent` at `0x14007acb6`
- `ntoskrnl!KeReadStateEvent` at `0x14007ac56`
- `ntoskrnl!KeReadStateEvent` at `0x14007acb6`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14007ac47`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14007ac47`
- `ntoskrnl!KeClearEvent` at `0x14007abea`
- `ntoskrnl!KeClearEvent` at `0x14007abea`
- `ntoskrnl!KeSetEvent` at `0x14007ac02`
- `ntoskrnl!KeSetEvent` at `0x14007ac02`

## pseudocode

```c
__int64 __fastcall FveWipeSetConversionSlider(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // r8
  ULONGLONG v7; // r15
  ULONGLONG v8; // rax
  ULONGLONG v9; // rbx
  ULONGLONG v10; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  ULONGLONG v17; // r12
  __int64 v18; // rax
  __int64 v19; // rax
  ULONGLONG v20; // rax
  int v21; // edx
  NTSTATUS v22; // r12d
  int v23; // r12d
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r12
  ULONGLONG v28; // r12
  __int64 v29; // rax
  __int64 v30; // rax
  ULONGLONG v31; // rax
  __int64 v32; // r8
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int64 v36; // [rsp+40h] [rbp-79h] BYREF
  __int64 v37; // [rsp+48h] [rbp-71h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v39[144]; // [rsp+60h] [rbp-59h] BYREF
  ULONGLONG pullResult; // [rsp+128h] [rbp+6Fh] BYREF
  ULONGLONG v41; // [rsp+138h] [rbp+7Fh] BYREF

  memset(v39, 0, sizeof(v39));
  pullResult = 0;
  *(_OWORD *)Object = 0;
  v36 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
  }
  if ( a3 != 1 )
    goto LABEL_14;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 1032) + 16LL);
  if ( v7 >= *(_QWORD *)(a2 + 48) && v7 < *(_QWORD *)(a2 + 56) )
    goto LABEL_14;
  v8 = *(_QWORD *)(a2 + 64);
  v9 = *(_QWORD *)(a1 + 1048);
  v10 = v8 + v7;
  if ( v8 + v7 <= v9 && v10 >= v7 )
  {
    v11 = a1;
    if ( v10 < v8 )
    {
      LOBYTE(v6) = 1;
LABEL_27:
      FvepAcquireDevFveLock(v11, v39, v6);
      *(_DWORD *)(a1 + 1440) = -1073741675;
      goto LABEL_13;
    }
    v41 = v8 + v7;
    v12 = FveTpAlignUp(a1, v10, &v41);
    if ( v12 < 0 )
    {
      LOBYTE(v6) = 1;
      FvepAcquireDevFveLock(a1, v39, v6);
      *(_DWORD *)(a1 + 1440) = v12;
LABEL_13:
      a3 = 3;
      FvepReleaseDevFveLock(v39);
      goto LABEL_14;
    }
    v9 = v41;
  }
  LOBYTE(v6) = 1;
  FvepAcquireDevFveLock(a1, v39, v6);
  v16 = *(_QWORD *)(a1 + 976);
  if ( v16 && *(_WORD *)(v16 + 10) > 1u )
  {
    v17 = *(_QWORD *)(v16 + 56);
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v15, v14)
      && (*(_BYTE *)(a1 + 4419) & 8) != 0
      || (v18 = *(_QWORD *)(a1 + 976), *(_WORD *)(v18 + 10) == 1) )
    {
      v19 = 0;
    }
    else
    {
      v19 = *(unsigned int *)(v18 + 28);
      if ( !(_DWORD)v19 )
        v19 = 1;
    }
    if ( v7 >= v17 || v9 <= v17 )
    {
      v20 = v17 + *(unsigned int *)(a1 + 1308) * v19;
      if ( v7 < v20 && v9 > v20 )
        v9 = v20;
    }
    else
    {
      v9 = v17;
    }
  }
  FvepReleaseDevFveLock(v39);
  v22 = RtlULongLongSub(v9, v7, &pullResult);
  if ( v22 < 0 )
    goto LABEL_37;
  v23 = FveFsAlignVolumeRangeToClusters((int)a2 + 528, v21, pullResult, (unsigned int)&v36, (__int64)&v37);
  if ( v23 < 0 )
  {
    LOBYTE(v6) = 1;
    FvepAcquireDevFveLock(a1, v39, v6);
    a3 = 3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        63,
        WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids,
        (unsigned int)v23);
    }
    *(_DWORD *)(a1 + 1440) = v23;
    FvepReleaseDevFveLock(v39);
    goto LABEL_14;
  }
  v24 = v36 + v37;
  if ( v36 + v37 < v36 )
  {
    LOBYTE(v6) = 1;
    v11 = a1;
    goto LABEL_27;
  }
  if ( v24 != v9 )
  {
    if ( v9 >= *(_QWORD *)(a2 + 600) )
    {
      if ( v9 <= *(_QWORD *)(a2 + 608) )
      {
        v9 = v24 + *(unsigned int *)(a2 + 636);
        if ( v9 > *(_QWORD *)(a1 + 1048) )
          v9 = *(_QWORD *)(a1 + 1048);
      }
      else
      {
        v9 = *(_QWORD *)(a1 + 1048);
      }
    }
    else
    {
      v9 = *(_QWORD *)(a2 + 600);
    }
    v22 = RtlULongLongSub(v9, v7, &pullResult);
    if ( v22 < 0 )
    {
LABEL_37:
      LOBYTE(v6) = 1;
      FvepAcquireDevFveLock(a1, v39, v6);
      *(_DWORD *)(a1 + 1440) = v22;
      goto LABEL_13;
    }
  }
  LOBYTE(v6) = 1;
  FvepAcquireDevFveLock(a1, v39, v6);
  v27 = *(_QWORD *)(a1 + 976);
  if ( v27 && *(_WORD *)(v27 + 10) > 1u )
  {
    v28 = *(_QWORD *)(v27 + 56);
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v26, v25)
      && (*(_BYTE *)(a1 + 4419) & 8) != 0
      || (v29 = *(_QWORD *)(a1 + 976), *(_WORD *)(v29 + 10) == 1) )
    {
      v30 = 0;
    }
    else
    {
      v30 = *(unsigned int *)(v29 + 28);
      if ( !(_DWORD)v30 )
        v30 = 1;
    }
    if ( v7 >= v28 || v9 <= v28 )
    {
      v31 = v28 + *(unsigned int *)(a1 + 1308) * v30;
      if ( v7 < v31 && v9 > v31 )
        v9 = v31;
    }
    else
    {
      v9 = v28;
    }
  }
  FvepReleaseDevFveLock(v39);
  if ( *(_BYTE *)(a2 + 40) )
  {
    LOBYTE(v32) = 1;
    FvepAcquireDevFveLock(a1, v39, v32);
    if ( (*(_DWORD *)(a1 + 852) & 8) == 0 )
    {
      a3 = 3;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v34 = 64;
LABEL_74:
      WPP_SF_(v33->AttachedDevice, v34, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
LABEL_75:
      *(_DWORD *)(a1 + 1440) = -1073741823;
      goto LABEL_14;
    }
    FvepReleaseDevFveLock(v39);
  }
  *(_QWORD *)(a2 + 392) = v9;
  *(_QWORD *)(a2 + 384) = v7;
  KeClearEvent((PRKEVENT)(a2 + 360));
  KeSetEvent((PRKEVENT)(a2 + 336), 0, 0);
  Object[0] = (PVOID)(a2 + 360);
  Object[1] = (PVOID)(a2 + 312);
  KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
  if ( KeReadStateEvent((PRKEVENT)(a2 + 360)) )
  {
    if ( *(int *)(a2 + 400) < 0 )
    {
      a3 = 3;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
      }
    }
  }
  if ( !KeReadStateEvent((PRKEVENT)(a2 + 312)) )
  {
    if ( *(_BYTE *)(a2 + 40) )
    {
      LOBYTE(v35) = 1;
      FvepAcquireDevFveLock(a1, v39, v35);
      if ( (*(_DWORD *)(a1 + 852) & 8) == 0 )
      {
        a3 = 3;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_75;
        }
        v34 = 67;
        goto LABEL_74;
      }
      FvepReleaseDevFveLock(v39);
    }
    if ( *(_QWORD *)(a2 + 48) == *(_QWORD *)(a1 + 1048) )
    {
      a3 = 2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
      }
      *(_BYTE *)(a2 + 304) = 1;
      *(_QWORD *)(*(_QWORD *)(a1 + 1032) + 16LL) = *(_QWORD *)(a1 + 1048);
    }
    goto LABEL_14;
  }
  a3 = 4;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return a3;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
  }
  return a3;
}

```

## disassembly

```asm
0x14007a794  mov     [rsp-8+arg_0], rbx
0x14007a799  mov     [rsp-8+arg_10], rsi
0x14007a79e  push    rbp
0x14007a79f  push    rdi
0x14007a7a0  push    r12
0x14007a7a2  push    r14
0x14007a7a4  push    r15
0x14007a7a6  lea     rbp, [rsp-37h]
0x14007a7ab  sub     rsp, 0F0h
0x14007a7b2  mov     esi, r8d
0x14007a7b5  mov     r14, rdx
0x14007a7b8  mov     rdi, rcx
0x14007a7bb  xor     edx, edx; Val
0x14007a7bd  mov     r8d, 90h; Size
0x14007a7c3  lea     rcx, [rbp+57h+var_B0]; void *
0x14007a7c7  call    memset
0x14007a7cc  xorps   xmm0, xmm0
0x14007a7cf  mov     [rbp+57h+pullResult], 0
0x14007a7d7  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14007a7db  mov     [rbp+57h+var_D0], 0
0x14007a7e3  mov     [rbp+57h+var_C8], 0
0x14007a7eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a7f2  lea     rax, WPP_GLOBAL_Control
0x14007a7f9  cmp     rcx, rax
0x14007a7fc  jz      short loc_14007A822
0x14007a7fe  test    dword ptr [rcx+2Ch], 1000h
0x14007a805  jz      short loc_14007A822
0x14007a807  cmp     byte ptr [rcx+29h], 5
0x14007a80b  jb      short loc_14007A822
0x14007a80d  mov     rcx, [rcx+18h]
0x14007a811  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007a818  mov     edx, 3Eh ; '>'
0x14007a81d  call    WPP_SF_
0x14007a822  mov     r12d, 1
0x14007a828  cmp     esi, r12d
0x14007a82b  jnz     short loc_14007A8A7
0x14007a82d  mov     rax, [rdi+408h]
0x14007a834  mov     r15, [rax+10h]
0x14007a838  cmp     r15, [r14+30h]
0x14007a83c  jb      short loc_14007A844
0x14007a83e  cmp     r15, [r14+38h]
0x14007a842  jb      short loc_14007A8A7
0x14007a844  mov     rax, [r14+40h]
0x14007a848  mov     rbx, [rdi+418h]
0x14007a84f  lea     rdx, [rax+r15]
0x14007a853  cmp     rdx, rbx
0x14007a856  ja      loc_14007A901
0x14007a85c  cmp     rdx, r15
0x14007a85f  jb      loc_14007A901
0x14007a865  mov     rcx, rdi
0x14007a868  cmp     rdx, rax
0x14007a86b  jb      loc_14007A94F
0x14007a871  lea     r8, [rbp+57h+arg_18]
0x14007a875  mov     [rbp+57h+arg_18], rdx
0x14007a879  call    FveTpAlignUp
0x14007a87e  mov     ebx, eax
0x14007a880  test    eax, eax
0x14007a882  jns     short loc_14007A8FD
0x14007a884  mov     r8b, r12b
0x14007a887  lea     rdx, [rbp+57h+var_B0]
0x14007a88b  mov     rcx, rdi
0x14007a88e  call    FvepAcquireDevFveLock
0x14007a893  mov     [rdi+5A0h], ebx
0x14007a899  lea     rcx, [rbp+57h+var_B0]
0x14007a89d  mov     esi, 3
0x14007a8a2  call    FvepReleaseDevFveLock
0x14007a8a7  lea     rbx, WPP_GLOBAL_Control
0x14007a8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a8b5  cmp     rcx, rbx
0x14007a8b8  jz      short loc_14007A8DE
0x14007a8ba  test    dword ptr [rcx+2Ch], 1000h
0x14007a8c1  jz      short loc_14007A8DE
0x14007a8c3  cmp     byte ptr [rcx+29h], 5
0x14007a8c7  jb      short loc_14007A8DE
0x14007a8c9  mov     rcx, [rcx+18h]
0x14007a8cd  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007a8d4  mov     edx, 45h ; 'E'
0x14007a8d9  call    WPP_SF_
0x14007a8de  lea     r11, [rsp+110h+var_20]
0x14007a8e6  mov     eax, esi
0x14007a8e8  mov     rbx, [r11+30h]
0x14007a8ec  mov     rsi, [r11+40h]
0x14007a8f0  mov     rsp, r11
0x14007a8f3  pop     r15
0x14007a8f5  pop     r14
0x14007a8f7  pop     r12
0x14007a8f9  pop     rdi
0x14007a8fa  pop     rbp
0x14007a8fb  retn
0x14007a8fd  mov     rbx, [rbp+57h+arg_18]
0x14007a901  mov     r8b, r12b
0x14007a904  lea     rdx, [rbp+57h+var_B0]
0x14007a908  mov     rcx, rdi
0x14007a90b  call    FvepAcquireDevFveLock
0x14007a910  mov     rax, [rdi+3D0h]
0x14007a917  test    rax, rax
0x14007a91a  jz      short loc_14007A99A
0x14007a91c  cmp     [rax+0Ah], r12w
0x14007a921  jbe     short loc_14007A99A
0x14007a923  mov     r12, [rax+38h]
0x14007a927  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14007a92c  test    eax, eax
0x14007a92e  jz      short loc_14007A939
0x14007a930  test    byte ptr [rdi+1143h], 8
0x14007a937  jnz     short loc_14007A94B
0x14007a939  mov     rax, [rdi+3D0h]
0x14007a940  mov     ecx, 1
0x14007a945  cmp     [rax+0Ah], cx
0x14007a949  jnz     short loc_14007A96A
0x14007a94b  xor     eax, eax
0x14007a94d  jmp     short loc_14007A972
0x14007a94f  mov     r8b, r12b
0x14007a952  lea     rdx, [rbp+57h+var_B0]
0x14007a956  call    FvepAcquireDevFveLock
0x14007a95b  mov     dword ptr [rdi+5A0h], 0C0000095h
0x14007a965  jmp     loc_14007A899
0x14007a96a  mov     eax, [rax+1Ch]
0x14007a96d  test    eax, eax
0x14007a96f  cmovz   eax, ecx
0x14007a972  cmp     r15, r12
0x14007a975  jnb     short loc_14007A981
0x14007a977  cmp     rbx, r12
0x14007a97a  jbe     short loc_14007A981
0x14007a97c  mov     rbx, r12
0x14007a97f  jmp     short loc_14007A99A
0x14007a981  mov     ecx, [rdi+51Ch]
0x14007a987  imul    rax, rcx
0x14007a98b  add     rax, r12
0x14007a98e  cmp     r15, rax
0x14007a991  jnb     short loc_14007A99A
0x14007a993  cmp     rbx, rax
0x14007a996  cmova   rbx, rax
0x14007a99a  lea     rcx, [rbp+57h+var_B0]
0x14007a99e  call    FvepReleaseDevFveLock
0x14007a9a3  lea     r8, [rbp+57h+pullResult]; pullResult
0x14007a9a7  mov     rdx, r15; ullSubtrahend
0x14007a9aa  mov     rcx, rbx; ullMinuend
0x14007a9ad  call    RtlULongLongSub
0x14007a9b2  mov     r12d, eax
0x14007a9b5  test    eax, eax
0x14007a9b7  jns     short loc_14007A9D4
0x14007a9b9  mov     r8b, 1
0x14007a9bc  lea     rdx, [rbp+57h+var_B0]
0x14007a9c0  mov     rcx, rdi
0x14007a9c3  call    FvepAcquireDevFveLock
0x14007a9c8  mov     [rdi+5A0h], r12d
0x14007a9cf  jmp     loc_14007A899
0x14007a9d4  mov     r8, [rbp+57h+pullResult]
0x14007a9d8  lea     rax, [rbp+57h+var_C8]
0x14007a9dc  lea     rcx, [r14+210h]
0x14007a9e3  mov     qword ptr [rsp+110h+WaitMode], rax
0x14007a9e8  lea     r9, [rbp+57h+var_D0]
0x14007a9ec  call    FveFsAlignVolumeRangeToClusters
0x14007a9f1  mov     r12d, eax
0x14007a9f4  test    eax, eax
0x14007a9f6  jns     short loc_14007AA59
0x14007a9f8  mov     r8b, 1
0x14007a9fb  lea     rdx, [rbp+57h+var_B0]
0x14007a9ff  mov     rcx, rdi
0x14007aa02  call    FvepAcquireDevFveLock
0x14007aa07  mov     esi, 3
0x14007aa0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aa13  lea     rbx, WPP_GLOBAL_Control
0x14007aa1a  cmp     rcx, rbx
0x14007aa1d  jz      short loc_14007AA44
0x14007aa1f  test    dword ptr [rcx+2Ch], 1000h
0x14007aa26  jz      short loc_14007AA44
0x14007aa28  cmp     byte ptr [rcx+29h], 2
0x14007aa2c  jb      short loc_14007AA44
0x14007aa2e  mov     rcx, [rcx+18h]
0x14007aa32  lea     edx, [rsi+3Ch]
0x14007aa35  mov     r9d, r12d
0x14007aa38  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007aa3f  call    WPP_SF_d
0x14007aa44  lea     rcx, [rbp+57h+var_B0]
0x14007aa48  mov     [rdi+5A0h], r12d
0x14007aa4f  call    FvepReleaseDevFveLock
0x14007aa54  jmp     loc_14007A8AE
0x14007aa59  mov     rdx, [rbp+57h+var_C8]
0x14007aa5d  add     rdx, [rbp+57h+var_D0]
0x14007aa61  cmp     rdx, [rbp+57h+var_D0]
0x14007aa65  jnb     short loc_14007AA72
0x14007aa67  mov     r8b, 1
0x14007aa6a  mov     rcx, rdi
0x14007aa6d  jmp     loc_14007A952
0x14007aa72  cmp     rdx, rbx
0x14007aa75  jz      short loc_14007AACC
0x14007aa77  mov     rax, [r14+258h]
0x14007aa7e  cmp     rbx, rax
0x14007aa81  jnb     short loc_14007AA88
0x14007aa83  mov     rbx, rax
0x14007aa86  jmp     short loc_14007AAB2
0x14007aa88  cmp     rbx, [r14+260h]
0x14007aa8f  jbe     short loc_14007AA9A
0x14007aa91  mov     rbx, [rdi+418h]
0x14007aa98  jmp     short loc_14007AAB2
0x14007aa9a  mov     rax, [rdi+418h]
0x14007aaa1  mov     ebx, [r14+27Ch]
0x14007aaa8  add     rbx, rdx
0x14007aaab  cmp     rbx, rax
0x14007aaae  cmova   rbx, rax
0x14007aab2  lea     r8, [rbp+57h+pullResult]; pullResult
0x14007aab6  mov     rdx, r15; ullSubtrahend
0x14007aab9  mov     rcx, rbx; ullMinuend
0x14007aabc  call    RtlULongLongSub
0x14007aac1  mov     r12d, eax
0x14007aac4  test    eax, eax
0x14007aac6  js      loc_14007A9B9
0x14007aacc  mov     r8b, 1
0x14007aacf  lea     rdx, [rbp+57h+var_B0]
0x14007aad3  mov     rcx, rdi
0x14007aad6  call    FvepAcquireDevFveLock
0x14007aadb  mov     r12, [rdi+3D0h]
0x14007aae2  test    r12, r12
0x14007aae5  jz      short loc_14007AB51
0x14007aae7  mov     eax, 1
0x14007aaec  cmp     [r12+0Ah], ax
0x14007aaf2  jbe     short loc_14007AB51
0x14007aaf4  mov     r12, [r12+38h]
0x14007aaf9  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14007aafe  test    eax, eax
0x14007ab00  jz      short loc_14007AB0B
0x14007ab02  test    byte ptr [rdi+1143h], 8
0x14007ab09  jnz     short loc_14007AB1D
0x14007ab0b  mov     rax, [rdi+3D0h]
0x14007ab12  mov     ecx, 1
0x14007ab17  cmp     [rax+0Ah], cx
0x14007ab1b  jnz     short loc_14007AB21
0x14007ab1d  xor     eax, eax
0x14007ab1f  jmp     short loc_14007AB29
0x14007ab21  mov     eax, [rax+1Ch]
0x14007ab24  test    eax, eax
0x14007ab26  cmovz   eax, ecx
0x14007ab29  cmp     r15, r12
0x14007ab2c  jnb     short loc_14007AB38
0x14007ab2e  cmp     rbx, r12
0x14007ab31  jbe     short loc_14007AB38
0x14007ab33  mov     rbx, r12
0x14007ab36  jmp     short loc_14007AB51
0x14007ab38  mov     ecx, [rdi+51Ch]
0x14007ab3e  imul    rax, rcx
0x14007ab42  add     rax, r12
0x14007ab45  cmp     r15, rax
0x14007ab48  jnb     short loc_14007AB51
0x14007ab4a  cmp     rbx, rax
0x14007ab4d  cmova   rbx, rax
0x14007ab51  lea     rcx, [rbp+57h+var_B0]
0x14007ab55  call    FvepReleaseDevFveLock
0x14007ab5a  cmp     byte ptr [r14+28h], 0
0x14007ab5f  mov     r12d, 1
0x14007ab65  jz      short loc_14007ABD2
0x14007ab67  mov     r8b, r12b
0x14007ab6a  lea     rdx, [rbp+57h+var_B0]
0x14007ab6e  mov     rcx, rdi
0x14007ab71  call    FvepAcquireDevFveLock
0x14007ab76  mov     eax, [rdi+354h]
0x14007ab7c  test    al, 8
0x14007ab7e  jnz     short loc_14007ABC9
0x14007ab80  lea     esi, [r12+2]
0x14007ab85  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ab8c  lea     rbx, WPP_GLOBAL_Control
0x14007ab93  cmp     rcx, rbx
0x14007ab96  jz      short loc_14007ABBA
0x14007ab98  test    dword ptr [rcx+2Ch], 1000h
0x14007ab9f  jz      short loc_14007ABBA
0x14007aba1  cmp     byte ptr [rcx+29h], 2
0x14007aba5  jb      short loc_14007ABBA
0x14007aba7  lea     edx, [rsi+3Dh]
0x14007abaa  mov     rcx, [rcx+18h]
0x14007abae  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007abb5  call    WPP_SF_
0x14007abba  mov     dword ptr [rdi+5A0h], 0C0000001h
0x14007abc4  jmp     loc_14007A8AE
0x14007abc9  lea     rcx, [rbp+57h+var_B0]
0x14007abcd  call    FvepReleaseDevFveLock
0x14007abd2  mov     [r14+188h], rbx
0x14007abd9  lea     rbx, [r14+168h]
0x14007abe0  mov     rcx, rbx; Event
0x14007abe3  mov     [r14+180h], r15
0x14007abea  call    cs:__imp_KeClearEvent
0x14007abf1  nop     dword ptr [rax+rax+00h]
0x14007abf6  lea     rcx, [r14+150h]; Event
0x14007abfd  xor     r8d, r8d; Wait
0x14007ac00  xor     edx, edx; Increment
0x14007ac02  call    cs:__imp_KeSetEvent
0x14007ac09  nop     dword ptr [rax+rax+00h]
0x14007ac0e  mov     [rsp+110h+WaitBlockArray], 0; WaitBlockArray
0x14007ac17  lea     r15, [r14+138h]
0x14007ac1e  xor     r9d, r9d; WaitReason
0x14007ac21  mov     [rsp+110h+Timeout], 0; Timeout
0x14007ac2a  mov     [rsp+110h+Alertable], 0; Alertable
0x14007ac2f  lea     rdx, [rbp+57h+Object]; Object
0x14007ac33  mov     r8d, r12d; WaitType
0x14007ac36  mov     [rbp+57h+Object], rbx
0x14007ac3a  mov     [rbp+57h+Object+8], r15
0x14007ac3e  lea     ecx, [r9+2]; Count
0x14007ac42  mov     [rsp+110h+WaitMode], 0; WaitMode
0x14007ac47  call    cs:__imp_KeWaitForMultipleObjects
0x14007ac4e  nop     dword ptr [rax+rax+00h]
0x14007ac53  mov     rcx, rbx; Event
  ... truncated ...
```
