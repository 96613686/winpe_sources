# CallReceiveDatagramCallback

- ea: `0x140016db0`
- end: `0x140017649`
- name: `CallReceiveDatagramCallback`
- size: `2201`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003d58`
- `0x140003e08`
- `0x140003e38`
- `0x1400046e4`
- `0x1400076d0`
- `0x140007710`
- `0x140016db0`
- `0x14001e4e0`
- `0x14001e540`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400172f1`
- `ntoskrnl!RtlCompareMemory` at `0x140017413`
- `ntoskrnl!RtlCompareMemory` at `0x1400172f1`
- `ntoskrnl!RtlCompareMemory` at `0x140017413`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016f6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001715f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001722a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400172ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017319`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017395`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016f6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001715f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001722a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400172ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017319`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017395`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016f45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400171d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001723d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016f45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400171d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001723d`
- `NDIS!NdisQueueIoWorkItem` at `0x140017291`
- `NDIS!NdisQueueIoWorkItem` at `0x140017291`
- `NDIS!NdisGetDataBuffer` at `0x140016e51`
- `NDIS!NdisGetDataBuffer` at `0x140016e51`

## pseudocode

```c
__int64 __fastcall CallReceiveDatagramCallback(__int64 *a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rdi
  __int16 *v4; // r12
  __int16 v6; // bx
  __int64 v7; // rbp
  struct _NET_BUFFER *v8; // rcx
  unsigned __int64 DataLength; // r13
  PVOID DataBuffer; // rax
  __int64 v11; // r8
  int v12; // esi
  __int64 v13; // r10
  int v14; // r8d
  __int64 v15; // r10
  char v16; // dl
  char v17; // r9
  int v18; // ecx
  int v19; // ebx
  unsigned int v20; // r14d
  unsigned __int64 v21; // rbx
  __int64 v22; // r12
  unsigned __int64 v24; // rbp
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r14
  KIRQL v28; // al
  __int64 v29; // rcx
  KIRQL v30; // dl
  KIRQL v31; // al
  _QWORD *v32; // r11
  __int64 v33; // rax
  _QWORD *v34; // r10
  unsigned __int32 v35; // r9d
  _QWORD *i; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rsi
  __int64 StringFromSockAddr; // rdi
  int v39; // eax
  int v40; // r8d
  struct _DEVICE_OBJECT *v41; // rdi
  __int64 v42; // rbx
  int v43; // eax
  int v44; // r8d
  __int64 v45; // [rsp+30h] [rbp-108h]
  __int64 v46; // [rsp+38h] [rbp-100h] BYREF
  PVOID v47; // [rsp+40h] [rbp-F8h]
  _BYTE v48[80]; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v49[80]; // [rsp+A0h] [rbp-98h] BYREF

  v3 = *a1;
  v4 = *(__int16 **)(a2 + 8);
  v6 = *v4;
  v45 = *(_QWORD *)(*a1 + 64);
  v7 = 0;
  LODWORD(v46) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  if ( v6 != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    }
    goto LABEL_29;
  }
  _InterlockedIncrement(&dword_14000B400);
  v8 = (struct _NET_BUFFER *)a3[1];
  DataLength = v8->DataLength;
  DataBuffer = NdisGetDataBuffer(v8, v8->DataLength, 0, 1u, 0);
  v47 = DataBuffer;
  if ( !DataBuffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    }
    v12 = -1073741285;
    _InterlockedIncrement(&dword_14000B410);
    goto LABEL_30;
  }
  v12 = ProcessIpv4AddressFromPacket(DataBuffer, (unsigned int)DataLength, v11, &v46);
  if ( v12 < 0 || (v14 = v46, DataLength < (unsigned __int64)(unsigned int)v46 + 12) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    }
    _InterlockedIncrement(&dword_14000B410);
