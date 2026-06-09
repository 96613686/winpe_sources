# FveCreateIceKey

- ea: `0x1400a7704`
- end: `0x1400a7d8d`
- name: `FveCreateIceKey`
- size: `1673`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x14007a0f8`
- `0x1400acd3c`
- `0x1400ad2fc`
- `0x1400ae214`

## callees

- `0x140005e50`
- `0x140008288`
- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x14000c050`
- `0x14000c598`
- `0x140014464`
- `0x140021a00`
- `0x140021d00`
- `0x14002e59c`
- `0x1400a7704`
- `0x1400c7358`
- `0x1400c8b70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7cff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7d21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7cff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7d21`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7979`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7a91`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7979`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7a91`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400a7b0f`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400a7b0f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400a7ccc`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400a7ccc`
- `ksecdd!BCryptDestroyHash` at `0x1400a7cad`
- `ksecdd!BCryptDestroyHash` at `0x1400a7cad`
- `ksecdd!BCryptFinishHash` at `0x1400a7c41`
- `ksecdd!BCryptFinishHash` at `0x1400a7c41`
- `ksecdd!BCryptHashData` at `0x1400a7bea`
- `ksecdd!BCryptHashData` at `0x1400a7bea`
- `ksecdd!BCryptCreateHash` at `0x1400a7ba3`
- `ksecdd!BCryptCreateHash` at `0x1400a7ba3`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400a7b30`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400a7b30`

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
  int v18; // ecx
  PDEVICE_OBJECT v19; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int16 v21; // cx
  int Size; // r8d
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  int HwWrappedFvekContentWithChallenge; // eax
  NTSTATUS v26; // ebx
  __int64 v27; // r9
  int v28; // ebx
  unsigned int *Pool2; // rax
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  void *v35; // rcx
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  BCRYPT_ALG_HANDLE v38; // rcx
  __int64 v39; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  int v43; // [rsp+B0h] [rbp+48h]
  unsigned int v44; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v45; // [rsp+C0h] [rbp+58h]
  int v46; // [rsp+C8h] [rbp+60h]

  v46 = a4;
  v45 = a3;
  v8 = 0;
  v9 = *(_DWORD *)(a1 + 1308) >> 9;
  phAlgorithm = 0;
  phHash = 0;
  v10 = FveIceAlgorithmBitSizeToKeySize(a4, a5);
  v15 = 0;
  v44 = 0;
  v16 = 0;
  v43 = 0;
  v17 = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_LLLD(WPP_GLOBAL_Control->AttachedDevice, &WPP_GLOBAL_Control, v11, v14, v12, v13, v9);
    v12 = v46;
  }
  if ( !a2 )
    goto LABEL_83;
  if ( !v9 )
    goto LABEL_83;
  if ( v17 == -1 )
    goto LABEL_83;
  if ( v12 >= 5 )
    goto LABEL_83;
  v18 = *(_DWORD *)(a1 + 1308);
  if ( !v18 || ((v18 - 1) & v18) != 0 || !a6 )
    goto LABEL_83;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      198,
      WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids,
      *(unsigned __int16 *)(a2 + 4));
  }
  IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v19);
  v21 = *(_WORD *)(a2 + 4);
  v16 = 1;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( v21 == 1 )
    {
      v43 = 0;
      v15 = a2;
      Size = (unsigned __int16)FveDatumKeyGetSize(a2);
      if ( v17 != Size )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_24;
        }
        v24 = 199;
        goto LABEL_23;
      }
LABEL_38:
      v28 = 112;
      Pool2 = (unsigned int *)ExAllocatePool2(64, 112, 1701736270);
      v8 = Pool2;
      if ( Pool2
        && (memset(Pool2, 0, 0x70u), v32 = ExAllocatePool2(64, v17, 1701736270), (*((_QWORD *)v8 + 7) = v32) != 0) )
      {
        if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v33) )
        {
          v8[22] = v44;
          *((_QWORD *)v8 + 12) = FveAdjustCryptoParametersCallback;
          v34 = 2;
          *((_QWORD *)v8 + 13) = 0;
        }
        else
        {
          v8[22] = 0;
          v28 = 72;
          v34 = 1;
        }
        *v8 = v34;
        v8[1] = v28;
        v35 = (void *)*((_QWORD *)v8 + 7);
        v8[2] = v45;
        v8[3] = v46;
        v8[5] = v17;
        v8[4] = v9;
        memmove(v35, (const void *)(v15 + 12), v17);
        *((PHYSICAL_ADDRESS *)v8 + 8) = MmGetPhysicalAddress(*((PVOID *)v8 + 7));
        v26 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 1u);
        if ( v26 < 0 )
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v37 = 205;
LABEL_65:
          WPP_SF_d(v36->AttachedDevice, v37, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, (unsigned int)v26);
LABEL_66:
          v16 = v43;
          goto LABEL_84;
        }
        v26 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
        if ( v26 < 0 )
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v37 = 206;
          goto LABEL_65;
        }
        v26 = BCryptHashData(phHash, *((PUCHAR *)v8 + 7), v17, 0);
        if ( v26 < 0 )
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v37 = 207;
          goto LABEL_65;
        }
        v26 = BCryptFinishHash(phHash, (PUCHAR)v8 + 24, 0x20u, 0);
        if ( v26 < 0 )
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_66;
          }
          v37 = 208;
          goto LABEL_65;
        }
        *a6 = v8;
        v8 = 0;
      }
      else
      {
        v26 = -1073741670;
      }
      v16 = v43;
      goto LABEL_84;
    }
    if ( v21 == 33 )
    {
      v43 = 1;
      HwWrappedFvekContentWithChallenge = FveIceExtractHwWrappedFvekContentWithChallenge(a1);
      v26 = HwWrappedFvekContentWithChallenge;
      if ( HwWrappedFvekContentWithChallenge >= 0 )
      {
        v26 = FveMapWrappingTypeToIceKeyType(*(unsigned int *)(a2 + 10), &v44);
        if ( v26 >= 0 )
        {
          v15 = 0;
          v17 = (unsigned __int16)FveDatumKeyGetSize(0);
          goto LABEL_38;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 201, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, v27, v26);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          200,
          WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids,
          (unsigned int)HwWrappedFvekContentWithChallenge);
      }
      v15 = 0;
      goto LABEL_84;
    }
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v31 = 202;
LABEL_45:
    WPP_SF_(v30->AttachedDevice, v31, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
    goto LABEL_24;
  }
  if ( v21 != 1 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v31 = 203;
    goto LABEL_45;
  }
  v15 = a2;
  Size = (unsigned __int16)FveDatumKeyGetSize(a2);
  if ( v17 == Size )
    goto LABEL_38;
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_24;
  }
  v24 = 204;
LABEL_23:
  WPP_SF_Dd(v23->AttachedDevice, v24, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, v17, Size);
LABEL_24:
  v16 = 0;
LABEL_83:
  v26 = -1073741811;
LABEL_84:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  v38 = phAlgorithm;
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( v8 )
  {
    v39 = *((_QWORD *)v8 + 7);
    if ( v39 )
    {
      FveSecureZeroAndFlush(v39, v17);
      ExFreePoolWithTag(*((PVOID *)v8 + 7), 0x656E6F4Eu);
    }
    memset(v8, 0, v8[1]);
    ExFreePoolWithTag(v8, 0x656E6F4Eu);
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v38) && v16 && v15 )
    FveDatumFree(v15);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      209,
      WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids,
      (unsigned int)v26);
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1400a7704  mov     [rsp-40h+arg_18], r9d
0x1400a7709  mov     [rsp-40h+arg_10], r8d
0x1400a770e  push    rbp
0x1400a770f  push    rbx
0x1400a7710  push    rsi
0x1400a7711  push    rdi
0x1400a7712  push    r12
0x1400a7714  push    r13
0x1400a7716  push    r14
0x1400a7718  push    r15
0x1400a771a  mov     rbp, rsp
0x1400a771d  sub     rsp, 68h
0x1400a7721  mov     r13d, [rcx+51Ch]
0x1400a7728  mov     rsi, rdx
0x1400a772b  mov     r10d, [rbp+arg_20]
0x1400a772f  mov     rbx, rcx
0x1400a7732  xor     edi, edi
0x1400a7734  shr     r13d, 9
0x1400a7738  mov     edx, r10d
0x1400a773b  mov     [rbp+phAlgorithm], rdi
0x1400a773f  mov     ecx, r9d
0x1400a7742  mov     [rbp+phHash], rdi
0x1400a7746  mov     r11d, r8d
0x1400a7749  call    FveIceAlgorithmBitSizeToKeySize
0x1400a774e  xor     r15d, r15d
0x1400a7751  mov     [rbp+arg_8], edi
0x1400a7754  xor     r14d, r14d
0x1400a7757  mov     [rbp+var_28], r15
0x1400a775b  mov     [rbp+arg_0], r14d
0x1400a775f  mov     r12d, eax
0x1400a7762  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7769  lea     rdx, WPP_GLOBAL_Control
0x1400a7770  cmp     rcx, rdx
0x1400a7773  jz      short loc_1400A77A8
0x1400a7775  mov     eax, [rcx+2Ch]
0x1400a7778  test    al, 4
0x1400a777a  jz      short loc_1400A77A8
0x1400a777c  cmp     byte ptr [rcx+29h], 5
0x1400a7780  jb      short loc_1400A77A8
0x1400a7782  mov     rcx, [rcx+18h]
0x1400a7786  mov     [rsp+68h+dwFlags], r13d
0x1400a778b  mov     [rsp+68h+cbSecret], r10d
0x1400a7790  mov     dword ptr [rsp+68h+pbSecret], r9d
0x1400a7795  mov     r9d, r11d
0x1400a7798  call    WPP_SF_LLLD
0x1400a779d  mov     r9d, [rbp+arg_18]
0x1400a77a1  lea     rdx, WPP_GLOBAL_Control
0x1400a77a8  test    rsi, rsi
0x1400a77ab  jz      loc_1400A7C98
0x1400a77b1  test    r13d, r13d
0x1400a77b4  jz      loc_1400A7C98
0x1400a77ba  cmp     r12d, 0FFFFFFFFh
0x1400a77be  jz      loc_1400A7C98
0x1400a77c4  cmp     r9d, 5
0x1400a77c8  jge     loc_1400A7C98
0x1400a77ce  mov     ecx, [rbx+51Ch]
0x1400a77d4  test    ecx, ecx
0x1400a77d6  jz      loc_1400A7C98
0x1400a77dc  lea     eax, [rcx-1]
0x1400a77df  test    ecx, eax
0x1400a77e1  jnz     loc_1400A7C98
0x1400a77e7  cmp     [rbp+arg_28], rdi
0x1400a77eb  jz      loc_1400A7C98
0x1400a77f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a77f8  cmp     rcx, rdx
0x1400a77fb  jz      short loc_1400A7824
0x1400a77fd  mov     eax, [rcx+2Ch]
0x1400a7800  test    al, 4
0x1400a7802  jz      short loc_1400A7824
0x1400a7804  cmp     byte ptr [rcx+29h], 5
0x1400a7808  jb      short loc_1400A7824
0x1400a780a  movzx   r9d, word ptr [rsi+4]
0x1400a780f  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a7816  mov     rcx, [rcx+18h]
0x1400a781a  mov     edx, 0C6h
0x1400a781f  call    WPP_SF_d
0x1400a7824  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400a7829  movzx   ecx, word ptr [rsi+4]
0x1400a782d  mov     r14d, 1
0x1400a7833  test    eax, eax
0x1400a7835  jz      loc_1400A79EC
0x1400a783b  cmp     cx, r14w
0x1400a783f  jnz     short loc_1400A78A3
0x1400a7841  xor     eax, eax
0x1400a7843  mov     rcx, rsi
0x1400a7846  mov     [rbp+arg_0], eax
0x1400a7849  mov     r15, rsi
0x1400a784c  call    FveDatumKeyGetSize
0x1400a7851  movzx   r8d, ax
0x1400a7855  cmp     r12d, r8d
0x1400a7858  jz      loc_1400A7969
0x1400a785e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7865  lea     rsi, WPP_GLOBAL_Control
0x1400a786c  cmp     rcx, rsi
0x1400a786f  jz      short loc_1400A789B
0x1400a7871  mov     eax, [rcx+2Ch]
0x1400a7874  test    al, 4
0x1400a7876  jz      short loc_1400A789B
0x1400a7878  cmp     byte ptr [rcx+29h], 2
0x1400a787c  jb      short loc_1400A789B
0x1400a787e  mov     edx, 0C7h
0x1400a7883  mov     rcx, [rcx+18h]
0x1400a7887  mov     r9d, r12d
0x1400a788a  mov     dword ptr [rsp+68h+pbSecret], r8d
0x1400a788f  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a7896  call    WPP_SF_Dd
0x1400a789b  mov     r14d, edi
0x1400a789e  jmp     loc_1400A7C9F
0x1400a78a3  cmp     cx, 21h ; '!'
0x1400a78a7  jnz     loc_1400A79A6
0x1400a78ad  lea     r8, [rbp+var_28]
0x1400a78b1  mov     [rbp+arg_0], r14d
0x1400a78b5  mov     rdx, rsi
0x1400a78b8  mov     rcx, rbx; int
0x1400a78bb  call    FveIceExtractHwWrappedFvekContentWithChallenge
0x1400a78c0  mov     ebx, eax
0x1400a78c2  test    eax, eax
0x1400a78c4  jns     short loc_1400A7908
0x1400a78c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a78cd  lea     rsi, WPP_GLOBAL_Control
0x1400a78d4  cmp     rcx, rsi
0x1400a78d7  jz      short loc_1400A78FF
0x1400a78d9  mov     edx, [rcx+2Ch]
0x1400a78dc  test    dl, 4
0x1400a78df  jz      short loc_1400A78FF
0x1400a78e1  cmp     byte ptr [rcx+29h], 2
0x1400a78e5  jb      short loc_1400A78FF
0x1400a78e7  mov     rcx, [rcx+18h]
0x1400a78eb  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a78f2  mov     edx, 0C8h
0x1400a78f7  mov     r9d, eax
0x1400a78fa  call    WPP_SF_d
0x1400a78ff  mov     r15, [rbp+var_28]
0x1400a7903  jmp     loc_1400A7CA4
0x1400a7908  mov     r9d, [rsi+0Ah]
0x1400a790c  lea     rdx, [rbp+arg_8]
0x1400a7910  mov     ecx, r9d
0x1400a7913  call    FveMapWrappingTypeToIceKeyType
0x1400a7918  mov     ebx, eax
0x1400a791a  test    eax, eax
0x1400a791c  jns     short loc_1400A7959
0x1400a791e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7925  lea     rsi, WPP_GLOBAL_Control
0x1400a792c  cmp     rcx, rsi
0x1400a792f  jz      short loc_1400A78FF
0x1400a7931  mov     eax, [rcx+2Ch]
0x1400a7934  test    al, 4
0x1400a7936  jz      short loc_1400A78FF
0x1400a7938  cmp     byte ptr [rcx+29h], 2
0x1400a793c  jb      short loc_1400A78FF
0x1400a793e  mov     rcx, [rcx+18h]
0x1400a7942  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a7949  mov     edx, 0C9h
0x1400a794e  mov     dword ptr [rsp+68h+pbSecret], ebx
0x1400a7952  call    WPP_SF_Dd
0x1400a7957  jmp     short loc_1400A78FF
0x1400a7959  mov     r15, [rbp+var_28]
0x1400a795d  mov     rcx, r15
0x1400a7960  call    FveDatumKeyGetSize
0x1400a7965  movzx   r12d, ax
0x1400a7969  mov     ebx, 70h ; 'p'
0x1400a796e  mov     r8d, 656E6F4Eh
0x1400a7974  mov     edx, ebx
0x1400a7976  lea     ecx, [rbx-30h]
0x1400a7979  call    cs:__imp_ExAllocatePool2
0x1400a7980  nop     dword ptr [rax+rax+00h]
0x1400a7985  mov     rdi, rax
0x1400a7988  test    rax, rax
0x1400a798b  jnz     loc_1400A7A73
0x1400a7991  mov     ebx, 0C000009Ah
0x1400a7996  mov     r14d, [rbp+arg_0]
0x1400a799a  lea     rsi, WPP_GLOBAL_Control
0x1400a79a1  jmp     loc_1400A7CA4
0x1400a79a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a79ad  lea     rsi, WPP_GLOBAL_Control
0x1400a79b4  cmp     rcx, rsi
0x1400a79b7  jz      loc_1400A789B
0x1400a79bd  mov     eax, [rcx+2Ch]
0x1400a79c0  test    al, 4
0x1400a79c2  jz      loc_1400A789B
0x1400a79c8  cmp     byte ptr [rcx+29h], 2
0x1400a79cc  jb      loc_1400A789B
0x1400a79d2  mov     edx, 0CAh
0x1400a79d7  mov     rcx, [rcx+18h]
0x1400a79db  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a79e2  call    WPP_SF_
0x1400a79e7  jmp     loc_1400A789B
0x1400a79ec  cmp     cx, r14w
0x1400a79f0  jz      short loc_1400A7A25
0x1400a79f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a79f9  lea     rsi, WPP_GLOBAL_Control
0x1400a7a00  cmp     rcx, rsi
0x1400a7a03  jz      loc_1400A789B
0x1400a7a09  mov     eax, [rcx+2Ch]
0x1400a7a0c  test    al, 4
0x1400a7a0e  jz      loc_1400A789B
0x1400a7a14  cmp     byte ptr [rcx+29h], 2
0x1400a7a18  jb      loc_1400A789B
0x1400a7a1e  mov     edx, 0CBh
0x1400a7a23  jmp     short loc_1400A79D7
0x1400a7a25  mov     rcx, rsi
0x1400a7a28  mov     r15, rsi
0x1400a7a2b  call    FveDatumKeyGetSize
0x1400a7a30  movzx   r8d, ax
0x1400a7a34  cmp     r12d, r8d
0x1400a7a37  jz      loc_1400A7969
0x1400a7a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7a44  lea     rsi, WPP_GLOBAL_Control
0x1400a7a4b  cmp     rcx, rsi
0x1400a7a4e  jz      loc_1400A789B
0x1400a7a54  mov     eax, [rcx+2Ch]
0x1400a7a57  test    al, 4
0x1400a7a59  jz      loc_1400A789B
0x1400a7a5f  cmp     byte ptr [rcx+29h], 2
0x1400a7a63  jb      loc_1400A789B
0x1400a7a69  mov     edx, 0CCh
0x1400a7a6e  jmp     loc_1400A7883
0x1400a7a73  mov     r8, rbx; Size
0x1400a7a76  xor     edx, edx; Val
0x1400a7a78  mov     rcx, rdi; void *
0x1400a7a7b  call    memset
0x1400a7a80  mov     r8d, 656E6F4Eh
0x1400a7a86  mov     edx, r12d
0x1400a7a89  mov     ecx, 40h ; '@'
0x1400a7a8e  mov     esi, r12d
0x1400a7a91  call    cs:__imp_ExAllocatePool2
0x1400a7a98  nop     dword ptr [rax+rax+00h]
0x1400a7a9d  mov     [rdi+38h], rax
0x1400a7aa1  test    rax, rax
0x1400a7aa4  jz      loc_1400A7991
0x1400a7aaa  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400a7aaf  test    eax, eax
0x1400a7ab1  jz      short loc_1400A7AD3
0x1400a7ab3  mov     eax, [rbp+arg_8]
0x1400a7ab6  mov     [rdi+58h], eax
0x1400a7ab9  lea     rax, FveAdjustCryptoParametersCallback
0x1400a7ac0  mov     [rdi+60h], rax
0x1400a7ac4  mov     eax, 2
0x1400a7ac9  mov     qword ptr [rdi+68h], 0
0x1400a7ad1  jmp     short loc_1400A7AE2
0x1400a7ad3  mov     dword ptr [rdi+58h], 0
0x1400a7ada  mov     ebx, 48h ; 'H'
0x1400a7adf  mov     eax, r14d
0x1400a7ae2  mov     [rdi], eax
0x1400a7ae4  lea     rdx, [r15+0Ch]; Src
0x1400a7ae8  mov     [rdi+4], ebx
0x1400a7aeb  mov     r8, rsi; Size
0x1400a7aee  mov     eax, [rbp+arg_10]
0x1400a7af1  mov     rcx, [rdi+38h]; void *
0x1400a7af5  mov     [rdi+8], eax
0x1400a7af8  mov     eax, [rbp+arg_18]
0x1400a7afb  mov     [rdi+0Ch], eax
0x1400a7afe  mov     [rdi+14h], r12d
0x1400a7b02  mov     [rdi+10h], r13d
0x1400a7b06  call    memmove
0x1400a7b0b  mov     rcx, [rdi+38h]; BaseAddress
0x1400a7b0f  call    cs:__imp_MmGetPhysicalAddress
0x1400a7b16  nop     dword ptr [rax+rax+00h]
0x1400a7b1b  mov     r9d, r14d; dwFlags
0x1400a7b1e  lea     rdx, aSha256; "SHA256"
0x1400a7b25  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400a7b29  mov     [rdi+40h], rax
0x1400a7b2d  xor     r8d, r8d; pszImplementation
0x1400a7b30  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400a7b37  nop     dword ptr [rax+rax+00h]
0x1400a7b3c  xor     r14d, r14d
0x1400a7b3f  mov     ebx, eax
0x1400a7b41  test    eax, eax
0x1400a7b43  jns     short loc_1400A7B86
0x1400a7b45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7b4c  lea     rsi, WPP_GLOBAL_Control
0x1400a7b53  cmp     rcx, rsi
0x1400a7b56  jz      short loc_1400A7B7D
0x1400a7b58  mov     eax, [rcx+2Ch]
0x1400a7b5b  test    al, 4
0x1400a7b5d  jz      short loc_1400A7B7D
0x1400a7b5f  cmp     byte ptr [rcx+29h], 2
0x1400a7b63  jb      short loc_1400A7B7D
0x1400a7b65  mov     edx, 0CDh
0x1400a7b6a  mov     rcx, [rcx+18h]
0x1400a7b6e  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a7b75  mov     r9d, ebx
0x1400a7b78  call    WPP_SF_d
0x1400a7b7d  mov     r14d, [rbp+arg_0]
0x1400a7b81  jmp     loc_1400A7CA4
0x1400a7b86  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400a7b8a  lea     rdx, [rbp+phHash]; phHash
0x1400a7b8e  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x1400a7b93  xor     r9d, r9d; cbHashObject
0x1400a7b96  mov     [rsp+68h+cbSecret], r14d; cbSecret
0x1400a7b9b  xor     r8d, r8d; pbHashObject
0x1400a7b9e  mov     [rsp+68h+pbSecret], r14; pbSecret
0x1400a7ba3  call    cs:__imp_BCryptCreateHash
0x1400a7baa  nop     dword ptr [rax+rax+00h]
0x1400a7baf  mov     ebx, eax
0x1400a7bb1  test    eax, eax
0x1400a7bb3  jns     short loc_1400A7BDC
0x1400a7bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7bbc  lea     rsi, WPP_GLOBAL_Control
0x1400a7bc3  cmp     rcx, rsi
  ... truncated ...
```
