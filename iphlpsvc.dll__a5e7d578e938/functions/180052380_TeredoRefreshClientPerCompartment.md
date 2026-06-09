# TeredoRefreshClientPerCompartment

- ea: `0x180052380`
- end: `0x18005253f`
- name: `TeredoRefreshClientPerCompartment`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cea0`
- `0x180015a7c`
- `0x1800190f0`
- `0x18001cb00`
- `0x180022b40`
- `0x180042118`
- `0x180052380`
- `0x18005badc`
- `0x18005dff8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800524f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800524f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005244d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005244d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005245e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005245e`

## string_xrefs

- `0x1800523ed`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18005242d`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18005249a`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180052515`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800523e0`: `TeredoRefreshClientPerCompartment`
- `0x180052420`: `TeredoRefreshClientPerCompartment`
- `0x18005248d`: `TeredoRefreshClientPerCompartment`
- `0x180052508`: `TeredoRefreshClientPerCompartment`
- `0x18005246a`: `Failed to wait for StopIoComplete Event, 0x%x`
- `0x1800524bd`: `TeredoDeleteCurrentGatewayKey returned 0x%x`
- `0x1800524df`: `TeredoDeleteAndRecreatePreviousState returned 0x%x`

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
0x180052380  mov     [rsp+arg_8], rbx
0x180052385  push    rdi
0x180052386  sub     rsp, 20h
0x18005238a  cmp     dword ptr [rdx+4], 0
0x18005238e  mov     rdi, rdx
0x180052391  mov     rbx, rcx
0x180052394  mov     [rsp+28h+hKey], 0FFFFFFFFFFFFFFFFh
0x18005239d  jnz     loc_180052533
0x1800523a3  cmp     dword ptr [rcx+10h], 1
0x1800523a7  jnz     loc_180052533
0x1800523ad  cmp     dword ptr [rcx+18h], 0
0x1800523b1  jz      short loc_1800523BF
0x1800523b3  mov     dword ptr [rdx+4], 45Bh
0x1800523ba  jmp     loc_180052533
0x1800523bf  call    TeredoTypeServer
0x1800523c4  test    eax, eax
0x1800523c6  jnz     loc_18005252C
0x1800523cc  cmp     cs:dword_1800CA09C, 3
0x1800523d3  jz      loc_18005252C
0x1800523d9  mov     r9, cs:g_TeredoLock
0x1800523e0  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x1800523e7  mov     r8d, 243Fh
0x1800523ed  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800523f4  call    GetAndTraceLock
0x1800523f9  test    eax, eax
0x1800523fb  jz      loc_180052523
0x180052401  lea     rcx, [rbx+1360h]
0x180052408  call    TeredoTelemetryWriteRefreshEvent
0x18005240d  lea     rcx, [rbx+1360h]
0x180052414  call    TeredoStopClient
0x180052419  mov     r9, cs:g_TeredoLock
0x180052420  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x180052427  mov     r8d, 2448h
0x18005242d  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180052434  call    ReleaseAndTraceLock
0x180052439  mov     rcx, [rbx+34D0h]; hHandle
0x180052440  test    rcx, rcx
0x180052443  jz      short loc_180052486
0x180052445  xor     r8d, r8d; bAlertable
0x180052448  mov     edx, 2710h; dwMilliseconds
0x18005244d  call    cs:__imp_WaitForSingleObjectEx
0x180052454  nop     dword ptr [rax+rax+00h]
0x180052459  cmp     eax, 0FFFFFFFFh
0x18005245c  jnz     short loc_180052486
0x18005245e  call    cs:__imp_GetLastError
0x180052465  nop     dword ptr [rax+rax+00h]
0x18005246a  lea     rdx, aFailedToWaitFo; "Failed to wait for StopIoComplete Event"...
0x180052471  mov     ecx, 100000h
0x180052476  mov     r8d, eax
0x180052479  mov     [rdi+4], eax
0x18005247c  call    EventWriteError0
0x180052481  jmp     loc_180052533
0x180052486  mov     r9, cs:g_TeredoLock
0x18005248d  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x180052494  mov     r8d, 2460h
0x18005249a  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800524a1  call    GetAndTraceLock
0x1800524a6  test    eax, eax
0x1800524a8  jz      short loc_180052523
0x1800524aa  lea     rcx, GatewayAddress; lpSubKey
0x1800524b1  call    TeredoDeleteGatewayKey
0x1800524b6  test    eax, eax
0x1800524b8  jz      short loc_180052501
0x1800524ba  mov     r8d, eax
0x1800524bd  lea     rdx, aTeredodeletecu; "TeredoDeleteCurrentGatewayKey returned "...
0x1800524c4  mov     ecx, 100000h
0x1800524c9  call    EventWriteError0
0x1800524ce  lea     rcx, [rsp+28h+hKey]; phkResult
0x1800524d3  call    TeredoDeleteAndRecreatePreviousState
0x1800524d8  test    eax, eax
0x1800524da  jz      short loc_1800524F0
0x1800524dc  mov     r8d, eax
0x1800524df  lea     rdx, aTeredodeletean; "TeredoDeleteAndRecreatePreviousState re"...
0x1800524e6  mov     ecx, 100000h
0x1800524eb  call    EventWriteError0
0x1800524f0  mov     rcx, [rsp+28h+hKey]; hKey
0x1800524f5  call    cs:__imp_RegCloseKey
0x1800524fc  nop     dword ptr [rax+rax+00h]
0x180052501  mov     r9, cs:g_TeredoLock
0x180052508  lea     rdx, aTeredorefreshc_4; "TeredoRefreshClientPerCompartment"
0x18005250f  mov     r8d, 2484h
0x180052515  lea     rcx, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005251c  call    ReleaseAndTraceLock
0x180052521  jmp     short loc_180052533
0x180052523  mov     dword ptr [rdi+4], 0A7h
0x18005252a  jmp     short loc_180052533
0x18005252c  mov     dword ptr [rdx+4], 65Eh
0x180052533  mov     rbx, [rsp+28h+arg_8]
0x180052538  add     rsp, 20h
0x18005253c  pop     rdi
0x18005253d  retn
```