LABEL_29:
    v12 = -1073741823;
    goto LABEL_30;
  }
  v15 = (unsigned int)v46 + v13;
  v46 = v15;
  v16 = *(_BYTE *)v15;
  v17 = *(_BYTE *)(v15 + 1);
  v18 = ((*(_BYTE *)v15 & 0x10 | 0x20u) >> 2) + (((__int64)v17 >> 63) & 4);
  v19 = DataLength - v18 - v14;
  v20 = v18 + v14;
  if ( (unsigned int)DataLength < v18 + v14
    || (unsigned __int16)__ROR2__(*(_WORD *)(v15 + 4), 8) > v19
    || (v16 & 0x6F) != 0x20
    || v16 < 0
    || (v17 & 7) != 1
    || (v17 & 0x78) != 0
    || *(_WORD *)(v15 + 2) != 2952 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
      v15 = v46;
    }
    v12 = -1073741823;
    _InterlockedIncrement(&dword_14000B414);
    if ( (unsigned int)DataLength >= v20 )
    {
      if ( (unsigned __int16)__ROR2__(*(_WORD *)(v15 + 4), 8) > v19 )
        _InterlockedIncrement(&dword_14000B41C);
    }
    else
    {
      _InterlockedIncrement(&dword_14000B418);
    }
    goto LABEL_30;
  }
  v21 = (unsigned __int16)__ROR2__(*(_WORD *)(v15 + 6), 8);
  if ( PptpClientSide )
    v21 &= 0x3FFFu;
  *(_BYTE *)(v3 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 8));
  if ( v21 < (unsigned int)PptpBaseCallId || v21 >= (unsigned int)PptpMaxCallId )
    goto LABEL_16;
  if ( PptpCallIdMaskSet )
  {
    v24 = (unsigned int)v21 & PptpCallIdMask;
    if ( v24 >= (unsigned int)PptpWanEndpoints )
      goto LABEL_16;
    v7 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 8 * v24);
    if ( !v7 || *(_QWORD *)(v7 + 208) != v21 )
      goto LABEL_16;
  }
  else
  {
    _mm_lfence();
    v7 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 8 * (v21 - (unsigned int)PptpBaseCallId));
    if ( !v7 )
    {
LABEL_16:
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), *(_BYTE *)(v3 + 16));
      v7 = 0;
      goto LABEL_17;
    }
  }
  if ( *(_DWORD *)(v7 + 48) != 1129337936 )
    goto LABEL_16;
  _InterlockedIncrement((volatile signed __int32 *)v7);
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), *(_BYTE *)(v3 + 16));
  if ( *(_DWORD *)(v7 + 48) != 1129337936 )
  {
LABEL_17:
    v12 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    }
    _InterlockedIncrement(&dword_14000B420);
    goto LABEL_30;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 616));
  if ( PptpValidateAddress )
  {
    if ( *v4 == *(_WORD *)(v7 + 280) )
    {
      if ( *v4 == 2 )
      {
        if ( RtlCompareMemory(v4 + 2, (const void *)(v7 + 284), 4u) == 4 )
          goto LABEL_50;
      }
      else if ( RtlCompareMemory(v4 + 4, (const void *)(v7 + 288), 0x10u) == 16 )
      {
        goto LABEL_50;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      StringFromSockAddr = GetStringFromSockAddr(v7 + 280, v48);
      v39 = GetStringFromSockAddr(v4, v49);
      WPP_SF_ss((_DWORD)AttachedDevice, 84, v40, v39, StringFromSockAddr);
    }
    v12 = -1073741823;
    _InterlockedIncrement(&dword_14000B424);
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 656));
    if ( *(_BYTE *)(v7 + 194)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v41 = WPP_GLOBAL_Control->AttachedDevice;
      v42 = GetStringFromSockAddr(v7 + 280, v48);
      v43 = GetStringFromSockAddr(v4, v49);
      WPP_SF_ss((_DWORD)v41, 85, v44, v43, v42);
    }
LABEL_30:
    v22 = v45;
LABEL_31:
    ReceiveDataComplete(v22, a3);
    goto LABEL_32;
  }
