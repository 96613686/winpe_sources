# DrvEnableDriver

- ea: `0x140036b30`
- end: `0x140037075`
- name: `DrvEnableDriver`
- size: `1349`
- prototype: `FN_DrvEnableDriver`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x14002a6b0`
- `0x140034460`
- `0x140034f70`
- `0x140036a20`
- `0x140036ab8`
- `0x140036b30`
- `0x140037340`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ZwSetSystemInformation` at `0x140036d14`
- `ntoskrnl!ZwSetSystemInformation` at `0x140036d14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140036cfa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140036cfa`
- `watchdog!WdLogSingleEntry2` at `0x140036d2d`
- `watchdog!WdLogSingleEntry2` at `0x140036d2d`
- `watchdog!WdLogSingleEntry1` at `0x140036bb4`
- `watchdog!WdLogSingleEntry1` at `0x140036bb4`
- `watchdog!WdLogNewEntry5_WdError` at `0x140036bcb`
- `watchdog!WdLogNewEntry5_WdError` at `0x140036db9`
- `watchdog!WdLogNewEntry5_WdError` at `0x140036bcb`
- `watchdog!WdLogNewEntry5_WdError` at `0x140036db9`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140036b78`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140036b78`
- `watchdog!WdLogSingleEntry0` at `0x140036b61`
- `watchdog!WdLogSingleEntry0` at `0x140036da2`
- `watchdog!WdLogSingleEntry0` at `0x140036e3b`
- `watchdog!WdLogSingleEntry0` at `0x140036ea4`
- `watchdog!WdLogSingleEntry0` at `0x140036ed8`
- `watchdog!WdLogSingleEntry0` at `0x140036f0c`
- `watchdog!WdLogSingleEntry0` at `0x140036f5a`
- `watchdog!WdLogSingleEntry0` at `0x140036f91`
- `watchdog!WdLogSingleEntry0` at `0x140036fc8`
- `watchdog!WdLogSingleEntry0` at `0x140036fff`
- `watchdog!WdLogSingleEntry0` at `0x140037029`
- `watchdog!WdLogSingleEntry0` at `0x140036b61`
- `watchdog!WdLogSingleEntry0` at `0x140036da2`
- `watchdog!WdLogSingleEntry0` at `0x140036e3b`
- `watchdog!WdLogSingleEntry0` at `0x140036ea4`
- `watchdog!WdLogSingleEntry0` at `0x140036ed8`
- `watchdog!WdLogSingleEntry0` at `0x140036f0c`
- `watchdog!WdLogSingleEntry0` at `0x140036f5a`
- `watchdog!WdLogSingleEntry0` at `0x140036f91`
- `watchdog!WdLogSingleEntry0` at `0x140036fc8`
- `watchdog!WdLogSingleEntry0` at `0x140036fff`
- `watchdog!WdLogSingleEntry0` at `0x140037029`
- `WIN32K!W32GetSessionState` at `0x140036c1f`
- `WIN32K!W32GetSessionState` at `0x140036c41`
- `WIN32K!W32GetSessionState` at `0x140036c64`
- `WIN32K!W32GetSessionState` at `0x140036c9f`
- `WIN32K!W32GetSessionState` at `0x140036cb6`
- `WIN32K!W32GetSessionState` at `0x140036d43`
- `WIN32K!W32GetSessionState` at `0x140036d5e`
- `WIN32K!W32GetSessionState` at `0x140036df6`
- `WIN32K!W32GetSessionState` at `0x140036c1f`
- `WIN32K!W32GetSessionState` at `0x140036c41`
- `WIN32K!W32GetSessionState` at `0x140036c64`
- `WIN32K!W32GetSessionState` at `0x140036c9f`
- `WIN32K!W32GetSessionState` at `0x140036cb6`
- `WIN32K!W32GetSessionState` at `0x140036d43`
- `WIN32K!W32GetSessionState` at `0x140036d5e`
- `WIN32K!W32GetSessionState` at `0x140036df6`
- `WIN32K!EngCreateSemaphore` at `0x140036c90`
- `WIN32K!EngCreateSemaphore` at `0x140036c90`

