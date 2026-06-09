# CommonUtil::UtilSetupRasConnectionNotificationFromPPL(void *)

- ea: `0x18008de80`
- end: `0x18008e3d3`
- name: `?UtilSetupRasConnectionNotificationFromPPL@CommonUtil@@YAJPEAX@Z`
- size: `1363`
- prototype: `__int64 __fastcall(void **this, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008d01c`

## callees

- `0x1800809d0`
- `0x18008de80`
- `0x1800ccf98`
- `0x180101298`
- `0x180101348`
- `0x1801034d4`
- `0x180103640`
- `0x180104754`
- `0x1801054f0`
- `0x18010556c`
- `0x180106620`
- `0x18010cb40`
- `0x18010ce3c`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18008e302`
- `KERNEL32!TerminateProcess` at `0x18008e302`
- `KERNEL32!GetLastError` at `0x18008e1bf`
- `KERNEL32!GetLastError` at `0x18008e26d`
- `KERNEL32!GetLastError` at `0x18008e1bf`
- `KERNEL32!GetLastError` at `0x18008e26d`
- `KERNEL32!CloseHandle` at `0x18008dff0`
- `KERNEL32!CloseHandle` at `0x18008e35e`
- `KERNEL32!CloseHandle` at `0x18008e397`
- `KERNEL32!CloseHandle` at `0x18008e3a2`
- `KERNEL32!CloseHandle` at `0x18008dff0`
- `KERNEL32!CloseHandle` at `0x18008e35e`
- `KERNEL32!CloseHandle` at `0x18008e397`
- `KERNEL32!CloseHandle` at `0x18008e3a2`
- `KERNEL32!GetCurrentProcess` at `0x18008e14d`
- `KERNEL32!GetCurrentProcess` at `0x18008e14d`
- `KERNEL32!CreateNamedPipeW` at `0x18008def4`
- `KERNEL32!CreateNamedPipeW` at `0x18008def4`
- `KERNEL32!ConnectNamedPipe` at `0x18008e1ac`
- `KERNEL32!ConnectNamedPipe` at `0x18008e1ac`
- `KERNEL32!GetOverlappedResult` at `0x18008e263`
- `KERNEL32!GetOverlappedResult` at `0x18008e263`
- `ADVAPI32!RegCloseKey` at `0x18008dfdd`
- `ADVAPI32!RegCloseKey` at `0x18008e388`
- `ADVAPI32!RegCloseKey` at `0x18008dfdd`
- `ADVAPI32!RegCloseKey` at `0x18008e388`

## string_xrefs

- `0x18008e00a`: `InstallLocation`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilSetupRasConnectionNotificationFromPPL(void **this, void *a2)
{
  HANDLE NamedPipeW; // r14
  int Event; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int ValueString; // eax
  const struct std::nothrow_t *v9; // rdx
  int v10; // eax
  void *v11; // rbx
  signed int Process; // edi
  _QWORD *v13; // rcx
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // rdx
  HANDLE v16; // rdi
  HANDLE CurrentProcess; // rax
  const void *v18; // r9
  signed int LastError; // eax
  unsigned int v20; // r8d
  signed int v21; // eax
  unsigned int v22; // r8d
  void *v23; // r8
  unsigned int nOutBufferSize; // [rsp+28h] [rbp-49h]
  const struct _SECURITY_ATTRIBUTES *nInBufferSize; // [rsp+30h] [rbp-41h]
  void *nDefaultTimeOut; // [rsp+38h] [rbp-39h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // [rsp+40h] [rbp-31h]
  bool lpSecurityAttributesa; // [rsp+40h] [rbp-31h]
  unsigned __int64 v29; // [rsp+58h] [rbp-19h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-11h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp+Fh] BYREF
  HANDLE hProcess; // [rsp+88h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+1Fh] BYREF
  wchar_t *v34; // [rsp+98h] [rbp+27h] BYREF
  DWORD ExitCode; // [rsp+A0h] [rbp+2Fh] BYREF
  DWORD NumberOfBytesTransferred[2]; // [rsp+A8h] [rbp+37h] BYREF

  if ( !this )
    return 2147942487LL;
  NamedPipeW = CreateNamedPipeW(L"\\\\.\\pipe\\RasConnectionNotification", 0x40000003u, 0, 1u, 8u, 8u, 0xFFFFFFFF, 0);
  if ( NamedPipeW == (HANDLE)-1LL )
    return 2147500037LL;
  memset(&Overlapped, 0, 24);
  hObject = 0;
  Event = CommonUtil::UtilCreateEvent((CommonUtil *)&hObject, 0, 0, 0, 0, nInBufferSize);
  v6 = Event;
  if ( Event >= 0 )
  {
    Overlapped.hEvent = hObject;
    hKey = 0;
    v7 = CommonUtil::UtilRegOpenKey(
           (CommonUtil *)&hKey,
           (HKEY *)0xFFFFFFFF80000002LL,
           (HKEY)&stru_1802AD210,
           (const wchar_t *)0x20019,
           nOutBufferSize);
    v6 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_a134d450411735483d7af4aa7407bce1_Traceguids,
          (unsigned int)v7);
LABEL_13:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_15;
    }
    v34 = 0;
    ValueString = CommonUtil::UtilRegGetValueString(hKey, L"InstallLocation", &v34, 0, 0);
    v6 = ValueString;
    if ( ValueString < 0 )
    {
      v9 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_a134d450411735483d7af4aa7407bce1_Traceguids,
          (unsigned int)ValueString);
LABEL_21:
      if ( v34 )
        operator delete(v34, v9);
      goto LABEL_13;
    }
    *(_QWORD *)NumberOfBytesTransferred = 0;
    v10 = CommonUtil::NewSprintfW(
            (CommonUtil *)NumberOfBytesTransferred,
            (wchar_t **)L"\"%lsMpCmdRun.exe\" -RasConnectionNotification",
            v34);
    v6 = v10;
    if ( v10 < 0 )
    {
      v9 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_a134d450411735483d7af4aa7407bce1_Traceguids,
          (unsigned int)v10);
      if ( *(_QWORD *)NumberOfBytesTransferred )
        operator delete(*(void **)NumberOfBytesTransferred, v9);
      goto LABEL_21;
    }
    v11 = *(void **)NumberOfBytesTransferred;
    LOBYTE(lpSecurityAttributes) = 0;
    hProcess = 0;
    Process = CommonUtil::UtilCreateProcess(
                (CommonUtil *)&hProcess,
                *(void ***)NumberOfBytesTransferred,
                (const wchar_t *)0x20,
                0,
                0,
                0,
                0,
                lpSecurityAttributes,
                0,
                0,
                (const wchar_t *)v29);
    if ( Process < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v15 = 14;
      goto LABEL_33;
    }
    v16 = hProcess;
    v29 = 0;
    CurrentProcess = GetCurrentProcess();
    LOBYTE(nDefaultTimeOut) = 0;
    Process = CommonUtil::UtilDuplicateHandle(
                (CommonUtil *)&v29,
                this,
                0,
                2u,
                CurrentProcess,
                v16,
                nDefaultTimeOut,
                lpSecurityAttributesa);
    if ( Process < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v15 = 15;
      goto LABEL_33;
    }
    if ( !ConnectNamedPipe(NamedPipeW, &Overlapped) )
    {
      LastError = GetLastError();
      Process = LastError;
      if ( LastError > 0 )
        Process = (unsigned __int16)LastError | 0x80070000;
      if ( Process != -2147024361 )
      {
        if ( Process == -2147023899 )
        {
          if ( CommonUtil::UtilWaitForSingleObject((CommonUtil *)Overlapped.hEvent, (void *)0x1388, v20) )
          {
            v13 = WPP_GLOBAL_Control;
            v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
            Process = -2147023436;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 16;
            goto LABEL_33;
          }
        }
        else if ( Process < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_70;
          v15 = 17;
          goto LABEL_33;
        }
      }
      NumberOfBytesTransferred[0] = 0;
      if ( !GetOverlappedResult(NamedPipeW, &Overlapped, NumberOfBytesTransferred, 0) )
      {
        v21 = GetLastError();
        Process = v21;
        if ( v21 > 0 )
          Process = (unsigned __int16)v21 | 0x80070000;
        if ( Process < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_70;
          v15 = 19;
          goto LABEL_33;
        }
      }
    }
    Process = CommonUtil::UtilWriteFile(NamedPipeW, (void *)8, (unsigned __int64)&v29, v18);
    if ( Process >= 0 )
    {
      if ( CommonUtil::UtilWaitForSingleObject((CommonUtil *)hProcess, (void *)0x1388, v22) )
      {
        TerminateProcess(hProcess, 0x5B4u);
        Process = -2147023436;
        goto LABEL_70;
      }
      ExitCode = 0;
      Process = CommonUtil::UtilGetExitCodeProcess(&ExitCode, hProcess, v23);
      if ( Process >= 0 )
      {
        Process = ExitCode;
        if ( (int)ExitCode > 0 )
          Process = (unsigned __int16)ExitCode | 0x80070000;
        goto LABEL_70;
      }
      v13 = WPP_GLOBAL_Control;
      v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_70:
        if ( hProcess )
          CloseHandle(hProcess);
        if ( v11 )
          operator delete(v11, v14);
        if ( v34 )
          operator delete(v34, v14);
        if ( hKey )
          RegCloseKey(hKey);
        if ( hObject )
          CloseHandle(hObject);
        v6 = Process;
        goto LABEL_81;
      }
      v15 = 21;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v15 = 20;
    }
LABEL_33:
    WPP_SF_d(v13[2], v15, WPP_a134d450411735483d7af4aa7407bce1_Traceguids, (unsigned int)Process);
    goto LABEL_70;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_a134d450411735483d7af4aa7407bce1_Traceguids,
      (unsigned int)Event);
LABEL_15:
  if ( hObject )
    CloseHandle(hObject);
LABEL_81:
  CloseHandle(NamedPipeW);
  return v6;
}

```

