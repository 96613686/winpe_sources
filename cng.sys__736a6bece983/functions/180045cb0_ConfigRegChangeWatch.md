# ConfigRegChangeWatch

- ea: `0x180045cb0`
- end: `0x180046234`
- name: `ConfigRegChangeWatch`
- size: `1412`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180018ec0`
- `0x1800372b8`
- `0x180041124`
- `0x180043e28`
- `0x180045c80`
- `0x180045cb0`
- `0x1800476d4`
- `0x1800487c4`
- `0x180048944`
- `0x180049714`
- `0x180049a3c`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x180045fc4`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180045fc4`
- `ntoskrnl!ZwNotifyChangeKey` at `0x180045ddd`
- `ntoskrnl!ZwNotifyChangeKey` at `0x180045ddd`
- `ntoskrnl!KeSetEvent` at `0x1800461f6`
- `ntoskrnl!KeSetEvent` at `0x1800461f6`
- `ntoskrnl!KeSetTimer` at `0x180045f7f`
- `ntoskrnl!KeSetTimer` at `0x180045f7f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x180046052`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x180046052`
- `ntoskrnl!KeInitializeTimer` at `0x180045d3e`
- `ntoskrnl!KeInitializeTimer` at `0x180045d3e`
- `ntoskrnl!KeClearEvent` at `0x180045d84`
- `ntoskrnl!KeClearEvent` at `0x180045d84`
- `ntoskrnl!KeCancelTimer` at `0x1800460fa`
- `ntoskrnl!KeCancelTimer` at `0x1800461cf`
- `ntoskrnl!KeCancelTimer` at `0x1800460fa`
- `ntoskrnl!KeCancelTimer` at `0x1800461cf`
- `ntoskrnl!PsTerminateSystemThread` at `0x180046204`
- `ntoskrnl!PsTerminateSystemThread` at `0x180046204`

## string_xrefs

- `0x180045d16`: `ConfigRegChangeWatch:: pRegKeyNotifyRoot == nullptr`
- `0x180045cf9`: `ConfigRegChangeWatch:: pCngConfigContext == nullptr`
- `0x180045e48`: `ConfigRegChangeWatch:: ZwNotifyChangeKey failed`
- `0x180045e17`: `ConfigRegChangeWatch:: ZwNotifyChangeKey failed. ntStatus: %ld`
- `0x18004606d`: `ConfigRegChangeWatch:: KeWaitForMultipleObjects failed. ntStatus: %ld`
- `0x18004601e`: `ConfigRegChangeWatch:: CcnPublish failed`
- `0x18004609a`: `ConfigRegChangeWatch:: KeWaitForMultipleObjects failed`

## pseudocode

