# AddParentJob(_LIST_ENTRY * const,ushort const *,_FAX_PERSONAL_PROFILEW const *,_FAX_JOB_PARAM_EXW const *,_FAX_COVERPAGE_INFO_EXW const *,ushort const *,void *,_FAX_PERSONAL_PROFILEW const *,ushort const *,int)

- ea: `0x14003567c`
- end: `0x140035f83`
- name: `?AddParentJob@@YAPEAU_JOB_QUEUE@@QEAU_LIST_ENTRY@@PEBGPEBU_FAX_PERSONAL_PROFILEW@@PEBU_FAX_JOB_PARAM_EXW@@PEBU_FAX_COVERPAGE_INFO_EXW@@1PEAX21H@Z`
- size: `2311`
- prototype: `struct _JOB_QUEUE *(struct _LIST_ENTRY *const, const unsigned __int16 *, const struct _FAX_PERSONAL_PROFILEW *, const struct _FAX_JOB_PARAM_EXW *, const struct _FAX_COVERPAGE_INFO_EXW *, const unsigned __int16 *, void *, const struct _FAX_PERSONAL_PROFILEW *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001cf70`
- `0x14003c270`

## callees

- `0x1400023cc`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14003567c`
- `0x140036eb4`
- `0x140037890`
- `0x140037988`
- `0x1400382a4`
- `0x1400388d0`
- `0x14003a3d8`
- `0x14003db00`
- `0x14003e14c`
- `0x14004f56c`
- `0x1400507f4`
- `0x140051874`
- `0x140067168`
- `0x14006ef88`
- `0x140074b88`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003580b`
- `KERNEL32!GetLastError` at `0x140035882`
- `KERNEL32!GetLastError` at `0x140035933`
- `KERNEL32!GetLastError` at `0x140035958`
- `KERNEL32!GetLastError` at `0x14003598b`
- `KERNEL32!GetLastError` at `0x1400359da`
- `KERNEL32!GetLastError` at `0x140035a0d`
- `KERNEL32!GetLastError` at `0x140035a30`
- `KERNEL32!GetLastError` at `0x140035a63`
- `KERNEL32!GetLastError` at `0x140035af9`
- `KERNEL32!GetLastError` at `0x140035b36`
- `KERNEL32!GetLastError` at `0x140035b8f`
- `KERNEL32!GetLastError` at `0x140035c02`
- `KERNEL32!GetLastError` at `0x140035c6a`
- `KERNEL32!GetLastError` at `0x140035cbd`
- `KERNEL32!GetLastError` at `0x140035d42`
- `KERNEL32!GetLastError` at `0x140035d75`
- `KERNEL32!GetLastError` at `0x140035db1`
- `KERNEL32!GetLastError` at `0x140035de4`
- `KERNEL32!GetLastError` at `0x140035e1c`
- `KERNEL32!GetLastError` at `0x140035e43`
- `KERNEL32!GetLastError` at `0x140035f03`
- `KERNEL32!GetLastError` at `0x140035f2a`
- `KERNEL32!GetLastError` at `0x14003580b`
- `KERNEL32!GetLastError` at `0x140035882`
- `KERNEL32!GetLastError` at `0x140035933`
- `KERNEL32!GetLastError` at `0x140035958`
- `KERNEL32!GetLastError` at `0x14003598b`
- `KERNEL32!GetLastError` at `0x1400359da`
- `KERNEL32!GetLastError` at `0x140035a0d`
- `KERNEL32!GetLastError` at `0x140035a30`
- `KERNEL32!GetLastError` at `0x140035a63`
- `KERNEL32!GetLastError` at `0x140035af9`
- `KERNEL32!GetLastError` at `0x140035b36`
- `KERNEL32!GetLastError` at `0x140035b8f`
- `KERNEL32!GetLastError` at `0x140035c02`
- `KERNEL32!GetLastError` at `0x140035c6a`
- `KERNEL32!GetLastError` at `0x140035cbd`
- `KERNEL32!GetLastError` at `0x140035d42`
- `KERNEL32!GetLastError` at `0x140035d75`
- `KERNEL32!GetLastError` at `0x140035db1`
- `KERNEL32!GetLastError` at `0x140035de4`
- `KERNEL32!GetLastError` at `0x140035e1c`
- `KERNEL32!GetLastError` at `0x140035e43`
- `KERNEL32!GetLastError` at `0x140035f03`
- `KERNEL32!GetLastError` at `0x140035f2a`
- `KERNEL32!SetLastError` at `0x140035f51`
- `KERNEL32!SetLastError` at `0x140035f51`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140035bdd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140035bdd`
- `KERNEL32!EnterCriticalSection` at `0x140035d18`
- `KERNEL32!EnterCriticalSection` at `0x140035d18`
- `KERNEL32!LeaveCriticalSection` at `0x140035e70`
- `KERNEL32!LeaveCriticalSection` at `0x140035ec0`
- `KERNEL32!LeaveCriticalSection` at `0x140035e70`
- `KERNEL32!LeaveCriticalSection` at `0x140035ec0`
- `KERNEL32!InitializeCriticalSection` at `0x1400357a3`
- `KERNEL32!InitializeCriticalSection` at `0x1400357b0`
- `KERNEL32!InitializeCriticalSection` at `0x1400357a3`
- `KERNEL32!InitializeCriticalSection` at `0x1400357b0`
- `KERNEL32!GetSystemTime` at `0x140035c56`
- `KERNEL32!GetSystemTime` at `0x140035c56`
- `KERNEL32!SystemTimeToFileTime` at `0x140035bf4`
- `KERNEL32!SystemTimeToFileTime` at `0x140035cb3`
- `KERNEL32!SystemTimeToFileTime` at `0x140035bf4`
- `KERNEL32!SystemTimeToFileTime` at `0x140035cb3`
- `FXSTIFF!TiffClose` at `0x140035aa4`
- `FXSTIFF!TiffClose` at `0x140035aa4`
- `FXSTIFF!TiffOpen` at `0x140035a8b`
- `FXSTIFF!TiffOpen` at `0x140035a8b`

## pseudocode

```c
struct _JOB_QUEUE *__fastcall AddParentJob(
        struct _LIST_ENTRY *const a1,
        unsigned __int16 *a2,
        const struct _FAX_PERSONAL_PROFILEW *a3,
        const struct _FAX_JOB_PARAM_EXW *a4,
        const struct _FAX_COVERPAGE_INFO_EXW *a5,
        unsigned __int16 *a6,
        PSID pSourceSid,
        const struct _FAX_PERSONAL_PROFILEW *a8,
        unsigned __int16 *a9,
        int a10)
{
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  DWORD LastError; // ebx
  __int64 v14; // rax
  DWORD v15; // eax
  __int64 v16; // rdx
  CMapDeviceId *v17; // rcx
  __int64 v18; // rax
  DWORD v19; // eax
  __int64 v20; // rax
  DWORD v21; // eax
  __int64 v22; // rdx
  CMapDeviceId *v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // eax
  unsigned int *v26; // rdx
  unsigned int FileSize; // eax
  unsigned int MergedFileSize; // eax
  _QWORD *v29; // rbx
  unsigned int v30; // r8d
  unsigned __int64 UniqueQueueFile; // rax
  DWORD v32; // eax
  __int64 v33; // rax
  DWORD v34; // eax
  char v35; // al
  struct _LIST_ENTRY *Blink; // rax
  CFaxConfiguration *v37; // rcx
  DWORD v39; // eax
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v43[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v44[264]; // [rsp+80h] [rbp-80h] BYREF

  memset(v43, 0, sizeof(v43));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v11 = operator new(0x738u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&SystemTime.wYear = v11;
  v12 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v39);
    }
    goto LABEL_117;
  }
  v11[461] = 0;
  LastError = 0;
  memset_0(v11, 0, 0x738u);
  *((_QWORD *)v12 + 213) = v12 + 424;
  *((_QWORD *)v12 + 212) = v12 + 424;
  *((_QWORD *)v12 + 221) = v12 + 440;
  *((_QWORD *)v12 + 220) = v12 + 440;
  *((_QWORD *)v12 + 28) = v12 + 54;
  *((_QWORD *)v12 + 27) = v12 + 54;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 444));
  InitializeCriticalSection((LPCRITICAL_SECTION)v12 + 43);
  v12[8] = _InterlockedIncrement((volatile signed __int32 *)g_pFaxConfig + 27);
  v14 = StringDup(a2);
  *((_QWORD *)v12 + 9) = v14;
  if ( a2 && !v14 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v15 = GetLastError();
    v16 = 209;
    goto LABEL_12;
  }
  v12[9] = 32;
  v18 = StringDup(a6);
  *((_QWORD *)v12 + 50) = v18;
  if ( a6 && !v18 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v15 = GetLastError();
    v16 = 210;
    goto LABEL_12;
  }
  v19 = AllocateAndCopySid(pSourceSid, (LPVOID *)v12 + 51);
  LastError = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v19);
    }
    goto LABEL_107;
  }
  v20 = StringDup(a9);
  *((_QWORD *)v12 + 55) = v20;
  if ( a9 && !v20 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v15 = GetLastError();
    v16 = 212;
LABEL_12:
    v17 = WPP_GLOBAL_Control;
    LastError = v15;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v17 + 2), v16, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v15);
