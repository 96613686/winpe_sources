# GetCurrentNetworkId

- ea: `0x180014278`
- end: `0x180014440`
- name: `GetCurrentNetworkId`
- size: `456`
- prototype: `__int64 __fastcall(unsigned __int16 **, enum DefPrnNetworkDescriptor *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012e60`
- `0x18001366c`

## callees

- `0x180014278`
- `0x180014448`
- `0x18001446c`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x1800142a0`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x1800142a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014340`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014340`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001439c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001440d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001439c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001440d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001434e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001437f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001434e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001437f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143e4`
- `KERNEL32!CreateThreadpoolWork` at `0x180014371`
- `KERNEL32!CreateThreadpoolWork` at `0x180014371`
- `KERNEL32!CloseThreadpoolWork` at `0x1800143f2`
- `KERNEL32!CloseThreadpoolWork` at `0x1800143f2`
- `KERNEL32!SubmitThreadpoolWork` at `0x18001438e`
- `KERNEL32!SubmitThreadpoolWork` at `0x18001438e`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180014402`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180014402`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800142b8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800142b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800142d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800142d6`

## pseudocode

```c
__int64 __fastcall GetCurrentNetworkId(unsigned __int16 **a1, enum DefPrnNetworkDescriptor *a2)
{
  DWORD LastError; // ebx
  HRESULT v5; // eax
  int CurrentNetworkIdInternal; // eax
  HANDLE EventW; // rsi
  struct _TP_WORK *v8; // rdi
  DWORD v9; // eax
  __int128 pv; // [rsp+20h] [rbp-49h] BYREF
  __int128 v12; // [rsp+30h] [rbp-39h]
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+40h] [rbp-29h] BYREF

  *a1 = 0;
  *(_DWORD *)a2 = 0;
  if ( RtlIsThreadWithinLoaderCallout() )
    return 1168;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    CurrentNetworkIdInternal = GetCurrentNetworkIdInternal(a1, a2);
    LastError = WIN32_FROM_HRESULT(CurrentNetworkIdInternal);
    CoUninitialize();
    return LastError;
  }
  if ( v5 != -2147417850 )
    return WIN32_FROM_HRESULT(v5);
  *(_QWORD *)&pcbe.Version = 3;
  *(_QWORD *)&pcbe.Size = 72;
  memset(&pcbe.Pool, 0, 56);
  pv = 0;
  v12 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW || (LastError = GetLastError()) == 0 )
  {
    *(_QWORD *)&pv = EventW;
    v8 = CreateThreadpoolWork(GetCurrentNetworkIdWorker, &pv, &pcbe);
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_16;
    }
    SubmitThreadpoolWork(v8);
    v9 = WaitForSingleObject(EventW, 0x3E8u);
    if ( v9 )
    {
      if ( v9 == 128 )
        goto LABEL_22;
      if ( v9 == 258 )
      {
        WaitForThreadpoolWorkCallbacks(v8, 1);
        if ( WaitForSingleObject(EventW, 0) )
        {
          LastError = 1460;
          goto LABEL_16;
        }
        goto LABEL_15;
      }
      if ( v9 != -1 )
      {
LABEL_22:
        LastError = -2147418113;
        goto LABEL_16;
      }
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_16:
        if ( EventW )
          CloseHandle(EventW);
        if ( v8 )
          CloseThreadpoolWork(v8);
        return LastError;
      }
    }
LABEL_15:
    LastError = WIN32_FROM_HRESULT(SDWORD2(pv));
    *a1 = (unsigned __int16 *)v12;
    *(_DWORD *)a2 = DWORD2(v12);
    goto LABEL_16;
  }
  return LastError;
}

