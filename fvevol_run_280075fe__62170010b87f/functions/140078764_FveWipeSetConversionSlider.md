# FveWipeSetConversionSlider

- ea: `0x140078764`
- end: `0x140078d98`
- name: `FveWipeSetConversionSlider`
- size: `1588`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140077d10`

## callees

- `0x140006ac0`
- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x140021d00`
- `0x140078764`
- `0x1400b86b8`
- `0x1400bbc9c`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x140078c26`
- `ntoskrnl!KeReadStateEvent` at `0x140078c86`
- `ntoskrnl!KeReadStateEvent` at `0x140078c26`
- `ntoskrnl!KeReadStateEvent` at `0x140078c86`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140078c17`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140078c17`
- `ntoskrnl!KeClearEvent` at `0x140078bba`
- `ntoskrnl!KeClearEvent` at `0x140078bba`
- `ntoskrnl!KeSetEvent` at `0x140078bd2`
- `ntoskrnl!KeSetEvent` at `0x140078bd2`

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
  __int64 v14; // rcx
  __int64 v15; // rax
  ULONGLONG v16; // r12
  __int64 v17; // rax
  __int64 v18; // rax
  ULONGLONG v19; // rax
  int v20; // edx
  NTSTATUS v21; // r12d
  int v22; // r12d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r12
  ULONGLONG v26; // r12
  __int64 v27; // rax
  __int64 v28; // rax
  ULONGLONG v29; // rax
  __int64 v30; // r8
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned __int64 v34; // [rsp+40h] [rbp-79h] BYREF
  __int64 v35; // [rsp+48h] [rbp-71h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v37[144]; // [rsp+60h] [rbp-59h] BYREF
  ULONGLONG pullResult; // [rsp+128h] [rbp+6Fh] BYREF
  ULONGLONG v39; // [rsp+138h] [rbp+7Fh] BYREF

  memset(v37, 0, sizeof(v37));
  pullResult = 0;
  *(_OWORD *)Object = 0;
  v34 = 0;
  v35 = 0;
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
      FvepAcquireDevFveLock(v11, v37, v6);
      *(_DWORD *)(a1 + 1440) = -1073741675;
      goto LABEL_13;
    }
    v39 = v8 + v7;
    v12 = FveTpAlignUp(a1, v10, &v39);
    if ( v12 < 0 )
    {
      LOBYTE(v6) = 1;
      FvepAcquireDevFveLock(a1, v37, v6);
      *(_DWORD *)(a1 + 1440) = v12;
LABEL_13:
      a3 = 3;
      FvepReleaseDevFveLock(v37);
      goto LABEL_14;
    }
    v9 = v39;
  }
  LOBYTE(v6) = 1;
  FvepAcquireDevFveLock(a1, v37, v6);
  v15 = *(_QWORD *)(a1 + 976);
  if ( v15 && *(_WORD *)(v15 + 10) > 1u )
  {
    v16 = *(_QWORD *)(v15 + 56);
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v14)
      && (*(_BYTE *)(a1 + 4403) & 8) != 0
      || (v17 = *(_QWORD *)(a1 + 976), *(_WORD *)(v17 + 10) == 1) )
    {
      v18 = 0;
    }
    else
    {
      v18 = *(unsigned int *)(v17 + 28);
      if ( !(_DWORD)v18 )
        v18 = 1;
    }
    if ( v7 >= v16 || v9 <= v16 )
    {
      v19 = v16 + *(unsigned int *)(a1 + 1308) * v18;
      if ( v7 < v19 && v9 > v19 )
        v9 = v19;
    }
    else
    {
      v9 = v16;
    }
  }
  FvepReleaseDevFveLock(v37);
  v21 = RtlULongLongSub(v9, v7, &pullResult);
  if ( v21 < 0 )
    goto LABEL_37;
  v22 = FveFsAlignVolumeRangeToClusters((int)a2 + 528, v20, pullResult, (unsigned int)&v34, (__int64)&v35);
  if ( v22 < 0 )
  {
    LOBYTE(v6) = 1;
    FvepAcquireDevFveLock(a1, v37, v6);
    a3 = 3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        63,
        WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids,
        (unsigned int)v22);
    }
    *(_DWORD *)(a1 + 1440) = v22;
    FvepReleaseDevFveLock(v37);
    goto LABEL_14;
  }
  v23 = v34 + v35;
  if ( v34 + v35 < v34 )
  {
    LOBYTE(v6) = 1;
    v11 = a1;
    goto LABEL_27;
  }
  if ( v23 != v9 )
  {
    if ( v9 >= *(_QWORD *)(a2 + 600) )
    {
      if ( v9 <= *(_QWORD *)(a2 + 608) )
      {
        v9 = v23 + *(unsigned int *)(a2 + 636);
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
    v21 = RtlULongLongSub(v9, v7, &pullResult);
    if ( v21 < 0 )
    {
LABEL_37:
      LOBYTE(v6) = 1;
      FvepAcquireDevFveLock(a1, v37, v6);
      *(_DWORD *)(a1 + 1440) = v21;
      goto LABEL_13;
    }
  }
  LOBYTE(v6) = 1;
  FvepAcquireDevFveLock(a1, v37, v6);
  v25 = *(_QWORD *)(a1 + 976);
  if ( v25 && *(_WORD *)(v25 + 10) > 1u )
  {
    v26 = *(_QWORD *)(v25 + 56);
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v24)
      && (*(_BYTE *)(a1 + 4403) & 8) != 0
      || (v27 = *(_QWORD *)(a1 + 976), *(_WORD *)(v27 + 10) == 1) )
    {
      v28 = 0;
    }
    else
    {
      v28 = *(unsigned int *)(v27 + 28);
      if ( !(_DWORD)v28 )
        v28 = 1;
    }
    if ( v7 >= v26 || v9 <= v26 )
    {
      v29 = v26 + *(unsigned int *)(a1 + 1308) * v28;
      if ( v7 < v29 && v9 > v29 )
        v9 = v29;
    }
    else
    {
      v9 = v26;
    }
  }
  FvepReleaseDevFveLock(v37);
  if ( *(_BYTE *)(a2 + 40) )
  {
    LOBYTE(v30) = 1;
    FvepAcquireDevFveLock(a1, v37, v30);
    if ( (*(_DWORD *)(a1 + 852) & 8) == 0 )
    {
      a3 = 3;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_75;
      }
      v32 = 64;
LABEL_74:
      WPP_SF_(v31->AttachedDevice, v32, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
LABEL_75:
      *(_DWORD *)(a1 + 1440) = -1073741823;
      goto LABEL_14;
    }
    FvepReleaseDevFveLock(v37);
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
      LOBYTE(v33) = 1;
      FvepAcquireDevFveLock(a1, v37, v33);
      if ( (*(_DWORD *)(a1 + 852) & 8) == 0 )
      {
        a3 = 3;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_75;
        }
        v32 = 67;
        goto LABEL_74;
      }
      FvepReleaseDevFveLock(v37);
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
0x140078764  mov     [rsp-8+arg_0], rbx
0x140078769  mov     [rsp-8+arg_10], rsi
0x14007876e  push    rbp
0x14007876f  push    rdi
0x140078770  push    r12
0x140078772  push    r14
0x140078774  push    r15
0x140078776  lea     rbp, [rsp-37h]
0x14007877b  sub     rsp, 0F0h
0x140078782  mov     esi, r8d
0x140078785  mov     r14, rdx
0x140078788  mov     rdi, rcx
0x14007878b  xor     edx, edx; Val
0x14007878d  mov     r8d, 90h; Size
0x140078793  lea     rcx, [rbp+57h+var_B0]; void *
0x140078797  call    memset
0x14007879c  xorps   xmm0, xmm0
0x14007879f  mov     [rbp+57h+pullResult], 0
0x1400787a7  movups  xmmword ptr [rbp+57h+Object], xmm0
0x1400787ab  mov     [rbp+57h+var_D0], 0
0x1400787b3  mov     [rbp+57h+var_C8], 0
0x1400787bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400787c2  lea     rax, WPP_GLOBAL_Control
0x1400787c9  cmp     rcx, rax
0x1400787cc  jz      short loc_1400787F2
0x1400787ce  test    dword ptr [rcx+2Ch], 1000h
0x1400787d5  jz      short loc_1400787F2
0x1400787d7  cmp     byte ptr [rcx+29h], 5
0x1400787db  jb      short loc_1400787F2
0x1400787dd  mov     rcx, [rcx+18h]
0x1400787e1  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x1400787e8  mov     edx, 3Eh ; '>'
0x1400787ed  call    WPP_SF_
0x1400787f2  mov     r12d, 1
0x1400787f8  cmp     esi, r12d
0x1400787fb  jnz     short loc_140078877
0x1400787fd  mov     rax, [rdi+408h]
0x140078804  mov     r15, [rax+10h]
0x140078808  cmp     r15, [r14+30h]
0x14007880c  jb      short loc_140078814
0x14007880e  cmp     r15, [r14+38h]
0x140078812  jb      short loc_140078877
0x140078814  mov     rax, [r14+40h]
0x140078818  mov     rbx, [rdi+418h]
0x14007881f  lea     rdx, [rax+r15]
0x140078823  cmp     rdx, rbx
0x140078826  ja      loc_1400788D1
0x14007882c  cmp     rdx, r15
0x14007882f  jb      loc_1400788D1
0x140078835  mov     rcx, rdi
0x140078838  cmp     rdx, rax
0x14007883b  jb      loc_14007891F
0x140078841  lea     r8, [rbp+57h+arg_18]
0x140078845  mov     [rbp+57h+arg_18], rdx
0x140078849  call    FveTpAlignUp
0x14007884e  mov     ebx, eax
0x140078850  test    eax, eax
0x140078852  jns     short loc_1400788CD
0x140078854  mov     r8b, r12b
0x140078857  lea     rdx, [rbp+57h+var_B0]
0x14007885b  mov     rcx, rdi
0x14007885e  call    FvepAcquireDevFveLock
0x140078863  mov     [rdi+5A0h], ebx
0x140078869  lea     rcx, [rbp+57h+var_B0]
0x14007886d  mov     esi, 3
0x140078872  call    FvepReleaseDevFveLock
0x140078877  lea     rbx, WPP_GLOBAL_Control
0x14007887e  mov     rcx, cs:WPP_GLOBAL_Control
0x140078885  cmp     rcx, rbx
0x140078888  jz      short loc_1400788AE
0x14007888a  test    dword ptr [rcx+2Ch], 1000h
0x140078891  jz      short loc_1400788AE
0x140078893  cmp     byte ptr [rcx+29h], 5
0x140078897  jb      short loc_1400788AE
0x140078899  mov     rcx, [rcx+18h]
0x14007889d  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x1400788a4  mov     edx, 45h ; 'E'
0x1400788a9  call    WPP_SF_
0x1400788ae  lea     r11, [rsp+110h+var_20]
0x1400788b6  mov     eax, esi
0x1400788b8  mov     rbx, [r11+30h]
0x1400788bc  mov     rsi, [r11+40h]
0x1400788c0  mov     rsp, r11
0x1400788c3  pop     r15
0x1400788c5  pop     r14
0x1400788c7  pop     r12
0x1400788c9  pop     rdi
0x1400788ca  pop     rbp
0x1400788cb  retn
0x1400788cd  mov     rbx, [rbp+57h+arg_18]
0x1400788d1  mov     r8b, r12b
0x1400788d4  lea     rdx, [rbp+57h+var_B0]
0x1400788d8  mov     rcx, rdi
0x1400788db  call    FvepAcquireDevFveLock
0x1400788e0  mov     rax, [rdi+3D0h]
0x1400788e7  test    rax, rax
0x1400788ea  jz      short loc_14007896A
0x1400788ec  cmp     [rax+0Ah], r12w
0x1400788f1  jbe     short loc_14007896A
0x1400788f3  mov     r12, [rax+38h]
0x1400788f7  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400788fc  test    eax, eax
0x1400788fe  jz      short loc_140078909
0x140078900  test    byte ptr [rdi+1133h], 8
0x140078907  jnz     short loc_14007891B
0x140078909  mov     rax, [rdi+3D0h]
0x140078910  mov     ecx, 1
0x140078915  cmp     [rax+0Ah], cx
0x140078919  jnz     short loc_14007893A
0x14007891b  xor     eax, eax
0x14007891d  jmp     short loc_140078942
0x14007891f  mov     r8b, r12b
0x140078922  lea     rdx, [rbp+57h+var_B0]
0x140078926  call    FvepAcquireDevFveLock
0x14007892b  mov     dword ptr [rdi+5A0h], 0C0000095h
0x140078935  jmp     loc_140078869
0x14007893a  mov     eax, [rax+1Ch]
0x14007893d  test    eax, eax
0x14007893f  cmovz   eax, ecx
0x140078942  cmp     r15, r12
0x140078945  jnb     short loc_140078951
0x140078947  cmp     rbx, r12
0x14007894a  jbe     short loc_140078951
0x14007894c  mov     rbx, r12
0x14007894f  jmp     short loc_14007896A
0x140078951  mov     ecx, [rdi+51Ch]
0x140078957  imul    rax, rcx
0x14007895b  add     rax, r12
0x14007895e  cmp     r15, rax
0x140078961  jnb     short loc_14007896A
0x140078963  cmp     rbx, rax
0x140078966  cmova   rbx, rax
0x14007896a  lea     rcx, [rbp+57h+var_B0]
0x14007896e  call    FvepReleaseDevFveLock
0x140078973  lea     r8, [rbp+57h+pullResult]; pullResult
0x140078977  mov     rdx, r15; ullSubtrahend
0x14007897a  mov     rcx, rbx; ullMinuend
0x14007897d  call    RtlULongLongSub
0x140078982  mov     r12d, eax
0x140078985  test    eax, eax
0x140078987  jns     short loc_1400789A4
0x140078989  mov     r8b, 1
0x14007898c  lea     rdx, [rbp+57h+var_B0]
0x140078990  mov     rcx, rdi
0x140078993  call    FvepAcquireDevFveLock
0x140078998  mov     [rdi+5A0h], r12d
0x14007899f  jmp     loc_140078869
0x1400789a4  mov     r8, [rbp+57h+pullResult]
0x1400789a8  lea     rax, [rbp+57h+var_C8]
0x1400789ac  lea     rcx, [r14+210h]
0x1400789b3  mov     qword ptr [rsp+110h+WaitMode], rax
0x1400789b8  lea     r9, [rbp+57h+var_D0]
0x1400789bc  call    FveFsAlignVolumeRangeToClusters
0x1400789c1  mov     r12d, eax
0x1400789c4  test    eax, eax
0x1400789c6  jns     short loc_140078A29
0x1400789c8  mov     r8b, 1
0x1400789cb  lea     rdx, [rbp+57h+var_B0]
0x1400789cf  mov     rcx, rdi
0x1400789d2  call    FvepAcquireDevFveLock
0x1400789d7  mov     esi, 3
0x1400789dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400789e3  lea     rbx, WPP_GLOBAL_Control
0x1400789ea  cmp     rcx, rbx
0x1400789ed  jz      short loc_140078A14
0x1400789ef  test    dword ptr [rcx+2Ch], 1000h
0x1400789f6  jz      short loc_140078A14
0x1400789f8  cmp     byte ptr [rcx+29h], 2
0x1400789fc  jb      short loc_140078A14
0x1400789fe  mov     rcx, [rcx+18h]
0x140078a02  lea     edx, [rsi+3Ch]
0x140078a05  mov     r9d, r12d
0x140078a08  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x140078a0f  call    WPP_SF_d
0x140078a14  lea     rcx, [rbp+57h+var_B0]
0x140078a18  mov     [rdi+5A0h], r12d
0x140078a1f  call    FvepReleaseDevFveLock
0x140078a24  jmp     loc_14007887E
0x140078a29  mov     rdx, [rbp+57h+var_C8]
0x140078a2d  add     rdx, [rbp+57h+var_D0]
0x140078a31  cmp     rdx, [rbp+57h+var_D0]
0x140078a35  jnb     short loc_140078A42
0x140078a37  mov     r8b, 1
0x140078a3a  mov     rcx, rdi
0x140078a3d  jmp     loc_140078922
0x140078a42  cmp     rdx, rbx
0x140078a45  jz      short loc_140078A9C
0x140078a47  mov     rax, [r14+258h]
0x140078a4e  cmp     rbx, rax
0x140078a51  jnb     short loc_140078A58
0x140078a53  mov     rbx, rax
0x140078a56  jmp     short loc_140078A82
0x140078a58  cmp     rbx, [r14+260h]
0x140078a5f  jbe     short loc_140078A6A
0x140078a61  mov     rbx, [rdi+418h]
0x140078a68  jmp     short loc_140078A82
0x140078a6a  mov     rax, [rdi+418h]
0x140078a71  mov     ebx, [r14+27Ch]
0x140078a78  add     rbx, rdx
0x140078a7b  cmp     rbx, rax
0x140078a7e  cmova   rbx, rax
0x140078a82  lea     r8, [rbp+57h+pullResult]; pullResult
0x140078a86  mov     rdx, r15; ullSubtrahend
0x140078a89  mov     rcx, rbx; ullMinuend
0x140078a8c  call    RtlULongLongSub
0x140078a91  mov     r12d, eax
0x140078a94  test    eax, eax
0x140078a96  js      loc_140078989
0x140078a9c  mov     r8b, 1
0x140078a9f  lea     rdx, [rbp+57h+var_B0]
0x140078aa3  mov     rcx, rdi
0x140078aa6  call    FvepAcquireDevFveLock
0x140078aab  mov     r12, [rdi+3D0h]
0x140078ab2  test    r12, r12
0x140078ab5  jz      short loc_140078B21
0x140078ab7  mov     eax, 1
0x140078abc  cmp     [r12+0Ah], ax
0x140078ac2  jbe     short loc_140078B21
0x140078ac4  mov     r12, [r12+38h]
0x140078ac9  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x140078ace  test    eax, eax
0x140078ad0  jz      short loc_140078ADB
0x140078ad2  test    byte ptr [rdi+1133h], 8
0x140078ad9  jnz     short loc_140078AED
0x140078adb  mov     rax, [rdi+3D0h]
0x140078ae2  mov     ecx, 1
0x140078ae7  cmp     [rax+0Ah], cx
0x140078aeb  jnz     short loc_140078AF1
0x140078aed  xor     eax, eax
0x140078aef  jmp     short loc_140078AF9
0x140078af1  mov     eax, [rax+1Ch]
0x140078af4  test    eax, eax
0x140078af6  cmovz   eax, ecx
0x140078af9  cmp     r15, r12
0x140078afc  jnb     short loc_140078B08
0x140078afe  cmp     rbx, r12
0x140078b01  jbe     short loc_140078B08
0x140078b03  mov     rbx, r12
0x140078b06  jmp     short loc_140078B21
0x140078b08  mov     ecx, [rdi+51Ch]
0x140078b0e  imul    rax, rcx
0x140078b12  add     rax, r12
0x140078b15  cmp     r15, rax
0x140078b18  jnb     short loc_140078B21
0x140078b1a  cmp     rbx, rax
0x140078b1d  cmova   rbx, rax
0x140078b21  lea     rcx, [rbp+57h+var_B0]
0x140078b25  call    FvepReleaseDevFveLock
0x140078b2a  cmp     byte ptr [r14+28h], 0
0x140078b2f  mov     r12d, 1
0x140078b35  jz      short loc_140078BA2
0x140078b37  mov     r8b, r12b
0x140078b3a  lea     rdx, [rbp+57h+var_B0]
0x140078b3e  mov     rcx, rdi
0x140078b41  call    FvepAcquireDevFveLock
0x140078b46  mov     eax, [rdi+354h]
0x140078b4c  test    al, 8
0x140078b4e  jnz     short loc_140078B99
0x140078b50  lea     esi, [r12+2]
0x140078b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b5c  lea     rbx, WPP_GLOBAL_Control
0x140078b63  cmp     rcx, rbx
0x140078b66  jz      short loc_140078B8A
0x140078b68  test    dword ptr [rcx+2Ch], 1000h
0x140078b6f  jz      short loc_140078B8A
0x140078b71  cmp     byte ptr [rcx+29h], 2
0x140078b75  jb      short loc_140078B8A
0x140078b77  lea     edx, [rsi+3Dh]
0x140078b7a  mov     rcx, [rcx+18h]
0x140078b7e  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x140078b85  call    WPP_SF_
0x140078b8a  mov     dword ptr [rdi+5A0h], 0C0000001h
0x140078b94  jmp     loc_14007887E
0x140078b99  lea     rcx, [rbp+57h+var_B0]
0x140078b9d  call    FvepReleaseDevFveLock
0x140078ba2  mov     [r14+188h], rbx
0x140078ba9  lea     rbx, [r14+168h]
0x140078bb0  mov     rcx, rbx; Event
0x140078bb3  mov     [r14+180h], r15
0x140078bba  call    cs:__imp_KeClearEvent
0x140078bc1  nop     dword ptr [rax+rax+00h]
0x140078bc6  lea     rcx, [r14+150h]; Event
0x140078bcd  xor     r8d, r8d; Wait
0x140078bd0  xor     edx, edx; Increment
0x140078bd2  call    cs:__imp_KeSetEvent
0x140078bd9  nop     dword ptr [rax+rax+00h]
0x140078bde  mov     [rsp+110h+WaitBlockArray], 0; WaitBlockArray
0x140078be7  lea     r15, [r14+138h]
0x140078bee  xor     r9d, r9d; WaitReason
0x140078bf1  mov     [rsp+110h+Timeout], 0; Timeout
0x140078bfa  mov     [rsp+110h+Alertable], 0; Alertable
0x140078bff  lea     rdx, [rbp+57h+Object]; Object
0x140078c03  mov     r8d, r12d; WaitType
0x140078c06  mov     [rbp+57h+Object], rbx
0x140078c0a  mov     [rbp+57h+Object+8], r15
0x140078c0e  lea     ecx, [r9+2]; Count
0x140078c12  mov     [rsp+110h+WaitMode], 0; WaitMode
0x140078c17  call    cs:__imp_KeWaitForMultipleObjects
0x140078c1e  nop     dword ptr [rax+rax+00h]
0x140078c23  mov     rcx, rbx; Event
  ... truncated ...
```
