# ConfigRegChangeWatch

- ea: `0x180045220`
- end: `0x1800457a4`
- name: `ConfigRegChangeWatch`
- size: `1412`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18001be10`
- `0x1800367b8`
- `0x180040594`
- `0x180043398`
- `0x1800451f0`
- `0x180045220`
- `0x180046c44`
- `0x180047d34`
- `0x180047eb4`
- `0x180048c84`
- `0x180048fac`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!PsGetCurrentServerSilo` at `0x180045534`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180045534`
- `ntoskrnl!ZwNotifyChangeKey` at `0x18004534d`
- `ntoskrnl!ZwNotifyChangeKey` at `0x18004534d`
- `ntoskrnl!KeSetEvent` at `0x180045766`
- `ntoskrnl!KeSetEvent` at `0x180045766`
- `ntoskrnl!KeSetTimer` at `0x1800454ef`
- `ntoskrnl!KeSetTimer` at `0x1800454ef`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1800455c2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1800455c2`
- `ntoskrnl!KeInitializeTimer` at `0x1800452ae`
- `ntoskrnl!KeInitializeTimer` at `0x1800452ae`
- `ntoskrnl!KeClearEvent` at `0x1800452f4`
- `ntoskrnl!KeClearEvent` at `0x1800452f4`
- `ntoskrnl!KeCancelTimer` at `0x18004566a`
- `ntoskrnl!KeCancelTimer` at `0x18004573f`
- `ntoskrnl!KeCancelTimer` at `0x18004566a`
- `ntoskrnl!KeCancelTimer` at `0x18004573f`
- `ntoskrnl!PsTerminateSystemThread` at `0x180045774`
- `ntoskrnl!PsTerminateSystemThread` at `0x180045774`

## string_xrefs

- `0x180045286`: `ConfigRegChangeWatch:: pRegKeyNotifyRoot == nullptr`
- `0x180045269`: `ConfigRegChangeWatch:: pCngConfigContext == nullptr`
- `0x1800453b8`: `ConfigRegChangeWatch:: ZwNotifyChangeKey failed`
- `0x180045387`: `ConfigRegChangeWatch:: ZwNotifyChangeKey failed. ntStatus: %ld`
- `0x1800455dd`: `ConfigRegChangeWatch:: KeWaitForMultipleObjects failed. ntStatus: %ld`
- `0x18004558e`: `ConfigRegChangeWatch:: CcnPublish failed`
- `0x18004560a`: `ConfigRegChangeWatch:: KeWaitForMultipleObjects failed`

## pseudocode

