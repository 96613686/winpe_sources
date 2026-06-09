# NatStartServiceSync(ushort const *,ulong,ulong)

- ea: `0x180039764`
- end: `0x1800399c1`
- name: `?NatStartServiceSync@@YAJPEBGKK@Z`
- size: `605`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18006e294`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180039764`
- `0x1800399c8`
- `0x180039b20`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039929`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800398d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800398d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800397d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800398bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800397d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800398bc`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003982f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003982f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800398a4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800398a4`

## pseudocode

```c
__int64 __fastcall NatStartServiceSync(LPCWSTR lpServiceName)
{
  DWORD TickCount; // esi
  unsigned int v3; // edx
  int v4; // eax
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // edi
  signed int LastError; // eax
  unsigned int v11; // eax
  DWORD v12; // ecx
  signed int v13; // eax
  SC_HANDLE hService; // [rsp+20h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  hService = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  TickCount = GetTickCount();
  v4 = NatOpenService(lpServiceName, v3, &hService);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = 0;
    if ( StartServiceW(hService, 0, 0) )
      goto LABEL_21;
    LastError = GetLastError();
    if ( LastError != 1056 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      if ( v5 >= 0 )
        goto LABEL_46;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v7 = 186;
LABEL_44:
      v8 = (unsigned int)v5;
      goto LABEL_45;
    }
LABEL_20:
    v9 = 1;
LABEL_21:
    while ( !v9 )
    {
      if ( !QueryServiceStatus(hService, &ServiceStatus) )
      {
        v13 = GetLastError();
        v5 = v13;
        if ( v13 > 0 )
          v5 = (unsigned __int16)v13 | 0x80070000;
        if ( v5 < 0 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = 187;
            goto LABEL_44;
          }
        }
        break;
      }
      if ( ServiceStatus.dwCurrentState == 4 )
        goto LABEL_20;
      if ( ServiceStatus.dwCurrentState != 2 )
      {
        v5 = -2147023834;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 189;
          goto LABEL_44;
        }
        break;
      }
      v11 = GetTickCount() - TickCount;
      if ( v11 >= 0x3A98 )
      {
        v5 = -2147024638;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 188;
          goto LABEL_44;
        }
        break;
      }
      v12 = 50;
      if ( 15000 - v11 < 0x32 )
        v12 = 15000 - v11;
      Sleep(v12);
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 185;
      v8 = (unsigned int)v4;
LABEL_45:
      WPP_SF_d(v6[2], v7, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v8);
    }
  }
LABEL_46:
  NatCloseServiceHandle(hService);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      190,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039764  push    rbx
