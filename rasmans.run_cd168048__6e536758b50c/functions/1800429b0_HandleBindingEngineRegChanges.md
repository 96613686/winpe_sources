# HandleBindingEngineRegChanges

- ea: `0x1800429b0`
- end: `0x180042eec`
- name: `HandleBindingEngineRegChanges`
- size: `1340`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c3c0`
- `0x1800429b0`
- `0x1800463fc`
- `0x1800474f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d1b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180042d04`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180042d04`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180042a1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180042a83`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180042a1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180042a83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d8b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180042e53`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180042e53`

## pseudocode

```c
void __fastcall __noreturn HandleBindingEngineRegChanges(PVOID Parameter)
{
  DWORD LastError; // eax
  DWORD v2; // ebx
  struct _LIST_ENTRY *v3; // rcx
  __int64 v4; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  const char *v6; // r9
  DWORD v7; // edi
  __int64 v8; // rdx
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF
  HKEY v10; // [rsp+88h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 713, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  hKey = 0;
  v10 = 0;
  hEvent = CreateEventA(0, 1, 0, 0);
  if ( !hEvent )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_68;
      }
      v4 = 714;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  qword_180110DB0 = CreateEventA(0, 1, 0, 0);
  if ( !qword_180110DB0 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_68;
      }
      v4 = 715;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  LastError = RegisterRegNotification(&hKey, &v10);
  v2 = LastError;
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_68;
    }
    v4 = 716;
    goto LABEL_66;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 717, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  while ( 1 )
  {
    v7 = WaitForMultipleObjectsEx(3u, &g_phEvents, 0, 0xFFFFFFFF, 0);
    if ( v7 == -1 )
      break;
    if ( v7 == 258 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 719, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, 0xFFFFFFFFLL);
      }
      LastError = ProcessRasBindingKeys(&hKey, &v10);
      v2 = LastError;
      if ( LastError )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_68;
        }
        v4 = 722;
        goto LABEL_66;
      }
    }
    else
    {
      if ( RasmanShuttingDown )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 5u )
        {
          goto LABEL_68;
        }
        v8 = 720;
LABEL_91:
        WPP_SF_(v3[1].Flink, v8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        goto LABEL_67;
      }
      if ( v7 + 1 <= 3 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 723, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v7);
          v3 = WPP_GLOBAL_Control;
        }
        if ( !v7 )
        {
          if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v3[1].Blink) & 0x2000) != 0
            && BYTE1(v3[1].Blink) >= 5u )
          {
            v8 = 726;
            goto LABEL_91;
          }
LABEL_68:
          if ( hKey )
          {
            RegCloseKey(hKey);
            v3 = WPP_GLOBAL_Control;
          }
          if ( v10 )
          {
            RegCloseKey(v10);
            v3 = WPP_GLOBAL_Control;
          }
          if ( hEvent )
          {
            CloseHandle(hEvent);
            v3 = WPP_GLOBAL_Control;
            hEvent = 0;
          }
          if ( qword_180110DB0 )
          {
            CloseHandle(qword_180110DB0);
            v3 = WPP_GLOBAL_Control;
            qword_180110DB0 = 0;
          }
          if ( g_phEvents )
          {
            CloseHandle(g_phEvents);
            v3 = WPP_GLOBAL_Control;
            g_phEvents = 0;
          }
          if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v3[1].Blink) & 0x2000) != 0
            && BYTE1(v3[1].Blink) >= 6u )
          {
            WPP_SF_d(v3[1].Flink, 728, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v2);
          }
          FreeLibraryAndExitThread(g_hModule, v2);
        }
        if ( v7 - 1 < 2 )
        {
          if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v3[1].Blink) & 0x2000) != 0
            && BYTE1(v3[1].Blink) >= 5u )
          {
            Flink = v3[1].Flink;
            v6 = "LanmanServer Key";
            if ( v7 != 1 )
              v6 = "LanmanWorkStation Key";
            WPP_SF_s(Flink, 724, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v6);
          }
          LastError = ProcessRasBindingKeys(&hKey, &v10);
          v2 = LastError;
          if ( LastError )
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_68;
            }
            v4 = 725;