```c
void __fastcall ConfigRegChangeWatch(_QWORD *StartContext)
{
  __int64 v1; // rbx
  const wchar_t *v2; // rcx
  __int64 v3; // r9
  char *Pointer; // r15
  int v5; // r13d
  unsigned int i; // edi
  __int64 v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  void *v12; // rcx
  void *v13; // rdx
  NTSTATUS v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  wchar_t *v18; // rcx
  unsigned __int64 v19; // rdi
  void *v20; // rax
  PVOID *v21; // r12
  __int64 v22; // r9
  unsigned int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  struct _KWAIT_BLOCK *v27; // r14
  struct _KWAIT_BLOCK *v28; // rax
  __int64 CurrentServerSilo; // rax
  int v30; // r8d
  int v31; // r9d
  const char *v32; // rcx
  int v33; // esi
  NTSTATUS v34; // eax
  __int64 v35; // r9
  __int64 v36; // r8
  int v37; // eax
  wchar_t *v38; // rcx
  unsigned int v39; // esi
  __int64 v40; // r13
  __int64 v41; // r14
  __int64 v42; // rdi
  void *v43; // rcx
  void *v44; // rcx
  struct _KEVENT *v45; // rcx
  BOOLEAN WatchTree[8]; // [rsp+30h] [rbp-D0h]
  BOOLEAN WatchTreea[8]; // [rsp+30h] [rbp-D0h]
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+54h] [rbp-ACh]
  const char *v50; // [rsp+58h] [rbp-A8h] BYREF
  PKWAIT_BLOCK WaitBlockArray; // [rsp+60h] [rbp-A0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h]
  _QWORD *v54; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[1024]; // [rsp+90h] [rbp-70h] BYREF

  v54 = StartContext;
  IoStatusBlock.Pointer = 0;
  v48 = 0;
  if ( !StartContext )
  {
    v1 = 0;
    v2 = L"ConfigRegChangeWatch:: pCngConfigContext == nullptr";
LABEL_3:
    SendTelemetry(v2);
    goto LABEL_81;
  }
  v1 = StartContext[53];
  if ( !v1 )
  {
    v2 = L"ConfigRegChangeWatch:: pRegKeyNotifyRoot == nullptr";
    goto LABEL_3;
  }
  WaitBlockArray = 0;
  P = 0;
  v49 = 0;
  WaitForRegAvailability();
  KeInitializeTimer((PKTIMER)(v1 + 24));
  if ( (int)InitEventArray((__int64 *)v1, &IoStatusBlock, &v48, v3) < 0 )
    goto LABEL_78;
  Pointer = (char *)IoStatusBlock.Pointer;
  v5 = v48;
  while ( 2 )
  {
    for ( i = 0; i < 2; ++i )
    {
      v7 = *(_QWORD *)v1;
      v8 = 32LL * i;
      KeClearEvent(*(PRKEVENT *)(v8 + *(_QWORD *)v1 + 16));
      v12 = *(void **)(v8 + v7);
      if ( !v12 )
        continue;
      v13 = *(void **)(v8 + v7 + 8);
      IoStatusBlock = 0;
      v14 = ZwNotifyChangeKey(v12, v13, 0, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
      if ( v14 == -1073741444 )
      {
        KeRegCloseKey(*(HANDLE *)(v8 + v7));
        if ( !(unsigned int)OpenLowestPossibleRegKey((_QWORD *)v1, i, v15, v16) )
        {
          --i;
          continue;
        }
      }
      else
      {
        if ( v14 >= 0 )
          continue;
        *(_DWORD *)WatchTree = v14;
        v17 = StringCchPrintfExW(
                pszDest,
                0x400u,
                0,
                0,
                0,
                L"ConfigRegChangeWatch:: ZwNotifyChangeKey failed. ntStatus: %ld",
                *(_QWORD *)WatchTree);
        if ( (int)(v17 + 0x80000000) < 0
          || (v18 = L"ConfigRegChangeWatch:: ZwNotifyChangeKey failed", v17 == -2147024774) )
        {
          v18 = pszDest;
        }
        SendTelemetry(v18);
        KeRegCloseKey(*(HANDLE *)(v8 + v7));
      }
      v5 = 1;
      *(_QWORD *)(v8 + v7) = 0;
      --Pointer;
    }
    if ( P )
      MSCryptFree(P);
    v19 = (unsigned __int64)(Pointer + 1);
    if ( v5 )
      v19 = (unsigned __int64)(Pointer + 2);
    v20 = (void *)MSCryptAlloc(8 * v19, v9, v10, v11);
    P = v20;
    v21 = (PVOID *)v20;
    if ( !v20 )
    {
      v27 = WaitBlockArray;
      goto LABEL_74;
    }
    memset(v20, 0, 8 * v19);
    *v21 = *(PVOID *)(v1 + 8);
    v23 = 1;
    if ( v5 )
    {
      v21[1] = (PVOID)(v1 + 24);
      v23 = 2;
    }
    v24 = 0;
    do
    {
      v25 = v23;
      if ( v23 >= v19 )
        break;
      v22 = *(_QWORD *)v1;
      v26 = 32LL * (unsigned int)v24;
      if ( *(_QWORD *)(v26 + *(_QWORD *)v1) )
      {
        ++v23;
        v21[v25] = *(PVOID *)(v26 + v22 + 16);
      }
      v24 = (unsigned int)(v24 + 1);
    }
    while ( (unsigned int)v24 < 2 );
    v27 = WaitBlockArray;
    if ( WaitBlockArray )
    {
      MSCryptFree(WaitBlockArray);
      v27 = 0;
      WaitBlockArray = 0;
    }
    if ( v19 <= 3 )
    {
LABEL_37:
      if ( v5 )
        KeSetTimer((PKTIMER)(v1 + 24), (LARGE_INTEGER)-600000000LL, 0);
      if ( v49 )
      {
        if ( (unsigned int)dword_1800CB588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800CB588, 0x200000000000LL) )
        {
          IoStatusBlock.Pointer = (PVOID)2048;
          CurrentServerSilo = PsGetCurrentServerSilo();
          v32 = "Container";
          if ( !CurrentServerSilo )
            v32 = "Host";
          v50 = v32;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (_DWORD)v32,
            (unsigned int)byte_1800C31C3,
            v30,
            v31,
            (__int64)&v50,
            (__int64)&IoStatusBlock);
        }
        if ( (unsigned int)CcnPublish((PERESOURCE)v54[33]) )
          SendTelemetry(L"ConfigRegChangeWatch:: CcnPublish failed");
      }
      v33 = 0;
      v49 = 0;
      v34 = KeWaitForMultipleObjects(v19, v21, WaitAny, Executive, 0, 0, 0, v27);
      v36 = (unsigned int)v34;
      if ( v34 < 0 )
      {
        *(_DWORD *)WatchTreea = v34;
        v37 = StringCchPrintfExW(
                pszDest,
                0x400u,
                0,
                0,
                0,
                L"ConfigRegChangeWatch:: KeWaitForMultipleObjects failed. ntStatus: %ld",
                *(_QWORD *)WatchTreea);
        if ( (int)(v37 + 0x80000000) < 0
          || (v38 = L"ConfigRegChangeWatch:: KeWaitForMultipleObjects failed", v37 == -2147024774) )
        {
          v38 = pszDest;
        }
        SendTelemetry(v38);
LABEL_59:
        if ( v5 )
          KeCancelTimer((PKTIMER)(v1 + 24));
        Pointer = 0;
        v39 = 0;
        LODWORD(v50) = 0;
        v40 = 0;
        do
        {
          v41 = *(_QWORD *)v1;
          v42 = 32 * v40;
          v48 = 0;
          v43 = *(void **)(32 * v40 + v41);
          IoStatusBlock.Status = *(_DWORD *)(32 * v40 + v41 + 24);
          if ( v43 )
          {
            KeRegCloseKey(v43);
            v48 = 1;
          }
          if ( (unsigned int)OpenLowestPossibleRegKey((_QWORD *)v1, v39, v36, v35) )
          {
            *(_QWORD *)(v42 + v41) = 0;
            LODWORD(v50) = 1;
          }
          else
          {
            if ( *(_DWORD *)(v42 + *(_QWORD *)v1 + 24) && (!v48 || !IoStatusBlock.Status) )
              v49 = 1;
            ++Pointer;
          }
          ++v39;
          ++v40;
        }
        while ( v39 < 2 );
        v5 = (int)v50;
        continue;
      }
      if ( v34 )
      {
        if ( (v34 & 0xFFFFFF80) == 0 && (!v5 || v34 != 1) )
        {
          v36 = v34 - ((unsigned int)(v5 != 0) + 1);
          if ( *(_DWORD *)(32LL * (int)v36 + *(_QWORD *)v1 + 24) == 1 )
            v33 = 1;
          v49 = v33;
        }
        goto LABEL_59;
      }
LABEL_74:
      if ( v27 )
        MSCryptFree(v27);
      if ( v21 )
        goto LABEL_77;
      goto LABEL_78;
    }
    break;
  }
  v28 = (struct _KWAIT_BLOCK *)MSCryptAlloc(48 * v19, v24, v25, v22);
  WaitBlockArray = v28;
  v27 = v28;
  if ( v28 )
  {
    memset(v28, 0, 48 * v19);
    goto LABEL_37;
  }
LABEL_77:
  MSCryptFree(v21);
LABEL_78:
  v44 = *(void **)(v1 + 8);
  if ( v44 )
  {
    MSCryptFree(v44);
    *(_QWORD *)(v1 + 8) = 0;
  }
  KeCancelTimer((PKTIMER)(v1 + 24));
LABEL_81:
  CleanupRegKeyNotifyRoot(v1);
  if ( v1 )
  {
    v45 = *(struct _KEVENT **)(v1 + 16);
    if ( v45 )
      KeSetEvent(v45, 0, 0);
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x180045cb0  push    rbp
0x180045cb2  push    rbx
0x180045cb3  push    rsi
0x180045cb4  push    rdi
0x180045cb5  push    r12
0x180045cb7  push    r13
0x180045cb9  push    r14
0x180045cbb  push    r15
0x180045cbd  lea     rbp, [rsp-7A8h]
0x180045cc5  sub     rsp, 8A8h
0x180045ccc  mov     rax, cs:__security_cookie
0x180045cd3  xor     rax, rsp
0x180045cd6  mov     [rbp+7E0h+var_50], rax
0x180045cdd  mov     [rbp+7E0h+var_860], rcx
0x180045ce1  mov     qword ptr [rsp+8E0h+var_878], 0
0x180045cea  mov     [rsp+8E0h+var_890], 0
0x180045cf2  test    rcx, rcx
0x180045cf5  jnz     short loc_180045D0A
0x180045cf7  xor     ebx, ebx
0x180045cf9  lea     rcx, aConfigregchang_2; "ConfigRegChangeWatch:: pCngConfigContex"...
0x180045d00  call    SendTelemetry
0x180045d05  jmp     loc_1800461DB
0x180045d0a  mov     rbx, [rcx+1A8h]
0x180045d11  test    rbx, rbx
0x180045d14  jnz     short loc_180045D1F
0x180045d16  lea     rcx, aConfigregchang_5; "ConfigRegChangeWatch:: pRegKeyNotifyRoo"...
0x180045d1d  jmp     short loc_180045D00
0x180045d1f  xor     r12d, r12d
0x180045d22  mov     [rsp+8E0h+WaitBlockArray], 0
0x180045d2b  mov     [rsp+8E0h+P], r12
0x180045d30  mov     [rsp+8E0h+var_88C], r12d
0x180045d35  call    WaitForRegAvailability
0x180045d3a  lea     rcx, [rbx+18h]; Timer
0x180045d3e  call    cs:__imp_KeInitializeTimer
0x180045d45  nop     dword ptr [rax+rax+00h]
0x180045d4a  lea     r8, [rsp+8E0h+var_890]
0x180045d4f  mov     rcx, rbx
0x180045d52  lea     rdx, [rsp+8E0h+var_878]
0x180045d57  call    InitEventArray
0x180045d5c  test    eax, eax
0x180045d5e  js      loc_1800461B5
0x180045d64  mov     r15, qword ptr [rsp+8E0h+var_878]
0x180045d69  mov     r13d, [rsp+8E0h+var_890]
0x180045d6e  mov     r12d, 1
0x180045d74  xor     edi, edi
0x180045d76  mov     r14, [rbx]
0x180045d79  mov     esi, edi
0x180045d7b  shl     rsi, 5
0x180045d7f  mov     rcx, [rsi+r14+10h]; Event
0x180045d84  call    cs:__imp_KeClearEvent
0x180045d8b  nop     dword ptr [rax+rax+00h]
0x180045d90  mov     rcx, [rsi+r14]; KeyHandle
0x180045d94  test    rcx, rcx
0x180045d97  jz      loc_180045E76
0x180045d9d  mov     rdx, [rsi+r14+8]; Event
0x180045da2  lea     rax, [rsp+8E0h+var_878]
0x180045da7  mov     [rsp+8E0h+Asynchronous], r12b; Asynchronous
0x180045dac  xorps   xmm0, xmm0
0x180045daf  mov     [rsp+8E0h+BufferSize], 0; BufferSize
0x180045db7  mov     r9, r12; ApcContext
0x180045dba  mov     [rsp+8E0h+Buffer], 0; Buffer
0x180045dc3  xor     r8d, r8d; ApcRoutine
0x180045dc6  mov     [rsp+8E0h+WatchTree], r12b; WatchTree
0x180045dcb  mov     [rsp+8E0h+CompletionFilter], 5; CompletionFilter
0x180045dd3  mov     [rsp+8E0h+IoStatusBlock], rax; IoStatusBlock
0x180045dd8  movups  xmmword ptr [rsp+8E0h+var_878], xmm0
0x180045ddd  call    cs:__imp_ZwNotifyChangeKey
0x180045de4  nop     dword ptr [rax+rax+00h]
0x180045de9  cmp     eax, 0C000017Ch
0x180045dee  jnz     short loc_180045E0B
0x180045df0  mov     rcx, [rsi+r14]; Handle
0x180045df4  call    KeRegCloseKey
0x180045df9  mov     edx, edi
0x180045dfb  mov     rcx, rbx
0x180045dfe  call    OpenLowestPossibleRegKey
0x180045e03  test    eax, eax
0x180045e05  jnz     short loc_180045E68
0x180045e07  dec     edi
0x180045e09  jmp     short loc_180045E76
0x180045e0b  test    eax, eax
0x180045e0d  jns     short loc_180045E76
0x180045e0f  mov     dword ptr [rsp+8E0h+WatchTree], eax
0x180045e13  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x180045e17  lea     rax, aConfigregchang_0; "ConfigRegChangeWatch:: ZwNotifyChangeKe"...
0x180045e1e  xor     r9d, r9d; unsigned __int64 *
0x180045e21  mov     qword ptr [rsp+8E0h+CompletionFilter], rax; unsigned __int16 *
0x180045e26  xor     r8d, r8d; unsigned __int16 **
0x180045e29  mov     edx, 400h; unsigned __int64
0x180045e2e  mov     [rsp+8E0h+IoStatusBlock], 0; unsigned int
0x180045e37  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180045e3c  mov     edx, 80000000h
0x180045e41  lea     ecx, [rax+rdx]
0x180045e44  test    edx, ecx
0x180045e46  jnz     short loc_180045E56
0x180045e48  lea     rcx, aConfigregchang_4; "ConfigRegChangeWatch:: ZwNotifyChangeKe"...
0x180045e4f  cmp     eax, 8007007Ah
0x180045e54  jnz     short loc_180045E5A
0x180045e56  lea     rcx, [rbp+7E0h+pszDest]
0x180045e5a  call    SendTelemetry
0x180045e5f  mov     rcx, [rsi+r14]; Handle
0x180045e63  call    KeRegCloseKey
0x180045e68  mov     r13d, r12d
0x180045e6b  mov     qword ptr [rsi+r14], 0
0x180045e73  sub     r15, r12
0x180045e76  add     edi, r12d
0x180045e79  cmp     edi, 2
0x180045e7c  jb      loc_180045D76
0x180045e82  mov     r12, [rsp+8E0h+P]
0x180045e87  test    r12, r12
0x180045e8a  jz      short loc_180045E94
0x180045e8c  mov     rcx, r12; P
0x180045e8f  call    MSCryptFree
0x180045e94  lea     rdi, [r15+1]
0x180045e98  test    r13d, r13d
0x180045e9b  jz      short loc_180045EA0
0x180045e9d  inc     rdi
0x180045ea0  lea     rsi, ds:0[rdi*8]
0x180045ea8  mov     rcx, rsi
0x180045eab  call    MSCryptAlloc
0x180045eb0  mov     [rsp+8E0h+P], rax
0x180045eb5  mov     r12, rax
0x180045eb8  test    rax, rax
0x180045ebb  jz      loc_180046196
0x180045ec1  mov     r8, rsi; Size
0x180045ec4  xor     edx, edx; Val
0x180045ec6  mov     rcx, rax; void *
0x180045ec9  call    memset
0x180045ece  mov     rax, [rbx+8]
0x180045ed2  mov     r10d, 1
0x180045ed8  mov     [r12], rax
0x180045edc  mov     ecx, r10d
0x180045edf  lea     r15, [rbx+18h]
0x180045ee3  test    r13d, r13d
0x180045ee6  jz      short loc_180045EF1
0x180045ee8  mov     [r12+8], r15
0x180045eed  lea     ecx, [r10+1]
0x180045ef1  xor     edx, edx
0x180045ef3  mov     r8d, ecx
0x180045ef6  cmp     r8, rdi
0x180045ef9  jnb     short loc_180045F1F
0x180045efb  mov     r9, [rbx]
0x180045efe  mov     eax, edx
0x180045f00  shl     rax, 5
0x180045f04  cmp     qword ptr [rax+r9], 0
0x180045f09  jz      short loc_180045F17
0x180045f0b  mov     rax, [rax+r9+10h]
0x180045f10  add     ecx, r10d
0x180045f13  mov     [r12+r8*8], rax
0x180045f17  add     edx, r10d
0x180045f1a  cmp     edx, 2
0x180045f1d  jb      short loc_180045EF3
0x180045f1f  mov     r14, [rsp+8E0h+WaitBlockArray]
0x180045f24  test    r14, r14
0x180045f27  jz      short loc_180045F39
0x180045f29  mov     rcx, r14; P
0x180045f2c  call    MSCryptFree
0x180045f31  xor     r14d, r14d
0x180045f34  mov     [rsp+8E0h+WaitBlockArray], r14
0x180045f39  cmp     rdi, 3
0x180045f3d  jbe     short loc_180045F6D
0x180045f3f  lea     rsi, [rdi+rdi*2]
0x180045f43  shl     rsi, 4
0x180045f47  mov     rcx, rsi
0x180045f4a  call    MSCryptAlloc
0x180045f4f  mov     [rsp+8E0h+WaitBlockArray], rax
0x180045f54  mov     r14, rax
0x180045f57  test    rax, rax
0x180045f5a  jz      loc_1800461AD
0x180045f60  mov     r8, rsi; Size
0x180045f63  xor     edx, edx; Val
0x180045f65  mov     rcx, rax; void *
0x180045f68  call    memset
0x180045f6d  test    r13d, r13d
0x180045f70  jz      short loc_180045F8B
0x180045f72  xor     r8d, r8d; Dpc
0x180045f75  mov     rdx, 0FFFFFFFFDC3CBA00h; DueTime
0x180045f7c  mov     rcx, r15; Timer
0x180045f7f  call    cs:__imp_KeSetTimer
0x180045f86  nop     dword ptr [rax+rax+00h]
0x180045f8b  cmp     [rsp+8E0h+var_88C], 0
0x180045f90  jz      loc_18004602A
0x180045f96  mov     eax, cs:dword_1800CB588
0x180045f9c  cmp     eax, 5
0x180045f9f  jbe     short loc_18004600A
0x180045fa1  mov     rdx, 200000000000h
0x180045fab  lea     rcx, dword_1800CB588
0x180045fb2  call    _tlgKeywordOn
0x180045fb7  test    al, al
0x180045fb9  jz      short loc_18004600A
0x180045fbb  mov     qword ptr [rsp+8E0h+var_878], 800h
0x180045fc4  call    cs:__imp_PsGetCurrentServerSilo
0x180045fcb  nop     dword ptr [rax+rax+00h]
0x180045fd0  test    rax, rax
0x180045fd3  lea     rdx, aHost; "Host"
0x180045fda  lea     rax, [rsp+8E0h+var_878]
0x180045fdf  mov     qword ptr [rsp+8E0h+CompletionFilter], rax
0x180045fe4  lea     rcx, aContainer; "Container"
0x180045feb  cmovz   rcx, rdx
0x180045fef  lea     rax, [rsp+8E0h+var_888]
0x180045ff4  lea     rdx, byte_1800C31C3
0x180045ffb  mov     [rsp+8E0h+IoStatusBlock], rax
0x180046000  mov     [rsp+8E0h+var_888], rcx
0x180046005  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18004600a  mov     rax, [rbp+7E0h+var_860]
0x18004600e  mov     rcx, [rax+108h]; Resource
0x180046015  call    CcnPublish
0x18004601a  test    eax, eax
0x18004601c  jz      short loc_18004602A
0x18004601e  lea     rcx, aConfigregchang_1; "ConfigRegChangeWatch:: CcnPublish faile"...
0x180046025  call    SendTelemetry
0x18004602a  xor     esi, esi
0x18004602c  mov     [rsp+8E0h+Buffer], r14; WaitBlockArray
0x180046031  mov     ecx, edi; Count
0x180046033  mov     qword ptr [rsp+8E0h+WatchTree], rsi; Timeout
0x180046038  mov     byte ptr [rsp+8E0h+CompletionFilter], sil; Alertable
0x18004603d  xor     r9d, r9d; WaitReason
0x180046040  mov     rdx, r12; Object
0x180046043  mov     [rsp+8E0h+var_88C], esi
0x180046047  lea     edi, [rsi+1]
0x18004604a  mov     byte ptr [rsp+8E0h+IoStatusBlock], sil; WaitMode
0x18004604f  mov     r8d, edi; WaitType
0x180046052  call    cs:__imp_KeWaitForMultipleObjects
0x180046059  nop     dword ptr [rax+rax+00h]
0x18004605e  mov     r8d, eax
0x180046061  test    eax, eax
0x180046063  jns     short loc_1800460B3
0x180046065  mov     dword ptr [rsp+8E0h+WatchTree], eax
0x180046069  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x18004606d  lea     rax, aConfigregchang_3; "ConfigRegChangeWatch:: KeWaitForMultipl"...
0x180046074  xor     r9d, r9d; unsigned __int64 *
0x180046077  mov     qword ptr [rsp+8E0h+CompletionFilter], rax; unsigned __int16 *
0x18004607c  xor     r8d, r8d; unsigned __int16 **
0x18004607f  mov     edx, 400h; unsigned __int64
0x180046084  mov     [rsp+8E0h+IoStatusBlock], rsi; unsigned int
0x180046089  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004608e  mov     edx, 80000000h
0x180046093  lea     ecx, [rax+rdx]
0x180046096  test    edx, ecx
0x180046098  jnz     short loc_1800460A8
0x18004609a  lea     rcx, aConfigregchang; "ConfigRegChangeWatch:: KeWaitForMultipl"...
0x1800460a1  cmp     eax, 8007007Ah
0x1800460a6  jnz     short loc_1800460AC
0x1800460a8  lea     rcx, [rbp+7E0h+pszDest]
0x1800460ac  call    SendTelemetry
0x1800460b1  jmp     short loc_1800460F2
0x1800460b3  test    r8d, r8d
0x1800460b6  jz      loc_18004619B
0x1800460bc  test    r8d, 0FFFFFF80h
0x1800460c3  jnz     short loc_1800460F2
0x1800460c5  test    r13d, r13d
0x1800460c8  jz      short loc_1800460CF
0x1800460ca  cmp     r8d, edi
0x1800460cd  jz      short loc_1800460F2
0x1800460cf  mov     rdx, [rbx]
0x1800460d2  mov     eax, r13d
0x1800460d5  neg     eax
0x1800460d7  sbb     ecx, ecx
0x1800460d9  neg     ecx
0x1800460db  add     ecx, edi
0x1800460dd  sub     r8d, ecx
0x1800460e0  movsxd  rax, r8d
0x1800460e3  shl     rax, 5
0x1800460e7  cmp     [rax+rdx+18h], edi
0x1800460eb  cmovz   esi, edi
0x1800460ee  mov     [rsp+8E0h+var_88C], esi
0x1800460f2  test    r13d, r13d
0x1800460f5  jz      short loc_180046106
0x1800460f7  mov     rcx, r15; PKTIMER
0x1800460fa  call    cs:__imp_KeCancelTimer
0x180046101  nop     dword ptr [rax+rax+00h]
0x180046106  xor     eax, eax
0x180046108  xor     r15d, r15d
0x18004610b  xor     esi, esi
0x18004610d  mov     dword ptr [rsp+8E0h+var_888], eax
0x180046111  xor     r13d, r13d
0x180046114  mov     r14, [rbx]
0x180046117  mov     rdi, r13
0x18004611a  shl     rdi, 5
0x18004611e  mov     [rsp+8E0h+var_890], 0
0x180046126  mov     rcx, [rdi+r14]; Handle
0x18004612a  mov     eax, [rdi+r14+18h]
0x18004612f  mov     dword ptr [rsp+8E0h+var_878], eax
0x180046133  test    rcx, rcx
0x180046136  jz      short loc_180046145
0x180046138  call    KeRegCloseKey
0x18004613d  mov     [rsp+8E0h+var_890], 1
0x180046145  mov     edx, esi
0x180046147  mov     rcx, rbx
0x18004614a  call    OpenLowestPossibleRegKey
0x18004614f  xor     ecx, ecx
0x180046151  test    eax, eax
0x180046153  jz      short loc_180046162
0x180046155  lea     eax, [rcx+1]
0x180046158  mov     [rdi+r14], rcx
0x18004615c  mov     dword ptr [rsp+8E0h+var_888], eax
0x180046160  jmp     short loc_180046182
0x180046162  mov     rax, [rbx]
0x180046165  cmp     [rdi+rax+18h], ecx
0x180046169  jz      short loc_18004617F
0x18004616b  cmp     [rsp+8E0h+var_890], ecx
  ... truncated ...
```
