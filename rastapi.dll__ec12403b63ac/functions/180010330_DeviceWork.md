# DeviceWork

- ea: `0x180010330`
- end: `0x1800107a2`
- name: `DeviceWork`
- size: `1138`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002b20`
- `0x18000d92c`
- `0x180010330`
- `0x180012340`
- `0x180012f20`
- `0x1800231f8`
- `0x180023404`
- `0x180024b38`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180010672`
- `msvcrt!_stricmp` at `0x180010672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001076f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001076f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010728`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010765`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010728`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010765`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800106fb`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800106fb`
- `api-ms-win-core-comm-l1-1-0!SetupComm` at `0x180010758`
- `api-ms-win-core-comm-l1-1-0!SetupComm` at `0x180010758`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallStatus` at `0x180010407`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallStatus` at `0x180010407`
- `ext-ms-win-ras-tapi32-l1-1-1!lineAccept` at `0x180010504`
- `ext-ms-win-ras-tapi32-l1-1-1!lineAccept` at `0x180010504`
- `ext-ms-win-ras-tapi32-l1-1-1!lineAnswer` at `0x180010599`
- `ext-ms-win-ras-tapi32-l1-1-1!lineAnswer` at `0x180010599`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetIDA` at `0x1800106b3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetIDA` at `0x1800106b3`

## string_xrefs

- `0x180010687`: `comm/datamodem`
- `0x1800106cc`: `DeviceWork: TPCB_CommHandle=%d`
- `0x18001070f`: `DeviceWork: %s. CreateIoCompletionPort failed. %d`

## pseudocode