LABEL_50:
  v25 = a3[2];
  v22 = v45;
  v26 = *(unsigned __int16 *)(v25 + 10);
  *(_QWORD *)(v26 + v25 + 16) = v47;
  *(_QWORD *)(v26 + v25 + 24) = v46;
  *(_QWORD *)(v26 + v25 + 32) = v45;
  *(_DWORD *)(v26 + v25 + 40) = DataLength;
  v27 = *(_QWORD *)(*(unsigned __int16 *)(a3[2] + 10LL) + a3[2] + 24LL);
  if ( (*(_BYTE *)v27 & 0x10) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 624));
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 640));
    _InterlockedIncrement(&dword_14000B404);
    goto LABEL_31;
  }
  v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 96));
  *(_BYTE *)(v7 + 104) = v28;
  if ( __ROR2__(*(_WORD *)(v27 + 6), 8) != *(_WORD *)(v7 + 320) )
    goto LABEL_65;
  if ( *(_DWORD *)(v7 + 112) != 9 )
    goto LABEL_66;
  v29 = *(_QWORD *)(v7 + 80);
  if ( !v29 || *(_DWORD *)(v29 + 48) == 7 )
  {
LABEL_65:
    if ( *(_DWORD *)(v7 + 112) == 9 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 96), v28);
      v33 = 648;
      goto LABEL_67;
    }
LABEL_66:
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 96), v28);
    v33 = 644;
LABEL_67:
    _InterlockedIncrement((volatile signed __int32 *)(v7 + v33));
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 624));
    _InterlockedIncrement(&dword_14000B404);
    goto LABEL_31;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 32));
  v30 = *(_BYTE *)(v7 + 104);
  ++*(_DWORD *)(v7 + 184);
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 96), v30);
  v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 168));
  v32 = *(_QWORD **)(v7 + 152);
  *(_BYTE *)(v7 + 176) = v31;
  if ( v32 )
  {
    v34 = 0;
    v35 = _byteswap_ulong(*(_DWORD *)(v27 + 8));
    for ( i = v32; ; i = (_QWORD *)*i )
    {
      if ( !i )
      {
        **(_QWORD **)(v7 + 160) = a3;
        goto LABEL_57;
      }
      if ( (int)(_byteswap_ulong(*(_DWORD *)(*(_QWORD *)(*(unsigned __int16 *)(i[2] + 10LL) + i[2] + 24LL) + 8LL)) - v35) > 0 )
        break;
      v34 = i;
    }
    if ( v34 )
    {
      *a3 = *v34;
      *v34 = a3;
    }
    else
    {
      *a3 = v32;
      *(_QWORD *)(v7 + 152) = a3;
    }
  }
  else
  {
    *(_QWORD *)(v7 + 152) = a3;
LABEL_57:
    *(_QWORD *)(v7 + 160) = a3;
  }
  if ( !*(_BYTE *)(v7 + 584) )
  {
    *(_BYTE *)(v7 + 584) = 1;
    _InterlockedIncrement((volatile signed __int32 *)v7);
    NdisQueueIoWorkItem(*(NDIS_HANDLE *)(v7 + 608), CallProcessRxNBLs, (PVOID)v7);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 168), *(_BYTE *)(v7 + 176));
LABEL_32:
  if ( v12 )
  {
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 624));
    _InterlockedIncrement(&dword_14000B404);
  }
  if ( v7
    && *(_DWORD *)(v7 + 48) == 1129337936
    && _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(v7 + 8))(v7);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140016db0  mov     r11, rsp
