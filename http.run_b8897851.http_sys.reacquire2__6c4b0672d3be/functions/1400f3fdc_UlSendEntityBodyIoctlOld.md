# UlSendEntityBodyIoctlOld

- ea: `0x1400f3fdc`
- end: `0x1400f4c68`
- name: `UlSendEntityBodyIoctlOld`
- size: `3212`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x1400f1ab0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x140019d70`
- `0x140019f88`
- `0x14001a360`
- `0x14001a794`
- `0x14001c8b4`
- `0x14001cb08`
- `0x14001ceac`
- `0x14001f2c0`
- `0x14001f9f4`
- `0x140022610`
- `0x140033850`
- `0x1400354c0`
- `0x140035a70`
- `0x140039360`
- `0x1400474f0`
- `0x140062bf0`
- `0x14008ab10`
- `0x14009da44`
- `0x1400aa118`
- `0x1400b1bac`
- `0x1400b387c`
- `0x1400e3590`
- `0x1400ee2d4`
- `0x1400f3fdc`
- `0x1400fce68`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c49c4`
- `0x1401cdb74`
- `0x1401ce090`
- `0x1401ce0e0`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400f4ae1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f4ae1`
- `ntoskrnl!IofCompleteRequest` at `0x1400f4bcb`
- `ntoskrnl!IofCompleteRequest` at `0x1400f4bcb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f447f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f447f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f49d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f49ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f49d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f49ef`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f4437`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f4437`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f4473`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f4473`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f441d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f441d`

## pseudocode