```c
__int64 __fastcall DeviceWork(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // r8
  __int64 v5; // r9
  DWORD LastError; // r14d
  unsigned int IDA; // edi
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  int v12; // r12d
  LONG *v13; // rdi
  HCALL v14; // ecx
  LONG *v15; // r15
  HCALL v16; // ecx
  const CHAR *v17; // rcx
  struct varstring_tag DeviceID; // [rsp+30h] [rbp-D0h] BYREF
  struct linecallstatus_tag CallStatus; // [rsp+A0h] [rbp-60h] BYREF

  v3 = LookUpControlBlock(a1);
  if ( !v3 )
  {
    RasTapiTrace("DeviceWork: port 0x%x not found");
    return 615;
  }
  LastError = 651;
  IDA = 651;
  GetMutex(v2, v1, v4, v5);
  memset_0(&CallStatus.dwNeededSize, 0, 0x3E4u);
  CallStatus.dwTotalSize = 1000;
  RasTapiTrace("DeviceWork: %s. State = %d");
  if ( *(_DWORD *)(v3 + 56) == 4 )
  {
    if ( *(_DWORD *)(v3 + 256) )
    {
      IDA = *(_DWORD *)(v3 + 256);
      *(_DWORD *)(v3 + 256) = 0;
    }
    else if ( !*(_DWORD *)(*(_QWORD *)(v3 + 216) + 60LL) && lineGetCallStatus(*(_DWORD *)(v3 + 232), &CallStatus)
           || *(_DWORD *)(*(_QWORD *)(v3 + 216) + 60LL)
           && (unsigned int)RasLineGetCallStatus(*(unsigned int *)(v3 + 232), &CallStatus) )
    {
      RasTapiTrace("DeviceWork: lineGetCallStatus failed");
    }
    else if ( CallStatus.dwCallState == 256 )
    {
      RasTapiTrace("DeviceWork: Changing state for %s from %d -> %d");
      IDA = 0;
      *(_DWORD *)(v3 + 56) = 3;
    }
    else if ( CallStatus.dwCallState == 0x4000 )
    {
      IDA = DwRasErrorFromDisconnectMode(CallStatus.dwCallStateMode, v3);
      RasTapiTrace("DeviceWork: callstate = 0x%x. callmode = 0x%x, retcode %d");
    }
    else if ( CallStatus.dwCallState == 128 && CallStatus.dwCallStateMode == 1 )
    {
      RasTapiTrace("DeviceWork: ERROR_NO_ACTIVE_ISDN_LINES");
      IDA = 713;
    }
  }
  if ( *(_DWORD *)(v3 + 56) == 2 )
  {
    v12 = 0;
    if ( *(_DWORD *)(v3 + 60) == 5 )
    {
      RasTapiTrace("DeviceWork: %s. ListenState = LS_ERROR");
      IDA = 651;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(v3 + 60) != 2 )
    {
LABEL_32:
      if ( *(_DWORD *)(v3 + 60) != 3 )
        goto LABEL_43;
      v15 = (LONG *)(v3 + 252);
      v16 = *(_DWORD *)(v3 + 232);
      if ( *(_DWORD *)(*(_QWORD *)(v3 + 216) + 60LL) )
        v12 = RasLineAnswer(v16, v9, v10, v11, v3 + 252);
      else
        *v15 = lineAnswer(v16, 0, 0);
      RasTapiTrace("DeviceWork: %s. lineAnswer returned RequestID = 0x%x, Status = 0x%x");
      if ( *(_DWORD *)(*(_QWORD *)(v3 + 216) + 60LL) )
      {
        if ( !v12 )
        {
LABEL_38:
          if ( *v15 )
          {
            IDA = 600;
          }
          else
          {
            RasTapiTrace("DeviceWork: Changing Listen state for %s from %d -> %d");
            *(_DWORD *)(v3 + 60) = 4;
          }
LABEL_43:
          if ( *(_DWORD *)(v3 + 60) == 4 )
          {
            if ( *(_DWORD *)(v3 + 232) == -1 )
            {
              IDA = 651;
            }
            else
            {
              RasTapiTrace("DeviceWork: Changing State for %s from %d -> %d");
              IDA = 0;
              *(_DWORD *)(v3 + 56) = 3;
            }
          }
          goto LABEL_47;
        }
      }
      else if ( (unsigned int)*v15 <= 0x80000000 )
      {
        goto LABEL_38;
      }
      RasTapiTrace("DeviceWork: lineAnswer returned an error");
      IDA = 651;
      goto LABEL_43;
    }
    v13 = (LONG *)(v3 + 252);
    v14 = *(_DWORD *)(v3 + 232);
    if ( *(_DWORD *)(*(_QWORD *)(v3 + 216) + 60LL) )
      v12 = RasLineAccept(v14, v9, v10, v11, v3 + 252);
    else
      *v13 = lineAccept(v14, 0, 0);
    RasTapiTrace("DeviceWork: %s. lineAccept returned RequestID = 0x%x, Status = 0x%x");
    if ( *(_DWORD *)(*(_QWORD *)(v3 + 216) + 60LL) )
    {
      if ( v12 )
        goto LABEL_30;
    }
    else if ( (unsigned int)*v13 > 0x80000000 )
    {
      goto LABEL_30;
    }
    if ( *v13 )
    {
LABEL_31:
      IDA = 600;
      goto LABEL_32;
    }
LABEL_30:
    RasTapiTrace("DeviceWork: changing Listen state for %s from %d -> %d");
    *(_DWORD *)(v3 + 60) = 3;
    goto LABEL_31;
  }
LABEL_47:
  if ( *(_DWORD *)(v3 + 56) == 3 )
  {
    DeviceID.dwTotalSize = 100;
    if ( !_stricmp((const char *)(v3 + 64), "MODEM") )
    {
      IDA = lineGetIDA(
              *(_DWORD *)(*(_QWORD *)(v3 + 216) + 12LL),
              *(_DWORD *)(v3 + 224),
              *(_DWORD *)(v3 + 232),
              4u,
              &DeviceID,
              "comm/datamodem");
      if ( IDA )
      {
        v17 = "DeviceWork: %s lineGetID Failed. 0x%x";
LABEL_53:
        RasTapiTrace(v17);
        if ( !ReleaseMutex(RasTapiMutex) )
          GetLastError();
        RasTapiTrace(" ");
        return LastError;
      }
      *(_QWORD *)(v3 + 888) = *(unsigned int *)((char *)&DeviceID.dwTotalSize + DeviceID.dwStringOffset);
      RasTapiTrace("DeviceWork: TPCB_CommHandle=%d");
      if ( !CreateIoCompletionPort(*(HANDLE *)(v3 + 888), *(HANDLE *)(v3 + 240), *(unsigned int *)(v3 + 248), 0) )
      {
        LastError = GetLastError();
        v17 = "DeviceWork: %s. CreateIoCompletionPort failed. %d";
        goto LABEL_53;
      }
      SetupComm(*(HANDLE *)(v3 + 888), 0x5EAu, 0x5EAu);
    }
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return IDA;
}

```

