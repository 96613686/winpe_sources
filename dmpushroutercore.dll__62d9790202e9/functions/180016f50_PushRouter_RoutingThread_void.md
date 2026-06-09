# PushRouter::RoutingThread(void *)

- ea: `0x180016f50`
- end: `0x18001724f`
- name: `?RoutingThread@PushRouter@@CAKPEAX@Z`
- size: `767`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001464`
- `0x1800039f0`
- `0x1800138e8`
- `0x180014c88`
- `0x180016c04`
- `0x180016f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017129`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017129`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017106`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017106`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800171d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800171d7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016fea`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016fff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001714c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017208`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016fea`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016fff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001714c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017208`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800171c5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800171c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016f98`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016f98`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800170ca`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800170ca`

## pseudocode

```c
__int64 __fastcall PushRouter::RoutingThread(PVOID Parameter)
{
  int v2; // r14d
  int v3; // ebx
  GUID *v4; // r9
  DWORD v5; // esi
  DWORD v6; // eax
  signed int LastError; // eax
  unsigned int v9; // [rsp+30h] [rbp-69h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-61h] BYREF
  int v11; // [rsp+48h] [rbp-51h]
  char v12; // [rsp+4Ch] [rbp-4Dh]
  GUID ActivityId; // [rsp+50h] [rbp-49h] BYREF
  GUID v14; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp-29h] BYREF
  unsigned int *v16; // [rsp+90h] [rbp-9h]
  __int64 v17; // [rsp+98h] [rbp-1h]
  _BYTE v18[32]; // [rsp+A0h] [rbp+7h] BYREF

  *(_OWORD *)Handles = 0;
  v2 = 0;
  v11 = 0;
  v12 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 >= 0 )
  {
    v2 = 1;
    if ( (unsigned int)dword_180050060 > 5
      && (qword_180050070 & 0x200000000000LL) != 0
      && (qword_180050078 & 0x200000000000LL) == qword_180050078 )
    {
      EventActivityIdControl(3u, &ActivityId);
      v14 = ActivityId;
      EventActivityIdControl(4u, &v14);
      v12 = 1;
    }
    else
    {
      ActivityId = 0;
    }
    v11 = 1;
    if ( (unsigned int)dword_180050060 > 5
      && (qword_180050070 & 0x200000000000LL) != 0
      && (qword_180050078 & 0x200000000000LL) == qword_180050078 )
    {
      if ( v12 && (v14.Data1 || *(_DWORD *)&v14.Data2 || *(_DWORD *)v14.Data4 || *(_DWORD *)&v14.Data4[4]) )
        v4 = &v14;
      else
        v4 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_180050060, &byte_18004657F, &ActivityId, v4, 2, v18);
    }
    if ( Parameter )
    {
      Handles[0] = *((HANDLE *)Parameter + 22);
      Handles[1] = *((HANDLE *)Parameter + 25);
LABEL_21:
      v5 = 5000;
      while ( 1 )
      {
        v6 = WaitForMultipleObjects(2u, Handles, 0, v5);
        if ( v6 == 1 )
          break;
        if ( v6 == 258 )
        {
          EnterCriticalSection(*((LPCRITICAL_SECTION *)Parameter + 33));
          v3 = PushRouter::HousekeepClientList((PushRouter *)Parameter);
          if ( v3 >= 0 && !*((_DWORD *)Parameter + 12) )
            v5 = -1;
          LeaveCriticalSection(*((LPCRITICAL_SECTION *)Parameter + 33));
        }
        else if ( v6 != -1 )
        {
          v9 = 0;
          v3 = PushRouter::RouteNewMessages((PushRouter *)Parameter, &v9);
          if ( v3 >= 0 )
          {
            if ( v9 )
              goto LABEL_21;
          }
        }
      }
    }
    else
    {
      v3 = -2147418113;
    }
  }
  if ( v12 )
    EventActivityIdControl(4u, &v14);
  v11 = 2;
  if ( (unsigned int)dword_180050060 > 5
    && (qword_180050070 & 0x200000000000LL) != 0
    && (qword_180050078 & 0x200000000000LL) == qword_180050078 )
  {
    v9 = v3;
    v16 = &v9;
    v17 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180050060, word_180046552, &ActivityId, 0, 3, v15);
  }
  if ( v2 )
    CoUninitialize();
  if ( g_hevtShutdownComplete )
  {
    if ( !SetEvent(g_hevtShutdownComplete) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v11 == 1 )
  {
    if ( v12 )
      EventActivityIdControl(4u, &v14);
    v11 = 2;
    _tlgWriteActivityAutoStop<35184372088832,5>((unsigned int *)&dword_180050060, (__int64)&ActivityId);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016f50  mov     [rsp-8+arg_8], rbx
0x180016f55  mov     [rsp-8+arg_10], rsi
0x180016f5a  push    rbp
0x180016f5b  push    rdi
0x180016f5c  push    r12
0x180016f5e  push    r14
0x180016f60  push    r15
0x180016f62  lea     rbp, [rsp-37h]
0x180016f67  sub     rsp, 0D0h
0x180016f6e  mov     rax, cs:__security_cookie
0x180016f75  xor     rax, rsp
0x180016f78  mov     [rbp+57h+var_30], rax
0x180016f7c  mov     rdi, rcx
0x180016f7f  xorps   xmm0, xmm0
0x180016f82  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x180016f86  xor     r15d, r15d
0x180016f89  mov     r14d, r15d
0x180016f8c  mov     [rbp+57h+var_A8], r15d
0x180016f90  mov     [rbp+57h+var_A4], r15b
0x180016f94  xor     edx, edx; dwCoInit
0x180016f96  xor     ecx, ecx; pvReserved
0x180016f98  call    cs:__imp_CoInitializeEx
0x180016f9e  mov     ebx, eax
0x180016fa0  lea     esi, [r15+4]
0x180016fa4  mov     r12, 200000000000h
0x180016fae  test    eax, eax
0x180016fb0  js      loc_180017140
0x180016fb6  lea     r14d, [r15+1]
0x180016fba  mov     ecx, cs:dword_180050060
0x180016fc0  cmp     ecx, 5
0x180016fc3  jbe     short loc_18001700B
0x180016fc5  mov     rcx, cs:qword_180050078
0x180016fcc  mov     rax, cs:qword_180050070
0x180016fd3  test    r12, rax
0x180016fd6  jz      short loc_18001700B
0x180016fd8  mov     rax, rcx
0x180016fdb  and     rax, r12
0x180016fde  cmp     rax, rcx
0x180016fe1  jnz     short loc_18001700B
0x180016fe3  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180016fe7  lea     ecx, [rsi-1]; ControlCode
0x180016fea  call    cs:__imp_EventActivityIdControl
0x180016ff0  movups  xmm0, xmmword ptr [rbp+57h+ActivityId.Data1]
0x180016ff4  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180016ff9  lea     rdx, [rbp+57h+var_90]; ActivityId
0x180016ffd  mov     ecx, esi; ControlCode
0x180016fff  call    cs:__imp_EventActivityIdControl
0x180017005  mov     [rbp+57h+var_A4], r14b
0x180017009  jmp     short loc_180017012
0x18001700b  xorps   xmm0, xmm0
0x18001700e  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180017012  mov     [rbp+57h+var_A8], r14d
0x180017016  mov     eax, cs:dword_180050060
0x18001701c  cmp     eax, 5
0x18001701f  jbe     short loc_18001708E
0x180017021  mov     rcx, cs:qword_180050078
0x180017028  mov     rax, cs:qword_180050070
0x18001702f  test    r12, rax
0x180017032  jz      short loc_18001708E
0x180017034  mov     rax, rcx
0x180017037  and     rax, r12
0x18001703a  cmp     rax, rcx
0x18001703d  jnz     short loc_18001708E
0x18001703f  cmp     [rbp+57h+var_A4], r15b
0x180017043  jz      short loc_180017063
0x180017045  cmp     [rbp+57h+var_90.Data1], r15d
0x180017049  jnz     short loc_18001705D
0x18001704b  cmp     dword ptr [rbp+57h+var_90.Data2], r15d
0x18001704f  jnz     short loc_18001705D
0x180017051  cmp     dword ptr [rbp+57h+var_90.Data4], r15d
0x180017055  jnz     short loc_18001705D
0x180017057  cmp     dword ptr [rbp+57h+var_90.Data4+4], r15d
0x18001705b  jz      short loc_180017063
0x18001705d  lea     r9, [rbp+57h+var_90]
0x180017061  jmp     short loc_180017066
0x180017063  mov     r9, r15
0x180017066  lea     rax, [rbp+57h+var_50]
0x18001706a  mov     [rsp+0F0h+var_C8], rax
0x18001706f  mov     [rsp+0F0h+var_D0], 2
0x180017077  lea     r8, [rbp+57h+ActivityId]
0x18001707b  lea     rdx, byte_18004657F
0x180017082  lea     rcx, dword_180050060
0x180017089  call    _tlgWriteTransfer_EventWriteTransfer
0x18001708e  test    rdi, rdi
0x180017091  jnz     short loc_18001709D
0x180017093  mov     ebx, 8000FFFFh
0x180017098  jmp     loc_180017140
0x18001709d  mov     rax, [rdi+0B0h]
0x1800170a4  mov     [rbp+57h+Handles], rax
0x1800170a8  mov     rax, [rdi+0C8h]
0x1800170af  mov     [rbp+57h+Handles+8], rax
0x1800170b3  or      r12d, 0FFFFFFFFh
0x1800170b7  mov     esi, 1388h
0x1800170bc  mov     r9d, esi; dwMilliseconds
0x1800170bf  xor     r8d, r8d; bWaitAll
0x1800170c2  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800170c6  lea     ecx, [r8+2]; nCount
0x1800170ca  call    cs:__imp_WaitForMultipleObjects
0x1800170d0  cmp     eax, r14d
0x1800170d3  jz      short loc_180017131
0x1800170d5  cmp     eax, 102h
0x1800170da  jz      short loc_1800170FF
0x1800170dc  cmp     eax, r12d
0x1800170df  jz      short loc_1800170BC
0x1800170e1  mov     [rbp+57h+var_C0], r15d
0x1800170e5  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x1800170e9  mov     rcx, rdi; this
0x1800170ec  call    ?RouteNewMessages@PushRouter@@AEAAJPEAK@Z; PushRouter::RouteNewMessages(ulong *)
0x1800170f1  mov     ebx, eax
0x1800170f3  test    eax, eax
0x1800170f5  js      short loc_1800170BC
0x1800170f7  cmp     [rbp+57h+var_C0], r15d
0x1800170fb  jz      short loc_1800170BC
0x1800170fd  jmp     short loc_1800170B7
0x1800170ff  mov     rcx, [rdi+108h]; lpCriticalSection
0x180017106  call    cs:__imp_EnterCriticalSection
0x18001710c  mov     rcx, rdi; this
0x18001710f  call    ?HousekeepClientList@PushRouter@@AEAAJXZ; PushRouter::HousekeepClientList(void)
0x180017114  mov     ebx, eax
0x180017116  test    eax, eax
0x180017118  js      short loc_180017122
0x18001711a  cmp     [rdi+30h], r15d
0x18001711e  cmovz   esi, r12d
0x180017122  mov     rcx, [rdi+108h]; lpCriticalSection
0x180017129  call    cs:__imp_LeaveCriticalSection
0x18001712f  jmp     short loc_1800170BC
0x180017131  mov     esi, 4
0x180017136  mov     r12, 200000000000h
0x180017140  cmp     [rbp+57h+var_A4], r15b
0x180017144  jz      short loc_180017152
0x180017146  lea     rdx, [rbp+57h+var_90]; ActivityId
0x18001714a  mov     ecx, esi; ControlCode
0x18001714c  call    cs:__imp_EventActivityIdControl
0x180017152  mov     [rbp+57h+var_A8], 2
0x180017159  mov     eax, cs:dword_180050060
0x18001715f  cmp     eax, 5
0x180017162  jbe     short loc_1800171C0
0x180017164  mov     rcx, cs:qword_180050078
0x18001716b  mov     rax, cs:qword_180050070
0x180017172  test    r12, rax
0x180017175  jz      short loc_1800171C0
0x180017177  mov     rax, rcx
0x18001717a  and     rax, r12
0x18001717d  cmp     rax, rcx
0x180017180  jnz     short loc_1800171C0
0x180017182  mov     [rbp+57h+var_C0], ebx
0x180017185  lea     rax, [rbp+57h+var_C0]
0x180017189  mov     [rbp+57h+var_60], rax
0x18001718d  mov     [rbp+57h+var_58], 4
0x180017195  lea     rax, [rbp+57h+var_80]
0x180017199  mov     [rsp+0F0h+var_C8], rax
0x18001719e  mov     [rsp+0F0h+var_D0], 3
0x1800171a6  xor     r9d, r9d
0x1800171a9  lea     r8, [rbp+57h+ActivityId]
0x1800171ad  lea     rdx, word_180046552
0x1800171b4  lea     rcx, dword_180050060
0x1800171bb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800171c0  test    r14d, r14d
0x1800171c3  jz      short loc_1800171CB
0x1800171c5  call    cs:__imp_CoUninitialize
0x1800171cb  mov     rcx, cs:?g_hevtShutdownComplete@@3PEAXEA; hEvent
0x1800171d2  test    rcx, rcx
0x1800171d5  jz      short loc_1800171F6
0x1800171d7  call    cs:__imp_SetEvent
0x1800171dd  test    eax, eax
0x1800171df  jnz     short loc_1800171F6
0x1800171e1  call    cs:__imp_GetLastError
0x1800171e7  mov     ebx, eax
0x1800171e9  test    eax, eax
0x1800171eb  jle     short loc_1800171F6
0x1800171ed  movzx   ebx, ax
0x1800171f0  or      ebx, 80070000h
0x1800171f6  cmp     [rbp+57h+var_A8], 1
0x1800171fa  jnz     short loc_180017225
0x1800171fc  cmp     [rbp+57h+var_A4], r15b
0x180017200  jz      short loc_18001720E
0x180017202  lea     rdx, [rbp+57h+var_90]; ActivityId
0x180017206  mov     ecx, esi; ControlCode
0x180017208  call    cs:__imp_EventActivityIdControl
0x18001720e  mov     [rbp+57h+var_A8], 2
0x180017215  lea     rdx, [rbp+57h+ActivityId]
0x180017219  lea     rcx, dword_180050060
0x180017220  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x180017225  mov     eax, ebx
0x180017227  mov     rcx, [rbp+57h+var_30]
0x18001722b  xor     rcx, rsp; StackCookie
0x18001722e  call    __security_check_cookie
0x180017233  lea     r11, [rsp+0F0h+var_20]
0x18001723b  mov     rbx, [r11+38h]
0x18001723f  mov     rsi, [r11+40h]
0x180017243  mov     rsp, r11
0x180017246  pop     r15
0x180017248  pop     r14
0x18001724a  pop     r12
0x18001724c  pop     rdi
0x18001724d  pop     rbp
0x18001724e  retn
```