```

## disassembly

```asm
0x180014278  push    rbp
0x18001427a  push    rbx
0x18001427b  push    rsi
0x18001427c  push    rdi
0x18001427d  push    r14
0x18001427f  push    r15
0x180014281  lea     rbp, [rsp-2Fh]
0x180014286  sub     rsp, 98h
0x18001428d  mov     r14, rdx
0x180014290  mov     qword ptr [rcx], 0
0x180014297  mov     r15, rcx
0x18001429a  mov     dword ptr [rdx], 0
0x1800142a0  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x1800142a6  test    al, al
0x1800142a8  jz      short loc_1800142B4
0x1800142aa  mov     ebx, 490h
0x1800142af  jmp     loc_18001442E
0x1800142b4  xor     edx, edx; dwCoInit
0x1800142b6  xor     ecx, ecx; pvReserved
0x1800142b8  call    cs:__imp_CoInitializeEx
0x1800142be  test    eax, eax
0x1800142c0  js      short loc_1800142E1
0x1800142c2  mov     rdx, r14; enum DefPrnNetworkDescriptor *
0x1800142c5  mov     rcx, r15; unsigned __int16 **
0x1800142c8  call    ?GetCurrentNetworkIdInternal@@YAJPEAPEAGPEAW4DefPrnNetworkDescriptor@@@Z; GetCurrentNetworkIdInternal(ushort * *,DefPrnNetworkDescriptor *)
0x1800142cd  mov     ecx, eax; int
0x1800142cf  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800142d4  mov     ebx, eax
0x1800142d6  call    cs:__imp_CoUninitialize
0x1800142dc  jmp     loc_18001442E
0x1800142e1  cmp     eax, 80010106h
0x1800142e6  jnz     loc_180014425
0x1800142ec  xorps   xmm0, xmm0
0x1800142ef  mov     qword ptr [rbp+57h+pcbe.Version], 3
0x1800142f7  xor     r9d, r9d; lpName
0x1800142fa  mov     qword ptr [rbp+57h+pcbe.Size], 48h ; 'H'
0x180014302  xor     r8d, r8d; bInitialState
0x180014305  mov     [rbp+57h+pcbe.Pool], 0
0x18001430d  xor     ecx, ecx; lpEventAttributes
0x18001430f  mov     [rbp+57h+pcbe.CleanupGroup], 0
0x180014317  movups  [rbp+57h+pv], xmm0
0x18001431b  lea     edx, [r9+1]; bManualReset
0x18001431f  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x180014327  movups  [rbp+57h+var_90], xmm0
0x18001432b  mov     [rbp+57h+pcbe.FinalizationCallback], 0
0x180014333  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x180014338  mov     qword ptr [rbp+57h+pcbe.u], 0
0x180014340  call    cs:__imp_CreateEventW
0x180014346  mov     rsi, rax
0x180014349  test    rax, rax
0x18001434c  jnz     short loc_18001435E
0x18001434e  call    cs:__imp_GetLastError
0x180014354  mov     ebx, eax
0x180014356  test    eax, eax
0x180014358  jnz     loc_18001442E
0x18001435e  lea     r8, [rbp+57h+pcbe]; pcbe
0x180014362  mov     qword ptr [rbp+57h+pv], rsi
0x180014366  lea     rdx, [rbp+57h+pv]; pv
0x18001436a  lea     rcx, ?GetCurrentNetworkIdWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180014371  call    cs:__imp_CreateThreadpoolWork
0x180014377  mov     rdi, rax
0x18001437a  test    rax, rax
0x18001437d  jnz     short loc_18001438B
0x18001437f  call    cs:__imp_GetLastError
0x180014385  mov     ebx, eax
0x180014387  test    eax, eax
0x180014389  jnz     short loc_1800143DC
0x18001438b  mov     rcx, rdi; pwk
0x18001438e  call    cs:__imp_SubmitThreadpoolWork
0x180014394  mov     edx, 3E8h; dwMilliseconds
0x180014399  mov     rcx, rsi; hHandle
0x18001439c  call    cs:__imp_WaitForSingleObject
0x1800143a2  test    eax, eax
0x1800143a4  jz      short loc_1800143C5
0x1800143a6  cmp     eax, 80h
0x1800143ab  jz      short loc_18001441E
0x1800143ad  cmp     eax, 102h
0x1800143b2  jz      short loc_1800143FA
0x1800143b4  cmp     eax, 0FFFFFFFFh
0x1800143b7  jnz     short loc_18001441E
0x1800143b9  call    cs:__imp_GetLastError
0x1800143bf  mov     ebx, eax
0x1800143c1  test    eax, eax
0x1800143c3  jnz     short loc_1800143DC
0x1800143c5  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x1800143c8  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800143cd  mov     ebx, eax
0x1800143cf  mov     rax, qword ptr [rbp+57h+var_90]
0x1800143d3  mov     [r15], rax
0x1800143d6  mov     eax, dword ptr [rbp+57h+var_90+8]
0x1800143d9  mov     [r14], eax
0x1800143dc  test    rsi, rsi
0x1800143df  jz      short loc_1800143EA
0x1800143e1  mov     rcx, rsi; hObject
0x1800143e4  call    cs:__imp_CloseHandle
0x1800143ea  test    rdi, rdi
0x1800143ed  jz      short loc_18001442E
0x1800143ef  mov     rcx, rdi; pwk
0x1800143f2  call    cs:__imp_CloseThreadpoolWork
0x1800143f8  jmp     short loc_18001442E
0x1800143fa  mov     edx, 1; fCancelPendingCallbacks
0x1800143ff  mov     rcx, rdi; pwk
0x180014402  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180014408  xor     edx, edx; dwMilliseconds
0x18001440a  mov     rcx, rsi; hHandle
0x18001440d  call    cs:__imp_WaitForSingleObject
0x180014413  test    eax, eax
0x180014415  jz      short loc_1800143C5
0x180014417  mov     ebx, 5B4h
0x18001441c  jmp     short loc_1800143DC
0x18001441e  mov     ebx, 8000FFFFh
0x180014423  jmp     short loc_1800143DC
0x180014425  mov     ecx, eax; int
0x180014427  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001442c  mov     ebx, eax
0x18001442e  mov     eax, ebx
0x180014430  add     rsp, 98h
0x180014437  pop     r15
0x180014439  pop     r14
0x18001443b  pop     rdi
0x18001443c  pop     rsi
0x18001443d  pop     rbx
0x18001443e  pop     rbp
0x18001443f  retn
```
