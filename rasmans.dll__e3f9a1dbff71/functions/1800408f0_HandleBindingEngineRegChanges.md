# HandleBindingEngineRegChanges

- ea: `0x1800408f0`
- end: `0x180040de4`
- name: `HandleBindingEngineRegChanges`
- size: `1268`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bfb0`
- `0x1800408f0`
- `0x180044198`
- `0x18004521c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040ce4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040ce4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004096f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004096f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004095d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800409b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004095d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800409b7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180040c2c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180040c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040c88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040c88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040ca1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180040d51`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180040d51`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 715, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
      v4 = 716;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  qword_18010FED0 = CreateEventA(0, 1, 0, 0);
  if ( !qword_18010FED0 )
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
      v4 = 717;
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
    v4 = 718;
    goto LABEL_66;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 719, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 721, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, 0xFFFFFFFFLL);
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
        v4 = 724;
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
        v8 = 722;
LABEL_91:
        WPP_SF_(v3[1].Flink, v8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        goto LABEL_67;
      }
      if ( v7 + 1 <= 3 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 725, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v7);
          v3 = WPP_GLOBAL_Control;
        }
        if ( !v7 )
        {
          if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v3[1].Blink) & 0x2000) != 0
            && BYTE1(v3[1].Blink) >= 5u )
          {
            v8 = 728;
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
          if ( qword_18010FED0 )
          {
            CloseHandle(qword_18010FED0);
            v3 = WPP_GLOBAL_Control;
            qword_18010FED0 = 0;
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
            WPP_SF_d(v3[1].Flink, 730, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v2);
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
            WPP_SF_s(Flink, 726, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v6);
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
            v4 = 727;
LABEL_66:
            WPP_SF_d(v3[1].Flink, v4, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, LastError);
LABEL_67:
            v3 = WPP_GLOBAL_Control;
            goto LABEL_68;
          }
        }
        else if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
               && (HIDWORD(v3[1].Blink) & 0x2000) != 0
               && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 729, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 723, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v7);
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
    v4 = 720;
    goto LABEL_66;
  }
  goto LABEL_67;
}

