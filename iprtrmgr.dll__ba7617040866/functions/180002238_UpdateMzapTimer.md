# UpdateMzapTimer

- ea: `0x180002238`
- end: `0x1800023ee`
- name: `UpdateMzapTimer`
- size: `438`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002130`
- `0x18002f2e8`
- `0x1800325c0`
- `0x1800327ec`

## callees

- `0x180002238`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!SetWaitableTimer` at `0x180002352`
- `KERNEL32!SetWaitableTimer` at `0x180002352`
- `KERNEL32!GetLastError` at `0x18000235c`
- `KERNEL32!GetLastError` at `0x18000235c`

## string_xrefs

- `0x18000228a`: `UpdateMzapTimer`
- `0x18000236f`: `UpdateMzapTimer: Error %d setting timer`
- `0x1800023b2`: `Leaving: UpdateMzapTimer`

## pseudocode

```c
__int64 UpdateMzapTimer()
{
  LARGE_INTEGER v0; // rax
  DWORD v1; // ebx
  DWORD LastError; // eax
  LARGE_INTEGER DueTime; // [rsp+30h] [rbp-D0h] BYREF
  int v5; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v6[2044]; // [rsp+44h] [rbp-BCh] BYREF

  DueTime.QuadPart = 0;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"Entered: %ws", L"UpdateMzapTimer");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v5);
  }
  v0.QuadPart = g_liZamExpiryTime;
  v1 = 0;
  DueTime.QuadPart = g_liZamExpiryTime;
  if ( (__int64 *)g_zbrTimerList != &g_zbrTimerList && *(_QWORD *)(g_zbrTimerList + 24) < g_liZamExpiryTime )
  {
    v0 = *(LARGE_INTEGER *)(g_zbrTimerList + 24);
    DueTime = v0;
  }
  if ( (__int64 *)g_zleTimerList != &g_zleTimerList && *(_QWORD *)(g_zleTimerList + 32) < v0.QuadPart )
    DueTime = *(LARGE_INTEGER *)(g_zleTimerList + 32);
  if ( !SetWaitableTimer(g_hMzapTimer, &DueTime, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"UpdateMzapTimer: Error %d setting timer", LastError);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v5);
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: UpdateMzapTimer");
  return v1;
}

```

## disassembly

```asm
0x180002238  mov     [rsp-8+arg_0], rbx
0x18000223d  push    rbp
0x18000223e  lea     rbp, [rsp-750h]
0x180002246  sub     rsp, 850h
0x18000224d  mov     rax, cs:__security_cookie
0x180002254  xor     rax, rsp
0x180002257  mov     [rbp+750h+var_10], rax
0x18000225e  xor     eax, eax
0x180002260  mov     qword ptr [rsp+850h+DueTime], 0
0x180002269  xor     edx, edx; Val
0x18000226b  mov     [rsp+850h+var_810], eax
0x18000226f  mov     r8d, 7FCh; Size
0x180002275  lea     rcx, [rsp+850h+var_80C]; void *
0x18000227a  call    memset_0
0x18000227f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180002286  jge     short loc_1800022C8
0x180002288  xor     eax, eax
0x18000228a  lea     r8, aUpdatemzaptime_0; "UpdateMzapTimer"
0x180002291  lea     rdx, aEnteredWs; "Entered: %ws"
0x180002298  mov     word ptr [rsp+850h+var_810], ax
0x18000229d  lea     rcx, [rsp+850h+var_810]
0x1800022a2  call    FormatRRASErrorString
0x1800022a7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800022ae  jge     short loc_1800022C8
0x1800022b0  lea     r8, [rsp+850h+var_810]
0x1800022b5  lea     rdx, RasRtrmgrTraceInfo
0x1800022bc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800022c3  call    McTemplateU0z_EventWriteTransfer
0x1800022c8  mov     rcx, cs:g_zbrTimerList
0x1800022cf  lea     rdx, g_zbrTimerList
0x1800022d6  mov     rax, cs:g_liZamExpiryTime
0x1800022dd  xor     ebx, ebx
0x1800022df  mov     qword ptr [rsp+850h+DueTime], rax
0x1800022e4  cmp     rcx, rdx
0x1800022e7  jz      short loc_180002306
0x1800022e9  mov     edx, dword ptr cs:g_liZamExpiryTime+4
0x1800022ef  cmp     [rcx+1Ch], edx
0x1800022f2  jnz     short loc_1800022FB
0x1800022f4  cmp     [rcx+18h], eax
0x1800022f7  jnb     short loc_180002306
0x1800022f9  jmp     short loc_1800022FD
0x1800022fb  jge     short loc_180002306
0x1800022fd  mov     rax, [rcx+18h]
0x180002301  mov     qword ptr [rsp+850h+DueTime], rax
0x180002306  mov     rcx, cs:g_zleTimerList
0x18000230d  lea     rdx, g_zleTimerList
0x180002314  cmp     rcx, rdx
0x180002317  jz      short loc_180002337
0x180002319  mov     rdx, rax
0x18000231c  shr     rdx, 20h
0x180002320  cmp     [rcx+24h], edx
0x180002323  jnz     short loc_18000232C
0x180002325  cmp     [rcx+20h], eax
0x180002328  jnb     short loc_180002337
0x18000232a  jmp     short loc_18000232E
0x18000232c  jge     short loc_180002337
0x18000232e  mov     rax, [rcx+20h]
0x180002332  mov     qword ptr [rsp+850h+DueTime], rax
0x180002337  mov     rcx, cs:g_hMzapTimer; hTimer
0x18000233e  lea     rdx, [rsp+850h+DueTime]; lpDueTime
0x180002343  mov     [rsp+850h+fResume], ebx; fResume
0x180002347  xor     r9d, r9d; pfnCompletionRoutine
0x18000234a  xor     r8d, r8d; lPeriod
0x18000234d  mov     [rsp+850h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x180002352  call    cs:__imp_SetWaitableTimer
0x180002358  test    eax, eax
0x18000235a  jnz     short loc_1800023A9
0x18000235c  call    cs:__imp_GetLastError
0x180002362  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180002369  mov     ebx, eax
0x18000236b  jz      short loc_1800023A9
0x18000236d  xor     ecx, ecx
0x18000236f  lea     rdx, aUpdatemzaptime; "UpdateMzapTimer: Error %d setting timer"
0x180002376  mov     word ptr [rsp+850h+var_810], cx
0x18000237b  mov     r8d, eax
0x18000237e  lea     rcx, [rsp+850h+var_810]
0x180002383  call    FormatRRASErrorString
0x180002388  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000238f  jz      short loc_1800023A9
0x180002391  lea     r8, [rsp+850h+var_810]
0x180002396  lea     rdx, RasRtrMgrTraceError
0x18000239d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800023a4  call    McTemplateU0z_EventWriteTransfer
0x1800023a9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800023b0  jz      short loc_1800023CC
0x1800023b2  lea     r8, aLeavingUpdatem; "Leaving: UpdateMzapTimer"
0x1800023b9  lea     rdx, RasRtrmgrTraceInfo
0x1800023c0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800023c7  call    McTemplateU0z_EventWriteTransfer
0x1800023cc  mov     eax, ebx
0x1800023ce  mov     rcx, [rbp+750h+var_10]
0x1800023d5  xor     rcx, rsp; StackCookie
0x1800023d8  call    __security_check_cookie
0x1800023dd  mov     rbx, [rsp+850h+arg_0]
0x1800023e5  add     rsp, 850h
0x1800023ec  pop     rbp
0x1800023ed  retn
```
