# HidpMajorHandler

- ea: `0x180004c00`
- end: `0x1800053b2`
- name: `HidpMajorHandler`
- size: `1970`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003900`
- `0x180003b70`
- `0x180003f40`
- `0x1800043a0`
- `0x180004c00`
- `0x1800053c0`
- `0x18000621c`
- `0x180006940`
- `0x180006ac8`
- `0x18000a264`
- `0x18000b140`
- `0x180012304`
- `0x180015438`
- `0x180015b98`
- `0x1800163bc`
- `0x18001e99c`
- `0x18001f890`
- `0x18003e58c`
- `0x18003fb20`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180004fc7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180004fc7`
- `ntoskrnl!IofCompleteRequest` at `0x180005132`
- `ntoskrnl!IofCompleteRequest` at `0x180005165`
- `ntoskrnl!IofCompleteRequest` at `0x180005132`
- `ntoskrnl!IofCompleteRequest` at `0x180005165`
- `ntoskrnl!KeReleaseSpinLock` at `0x180004e72`
- `ntoskrnl!KeReleaseSpinLock` at `0x180004f7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800050cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800050f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x180004e72`
- `ntoskrnl!KeReleaseSpinLock` at `0x180004f7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800050cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800050f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180004e42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180004e42`

## pseudocode

