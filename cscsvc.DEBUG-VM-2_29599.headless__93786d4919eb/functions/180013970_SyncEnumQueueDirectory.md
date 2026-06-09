# SyncEnumQueueDirectory

- ea: `0x180013970`
- end: `0x180013e41`
- name: `SyncEnumQueueDirectory`
- size: `1233`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011ef0`

## callees

- `0x180004c40`
- `0x180011ef0`
- `0x180013970`
- `0x1800360c0`
- `0x180036394`
- `0x1800772e4`
- `0x18007cac4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013b80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013b80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013c2a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013c91`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013c91`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013e1e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013e1e`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x180013ac6`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x180013ac6`
- `KERNEL32!GetCurrentProcess` at `0x180013dd0`
- `KERNEL32!GetCurrentProcess` at `0x180013dd0`
- `KERNEL32!LocalAlloc` at `0x180013bf0`
- `KERNEL32!LocalAlloc` at `0x180013bf0`
- `KERNEL32!LocalFree` at `0x180013af0`
- `KERNEL32!LocalFree` at `0x180013af0`
- `ADVAPI32!OpenProcessToken` at `0x180013de3`
- `ADVAPI32!OpenProcessToken` at `0x180013de3`
- `ADVAPI32!OpenThreadToken` at `0x180013c41`
- `ADVAPI32!OpenThreadToken` at `0x180013c41`

## string_xrefs

- `0x180013ca9`: `SyncEnumQueueDirectory: phdl: 0x%p shdl: 0x%p pDirInfo: 0x%p sDirInfo: 0x%p args: 0x%p`
- `0x180013d19`: `SyncEnumQueueDirectory: mode: 0x%x callback_arg: 0x%p sync: 0x%p Depth: %d`
- `0x180013b30`: `SyncEnumQueueDirectory: 0x%x`
- `0x180013d83`: `SyncEnumQueueDirectory: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncEnumQueueDirectory(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        TOKEN_TYPE a11)
{
  CObjectMonitor *v14; // rax
  unsigned int v15; // ebx
  __int32 v16; // ecx
  DWORD LastError; // r12d
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rbp
  __int32 v22; // ecx
  char *v23; // r14
  HANDLE *v24; // r13
  HANDLE CurrentThread; // rax
  __int64 v26; // r8
  HANDLE CurrentProcess; // rax
  TOKEN_TYPE TokenType[2]; // [rsp+20h] [rbp-B8h]
  char v29[8]; // [rsp+60h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-70h] BYREF
  __int64 v31; // [rsp+70h] [rbp-68h] BYREF
  __int64 v32; // [rsp+78h] [rbp-60h] BYREF
  __int64 v33; // [rsp+80h] [rbp-58h] BYREF
  PTP_CALLBACK_ENVIRON pcbe; // [rsp+88h] [rbp-50h]
  int v35; // [rsp+F8h] [rbp+20h]

  v35 = a4;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v29[0] = 0;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncEnumQueueDirectory: phdl: 0x%p shdl: 0x%p pDirInfo: 0x%p sDirInfo: 0x%p args: 0x%p",
        a1,
        a2,
        a3,
        a5,
        a7);
      WPP_SF_qqqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        28,
        WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids,
        a1,
        a2,
        a3,
        a5,
        a7);
      v14 = WPP_GLOBAL_Control;
      a4 = v35;
    }
    if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 4) != 0 )
    {
      TokenType[0] = a11;
      SyncTraceOutputInternal(
        L"SyncEnumQueueDirectory: mode: 0x%x callback_arg: 0x%p sync: 0x%p Depth: %d",
        a8,
        a9,
        a10,
        *(_QWORD *)TokenType);
      WPP_SF_Dqqd(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, v26, a8, a9, a10, a11);
      v14 = WPP_GLOBAL_Control;
      a4 = v35;
    }
  }
  if ( a11 != TokenPrimary )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int, __int64, int, __int64 *, __int64 *, __int64 *, char *))(a7 + 8))(
            a9,
            a1,
            a2,
            a3,
            a4,
            a5,
            a6,
            &v33,
            &v32,
            &v31,
            v29);
    if ( !v15 && v29[0] )
    {
      if ( (a8 & 8) == 0
        || (TotalAlloc += 80,
            ++NumAlloc,
            ProcessHeap = GetProcessHeap(),
            v20 = HeapAlloc(ProcessHeap, 8u, 0x50u),
            (v21 = v20) == 0) )
      {
LABEL_11:
        v16 = 0;
        if ( a11 )
          v16 = a11 - 1;
        v15 = SyncEnumTreeInternal(v33, v32, a7, a8, v31, a10, v16);
        goto LABEL_21;
      }
      v20[3] = v33;
      v20[4] = v32;
      v20[6] = a7;
      v20[7] = v31;
      v22 = 0;
      *((_DWORD *)v20 + 10) = a8;
      v20[8] = a10;
      *((_DWORD *)v20 + 4) = 0;
      if ( a11 )
        v22 = a11 - 1;
      *((_DWORD *)v20 + 18) = v22;
      _InterlockedIncrement((volatile signed __int32 *)a10);
      pcbe = *(PTP_CALLBACK_ENVIRON *)(a7 + 64);
      v23 = (char *)LocalAlloc(0x40u, 0x28u);
      if ( !v23 && GetLastError() )
      {
LABEL_35:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a10, 0xFFFFFFFF) == 1 )
          SetEvent(*(HANDLE *)(a10 + 8));
        SyncFree(v21);
        goto LABEL_11;
      }
      *(_DWORD *)v23 = 1;
      *((_QWORD *)v23 + 2) = SyncEnumThread;
      v24 = (HANDLE *)(v23 + 8);
      *((_QWORD *)v23 + 4) = v21;
      *((_QWORD *)v23 + 3) = SyncEnumWorkItemCancelled;
      LastError = 0;
      *((_QWORD *)v23 + 1) = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)v23 + 1) )
      {
        LastError = GetLastError();
        if ( LastError == 1008 )
        {
          TokenHandle = 0;
          CurrentProcess = GetCurrentProcess();
          if ( OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
          {
            LastError = 0;
            if ( !DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)v23 + 1) )
              LastError = GetLastError();
            CloseHandle(TokenHandle);
          }
          else
          {
            LastError = GetLastError();
          }
        }
      }
      if ( LastError )
      {
LABEL_16:
        if ( v23 )
        {
          if ( *v24 )
            CloseHandle(*v24);
          LocalFree(v23);
        }
        if ( !LastError )
          goto LABEL_21;
        goto LABEL_35;
      }
      if ( !TrySubmitThreadpoolCallback(CscTppSimpleWorkItemCallback, v23, pcbe) )
      {
        LastError = GetLastError();
        goto LABEL_16;
      }
    }
