# FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)

- ea: `0x18000568c`
- end: `0x180005831`
- name: `?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z`
- size: `421`
- prototype: `__int64 __fastcall(LPCWSTR lpMachineName, LPCWSTR lpServiceName, struct SC_HANDLE__ **, struct SC_HANDLE__ **, unsigned int, DWORD dwDesiredAccess, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004e20`
- `0x180005a28`
- `0x180005b6c`

## callees

- `0x1800055a0`
- `0x18000568c`
- `0x180005eac`
- `0x180005ed4`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005713`
- `KERNEL32!GetLastError` at `0x180005765`
- `KERNEL32!GetLastError` at `0x1800057b5`
- `KERNEL32!GetLastError` at `0x180005713`
- `KERNEL32!GetLastError` at `0x180005765`
- `KERNEL32!GetLastError` at `0x1800057b5`
- `ADVAPI32!QueryServiceStatus` at `0x1800057ab`
- `ADVAPI32!QueryServiceStatus` at `0x1800057ab`
- `ADVAPI32!OpenSCManagerW` at `0x180005703`
- `ADVAPI32!OpenSCManagerW` at `0x180005703`
- `ADVAPI32!OpenServiceW` at `0x180005757`
- `ADVAPI32!OpenServiceW` at `0x180005757`

## pseudocode

```c
__int64 __fastcall FaxOpenService(
        LPCWSTR lpMachineName,
        LPCWSTR lpServiceName,
        struct SC_HANDLE__ **a3,
        struct SC_HANDLE__ **a4,
        unsigned int a5,
        DWORD dwDesiredAccess,
        unsigned int *a7)
{
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rsi
  SC_HANDLE v13; // rdi
  DWORD LastError; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  SC_HANDLE v17; // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v11 = OpenSCManagerW(lpMachineName, 0, 1u);
  v12 = v11;
  if ( v11 )
  {
    v17 = OpenServiceW(v11, lpServiceName, dwDesiredAccess);
    v13 = v17;
    if ( v17 )
    {
      if ( a7 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !QueryServiceStatus(v17, &ServiceStatus) )
        {
          LastError = GetLastError();
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 13;
            goto LABEL_21;
          }
          goto LABEL_22;
        }
        *a7 = ServiceStatus.dwCurrentState;
      }
      *a3 = v12;
      LastError = 0;
      *a4 = v13;
      return LastError;
    }
    LastError = GetLastError();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 12;
      goto LABEL_21;
    }
  }
  else
  {
    v13 = 0;
    LastError = GetLastError();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 11;
LABEL_21:
      WPP_SF_d(v15[2], v16, &WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
  }
LABEL_22:
  if ( LastError )
    FaxCloseService(v12, v13);
  return LastError;
}

