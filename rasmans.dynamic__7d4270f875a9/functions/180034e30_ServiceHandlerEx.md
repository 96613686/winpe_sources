# ServiceHandlerEx

- ea: `0x180034e30`
- end: `0x1800353aa`
- name: `ServiceHandlerEx`
- size: `1402`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x18000c37c`
- `0x18000c3c0`
- `0x1800347c0`
- `0x180034e30`
- `0x18003c9b4`
- `0x1800473d8`
- `0x1800df210`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800352ef`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800352ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035339`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035339`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800351d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003529e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800351d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003529e`

## pseudocode

```c
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, DWORD dwEventType, _DWORD *lpEventData, LPVOID lpContext)
{
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 29, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, dwControl, dwEventType);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 32;
  ServiceStatus.dwServiceType = 32;
  memset(&ServiceStatus.dwCurrentState, 0, 24);
  v9 = dwControl - 1;
  if ( !v9 )
    goto LABEL_84;
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 6;
          if ( !v14 )
          {
LABEL_19:
            if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v7[1].Blink) & 0x2000) != 0
              && BYTE1(v7[1].Blink) >= 5u )
            {
              WPP_SF_(v7[1].Flink, 45, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
              v7 = WPP_GLOBAL_Control;
            }
            if ( RasmanShuttingDown || g_fModemPresent || !lpEventData || lpEventData[1] != 5 || dwEventType != 0x8000 )
              goto LABEL_104;
            if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v7[1].Blink) & 0x2000) != 0
              && BYTE1(v7[1].Blink) >= 5u )
            {
              WPP_SF_s(v7[1].Flink, 46, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, lpEventData + 7);
            }
            g_fModemPresent = 1;
            ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, _DWORD *, LPVOID))RastapiUpdateTapiService)(
              v7,
              v8,
              lpEventData,
              lpContext);
            goto LABEL_103;
          }
          v15 = v14 - 2;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 == 19 )
              {
                if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                  && BYTE1(v7[1].Blink) >= 5u )
                {
                  WPP_SF_(v7[1].Flink, 44, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                }
                HandleSessionChange(dwEventType, lpEventData, lpEventData, lpContext);
                v7 = WPP_GLOBAL_Control;
                goto LABEL_19;
              }
LABEL_104:
              if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                && BYTE1(v7[1].Blink) >= 6u )
              {
                WPP_SF_d(v7[1].Flink, 47, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, 0);
              }
              return 0;
            }
            goto LABEL_70;
          }
          if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v7[1].Blink) & 0x2000) != 0
            && BYTE1(v7[1].Blink) >= 5u )
          {
            WPP_SF_d(v7[1].Flink, 36, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, dwEventType);
            v7 = WPP_GLOBAL_Control;
          }
          if ( dwEventType )
          {
            if ( dwEventType != 1 )
            {
              switch ( dwEventType )
              {
                case 6u:
                  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                    && BYTE1(v7[1].Blink) >= 5u )
                  {
                    WPP_SF_(v7[1].Flink, 39, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                  }
                  DropAllActiveConnectionsWith(9);
                  v7 = WPP_GLOBAL_Control;
                  break;
                case 7u:
                  goto LABEL_55;
                case 8u:
                  break;
                default:
                  if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  {
LABEL_74:
                    if ( dwEventType - 5 <= 1 )
                      goto LABEL_104;
                    HandleSessionChange(dwEventType, lpEventData, lpEventData, lpContext);
                    goto LABEL_103;
                  }
                  if ( (HIDWORD(v7[1].Blink) & 0x2000) == 0 || BYTE1(v7[1].Blink) < 5u )
                  {
LABEL_70:
                    if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                      && BYTE1(v7[1].Blink) >= 5u )
                    {
                      WPP_SF_(v7[1].Flink, 43, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                      v7 = WPP_GLOBAL_Control;
                    }
                    goto LABEL_74;
                  }
                  WPP_SF_(v7[1].Flink, 42, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
LABEL_69:
                  v7 = WPP_GLOBAL_Control;
                  goto LABEL_70;
              }
              if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
LABEL_59:
                RefreshDevices(v7, v8, lpEventData, lpContext);
                VpnProfileActiveHandleSleepResume(0);
                goto LABEL_69;
              }
              if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 5u )
              {
                WPP_SF_(v7[1].Flink, 40, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
                v7 = WPP_GLOBAL_Control;
              }
LABEL_55:
              if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v7[1].Blink) & 0x2000) != 0
                && BYTE1(v7[1].Blink) >= 5u )
              {
                WPP_SF_(v7[1].Flink, 41, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
              }
              goto LABEL_59;
            }
            if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
