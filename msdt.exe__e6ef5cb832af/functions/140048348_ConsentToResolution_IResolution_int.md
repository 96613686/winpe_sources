# ConsentToResolution(IResolution *,int *)

- ea: `0x140048348`
- end: `0x1400484ff`
- name: `?ConsentToResolution@@YAJPEAVIResolution@@PEAH@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct IResolution *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x14004c2ac`

## callees

- `0x14001ccc0`
- `0x140020420`
- `0x14003ea28`
- `0x140048348`
- `0x14004ef0c`
- `0x14004f1a0`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400484c0`
- `KERNEL32!GetLastError` at `0x1400484c0`
- `KERNEL32!SetEvent` at `0x1400484ac`
- `KERNEL32!SetEvent` at `0x1400484ac`
- `KERNEL32!WaitForMultipleObjects` at `0x140048471`
- `KERNEL32!WaitForMultipleObjects` at `0x140048471`
- `USER32!PostMessageW` at `0x140048453`
- `USER32!PostMessageW` at `0x140048453`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140048439`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140048439`

## pseudocode

```c
__int64 __fastcall ConsentToResolution(struct IResolution *a1, int *a2)
{
  unsigned int v2; // ebx
  int v5; // eax
  int v6; // r9d
  int v7; // edi
  int v8; // eax
  HWND ParentHWND; // rax
  DWORD v10; // eax
  DWORD v11; // eax
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-38h]
  struct PageManager *v15; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v15 = 0;
  if ( !(unsigned int)Resolution_GetRequiresConsent(a1) )
  {
    *a2 = 1;
    return v2;
  }
  if ( *a2 )
    return v2;
  if ( !(unsigned int)Resolution_GetConsentProvided(a1) && !*((_DWORD *)Config + 10) )
  {
    *a2 = 0;
    return v2;
  }
  v5 = WaitForProgressPage();
  v2 = v5;
  if ( v5 < 0 )
  {
    v14 = v5;
    v6 = 1891;
LABEL_9:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ConsentToResolution", v6, v14);
    return v2;
  }
  v7 = 1;
  if ( v5 == 1 )
    return v2;
  v8 = PageManager::Instance(&v15);
  v2 = v8;
  if ( v8 < 0 )
  {
    v14 = v8;
    v6 = 1903;
    goto LABEL_9;
  }
  if ( a1 )
  {
    (*(void (__fastcall **)(struct IResolution *))(*(_QWORD *)a1 + 8LL))(a1);
    ParentHWND = DirectUI::TaskPage::GetParentHWND(*((DirectUI::TaskPage **)v15 + 1));
    PostMessageW(ParentHWND, 0x9E0u, 0, (LPARAM)a1);
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::Consent", 595, -2147024809);
  }
  v10 = WaitForMultipleObjects(0x1Cu, &g_EventsToWorker, 0, 0xFFFFFFFF) - 9;
  if ( !v10 )
  {
LABEL_27:
    *a2 = v7;
    return v2;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v7 = 0;
    goto LABEL_27;
  }
  if ( v11 != 17 )
  {
    v2 = -2147024809;
    v6 = 1934;
    v14 = -2147024809;
    goto LABEL_9;
  }
  g_Stop = 1;
  if ( SetEvent(qword_140080088) )
    return 0;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
  {
    v14 = v2;
    v6 = 1928;
    goto LABEL_9;
  }
  return v2;
}

