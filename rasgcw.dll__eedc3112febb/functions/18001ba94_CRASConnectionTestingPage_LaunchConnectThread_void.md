# CRASConnectionTestingPage::LaunchConnectThread(void)

- ea: `0x18001ba94`
- end: `0x18001bc38`
- name: `?LaunchConnectThread@CRASConnectionTestingPage@@IEAAHXZ`
- size: `420`
- prototype: `__int64 __fastcall(CRASConnectionTestingPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bc90`

## callees

- `0x1800114d8`
- `0x18001b880`
- `0x18001ba94`
- `0x18002b970`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb9a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001bb84`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001bb84`
- `USER32!PostMessageW` at `0x18001bb59`
- `USER32!PostMessageW` at `0x18001bb59`
- `USER32!GetParent` at `0x18001bb44`
- `USER32!GetParent` at `0x18001bb44`
- `rtutils!TracePrintfExA` at `0x18001baed`
- `rtutils!TracePrintfExA` at `0x18001bb3a`
- `rtutils!TracePrintfExA` at `0x18001bbc9`
- `rtutils!TracePrintfExA` at `0x18001baed`
- `rtutils!TracePrintfExA` at `0x18001bb3a`
- `rtutils!TracePrintfExA` at `0x18001bbc9`

## string_xrefs

- `0x18001bac3`: `LaunchConnectThread is already running. This is invalid state.`
- `0x18001bb2e`: `LaunchConnectThread: Skipping the connection test and Going to next page`
- `0x18001bbbd`: `LaunchConnectThread:Failed to start testing thread. Error = hr = %#x`

## pseudocode

