# CscSyncPrepareForSyncEx

- ea: `0x180020514`
- end: `0x180020a43`
- name: `CscSyncPrepareForSyncEx`
- size: `1327`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x1800315a8`
- `0x18006b800`

## callees

- `0x180003a00`
- `0x1800060a0`
- `0x180020514`
- `0x180020a4c`
- `0x1800223c0`
- `0x18003085c`
- `0x180035ba0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18003c4e8`
- `0x180071fe0`
- `0x180074544`
- `0x1800745b0`
- `0x180074f84`
- `0x1800752ec`
- `0x180076270`
- `0x180076f60`
- `0x1800774d8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800205c5`
- `ntdll!RtlInitUnicodeString` at `0x1800205c5`
- `ntdll!RtlNtStatusToDosError` at `0x1800209a6`
- `ntdll!RtlNtStatusToDosError` at `0x1800209a6`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180020679`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180020679`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002085a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002085a`

## string_xrefs

- `0x180020574`: `CscSyncPrepareForSync: Callbacks: 0x%p NetworkPath: %ws LocalPath: 0x%p Flags: 0x%x Handle: 0x%p CallerContext: 0x%p`
- `0x180020973`: `CscSyncPrepareForSync: SyncTreeCreateContext failed with %x`
- `0x180020628`: `CscSyncPrepareForSync: SyncActionQueueCreate failed with %x`
- `0x180020733`: `CscSyncPrepareForSync: SyncOpenUNCPathServerForEnumeration failed for %ws with %x`
- `0x180020902`: `CscSyncPrepareForSync: Sparse file could not be opened Forced-offline`
- `0x18002092e`: `CscSyncPrepareForSync: Cached file could not be opened Forced-offline`
- `0x180020829`: `CscSyncPrepareForSync: SyncOpenUNCPathLocalForEnumeration failed for %ws with %x`

## pseudocode

