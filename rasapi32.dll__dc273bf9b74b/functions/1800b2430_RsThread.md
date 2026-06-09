# RsThread

- ea: `0x1800b2430`
- end: `0x1800b286d`
- name: `RsThread`
- size: `1085`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800b1ef4`
- `0x1800b2284`
- `0x1800b2318`
- `0x1800b23c8`
- `0x1800b2430`
- `0x1800b2874`
- `0x1800b7a2c`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b24dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b2825`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b24dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b2825`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2766`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2766`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b250c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b2538`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b250c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b2538`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800b2530`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800b2530`
- `rtutils!TracePrintfExA` at `0x1800b248b`
- `rtutils!TracePrintfExA` at `0x1800b24be`
- `rtutils!TracePrintfExA` at `0x1800b257c`
- `rtutils!TracePrintfExA` at `0x1800b2634`
- `rtutils!TracePrintfExA` at `0x1800b26a0`
- `rtutils!TracePrintfExA` at `0x1800b26c3`
- `rtutils!TracePrintfExA` at `0x1800b27ce`
- `rtutils!TracePrintfExA` at `0x1800b2806`
- `rtutils!TracePrintfExA` at `0x1800b2842`
- `rtutils!TracePrintfExA` at `0x1800b248b`
- `rtutils!TracePrintfExA` at `0x1800b24be`
- `rtutils!TracePrintfExA` at `0x1800b257c`
- `rtutils!TracePrintfExA` at `0x1800b2634`
- `rtutils!TracePrintfExA` at `0x1800b26a0`
- `rtutils!TracePrintfExA` at `0x1800b26c3`
- `rtutils!TracePrintfExA` at `0x1800b27ce`
- `rtutils!TracePrintfExA` at `0x1800b2806`
- `rtutils!TracePrintfExA` at `0x1800b2842`
- `rtutils!TraceDumpExA` at `0x1800b273c`
- `rtutils!TraceDumpExA` at `0x1800b273c`
- `rasman!RasPortCancelReceive` at `0x1800b281b`
- `rasman!RasPortCancelReceive` at `0x1800b281b`
- `rasman!RasGetInfo` at `0x1800b2662`
- `rasman!RasGetInfo` at `0x1800b2662`

## string_xrefs

- `0x1800b256d`: `RsThread: waited for %d milliseconds`
- `0x1800b27f7`: `RsThread: stop event signalled`
- `0x1800b2481`: `RsThread`
- `0x1800b27db`: `Link dropped! port no longer in connecting state`
- `0x1800b2625`: `RsThread: receive event signalled`
- `0x1800b2836`: `RsThread done`
- `0x1800b26b7`: `RsThread: received %d bytes`

## pseudocode

```c
__int64 __fastcall RsThread(PVOID Parameter)
{
  __int64 v1; // rsi
  DWORD v3; // eax
  DWORD v4; // edi
  int v5; // r13d
  DWORD TickCount; // r15d
  DWORD v7; // r9d
  DWORD v8; // eax
  DWORD v9; // r12d
  DWORD v10; // ecx
  DWORD v11; // r15d
  DWORD v12; // r12d
  DWORD v13; // eax
  _DWORD *v14; // rcx
  DWORD v15; // eax
  DWORD Info; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+64h] [rbp-9Ch]
  int v25; // [rsp+6Ch] [rbp-94h]
  DWORD dwByteCount; // [rsp+1B4h] [rbp+B4h]

  v1 = *((_QWORD *)Parameter + 14);
  *(_OWORD *)Handles = 0;
  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThread");
  v3 = RsPostReceive(Parameter);
  v4 = v3;
  if ( v3 && v3 != 600 )
  {
    if ( g_dwRasscrptTraceId != -1 )
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d posting receive to RASMAN", v3);
    RsPostReceiveEx(Parameter);
    RsSignal(Parameter, 1);
    SetEvent(*((HANDLE *)Parameter + 12));
    return v4;
  }
  Handles[0] = *((HANDLE *)Parameter + 11);
  v5 = 1;
  Handles[1] = *((HANDLE *)Parameter + 9);
  if ( v1 )
    *(_DWORD *)(v1 + 8) = -1;
  while ( 1 )
  {
    TickCount = GetTickCount();
    if ( v1 )
      v7 = *(_DWORD *)(v1 + 8);
    else
      v7 = -1;
    v4 = WaitForMultipleObjects(2u, Handles, 0, v7);
    v8 = GetTickCount();
    v9 = v8;
    if ( v8 < TickCount )
      v9 = -1 - TickCount + v8;
    v10 = 0;
    if ( v8 >= TickCount )
      v10 = TickCount;
    v11 = g_dwRasscrptTraceId;
    v12 = v9 - v10;
    if ( g_dwRasscrptTraceId != -1 )
    {
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThread: waited for %d milliseconds", v12);
      v11 = g_dwRasscrptTraceId;
    }
    if ( v1 )
    {
      v13 = *(_DWORD *)(v1 + 8);
      if ( v13 != -1 )
      {
        if ( v12 < v13 )
          *(_DWORD *)(v1 + 8) = v13 - v12;
        else
          *(_DWORD *)(v1 + 8) = -1;
        v11 = g_dwRasscrptTraceId;
      }
    }
    if ( !v4 )
      break;
    if ( v4 == 258 )
    {
      if ( v1 )
      {
        **(_DWORD **)(v1 + 1072) &= ~2u;
        v14 = *(_DWORD **)(v1 + 1072);
        if ( (*v14 & 0x10) != 0 )
        {
          *v14 |= 0x20u;
          **(_DWORD **)(v1 + 1072) &= ~0x10u;
        }
        goto LABEL_55;
      }
    }
    else if ( v4 == 1 )
    {
      memset_0(v23, 0, 0x398u);
      v21 = 0;
      v20 = 0;
      if ( v11 != -1 )
        TracePrintfExA(v11, 0xCu, "RsThread: receive event signalled");
      v15 = RsPostReceiveEx(Parameter);
      v4 = v15;
      if ( v15 && v15 != 600 )
      {
        if ( g_dwRasscrptTraceId != -1 )
          TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d in RsPostReceiveEx", v15);
        goto LABEL_67;
      }
      Info = RasGetInfo(0, *((_QWORD *)Parameter + 5), v23);
      v4 = Info;
      if ( Info )
      {
        if ( g_dwRasscrptTraceId != -1 )
          TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d retrieving RASMAN_INFO", Info);
        goto LABEL_67;
      }
      if ( v25 )
      {
        if ( v24 )
        {
          if ( g_dwRasscrptTraceId != -1 )
            TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "Link dropped! port no longer in connecting state");
          goto LABEL_67;
        }
        if ( g_dwRasscrptTraceId != -1 )
          TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "last error: %d", v25);
      }
      else
      {
        if ( g_dwRasscrptTraceId != -1 )
          TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThread: received %d bytes", dwByteCount);
        v17 = dwByteCount;
        if ( !v5 && !dwByteCount )
          goto LABEL_44;
        *((_DWORD *)Parameter + 16) = dwByteCount;
        v5 = 0;
        *((_DWORD *)Parameter + 17) = 0;
        if ( g_dwTraceId != -1 )
        {
          TraceDumpExA(g_dwTraceId, 1u, *((LPBYTE *)Parameter + 7), v17, 1u, 1, 0);
          v17 = dwByteCount;
        }
        if ( v17 && (*((_BYTE *)Parameter + 8) & 1) != 0 )
        {
          RsSignal(Parameter, 2);
          WaitForSingleObject(*((HANDLE *)Parameter + 10), 0xFFFFFFFF);
        }
        if ( v1 )
        {
          ReadIntoBuffer(v1, &v21, &v20);
LABEL_55:
          if ( (unsigned int)RsThreadProcess(Parameter) == 259 )
          {
            if ( !*((_DWORD *)Parameter + 26) )
              goto LABEL_68;
            RsDestroyData((HGLOBAL)v1);
            *((_QWORD *)Parameter + 14) = 0;
            v1 = 0;
          }
        }
        else
        {
LABEL_44:
          v18 = RsPostReceive(Parameter);
          v4 = v18;
          if ( v18 && v18 != 600 )
          {
            if ( g_dwRasscrptTraceId != -1 )
              TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d in RsPostReceive", v18);
            goto LABEL_67;
          }
        }
      }
    }
  }
  if ( v11 != -1 )
    TracePrintfExA(v11, 0xCu, "RsThread: stop event signalled");
