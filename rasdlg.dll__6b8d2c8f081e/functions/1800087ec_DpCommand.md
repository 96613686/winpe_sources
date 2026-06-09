# DpCommand

- ea: `0x1800087ec`
- end: `0x180008974`
- name: `DpCommand`
- size: `392`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009340`

## callees

- `0x1800087ec`
- `0x18000dd64`
- `0x18000f154`
- `0x180047a20`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000885f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000885f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008867`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008867`
- `USER32!PostMessageW` at `0x180008961`
- `USER32!PostMessageW` at `0x180008961`
- `USER32!ShowWindow` at `0x18000889c`
- `USER32!ShowWindow` at `0x18000889c`
- `rtutils!TracePrintfExA` at `0x18000882b`
- `rtutils!TracePrintfExA` at `0x180008851`
- `rtutils!TracePrintfExA` at `0x180008884`
- `rtutils!TracePrintfExA` at `0x1800088c1`
- `rtutils!TracePrintfExA` at `0x1800088e5`
- `rtutils!TracePrintfExA` at `0x180008912`
- `rtutils!TracePrintfExA` at `0x180008944`
- `rtutils!TracePrintfExA` at `0x18000882b`
- `rtutils!TracePrintfExA` at `0x180008851`
- `rtutils!TracePrintfExA` at `0x180008884`
- `rtutils!TracePrintfExA` at `0x1800088c1`
- `rtutils!TracePrintfExA` at `0x1800088e5`
- `rtutils!TracePrintfExA` at `0x180008912`
- `rtutils!TracePrintfExA` at `0x180008944`

## string_xrefs

- `0x180008818`: `DpCommand(n=%d,i=%d,c=$%x)`
- `0x18000883f`: `DpCommand:pInfo address (0x%x), Dialog Handle (0x%x)`
- `0x180008873`: `DpCommand:Current proces:(0x%d), Current Thread:(0x%d)`
- `0x1800088b7`: `DpCommand:Cancel pressed`
- `0x1800088db`: `DpCommand:RasHangUp`
- `0x180008908`: `DpCommand:RasHangUp=%d`
- `0x18000893a`: `DpCommand stall, current thread's fCallbacksActive n=%d`

## pseudocode