```c
__int64 __fastcall HidpMajorHandler(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // r15
  char v5; // r12
  __int64 v6; // rbp
  int v7; // r14d
  __int64 v8; // r10
  _QWORD *v9; // rbx
  __int64 v10; // r13
  unsigned int v11; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // edi
  unsigned __int64 v16; // rdx
  bool v17; // zf
  __int64 v18; // r10
  __int64 v19; // rdi
  __int64 v20; // rcx
  KIRQL v21; // r8
  int v22; // eax
  char v23; // si
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 v26; // rdx
  __int64 v27; // rbp
  __int64 v28; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // r9
  KSPIN_LOCK *v31; // rcx
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-A8h]
  ULONG Priority; // [rsp+28h] [rbp-A0h]
  char *v34; // [rsp+30h] [rbp-98h]
  __int64 *v35; // [rsp+38h] [rbp-90h]
  __int64 v36; // [rsp+70h] [rbp-58h]
  char v37; // [rsp+D0h] [rbp+8h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+D8h] [rbp+10h]
  __int64 v39; // [rsp+E0h] [rbp+18h]
  __int64 v40; // [rsp+E8h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 64);
  v4 = a2;
  v5 = *(_BYTE *)(v3 + 24);
  v6 = v3 + 32;
  v7 = **(unsigned __int8 **)(a2 + 184);
  if ( v5 )
  {
    v8 = v3 + 32;
    v9 = (_QWORD *)(*(_QWORD *)(v3 + 96) + 32LL);
  }
  else
  {
    v8 = 0;
    v9 = (_QWORD *)(v3 + 32);
  }
  v10 = v9[84];
  v36 = v8;
  if ( v7 != 27 )
  {
    if ( v7 != 14 && v7 != 15 && v7 != 22 )
    {
      if ( v5 )
      {
        LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && LOWORD(WPP_GLOBAL_Control->DeviceType);
        if ( (_BYTE)a2 || (_BYTE)a3 )
        {
          v35 = WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids;
          LOWORD(v34) = 14;
          WPP_RECORDER_AND_TRACE_SF_qdqqc(WPP_GLOBAL_Control->AttachedDevice, a2, a3, v10, 5);
        }
      }
      else
      {
        LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && LOWORD(WPP_GLOBAL_Control->DeviceType);
        if ( (_BYTE)a2 || (_BYTE)a3 )
        {
          v35 = WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids;
          LOWORD(v34) = 15;
          WPP_RECORDER_AND_TRACE_SF_qqc(WPP_GLOBAL_Control->AttachedDevice, a2, a3, v10, 5);
        }
      }
    }
    if ( v7 == 3 )
    {
      v11 = HidpIrpMajorRead(v3, v4);
      goto LABEL_20;
    }
    if ( v7 == 2 )
    {
      v11 = HidpIrpMajorClose(v3, v4, a3, &WPP_GLOBAL_Control);
LABEL_20:
      v14 = v11;
      goto LABEL_21;
    }
  }
  v16 = 0x180000000uLL;
  switch ( v7 )
  {
    case 0:
      v11 = HidpIrpMajorCreate(v3, (IRP *)v4);
      goto LABEL_20;
    case 4:
      v17 = *(_BYTE *)(v3 + 24) == 0;
      v37 = 0;
      if ( v17 )
      {
        v14 = -1073741585;
        goto LABEL_69;
      }
      v18 = *(_QWORD *)(v3 + 96) + 32LL;
      v40 = v18;
      LOBYTE(v16) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v35 = WPP_cc6278634ffa382d4d0173c5ca0c4d0f_Traceguids;
        LOWORD(v34) = 11;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqqc(WPP_GLOBAL_Control->AttachedDevice, v16, a3, *(_QWORD *)(v18 + 672), 4);
        v18 = v40;
      }
      if ( *(_DWORD *)(v3 + 36) != 3 || !*(_DWORD *)(v18 + 1720) )
      {
        v14 = -1073741667;
LABEL_69:
        *(_DWORD *)(v4 + 48) = v14;
        IofCompleteRequest((PIRP)v4, 0);
        goto LABEL_21;
      }
      v19 = *(_QWORD *)(v3 + 96) + 32LL;
      v39 = v19;
      v20 = MEMORY[0xFFFFF78000000014];
      _InterlockedExchange64((volatile __int64 *)(v19 + 2120), MEMORY[0xFFFFF78000000014]);
      _InterlockedExchange64((volatile __int64 *)(v3 + 368), v20);
      HidpFdoAcquirePoFxPowerReferenceWithTag(v19, 8u);
      SpinLock = (PKSPIN_LOCK)(v19 + 384);
      v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 384));
      v22 = *(_DWORD *)(v19 + 1720);
      if ( v22 != 1 )
      {
        if ( v22 )
        {
          v14 = 0;
          if ( v22 == 2 )
          {
            _InterlockedExchange64((volatile __int64 *)(v4 + 104), (__int64)&PowerDelayedCancelRoutine);
            if ( !*(_BYTE *)(v4 + 68) )
            {
              v28 = v39;
              v29 = v39 + 392;
              v30 = *(_QWORD **)(v39 + 400);
              if ( *v30 != v39 + 392 )
                __fastfail(3u);
              v14 = 259;
              *(_QWORD *)(v4 + 168) = v29;
              *(_QWORD *)(v4 + 176) = v30;
              *v30 = v4 + 168;
              *(_QWORD *)(v29 + 8) = v4 + 168;
              ++*(_DWORD *)(v28 + 408);
              v31 = SpinLock;
              *(_QWORD *)(v4 + 120) = v3;
              *(_BYTE *)(*(_QWORD *)(v4 + 184) + 3LL) |= 1u;
              KeReleaseSpinLock(v31, v21);
              v23 = 1;
              goto LABEL_64;
            }
            if ( _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0) )
            {
              v14 = -1073741536;
              goto LABEL_63;
            }
            v14 = 259;
            *(_QWORD *)(v4 + 176) = v4 + 168;
            *(_QWORD *)(v4 + 168) = v4 + 168;
            ++*(_DWORD *)(v39 + 408);
            *(_QWORD *)(v4 + 120) = v3;
            *(_BYTE *)(*(_QWORD *)(v4 + 184) + 3LL) |= 1u;
          }
          KeReleaseSpinLock(SpinLock, v21);
          v23 = 1;
          if ( !v14 )
            goto LABEL_48;
LABEL_64:
          if ( v14 == 259 )
            goto LABEL_21;
          v27 = v40;
          goto LABEL_66;
        }
        v14 = -1073741811;
LABEL_63:
        KeReleaseSpinLock(SpinLock, v21);
        HidpFdoReleasePoFxPowerReferenceWithTag(v39, 8);
        v23 = 0;
        goto LABEL_64;
      }
      ++*(_DWORD *)(v19 + 1860);
      KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 384), v21);
      v23 = 1;
LABEL_48:
      v24 = *(_QWORD *)(v4 + 8);
      v25 = *(_QWORD *)(v4 + 184);
      if ( v24 && (*(_BYTE *)(v24 + 10) & 5) == 0 )
        MmMapLockedPagesSpecifyCache((PMDL)v24, 0, MmCached, 0, 0, 0x40000010u);
      v26 = v6;
      v27 = v40;
      v34 = &v37;
      LOBYTE(Priority) = 0;
      BugCheckOnFailure = *(_DWORD *)(v25 + 8);
      v14 = HidpWriteReport(v40, v26, v4);
      if ( !v37 )
      {
LABEL_66:
        *(_DWORD *)(v4 + 48) = v14;
        IofCompleteRequest((PIRP)v4, 0);
        if ( v23 )
          HidpFdoResumeIdleForIo(v27, v4);
      }
LABEL_21:
      if ( (_BYTE)v7 != 27 && (_BYTE)v7 != 14 && (_BYTE)v7 != 22 && (int)(v14 + 0x80000000) >= 0 && v14 != -1073741637 )
      {
        if ( v5 )
        {
          LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qdqqcd(
              WPP_GLOBAL_Control->AttachedDevice,
              v12,
              v13,
              v10,
              BugCheckOnFailure,
              Priority,
              (_DWORD)v34,
              (_DWORD)v35,
              *(_QWORD *)(*(_QWORD *)(v36 + 64) + 32LL),
              *(_DWORD *)(v36 + 8),
              *(_QWORD *)(v36 + 48),
              v4,
              v7,
              v14);
          }
        }
        else
        {
          LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qqcd(
              WPP_GLOBAL_Control->AttachedDevice,
              v12,
              v13,
              v10,
              4,
              4,
              17,
              (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
              *v9,
              v4,
              v7,
              v14);
          }
        }
      }
      return v14;
    case 14:
      v11 = HidpIrpMajorDeviceControl(v3, (IRP *)v4);
      goto LABEL_20;
    case 15:
      v11 = HidpIrpMajorINTERNALDeviceControl(v3, v4, a3, &WPP_GLOBAL_Control);
      goto LABEL_20;
    case 22:
      if ( *(_BYTE *)(v3 + 24) )
        v11 = HidpPdoPower(v3, v4, a3, &WPP_GLOBAL_Control);
      else
        v11 = HidpFdoPower(v3, v4, a3, &WPP_GLOBAL_Control);
      goto LABEL_20;
    case 23:
      v11 = HidpIrpMajorSystemControl(v3, v4, a3, &WPP_GLOBAL_Control);
      goto LABEL_20;
    case 27:
      v11 = HidpIrpMajorPnp(v3, v4, a3, &WPP_GLOBAL_Control);
      goto LABEL_20;
    default:
      v11 = HidpIrpMajorDefault(v3, v4);
      goto LABEL_20;
  }
}

```