## pseudocode

```c
BOOL __stdcall DrvEnableDriver(ULONG iEngineVersion, ULONG cj, DRVENABLEDATA *pded)
{
  _QWORD *v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  _QWORD *v11; // rax
  int updated; // ebx
  DRVFN *v14; // r12
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 SessionState; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  HSEMAPHORE Semaphore; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // r14d
  const WCHAR *v27; // rdx
  NTSTATUS v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // edi
  _QWORD *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  ULONG c; // eax
  DRVFN *v42; // [rsp+40h] [rbp-39h] BYREF
  int v43; // [rsp+48h] [rbp-31h]
  ULONG v44; // [rsp+4Ch] [rbp-2Dh]
  __int128 v45; // [rsp+50h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString[7]; // [rsp+60h] [rbp-19h] BYREF

  if ( cj < 0x10 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2986;
    v6 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 2986;
  }
  v7 = CddSessionDataAccessor<CddSessionData>::AddSessionReference();
  if ( v7 < 0 )
  {
    WdLogSingleEntry1(2, v7);
    v10 = 2993;
LABEL_5:
    WdLogGlobalForLineNumber = v10;
    v11 = (_QWORD *)WdLogNewEntry5_WdError();
    v11[3] = gCddImageInfo;
    v11[4] = (unsigned int)dword_14003E570;
    v11[5] = 215857758;
    WdLogGlobalForLineNumber = v10;
    return 0;
  }
  if ( cj != 16 )
  {
    if ( cj != 32 )
      return 0;
    v43 = 104;
    v14 = (DRVFN *)(*(_QWORD *)(W32GetSessionState(v9, v8) + 72) + 1672LL);
    v42 = v14;
    SessionState = W32GetSessionState(v16, v15);
    memset((void *)(*(_QWORD *)(SessionState + 72) + 8LL), 0, 0x340u);
    v20 = W32GetSessionState(v19, v18);
    memset((void *)(*(_QWORD *)(v20 + 72) + 840LL), 0, 0x340u);
    if ( LODWORD(pded[1].pdrvfn) )
    {
      Semaphore = EngCreateSemaphore();
      v24 = *(_QWORD *)(W32GetSessionState(v23, v22) + 72);
      *(_QWORD *)(v24 + 3344) = Semaphore;
      if ( !*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v24, v25) + 72) + 3344LL) )
        return 0;
      v26 = 3;
    }
    else
    {
      v26 = 2;
    }
    v27 = *(const WCHAR **)&pded[1].iDriverVersion;
    memset(DestinationString, 0, 48);
    RtlInitUnicodeString(DestinationString, v27);
    v28 = ZwSetSystemInformation(SystemLoadGdiDriverInformation, DestinationString, 0x30u);
    if ( v28 < 0 )
    {
      WdLogSingleEntry2(2, v28, *(_QWORD *)&pded[1].iDriverVersion);
      v10 = 3058;
      goto LABEL_5;
    }
    v31 = *(_QWORD *)(W32GetSessionState(v30, v29) + 72);
    *(_QWORD *)(v31 + 3360) = DestinationString[1].Buffer;
    v33 = W32GetSessionState(v31, v32);
    updated = RmtpEnableAndVerifyDriver(
                iEngineVersion,
                v34,
                pded,
                *(_QWORD *)&DestinationString[2].Length,
                v26,
                *(_QWORD *)(v33 + 72) + 840LL,
                &off_140039630);
    if ( updated )
    {
      if ( v26 != 3
        || (v45 = 0,
            v39 = W32GetSessionState(v36, v35),
            (updated = RmtpEnableAndVerifyDriver(
                         iEngineVersion,
                         v40,
                         &v45,
                         CddEnableDriver,
                         3,
                         *(_QWORD *)(v39 + 72) + 8LL,
                         &RmtDispatchTbl)) != 0) )
      {
        if ( v26 != 2 )
        {
          pded->c = 35;
          pded->pdrvfn = (DRVFN *)&qword_14003E000;
          return updated;
        }
        c = pded->c;
        if ( c > 0x68 )
        {
          updated = 0;
          WdLogSingleEntry0(2);
          v37 = 3105;
        }
        else
        {
          memmove(v14, pded->pdrvfn, 16LL * c);
          v44 = pded->c;
          updated = GdiIdxPfnPairs::UpdateEntry((GdiIdxPfnPairs *)&v42, 1, 8u, (__int64 (*)(void))RmtDisableDriver);
          if ( updated )
          {
            updated = GdiIdxPfnPairs::UpdateEntry(
                        (GdiIdxPfnPairs *)&v42,
                        1,
                        0,
                        (__int64 (*)(void))RmtPassThroughEnablePDEV);
            if ( updated )
            {
              updated = GdiIdxPfnPairs::UpdateEntry(
                          (GdiIdxPfnPairs *)&v42,
                          1,
                          2u,
                          (__int64 (*)(void))RmtPassThroughDisablePDEV);
              if ( updated )
              {
                if ( (unsigned int)GdiIdxPfnPairs::UpdateEntry(
                                     (GdiIdxPfnPairs *)&v42,
                                     0,
                                     0x5Cu,
                                     (__int64 (*)(void))RmtPassThroughMovePointerEx)
                  || (updated = GdiIdxPfnPairs::UpdateEntry(
                                  (GdiIdxPfnPairs *)&v42,
                                  0,
                                  0x1Eu,
                                  (__int64 (*)(void))RmtPassThroughMovePointer)) != 0 )
                {
                  updated = GdiIdxPfnPairs::UpdateEntry(
                              (GdiIdxPfnPairs *)&v42,
                              1,
                              0x1Du,
                              (__int64 (*)(void))RmtPassThroughSetPointerShape);
                  if ( updated )
                  {
                    updated = GdiIdxPfnPairs::UpdateEntry(
                                (GdiIdxPfnPairs *)&v42,
                                1,
                                3u,
                                (__int64 (*)(void))RmtPassThroughEnableSurface);
                    if ( updated )
                    {
                      updated = GdiIdxPfnPairs::UpdateEntry(
                                  (GdiIdxPfnPairs *)&v42,
                                  1,
                                  4u,
                                  (__int64 (*)(void))RmtPassThroughDisableSurface);
                      if ( updated )
                      {
                        pded->c = v44;
                        pded->pdrvfn = v42;
                        return updated;
                      }
                      WdLogSingleEntry0(2);
                      v37 = 3160;
                    }
                    else
                    {
                      WdLogSingleEntry0(2);
                      v37 = 3154;
                    }
                  }
                  else
                  {
                    WdLogSingleEntry0(2);
                    v37 = 3146;
                  }
                }
                else
                {
                  WdLogSingleEntry0(2);
                  v37 = 3138;
                }
              }
              else
              {
                WdLogSingleEntry0(2);
                v37 = 3127;
              }
            }
            else
            {
              WdLogSingleEntry0(2);
              v37 = 3121;
            }
          }
          else
          {
            WdLogSingleEntry0(2);
            v37 = 3113;
          }
        }
      }
      else
      {
        WdLogSingleEntry0(2);
        v37 = 3093;
      }
    }
    else
    {
      WdLogSingleEntry0(2);
      v37 = 3074;
    }
    WdLogGlobalForLineNumber = v37;
    v38 = (_QWORD *)WdLogNewEntry5_WdError();
    v38[3] = gCddImageInfo;
    v38[4] = (unsigned int)dword_14003E570;
    v38[5] = 215857758;
    WdLogGlobalForLineNumber = v37;
    RmtDisableDriver();
    return updated;
  }
  return CddEnableDriver(iEngineVersion, 0x10u, pded);
}

```

