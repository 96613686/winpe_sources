# SmbCeReceiveInd

- ea: `0x140004a60`
- end: `0x1400052e4`
- name: `SmbCeReceiveInd`
- size: `2180`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, unsigned int *, __int64, _QWORD *, _DWORD *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400043a0`

## callees

- `0x140004a60`
- `0x1400054b0`
- `0x140005d10`
- `0x140005da0`
- `0x140009f40`
- `0x14000a600`
- `0x14000dfa8`
- `0x14000e01c`
- `0x14000e52c`
- `0x14000ebd8`
- `0x14000fd40`
- `0x140012014`
- `0x14001260c`
- `0x140012ff0`
- `0x140013054`
- `0x140016560`
- `0x140016640`
- `0x140016ee0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004b33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004d7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004ea7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000513a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400051d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400051f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004d7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004ea7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000513a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400051d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400051f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004b0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ce8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005112`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400051b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004b0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ce8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005112`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400051b8`
- `ntoskrnl!DbgPrint` at `0x1400050aa`
- `ntoskrnl!DbgPrint` at `0x1400050aa`
- `rdbss!RxPerProcessCountersEnabled` at `0x140004ebb`
- `rdbss!RxPerProcessCountersEnabled` at `0x140004ebb`
- `rdbss!RxIndicateChangeOfOplockState` at `0x140004c34`
- `rdbss!RxIndicateChangeOfOplockState` at `0x140004c34`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140004b5d`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140004b6c`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140004bd8`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140004be7`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000500b`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140005021`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000523c`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000524f`

## string_xrefs

- `0x1400050a3`: `VctIndReceive:Error handling copy data request %lx\n`

## pseudocode

```c
__int64 __fastcall SmbCeReceiveInd(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        __int64 a6,
        _QWORD *a7,
        _DWORD *a8,
        int a9)
{
  unsigned int LockArray_high; // ebx
  char v13; // al
  KIRQL v14; // al
  unsigned int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  signed __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned __int16 v21; // bx
  KIRQL v22; // al
  __int64 v23; // r8
  unsigned __int16 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rbx
  char v27; // al
  int v28; // eax
  unsigned __int16 v29; // cx
  __int64 v30; // r9
  int v31; // eax
  int v32; // edx
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rbp
  KIRQL v36; // al
  int v37; // ecx
  int v38; // ebp
  __int64 v39; // rax
  unsigned int v40; // ebp
  unsigned int *v41; // r9
  int v42; // eax
  int v43; // ebp
  __int64 v44; // r8
  KIRQL v45; // al
  int v46; // ecx
  KIRQL v47; // al
  unsigned int v50; // [rsp+70h] [rbp-78h]
  _QWORD v51[2]; // [rsp+80h] [rbp-68h] BYREF

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v51[0] = a1;
  v50 = LockArray_high;
  if ( a4 < 0x22 || *(_DWORD *)a6 != 1112364031 || (v13 = *(_BYTE *)(a6 + 4), v13 == -1) )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
      goto LABEL_101;
    v34 = 11;
    goto LABEL_100;
  }
  if ( v13 != 43 )
  {
    if ( v13 == 36 && a3 == 51 )
    {
      v15 = *(unsigned __int16 *)(a6 + 39);
      if ( (v15 & 2) != 0 )
      {
        if ( !(v15 >> 8) || (v16 = 3, v15 >> 8 != 1) )
          v16 = 0;
        RxMiniSniffer((unsigned int)MRxSmbMiniSniffReceiveIndicateOplock, a2, 51, 0, a6);
        _InterlockedIncrement64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + 8LL));
        _InterlockedAdd64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + ((unsigned __int64)v50 << 8)), 0x33u);
        v17 = *(_QWORD *)(a2 + 48);
        if ( v17 )
        {
          v18 = *(unsigned __int16 *)(a6 + 37) | ((unsigned __int64)*(unsigned __int16 *)(a6 + 24) << 16);
          v51[1] = 0;
          v51[0] = v18;
          RxIndicateChangeOfOplockState(v17, v51, 0, v16);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids,
            *(unsigned __int16 *)(a6 + 37),
            *(unsigned __int8 *)(a6 + 40));
        }
        *a5 = 51;
        return 0;
      }
    }
    if ( *(_WORD *)(a6 + 30) == 0xFFFF )
    {
      *a5 = a3;
      _InterlockedIncrement64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + 8LL));
      _InterlockedAdd64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + ((unsigned __int64)LockArray_high << 8)), a3);
      RxMiniSniffer((unsigned int)MRxSmbMiniSniffReceiveDiscardOplock, a2, a3, 0, a6);
      return 0;
    }
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 456));
    *a7 = 0;
    *a8 = 0;
    if ( *(_BYTE *)(a6 + 4) == 114 )
    {
      v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 392), 0, *(_QWORD *)(a2 + 392));
      v20 = v19;
      if ( v19 )
      {
        SmbCeDecrementPendingOperations(v19, 1);
        goto LABEL_34;
      }
    }
    else
    {
      v21 = *(_WORD *)(a6 + 30);
      v22 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
      v23 = *(_QWORD *)(a2 + 384);
      s_SmbCeDbSpinLockSavedIrql = v22;
      if ( v23 )
      {
        v24 = v21;
        v20 = *(_QWORD *)(v23 + 48);
        do
        {
          v25 = (unsigned __int16)(v24 & *(_WORD *)(v20 + 22)) >> *(_BYTE *)(v20 + 24);
          if ( (unsigned int)v25 >= *(unsigned __int16 *)(v20 + 16) )
            break;
          v26 = *(_QWORD *)(v20 + 8 * v25 + 40);
          v27 = v26;
          v20 = v26 & 0xFFFFFFFFFFFFFFFCuLL;
          v28 = v27 & 3;
          if ( v28 == 2 )
          {
            if ( !v20 )
              goto LABEL_32;
            v29 = *(_WORD *)(v23 + 8);
            if ( v29 >= 0x10u || (v24 & (unsigned __int16)~((1 << v29) - 1)) == *(_WORD *)(v20 + 62) )
              goto LABEL_32;
            break;
          }
        }
        while ( v28 == 3 );
      }
      v20 = 0;
LABEL_32:
      KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    }
    LOBYTE(v30) = 0;
    if ( !v20 )
    {
LABEL_35:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_sqLLLLqq(
          WPP_GLOBAL_Control->AttachedDevice,
          *(unsigned __int16 *)(a6 + 30) | (*(unsigned __int8 *)(a6 + 4) << 24),
          *(unsigned __int16 *)(a6 + 10) | (*(unsigned __int8 *)(a6 + 9) << 16),
          (unsigned int)MRxSmbMiniSniffReceive,
          a2,
          *(_WORD *)(a6 + 30),
          *(_DWORD *)(a6 + 5),
          a3,
          *(_WORD *)(a6 + 10),
          v20,
          v30);
      }
      if ( v20 )
      {
        v31 = *(unsigned __int8 *)(a6 + 4);
        if ( (_BYTE)v31 != 0xA4 )
        {
          v32 = *(unsigned __int8 *)(v20 + 304);
          if ( (_BYTE)v32 != (_BYTE)v31 && v32 != v31 + 1 )
          {
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
            {
              goto LABEL_101;
            }
            v34 = 13;
LABEL_100:
            WPP_SF_q(v33->AttachedDevice, v34, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, a2);
LABEL_101:
            *a5 = a3;
            return 0;
          }
        }
        v35 = *(_QWORD *)(v20 + 80);
        v36 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
        v37 = *(_DWORD *)(v20 + 72);
        s_SmbCeDbSpinLockSavedIrql = v36;
        if ( (v37 & 8) != 0 )
        {
          KeReleaseSpinLock(&s_SmbCeDbSpinLock, v36);
        }
        else
        {
          if ( v35 && (!*(_DWORD *)(v35 + 328) || *(_WORD *)v20 == 0xED04) )
          {
            ++*(_DWORD *)(v20 + 116);
            v38 = 0;
            ++*(_DWORD *)(v20 + 108);
          }
          else
          {
            v38 = -1073741300;
          }
          KeReleaseSpinLock(&s_SmbCeDbSpinLock, v36);
          if ( !v38 )
          {
            if ( (unsigned __int8)RxPerProcessCountersEnabled() )
            {
              v39 = *(_QWORD *)(v20 + 24);
              if ( v39 && *(int *)(v39 + 120) >= 0 )
              {
                if ( *(_DWORD *)(v51[0] + 372LL) )
                  _InterlockedAdd(
                    (volatile signed __int32 *)(*(_QWORD *)(v20 + 24) + 196LL),
                    _InterlockedExchange((volatile __int32 *)(v51[0] + 372LL), 0));
                _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v20 + 24) + 196LL), a4);
              }
              else
              {
                _InterlockedAdd((volatile signed __int32 *)(v51[0] + 372LL), a4);
              }
            }
            if ( (*(_BYTE *)(a2 + 672) & 8) != 0 && (a9 & 0x400) != 0 && a3 == a4 )
            {
              if ( (int)SmbCheckSecuritySignature(v20, a2 + 400, a3, a6) < 0
                || (CngRsa32Compat_MD5Final(v20 + 272),
                    *(_BYTE *)(v20 + 255) = 0,
                    memcmp((const void *)(v20 + 288), (const void *)(v20 + 305), 8u)) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
                {
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    14,
                    WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids,
                    a2,
                    v20);
                }
                *(_BYTE *)(a6 + 5) = 2;
                *(_WORD *)(a6 + 7) = 59;
                SmbCeTransportDisconnectIndicated(*(PVOID *)(v20 + 80));
              }
            }
            v40 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, _QWORD, unsigned int *, __int64, _QWORD *, _DWORD *, int))(*(_QWORD *)(v20 + 152) + 8LL))(
                    v20,
                    a3,
                    a4,
                    a5,
                    a6,
                    a7,
                    a8,
                    a9);
            _InterlockedIncrement64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + 8LL));
            v41 = a5;
            _InterlockedAdd64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + ((unsigned __int64)v50 << 8)), *a5);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_LLq(
                WPP_GLOBAL_Control->AttachedDevice,
                15,
                WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids,
                v40,
                *a5,
                *a7);
              v41 = a5;
            }
            if ( v40 == -1073741802 )
            {
              v42 = SmbCeAssociateBufferWithExchange(a2, v20, *a7);
              v43 = v42;
              if ( v42 )
              {
                DbgPrint("VctIndReceive:Error handling copy data request %lx\n", v42);
                v41 = a5;
                *(_DWORD *)(v20 + 48) = v43;
                v40 = 0;
                *a5 = a4;
              }
              else
              {
                v41 = a5;
                v40 = -1073741802;
              }
            }
            if ( (*(_BYTE *)(a2 + 672) & 8) != 0 )
            {
              if ( v40 == -1073741802 )
              {
                v44 = *v41;
                if ( (_DWORD)v44 )
                  SmbCheckSecuritySignature(v20, a2 + 400, v44, a6);
                goto LABEL_79;
              }
            }
            else if ( v40 == -1073741802 )
            {
LABEL_79:
              SmbCeSetExpiryTime(v20);
LABEL_80:
              v45 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
              v46 = *(_DWORD *)(v20 + 112);
              s_SmbCeDbSpinLockSavedIrql = v45;
              if ( v46 > 0 )
                *(_DWORD *)(v20 + 112) = v46 - 1;
              KeReleaseSpinLock(&s_SmbCeDbSpinLock, v45);
              SmbCeDecrementPendingOperationsAndFinalize((PVOID)v20);
              if ( *a5 + *a8 < a4 && v40 != -1073741802 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids);
                }
                *a5 = a4;
              }
              return v40;
            }
            v47 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
            --*(_DWORD *)(v20 + 108);
            s_SmbCeDbSpinLockSavedIrql = v47;
            KeReleaseSpinLock(&s_SmbCeDbSpinLock, v47);
            goto LABEL_80;
          }
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, a2);
      }
      v40 = 0;
      *a5 = a4;
      return v40;
    }