LABEL_67:
  RsSignal(Parameter, 1);
LABEL_68:
  RasPortCancelReceive(*((_QWORD *)Parameter + 5));
  SetEvent(*((HANDLE *)Parameter + 12));
  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThread done");
  return v4;
}

```

## disassembly

```asm
0x1800b2430  push    rbp
0x1800b2432  push    rbx
0x1800b2433  push    rsi
0x1800b2434  push    rdi
0x1800b2435  push    r12
0x1800b2437  push    r13
0x1800b2439  push    r14
0x1800b243b  push    r15
0x1800b243d  lea     rbp, [rsp-318h]
0x1800b2445  sub     rsp, 418h
0x1800b244c  mov     rax, cs:__security_cookie
0x1800b2453  xor     rax, rsp
0x1800b2456  mov     [rbp+350h+var_50], rax
0x1800b245d  mov     rsi, [rcx+70h]
0x1800b2461  mov     rbx, rcx
0x1800b2464  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b246a  or      r15d, 0FFFFFFFFh
0x1800b246e  xorps   xmm0, xmm0
0x1800b2471  mov     r14d, 0Ch
0x1800b2477  movups  xmmword ptr [rsp+450h+Handles], xmm0
0x1800b247c  cmp     ecx, r15d
0x1800b247f  jz      short loc_1800B2491
0x1800b2481  lea     r8, aRsthread; "RsThread"
0x1800b2488  mov     edx, r14d; dwFlags
0x1800b248b  call    cs:__imp_TracePrintfExA
0x1800b2491  mov     rcx, rbx
0x1800b2494  call    RsPostReceive
0x1800b2499  mov     edi, eax
0x1800b249b  test    eax, eax
0x1800b249d  jz      short loc_1800B24E8
0x1800b249f  cmp     eax, 258h
0x1800b24a4  jz      short loc_1800B24E8
0x1800b24a6  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b24ac  cmp     ecx, r15d
0x1800b24af  jz      short loc_1800B24C4
0x1800b24b1  mov     r9d, eax
0x1800b24b4  lea     r8, aErrorDPostingR; "error %d posting receive to RASMAN"
0x1800b24bb  mov     edx, r14d; dwFlags
0x1800b24be  call    cs:__imp_TracePrintfExA
0x1800b24c4  mov     rcx, rbx
0x1800b24c7  call    RsPostReceiveEx
0x1800b24cc  mov     edx, 1
0x1800b24d1  mov     rcx, rbx
0x1800b24d4  call    RsSignal
0x1800b24d9  mov     rcx, [rbx+60h]; hEvent
0x1800b24dd  call    cs:__imp_SetEvent
0x1800b24e3  jmp     loc_1800B2848
0x1800b24e8  mov     rax, [rbx+58h]
0x1800b24ec  mov     r14d, 1
0x1800b24f2  mov     [rsp+450h+Handles], rax
0x1800b24f7  mov     r13d, r14d
0x1800b24fa  mov     rax, [rbx+48h]
0x1800b24fe  mov     [rsp+450h+Handles+8], rax
0x1800b2503  test    rsi, rsi
0x1800b2506  jz      short loc_1800B250C
0x1800b2508  mov     [rsi+8], r15d
0x1800b250c  call    cs:__imp_GetTickCount
0x1800b2512  mov     r15d, eax
0x1800b2515  test    rsi, rsi
0x1800b2518  jz      short loc_1800B2520
0x1800b251a  mov     r9d, [rsi+8]
0x1800b251e  jmp     short loc_1800B2524
0x1800b2520  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800b2524  xor     r8d, r8d; bWaitAll
0x1800b2527  lea     rdx, [rsp+450h+Handles]; lpHandles
0x1800b252c  lea     ecx, [r8+2]; nCount
0x1800b2530  call    cs:__imp_WaitForMultipleObjects
0x1800b2536  mov     edi, eax
0x1800b2538  call    cs:__imp_GetTickCount
0x1800b253e  mov     r12d, eax
0x1800b2541  cmp     eax, r15d
0x1800b2544  jnb     short loc_1800B254F
0x1800b2546  or      ecx, 0FFFFFFFFh
0x1800b2549  sub     ecx, r15d
0x1800b254c  add     r12d, ecx
0x1800b254f  xor     ecx, ecx
0x1800b2551  cmp     eax, r15d
0x1800b2554  cmovnb  ecx, r15d
0x1800b2558  mov     r15d, cs:g_dwRasscrptTraceId
0x1800b255f  sub     r12d, ecx
0x1800b2562  or      ecx, 0FFFFFFFFh
0x1800b2565  cmp     r15d, ecx
0x1800b2568  jz      short loc_1800B258C
0x1800b256a  mov     r9d, r12d
0x1800b256d  lea     r8, aRsthreadWaited; "RsThread: waited for %d milliseconds"
0x1800b2574  mov     edx, 0Ch; dwFlags
0x1800b2579  mov     ecx, r15d; dwTraceID
0x1800b257c  call    cs:__imp_TracePrintfExA
0x1800b2582  mov     r15d, cs:g_dwRasscrptTraceId
0x1800b2589  or      ecx, 0FFFFFFFFh
0x1800b258c  test    rsi, rsi
0x1800b258f  jz      short loc_1800B25AF
0x1800b2591  mov     eax, [rsi+8]
0x1800b2594  cmp     eax, ecx
0x1800b2596  jz      short loc_1800B25AF
0x1800b2598  cmp     r12d, eax
0x1800b259b  jb      short loc_1800B25A2
0x1800b259d  mov     [rsi+8], ecx
0x1800b25a0  jmp     short loc_1800B25A8
0x1800b25a2  sub     eax, r12d
0x1800b25a5  mov     [rsi+8], eax
0x1800b25a8  mov     r15d, cs:g_dwRasscrptTraceId
0x1800b25af  xor     r12d, r12d
0x1800b25b2  test    edi, edi
0x1800b25b4  jz      loc_1800B27F2
0x1800b25ba  cmp     edi, 102h
0x1800b25c0  jnz     short loc_1800B25FA
0x1800b25c2  test    rsi, rsi
0x1800b25c5  jz      loc_1800B250C
0x1800b25cb  mov     rax, [rsi+430h]
0x1800b25d2  and     dword ptr [rax], 0FFFFFFFDh
0x1800b25d5  mov     rcx, [rsi+430h]
0x1800b25dc  mov     eax, [rcx]
0x1800b25de  test    al, 10h
0x1800b25e0  jz      loc_1800B2787
0x1800b25e6  or      eax, 20h
0x1800b25e9  mov     [rcx], eax
0x1800b25eb  mov     rax, [rsi+430h]
0x1800b25f2  and     dword ptr [rax], 0FFFFFFEFh
0x1800b25f5  jmp     loc_1800B2787
0x1800b25fa  cmp     edi, r14d
0x1800b25fd  jnz     loc_1800B250C
0x1800b2603  xor     edx, edx; Val
0x1800b2605  lea     rcx, [rsp+450h+var_3F0]; void *
0x1800b260a  mov     r8d, 398h; Size
0x1800b2610  call    memset_0
0x1800b2615  mov     [rsp+450h+var_40C], r12d
0x1800b261a  mov     [rsp+450h+var_410], r12d
0x1800b261f  cmp     r15d, 0FFFFFFFFh
0x1800b2623  jz      short loc_1800B263A
0x1800b2625  lea     r8, aRsthreadReceiv; "RsThread: receive event signalled"
0x1800b262c  mov     edx, 0Ch; dwFlags
0x1800b2631  mov     ecx, r15d; dwTraceID
0x1800b2634  call    cs:__imp_TracePrintfExA
0x1800b263a  mov     rcx, rbx
0x1800b263d  call    RsPostReceiveEx
0x1800b2642  mov     edi, eax
0x1800b2644  mov     r15d, 258h
0x1800b264a  test    eax, eax
0x1800b264c  jz      short loc_1800B2657
0x1800b264e  cmp     eax, r15d
0x1800b2651  jnz     loc_1800B27B4
0x1800b2657  mov     rdx, [rbx+28h]
0x1800b265b  lea     r8, [rsp+450h+var_3F0]
0x1800b2660  xor     ecx, ecx
0x1800b2662  call    cs:__imp_RasGetInfo
0x1800b2668  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b266e  mov     edi, eax
0x1800b2670  test    eax, eax
0x1800b2672  jnz     loc_1800B27E4
0x1800b2678  mov     r9d, [rsp+450h+var_3E4]
0x1800b267d  test    r9d, r9d
0x1800b2680  jz      short loc_1800B26AB
0x1800b2682  cmp     [rsp+450h+var_3EC], r12d
0x1800b2687  jnz     loc_1800B27D6
0x1800b268d  cmp     ecx, 0FFFFFFFFh
0x1800b2690  jz      loc_1800B250C
0x1800b2696  lea     r8, aLastErrorD; "last error: %d"
0x1800b269d  lea     edx, [rax+0Ch]; dwFlags
0x1800b26a0  call    cs:__imp_TracePrintfExA
0x1800b26a6  jmp     loc_1800B250C
0x1800b26ab  cmp     ecx, 0FFFFFFFFh
0x1800b26ae  jz      short loc_1800B26C9
0x1800b26b0  mov     r9d, [rbp+350h+dwByteCount]
0x1800b26b7  lea     r8, aRsthreadReceiv_0; "RsThread: received %d bytes"
0x1800b26be  mov     edx, 0Ch; dwFlags
0x1800b26c3  call    cs:__imp_TracePrintfExA
0x1800b26c9  mov     eax, [rbp+350h+dwByteCount]
0x1800b26cf  test    r13d, r13d
0x1800b26d2  jnz     short loc_1800B270E
0x1800b26d4  test    eax, eax
0x1800b26d6  jnz     short loc_1800B270E
0x1800b26d8  mov     rcx, rbx
0x1800b26db  call    RsPostReceive
0x1800b26e0  mov     edi, eax
0x1800b26e2  test    eax, eax
0x1800b26e4  jz      loc_1800B250C
0x1800b26ea  cmp     eax, r15d
0x1800b26ed  jz      loc_1800B250C
0x1800b26f3  mov     ecx, cs:g_dwRasscrptTraceId
0x1800b26f9  cmp     ecx, 0FFFFFFFFh
0x1800b26fc  jz      loc_1800B280C
0x1800b2702  lea     r8, aErrorDInRspost; "error %d in RsPostReceive"
0x1800b2709  jmp     loc_1800B27C6
0x1800b270e  mov     [rbx+40h], eax
0x1800b2711  mov     r13d, r12d
0x1800b2714  mov     [rbx+44h], r12d
0x1800b2718  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800b271e  cmp     ecx, 0FFFFFFFFh
0x1800b2721  jz      short loc_1800B2748
0x1800b2723  mov     r8, [rbx+38h]; lpbBytes
0x1800b2727  mov     r9d, eax; dwByteCount
0x1800b272a  mov     [rsp+450h+lpszPrefix], r12; lpszPrefix
0x1800b272f  mov     edx, r14d; dwFlags
0x1800b2732  mov     [rsp+450h+bAddressPrefix], r14d; bAddressPrefix
0x1800b2737  mov     [rsp+450h+dwGroupSize], r14d; dwGroupSize
0x1800b273c  call    cs:__imp_TraceDumpExA
0x1800b2742  mov     eax, [rbp+350h+dwByteCount]
0x1800b2748  test    eax, eax
0x1800b274a  jz      short loc_1800B276C
0x1800b274c  test    [rbx+8], r14b
0x1800b2750  jz      short loc_1800B276C
0x1800b2752  mov     edx, 2
0x1800b2757  mov     rcx, rbx
0x1800b275a  call    RsSignal
0x1800b275f  mov     rcx, [rbx+50h]; hHandle
0x1800b2763  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2766  call    cs:__imp_WaitForSingleObject
0x1800b276c  test    rsi, rsi
0x1800b276f  jz      loc_1800B26D8
0x1800b2775  lea     r8, [rsp+450h+var_410]
0x1800b277a  mov     rcx, rsi
0x1800b277d  lea     rdx, [rsp+450h+var_40C]
0x1800b2782  call    ReadIntoBuffer
0x1800b2787  mov     rcx, rbx
0x1800b278a  call    RsThreadProcess
0x1800b278f  cmp     eax, 103h
0x1800b2794  jnz     loc_1800B250C
0x1800b279a  cmp     [rbx+68h], r12d
0x1800b279e  jz      short loc_1800B2817
0x1800b27a0  mov     rcx, rsi; hMem
0x1800b27a3  call    RsDestroyData
0x1800b27a8  mov     [rbx+70h], r12
0x1800b27ac  mov     rsi, r12
0x1800b27af  jmp     loc_1800B250C
0x1800b27b4  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b27ba  cmp     ecx, 0FFFFFFFFh
0x1800b27bd  jz      short loc_1800B280C
0x1800b27bf  lea     r8, aErrorDInRspost_0; "error %d in RsPostReceiveEx"
0x1800b27c6  mov     r9d, eax
0x1800b27c9  mov     edx, 0Ch; dwFlags
0x1800b27ce  call    cs:__imp_TracePrintfExA
0x1800b27d4  jmp     short loc_1800B280C
0x1800b27d6  cmp     ecx, 0FFFFFFFFh
0x1800b27d9  jz      short loc_1800B280C
0x1800b27db  lea     r8, aLinkDroppedPor; "Link dropped! port no longer in connect"...
0x1800b27e2  jmp     short loc_1800B2801
0x1800b27e4  cmp     ecx, 0FFFFFFFFh
0x1800b27e7  jz      short loc_1800B280C
0x1800b27e9  lea     r8, aErrorDRetrievi; "error %d retrieving RASMAN_INFO"
0x1800b27f0  jmp     short loc_1800B27C6
0x1800b27f2  cmp     r15d, ecx
0x1800b27f5  jz      short loc_1800B280C
0x1800b27f7  lea     r8, aRsthreadStopEv; "RsThread: stop event signalled"
0x1800b27fe  mov     ecx, r15d; dwTraceID
0x1800b2801  mov     edx, 0Ch; dwFlags
0x1800b2806  call    cs:__imp_TracePrintfExA
0x1800b280c  mov     edx, r14d
0x1800b280f  mov     rcx, rbx
0x1800b2812  call    RsSignal
0x1800b2817  mov     rcx, [rbx+28h]
0x1800b281b  call    cs:__imp_RasPortCancelReceive
0x1800b2821  mov     rcx, [rbx+60h]; hEvent
0x1800b2825  call    cs:__imp_SetEvent
0x1800b282b  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2831  cmp     ecx, 0FFFFFFFFh
0x1800b2834  jz      short loc_1800B2848
0x1800b2836  lea     r8, aRsthreadDone; "RsThread done"
0x1800b283d  mov     edx, 0Ch; dwFlags
0x1800b2842  call    cs:__imp_TracePrintfExA
0x1800b2848  mov     eax, edi
0x1800b284a  mov     rcx, [rbp+350h+var_50]
0x1800b2851  xor     rcx, rsp; StackCookie
0x1800b2854  call    __security_check_cookie
0x1800b2859  add     rsp, 418h
0x1800b2860  pop     r15
0x1800b2862  pop     r14
0x1800b2864  pop     r13
0x1800b2866  pop     r12
0x1800b2868  pop     rdi
0x1800b2869  pop     rsi
0x1800b286a  pop     rbx
0x1800b286b  pop     rbp
0x1800b286c  retn
```