LABEL_21:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumQueueDirectory: 0x%x", v15);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v15);
    }
    return v15;
  }
  if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumQueueDirectory: 0x%x", 0);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180013970  mov     r11, rsp
0x180013973  mov     [r11+20h], r9d
0x180013977  push    rbx
0x180013978  push    rbp
0x180013979  push    rsi
0x18001397a  push    rdi
0x18001397b  push    r12
0x18001397d  push    r13
0x18001397f  push    r14
0x180013981  push    r15
0x180013983  sub     rsp, 98h
0x18001398a  xor     eax, eax
0x18001398c  mov     rbp, r8
0x18001398f  mov     [r11-58h], rax
0x180013993  mov     r14, rdx
0x180013996  mov     [r11-60h], rax
0x18001399a  mov     r12, rcx
0x18001399d  mov     [r11-68h], rax
0x1800139a1  mov     [rsp+0D8h+var_78], al
0x1800139a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800139ac  lea     rcx, WPP_GLOBAL_Control
0x1800139b3  mov     edi, [rsp+0D8h+arg_50]
0x1800139ba  mov     rbx, [rsp+0D8h+arg_40]
0x1800139c2  mov     esi, [rsp+0D8h+arg_38]
0x1800139c9  mov     r15, [rsp+0D8h+arg_30]
0x1800139d1  mov     r13, [rsp+0D8h+arg_20]
0x1800139d9  cmp     rax, rcx
0x1800139dc  jz      short loc_1800139F7
0x1800139de  test    byte ptr [rax+6Ch], 4
0x1800139e2  jnz     loc_180013CA4
0x1800139e8  cmp     rax, rcx
0x1800139eb  jz      short loc_1800139F7
0x1800139ed  test    byte ptr [rax+6Ch], 4
0x1800139f1  jnz     loc_180013D11
0x1800139f7  cmp     edi, 1
0x1800139fa  jz      loc_180013C5D
0x180013a00  mov     edx, [rsp+0D8h+arg_28]
0x180013a07  lea     rax, [rsp+0D8h+var_78]
0x180013a0c  mov     [rsp+0D8h+var_88], rax
0x180013a11  mov     r8, r14
0x180013a14  lea     rax, [rsp+0D8h+var_68]
0x180013a19  mov     rcx, rbx
0x180013a1c  mov     [rsp+0D8h+var_90], rax
0x180013a21  lea     rax, [rsp+0D8h+var_60]
0x180013a26  mov     [rsp+0D8h+var_98], rax
0x180013a2b  lea     rax, [rsp+0D8h+var_58]
0x180013a33  mov     [rsp+0D8h+var_A0], rax
0x180013a38  mov     rax, [r15+8]
0x180013a3c  mov     dword ptr [rsp+0D8h+var_A8], edx
0x180013a40  mov     rdx, r12
0x180013a43  mov     [rsp+0D8h+phNewToken], r13
0x180013a48  mov     [rsp+0D8h+TokenType], r9d
0x180013a4d  mov     r9, rbp
0x180013a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a55  mov     ebx, eax
0x180013a57  test    eax, eax
0x180013a59  jnz     loc_180013AFF
0x180013a5f  cmp     [rsp+0D8h+var_78], al
0x180013a63  jz      loc_180013AFF
0x180013a69  test    sil, 8
0x180013a6d  jnz     loc_180013B5D
0x180013a73  mov     rdx, [rsp+0D8h+var_60]
0x180013a78  lea     eax, [rdi-1]
0x180013a7b  xor     ecx, ecx
0x180013a7d  mov     r9d, esi
0x180013a80  test    edi, edi
0x180013a82  mov     r8, r15
0x180013a85  cmovnz  ecx, eax
0x180013a88  mov     rax, [rsp+0D8h+arg_48]
0x180013a90  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x180013a94  mov     rcx, [rsp+0D8h+var_58]
0x180013a9c  mov     [rsp+0D8h+phNewToken], rax
0x180013aa1  mov     rax, [rsp+0D8h+var_68]
0x180013aa6  mov     qword ptr [rsp+0D8h+TokenType], rax
0x180013aab  call    SyncEnumTreeInternal
0x180013ab0  mov     ebx, eax
0x180013ab2  jmp     short loc_180013AFF
0x180013ab4  mov     r8, [rsp+0D8h+pcbe]; pcbe
0x180013abc  lea     rcx, ?CscTppSimpleWorkItemCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180013ac3  mov     rdx, r14; pv
0x180013ac6  call    cs:__imp_TrySubmitThreadpoolCallback
0x180013acc  test    eax, eax
0x180013ace  jnz     short loc_180013AFF
0x180013ad0  call    cs:__imp_GetLastError
0x180013ad6  mov     r12d, eax
0x180013ad9  test    r14, r14
0x180013adc  jz      short loc_180013AF6
0x180013ade  mov     rcx, [r13+0]; hObject
0x180013ae2  test    rcx, rcx
0x180013ae5  jz      short loc_180013AED
0x180013ae7  call    cs:__imp_CloseHandle
0x180013aed  mov     rcx, r14; hMem
0x180013af0  call    cs:__imp_LocalFree
0x180013af6  test    r12d, r12d
0x180013af9  jnz     loc_180013C77
0x180013aff  mov     rax, cs:WPP_GLOBAL_Control
0x180013b06  lea     rcx, WPP_GLOBAL_Control
0x180013b0d  cmp     rax, rcx
0x180013b10  jnz     short loc_180013B28
0x180013b12  mov     eax, ebx
0x180013b14  add     rsp, 98h
0x180013b1b  pop     r15
0x180013b1d  pop     r14
0x180013b1f  pop     r13
0x180013b21  pop     r12
0x180013b23  pop     rdi
0x180013b24  pop     rsi
0x180013b25  pop     rbp
0x180013b26  pop     rbx
0x180013b27  retn
0x180013b28  test    byte ptr [rax+6Ch], 8
0x180013b2c  jz      short loc_180013B12
0x180013b2e  mov     edx, ebx
0x180013b30  lea     rcx, aSyncenumqueued; "SyncEnumQueueDirectory: 0x%x"
0x180013b37  call    SyncTraceOutputInternal
0x180013b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b43  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x180013b4a  mov     edx, 1Fh
0x180013b4f  mov     r9d, ebx
0x180013b52  mov     rcx, [rcx+60h]
0x180013b56  call    WPP_SF_d
0x180013b5b  jmp     short loc_180013B12
0x180013b5d  add     cs:TotalAlloc, 50h ; 'P'
0x180013b65  inc     cs:NumAlloc
0x180013b6c  call    cs:__imp_GetProcessHeap
0x180013b72  mov     edx, 8; dwFlags
0x180013b77  mov     r8d, 50h ; 'P'; dwBytes
0x180013b7d  mov     rcx, rax; hHeap
0x180013b80  call    cs:__imp_HeapAlloc
0x180013b86  mov     rbp, rax
0x180013b89  test    rax, rax
0x180013b8c  jz      loc_180013A73
0x180013b92  mov     rcx, [rsp+0D8h+var_58]
0x180013b9a  mov     rdx, [rsp+0D8h+arg_48]
0x180013ba2  mov     [rax+18h], rcx
0x180013ba6  mov     rcx, [rsp+0D8h+var_60]
0x180013bab  mov     [rax+20h], rcx
0x180013baf  mov     [rax+30h], r15
0x180013bb3  mov     rcx, [rsp+0D8h+var_68]
0x180013bb8  mov     [rax+38h], rcx
0x180013bbc  xor     ecx, ecx
0x180013bbe  test    edi, edi
0x180013bc0  mov     [rax+28h], esi
0x180013bc3  mov     [rax+40h], rdx
0x180013bc7  mov     dword ptr [rax+10h], 0
0x180013bce  lea     eax, [rdi-1]
0x180013bd1  cmovnz  ecx, eax
0x180013bd4  mov     [rbp+48h], ecx
0x180013bd7  lock inc dword ptr [rdx]
0x180013bda  mov     rax, [r15+40h]
0x180013bde  mov     edx, 28h ; '('; uBytes
0x180013be3  mov     ecx, 40h ; '@'; uFlags
0x180013be8  mov     [rsp+0D8h+pcbe], rax
0x180013bf0  call    cs:__imp_LocalAlloc
0x180013bf6  mov     r14, rax
0x180013bf9  test    rax, rax
0x180013bfc  jz      short loc_180013C6D
0x180013bfe  lea     rax, SyncEnumThread
0x180013c05  mov     dword ptr [r14], 1
0x180013c0c  mov     [r14+10h], rax
0x180013c10  lea     r13, [r14+8]
0x180013c14  lea     rax, SyncEnumWorkItemCancelled
0x180013c1b  mov     [r14+20h], rbp
0x180013c1f  mov     [r14+18h], rax
0x180013c23  xor     r12d, r12d
0x180013c26  mov     [r13+0], r12
0x180013c2a  call    cs:__imp_GetCurrentThread
0x180013c30  mov     r9, r13; TokenHandle
0x180013c33  mov     edx, 0Ch; DesiredAccess
0x180013c38  mov     rcx, rax; ThreadHandle
0x180013c3b  mov     r8d, 1; OpenAsSelf
0x180013c41  call    cs:__imp_OpenThreadToken
0x180013c47  test    eax, eax
0x180013c49  jz      loc_180013DB3
0x180013c4f  test    r12d, r12d
0x180013c52  jz      loc_180013AB4
0x180013c58  jmp     loc_180013AD9
0x180013c5d  cmp     rax, rcx
0x180013c60  jnz     loc_180013D77
0x180013c66  xor     eax, eax
0x180013c68  jmp     loc_180013B14
0x180013c6d  call    cs:__imp_GetLastError
0x180013c73  test    eax, eax
0x180013c75  jz      short loc_180013BFE
0x180013c77  mov     rcx, [rsp+0D8h+arg_48]
0x180013c7f  mov     eax, 0FFFFFFFFh
0x180013c84  lock xadd [rcx], eax
0x180013c88  cmp     eax, 1
0x180013c8b  jnz     short loc_180013C97
0x180013c8d  mov     rcx, [rcx+8]; hEvent
0x180013c91  call    cs:__imp_SetEvent
0x180013c97  mov     rcx, rbp
0x180013c9a  call    SyncFree
0x180013c9f  jmp     loc_180013A73
0x180013ca4  mov     [rsp+0D8h+phNewToken], r15
0x180013ca9  lea     rcx, aSyncenumqueued_0; "SyncEnumQueueDirectory: phdl: 0x%p shdl"...
0x180013cb0  mov     r9, rbp
0x180013cb3  mov     qword ptr [rsp+0D8h+TokenType], r13
0x180013cb8  mov     r8, r14
0x180013cbb  mov     rdx, r12
0x180013cbe  call    SyncTraceOutputInternal
0x180013cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cca  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x180013cd1  mov     [rsp+0D8h+var_A0], r15
0x180013cd6  mov     edx, 1Ch
0x180013cdb  mov     [rsp+0D8h+var_A8], r13
0x180013ce0  mov     r9, r12
0x180013ce3  mov     [rsp+0D8h+phNewToken], rbp
0x180013ce8  mov     rcx, [rcx+60h]
0x180013cec  mov     qword ptr [rsp+0D8h+TokenType], r14
0x180013cf1  call    WPP_SF_qqqqq
0x180013cf6  mov     rax, cs:WPP_GLOBAL_Control
0x180013cfd  lea     rcx, WPP_GLOBAL_Control
0x180013d04  mov     r9d, [rsp+0D8h+arg_18]
0x180013d0c  jmp     loc_1800139E8
0x180013d11  mov     r9, [rsp+0D8h+arg_48]
0x180013d19  lea     rcx, aSyncenumqueued_1; "SyncEnumQueueDirectory: mode: 0x%x call"...
0x180013d20  mov     r8, rbx
0x180013d23  mov     [rsp+0D8h+TokenType], edi
0x180013d27  mov     edx, esi
0x180013d29  call    SyncTraceOutputInternal
0x180013d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d35  mov     edx, 1Dh
0x180013d3a  mov     rax, [rsp+0D8h+arg_48]
0x180013d42  mov     r9d, esi
0x180013d45  mov     dword ptr [rsp+0D8h+var_A8], edi
0x180013d49  mov     [rsp+0D8h+phNewToken], rax
0x180013d4e  mov     rcx, [rcx+60h]
0x180013d52  mov     qword ptr [rsp+0D8h+TokenType], rbx
0x180013d57  call    WPP_SF_Dqqd
0x180013d5c  mov     rax, cs:WPP_GLOBAL_Control
0x180013d63  lea     rcx, WPP_GLOBAL_Control
0x180013d6a  mov     r9d, [rsp+0D8h+arg_18]
0x180013d72  jmp     loc_1800139F7
0x180013d77  test    byte ptr [rax+6Ch], 8
0x180013d7b  jz      loc_180013C66
0x180013d81  xor     edx, edx
0x180013d83  lea     rcx, aSyncenumqueued; "SyncEnumQueueDirectory: 0x%x"
0x180013d8a  call    SyncTraceOutputInternal
0x180013d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d96  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x180013d9d  mov     edx, 1Eh
0x180013da2  xor     r9d, r9d
0x180013da5  mov     rcx, [rcx+60h]
0x180013da9  call    WPP_SF_d
0x180013dae  jmp     loc_180013C66
0x180013db3  call    cs:__imp_GetLastError
0x180013db9  mov     r12d, eax
0x180013dbc  cmp     eax, 3F0h
0x180013dc1  jnz     loc_180013C4F
0x180013dc7  mov     [rsp+0D8h+TokenHandle], 0
0x180013dd0  call    cs:__imp_GetCurrentProcess
0x180013dd6  lea     r8, [rsp+0D8h+TokenHandle]; TokenHandle
0x180013ddb  mov     edx, 2; DesiredAccess
0x180013de0  mov     rcx, rax; ProcessHandle
0x180013de3  call    cs:__imp_OpenProcessToken
0x180013de9  test    eax, eax
0x180013deb  jnz     short loc_180013DFB
0x180013ded  call    cs:__imp_GetLastError
0x180013df3  mov     r12d, eax
0x180013df6  jmp     loc_180013C4F
0x180013dfb  mov     rcx, [rsp+0D8h+TokenHandle]; hExistingToken
0x180013e00  mov     r9d, 2; ImpersonationLevel
0x180013e06  mov     [rsp+0D8h+phNewToken], r13; phNewToken
0x180013e0b  xor     r8d, r8d; lpTokenAttributes
0x180013e0e  mov     edx, 0Ch; dwDesiredAccess
0x180013e13  mov     [rsp+0D8h+TokenType], 2; TokenType
0x180013e1b  xor     r12d, r12d
0x180013e1e  call    cs:__imp_DuplicateTokenEx
0x180013e24  test    eax, eax
0x180013e26  jnz     short loc_180013E31
0x180013e28  call    cs:__imp_GetLastError
0x180013e2e  mov     r12d, eax
0x180013e31  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180013e36  call    cs:__imp_CloseHandle
0x180013e3c  jmp     loc_180013C4F
```
