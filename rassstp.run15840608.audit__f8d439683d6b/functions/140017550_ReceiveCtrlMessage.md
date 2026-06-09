# ReceiveCtrlMessage

- ea: `0x140017550`
- end: `0x14001804e`
- name: `ReceiveCtrlMessage`
- size: `2814`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400154e0`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140002f88`
- `0x1400053ec`
- `0x140005454`
- `0x140005df2`
- `0x140005e10`
- `0x140006240`
- `0x140015d70`
- `0x1400161b0`
- `0x140016414`
- `0x1400165a0`
- `0x140016734`
- `0x1400169a4`
- `0x140016cf0`
- `0x140016e84`
- `0x140016f4c`
- `0x140017204`
- `0x140017550`
- `0x140018054`
- `0x1400182dc`
- `0x140018698`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400176b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400176b7`
- `ntoskrnl!RtlCompareMemory` at `0x140017bd2`
- `ntoskrnl!RtlCompareMemory` at `0x140017c38`
- `ntoskrnl!RtlCompareMemory` at `0x140017cb3`
- `ntoskrnl!RtlCompareMemory` at `0x140017bd2`
- `ntoskrnl!RtlCompareMemory` at `0x140017c38`
- `ntoskrnl!RtlCompareMemory` at `0x140017cb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fda`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fda`
- `ntoskrnl!KeLowerIrql` at `0x140017f4e`
- `ntoskrnl!KeLowerIrql` at `0x140017f4e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017938`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017f2a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017938`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017f2a`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ReceiveCtrlMessage(__int64 a1, int a2, unsigned __int16 a3, int a4)
{
  char v7; // si
  __int64 v8; // r8
  __int64 v9; // rdi
  KIRQL v10; // r15
  __int64 v11; // rcx
  __int16 v12; // r14
  int v13; // r8d
  __m128i si128; // xmm0
  __int64 Timer_high; // rdx
  unsigned int v16; // ecx
  __int64 v17; // r8
  int v18; // r9d
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  _DWORD *v25; // rax
  unsigned __int8 v26; // cl
  __int128 v27; // xmm0
  char v28; // al
  __int128 v29; // xmm1
  int v30; // ecx
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rdx
  __int16 v33; // di
  __int64 v34; // r8
  int v35; // eax
  __int128 v36; // xmm1
  bool v37; // zf
  char valid; // di
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  PVOID v41; // rax
  int v42; // r8d
  PDEVICE_OBJECT *result; // rax
  char v44; // [rsp+50h] [rbp-B0h] BYREF
  char v45; // [rsp+51h] [rbp-AFh] BYREF
  _BYTE v46[2]; // [rsp+52h] [rbp-AEh] BYREF
  __int16 v47; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v48[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v49; // [rsp+5Ch] [rbp-A4h] BYREF
  int v50; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v51[151]; // [rsp+64h] [rbp-9Ch] BYREF
  __m128i v52; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v53; // [rsp+2D0h] [rbp+1D0h]
  _BYTE Src[4096]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v47 = 0;
  v48[0] = 0;
  v50 = 0;
  memset(v51, 0, 596);
  v49 = 0;
  v52.m128i_i64[0] = 0;
  v52.m128i_i16[4] = 0;
  v46[0] = 0;
  v45 = 0;
  v44 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  v7 = ParseSstpControlMessage(
         a2,
         a3,
         (unsigned int)Src,
         a4,
         (__int64)&v47,
         (__int64)v48,
         (__int64)&v50,
         (__int64)&v49,
         (__int64)v46,
         (__int64)&v44);
  v9 = v49;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF__guid_Lq(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v8, a1 + 364, v49, *(_QWORD *)(a1 + 136));
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
  if ( LOBYTE(v51[91]) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    }
    *(_BYTE *)(a1 + 322) = 1;
  }
  v11 = *(unsigned int *)(a1 + 24);
  *(_BYTE *)(a1 + 320) = 1;
  if ( (((_DWORD)v11 - 1) & 0xFFFFFFF7) == 0 )
    goto LABEL_179;
  v12 = v47;
  if ( (unsigned __int16)v47 > 0xFFFu || (unsigned int)(v9 - 1) > 8 || !v7 )
  {
    v13 = 7;
    goto LABEL_177;
  }
  GetAcceptedMessageTypesForCurrentState(v11, &v52, &v45);
  if ( v45 )
    goto LABEL_179;
  if ( !v52.m128i_i8[v9] )
  {
    v13 = 5;
LABEL_177:
    LODWORD(Timer_high) = 2;
    goto LABEL_178;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Timer_high = si128.m128i_i64[0];
  v53 = si128.m128i_i32[0];
  v52 = si128;
  switch ( (_DWORD)v9 )
  {
    case 1:
      v52.m128i_i32[1] = 0;
      break;
    case 2:
LABEL_31:
      v53 = *(_BYTE *)(a1 + 176) == 0 ? 2 : 0;
      goto LABEL_32;
    case 3:
      v52.m128i_i32[2] = 0;
      break;
    case 4:
      v52.m128i_i32[3] = 1;
      break;
    default:
      if ( (unsigned int)(v9 - 5) <= 1 )
        v52.m128i_i32[2] = 1;
      break;
  }
  if ( si128.m128i_i32[0] == 1 )
    goto LABEL_31;
LABEL_32:
  if ( v52.m128i_i32[3] == 1 )
    v52.m128i_i32[3] = *(_BYTE *)(a1 + 176) == 0 ? 2 : 0;
  LOBYTE(Timer_high) = v46[0];
  v16 = 1;
  v17 = 1;
  do
  {
    v18 = v51[30 * v17];
    v51[30 * v17 - 1] = v16;
    if ( v18 == 3 )
    {
      if ( v52.m128i_i32[v17] == 2 )
      {
        v51[30 * v17 + 28] = 9;
LABEL_41:
        LOBYTE(v51[30 * v17 + 27]) = v16;
        LOBYTE(Timer_high) = 1;
        LOBYTE(v51[30 * v17 + 1]) = 1;
        v51[30 * v17 - 1] = 2;
        goto LABEL_43;
      }
    }
    else if ( v18 == 4 && !v52.m128i_i32[v17] )
    {
      v51[30 * v17 + 28] = 10;
      goto LABEL_41;
    }
    LOBYTE(v51[30 * v17 + 1]) = 0;
LABEL_43:
    ++v16;
    ++v17;
  }
  while ( v16 < 5 );
  v19 = *(_DWORD *)(a1 + 24);
  if ( *(_BYTE *)(a1 + 326) )
  {
    v20 = v19 - 2;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
        goto LABEL_47;
LABEL_63:
      if ( (_DWORD)v9 == 5 )
      {
        *(_BYTE *)(a1 + 321) = 1;
LABEL_54:
        LOBYTE(Timer_high) = 1;
LABEL_55:
        MoveToAbortState2(a1, Timer_high, v17, 0, 0, 0);
        goto LABEL_179;
      }
      if ( (_DWORD)v9 != 6 )
        goto LABEL_179;
      *(_BYTE *)(a1 + 321) = 1;
LABEL_175:
      MoveToDisconnectState2(a1, Timer_high, v17);
      goto LABEL_179;
    }
    if ( (_DWORD)v9 == 2 )
    {
      if ( !v44 && !(_BYTE)Timer_high )
      {
        v26 = *(_BYTE *)(a1 + 176);
        if ( v26 )
        {
          Timer_high = 4;
          if ( v51[120] == 4 )
          {
            v13 = 10;
            goto LABEL_178;
          }
          if ( v51[120] == 3 && (HIBYTE(v51[122]) & v26) == 0 )
          {
            v13 = 4;
            goto LABEL_178;
          }
LABEL_77:
          v27 = *(_OWORD *)&v51[123];
          v28 = v26 & HIBYTE(v51[122]);
          v29 = *(_OWORD *)&v51[127];
          *(_BYTE *)(a1 + 176) = v26 & HIBYTE(v51[122]);
          *(_OWORD *)(a1 + 144) = v27;
          *(_OWORD *)(a1 + 160) = v29;
          if ( (v28 & 2) != 0 )
          {
            *(_BYTE *)(a1 + 176) = 2;
          }
          else if ( (v28 & 1) != 0 )
          {
            *(_BYTE *)(a1 + 176) = 1;
          }
          MoveToConnectAckReceivedState(a1, Timer_high, v17);
          goto LABEL_179;
        }
        if ( v51[120] != 4 )
        {
          if ( v51[120] == 3 )
          {
            v13 = 9;
            LODWORD(Timer_high) = 4;
LABEL_178:
            MoveToAbortState1(a1, Timer_high, v13, 0, 0);
            goto LABEL_179;
          }
          goto LABEL_77;
        }
LABEL_140:
        LOBYTE(Timer_high) = v10;
        MoveToCallConnectedState(a1, Timer_high, v17);
        goto LABEL_179;
      }
LABEL_156:
      v13 = 9;
LABEL_157:
      LODWORD(Timer_high) = 2;
      goto LABEL_178;
    }
    if ( (_DWORD)v9 != 3 )
      goto LABEL_63;
    if ( ++*(_DWORD *)(a1 + 316) <= 3u )
    {
      if ( (int)MoveToConnectRequestSentState(a1, Timer_high, v17) >= 0 )
        goto LABEL_179;
      goto LABEL_170;
    }
LABEL_168:
    v13 = 6;
    goto LABEL_157;
  }
  v30 = v19 - 10;
  if ( !v30 )
  {
    if ( (_DWORD)v9 != 1 )
      goto LABEL_63;
    if ( v51[29] == 1 && !LOBYTE(v51[31]) && v51[30] == 3 && v51[32] != *(_DWORD *)(a1 + 128) )
    {
      LOBYTE(v51[31]) = 1;
      LOBYTE(Timer_high) = 1;
      LOBYTE(v51[57]) = 1;
      v51[58] = 4;
    }
    if ( v44 )
    {
      LOBYTE(v51[61]) = 1;
      LOBYTE(Timer_high) = 1;
      LOBYTE(v51[87]) = 2;
      v51[88] = 11;
      v51[59] = 2;
    }
    if ( !(_BYTE)Timer_high )
    {
      MoveToCallConnectPendingState(a1, Timer_high, v17);
      goto LABEL_179;
    }
    if ( ++*(_DWORD *)(a1 + 316) > 3u )
      goto LABEL_168;
    v41 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
    if ( !v41 )
      goto LABEL_170;
    GenerateSstpConnectNak((int)&v50, (_DWORD)v41 + 18, v42, (_DWORD)v41 + 16, Src, v12, v48[0]);
LABEL_61:
    SendControlFrame(a1);
    goto LABEL_179;
  }
  v21 = v30 - 1;
  if ( !v21 )
  {
    if ( (_DWORD)v9 != 4 )
      goto LABEL_63;
    if ( v44 || (_BYTE)Timer_high )
      goto LABEL_156;
    if ( *(_BYTE *)(a1 + 324) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
      }
      v13 = 5;
      goto LABEL_177;
    }
    if ( v51[90] == 4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
      }
      goto LABEL_140;
    }
    if ( (*(_BYTE *)(a1 + 176) & HIBYTE(v51[92])) == 0 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v32 = 97;
        goto LABEL_154;
      }
