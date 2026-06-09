# ConfigRegChangeWatch

- ea: `0x18004f310`
- end: `0x18004f894`
- name: `ConfigRegChangeWatch`
- size: `1412`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x18000e090`
- `0x180010590`
- `0x180025f40`
- `0x180040828`
- `0x18004a570`
- `0x18004d378`
- `0x18004f2e0`
- `0x18004f310`
- `0x180050d34`
- `0x180051e24`
- `0x180051fa4`
- `0x180052d74`
- `0x1800530ac`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x18004f624`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18004f624`
- `ntoskrnl!ZwNotifyChangeKey` at `0x18004f43d`
- `ntoskrnl!ZwNotifyChangeKey` at `0x18004f43d`
- `ntoskrnl!KeSetEvent` at `0x18004f856`
- `ntoskrnl!KeSetEvent` at `0x18004f856`
- `ntoskrnl!KeSetTimer` at `0x18004f5df`
- `ntoskrnl!KeSetTimer` at `0x18004f5df`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18004f6b2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18004f6b2`
- `ntoskrnl!KeInitializeTimer` at `0x18004f39e`
- `ntoskrnl!KeInitializeTimer` at `0x18004f39e`
- `ntoskrnl!KeClearEvent` at `0x18004f3e4`
- `ntoskrnl!KeClearEvent` at `0x18004f3e4`
- `ntoskrnl!KeCancelTimer` at `0x18004f75a`
- `ntoskrnl!KeCancelTimer` at `0x18004f82f`
- `ntoskrnl!KeCancelTimer` at `0x18004f75a`
- `ntoskrnl!KeCancelTimer` at `0x18004f82f`
- `ntoskrnl!PsTerminateSystemThread` at `0x18004f864`
- `ntoskrnl!PsTerminateSystemThread` at `0x18004f864`

## string_xrefs

- `0x18004f359`: `ConfigRegChangeWatch:: pCngConfigContext == nullptr`
- `0x18004f477`: `ConfigRegChangeWatch:: ZwNotifyChangeKey failed. ntStatus: %ld`
- `0x18004f376`: `ConfigRegChangeWatch:: pRegKeyNotifyRoot == nullptr`
- `0x18004f4a8`: `ConfigRegChangeWatch:: ZwNotifyChangeKey failed`
- `0x18004f67e`: `ConfigRegChangeWatch:: CcnPublish failed`
- `0x18004f6fa`: `ConfigRegChangeWatch:: KeWaitForMultipleObjects failed`
- `0x18004f6cd`: `ConfigRegChangeWatch:: KeWaitForMultipleObjects failed. ntStatus: %ld`

## pseudocode