## disassembly

```asm
0x140036b30  push    rbp
0x140036b32  push    rbx
0x140036b33  push    rsi
0x140036b34  push    rdi
0x140036b35  push    r12
0x140036b37  push    r13
0x140036b39  push    r14
0x140036b3b  push    r15
0x140036b3d  lea     rbp, [rsp-1Fh]
0x140036b42  sub     rsp, 98h
0x140036b49  mov     rsi, r8
0x140036b4c  mov     ebx, edx
0x140036b4e  mov     r15d, ecx
0x140036b51  mov     r13d, 0CDDBA5Eh
0x140036b57  cmp     edx, 10h
0x140036b5a  jnb     short loc_140036BA3
0x140036b5c  mov     ecx, 1
0x140036b61  call    cs:__imp_WdLogSingleEntry0
0x140036b68  nop     dword ptr [rax+rax+00h]
0x140036b6d  mov     edi, 0BAAh
0x140036b72  mov     cs:WdLogGlobalForLineNumber, edi
0x140036b78  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140036b7f  nop     dword ptr [rax+rax+00h]
0x140036b84  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140036b8b  mov     [rax+18h], rcx
0x140036b8f  mov     ecx, cs:dword_14003E570
0x140036b95  mov     [rax+20h], rcx
0x140036b99  mov     [rax+28h], r13
0x140036b9d  mov     cs:WdLogGlobalForLineNumber, edi
0x140036ba3  call    ?AddSessionReference@?$CddSessionDataAccessor@UCddSessionData@@@@QEAAJXZ; CddSessionDataAccessor<CddSessionData>::AddSessionReference(void)
0x140036ba8  test    eax, eax
0x140036baa  jns     short loc_140036BFD
0x140036bac  movsxd  rdx, eax
0x140036baf  mov     ecx, 2
0x140036bb4  call    cs:__imp_WdLogSingleEntry1
0x140036bbb  nop     dword ptr [rax+rax+00h]
0x140036bc0  mov     ebx, 0BB1h
0x140036bc5  mov     cs:WdLogGlobalForLineNumber, ebx
0x140036bcb  call    cs:__imp_WdLogNewEntry5_WdError
0x140036bd2  nop     dword ptr [rax+rax+00h]
0x140036bd7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140036bde  mov     [rax+18h], rcx
0x140036be2  mov     ecx, cs:dword_14003E570
0x140036be8  mov     [rax+20h], rcx
0x140036bec  mov     [rax+28h], r13
0x140036bf0  mov     cs:WdLogGlobalForLineNumber, ebx
0x140036bf6  xor     eax, eax
0x140036bf8  jmp     loc_140037060
0x140036bfd  cmp     ebx, 10h
0x140036c00  jnz     short loc_140036C16
0x140036c02  mov     r8, rsi; struct tagDRVENABLEDATA *
0x140036c05  mov     edx, ebx; unsigned int
0x140036c07  mov     ecx, r15d; unsigned int
0x140036c0a  call    ?CddEnableDriver@@YAHKKPEAUtagDRVENABLEDATA@@@Z; CddEnableDriver(ulong,ulong,tagDRVENABLEDATA *)
0x140036c0f  mov     ebx, eax
0x140036c11  jmp     loc_14003705E
0x140036c16  cmp     ebx, 20h ; ' '
0x140036c19  jnz     loc_14003705C
0x140036c1f  call    cs:__imp_W32GetSessionState
0x140036c26  nop     dword ptr [rax+rax+00h]
0x140036c2b  mov     [rbp+57h+var_88], 68h ; 'h'
0x140036c32  mov     r12, [rax+48h]
0x140036c36  add     r12, 688h
0x140036c3d  mov     [rbp+57h+var_90], r12
0x140036c41  call    cs:__imp_W32GetSessionState
0x140036c48  nop     dword ptr [rax+rax+00h]
0x140036c4d  mov     ebx, 340h
0x140036c52  xor     edx, edx; Val
0x140036c54  mov     r8d, ebx; Size
0x140036c57  mov     rcx, [rax+48h]
0x140036c5b  add     rcx, 8; void *
0x140036c5f  call    memset
0x140036c64  call    cs:__imp_W32GetSessionState
0x140036c6b  nop     dword ptr [rax+rax+00h]
0x140036c70  mov     r8d, ebx; Size
0x140036c73  xor     edx, edx; Val
0x140036c75  mov     rcx, [rax+48h]
0x140036c79  add     rcx, 348h; void *
0x140036c80  call    memset
0x140036c85  cmp     dword ptr [rsi+18h], 0
0x140036c89  mov     edi, 2
0x140036c8e  jz      short loc_140036CDA
0x140036c90  call    cs:__imp_EngCreateSemaphore
0x140036c97  nop     dword ptr [rax+rax+00h]
0x140036c9c  mov     rbx, rax
0x140036c9f  call    cs:__imp_W32GetSessionState
0x140036ca6  nop     dword ptr [rax+rax+00h]
0x140036cab  mov     rcx, [rax+48h]
0x140036caf  mov     [rcx+0D10h], rbx
0x140036cb6  call    cs:__imp_W32GetSessionState
0x140036cbd  nop     dword ptr [rax+rax+00h]
0x140036cc2  mov     rcx, [rax+48h]
0x140036cc6  cmp     qword ptr [rcx+0D10h], 0
0x140036cce  jz      loc_140036BF6
0x140036cd4  lea     r14d, [rdi+1]
0x140036cd8  jmp     short loc_140036CDD
0x140036cda  mov     r14d, edi
0x140036cdd  mov     rdx, [rsi+10h]; SourceString
0x140036ce1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140036ce5  xorps   xmm0, xmm0
0x140036ce8  xor     eax, eax
0x140036cea  movups  xmmword ptr [rbp+57h+var_5E], xmm0
0x140036cee  mov     word ptr [rbp+57h+DestinationString], ax
0x140036cf2  movups  xmmword ptr [rbp+57h+var_5E+0Eh], xmm0
0x140036cf6  movups  xmmword ptr [rbp+57h+DestinationString+2], xmm0
0x140036cfa  call    cs:__imp_RtlInitUnicodeString
0x140036d01  nop     dword ptr [rax+rax+00h]
0x140036d06  mov     r8d, 30h ; '0'; SystemInformationLength
0x140036d0c  lea     rdx, [rbp+57h+DestinationString]; SystemInformation
0x140036d10  lea     ecx, [r8-16h]; SystemInformationClass
0x140036d14  call    cs:__imp_ZwSetSystemInformation
0x140036d1b  nop     dword ptr [rax+rax+00h]
0x140036d20  test    eax, eax
0x140036d22  jns     short loc_140036D43
0x140036d24  mov     r8, [rsi+10h]
0x140036d28  mov     ecx, edi
0x140036d2a  movsxd  rdx, eax
0x140036d2d  call    cs:__imp_WdLogSingleEntry2
0x140036d34  nop     dword ptr [rax+rax+00h]
0x140036d39  mov     ebx, 0BF2h
0x140036d3e  jmp     loc_140036BC5
0x140036d43  call    cs:__imp_W32GetSessionState
0x140036d4a  nop     dword ptr [rax+rax+00h]
0x140036d4f  mov     rcx, [rax+48h]
0x140036d53  mov     rax, qword ptr [rbp+57h+var_5E+6]
0x140036d57  mov     [rcx+0D20h], rax
0x140036d5e  call    cs:__imp_W32GetSessionState
0x140036d65  nop     dword ptr [rax+rax+00h]
0x140036d6a  mov     r9, qword ptr [rbp+57h+var_5E+0Eh]
0x140036d6e  mov     r8, rsi
0x140036d71  mov     rcx, [rax+48h]
0x140036d75  lea     rax, off_140039630
0x140036d7c  add     rcx, 348h
0x140036d83  mov     [rsp+0D0h+var_A0], rax
0x140036d88  mov     [rsp+0D0h+var_A8], rcx
0x140036d8d  mov     ecx, r15d
0x140036d90  mov     [rsp+0D0h+var_B0], r14d
0x140036d95  call    ?RmtpEnableAndVerifyDriver@@YAHKKPEAUtagDRVENABLEDATA@@P6AHKK0@ZW4CDD_OPERATIONAL_MODE@@PEAU_DDI_DISPATCH_TABLE@@PEBU3@@Z; RmtpEnableAndVerifyDriver(ulong,ulong,tagDRVENABLEDATA *,int (*)(ulong,ulong,tagDRVENABLEDATA *),CDD_OPERATIONAL_MODE,_DDI_DISPATCH_TABLE *,_DDI_DISPATCH_TABLE const *)
0x140036d9a  mov     ebx, eax
0x140036d9c  test    eax, eax
0x140036d9e  jnz     short loc_140036DE9
0x140036da0  mov     ecx, edi
0x140036da2  call    cs:__imp_WdLogSingleEntry0
0x140036da9  nop     dword ptr [rax+rax+00h]
0x140036dae  mov     edi, 0C02h
0x140036db3  mov     cs:WdLogGlobalForLineNumber, edi
0x140036db9  call    cs:__imp_WdLogNewEntry5_WdError
0x140036dc0  nop     dword ptr [rax+rax+00h]
0x140036dc5  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140036dcc  mov     [rax+18h], rcx
0x140036dd0  mov     ecx, cs:dword_14003E570
0x140036dd6  mov     [rax+20h], rcx
0x140036dda  mov     [rax+28h], r13
0x140036dde  mov     cs:WdLogGlobalForLineNumber, edi
0x140036de4  jmp     loc_140037055
0x140036de9  cmp     r14d, 3
0x140036ded  jnz     short loc_140036E51
0x140036def  xorps   xmm0, xmm0
0x140036df2  movups  [rbp+57h+var_80], xmm0
0x140036df6  call    cs:__imp_W32GetSessionState
0x140036dfd  nop     dword ptr [rax+rax+00h]
0x140036e02  lea     r9, ?CddEnableDriver@@YAHKKPEAUtagDRVENABLEDATA@@@Z; CddEnableDriver(ulong,ulong,tagDRVENABLEDATA *)
0x140036e09  lea     r8, [rbp+57h+var_80]
0x140036e0d  mov     rcx, [rax+48h]
0x140036e11  lea     rax, ?RmtDispatchTbl@@3U_DDI_DISPATCH_TABLE@@B; _DDI_DISPATCH_TABLE const RmtDispatchTbl
0x140036e18  add     rcx, 8
0x140036e1c  mov     [rsp+0D0h+var_A0], rax
0x140036e21  mov     [rsp+0D0h+var_A8], rcx
0x140036e26  mov     ecx, r15d
0x140036e29  mov     [rsp+0D0h+var_B0], r14d
0x140036e2e  call    ?RmtpEnableAndVerifyDriver@@YAHKKPEAUtagDRVENABLEDATA@@P6AHKK0@ZW4CDD_OPERATIONAL_MODE@@PEAU_DDI_DISPATCH_TABLE@@PEBU3@@Z; RmtpEnableAndVerifyDriver(ulong,ulong,tagDRVENABLEDATA *,int (*)(ulong,ulong,tagDRVENABLEDATA *),CDD_OPERATIONAL_MODE,_DDI_DISPATCH_TABLE *,_DDI_DISPATCH_TABLE const *)
0x140036e33  mov     ebx, eax
0x140036e35  test    eax, eax
0x140036e37  jnz     short loc_140036E51
0x140036e39  mov     ecx, edi
0x140036e3b  call    cs:__imp_WdLogSingleEntry0
0x140036e42  nop     dword ptr [rax+rax+00h]
0x140036e47  mov     edi, 0C15h
0x140036e4c  jmp     loc_140036DB3
0x140036e51  cmp     r14d, edi
0x140036e54  jnz     loc_14003703F
0x140036e5a  mov     eax, [rsi+4]
0x140036e5d  cmp     eax, 68h ; 'h'
0x140036e60  ja      loc_140037025
0x140036e66  mov     rdx, [rsi+8]; Src
0x140036e6a  mov     r8d, eax
0x140036e6d  shl     r8, 4; Size
0x140036e71  mov     rcx, r12; void *
0x140036e74  call    memmove
0x140036e79  mov     eax, [rsi+4]
0x140036e7c  lea     r9, ?RmtDisableDriver@@YAXXZ; __int64 (*)(void)
0x140036e83  mov     r8d, 8; unsigned int
0x140036e89  mov     [rbp+57h+var_84], eax
0x140036e8c  lea     rcx, [rbp+57h+var_90]; this
0x140036e90  lea     r14d, [r8-7]
0x140036e94  mov     edx, r14d; int
0x140036e97  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036e9c  mov     ebx, eax
0x140036e9e  test    eax, eax
0x140036ea0  jnz     short loc_140036EBA
0x140036ea2  mov     ecx, edi
0x140036ea4  call    cs:__imp_WdLogSingleEntry0
0x140036eab  nop     dword ptr [rax+rax+00h]
0x140036eb0  mov     edi, 0C29h
0x140036eb5  jmp     loc_140036DB3
0x140036eba  lea     r9, ?RmtPassThroughEnablePDEV@@YAPEAUDHPDEV__@@PEAU_devicemodeW@@PEAGKPEAPEAUHSURF__@@KPEAKKPEAUtagDEVINFO@@PEAUHDEV__@@1PEAX@Z; __int64 (*)(void)
0x140036ec1  xor     r8d, r8d; unsigned int
0x140036ec4  mov     edx, r14d; int
0x140036ec7  lea     rcx, [rbp+57h+var_90]; this
0x140036ecb  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036ed0  mov     ebx, eax
0x140036ed2  test    eax, eax
0x140036ed4  jnz     short loc_140036EEE
0x140036ed6  mov     ecx, edi
0x140036ed8  call    cs:__imp_WdLogSingleEntry0
0x140036edf  nop     dword ptr [rax+rax+00h]
0x140036ee4  mov     edi, 0C31h
0x140036ee9  jmp     loc_140036DB3
0x140036eee  lea     r9, ?RmtPassThroughDisablePDEV@@YAXPEAUDHPDEV__@@@Z; __int64 (*)(void)
0x140036ef5  mov     r8d, edi; unsigned int
0x140036ef8  mov     edx, r14d; int
0x140036efb  lea     rcx, [rbp+57h+var_90]; this
0x140036eff  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036f04  mov     ebx, eax
0x140036f06  test    eax, eax
0x140036f08  jnz     short loc_140036F22
0x140036f0a  mov     ecx, edi
0x140036f0c  call    cs:__imp_WdLogSingleEntry0
0x140036f13  nop     dword ptr [rax+rax+00h]
0x140036f18  mov     edi, 0C37h
0x140036f1d  jmp     loc_140036DB3
0x140036f22  xor     edx, edx; int
0x140036f24  lea     r9, ?RmtPassThroughMovePointerEx@@YAXPEAU_SURFOBJ@@JJK@Z; __int64 (*)(void)
0x140036f2b  lea     rcx, [rbp+57h+var_90]; this
0x140036f2f  lea     r8d, [rdx+5Ch]; unsigned int
0x140036f33  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036f38  test    eax, eax
0x140036f3a  jnz     short loc_140036F70
0x140036f3c  lea     r9, ?RmtPassThroughMovePointer@@YAXPEAU_SURFOBJ@@JJPEAU_RECTL@@@Z; __int64 (*)(void)
0x140036f43  xor     edx, edx; int
0x140036f45  lea     r8d, [rax+1Eh]; unsigned int
0x140036f49  lea     rcx, [rbp+57h+var_90]; this
0x140036f4d  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036f52  mov     ebx, eax
0x140036f54  test    eax, eax
0x140036f56  jnz     short loc_140036F70
0x140036f58  mov     ecx, edi
0x140036f5a  call    cs:__imp_WdLogSingleEntry0
0x140036f61  nop     dword ptr [rax+rax+00h]
0x140036f66  mov     edi, 0C42h
0x140036f6b  jmp     loc_140036DB3
0x140036f70  lea     r9, ?RmtPassThroughSetPointerShape@@YAKPEAU_SURFOBJ@@00PEAU_XLATEOBJ@@JJJJPEAU_RECTL@@K@Z; __int64 (*)(void)
0x140036f77  mov     r8d, 1Dh; unsigned int
0x140036f7d  mov     edx, r14d; int
0x140036f80  lea     rcx, [rbp+57h+var_90]; this
0x140036f84  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036f89  mov     ebx, eax
0x140036f8b  test    eax, eax
0x140036f8d  jnz     short loc_140036FA7
0x140036f8f  mov     ecx, edi
0x140036f91  call    cs:__imp_WdLogSingleEntry0
0x140036f98  nop     dword ptr [rax+rax+00h]
0x140036f9d  mov     edi, 0C4Ah
0x140036fa2  jmp     loc_140036DB3
0x140036fa7  lea     r9, ?RmtPassThroughEnableSurface@@YAPEAUHSURF__@@PEAUDHPDEV__@@@Z; __int64 (*)(void)
0x140036fae  mov     r8d, 3; unsigned int
0x140036fb4  mov     edx, r14d; int
0x140036fb7  lea     rcx, [rbp+57h+var_90]; this
0x140036fbb  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036fc0  mov     ebx, eax
0x140036fc2  test    eax, eax
0x140036fc4  jnz     short loc_140036FDE
0x140036fc6  mov     ecx, edi
0x140036fc8  call    cs:__imp_WdLogSingleEntry0
0x140036fcf  nop     dword ptr [rax+rax+00h]
0x140036fd4  mov     edi, 0C52h
0x140036fd9  jmp     loc_140036DB3
0x140036fde  lea     r9, ?RmtPassThroughDisableSurface@@YAXPEAUDHPDEV__@@@Z; __int64 (*)(void)
0x140036fe5  mov     r8d, 4; unsigned int
0x140036feb  mov     edx, r14d; int
0x140036fee  lea     rcx, [rbp+57h+var_90]; this
0x140036ff2  call    ?UpdateEntry@GdiIdxPfnPairs@@QEAAHHKP6A_JXZ@Z; GdiIdxPfnPairs::UpdateEntry(int,ulong,__int64 (*)(void))
0x140036ff7  mov     ebx, eax
0x140036ff9  test    eax, eax
0x140036ffb  jnz     short loc_140037015
0x140036ffd  mov     ecx, edi
0x140036fff  call    cs:__imp_WdLogSingleEntry0
0x140037006  nop     dword ptr [rax+rax+00h]
0x14003700b  mov     edi, 0C58h
0x140037010  jmp     loc_140036DB3
0x140037015  mov     eax, [rbp+57h+var_84]
0x140037018  mov     [rsi+4], eax
0x14003701b  mov     rax, [rbp+57h+var_90]
0x14003701f  mov     [rsi+8], rax
0x140037023  jmp     short loc_14003705E
0x140037025  xor     ebx, ebx
0x140037027  mov     ecx, edi
0x140037029  call    cs:__imp_WdLogSingleEntry0
0x140037030  nop     dword ptr [rax+rax+00h]
0x140037035  mov     edi, 0C21h
  ... truncated ...
```