```

## disassembly

```asm
0x1800408f0  push    rbp
0x1800408f2  push    rbx
0x1800408f3  push    rsi
0x1800408f4  push    rdi
0x1800408f5  push    r12
0x1800408f7  push    r13
0x1800408f9  push    r15
0x1800408fb  mov     rbp, rsp
0x1800408fe  sub     rsp, 30h
0x180040902  mov     rcx, cs:WPP_GLOBAL_Control
0x180040909  lea     r12, WPP_GLOBAL_Control
0x180040910  lea     r13, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180040917  mov     r15d, 2000h
0x18004091d  cmp     rcx, r12
0x180040920  jz      short loc_18004093F
0x180040922  test    [rcx+1Ch], r15d
0x180040926  jz      short loc_18004093F
0x180040928  cmp     byte ptr [rcx+19h], 6
0x18004092c  jb      short loc_18004093F
0x18004092e  mov     rcx, [rcx+10h]
0x180040932  mov     edx, 2CBh
0x180040937  mov     r8, r13
0x18004093a  call    WPP_SF_
0x18004093f  xor     r9d, r9d; lpName
0x180040942  mov     [rbp+hKey], 0
0x18004094a  xor     r8d, r8d; bInitialState
0x18004094d  mov     [rbp+arg_18], 0
0x180040955  xor     ecx, ecx; lpEventAttributes
0x180040957  lea     ebx, [r9+1]
0x18004095b  mov     edx, ebx; bManualReset
0x18004095d  call    cs:__imp_CreateEventA
0x180040963  mov     cs:hEvent, rax
0x18004096a  test    rax, rax
0x18004096d  jnz     short loc_1800409AD
0x18004096f  call    cs:__imp_GetLastError
0x180040975  mov     ebx, eax
0x180040977  test    eax, eax
0x180040979  jz      loc_180040C75
0x18004097f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040986  cmp     rcx, r12
0x180040989  jz      loc_180040C7C
0x18004098f  test    [rcx+1Ch], r15d
0x180040993  jz      loc_180040C7C
0x180040999  cmp     byte ptr [rcx+19h], 2
0x18004099d  jb      loc_180040C7C
0x1800409a3  mov     edx, 2CCh
0x1800409a8  jmp     loc_180040C66
0x1800409ad  xor     r9d, r9d; lpName
0x1800409b0  xor     r8d, r8d; bInitialState
0x1800409b3  mov     edx, ebx; bManualReset
0x1800409b5  xor     ecx, ecx; lpEventAttributes
0x1800409b7  call    cs:__imp_CreateEventA
0x1800409bd  mov     cs:qword_18010FED0, rax
0x1800409c4  test    rax, rax
0x1800409c7  jnz     short loc_180040A07
0x1800409c9  call    cs:__imp_GetLastError
0x1800409cf  mov     ebx, eax
0x1800409d1  test    eax, eax
0x1800409d3  jz      loc_180040C75
0x1800409d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800409e0  cmp     rcx, r12
0x1800409e3  jz      loc_180040C7C
0x1800409e9  test    [rcx+1Ch], r15d
0x1800409ed  jz      loc_180040C7C
0x1800409f3  cmp     byte ptr [rcx+19h], 2
0x1800409f7  jb      loc_180040C7C
0x1800409fd  mov     edx, 2CDh
0x180040a02  jmp     loc_180040C66
0x180040a07  xor     r8d, r8d
0x180040a0a  lea     rdx, [rbp+arg_18]; PHKEY
0x180040a0e  lea     rcx, [rbp+hKey]; phkResult
0x180040a12  call    RegisterRegNotification
0x180040a17  mov     ebx, eax
0x180040a19  test    eax, eax
0x180040a1b  jz      short loc_180040A4B
0x180040a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a24  cmp     rcx, r12
0x180040a27  jz      loc_180040C7C
0x180040a2d  test    [rcx+1Ch], r15d
0x180040a31  jz      loc_180040C7C
0x180040a37  cmp     byte ptr [rcx+19h], 2
0x180040a3b  jb      loc_180040C7C
0x180040a41  mov     edx, 2CEh
0x180040a46  jmp     loc_180040C66
0x180040a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a52  cmp     rcx, r12
0x180040a55  jz      short loc_180040A74
0x180040a57  test    [rcx+1Ch], r15d
0x180040a5b  jz      short loc_180040A74
0x180040a5d  cmp     byte ptr [rcx+19h], 5
0x180040a61  jb      short loc_180040A74
0x180040a63  mov     rcx, [rcx+10h]
0x180040a67  mov     edx, 2CFh
0x180040a6c  mov     r8, r13
0x180040a6f  call    WPP_SF_
0x180040a74  or      eax, 0FFFFFFFFh
0x180040a77  mov     esi, eax
0x180040a79  mov     [rbp+arg_8], eax
0x180040a7c  mov     r9d, eax
0x180040a7f  jmp     loc_180040C16
0x180040a84  cmp     edi, 102h
0x180040a8a  jnz     short loc_180040B01
0x180040a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a93  cmp     rcx, r12
0x180040a96  jz      short loc_180040AB8
0x180040a98  test    [rcx+1Ch], r15d
0x180040a9c  jz      short loc_180040AB8
0x180040a9e  cmp     byte ptr [rcx+19h], 5
0x180040aa2  jb      short loc_180040AB8
0x180040aa4  mov     rcx, [rcx+10h]
0x180040aa8  mov     edx, 2D1h
0x180040aad  mov     r9d, esi
0x180040ab0  mov     r8, r13
0x180040ab3  call    WPP_SF_d
0x180040ab8  lea     r8, [rbp+arg_8]
0x180040abc  lea     rdx, [rbp+arg_18]; PHKEY
0x180040ac0  lea     rcx, [rbp+hKey]; phkResult
0x180040ac4  call    ProcessRasBindingKeys
0x180040ac9  mov     ebx, eax
0x180040acb  test    eax, eax
0x180040acd  jz      loc_180040C10
0x180040ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ada  cmp     rcx, r12
0x180040add  jz      loc_180040C7C
0x180040ae3  test    [rcx+1Ch], r15d
0x180040ae7  jz      loc_180040C7C
0x180040aed  cmp     byte ptr [rcx+19h], 2
0x180040af1  jb      loc_180040C7C
0x180040af7  mov     edx, 2D4h
0x180040afc  jmp     loc_180040C66
0x180040b01  cmp     cs:RasmanShuttingDown, 0
0x180040b08  jnz     loc_180040DB9
0x180040b0e  lea     eax, [rdi+1]
0x180040b11  cmp     eax, 3
0x180040b14  jbe     short loc_180040B53
0x180040b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b1d  cmp     rcx, r12
0x180040b20  jz      loc_180040C13
0x180040b26  test    [rcx+1Ch], r15d
0x180040b2a  jz      loc_180040C13
0x180040b30  cmp     byte ptr [rcx+19h], 5
0x180040b34  jb      loc_180040C13
0x180040b3a  mov     rcx, [rcx+10h]
0x180040b3e  mov     edx, 2D3h
0x180040b43  mov     r9d, edi
0x180040b46  mov     r8, r13
0x180040b49  call    WPP_SF_d
0x180040b4e  jmp     loc_180040C13
0x180040b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b5a  cmp     rcx, r12
0x180040b5d  jz      short loc_180040B86
0x180040b5f  test    [rcx+1Ch], r15d
0x180040b63  jz      short loc_180040B86
0x180040b65  cmp     byte ptr [rcx+19h], 5
0x180040b69  jb      short loc_180040B86
0x180040b6b  mov     rcx, [rcx+10h]
0x180040b6f  mov     edx, 2D5h
0x180040b74  mov     r9d, edi
0x180040b77  mov     r8, r13
0x180040b7a  call    WPP_SF_d
0x180040b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b86  mov     eax, edi
0x180040b88  test    edi, edi
0x180040b8a  jz      loc_180040D86
0x180040b90  sub     eax, 1
0x180040b93  jz      short loc_180040BBE
0x180040b95  cmp     eax, 1
0x180040b98  jz      short loc_180040BBE
0x180040b9a  cmp     rcx, r12
0x180040b9d  jz      short loc_180040C13
0x180040b9f  test    [rcx+1Ch], r15d
0x180040ba3  jz      short loc_180040C13
0x180040ba5  cmp     byte ptr [rcx+19h], 5
0x180040ba9  jb      short loc_180040C13
0x180040bab  mov     rcx, [rcx+10h]
0x180040baf  mov     edx, 2D9h
0x180040bb4  mov     r8, r13
0x180040bb7  call    WPP_SF_
0x180040bbc  jmp     short loc_180040C13
0x180040bbe  cmp     rcx, r12
0x180040bc1  jz      short loc_180040BF5
0x180040bc3  test    [rcx+1Ch], r15d
0x180040bc7  jz      short loc_180040BF5
0x180040bc9  cmp     byte ptr [rcx+19h], 5
0x180040bcd  jb      short loc_180040BF5
0x180040bcf  mov     rcx, [rcx+10h]
0x180040bd3  lea     rax, aLanmanworkstat; "LanmanWorkStation Key"
0x180040bda  cmp     edi, 1
0x180040bdd  lea     r9, aLanmanserverKe; "LanmanServer Key"
0x180040be4  mov     edx, 2D6h
0x180040be9  mov     r8, r13
0x180040bec  cmovnz  r9, rax
0x180040bf0  call    WPP_SF_s
0x180040bf5  lea     r8, [rbp+arg_8]
0x180040bf9  lea     rdx, [rbp+arg_18]; PHKEY
0x180040bfd  lea     rcx, [rbp+hKey]; phkResult
0x180040c01  call    ProcessRasBindingKeys
0x180040c06  mov     ebx, eax
0x180040c08  test    eax, eax
0x180040c0a  jnz     loc_180040D58
0x180040c10  mov     esi, [rbp+arg_8]
0x180040c13  mov     r9d, esi; dwMilliseconds
0x180040c16  xor     r8d, r8d; bWaitAll
0x180040c19  mov     [rsp+30h+bAlertable], 0; bAlertable
0x180040c21  lea     rdx, g_phEvents; lpHandles
0x180040c28  lea     ecx, [r8+3]; nCount
0x180040c2c  call    cs:__imp_WaitForMultipleObjectsEx
0x180040c32  mov     edi, eax
0x180040c34  cmp     eax, 0FFFFFFFFh
0x180040c37  jnz     loc_180040A84
0x180040c3d  call    cs:__imp_GetLastError
0x180040c43  mov     ebx, eax
0x180040c45  test    eax, eax
0x180040c47  jz      short loc_180040C75
0x180040c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c50  cmp     rcx, r12
0x180040c53  jz      short loc_180040C7C
0x180040c55  test    [rcx+1Ch], r15d
0x180040c59  jz      short loc_180040C7C
0x180040c5b  cmp     byte ptr [rcx+19h], 2
0x180040c5f  jb      short loc_180040C7C
0x180040c61  mov     edx, 2D0h
0x180040c66  mov     rcx, [rcx+10h]
0x180040c6a  mov     r9d, eax
0x180040c6d  mov     r8, r13
0x180040c70  call    WPP_SF_d
0x180040c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c7c  mov     rax, [rbp+hKey]
0x180040c80  test    rax, rax
0x180040c83  jz      short loc_180040C95
0x180040c85  mov     rcx, rax; hKey
0x180040c88  call    cs:__imp_RegCloseKey
0x180040c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c95  mov     rax, [rbp+arg_18]
0x180040c99  test    rax, rax
0x180040c9c  jz      short loc_180040CAE
0x180040c9e  mov     rcx, rax; hKey
0x180040ca1  call    cs:__imp_RegCloseKey
0x180040ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180040cae  mov     rax, cs:hEvent
0x180040cb5  test    rax, rax
0x180040cb8  jz      short loc_180040CD5
0x180040cba  mov     rcx, rax; hObject
0x180040cbd  call    cs:__imp_CloseHandle
0x180040cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180040cca  mov     cs:hEvent, 0
0x180040cd5  mov     rax, cs:qword_18010FED0
0x180040cdc  test    rax, rax
0x180040cdf  jz      short loc_180040CFC
0x180040ce1  mov     rcx, rax; hObject
0x180040ce4  call    cs:__imp_CloseHandle
0x180040cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180040cf1  mov     cs:qword_18010FED0, 0
0x180040cfc  mov     rax, cs:g_phEvents
0x180040d03  test    rax, rax
0x180040d06  jz      short loc_180040D23
0x180040d08  mov     rcx, rax; hObject
0x180040d0b  call    cs:__imp_CloseHandle
0x180040d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d18  mov     cs:g_phEvents, 0
0x180040d23  cmp     rcx, r12
0x180040d26  jz      short loc_180040D48
0x180040d28  test    [rcx+1Ch], r15d
0x180040d2c  jz      short loc_180040D48
0x180040d2e  cmp     byte ptr [rcx+19h], 6
0x180040d32  jb      short loc_180040D48
0x180040d34  mov     rcx, [rcx+10h]
0x180040d38  mov     edx, 2DAh
0x180040d3d  mov     r9d, ebx
0x180040d40  mov     r8, r13
0x180040d43  call    WPP_SF_d
0x180040d48  mov     rcx, cs:g_hModule; hLibModule
0x180040d4f  mov     edx, ebx; dwExitCode
0x180040d51  call    cs:__imp_FreeLibraryAndExitThread
0x180040d57  int     3; Trap to Debugger
0x180040d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d5f  cmp     rcx, r12
0x180040d62  jz      loc_180040C7C
0x180040d68  test    [rcx+1Ch], r15d
0x180040d6c  jz      loc_180040C7C
0x180040d72  cmp     byte ptr [rcx+19h], 2
0x180040d76  jb      loc_180040C7C
0x180040d7c  mov     edx, 2D7h
0x180040d81  jmp     loc_180040C66
0x180040d86  cmp     rcx, r12
0x180040d89  jz      loc_180040C7C
0x180040d8f  test    [rcx+1Ch], r15d
0x180040d93  jz      loc_180040C7C
0x180040d99  cmp     byte ptr [rcx+19h], 5
0x180040d9d  jb      loc_180040C7C
0x180040da3  mov     edx, 2D8h
0x180040da8  mov     rcx, [rcx+10h]
0x180040dac  mov     r8, r13
0x180040daf  call    WPP_SF_
0x180040db4  jmp     loc_180040C75
0x180040db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180040dc0  cmp     rcx, r12
0x180040dc3  jz      loc_180040C7C
0x180040dc9  test    [rcx+1Ch], r15d
0x180040dcd  jz      loc_180040C7C
  ... truncated ...
```
