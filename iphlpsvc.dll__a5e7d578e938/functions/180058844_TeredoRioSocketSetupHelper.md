# TeredoRioSocketSetupHelper

- ea: `0x180058844`
- end: `0x1800589ef`
- name: `TeredoRioSocketSetupHelper`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800562a0`
- `0x180056c38`

## callees

- `0x180008210`
- `0x18000d7c0`
- `0x180057878`
- `0x180058844`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800588a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800588a7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005899b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800589ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800589bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005899b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800589ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800589bf`
- `WS2_32!__imp_WSAGetLastError` at `0x1800588bf`
- `WS2_32!__imp_WSAGetLastError` at `0x18005891f`
- `WS2_32!__imp_WSAGetLastError` at `0x180058976`
- `WS2_32!__imp_WSAGetLastError` at `0x1800588bf`
- `WS2_32!__imp_WSAGetLastError` at `0x18005891f`
- `WS2_32!__imp_WSAGetLastError` at `0x180058976`

## string_xrefs

- `0x1800588cb`: `DeviceSetupHelper Create CQ Notify Event failed with status %u`
- `0x18005892b`: `DeviceSetupHelper Create CQ failed with status %u`
- `0x180058982`: `DeviceSetupHelper Create RQ failed with status %u`

## pseudocode

```c
__int64 __fastcall TeredoRioSocketSetupHelper(__int64 **a1, unsigned int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int MaxReceiveCount; // ebx
  unsigned int v8; // ebp
  __int64 *EventW; // rax
  unsigned int Error; // eax
  const wchar_t *v11; // rdx
  unsigned int v12; // ebx
  __int64 (__fastcall *v13)(_QWORD, _QWORD *); // rax
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD v17[2]; // [rsp+50h] [rbp-48h] BYREF
  int v18; // [rsp+60h] [rbp-38h]
  __int64 v19; // [rsp+64h] [rbp-34h]

  v4 = **a1;
  EventWriteEnterEx(0x100000, L"TeredoRioSocketSetupHelper");
  MaxReceiveCount = TeredoRioGetMaxReceiveCount(v4 + 2768, a2);
  if ( a2 )
  {
    if ( a2 == 1 )
      MaxReceiveCount += *(_DWORD *)(v4 + 2892);
  }
  else
  {
    MaxReceiveCount += *(_DWORD *)(v4 + 2900);
  }
  v8 = TeredoRioGetMaxReceiveCount(v6, v5);
  EventW = (__int64 *)CreateEventW(0, 0, 0, 0);
  a1[21] = EventW;
  if ( EventW )
  {
    v17[1] = EventW;
    v13 = *(__int64 (__fastcall **)(_QWORD, _QWORD *))(v4 + 2816);
    v19 = 0;
    v18 = 0;
    v17[0] = 1;
    v14 = v13(MaxReceiveCount + v8 + 1, v17);
    a1[19] = (__int64 *)v14;
    if ( v14 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, int, __int64, __int64, _QWORD))(v4 + 2824))(
              a1[1],
              MaxReceiveCount,
              1,
              v8,
              1,
              v14,
              v14,
              0);
      a1[18] = (__int64 *)v15;
      if ( v15 )
      {
        v12 = 0;
        InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 3), 0xFA0u);
        InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 8), 0xFA0u);
        InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 13), 0xFA0u);
        *((_BYTE *)a1 + 20) = 1;
        goto LABEL_13;
      }
      Error = WSAGetLastError();
      v11 = L"DeviceSetupHelper Create RQ failed with status %u";
    }
    else
    {
      Error = WSAGetLastError();
      v11 = L"DeviceSetupHelper Create CQ failed with status %u";
    }
  }
  else
  {
    Error = WSAGetLastError();
    v11 = L"DeviceSetupHelper Create CQ Notify Event failed with status %u";
  }
  v12 = Error;
  EventWrite0(0x100000, v11, Error);
LABEL_13:
  EventWrite0(0x100000, L"TeredoRioSocketSetupHelper finished with status %u", v12);
  return v12;
}

```

## disassembly