LABEL_34:
    v30 = *(_QWORD *)(v20 + 24);
    goto LABEL_35;
  }
  _InterlockedExchange((volatile __int32 *)(a2 + 460), 1);
  v14 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  s_SmbCeDbSpinLockSavedIrql = v14;
  *(_QWORD *)(a2 + 448) = 0;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, v14);
  *a5 = a3;
  RxMiniSniffer((unsigned int)MRxSmbMiniSniffReceiveEcho, a2, a3, 0, a6);
  _InterlockedIncrement64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + 8LL));
  _InterlockedAdd64((volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + ((unsigned __int64)LockArray_high << 8)), a3);
  return 0;
}

```

## disassembly

```asm
0x140004a60  push    rbx
0x140004a62  push    rbp
0x140004a63  push    rsi
0x140004a64  push    rdi
0x140004a65  push    r12
0x140004a67  push    r13
0x140004a69  push    r14
0x140004a6b  push    r15
0x140004a6d  sub     rsp, 0A8h
0x140004a74  mov     rax, cs:__security_cookie
0x140004a7b  xor     rax, rsp
0x140004a7e  mov     [rsp+0E8h+var_58], rax
0x140004a86  mov     rbp, [rsp+0E8h+arg_20]
0x140004a8e  mov     r13d, r9d
0x140004a91  mov     ebx, gs:1A4h
0x140004a99  mov     r14, rdx
0x140004a9c  mov     rsi, [rsp+0E8h+arg_28]
0x140004aa4  mov     r12, [rsp+0E8h+arg_38]
0x140004aac  mov     [rsp+0E8h+var_68], rcx
0x140004ab4  mov     rcx, [rsp+0E8h+arg_30]
0x140004abc  mov     r15d, r8d
0x140004abf  mov     [rsp+0E8h+var_70], rcx
0x140004ac4  mov     [rsp+0E8h+var_88], r15d
0x140004ac9  mov     [rsp+0E8h+var_80], rbp
0x140004ace  mov     [rsp+0E8h+var_78], ebx
0x140004ad2  cmp     r9d, 22h ; '"'
0x140004ad6  jb      loc_140005282
0x140004adc  cmp     dword ptr [rsi], 424D53FFh
0x140004ae2  jnz     loc_140005282
0x140004ae8  movzx   eax, byte ptr [rsi+4]
0x140004aec  cmp     al, 0FFh
0x140004aee  jz      loc_140005282
0x140004af4  cmp     al, 2Bh ; '+'
0x140004af6  jnz     loc_140004B88
0x140004afc  mov     eax, 1
0x140004b01  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004b08  xchg    eax, [rdx+1CCh]
0x140004b0e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004b15  nop     dword ptr [rax+rax+00h]
0x140004b1a  xor     edi, edi
0x140004b1c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004b23  movzx   edx, al; NewIrql
0x140004b26  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140004b2c  mov     [r14+1C0h], rdi
0x140004b33  call    cs:__imp_KeReleaseSpinLock
0x140004b3a  nop     dword ptr [rax+rax+00h]
0x140004b3f  xor     r9d, r9d
0x140004b42  mov     [rbp+0], r15d
0x140004b46  mov     r8d, r15d
0x140004b49  mov     [rsp+0E8h+var_C8], rsi
0x140004b4e  mov     rdx, r14
0x140004b51  lea     rcx, MRxSmbMiniSniffReceiveEcho; "RcvEcho"
0x140004b58  call    RxMiniSniffer
0x140004b5d  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140004b64  mov     rcx, [rax]
0x140004b67  lock inc qword ptr [rcx+8]
0x140004b6c  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140004b73  mov     edx, r15d
0x140004b76  mov     ecx, ebx
0x140004b78  shl     rcx, 8
0x140004b7c  add     rcx, [rax]
0x140004b7f  lock add [rcx], rdx
0x140004b83  jmp     loc_1400052BD
0x140004b88  cmp     al, 24h ; '$'
0x140004b8a  jnz     loc_140004C8A
0x140004b90  cmp     r15d, 33h ; '3'
0x140004b94  jnz     loc_140004C8A
0x140004b9a  movzx   eax, word ptr [rsi+27h]
0x140004b9e  test    al, 2
0x140004ba0  jz      loc_140004C8A
0x140004ba6  mov     ecx, eax
0x140004ba8  xor     edi, edi
0x140004baa  shr     ecx, 8
0x140004bad  test    ecx, ecx
0x140004baf  jz      short loc_140004BBB
0x140004bb1  mov     ebx, 3
0x140004bb6  cmp     ecx, 1
0x140004bb9  jz      short loc_140004BBE
0x140004bbb  mov     rbx, rdi
0x140004bbe  xor     r9d, r9d
0x140004bc1  mov     [rsp+0E8h+var_C8], rsi
0x140004bc6  mov     r8d, 33h ; '3'
0x140004bcc  lea     rcx, MRxSmbMiniSniffReceiveIndicateOplock; "RcvIndicateOplock"
0x140004bd3  call    RxMiniSniffer
0x140004bd8  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140004bdf  mov     rcx, [rax]
0x140004be2  lock inc qword ptr [rcx+8]
0x140004be7  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140004bee  mov     ecx, [rsp+0E8h+var_78]
0x140004bf2  shl     rcx, 8
0x140004bf6  add     rcx, [rax]
0x140004bf9  lock add qword ptr [rcx], 33h ; '3'
0x140004bfe  mov     rcx, [r14+30h]
0x140004c02  test    rcx, rcx
0x140004c05  jz      short loc_140004C40
0x140004c07  movzx   edx, word ptr [rsi+18h]
0x140004c0b  mov     r9, rbx
0x140004c0e  movzx   eax, word ptr [rsi+25h]
0x140004c12  xor     r8d, r8d
0x140004c15  shl     rdx, 10h
0x140004c19  or      rdx, rax
0x140004c1c  mov     [rsp+0E8h+var_60], rdi
0x140004c24  mov     [rsp+0E8h+var_68], rdx
0x140004c2c  lea     rdx, [rsp+0E8h+var_68]
0x140004c34  call    cs:__imp_RxIndicateChangeOfOplockState
0x140004c3b  nop     dword ptr [rax+rax+00h]
0x140004c40  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004c47  lea     r15, WPP_GLOBAL_Control
0x140004c4e  cmp     rcx, r15
0x140004c51  jz      short loc_140004C7E
0x140004c53  test    dword ptr [rcx+2Ch], 200h
0x140004c5a  jz      short loc_140004C7E
0x140004c5c  movzx   eax, byte ptr [rsi+28h]
0x140004c60  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x140004c67  movzx   r9d, word ptr [rsi+25h]
0x140004c6c  mov     edx, 0Ch
0x140004c71  mov     rcx, [rcx+18h]
0x140004c75  mov     dword ptr [rsp+0E8h+var_C8], eax
0x140004c79  call    WPP_SF_Dd
0x140004c7e  mov     dword ptr [rbp+0], 33h ; '3'
0x140004c85  jmp     loc_1400052BD
0x140004c8a  mov     eax, 0FFFFh
0x140004c8f  cmp     [rsi+1Eh], ax
0x140004c93  jz      loc_14000523C
0x140004c99  lock inc dword ptr [rdx+1C8h]
0x140004ca0  xor     edi, edi
0x140004ca2  mov     [rcx], rdi
0x140004ca5  mov     [r12], edi
0x140004ca9  cmp     byte ptr [rsi+4], 72h ; 'r'
0x140004cad  jnz     short loc_140004CDD
0x140004caf  mov     rax, [rdx+188h]
0x140004cb6  lock cmpxchg [rdx+188h], rdi
0x140004cbf  mov     rbx, rax
0x140004cc2  test    rax, rax
0x140004cc5  jz      loc_140004D88
0x140004ccb  mov     edx, 1
0x140004cd0  mov     rcx, rax
0x140004cd3  call    SmbCeDecrementPendingOperations
0x140004cd8  jmp     loc_140004D90
0x140004cdd  movzx   ebx, word ptr [rsi+1Eh]
0x140004ce1  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004ce8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004cef  nop     dword ptr [rax+rax+00h]
0x140004cf4  mov     r8, [r14+180h]
0x140004cfb  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140004d01  test    r8, r8
0x140004d04  jz      short loc_140004D6B
0x140004d06  movzx   r9d, bx
0x140004d0a  mov     rbx, [r8+30h]
0x140004d0e  movzx   edx, word ptr [rbx+16h]
0x140004d12  movzx   ecx, byte ptr [rbx+18h]
0x140004d16  movzx   eax, r9w
0x140004d1a  and     edx, eax
0x140004d1c  movzx   eax, word ptr [rbx+10h]
0x140004d20  shr     edx, cl
0x140004d22  cmp     edx, eax
0x140004d24  jnb     short loc_140004D6B
0x140004d26  mov     rbx, [rbx+rdx*8+28h]
0x140004d2b  mov     eax, ebx
0x140004d2d  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140004d31  and     eax, 3
0x140004d34  cmp     eax, 2
0x140004d37  jz      short loc_140004D45
0x140004d39  cmp     eax, 3
0x140004d3c  jz      short loc_140004D0E
0x140004d3e  cmp     eax, 1
0x140004d41  jnz     short loc_140004D6B
0x140004d43  jmp     short loc_140004D6B
0x140004d45  test    rbx, rbx
0x140004d48  jz      short loc_140004D6E
0x140004d4a  movzx   ecx, word ptr [r8+8]
0x140004d4f  cmp     cx, 10h
0x140004d53  jnb     short loc_140004D6E
0x140004d55  mov     eax, 1
0x140004d5a  shl     ax, cl
0x140004d5d  lea     ecx, [rax-1]
0x140004d60  not     ecx
0x140004d62  and     ecx, r9d
0x140004d65  cmp     cx, [rbx+3Eh]
0x140004d69  jz      short loc_140004D6E
0x140004d6b  mov     rbx, rdi
0x140004d6e  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140004d75  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004d7c  call    cs:__imp_KeReleaseSpinLock
0x140004d83  nop     dword ptr [rax+rax+00h]
0x140004d88  mov     r9, rdi
0x140004d8b  test    rbx, rbx
0x140004d8e  jz      short loc_140004D94
0x140004d90  mov     r9, [rbx+18h]
0x140004d94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004d9b  lea     r15, WPP_GLOBAL_Control
0x140004da2  cmp     rcx, r15
0x140004da5  jz      short loc_140004E04
0x140004da7  test    dword ptr [rcx+2Ch], 200h
0x140004dae  jz      short loc_140004E04
0x140004db0  movzx   eax, word ptr [rsi+0Ah]
0x140004db4  movzx   r8d, byte ptr [rsi+9]
0x140004db9  movzx   edx, byte ptr [rsi+4]
0x140004dbd  mov     rcx, [rcx+18h]
0x140004dc1  mov     [rsp+0E8h+var_98], r9
0x140004dc6  lea     r9, MRxSmbMiniSniffReceive; "Receive"
0x140004dcd  mov     [rsp+0E8h+var_A0], rbx
0x140004dd2  shl     r8d, 10h
0x140004dd6  or      r8d, eax
0x140004dd9  shl     edx, 18h
0x140004ddc  movzx   eax, word ptr [rsi+1Eh]
0x140004de0  mov     [rsp+0E8h+var_A8], r8d
0x140004de5  or      edx, eax
0x140004de7  mov     eax, [rsp+0E8h+var_88]
0x140004deb  mov     [rsp+0E8h+var_B0], eax
0x140004def  mov     eax, [rsi+5]
0x140004df2  mov     dword ptr [rsp+0E8h+var_B8], eax
0x140004df6  mov     dword ptr [rsp+0E8h+var_C0], edx
0x140004dfa  mov     [rsp+0E8h+var_C8], r14
0x140004dff  call    WPP_SF_sqLLLLqq
0x140004e04  test    rbx, rbx
0x140004e07  jz      loc_1400051FE
0x140004e0d  movzx   eax, byte ptr [rsi+4]
0x140004e11  cmp     al, 0A4h
0x140004e13  jz      short loc_140004E4E
0x140004e15  movzx   edx, byte ptr [rbx+130h]
0x140004e1c  cmp     dl, al
0x140004e1e  jz      short loc_140004E4E
0x140004e20  lea     ecx, [rax+1]
0x140004e23  cmp     edx, ecx
0x140004e25  jz      short loc_140004E4E
0x140004e27  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004e2e  cmp     rcx, r15
0x140004e31  jz      loc_1400052B6
0x140004e37  test    dword ptr [rcx+2Ch], 200h
0x140004e3e  jz      loc_1400052B6
0x140004e44  mov     edx, 0Dh
0x140004e49  jmp     loc_1400052A3
0x140004e4e  mov     rbp, [rbx+50h]
0x140004e52  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004e59  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004e60  nop     dword ptr [rax+rax+00h]
0x140004e65  mov     ecx, [rbx+48h]
0x140004e68  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140004e6e  test    cl, 8
0x140004e71  jnz     loc_1400051E8
0x140004e77  test    rbp, rbp
0x140004e7a  jz      short loc_140004E98
0x140004e7c  cmp     [rbp+148h], edi
0x140004e82  jz      short loc_140004E8E
0x140004e84  mov     ecx, 0ED04h
0x140004e89  cmp     [rbx], cx
0x140004e8c  jnz     short loc_140004E98
0x140004e8e  inc     dword ptr [rbx+74h]
0x140004e91  mov     ebp, edi
0x140004e93  inc     dword ptr [rbx+6Ch]
0x140004e96  jmp     short loc_140004E9D
0x140004e98  mov     ebp, 0C000020Ch
0x140004e9d  movzx   edx, al; NewIrql
0x140004ea0  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004ea7  call    cs:__imp_KeReleaseSpinLock
0x140004eae  nop     dword ptr [rax+rax+00h]
0x140004eb3  test    ebp, ebp
0x140004eb5  jnz     loc_1400051FE
0x140004ebb  call    cs:__imp_RxPerProcessCountersEnabled
0x140004ec2  nop     dword ptr [rax+rax+00h]
0x140004ec7  test    al, al
0x140004ec9  jz      short loc_140004F1A
0x140004ecb  mov     rax, [rbx+18h]
0x140004ecf  test    rax, rax
0x140004ed2  jz      short loc_140004F0A
0x140004ed4  cmp     [rax+78h], edi
0x140004ed7  jl      short loc_140004F0A
0x140004ed9  mov     rax, [rsp+0E8h+var_68]
0x140004ee1  cmp     [rax+174h], edi
0x140004ee7  jz      short loc_140004EFC
0x140004ee9  mov     ecx, edi
0x140004eeb  xchg    ecx, [rax+174h]
0x140004ef1  mov     rax, [rbx+18h]
0x140004ef5  lock add [rax+0C4h], ecx
0x140004efc  mov     rax, [rbx+18h]
0x140004f00  lock add [rax+0C4h], r13d
0x140004f08  jmp     short loc_140004F1A
0x140004f0a  mov     rax, [rsp+0E8h+var_68]
0x140004f12  lock add [rax+174h], r13d
0x140004f1a  test    byte ptr [r14+2A0h], 8
0x140004f22  mov     ebp, [rsp+0E8h+arg_40]
0x140004f29  jz      loc_140004FD4
0x140004f2f  bt      ebp, 0Ah
0x140004f33  jnb     loc_140004FD4
0x140004f39  mov     eax, [rsp+0E8h+var_88]
0x140004f3d  cmp     eax, r13d
0x140004f40  jnz     loc_140004FD4
0x140004f46  lea     rdx, [r14+190h]
0x140004f4d  mov     r9, rsi
0x140004f50  mov     r8d, eax
0x140004f53  mov     rcx, rbx
0x140004f56  call    SmbCheckSecuritySignature
0x140004f5b  test    eax, eax
0x140004f5d  js      short loc_140004F8F
0x140004f5f  lea     rcx, [rbx+110h]
0x140004f66  call    CngRsa32Compat_MD5Final
0x140004f6b  lea     rdx, [rbx+131h]; Buf2
0x140004f72  mov     [rbx+0FFh], dil
0x140004f79  lea     rcx, [rbx+120h]; Buf1
  ... truncated ...
```