```

## disassembly

```asm
0x140048348  push    rbx
0x14004834a  push    rsi
0x14004834b  push    rdi
0x14004834c  push    r14
0x14004834e  sub     rsp, 38h
0x140048352  xor     ebx, ebx
0x140048354  mov     rsi, rdx
0x140048357  mov     [rsp+58h+arg_10], rbx
0x14004835c  mov     r14, rcx
0x14004835f  call    ?Resolution_GetRequiresConsent@@YAHPEAVIResolution@@@Z; Resolution_GetRequiresConsent(IResolution *)
0x140048364  test    eax, eax
0x140048366  jnz     short loc_140048373
0x140048368  mov     dword ptr [rsi], 1
0x14004836e  jmp     loc_1400484F2
0x140048373  cmp     [rsi], ebx
0x140048375  jnz     loc_1400484F2
0x14004837b  mov     rcx, r14; struct IResolution *
0x14004837e  call    ?Resolution_GetConsentProvided@@YAHPEAVIResolution@@@Z; Resolution_GetConsentProvided(IResolution *)
0x140048383  test    eax, eax
0x140048385  jnz     short loc_14004839A
0x140048387  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14004838e  cmp     [rax+28h], ebx
0x140048391  jnz     short loc_14004839A
0x140048393  mov     [rsi], ebx
0x140048395  jmp     loc_1400484F2
0x14004839a  call    ?WaitForProgressPage@@YAJXZ; WaitForProgressPage(void)
0x14004839f  mov     ebx, eax
0x1400483a1  test    eax, eax
0x1400483a3  jns     short loc_1400483CC
0x1400483a5  mov     [rsp+58h+var_38], eax
0x1400483a9  mov     r9d, 763h
0x1400483af  mov     ecx, 1; Level
0x1400483b4  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400483bb  lea     r8, aConsenttoresol; "ConsentToResolution"
0x1400483c2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400483c7  jmp     loc_1400484F2
0x1400483cc  mov     edi, 1
0x1400483d1  cmp     eax, edi
0x1400483d3  jz      loc_1400484F2
0x1400483d9  lea     rcx, [rsp+58h+arg_10]; struct PageManager **
0x1400483de  call    ?Instance@PageManager@@SAJPEAPEAV1@@Z; PageManager::Instance(PageManager * *)
0x1400483e3  mov     ebx, eax
0x1400483e5  test    eax, eax
0x1400483e7  jns     short loc_1400483F7
0x1400483e9  mov     [rsp+58h+var_38], eax
0x1400483ed  mov     r9d, 76Fh
0x1400483f3  mov     ecx, edi
0x1400483f5  jmp     short loc_1400483B4
0x1400483f7  test    r14, r14
0x1400483fa  jnz     short loc_140048421
0x1400483fc  mov     r9d, 253h
0x140048402  mov     [rsp+58h+var_38], 80070057h
0x14004840a  lea     r8, aPagemanagerCon; "PageManager::Consent"
0x140048411  mov     ecx, edi; Level
0x140048413  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004841a  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004841f  jmp     short loc_14004845F
0x140048421  mov     rax, [r14]
0x140048424  mov     rcx, r14
0x140048427  mov     rax, [rax+8]
0x14004842b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048430  mov     rcx, [rsp+58h+arg_10]
0x140048435  mov     rcx, [rcx+8]
0x140048439  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x140048440  nop     dword ptr [rax+rax+00h]
0x140048445  mov     r9, r14; lParam
0x140048448  xor     r8d, r8d; wParam
0x14004844b  mov     rcx, rax; hWnd
0x14004844e  mov     edx, 9E0h; Msg
0x140048453  call    cs:__imp_PostMessageW
0x14004845a  nop     dword ptr [rax+rax+00h]
0x14004845f  xor     r8d, r8d; bWaitAll
0x140048462  lea     rdx, ?g_EventsToWorker@@3PAPEAXA; lpHandles
0x140048469  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14004846d  lea     ecx, [r8+1Ch]; nCount
0x140048471  call    cs:__imp_WaitForMultipleObjects
0x140048478  nop     dword ptr [rax+rax+00h]
0x14004847d  sub     eax, 9
0x140048480  jz      short loc_1400484F0
0x140048482  sub     eax, edi
0x140048484  jz      short loc_1400484EE
0x140048486  cmp     eax, 11h
0x140048489  jz      short loc_14004849F
0x14004848b  mov     ebx, 80070057h
0x140048490  mov     r9d, 78Eh
0x140048496  mov     [rsp+58h+var_38], ebx
0x14004849a  jmp     loc_1400483F3
0x14004849f  mov     rcx, cs:qword_140080088; hEvent
0x1400484a6  mov     cs:?g_Stop@@3HA, edi; int g_Stop
0x1400484ac  call    cs:__imp_SetEvent
0x1400484b3  nop     dword ptr [rax+rax+00h]
0x1400484b8  test    eax, eax
0x1400484ba  jz      short loc_1400484C0
0x1400484bc  xor     ebx, ebx
0x1400484be  jmp     short loc_1400484F2
0x1400484c0  call    cs:__imp_GetLastError
0x1400484c7  nop     dword ptr [rax+rax+00h]
0x1400484cc  mov     ebx, eax
0x1400484ce  test    eax, eax
0x1400484d0  jle     short loc_1400484DB
0x1400484d2  movzx   ebx, ax
0x1400484d5  or      ebx, 80070000h
0x1400484db  test    ebx, ebx
0x1400484dd  jns     short loc_1400484F2
0x1400484df  mov     [rsp+58h+var_38], ebx
0x1400484e3  mov     r9d, 788h
0x1400484e9  jmp     loc_1400483F3
0x1400484ee  xor     edi, edi
0x1400484f0  mov     [rsi], edi
0x1400484f2  mov     eax, ebx
0x1400484f4  add     rsp, 38h
0x1400484f8  pop     r14
0x1400484fa  pop     rdi
0x1400484fb  pop     rsi
0x1400484fc  pop     rbx
0x1400484fd  retn
```