LABEL_107:
    FreeParentQueueEntry((struct _JOB_QUEUE *)v12);
LABEL_117:
    SetLastError(LastError);
    return 0;
  }
  if ( !(unsigned int)CopyJobParamEx((struct _FAX_JOB_PARAM_EXW *)(v12 + 20), a4) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v21 = GetLastError();
    v22 = 213;
    goto LABEL_36;
  }
  _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v12, 1u);
  if ( !(unsigned int)CopyPersonalProfile(v12 + 60, a3) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v21 = GetLastError();
    v22 = 214;
    goto LABEL_36;
  }
  if ( !(unsigned int)CopyCoverPageInfoEx((struct _FAX_COVERPAGE_INFO_EXW *)(v12 + 44), a5) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_107;
    }
    v21 = GetLastError();
    v22 = 215;
LABEL_36:
    v23 = WPP_GLOBAL_Control;
LABEL_37:
    WPP_SF_d(*((_QWORD *)v23 + 2), v22, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v21);
    goto LABEL_107;
  }
  if ( a2 )
  {
    v24 = TiffOpen(a2, v43, 1, 1);
    if ( !v24 )
    {
      v21 = GetLastError();
      LastError = v21;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v22 = 216;
      goto LABEL_37;
    }
    v12[16] = DWORD2(v43[0]);
    TiffClose(v24);
  }
  v25 = v12[42];
  v26 = v12 + 16;
  if ( v25 )
    *v26 = v25;
  if ( a5 && *((_QWORD *)a5 + 1) )
  {
    v26 = v12 + 16;
    ++v12[16];
  }
  if ( a8 )
  {
    if ( *((_QWORD *)a5 + 1) )
    {
      MergedFileSize = GetMergedFileSize(a2, *v26, a5, a3, a8);
      v12[97] = MergedFileSize;
      if ( !MergedFileSize )
      {
        v15 = GetLastError();
        LastError = v15;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_107;
        }
        v16 = 218;
        goto LABEL_13;
      }
    }
    else
    {
      FileSize = MyGetFileSize(a2);
      v12[97] = FileSize;
      if ( !FileSize )
      {
        v15 = GetLastError();
        LastError = v15;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_107;
        }
        v16 = 217;
        goto LABEL_13;
      }
    }
  }
  *((_QWORD *)v12 + 49) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)v12 + 53);
  if ( *((_DWORD *)a4 + 1) == 1 )
  {
    v29 = v12 + 6;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)(v12 + 22), (LPFILETIME)v12 + 3) )
    {
      v15 = GetLastError();
      LastError = v15;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v16 = 219;
      goto LABEL_13;
    }
  }
  else if ( *((_DWORD *)a4 + 1) == 2 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    if ( !(unsigned int)SetDiscountTime(&SystemTime) )
    {
      v15 = GetLastError();
      LastError = v15;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v16 = 220;
      goto LABEL_13;
    }
    v29 = v12 + 6;
    if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v12 + 3) )
    {
      v15 = GetLastError();
      LastError = v15;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_107;
      }
      v16 = 221;
      goto LABEL_13;
    }
  }
  else
  {
    v29 = v12 + 6;
    *((_QWORD *)v12 + 3) = *((_QWORD *)v12 + 53);
  }
  *((_QWORD *)v12 + 52) = *v29;
  EnterCriticalSection(&g_CsQueue);
  if ( a10 )
  {
    UniqueQueueFile = GenerateUniqueQueueFile(0x20u, v44, v30);
    *((_QWORD *)v12 + 2) = UniqueQueueFile;
    if ( !UniqueQueueFile )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v32 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v32);
      }