LABEL_155:
      v13 = 4;
      LODWORD(Timer_high) = 3;
      goto LABEL_178;
    }
    v33 = 32;
    *(_BYTE *)(a1 + 176) &= HIBYTE(v51[92]);
    if ( RtlCompareMemory((const void *)(a1 + 144), &v51[93], 0x20u) != 32 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_155;
      }
      v32 = 98;
      goto LABEL_154;
    }
    if ( HIBYTE(v51[92]) == 1 )
    {
      v33 = 20;
      if ( RtlCompareMemory((const void *)(a1 + 177), &v51[101], 0x14u) != 20 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_155;
        }
        v32 = 99;
        goto LABEL_154;
      }
      v35 = v51[113];
      *(_OWORD *)(a1 + 327) = *(_OWORD *)&v51[109];
      *(_DWORD *)(a1 + 343) = v35;
LABEL_129:
      v37 = *(_BYTE *)(a1 + 323) == 0;
      *(_WORD *)(a1 + 360) = v33;
      if ( v37 )
      {
        *(_BYTE *)(a1 + 324) = 1;
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_179;
        }
        v40 = 104;
      }
      else
      {
        LOBYTE(v34) = v10;
        valid = IsValidCryptoBinding(a1, Src, v34);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Timer_high & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v17, valid == 0);
          }
        }
        if ( !valid )
          goto LABEL_155;
        if ( *(_DWORD *)(a1 + 24) == 11 )
          goto LABEL_140;
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_179;
        }
        v40 = 105;
      }
      WPP_SF__guid_(v39->AttachedDevice, v40, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
      goto LABEL_179;
    }
    if ( HIBYTE(v51[92]) == 2 )
    {
      if ( RtlCompareMemory((const void *)(a1 + 197), &v51[101], 0x20u) == 32 )
      {
        v36 = *(_OWORD *)&v51[113];
        *(_OWORD *)(a1 + 327) = *(_OWORD *)&v51[109];
        *(_OWORD *)(a1 + 343) = v36;
        goto LABEL_129;
      }
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_155;
      }
      v32 = 100;
    }
    else
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_155;
      }
      v32 = 101;
    }
