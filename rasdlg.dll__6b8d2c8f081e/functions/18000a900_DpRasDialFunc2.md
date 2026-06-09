# DpRasDialFunc2

- ea: `0x18000a900`
- end: `0x18000ac51`
- name: `DpRasDialFunc2`
- size: `849`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18000a900`
- `0x18000dd64`
- `0x18000ddbc`
- `0x18000edd8`
- `0x18000ee30`
- `0x18002a99c`
- `0x18002b360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000aaa3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000aaa3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000aa70`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000aa70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000aa2d`
- `USER32!PostMessageW` at `0x18000aa8f`
- `USER32!PostMessageW` at `0x18000aa8f`
- `rtutils!TracePrintfExA` at `0x18000a95c`
- `rtutils!TracePrintfExA` at `0x18000a991`
- `rtutils!TracePrintfExA` at `0x18000a9ee`
- `rtutils!TracePrintfExA` at `0x18000aa0e`
- `rtutils!TracePrintfExA` at `0x18000aa3c`
- `rtutils!TracePrintfExA` at `0x18000aa63`
- `rtutils!TracePrintfExA` at `0x18000aae2`
- `rtutils!TracePrintfExA` at `0x18000ab00`
- `rtutils!TracePrintfExA` at `0x18000ab30`
- `rtutils!TracePrintfExA` at `0x18000ab4f`
- `rtutils!TracePrintfExA` at `0x18000ab6a`
- `rtutils!TracePrintfExA` at `0x18000ab99`
- `rtutils!TracePrintfExA` at `0x18000abbc`
- `rtutils!TracePrintfExA` at `0x18000abe8`
- `rtutils!TracePrintfExA` at `0x18000ac1d`
- `rtutils!TracePrintfExA` at `0x18000ac35`
- `rtutils!TracePrintfExA` at `0x18000a95c`
- `rtutils!TracePrintfExA` at `0x18000a991`
- `rtutils!TracePrintfExA` at `0x18000a9ee`
- `rtutils!TracePrintfExA` at `0x18000aa0e`
- `rtutils!TracePrintfExA` at `0x18000aa3c`
- `rtutils!TracePrintfExA` at `0x18000aa63`
- `rtutils!TracePrintfExA` at `0x18000aae2`
- `rtutils!TracePrintfExA` at `0x18000ab00`
- `rtutils!TracePrintfExA` at `0x18000ab30`
- `rtutils!TracePrintfExA` at `0x18000ab4f`
- `rtutils!TracePrintfExA` at `0x18000ab6a`
- `rtutils!TracePrintfExA` at `0x18000ab99`
- `rtutils!TracePrintfExA` at `0x18000abbc`
- `rtutils!TracePrintfExA` at `0x18000abe8`
- `rtutils!TracePrintfExA` at `0x18000ac1d`
- `rtutils!TracePrintfExA` at `0x18000ac35`

## string_xrefs

- `0x18000aa26`: `DpRasDialFunc2:Process:(%x),Thread(%x)`
- `0x18000ab26`: `Current thread's active:(%d)`
- `0x18000abdb`: `Current thread's active:(%d)`
- `0x18000ab45`: `Current Thread wants to terminate itself, its fterminateASSP=1!`
- `0x18000ab60`: `Current thread will decrease its own and global active!`
- `0x18000ab8f`: `Current Thread does NOT want to terminate itself,its fterminateASAP=0!`

## pseudocode