LABEL_106:
      LeaveCriticalSection(&g_CsQueue);
      goto LABEL_107;
    }
    v33 = StringDup(v44);
    *((_QWORD *)v12 + 7) = v33;
    if ( !v33 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v34);
      }
      goto LABEL_106;
    }
    if ( !(unsigned int)CommitQueueEntry((struct _JOB_QUEUE *)v12, 1) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          224,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          (unsigned int)v44,
          v35);
      }
      goto LABEL_106;
    }
  }
  Blink = g_QueueListHead.Blink;
  *(_QWORD *)v12 = &g_QueueListHead;
  *((_QWORD *)v12 + 1) = Blink;
  Blink->Flink = (struct _LIST_ENTRY *)v12;
  g_QueueListHead.Blink = (struct _LIST_ENTRY *)v12;
  SafeIncIdleCounter(&g_dwQueueCount);
  CFaxConfiguration::StoreNextJobId(v37, *((_DWORD *)g_pFaxConfig + 27));
  LeaveCriticalSection(&g_CsQueue);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      225,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      (unsigned int)v12[8]);
  }
  return (struct _JOB_QUEUE *)v12;
}

```

## disassembly

```asm
0x14003567c  mov     [rsp-8+arg_0], rbx
0x140035681  push    rbp
0x140035682  push    rsi
0x140035683  push    rdi
0x140035684  push    r12
0x140035686  push    r13
0x140035688  push    r14
0x14003568a  push    r15
0x14003568c  lea     rbp, [rsp-1A0h]
0x140035694  sub     rsp, 2A0h
0x14003569b  mov     rax, cs:__security_cookie
0x1400356a2  xor     rax, rsp
0x1400356a5  mov     [rbp+1D0h+var_40], rax
0x1400356ac  mov     rax, [rbp+1D0h+arg_38]
0x1400356b3  xorps   xmm0, xmm0
0x1400356b6  mov     rsi, [rbp+1D0h+arg_20]
0x1400356bd  mov     r14, rdx
0x1400356c0  mov     r15, [rbp+1D0h+arg_28]
0x1400356c7  mov     r13, [rbp+1D0h+pSourceSid]
0x1400356ce  mov     r12, [rbp+1D0h+arg_40]
0x1400356d5  mov     [rsp+2D0h+var_290], rax
0x1400356da  movups  [rsp+2D0h+var_278], xmm0
0x1400356df  mov     [rsp+2D0h+var_2A0], r9
0x1400356e4  movups  [rsp+2D0h+var_268], xmm0
0x1400356e9  mov     [rsp+2D0h+var_298], r8
0x1400356ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400356f5  lea     rax, WPP_GLOBAL_Control
0x1400356fc  cmp     rcx, rax
0x1400356ff  jz      short loc_140035722
0x140035701  test    byte ptr [rcx+1Ch], 4
0x140035705  jz      short loc_140035722
0x140035707  cmp     byte ptr [rcx+19h], 5
0x14003570b  jb      short loc_140035722
0x14003570d  mov     rcx, [rcx+10h]
0x140035711  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140035718  mov     edx, 0CFh
0x14003571d  call    WPP_SF_
0x140035722  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140035729  mov     ecx, 738h; unsigned __int64
0x14003572e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140035733  mov     qword ptr [rsp+2D0h+SystemTime.wYear], rax
0x140035738  mov     rdi, rax
0x14003573b  test    rax, rax
0x14003573e  jz      loc_140035F03
0x140035744  mov     dword ptr [rax+734h], 0
0x14003574e  test    rax, rax
0x140035751  jz      loc_140035F03
0x140035757  xor     edx, edx; Val
0x140035759  mov     r8d, 738h; Size
0x14003575f  mov     rcx, rax; void *
0x140035762  xor     ebx, ebx
0x140035764  call    memset_0
0x140035769  lea     rax, [rdi+6A0h]
0x140035770  mov     [rdi+6A8h], rax
0x140035777  lea     rcx, [rdi+6F0h]; lpCriticalSection
0x14003577e  mov     [rax], rax
0x140035781  lea     rax, [rdi+6E0h]
0x140035788  mov     [rdi+6E8h], rax
0x14003578f  mov     [rax], rax
0x140035792  lea     rax, [rdi+0D8h]
0x140035799  mov     [rdi+0E0h], rax
0x1400357a0  mov     [rax], rax
0x1400357a3  call    cs:__imp_InitializeCriticalSection
0x1400357a9  lea     rcx, [rdi+6B8h]; lpCriticalSection
0x1400357b0  call    cs:__imp_InitializeCriticalSection
0x1400357b6  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400357bd  lea     eax, [rbx+1]
0x1400357c0  lock xadd [rcx+6Ch], eax
0x1400357c5  inc     eax
0x1400357c7  mov     rcx, r14; unsigned __int16 *
0x1400357ca  mov     [rdi+20h], eax
0x1400357cd  call    StringDup
0x1400357d2  mov     [rdi+48h], rax
0x1400357d6  test    r14, r14
0x1400357d9  jz      short loc_140035837
0x1400357db  test    rax, rax
0x1400357de  jnz     short loc_140035837
0x1400357e0  mov     rax, cs:WPP_GLOBAL_Control
0x1400357e7  lea     rdx, WPP_GLOBAL_Control
0x1400357ee  cmp     rax, rdx
0x1400357f1  jz      loc_140035E76
0x1400357f7  test    byte ptr [rax+1Ch], 4
0x1400357fb  jz      loc_140035E76
0x140035801  cmp     byte ptr [rax+19h], 2
0x140035805  jb      loc_140035E76
0x14003580b  call    cs:__imp_GetLastError
0x140035811  mov     edx, 0D1h
0x140035816  mov     rcx, cs:WPP_GLOBAL_Control
0x14003581d  mov     ebx, eax
0x14003581f  mov     rcx, [rcx+10h]
0x140035823  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003582a  mov     r9d, eax
0x14003582d  call    WPP_SF_d
0x140035832  jmp     loc_140035E76
0x140035837  mov     rcx, r15; unsigned __int16 *
0x14003583a  mov     dword ptr [rdi+24h], 20h ; ' '
0x140035841  call    StringDup
0x140035846  mov     [rdi+190h], rax
0x14003584d  test    r15, r15
0x140035850  jz      short loc_14003588F
0x140035852  test    rax, rax
0x140035855  jnz     short loc_14003588F
0x140035857  mov     rax, cs:WPP_GLOBAL_Control
0x14003585e  lea     rdx, WPP_GLOBAL_Control
0x140035865  cmp     rax, rdx
0x140035868  jz      loc_140035E76
0x14003586e  test    byte ptr [rax+1Ch], 4
0x140035872  jz      loc_140035E76
0x140035878  cmp     byte ptr [rax+19h], 2
0x14003587c  jb      loc_140035E76
0x140035882  call    cs:__imp_GetLastError
0x140035888  mov     edx, 0D2h
0x14003588d  jmp     short loc_140035816
0x14003588f  lea     rdx, [rdi+198h]
0x140035896  mov     rcx, r13; pSourceSid
0x140035899  call    AllocateAndCopySid
0x14003589e  xor     r13d, r13d
0x1400358a1  mov     ebx, eax
0x1400358a3  test    eax, eax
0x1400358a5  jz      short loc_1400358EF
0x1400358a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400358ae  lea     rdx, WPP_GLOBAL_Control
0x1400358b5  cmp     rcx, rdx
0x1400358b8  jz      loc_140035E76
0x1400358be  test    byte ptr [rcx+1Ch], 4
0x1400358c2  jz      loc_140035E76
0x1400358c8  cmp     byte ptr [rcx+19h], 2
0x1400358cc  jb      loc_140035E76
0x1400358d2  mov     rcx, [rcx+10h]
0x1400358d6  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400358dd  mov     edx, 0D3h
0x1400358e2  mov     r9d, eax
0x1400358e5  call    WPP_SF_d
0x1400358ea  jmp     loc_140035E76
0x1400358ef  mov     rcx, r12; unsigned __int16 *
0x1400358f2  call    StringDup
0x1400358f7  mov     [rdi+1B8h], rax
0x1400358fe  test    r12, r12
0x140035901  jz      short loc_140035943
0x140035903  test    rax, rax
0x140035906  jnz     short loc_140035943
0x140035908  mov     rax, cs:WPP_GLOBAL_Control
0x14003590f  lea     rdx, WPP_GLOBAL_Control
0x140035916  cmp     rax, rdx
0x140035919  jz      loc_140035E76
0x14003591f  test    byte ptr [rax+1Ch], 4
0x140035923  jz      loc_140035E76
0x140035929  cmp     byte ptr [rax+19h], 2
0x14003592d  jb      loc_140035E76
0x140035933  call    cs:__imp_GetLastError
0x140035939  mov     edx, 0D4h
0x14003593e  jmp     loc_140035816
0x140035943  mov     rbx, [rsp+2D0h+var_2A0]
0x140035948  lea     rcx, [rdi+50h]; struct _FAX_JOB_PARAM_EXW *
0x14003594c  mov     rdx, rbx; struct _FAX_JOB_PARAM_EXW *
0x14003594f  call    ?CopyJobParamEx@@YAHPEAU_FAX_JOB_PARAM_EXW@@PEBU1@@Z; CopyJobParamEx(_FAX_JOB_PARAM_EXW *,_FAX_JOB_PARAM_EXW const *)
0x140035954  test    eax, eax
0x140035956  jnz     short loc_1400359B5
0x140035958  call    cs:__imp_GetLastError
0x14003595e  mov     ebx, eax
0x140035960  mov     rax, cs:WPP_GLOBAL_Control
0x140035967  lea     rdx, WPP_GLOBAL_Control
0x14003596e  cmp     rax, rdx
0x140035971  jz      loc_140035E76
0x140035977  test    byte ptr [rax+1Ch], 4
0x14003597b  jz      loc_140035E76
0x140035981  cmp     byte ptr [rax+19h], 2
0x140035985  jb      loc_140035E76
0x14003598b  call    cs:__imp_GetLastError
0x140035991  mov     edx, 0D5h
0x140035996  mov     rcx, cs:WPP_GLOBAL_Control
0x14003599d  mov     rcx, [rcx+10h]
0x1400359a1  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400359a8  mov     r9d, eax
0x1400359ab  call    WPP_SF_d
0x1400359b0  jmp     loc_140035E76
0x1400359b5  mov     edx, 1; unsigned int
0x1400359ba  mov     rcx, rdi; this
0x1400359bd  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x1400359c2  mov     r12, [rsp+2D0h+var_298]
0x1400359c7  lea     rcx, [rdi+0F0h]
0x1400359ce  mov     rdx, r12
0x1400359d1  call    CopyPersonalProfile
0x1400359d6  test    eax, eax
0x1400359d8  jnz     short loc_140035A1D
0x1400359da  call    cs:__imp_GetLastError
0x1400359e0  mov     ebx, eax
0x1400359e2  mov     rax, cs:WPP_GLOBAL_Control
0x1400359e9  lea     rdx, WPP_GLOBAL_Control
0x1400359f0  cmp     rax, rdx
0x1400359f3  jz      loc_140035E76
0x1400359f9  test    byte ptr [rax+1Ch], 4
0x1400359fd  jz      loc_140035E76
0x140035a03  cmp     byte ptr [rax+19h], 2
0x140035a07  jb      loc_140035E76
0x140035a0d  call    cs:__imp_GetLastError
0x140035a13  mov     edx, 0D6h
0x140035a18  jmp     loc_140035996
0x140035a1d  lea     rcx, [rdi+0B0h]; struct _FAX_COVERPAGE_INFO_EXW *
0x140035a24  mov     rdx, rsi; struct _FAX_COVERPAGE_INFO_EXW *
0x140035a27  call    ?CopyCoverPageInfoEx@@YAHPEAU_FAX_COVERPAGE_INFO_EXW@@PEBU1@@Z; CopyCoverPageInfoEx(_FAX_COVERPAGE_INFO_EXW *,_FAX_COVERPAGE_INFO_EXW const *)
0x140035a2c  test    eax, eax
0x140035a2e  jnz     short loc_140035A73
0x140035a30  call    cs:__imp_GetLastError
0x140035a36  mov     ebx, eax
0x140035a38  mov     rax, cs:WPP_GLOBAL_Control
0x140035a3f  lea     rdx, WPP_GLOBAL_Control
0x140035a46  cmp     rax, rdx
0x140035a49  jz      loc_140035E76
0x140035a4f  test    byte ptr [rax+1Ch], 4
0x140035a53  jz      loc_140035E76
0x140035a59  cmp     byte ptr [rax+19h], 2
0x140035a5d  jb      loc_140035E76
0x140035a63  call    cs:__imp_GetLastError
0x140035a69  mov     edx, 0D7h
0x140035a6e  jmp     loc_140035996
0x140035a73  test    r14, r14
0x140035a76  jz      short loc_140035AAA
0x140035a78  mov     eax, 1
0x140035a7d  lea     rdx, [rsp+2D0h+var_278]
0x140035a82  mov     r9d, eax
0x140035a85  mov     r8d, eax
0x140035a88  mov     rcx, r14
0x140035a8b  call    cs:__imp_TiffOpen
0x140035a91  test    rax, rax
0x140035a94  jz      loc_140035B36
0x140035a9a  mov     ecx, dword ptr [rsp+2D0h+var_278+8]
0x140035a9e  mov     [rdi+40h], ecx
0x140035aa1  mov     rcx, rax
0x140035aa4  call    cs:__imp_TiffClose
0x140035aaa  mov     eax, [rdi+0A8h]
0x140035ab0  lea     rdx, [rdi+40h]
0x140035ab4  test    eax, eax
0x140035ab6  jz      short loc_140035ABA
0x140035ab8  mov     [rdx], eax
0x140035aba  test    rsi, rsi
0x140035abd  jz      short loc_140035ACB
0x140035abf  cmp     [rsi+8], r13
0x140035ac3  jz      short loc_140035ACB
0x140035ac5  lea     rdx, [rdi+40h]
0x140035ac9  inc     dword ptr [rdx]
0x140035acb  mov     rax, [rsp+2D0h+var_290]
0x140035ad0  test    rax, rax
0x140035ad3  jz      loc_140035BCC
0x140035ad9  mov     rcx, r14; unsigned __int16 *
0x140035adc  cmp     [rsi+8], r13
0x140035ae0  jnz     loc_140035B73
0x140035ae6  call    ?MyGetFileSize@@YAKPEBG@Z; MyGetFileSize(ushort const *)
0x140035aeb  mov     [rdi+184h], eax
0x140035af1  test    eax, eax
0x140035af3  jnz     loc_140035BCC
0x140035af9  call    cs:__imp_GetLastError
0x140035aff  mov     ebx, eax
0x140035b01  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b08  lea     rdx, WPP_GLOBAL_Control
0x140035b0f  cmp     rcx, rdx
0x140035b12  jz      loc_140035E76
0x140035b18  test    byte ptr [rcx+1Ch], 4
0x140035b1c  jz      loc_140035E76
0x140035b22  cmp     byte ptr [rcx+19h], 2
0x140035b26  jb      loc_140035E76
0x140035b2c  mov     edx, 0D9h
0x140035b31  jmp     loc_14003581F
0x140035b36  call    cs:__imp_GetLastError
0x140035b3c  mov     ebx, eax
0x140035b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b45  lea     rdx, WPP_GLOBAL_Control
0x140035b4c  cmp     rcx, rdx
0x140035b4f  jz      loc_140035E76
0x140035b55  test    byte ptr [rcx+1Ch], 4
0x140035b59  jz      loc_140035E76
0x140035b5f  cmp     byte ptr [rcx+19h], 2
0x140035b63  jb      loc_140035E76
0x140035b69  mov     edx, 0D8h
0x140035b6e  jmp     loc_14003599D
0x140035b73  mov     edx, [rdx]; unsigned int
0x140035b75  mov     r9, r12; struct _FAX_PERSONAL_PROFILEW *
0x140035b78  mov     r8, rsi; struct _FAX_COVERPAGE_INFO_EXW *
0x140035b7b  mov     [rsp+2D0h+var_2B0], rax; struct _FAX_PERSONAL_PROFILEW *
0x140035b80  call    ?GetMergedFileSize@@YAKPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@2@Z; GetMergedFileSize(ushort const *,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *)
0x140035b85  mov     [rdi+184h], eax
0x140035b8b  test    eax, eax
0x140035b8d  jnz     short loc_140035BCC
0x140035b8f  call    cs:__imp_GetLastError
0x140035b95  mov     ebx, eax
0x140035b97  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b9e  lea     rdx, WPP_GLOBAL_Control
0x140035ba5  cmp     rcx, rdx
0x140035ba8  jz      loc_140035E76
0x140035bae  test    byte ptr [rcx+1Ch], 4
0x140035bb2  jz      loc_140035E76
0x140035bb8  cmp     byte ptr [rcx+19h], 2
0x140035bbc  jb      loc_140035E76
0x140035bc2  mov     edx, 0DAh
0x140035bc7  jmp     loc_14003581F
0x140035bcc  lea     rsi, [rdi+1A8h]
0x140035bd3  mov     [rdi+188h], r13
0x140035bda  mov     rcx, rsi; lpSystemTimeAsFileTime
0x140035bdd  call    cs:__imp_GetSystemTimeAsFileTime
0x140035be3  cmp     dword ptr [rbx+4], 1
  ... truncated ...
```