## disassembly

```asm
0x18008de80  mov     rax, rsp
0x18008de83  mov     [rax+10h], rbx
0x18008de87  mov     [rax+18h], rsi
0x18008de8b  mov     [rax+20h], rdi
0x18008de8f  push    rbp
0x18008de90  push    r14
0x18008de92  push    r15
0x18008de94  lea     rbp, [rax-5Fh]
0x18008de98  sub     rsp, 0B0h
0x18008de9f  mov     rax, cs:__security_cookie
0x18008dea6  xor     rax, rsp
0x18008dea9  mov     [rbp+57h+var_18], rax
0x18008dead  xor     r15d, r15d
0x18008deb0  mov     rsi, rcx
0x18008deb3  test    rcx, rcx
0x18008deb6  jnz     short loc_18008DEC2
0x18008deb8  mov     eax, 80070057h
0x18008debd  jmp     loc_18008E3AA
0x18008dec2  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18008dec7  lea     rcx, Name; "\\\\.\\pipe\\RasConnectionNotification"
0x18008dece  mov     [rsp+0C0h+nDefaultTimeOut], 0FFFFFFFFh; nDefaultTimeOut
0x18008ded6  mov     r9d, 1; nMaxInstances
0x18008dedc  mov     [rsp+0C0h+nInBufferSize], 8; struct _SECURITY_ATTRIBUTES *
0x18008dee4  xor     r8d, r8d; dwPipeMode
0x18008dee7  mov     edx, 40000003h; dwOpenMode
0x18008deec  mov     [rsp+0C0h+nOutBufferSize], 8; nOutBufferSize
0x18008def4  call    cs:__imp_CreateNamedPipeW
0x18008defa  mov     r14, rax
0x18008defd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008df01  jnz     short loc_18008DF0D
0x18008df03  mov     eax, 80004005h
0x18008df08  jmp     loc_18008E3AA
0x18008df0d  xorps   xmm0, xmm0
0x18008df10  mov     [rbp+57h+Overlapped.Internal], r15
0x18008df14  xor     r9d, r9d; int
0x18008df17  mov     [rbp+57h+hObject], r15
0x18008df1b  xor     r8d, r8d; int
0x18008df1e  mov     qword ptr [rsp+0C0h+nOutBufferSize], r15; unsigned int
0x18008df23  xor     edx, edx; void **
0x18008df25  lea     rcx, [rbp+57h+hObject]; this
0x18008df29  movdqu  xmmword ptr [rbp+57h+Overlapped.InternalHigh], xmm0
0x18008df2e  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEB_WPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,wchar_t const *,_SECURITY_ATTRIBUTES const *)
0x18008df33  mov     ebx, eax
0x18008df35  test    eax, eax
0x18008df37  jns     short loc_18008DF74
0x18008df39  mov     rcx, cs:WPP_GLOBAL_Control
0x18008df40  lea     rdx, WPP_GLOBAL_Control
0x18008df47  cmp     rcx, rdx
0x18008df4a  jz      loc_18008DFE3
0x18008df50  test    byte ptr [rcx+1Ch], 1
0x18008df54  jz      loc_18008DFE3
0x18008df5a  mov     rcx, [rcx+10h]
0x18008df5e  lea     r8, WPP_a134d450411735483d7af4aa7407bce1_Traceguids
0x18008df65  mov     edx, 0Ah
0x18008df6a  mov     r9d, eax
0x18008df6d  call    WPP_SF_d
0x18008df72  jmp     short loc_18008DFE3
0x18008df74  mov     rax, [rbp+57h+hObject]
0x18008df78  lea     r8, stru_1802AD210; HKEY
0x18008df7f  mov     r9d, 20019h; wchar_t *
0x18008df85  mov     [rbp+57h+Overlapped.hEvent], rax
0x18008df89  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x18008df90  mov     [rbp+57h+hKey], r15
0x18008df94  lea     rcx, [rbp+57h+hKey]; this
0x18008df98  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x18008df9d  mov     ebx, eax
0x18008df9f  test    eax, eax
0x18008dfa1  jns     short loc_18008DFFB
0x18008dfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dfaa  lea     rdx, WPP_GLOBAL_Control
0x18008dfb1  cmp     rcx, rdx
0x18008dfb4  jz      short loc_18008DFD4
0x18008dfb6  test    byte ptr [rcx+1Ch], 1
0x18008dfba  jz      short loc_18008DFD4
0x18008dfbc  mov     rcx, [rcx+10h]
0x18008dfc0  lea     r8, WPP_a134d450411735483d7af4aa7407bce1_Traceguids
0x18008dfc7  mov     edx, 0Bh
0x18008dfcc  mov     r9d, eax
0x18008dfcf  call    WPP_SF_d
0x18008dfd4  mov     rcx, [rbp+57h+hKey]; hKey
0x18008dfd8  test    rcx, rcx
0x18008dfdb  jz      short loc_18008DFE3
0x18008dfdd  call    cs:__imp_RegCloseKey
0x18008dfe3  mov     rcx, [rbp+57h+hObject]; hObject
0x18008dfe7  test    rcx, rcx
0x18008dfea  jz      loc_18008E39F
0x18008dff0  call    cs:__imp_CloseHandle
0x18008dff6  jmp     loc_18008E39F
0x18008dffb  mov     rcx, [rbp+57h+hKey]
0x18008dfff  lea     r8, [rbp+57h+var_30]
0x18008e003  xor     r9d, r9d
0x18008e006  mov     [rbp+57h+var_30], r15
0x18008e00a  lea     rdx, aInstalllocatio; "InstallLocation"
0x18008e011  mov     qword ptr [rsp+0C0h+nOutBufferSize], r15
0x18008e016  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x18008e01b  mov     ebx, eax
0x18008e01d  test    eax, eax
0x18008e01f  jns     short loc_18008E069
0x18008e021  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e028  lea     rdx, WPP_GLOBAL_Control
0x18008e02f  cmp     rcx, rdx
0x18008e032  jz      short loc_18008E052
0x18008e034  test    byte ptr [rcx+1Ch], 1
0x18008e038  jz      short loc_18008E052
0x18008e03a  mov     rcx, [rcx+10h]
0x18008e03e  lea     r8, WPP_a134d450411735483d7af4aa7407bce1_Traceguids
0x18008e045  mov     edx, 0Ch
0x18008e04a  mov     r9d, eax
0x18008e04d  call    WPP_SF_d
0x18008e052  mov     rcx, [rbp+57h+var_30]; void *
0x18008e056  test    rcx, rcx
0x18008e059  jz      loc_18008DFD4
0x18008e05f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008e064  jmp     loc_18008DFD4
0x18008e069  mov     r8, [rbp+57h+var_30]; wchar_t *
0x18008e06d  lea     rdx, aLsmpcmdrunExeR; "\"%lsMpCmdRun.exe\" -RasConnectionNotif"...
0x18008e074  lea     rcx, [rbp+57h+NumberOfBytesTransferred]; this
0x18008e078  mov     qword ptr [rbp+57h+NumberOfBytesTransferred], r15
0x18008e07c  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18008e081  mov     ebx, eax
0x18008e083  test    eax, eax
0x18008e085  jns     short loc_18008E0C8
0x18008e087  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e08e  lea     rdx, WPP_GLOBAL_Control
0x18008e095  cmp     rcx, rdx
0x18008e098  jz      short loc_18008E0B8
0x18008e09a  test    byte ptr [rcx+1Ch], 1
0x18008e09e  jz      short loc_18008E0B8
0x18008e0a0  mov     rcx, [rcx+10h]
0x18008e0a4  lea     r8, WPP_a134d450411735483d7af4aa7407bce1_Traceguids
0x18008e0ab  mov     edx, 0Dh
0x18008e0b0  mov     r9d, eax
0x18008e0b3  call    WPP_SF_d
0x18008e0b8  mov     rcx, qword ptr [rbp+57h+NumberOfBytesTransferred]; void *
0x18008e0bc  test    rcx, rcx
0x18008e0bf  jz      short loc_18008E052
0x18008e0c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008e0c6  jmp     short loc_18008E052
0x18008e0c8  mov     rbx, qword ptr [rbp+57h+NumberOfBytesTransferred]
0x18008e0cc  lea     rcx, [rbp+57h+hProcess]; this
0x18008e0d0  mov     [rsp+0C0h+var_78], r15; void *
0x18008e0d5  xor     r9d, r9d; unsigned int
0x18008e0d8  mov     qword ptr [rsp+0C0h+var_80], r15; bool
0x18008e0dd  mov     rdx, rbx; void **
0x18008e0e0  mov     byte ptr [rsp+0C0h+lpSecurityAttributes], r15b; bool
0x18008e0e5  mov     qword ptr [rsp+0C0h+nDefaultTimeOut], r15; struct _SECURITY_ATTRIBUTES *
0x18008e0ea  lea     r8d, [r9+20h]; wchar_t *
0x18008e0ee  mov     qword ptr [rsp+0C0h+nInBufferSize], r15; wchar_t *
0x18008e0f3  mov     [rbp+57h+hProcess], r15
0x18008e0f7  mov     qword ptr [rsp+0C0h+nOutBufferSize], r15; struct _STARTUPINFOW *
0x18008e0fc  call    ?UtilCreateProcess@CommonUtil@@YAJPEAPEAXPEB_WKPEAU_STARTUPINFOW@@1PEAU_SECURITY_ATTRIBUTES@@3_NPEAX1@Z; CommonUtil::UtilCreateProcess(void * *,wchar_t const *,ulong,_STARTUPINFOW *,wchar_t const *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,bool,void *,wchar_t const *)
0x18008e101  mov     edi, eax
0x18008e103  test    eax, eax
0x18008e105  jns     short loc_18008E145
0x18008e107  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e10e  lea     rdx, WPP_GLOBAL_Control
0x18008e115  cmp     rcx, rdx
0x18008e118  jz      loc_18008E355
0x18008e11e  test    byte ptr [rcx+1Ch], 1
0x18008e122  jz      loc_18008E355
0x18008e128  mov     edx, 0Eh
0x18008e12d  mov     rcx, [rcx+10h]
0x18008e131  lea     r8, WPP_a134d450411735483d7af4aa7407bce1_Traceguids
0x18008e138  mov     r9d, edi
0x18008e13b  call    WPP_SF_d
0x18008e140  jmp     loc_18008E355
0x18008e145  mov     rdi, [rbp+57h+hProcess]
0x18008e149  mov     [rbp+57h+var_70], r15
0x18008e14d  call    cs:__imp_GetCurrentProcess
0x18008e153  mov     byte ptr [rsp+0C0h+nDefaultTimeOut], r15b; void *
0x18008e158  lea     rcx, [rbp+57h+var_70]; this
0x18008e15c  mov     qword ptr [rsp+0C0h+nInBufferSize], rdi; hTargetProcessHandle
0x18008e161  mov     r9d, 2; unsigned int
0x18008e167  xor     r8d, r8d; void *
0x18008e16a  mov     qword ptr [rsp+0C0h+nOutBufferSize], rax; hSourceProcessHandle
0x18008e16f  mov     rdx, rsi; void **
0x18008e172  call    ?UtilDuplicateHandle@CommonUtil@@YAJPEAPEAXPEAXKK11_N@Z; CommonUtil::UtilDuplicateHandle(void * *,void *,ulong,ulong,void *,void *,bool)
0x18008e177  mov     edi, eax
0x18008e179  test    eax, eax
0x18008e17b  jns     short loc_18008E1A5
0x18008e17d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e184  lea     rdx, WPP_GLOBAL_Control
0x18008e18b  cmp     rcx, rdx
0x18008e18e  jz      loc_18008E355
0x18008e194  test    byte ptr [rcx+1Ch], 1
0x18008e198  jz      loc_18008E355
0x18008e19e  mov     edx, 0Fh
0x18008e1a3  jmp     short loc_18008E12D
0x18008e1a5  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18008e1a9  mov     rcx, r14; hNamedPipe
0x18008e1ac  call    cs:__imp_ConnectNamedPipe
0x18008e1b2  mov     esi, 80070000h
0x18008e1b7  test    eax, eax
0x18008e1b9  jnz     loc_18008E2AD
0x18008e1bf  call    cs:__imp_GetLastError
0x18008e1c5  mov     edi, eax
0x18008e1c7  test    eax, eax
0x18008e1c9  jle     short loc_18008E1D0
0x18008e1cb  movzx   edi, ax
0x18008e1ce  or      edi, esi
0x18008e1d0  cmp     edi, 80070217h
0x18008e1d6  jz      short loc_18008E251
0x18008e1d8  cmp     edi, 800703E5h
0x18008e1de  jz      short loc_18008E20F
0x18008e1e0  test    edi, edi
0x18008e1e2  jns     short loc_18008E251
0x18008e1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e1eb  lea     rdx, WPP_GLOBAL_Control
0x18008e1f2  cmp     rcx, rdx
0x18008e1f5  jz      loc_18008E355
0x18008e1fb  test    byte ptr [rcx+1Ch], 1
0x18008e1ff  jz      loc_18008E355
0x18008e205  mov     edx, 11h
0x18008e20a  jmp     loc_18008E12D
0x18008e20f  mov     rcx, [rbp+57h+Overlapped.hEvent]; this
0x18008e213  mov     edx, 1388h; void *
0x18008e218  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x18008e21d  test    al, al
0x18008e21f  jz      short loc_18008E251
0x18008e221  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e228  lea     rdx, WPP_GLOBAL_Control
0x18008e22f  mov     edi, 800705B4h
0x18008e234  cmp     rcx, rdx
0x18008e237  jz      loc_18008E355
0x18008e23d  test    byte ptr [rcx+1Ch], 1
0x18008e241  jz      loc_18008E355
0x18008e247  mov     edx, 10h
0x18008e24c  jmp     loc_18008E12D
0x18008e251  xor     r9d, r9d; bWait
0x18008e254  mov     [rbp+57h+NumberOfBytesTransferred], r15d
0x18008e258  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18008e25c  mov     rcx, r14; hFile
0x18008e25f  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18008e263  call    cs:__imp_GetOverlappedResult
0x18008e269  test    eax, eax
0x18008e26b  jnz     short loc_18008E2AD
0x18008e26d  call    cs:__imp_GetLastError
0x18008e273  mov     edi, eax
0x18008e275  test    eax, eax
0x18008e277  jle     short loc_18008E27E
0x18008e279  movzx   edi, ax
0x18008e27c  or      edi, esi
0x18008e27e  test    edi, edi
0x18008e280  jns     short loc_18008E2AD
0x18008e282  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e289  lea     rdx, WPP_GLOBAL_Control
0x18008e290  cmp     rcx, rdx
0x18008e293  jz      loc_18008E355
0x18008e299  test    byte ptr [rcx+1Ch], 1
0x18008e29d  jz      loc_18008E355
0x18008e2a3  mov     edx, 13h
0x18008e2a8  jmp     loc_18008E12D
0x18008e2ad  lea     r8, [rbp+57h+var_70]; unsigned __int64
0x18008e2b1  mov     edx, 8; void *
0x18008e2b6  mov     rcx, r14; hFile
0x18008e2b9  call    ?UtilWriteFile@CommonUtil@@YAJPEAX_KPEBX@Z; CommonUtil::UtilWriteFile(void *,unsigned __int64,void const *)
0x18008e2be  mov     edi, eax
0x18008e2c0  test    eax, eax
0x18008e2c2  jns     short loc_18008E2E7
0x18008e2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e2cb  lea     rdx, WPP_GLOBAL_Control
0x18008e2d2  cmp     rcx, rdx
0x18008e2d5  jz      short loc_18008E355
0x18008e2d7  test    byte ptr [rcx+1Ch], 1
0x18008e2db  jz      short loc_18008E355
0x18008e2dd  mov     edx, 14h
0x18008e2e2  jmp     loc_18008E12D
0x18008e2e7  mov     rcx, [rbp+57h+hProcess]; this
0x18008e2eb  mov     edx, 1388h; void *
0x18008e2f0  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x18008e2f5  test    al, al
0x18008e2f7  jz      short loc_18008E30F
0x18008e2f9  mov     rcx, [rbp+57h+hProcess]; hProcess
0x18008e2fd  mov     edx, 5B4h; uExitCode
0x18008e302  call    cs:__imp_TerminateProcess
0x18008e308  mov     edi, 800705B4h
0x18008e30d  jmp     short loc_18008E355
0x18008e30f  mov     rdx, [rbp+57h+hProcess]; hProcess
0x18008e313  lea     rcx, [rbp+57h+ExitCode]; lpExitCode
0x18008e317  mov     [rbp+57h+ExitCode], r15d
0x18008e31b  call    ?UtilGetExitCodeProcess@CommonUtil@@YAJPEAKPEAX@Z; CommonUtil::UtilGetExitCodeProcess(ulong *,void *)
0x18008e320  mov     edi, eax
0x18008e322  test    eax, eax
0x18008e324  jns     short loc_18008E349
0x18008e326  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e32d  lea     rdx, WPP_GLOBAL_Control
0x18008e334  cmp     rcx, rdx
0x18008e337  jz      short loc_18008E355
0x18008e339  test    byte ptr [rcx+1Ch], 1
0x18008e33d  jz      short loc_18008E355
0x18008e33f  mov     edx, 15h
0x18008e344  jmp     loc_18008E12D
0x18008e349  mov     edi, [rbp+57h+ExitCode]
0x18008e34c  test    edi, edi
0x18008e34e  jle     short loc_18008E355
0x18008e350  movzx   edi, di
0x18008e353  or      edi, esi
0x18008e355  mov     rcx, [rbp+57h+hProcess]; hObject
0x18008e359  test    rcx, rcx
0x18008e35c  jz      short loc_18008E364
  ... truncated ...
```