```c
void __fastcall ConfigRegChangeWatch(_QWORD *StartContext)
{
  __int64 *v1; // rbx
  const wchar_t *v2; // rcx
  char *Pointer; // r15
  int v4; // r13d
  unsigned int i; // edi
  __int64 v6; // r14
  __int64 v7; // rsi
  __int64 v8; // rdx
  void *v9; // rcx
  void *v10; // rdx
  NTSTATUS v11; // eax
  int v12; // eax
  wchar_t *v13; // rcx
  unsigned __int64 v14; // rdi
  void *v15; // rax
  PVOID *v16; // r12
  unsigned int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  struct _KWAIT_BLOCK *v21; // r14
  struct _KWAIT_BLOCK *v22; // rax
  __int64 CurrentServerSilo; // rax
  int v24; // r8d
  int v25; // r9d
  const char *v26; // rcx
  int v27; // esi
  NTSTATUS v28; // eax
  int v29; // eax
  wchar_t *v30; // rcx
  unsigned int v31; // esi
  __int64 v32; // r13
  __int64 v33; // r14
  __int64 v34; // rdi
  void *v35; // rcx
  void *v36; // rcx
  struct _KEVENT *v37; // rcx
  BOOLEAN WatchTree[8]; // [rsp+30h] [rbp-D0h]
  BOOLEAN WatchTreea[8]; // [rsp+30h] [rbp-D0h]
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  int v41; // [rsp+54h] [rbp-ACh]
  const char *v42; // [rsp+58h] [rbp-A8h] BYREF
  PKWAIT_BLOCK WaitBlockArray; // [rsp+60h] [rbp-A0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h]
  _QWORD *v46; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[1024]; // [rsp+90h] [rbp-70h] BYREF

  v46 = StartContext;
  IoStatusBlock.Pointer = 0;
  v40 = 0;
  if ( !StartContext )
  {
    v1 = 0;
    v2 = L"ConfigRegChangeWatch:: pCngConfigContext == nullptr";
LABEL_3:
    SendTelemetry(v2);
    goto LABEL_81;
  }
  v1 = (__int64 *)StartContext[53];
  if ( !v1 )
  {
    v2 = L"ConfigRegChangeWatch:: pRegKeyNotifyRoot == nullptr";
    goto LABEL_3;
  }
  WaitBlockArray = 0;
  P = 0;
  v41 = 0;
  WaitForRegAvailability();
  KeInitializeTimer((PKTIMER)(v1 + 3));
  if ( (int)InitEventArray(v1, &IoStatusBlock, &v40) < 0 )
    goto LABEL_78;
  Pointer = (char *)IoStatusBlock.Pointer;
  v4 = v40;
  while ( 2 )
  {
    for ( i = 0; i < 2; ++i )
    {
      v6 = *v1;
      v7 = 32LL * i;
      KeClearEvent(*(PRKEVENT *)(v7 + *v1 + 16));
      v9 = *(void **)(v7 + v6);
      if ( !v9 )
        continue;
      v10 = *(void **)(v7 + v6 + 8);
      IoStatusBlock = 0;
      v11 = ZwNotifyChangeKey(v9, v10, 0, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
      if ( v11 == -1073741444 )
      {
        KeRegCloseKey(*(HANDLE *)(v7 + v6));
        if ( !(unsigned int)OpenLowestPossibleRegKey(v1, i) )
        {
          --i;
          continue;
        }
      }
      else
      {
        if ( v11 >= 0 )
          continue;
        *(_DWORD *)WatchTree = v11;
        v12 = StringCchPrintfExW(
                pszDest,
                0x400u,
                0,
                0,
                0,
                L"ConfigRegChangeWatch:: ZwNotifyChangeKey failed. ntStatus: %ld",
                *(_QWORD *)WatchTree);
        if ( (int)(v12 + 0x80000000) < 0
          || (v13 = L"ConfigRegChangeWatch:: ZwNotifyChangeKey failed", v12 == -2147024774) )
        {
          v13 = pszDest;
        }
        SendTelemetry(v13);
        KeRegCloseKey(*(HANDLE *)(v7 + v6));
      }
      v4 = 1;
      *(_QWORD *)(v7 + v6) = 0;
      --Pointer;
    }
    if ( P )
      MSCryptFree(P);
    v14 = (unsigned __int64)(Pointer + 1);
    if ( v4 )
      v14 = (unsigned __int64)(Pointer + 2);
    v15 = (void *)MSCryptAlloc(8 * v14, v8);
    P = v15;
    v16 = (PVOID *)v15;
    if ( !v15 )
    {
      v21 = WaitBlockArray;
      goto LABEL_74;
    }
    memset(v15, 0, 8 * v14);
    *v16 = (PVOID)v1[1];
    v17 = 1;
    if ( v4 )
    {
      v16[1] = v1 + 3;
      v17 = 2;
    }
    v18 = 0;
    do
    {
      v19 = v17;
      if ( v17 >= v14 )
        break;
      v20 = 32LL * (unsigned int)v18;
      if ( *(_QWORD *)(v20 + *v1) )
      {
        ++v17;
        v16[v19] = *(PVOID *)(v20 + *v1 + 16);
      }
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (unsigned int)v18 < 2 );
    v21 = WaitBlockArray;
    if ( WaitBlockArray )
    {
      MSCryptFree(WaitBlockArray);
      v21 = 0;
      WaitBlockArray = 0;
    }
    if ( v14 <= 3 )
    {
LABEL_37:
      if ( v4 )
        KeSetTimer((PKTIMER)(v1 + 3), (LARGE_INTEGER)-600000000LL, 0);
      if ( v41 )
      {
        if ( (unsigned int)dword_1800D1588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D1588, 0x200000000000LL) )
        {
          IoStatusBlock.Pointer = (PVOID)2048;
          CurrentServerSilo = PsGetCurrentServerSilo();
          v26 = "Container";
          if ( !CurrentServerSilo )
            v26 = "Host";
          v42 = v26;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (_DWORD)v26,
            (unsigned int)byte_1800C9443,
            v24,
            v25,
            (__int64)&v42,
            (__int64)&IoStatusBlock);
        }
        if ( (unsigned int)CcnPublish((PERESOURCE)v46[33]) )
          SendTelemetry(L"ConfigRegChangeWatch:: CcnPublish failed");
      }
      v27 = 0;
      v41 = 0;
      v28 = KeWaitForMultipleObjects(v14, v16, WaitAny, Executive, 0, 0, 0, v21);
      if ( v28 < 0 )
      {
        *(_DWORD *)WatchTreea = v28;
        v29 = StringCchPrintfExW(
                pszDest,
                0x400u,
                0,
                0,
                0,
                L"ConfigRegChangeWatch:: KeWaitForMultipleObjects failed. ntStatus: %ld",
                *(_QWORD *)WatchTreea);
        if ( (int)(v29 + 0x80000000) < 0
          || (v30 = L"ConfigRegChangeWatch:: KeWaitForMultipleObjects failed", v29 == -2147024774) )
        {
          v30 = pszDest;
        }
        SendTelemetry(v30);
LABEL_59:
        if ( v4 )
          KeCancelTimer((PKTIMER)(v1 + 3));
        Pointer = 0;
        v31 = 0;
        LODWORD(v42) = 0;
        v32 = 0;
        do
        {
          v33 = *v1;
          v34 = 32 * v32;
          v40 = 0;
          v35 = *(void **)(32 * v32 + v33);
          IoStatusBlock.Status = *(_DWORD *)(32 * v32 + v33 + 24);
          if ( v35 )
          {
            KeRegCloseKey(v35);
            v40 = 1;
          }
          if ( (unsigned int)OpenLowestPossibleRegKey(v1, v31) )
          {
            *(_QWORD *)(v34 + v33) = 0;
            LODWORD(v42) = 1;
          }
          else
          {
            if ( *(_DWORD *)(v34 + *v1 + 24) && (!v40 || !IoStatusBlock.Status) )
              v41 = 1;
            ++Pointer;
          }
          ++v31;
          ++v32;
        }
        while ( v31 < 2 );
        v4 = (int)v42;
        continue;
      }
      if ( v28 )
      {
        if ( (v28 & 0xFFFFFF80) == 0 && (!v4 || v28 != 1) )
        {
          if ( *(_DWORD *)(32LL * (v28 - ((v4 != 0) + 1)) + *v1 + 24) == 1 )
            v27 = 1;
          v41 = v27;
        }
        goto LABEL_59;
      }
LABEL_74:
      if ( v21 )
        MSCryptFree(v21);
      if ( v16 )
        goto LABEL_77;
      goto LABEL_78;
    }
    break;
  }
  v22 = (struct _KWAIT_BLOCK *)MSCryptAlloc(48 * v14, v18);
  WaitBlockArray = v22;
  v21 = v22;
  if ( v22 )
  {
    memset(v22, 0, 48 * v14);
    goto LABEL_37;
  }
LABEL_77:
  MSCryptFree(v16);
LABEL_78:
  v36 = (void *)v1[1];
  if ( v36 )
  {
    MSCryptFree(v36);
    v1[1] = 0;
  }
  KeCancelTimer((PKTIMER)(v1 + 3));
LABEL_81:
  CleanupRegKeyNotifyRoot(v1);
  if ( v1 )
  {
    v37 = (struct _KEVENT *)v1[2];
    if ( v37 )
      KeSetEvent(v37, 0, 0);
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x18004f310  push    rbp
0x18004f312  push    rbx
0x18004f313  push    rsi
0x18004f314  push    rdi
0x18004f315  push    r12
0x18004f317  push    r13
0x18004f319  push    r14
0x18004f31b  push    r15
0x18004f31d  lea     rbp, [rsp-7A8h]
0x18004f325  sub     rsp, 8A8h
0x18004f32c  mov     rax, cs:__security_cookie
0x18004f333  xor     rax, rsp
0x18004f336  mov     [rbp+7E0h+var_50], rax
0x18004f33d  mov     [rbp+7E0h+var_860], rcx
0x18004f341  mov     qword ptr [rsp+8E0h+var_878], 0
0x18004f34a  mov     [rsp+8E0h+var_890], 0
0x18004f352  test    rcx, rcx
0x18004f355  jnz     short loc_18004F36A
0x18004f357  xor     ebx, ebx
0x18004f359  lea     rcx, aConfigregchang_2; "ConfigRegChangeWatch:: pCngConfigContex"...
0x18004f360  call    SendTelemetry
0x18004f365  jmp     loc_18004F83B
0x18004f36a  mov     rbx, [rcx+1A8h]
0x18004f371  test    rbx, rbx
0x18004f374  jnz     short loc_18004F37F
0x18004f376  lea     rcx, aConfigregchang_5; "ConfigRegChangeWatch:: pRegKeyNotifyRoo"...
0x18004f37d  jmp     short loc_18004F360
0x18004f37f  xor     r12d, r12d
0x18004f382  mov     [rsp+8E0h+WaitBlockArray], 0
0x18004f38b  mov     [rsp+8E0h+P], r12
0x18004f390  mov     [rsp+8E0h+var_88C], r12d
0x18004f395  call    WaitForRegAvailability
0x18004f39a  lea     rcx, [rbx+18h]; Timer
0x18004f39e  call    cs:__imp_KeInitializeTimer
0x18004f3a5  nop     dword ptr [rax+rax+00h]
0x18004f3aa  lea     r8, [rsp+8E0h+var_890]
0x18004f3af  mov     rcx, rbx
0x18004f3b2  lea     rdx, [rsp+8E0h+var_878]
0x18004f3b7  call    InitEventArray
0x18004f3bc  test    eax, eax
0x18004f3be  js      loc_18004F815
0x18004f3c4  mov     r15, qword ptr [rsp+8E0h+var_878]
0x18004f3c9  mov     r13d, [rsp+8E0h+var_890]
0x18004f3ce  mov     r12d, 1
0x18004f3d4  xor     edi, edi
0x18004f3d6  mov     r14, [rbx]
0x18004f3d9  mov     esi, edi
0x18004f3db  shl     rsi, 5
0x18004f3df  mov     rcx, [rsi+r14+10h]; Event
0x18004f3e4  call    cs:__imp_KeClearEvent
0x18004f3eb  nop     dword ptr [rax+rax+00h]
0x18004f3f0  mov     rcx, [rsi+r14]; KeyHandle
0x18004f3f4  test    rcx, rcx
0x18004f3f7  jz      loc_18004F4D6
0x18004f3fd  mov     rdx, [rsi+r14+8]; Event
0x18004f402  lea     rax, [rsp+8E0h+var_878]
0x18004f407  mov     [rsp+8E0h+Asynchronous], r12b; Asynchronous
0x18004f40c  xorps   xmm0, xmm0
0x18004f40f  mov     [rsp+8E0h+BufferSize], 0; BufferSize
0x18004f417  mov     r9, r12; ApcContext
0x18004f41a  mov     [rsp+8E0h+Buffer], 0; Buffer
0x18004f423  xor     r8d, r8d; ApcRoutine
0x18004f426  mov     [rsp+8E0h+WatchTree], r12b; WatchTree
0x18004f42b  mov     [rsp+8E0h+CompletionFilter], 5; CompletionFilter
0x18004f433  mov     [rsp+8E0h+IoStatusBlock], rax; IoStatusBlock
0x18004f438  movups  xmmword ptr [rsp+8E0h+var_878], xmm0
0x18004f43d  call    cs:__imp_ZwNotifyChangeKey
0x18004f444  nop     dword ptr [rax+rax+00h]
0x18004f449  cmp     eax, 0C000017Ch
0x18004f44e  jnz     short loc_18004F46B
0x18004f450  mov     rcx, [rsi+r14]; Handle
0x18004f454  call    KeRegCloseKey
0x18004f459  mov     edx, edi
0x18004f45b  mov     rcx, rbx
0x18004f45e  call    OpenLowestPossibleRegKey
0x18004f463  test    eax, eax
0x18004f465  jnz     short loc_18004F4C8
0x18004f467  dec     edi
0x18004f469  jmp     short loc_18004F4D6
0x18004f46b  test    eax, eax
0x18004f46d  jns     short loc_18004F4D6
0x18004f46f  mov     dword ptr [rsp+8E0h+WatchTree], eax
0x18004f473  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x18004f477  lea     rax, aConfigregchang_0; "ConfigRegChangeWatch:: ZwNotifyChangeKe"...
0x18004f47e  xor     r9d, r9d; unsigned __int64 *
0x18004f481  mov     qword ptr [rsp+8E0h+CompletionFilter], rax; unsigned __int16 *
0x18004f486  xor     r8d, r8d; unsigned __int16 **
0x18004f489  mov     edx, 400h; unsigned __int64
0x18004f48e  mov     [rsp+8E0h+IoStatusBlock], 0; unsigned int
0x18004f497  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004f49c  mov     edx, 80000000h
0x18004f4a1  lea     ecx, [rax+rdx]
0x18004f4a4  test    edx, ecx
0x18004f4a6  jnz     short loc_18004F4B6
0x18004f4a8  lea     rcx, aConfigregchang_4; "ConfigRegChangeWatch:: ZwNotifyChangeKe"...
0x18004f4af  cmp     eax, 8007007Ah
0x18004f4b4  jnz     short loc_18004F4BA
0x18004f4b6  lea     rcx, [rbp+7E0h+pszDest]
0x18004f4ba  call    SendTelemetry
0x18004f4bf  mov     rcx, [rsi+r14]; Handle
0x18004f4c3  call    KeRegCloseKey
0x18004f4c8  mov     r13d, r12d
0x18004f4cb  mov     qword ptr [rsi+r14], 0
0x18004f4d3  sub     r15, r12
0x18004f4d6  add     edi, r12d
0x18004f4d9  cmp     edi, 2
0x18004f4dc  jb      loc_18004F3D6
0x18004f4e2  mov     r12, [rsp+8E0h+P]
0x18004f4e7  test    r12, r12
0x18004f4ea  jz      short loc_18004F4F4
0x18004f4ec  mov     rcx, r12; P
0x18004f4ef  call    MSCryptFree
0x18004f4f4  lea     rdi, [r15+1]
0x18004f4f8  test    r13d, r13d
0x18004f4fb  jz      short loc_18004F500
0x18004f4fd  inc     rdi
0x18004f500  lea     rsi, ds:0[rdi*8]
0x18004f508  mov     rcx, rsi
0x18004f50b  call    MSCryptAlloc
0x18004f510  mov     [rsp+8E0h+P], rax
0x18004f515  mov     r12, rax
0x18004f518  test    rax, rax
0x18004f51b  jz      loc_18004F7F6
0x18004f521  mov     r8, rsi; Size
0x18004f524  xor     edx, edx; Val
0x18004f526  mov     rcx, rax; void *
0x18004f529  call    memset
0x18004f52e  mov     rax, [rbx+8]
0x18004f532  mov     r10d, 1
0x18004f538  mov     [r12], rax
0x18004f53c  mov     ecx, r10d
0x18004f53f  lea     r15, [rbx+18h]
0x18004f543  test    r13d, r13d
0x18004f546  jz      short loc_18004F551
0x18004f548  mov     [r12+8], r15
0x18004f54d  lea     ecx, [r10+1]
0x18004f551  xor     edx, edx
0x18004f553  mov     r8d, ecx
0x18004f556  cmp     r8, rdi
0x18004f559  jnb     short loc_18004F57F
0x18004f55b  mov     r9, [rbx]
0x18004f55e  mov     eax, edx
0x18004f560  shl     rax, 5
0x18004f564  cmp     qword ptr [rax+r9], 0
0x18004f569  jz      short loc_18004F577
0x18004f56b  mov     rax, [rax+r9+10h]
0x18004f570  add     ecx, r10d
0x18004f573  mov     [r12+r8*8], rax
0x18004f577  add     edx, r10d
0x18004f57a  cmp     edx, 2
0x18004f57d  jb      short loc_18004F553
0x18004f57f  mov     r14, [rsp+8E0h+WaitBlockArray]
0x18004f584  test    r14, r14
0x18004f587  jz      short loc_18004F599
0x18004f589  mov     rcx, r14; P
0x18004f58c  call    MSCryptFree
0x18004f591  xor     r14d, r14d
0x18004f594  mov     [rsp+8E0h+WaitBlockArray], r14
0x18004f599  cmp     rdi, 3
0x18004f59d  jbe     short loc_18004F5CD
0x18004f59f  lea     rsi, [rdi+rdi*2]
0x18004f5a3  shl     rsi, 4
0x18004f5a7  mov     rcx, rsi
0x18004f5aa  call    MSCryptAlloc
0x18004f5af  mov     [rsp+8E0h+WaitBlockArray], rax
0x18004f5b4  mov     r14, rax
0x18004f5b7  test    rax, rax
0x18004f5ba  jz      loc_18004F80D
0x18004f5c0  mov     r8, rsi; Size
0x18004f5c3  xor     edx, edx; Val
0x18004f5c5  mov     rcx, rax; void *
0x18004f5c8  call    memset
0x18004f5cd  test    r13d, r13d
0x18004f5d0  jz      short loc_18004F5EB
0x18004f5d2  xor     r8d, r8d; Dpc
0x18004f5d5  mov     rdx, 0FFFFFFFFDC3CBA00h; DueTime
0x18004f5dc  mov     rcx, r15; Timer
0x18004f5df  call    cs:__imp_KeSetTimer
0x18004f5e6  nop     dword ptr [rax+rax+00h]
0x18004f5eb  cmp     [rsp+8E0h+var_88C], 0
0x18004f5f0  jz      loc_18004F68A
0x18004f5f6  mov     eax, cs:dword_1800D1588
0x18004f5fc  cmp     eax, 5
0x18004f5ff  jbe     short loc_18004F66A
0x18004f601  mov     rdx, 200000000000h
0x18004f60b  lea     rcx, dword_1800D1588
0x18004f612  call    _tlgKeywordOn
0x18004f617  test    al, al
0x18004f619  jz      short loc_18004F66A
0x18004f61b  mov     qword ptr [rsp+8E0h+var_878], 800h
0x18004f624  call    cs:__imp_PsGetCurrentServerSilo
0x18004f62b  nop     dword ptr [rax+rax+00h]
0x18004f630  test    rax, rax
0x18004f633  lea     rdx, aHost; "Host"
0x18004f63a  lea     rax, [rsp+8E0h+var_878]
0x18004f63f  mov     qword ptr [rsp+8E0h+CompletionFilter], rax
0x18004f644  lea     rcx, aContainer; "Container"
0x18004f64b  cmovz   rcx, rdx
0x18004f64f  lea     rax, [rsp+8E0h+var_888]
0x18004f654  lea     rdx, byte_1800C9443
0x18004f65b  mov     [rsp+8E0h+IoStatusBlock], rax
0x18004f660  mov     [rsp+8E0h+var_888], rcx
0x18004f665  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18004f66a  mov     rax, [rbp+7E0h+var_860]
0x18004f66e  mov     rcx, [rax+108h]; Resource
0x18004f675  call    CcnPublish
0x18004f67a  test    eax, eax
0x18004f67c  jz      short loc_18004F68A
0x18004f67e  lea     rcx, aConfigregchang_1; "ConfigRegChangeWatch:: CcnPublish faile"...
0x18004f685  call    SendTelemetry
0x18004f68a  xor     esi, esi
0x18004f68c  mov     [rsp+8E0h+Buffer], r14; WaitBlockArray
0x18004f691  mov     ecx, edi; Count
0x18004f693  mov     qword ptr [rsp+8E0h+WatchTree], rsi; Timeout
0x18004f698  mov     byte ptr [rsp+8E0h+CompletionFilter], sil; Alertable
0x18004f69d  xor     r9d, r9d; WaitReason
0x18004f6a0  mov     rdx, r12; Object
0x18004f6a3  mov     [rsp+8E0h+var_88C], esi
0x18004f6a7  lea     edi, [rsi+1]
0x18004f6aa  mov     byte ptr [rsp+8E0h+IoStatusBlock], sil; WaitMode
0x18004f6af  mov     r8d, edi; WaitType
0x18004f6b2  call    cs:__imp_KeWaitForMultipleObjects
0x18004f6b9  nop     dword ptr [rax+rax+00h]
0x18004f6be  mov     r8d, eax
0x18004f6c1  test    eax, eax
0x18004f6c3  jns     short loc_18004F713
0x18004f6c5  mov     dword ptr [rsp+8E0h+WatchTree], eax
0x18004f6c9  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x18004f6cd  lea     rax, aConfigregchang_3; "ConfigRegChangeWatch:: KeWaitForMultipl"...
0x18004f6d4  xor     r9d, r9d; unsigned __int64 *
0x18004f6d7  mov     qword ptr [rsp+8E0h+CompletionFilter], rax; unsigned __int16 *
0x18004f6dc  xor     r8d, r8d; unsigned __int16 **
0x18004f6df  mov     edx, 400h; unsigned __int64
0x18004f6e4  mov     [rsp+8E0h+IoStatusBlock], rsi; unsigned int
0x18004f6e9  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004f6ee  mov     edx, 80000000h
0x18004f6f3  lea     ecx, [rax+rdx]
0x18004f6f6  test    edx, ecx
0x18004f6f8  jnz     short loc_18004F708
0x18004f6fa  lea     rcx, aConfigregchang; "ConfigRegChangeWatch:: KeWaitForMultipl"...
0x18004f701  cmp     eax, 8007007Ah
0x18004f706  jnz     short loc_18004F70C
0x18004f708  lea     rcx, [rbp+7E0h+pszDest]
0x18004f70c  call    SendTelemetry
0x18004f711  jmp     short loc_18004F752
0x18004f713  test    r8d, r8d
0x18004f716  jz      loc_18004F7FB
0x18004f71c  test    r8d, 0FFFFFF80h
0x18004f723  jnz     short loc_18004F752
0x18004f725  test    r13d, r13d
0x18004f728  jz      short loc_18004F72F
0x18004f72a  cmp     r8d, edi
0x18004f72d  jz      short loc_18004F752
0x18004f72f  mov     rdx, [rbx]
0x18004f732  mov     eax, r13d
0x18004f735  neg     eax
0x18004f737  sbb     ecx, ecx
0x18004f739  neg     ecx
0x18004f73b  add     ecx, edi
0x18004f73d  sub     r8d, ecx
0x18004f740  movsxd  rax, r8d
0x18004f743  shl     rax, 5
0x18004f747  cmp     [rax+rdx+18h], edi
0x18004f74b  cmovz   esi, edi
0x18004f74e  mov     [rsp+8E0h+var_88C], esi
0x18004f752  test    r13d, r13d
0x18004f755  jz      short loc_18004F766
0x18004f757  mov     rcx, r15; PKTIMER
0x18004f75a  call    cs:__imp_KeCancelTimer
0x18004f761  nop     dword ptr [rax+rax+00h]
0x18004f766  xor     eax, eax
0x18004f768  xor     r15d, r15d
0x18004f76b  xor     esi, esi
0x18004f76d  mov     dword ptr [rsp+8E0h+var_888], eax
0x18004f771  xor     r13d, r13d
0x18004f774  mov     r14, [rbx]
0x18004f777  mov     rdi, r13
0x18004f77a  shl     rdi, 5
0x18004f77e  mov     [rsp+8E0h+var_890], 0
0x18004f786  mov     rcx, [rdi+r14]; Handle
0x18004f78a  mov     eax, [rdi+r14+18h]
0x18004f78f  mov     dword ptr [rsp+8E0h+var_878], eax
0x18004f793  test    rcx, rcx
0x18004f796  jz      short loc_18004F7A5
0x18004f798  call    KeRegCloseKey
0x18004f79d  mov     [rsp+8E0h+var_890], 1
0x18004f7a5  mov     edx, esi
0x18004f7a7  mov     rcx, rbx
0x18004f7aa  call    OpenLowestPossibleRegKey
0x18004f7af  xor     ecx, ecx
0x18004f7b1  test    eax, eax
0x18004f7b3  jz      short loc_18004F7C2
0x18004f7b5  lea     eax, [rcx+1]
0x18004f7b8  mov     [rdi+r14], rcx
0x18004f7bc  mov     dword ptr [rsp+8E0h+var_888], eax
0x18004f7c0  jmp     short loc_18004F7E2
0x18004f7c2  mov     rax, [rbx]
0x18004f7c5  cmp     [rdi+rax+18h], ecx
0x18004f7c9  jz      short loc_18004F7DF
0x18004f7cb  cmp     [rsp+8E0h+var_890], ecx
  ... truncated ...
```
