# WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)

- ea: `0x180005838`
- end: `0x180005a20`
- name: `?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z`
- size: `488`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180004e20`
- `0x180005b6c`

## callees

- `0x180005838`
- `0x180005eac`
- `0x180005ed4`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!Sleep` at `0x180005956`
- `KERNEL32!Sleep` at `0x180005956`
- `KERNEL32!GetTickCount` at `0x180005903`
- `KERNEL32!GetTickCount` at `0x18000593a`
- `KERNEL32!GetTickCount` at `0x180005903`
- `KERNEL32!GetTickCount` at `0x18000593a`
- `KERNEL32!GetLastError` at `0x1800058b2`
- `KERNEL32!GetLastError` at `0x18000596e`
- `KERNEL32!GetLastError` at `0x1800058b2`
- `KERNEL32!GetLastError` at `0x18000596e`
- `ADVAPI32!QueryServiceStatus` at `0x1800058a8`
- `ADVAPI32!QueryServiceStatus` at `0x180005964`
- `ADVAPI32!QueryServiceStatus` at `0x1800058a8`
- `ADVAPI32!QueryServiceStatus` at `0x180005964`

## pseudocode

```c
__int64 __fastcall WaitForServiceStopOrStart(SC_HANDLE hService, int a2, DWORD a3)
{
  DWORD LastError; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  bool v10; // zf
  DWORD TickCount; // esi
  bool v12; // zf
  DWORD v13; // ecx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  if ( !QueryServiceStatus(hService, &ServiceStatus) )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 77;
LABEL_10:
      WPP_SF_d(v7[2], v8, &WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
    return LastError;
  }
  if ( a2 )
    v10 = ServiceStatus.dwCurrentState == 1;
  else
    v10 = ServiceStatus.dwCurrentState == 4;
  if ( !v10 )
  {
    TickCount = GetTickCount();
    while ( QueryServiceStatus(hService, &ServiceStatus) )
    {
      if ( a2 )
      {
        if ( ServiceStatus.dwCurrentState == 1 )
          return 0;
        v12 = ServiceStatus.dwCurrentState == 3;
      }
      else
      {
        if ( ServiceStatus.dwCurrentState == 4 )
          return 0;
        v12 = ServiceStatus.dwCurrentState == 2;
      }
      if ( !v12 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            &WPP_db036311db36307996a98c23702218b2_Traceguids,
            ServiceStatus.dwCurrentState);
        }
        return 1062;
      }
      if ( GetTickCount() - TickCount > a3 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_db036311db36307996a98c23702218b2_Traceguids);
        }
        return 1460;
      }
      v13 = 5000;
      if ( ServiceStatus.dwWaitHint >> 1 < 0x1388 )
        v13 = ServiceStatus.dwWaitHint >> 1;
      Sleep(v13);
    }
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 78;
      goto LABEL_10;
    }
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x180005838  push    rbx
0x18000583a  push    rbp
0x18000583b  push    rsi
0x18000583c  push    rdi
0x18000583d  push    r12
0x18000583f  push    r15
0x180005841  sub     rsp, 58h
0x180005845  mov     rax, cs:__security_cookie
0x18000584c  xor     rax, rsp
0x18000584f  mov     [rsp+88h+var_48], rax
0x180005854  xorps   xmm0, xmm0
0x180005857  mov     ebp, r8d
0x18000585a  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18000585f  mov     edi, edx
0x180005861  mov     rbx, rcx
0x180005864  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180005869  mov     rcx, cs:WPP_GLOBAL_Control
0x180005870  lea     r15, WPP_GLOBAL_Control
0x180005877  lea     r12, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18000587e  cmp     rcx, r15
0x180005881  jz      short loc_1800058A0
0x180005883  test    byte ptr [rcx+1Ch], 2
0x180005887  jz      short loc_1800058A0
0x180005889  cmp     byte ptr [rcx+19h], 5
0x18000588d  jb      short loc_1800058A0
0x18000588f  mov     rcx, [rcx+10h]
0x180005893  mov     edx, 4Ch ; 'L'
0x180005898  mov     r8, r12
0x18000589b  call    WPP_SF_
0x1800058a0  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800058a5  mov     rcx, rbx; hService
0x1800058a8  call    cs:__imp_QueryServiceStatus
0x1800058ae  test    eax, eax
0x1800058b0  jnz     short loc_1800058ED
0x1800058b2  call    cs:__imp_GetLastError
0x1800058b8  mov     ebx, eax
0x1800058ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058c1  cmp     rcx, r15
0x1800058c4  jz      short loc_1800058E6
0x1800058c6  test    byte ptr [rcx+1Ch], 2
0x1800058ca  jz      short loc_1800058E6
0x1800058cc  cmp     byte ptr [rcx+19h], 2
0x1800058d0  jb      short loc_1800058E6
0x1800058d2  mov     edx, 4Dh ; 'M'
0x1800058d7  mov     rcx, [rcx+10h]
0x1800058db  mov     r9d, ebx
0x1800058de  mov     r8, r12
0x1800058e1  call    WPP_SF_d
0x1800058e6  mov     eax, ebx
0x1800058e8  jmp     loc_180005A06
0x1800058ed  test    edi, edi
0x1800058ef  jz      short loc_1800058F8
0x1800058f1  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 1
0x1800058f6  jmp     short loc_1800058FD
0x1800058f8  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x1800058fd  jz      loc_180005A04
0x180005903  call    cs:__imp_GetTickCount
0x180005909  mov     esi, eax
0x18000590b  jmp     short loc_18000595C
0x18000590d  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x180005912  test    edi, edi
0x180005914  jz      short loc_180005926
0x180005916  cmp     r9d, 1
0x18000591a  jz      loc_180005A04
0x180005920  cmp     r9d, 3
0x180005924  jmp     short loc_180005934
0x180005926  cmp     r9d, 4
0x18000592a  jz      loc_180005A04
0x180005930  cmp     r9d, 2
0x180005934  jnz     loc_1800059D4
0x18000593a  call    cs:__imp_GetTickCount
0x180005940  sub     eax, esi
0x180005942  cmp     eax, ebp
0x180005944  ja      short loc_1800059A4
0x180005946  mov     eax, [rsp+88h+ServiceStatus.dwWaitHint]
0x18000594a  mov     ecx, 1388h
0x18000594f  shr     eax, 1
0x180005951  cmp     eax, ecx
0x180005953  cmovb   ecx, eax; dwMilliseconds
0x180005956  call    cs:__imp_Sleep
0x18000595c  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180005961  mov     rcx, rbx; hService
0x180005964  call    cs:__imp_QueryServiceStatus
0x18000596a  test    eax, eax
0x18000596c  jnz     short loc_18000590D
0x18000596e  call    cs:__imp_GetLastError
0x180005974  mov     ebx, eax
0x180005976  mov     rcx, cs:WPP_GLOBAL_Control
0x18000597d  cmp     rcx, r15
0x180005980  jz      loc_1800058E6
0x180005986  test    byte ptr [rcx+1Ch], 2
0x18000598a  jz      loc_1800058E6
0x180005990  cmp     byte ptr [rcx+19h], 2
0x180005994  jb      loc_1800058E6
0x18000599a  mov     edx, 4Eh ; 'N'
0x18000599f  jmp     loc_1800058D7
0x1800059a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059ab  cmp     rcx, r15
0x1800059ae  jz      short loc_1800059CD
0x1800059b0  test    byte ptr [rcx+1Ch], 2
0x1800059b4  jz      short loc_1800059CD
0x1800059b6  cmp     byte ptr [rcx+19h], 2
0x1800059ba  jb      short loc_1800059CD
0x1800059bc  mov     rcx, [rcx+10h]
0x1800059c0  mov     edx, 50h ; 'P'
0x1800059c5  mov     r8, r12
0x1800059c8  call    WPP_SF_
0x1800059cd  mov     eax, 5B4h
0x1800059d2  jmp     short loc_180005A06
0x1800059d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059db  cmp     rcx, r15
0x1800059de  jz      short loc_1800059FD
0x1800059e0  test    byte ptr [rcx+1Ch], 2
0x1800059e4  jz      short loc_1800059FD
0x1800059e6  cmp     byte ptr [rcx+19h], 2
0x1800059ea  jb      short loc_1800059FD
0x1800059ec  mov     rcx, [rcx+10h]
0x1800059f0  mov     edx, 4Fh ; 'O'
0x1800059f5  mov     r8, r12
0x1800059f8  call    WPP_SF_d
0x1800059fd  mov     eax, 426h
0x180005a02  jmp     short loc_180005A06
0x180005a04  xor     eax, eax
0x180005a06  mov     rcx, [rsp+88h+var_48]
0x180005a0b  xor     rcx, rsp; StackCookie
0x180005a0e  call    __security_check_cookie
0x180005a13  add     rsp, 58h
0x180005a17  pop     r15
0x180005a19  pop     r12
0x180005a1b  pop     rdi
0x180005a1c  pop     rsi
0x180005a1d  pop     rbp
0x180005a1e  pop     rbx
0x180005a1f  retn
```