```c
__int64 __fastcall DpCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // esi
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  int v9; // eax

  v5 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "DpCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "DpCommand:pInfo address (0x%x), Dialog Handle (0x%x)",
        a1,
        *(_QWORD *)(a1 + 16));
      if ( g_dwTraceId != -1 )
      {
        CurrentThreadId = GetCurrentThreadId();
        CurrentProcessId = GetCurrentProcessId();
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "DpCommand:Current proces:(0x%d), Current Thread:(0x%d)",
          CurrentProcessId,
          CurrentThreadId);
      }
    }
  }
  if ( v5 != 2 )
    return 0;
  ShowWindow(*(HWND *)(a1 + 16), 0);
  if ( !*(_DWORD *)(a1 + 124) )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "DpCommand:Cancel pressed");
    *(_DWORD *)(a1 + 124) = 1;
  }
  if ( *(_QWORD *)(a1 + 56) )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "DpCommand:RasHangUp");
    v9 = ((__int64 (__fastcall *)(_QWORD))g_pRasHangUp)(*(_QWORD *)(a1 + 56));
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "DpCommand:RasHangUp=%d", v9);
  }
  CancelOwnedWindows(*(_QWORD *)(a1 + 16));
  if ( (unsigned int)GetCallbackActive(a1) == 1 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "DpCommand stall, current thread's fCallbacksActive n=%d", 1);
    SetTerminateFlag(a1);
  }
  PostMessageW(*(HWND *)(a1 + 16), 0xCCD0u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1800087ec  push    rbx
0x1800087ee  push    rbp
0x1800087ef  push    rsi
0x1800087f0  push    rdi
0x1800087f1  push    r14
0x1800087f3  sub     rsp, 30h
0x1800087f7  mov     rdi, rcx
0x1800087fa  movzx   esi, r8w
0x1800087fe  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180008804  or      ebp, 0FFFFFFFFh
0x180008807  mov     r10, r9
0x18000880a  mov     r14d, 0Ch
0x180008810  cmp     ecx, ebp
0x180008812  jz      short loc_18000888A
0x180008814  movzx   r9d, dx
0x180008818  lea     r8, aDpcommandNDIDC; "DpCommand(n=%d,i=%d,c=$%x)"
0x18000881f  mov     [rsp+58h+var_30], r10
0x180008824  mov     edx, r14d; dwFlags
0x180008827  mov     dword ptr [rsp+58h+var_38], esi
0x18000882b  call    cs:__imp_TracePrintfExA
0x180008831  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180008837  cmp     ecx, ebp
0x180008839  jz      short loc_18000888A
0x18000883b  mov     rax, [rdi+10h]
0x18000883f  lea     r8, aDpcommandPinfo; "DpCommand:pInfo address (0x%x), Dialog "...
0x180008846  mov     r9, rdi
0x180008849  mov     [rsp+58h+var_38], rax
0x18000884e  mov     edx, r14d; dwFlags
0x180008851  call    cs:__imp_TracePrintfExA
0x180008857  cmp     cs:g_dwTraceId, ebp
0x18000885d  jz      short loc_18000888A
0x18000885f  call    cs:__imp_GetCurrentThreadId
0x180008865  mov     ebx, eax
0x180008867  call    cs:__imp_GetCurrentProcessId
0x18000886d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180008873  lea     r8, aDpcommandCurre; "DpCommand:Current proces:(0x%d), Curren"...
0x18000887a  mov     r9d, eax
0x18000887d  mov     dword ptr [rsp+58h+var_38], ebx
0x180008881  mov     edx, r14d; dwFlags
0x180008884  call    cs:__imp_TracePrintfExA
0x18000888a  cmp     esi, 2
0x18000888d  jz      short loc_180008896
0x18000888f  xor     eax, eax
0x180008891  jmp     loc_180008969
0x180008896  mov     rcx, [rdi+10h]; hWnd
0x18000889a  xor     edx, edx; nCmdShow
0x18000889c  call    cs:__imp_ShowWindow
0x1800088a2  cmp     dword ptr [rdi+7Ch], 0
0x1800088a6  mov     ebx, 1
0x1800088ab  jnz     short loc_1800088CA
0x1800088ad  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800088b3  cmp     ecx, ebp
0x1800088b5  jz      short loc_1800088C7
0x1800088b7  lea     r8, aDpcommandCance; "DpCommand:Cancel pressed"
0x1800088be  mov     edx, r14d; dwFlags
0x1800088c1  call    cs:__imp_TracePrintfExA
0x1800088c7  mov     [rdi+7Ch], ebx
0x1800088ca  cmp     qword ptr [rdi+38h], 0
0x1800088cf  jz      short loc_180008918
0x1800088d1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800088d7  cmp     ecx, ebp
0x1800088d9  jz      short loc_1800088EB
0x1800088db  lea     r8, aDpcommandRasha_0; "DpCommand:RasHangUp"
0x1800088e2  mov     edx, r14d; dwFlags
0x1800088e5  call    cs:__imp_TracePrintfExA
0x1800088eb  mov     rcx, [rdi+38h]
0x1800088ef  mov     rax, cs:g_pRasHangUp
0x1800088f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088fb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180008901  cmp     ecx, ebp
0x180008903  jz      short loc_180008918
0x180008905  mov     r9d, eax
0x180008908  lea     r8, aDpcommandRasha; "DpCommand:RasHangUp=%d"
0x18000890f  mov     edx, r14d; dwFlags
0x180008912  call    cs:__imp_TracePrintfExA
0x180008918  mov     rcx, [rdi+10h]
0x18000891c  call    CancelOwnedWindows
0x180008921  mov     rcx, rdi
0x180008924  call    GetCallbackActive
0x180008929  cmp     eax, ebx
0x18000892b  jnz     short loc_180008952
0x18000892d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180008933  cmp     ecx, ebp
0x180008935  jz      short loc_18000894A
0x180008937  mov     r9d, ebx
0x18000893a  lea     r8, aDpcommandStall; "DpCommand stall, current thread's fCall"...
0x180008941  mov     edx, r14d; dwFlags
0x180008944  call    cs:__imp_TracePrintfExA
0x18000894a  mov     rcx, rdi
0x18000894d  call    SetTerminateFlag
0x180008952  mov     rcx, [rdi+10h]; hWnd
0x180008956  xor     r9d, r9d; lParam
0x180008959  xor     r8d, r8d; wParam
0x18000895c  mov     edx, 0CCD0h; Msg
0x180008961  call    cs:__imp_PostMessageW
0x180008967  mov     eax, ebx
0x180008969  add     rsp, 30h
0x18000896d  pop     r14
0x18000896f  pop     rdi
0x180008970  pop     rsi
0x180008971  pop     rbp
0x180008972  pop     rbx
0x180008973  retn
```