## disassembly

```asm
0x180010330  mov     [rsp-8+arg_8], rbx
0x180010335  mov     [rsp-8+arg_10], rsi
0x18001033a  push    rbp
0x18001033b  push    rdi
0x18001033c  push    r12
0x18001033e  push    r14
0x180010340  push    r15
0x180010342  lea     rbp, [rsp-3A0h]
0x18001034a  sub     rsp, 4A0h
0x180010351  mov     rax, cs:__security_cookie
0x180010358  xor     rax, rsp
0x18001035b  mov     [rbp+3C0h+var_30], rax
0x180010362  call    LookUpControlBlock
0x180010367  mov     rbx, rax
0x18001036a  test    rax, rax
0x18001036d  jnz     short loc_180010388
0x18001036f  mov     rdx, rcx
0x180010372  lea     rcx, aDeviceworkPort; "DeviceWork: port 0x%x not found"
0x180010379  call    RasTapiTrace
0x18001037e  mov     eax, 267h
0x180010383  jmp     loc_180010777
0x180010388  mov     r14d, 28Bh
0x18001038e  mov     edi, r14d
0x180010391  call    GetMutex
0x180010396  xor     edx, edx; Val
0x180010398  lea     rcx, [rbp+3C0h+CallStatus.dwNeededSize]; void *
0x18001039c  mov     r8d, 3E4h; Size
0x1800103a2  call    memset_0
0x1800103a7  mov     [rbp+3C0h+CallStatus.dwTotalSize], 3E8h
0x1800103ae  lea     rsi, [rbx+18h]
0x1800103b2  mov     r8d, [rbx+38h]
0x1800103b6  lea     rcx, aDeviceworkSSta; "DeviceWork: %s. State = %d"
0x1800103bd  mov     rdx, rsi
0x1800103c0  call    RasTapiTrace
0x1800103c5  cmp     dword ptr [rbx+38h], 4
0x1800103c9  mov     r15d, 3
0x1800103cf  jnz     loc_1800104B1
0x1800103d5  mov     eax, [rbx+100h]
0x1800103db  test    eax, eax
0x1800103dd  jz      short loc_1800103F0
0x1800103df  mov     edi, eax
0x1800103e1  mov     dword ptr [rbx+100h], 0
0x1800103eb  jmp     loc_1800104B1
0x1800103f0  mov     rax, [rbx+0D8h]
0x1800103f7  cmp     dword ptr [rax+3Ch], 0
0x1800103fb  jnz     short loc_180010411
0x1800103fd  mov     ecx, [rbx+0E8h]; hCall
0x180010403  lea     rdx, [rbp+3C0h+CallStatus]; lpCallStatus
0x180010407  call    cs:__imp_lineGetCallStatus
0x18001040d  test    eax, eax
0x18001040f  jnz     short loc_180010431
0x180010411  mov     rax, [rbx+0D8h]
0x180010418  cmp     dword ptr [rax+3Ch], 0
0x18001041c  jz      short loc_18001043F
0x18001041e  mov     ecx, [rbx+0E8h]
0x180010424  lea     rdx, [rbp+3C0h+CallStatus]
0x180010428  call    RasLineGetCallStatus
0x18001042d  test    eax, eax
0x18001042f  jz      short loc_18001043F
0x180010431  lea     rcx, aDeviceworkLine; "DeviceWork: lineGetCallStatus failed"
0x180010438  call    RasTapiTrace
0x18001043d  jmp     short loc_1800104B1
0x18001043f  mov     eax, [rbp+3C0h+CallStatus.dwCallState]
0x180010442  cmp     eax, 100h
0x180010447  jnz     short loc_180010467
0x180010449  mov     r8d, [rbx+38h]
0x18001044d  lea     rcx, aDeviceworkChan; "DeviceWork: Changing state for %s from "...
0x180010454  mov     r9d, r15d
0x180010457  mov     rdx, rsi
0x18001045a  call    RasTapiTrace
0x18001045f  xor     edi, edi
0x180010461  mov     [rbx+38h], r15d
0x180010465  jmp     short loc_1800104B1
0x180010467  cmp     eax, 4000h
0x18001046c  jnz     short loc_180010493
0x18001046e  mov     ecx, [rbp+3C0h+CallStatus.dwCallStateMode]
0x180010471  mov     rdx, rbx
0x180010474  call    DwRasErrorFromDisconnectMode
0x180010479  mov     r8d, [rbp+3C0h+CallStatus.dwCallStateMode]
0x18001047d  lea     rcx, aDeviceworkCall; "DeviceWork: callstate = 0x%x. callmode "...
0x180010484  mov     edx, [rbp+3C0h+CallStatus.dwCallState]
0x180010487  mov     r9d, eax
0x18001048a  mov     edi, eax
0x18001048c  call    RasTapiTrace
0x180010491  jmp     short loc_1800104B1
0x180010493  cmp     eax, 80h
0x180010498  jnz     short loc_1800104B1
0x18001049a  cmp     [rbp+3C0h+CallStatus.dwCallStateMode], 1
0x18001049e  jnz     short loc_1800104B1
0x1800104a0  lea     rcx, aDeviceworkErro; "DeviceWork: ERROR_NO_ACTIVE_ISDN_LINES"
0x1800104a7  call    RasTapiTrace
0x1800104ac  mov     edi, 2C9h
0x1800104b1  cmp     dword ptr [rbx+38h], 2
0x1800104b5  jnz     loc_180010655
0x1800104bb  xor     r12d, r12d
0x1800104be  cmp     dword ptr [rbx+3Ch], 5
0x1800104c2  jnz     short loc_1800104DB
0x1800104c4  mov     rdx, rsi
0x1800104c7  lea     rcx, aDeviceworkSLis; "DeviceWork: %s. ListenState = LS_ERROR"
0x1800104ce  call    RasTapiTrace
0x1800104d3  mov     edi, r14d
0x1800104d6  jmp     loc_180010570
0x1800104db  cmp     dword ptr [rbx+3Ch], 2
0x1800104df  jnz     loc_180010570
0x1800104e5  mov     rax, [rbx+0D8h]
0x1800104ec  lea     rdi, [rbx+0FCh]
0x1800104f3  mov     ecx, [rbx+0E8h]; hCall
0x1800104f9  cmp     [rax+3Ch], r12d
0x1800104fd  jnz     short loc_18001050E
0x1800104ff  xor     r8d, r8d; dwSize
0x180010502  xor     edx, edx; lpsUserUserInfo
0x180010504  call    cs:__imp_lineAccept
0x18001050a  mov     [rdi], eax
0x18001050c  jmp     short loc_18001051B
0x18001050e  mov     [rsp+4C0h+lpDeviceID], rdi
0x180010513  call    RasLineAccept
0x180010518  mov     r12d, eax
0x18001051b  mov     r8d, [rdi]
0x18001051e  lea     rcx, aDeviceworkSLin_0; "DeviceWork: %s. lineAccept returned Req"...
0x180010525  mov     r9d, r12d
0x180010528  mov     rdx, rsi
0x18001052b  call    RasTapiTrace
0x180010530  mov     rcx, [rbx+0D8h]
0x180010537  cmp     dword ptr [rcx+3Ch], 0
0x18001053b  jnz     short loc_180010547
0x18001053d  cmp     dword ptr [rdi], 80000000h
0x180010543  ja      short loc_180010551
0x180010545  jmp     short loc_18001054C
0x180010547  test    r12d, r12d
0x18001054a  jnz     short loc_180010551
0x18001054c  cmp     dword ptr [rdi], 0
0x18001054f  jnz     short loc_18001056B
0x180010551  mov     r8d, [rbx+3Ch]
0x180010555  lea     rcx, aDeviceworkChan_0; "DeviceWork: changing Listen state for %"...
0x18001055c  mov     r9d, r15d
0x18001055f  mov     rdx, rsi
0x180010562  call    RasTapiTrace
0x180010567  mov     [rbx+3Ch], r15d
0x18001056b  mov     edi, 258h
0x180010570  cmp     [rbx+3Ch], r15d
0x180010574  jnz     loc_180010625
0x18001057a  mov     rax, [rbx+0D8h]
0x180010581  lea     r15, [rbx+0FCh]
0x180010588  mov     ecx, [rbx+0E8h]; hCall
0x18001058e  cmp     dword ptr [rax+3Ch], 0
0x180010592  jnz     short loc_1800105A4
0x180010594  xor     r8d, r8d; dwSize
0x180010597  xor     edx, edx; lpsUserUserInfo
0x180010599  call    cs:__imp_lineAnswer
0x18001059f  mov     [r15], eax
0x1800105a2  jmp     short loc_1800105B1
0x1800105a4  mov     [rsp+4C0h+lpDeviceID], r15
0x1800105a9  call    RasLineAnswer
0x1800105ae  mov     r12d, eax
0x1800105b1  mov     r8d, [r15]
0x1800105b4  lea     rcx, aDeviceworkSLin_1; "DeviceWork: %s. lineAnswer returned Req"...
0x1800105bb  mov     r9d, r12d
0x1800105be  mov     rdx, rsi
0x1800105c1  call    RasTapiTrace
0x1800105c6  mov     rax, [rbx+0D8h]
0x1800105cd  cmp     dword ptr [rax+3Ch], 0
0x1800105d1  jnz     short loc_1800105E9
0x1800105d3  cmp     dword ptr [r15], 80000000h
0x1800105da  ja      short loc_1800105EE
0x1800105dc  cmp     dword ptr [r15], 0
0x1800105e0  jz      short loc_1800105FF
0x1800105e2  mov     edi, 258h
0x1800105e7  jmp     short loc_18001061F
0x1800105e9  test    r12d, r12d
0x1800105ec  jz      short loc_1800105DC
0x1800105ee  lea     rcx, aDeviceworkLine_0; "DeviceWork: lineAnswer returned an erro"...
0x1800105f5  call    RasTapiTrace
0x1800105fa  mov     edi, r14d
0x1800105fd  jmp     short loc_18001061F
0x1800105ff  mov     r8d, [rbx+3Ch]
0x180010603  lea     rcx, aDeviceworkChan_1; "DeviceWork: Changing Listen state for %"...
0x18001060a  mov     r9d, 4
0x180010610  mov     rdx, rsi
0x180010613  call    RasTapiTrace
0x180010618  mov     dword ptr [rbx+3Ch], 4
0x18001061f  mov     r15d, 3
0x180010625  cmp     dword ptr [rbx+3Ch], 4
0x180010629  jnz     short loc_180010655
0x18001062b  cmp     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x180010632  jnz     short loc_180010639
0x180010634  mov     edi, r14d
0x180010637  jmp     short loc_180010655
0x180010639  mov     r8d, [rbx+38h]
0x18001063d  lea     rcx, aDeviceworkChan_2; "DeviceWork: Changing State for %s from "...
0x180010644  mov     r9d, r15d
0x180010647  mov     rdx, rsi
0x18001064a  call    RasTapiTrace
0x18001064f  xor     edi, edi
0x180010651  mov     [rbx+38h], r15d
0x180010655  cmp     [rbx+38h], r15d
0x180010659  jnz     loc_18001075E
0x18001065f  lea     rcx, [rbx+40h]; String1
0x180010663  mov     [rsp+4C0h+DeviceID.dwTotalSize], 64h ; 'd'
0x18001066b  lea     rdx, aModem; "MODEM"
0x180010672  call    cs:__imp__stricmp
0x180010678  test    eax, eax
0x18001067a  jnz     loc_18001075E
0x180010680  mov     rcx, [rbx+0D8h]
0x180010687  lea     rax, SubStr; "comm/datamodem"
0x18001068e  mov     r8d, [rbx+0E8h]; hCall
0x180010695  mov     r9d, 4; dwSelect
0x18001069b  mov     edx, [rbx+0E0h]; dwAddressID
0x1800106a1  mov     [rsp+4C0h+lpszDeviceClass], rax; lpszDeviceClass
0x1800106a6  lea     rax, [rsp+4C0h+DeviceID]
0x1800106ab  mov     ecx, [rcx+0Ch]; hLine
0x1800106ae  mov     [rsp+4C0h+lpDeviceID], rax; lpDeviceID
0x1800106b3  call    cs:__imp_lineGetIDA
0x1800106b9  mov     edi, eax
0x1800106bb  test    eax, eax
0x1800106bd  jz      short loc_1800106C8
0x1800106bf  lea     rcx, aDeviceworkSLin; "DeviceWork: %s lineGetID Failed. 0x%x"
0x1800106c6  jmp     short loc_180010716
0x1800106c8  mov     eax, [rsp+4C0h+DeviceID.dwStringOffset]
0x1800106cc  lea     rcx, aDeviceworkTpcb; "DeviceWork: TPCB_CommHandle=%d"
0x1800106d3  mov     edx, [rsp+rax+4C0h+DeviceID.dwTotalSize]
0x1800106d7  mov     [rbx+378h], rdx
0x1800106de  call    RasTapiTrace
0x1800106e3  mov     r8d, [rbx+0F8h]; CompletionKey
0x1800106ea  xor     r9d, r9d; NumberOfConcurrentThreads
0x1800106ed  mov     rdx, [rbx+0F0h]; ExistingCompletionPort
0x1800106f4  mov     rcx, [rbx+378h]; FileHandle
0x1800106fb  call    cs:__imp_CreateIoCompletionPort
0x180010701  test    rax, rax
0x180010704  jnz     short loc_180010749
0x180010706  call    cs:__imp_GetLastError
0x18001070c  mov     r14d, eax
0x18001070f  lea     rcx, aDeviceworkSCre; "DeviceWork: %s. CreateIoCompletionPort "...
0x180010716  mov     r8d, eax
0x180010719  mov     rdx, rsi
0x18001071c  call    RasTapiTrace
0x180010721  mov     rcx, cs:RasTapiMutex; hMutex
0x180010728  call    cs:__imp_ReleaseMutex
0x18001072e  test    eax, eax
0x180010730  jnz     short loc_180010738
0x180010732  call    cs:__imp_GetLastError
0x180010738  lea     rcx, asc_18002C0B8; " "
0x18001073f  call    RasTapiTrace
0x180010744  mov     eax, r14d
0x180010747  jmp     short loc_180010777
0x180010749  mov     rcx, [rbx+378h]; hFile
0x180010750  mov     edx, 5EAh; dwInQueue
0x180010755  mov     r8d, edx; dwOutQueue
0x180010758  call    cs:__imp_SetupComm
0x18001075e  mov     rcx, cs:RasTapiMutex; hMutex
0x180010765  call    cs:__imp_ReleaseMutex
0x18001076b  test    eax, eax
0x18001076d  jnz     short loc_180010775
0x18001076f  call    cs:__imp_GetLastError
0x180010775  mov     eax, edi
0x180010777  mov     rcx, [rbp+3C0h+var_30]
0x18001077e  xor     rcx, rsp; StackCookie
0x180010781  call    __security_check_cookie
0x180010786  lea     r11, [rsp+4C0h+var_20]
0x18001078e  mov     rbx, [r11+38h]
0x180010792  mov     rsi, [r11+40h]
0x180010796  mov     rsp, r11
0x180010799  pop     r15
0x18001079b  pop     r14
0x18001079d  pop     r12
0x18001079f  pop     rdi
0x1800107a0  pop     rbp
0x1800107a1  retn
```
