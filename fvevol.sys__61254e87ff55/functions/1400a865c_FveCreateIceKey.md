# FveCreateIceKey

- ea: `0x1400a865c`
- end: `0x1400a8ce5`
- name: `FveCreateIceKey`
- size: `1673`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x14007c19c`
- `0x1400adfbc`
- `0x1400ae57c`
- `0x1400af494`

## callees

- `0x140005e60`
- `0x140008348`
- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000c1e0`
- `0x14000c728`
- `0x140014e1c`
- `0x140022d40`
- `0x140023040`
- `0x14002f59c`
- `0x1400a865c`
- `0x1400cade8`
- `0x1400cc64c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400a8c57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a8c79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a8c57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a8c79`
- `ntoskrnl!ExAllocatePool2` at `0x1400a88d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400a89e9`
- `ntoskrnl!ExAllocatePool2` at `0x1400a88d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400a89e9`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400a8a67`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400a8a67`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400a8c24`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400a8c24`
- `ksecdd!BCryptDestroyHash` at `0x1400a8c05`
- `ksecdd!BCryptDestroyHash` at `0x1400a8c05`
- `ksecdd!BCryptFinishHash` at `0x1400a8b99`
- `ksecdd!BCryptFinishHash` at `0x1400a8b99`
- `ksecdd!BCryptHashData` at `0x1400a8b42`
- `ksecdd!BCryptHashData` at `0x1400a8b42`
- `ksecdd!BCryptCreateHash` at `0x1400a8afb`
- `ksecdd!BCryptCreateHash` at `0x1400a8afb`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400a8a88`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400a8a88`

## pseudocode

