# TeredoRefreshClientPerCompartment

- ea: `0x1800523c0`
- end: `0x18005257f`
- name: `TeredoRefreshClientPerCompartment`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ce90`
- `0x180015a6c`
- `0x1800190e0`
- `0x18001caf0`
- `0x180022b30`
- `0x180042158`
- `0x1800523c0`
- `0x18005babc`
- `0x18005dfd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052535`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052535`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005248d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005248d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005249e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005249e`

## string_xrefs

- `0x18005242d`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18005246d`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800524da`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180052555`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180052420`: `TeredoRefreshClientPerCompartment`
- `0x180052460`: `TeredoRefreshClientPerCompartment`
- `0x1800524cd`: `TeredoRefreshClientPerCompartment`
- `0x180052548`: `TeredoRefreshClientPerCompartment`
- `0x1800524aa`: `Failed to wait for StopIoComplete Event, 0x%x`
- `0x1800524fd`: `TeredoDeleteCurrentGatewayKey returned 0x%x`
- `0x18005251f`: `TeredoDeleteAndRecreatePreviousState returned 0x%x`

## pseudocode

```c
void __fastcall TeredoRefreshClientPerCompartment(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rcx
  DWORD LastError; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a2 + 4) == 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( v2 && *(_DWORD *)(a1 + 16) == 1 )
  {
    if ( *(_DWORD *)(a1 + 24) )
    {
      *(_DWORD *)(a2 + 4) = 1115;
      return;
    }
    if ( (unsigned int)TeredoTypeServer(a1) || dword_1800CA09C == 3 )
    {
      *(_DWORD *)(v5 + 4) = 1630;
    }
    else
    {
      if ( !(unsigned int)GetAndTraceLock(
                            "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
                            "TeredoRefreshClientPerCompartment",
                            9279,
                            g_TeredoLock) )
        goto LABEL_17;
      TeredoTelemetryWriteRefreshEvent(a1 + 4960);
      TeredoStopClient(a1 + 4960, v6, v7);
      ReleaseAndTraceLock(
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
        "TeredoRefreshClientPerCompartment",
        9288,
        g_TeredoLock);
      v8 = *(void **)(a1 + 13520);
      if ( v8 && WaitForSingleObjectEx(v8, 0x2710u, 0) == -1 )
      {
        LastError = GetLastError();
        *(_DWORD *)(a2 + 4) = LastError;
        EventWriteError0(0x100000, L"Failed to wait for StopIoComplete Event, 0x%x", LastError);
        return;
      }
      if ( (unsigned int)GetAndTraceLock(
                           "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
                           "TeredoRefreshClientPerCompartment",
                           9312,
                           g_TeredoLock) )
      {
        v10 = TeredoDeleteGatewayKey(&GatewayAddress);
        if ( v10 )
        {
          EventWriteError0(0x100000, L"TeredoDeleteCurrentGatewayKey returned 0x%x", v10);
          v11 = TeredoDeleteAndRecreatePreviousState(&hKey);
          if ( v11 )
            EventWriteError0(0x100000, L"TeredoDeleteAndRecreatePreviousState returned 0x%x", v11);
          RegCloseKey(hKey);
        }
        ReleaseAndTraceLock(
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
          "TeredoRefreshClientPerCompartment",
          9348,
          g_TeredoLock);
      }
      else
      {
LABEL_17:
        *(_DWORD *)(a2 + 4) = 167;
      }
    }
  }
}