```c
__int64 __fastcall DpRasDialFunc2(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5, int a6, int a7)
{
  DWORD v8; // ecx
  WPARAM v9; // rdi
  __int64 v11; // rbp
  __int64 v12; // rsi
  HWND v13; // rcx
  unsigned int v14; // edi
  int TerminateFlag; // esi
  int CallbackActive; // eax
  DWORD v17; // ecx
  int GlobalCallbackActive; // eax
  DWORD v19; // ecx
  int v20; // eax

  v8 = g_dwTraceId;
  v9 = a2;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "/DpRasDialFunc2(rcs=%d,s=%d,e=%d,x=%d)", a5, a2, a6, a7);
    v8 = g_dwTraceId;
  }
  if ( !a1 )
  {
    if ( v8 != -1 )
      TracePrintfExA(v8, 0xCu, "DpRasDialFunc2(): Invalid pInfo");
    return 0;
  }
  if ( *(_DWORD *)a1 != -1061437218 )
  {
    if ( v8 != -1 )
      TracePrintfExA(v8, 0xCu, "DpRasDialFunc2 returns for Late callback?");
    return 0;
  }
  if ( !(_DWORD)v9 || (unsigned int)v9 > *(_DWORD *)(a1 + 88) )
  {
    if ( v8 != -1 )
      TracePrintfExA(v8, 0xCu, "DpRasDialFunc2 returns for Subentry out of range?");
    return 1;
  }
  v11 = *(_QWORD *)(a1 + 80);
  v12 = 96LL * (unsigned int)(v9 - 1);
  *(_DWORD *)(v12 + v11 + 8) = a7;
  *(_DWORD *)(v12 + v11) = a5;
  *(_DWORD *)(v12 + v11 + 4) = a6;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "Send RasEvent to Dial Progress window, subEntry:(%d)", v9);
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "Get dwError=(%d) from RasMan", *(_DWORD *)(v12 + v11 + 4));
      if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "DpRasDialFunc2:Process:(%x),Thread(%x)",
          (_DWORD)GetCurrentProcessId,
          (_DWORD)GetCurrentThreadId);
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "DpRasDialFunc2:pInfo address (0x%x), Dialog Handle (0x%x)",
            a1,
            *(_QWORD *)(a1 + 16));
      }
    }
  }
  ResetEvent(*(HANDLE *)(a1 + 128));
  v13 = *(HWND *)(a1 + 16);
  *(_DWORD *)(a1 + 136) = 0;
  if ( !PostMessageW(v13, 0xCCCCu, v9, 0) )
  {
    v14 = 0;
    if ( g_dwTraceId == -1 )
      goto LABEL_26;
    TracePrintfExA(g_dwTraceId, 0xCu, "\\DpRasDialFunc2: dwCode from PostMessage()");
LABEL_24:
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "dwCode returned:(%d)", v14);
    goto LABEL_26;
  }
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 128), 0xFFFFFFFF) )
  {
    v14 = *(_DWORD *)(a1 + 136);
    goto LABEL_24;
  }
  v14 = 0;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "\\DpRasDialFunc2: WaitForSingleObject failed");
    goto LABEL_24;
  }
LABEL_26:
  TerminateFlag = GetTerminateFlag(a1);
  CallbackActive = GetCallbackActive(a1);
  v17 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "Current thread's active:(%d)", CallbackActive);
    v17 = g_dwTraceId;
  }
  if ( TerminateFlag )
  {
    if ( v17 != -1 )
    {
      TracePrintfExA(v17, 0xCu, "Current Thread wants to terminate itself, its fterminateASSP=1!");
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Current thread will decrease its own and global active!");
    }
    DecGlobalCallbackActive();
    ResetTerminateFlag(a1);
    ResetCallbackActive(a1);
    return 0;
  }
  if ( v17 != -1 )
    TracePrintfExA(v17, 0xCu, "Current Thread does NOT want to terminate itself,its fterminateASAP=0!");
  GlobalCallbackActive = GetGlobalCallbackActive();
  v19 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "Global active:(%d)", GlobalCallbackActive);
    v19 = g_dwTraceId;
    if ( g_dwTraceId != -1 )
    {
      v20 = GetCallbackActive(a1);
      TracePrintfExA(g_dwTraceId, 0xCu, "Current thread's active:(%d)", v20);
      v19 = g_dwTraceId;
    }
  }
  if ( !v14 )
  {
    ResetCallbackActive(a1);
    DecGlobalCallbackActive();
    v19 = g_dwTraceId;
  }
  if ( v19 != -1 )
    TracePrintfExA(v19, 0xCu, "\\DpRasDialFunc2:final dwCode returned=%d", v14);
  return v14;
}

```