```c
__int64 __fastcall CscSyncPrepareForSyncEx(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // edi
  int v11; // edx
  int v12; // r8d
  unsigned int SingleNodeTree; // ebx
  __int64 v14; // rbx
  unsigned int v15; // eax
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // edx
  char v19; // cl
  __int64 v20; // r9
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  unsigned int v23; // eax
  char v24; // di
  _DWORD *RootItem; // rax
  __int64 v26; // rdx
  ULONG v27; // edi
  __int64 v28; // rcx
  __int16 v30; // [rsp+50h] [rbp-31h] BYREF
  char v31; // [rsp+52h] [rbp-2Fh] BYREF
  __int64 v32; // [rsp+58h] [rbp-29h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-21h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-11h] BYREF

  v32 = 0;
  v7 = a4;
  Handle = 0;
  FileHandle = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"CscSyncPrepareForSync: Callbacks: 0x%p NetworkPath: %ws LocalPath: 0x%p Flags: 0x%x Handle: 0x%p CallerContext: 0x%p",
      a1,
      a2,
      a3,
      a4,
      a5,
      a6);
    WPP_SF_qSqDqq(*((_QWORD *)WPP_GLOBAL_Control + 12), v11, v12, a1, (__int64)a2, a3, v7, (char)a5, a6);
  }
  RtlInitUnicodeString(&DestinationString, a2);
  SingleNodeTree = SyncTreeCreateContext(&v32);
  if ( !SingleNodeTree && v32 )
  {
    *(_DWORD *)(v32 + 8) = v7;
    *(_QWORD *)(v32 + 88) = a7;
    SingleNodeTree = SyncActionQueueCreate(v32 + 24);
    if ( SingleNodeTree )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"CscSyncPrepareForSync: SyncActionQueueCreate failed with %x", SingleNodeTree);
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          12,
          WPP_49c63760df5a37e97d50b2be11371744_Traceguids,
          SingleNodeTree);
      }
      SyncTreeDestroyContext(v32);
      v32 = 0;
      goto LABEL_56;
    }
    v14 = v32;
    *(_QWORD *)(v14 + 72) = CreateSemaphoreW(0, 2, 2, 0);
    if ( !*(_QWORD *)(v32 + 72) )
    {
      SingleNodeTree = -1073741670;
      goto LABEL_56;
    }
    if ( (v7 & 0x400) != 0 )
      SyncItemTraceThreadAttachInitialize();
    if ( (v7 & 4) != 0 )
    {
      v15 = SyncOpenUNCPathServerForEnumeration((unsigned int)&Handle, 0, (unsigned int)&DestinationString, 129, 5);
      SingleNodeTree = v15;
      if ( v15 )
      {
        v16 = v15 + 1073741809;
        if ( (unsigned int)v16 > 0x2B || (v17 = 0x82000000001LL, !_bittest64(&v17, v16)) )
        {
          if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_56;
          }
          SyncTraceOutputInternal(
            L"CscSyncPrepareForSync: SyncOpenUNCPathServerForEnumeration failed for %ws with %x",
            a2,
            SingleNodeTree);
          v18 = 13;
          goto LABEL_25;
        }
        Handle = 0;
        v7 |= 0x100u;
      }
    }
    if ( a3 )
    {
      SyncOpenFileByPath(&FileHandle);
LABEL_38:
      GetSystemTimeAsFileTime((LPFILETIME)(v32 + 80));
      if ( (v7 & 4) != 0 )
        v23 = SyncFullSyncPrepByHandles((_DWORD)Handle, (_DWORD)FileHandle, a1, v7, v32, a6);
      else
        v23 = SyncClientOnlySyncPrepByHandles((_DWORD)FileHandle, a1, v7, v32, a6);
      SingleNodeTree = v23;
      goto LABEL_55;
    }
    v30 = 257;
    v19 = (*(_DWORD *)(v32 + 8) & 0x800) != 0;
    v31 = 1;
    SingleNodeTree = SyncOpenUNCPathLocalForEnumeration(
                       &FileHandle,
                       5u,
                       (__int64)&v30,
                       (__int64)&v30 + 1,
                       (__int64)&v31,
                       v19,
                       0);
    v21 = SingleNodeTree + 1073741809;
    if ( (unsigned int)v21 <= 0x2B )
    {
      v22 = 0x82000000001LL;
      if ( _bittest64(&v22, v21) )
      {
        FileHandle = 0;
        goto LABEL_38;
      }
    }
    switch ( SingleNodeTree )
    {
      case 0xC00000B7:
        v24 = 1;
        break;
      case 0xC00000B8:
        v24 = 0;
        break;
      case 0u:
        if ( !(_BYTE)v30 || HIBYTE(v30) )
          v7 |= 0x100u;
        goto LABEL_38;
      default:
        if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_56;
        }
        SyncTraceOutputInternal(
          L"CscSyncPrepareForSync: SyncOpenUNCPathLocalForEnumeration failed for %ws with %x",
          a2,
          SingleNodeTree);
        v18 = 16;
LABEL_25:
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          v18,
          (unsigned int)WPP_49c63760df5a37e97d50b2be11371744_Traceguids,
          (_DWORD)a2,
          SingleNodeTree);
        goto LABEL_56;
    }
    LOBYTE(v20) = v24 ^ 1;
    SingleNodeTree = SyncEnumCreateSingleNodeTree(v32, a1, a6, v20);
    if ( v24 )
    {
      RootItem = (_DWORD *)CscSyncGetRootItem(v32);
      *RootItem |= 0x200000u;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_55;
      }
      SyncTraceOutputInternal(L"CscSyncPrepareForSync: Sparse file could not be opened Forced-offline");
      v26 = 14;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_55;
      }
      SyncTraceOutputInternal(L"CscSyncPrepareForSync: Cached file could not be opened Forced-offline");
      v26 = 15;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), v26, WPP_49c63760df5a37e97d50b2be11371744_Traceguids);
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"CscSyncPrepareForSync: SyncTreeCreateContext failed with %x", SingleNodeTree);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_49c63760df5a37e97d50b2be11371744_Traceguids, SingleNodeTree);
  }
LABEL_55:
  v27 = 0;
  if ( !SingleNodeTree )
  {
LABEL_59:
    *a5 = v32;
    goto LABEL_60;
  }
LABEL_56:
  v27 = RtlNtStatusToDosError(SingleNodeTree);
  if ( !v27 )
    goto LABEL_59;
  v28 = v32;
  *a5 = 0;
  if ( v28 )
    CscSyncReleaseSyncContext(v28);
LABEL_60:
  if ( Handle )
    SyncCloseFile(Handle);
  if ( FileHandle )
    SyncCloseFile(FileHandle);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"CscSyncPrepareForSync: %d", v27);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_49c63760df5a37e97d50b2be11371744_Traceguids, v27);
  }
  return v27;
}

```

