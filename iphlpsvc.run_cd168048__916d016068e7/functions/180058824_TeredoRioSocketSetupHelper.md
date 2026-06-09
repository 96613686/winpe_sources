# TeredoRioSocketSetupHelper

- ea: `0x180058824`
- end: `0x1800589cf`
- name: `TeredoRioSocketSetupHelper`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180056280`
- `0x180056c18`

## callees

- `0x180008200`
- `0x18000d7b0`
- `0x180057858`
- `0x180058824`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180058887`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180058887`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005897b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005898d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005899f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005897b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005898d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005899f`
- `WS2_32!__imp_WSAGetLastError` at `0x18005889f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800588ff`
- `WS2_32!__imp_WSAGetLastError` at `0x180058956`
- `WS2_32!__imp_WSAGetLastError` at `0x18005889f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800588ff`
- `WS2_32!__imp_WSAGetLastError` at `0x180058956`

## string_xrefs

- `0x1800588ab`: `DeviceSetupHelper Create CQ Notify Event failed with status %u`
- `0x18005890b`: `DeviceSetupHelper Create CQ failed with status %u`
- `0x180058962`: `DeviceSetupHelper Create RQ failed with status %u`

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
0x180058824  push    rbx
0x180058826  push    rbp
0x180058827  push    rsi
0x180058828  push    rdi
0x180058829  push    r14
0x18005882b  sub     rsp, 70h
0x18005882f  mov     rax, [rcx]
0x180058832  mov     ebp, edx
0x180058834  mov     rdi, rcx
0x180058837  lea     rdx, aTeredoriosocke; "TeredoRioSocketSetupHelper"
0x18005883e  mov     r14d, 100000h
0x180058844  mov     ecx, r14d
0x180058847  mov     rsi, [rax]
0x18005884a  call    EventWriteEnterEx
0x18005884f  lea     rcx, [rsi+0AD0h]
0x180058856  mov     edx, ebp
0x180058858  call    TeredoRioGetMaxReceiveCount
0x18005885d  mov     ebx, eax
0x18005885f  test    ebp, ebp
0x180058861  jnz     short loc_18005886B
0x180058863  add     ebx, [rsi+0B54h]
0x180058869  jmp     short loc_180058876
0x18005886b  cmp     ebp, 1
0x18005886e  jnz     short loc_180058876
0x180058870  add     ebx, [rsi+0B4Ch]
0x180058876  call    TeredoRioGetMaxReceiveCount
0x18005887b  xor     r9d, r9d; lpName
0x18005887e  xor     r8d, r8d; bInitialState
0x180058881  xor     edx, edx; bManualReset
0x180058883  xor     ecx, ecx; lpEventAttributes
0x180058885  mov     ebp, eax
0x180058887  call    cs:__imp_CreateEventW
0x18005888e  nop     dword ptr [rax+rax+00h]
0x180058893  mov     [rdi+0A8h], rax
0x18005889a  test    rax, rax
0x18005889d  jnz     short loc_1800588C4
0x18005889f  call    cs:__imp_WSAGetLastError
0x1800588a6  nop     dword ptr [rax+rax+00h]
0x1800588ab  lea     rdx, aDevicesetuphel; "DeviceSetupHelper Create CQ Notify Even"...
0x1800588b2  mov     r8d, eax
0x1800588b5  mov     ecx, r14d
0x1800588b8  mov     ebx, eax
0x1800588ba  call    EventWrite0
0x1800588bf  jmp     loc_1800589AF
0x1800588c4  xor     ecx, ecx
0x1800588c6  mov     [rsp+98h+var_40], rax
0x1800588cb  mov     rax, [rsi+0B00h]
0x1800588d2  lea     rdx, [rsp+98h+var_48]
0x1800588d7  mov     [rsp+98h+var_34], rcx
0x1800588dc  mov     [rsp+98h+var_38], ecx
0x1800588e0  lea     ecx, [rbp+1]
0x1800588e3  add     ecx, ebx
0x1800588e5  mov     [rsp+98h+var_48], 1
0x1800588ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588f3  mov     [rdi+98h], rax
0x1800588fa  test    rax, rax
0x1800588fd  jnz     short loc_180058914
0x1800588ff  call    cs:__imp_WSAGetLastError
0x180058906  nop     dword ptr [rax+rax+00h]
0x18005890b  lea     rdx, aDevicesetuphel_1; "DeviceSetupHelper Create CQ failed with"...
0x180058912  jmp     short loc_1800588B2
0x180058914  mov     rcx, [rdi+8]
0x180058918  mov     r9d, ebp
0x18005891b  mov     [rsp+98h+var_60], 0
0x180058924  mov     r8d, 1
0x18005892a  mov     [rsp+98h+var_68], rax
0x18005892f  mov     edx, ebx
0x180058931  mov     [rsp+98h+var_70], rax
0x180058936  mov     rax, [rsi+0B08h]
0x18005893d  mov     [rsp+98h+var_78], 1
0x180058945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005894a  mov     [rdi+90h], rax
0x180058951  test    rax, rax
0x180058954  jnz     short loc_18005896E
0x180058956  call    cs:__imp_WSAGetLastError
0x18005895d  nop     dword ptr [rax+rax+00h]
0x180058962  lea     rdx, aDevicesetuphel_0; "DeviceSetupHelper Create RQ failed with"...
0x180058969  jmp     loc_1800588B2
0x18005896e  mov     esi, 0FA0h
0x180058973  lea     rcx, [rdi+18h]; lpCriticalSection
0x180058977  mov     edx, esi; dwSpinCount
0x180058979  xor     ebx, ebx
0x18005897b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180058982  nop     dword ptr [rax+rax+00h]
0x180058987  lea     rcx, [rdi+40h]; lpCriticalSection
0x18005898b  mov     edx, esi; dwSpinCount
0x18005898d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180058994  nop     dword ptr [rax+rax+00h]
0x180058999  lea     rcx, [rdi+68h]; lpCriticalSection
0x18005899d  mov     edx, esi; dwSpinCount
0x18005899f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800589a6  nop     dword ptr [rax+rax+00h]
0x1800589ab  mov     byte ptr [rdi+14h], 1
0x1800589af  mov     r8d, ebx
0x1800589b2  lea     rdx, aTeredoriosocke_0; "TeredoRioSocketSetupHelper finished wit"...
0x1800589b9  mov     ecx, r14d
0x1800589bc  call    EventWrite0
0x1800589c1  mov     eax, ebx
0x1800589c3  add     rsp, 70h
0x1800589c7  pop     r14
0x1800589c9  pop     rdi
0x1800589ca  pop     rsi
0x1800589cb  pop     rbp
0x1800589cc  pop     rbx
0x1800589cd  retn
```