## disassembly

```asm
0x180004c00  push    rbx
0x180004c02  push    rbp
0x180004c03  push    rsi
0x180004c04  push    rdi
0x180004c05  push    r12
0x180004c07  push    r13
0x180004c09  push    r14
0x180004c0b  push    r15
0x180004c0d  sub     rsp, 88h
0x180004c14  mov     rsi, [rcx+40h]
0x180004c18  mov     r15, rdx
0x180004c1b  mov     rax, [rdx+0B8h]
0x180004c22  movzx   r12d, byte ptr [rsi+18h]
0x180004c27  lea     rbp, [rsi+20h]
0x180004c2b  movzx   r14d, byte ptr [rax]
0x180004c2f  test    r12b, r12b
0x180004c32  jz      loc_180005176
0x180004c38  mov     rbx, [rbp+40h]
0x180004c3c  mov     r10, rbp
0x180004c3f  add     rbx, 20h ; ' '
0x180004c43  mov     r13, [rbx+2A0h]
0x180004c4a  lea     r9, WPP_GLOBAL_Control
0x180004c51  mov     [rsp+0C8h+var_58], r10
0x180004c56  lea     r11, WPP_RECORDER_INITIALIZED
0x180004c5d  cmp     r14d, 1Bh
0x180004c61  jz      loc_180004D14
0x180004c67  mov     ecx, r14d
0x180004c6a  sub     ecx, 0Eh
0x180004c6d  jz      short loc_180004CC3
0x180004c6f  sub     ecx, 1
0x180004c72  jz      short loc_180004CC3
0x180004c74  cmp     ecx, 7
0x180004c77  jz      short loc_180004CC3
0x180004c79  test    r12b, r12b
0x180004c7c  jz      loc_1800051A1
0x180004c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c89  cmp     rcx, r9
0x180004c8c  jz      short loc_180004C99
0x180004c8e  mov     eax, [rcx+2Ch]
0x180004c91  test    al, 8
0x180004c93  jnz     loc_180005257
0x180004c99  xor     dl, dl
0x180004c9b  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x180004ca2  jz      short loc_180004CAF
0x180004ca4  cmp     word ptr [rcx+48h], 0
0x180004ca9  jnz     loc_180005268
0x180004caf  xor     r8b, r8b
0x180004cb2  test    dl, dl
0x180004cb4  jnz     loc_180005270
0x180004cba  test    r8b, r8b
0x180004cbd  jnz     loc_180005270
0x180004cc3  cmp     r14d, 3
0x180004cc7  jz      short loc_180004CDC
0x180004cc9  cmp     r14d, 2
0x180004ccd  jnz     short loc_180004D0A
0x180004ccf  mov     rdx, r15
0x180004cd2  mov     rcx, rsi
0x180004cd5  call    HidpIrpMajorClose
0x180004cda  jmp     short loc_180004CE7
0x180004cdc  mov     rdx, r15
0x180004cdf  mov     rcx, rsi
0x180004ce2  call    HidpIrpMajorRead
0x180004ce7  mov     edi, eax
0x180004ce9  cmp     r14b, 1Bh
0x180004ced  jnz     loc_180004E86
0x180004cf3  mov     eax, edi
0x180004cf5  add     rsp, 88h
0x180004cfc  pop     r15
0x180004cfe  pop     r14
0x180004d00  pop     r13
0x180004d02  pop     r12
0x180004d04  pop     rdi
0x180004d05  pop     rsi
0x180004d06  pop     rbp
0x180004d07  pop     rbx
0x180004d08  retn
0x180004d0a  cmp     r14d, 1Bh; switch 28 cases
0x180004d0e  ja      def_180004D2E; jumptable 0000000180004D2E default case, cases 1-3,5-13,16-21,24-26
0x180004d14  lea     rdx, cs:180000000h
0x180004d1b  movzx   eax, ds:(byte_18002C5DC - 180000000h)[rdx+r14]
0x180004d24  mov     ecx, ds:(jpt_180004D2E - 180000000h)[rdx+rax*4]
0x180004d2b  add     rcx, rdx
0x180004d2e  jmp     rcx; switch jump
0x180004d34  cmp     byte ptr [rsi+18h], 0; jumptable 0000000180004D2E case 4
0x180004d38  mov     [rsp+0C8h+arg_0], 0
0x180004d40  jz      loc_1800052EA
0x180004d46  mov     r10, [rsi+60h]
0x180004d4a  add     r10, 20h ; ' '
0x180004d4e  mov     [rsp+0C8h+arg_18], r10
0x180004d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d5d  cmp     rcx, r9
0x180004d60  jz      short loc_180004D6D
0x180004d62  mov     eax, [rcx+2Ch]
0x180004d65  test    al, 8
0x180004d67  jnz     loc_1800052F4
0x180004d6d  xor     dl, dl
0x180004d6f  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x180004d76  setnz   r8b
0x180004d7a  test    dl, dl
0x180004d7c  jnz     short loc_180004D83
0x180004d7e  test    r8b, r8b
0x180004d81  jz      short loc_180004DDA
0x180004d83  mov     rax, [rbp+30h]
0x180004d87  mov     r9, [rbp+40h]
0x180004d8b  mov     rcx, [rcx+18h]
0x180004d8f  mov     [rsp+0C8h+var_68], 4
0x180004d94  mov     [rsp+0C8h+var_70], r15
0x180004d99  mov     [rsp+0C8h+var_78], rax
0x180004d9e  mov     eax, [rbp+8]
0x180004da1  mov     dword ptr [rsp+0C8h+var_80], eax
0x180004da5  mov     rax, [r9+20h]
0x180004da9  mov     r9, [r10+2A0h]
0x180004db0  mov     [rsp+0C8h+var_88], rax
0x180004db5  lea     rax, WPP_cc6278634ffa382d4d0173c5ca0c4d0f_Traceguids
0x180004dbc  mov     [rsp+0C8h+var_90], rax
0x180004dc1  mov     word ptr [rsp+0C8h+var_98], 0Bh
0x180004dc8  mov     byte ptr [rsp+0C8h+BugCheckOnFailure], 4
0x180004dcd  call    WPP_RECORDER_AND_TRACE_SF_qdqqc
0x180004dd2  mov     r10, [rsp+0C8h+arg_18]
0x180004dda  cmp     dword ptr [rbp+4], 3
0x180004dde  jnz     loc_180005157
0x180004de4  cmp     dword ptr [r10+6B8h], 0
0x180004dec  jz      loc_180005157
0x180004df2  mov     rdi, [rsi+60h]
0x180004df6  mov     rax, 0FFFFF78000000014h
0x180004e00  add     rdi, 20h ; ' '
0x180004e04  mov     r8, r15
0x180004e07  mov     edx, 8
0x180004e0c  mov     [rsp+0C8h+arg_10], rdi
0x180004e14  mov     rax, [rax]
0x180004e17  mov     rcx, rax
0x180004e1a  xchg    rcx, [rdi+848h]
0x180004e21  xchg    rax, [rsi+170h]
0x180004e28  mov     rcx, rdi
0x180004e2b  call    HidpFdoAcquirePoFxPowerReferenceWithTag
0x180004e30  lea     rax, [rdi+180h]
0x180004e37  mov     rcx, rax; SpinLock
0x180004e3a  mov     [rsp+0C8h+SpinLock], rax
0x180004e42  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180004e49  nop     dword ptr [rax+rax+00h]
0x180004e4e  movzx   r8d, al
0x180004e52  mov     eax, [rdi+6B8h]
0x180004e58  cmp     eax, 1
0x180004e5b  jnz     loc_180005050
0x180004e61  inc     dword ptr [rdi+744h]
0x180004e67  lea     rcx, [rdi+180h]; SpinLock
0x180004e6e  movzx   edx, r8b; NewIrql
0x180004e72  call    cs:__imp_KeReleaseSpinLock
0x180004e79  nop     dword ptr [rax+rax+00h]
0x180004e7e  mov     sil, 1
0x180004e81  jmp     loc_180004F99
0x180004e86  cmp     r14b, 0Eh
0x180004e8a  jz      loc_180004CF3
0x180004e90  cmp     r14b, 16h
0x180004e94  jz      loc_180004CF3
0x180004e9a  mov     ecx, 80000000h
0x180004e9f  lea     eax, [rdi+rcx]
0x180004ea2  test    ecx, eax
0x180004ea4  jnz     loc_180004CF3
0x180004eaa  cmp     edi, 0C00000BBh
0x180004eb0  jz      loc_180004CF3
0x180004eb6  test    r12b, r12b
0x180004eb9  jz      loc_180005326
0x180004ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ec6  lea     rax, WPP_GLOBAL_Control
0x180004ecd  cmp     rcx, rax
0x180004ed0  jz      short loc_180004EDD
0x180004ed2  mov     eax, [rcx+2Ch]
0x180004ed5  test    al, 8
0x180004ed7  jnz     loc_180005315
0x180004edd  xor     dl, dl
0x180004edf  lea     rax, WPP_RECORDER_INITIALIZED
0x180004ee6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180004eed  setnz   r8b
0x180004ef1  test    dl, dl
0x180004ef3  jnz     short loc_180004EFE
0x180004ef5  test    r8b, r8b
0x180004ef8  jz      loc_180004CF3
0x180004efe  mov     r11, [rsp+0C8h+var_58]
0x180004f03  mov     r9, r13
0x180004f06  mov     rcx, [rcx+18h]
0x180004f0a  mov     [rsp+0C8h+var_60], edi
0x180004f0e  mov     [rsp+0C8h+var_68], r14b
0x180004f13  mov     rax, [r11+30h]
0x180004f17  mov     r10, [r11+40h]
0x180004f1b  mov     [rsp+0C8h+var_70], r15
0x180004f20  mov     [rsp+0C8h+var_78], rax
0x180004f25  mov     eax, [r11+8]
0x180004f29  mov     dword ptr [rsp+0C8h+var_80], eax
0x180004f2d  mov     rax, [r10+20h]
0x180004f31  mov     [rsp+0C8h+var_88], rax
0x180004f36  call    WPP_RECORDER_AND_TRACE_SF_qdqqcd
0x180004f3b  jmp     loc_180004CF3
0x180004f40  lea     rax, [r15+0A8h]
0x180004f47  mov     edi, 103h
0x180004f4c  mov     [rax+8], rax
0x180004f50  mov     [rax], rax
0x180004f53  mov     rax, [rsp+0C8h+arg_10]
0x180004f5b  inc     dword ptr [rax+198h]
0x180004f61  mov     [r15+78h], rsi
0x180004f65  mov     rax, [r15+0B8h]
0x180004f6c  or      byte ptr [rax+3], 1
0x180004f70  mov     rcx, [rsp+0C8h+SpinLock]; SpinLock
0x180004f78  movzx   edx, r8b; NewIrql
0x180004f7c  call    cs:__imp_KeReleaseSpinLock
0x180004f83  nop     dword ptr [rax+rax+00h]
0x180004f88  test    edi, edi
0x180004f8a  js      loc_1800050FD
0x180004f90  mov     sil, 1
0x180004f93  jnz     loc_180005115
0x180004f99  mov     rcx, [r15+8]; MemoryDescriptorList
0x180004f9d  xor     r9d, r9d; RequestedAddress
0x180004fa0  mov     rdi, [r15+0B8h]
0x180004fa7  test    rcx, rcx
0x180004faa  jz      short loc_180004FD6
0x180004fac  test    byte ptr [rcx+0Ah], 5
0x180004fb0  jnz     short loc_18000502A
0x180004fb2  mov     [rsp+0C8h+Priority], 40000010h; Priority
0x180004fba  xor     edx, edx; AccessMode
0x180004fbc  mov     r8d, 1; CacheType
0x180004fc2  mov     [rsp+0C8h+BugCheckOnFailure], r9d; BugCheckOnFailure
0x180004fc7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180004fce  nop     dword ptr [rax+rax+00h]
0x180004fd3  mov     r9, rax
0x180004fd6  lea     rax, [rsp+0C8h+arg_0]
0x180004fde  mov     rdx, rbp
0x180004fe1  mov     rbp, [rsp+0C8h+arg_18]
0x180004fe9  mov     r8, r15
0x180004fec  mov     [rsp+0C8h+var_98], rax
0x180004ff1  mov     rcx, rbp
0x180004ff4  mov     eax, [rdi+8]
0x180004ff7  mov     byte ptr [rsp+0C8h+Priority], 0
0x180004ffc  mov     [rsp+0C8h+BugCheckOnFailure], eax
0x180005000  call    HidpWriteReport
0x180005005  cmp     [rsp+0C8h+arg_0], 0
0x18000500d  mov     edi, eax
0x18000500f  jnz     loc_180004CE9
0x180005015  jmp     loc_180005129
0x18000501a  mov     rdx, r15; jumptable 0000000180004D2E case 14
0x18000501d  mov     rcx, rsi
0x180005020  call    HidpIrpMajorDeviceControl
0x180005025  jmp     loc_180004CE7
0x18000502a  mov     r9, [rcx+18h]
0x18000502e  jmp     short loc_180004FD6
0x180005030  mov     rdx, r15; jumptable 0000000180004D2E case 0
0x180005033  mov     rcx, rsi
0x180005036  call    HidpIrpMajorCreate
0x18000503b  jmp     loc_180004CE7
0x180005040  mov     rdx, r15; jumptable 0000000180004D2E case 27
0x180005043  mov     rcx, rsi
0x180005046  call    HidpIrpMajorPnp
0x18000504b  jmp     loc_180004CE7
0x180005050  test    eax, eax
0x180005052  jz      loc_1800050E0
0x180005058  xor     edi, edi
0x18000505a  cmp     eax, 2
0x18000505d  jnz     loc_180004F70
0x180005063  lea     rdx, PowerDelayedCancelRoutine
0x18000506a  xchg    rdx, [r15+68h]
0x18000506e  cmp     [r15+44h], dil
0x180005072  jnz     loc_180005227
0x180005078  mov     rcx, [rsp+0C8h+arg_10]
0x180005080  lea     rdx, [rcx+188h]
0x180005087  mov     r9, [rdx+8]
0x18000508b  cmp     [r9], rdx
0x18000508e  jnz     loc_180005250
0x180005094  lea     rax, [r15+0A8h]
0x18000509b  mov     edi, 103h
0x1800050a0  mov     [rax], rdx
0x1800050a3  mov     [rax+8], r9
0x1800050a7  mov     [r9], rax
0x1800050aa  mov     [rdx+8], rax
0x1800050ae  movzx   edx, r8b; NewIrql
0x1800050b2  inc     dword ptr [rcx+198h]
0x1800050b8  mov     rcx, [rsp+0C8h+SpinLock]; SpinLock
0x1800050c0  mov     [r15+78h], rsi
0x1800050c4  mov     rax, [r15+0B8h]
0x1800050cb  or      byte ptr [rax+3], 1
0x1800050cf  call    cs:__imp_KeReleaseSpinLock
0x1800050d6  nop     dword ptr [rax+rax+00h]
0x1800050db  mov     sil, 1
0x1800050de  jmp     short loc_180005115
0x1800050e0  mov     edi, 0C000000Dh
0x1800050e5  mov     rcx, [rsp+0C8h+SpinLock]; SpinLock
0x1800050ed  movzx   edx, r8b; NewIrql
0x1800050f1  call    cs:__imp_KeReleaseSpinLock
0x1800050f8  nop     dword ptr [rax+rax+00h]
0x1800050fd  mov     rcx, [rsp+0C8h+arg_10]
0x180005105  mov     r8, r15
0x180005108  mov     edx, 8
0x18000510d  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x180005112  xor     sil, sil
0x180005115  cmp     edi, 103h
0x18000511b  jz      loc_180004CE9
0x180005121  mov     rbp, [rsp+0C8h+arg_18]
0x180005129  xor     edx, edx; PriorityBoost
0x18000512b  mov     [r15+30h], edi
0x18000512f  mov     rcx, r15; Irp
0x180005132  call    cs:__imp_IofCompleteRequest
0x180005139  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