0x180039766  push    rsi
0x180039767  push    rdi
0x180039768  push    r12
0x18003976a  push    r14
0x18003976c  push    r15
0x18003976e  sub     rsp, 58h
0x180039772  mov     rax, cs:__security_cookie
0x180039779  xor     rax, rsp
0x18003977c  mov     [rsp+88h+var_40], rax
0x180039781  mov     rbx, rcx
0x180039784  mov     rcx, cs:WPP_GLOBAL_Control
0x18003978b  lea     r15, WPP_GLOBAL_Control
0x180039792  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180039799  mov     r14d, 200h
0x18003979f  cmp     rcx, r15
0x1800397a2  jz      short loc_1800397C1
0x1800397a4  test    [rcx+1Ch], r14d
0x1800397a8  jz      short loc_1800397C1
0x1800397aa  cmp     byte ptr [rcx+19h], 6
0x1800397ae  jb      short loc_1800397C1
0x1800397b0  mov     rcx, [rcx+10h]
0x1800397b4  mov     edx, 0B8h
0x1800397b9  mov     r8, r12
0x1800397bc  call    WPP_SF_
0x1800397c1  xorps   xmm0, xmm0
0x1800397c4  mov     [rsp+88h+hService], 0
0x1800397cd  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x1800397d2  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800397d7  call    cs:__imp_GetTickCount
0x1800397dd  lea     r8, [rsp+88h+hService]; struct SC_HANDLE__ **
0x1800397e2  mov     rcx, rbx; lpServiceName
0x1800397e5  mov     esi, eax
0x1800397e7  call    ?NatOpenService@@YAJPEBGKPEAPEAUSC_HANDLE__@@@Z; NatOpenService(ushort const *,ulong,SC_HANDLE__ * *)
0x1800397ec  mov     ebx, eax
0x1800397ee  test    eax, eax
0x1800397f0  jns     short loc_180039823
0x1800397f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800397f9  cmp     rcx, r15
0x1800397fc  jz      loc_18003996E
0x180039802  test    [rcx+1Ch], r14d
0x180039806  jz      loc_18003996E
0x18003980c  cmp     byte ptr [rcx+19h], 2
0x180039810  jb      loc_18003996E
0x180039816  mov     edx, 0B9h
0x18003981b  mov     r9d, eax
0x18003981e  jmp     loc_180039962
0x180039823  mov     rcx, [rsp+88h+hService]; hService
0x180039828  xor     r8d, r8d; lpServiceArgVectors
0x18003982b  xor     edx, edx; dwNumServiceArgs
0x18003982d  xor     edi, edi
0x18003982f  call    cs:__imp_StartServiceW
0x180039835  test    eax, eax
0x180039837  jnz     short loc_180039892
0x180039839  call    cs:__imp_GetLastError
0x18003983f  cmp     eax, 420h
0x180039844  jz      short loc_18003988D
0x180039846  test    eax, eax
0x180039848  jg      short loc_18003984E
0x18003984a  mov     ebx, eax
0x18003984c  jmp     short loc_180039857
0x18003984e  movzx   ebx, ax
0x180039851  or      ebx, 80070000h
0x180039857  test    ebx, ebx
0x180039859  jns     loc_18003996E
0x18003985f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039866  cmp     rcx, r15
0x180039869  jz      loc_18003996E
0x18003986f  test    [rcx+1Ch], r14d
0x180039873  jz      loc_18003996E
0x180039879  cmp     byte ptr [rcx+19h], 2
0x18003987d  jb      loc_18003996E
0x180039883  mov     edx, 0BAh
0x180039888  jmp     loc_18003995F
0x18003988d  mov     edi, 1
0x180039892  test    edi, edi
0x180039894  jnz     loc_18003996E
0x18003989a  mov     rcx, [rsp+88h+hService]; hService
0x18003989f  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800398a4  call    cs:__imp_QueryServiceStatus
0x1800398aa  test    eax, eax
0x1800398ac  jz      short loc_180039929
0x1800398ae  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x1800398b3  jz      short loc_18003988D
0x1800398b5  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 2
0x1800398ba  jnz     short loc_180039905
0x1800398bc  call    cs:__imp_GetTickCount
0x1800398c2  sub     eax, esi
0x1800398c4  mov     ecx, 3A98h
0x1800398c9  cmp     eax, ecx
0x1800398cb  jnb     short loc_1800398E1
0x1800398cd  mov     edx, ecx
0x1800398cf  lea     ecx, [rdi+32h]
0x1800398d2  sub     edx, eax
0x1800398d4  cmp     edx, ecx
0x1800398d6  cmovb   ecx, edx; dwMilliseconds
0x1800398d9  call    cs:__imp_Sleep
0x1800398df  jmp     short loc_180039892
0x1800398e1  mov     ebx, 80070102h
0x1800398e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398ed  cmp     rcx, r15
0x1800398f0  jz      short loc_18003996E
0x1800398f2  test    [rcx+1Ch], r14d
0x1800398f6  jz      short loc_18003996E
0x1800398f8  cmp     byte ptr [rcx+19h], 2
0x1800398fc  jb      short loc_18003996E
0x1800398fe  mov     edx, 0BCh
0x180039903  jmp     short loc_18003995F
0x180039905  mov     ebx, 80070426h
0x18003990a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039911  cmp     rcx, r15
0x180039914  jz      short loc_18003996E
0x180039916  test    [rcx+1Ch], r14d
0x18003991a  jz      short loc_18003996E
0x18003991c  cmp     byte ptr [rcx+19h], 2
0x180039920  jb      short loc_18003996E
0x180039922  mov     edx, 0BDh
0x180039927  jmp     short loc_18003995F
0x180039929  call    cs:__imp_GetLastError
0x18003992f  mov     ebx, eax
0x180039931  test    eax, eax
0x180039933  jle     short loc_18003993E
0x180039935  movzx   ebx, ax
0x180039938  or      ebx, 80070000h
0x18003993e  test    ebx, ebx
0x180039940  jns     short loc_18003996E
0x180039942  mov     rcx, cs:WPP_GLOBAL_Control
0x180039949  cmp     rcx, r15
0x18003994c  jz      short loc_18003996E
0x18003994e  test    [rcx+1Ch], r14d
0x180039952  jz      short loc_18003996E
0x180039954  cmp     byte ptr [rcx+19h], 2
0x180039958  jb      short loc_18003996E
0x18003995a  mov     edx, 0BBh
0x18003995f  mov     r9d, ebx
0x180039962  mov     rcx, [rcx+10h]
0x180039966  mov     r8, r12
0x180039969  call    WPP_SF_d
0x18003996e  mov     rcx, [rsp+88h+hService]; hSCObject
0x180039973  call    ?NatCloseServiceHandle@@YAXPEAUSC_HANDLE__@@@Z; NatCloseServiceHandle(SC_HANDLE__ *)
0x180039978  mov     rcx, cs:WPP_GLOBAL_Control
0x18003997f  cmp     rcx, r15
0x180039982  jz      short loc_1800399A4
0x180039984  test    [rcx+1Ch], r14d
0x180039988  jz      short loc_1800399A4
0x18003998a  cmp     byte ptr [rcx+19h], 6
0x18003998e  jb      short loc_1800399A4
0x180039990  mov     rcx, [rcx+10h]
0x180039994  mov     edx, 0BEh
0x180039999  mov     r9d, ebx
0x18003999c  mov     r8, r12
0x18003999f  call    WPP_SF_d
0x1800399a4  mov     eax, ebx
0x1800399a6  mov     rcx, [rsp+88h+var_40]
0x1800399ab  xor     rcx, rsp; StackCookie
0x1800399ae  call    __security_check_cookie
0x1800399b3  add     rsp, 58h
0x1800399b7  pop     r15
0x1800399b9  pop     r14
0x1800399bb  pop     r12
0x1800399bd  pop     rdi
0x1800399be  pop     rsi
0x1800399bf  pop     rbx
0x1800399c0  retn
```