## disassembly

```asm
0x180020514  push    rbp
0x180020516  push    rbx
0x180020517  push    rsi
0x180020518  push    rdi
0x180020519  push    r12
0x18002051b  push    r13
0x18002051d  push    r14
0x18002051f  push    r15
0x180020521  lea     rbp, [rsp-7]
0x180020526  sub     rsp, 88h
0x18002052d  xor     eax, eax
0x18002052f  xorps   xmm0, xmm0
0x180020532  mov     [rbp+3Fh+var_68], rax
0x180020536  mov     edi, r9d
0x180020539  mov     [rbp+3Fh+Handle], rax
0x18002053d  mov     r14, r8
0x180020540  mov     [rbp+3Fh+FileHandle], rax
0x180020544  mov     rsi, rdx
0x180020547  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18002054b  mov     r15, rcx
0x18002054e  mov     rax, cs:WPP_GLOBAL_Control
0x180020555  lea     rcx, WPP_GLOBAL_Control
0x18002055c  mov     r12, [rbp+3Fh+arg_28]
0x180020560  mov     r13, [rbp+3Fh+arg_20]
0x180020564  cmp     rax, rcx
0x180020567  jz      short loc_1800205BE
0x180020569  test    byte ptr [rax+6Ch], 4
0x18002056d  jz      short loc_1800205BE
0x18002056f  mov     [rsp+0C0h+var_90], r12
0x180020574  lea     rcx, aCscsyncprepare_1; "CscSyncPrepareForSync: Callbacks: 0x%p "...
0x18002057b  mov     [rsp+0C0h+var_98], r13
0x180020580  mov     [rsp+0C0h+var_A0], r9d
0x180020585  mov     r9, r8
0x180020588  mov     r8, rdx
0x18002058b  mov     rdx, r15
0x18002058e  call    SyncTraceOutputInternal
0x180020593  mov     rcx, cs:WPP_GLOBAL_Control
0x18002059a  mov     r9, r15
0x18002059d  mov     qword ptr [rsp+0C0h+var_80], r12
0x1800205a2  mov     [rsp+0C0h+var_88], r13
0x1800205a7  mov     dword ptr [rsp+0C0h+var_90], edi
0x1800205ab  mov     rcx, [rcx+60h]
0x1800205af  mov     [rsp+0C0h+var_98], r14
0x1800205b4  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x1800205b9  call    WPP_SF_qSqDqq
0x1800205be  mov     rdx, rsi; SourceString
0x1800205c1  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800205c5  call    cs:__imp_RtlInitUnicodeString
0x1800205cb  lea     rcx, [rbp+3Fh+var_68]
0x1800205cf  call    SyncTreeCreateContext
0x1800205d4  mov     ebx, eax
0x1800205d6  test    eax, eax
0x1800205d8  jnz     loc_180020958
0x1800205de  mov     rax, [rbp+3Fh+var_68]
0x1800205e2  test    rax, rax
0x1800205e5  jz      loc_180020958
0x1800205eb  mov     [rax+8], edi
0x1800205ee  mov     rcx, [rbp+3Fh+var_68]
0x1800205f2  mov     rax, [rbp+3Fh+arg_30]
0x1800205f6  mov     [rcx+58h], rax
0x1800205fa  mov     rcx, [rbp+3Fh+var_68]
0x1800205fe  add     rcx, 18h
0x180020602  call    SyncActionQueueCreate
0x180020607  mov     ebx, eax
0x180020609  test    eax, eax
0x18002060b  jz      short loc_180020669
0x18002060d  mov     rax, cs:WPP_GLOBAL_Control
0x180020614  lea     r14, WPP_GLOBAL_Control
0x18002061b  cmp     rax, r14
0x18002061e  jz      short loc_180020653
0x180020620  test    byte ptr [rax+6Ch], 1
0x180020624  jz      short loc_180020653
0x180020626  mov     edx, ebx
0x180020628  lea     rcx, aCscsyncprepare_4; "CscSyncPrepareForSync: SyncActionQueueC"...
0x18002062f  call    SyncTraceOutputInternal
0x180020634  mov     rcx, cs:WPP_GLOBAL_Control
0x18002063b  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x180020642  mov     edx, 0Ch
0x180020647  mov     r9d, ebx
0x18002064a  mov     rcx, [rcx+60h]
0x18002064e  call    WPP_SF_d
0x180020653  mov     rcx, [rbp+3Fh+var_68]
0x180020657  call    SyncTreeDestroyContext
0x18002065c  mov     [rbp+3Fh+var_68], 0
0x180020664  jmp     loc_1800209A4
0x180020669  mov     rbx, [rbp+3Fh+var_68]
0x18002066d  xor     r9d, r9d; lpName
0x180020670  xor     ecx, ecx; lpSemaphoreAttributes
0x180020672  lea     edx, [r9+2]; lInitialCount
0x180020676  mov     r8d, edx; lMaximumCount
0x180020679  call    cs:__imp_CreateSemaphoreW
0x18002067f  mov     [rbx+48h], rax
0x180020683  mov     rax, [rbp+3Fh+var_68]
0x180020687  cmp     qword ptr [rax+48h], 0
0x18002068c  jnz     short loc_18002069F
0x18002068e  mov     ebx, 0C000009Ah
0x180020693  lea     r14, WPP_GLOBAL_Control
0x18002069a  jmp     loc_1800209A4
0x18002069f  bt      edi, 0Ah
0x1800206a3  jnb     short loc_1800206AA
0x1800206a5  call    SyncItemTraceThreadAttachInitialize
0x1800206aa  test    dil, 4
0x1800206ae  jz      short loc_1800206F9
0x1800206b0  mov     r9d, 81h
0x1800206b6  mov     [rsp+0C0h+var_A0], 5
0x1800206be  lea     r8, [rbp+3Fh+DestinationString]
0x1800206c2  xor     edx, edx
0x1800206c4  lea     rcx, [rbp+3Fh+Handle]
0x1800206c8  call    SyncOpenUNCPathServerForEnumeration
0x1800206cd  mov     ebx, eax
0x1800206cf  test    eax, eax
0x1800206d1  jz      short loc_1800206F9
0x1800206d3  add     eax, 3FFFFFF1h
0x1800206d8  cmp     eax, 2Bh ; '+'
0x1800206db  ja      short loc_18002070F
0x1800206dd  mov     rcx, 82000000001h
0x1800206e7  bt      rcx, rax
0x1800206eb  jnb     short loc_18002070F
0x1800206ed  mov     [rbp+3Fh+Handle], 0
0x1800206f5  bts     edi, 8
0x1800206f9  test    r14, r14
0x1800206fc  jz      short loc_18002076A
0x1800206fe  mov     r8, r14
0x180020701  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180020705  call    SyncOpenFileByPath
0x18002070a  jmp     loc_180020852
0x18002070f  mov     rax, cs:WPP_GLOBAL_Control
0x180020716  lea     r14, WPP_GLOBAL_Control
0x18002071d  cmp     rax, r14
0x180020720  jz      loc_1800209A4
0x180020726  test    byte ptr [rax+6Ch], 1
0x18002072a  jz      loc_1800209A4
0x180020730  mov     r8d, ebx
0x180020733  lea     rcx, aCscsyncprepare_2; "CscSyncPrepareForSync: SyncOpenUNCPathS"...
0x18002073a  mov     rdx, rsi
0x18002073d  call    SyncTraceOutputInternal
0x180020742  mov     edx, 0Dh
0x180020747  mov     rcx, cs:WPP_GLOBAL_Control
0x18002074e  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x180020755  mov     r9, rsi
0x180020758  mov     [rsp+0C0h+var_A0], ebx
0x18002075c  mov     rcx, [rcx+60h]
0x180020760  call    WPP_SF_Sd
0x180020765  jmp     loc_1800209A4
0x18002076a  mov     rax, [rbp+3Fh+var_68]
0x18002076e  lea     r8, [rbp+3Fh+DestinationString]
0x180020772  xor     r14d, r14d
0x180020775  mov     byte ptr [rbp+3Fh+var_70], 1
0x180020779  mov     [rsp+0C0h+var_78], r14; __int64
0x18002077e  mov     r9d, 81h
0x180020784  xor     edx, edx
0x180020786  mov     byte ptr [rbp+3Fh+var_70+1], 1
0x18002078a  mov     ecx, [rax+8]
0x18002078d  lea     rax, [rbp+3Fh+var_70+2]
0x180020791  shr     ecx, 0Bh
0x180020794  and     cl, 1
0x180020797  mov     byte ptr [rbp+3Fh+var_70+2], 1
0x18002079b  mov     [rsp+0C0h+var_80], cl; char
0x18002079f  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1800207a3  mov     [rsp+0C0h+var_88], rax; __int64
0x1800207a8  lea     rax, [rbp+3Fh+var_70+1]
0x1800207ac  mov     [rsp+0C0h+var_90], rax; __int64
0x1800207b1  lea     rax, [rbp+3Fh+var_70]
0x1800207b5  mov     [rsp+0C0h+var_98], rax; __int64
0x1800207ba  mov     [rsp+0C0h+var_A0], 5; ULONG
0x1800207c2  call    SyncOpenUNCPathLocalForEnumeration
0x1800207c7  mov     ebx, eax
0x1800207c9  add     eax, 3FFFFFF1h
0x1800207ce  cmp     eax, 2Bh ; '+'
0x1800207d1  ja      short loc_1800207E9
0x1800207d3  mov     rcx, 82000000001h
0x1800207dd  bt      rcx, rax
0x1800207e1  jnb     short loc_1800207E9
0x1800207e3  mov     [rbp+3Fh+FileHandle], r14
0x1800207e7  jmp     short loc_180020852
0x1800207e9  cmp     ebx, 0C00000B7h
0x1800207ef  jz      loc_1800208B4
0x1800207f5  cmp     ebx, 0C00000B8h
0x1800207fb  jz      loc_1800208AF
0x180020801  test    ebx, ebx
0x180020803  jz      short loc_180020842
0x180020805  mov     rax, cs:WPP_GLOBAL_Control
0x18002080c  lea     r14, WPP_GLOBAL_Control
0x180020813  cmp     rax, r14
0x180020816  jz      loc_1800209A4
0x18002081c  test    byte ptr [rax+6Ch], 1
0x180020820  jz      loc_1800209A4
0x180020826  mov     r8d, ebx
0x180020829  lea     rcx, aCscsyncprepare; "CscSyncPrepareForSync: SyncOpenUNCPathL"...
0x180020830  mov     rdx, rsi
0x180020833  call    SyncTraceOutputInternal
0x180020838  mov     edx, 10h
0x18002083d  jmp     loc_180020747
0x180020842  cmp     byte ptr [rbp+3Fh+var_70], r14b
0x180020846  jz      short loc_18002084E
0x180020848  cmp     byte ptr [rbp+3Fh+var_70+1], r14b
0x18002084c  jz      short loc_180020852
0x18002084e  bts     edi, 8
0x180020852  mov     rcx, [rbp+3Fh+var_68]
0x180020856  add     rcx, 50h ; 'P'; lpSystemTimeAsFileTime
0x18002085a  call    cs:__imp_GetSystemTimeAsFileTime
0x180020860  test    dil, 4
0x180020864  jz      short loc_180020895
0x180020866  mov     rax, [rbp+3Fh+var_68]
0x18002086a  mov     r9d, edi
0x18002086d  mov     rdx, [rbp+3Fh+FileHandle]
0x180020871  mov     r8, r15
0x180020874  mov     rcx, [rbp+3Fh+Handle]
0x180020878  mov     [rsp+0C0h+var_98], r12
0x18002087d  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180020882  call    SyncFullSyncPrepByHandles
0x180020887  mov     ebx, eax
0x180020889  lea     r14, WPP_GLOBAL_Control
0x180020890  jmp     loc_18002099E
0x180020895  mov     r9, [rbp+3Fh+var_68]
0x180020899  mov     r8d, edi
0x18002089c  mov     rcx, [rbp+3Fh+FileHandle]
0x1800208a0  mov     rdx, r15
0x1800208a3  mov     qword ptr [rsp+0C0h+var_A0], r12
0x1800208a8  call    SyncClientOnlySyncPrepByHandles
0x1800208ad  jmp     short loc_180020887
0x1800208af  mov     dil, r14b
0x1800208b2  jmp     short loc_1800208B7
0x1800208b4  mov     dil, 1
0x1800208b7  mov     rcx, [rbp+3Fh+var_68]
0x1800208bb  mov     r9b, dil
0x1800208be  xor     r9b, 1
0x1800208c2  mov     r8, r12
0x1800208c5  mov     rdx, r15
0x1800208c8  call    SyncEnumCreateSingleNodeTree
0x1800208cd  mov     ebx, eax
0x1800208cf  test    dil, dil
0x1800208d2  jz      short loc_180020915
0x1800208d4  mov     rcx, [rbp+3Fh+var_68]
0x1800208d8  call    CscSyncGetRootItem
0x1800208dd  bts     dword ptr [rax], 15h
0x1800208e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800208e8  lea     r14, WPP_GLOBAL_Control
0x1800208ef  cmp     rax, r14
0x1800208f2  jz      loc_18002099E
0x1800208f8  test    byte ptr [rax+6Ch], 1
0x1800208fc  jz      loc_18002099E
0x180020902  lea     rcx, aCscsyncprepare_5; "CscSyncPrepareForSync: Sparse file coul"...
0x180020909  call    SyncTraceOutputInternal
0x18002090e  mov     edx, 0Eh
0x180020913  jmp     short loc_18002093F
0x180020915  mov     rax, cs:WPP_GLOBAL_Control
0x18002091c  lea     r14, WPP_GLOBAL_Control
0x180020923  cmp     rax, r14
0x180020926  jz      short loc_18002099E
0x180020928  test    byte ptr [rax+6Ch], 1
0x18002092c  jz      short loc_18002099E
0x18002092e  lea     rcx, aCscsyncprepare_0; "CscSyncPrepareForSync: Cached file coul"...
0x180020935  call    SyncTraceOutputInternal
0x18002093a  mov     edx, 0Fh
0x18002093f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020946  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x18002094d  mov     rcx, [rcx+60h]
0x180020951  call    WPP_SF_
0x180020956  jmp     short loc_18002099E
0x180020958  mov     rax, cs:WPP_GLOBAL_Control
0x18002095f  lea     r14, WPP_GLOBAL_Control
0x180020966  cmp     rax, r14
0x180020969  jz      short loc_18002099E
0x18002096b  test    byte ptr [rax+6Ch], 1
0x18002096f  jz      short loc_18002099E
0x180020971  mov     edx, ebx
0x180020973  lea     rcx, aCscsyncprepare_6; "CscSyncPrepareForSync: SyncTreeCreateCo"...
0x18002097a  call    SyncTraceOutputInternal
0x18002097f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020986  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x18002098d  mov     edx, 0Bh
0x180020992  mov     r9d, ebx
0x180020995  mov     rcx, [rcx+60h]
0x180020999  call    WPP_SF_d
0x18002099e  xor     edi, edi
0x1800209a0  test    ebx, ebx
0x1800209a2  jz      short loc_1800209CA
0x1800209a4  mov     ecx, ebx; Status
0x1800209a6  call    cs:__imp_RtlNtStatusToDosError
0x1800209ac  mov     edi, eax
0x1800209ae  test    eax, eax
0x1800209b0  jz      short loc_1800209CA
0x1800209b2  mov     rcx, [rbp+3Fh+var_68]
0x1800209b6  mov     qword ptr [r13+0], 0
0x1800209be  test    rcx, rcx
0x1800209c1  jz      short loc_1800209D2
0x1800209c3  call    CscSyncReleaseSyncContext
0x1800209c8  jmp     short loc_1800209D2
0x1800209ca  mov     rax, [rbp+3Fh+var_68]
0x1800209ce  mov     [r13+0], rax
0x1800209d2  mov     rcx, [rbp+3Fh+Handle]; Handle
0x1800209d6  test    rcx, rcx
0x1800209d9  jz      short loc_1800209E0
0x1800209db  call    SyncCloseFile
0x1800209e0  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1800209e4  test    rcx, rcx
0x1800209e7  jz      short loc_1800209EE
0x1800209e9  call    SyncCloseFile
0x1800209ee  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