0x140016db3  push    rsi
0x140016db4  sub     rsp, 130h
0x140016dbb  mov     rax, cs:__security_cookie
0x140016dc2  xor     rax, rsp
0x140016dc5  mov     [rsp+138h+var_48], rax
0x140016dcd  mov     [r11+20h], rbx
0x140016dd1  mov     [r11-10h], rbp
0x140016dd5  mov     [r11-18h], rdi
0x140016dd9  mov     rdi, [rcx]
0x140016ddc  mov     [r11-20h], r12
0x140016de0  mov     r12, [rdx+8]
0x140016de4  mov     [r11-30h], r14
0x140016de8  mov     rax, [rdi+40h]
0x140016dec  mov     [r11-38h], r15
0x140016df0  mov     r15, r8
0x140016df3  movzx   ebx, word ptr [r12]
0x140016df8  xor     r8d, r8d
0x140016dfb  mov     [rsp+138h+var_108], rax
0x140016e00  mov     ebp, r8d
0x140016e03  mov     dword ptr [rsp+138h+var_100], r8d
0x140016e08  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e0f  lea     r14, WPP_GLOBAL_Control
0x140016e16  cmp     rcx, r14
0x140016e19  jnz     loc_140016FBC
0x140016e1f  mov     [rsp+138h+var_28], r13
0x140016e27  cmp     bx, 2
0x140016e2b  jnz     loc_140016FEE
0x140016e31  lock inc cs:dword_14000B400
0x140016e38  mov     rcx, [r15+8]; NetBuffer
0x140016e3c  mov     r9d, 1; AlignMultiple
0x140016e42  mov     [rsp+138h+AlignOffset], r8d; AlignOffset
0x140016e47  xor     r8d, r8d; Storage
0x140016e4a  mov     r13d, [rcx+18h]
0x140016e4e  mov     edx, r13d; BytesNeeded
0x140016e51  call    cs:__imp_NdisGetDataBuffer
0x140016e58  nop     dword ptr [rax+rax+00h]
0x140016e5d  mov     [rsp+138h+var_F8], rax
0x140016e62  mov     r10, rax
0x140016e65  test    rax, rax
0x140016e68  jz      loc_1400173C2
0x140016e6e  lea     r9, [rsp+138h+var_100]
0x140016e73  mov     edx, r13d
0x140016e76  mov     rcx, rax
0x140016e79  call    ProcessIpv4AddressFromPacket
0x140016e7e  mov     esi, eax
0x140016e80  test    eax, eax
0x140016e82  js      loc_1400175D0
0x140016e88  mov     r8d, dword ptr [rsp+138h+var_100]
0x140016e8d  lea     rdx, [r8+0Ch]
0x140016e91  cmp     r13, rdx
0x140016e94  jb      loc_1400175D0
0x140016e9a  add     r10, r8
0x140016e9d  mov     ebx, r13d
0x140016ea0  mov     [rsp+138h+var_100], r10
0x140016ea5  movzx   edx, byte ptr [r10]
0x140016ea9  movsx   r9, byte ptr [r10+1]
0x140016eae  mov     eax, edx
0x140016eb0  and     eax, 10h
0x140016eb3  mov     rcx, r9
0x140016eb6  sar     rcx, 3Fh
0x140016eba  or      eax, 20h
0x140016ebd  shr     eax, 2
0x140016ec0  and     ecx, 4
0x140016ec3  add     ecx, eax
0x140016ec5  sub     ebx, ecx
0x140016ec7  sub     ebx, r8d
0x140016eca  lea     r14d, [rcx+r8]
0x140016ece  cmp     r13d, r14d
0x140016ed1  jb      loc_140017559
0x140016ed7  movzx   eax, word ptr [r10+4]
0x140016edc  ror     ax, 8
0x140016ee0  movzx   eax, ax
0x140016ee3  cmp     eax, ebx
0x140016ee5  jg      loc_140017559
0x140016eeb  movzx   eax, dl
0x140016eee  and     al, 6Fh
0x140016ef0  cmp     al, 20h ; ' '
0x140016ef2  jnz     loc_140017559
0x140016ef8  test    dl, dl
0x140016efa  js      loc_140017559
0x140016f00  movzx   eax, r9b
0x140016f04  and     al, 7
0x140016f06  cmp     al, 1
0x140016f08  jnz     loc_140017559
0x140016f0e  test    r9b, 78h
0x140016f12  jnz     loc_140017559
0x140016f18  mov     eax, 0B88h
0x140016f1d  cmp     [r10+2], ax
0x140016f22  jnz     loc_140017559
0x140016f28  movzx   eax, word ptr [r10+6]
0x140016f2d  ror     ax, 8
0x140016f31  cmp     cs:PptpClientSide, bpl
0x140016f38  movzx   ebx, ax
0x140016f3b  jnz     loc_14001710B
0x140016f41  lea     rcx, [rdi+8]; SpinLock
0x140016f45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016f4c  nop     dword ptr [rax+rax+00h]
0x140016f51  mov     [rdi+10h], al
0x140016f54  mov     eax, cs:PptpBaseCallId
0x140016f5a  cmp     rbx, rax
0x140016f5d  jnb     loc_1400170BB
0x140016f63  movzx   edx, byte ptr [rdi+10h]; NewIrql
0x140016f67  lea     rcx, [rdi+8]; SpinLock
0x140016f6b  call    cs:__imp_KeReleaseSpinLock
0x140016f72  nop     dword ptr [rax+rax+00h]
0x140016f77  xor     ebp, ebp
0x140016f79  mov     esi, 0C0000001h
0x140016f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f85  lea     rdi, WPP_GLOBAL_Control
0x140016f8c  cmp     rcx, rdi
0x140016f8f  jz      short loc_140016FB3
0x140016f91  mov     eax, [rcx+2Ch]
0x140016f94  test    al, 10h
0x140016f96  jz      short loc_140016FB3
0x140016f98  cmp     byte ptr [rcx+29h], 1
0x140016f9c  jb      short loc_140016FB3
0x140016f9e  mov     rcx, [rcx+18h]
0x140016fa2  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140016fa9  mov     edx, 53h ; 'S'
0x140016fae  call    WPP_SF_
0x140016fb3  lock inc cs:dword_14000B420
0x140016fba  jmp     short loc_140017017
0x140016fbc  mov     eax, [rcx+2Ch]
0x140016fbf  test    al, 8
0x140016fc1  jz      loc_140016E1F
0x140016fc7  cmp     byte ptr [rcx+29h], 2
0x140016fcb  jb      loc_140016E1F
0x140016fd1  mov     rcx, [rcx+18h]
0x140016fd5  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140016fdc  mov     edx, 4Eh ; 'N'
0x140016fe1  call    WPP_SF_
0x140016fe6  xor     r8d, r8d
0x140016fe9  jmp     loc_140016E1F
0x140016fee  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ff5  cmp     rcx, r14
0x140016ff8  jz      short loc_14001700B
0x140016ffa  mov     eax, [rcx+2Ch]
0x140016ffd  test    al, 10h
0x140016fff  jz      short loc_14001700B
0x140017001  cmp     byte ptr [rcx+29h], 1
0x140017005  jnb     loc_1400173A8
0x14001700b  mov     esi, 0C0000001h
0x140017010  lea     rdi, WPP_GLOBAL_Control
0x140017017  mov     r12, [rsp+138h+var_108]
0x14001701c  mov     rdx, r15
0x14001701f  mov     rcx, r12
0x140017022  call    ReceiveDataComplete
0x140017027  mov     r15, [rsp+138h+var_38]
0x14001702f  mov     r14, [rsp+138h+var_30]
0x140017037  mov     r13, [rsp+138h+var_28]
0x14001703f  mov     r12, [rsp+138h+var_20]
0x140017047  mov     rbx, [rsp+138h+arg_18]
0x14001704f  test    esi, esi
0x140017051  jnz     loc_14001760A
0x140017057  test    rbp, rbp
0x14001705a  jz      short loc_140017078
0x14001705c  cmp     dword ptr [rbp+30h], 43505450h
0x140017063  jnz     short loc_140017078
0x140017065  mov     eax, 0FFFFFFFFh
0x14001706a  lock xadd [rbp+0], eax
0x14001706f  cmp     eax, 1
0x140017072  jz      loc_140017116
0x140017078  mov     rcx, cs:WPP_GLOBAL_Control
0x14001707f  mov     rbp, [rsp+138h+var_10]
0x140017087  cmp     rcx, rdi
0x14001708a  mov     rdi, [rsp+138h+var_18]
0x140017092  jz      short loc_14001709F
0x140017094  mov     eax, [rcx+2Ch]
0x140017097  test    al, 8
0x140017099  jnz     loc_140017622
0x14001709f  mov     eax, esi
0x1400170a1  mov     rcx, [rsp+138h+var_48]
0x1400170a9  xor     rcx, rsp; StackCookie
0x1400170ac  call    __security_check_cookie
0x1400170b1  add     rsp, 130h
0x1400170b8  pop     rsi
0x1400170b9  retn
0x1400170bb  mov     eax, cs:PptpMaxCallId
0x1400170c1  cmp     rbx, rax
0x1400170c4  jnb     loc_140016F63
0x1400170ca  cmp     cs:PptpCallIdMaskSet, bpl
0x1400170d1  jz      short loc_140017127
0x1400170d3  mov     ebp, cs:PptpCallIdMask
0x1400170d9  mov     eax, cs:PptpWanEndpoints
0x1400170df  and     rbp, rbx
0x1400170e2  cmp     rbp, rax
0x1400170e5  jnb     loc_140016F63
0x1400170eb  mov     rax, [rdi+20h]
0x1400170ef  mov     rbp, [rax+rbp*8]
0x1400170f3  test    rbp, rbp
0x1400170f6  jz      loc_140016F63
0x1400170fc  cmp     [rbp+0D0h], rbx
0x140017103  jnz     loc_140016F63
0x140017109  jmp     short loc_140017144
0x14001710b  and     ebx, 3FFFh
0x140017111  jmp     loc_140016F41
0x140017116  mov     rax, [rbp+8]
0x14001711a  mov     rcx, rbp
0x14001711d  call    _guard_dispatch_icall
0x140017122  jmp     loc_140017078
0x140017127  lfence
0x14001712a  mov     eax, cs:PptpBaseCallId
0x140017130  sub     rbx, rax
0x140017133  mov     rax, [rdi+20h]
0x140017137  mov     rbp, [rax+rbx*8]
0x14001713b  test    rbp, rbp
0x14001713e  jz      loc_140016F63
0x140017144  mov     rbx, rbp
0x140017147  cmp     dword ptr [rbx+30h], 43505450h
0x14001714e  jnz     loc_140016F63
0x140017154  lock inc dword ptr [rbx]
0x140017157  movzx   edx, byte ptr [rdi+10h]; NewIrql
0x14001715b  lea     rcx, [rdi+8]; SpinLock
0x14001715f  call    cs:__imp_KeReleaseSpinLock
0x140017166  nop     dword ptr [rax+rax+00h]
0x14001716b  cmp     dword ptr [rbx+30h], 43505450h
0x140017172  jnz     loc_140016F79
0x140017178  lock inc dword ptr [rbx+268h]
0x14001717f  cmp     cs:PptpValidateAddress, 0
0x140017186  jnz     loc_1400172C3
0x14001718c  mov     rcx, [r15+10h]
0x140017190  mov     rdx, [rsp+138h+var_F8]
0x140017195  mov     r12, [rsp+138h+var_108]
0x14001719a  movzx   eax, word ptr [rcx+0Ah]
0x14001719e  mov     [rax+rcx+10h], rdx
0x1400171a3  mov     rdx, [rsp+138h+var_100]
0x1400171a8  mov     [rax+rcx+18h], rdx
0x1400171ad  mov     [rax+rcx+20h], r12
0x1400171b2  mov     [rax+rcx+28h], r13d
0x1400171b7  mov     rcx, [r15+10h]
0x1400171bb  movzx   eax, word ptr [rcx+0Ah]
0x1400171bf  mov     r14, [rax+rcx+18h]
0x1400171c4  test    byte ptr [r14], 10h
0x1400171c8  jz      loc_140017516
0x1400171ce  lea     rcx, [rbx+60h]; SpinLock
0x1400171d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400171d9  nop     dword ptr [rax+rax+00h]
0x1400171de  mov     [rbx+68h], al
0x1400171e1  movzx   ecx, word ptr [r14+6]
0x1400171e6  ror     cx, 8
0x1400171ea  cmp     cx, [rbx+140h]
0x1400171f1  jnz     loc_14001730C
0x1400171f7  cmp     dword ptr [rbx+70h], 9
0x1400171fb  jnz     loc_140017312
0x140017201  mov     rcx, [rbx+50h]
0x140017205  test    rcx, rcx
0x140017208  jz      loc_14001730C
0x14001720e  cmp     dword ptr [rcx+30h], 7
0x140017212  jz      loc_14001730C
0x140017218  lock inc dword ptr [rbx+20h]
0x14001721c  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x140017220  lea     rcx, [rbx+60h]; SpinLock
0x140017224  inc     dword ptr [rbx+0B8h]
0x14001722a  call    cs:__imp_KeReleaseSpinLock
0x140017231  nop     dword ptr [rax+rax+00h]
0x140017236  lea     rcx, [rbx+0A8h]; SpinLock
0x14001723d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017244  nop     dword ptr [rax+rax+00h]
0x140017249  mov     r11, [rbx+98h]
0x140017250  mov     [rbx+0B0h], al
0x140017256  test    r11, r11
0x140017259  jnz     loc_140017348
0x14001725f  mov     [rbx+98h], r15
0x140017266  mov     [rbx+0A0h], r15
0x14001726d  cmp     byte ptr [rbx+248h], 0
0x140017274  jnz     short loc_14001729D
0x140017276  mov     byte ptr [rbx+248h], 1
0x14001727d  lock inc dword ptr [rbx]
0x140017280  mov     rcx, [rbx+260h]; NdisIoWorkItemHandle
0x140017287  lea     rdx, CallProcessRxNBLs; Routine
0x14001728e  mov     r8, rbx; WorkItemContext
0x140017291  call    cs:__imp_NdisQueueIoWorkItem
0x140017298  nop     dword ptr [rax+rax+00h]
0x14001729d  movzx   edx, byte ptr [rbx+0B0h]; NewIrql
0x1400172a4  lea     rcx, [rbx+0A8h]; SpinLock
0x1400172ab  call    cs:__imp_KeReleaseSpinLock
0x1400172b2  nop     dword ptr [rax+rax+00h]
0x1400172b7  lea     rdi, WPP_GLOBAL_Control
0x1400172be  jmp     loc_140017027
0x1400172c3  movzx   eax, word ptr [r12]
0x1400172c8  cmp     ax, [rbx+118h]
0x1400172cf  jnz     loc_140017429
0x1400172d5  cmp     ax, 2
0x1400172d9  jnz     loc_140017401
0x1400172df  lea     rdx, [rbx+11Ch]; Source2
0x1400172e6  mov     r8d, 4; Length
0x1400172ec  lea     rcx, [r12+4]; Source1
0x1400172f1  call    cs:__imp_RtlCompareMemory
0x1400172f8  nop     dword ptr [rax+rax+00h]
0x1400172fd  cmp     rax, 4
0x140017301  jz      loc_14001718C
0x140017307  jmp     loc_140017429
0x14001730c  cmp     dword ptr [rbx+70h], 9
0x140017310  jz      short loc_14001738E
0x140017312  movzx   edx, al; NewIrql
0x140017315  lea     rcx, [rbx+60h]; SpinLock
0x140017319  call    cs:__imp_KeReleaseSpinLock
0x140017320  nop     dword ptr [rax+rax+00h]
0x140017325  mov     eax, 284h
  ... truncated ...
```