LABEL_68:
              DropAllActiveConnectionsWith(9);
              goto LABEL_69;
            }
            if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 5u )
            {
              WPP_SF_(v7[1].Flink, 37, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
              v7 = WPP_GLOBAL_Control;
            }
          }
          if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v7[1].Blink) & 0x2000) != 0
            && BYTE1(v7[1].Blink) >= 5u )
          {
            WPP_SF_(v7[1].Flink, 38, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
          }
          goto LABEL_68;
        }
LABEL_84:
        if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 5u )
          {
            WPP_SF_(v7[1].Flink, 32, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
            v7 = WPP_GLOBAL_Control;
          }
          if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v7[1].Blink) & 0x2000) != 0
            && BYTE1(v7[1].Blink) >= 5u )
          {
            LOBYTE(lpContext) = RasmanShuttingDown != 0;
            WPP_SF_c(v7[1].Flink, 33, WPP_101c73712a933762328fe4f7a83f8625_Traceguids, lpContext);
            v7 = WPP_GLOBAL_Control;
          }
        }
        if ( !RasmanShuttingDown )
        {
          dwCurrentState = 3;
          ServiceStatus.dwCurrentState = 3;
          SetServiceStatus((SERVICE_STATUS_HANDLE)hService, &ServiceStatus);
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 34, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
          }
          DropAllActiveConnectionsWith(8);
          PostQueuedCompletionStatus(hIoCompletionPort, 0, 0, &RO_CloseEvent);
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
            v7 = WPP_GLOBAL_Control;
          }
        }
        if ( !g_hGdi32 )
          goto LABEL_104;
        FreeLibrary(g_hGdi32);
        g_hGdi32 = 0;
        g_pfnDeviceCapabilitiesExA = 0;
        goto LABEL_103;
      }
    }
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
    && BYTE1(v7[1].Blink) >= 5u )
  {
    WPP_SF_(v7[1].Flink, 30, WPP_101c73712a933762328fe4f7a83f8625_Traceguids);
  }
  ServiceStatus.dwCurrentState = dwCurrentState;
  ServiceStatus.dwControlsAccepted = dwControlsAccepted;
  ServiceStatus.dwCheckPoint = CheckPoint++;
  SetServiceStatus((SERVICE_STATUS_HANDLE)hService, &ServiceStatus);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 5u )
      goto LABEL_104;
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      31,
      WPP_101c73712a933762328fe4f7a83f8625_Traceguids,
      (unsigned int)dwCurrentState);
LABEL_103:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_104;
  }
  return 0;
}

