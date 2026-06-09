# HNS::Service::Network::ICSNetwork::StartTimerOnEndpointNicConnected(void)

- ea: `0x18012d21c`
- end: `0x18012d36c`
- name: `?StartTimerOnEndpointNicConnected@ICSNetwork@Network@Service@HNS@@AEAA_NXZ`
- size: `336`
- prototype: `bool __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18012d8c0`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x1800663fc`
- `0x18012d21c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012d2d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012d2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d2a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012d2ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012d2ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012d2c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012d2c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012d2b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012d302`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012d2b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012d302`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012d28f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012d28f`

## string_xrefs

- `0x18012d35a`: `onecore\vm\dv\net\hns\service\entity\network\icsnetwork.cpp`

## pseudocode

```c
char __fastcall HNS::Service::Network::ICSNetwork::StartTimerOnEndpointNicConnected(_QWORD *pv)
{
  struct _TP_TIMER *v1; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v4; // r9
  struct _TP_TIMER *v5; // rbp
  DWORD LastError; // ebx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = (struct _TP_TIMER *)pv[593];
  pftDueTime = 0;
  if ( !v1 )
  {
    if ( *(_DWORD *)qword_18039A3F8 > 5u )
      tlgWriteTransfer_EventWriteTransfer(qword_18039A3F8, &unk_1803399BD, 0, 0, 2, v9);
    ThreadpoolTimer = CreateThreadpoolTimer(HNS::Service::Network::ICSNetwork::ValidateEndpointsGetIPAddress, pv, 0);
    v5 = (struct _TP_TIMER *)pv[593];
    v1 = ThreadpoolTimer;
    if ( v5 )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v5, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v5, 1);
      CloseThreadpoolTimer(v5);
      SetLastError(LastError);
    }
    pv[593] = v1;
    if ( !v1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x504,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\network\\icsnetwork.cpp",
        v4);
  }
  pftDueTime = (struct _FILETIME)-100000000LL;
  SetThreadpoolTimer(v1, &pftDueTime, 0, 0xFAu);
  if ( *(_DWORD *)qword_18039A3F8 > 5u )
    tlgWriteTransfer_EventWriteTransfer(qword_18039A3F8, &unk_180339A06, 0, 0, 2, v9);
  return 1;
}

```

## disassembly

```asm
0x18012d21c  push    rbx
0x18012d21e  push    rbp
0x18012d21f  push    rsi
0x18012d220  push    rdi
0x18012d221  sub     rsp, 68h
0x18012d225  mov     rax, cs:__security_cookie
0x18012d22c  xor     rax, rsp
0x18012d22f  mov     [rsp+88h+var_30], rax
0x18012d234  mov     rdi, [rcx+1288h]
0x18012d23b  mov     rsi, rcx
0x18012d23e  mov     qword ptr [rsp+88h+pftDueTime.dwLowDateTime], 0
0x18012d247  test    rdi, rdi
0x18012d24a  jnz     loc_18012D2E8
0x18012d250  mov     rcx, cs:qword_18039A3F8
0x18012d257  mov     eax, [rcx]
0x18012d259  cmp     eax, 5
0x18012d25c  jbe     short loc_18012D282
0x18012d25e  lea     rax, [rsp+88h+var_50]
0x18012d263  xor     r9d, r9d
0x18012d266  mov     [rsp+88h+var_60], rax
0x18012d26b  lea     rdx, unk_1803399BD
0x18012d272  xor     r8d, r8d
0x18012d275  mov     [rsp+88h+var_68], 2
0x18012d27d  call    _tlgWriteTransfer_EventWriteTransfer
0x18012d282  xor     r8d, r8d; pcbe
0x18012d285  lea     rcx, ?ValidateEndpointsGetIPAddress@ICSNetwork@Network@Service@HNS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18012d28c  mov     rdx, rsi; pv
0x18012d28f  call    cs:__imp_CreateThreadpoolTimer
0x18012d295  mov     rbp, [rsi+1288h]
0x18012d29c  mov     rdi, rax
0x18012d29f  test    rbp, rbp
0x18012d2a2  jz      short loc_18012D2DC
0x18012d2a4  call    cs:__imp_GetLastError
0x18012d2aa  xor     r9d, r9d; msWindowLength
0x18012d2ad  xor     r8d, r8d; msPeriod
0x18012d2b0  xor     edx, edx; pftDueTime
0x18012d2b2  mov     rcx, rbp; pti
0x18012d2b5  mov     ebx, eax
0x18012d2b7  call    cs:__imp_SetThreadpoolTimer
0x18012d2bd  mov     edx, 1; fCancelPendingCallbacks
0x18012d2c2  mov     rcx, rbp; pti
0x18012d2c5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18012d2cb  mov     rcx, rbp; pti
0x18012d2ce  call    cs:__imp_CloseThreadpoolTimer
0x18012d2d4  mov     ecx, ebx; dwErrCode
0x18012d2d6  call    cs:__imp_SetLastError
0x18012d2dc  mov     [rsi+1288h], rdi
0x18012d2e3  test    rdi, rdi
0x18012d2e6  jz      short loc_18012D352
0x18012d2e8  mov     r9d, 0FAh; msWindowLength
0x18012d2ee  mov     qword ptr [rsp+88h+pftDueTime.dwLowDateTime], 0FFFFFFFFFA0A1F00h
0x18012d2f7  xor     r8d, r8d; msPeriod
0x18012d2fa  lea     rdx, [rsp+88h+pftDueTime]; pftDueTime
0x18012d2ff  mov     rcx, rdi; pti
0x18012d302  call    cs:__imp_SetThreadpoolTimer
0x18012d308  mov     rcx, cs:qword_18039A3F8
0x18012d30f  mov     eax, [rcx]
0x18012d311  cmp     eax, 5
0x18012d314  jbe     short loc_18012D33A
0x18012d316  lea     rdx, [rsp+88h+var_50]
0x18012d31b  xor     r9d, r9d
0x18012d31e  mov     [rsp+88h+var_60], rdx
0x18012d323  xor     r8d, r8d
0x18012d326  lea     rdx, unk_180339A06
0x18012d32d  mov     [rsp+88h+var_68], 2
0x18012d335  call    _tlgWriteTransfer_EventWriteTransfer
0x18012d33a  mov     al, 1
0x18012d33c  mov     rcx, [rsp+88h+var_30]
0x18012d341  xor     rcx, rsp; StackCookie
0x18012d344  call    __security_check_cookie
0x18012d349  add     rsp, 68h
0x18012d34d  pop     rdi
0x18012d34e  pop     rsi
0x18012d34f  pop     rbp
0x18012d350  pop     rbx
0x18012d351  retn
0x18012d352  mov     rcx, [rsp+88h]; this
0x18012d35a  lea     r8, aOnecoreVmDvNet_175; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x18012d361  mov     edx, 504h; void *
0x18012d366  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
