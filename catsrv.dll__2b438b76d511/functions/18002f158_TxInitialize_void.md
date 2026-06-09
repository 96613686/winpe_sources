# TxInitialize(void)

- ea: `0x18002f158`
- end: `0x18002f31e`
- name: `?TxInitialize@@YAJXZ`
- size: `454`
- prototype: `__int64(void)`
- caller_count: `20`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d8c0`
- `0x18000dc28`
- `0x180018620`
- `0x18001a7e0`
- `0x18001b550`
- `0x18001be80`
- `0x18001cd30`
- `0x18001d660`
- `0x18001fd60`
- `0x1800232d0`
- `0x180023460`
- `0x180023610`
- `0x1800237a0`
- `0x180023920`
- `0x1800241f0`
- `0x180025390`
- `0x180026590`
- `0x180028d90`
- `0x180028ec0`
- `0x1800291c0`

## callees

- `0x18000af70`
- `0x18002f158`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f25c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f30b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f25c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f30b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f1c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f1c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f211`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f211`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f185`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f1f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f185`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f1f7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f2d5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002f2d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f249`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f249`

## string_xrefs

- `0x18002f2a7`: `COM+ Registration Database`

## pseudocode

```c
__int64 TxInitialize(void)
{
  int TransactionID; // edi
  int v1; // ebx
  HRESULT v2; // ebx
  int i; // ebx
  struct BOID Buf1; // [rsp+30h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  Buf1 = 0;
  TransactionID = _GetTransactionID(&Buf1);
  if ( !TransactionID )
  {
    EnterCriticalSection(&stru_180073228);
    v1 = memcmp_0(&Buf1, &g_txUOW, 0x10u);
    LeaveCriticalSection(&stru_180073228);
    if ( v1 )
    {
      WaitForSingleObject(g_hTxInProgressEvent, 0xFFFFFFFF);
      dword_180072D18 = TransactionID;
      if ( qword_180072D28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180072D28 + 16LL))(qword_180072D28);
        qword_180072D28 = 0;
      }
      EnterCriticalSection(&stru_180073228);
      g_txUOW = Buf1;
      LeaveCriticalSection(&stru_180073228);
      ppv = 0;
      g_pICrmLogControl = 0;
      v2 = CoCreateInstance(&GUID_ecabb0bd_7f19_11d2_978e_0000f8757e2a, 0, 1u, &IID_IUnknown, &ppv);
      if ( v2 < 0
        || (v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ICrmLogControl **))ppv)(
                   ppv,
                   &GUID_a0e174b3_d26e_11d2_8f84_00805fc7bcd9,
                   &g_pICrmLogControl),
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv),
            v2 < 0) )
      {
        SetEvent(g_hTxInProgressEvent);
        return (unsigned int)v2;
      }
      for ( i = 0; i < 30; ++i )
      {
        TransactionID = ((__int64 (__fastcall *)(struct ICrmLogControl *, const wchar_t *, const wchar_t *, __int64))g_pICrmLogControl->lpVtbl->RegisterCompensator)(
                          g_pICrmLogControl,
                          L"{CB39A782-E5E4-11D1-8CC0-00C04FC3261D}",
                          L"COM+ Registration Database",
                          7);
        if ( TransactionID != -2147168126 )
          break;
        Sleep(0x3E8u);
      }
      if ( TransactionID < 0 )
      {
        ((void (__fastcall *)(struct ICrmLogControl *))g_pICrmLogControl->lpVtbl->Release)(g_pICrmLogControl);
        g_pICrmLogControl = 0;
        SetEvent(g_hTxInProgressEvent);
      }
    }
  }
  return (unsigned int)TransactionID;
}