```c
__int64 __fastcall UlSendEntityBodyIoctlOld(PIRP Irp, __int64 a2)
{
  PIRP v3; // r13
  __int64 v4; // rsi
  char v5; // r12
  __int64 v6; // rdx
  int Consumer; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  int ChunkInfoOld; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r12d
  __int64 RequestFromId; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  bool v18; // r15
  __int64 v19; // rax
  char v20; // dl
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdi
  unsigned int v26; // eax
  __int64 v27; // r13
  int v28; // eax
  ULONG_PTR v29; // rdx
  int v30; // ecx
  _QWORD *v31; // rdx
  int v32; // ecx
  __int64 v33; // rsi
  __int64 v34; // r12
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v42; // [rsp+88h] [rbp-318h]
  char *v43; // [rsp+90h] [rbp-310h]
  bool v44; // [rsp+EEh] [rbp-2B2h]
  __int16 v46; // [rsp+108h] [rbp-298h] BYREF
  __int64 v47; // [rsp+110h] [rbp-290h] BYREF
  __int64 v48; // [rsp+118h] [rbp-288h] BYREF
  __int64 v49; // [rsp+120h] [rbp-280h]
  PVOID P; // [rsp+128h] [rbp-278h]
  __int64 v51; // [rsp+130h] [rbp-270h]
  __int64 v52; // [rsp+138h] [rbp-268h]
  __int128 v53; // [rsp+140h] [rbp-260h] BYREF
  __int128 v54; // [rsp+150h] [rbp-250h]
  __int128 v55; // [rsp+160h] [rbp-240h]
  __int64 v56; // [rsp+170h] [rbp-230h]
  __int128 v57; // [rsp+178h] [rbp-228h] BYREF
  _BYTE v58[144]; // [rsp+188h] [rbp-218h] BYREF
  __int128 v59; // [rsp+218h] [rbp-188h] BYREF
  char v60; // [rsp+228h] [rbp-178h] BYREF

  v3 = Irp;
  *(_QWORD *)&v57 = Irp;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v47 = 0;
  v4 = 0;
  v52 = 0;
  v48 = 0;
  v5 = 0;
  v44 = 0;
  v51 = 0;
  P = 0;
  memset(v58, 0, sizeof(v58));
  v46 = 0;
  v59 = 0;
  v49 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1033, 24, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, v3, a2);
  Consumer = UlGetConsumer(*(_QWORD *)(a2 + 48), 1, &v48);
  if ( Consumer >= 0 )
  {
    LOBYTE(v6) = v3->RequestorMode;
    Consumer = UlpGetSendInfoOld(v3, v6, *(_QWORD *)(a2 + 32), *(unsigned int *)(a2 + 16), &v53);
    if ( Consumer < 0 )
    {
      v3 = Irp;
      goto LABEL_83;
    }
    v43 = &v60;
    LOBYTE(v10) = v3->RequestorMode;
    ChunkInfoOld = UlpGetChunkInfoOld(v3, v10, WORD4(v53), v54);
    Consumer = ChunkInfoOld;
    if ( ChunkInfoOld < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 25, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)ChunkInfoOld);
      v3 = Irp;
      goto LABEL_83;
    }
    LOBYTE(v12) = v3->RequestorMode;
    Consumer = UlpGetLogInfoOld(v3, v12, &v53, v58);
    if ( Consumer < 0 )
    {
      v3 = Irp;
      goto LABEL_83;
    }
    v8 = DWORD2(v55);
    v14 = BYTE8(v55) & 2;
    v44 = v14 == 0;
    if ( (BYTE8(v55) & 2) == 0 )
    {
      v9 = v55;
      v51 = v55;
      *((_QWORD *)&v59 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
      *(_QWORD *)&v59 = v55;
      v13 = *(_QWORD *)(*(_QWORD *)(v48 + 8) + 328LL);
      if ( (*(_BYTE *)(v13 + 1760) & 4) == 0 )
      {
LABEL_16:
        if ( v49 && v14 )
        {
          Consumer = -1073741811;
          v3 = Irp;
          v5 = 0;
          goto LABEL_83;
        }
        if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
        {
          WORD1(v42) = WORD1(v8);
          WPP_SF_iD(v13, 26);
        }
        RequestFromId = UlGetRequestFromId(v55, v48);
        v4 = RequestFromId;
        v52 = RequestFromId;
        if ( !RequestFromId )
        {
          Consumer = -1073741254;
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
            WPP_SF_d(774, 27, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, 3221226042LL);
          v3 = Irp;
          v5 = 0;
          goto LABEL_83;
        }
        v16 = *(_QWORD *)(RequestFromId + 24);
        if ( v16 )
        {
          v17 = *(_QWORD *)(v16 + 1096);
          if ( (*(_BYTE *)(v17 + 1760) & 4) != 0
            && (!*(_QWORD *)(v17 + 1776)
             || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(RequestFromId, v16, 0)) )
          {
            McTemplateK0xx_EtwWriteTransfer(
              *(_QWORD *)(*(_QWORD *)(v4 + 24) + 1096LL) + 1688LL,
              v16,
              v4 + 72,
              *(_QWORD *)(v4 + 56),
              *(_QWORD *)(*(_QWORD *)(v4 + 24) + 48LL));
          }
        }
        if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_ii(
            *(_QWORD *)(*(_QWORD *)(v4 + 24) + 48LL),
            v16,
            v8,
            *(_QWORD *)(v4 + 56),
            *(_QWORD *)(*(_QWORD *)(v4 + 24) + 48LL));
        if ( *(_QWORD *)(v4 + 2488) )
        {
          v18 = 0;
          KeEnterCriticalRegion();
          ExAcquirePushLockSharedEx(*(_QWORD *)(v4 + 24) + 576LL, 0);
          v19 = *(_QWORD *)(v4 + 2512);
          if ( v19 && !*(_DWORD *)(v19 + 136) )
            v18 = *(_DWORD *)(v19 + 256) == 1;
          ExReleasePushLockSharedEx(*(_QWORD *)(v4 + 24) + 576LL, 0);
          KeLeaveCriticalRegion();
        }
        else
        {
          v18 = 0;
        }
        if ( !v18
          && !*(_DWORD *)(v4 + 2212)
          && (BYTE8(v55) & 4) == 0
          && !(unsigned __int8)UlAutomaticChunkingTransformationNeeded(v4, DWORD2(v55)) )
        {
          UxTpIsFastSendPossible(*(_QWORD *)(v4 + 24) + 976LL);
        }
        v20 = !v14 || (BYTE8(v55) & 1) != 0;
        v21 = UlCaptureHttpResponseOld(
                v48,
                0,
                v4,
                (_DWORD)v3,
                0,
                (__int64)P,
                v3->RequestorMode,
                DWORD2(v55),
                0,
                0,
                v56,
                0,
                v20,
                v49,
                (__int64)&v46,
                (__int64)&v47);
        Consumer = v21;
        if ( v21 < 0 )
        {
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
            WPP_SF_d(774, 29, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v21);
          v3 = Irp;
          v5 = 0;
          goto LABEL_83;
        }
        if ( *(_DWORD *)(v4 + 2212) == 1 )
        {
          Consumer = 0;
          v3->IoStatus.Information = *(_QWORD *)(v47 + 520);
          v3 = Irp;
          v5 = 0;
          goto LABEL_83;
        }
        v22 = UlCheckSendResponseFlags(v4, DWORD2(v55), 0, 0, *(_BYTE *)(v47 + 64), 1);
        Consumer = v22;
        if ( v22 < 0 )
        {
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
            WPP_SF_d(774, 30, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v22);
          v3 = Irp;
          v5 = 0;
          goto LABEL_83;
        }
        v23 = UlCheckForZombieConnection(v4, *(_QWORD *)(v4 + 24), DWORD2(v55), v56, v3->RequestorMode);
        Consumer = v23;
        if ( v23 < 0 )
        {
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
            WPP_SF_d(774, 31, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v23);
          v3 = Irp;
          v5 = 0;
          goto LABEL_83;
        }
        if ( v47 )
        {
          if ( v56 )
          {
            if ( !v14 )
            {
              v24 = UlCaptureUserLogData(v56, v4, v47 + 512);
              Consumer = v24;
              if ( v24 < 0 )
              {
                if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
                  WPP_SF_d(774, 32, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v24);
                v3 = Irp;
                v5 = 0;
                goto LABEL_83;
              }
            }
          }
        }
        v5 = 0;
        if ( Consumer < 0 )
        {
LABEL_76:
          v3 = Irp;
          goto LABEL_83;
        }
        if ( (WORD4(v55) & 0x100) != 0 )
        {
          v25 = *(_QWORD *)(v4 + 24);
          if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
            WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v25 + 496, 51, 0, 0, 0, 0);
          v43 = 0;
          v42 = 0;
          v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(v25 + 504) + 136LL))(
                  *(_QWORD *)(v25 + 496),
                  51,
                  0);
          Consumer = v26;
          if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
            WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v26);
          if ( Consumer < 0 )
          {
LABEL_75:
            v5 = 1;
            goto LABEL_76;
          }
        }
        if ( (unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(v4 + 24), v3) )
        {
          *(_QWORD *)(v47 + 592) = v3;
          v27 = v47;
          v47 = 0;
          *(_BYTE *)(v27 + 51) = v18;
          v28 = UlSendHttpResponse(v4, v27, (unsigned int)UlRestartSendHttpResponseIoctl, v27, 0);
          Consumer = v28;
          if ( v28 != 259 )
          {
            UlRestartSendHttpResponseIoctl(v27, v28, 0);
            Consumer = 259;
            goto LABEL_75;
          }
        }
        else
        {
          Consumer = -1073741536;
        }
        v3 = Irp;
        v5 = 0;
        goto LABEL_83;
      }
      McTemplateK0x_EtwWriteTransfer(v13 + 1688, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY, &v59, v55);
      v8 = DWORD2(v55);
    }
    v9 = v51;
    goto LABEL_16;
  }
LABEL_83:
  if ( v4 )
  {
    if ( ((Consumer + 0x80000000) & 0x80000000) == 0 && Consumer != -1073741766 || v5 )
      UlCloseConnection(*(_QWORD *)(v4 + 24));
    v29 = v4 + 48;
    v30 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 48));
    if ( UxDebugCheckRefcount && v30 <= -1 )
      UlBugCheckEx(3u, v29, 0xBu, v30);
    if ( !v30 )
      UlpQueueFreeHttpRequest(v4, v29, v8, v9);
  }
  v31 = (_QWORD *)v47;
  if ( v47 )
  {
    v32 = _InterlockedDecrement((volatile signed __int32 *)(v47 + 20));
    if ( UxDebugCheckRefcount && v32 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v31 + 20, 1u, v32);
    if ( !v32 )
    {
      v33 = (__int64)(v31 + 76);
      v57 = 0;
      if ( v31[76] || v31[78] || v31[80] )
        UlBugCheckEx(1u, (ULONG_PTR)(v31 + 76), (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x453u);
      v34 = *(_QWORD *)(*(_QWORD *)(v31[3] + 24LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        LOBYTE(v35) = 1;
        UlThreadPoolEnqueueWorkItem(0, v33, UlDestroyCapturedResponse, v35, v34, -1);
      }
      else
      {
        UxPodAttachThread(v34, (__int64)&v57);
        UlDestroyCapturedResponse(v33, v36, v37, v38);
        UxPodDetachThread((__int64)&v57);
      }
    }
  }
  if ( v44 && ((Consumer + 0x80000000) & 0x80000000) == 0 && Consumer != -1073741766 )
  {
    v39 = *(_QWORD *)(*(_QWORD *)(v48 + 8) + 328LL);
    v40 = v51;
    if ( (*(_BYTE *)(v39 + 1760) & 0x20) != 0 )
    {
      LOWORD(v42) = v46;
      McTemplateK0xh_EtwWriteTransfer(v39 + 1688, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, &v59, v51, v42);
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
    {
      LOWORD(v43) = v46;
      WPP_SF_diH(v39, 34, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)Consumer, v40, v43);
    }
  }
  if ( Consumer != 259 )
  {
    v3->IoStatus.Status = Consumer;
    IofCompleteRequest(v3, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 35, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)Consumer);
  return (unsigned int)Consumer;
}

```

