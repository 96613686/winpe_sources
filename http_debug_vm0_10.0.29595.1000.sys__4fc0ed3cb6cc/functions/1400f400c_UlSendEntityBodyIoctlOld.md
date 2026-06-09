# UlSendEntityBodyIoctlOld

- ea: `0x1400f400c`
- end: `0x1400f4c98`
- name: `UlSendEntityBodyIoctlOld`
- size: `3212`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x1400f1ae0`

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
- `0x140033830`
- `0x1400354a0`
- `0x140035a50`
- `0x140039340`
- `0x1400474d0`
- `0x140062bd0`
- `0x14008aaf0`
- `0x14009da24`
- `0x1400aa0f8`
- `0x1400b1acc`
- `0x1400b379c`
- `0x1400e35c0`
- `0x1400ee304`
- `0x1400f400c`
- `0x1400fce98`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c49c4`
- `0x1401cdb74`
- `0x1401ce090`
- `0x1401ce0e0`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400f4b11`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f4b11`
- `ntoskrnl!IofCompleteRequest` at `0x1400f4bfb`
- `ntoskrnl!IofCompleteRequest` at `0x1400f4bfb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f44af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f44af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f4a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f4a1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f4a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f4a1f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f4467`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f4467`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f44a3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f44a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f444d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f444d`

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
0x1400f400c  mov     r11, rsp
0x1400f400f  mov     [r11+18h], rbx
0x1400f4013  mov     [r11+20h], rsi
0x1400f4017  push    rdi
0x1400f4018  push    r12
0x1400f401a  push    r13
0x1400f401c  push    r14
0x1400f401e  push    r15
0x1400f4020  sub     rsp, 310h
0x1400f4027  mov     rax, cs:__security_cookie
0x1400f402e  xor     rax, rsp
0x1400f4031  mov     [rsp+338h+var_38], rax
0x1400f4039  mov     r15, rdx
0x1400f403c  mov     r13, rcx
0x1400f403f  mov     [rsp+338h+var_2A8], rcx
0x1400f4047  mov     qword ptr [rsp+338h+var_228], rcx
0x1400f404f  xorps   xmm0, xmm0
0x1400f4052  xor     eax, eax
0x1400f4054  movups  [rsp+338h+var_260], xmm0
0x1400f405c  movups  [rsp+338h+var_250], xmm0
0x1400f4064  movups  [rsp+338h+var_240], xmm0
0x1400f406c  mov     [r11-230h], rax
0x1400f4073  xor     ebx, ebx
0x1400f4075  mov     [r11-290h], rbx
0x1400f407c  mov     esi, ebx
0x1400f407e  mov     [r11-268h], rbx
0x1400f4085  mov     [r11-288h], rbx
0x1400f408c  mov     r12b, bl
0x1400f408f  mov     [rsp+338h+var_2B8], bl
0x1400f4096  mov     [rsp+338h+var_2B2], bl
0x1400f409d  mov     [rsp+338h+var_2A0], bl
0x1400f40a4  mov     [rsp+338h+var_2AC], eax
0x1400f40ab  mov     [rsp+338h+var_2B6], al
0x1400f40b2  mov     [r11-270h], rbx
0x1400f40b9  mov     [r11-278h], rbx
0x1400f40c0  mov     [rsp+338h+var_2B3], bl
0x1400f40c7  xor     edx, edx; Val
0x1400f40c9  mov     r8d, 90h; Size
0x1400f40cf  lea     rcx, [r11-218h]; void *
0x1400f40d6  call    memset
0x1400f40db  mov     [rsp+338h+var_298], bx
0x1400f40e3  xorps   xmm0, xmm0
0x1400f40e6  movups  [rsp+338h+var_188], xmm0
0x1400f40ee  mov     [rsp+338h+var_2B5], bl
0x1400f40f5  mov     [rsp+338h+var_280], rbx
0x1400f40fd  mov     [rsp+338h+var_29C], bx
0x1400f4105  mov     [rsp+338h+var_2B4], bl
0x1400f410c  mov     [rsp+338h+var_29F], bl
0x1400f4113  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400f411a  jz      short loc_1400F4138
0x1400f411c  lea     edx, [rbx+18h]
0x1400f411f  mov     ecx, 409h
0x1400f4124  mov     [rsp+338h+var_318], r15
0x1400f4129  mov     r9, r13
0x1400f412c  lea     r8, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids
0x1400f4133  call    WPP_SF_qq
0x1400f4138  lea     r8, [rsp+338h+var_288]
0x1400f4140  mov     r14d, 1
0x1400f4146  mov     edx, r14d
0x1400f4149  mov     rcx, [r15+30h]
0x1400f414d  call    UlGetConsumer
0x1400f4152  mov     edi, eax
0x1400f4154  test    eax, eax
0x1400f4156  js      loc_1400F49E9
0x1400f415c  lea     rax, [rsp+338h+var_260]
0x1400f4164  mov     [rsp+338h+var_318], rax
0x1400f4169  mov     r9d, [r15+10h]
0x1400f416d  mov     r8, [r15+20h]
0x1400f4171  mov     dl, [r13+40h]
0x1400f4175  mov     rcx, r13
0x1400f4178  call    UlpGetSendInfoOld
0x1400f417d  mov     edi, eax
0x1400f417f  mov     [rsp+338h+var_2B0], eax
0x1400f4186  test    eax, eax
0x1400f4188  jns     short loc_1400F4197
0x1400f418a  mov     r13, [rsp+338h+var_2A8]
0x1400f4192  jmp     loc_1400F49E9
0x1400f4197  lea     rax, [rsp+338h+var_29C]
0x1400f419f  mov     [rsp+338h+var_2E8], rax
0x1400f41a4  lea     rax, [rsp+338h+var_2B4]
0x1400f41ac  mov     [rsp+338h+var_2F0], rax
0x1400f41b1  lea     rax, [rsp+338h+var_280]
0x1400f41b9  mov     [rsp+338h+var_2F8], rax
0x1400f41be  lea     rax, [rsp+338h+var_2B3]
0x1400f41c6  mov     [rsp+338h+var_300], rax
0x1400f41cb  lea     rax, [rsp+338h+P]
0x1400f41d3  mov     [rsp+338h+var_308], rax
0x1400f41d8  lea     rax, [rsp+338h+var_178]
0x1400f41e0  mov     [rsp+338h+var_310], rax
0x1400f41e5  mov     r9, qword ptr [rsp+338h+var_250]
0x1400f41ed  movzx   r8d, word ptr [rsp+338h+var_260+8]
0x1400f41f6  mov     dl, [r13+40h]
0x1400f41fa  mov     rcx, r13
0x1400f41fd  call    UlpGetChunkInfoOld
0x1400f4202  mov     edi, eax
0x1400f4204  mov     [rsp+338h+var_2B0], eax
0x1400f420b  test    eax, eax
0x1400f420d  jns     short loc_1400F423E
0x1400f420f  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400f4216  jz      short loc_1400F4231
0x1400f4218  mov     edx, 19h
0x1400f421d  mov     ecx, 306h
0x1400f4222  mov     r9d, eax
0x1400f4225  lea     r8, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids
0x1400f422c  call    WPP_SF_d
0x1400f4231  mov     r13, [rsp+338h+var_2A8]
0x1400f4239  jmp     loc_1400F49E9
0x1400f423e  lea     r9, [rsp+338h+var_218]
0x1400f4246  lea     r8, [rsp+338h+var_260]
0x1400f424e  mov     dl, [r13+40h]
0x1400f4252  mov     rcx, r13
0x1400f4255  call    UlpGetLogInfoOld
0x1400f425a  mov     edi, eax
0x1400f425c  mov     [rsp+338h+var_2B0], eax
0x1400f4263  test    eax, eax
0x1400f4265  jns     short loc_1400F4274
0x1400f4267  mov     r13, [rsp+338h+var_2A8]
0x1400f426f  jmp     loc_1400F49E9
0x1400f4274  mov     r8d, dword ptr [rsp+338h+var_240+8]
0x1400f427c  mov     r12d, r8d
0x1400f427f  and     r12d, 2
0x1400f4283  setz    [rsp+338h+var_2B2]
0x1400f428b  test    r12d, r12d
0x1400f428e  jnz     short loc_1400F42F7
0x1400f4290  mov     r9, qword ptr [rsp+338h+var_240]
0x1400f4298  mov     [rsp+338h+var_270], r9
0x1400f42a0  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1400f42a7  movdqu  [rsp+338h+var_188], xmm0
0x1400f42b0  mov     qword ptr [rsp+338h+var_188], r9
0x1400f42b8  mov     rax, [rsp+338h+var_288]
0x1400f42c0  mov     rcx, [rax+8]
0x1400f42c4  mov     rcx, [rcx+148h]
0x1400f42cb  test    byte ptr [rcx+6E0h], 4
0x1400f42d2  jz      short loc_1400F42FF
0x1400f42d4  add     rcx, 698h
0x1400f42db  lea     r8, [rsp+338h+var_188]
0x1400f42e3  lea     rdx, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY
0x1400f42ea  call    McTemplateK0x_EtwWriteTransfer
0x1400f42ef  mov     r8d, dword ptr [rsp+338h+var_240+8]
0x1400f42f7  mov     r9, [rsp+338h+var_270]
0x1400f42ff  cmp     [rsp+338h+var_280], rbx
0x1400f4307  jz      short loc_1400F432F
0x1400f4309  test    r12d, r12d
0x1400f430c  jz      short loc_1400F432F
0x1400f430e  mov     edi, 0C000000Dh
0x1400f4313  mov     [rsp+338h+var_2B0], edi
0x1400f431a  mov     r13, [rsp+338h+var_2A8]
0x1400f4322  mov     r12b, [rsp+338h+var_2B8]
0x1400f432a  jmp     loc_1400F49E9
0x1400f432f  mov     [rsp+338h+var_2B0], ebx
0x1400f4336  test    byte ptr cs:xmmword_1401A2CA0+2, r14b
0x1400f433d  jz      short loc_1400F434E
0x1400f433f  mov     edx, 1Ah
0x1400f4344  mov     dword ptr [rsp+338h+var_318], r8d
0x1400f4349  call    WPP_SF_iD
0x1400f434e  mov     rdx, [rsp+338h+var_288]
0x1400f4356  mov     rcx, qword ptr [rsp+338h+var_240]
0x1400f435e  call    UlGetRequestFromId
0x1400f4363  mov     rsi, rax
0x1400f4366  mov     [rsp+338h+var_268], rax
0x1400f436e  test    rax, rax
0x1400f4371  jnz     short loc_1400F43B4
0x1400f4373  mov     edi, 0C000023Ah
0x1400f4378  mov     [rsp+338h+var_2B0], edi
0x1400f437f  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400f4386  jz      short loc_1400F439F
0x1400f4388  lea     edx, [rax+1Bh]
0x1400f438b  mov     ecx, 306h
0x1400f4390  mov     r9d, edi
0x1400f4393  lea     r8, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids
0x1400f439a  call    WPP_SF_d
0x1400f439f  mov     r13, [rsp+338h+var_2A8]
0x1400f43a7  mov     r12b, [rsp+338h+var_2B8]
0x1400f43af  jmp     loc_1400F49E9
0x1400f43b4  mov     rdx, [rax+18h]
0x1400f43b8  test    rdx, rdx
0x1400f43bb  jz      short loc_1400F440D
0x1400f43bd  mov     rcx, [rdx+448h]
0x1400f43c4  test    byte ptr [rcx+6E0h], 4
0x1400f43cb  jz      short loc_1400F440D
0x1400f43cd  cmp     [rcx+6F0h], rbx
0x1400f43d4  jz      short loc_1400F43E5
0x1400f43d6  xor     r8d, r8d
0x1400f43d9  mov     rcx, rsi
0x1400f43dc  call    UlEtwEvaluateFilterForRequestConnection
0x1400f43e1  test    al, al
0x1400f43e3  jz      short loc_1400F440D
0x1400f43e5  mov     rax, [rsi+18h]
0x1400f43e9  lea     r8, [rsi+48h]
0x1400f43ed  mov     rcx, [rax+448h]
0x1400f43f4  add     rcx, 698h
0x1400f43fb  mov     rax, [rax+30h]
0x1400f43ff  mov     [rsp+338h+var_318], rax
0x1400f4404  mov     r9, [rsi+38h]
0x1400f4408  call    McTemplateK0xx_EtwWriteTransfer
0x1400f440d  test    byte ptr cs:xmmword_1401A2CA0+2, r14b
0x1400f4414  jz      short loc_1400F442C
0x1400f4416  mov     rax, [rsi+18h]
0x1400f441a  mov     rcx, [rax+30h]
0x1400f441e  mov     [rsp+338h+var_318], rcx
0x1400f4423  mov     r9, [rsi+38h]
0x1400f4427  call    WPP_SF_ii
0x1400f442c  mov     [rsp+338h+var_2B7], bl
0x1400f4433  cmp     [rsi+9B8h], rbx
0x1400f443a  jnz     short loc_1400F4441
0x1400f443c  mov     r15b, bl
0x1400f443f  jmp     short loc_1400F44BB
0x1400f4441  movzx   r15d, bl
0x1400f4445  mov     [rsp+338h+var_2B7], r15b
0x1400f444d  call    cs:__imp_KeEnterCriticalRegion
0x1400f4454  nop     dword ptr [rax+rax+00h]
0x1400f4459  mov     rcx, [rsi+18h]
0x1400f445d  mov     edi, 240h
0x1400f4462  add     rcx, rdi
0x1400f4465  xor     edx, edx
0x1400f4467  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400f446e  nop     dword ptr [rax+rax+00h]
0x1400f4473  mov     rax, [rsi+9D0h]
0x1400f447a  test    rax, rax
0x1400f447d  jz      short loc_1400F449A
0x1400f447f  cmp     [rax+88h], ebx
0x1400f4485  jnz     short loc_1400F449A
0x1400f4487  cmp     [rax+100h], r14d
0x1400f448e  cmovz   r15d, r14d
0x1400f4492  mov     [rsp+338h+var_2B7], r15b
0x1400f449a  mov     rcx, [rsi+18h]
0x1400f449e  add     rcx, rdi
0x1400f44a1  xor     edx, edx
0x1400f44a3  call    cs:__imp_ExReleasePushLockSharedEx
0x1400f44aa  nop     dword ptr [rax+rax+00h]
0x1400f44af  call    cs:__imp_KeLeaveCriticalRegion
0x1400f44b6  nop     dword ptr [rax+rax+00h]
0x1400f44bb  mov     [rsp+338h+var_2B5], r15b
0x1400f44c3  test    r15b, r15b
0x1400f44c6  jnz     short loc_1400F453E
0x1400f44c8  cmp     [rsi+8A4h], ebx
0x1400f44ce  jnz     short loc_1400F453E
0x1400f44d0  mov     edx, dword ptr [rsp+338h+var_240+8]
0x1400f44d7  test    dl, 4
0x1400f44da  jnz     short loc_1400F453E
0x1400f44dc  mov     rcx, rsi
0x1400f44df  call    UlAutomaticChunkingTransformationNeeded
0x1400f44e4  test    al, al
0x1400f44e6  jnz     short loc_1400F453E
0x1400f44e8  mov     rcx, [rsi+18h]
0x1400f44ec  add     rcx, 3D0h
0x1400f44f3  call    UxTpIsFastSendPossible
0x1400f44f8  test    al, al
0x1400f44fa  jz      short loc_1400F453E
0x1400f44fc  cmp     [rsp+338h+var_29C], r14w
0x1400f4505  jnz     short loc_1400F453E
0x1400f4507  mov     r8, [rsp+338h+P]
0x1400f450f  mov     ecx, [rsp+338h+var_2AC]
0x1400f4516  cmp     [r8], ebx
0x1400f4519  jnz     short loc_1400F4545
0x1400f451b  mov     eax, [r8+10h]
0x1400f451f  sub     eax, r14d
0x1400f4522  movzx   ecx, cl
0x1400f4525  cmp     eax, 0FFFFh
0x1400f452a  cmovbe  ecx, r14d
0x1400f452e  mov     [rsp+338h+var_2AC], ecx
0x1400f4535  mov     [rsp+338h+var_2B6], cl
0x1400f453c  jmp     short loc_1400F4545
0x1400f453e  mov     ecx, [rsp+338h+var_2AC]
0x1400f4545  test    r12d, r12d
0x1400f4548  jz      short loc_1400F4554
0x1400f454a  test    byte ptr [rsp+338h+var_240+8], r14b
0x1400f4552  jz      short loc_1400F4559
0x1400f4554  mov     dl, r14b
0x1400f4557  jmp     short loc_1400F4560
0x1400f4559  mov     dl, [rsp+338h+var_2A0]
0x1400f4560  test    cl, cl
0x1400f4562  jnz     loc_1400F463F
0x1400f4568  lea     rax, [rsp+338h+var_290]
0x1400f4570  mov     [rsp+338h+var_2C0], rax
0x1400f4575  lea     rax, [rsp+338h+var_298]
0x1400f457d  mov     [rsp+338h+var_2C8], rax
0x1400f4582  mov     rax, [rsp+338h+var_280]
0x1400f458a  mov     [rsp+338h+var_2D0], rax
0x1400f458f  mov     byte ptr [rsp+338h+var_2D8], dl
0x1400f4593  mov     [rsp+338h+var_2E0], bl
0x1400f4597  mov     rax, [rsp+338h+var_230]
0x1400f459f  mov     [rsp+338h+var_2E8], rax
0x1400f45a4  mov     byte ptr [rsp+338h+var_2F0], bl
0x1400f45a8  mov     byte ptr [rsp+338h+var_2F8], bl
0x1400f45ac  mov     eax, dword ptr [rsp+338h+var_240+8]
0x1400f45b3  mov     dword ptr [rsp+338h+var_300], eax
0x1400f45b7  mov     al, [r13+40h]
0x1400f45bb  mov     byte ptr [rsp+338h+var_308], al
0x1400f45bf  mov     rax, [rsp+338h+P]
0x1400f45c7  mov     [rsp+338h+var_310], rax
0x1400f45cc  movzx   eax, [rsp+338h+var_29C]
0x1400f45d4  mov     word ptr [rsp+338h+var_318], ax
0x1400f45d9  mov     r9, r13
0x1400f45dc  mov     r8, rsi
0x1400f45df  xor     edx, edx
0x1400f45e1  mov     rcx, [rsp+338h+var_288]
0x1400f45e9  call    UlCaptureHttpResponseOld
0x1400f45ee  mov     edi, eax
0x1400f45f0  mov     [rsp+338h+var_2B0], eax
  ... truncated ...
```