```asm
0x180058844  push    rbx
0x180058846  push    rbp
0x180058847  push    rsi
0x180058848  push    rdi
0x180058849  push    r14
0x18005884b  sub     rsp, 70h
0x18005884f  mov     rax, [rcx]
0x180058852  mov     ebp, edx
0x180058854  mov     rdi, rcx
0x180058857  lea     rdx, aTeredoriosocke; "TeredoRioSocketSetupHelper"
0x18005885e  mov     r14d, 100000h
0x180058864  mov     ecx, r14d
0x180058867  mov     rsi, [rax]
0x18005886a  call    EventWriteEnterEx
0x18005886f  lea     rcx, [rsi+0AD0h]
0x180058876  mov     edx, ebp
0x180058878  call    TeredoRioGetMaxReceiveCount
0x18005887d  mov     ebx, eax
0x18005887f  test    ebp, ebp
0x180058881  jnz     short loc_18005888B
0x180058883  add     ebx, [rsi+0B54h]
0x180058889  jmp     short loc_180058896
0x18005888b  cmp     ebp, 1
0x18005888e  jnz     short loc_180058896
0x180058890  add     ebx, [rsi+0B4Ch]
0x180058896  call    TeredoRioGetMaxReceiveCount
0x18005889b  xor     r9d, r9d; lpName
0x18005889e  xor     r8d, r8d; bInitialState
0x1800588a1  xor     edx, edx; bManualReset
0x1800588a3  xor     ecx, ecx; lpEventAttributes
0x1800588a5  mov     ebp, eax
0x1800588a7  call    cs:__imp_CreateEventW
0x1800588ae  nop     dword ptr [rax+rax+00h]
0x1800588b3  mov     [rdi+0A8h], rax
0x1800588ba  test    rax, rax
0x1800588bd  jnz     short loc_1800588E4
0x1800588bf  call    cs:__imp_WSAGetLastError
0x1800588c6  nop     dword ptr [rax+rax+00h]
0x1800588cb  lea     rdx, aDevicesetuphel; "DeviceSetupHelper Create CQ Notify Even"...
0x1800588d2  mov     r8d, eax
0x1800588d5  mov     ecx, r14d
0x1800588d8  mov     ebx, eax
0x1800588da  call    EventWrite0
0x1800588df  jmp     loc_1800589CF
0x1800588e4  xor     ecx, ecx
0x1800588e6  mov     [rsp+98h+var_40], rax
0x1800588eb  mov     rax, [rsi+0B00h]
0x1800588f2  lea     rdx, [rsp+98h+var_48]
0x1800588f7  mov     [rsp+98h+var_34], rcx
0x1800588fc  mov     [rsp+98h+var_38], ecx
0x180058900  lea     ecx, [rbp+1]
0x180058903  add     ecx, ebx
0x180058905  mov     [rsp+98h+var_48], 1
0x18005890e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058913  mov     [rdi+98h], rax
0x18005891a  test    rax, rax
0x18005891d  jnz     short loc_180058934
0x18005891f  call    cs:__imp_WSAGetLastError
0x180058926  nop     dword ptr [rax+rax+00h]
0x18005892b  lea     rdx, aDevicesetuphel_1; "DeviceSetupHelper Create CQ failed with"...
0x180058932  jmp     short loc_1800588D2
0x180058934  mov     rcx, [rdi+8]
0x180058938  mov     r9d, ebp
0x18005893b  mov     [rsp+98h+var_60], 0
0x180058944  mov     r8d, 1
0x18005894a  mov     [rsp+98h+var_68], rax
0x18005894f  mov     edx, ebx
0x180058951  mov     [rsp+98h+var_70], rax
0x180058956  mov     rax, [rsi+0B08h]
0x18005895d  mov     [rsp+98h+var_78], 1
0x180058965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005896a  mov     [rdi+90h], rax
0x180058971  test    rax, rax
0x180058974  jnz     short loc_18005898E
0x180058976  call    cs:__imp_WSAGetLastError
0x18005897d  nop     dword ptr [rax+rax+00h]
0x180058982  lea     rdx, aDevicesetuphel_0; "DeviceSetupHelper Create RQ failed with"...
0x180058989  jmp     loc_1800588D2
0x18005898e  mov     esi, 0FA0h
0x180058993  lea     rcx, [rdi+18h]; lpCriticalSection
0x180058997  mov     edx, esi; dwSpinCount
0x180058999  xor     ebx, ebx
0x18005899b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800589a2  nop     dword ptr [rax+rax+00h]
0x1800589a7  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800589ab  mov     edx, esi; dwSpinCount
0x1800589ad  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800589b4  nop     dword ptr [rax+rax+00h]
0x1800589b9  lea     rcx, [rdi+68h]; lpCriticalSection
0x1800589bd  mov     edx, esi; dwSpinCount
0x1800589bf  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800589c6  nop     dword ptr [rax+rax+00h]
0x1800589cb  mov     byte ptr [rdi+14h], 1
0x1800589cf  mov     r8d, ebx
0x1800589d2  lea     rdx, aTeredoriosocke_0; "TeredoRioSocketSetupHelper finished wit"...
0x1800589d9  mov     ecx, r14d
0x1800589dc  call    EventWrite0
0x1800589e1  mov     eax, ebx
0x1800589e3  add     rsp, 70h
0x1800589e7  pop     r14
0x1800589e9  pop     rdi
0x1800589ea  pop     rsi
0x1800589eb  pop     rbp
0x1800589ec  pop     rbx
0x1800589ed  retn
```