```

## disassembly

```asm
0x1800523c0  mov     [rsp+arg_8], rbx
0x1800523c5  push    rdi
0x1800523c6  sub     rsp, 20h
0x1800523ca  cmp     dword ptr [rdx+4], 0
0x1800523ce  mov     rdi, rdx
0x1800523d1  mov     rbx, rcx
0x1800523d4  mov     [rsp+28h+hKey], 0FFFFFFFFFFFFFFFFh
0x1800523dd  jnz     loc_180052573
0x1800523e3  cmp     dword ptr [rcx+10h], 1
0x1800523e7  jnz     loc_180052573
0x1800523ed  cmp     dword ptr [rcx+18h], 0
0x1800523f1  jz      short loc_1800523FF
0x1800523f3  mov     dword ptr [rdx+4], 45Bh
0x1800523fa  jmp     loc_180052573
0x1800523ff  call    TeredoTypeServer
0x180052404  test    eax, eax
0x180052406  jnz     loc_18005256C
0x18005240c  cmp     cs:dword_1800CA09C, 3
0x180052413  jz      loc_18005256C
0x180052419  mov     r9, cs:g_TeredoLock
0x180052420  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x180052427  mov     r8d, 243Fh
0x18005242d  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180052434  call    GetAndTraceLock
0x180052439  test    eax, eax
0x18005243b  jz      loc_180052563
0x180052441  lea     rcx, [rbx+1360h]
0x180052448  call    TeredoTelemetryWriteRefreshEvent
0x18005244d  lea     rcx, [rbx+1360h]
0x180052454  call    TeredoStopClient
0x180052459  mov     r9, cs:g_TeredoLock
0x180052460  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x180052467  mov     r8d, 2448h
0x18005246d  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180052474  call    ReleaseAndTraceLock
0x180052479  mov     rcx, [rbx+34D0h]; hHandle
0x180052480  test    rcx, rcx
0x180052483  jz      short loc_1800524C6
0x180052485  xor     r8d, r8d; bAlertable
0x180052488  mov     edx, 2710h; dwMilliseconds
0x18005248d  call    cs:__imp_WaitForSingleObjectEx
0x180052494  nop     dword ptr [rax+rax+00h]
0x180052499  cmp     eax, 0FFFFFFFFh
0x18005249c  jnz     short loc_1800524C6
0x18005249e  call    cs:__imp_GetLastError
0x1800524a5  nop     dword ptr [rax+rax+00h]
0x1800524aa  lea     rdx, aFailedToWaitFo; "Failed to wait for StopIoComplete Event"...
0x1800524b1  mov     ecx, 100000h
0x1800524b6  mov     r8d, eax
0x1800524b9  mov     [rdi+4], eax
0x1800524bc  call    EventWriteError0
0x1800524c1  jmp     loc_180052573
0x1800524c6  mov     r9, cs:g_TeredoLock
0x1800524cd  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x1800524d4  mov     r8d, 2460h
0x1800524da  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800524e1  call    GetAndTraceLock
0x1800524e6  test    eax, eax
0x1800524e8  jz      short loc_180052563
0x1800524ea  lea     rcx, GatewayAddress; lpSubKey
0x1800524f1  call    TeredoDeleteGatewayKey
0x1800524f6  test    eax, eax
0x1800524f8  jz      short loc_180052541
0x1800524fa  mov     r8d, eax
0x1800524fd  lea     rdx, aTeredodeletecu; "TeredoDeleteCurrentGatewayKey returned "...
0x180052504  mov     ecx, 100000h
0x180052509  call    EventWriteError0
0x18005250e  lea     rcx, [rsp+28h+hKey]; phkResult
0x180052513  call    TeredoDeleteAndRecreatePreviousState
0x180052518  test    eax, eax
0x18005251a  jz      short loc_180052530
0x18005251c  mov     r8d, eax
0x18005251f  lea     rdx, aTeredodeletean; "TeredoDeleteAndRecreatePreviousState re"...
0x180052526  mov     ecx, 100000h
0x18005252b  call    EventWriteError0
0x180052530  mov     rcx, [rsp+28h+hKey]; hKey
0x180052535  call    cs:__imp_RegCloseKey
0x18005253c  nop     dword ptr [rax+rax+00h]
0x180052541  mov     r9, cs:g_TeredoLock
0x180052548  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x18005254f  mov     r8d, 2484h
0x180052555  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005255c  call    ReleaseAndTraceLock
0x180052561  jmp     short loc_180052573
0x180052563  mov     dword ptr [rdi+4], 0A7h
0x18005256a  jmp     short loc_180052573
0x18005256c  mov     dword ptr [rdx+4], 65Eh
0x180052573  mov     rbx, [rsp+28h+arg_8]
0x180052578  add     rsp, 20h
0x18005257c  pop     rdi
0x18005257d  retn
```