```c
__int64 __fastcall FveCreateIceKey(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int **a6)
{
  unsigned int *v8; // rdi
  unsigned int v9; // r13d
  ULONG v10; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // r10d
  unsigned int v14; // r11d
  __int64 v15; // r15
  int v16; // r14d
  ULONG v17; // r12d
  PDEVICE_OBJECT *Timer_high; // rdx
  int v19; // ecx
  PDEVICE_OBJECT v20; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int16 v22; // cx
  int Size; // r8d
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  int HwWrappedFvekContentWithChallenge; // eax
  NTSTATUS v27; // ebx
  __int64 v28; // r9
  int v29; // ebx
  unsigned int *Pool2; // rax
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  void *v36; // rcx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  BCRYPT_ALG_HANDLE v39; // rcx
  __int64 v40; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  int v44; // [rsp+B0h] [rbp+48h]
  unsigned int v45; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v46; // [rsp+C0h] [rbp+58h]
  int v47; // [rsp+C8h] [rbp+60h]

  v47 = a4;
  v46 = a3;
  v8 = 0;
  v9 = *(_DWORD *)(a1 + 1308) >> 9;
  phAlgorithm = 0;
  phHash = 0;
  v10 = FveIceAlgorithmBitSizeToKeySize(a4, a5);
  v15 = 0;
  v45 = 0;
  v16 = 0;
  v44 = 0;
  v17 = v10;
  Timer_high = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_LLLD(WPP_GLOBAL_Control->AttachedDevice, &WPP_GLOBAL_Control, v11, v14, v12, v13, v9);
    v12 = v47;
    Timer_high = &WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_83;
  if ( !v9 )
    goto LABEL_83;
  if ( v17 == -1 )
    goto LABEL_83;
  if ( v12 >= 5 )
    goto LABEL_83;
  v19 = *(_DWORD *)(a1 + 1308);
  if ( !v19 || ((v19 - 1) & v19) != 0 || !a6 )
    goto LABEL_83;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      198,
      WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids,
      *(unsigned __int16 *)(a2 + 4));
  }
  IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                   v20,
                                   Timer_high);
  v22 = *(_WORD *)(a2 + 4);
  v16 = 1;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( v22 == 1 )
    {
      v44 = 0;
      v15 = a2;
      Size = (unsigned __int16)FveDatumKeyGetSize(a2);
      if ( v17 != Size )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_24;
        }
        v25 = 199;
        goto LABEL_23;
      }
LABEL_38:
      v29 = 112;
      Pool2 = (unsigned int *)ExAllocatePool2(64, 112, 1701736270);
      v8 = Pool2;
      if ( Pool2
        && (memset(Pool2, 0, 0x70u), v33 = ExAllocatePool2(64, v17, 1701736270), (*((_QWORD *)v8 + 7) = v33) != 0) )
      {
        if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v34, Timer_high) )
        {
          v8[22] = v45;
          *((_QWORD *)v8 + 12) = FveAdjustCryptoParametersCallback;
          v35 = 2;
          *((_QWORD *)v8 + 13) = 0;
        }
        else
        {
          v8[22] = 0;
          v29 = 72;
          v35 = 1;
        }
        *v8 = v35;
        v8[1] = v29;
        v36 = (void *)*((_QWORD *)v8 + 7);
        v8[2] = v46;
        v8[3] = v47;
        v8[5] = v17;
        v8[4] = v9;
        memmove(v36, (const void *)(v15 + 12), v17);
        *((PHYSICAL_ADDRESS *)v8 + 8) = MmGetPhysicalAddress(*((PVOID *)v8 + 7));
        v27 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 1u);
        if ( v27 < 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v38 = 205;
LABEL_65:
          WPP_SF_d(v37->AttachedDevice, v38, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, (unsigned int)v27);
LABEL_66:
          v16 = v44;
          goto LABEL_84;
        }
        v27 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
        if ( v27 < 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v38 = 206;
          goto LABEL_65;
        }
        v27 = BCryptHashData(phHash, *((PUCHAR *)v8 + 7), v17, 0);
        if ( v27 < 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v38 = 207;
          goto LABEL_65;
        }
        v27 = BCryptFinishHash(phHash, (PUCHAR)v8 + 24, 0x20u, 0);
        if ( v27 < 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v38 = 208;
          goto LABEL_65;
        }
        *a6 = v8;
        v8 = 0;
      }
      else
      {
        v27 = -1073741670;
      }
      v16 = v44;
      goto LABEL_84;
    }
    if ( v22 == 33 )
    {
      v44 = 1;
      HwWrappedFvekContentWithChallenge = FveIceExtractHwWrappedFvekContentWithChallenge(a1);
      v27 = HwWrappedFvekContentWithChallenge;
      if ( HwWrappedFvekContentWithChallenge >= 0 )
      {
        v27 = FveMapWrappingTypeToIceKeyType(*(unsigned int *)(a2 + 10), &v45);
        if ( v27 >= 0 )
        {
          v15 = 0;
          v17 = (unsigned __int16)FveDatumKeyGetSize(0);
          goto LABEL_38;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 201, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, v28, v27);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( ((unsigned __int8)Timer_high & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            200,
            WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids,
            (unsigned int)HwWrappedFvekContentWithChallenge);
      }
      v15 = 0;
      goto LABEL_84;
    }
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v32 = 202;
LABEL_45:
    WPP_SF_(v31->AttachedDevice, v32, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
    goto LABEL_24;
  }
  if ( v22 != 1 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v32 = 203;
    goto LABEL_45;
  }
  v15 = a2;
  Size = (unsigned __int16)FveDatumKeyGetSize(a2);
  if ( v17 == Size )
    goto LABEL_38;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_24;
  }
  v25 = 204;
LABEL_23:
  WPP_SF_Dd(v24->AttachedDevice, v25, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, v17, Size);
LABEL_24:
  v16 = 0;
LABEL_83:
  v27 = -1073741811;
LABEL_84:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  v39 = phAlgorithm;
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( v8 )
  {
    v40 = *((_QWORD *)v8 + 7);
    if ( v40 )
    {
      FveSecureZeroAndFlush(v40, v17);
      ExFreePoolWithTag(*((PVOID *)v8 + 7), 0x656E6F4Eu);
    }
    memset(v8, 0, v8[1]);
    ExFreePoolWithTag(v8, 0x656E6F4Eu);
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v39, Timer_high)
    && v16
    && v15 )
  {
    FveDatumFree(v15);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      209,
      WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids,
      (unsigned int)v27);
  }
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x1400a865c  mov     [rsp-40h+arg_18], r9d
0x1400a8661  mov     [rsp-40h+arg_10], r8d
0x1400a8666  push    rbp
0x1400a8667  push    rbx
0x1400a8668  push    rsi
0x1400a8669  push    rdi
0x1400a866a  push    r12
0x1400a866c  push    r13
0x1400a866e  push    r14
0x1400a8670  push    r15
0x1400a8672  mov     rbp, rsp
0x1400a8675  sub     rsp, 68h
0x1400a8679  mov     r13d, [rcx+51Ch]
0x1400a8680  mov     rsi, rdx
0x1400a8683  mov     r10d, [rbp+arg_20]
0x1400a8687  mov     rbx, rcx
0x1400a868a  xor     edi, edi
0x1400a868c  shr     r13d, 9
0x1400a8690  mov     edx, r10d
0x1400a8693  mov     [rbp+phAlgorithm], rdi
0x1400a8697  mov     ecx, r9d
0x1400a869a  mov     [rbp+phHash], rdi
0x1400a869e  mov     r11d, r8d
0x1400a86a1  call    FveIceAlgorithmBitSizeToKeySize
0x1400a86a6  xor     r15d, r15d
0x1400a86a9  mov     [rbp+arg_8], edi
0x1400a86ac  xor     r14d, r14d
0x1400a86af  mov     [rbp+var_28], r15
0x1400a86b3  mov     [rbp+arg_0], r14d
0x1400a86b7  mov     r12d, eax
0x1400a86ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a86c1  lea     rdx, WPP_GLOBAL_Control
0x1400a86c8  cmp     rcx, rdx
0x1400a86cb  jz      short loc_1400A8700
0x1400a86cd  mov     eax, [rcx+2Ch]
0x1400a86d0  test    al, 4
0x1400a86d2  jz      short loc_1400A8700
0x1400a86d4  cmp     byte ptr [rcx+29h], 5
0x1400a86d8  jb      short loc_1400A8700
0x1400a86da  mov     rcx, [rcx+18h]
0x1400a86de  mov     [rsp+68h+dwFlags], r13d
0x1400a86e3  mov     [rsp+68h+cbSecret], r10d
0x1400a86e8  mov     dword ptr [rsp+68h+pbSecret], r9d
0x1400a86ed  mov     r9d, r11d
0x1400a86f0  call    WPP_SF_LLLD
0x1400a86f5  mov     r9d, [rbp+arg_18]
0x1400a86f9  lea     rdx, WPP_GLOBAL_Control
0x1400a8700  test    rsi, rsi
0x1400a8703  jz      loc_1400A8BF0
0x1400a8709  test    r13d, r13d
0x1400a870c  jz      loc_1400A8BF0
0x1400a8712  cmp     r12d, 0FFFFFFFFh
0x1400a8716  jz      loc_1400A8BF0
0x1400a871c  cmp     r9d, 5
0x1400a8720  jge     loc_1400A8BF0
0x1400a8726  mov     ecx, [rbx+51Ch]
0x1400a872c  test    ecx, ecx
0x1400a872e  jz      loc_1400A8BF0
0x1400a8734  lea     eax, [rcx-1]
0x1400a8737  test    ecx, eax
0x1400a8739  jnz     loc_1400A8BF0
0x1400a873f  cmp     [rbp+arg_28], rdi
0x1400a8743  jz      loc_1400A8BF0
0x1400a8749  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8750  cmp     rcx, rdx
0x1400a8753  jz      short loc_1400A877C
0x1400a8755  mov     eax, [rcx+2Ch]
0x1400a8758  test    al, 4
0x1400a875a  jz      short loc_1400A877C
0x1400a875c  cmp     byte ptr [rcx+29h], 5
0x1400a8760  jb      short loc_1400A877C
0x1400a8762  movzx   r9d, word ptr [rsi+4]
0x1400a8767  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a876e  mov     rcx, [rcx+18h]
0x1400a8772  mov     edx, 0C6h
0x1400a8777  call    WPP_SF_d
0x1400a877c  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400a8781  movzx   ecx, word ptr [rsi+4]
0x1400a8785  mov     r14d, 1
0x1400a878b  test    eax, eax
0x1400a878d  jz      loc_1400A8944
0x1400a8793  cmp     cx, r14w
0x1400a8797  jnz     short loc_1400A87FB
0x1400a8799  xor     eax, eax
0x1400a879b  mov     rcx, rsi
0x1400a879e  mov     [rbp+arg_0], eax
0x1400a87a1  mov     r15, rsi
0x1400a87a4  call    FveDatumKeyGetSize
0x1400a87a9  movzx   r8d, ax
0x1400a87ad  cmp     r12d, r8d
0x1400a87b0  jz      loc_1400A88C1
0x1400a87b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a87bd  lea     rsi, WPP_GLOBAL_Control
0x1400a87c4  cmp     rcx, rsi
0x1400a87c7  jz      short loc_1400A87F3
0x1400a87c9  mov     eax, [rcx+2Ch]
0x1400a87cc  test    al, 4
0x1400a87ce  jz      short loc_1400A87F3
0x1400a87d0  cmp     byte ptr [rcx+29h], 2
0x1400a87d4  jb      short loc_1400A87F3
0x1400a87d6  mov     edx, 0C7h
0x1400a87db  mov     rcx, [rcx+18h]
0x1400a87df  mov     r9d, r12d
0x1400a87e2  mov     dword ptr [rsp+68h+pbSecret], r8d
0x1400a87e7  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a87ee  call    WPP_SF_Dd
0x1400a87f3  mov     r14d, edi
0x1400a87f6  jmp     loc_1400A8BF7
0x1400a87fb  cmp     cx, 21h ; '!'
0x1400a87ff  jnz     loc_1400A88FE
0x1400a8805  lea     r8, [rbp+var_28]
0x1400a8809  mov     [rbp+arg_0], r14d
0x1400a880d  mov     rdx, rsi
0x1400a8810  mov     rcx, rbx; int
0x1400a8813  call    FveIceExtractHwWrappedFvekContentWithChallenge
0x1400a8818  mov     ebx, eax
0x1400a881a  test    eax, eax
0x1400a881c  jns     short loc_1400A8860
0x1400a881e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8825  lea     rsi, WPP_GLOBAL_Control
0x1400a882c  cmp     rcx, rsi
0x1400a882f  jz      short loc_1400A8857
0x1400a8831  mov     edx, [rcx+2Ch]
0x1400a8834  test    dl, 4
0x1400a8837  jz      short loc_1400A8857
0x1400a8839  cmp     byte ptr [rcx+29h], 2
0x1400a883d  jb      short loc_1400A8857
0x1400a883f  mov     rcx, [rcx+18h]
0x1400a8843  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a884a  mov     edx, 0C8h
0x1400a884f  mov     r9d, eax
0x1400a8852  call    WPP_SF_d
0x1400a8857  mov     r15, [rbp+var_28]
0x1400a885b  jmp     loc_1400A8BFC
0x1400a8860  mov     r9d, [rsi+0Ah]
0x1400a8864  lea     rdx, [rbp+arg_8]
0x1400a8868  mov     ecx, r9d
0x1400a886b  call    FveMapWrappingTypeToIceKeyType
0x1400a8870  mov     ebx, eax
0x1400a8872  test    eax, eax
0x1400a8874  jns     short loc_1400A88B1
0x1400a8876  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a887d  lea     rsi, WPP_GLOBAL_Control
0x1400a8884  cmp     rcx, rsi
0x1400a8887  jz      short loc_1400A8857
0x1400a8889  mov     eax, [rcx+2Ch]
0x1400a888c  test    al, 4
0x1400a888e  jz      short loc_1400A8857
0x1400a8890  cmp     byte ptr [rcx+29h], 2
0x1400a8894  jb      short loc_1400A8857
0x1400a8896  mov     rcx, [rcx+18h]
0x1400a889a  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a88a1  mov     edx, 0C9h
0x1400a88a6  mov     dword ptr [rsp+68h+pbSecret], ebx
0x1400a88aa  call    WPP_SF_Dd
0x1400a88af  jmp     short loc_1400A8857
0x1400a88b1  mov     r15, [rbp+var_28]
0x1400a88b5  mov     rcx, r15
0x1400a88b8  call    FveDatumKeyGetSize
0x1400a88bd  movzx   r12d, ax
0x1400a88c1  mov     ebx, 70h ; 'p'
0x1400a88c6  mov     r8d, 656E6F4Eh
0x1400a88cc  mov     edx, ebx
0x1400a88ce  lea     ecx, [rbx-30h]
0x1400a88d1  call    cs:__imp_ExAllocatePool2
0x1400a88d8  nop     dword ptr [rax+rax+00h]
0x1400a88dd  mov     rdi, rax
0x1400a88e0  test    rax, rax
0x1400a88e3  jnz     loc_1400A89CB
0x1400a88e9  mov     ebx, 0C000009Ah
0x1400a88ee  mov     r14d, [rbp+arg_0]
0x1400a88f2  lea     rsi, WPP_GLOBAL_Control
0x1400a88f9  jmp     loc_1400A8BFC
0x1400a88fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8905  lea     rsi, WPP_GLOBAL_Control
0x1400a890c  cmp     rcx, rsi
0x1400a890f  jz      loc_1400A87F3
0x1400a8915  mov     eax, [rcx+2Ch]
0x1400a8918  test    al, 4
0x1400a891a  jz      loc_1400A87F3
0x1400a8920  cmp     byte ptr [rcx+29h], 2
0x1400a8924  jb      loc_1400A87F3
0x1400a892a  mov     edx, 0CAh
0x1400a892f  mov     rcx, [rcx+18h]
0x1400a8933  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a893a  call    WPP_SF_
0x1400a893f  jmp     loc_1400A87F3
0x1400a8944  cmp     cx, r14w
0x1400a8948  jz      short loc_1400A897D
0x1400a894a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8951  lea     rsi, WPP_GLOBAL_Control
0x1400a8958  cmp     rcx, rsi
0x1400a895b  jz      loc_1400A87F3
0x1400a8961  mov     eax, [rcx+2Ch]
0x1400a8964  test    al, 4
0x1400a8966  jz      loc_1400A87F3
0x1400a896c  cmp     byte ptr [rcx+29h], 2
0x1400a8970  jb      loc_1400A87F3
0x1400a8976  mov     edx, 0CBh
0x1400a897b  jmp     short loc_1400A892F
0x1400a897d  mov     rcx, rsi
0x1400a8980  mov     r15, rsi
0x1400a8983  call    FveDatumKeyGetSize
0x1400a8988  movzx   r8d, ax
0x1400a898c  cmp     r12d, r8d
0x1400a898f  jz      loc_1400A88C1
0x1400a8995  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a899c  lea     rsi, WPP_GLOBAL_Control
0x1400a89a3  cmp     rcx, rsi
0x1400a89a6  jz      loc_1400A87F3
0x1400a89ac  mov     eax, [rcx+2Ch]
0x1400a89af  test    al, 4
0x1400a89b1  jz      loc_1400A87F3
0x1400a89b7  cmp     byte ptr [rcx+29h], 2
0x1400a89bb  jb      loc_1400A87F3
0x1400a89c1  mov     edx, 0CCh
0x1400a89c6  jmp     loc_1400A87DB
0x1400a89cb  mov     r8, rbx; Size
0x1400a89ce  xor     edx, edx; Val
0x1400a89d0  mov     rcx, rdi; void *
0x1400a89d3  call    memset
0x1400a89d8  mov     r8d, 656E6F4Eh
0x1400a89de  mov     edx, r12d
0x1400a89e1  mov     ecx, 40h ; '@'
0x1400a89e6  mov     esi, r12d
0x1400a89e9  call    cs:__imp_ExAllocatePool2
0x1400a89f0  nop     dword ptr [rax+rax+00h]
0x1400a89f5  mov     [rdi+38h], rax
0x1400a89f9  test    rax, rax
0x1400a89fc  jz      loc_1400A88E9
0x1400a8a02  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400a8a07  test    eax, eax
0x1400a8a09  jz      short loc_1400A8A2B
0x1400a8a0b  mov     eax, [rbp+arg_8]
0x1400a8a0e  mov     [rdi+58h], eax
0x1400a8a11  lea     rax, FveAdjustCryptoParametersCallback
0x1400a8a18  mov     [rdi+60h], rax
0x1400a8a1c  mov     eax, 2
0x1400a8a21  mov     qword ptr [rdi+68h], 0
0x1400a8a29  jmp     short loc_1400A8A3A
0x1400a8a2b  mov     dword ptr [rdi+58h], 0
0x1400a8a32  mov     ebx, 48h ; 'H'
0x1400a8a37  mov     eax, r14d
0x1400a8a3a  mov     [rdi], eax
0x1400a8a3c  lea     rdx, [r15+0Ch]; Src
0x1400a8a40  mov     [rdi+4], ebx
0x1400a8a43  mov     r8, rsi; Size
0x1400a8a46  mov     eax, [rbp+arg_10]
0x1400a8a49  mov     rcx, [rdi+38h]; void *
0x1400a8a4d  mov     [rdi+8], eax
0x1400a8a50  mov     eax, [rbp+arg_18]
0x1400a8a53  mov     [rdi+0Ch], eax
0x1400a8a56  mov     [rdi+14h], r12d
0x1400a8a5a  mov     [rdi+10h], r13d
0x1400a8a5e  call    memmove
0x1400a8a63  mov     rcx, [rdi+38h]; BaseAddress
0x1400a8a67  call    cs:__imp_MmGetPhysicalAddress
0x1400a8a6e  nop     dword ptr [rax+rax+00h]
0x1400a8a73  mov     r9d, r14d; dwFlags
0x1400a8a76  lea     rdx, aSha256; "SHA256"
0x1400a8a7d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400a8a81  mov     [rdi+40h], rax
0x1400a8a85  xor     r8d, r8d; pszImplementation
0x1400a8a88  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400a8a8f  nop     dword ptr [rax+rax+00h]
0x1400a8a94  xor     r14d, r14d
0x1400a8a97  mov     ebx, eax
0x1400a8a99  test    eax, eax
0x1400a8a9b  jns     short loc_1400A8ADE
0x1400a8a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8aa4  lea     rsi, WPP_GLOBAL_Control
0x1400a8aab  cmp     rcx, rsi
0x1400a8aae  jz      short loc_1400A8AD5
0x1400a8ab0  mov     eax, [rcx+2Ch]
0x1400a8ab3  test    al, 4
0x1400a8ab5  jz      short loc_1400A8AD5
0x1400a8ab7  cmp     byte ptr [rcx+29h], 2
0x1400a8abb  jb      short loc_1400A8AD5
0x1400a8abd  mov     edx, 0CDh
0x1400a8ac2  mov     rcx, [rcx+18h]
0x1400a8ac6  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a8acd  mov     r9d, ebx
0x1400a8ad0  call    WPP_SF_d
0x1400a8ad5  mov     r14d, [rbp+arg_0]
0x1400a8ad9  jmp     loc_1400A8BFC
0x1400a8ade  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400a8ae2  lea     rdx, [rbp+phHash]; phHash
0x1400a8ae6  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x1400a8aeb  xor     r9d, r9d; cbHashObject
0x1400a8aee  mov     [rsp+68h+cbSecret], r14d; cbSecret
0x1400a8af3  xor     r8d, r8d; pbHashObject
0x1400a8af6  mov     [rsp+68h+pbSecret], r14; pbSecret
0x1400a8afb  call    cs:__imp_BCryptCreateHash
0x1400a8b02  nop     dword ptr [rax+rax+00h]
0x1400a8b07  mov     ebx, eax
0x1400a8b09  test    eax, eax
0x1400a8b0b  jns     short loc_1400A8B34
0x1400a8b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8b14  lea     rsi, WPP_GLOBAL_Control
0x1400a8b1b  cmp     rcx, rsi
  ... truncated ...
```