LABEL_154:
    WPP_SF__guid_(v31->AttachedDevice, v32, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    goto LABEL_155;
  }
LABEL_47:
  v22 = v21 - 1;
  if ( !v22 )
  {
    if ( (_DWORD)v9 != 8 )
    {
      if ( (_DWORD)v9 != 9 )
        goto LABEL_63;
      goto LABEL_179;
    }
    v25 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
    if ( !v25 )
      goto LABEL_179;
    v25[4] = 17825800;
    *((_WORD *)v25 + 11) = 2304;
    *((_WORD *)v25 + 12) = 0;
    *((_WORD *)v25 + 10) = __ROR2__(*((_WORD *)v25 + 8), 8);
    goto LABEL_61;
  }
  v23 = v22 - 1;
  if ( v23 )
  {
    v24 = v23 - 2;
    if ( v24 )
    {
      if ( v24 != 1 || (_DWORD)v9 != 7 )
        goto LABEL_179;
    }
    else if ( (_DWORD)v9 != 7 )
    {
      if ( (_DWORD)v9 != 6 )
      {
        if ( (_DWORD)v9 == 5 )
          goto LABEL_54;
        goto LABEL_179;
      }
      goto LABEL_175;
    }
LABEL_170:
    MoveToCallDisconnectedState(a1, 0, 0);
    KeLowerIrql(v10);
  }
  else
  {
    if ( (_DWORD)v9 == 5 )
    {
      LODWORD(Timer_high) = 0;
      goto LABEL_55;
    }
LABEL_179:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v10);
  }
  DereferenceRefCount(a1 + 32);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)(HIDWORD(WPP_GLOBAL_Control->Timer) & 0x84);
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      return (PDEVICE_OBJECT *)WPP_SF_(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 106,
                                 WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140017550  mov     [rsp-8+arg_10], rbx
0x140017555  push    rbp
0x140017556  push    rsi
0x140017557  push    rdi
0x140017558  push    r12
0x14001755a  push    r13
0x14001755c  push    r14
0x14001755e  push    r15
0x140017560  lea     rbp, [rsp-11F0h]
0x140017568  mov     eax, 12F0h
0x14001756d  call    __chkstk_0
0x140017572  sub     rsp, rax
0x140017575  mov     rax, cs:__security_cookie
0x14001757c  xor     rax, rsp
0x14001757f  mov     [rbp+1220h+var_40], rax
0x140017586  xor     r14d, r14d
0x140017589  movzx   edi, r8w
0x14001758d  mov     rsi, rdx
0x140017590  mov     [rsp+1320h+var_12CC], r14w
0x140017596  mov     rbx, rcx
0x140017599  mov     [rsp+1320h+var_12C8], r14w
0x14001759f  xor     edx, edx; Val
0x1400175a1  mov     [rsp+1320h+var_12C0], r14d
0x1400175a6  lea     r8d, [r14+74h]; Size
0x1400175aa  lea     rcx, [rsp+1320h+var_12BC]; void *
0x1400175af  call    memset
0x1400175b4  xor     edx, edx; Val
0x1400175b6  lea     rcx, [rbp+1220h+var_1248]; void *
0x1400175ba  mov     r8d, 1E0h; Size
0x1400175c0  call    memset
0x1400175c5  xor     eax, eax
0x1400175c7  mov     [rsp+1320h+var_12C4], r14d
0x1400175cc  mov     qword ptr [rbp+1220h+var_1060], rax
0x1400175d3  mov     word ptr [rbp+1220h+var_1060+8], ax
0x1400175da  mov     [rsp+1320h+var_12CE], r14b
0x1400175df  mov     [rsp+1320h+var_12CF], r14b
0x1400175e4  mov     [rsp+1320h+var_12D0], r14b
0x1400175e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175f0  lea     r15, WPP_GLOBAL_Control
0x1400175f7  cmp     rcx, r15
0x1400175fa  jz      short loc_14001761C
0x1400175fc  mov     eax, [rcx+2Ch]
0x1400175ff  and     eax, 84h
0x140017604  cmp     al, 84h
0x140017606  jnz     short loc_14001761C
0x140017608  mov     rcx, [rcx+18h]
0x14001760c  lea     edx, [r14+5Ch]
0x140017610  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140017617  call    WPP_SF_
0x14001761c  lea     rax, [rsp+1320h+var_12D0]
0x140017621  movzx   edx, di
0x140017624  mov     [rsp+1320h+var_12D8], rax
0x140017629  lea     r8, [rbp+1220h+var_1040]
0x140017630  lea     rax, [rsp+1320h+var_12CE]
0x140017635  mov     rcx, rsi
0x140017638  mov     [rsp+1320h+var_12E0], rax
0x14001763d  lea     rax, [rsp+1320h+var_12C4]
0x140017642  mov     [rsp+1320h+var_12E8], rax
0x140017647  lea     rax, [rsp+1320h+var_12C0]
0x14001764c  mov     qword ptr [rsp+1320h+var_12F0], rax
0x140017651  lea     rax, [rsp+1320h+var_12C8]
0x140017656  mov     qword ptr [rsp+1320h+var_12F8], rax
0x14001765b  lea     rax, [rsp+1320h+var_12CC]
0x140017660  mov     [rsp+1320h+Src], rax
0x140017665  call    ParseSstpControlMessage
0x14001766a  mov     sil, al
0x14001766d  mov     rdx, cs:WPP_GLOBAL_Control
0x140017674  movsxd  rdi, [rsp+1320h+var_12C4]
0x140017679  cmp     rdx, r15
0x14001767c  jz      short loc_1400176AC
0x14001767e  mov     ecx, [rdx+2Ch]
0x140017681  test    cl, 4
0x140017684  jz      short loc_1400176AC
0x140017686  cmp     byte ptr [rdx+29h], 3
0x14001768a  jb      short loc_1400176AC
0x14001768c  mov     rax, [rbx+88h]
0x140017693  lea     r9, [rbx+16Ch]
0x14001769a  mov     rcx, [rdx+18h]
0x14001769e  mov     qword ptr [rsp+1320h+var_12F8], rax
0x1400176a3  mov     dword ptr [rsp+1320h+Src], edi
0x1400176a7  call    WPP_SF__guid_Lq
0x1400176ac  lock inc dword ptr [rbx+20h]
0x1400176b0  lea     r12, [rbx+10h]
0x1400176b4  mov     rcx, r12; SpinLock
0x1400176b7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400176be  nop     dword ptr [rax+rax+00h]
0x1400176c3  mov     r15b, al
0x1400176c6  cmp     [rbp+1220h+var_1150], r14b
0x1400176cd  jz      short loc_14001770E
0x1400176cf  mov     r9, cs:WPP_GLOBAL_Control
0x1400176d6  lea     rax, WPP_GLOBAL_Control
0x1400176dd  cmp     r9, rax
0x1400176e0  jz      short loc_140017707
0x1400176e2  mov     ecx, [r9+2Ch]
0x1400176e6  test    cl, 4
0x1400176e9  jz      short loc_140017707
0x1400176eb  cmp     byte ptr [r9+29h], 2
0x1400176f0  jb      short loc_140017707
0x1400176f2  mov     rcx, [r9+18h]
0x1400176f6  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400176fd  mov     edx, 5Eh ; '^'
0x140017702  call    WPP_SF_
0x140017707  mov     byte ptr [rbx+142h], 1
0x14001770e  mov     ecx, [rbx+18h]
0x140017711  mov     byte ptr [rbx+140h], 1
0x140017718  lea     eax, [rcx-1]
0x14001771b  test    eax, 0FFFFFFF7h
0x140017720  jz      loc_140017FD4
0x140017726  movzx   r14d, [rsp+1320h+var_12CC]
0x14001772c  mov     eax, 0FFFh
0x140017731  cmp     r14w, ax
0x140017735  ja      loc_140017FB5
0x14001773b  lea     eax, [rdi-1]
0x14001773e  cmp     eax, 8
0x140017741  ja      loc_140017FB5
0x140017747  test    sil, sil
0x14001774a  jz      loc_140017FB5
0x140017750  lea     r8, [rsp+1320h+var_12CF]
0x140017755  lea     rdx, [rbp+1220h+var_1060]
0x14001775c  call    GetAcceptedMessageTypesForCurrentState
0x140017761  cmp     [rsp+1320h+var_12CF], 0
0x140017766  jnz     loc_140017FD4
0x14001776c  cmp     byte ptr [rbp+rdi+1220h+var_1060], 0
0x140017774  jnz     short loc_140017781
0x140017776  mov     r8d, 5
0x14001777c  jmp     loc_140017FBB
0x140017781  movdqa  xmm0, cs:__xmm@00000002000000020000000200000002
0x140017789  mov     ecx, edi
0x14001778b  movq    rdx, xmm0
0x140017790  mov     [rbp+1220h+var_1050], edx
0x140017796  movups  [rbp+1220h+var_1060], xmm0
0x14001779d  sub     ecx, 1
0x1400177a0  jz      short loc_1400177DF
0x1400177a2  sub     ecx, 1
0x1400177a5  jz      short loc_1400177EE
0x1400177a7  sub     ecx, 1
0x1400177aa  jz      short loc_1400177D3
0x1400177ac  sub     ecx, 1
0x1400177af  jz      short loc_1400177C7
0x1400177b1  sub     ecx, 1
0x1400177b4  jz      short loc_1400177BB
0x1400177b6  cmp     ecx, 1
0x1400177b9  jnz     short loc_1400177E9
0x1400177bb  mov     dword ptr [rbp+1220h+var_1060+8], 1
0x1400177c5  jmp     short loc_1400177E9
0x1400177c7  mov     dword ptr [rbp+1220h+var_1060+0Ch], 1
0x1400177d1  jmp     short loc_1400177E9
0x1400177d3  mov     dword ptr [rbp+1220h+var_1060+8], 0
0x1400177dd  jmp     short loc_1400177E9
0x1400177df  mov     dword ptr [rbp+1220h+var_1060+4], 0
0x1400177e9  cmp     edx, 1
0x1400177ec  jnz     short loc_14001780B
0x1400177ee  mov     al, [rbx+0B0h]
0x1400177f4  mov     r10d, 2
0x1400177fa  neg     al
0x1400177fc  sbb     ecx, ecx
0x1400177fe  not     ecx
0x140017800  and     ecx, r10d
0x140017803  mov     [rbp+1220h+var_1050], ecx
0x140017809  jmp     short loc_140017811
0x14001780b  mov     r10d, 2
0x140017811  cmp     dword ptr [rbp+1220h+var_1060+0Ch], 1
0x140017818  jnz     short loc_14001782F
0x14001781a  mov     al, [rbx+0B0h]
0x140017820  neg     al
0x140017822  sbb     ecx, ecx
0x140017824  not     ecx
0x140017826  and     ecx, r10d
0x140017829  mov     dword ptr [rbp+1220h+var_1060+0Ch], ecx
0x14001782f  mov     dl, [rsp+1320h+var_12CE]
0x140017833  mov     ecx, 1
0x140017838  mov     r8d, ecx
0x14001783b  lea     esi, [rcx+4]
0x14001783e  lea     r11d, [rcx+8]
0x140017842  imul    rax, r8, 78h ; 'x'
0x140017846  mov     r9d, [rsp+rax+1320h+var_12BC]
0x14001784b  mov     [rsp+rax+1320h+var_12C0], ecx
0x14001784f  cmp     r9d, 3
0x140017853  jnz     short loc_140017866
0x140017855  cmp     dword ptr [rbp+r8*4+1220h+var_1060], r10d
0x14001785d  jnz     short loc_140017891
0x14001785f  mov     [rbp+rax+1220h+var_124C], r11d
0x140017864  jmp     short loc_14001787F
0x140017866  cmp     r9d, 4
0x14001786a  jnz     short loc_140017891
0x14001786c  cmp     dword ptr [rbp+r8*4+1220h+var_1060], 0
0x140017875  jnz     short loc_140017891
0x140017877  mov     [rbp+rax+1220h+var_124C], 0Ah
0x14001787f  mov     [rbp+rax+1220h+var_1250], cl
0x140017883  mov     dl, 1
0x140017885  mov     [rsp+rax+1320h+var_12B8], 1
0x14001788a  mov     [rsp+rax+1320h+var_12C0], r10d
0x14001788f  jmp     short loc_140017896
0x140017891  mov     [rsp+rax+1320h+var_12B8], 0
0x140017896  inc     ecx
0x140017898  inc     r8
0x14001789b  cmp     ecx, esi
0x14001789d  jb      short loc_140017842
0x14001789f  cmp     byte ptr [rbx+146h], 0
0x1400178a6  mov     ecx, [rbx+18h]
0x1400178a9  jz      loc_140017A8D
0x1400178af  sub     ecx, r10d
0x1400178b2  jz      loc_140017999
0x1400178b8  sub     ecx, 1
0x1400178bb  jz      loc_140017985
0x1400178c1  sub     ecx, 1
0x1400178c4  jz      short loc_140017922
0x1400178c6  sub     ecx, 1
0x1400178c9  jz      short loc_140017913
0x1400178cb  sub     ecx, r10d
0x1400178ce  jz      loc_140017B03
0x1400178d4  cmp     ecx, 1
0x1400178d7  jnz     loc_140017FD4
0x1400178dd  cmp     edi, 7
0x1400178e0  jz      loc_140017F3E
0x1400178e6  jmp     loc_140017FD4
0x1400178eb  cmp     edi, esi
0x1400178ed  jnz     loc_140017FD4
0x1400178f3  xor     r9d, r9d
0x1400178f6  mov     dl, 1
0x1400178f8  mov     qword ptr [rsp+1320h+var_12F8], 0
0x140017901  mov     rcx, rbx
0x140017904  mov     byte ptr [rsp+1320h+Src], 0
0x140017909  call    MoveToAbortState2
0x14001790e  jmp     loc_140017FD4
0x140017913  cmp     edi, esi
0x140017915  jnz     loc_140017FD4
0x14001791b  xor     r9d, r9d
0x14001791e  xor     edx, edx
0x140017920  jmp     short loc_1400178F8
0x140017922  mov     r14d, 8
0x140017928  cmp     edi, r14d
0x14001792b  jnz     short loc_14001797C
0x14001792d  mov     rcx, cs:SstpFsmGlobalInfo
0x140017934  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140017938  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001793f  nop     dword ptr [rax+rax+00h]
0x140017944  mov     rdx, rax
0x140017947  test    rax, rax
0x14001794a  jz      loc_140017FD4
0x140017950  mov     dword ptr [rax+10h], 1100008h
0x140017957  mov     word ptr [rax+16h], 900h
0x14001795d  xor     eax, eax
0x14001795f  mov     [rdx+18h], ax
0x140017963  movzx   eax, word ptr [rdx+10h]
0x140017967  ror     ax, 8
0x14001796b  mov     [rdx+14h], ax
0x14001796f  mov     rcx, rbx
0x140017972  call    SendControlFrame
0x140017977  jmp     loc_140017FD4
0x14001797c  cmp     edi, r11d
0x14001797f  jz      loc_140017FD4
0x140017985  cmp     edi, esi
0x140017987  jnz     loc_140017F9F
0x14001798d  mov     byte ptr [rbx+141h], 1
0x140017994  jmp     loc_1400178F3
0x140017999  cmp     edi, r10d
0x14001799c  jnz     loc_140017A5D
0x1400179a2  cmp     [rsp+1320h+var_12D0], 0
0x1400179a7  jnz     loc_140017E9C
0x1400179ad  test    dl, dl
0x1400179af  jnz     loc_140017E9C
0x1400179b5  mov     cl, [rbx+0B0h]
0x1400179bb  mov     al, [rbp+1220h+var_10D1]
0x1400179c1  test    cl, cl
0x1400179c3  jnz     short loc_1400179E8
0x1400179c5  cmp     [rbp+1220h+var_10DC], 4
0x1400179cc  jz      loc_140017DC0
0x1400179d2  cmp     [rbp+1220h+var_10DC], 3
0x1400179d9  jnz     short loc_140017A13
0x1400179db  mov     r8d, r11d
0x1400179de  mov     edx, 4
0x1400179e3  jmp     loc_140017FC0
0x1400179e8  mov     edx, 4
0x1400179ed  cmp     [rbp+1220h+var_10DC], edx
0x1400179f3  jnz     short loc_1400179FE
0x1400179f5  lea     r8d, [rdx+6]
0x1400179f9  jmp     loc_140017FC0
0x1400179fe  cmp     [rbp+1220h+var_10DC], 3
0x140017a05  jnz     short loc_140017A13
0x140017a07  test    cl, al
0x140017a09  jnz     short loc_140017A13
0x140017a0b  mov     r8d, edx
0x140017a0e  jmp     loc_140017FC0
0x140017a13  movaps  xmm0, [rbp+1220h+var_10D0]
0x140017a1a  and     al, cl
0x140017a1c  movaps  xmm1, [rbp+1220h+var_10C0]
0x140017a23  mov     [rbx+0B0h], al
0x140017a29  movups  xmmword ptr [rbx+90h], xmm0
0x140017a30  movups  xmmword ptr [rbx+0A0h], xmm1
0x140017a37  test    r10b, al
0x140017a3a  jz      short loc_140017A45
0x140017a3c  mov     [rbx+0B0h], r10b
0x140017a43  jmp     short loc_140017A50
0x140017a45  test    al, 1
0x140017a47  jz      short loc_140017A50
0x140017a49  mov     byte ptr [rbx+0B0h], 1
0x140017a50  mov     rcx, rbx
0x140017a53  call    MoveToConnectAckReceivedState
0x140017a58  jmp     loc_140017FD4
  ... truncated ...
```