## disassembly

```asm
0x1400f3fdc  mov     r11, rsp
0x1400f3fdf  mov     [r11+18h], rbx
0x1400f3fe3  mov     [r11+20h], rsi
0x1400f3fe7  push    rdi
0x1400f3fe8  push    r12
0x1400f3fea  push    r13
0x1400f3fec  push    r14
0x1400f3fee  push    r15
0x1400f3ff0  sub     rsp, 310h
0x1400f3ff7  mov     rax, cs:__security_cookie
0x1400f3ffe  xor     rax, rsp
0x1400f4001  mov     [rsp+338h+var_38], rax
0x1400f4009  mov     r15, rdx
0x1400f400c  mov     r13, rcx
0x1400f400f  mov     [rsp+338h+var_2A8], rcx
0x1400f4017  mov     qword ptr [rsp+338h+var_228], rcx
0x1400f401f  xorps   xmm0, xmm0
0x1400f4022  xor     eax, eax
0x1400f4024  movups  [rsp+338h+var_260], xmm0
0x1400f402c  movups  [rsp+338h+var_250], xmm0
0x1400f4034  movups  [rsp+338h+var_240], xmm0
0x1400f403c  mov     [r11-230h], rax
0x1400f4043  xor     ebx, ebx
0x1400f4045  mov     [r11-290h], rbx
0x1400f404c  mov     esi, ebx
0x1400f404e  mov     [r11-268h], rbx
0x1400f4055  mov     [r11-288h], rbx
0x1400f405c  mov     r12b, bl
0x1400f405f  mov     [rsp+338h+var_2B8], bl
0x1400f4066  mov     [rsp+338h+var_2B2], bl
0x1400f406d  mov     [rsp+338h+var_2A0], bl
0x1400f4074  mov     [rsp+338h+var_2AC], eax
0x1400f407b  mov     [rsp+338h+var_2B6], al
0x1400f4082  mov     [r11-270h], rbx
0x1400f4089  mov     [r11-278h], rbx
0x1400f4090  mov     [rsp+338h+var_2B3], bl
0x1400f4097  xor     edx, edx; Val
0x1400f4099  mov     r8d, 90h; Size
0x1400f409f  lea     rcx, [r11-218h]; void *
0x1400f40a6  call    memset
0x1400f40ab  mov     [rsp+338h+var_298], bx
0x1400f40b3  xorps   xmm0, xmm0
0x1400f40b6  movups  [rsp+338h+var_188], xmm0
0x1400f40be  mov     [rsp+338h+var_2B5], bl
0x1400f40c5  mov     [rsp+338h+var_280], rbx
0x1400f40cd  mov     [rsp+338h+var_29C], bx
0x1400f40d5  mov     [rsp+338h+var_2B4], bl
0x1400f40dc  mov     [rsp+338h+var_29F], bl
0x1400f40e3  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400f40ea  jz      short loc_1400F4108
0x1400f40ec  lea     edx, [rbx+18h]
0x1400f40ef  mov     ecx, 409h
0x1400f40f4  mov     [rsp+338h+var_318], r15
0x1400f40f9  mov     r9, r13
0x1400f40fc  lea     r8, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids
0x1400f4103  call    WPP_SF_qq
0x1400f4108  lea     r8, [rsp+338h+var_288]
0x1400f4110  mov     r14d, 1
0x1400f4116  mov     edx, r14d
0x1400f4119  mov     rcx, [r15+30h]
0x1400f411d  call    UlGetConsumer
0x1400f4122  mov     edi, eax
0x1400f4124  test    eax, eax
0x1400f4126  js      loc_1400F49B9
0x1400f412c  lea     rax, [rsp+338h+var_260]
0x1400f4134  mov     [rsp+338h+var_318], rax
0x1400f4139  mov     r9d, [r15+10h]
0x1400f413d  mov     r8, [r15+20h]
0x1400f4141  mov     dl, [r13+40h]
0x1400f4145  mov     rcx, r13
0x1400f4148  call    UlpGetSendInfoOld
0x1400f414d  mov     edi, eax
0x1400f414f  mov     [rsp+338h+var_2B0], eax
0x1400f4156  test    eax, eax
0x1400f4158  jns     short loc_1400F4167
0x1400f415a  mov     r13, [rsp+338h+var_2A8]
0x1400f4162  jmp     loc_1400F49B9
0x1400f4167  lea     rax, [rsp+338h+var_29C]
0x1400f416f  mov     [rsp+338h+var_2E8], rax
0x1400f4174  lea     rax, [rsp+338h+var_2B4]
0x1400f417c  mov     [rsp+338h+var_2F0], rax
0x1400f4181  lea     rax, [rsp+338h+var_280]
0x1400f4189  mov     [rsp+338h+var_2F8], rax
0x1400f418e  lea     rax, [rsp+338h+var_2B3]
0x1400f4196  mov     [rsp+338h+var_300], rax
0x1400f419b  lea     rax, [rsp+338h+P]
0x1400f41a3  mov     [rsp+338h+var_308], rax
0x1400f41a8  lea     rax, [rsp+338h+var_178]
0x1400f41b0  mov     [rsp+338h+var_310], rax
0x1400f41b5  mov     r9, qword ptr [rsp+338h+var_250]
0x1400f41bd  movzx   r8d, word ptr [rsp+338h+var_260+8]
0x1400f41c6  mov     dl, [r13+40h]
0x1400f41ca  mov     rcx, r13
0x1400f41cd  call    UlpGetChunkInfoOld
0x1400f41d2  mov     edi, eax
0x1400f41d4  mov     [rsp+338h+var_2B0], eax
0x1400f41db  test    eax, eax
0x1400f41dd  jns     short loc_1400F420E
0x1400f41df  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400f41e6  jz      short loc_1400F4201
0x1400f41e8  mov     edx, 19h
0x1400f41ed  mov     ecx, 306h
0x1400f41f2  mov     r9d, eax
0x1400f41f5  lea     r8, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids
0x1400f41fc  call    WPP_SF_d
0x1400f4201  mov     r13, [rsp+338h+var_2A8]
0x1400f4209  jmp     loc_1400F49B9
0x1400f420e  lea     r9, [rsp+338h+var_218]
0x1400f4216  lea     r8, [rsp+338h+var_260]
0x1400f421e  mov     dl, [r13+40h]
0x1400f4222  mov     rcx, r13
0x1400f4225  call    UlpGetLogInfoOld
0x1400f422a  mov     edi, eax
0x1400f422c  mov     [rsp+338h+var_2B0], eax
0x1400f4233  test    eax, eax
0x1400f4235  jns     short loc_1400F4244
0x1400f4237  mov     r13, [rsp+338h+var_2A8]
0x1400f423f  jmp     loc_1400F49B9
0x1400f4244  mov     r8d, dword ptr [rsp+338h+var_240+8]
0x1400f424c  mov     r12d, r8d
0x1400f424f  and     r12d, 2
0x1400f4253  setz    [rsp+338h+var_2B2]
0x1400f425b  test    r12d, r12d
0x1400f425e  jnz     short loc_1400F42C7
0x1400f4260  mov     r9, qword ptr [rsp+338h+var_240]
0x1400f4268  mov     [rsp+338h+var_270], r9
0x1400f4270  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1400f4277  movdqu  [rsp+338h+var_188], xmm0
0x1400f4280  mov     qword ptr [rsp+338h+var_188], r9
0x1400f4288  mov     rax, [rsp+338h+var_288]
0x1400f4290  mov     rcx, [rax+8]
0x1400f4294  mov     rcx, [rcx+148h]
0x1400f429b  test    byte ptr [rcx+6E0h], 4
0x1400f42a2  jz      short loc_1400F42CF
0x1400f42a4  add     rcx, 698h
0x1400f42ab  lea     r8, [rsp+338h+var_188]
0x1400f42b3  lea     rdx, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY
0x1400f42ba  call    McTemplateK0x_EtwWriteTransfer
0x1400f42bf  mov     r8d, dword ptr [rsp+338h+var_240+8]
0x1400f42c7  mov     r9, [rsp+338h+var_270]
0x1400f42cf  cmp     [rsp+338h+var_280], rbx
0x1400f42d7  jz      short loc_1400F42FF
0x1400f42d9  test    r12d, r12d
0x1400f42dc  jz      short loc_1400F42FF
0x1400f42de  mov     edi, 0C000000Dh
0x1400f42e3  mov     [rsp+338h+var_2B0], edi
0x1400f42ea  mov     r13, [rsp+338h+var_2A8]
0x1400f42f2  mov     r12b, [rsp+338h+var_2B8]
0x1400f42fa  jmp     loc_1400F49B9
0x1400f42ff  mov     [rsp+338h+var_2B0], ebx
0x1400f4306  test    byte ptr cs:xmmword_1401A2CA0+2, r14b
0x1400f430d  jz      short loc_1400F431E
0x1400f430f  mov     edx, 1Ah
0x1400f4314  mov     dword ptr [rsp+338h+var_318], r8d
0x1400f4319  call    WPP_SF_iD
0x1400f431e  mov     rdx, [rsp+338h+var_288]
0x1400f4326  mov     rcx, qword ptr [rsp+338h+var_240]
0x1400f432e  call    UlGetRequestFromId
0x1400f4333  mov     rsi, rax
0x1400f4336  mov     [rsp+338h+var_268], rax
0x1400f433e  test    rax, rax
0x1400f4341  jnz     short loc_1400F4384
0x1400f4343  mov     edi, 0C000023Ah
0x1400f4348  mov     [rsp+338h+var_2B0], edi
0x1400f434f  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400f4356  jz      short loc_1400F436F
0x1400f4358  lea     edx, [rax+1Bh]
0x1400f435b  mov     ecx, 306h
0x1400f4360  mov     r9d, edi
0x1400f4363  lea     r8, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids
0x1400f436a  call    WPP_SF_d
0x1400f436f  mov     r13, [rsp+338h+var_2A8]
0x1400f4377  mov     r12b, [rsp+338h+var_2B8]
0x1400f437f  jmp     loc_1400F49B9
0x1400f4384  mov     rdx, [rax+18h]
0x1400f4388  test    rdx, rdx
0x1400f438b  jz      short loc_1400F43DD
0x1400f438d  mov     rcx, [rdx+448h]
0x1400f4394  test    byte ptr [rcx+6E0h], 4
0x1400f439b  jz      short loc_1400F43DD
0x1400f439d  cmp     [rcx+6F0h], rbx
0x1400f43a4  jz      short loc_1400F43B5
0x1400f43a6  xor     r8d, r8d
0x1400f43a9  mov     rcx, rsi
0x1400f43ac  call    UlEtwEvaluateFilterForRequestConnection
0x1400f43b1  test    al, al
0x1400f43b3  jz      short loc_1400F43DD
0x1400f43b5  mov     rax, [rsi+18h]
0x1400f43b9  lea     r8, [rsi+48h]
0x1400f43bd  mov     rcx, [rax+448h]
0x1400f43c4  add     rcx, 698h
0x1400f43cb  mov     rax, [rax+30h]
0x1400f43cf  mov     [rsp+338h+var_318], rax
0x1400f43d4  mov     r9, [rsi+38h]
0x1400f43d8  call    McTemplateK0xx_EtwWriteTransfer
0x1400f43dd  test    byte ptr cs:xmmword_1401A2CA0+2, r14b
0x1400f43e4  jz      short loc_1400F43FC
0x1400f43e6  mov     rax, [rsi+18h]
0x1400f43ea  mov     rcx, [rax+30h]
0x1400f43ee  mov     [rsp+338h+var_318], rcx
0x1400f43f3  mov     r9, [rsi+38h]
0x1400f43f7  call    WPP_SF_ii
0x1400f43fc  mov     [rsp+338h+var_2B7], bl
0x1400f4403  cmp     [rsi+9B8h], rbx
0x1400f440a  jnz     short loc_1400F4411
0x1400f440c  mov     r15b, bl
0x1400f440f  jmp     short loc_1400F448B
0x1400f4411  movzx   r15d, bl
0x1400f4415  mov     [rsp+338h+var_2B7], r15b
0x1400f441d  call    cs:__imp_KeEnterCriticalRegion
0x1400f4424  nop     dword ptr [rax+rax+00h]
0x1400f4429  mov     rcx, [rsi+18h]
0x1400f442d  mov     edi, 240h
0x1400f4432  add     rcx, rdi
0x1400f4435  xor     edx, edx
0x1400f4437  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400f443e  nop     dword ptr [rax+rax+00h]
0x1400f4443  mov     rax, [rsi+9D0h]
0x1400f444a  test    rax, rax
0x1400f444d  jz      short loc_1400F446A
0x1400f444f  cmp     [rax+88h], ebx
0x1400f4455  jnz     short loc_1400F446A
0x1400f4457  cmp     [rax+100h], r14d
0x1400f445e  cmovz   r15d, r14d
0x1400f4462  mov     [rsp+338h+var_2B7], r15b
0x1400f446a  mov     rcx, [rsi+18h]
0x1400f446e  add     rcx, rdi
0x1400f4471  xor     edx, edx
0x1400f4473  call    cs:__imp_ExReleasePushLockSharedEx
0x1400f447a  nop     dword ptr [rax+rax+00h]
0x1400f447f  call    cs:__imp_KeLeaveCriticalRegion
0x1400f4486  nop     dword ptr [rax+rax+00h]
0x1400f448b  mov     [rsp+338h+var_2B5], r15b
0x1400f4493  test    r15b, r15b
0x1400f4496  jnz     short loc_1400F450E
0x1400f4498  cmp     [rsi+8A4h], ebx
0x1400f449e  jnz     short loc_1400F450E
0x1400f44a0  mov     edx, dword ptr [rsp+338h+var_240+8]
0x1400f44a7  test    dl, 4
0x1400f44aa  jnz     short loc_1400F450E
0x1400f44ac  mov     rcx, rsi
0x1400f44af  call    UlAutomaticChunkingTransformationNeeded
0x1400f44b4  test    al, al
0x1400f44b6  jnz     short loc_1400F450E
0x1400f44b8  mov     rcx, [rsi+18h]
0x1400f44bc  add     rcx, 3D0h
0x1400f44c3  call    UxTpIsFastSendPossible
0x1400f44c8  test    al, al
0x1400f44ca  jz      short loc_1400F450E
0x1400f44cc  cmp     [rsp+338h+var_29C], r14w
0x1400f44d5  jnz     short loc_1400F450E
0x1400f44d7  mov     r8, [rsp+338h+P]
0x1400f44df  mov     ecx, [rsp+338h+var_2AC]
0x1400f44e6  cmp     [r8], ebx
0x1400f44e9  jnz     short loc_1400F4515
0x1400f44eb  mov     eax, [r8+10h]
0x1400f44ef  sub     eax, r14d
0x1400f44f2  movzx   ecx, cl
0x1400f44f5  cmp     eax, 0FFFFh
0x1400f44fa  cmovbe  ecx, r14d
0x1400f44fe  mov     [rsp+338h+var_2AC], ecx
0x1400f4505  mov     [rsp+338h+var_2B6], cl
0x1400f450c  jmp     short loc_1400F4515
0x1400f450e  mov     ecx, [rsp+338h+var_2AC]
0x1400f4515  test    r12d, r12d
0x1400f4518  jz      short loc_1400F4524
0x1400f451a  test    byte ptr [rsp+338h+var_240+8], r14b
0x1400f4522  jz      short loc_1400F4529
0x1400f4524  mov     dl, r14b
0x1400f4527  jmp     short loc_1400F4530
0x1400f4529  mov     dl, [rsp+338h+var_2A0]
0x1400f4530  test    cl, cl
0x1400f4532  jnz     loc_1400F460F
0x1400f4538  lea     rax, [rsp+338h+var_290]
0x1400f4540  mov     [rsp+338h+var_2C0], rax
0x1400f4545  lea     rax, [rsp+338h+var_298]
0x1400f454d  mov     [rsp+338h+var_2C8], rax
0x1400f4552  mov     rax, [rsp+338h+var_280]
0x1400f455a  mov     [rsp+338h+var_2D0], rax
0x1400f455f  mov     byte ptr [rsp+338h+var_2D8], dl
0x1400f4563  mov     [rsp+338h+var_2E0], bl
0x1400f4567  mov     rax, [rsp+338h+var_230]
0x1400f456f  mov     [rsp+338h+var_2E8], rax
0x1400f4574  mov     byte ptr [rsp+338h+var_2F0], bl
0x1400f4578  mov     byte ptr [rsp+338h+var_2F8], bl
0x1400f457c  mov     eax, dword ptr [rsp+338h+var_240+8]
0x1400f4583  mov     dword ptr [rsp+338h+var_300], eax
0x1400f4587  mov     al, [r13+40h]
0x1400f458b  mov     byte ptr [rsp+338h+var_308], al
0x1400f458f  mov     rax, [rsp+338h+P]
0x1400f4597  mov     [rsp+338h+var_310], rax
0x1400f459c  movzx   eax, [rsp+338h+var_29C]
0x1400f45a4  mov     word ptr [rsp+338h+var_318], ax
0x1400f45a9  mov     r9, r13
0x1400f45ac  mov     r8, rsi
0x1400f45af  xor     edx, edx
0x1400f45b1  mov     rcx, [rsp+338h+var_288]
0x1400f45b9  call    UlCaptureHttpResponseOld
0x1400f45be  mov     edi, eax
0x1400f45c0  mov     [rsp+338h+var_2B0], eax
  ... truncated ...
```
