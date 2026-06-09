# CommonUtil::UtilGetLatestActiveLogonSession(void * *,_LUID *,ulong *)

- ea: `0x180107188`
- end: `0x180107441`
- name: `?UtilGetLatestActiveLogonSession@CommonUtil@@YAJPEAPEAXPEAU_LUID@@PEAK@Z`
- size: `697`
- prototype: `__int64 __fastcall(PHANDLE phToken, void **, struct _LUID *, unsigned int *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18014e31c`
- `0x180209ea0`
- `0x18022bc00`
- `0x18022d034`
- `0x18022d2f0`

## callees

- `0x180107188`
- `0x180108d8d`
- `0x180108e18`
- `0x180108e2a`
- `0x180108e4e`
- `0x180108e54`
- `0x180108edf`
- `0x180108ef1`
- `0x18010cb40`
- `0x180119740`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801073d1`
- `KERNEL32!GetLastError` at `0x1801073d1`
- `ADVAPI32!IsWellKnownSid` at `0x1801072bb`
- `ADVAPI32!IsWellKnownSid` at `0x1801072d4`
- `ADVAPI32!IsWellKnownSid` at `0x1801072ed`
- `ADVAPI32!IsWellKnownSid` at `0x1801072bb`
- `ADVAPI32!IsWellKnownSid` at `0x1801072d4`
- `ADVAPI32!IsWellKnownSid` at `0x1801072ed`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetLatestActiveLogonSession(
        PHANDLE phToken,
        void **a2,
        struct _LUID *a3,
        unsigned int *a4)
{
  NTSTATUS v6; // eax
  signed int v7; // eax
  signed int v8; // esi
  LARGE_INTEGER LogonTime; // rdi
  ULONG Session; // r12d
  void *v11; // rbx
  int v12; // r14d
  struct _LUID *v13; // rdx
  NTSTATUS LogonSessionData_0; // eax
  signed int v15; // eax
  PSECURITY_LOGON_SESSION_DATA v16; // rcx
  PSECURITY_LOGON_SESSION_DATA v17; // rax
  int v18; // r15d
  signed int LastError; // eax
  LPWSTR ppBuffer; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+48h] [rbp-28h] BYREF
  ULONG LogonSessionCount; // [rsp+50h] [rbp-20h] BYREF
  PLUID LogonSessionList; // [rsp+58h] [rbp-18h] BYREF
  DWORD pBytesReturned; // [rsp+60h] [rbp-10h] BYREF

  if ( !phToken )
    return 2147942487LL;
  *phToken = 0;
  LogonSessionCount = 0;
  LogonSessionList = 0;
  v6 = LsaEnumerateLogonSessions_0(&LogonSessionCount, &LogonSessionList);
  v7 = LsaNtStatusToWinError_0(v6);
  v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    v8 = v7;
  _mm_lfence();
  if ( v8 >= 0 )
  {
    LogonTime.QuadPart = 0;
    Session = 0;
    v11 = 0;
    v12 = 0;
    if ( !LogonSessionCount )
      goto LABEL_47;
    while ( 1 )
    {
      v13 = &LogonSessionList[v12];
      if ( v13->LowPart == 999 )
        break;
      if ( LogonSessionList[v12].LowPart != 997 )
        goto LABEL_11;
LABEL_12:
      if ( !v13->HighPart )
        goto LABEL_37;
LABEL_13:
      ppLogonSessionData = 0;
      LogonSessionData_0 = LsaGetLogonSessionData_0(&LogonSessionList[v12], &ppLogonSessionData);
      v15 = LsaNtStatusToWinError_0(LogonSessionData_0);
      v16 = ppLogonSessionData;
      v8 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 <= 0 )
        v8 = v15;
      if ( v8 >= 0 )
      {
        if ( !ppLogonSessionData->Session
          || ppLogonSessionData->LogonType != 2
          && ppLogonSessionData->LogonType != 4
          && ppLogonSessionData->LogonType != 10 )
        {
          goto LABEL_36;
        }
        if ( !IsWellKnownSid(ppLogonSessionData->Sid, WinNetworkServiceSid)
          && !IsWellKnownSid(ppLogonSessionData->Sid, WinLocalServiceSid)
          && !IsWellKnownSid(ppLogonSessionData->Sid, WinServiceSid) )
        {
          v17 = ppLogonSessionData;
          if ( ppLogonSessionData->LogonDomain.Length != 32 )
            goto LABEL_26;
          if ( wcsicmp(ppLogonSessionData->LogonDomain.Buffer, L"Font Driver Host") )
          {
            v17 = ppLogonSessionData;
LABEL_26:
            if ( v17->LogonDomain.Length == 28 )
            {
              if ( wcsicmp(v17->LogonDomain.Buffer, L"Window Manager") )
              {
                v17 = ppLogonSessionData;
                goto LABEL_29;
              }
            }
            else
            {
LABEL_29:
              ppBuffer = 0;
              pBytesReturned = 0;
              if ( WTSQuerySessionInformationW_0(0, v17->Session, WTSSessionInfo, &ppBuffer, &pBytesReturned) )
              {
                v18 = *(_DWORD *)ppBuffer;
                WTSFreeMemory_0(ppBuffer);
                v16 = ppLogonSessionData;
                if ( ppLogonSessionData->LogonTime.QuadPart > LogonTime.QuadPart && !v18 )
                {
                  LogonTime = ppLogonSessionData->LogonTime;
                  Session = ppLogonSessionData->Session;
                  v11 = (void *)LogonSessionList[v12];
                }
LABEL_36:
                LsaFreeReturnBuffer_0(v16);
                goto LABEL_37;
              }
            }
          }
        }
        v16 = ppLogonSessionData;
      }
      if ( v16 )
        goto LABEL_36;
LABEL_37:
      if ( ++v12 >= LogonSessionCount )
      {
        if ( Session )
        {
          if ( !WTSQueryUserToken_0(Session, phToken) )
          {
            LastError = GetLastError();
            v8 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v8 = LastError;
          }
          if ( v8 >= 0 )
          {
            if ( a3 )
              a3->LowPart = Session;
            if ( a2 )
              *a2 = v11;
          }
          goto LABEL_48;
        }
LABEL_47:
        v8 = -2147023728;
        goto LABEL_48;
      }
    }
    if ( !v13->HighPart )
      goto LABEL_37;
LABEL_11:
    if ( LogonSessionList[v12].LowPart != 996 )
      goto LABEL_13;
    goto LABEL_12;
  }
LABEL_48:
  if ( LogonSessionList )
    LsaFreeReturnBuffer_0(LogonSessionList);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180107188  mov     [rsp-38h+arg_18], rbx
0x18010718d  push    rbp
0x18010718e  push    rsi
0x18010718f  push    rdi
0x180107190  push    r12
0x180107192  push    r13
0x180107194  push    r14
0x180107196  push    r15
0x180107198  mov     rbp, rsp
0x18010719b  sub     rsp, 70h
0x18010719f  mov     rax, cs:__security_cookie
0x1801071a6  xor     rax, rsp
0x1801071a9  mov     [rbp+var_8], rax
0x1801071ad  xor     r15d, r15d
0x1801071b0  mov     [rbp+var_40], r8
0x1801071b4  mov     [rbp+var_38], rdx
0x1801071b8  mov     r13, rcx
0x1801071bb  test    rcx, rcx
0x1801071be  jnz     short loc_1801071CA
0x1801071c0  mov     eax, 80070057h
0x1801071c5  jmp     loc_18010741D
0x1801071ca  mov     [rcx], r15
0x1801071cd  lea     rdx, [rbp+LogonSessionList]; LogonSessionList
0x1801071d1  lea     rcx, [rbp+LogonSessionCount]; LogonSessionCount
0x1801071d5  mov     [rbp+LogonSessionCount], r15d
0x1801071d9  mov     [rbp+LogonSessionList], r15
0x1801071dd  call    LsaEnumerateLogonSessions_0
0x1801071e2  mov     ecx, eax; Status
0x1801071e4  call    LsaNtStatusToWinError_0
0x1801071e9  movzx   esi, ax
0x1801071ec  or      esi, 80070000h
0x1801071f2  test    eax, eax
0x1801071f4  cmovle  esi, eax
0x1801071f7  lfence
0x1801071fa  test    esi, esi
0x1801071fc  js      loc_18010740D
0x180107202  mov     rdi, r15
0x180107205  mov     r12d, r15d
0x180107208  mov     rbx, r15
0x18010720b  mov     r14d, r15d
0x18010720e  cmp     [rbp+LogonSessionCount], r15d
0x180107212  jbe     loc_180107408
0x180107218  mov     rax, [rbp+LogonSessionList]
0x18010721c  mov     ecx, r14d
0x18010721f  cmp     dword ptr [rax+rcx*8], 3E7h
0x180107226  lea     rdx, [rax+rcx*8]
0x18010722a  jnz     short loc_180107238
0x18010722c  cmp     [rdx+4], r15d
0x180107230  jz      loc_1801073B0
0x180107236  jmp     short loc_180107241
0x180107238  cmp     dword ptr [rax+rcx*8], 3E5h
0x18010723f  jz      short loc_18010724A
0x180107241  cmp     dword ptr [rax+rcx*8], 3E4h
0x180107248  jnz     short loc_180107254
0x18010724a  cmp     [rdx+4], r15d
0x18010724e  jz      loc_1801073B0
0x180107254  mov     rax, [rbp+LogonSessionList]
0x180107258  lea     rdx, [rbp+ppLogonSessionData]; ppLogonSessionData
0x18010725c  mov     ecx, r14d
0x18010725f  mov     [rbp+ppLogonSessionData], r15
0x180107263  lea     rcx, [rax+rcx*8]; LogonId
0x180107267  call    LsaGetLogonSessionData_0
0x18010726c  mov     ecx, eax; Status
0x18010726e  call    LsaNtStatusToWinError_0
0x180107273  mov     rcx, [rbp+ppLogonSessionData]
0x180107277  movzx   esi, ax
0x18010727a  or      esi, 80070000h
0x180107280  test    eax, eax
0x180107282  cmovle  esi, eax
0x180107285  mov     eax, esi
0x180107287  shr     eax, 1Fh
0x18010728a  test    al, al
0x18010728c  jnz     loc_1801073A6
0x180107292  cmp     [rcx+44h], r15d
0x180107296  jz      loc_1801073AB
0x18010729c  cmp     dword ptr [rcx+40h], 2
0x1801072a0  jz      short loc_1801072B2
0x1801072a2  cmp     dword ptr [rcx+40h], 4
0x1801072a6  jz      short loc_1801072B2
0x1801072a8  cmp     dword ptr [rcx+40h], 0Ah
0x1801072ac  jnz     loc_1801073AB
0x1801072b2  mov     rcx, [rcx+48h]; pSid
0x1801072b6  mov     edx, 18h; WellKnownSidType
0x1801072bb  call    cs:__imp_IsWellKnownSid
0x1801072c1  test    eax, eax
0x1801072c3  jnz     loc_1801073A2
0x1801072c9  mov     rcx, [rbp+ppLogonSessionData]
0x1801072cd  lea     edx, [rax+17h]; WellKnownSidType
0x1801072d0  mov     rcx, [rcx+48h]; pSid
0x1801072d4  call    cs:__imp_IsWellKnownSid
0x1801072da  test    eax, eax
0x1801072dc  jnz     loc_1801073A2
0x1801072e2  mov     rcx, [rbp+ppLogonSessionData]
0x1801072e6  lea     edx, [rax+0Ch]; WellKnownSidType
0x1801072e9  mov     rcx, [rcx+48h]; pSid
0x1801072ed  call    cs:__imp_IsWellKnownSid
0x1801072f3  test    eax, eax
0x1801072f5  jnz     loc_1801073A2
0x1801072fb  mov     rax, [rbp+ppLogonSessionData]
0x1801072ff  cmp     word ptr [rax+20h], 20h ; ' '
0x180107304  jnz     short loc_180107322
0x180107306  mov     rcx, [rax+28h]; String1
0x18010730a  lea     rdx, aFontDriverHost; "Font Driver Host"
0x180107311  call    _wcsicmp
0x180107316  test    eax, eax
0x180107318  jz      loc_1801073A2
0x18010731e  mov     rax, [rbp+ppLogonSessionData]
0x180107322  cmp     word ptr [rax+20h], 1Ch
0x180107327  jnz     short loc_180107341
0x180107329  mov     rcx, [rax+28h]; String1
0x18010732d  lea     rdx, aWindowManager; "Window Manager"
0x180107334  call    _wcsicmp
0x180107339  test    eax, eax
0x18010733b  jz      short loc_1801073A2
0x18010733d  mov     rax, [rbp+ppLogonSessionData]
0x180107341  lea     rcx, [rbp+var_10]
0x180107345  mov     [rbp+ppBuffer], r15
0x180107349  mov     [rsp+70h+pBytesReturned], rcx; pBytesReturned
0x18010734e  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180107352  mov     [rbp+var_10], r15d
0x180107356  xor     ecx, ecx; hServer
0x180107358  mov     edx, [rax+44h]; SessionId
0x18010735b  mov     r8d, 18h; WTSInfoClass
0x180107361  call    WTSQuerySessionInformationW_0
0x180107366  test    eax, eax
0x180107368  jz      short loc_1801073A2
0x18010736a  mov     rcx, [rbp+ppBuffer]; pMemory
0x18010736e  mov     r15d, [rcx]
0x180107371  call    WTSFreeMemory_0
0x180107376  mov     rcx, [rbp+ppLogonSessionData]; Buffer
0x18010737a  cmp     [rcx+50h], rdi
0x18010737e  jle     short loc_180107398
0x180107380  test    r15d, r15d
0x180107383  jnz     short loc_180107398
0x180107385  mov     rbx, [rbp+LogonSessionList]
0x180107389  mov     rdi, [rcx+50h]
0x18010738d  mov     r12d, [rcx+44h]
0x180107391  mov     eax, r14d
0x180107394  mov     rbx, [rbx+rax*8]
0x180107398  call    LsaFreeReturnBuffer_0
0x18010739d  xor     r15d, r15d
0x1801073a0  jmp     short loc_1801073B0
0x1801073a2  mov     rcx, [rbp+ppLogonSessionData]; Buffer
0x1801073a6  test    rcx, rcx
0x1801073a9  jz      short loc_1801073B0
0x1801073ab  call    LsaFreeReturnBuffer_0
0x1801073b0  inc     r14d
0x1801073b3  cmp     r14d, [rbp+LogonSessionCount]
0x1801073b7  jb      loc_180107218
0x1801073bd  test    r12d, r12d
0x1801073c0  jz      short loc_180107408
0x1801073c2  mov     rdx, r13; phToken
0x1801073c5  mov     ecx, r12d; SessionId
0x1801073c8  call    WTSQueryUserToken_0
0x1801073cd  test    eax, eax
0x1801073cf  jnz     short loc_1801073E5
0x1801073d1  call    cs:__imp_GetLastError
0x1801073d7  movzx   esi, ax
0x1801073da  or      esi, 80070000h
0x1801073e0  test    eax, eax
0x1801073e2  cmovle  esi, eax
0x1801073e5  mov     eax, esi
0x1801073e7  shr     eax, 1Fh
0x1801073ea  test    al, al
0x1801073ec  jnz     short loc_18010740D
0x1801073ee  mov     rax, [rbp+var_40]
0x1801073f2  test    rax, rax
0x1801073f5  jz      short loc_1801073FA
0x1801073f7  mov     [rax], r12d
0x1801073fa  mov     rax, [rbp+var_38]
0x1801073fe  test    rax, rax
0x180107401  jz      short loc_18010740D
0x180107403  mov     [rax], rbx
0x180107406  jmp     short loc_18010740D
0x180107408  mov     esi, 80070490h
0x18010740d  mov     rcx, [rbp+LogonSessionList]; Buffer
0x180107411  test    rcx, rcx
0x180107414  jz      short loc_18010741B
0x180107416  call    LsaFreeReturnBuffer_0
0x18010741b  mov     eax, esi
0x18010741d  mov     rcx, [rbp+var_8]
0x180107421  xor     rcx, rsp; StackCookie
0x180107424  call    __security_check_cookie
0x180107429  mov     rbx, [rsp+70h+arg_18]
0x180107431  add     rsp, 70h
0x180107435  pop     r15
0x180107437  pop     r14
0x180107439  pop     r13
0x18010743b  pop     r12
0x18010743d  pop     rdi
0x18010743e  pop     rsi
0x18010743f  pop     rbp
0x180107440  retn
```