```

## disassembly

```asm
0x180034e30  mov     [rsp+arg_18], rbx
0x180034e35  push    rbp
0x180034e36  push    rsi
0x180034e37  push    rdi
0x180034e38  push    r14
0x180034e3a  push    r15
0x180034e3c  sub     rsp, 60h
0x180034e40  mov     rax, cs:__security_cookie
0x180034e47  xor     rax, rsp
0x180034e4a  mov     [rsp+88h+var_38], rax
0x180034e4f  mov     rsi, r8
0x180034e52  mov     edi, edx
0x180034e54  mov     ebx, ecx
0x180034e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e5d  lea     r14, WPP_GLOBAL_Control
0x180034e64  lea     r15, WPP_101c73712a933762328fe4f7a83f8625_Traceguids
0x180034e6b  mov     ebp, 2000h
0x180034e70  cmp     rcx, r14
0x180034e73  jz      short loc_180034E9F
0x180034e75  test    [rcx+1Ch], ebp
0x180034e78  jz      short loc_180034E9F
0x180034e7a  cmp     byte ptr [rcx+19h], 6
0x180034e7e  jb      short loc_180034E9F
0x180034e80  mov     rcx, [rcx+10h]
0x180034e84  mov     edx, 1Dh
0x180034e89  mov     r9d, ebx
0x180034e8c  mov     [rsp+88h+var_68], edi
0x180034e90  mov     r8, r15
0x180034e93  call    WPP_SF_Dd
0x180034e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e9f  mov     qword ptr [rsp+88h+ServiceStatus.dwCheckPoint], 0
0x180034ea8  xorps   xmm0, xmm0
0x180034eab  mov     edx, 20h ; ' '
0x180034eb0  mov     [rsp+88h+ServiceStatus.dwServiceType], edx
0x180034eb4  movdqu  xmmword ptr [rsp+88h+ServiceStatus.dwCurrentState], xmm0
0x180034eba  sub     ebx, 1
0x180034ebd  jz      loc_180035220
0x180034ec3  sub     ebx, 1
0x180034ec6  jz      loc_180035181
0x180034ecc  sub     ebx, 1
0x180034ecf  jz      loc_180035181
0x180034ed5  sub     ebx, 1
0x180034ed8  jz      loc_180035181
0x180034ede  sub     ebx, 1
0x180034ee1  jz      loc_180035220
0x180034ee7  sub     ebx, 6
0x180034eea  jz      short loc_180034F37
0x180034eec  sub     ebx, 2
0x180034eef  jz      loc_180034FD8
0x180034ef5  sub     ebx, 1
0x180034ef8  jz      loc_18003513E
0x180034efe  cmp     ebx, 13h
0x180034f01  jnz     loc_180035362
0x180034f07  cmp     rcx, r14
0x180034f0a  jz      short loc_180034F26
0x180034f0c  test    [rcx+1Ch], ebp
0x180034f0f  jz      short loc_180034F26
0x180034f11  cmp     byte ptr [rcx+19h], 5
0x180034f15  jb      short loc_180034F26
0x180034f17  mov     rcx, [rcx+10h]
0x180034f1b  lea     edx, [rbx+19h]
0x180034f1e  mov     r8, r15
0x180034f21  call    WPP_SF_
0x180034f26  mov     rdx, rsi
0x180034f29  mov     ecx, edi
0x180034f2b  call    HandleSessionChange
0x180034f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f37  cmp     rcx, r14
0x180034f3a  jz      short loc_180034F5F
0x180034f3c  test    [rcx+1Ch], ebp
0x180034f3f  jz      short loc_180034F5F
0x180034f41  cmp     byte ptr [rcx+19h], 5
0x180034f45  jb      short loc_180034F5F
0x180034f47  mov     rcx, [rcx+10h]
0x180034f4b  mov     edx, 2Dh ; '-'
0x180034f50  mov     r8, r15
0x180034f53  call    WPP_SF_
0x180034f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f5f  cmp     cs:RasmanShuttingDown, 0
0x180034f66  jnz     loc_180035362
0x180034f6c  cmp     cs:g_fModemPresent, 0
0x180034f73  jnz     loc_180035362
0x180034f79  test    rsi, rsi
0x180034f7c  jz      loc_180035362
0x180034f82  cmp     dword ptr [rsi+4], 5
0x180034f86  jnz     loc_180035362
0x180034f8c  cmp     edi, 8000h
0x180034f92  jnz     loc_180035362
0x180034f98  cmp     rcx, r14
0x180034f9b  jz      short loc_180034FBD
0x180034f9d  test    [rcx+1Ch], ebp
0x180034fa0  jz      short loc_180034FBD
0x180034fa2  cmp     byte ptr [rcx+19h], 5
0x180034fa6  jb      short loc_180034FBD
0x180034fa8  mov     rcx, [rcx+10h]
0x180034fac  lea     r9, [rsi+1Ch]
0x180034fb0  mov     edx, 2Eh ; '.'
0x180034fb5  mov     r8, r15
0x180034fb8  call    WPP_SF_s
0x180034fbd  mov     rax, cs:RastapiUpdateTapiService
0x180034fc4  mov     cs:g_fModemPresent, 1
0x180034fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fd3  jmp     loc_18003535B
0x180034fd8  cmp     rcx, r14
0x180034fdb  jz      short loc_180035003
0x180034fdd  test    [rcx+1Ch], ebp
0x180034fe0  jz      short loc_180035003
0x180034fe2  cmp     byte ptr [rcx+19h], 5
0x180034fe6  jb      short loc_180035003
0x180034fe8  mov     rcx, [rcx+10h]
0x180034fec  mov     edx, 24h ; '$'
0x180034ff1  mov     r9d, edi
0x180034ff4  mov     r8, r15
0x180034ff7  call    WPP_SF_d
0x180034ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180035003  mov     eax, edi
0x180035005  test    edi, edi
0x180035007  jz      loc_18003510C
0x18003500d  sub     eax, 1
0x180035010  jz      loc_1800350E4
0x180035016  sub     eax, 5
0x180035019  jz      short loc_18003505B
0x18003501b  sub     eax, 1
0x18003501e  jz      loc_1800350B5
0x180035024  cmp     eax, 1
0x180035027  jz      short loc_18003508D
0x180035029  cmp     rcx, r14
0x18003502c  jz      loc_180035166
0x180035032  test    [rcx+1Ch], ebp
0x180035035  jz      loc_18003513E
0x18003503b  cmp     byte ptr [rcx+19h], 5
0x18003503f  jb      loc_18003513E
0x180035045  mov     rcx, [rcx+10h]
0x180035049  mov     edx, 2Ah ; '*'
0x18003504e  mov     r8, r15
0x180035051  call    WPP_SF_
0x180035056  jmp     loc_180035137
0x18003505b  cmp     rcx, r14
0x18003505e  jz      short loc_18003507C
0x180035060  test    [rcx+1Ch], ebp
0x180035063  jz      short loc_18003507C
0x180035065  cmp     byte ptr [rcx+19h], 5
0x180035069  jb      short loc_18003507C
0x18003506b  mov     rcx, [rcx+10h]
0x18003506f  mov     edx, 27h ; '''
0x180035074  mov     r8, r15
0x180035077  call    WPP_SF_
0x18003507c  xor     edx, edx
0x18003507e  lea     ecx, [rdx+9]
0x180035081  call    DropAllActiveConnectionsWith
0x180035086  mov     rcx, cs:WPP_GLOBAL_Control
0x18003508d  cmp     rcx, r14
0x180035090  jz      short loc_1800350D6
0x180035092  test    [rcx+1Ch], ebp
0x180035095  jz      short loc_1800350B5
0x180035097  cmp     byte ptr [rcx+19h], 5
0x18003509b  jb      short loc_1800350B5
0x18003509d  mov     rcx, [rcx+10h]
0x1800350a1  mov     edx, 28h ; '('
0x1800350a6  mov     r8, r15
0x1800350a9  call    WPP_SF_
0x1800350ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350b5  cmp     rcx, r14
0x1800350b8  jz      short loc_1800350D6
0x1800350ba  test    [rcx+1Ch], ebp
0x1800350bd  jz      short loc_1800350D6
0x1800350bf  cmp     byte ptr [rcx+19h], 5
0x1800350c3  jb      short loc_1800350D6
0x1800350c5  mov     rcx, [rcx+10h]
0x1800350c9  mov     edx, 29h ; ')'
0x1800350ce  mov     r8, r15
0x1800350d1  call    WPP_SF_
0x1800350d6  call    RefreshDevices
0x1800350db  xor     ecx, ecx
0x1800350dd  call    VpnProfileActiveHandleSleepResume
0x1800350e2  jmp     short loc_180035137
0x1800350e4  cmp     rcx, r14
0x1800350e7  jz      short loc_18003512D
0x1800350e9  test    [rcx+1Ch], ebp
0x1800350ec  jz      short loc_18003510C
0x1800350ee  cmp     byte ptr [rcx+19h], 5
0x1800350f2  jb      short loc_18003510C
0x1800350f4  mov     rcx, [rcx+10h]
0x1800350f8  mov     edx, 25h ; '%'
0x1800350fd  mov     r8, r15
0x180035100  call    WPP_SF_
0x180035105  mov     rcx, cs:WPP_GLOBAL_Control
0x18003510c  cmp     rcx, r14
0x18003510f  jz      short loc_18003512D
0x180035111  test    [rcx+1Ch], ebp
0x180035114  jz      short loc_18003512D
0x180035116  cmp     byte ptr [rcx+19h], 5
0x18003511a  jb      short loc_18003512D
0x18003511c  mov     rcx, [rcx+10h]
0x180035120  mov     edx, 26h ; '&'
0x180035125  mov     r8, r15
0x180035128  call    WPP_SF_
0x18003512d  xor     edx, edx
0x18003512f  lea     ecx, [rdx+9]
0x180035132  call    DropAllActiveConnectionsWith
0x180035137  mov     rcx, cs:WPP_GLOBAL_Control
0x18003513e  cmp     rcx, r14
0x180035141  jz      short loc_180035166
0x180035143  test    [rcx+1Ch], ebp
0x180035146  jz      short loc_180035166
0x180035148  cmp     byte ptr [rcx+19h], 5
0x18003514c  jb      short loc_180035166
0x18003514e  mov     rcx, [rcx+10h]
0x180035152  mov     edx, 2Bh ; '+'
0x180035157  mov     r8, r15
0x18003515a  call    WPP_SF_
0x18003515f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035166  lea     eax, [rdi-5]
0x180035169  cmp     eax, 1
0x18003516c  jbe     loc_180035362
0x180035172  mov     rdx, rsi
0x180035175  mov     ecx, edi
0x180035177  call    HandleSessionChange
0x18003517c  jmp     loc_18003535B
0x180035181  cmp     rcx, r14
0x180035184  jz      short loc_1800351A2
0x180035186  test    [rcx+1Ch], ebp
0x180035189  jz      short loc_1800351A2
0x18003518b  cmp     byte ptr [rcx+19h], 5
0x18003518f  jb      short loc_1800351A2
0x180035191  mov     rcx, [rcx+10h]
0x180035195  mov     edx, 1Eh
0x18003519a  mov     r8, r15
0x18003519d  call    WPP_SF_
0x1800351a2  mov     eax, cs:dwCurrentState
0x1800351a8  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800351ad  mov     rcx, cs:hService; hServiceStatus
0x1800351b4  mov     [rsp+88h+ServiceStatus.dwCurrentState], eax
0x1800351b8  mov     eax, cs:dwControlsAccepted
0x1800351be  mov     [rsp+88h+ServiceStatus.dwControlsAccepted], eax
0x1800351c2  mov     eax, cs:CheckPoint
0x1800351c8  mov     [rsp+88h+ServiceStatus.dwCheckPoint], eax
0x1800351cc  inc     eax
0x1800351ce  mov     cs:CheckPoint, eax
0x1800351d4  call    cs:__imp_SetServiceStatus
0x1800351db  nop     dword ptr [rax+rax+00h]
0x1800351e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351e7  cmp     rcx, r14
0x1800351ea  jz      loc_180035386
0x1800351f0  test    [rcx+1Ch], ebp
0x1800351f3  jz      loc_180035362
0x1800351f9  cmp     byte ptr [rcx+19h], 5
0x1800351fd  jb      loc_180035362
0x180035203  mov     r9d, cs:dwCurrentState
0x18003520a  mov     edx, 1Fh
0x18003520f  mov     rcx, [rcx+10h]
0x180035213  mov     r8, r15
0x180035216  call    WPP_SF_d
0x18003521b  jmp     loc_18003535B
0x180035220  cmp     rcx, r14
0x180035223  jz      short loc_180035276
0x180035225  test    [rcx+1Ch], ebp
0x180035228  jz      short loc_180035243
0x18003522a  cmp     byte ptr [rcx+19h], 5
0x18003522e  jb      short loc_180035243
0x180035230  mov     rcx, [rcx+10h]
0x180035234  mov     r8, r15
0x180035237  call    WPP_SF_
0x18003523c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035243  cmp     rcx, r14
0x180035246  jz      short loc_180035276
0x180035248  test    [rcx+1Ch], ebp
0x18003524b  jz      short loc_180035276
0x18003524d  cmp     byte ptr [rcx+19h], 5
0x180035251  jb      short loc_180035276
0x180035253  cmp     cs:RasmanShuttingDown, 0
0x18003525a  mov     edx, 21h ; '!'
0x18003525f  mov     rcx, [rcx+10h]
0x180035263  mov     r8, r15
0x180035266  setnz   r9b
0x18003526a  call    WPP_SF_c
0x18003526f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035276  cmp     cs:RasmanShuttingDown, 0
0x18003527d  jnz     loc_18003532A
0x180035283  mov     rcx, cs:hService; hServiceStatus
0x18003528a  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18003528f  mov     eax, 3
0x180035294  mov     cs:dwCurrentState, eax
0x18003529a  mov     [rsp+88h+ServiceStatus.dwCurrentState], eax
0x18003529e  call    cs:__imp_SetServiceStatus
0x1800352a5  nop     dword ptr [rax+rax+00h]
0x1800352aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800352b1  cmp     rcx, r14
0x1800352b4  jz      short loc_1800352D2
0x1800352b6  test    [rcx+1Ch], ebp
0x1800352b9  jz      short loc_1800352D2
0x1800352bb  cmp     byte ptr [rcx+19h], 5
0x1800352bf  jb      short loc_1800352D2
0x1800352c1  mov     rcx, [rcx+10h]
0x1800352c5  mov     edx, 22h ; '"'
0x1800352ca  mov     r8, r15
0x1800352cd  call    WPP_SF_
0x1800352d2  xor     edx, edx
0x1800352d4  lea     ecx, [rdx+8]
0x1800352d7  call    DropAllActiveConnectionsWith
  ... truncated ...
```