```

## disassembly

```asm
0x18000568c  push    rbx
0x18000568e  push    rbp
0x18000568f  push    rsi
0x180005690  push    rdi
0x180005691  push    r12
0x180005693  push    r14
0x180005695  push    r15
0x180005697  sub     rsp, 50h
0x18000569b  mov     rax, cs:__security_cookie
0x1800056a2  xor     rax, rsp
0x1800056a5  mov     [rsp+88h+var_48], rax
0x1800056aa  mov     r12d, [rsp+88h+dwDesiredAccess]
0x1800056b2  mov     r15, r9
0x1800056b5  mov     rbx, [rsp+88h+arg_30]
0x1800056bd  mov     r14, r8
0x1800056c0  mov     rbp, rdx
0x1800056c3  mov     rdi, rcx
0x1800056c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056cd  lea     rax, WPP_GLOBAL_Control
0x1800056d4  cmp     rcx, rax
0x1800056d7  jz      short loc_1800056FA
0x1800056d9  test    byte ptr [rcx+1Ch], 2
0x1800056dd  jz      short loc_1800056FA
0x1800056df  cmp     byte ptr [rcx+19h], 5
0x1800056e3  jb      short loc_1800056FA
0x1800056e5  mov     rcx, [rcx+10h]
0x1800056e9  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1800056f0  mov     edx, 0Ah
0x1800056f5  call    WPP_SF_
0x1800056fa  xor     edx, edx; lpDatabaseName
0x1800056fc  mov     rcx, rdi; lpMachineName
0x1800056ff  lea     r8d, [rdx+1]; dwDesiredAccess
0x180005703  call    cs:__imp_OpenSCManagerW
0x180005709  mov     rsi, rax
0x18000570c  test    rax, rax
0x18000570f  jnz     short loc_18000574E
0x180005711  xor     edi, edi
0x180005713  call    cs:__imp_GetLastError
0x180005719  mov     ebx, eax
0x18000571b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005722  lea     rax, WPP_GLOBAL_Control
0x180005729  cmp     rcx, rax
0x18000572c  jz      loc_1800057F4
0x180005732  test    byte ptr [rcx+1Ch], 2
0x180005736  jz      loc_1800057F4
0x18000573c  cmp     byte ptr [rcx+19h], 2
0x180005740  jb      loc_1800057F4
0x180005746  lea     edx, [rsi+0Bh]
0x180005749  jmp     loc_1800057E1
0x18000574e  mov     r8d, r12d; dwDesiredAccess
0x180005751  mov     rdx, rbp; lpServiceName
0x180005754  mov     rcx, rsi; hSCManager
0x180005757  call    cs:__imp_OpenServiceW
0x18000575d  mov     rdi, rax
0x180005760  test    rax, rax
0x180005763  jnz     short loc_180005791
0x180005765  call    cs:__imp_GetLastError
0x18000576b  mov     ebx, eax
0x18000576d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005774  lea     rax, WPP_GLOBAL_Control
0x18000577b  cmp     rcx, rax
0x18000577e  jz      short loc_1800057F4
0x180005780  test    byte ptr [rcx+1Ch], 2
0x180005784  jz      short loc_1800057F4
0x180005786  cmp     byte ptr [rcx+19h], 2
0x18000578a  jb      short loc_1800057F4
0x18000578c  lea     edx, [rdi+0Ch]
0x18000578f  jmp     short loc_1800057E1
0x180005791  test    rbx, rbx
0x180005794  jz      short loc_18000580B
0x180005796  xorps   xmm0, xmm0
0x180005799  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18000579e  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x1800057a3  mov     rcx, rdi; hService
0x1800057a6  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800057ab  call    cs:__imp_QueryServiceStatus
0x1800057b1  test    eax, eax
0x1800057b3  jnz     short loc_180005805
0x1800057b5  call    cs:__imp_GetLastError
0x1800057bb  mov     ebx, eax
0x1800057bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057c4  lea     rax, WPP_GLOBAL_Control
0x1800057cb  cmp     rcx, rax
0x1800057ce  jz      short loc_1800057F4
0x1800057d0  test    byte ptr [rcx+1Ch], 2
0x1800057d4  jz      short loc_1800057F4
0x1800057d6  cmp     byte ptr [rcx+19h], 2
0x1800057da  jb      short loc_1800057F4
0x1800057dc  mov     edx, 0Dh
0x1800057e1  mov     rcx, [rcx+10h]
0x1800057e5  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1800057ec  mov     r9d, ebx
0x1800057ef  call    WPP_SF_d
0x1800057f4  test    ebx, ebx
0x1800057f6  jz      short loc_180005813
0x1800057f8  mov     rdx, rdi; SC_HANDLE
0x1800057fb  mov     rcx, rsi; hSCObject
0x1800057fe  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x180005803  jmp     short loc_180005813
0x180005805  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x180005809  mov     [rbx], eax
0x18000580b  mov     [r14], rsi
0x18000580e  xor     ebx, ebx
0x180005810  mov     [r15], rdi
0x180005813  mov     eax, ebx
0x180005815  mov     rcx, [rsp+88h+var_48]
0x18000581a  xor     rcx, rsp; StackCookie
0x18000581d  call    __security_check_cookie
0x180005822  add     rsp, 50h
0x180005826  pop     r15
0x180005828  pop     r14
0x18000582a  pop     r12
0x18000582c  pop     rdi
0x18000582d  pop     rsi
0x18000582e  pop     rbp
0x18000582f  pop     rbx
0x180005830  retn
```