```c
__int64 __fastcall CRASConnectionTestingPage::LaunchConnectThread(CRASConnectionTestingPage *this)
{
  bool v1; // zf
  struct _RASNCWINFO *RASConnectionPropertiesFromPropertyBag; // rax
  HWND Parent; // rax
  HANDLE v6; // rax
  signed int LastError; // eax
  unsigned int v8; // esi
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, _QWORD, __int64, _QWORD); // rbx
  __int64 StringPcch; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  int v13; // [rsp+48h] [rbp+10h]

  v1 = *((_QWORD *)this + 142) == 0;
  ThreadId = 0;
  if ( !v1 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "LaunchConnectThread is already running. This is invalid state.");
    return 0;
  }
  RASConnectionPropertiesFromPropertyBag = CRASConnectionTestingPage::GetRASConnectionPropertiesFromPropertyBag(this);
  if ( !RASConnectionPropertiesFromPropertyBag )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unable to get RAS connection properties bag.");
    return 0;
  }
  *((_QWORD *)this + 141) = 0;
  if ( *((_DWORD *)RASConnectionPropertiesFromPropertyBag + 453) )
  {
    *((_DWORD *)this + 283) = 1;
    *((_QWORD *)this + 142) = 0;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "LaunchConnectThread: Skipping the connection test and Going to next page");
    Parent = GetParent(*((HWND *)this + 1));
    PostMessageW(Parent, 0x471u, 1u, 0);
  }
  else
  {
    v6 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CRASConnectionTestingPage::ConnectThread, this, 0, &ThreadId);
    *((_QWORD *)this + 142) = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "LaunchConnectThread:Failed to start testing thread. Error = hr = %#x", v8);
      if ( (int)HrEnsureTearOffInterfaceLoaded(*((_QWORD *)this + 9), &IID_IXWizardPageReport, (char *)this + 64) >= 0 )
      {
        v9 = *((_QWORD *)this + 8);
        v13 = 0;
        v10 = *(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v9 + 24LL);
        StringPcch = PszLoadStringPcch(qword_18004D9B0);
        v10(v9, v8, StringPcch, 0);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001ba94  mov     [rsp+arg_10], rbx
0x18001ba99  mov     [rsp+arg_18], rsi
0x18001ba9e  push    rdi
0x18001ba9f  sub     rsp, 30h
0x18001baa3  cmp     qword ptr [rcx+470h], 0
0x18001baab  mov     rbx, rcx
0x18001baae  mov     [rsp+38h+ThreadId], 0
0x18001bab6  jz      short loc_18001BACC
0x18001bab8  mov     ecx, cs:g_dwTraceId; this
0x18001babe  cmp     ecx, 0FFFFFFFFh
0x18001bac1  jz      short loc_18001BAF3
0x18001bac3  lea     r8, aLaunchconnectt; "LaunchConnectThread is already running."...
0x18001baca  jmp     short loc_18001BAE8
0x18001bacc  call    ?GetRASConnectionPropertiesFromPropertyBag@CRASConnectionTestingPage@@IEAAPEAU_RASNCWINFO@@XZ; CRASConnectionTestingPage::GetRASConnectionPropertiesFromPropertyBag(void)
0x18001bad1  test    rax, rax
0x18001bad4  jnz     short loc_18001BAFA
0x18001bad6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001badc  cmp     ecx, 0FFFFFFFFh
0x18001badf  jz      short loc_18001BAF3
0x18001bae1  lea     r8, aUnableToGetRas; "Unable to get RAS connection properties"...
0x18001bae8  mov     edx, 0Ch; dwFlags
0x18001baed  call    cs:__imp_TracePrintfExA
0x18001baf3  xor     eax, eax
0x18001baf5  jmp     loc_18001BC28
0x18001bafa  mov     qword ptr [rbx+468h], 0
0x18001bb05  cmp     dword ptr [rax+714h], 0
0x18001bb0c  jz      short loc_18001BB64
0x18001bb0e  mov     dword ptr [rbx+46Ch], 1
0x18001bb18  mov     qword ptr [rbx+470h], 0
0x18001bb23  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001bb29  cmp     ecx, 0FFFFFFFFh
0x18001bb2c  jz      short loc_18001BB40
0x18001bb2e  lea     r8, aLaunchconnectt_0; "LaunchConnectThread: Skipping the conne"...
0x18001bb35  mov     edx, 0Ch; dwFlags
0x18001bb3a  call    cs:__imp_TracePrintfExA
0x18001bb40  mov     rcx, [rbx+8]; hWnd
0x18001bb44  call    cs:__imp_GetParent
0x18001bb4a  xor     r9d, r9d; lParam
0x18001bb4d  mov     edx, 471h; Msg
0x18001bb52  mov     rcx, rax; hWnd
0x18001bb55  lea     r8d, [r9+1]; wParam
0x18001bb59  call    cs:__imp_PostMessageW
0x18001bb5f  jmp     loc_18001BC23
0x18001bb64  lea     rax, [rsp+38h+ThreadId]
0x18001bb69  mov     r9, rbx; lpParameter
0x18001bb6c  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001bb71  lea     r8, ?ConnectThread@CRASConnectionTestingPage@@KAP6AKPEAX@ZPEAV1@@Z; lpStartAddress
0x18001bb78  xor     edx, edx; dwStackSize
0x18001bb7a  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001bb82  xor     ecx, ecx; lpThreadAttributes
0x18001bb84  call    cs:__imp_CreateThread
0x18001bb8a  mov     [rbx+470h], rax
0x18001bb91  test    rax, rax
0x18001bb94  jnz     loc_18001BC23
0x18001bb9a  call    cs:__imp_GetLastError
0x18001bba0  mov     esi, eax
0x18001bba2  test    eax, eax
0x18001bba4  jle     short loc_18001BBAF
0x18001bba6  movzx   esi, ax
0x18001bba9  or      esi, 80070000h
0x18001bbaf  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001bbb5  cmp     ecx, 0FFFFFFFFh
0x18001bbb8  jz      short loc_18001BBCF
0x18001bbba  mov     r9d, esi
0x18001bbbd  lea     r8, aLaunchconnectt_1; "LaunchConnectThread:Failed to start tes"...
0x18001bbc4  mov     edx, 0Ch; dwFlags
0x18001bbc9  call    cs:__imp_TracePrintfExA
0x18001bbcf  mov     rcx, [rbx+48h]
0x18001bbd3  lea     r8, [rbx+40h]
0x18001bbd7  lea     rdx, IID_IXWizardPageReport
0x18001bbde  call    HrEnsureTearOffInterfaceLoaded
0x18001bbe3  test    eax, eax
0x18001bbe5  js      short loc_18001BC23
0x18001bbe7  mov     rdi, [rbx+40h]
0x18001bbeb  lea     r8, [rsp+38h+arg_8]
0x18001bbf0  mov     rcx, cs:qword_18004D9B0; hModule
0x18001bbf7  mov     edx, 0C03h
0x18001bbfc  mov     [rsp+38h+arg_8], 0
0x18001bc04  mov     rax, [rdi]
0x18001bc07  mov     rbx, [rax+18h]
0x18001bc0b  call    PszLoadStringPcch
0x18001bc10  mov     r8, rax
0x18001bc13  xor     r9d, r9d
0x18001bc16  mov     rax, rbx
0x18001bc19  mov     edx, esi
0x18001bc1b  mov     rcx, rdi
0x18001bc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc23  mov     eax, 1
0x18001bc28  mov     rbx, [rsp+38h+arg_10]
0x18001bc2d  mov     rsi, [rsp+38h+arg_18]
0x18001bc32  add     rsp, 30h
0x18001bc36  pop     rdi
0x18001bc37  retn
```
