# RefsCheckpointVolume

- ea: `0x1c01cd860`
- end: `0x1c01cdfd5`
- name: `RefsCheckpointVolume`
- size: `1909`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x1c0196bc8`
- `0x1c01c5b68`
- `0x1c01cd29c`
- `0x1c01cd36c`

## callees

- `0x1c000f770`
- `0x1c004c1f0`
- `0x1c0052844`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006ab80`
- `0x1c00b2eb0`
- `0x1c00b36c0`
- `0x1c00b4d48`
- `0x1c016154c`
- `0x1c01cd860`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdac4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdba8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdf17`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdfbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdac4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdba8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdf17`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01cdfbf`
- `ntoskrnl!KeInitializeEvent` at `0x1c01cda72`
- `ntoskrnl!KeInitializeEvent` at `0x1c01cda72`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c01cdae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c01cdbd8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c01cdae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c01cdbd8`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cd8ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cda88`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cde18`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cded5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cdf6b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cd8ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cda88`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cde18`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cded5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01cdf6b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cd928`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdab1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdb15`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cde2e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdefc`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdf92`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cd928`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdab1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdb15`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cde2e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdefc`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01cdf92`
- `ntoskrnl!KeSetEvent` at `0x1c01cdeed`
- `ntoskrnl!KeSetEvent` at `0x1c01cdf83`
- `ntoskrnl!KeSetEvent` at `0x1c01cdeed`
- `ntoskrnl!KeSetEvent` at `0x1c01cdf83`
- `ntoskrnl!KeResetEvent` at `0x1c01cdb06`
- `ntoskrnl!KeResetEvent` at `0x1c01cdb06`
- `ntoskrnl!KeReadStateEvent` at `0x1c01cda9e`
- `ntoskrnl!KeReadStateEvent` at `0x1c01cda9e`

## pseudocode