```c
void __fastcall ConfigRegChangeWatch(_QWORD *StartContext)
{
  __int64 v1; // rbx
  const wchar_t *v2; // rcx
  char *Pointer; // r15
  int v4; // r13d
  unsigned int i; // edi
  __int64 v6; // r14
  __int64 v7; // rsi
  void *v8; // rcx
  void *v9; // rdx
  NTSTATUS v10; // eax
  int v11; // eax
  wchar_t *v12; // rcx
  unsigned __int64 v13; // rdi
  void *v14; // rax
  PVOID *v15; // r12
  unsigned int v16; // ecx
  unsigned int j; // edx
  __int64 v18; // r8
  __int64 v19; // rax
  struct _KWAIT_BLOCK *v20; // r14
  struct _KWAIT_BLOCK *v21; // rax
  __int64 CurrentServerSilo; // rax
  int v23; // r8d
  int v24; // r9d
  const char *v25; // rcx
  int v26; // esi
  NTSTATUS v27; // eax
  int v28; // eax
  wchar_t *v29; // rcx
  unsigned int v30; // esi
  __int64 v31; // r13
  __int64 v32; // r14
  __int64 v33; // rdi
  void *v34; // rcx
  void *v35; // rcx
  struct _KEVENT *v36; // rcx
  BOOLEAN WatchTree[8]; // [rsp+30h] [rbp-D0h]
  BOOLEAN WatchTreea[8]; // [rsp+30h] [rbp-D0h]
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+54h] [rbp-ACh]
  const char *v41; // [rsp+58h] [rbp-A8h] BYREF
  PKWAIT_BLOCK WaitBlockArray; // [rsp+60h] [rbp-A0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h]
  _QWORD *v45; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[1024]; // [rsp+90h] [rbp-70h] BYREF

  v45 = StartContext;
  IoStatusBlock.Pointer = 0;
  v39 = 0;
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
  v40 = 0;
  WaitForRegAvailability();
  KeInitializeTimer((PKTIMER)(v1 + 24));
  if ( (int)InitEventArray((__int64 *)v1, &IoStatusBlock, &v39) < 0 )
    goto LABEL_78;
  Pointer = (char *)IoStatusBlock.Pointer;
  v4 = v39;
  while ( 2 )
  {
    for ( i = 0; i < 2; ++i )
    {
      v6 = *(_QWORD *)v1;
      v7 = 32LL * i;
      KeClearEvent(*(PRKEVENT *)(v7 + *(_QWORD *)v1 + 16));
      v8 = *(void **)(v7 + v6);
      if ( !v8 )
        continue;
      v9 = *(void **)(v7 + v6 + 8);
      IoStatusBlock = 0;
      v10 = ZwNotifyChangeKey(v8, v9, 0, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
      if ( v10 == -1073741444 )
      {
        KeRegCloseKey(*(HANDLE *)(v7 + v6));
        if ( !(unsigned int)OpenLowestPossibleRegKey((_QWORD *)v1, i) )
        {
          --i;
          continue;
        }
      }
      else
      {
        if ( v10 >= 0 )
          continue;
        *(_DWORD *)WatchTree = v10;
        v11 = StringCchPrintfExW(
                pszDest,
                0x400u,
                0,
                0,
                0,
                L"ConfigRegChangeWatch:: ZwNotifyChangeKey failed. ntStatus: %ld",
                *(_QWORD *)WatchTree);
        if ( (int)(v11 + 0x80000000) < 0
          || (v12 = L"ConfigRegChangeWatch:: ZwNotifyChangeKey failed", v11 == -2147024774) )
        {
          v12 = pszDest;
        }
        SendTelemetry(v12);
        KeRegCloseKey(*(HANDLE *)(v7 + v6));
      }
      v4 = 1;
      *(_QWORD *)(v7 + v6) = 0;
      --Pointer;
    }
    if ( P )
      MSCryptFree(P);
    v13 = (unsigned __int64)(Pointer + 1);
    if ( v4 )
      v13 = (unsigned __int64)(Pointer + 2);
    v14 = (void *)MSCryptAlloc(8 * v13);
    P = v14;
    v15 = (PVOID *)v14;
    if ( !v14 )
    {
      v20 = WaitBlockArray;
      goto LABEL_74;
    }
    memset(v14, 0, 8 * v13);
    *v15 = *(PVOID *)(v1 + 8);
    v16 = 1;
    if ( v4 )
    {
      v15[1] = (PVOID)(v1 + 24);
      v16 = 2;
    }
    for ( j = 0; j < 2; ++j )
    {
      v18 = v16;
      if ( v16 >= v13 )
        break;
      v19 = 32LL * j;
      if ( *(_QWORD *)(v19 + *(_QWORD *)v1) )
      {
        ++v16;
        v15[v18] = *(PVOID *)(v19 + *(_QWORD *)v1 + 16);
      }
    }
    v20 = WaitBlockArray;
    if ( WaitBlockArray )
    {
      MSCryptFree(WaitBlockArray);
      v20 = 0;
      WaitBlockArray = 0;
    }
    if ( v13 <= 3 )
    {
LABEL_37:
      if ( v4 )
        KeSetTimer((PKTIMER)(v1 + 24), (LARGE_INTEGER)-600000000LL, 0);
      if ( v40 )
      {
        if ( (unsigned int)dword_1800C9588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C9588, 0x200000000000LL) )
        {
          IoStatusBlock.Pointer = (PVOID)2048;
          CurrentServerSilo = PsGetCurrentServerSilo();
          v25 = "Container";
          if ( !CurrentServerSilo )
            v25 = "Host";
          v41 = v25;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (_DWORD)v25,
            (unsigned int)byte_1800C0BC3,
            v23,
            v24,
            (__int64)&v41,
            (__int64)&IoStatusBlock);
        }
        if ( CcnPublish((PERESOURCE)v45[33]) )
          SendTelemetry(L"ConfigRegChangeWatch:: CcnPublish failed");
      }
      v26 = 0;
      v40 = 0;
      v27 = KeWaitForMultipleObjects(v13, v15, WaitAny, Executive, 0, 0, 0, v20);
      if ( v27 < 0 )
      {
        *(_DWORD *)WatchTreea = v27;
        v28 = StringCchPrintfExW(
                pszDest,
                0x400u,
                0,
                0,
                0,
                L"ConfigRegChangeWatch:: KeWaitForMultipleObjects failed. ntStatus: %ld",
                *(_QWORD *)WatchTreea);
        if ( (int)(v28 + 0x80000000) < 0
          || (v29 = L"ConfigRegChangeWatch:: KeWaitForMultipleObjects failed", v28 == -2147024774) )
        {
          v29 = pszDest;
        }
        SendTelemetry(v29);
LABEL_59:
        if ( v4 )
          KeCancelTimer((PKTIMER)(v1 + 24));
        Pointer = 0;
        v30 = 0;
        LODWORD(v41) = 0;
        v31 = 0;
        do
        {
          v32 = *(_QWORD *)v1;
          v33 = 32 * v31;
          v39 = 0;
          v34 = *(void **)(32 * v31 + v32);
          IoStatusBlock.Status = *(_DWORD *)(32 * v31 + v32 + 24);
          if ( v34 )
          {
            KeRegCloseKey(v34);
            v39 = 1;
          }
          if ( (unsigned int)OpenLowestPossibleRegKey((_QWORD *)v1, v30) )
          {
            *(_QWORD *)(v33 + v32) = 0;
            LODWORD(v41) = 1;
          }
          else
          {
            if ( *(_DWORD *)(v33 + *(_QWORD *)v1 + 24) && (!v39 || !IoStatusBlock.Status) )
              v40 = 1;
            ++Pointer;
          }
          ++v30;
          ++v31;
        }
        while ( v30 < 2 );
        v4 = (int)v41;
        continue;
      }
      if ( v27 )
      {
        if ( (v27 & 0xFFFFFF80) == 0 && (!v4 || v27 != 1) )
        {
          if ( *(_DWORD *)(32LL * (v27 - ((v4 != 0) + 1)) + *(_QWORD *)v1 + 24) == 1 )
            v26 = 1;
          v40 = v26;
        }
        goto LABEL_59;
      }
LABEL_74:
      if ( v20 )
        MSCryptFree(v20);
      if ( v15 )
        goto LABEL_77;
      goto LABEL_78;
    }
    break;
  }
  v21 = (struct _KWAIT_BLOCK *)MSCryptAlloc(48 * v13);
  WaitBlockArray = v21;
  v20 = v21;
  if ( v21 )
  {
    memset(v21, 0, 48 * v13);
    goto LABEL_37;
  }
LABEL_77:
  MSCryptFree(v15);
LABEL_78:
  v35 = *(void **)(v1 + 8);
  if ( v35 )
  {
    MSCryptFree(v35);
    *(_QWORD *)(v1 + 8) = 0;
  }
  KeCancelTimer((PKTIMER)(v1 + 24));
LABEL_81:
  CleanupRegKeyNotifyRoot(v1);
  if ( v1 )
  {
    v36 = *(struct _KEVENT **)(v1 + 16);
    if ( v36 )
      KeSetEvent(v36, 0, 0);
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x180045220  push    rbp
0x180045222  push    rbx
0x180045223  push    rsi
0x180045224  push    rdi
0x180045225  push    r12
0x180045227  push    r13
0x180045229  push    r14
0x18004522b  push    r15
0x18004522d  lea     rbp, [rsp-7A8h]
0x180045235  sub     rsp, 8A8h
0x18004523c  mov     rax, cs:__security_cookie
0x180045243  xor     rax, rsp
0x180045246  mov     [rbp+7E0h+var_50], rax
0x18004524d  mov     [rbp+7E0h+var_860], rcx
0x180045251  mov     qword ptr [rsp+8E0h+var_878], 0
0x18004525a  mov     [rsp+8E0h+var_890], 0
0x180045262  test    rcx, rcx
0x180045265  jnz     short loc_18004527A
0x180045267  xor     ebx, ebx
0x180045269  lea     rcx, aConfigregchang_2; "ConfigRegChangeWatch:: pCngConfigContex"...
0x180045270  call    SendTelemetry
0x180045275  jmp     loc_18004574B
0x18004527a  mov     rbx, [rcx+1A8h]
0x180045281  test    rbx, rbx
0x180045284  jnz     short loc_18004528F
0x180045286  lea     rcx, aConfigregchang_5; "ConfigRegChangeWatch:: pRegKeyNotifyRoo"...
0x18004528d  jmp     short loc_180045270
0x18004528f  xor     r12d, r12d
0x180045292  mov     [rsp+8E0h+WaitBlockArray], 0
0x18004529b  mov     [rsp+8E0h+P], r12
0x1800452a0  mov     [rsp+8E0h+var_88C], r12d
0x1800452a5  call    WaitForRegAvailability
0x1800452aa  lea     rcx, [rbx+18h]; Timer
0x1800452ae  call    cs:__imp_KeInitializeTimer
0x1800452b5  nop     dword ptr [rax+rax+00h]
0x1800452ba  lea     r8, [rsp+8E0h+var_890]
0x1800452bf  mov     rcx, rbx
0x1800452c2  lea     rdx, [rsp+8E0h+var_878]
0x1800452c7  call    InitEventArray
0x1800452cc  test    eax, eax
0x1800452ce  js      loc_180045725
0x1800452d4  mov     r15, qword ptr [rsp+8E0h+var_878]
0x1800452d9  mov     r13d, [rsp+8E0h+var_890]
0x1800452de  mov     r12d, 1
0x1800452e4  xor     edi, edi
0x1800452e6  mov     r14, [rbx]
0x1800452e9  mov     esi, edi
0x1800452eb  shl     rsi, 5
0x1800452ef  mov     rcx, [rsi+r14+10h]; Event
0x1800452f4  call    cs:__imp_KeClearEvent
0x1800452fb  nop     dword ptr [rax+rax+00h]
0x180045300  mov     rcx, [rsi+r14]; KeyHandle
0x180045304  test    rcx, rcx
0x180045307  jz      loc_1800453E6
0x18004530d  mov     rdx, [rsi+r14+8]; Event
0x180045312  lea     rax, [rsp+8E0h+var_878]
0x180045317  mov     [rsp+8E0h+Asynchronous], r12b; Asynchronous
0x18004531c  xorps   xmm0, xmm0
0x18004531f  mov     [rsp+8E0h+BufferSize], 0; BufferSize
0x180045327  mov     r9, r12; ApcContext
0x18004532a  mov     [rsp+8E0h+Buffer], 0; Buffer
0x180045333  xor     r8d, r8d; ApcRoutine
0x180045336  mov     [rsp+8E0h+WatchTree], r12b; WatchTree
0x18004533b  mov     [rsp+8E0h+CompletionFilter], 5; CompletionFilter
0x180045343  mov     [rsp+8E0h+IoStatusBlock], rax; IoStatusBlock
0x180045348  movups  xmmword ptr [rsp+8E0h+var_878], xmm0
0x18004534d  call    cs:__imp_ZwNotifyChangeKey
0x180045354  nop     dword ptr [rax+rax+00h]
0x180045359  cmp     eax, 0C000017Ch
0x18004535e  jnz     short loc_18004537B
0x180045360  mov     rcx, [rsi+r14]; Handle
0x180045364  call    KeRegCloseKey
0x180045369  mov     edx, edi
0x18004536b  mov     rcx, rbx
0x18004536e  call    OpenLowestPossibleRegKey
0x180045373  test    eax, eax
0x180045375  jnz     short loc_1800453D8
0x180045377  dec     edi
0x180045379  jmp     short loc_1800453E6
0x18004537b  test    eax, eax
0x18004537d  jns     short loc_1800453E6
0x18004537f  mov     dword ptr [rsp+8E0h+WatchTree], eax
0x180045383  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x180045387  lea     rax, aConfigregchang_0; "ConfigRegChangeWatch:: ZwNotifyChangeKe"...
0x18004538e  xor     r9d, r9d; unsigned __int64 *
0x180045391  mov     qword ptr [rsp+8E0h+CompletionFilter], rax; unsigned __int16 *
0x180045396  xor     r8d, r8d; unsigned __int16 **
0x180045399  mov     edx, 400h; unsigned __int64
0x18004539e  mov     [rsp+8E0h+IoStatusBlock], 0; unsigned int
0x1800453a7  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800453ac  mov     edx, 80000000h
0x1800453b1  lea     ecx, [rax+rdx]
0x1800453b4  test    edx, ecx
0x1800453b6  jnz     short loc_1800453C6
0x1800453b8  lea     rcx, aConfigregchang_4; "ConfigRegChangeWatch:: ZwNotifyChangeKe"...
0x1800453bf  cmp     eax, 8007007Ah
0x1800453c4  jnz     short loc_1800453CA
0x1800453c6  lea     rcx, [rbp+7E0h+pszDest]
0x1800453ca  call    SendTelemetry
0x1800453cf  mov     rcx, [rsi+r14]; Handle
0x1800453d3  call    KeRegCloseKey
0x1800453d8  mov     r13d, r12d
0x1800453db  mov     qword ptr [rsi+r14], 0
0x1800453e3  sub     r15, r12
0x1800453e6  add     edi, r12d
0x1800453e9  cmp     edi, 2
0x1800453ec  jb      loc_1800452E6
0x1800453f2  mov     r12, [rsp+8E0h+P]
0x1800453f7  test    r12, r12
0x1800453fa  jz      short loc_180045404
0x1800453fc  mov     rcx, r12; P
0x1800453ff  call    MSCryptFree
0x180045404  lea     rdi, [r15+1]
0x180045408  test    r13d, r13d
0x18004540b  jz      short loc_180045410
0x18004540d  inc     rdi
0x180045410  lea     rsi, ds:0[rdi*8]
0x180045418  mov     rcx, rsi
0x18004541b  call    MSCryptAlloc
0x180045420  mov     [rsp+8E0h+P], rax
0x180045425  mov     r12, rax
0x180045428  test    rax, rax
0x18004542b  jz      loc_180045706
0x180045431  mov     r8, rsi; Size
0x180045434  xor     edx, edx; Val
0x180045436  mov     rcx, rax; void *
0x180045439  call    memset
0x18004543e  mov     rax, [rbx+8]
0x180045442  mov     r10d, 1
0x180045448  mov     [r12], rax
0x18004544c  mov     ecx, r10d
0x18004544f  lea     r15, [rbx+18h]
0x180045453  test    r13d, r13d
0x180045456  jz      short loc_180045461
0x180045458  mov     [r12+8], r15
0x18004545d  lea     ecx, [r10+1]
0x180045461  xor     edx, edx
0x180045463  mov     r8d, ecx
0x180045466  cmp     r8, rdi
0x180045469  jnb     short loc_18004548F
0x18004546b  mov     r9, [rbx]
0x18004546e  mov     eax, edx
0x180045470  shl     rax, 5
0x180045474  cmp     qword ptr [rax+r9], 0
0x180045479  jz      short loc_180045487
0x18004547b  mov     rax, [rax+r9+10h]
0x180045480  add     ecx, r10d
0x180045483  mov     [r12+r8*8], rax
0x180045487  add     edx, r10d
0x18004548a  cmp     edx, 2
0x18004548d  jb      short loc_180045463
0x18004548f  mov     r14, [rsp+8E0h+WaitBlockArray]
0x180045494  test    r14, r14
0x180045497  jz      short loc_1800454A9
0x180045499  mov     rcx, r14; P
0x18004549c  call    MSCryptFree
0x1800454a1  xor     r14d, r14d
0x1800454a4  mov     [rsp+8E0h+WaitBlockArray], r14
0x1800454a9  cmp     rdi, 3
0x1800454ad  jbe     short loc_1800454DD
0x1800454af  lea     rsi, [rdi+rdi*2]
0x1800454b3  shl     rsi, 4
0x1800454b7  mov     rcx, rsi
0x1800454ba  call    MSCryptAlloc
0x1800454bf  mov     [rsp+8E0h+WaitBlockArray], rax
0x1800454c4  mov     r14, rax
0x1800454c7  test    rax, rax
0x1800454ca  jz      loc_18004571D
0x1800454d0  mov     r8, rsi; Size
0x1800454d3  xor     edx, edx; Val
0x1800454d5  mov     rcx, rax; void *
0x1800454d8  call    memset
0x1800454dd  test    r13d, r13d
0x1800454e0  jz      short loc_1800454FB
0x1800454e2  xor     r8d, r8d; Dpc
0x1800454e5  mov     rdx, 0FFFFFFFFDC3CBA00h; DueTime
0x1800454ec  mov     rcx, r15; Timer
0x1800454ef  call    cs:__imp_KeSetTimer
0x1800454f6  nop     dword ptr [rax+rax+00h]
0x1800454fb  cmp     [rsp+8E0h+var_88C], 0
0x180045500  jz      loc_18004559A
0x180045506  mov     eax, cs:dword_1800C9588
0x18004550c  cmp     eax, 5
0x18004550f  jbe     short loc_18004557A
0x180045511  mov     rdx, 200000000000h
0x18004551b  lea     rcx, dword_1800C9588
0x180045522  call    _tlgKeywordOn
0x180045527  test    al, al
0x180045529  jz      short loc_18004557A
0x18004552b  mov     qword ptr [rsp+8E0h+var_878], 800h
0x180045534  call    cs:__imp_PsGetCurrentServerSilo
0x18004553b  nop     dword ptr [rax+rax+00h]
0x180045540  test    rax, rax
0x180045543  lea     rdx, aHost; "Host"
0x18004554a  lea     rax, [rsp+8E0h+var_878]
0x18004554f  mov     qword ptr [rsp+8E0h+CompletionFilter], rax
0x180045554  lea     rcx, aContainer; "Container"
0x18004555b  cmovz   rcx, rdx
0x18004555f  lea     rax, [rsp+8E0h+var_888]
0x180045564  lea     rdx, byte_1800C0BC3
0x18004556b  mov     [rsp+8E0h+IoStatusBlock], rax
0x180045570  mov     [rsp+8E0h+var_888], rcx
0x180045575  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18004557a  mov     rax, [rbp+7E0h+var_860]
0x18004557e  mov     rcx, [rax+108h]; Resource
0x180045585  call    CcnPublish
0x18004558a  test    eax, eax
0x18004558c  jz      short loc_18004559A
0x18004558e  lea     rcx, aConfigregchang_1; "ConfigRegChangeWatch:: CcnPublish faile"...
0x180045595  call    SendTelemetry
0x18004559a  xor     esi, esi
0x18004559c  mov     [rsp+8E0h+Buffer], r14; WaitBlockArray
0x1800455a1  mov     ecx, edi; Count
0x1800455a3  mov     qword ptr [rsp+8E0h+WatchTree], rsi; Timeout
0x1800455a8  mov     byte ptr [rsp+8E0h+CompletionFilter], sil; Alertable
0x1800455ad  xor     r9d, r9d; WaitReason
0x1800455b0  mov     rdx, r12; Object
0x1800455b3  mov     [rsp+8E0h+var_88C], esi
0x1800455b7  lea     edi, [rsi+1]
0x1800455ba  mov     byte ptr [rsp+8E0h+IoStatusBlock], sil; WaitMode
0x1800455bf  mov     r8d, edi; WaitType
0x1800455c2  call    cs:__imp_KeWaitForMultipleObjects
0x1800455c9  nop     dword ptr [rax+rax+00h]
0x1800455ce  mov     r8d, eax
0x1800455d1  test    eax, eax
0x1800455d3  jns     short loc_180045623
0x1800455d5  mov     dword ptr [rsp+8E0h+WatchTree], eax
0x1800455d9  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x1800455dd  lea     rax, aConfigregchang_3; "ConfigRegChangeWatch:: KeWaitForMultipl"...
0x1800455e4  xor     r9d, r9d; unsigned __int64 *
0x1800455e7  mov     qword ptr [rsp+8E0h+CompletionFilter], rax; unsigned __int16 *
0x1800455ec  xor     r8d, r8d; unsigned __int16 **
0x1800455ef  mov     edx, 400h; unsigned __int64
0x1800455f4  mov     [rsp+8E0h+IoStatusBlock], rsi; unsigned int
0x1800455f9  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800455fe  mov     edx, 80000000h
0x180045603  lea     ecx, [rax+rdx]
0x180045606  test    edx, ecx
0x180045608  jnz     short loc_180045618
0x18004560a  lea     rcx, aConfigregchang; "ConfigRegChangeWatch:: KeWaitForMultipl"...
0x180045611  cmp     eax, 8007007Ah
0x180045616  jnz     short loc_18004561C
0x180045618  lea     rcx, [rbp+7E0h+pszDest]
0x18004561c  call    SendTelemetry
0x180045621  jmp     short loc_180045662
0x180045623  test    r8d, r8d
0x180045626  jz      loc_18004570B
0x18004562c  test    r8d, 0FFFFFF80h
0x180045633  jnz     short loc_180045662
0x180045635  test    r13d, r13d
0x180045638  jz      short loc_18004563F
0x18004563a  cmp     r8d, edi
0x18004563d  jz      short loc_180045662
0x18004563f  mov     rdx, [rbx]
0x180045642  mov     eax, r13d
0x180045645  neg     eax
0x180045647  sbb     ecx, ecx
0x180045649  neg     ecx
0x18004564b  add     ecx, edi
0x18004564d  sub     r8d, ecx
0x180045650  movsxd  rax, r8d
0x180045653  shl     rax, 5
0x180045657  cmp     [rax+rdx+18h], edi
0x18004565b  cmovz   esi, edi
0x18004565e  mov     [rsp+8E0h+var_88C], esi
0x180045662  test    r13d, r13d
0x180045665  jz      short loc_180045676
0x180045667  mov     rcx, r15; PKTIMER
0x18004566a  call    cs:__imp_KeCancelTimer
0x180045671  nop     dword ptr [rax+rax+00h]
0x180045676  xor     eax, eax
0x180045678  xor     r15d, r15d
0x18004567b  xor     esi, esi
0x18004567d  mov     dword ptr [rsp+8E0h+var_888], eax
0x180045681  xor     r13d, r13d
0x180045684  mov     r14, [rbx]
0x180045687  mov     rdi, r13
0x18004568a  shl     rdi, 5
0x18004568e  mov     [rsp+8E0h+var_890], 0
0x180045696  mov     rcx, [rdi+r14]; Handle
0x18004569a  mov     eax, [rdi+r14+18h]
0x18004569f  mov     dword ptr [rsp+8E0h+var_878], eax
0x1800456a3  test    rcx, rcx
0x1800456a6  jz      short loc_1800456B5
0x1800456a8  call    KeRegCloseKey
0x1800456ad  mov     [rsp+8E0h+var_890], 1
0x1800456b5  mov     edx, esi
0x1800456b7  mov     rcx, rbx
0x1800456ba  call    OpenLowestPossibleRegKey
0x1800456bf  xor     ecx, ecx
0x1800456c1  test    eax, eax
0x1800456c3  jz      short loc_1800456D2
0x1800456c5  lea     eax, [rcx+1]
0x1800456c8  mov     [rdi+r14], rcx
0x1800456cc  mov     dword ptr [rsp+8E0h+var_888], eax
0x1800456d0  jmp     short loc_1800456F2
0x1800456d2  mov     rax, [rbx]
0x1800456d5  cmp     [rdi+rax+18h], ecx
0x1800456d9  jz      short loc_1800456EF
0x1800456db  cmp     [rsp+8E0h+var_890], ecx
  ... truncated ...
```