## disassembly

```asm
0x18000a900  push    rbx
0x18000a902  push    rbp
0x18000a903  push    rsi
0x18000a904  push    rdi
0x18000a905  push    r12
0x18000a907  push    r13
0x18000a909  push    r14
0x18000a90b  push    r15
0x18000a90d  sub     rsp, 48h
0x18000a911  mov     r14d, [rsp+88h+arg_30]
0x18000a919  mov     rbx, rcx
0x18000a91c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a922  or      r13d, 0FFFFFFFFh
0x18000a926  mov     r15d, [rsp+88h+arg_28]
0x18000a92e  mov     esi, 0Ch
0x18000a933  mov     r12d, [rsp+88h+arg_20]
0x18000a93b  mov     edi, edx
0x18000a93d  cmp     ecx, r13d
0x18000a940  jz      short loc_18000A968
0x18000a942  mov     [rsp+88h+var_58], r14d
0x18000a947  lea     r8, aDprasdialfunc2_7; "/DpRasDialFunc2(rcs=%d,s=%d,e=%d,x=%d)"
0x18000a94e  mov     [rsp+88h+var_60], r15d
0x18000a953  mov     r9d, r12d
0x18000a956  mov     edx, esi; dwFlags
0x18000a958  mov     dword ptr [rsp+88h+var_68], edi
0x18000a95c  call    cs:__imp_TracePrintfExA
0x18000a962  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a968  test    rbx, rbx
0x18000a96b  jnz     short loc_18000A97B
0x18000a96d  cmp     ecx, r13d
0x18000a970  jz      short loc_18000A997
0x18000a972  lea     r8, aDprasdialfunc2_2; "DpRasDialFunc2(): Invalid pInfo"
0x18000a979  jmp     short loc_18000A98F
0x18000a97b  cmp     dword ptr [rbx], 0C0BBC0DEh
0x18000a981  jz      short loc_18000A99E
0x18000a983  cmp     ecx, r13d
0x18000a986  jz      short loc_18000A997
0x18000a988  lea     r8, aDprasdialfunc2_4; "DpRasDialFunc2 returns for Late callbac"...
0x18000a98f  mov     edx, esi; dwFlags
0x18000a991  call    cs:__imp_TracePrintfExA
0x18000a997  xor     eax, eax
0x18000a999  jmp     loc_18000AC40
0x18000a99e  test    edi, edi
0x18000a9a0  jz      loc_18000AC27
0x18000a9a6  cmp     edi, [rbx+58h]
0x18000a9a9  ja      loc_18000AC27
0x18000a9af  mov     rbp, [rbx+50h]
0x18000a9b3  lea     eax, [rdi-1]
0x18000a9b6  lea     rsi, [rax+rax*2]
0x18000a9ba  shl     rsi, 5
0x18000a9be  mov     [rsi+rbp+8], r14d
0x18000a9c3  mov     r14d, 0Ch
0x18000a9c9  mov     [rsi+rbp], r12d
0x18000a9cd  mov     [rsi+rbp+4], r15d
0x18000a9d2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a9d8  cmp     ecx, r13d
0x18000a9db  jz      loc_18000AA69
0x18000a9e1  mov     r9d, edi
0x18000a9e4  lea     r8, aSendRaseventTo; "Send RasEvent to Dial Progress window, "...
0x18000a9eb  mov     edx, r14d; dwFlags
0x18000a9ee  call    cs:__imp_TracePrintfExA
0x18000a9f4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a9fa  cmp     ecx, r13d
0x18000a9fd  jz      short loc_18000AA69
0x18000a9ff  mov     r9d, [rsi+rbp+4]
0x18000aa04  lea     r8, aGetDwerrorDFro; "Get dwError=(%d) from RasMan"
0x18000aa0b  mov     edx, r14d; dwFlags
0x18000aa0e  call    cs:__imp_TracePrintfExA
0x18000aa14  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000aa1a  cmp     ecx, r13d
0x18000aa1d  jz      short loc_18000AA69
0x18000aa1f  mov     rax, cs:__imp_GetCurrentThreadId
0x18000aa26  lea     r8, aDprasdialfunc2; "DpRasDialFunc2:Process:(%x),Thread(%x)"
0x18000aa2d  mov     r9, cs:__imp_GetCurrentProcessId
0x18000aa34  mov     edx, r14d; dwFlags
0x18000aa37  mov     [rsp+88h+var_68], rax
0x18000aa3c  call    cs:__imp_TracePrintfExA
0x18000aa42  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000aa48  cmp     ecx, r13d
0x18000aa4b  jz      short loc_18000AA69
0x18000aa4d  mov     rax, [rbx+10h]
0x18000aa51  lea     r8, aDprasdialfunc2_1; "DpRasDialFunc2:pInfo address (0x%x), Di"...
0x18000aa58  mov     r9, rbx
0x18000aa5b  mov     [rsp+88h+var_68], rax
0x18000aa60  mov     edx, r14d; dwFlags
0x18000aa63  call    cs:__imp_TracePrintfExA
0x18000aa69  mov     rcx, [rbx+80h]; hEvent
0x18000aa70  call    cs:__imp_ResetEvent
0x18000aa76  mov     rcx, [rbx+10h]; hWnd
0x18000aa7a  mov     r8, rdi; wParam
0x18000aa7d  xor     r9d, r9d; lParam
0x18000aa80  mov     dword ptr [rbx+88h], 0
0x18000aa8a  mov     edx, 0CCCCh; Msg
0x18000aa8f  call    cs:__imp_PostMessageW
0x18000aa95  test    eax, eax
0x18000aa97  jz      short loc_18000AACB
0x18000aa99  mov     rcx, [rbx+80h]; hHandle
0x18000aaa0  mov     edx, r13d; dwMilliseconds
0x18000aaa3  call    cs:__imp_WaitForSingleObject
0x18000aaa9  test    eax, eax
0x18000aaab  jz      short loc_18000AAC3
0x18000aaad  mov     ecx, cs:g_dwTraceId
0x18000aab3  xor     edi, edi
0x18000aab5  cmp     ecx, r13d
0x18000aab8  jz      short loc_18000AB06
0x18000aaba  lea     r8, aDprasdialfunc2_3; "\\DpRasDialFunc2: WaitForSingleObject f"...
0x18000aac1  jmp     short loc_18000AADF
0x18000aac3  mov     edi, [rbx+88h]
0x18000aac9  jmp     short loc_18000AAE8
0x18000aacb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000aad1  xor     edi, edi
0x18000aad3  cmp     ecx, r13d
0x18000aad6  jz      short loc_18000AB06
0x18000aad8  lea     r8, aDprasdialfunc2_5; "\\DpRasDialFunc2: dwCode from PostMessa"...
0x18000aadf  mov     edx, r14d; dwFlags
0x18000aae2  call    cs:__imp_TracePrintfExA
0x18000aae8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000aaee  cmp     ecx, r13d
0x18000aaf1  jz      short loc_18000AB06
0x18000aaf3  mov     r9d, edi
0x18000aaf6  lea     r8, aDwcodeReturned; "dwCode returned:(%d)"
0x18000aafd  mov     edx, r14d; dwFlags
0x18000ab00  call    cs:__imp_TracePrintfExA
0x18000ab06  mov     rcx, rbx
0x18000ab09  call    GetTerminateFlag
0x18000ab0e  mov     rcx, rbx
0x18000ab11  mov     esi, eax
0x18000ab13  call    GetCallbackActive
0x18000ab18  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000ab1e  cmp     ecx, r13d
0x18000ab21  jz      short loc_18000AB3C
0x18000ab23  mov     r9d, eax
0x18000ab26  lea     r8, aCurrentThreadS; "Current thread's active:(%d)"
0x18000ab2d  mov     edx, r14d; dwFlags
0x18000ab30  call    cs:__imp_TracePrintfExA
0x18000ab36  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000ab3c  test    esi, esi
0x18000ab3e  jz      short loc_18000AB8A
0x18000ab40  cmp     ecx, r13d
0x18000ab43  jz      short loc_18000AB70
0x18000ab45  lea     r8, aCurrentThreadW; "Current Thread wants to terminate itsel"...
0x18000ab4c  mov     edx, r14d; dwFlags
0x18000ab4f  call    cs:__imp_TracePrintfExA
0x18000ab55  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000ab5b  cmp     ecx, r13d
0x18000ab5e  jz      short loc_18000AB70
0x18000ab60  lea     r8, aCurrentThreadW_0; "Current thread will decrease its own an"...
0x18000ab67  mov     edx, r14d; dwFlags
0x18000ab6a  call    cs:__imp_TracePrintfExA
0x18000ab70  call    DecGlobalCallbackActive
0x18000ab75  mov     rcx, rbx
0x18000ab78  call    ResetTerminateFlag
0x18000ab7d  mov     rcx, rbx
0x18000ab80  call    ResetCallbackActive
0x18000ab85  jmp     loc_18000A997
0x18000ab8a  cmp     ecx, r13d
0x18000ab8d  jz      short loc_18000AB9F
0x18000ab8f  lea     r8, aCurrentThreadD; "Current Thread does NOT want to termina"...
0x18000ab96  mov     edx, r14d; dwFlags
0x18000ab99  call    cs:__imp_TracePrintfExA
0x18000ab9f  call    GetGlobalCallbackActive
0x18000aba4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000abaa  cmp     ecx, r13d
0x18000abad  jz      short loc_18000ABF4
0x18000abaf  mov     r9d, eax
0x18000abb2  lea     r8, aGlobalActiveD; "Global active:(%d)"
0x18000abb9  mov     edx, r14d; dwFlags
0x18000abbc  call    cs:__imp_TracePrintfExA
0x18000abc2  mov     ecx, cs:g_dwTraceId
0x18000abc8  cmp     ecx, r13d
0x18000abcb  jz      short loc_18000ABF4
0x18000abcd  mov     rcx, rbx
0x18000abd0  call    GetCallbackActive
0x18000abd5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000abdb  lea     r8, aCurrentThreadS; "Current thread's active:(%d)"
0x18000abe2  mov     r9d, eax
0x18000abe5  mov     edx, r14d; dwFlags
0x18000abe8  call    cs:__imp_TracePrintfExA
0x18000abee  mov     ecx, cs:g_dwTraceId
0x18000abf4  test    edi, edi
0x18000abf6  jnz     short loc_18000AC0B
0x18000abf8  mov     rcx, rbx
0x18000abfb  call    ResetCallbackActive
0x18000ac00  call    DecGlobalCallbackActive
0x18000ac05  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000ac0b  cmp     ecx, r13d
0x18000ac0e  jz      short loc_18000AC23
0x18000ac10  mov     r9d, edi
0x18000ac13  lea     r8, aDprasdialfunc2_6; "\\DpRasDialFunc2:final dwCode returned="...
0x18000ac1a  mov     edx, r14d; dwFlags
0x18000ac1d  call    cs:__imp_TracePrintfExA
0x18000ac23  mov     eax, edi
0x18000ac25  jmp     short loc_18000AC40
0x18000ac27  cmp     ecx, r13d
0x18000ac2a  jz      short loc_18000AC3B
0x18000ac2c  lea     r8, aDprasdialfunc2_0; "DpRasDialFunc2 returns for Subentry out"...
0x18000ac33  mov     edx, esi; dwFlags
0x18000ac35  call    cs:__imp_TracePrintfExA
0x18000ac3b  mov     eax, 1
0x18000ac40  add     rsp, 48h
0x18000ac44  pop     r15
0x18000ac46  pop     r14
0x18000ac48  pop     r13
0x18000ac4a  pop     r12
0x18000ac4c  pop     rdi
0x18000ac4d  pop     rsi
0x18000ac4e  pop     rbp
0x18000ac4f  pop     rbx
0x18000ac50  retn
```