```c
void __fastcall RefsCheckpointVolume(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        char a5,
        char a6,
        char a7,
        unsigned __int8 *a8,
        unsigned __int8 *a9)
{
  unsigned __int8 *v12; // r14
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  NTSTATUS v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // ecx
  int v21; // edx
  __int128 *v22; // r8
  int v23; // r9d
  unsigned __int8 *v24; // rax
  NTSTATUS v25; // r14d
  __int64 v26; // [rsp+0h] [rbp-D8h] BYREF
  char v27; // [rsp+30h] [rbp-A8h]
  char v28; // [rsp+31h] [rbp-A7h]
  char v29; // [rsp+32h] [rbp-A6h]
  int v30; // [rsp+34h] [rbp-A4h]
  NTSTATUS Status; // [rsp+38h] [rbp-A0h]
  __int64 *v32; // [rsp+40h] [rbp-98h]
  union _LARGE_INTEGER Timeout; // [rsp+48h] [rbp-90h] BYREF
  __int64 v34; // [rsp+50h] [rbp-88h]
  __int64 v35; // [rsp+58h] [rbp-80h]
  unsigned __int8 *v36; // [rsp+60h] [rbp-78h]
  unsigned __int8 *v37; // [rsp+68h] [rbp-70h]
  struct _KEVENT Event; // [rsp+70h] [rbp-68h] BYREF
  __int128 v39; // [rsp+88h] [rbp-50h] BYREF
  __int128 v40; // [rsp+98h] [rbp-40h]

  v32 = &v26;
  v29 = a3;
  v12 = a9;
  v36 = a9;
  v37 = a8;
  v35 = a2;
  v39 = 0;
  v40 = 0;
  Timeout.QuadPart = 0;
  v28 = 0;
  v27 = 0;
  v13 = 0;
  v34 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( (*(_DWORD *)(a2 + 4) & 0x2000000) == 0 )
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 112));
    v14 = *(_QWORD *)(a2 + 104);
    if ( v14 )
    {
      v13 = *(_QWORD *)(a2 + 104);
      v34 = v13;
      MsReferenceVolume(v14);
    }
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 112));
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids, 3221226094LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      RefsRaiseStatusInternal(a1, 3221226094LL);
    }
    LOBYTE(v15) = 1;
    if ( a4 )
    {
      memset(&Event, 0, sizeof(Event));
      RefsAcquireSharedVcb(a1, a2, v15, v16);
      v27 = 1;
      if ( (*(_DWORD *)(a2 + 4) & 0x8000823) != 1 )
      {
        if ( ((*(_BYTE *)(a1 + 40) - 2) & 0xEF) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              11,
              WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids,
              3221226094LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741202);
          RefsRaiseStatusInternal(a1, 3221226094LL);
        }
        local_unwind_0(v32, &loc_1C01CDF23);
      }
      KeInitializeEvent(&Event, NotificationEvent, 0);
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 3848));
      if ( !KeReadStateEvent((PRKEVENT)(a2 + 3904)) )
      {
        KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 3848));
        ExReleaseResourceLite((PERESOURCE)(a2 + 1424));
        v27 = 0;
        KeWaitForSingleObject((PVOID)(a2 + 3904), Executive, 0, 0, 0);
        local_unwind_0(v32, &loc_1C01CDF23);
      }
      KeResetEvent((PRKEVENT)(a2 + 3904));
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 3848));
      v28 = 1;
      v17 = MsSyncForFreeSpace(v13, &Event);
      Status = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids,
            (unsigned int)v17);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(Status);
        RefsRaiseStatusInternal(a1, (unsigned int)Status);
      }
      ExReleaseResourceLite((PERESOURCE)(a2 + 1424));
      v27 = 0;
      Timeout.QuadPart = -160000000;
      while ( KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout) )
        MsPulseLazyWriterScan();
      LOBYTE(v18) = 1;
      RefsAcquireSharedVcb(a1, a2, v18, v19);
      v27 = 1;
      v20 = *(_DWORD *)(a2 + 4);
      if ( (v20 & 0x8000823) != 1 )
      {
        if ( ((*(_BYTE *)(a1 + 40) - 2) & 0xEF) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids,
              3221226094LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741202);
          RefsRaiseStatusInternal(a1, 3221226094LL);
        }
        local_unwind_0(v32, &loc_1C01CDF23);
      }
      v12 = v36;
    }
    else
    {
      RefsAcquireSharedVcb(a1, a2, v15, v16);
      v27 = 1;
      v20 = *(_DWORD *)(a2 + 4);
      if ( (v20 & 0x8000823) != 1 )
      {
        if ( ((*(_BYTE *)(a1 + 40) - 2) & 0xEF) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids,
              3221226094LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741202);
          RefsRaiseStatusInternal(a1, 3221226094LL);
        }
        local_unwind_0(v32, &loc_1C01CDF23);
      }
    }
    v21 = a4 != 0 ? 1 : 17;
    v30 = v21;
    if ( a6 )
    {
      v21 |= 0x400u;
      v30 = v21;
    }
    if ( a7 )
    {
      v21 |= 0x200u;
      v30 = v21;
    }
    if ( v29 )
    {
      if ( a5 )
      {
        v21 |= 0x80u;
        v30 = v21;
      }
      if ( (v20 & 0x100000) != 0 )
      {
        LODWORD(v22) = 0;
        v23 = 0;
      }
      else
      {
        v39 = *(_OWORD *)(a2 + 880);
        v40 = *(_OWORD *)(a2 + 928);
        v22 = &v39;
        v23 = 32;
      }
      v24 = v37;
    }
    else
    {
      LODWORD(v22) = 0;
      v23 = 0;
      v24 = 0;
      v12 = 0;
    }
    v25 = MsFlushVolume(v13, v21, (_DWORD)v22, v23, v24, v12);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 480));
    *(_DWORD *)(a2 + 472) &= ~1u;
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 480));
    if ( v25 < 0 )
    {
      if ( ((*(_BYTE *)(a1 + 40) - 2) & 0xEF) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids,
            (unsigned int)v25);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(v25);
        RefsRaiseStatusInternal(a1, (unsigned int)v25);
      }
      local_unwind_0(v32, &loc_1C01CDF23);
    }
    if ( v28 )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 3848));
      KeSetEvent((PRKEVENT)(a2 + 3904), 0, 0);
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 3848));
    }
    MsReleaseVolume(v13);
    ExReleaseResourceLite((PERESOURCE)(a2 + 1424));
  }
}

```