LABEL_66:
            WPP_SF_d(v3[1].Flink, v4, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, LastError);
LABEL_67:
            v3 = WPP_GLOBAL_Control;
            goto LABEL_68;
          }
        }
        else if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
               && (HIDWORD(v3[1].Blink) & 0x2000) != 0
               && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 727, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 721, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v7);
      }
    }
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_68;
    }
    v4 = 718;
    goto LABEL_66;
  }
  goto LABEL_67;
}

```

## disassembly

```asm
0x1800429b0  push    rbp
0x1800429b2  push    rbx
0x1800429b3  push    rsi
0x1800429b4  push    rdi
0x1800429b5  push    r12
0x1800429b7  push    r13
0x1800429b9  push    r15
0x1800429bb  mov     rbp, rsp
0x1800429be  sub     rsp, 30h
0x1800429c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429c9  lea     r12, WPP_GLOBAL_Control
0x1800429d0  lea     r13, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800429d7  mov     r15d, 2000h
0x1800429dd  cmp     rcx, r12
0x1800429e0  jz      short loc_1800429FF
0x1800429e2  test    [rcx+1Ch], r15d
0x1800429e6  jz      short loc_1800429FF
0x1800429e8  cmp     byte ptr [rcx+19h], 6
0x1800429ec  jb      short loc_1800429FF
0x1800429ee  mov     rcx, [rcx+10h]
0x1800429f2  mov     edx, 2C9h
0x1800429f7  mov     r8, r13
0x1800429fa  call    WPP_SF_
0x1800429ff  xor     r9d, r9d; lpName
0x180042a02  mov     [rbp+hKey], 0
0x180042a0a  xor     r8d, r8d; bInitialState
0x180042a0d  mov     [rbp+arg_18], 0
0x180042a15  xor     ecx, ecx; lpEventAttributes
0x180042a17  lea     ebx, [r9+1]
0x180042a1b  mov     edx, ebx; bManualReset
0x180042a1d  call    cs:__imp_CreateEventA
0x180042a24  nop     dword ptr [rax+rax+00h]
0x180042a29  mov     cs:hEvent, rax
0x180042a30  test    rax, rax
0x180042a33  jnz     short loc_180042A79
0x180042a35  call    cs:__imp_GetLastError
0x180042a3c  nop     dword ptr [rax+rax+00h]
0x180042a41  mov     ebx, eax
0x180042a43  test    eax, eax
0x180042a45  jz      loc_180042D59
0x180042a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a52  cmp     rcx, r12
0x180042a55  jz      loc_180042D60
0x180042a5b  test    [rcx+1Ch], r15d
0x180042a5f  jz      loc_180042D60
0x180042a65  cmp     byte ptr [rcx+19h], 2
0x180042a69  jb      loc_180042D60
0x180042a6f  mov     edx, 2CAh
0x180042a74  jmp     loc_180042D4A
0x180042a79  xor     r9d, r9d; lpName
0x180042a7c  xor     r8d, r8d; bInitialState
0x180042a7f  mov     edx, ebx; bManualReset
0x180042a81  xor     ecx, ecx; lpEventAttributes
0x180042a83  call    cs:__imp_CreateEventA
0x180042a8a  nop     dword ptr [rax+rax+00h]
0x180042a8f  mov     cs:qword_180110DB0, rax
0x180042a96  test    rax, rax
0x180042a99  jnz     short loc_180042ADF
0x180042a9b  call    cs:__imp_GetLastError
0x180042aa2  nop     dword ptr [rax+rax+00h]
0x180042aa7  mov     ebx, eax
0x180042aa9  test    eax, eax
0x180042aab  jz      loc_180042D59
0x180042ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ab8  cmp     rcx, r12
0x180042abb  jz      loc_180042D60
0x180042ac1  test    [rcx+1Ch], r15d
0x180042ac5  jz      loc_180042D60
0x180042acb  cmp     byte ptr [rcx+19h], 2
0x180042acf  jb      loc_180042D60
0x180042ad5  mov     edx, 2CBh
0x180042ada  jmp     loc_180042D4A
0x180042adf  xor     r8d, r8d
0x180042ae2  lea     rdx, [rbp+arg_18]; PHKEY
0x180042ae6  lea     rcx, [rbp+hKey]; phkResult
0x180042aea  call    RegisterRegNotification
0x180042aef  mov     ebx, eax
0x180042af1  test    eax, eax
0x180042af3  jz      short loc_180042B23
0x180042af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180042afc  cmp     rcx, r12
0x180042aff  jz      loc_180042D60
0x180042b05  test    [rcx+1Ch], r15d
0x180042b09  jz      loc_180042D60
0x180042b0f  cmp     byte ptr [rcx+19h], 2
0x180042b13  jb      loc_180042D60
0x180042b19  mov     edx, 2CCh
0x180042b1e  jmp     loc_180042D4A
0x180042b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b2a  cmp     rcx, r12
0x180042b2d  jz      short loc_180042B4C
0x180042b2f  test    [rcx+1Ch], r15d
0x180042b33  jz      short loc_180042B4C
0x180042b35  cmp     byte ptr [rcx+19h], 5
0x180042b39  jb      short loc_180042B4C
0x180042b3b  mov     rcx, [rcx+10h]
0x180042b3f  mov     edx, 2CDh
0x180042b44  mov     r8, r13
0x180042b47  call    WPP_SF_
0x180042b4c  or      eax, 0FFFFFFFFh
0x180042b4f  mov     esi, eax
0x180042b51  mov     [rbp+arg_8], eax
0x180042b54  mov     r9d, eax
0x180042b57  jmp     loc_180042CEE
0x180042b5c  cmp     edi, 102h
0x180042b62  jnz     short loc_180042BD9
0x180042b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b6b  cmp     rcx, r12
0x180042b6e  jz      short loc_180042B90
0x180042b70  test    [rcx+1Ch], r15d
0x180042b74  jz      short loc_180042B90
0x180042b76  cmp     byte ptr [rcx+19h], 5
0x180042b7a  jb      short loc_180042B90
0x180042b7c  mov     rcx, [rcx+10h]
0x180042b80  mov     edx, 2CFh
0x180042b85  mov     r9d, esi
0x180042b88  mov     r8, r13
0x180042b8b  call    WPP_SF_d
0x180042b90  lea     r8, [rbp+arg_8]
0x180042b94  lea     rdx, [rbp+arg_18]; PHKEY
0x180042b98  lea     rcx, [rbp+hKey]; phkResult
0x180042b9c  call    ProcessRasBindingKeys
0x180042ba1  mov     ebx, eax
0x180042ba3  test    eax, eax
0x180042ba5  jz      loc_180042CE8
0x180042bab  mov     rcx, cs:WPP_GLOBAL_Control
0x180042bb2  cmp     rcx, r12
0x180042bb5  jz      loc_180042D60
0x180042bbb  test    [rcx+1Ch], r15d
0x180042bbf  jz      loc_180042D60
0x180042bc5  cmp     byte ptr [rcx+19h], 2
0x180042bc9  jb      loc_180042D60
0x180042bcf  mov     edx, 2D2h
0x180042bd4  jmp     loc_180042D4A
0x180042bd9  cmp     cs:RasmanShuttingDown, 0
0x180042be0  jnz     loc_180042EC1
0x180042be6  lea     eax, [rdi+1]
0x180042be9  cmp     eax, 3
0x180042bec  jbe     short loc_180042C2B
0x180042bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180042bf5  cmp     rcx, r12
0x180042bf8  jz      loc_180042CEB
0x180042bfe  test    [rcx+1Ch], r15d
0x180042c02  jz      loc_180042CEB
0x180042c08  cmp     byte ptr [rcx+19h], 5
0x180042c0c  jb      loc_180042CEB
0x180042c12  mov     rcx, [rcx+10h]
0x180042c16  mov     edx, 2D1h
0x180042c1b  mov     r9d, edi
0x180042c1e  mov     r8, r13
0x180042c21  call    WPP_SF_d
0x180042c26  jmp     loc_180042CEB
0x180042c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c32  cmp     rcx, r12
0x180042c35  jz      short loc_180042C5E
0x180042c37  test    [rcx+1Ch], r15d
0x180042c3b  jz      short loc_180042C5E
0x180042c3d  cmp     byte ptr [rcx+19h], 5
0x180042c41  jb      short loc_180042C5E
0x180042c43  mov     rcx, [rcx+10h]
0x180042c47  mov     edx, 2D3h
0x180042c4c  mov     r9d, edi
0x180042c4f  mov     r8, r13
0x180042c52  call    WPP_SF_d
0x180042c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c5e  mov     eax, edi
0x180042c60  test    edi, edi
0x180042c62  jz      loc_180042E8E
0x180042c68  sub     eax, 1
0x180042c6b  jz      short loc_180042C96
0x180042c6d  cmp     eax, 1
0x180042c70  jz      short loc_180042C96
0x180042c72  cmp     rcx, r12
0x180042c75  jz      short loc_180042CEB
0x180042c77  test    [rcx+1Ch], r15d
0x180042c7b  jz      short loc_180042CEB
0x180042c7d  cmp     byte ptr [rcx+19h], 5
0x180042c81  jb      short loc_180042CEB
0x180042c83  mov     rcx, [rcx+10h]
0x180042c87  mov     edx, 2D7h
0x180042c8c  mov     r8, r13
0x180042c8f  call    WPP_SF_
0x180042c94  jmp     short loc_180042CEB
0x180042c96  cmp     rcx, r12
0x180042c99  jz      short loc_180042CCD
0x180042c9b  test    [rcx+1Ch], r15d
0x180042c9f  jz      short loc_180042CCD
0x180042ca1  cmp     byte ptr [rcx+19h], 5
0x180042ca5  jb      short loc_180042CCD
0x180042ca7  mov     rcx, [rcx+10h]
0x180042cab  lea     rax, aLanmanworkstat; "LanmanWorkStation Key"
0x180042cb2  cmp     edi, 1
0x180042cb5  lea     r9, aLanmanserverKe; "LanmanServer Key"
0x180042cbc  mov     edx, 2D4h
0x180042cc1  mov     r8, r13
0x180042cc4  cmovnz  r9, rax
0x180042cc8  call    WPP_SF_s
0x180042ccd  lea     r8, [rbp+arg_8]
0x180042cd1  lea     rdx, [rbp+arg_18]; PHKEY
0x180042cd5  lea     rcx, [rbp+hKey]; phkResult
0x180042cd9  call    ProcessRasBindingKeys
0x180042cde  mov     ebx, eax
0x180042ce0  test    eax, eax
0x180042ce2  jnz     loc_180042E60
0x180042ce8  mov     esi, [rbp+arg_8]
0x180042ceb  mov     r9d, esi; dwMilliseconds
0x180042cee  xor     r8d, r8d; bWaitAll
0x180042cf1  mov     [rsp+30h+bAlertable], 0; bAlertable
0x180042cf9  lea     rdx, g_phEvents; lpHandles
0x180042d00  lea     ecx, [r8+3]; nCount
0x180042d04  call    cs:__imp_WaitForMultipleObjectsEx
0x180042d0b  nop     dword ptr [rax+rax+00h]
0x180042d10  mov     edi, eax
0x180042d12  cmp     eax, 0FFFFFFFFh
0x180042d15  jnz     loc_180042B5C
0x180042d1b  call    cs:__imp_GetLastError
0x180042d22  nop     dword ptr [rax+rax+00h]
0x180042d27  mov     ebx, eax
0x180042d29  test    eax, eax
0x180042d2b  jz      short loc_180042D59
0x180042d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d34  cmp     rcx, r12
0x180042d37  jz      short loc_180042D60
0x180042d39  test    [rcx+1Ch], r15d
0x180042d3d  jz      short loc_180042D60
0x180042d3f  cmp     byte ptr [rcx+19h], 2
0x180042d43  jb      short loc_180042D60
0x180042d45  mov     edx, 2CEh
0x180042d4a  mov     rcx, [rcx+10h]
0x180042d4e  mov     r9d, eax
0x180042d51  mov     r8, r13
0x180042d54  call    WPP_SF_d
0x180042d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d60  mov     rax, [rbp+hKey]
0x180042d64  test    rax, rax
0x180042d67  jz      short loc_180042D7F
0x180042d69  mov     rcx, rax; hKey
0x180042d6c  call    cs:__imp_RegCloseKey
0x180042d73  nop     dword ptr [rax+rax+00h]
0x180042d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d7f  mov     rax, [rbp+arg_18]
0x180042d83  test    rax, rax
0x180042d86  jz      short loc_180042D9E
0x180042d88  mov     rcx, rax; hKey
0x180042d8b  call    cs:__imp_RegCloseKey
0x180042d92  nop     dword ptr [rax+rax+00h]
0x180042d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d9e  mov     rax, cs:hEvent
0x180042da5  test    rax, rax
0x180042da8  jz      short loc_180042DCB
0x180042daa  mov     rcx, rax; hObject
0x180042dad  call    cs:__imp_CloseHandle
0x180042db4  nop     dword ptr [rax+rax+00h]
0x180042db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180042dc0  mov     cs:hEvent, 0
0x180042dcb  mov     rax, cs:qword_180110DB0
0x180042dd2  test    rax, rax
0x180042dd5  jz      short loc_180042DF8
0x180042dd7  mov     rcx, rax; hObject
0x180042dda  call    cs:__imp_CloseHandle
0x180042de1  nop     dword ptr [rax+rax+00h]
0x180042de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ded  mov     cs:qword_180110DB0, 0
0x180042df8  mov     rax, cs:g_phEvents
0x180042dff  test    rax, rax
0x180042e02  jz      short loc_180042E25
0x180042e04  mov     rcx, rax; hObject
0x180042e07  call    cs:__imp_CloseHandle
0x180042e0e  nop     dword ptr [rax+rax+00h]
0x180042e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e1a  mov     cs:g_phEvents, 0
0x180042e25  cmp     rcx, r12
0x180042e28  jz      short loc_180042E4A
0x180042e2a  test    [rcx+1Ch], r15d
0x180042e2e  jz      short loc_180042E4A
0x180042e30  cmp     byte ptr [rcx+19h], 6
0x180042e34  jb      short loc_180042E4A
0x180042e36  mov     rcx, [rcx+10h]
0x180042e3a  mov     edx, 2D8h
0x180042e3f  mov     r9d, ebx
0x180042e42  mov     r8, r13
0x180042e45  call    WPP_SF_d
0x180042e4a  mov     rcx, cs:g_hModule; hLibModule
0x180042e51  mov     edx, ebx; dwExitCode
0x180042e53  call    cs:__imp_FreeLibraryAndExitThread
0x180042e5a  nop     dword ptr [rax+rax+00h]
0x180042e5f  int     3; Trap to Debugger
0x180042e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e67  cmp     rcx, r12
0x180042e6a  jz      loc_180042D60
0x180042e70  test    [rcx+1Ch], r15d
0x180042e74  jz      loc_180042D60
0x180042e7a  cmp     byte ptr [rcx+19h], 2
0x180042e7e  jb      loc_180042D60
0x180042e84  mov     edx, 2D5h
0x180042e89  jmp     loc_180042D4A
0x180042e8e  cmp     rcx, r12
0x180042e91  jz      loc_180042D60
0x180042e97  test    [rcx+1Ch], r15d
0x180042e9b  jz      loc_180042D60
  ... truncated ...
```