```

## disassembly

```asm
0x18002f158  mov     [rsp+arg_8], rbx
0x18002f15d  push    rdi
0x18002f15e  sub     rsp, 40h
0x18002f162  xorps   xmm0, xmm0
0x18002f165  lea     rcx, [rsp+48h+Buf1]; struct BOID *
0x18002f16a  movups  xmmword ptr [rsp+48h+Buf1.rgb], xmm0
0x18002f16f  call    ?_GetTransactionID@@YAJPEAUBOID@@@Z; _GetTransactionID(BOID *)
0x18002f174  mov     edi, eax
0x18002f176  test    eax, eax
0x18002f178  jnz     loc_18002F311
0x18002f17e  lea     rcx, stru_180073228; lpCriticalSection
0x18002f185  call    cs:__imp_EnterCriticalSection
0x18002f18b  lea     r8d, [rdi+10h]; Size
0x18002f18f  lea     rdx, ?g_txUOW@@3UBOID@@A; Buf2
0x18002f196  lea     rcx, [rsp+48h+Buf1]; Buf1
0x18002f19b  call    memcmp_0
0x18002f1a0  lea     rcx, stru_180073228; lpCriticalSection
0x18002f1a7  mov     ebx, eax
0x18002f1a9  call    cs:__imp_LeaveCriticalSection
0x18002f1af  test    ebx, ebx
0x18002f1b1  jz      loc_18002F311
0x18002f1b7  mov     rcx, cs:?g_hTxInProgressEvent@@3PEAXEA; hHandle
0x18002f1be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002f1c1  call    cs:__imp_WaitForSingleObject
0x18002f1c7  mov     rcx, cs:qword_180072D28
0x18002f1ce  mov     cs:dword_180072D18, edi
0x18002f1d4  test    rcx, rcx
0x18002f1d7  jz      short loc_18002F1F0
0x18002f1d9  mov     rax, [rcx]
0x18002f1dc  mov     rax, [rax+10h]
0x18002f1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1e5  mov     cs:qword_180072D28, 0
0x18002f1f0  lea     rcx, stru_180073228; lpCriticalSection
0x18002f1f7  call    cs:__imp_EnterCriticalSection
0x18002f1fd  movups  xmm0, xmmword ptr [rsp+48h+Buf1.rgb]
0x18002f202  lea     rcx, stru_180073228; lpCriticalSection
0x18002f209  movdqu  cs:?g_txUOW@@3UBOID@@A, xmm0; BOID g_txUOW
0x18002f211  call    cs:__imp_LeaveCriticalSection
0x18002f217  xor     edx, edx; pUnkOuter
0x18002f219  mov     [rsp+48h+arg_0], 0
0x18002f222  lea     rax, [rsp+48h+arg_0]
0x18002f227  mov     cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA, 0; ICrmLogControl * g_pICrmLogControl
0x18002f232  lea     r9, IID_IUnknown; riid
0x18002f239  mov     [rsp+48h+ppv], rax; ppv
0x18002f23e  lea     rcx, _GUID_ecabb0bd_7f19_11d2_978e_0000f8757e2a; rclsid
0x18002f245  lea     r8d, [rdx+1]; dwClsContext
0x18002f249  call    cs:__imp_CoCreateInstance
0x18002f24f  mov     ebx, eax
0x18002f251  test    eax, eax
0x18002f253  jns     short loc_18002F269
0x18002f255  mov     rcx, cs:?g_hTxInProgressEvent@@3PEAXEA; hEvent
0x18002f25c  call    cs:__imp_SetEvent
0x18002f262  mov     eax, ebx
0x18002f264  jmp     loc_18002F313
0x18002f269  mov     rcx, [rsp+48h+arg_0]
0x18002f26e  lea     r8, ?g_pICrmLogControl@@3PEAUICrmLogControl@@EA; ICrmLogControl * g_pICrmLogControl
0x18002f275  lea     rdx, _GUID_a0e174b3_d26e_11d2_8f84_00805fc7bcd9
0x18002f27c  mov     rax, [rcx]
0x18002f27f  mov     rax, [rax]
0x18002f282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f287  mov     rcx, [rsp+48h+arg_0]
0x18002f28c  mov     ebx, eax
0x18002f28e  mov     rdx, [rcx]
0x18002f291  mov     rax, [rdx+10h]
0x18002f295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f29a  test    ebx, ebx
0x18002f29c  js      short loc_18002F255
0x18002f29e  xor     ebx, ebx
0x18002f2a0  mov     rcx, cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA; ICrmLogControl * g_pICrmLogControl
0x18002f2a7  lea     r8, aComRegistratio; "COM+ Registration Database"
0x18002f2ae  mov     r9d, 7
0x18002f2b4  lea     rdx, aCb39a782E5e411; "{CB39A782-E5E4-11D1-8CC0-00C04FC3261D}"
0x18002f2bb  mov     rax, [rcx]
0x18002f2be  mov     rax, [rax+20h]
0x18002f2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2c7  mov     edi, eax
0x18002f2c9  cmp     eax, 8004D082h
0x18002f2ce  jnz     short loc_18002F2E2
0x18002f2d0  mov     ecx, 3E8h; dwMilliseconds
0x18002f2d5  call    cs:__imp_Sleep
0x18002f2db  inc     ebx
0x18002f2dd  cmp     ebx, 1Eh
0x18002f2e0  jl      short loc_18002F2A0
0x18002f2e2  test    edi, edi
0x18002f2e4  jns     short loc_18002F311
0x18002f2e6  mov     rcx, cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA; ICrmLogControl * g_pICrmLogControl
0x18002f2ed  mov     rax, [rcx]
0x18002f2f0  mov     rax, [rax+10h]
0x18002f2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2f9  mov     rcx, cs:?g_hTxInProgressEvent@@3PEAXEA; hEvent
0x18002f300  mov     cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA, 0; ICrmLogControl * g_pICrmLogControl
0x18002f30b  call    cs:__imp_SetEvent
0x18002f311  mov     eax, edi
0x18002f313  mov     rbx, [rsp+48h+arg_8]
0x18002f318  add     rsp, 40h
0x18002f31c  pop     rdi
0x18002f31d  retn
```