## disassembly

```asm
0x1c01cd860  mov     r11, rsp
0x1c01cd863  mov     [r11+18h], rbx
0x1c01cd867  push    rsi
0x1c01cd868  push    rdi
0x1c01cd869  push    r13
0x1c01cd86b  push    r14
0x1c01cd86d  push    r15
0x1c01cd86f  sub     rsp, 0B0h
0x1c01cd876  mov     rax, cs:__security_cookie
0x1c01cd87d  xor     rax, rsp
0x1c01cd880  mov     [rsp+0D8h+var_30], rax
0x1c01cd888  mov     [rsp+0D8h+var_98], rsp
0x1c01cd88d  mov     r13b, r9b
0x1c01cd890  mov     [rsp+0D8h+var_A6], r8b
0x1c01cd895  mov     rdi, rdx
0x1c01cd898  mov     rsi, rcx
0x1c01cd89b  mov     r14, [rsp+0D8h+arg_40]
0x1c01cd8a3  mov     [rsp+0D8h+var_78], r14
0x1c01cd8a8  mov     rax, [rsp+0D8h+arg_38]
0x1c01cd8b0  mov     [rsp+0D8h+var_70], rax
0x1c01cd8b5  mov     [r11-80h], rdx
0x1c01cd8b9  xorps   xmm0, xmm0
0x1c01cd8bc  movups  xmmword ptr [r11-50h], xmm0
0x1c01cd8c1  movups  xmmword ptr [r11-40h], xmm0
0x1c01cd8c6  and     qword ptr [rsp+0D8h+var_90], 0
0x1c01cd8cc  mov     [rsp+0D8h+var_A7], 0
0x1c01cd8d1  mov     [rsp+0D8h+var_A8], 0
0x1c01cd8d6  xor     r15d, r15d
0x1c01cd8d9  mov     [rsp+0D8h+var_88], r15
0x1c01cd8de  test    rax, rax
0x1c01cd8e1  jz      short loc_1C01CD8E6
0x1c01cd8e3  mov     [rax], r15b
0x1c01cd8e6  test    r14, r14
0x1c01cd8e9  jz      short loc_1C01CD8EE
0x1c01cd8eb  mov     [r14], r15b
0x1c01cd8ee  test    dword ptr [rdx+4], 2000000h
0x1c01cd8f5  jnz     loc_1C01CDF23
0x1c01cd8fb  lea     rcx, [rdx+70h]; Mutex
0x1c01cd8ff  call    cs:__imp_KeAcquireGuardedMutex
0x1c01cd906  nop     dword ptr [rax+rax+00h]
0x1c01cd90b  mov     rax, [rdi+68h]
0x1c01cd90f  test    rax, rax
0x1c01cd912  jz      short loc_1C01CD924
0x1c01cd914  mov     r15, rax
0x1c01cd917  mov     [rsp+0D8h+var_88], rax
0x1c01cd91c  mov     rcx, rax
0x1c01cd91f  call    MsReferenceVolume
0x1c01cd924  lea     rcx, [rdi+70h]; Mutex
0x1c01cd928  call    cs:__imp_KeReleaseGuardedMutex
0x1c01cd92f  nop     dword ptr [rax+rax+00h]
0x1c01cd934  xor     ebx, ebx
0x1c01cd936  test    r15, r15
0x1c01cd939  jnz     short loc_1C01CD9A4
0x1c01cd93b  lea     rax, WPP_GLOBAL_Control
0x1c01cd942  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cd949  cmp     rcx, rax
0x1c01cd94c  jz      short loc_1C01CD976
0x1c01cd94e  test    dword ptr [rcx+2Ch], 100h
0x1c01cd955  jz      short loc_1C01CD976
0x1c01cd957  cmp     byte ptr [rcx+29h], 4
0x1c01cd95b  jb      short loc_1C01CD976
0x1c01cd95d  lea     edx, [rbx+0Ah]
0x1c01cd960  mov     r9d, 0C000026Eh
0x1c01cd966  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cd96d  mov     rcx, [rcx+18h]
0x1c01cd971  call    WPP_SF_D
0x1c01cd976  mov     al, cs:RefsStatusDebugEnabled
0x1c01cd97c  test    al, al
0x1c01cd97e  jz      short loc_1C01CD997
0x1c01cd980  mov     r8d, 0CBh
0x1c01cd986  lea     rdx, aTranssupC; "TransSup.c"
0x1c01cd98d  mov     ecx, 0C000026Eh; Status
0x1c01cd992  call    RefsStatusDebug
0x1c01cd997  mov     edx, 0C000026Eh
0x1c01cd99c  mov     rcx, rsi
0x1c01cd99f  call    RefsRaiseStatusInternal
0x1c01cd9a4  mov     r8b, 1
0x1c01cd9a7  mov     rdx, rdi
0x1c01cd9aa  mov     rcx, rsi
0x1c01cd9ad  test    r13b, r13b
0x1c01cd9b0  jz      loc_1C01CDCA4
0x1c01cd9b6  xorps   xmm0, xmm0
0x1c01cd9b9  xor     eax, eax
0x1c01cd9bb  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x1c01cd9c0  mov     [rsp+0D8h+Event.Header.WaitListHead.Blink], rax
0x1c01cd9c8  call    RefsAcquireSharedVcb
0x1c01cd9cd  mov     [rsp+0D8h+var_A8], 1
0x1c01cd9d2  mov     eax, [rdi+4]
0x1c01cd9d5  and     eax, 8000823h
0x1c01cd9da  cmp     eax, 1
0x1c01cd9dd  jz      loc_1C01CDA68
0x1c01cd9e3  mov     al, [rsi+28h]
0x1c01cd9e6  sub     al, 2
0x1c01cd9e8  test    al, 0EFh
0x1c01cd9ea  jz      short loc_1C01CDA57
0x1c01cd9ec  lea     rax, WPP_GLOBAL_Control
0x1c01cd9f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cd9fa  cmp     rcx, rax
0x1c01cd9fd  jz      short loc_1C01CDA29
0x1c01cd9ff  test    dword ptr [rcx+2Ch], 100h
0x1c01cda06  jz      short loc_1C01CDA29
0x1c01cda08  cmp     byte ptr [rcx+29h], 4
0x1c01cda0c  jb      short loc_1C01CDA29
0x1c01cda0e  mov     edx, 0Bh
0x1c01cda13  mov     r9d, 0C000026Eh
0x1c01cda19  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cda20  mov     rcx, [rcx+18h]
0x1c01cda24  call    WPP_SF_D
0x1c01cda29  mov     al, cs:RefsStatusDebugEnabled
0x1c01cda2f  test    al, al
0x1c01cda31  jz      short loc_1C01CDA4A
0x1c01cda33  mov     r8d, 0E8h
0x1c01cda39  lea     rdx, aTranssupC; "TransSup.c"
0x1c01cda40  mov     ecx, 0C000026Eh; Status
0x1c01cda45  call    RefsStatusDebug
0x1c01cda4a  mov     edx, 0C000026Eh
0x1c01cda4f  mov     rcx, rsi
0x1c01cda52  call    RefsRaiseStatusInternal
0x1c01cda57  lea     rdx, loc_1C01CDF23
0x1c01cda5e  mov     rcx, [rsp+0D8h+var_98]
0x1c01cda63  call    _local_unwind_0
0x1c01cda68  xor     r8d, r8d; State
0x1c01cda6b  xor     edx, edx; Type
0x1c01cda6d  lea     rcx, [rsp+0D8h+Event]; Event
0x1c01cda72  call    cs:__imp_KeInitializeEvent
0x1c01cda79  nop     dword ptr [rax+rax+00h]
0x1c01cda7e  lea     rbx, [rdi+0F08h]
0x1c01cda85  mov     rcx, rbx; Mutex
0x1c01cda88  call    cs:__imp_KeAcquireGuardedMutex
0x1c01cda8f  nop     dword ptr [rax+rax+00h]
0x1c01cda94  lea     r14, [rdi+0F40h]
0x1c01cda9b  mov     rcx, r14; Event
0x1c01cda9e  call    cs:__imp_KeReadStateEvent
0x1c01cdaa5  nop     dword ptr [rax+rax+00h]
0x1c01cdaaa  test    eax, eax
0x1c01cdaac  jnz     short loc_1C01CDB03
0x1c01cdaae  mov     rcx, rbx; Mutex
0x1c01cdab1  call    cs:__imp_KeReleaseGuardedMutex
0x1c01cdab8  nop     dword ptr [rax+rax+00h]
0x1c01cdabd  lea     rcx, [rdi+590h]; Resource
0x1c01cdac4  call    cs:__imp_ExReleaseResourceLite
0x1c01cdacb  nop     dword ptr [rax+rax+00h]
0x1c01cdad0  mov     [rsp+0D8h+var_A8], 0
0x1c01cdad5  and     [rsp+0D8h+Timeout], 0
0x1c01cdadb  xor     r9d, r9d; Alertable
0x1c01cdade  xor     r8d, r8d; WaitMode
0x1c01cdae1  xor     edx, edx; WaitReason
0x1c01cdae3  mov     rcx, r14; Object
0x1c01cdae6  call    cs:__imp_KeWaitForSingleObject
0x1c01cdaed  nop     dword ptr [rax+rax+00h]
0x1c01cdaf2  lea     rdx, loc_1C01CDF23
0x1c01cdaf9  mov     rcx, [rsp+0D8h+var_98]
0x1c01cdafe  call    _local_unwind_0
0x1c01cdb03  mov     rcx, r14; Event
0x1c01cdb06  call    cs:__imp_KeResetEvent
0x1c01cdb0d  nop     dword ptr [rax+rax+00h]
0x1c01cdb12  mov     rcx, rbx; Mutex
0x1c01cdb15  call    cs:__imp_KeReleaseGuardedMutex
0x1c01cdb1c  nop     dword ptr [rax+rax+00h]
0x1c01cdb21  mov     [rsp+0D8h+var_A7], 1
0x1c01cdb26  lea     rdx, [rsp+0D8h+Event]
0x1c01cdb2b  mov     rcx, r15
0x1c01cdb2e  call    MsSyncForFreeSpace
0x1c01cdb33  mov     r9d, eax
0x1c01cdb36  mov     [rsp+0D8h+Status], eax
0x1c01cdb3a  xor     ebx, ebx
0x1c01cdb3c  test    eax, eax
0x1c01cdb3e  jns     short loc_1C01CDBA1
0x1c01cdb40  lea     rax, WPP_GLOBAL_Control
0x1c01cdb47  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cdb4e  cmp     rcx, rax
0x1c01cdb51  jz      short loc_1C01CDB75
0x1c01cdb53  test    dword ptr [rcx+2Ch], 100h
0x1c01cdb5a  jz      short loc_1C01CDB75
0x1c01cdb5c  cmp     byte ptr [rcx+29h], 4
0x1c01cdb60  jb      short loc_1C01CDB75
0x1c01cdb62  lea     edx, [rbx+0Ch]
0x1c01cdb65  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cdb6c  mov     rcx, [rcx+18h]
0x1c01cdb70  call    WPP_SF_D
0x1c01cdb75  mov     al, cs:RefsStatusDebugEnabled
0x1c01cdb7b  test    al, al
0x1c01cdb7d  jz      short loc_1C01CDB95
0x1c01cdb7f  mov     r8d, 114h
0x1c01cdb85  lea     rdx, aTranssupC; "TransSup.c"
0x1c01cdb8c  mov     ecx, [rsp+0D8h+Status]; Status
0x1c01cdb90  call    RefsStatusDebug
0x1c01cdb95  mov     edx, [rsp+0D8h+Status]
0x1c01cdb99  mov     rcx, rsi
0x1c01cdb9c  call    RefsRaiseStatusInternal
0x1c01cdba1  lea     rcx, [rdi+590h]; Resource
0x1c01cdba8  call    cs:__imp_ExReleaseResourceLite
0x1c01cdbaf  nop     dword ptr [rax+rax+00h]
0x1c01cdbb4  mov     [rsp+0D8h+var_A8], bl
0x1c01cdbb8  mov     qword ptr [rsp+0D8h+var_90], 0FFFFFFFFF6769800h
0x1c01cdbc1  lea     rax, [rsp+0D8h+var_90]
0x1c01cdbc6  mov     [rsp+0D8h+Timeout], rax; Timeout
0x1c01cdbcb  xor     r9d, r9d; Alertable
0x1c01cdbce  xor     r8d, r8d; WaitMode
0x1c01cdbd1  xor     edx, edx; WaitReason
0x1c01cdbd3  lea     rcx, [rsp+0D8h+Event]; Object
0x1c01cdbd8  call    cs:__imp_KeWaitForSingleObject
0x1c01cdbdf  nop     dword ptr [rax+rax+00h]
0x1c01cdbe4  test    eax, eax
0x1c01cdbe6  jz      short loc_1C01CDBEF
0x1c01cdbe8  call    MsPulseLazyWriterScan
0x1c01cdbed  jmp     short loc_1C01CDBC1
0x1c01cdbef  mov     r8b, 1
0x1c01cdbf2  mov     rdx, rdi
0x1c01cdbf5  mov     rcx, rsi
0x1c01cdbf8  call    RefsAcquireSharedVcb
0x1c01cdbfd  mov     [rsp+0D8h+var_A8], 1
0x1c01cdc02  mov     ecx, [rdi+4]
0x1c01cdc05  mov     eax, ecx
0x1c01cdc07  and     eax, 8000823h
0x1c01cdc0c  cmp     eax, 1
0x1c01cdc0f  jz      loc_1C01CDC9A
0x1c01cdc15  mov     al, [rsi+28h]
0x1c01cdc18  sub     al, 2
0x1c01cdc1a  test    al, 0EFh
0x1c01cdc1c  jz      short loc_1C01CDC89
0x1c01cdc1e  lea     rax, WPP_GLOBAL_Control
0x1c01cdc25  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cdc2c  cmp     rcx, rax
0x1c01cdc2f  jz      short loc_1C01CDC5B
0x1c01cdc31  test    dword ptr [rcx+2Ch], 100h
0x1c01cdc38  jz      short loc_1C01CDC5B
0x1c01cdc3a  cmp     byte ptr [rcx+29h], 4
0x1c01cdc3e  jb      short loc_1C01CDC5B
0x1c01cdc40  mov     edx, 0Dh
0x1c01cdc45  mov     r9d, 0C000026Eh
0x1c01cdc4b  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cdc52  mov     rcx, [rcx+18h]
0x1c01cdc56  call    WPP_SF_D
0x1c01cdc5b  mov     al, cs:RefsStatusDebugEnabled
0x1c01cdc61  test    al, al
0x1c01cdc63  jz      short loc_1C01CDC7C
0x1c01cdc65  mov     r8d, 13Ah
0x1c01cdc6b  lea     rdx, aTranssupC; "TransSup.c"
0x1c01cdc72  mov     ecx, 0C000026Eh; Status
0x1c01cdc77  call    RefsStatusDebug
0x1c01cdc7c  mov     edx, 0C000026Eh
0x1c01cdc81  mov     rcx, rsi
0x1c01cdc84  call    RefsRaiseStatusInternal
0x1c01cdc89  lea     rdx, loc_1C01CDF23
0x1c01cdc90  mov     rcx, [rsp+0D8h+var_98]
0x1c01cdc95  call    _local_unwind_0
0x1c01cdc9a  mov     r14, [rsp+0D8h+var_78]
0x1c01cdc9f  jmp     loc_1C01CDD46
0x1c01cdca4  call    RefsAcquireSharedVcb
0x1c01cdca9  mov     [rsp+0D8h+var_A8], 1
0x1c01cdcae  mov     ecx, [rdi+4]
0x1c01cdcb1  mov     eax, ecx
0x1c01cdcb3  and     eax, 8000823h
0x1c01cdcb8  cmp     eax, 1
0x1c01cdcbb  jz      loc_1C01CDD46
0x1c01cdcc1  mov     al, [rsi+28h]
0x1c01cdcc4  sub     al, 2
0x1c01cdcc6  test    al, 0EFh
0x1c01cdcc8  jz      short loc_1C01CDD35
0x1c01cdcca  lea     rax, WPP_GLOBAL_Control
0x1c01cdcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01cdcd8  cmp     rcx, rax
0x1c01cdcdb  jz      short loc_1C01CDD07
0x1c01cdcdd  test    dword ptr [rcx+2Ch], 100h
0x1c01cdce4  jz      short loc_1C01CDD07
0x1c01cdce6  cmp     byte ptr [rcx+29h], 4
0x1c01cdcea  jb      short loc_1C01CDD07
0x1c01cdcec  mov     edx, 0Eh
0x1c01cdcf1  mov     r9d, 0C000026Eh
0x1c01cdcf7  lea     r8, WPP_19f529de63163e1eb7d47934ee167ea0_Traceguids
0x1c01cdcfe  mov     rcx, [rcx+18h]
0x1c01cdd02  call    WPP_SF_D
0x1c01cdd07  mov     al, cs:RefsStatusDebugEnabled
0x1c01cdd0d  test    al, al
0x1c01cdd0f  jz      short loc_1C01CDD28
0x1c01cdd11  mov     r8d, 14Eh
0x1c01cdd17  lea     rdx, aTranssupC; "TransSup.c"
0x1c01cdd1e  mov     ecx, 0C000026Eh; Status
0x1c01cdd23  call    RefsStatusDebug
0x1c01cdd28  mov     edx, 0C000026Eh
0x1c01cdd2d  mov     rcx, rsi
0x1c01cdd30  call    RefsRaiseStatusInternal
0x1c01cdd35  lea     rdx, loc_1C01CDF23
0x1c01cdd3c  mov     rcx, [rsp+0D8h+var_98]
0x1c01cdd41  call    _local_unwind_0
0x1c01cdd46  neg     r13b
0x1c01cdd49  sbb     edx, edx
0x1c01cdd4b  and     edx, 0FFFFFFF0h
0x1c01cdd4e  add     edx, 11h
0x1c01cdd51  mov     [rsp+0D8h+var_A4], edx
0x1c01cdd55  cmp     [rsp+0D8h+arg_28], bl
0x1c01cdd5c  jz      short loc_1C01CDD66
0x1c01cdd5e  bts     edx, 0Ah
0x1c01cdd62  mov     [rsp+0D8h+var_A4], edx
0x1c01cdd66  cmp     [rsp+0D8h+arg_30], bl
0x1c01cdd6d  jz      short loc_1C01CDD77
0x1c01cdd6f  bts     edx, 9
0x1c01cdd73  mov     [rsp+0D8h+var_A4], edx
0x1c01cdd77  cmp     [rsp+0D8h+var_A6], bl
  ... truncated ...
```
