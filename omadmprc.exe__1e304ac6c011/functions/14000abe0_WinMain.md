# WinMain

- ea: `0x14000abe0`
- end: `0x14000b099`
- name: `WinMain`
- size: `1209`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140002008`

## callees

- `0x140001090`
- `0x14000271f`
- `0x1400060cc`
- `0x140006970`
- `0x14000ab68`
- `0x14000aba8`
- `0x14000abe0`
- `0x14000b708`
- `0x14000debc`
- `0x14000fff0`
- `0x1400107ec`
- `0x140015690`
- `0x140017010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000ac72`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000ac72`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000b053`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14000b053`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000ac97`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000ac97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ad79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000adab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ad79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000adab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adca`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000ad65`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000ad65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000ae3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000ae3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b012`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b023`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b023`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000acf4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000acf4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000adbc`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b06c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000adbc`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b06c`
- `DMPushProxy!__imp_PushRouter_Close` at `0x14000affe`
- `DMPushProxy!__imp_PushRouter_Close` at `0x14000affe`
- `DMPushProxy!__imp_PushRouter_Open` at `0x14000ad28`
- `DMPushProxy!__imp_PushRouter_Open` at `0x14000ad28`
- `DMPushProxy!__imp_PushRouter_GetMessageEx` at `0x14000aefe`
- `DMPushProxy!__imp_PushRouter_GetMessageEx` at `0x14000aefe`
- `DMPushProxy!__imp_PushRouter_FreeMessageEx` at `0x14000aed3`
- `DMPushProxy!__imp_PushRouter_FreeMessageEx` at `0x14000afdc`
- `DMPushProxy!__imp_PushRouter_FreeMessageEx` at `0x14000aed3`
- `DMPushProxy!__imp_PushRouter_FreeMessageEx` at `0x14000afdc`
- `DMPushProxy!__imp_PushRouter_FreeGetMessageEventName` at `0x14000afed`
- `DMPushProxy!__imp_PushRouter_FreeGetMessageEventName` at `0x14000afed`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  HANDLE v4; // rsi
  int v5; // r14d
  HRESULT Message; // ebx
  char *v7; // rdx
  signed int LastError; // eax
  OLECHAR *v9; // rdi
  DWORD v10; // ebx
  int v11; // eax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  const unsigned __int16 *v13; // rcx
  REGHANDLE v14; // rcx
  int v15; // ebx
  HRESULT v17; // [rsp+30h] [rbp-99h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-91h] BYREF
  __int64 v19; // [rsp+40h] [rbp-89h] BYREF
  LPCWSTR lpName; // [rsp+48h] [rbp-81h] BYREF
  _DWORD v21[20]; // [rsp+50h] [rbp-79h] BYREF
  GUID ProviderId; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v23[32]; // [rsp+B0h] [rbp-19h] BYREF
  HRESULT *v24; // [rsp+D0h] [rbp+7h]
  __int64 v25; // [rsp+D8h] [rbp+Fh]

  v19 = 0;
  v4 = 0;
  memset_0(v21, 0, sizeof(v21));
  v5 = 0;
  lpName = 0;
  bstrString = 0;
  ProviderId = *(GUID *)&(*off_140023008)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_140023028 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_140023000, &RegHandle) )
    EventSetInformation(RegHandle, 2, (char *)off_140023008, *(unsigned __int16 *)off_140023008);
  McGenEventRegister_EventRegister();
  if ( (unsigned int)dword_140023000 > 5 )
  {
    v17 = 0;
    v24 = &v17;
    v25 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_140023000, byte_14001DA33, 0, 0, 3, v23);
  }
  Message = CoInitializeEx(0, 0);
  if ( Message < 0 )
    goto LABEL_40;
  v5 = 1;
  Message = PushRouter_Open(L"application/vnd.syncml.notification", L"x-wap-application:syncml.dm", &lpName, &v19);
  if ( Message >= 0 )
  {
    v4 = OpenEventW(0x100000u, 0, lpName);
    if ( !v4 )
    {
      LastError = GetLastError();
      Message = -2147024896;
      if ( LastError <= 0 )
        Message = LastError;
      goto LABEL_40;
    }
    if ( IsWvdFeatureEnabled() )
    {
      v9 = bstrString;
      if ( bstrString )
      {
        v10 = GetLastError();
        SysFreeString(v9);
        SetLastError(v10);
      }
      bstrString = 0;
      Message = QueryWvdEnrollmentId(&bstrString);
      if ( Message < 0 )
      {
        if ( (unsigned int)dword_140023000 <= 5 )
          goto LABEL_40;
        v7 = byte_14001D9C5;
        goto LABEL_38;
      }
      Message = InitializeThreadpools(bstrString);
      if ( Message < 0 )
      {
        if ( (unsigned int)dword_140023000 <= 5 )
          goto LABEL_40;
        v7 = byte_14001D98B;
        goto LABEL_38;
      }
    }
LABEL_24:
    if ( WaitForSingleObject(v4, 0x2710u)
      && (!qword_140024308 || !_InterlockedCompareExchange(&ThreadpoolManager::m_numberOfWorkQueued, 0, 0)) )
    {
      goto LABEL_40;
    }
    while ( 1 )
    {
      memset_0(v21, 0, sizeof(v21));
      v21[0] = 80;
      Message = PushRouter_GetMessageEx(v19, v21);
      if ( Message == 5439490 )
      {
        if ( (unsigned int)dword_140023000 > 5 )
        {
          v17 = Message;
          v24 = &v17;
          v25 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_140023000, byte_14001D95D, 0, 0, 3, v23);
        }
        goto LABEL_24;
      }
      if ( Message < 0 )
        break;
      v11 = HandleMessage((struct tagPushMsgEx *)v21);
      if ( v11 < 0 && (unsigned int)dword_140023000 > 5 )
      {
        v17 = v11;
        v25 = 4;
        v24 = &v17;
        tlgWriteTransfer_EventWriteTransfer(&dword_140023000, byte_14001D8F1, 0, 0, 3, v23);
      }
      PushRouter_FreeMessageEx(v21);
    }
    if ( (unsigned int)dword_140023000 <= 5 )
      goto LABEL_40;
    v7 = (char *)word_14001D922;
LABEL_38:
    v25 = 4;
    goto LABEL_39;
  }
  if ( (unsigned int)dword_140023000 > 5 )
  {
    v25 = 4;
    v7 = (char *)&unk_14001DA00;
LABEL_39:
    v24 = &v17;
    v17 = Message;
    tlgWriteTransfer_EventWriteTransfer(&dword_140023000, v7, 0, 0, 3, v23);
  }
LABEL_40:
  if ( IsWvdFeatureEnabled() )
  {
    v12 = (void (__fastcall ***)(_QWORD, __int64))qword_140024308;
    qword_140024308 = 0;
    if ( v12 )
      (**v12)(v12, 1);
  }
  PushRouter_FreeMessageEx(v21);
  PushRouter_FreeGetMessageEventName(lpName);
  PushRouter_Close(v19);
  if ( v4 )
    CloseHandle(v4);
  if ( v5 )
    CoUninitialize();
  COmaDmPrcLogger::GetLogger();
  IncrementCorrelationVectorForNextDmSession(v13);
  McGenEventUnregister_EventUnregister();
  v14 = RegHandle;
  dword_140023000 = 0;
  RegHandle = 0;
  EventUnregister(v14);
  v15 = (unsigned int)Message >> 31;
  if ( bstrString )
    SysFreeString(bstrString);
  return v15;
}

```

## disassembly

```asm
0x14000abe0  push    rbp
0x14000abe2  push    rbx
0x14000abe3  push    rsi
0x14000abe4  push    rdi
0x14000abe5  push    r13
0x14000abe7  push    r14
0x14000abe9  push    r15
0x14000abeb  lea     rbp, [rsp-27h]
0x14000abf0  sub     rsp, 0F0h
0x14000abf7  mov     rax, cs:__security_cookie
0x14000abfe  xor     rax, rsp
0x14000ac01  mov     [rbp+57h+var_40], rax
0x14000ac05  xor     r15d, r15d
0x14000ac08  lea     rcx, [rbp+57h+var_D0]; void *
0x14000ac0c  xor     edx, edx; Val
0x14000ac0e  mov     [rsp+120h+var_E0], r15
0x14000ac13  mov     esi, r15d
0x14000ac16  lea     r8d, [r15+50h]; Size
0x14000ac1a  call    memset_0
0x14000ac1f  cmp     cs:RegHandle, r15
0x14000ac26  mov     r14d, r15d
0x14000ac29  mov     rax, cs:off_140023008
0x14000ac30  mov     [rsp+120h+lpName], r15
0x14000ac35  mov     [rsp+120h+bstrString], r15
0x14000ac3a  movups  xmm0, xmmword ptr [rax-10h]
0x14000ac3e  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x14000ac43  jz      short loc_14000AC4B
0x14000ac45  lea     ecx, [r15+5]
0x14000ac49  int     29h; Win8: RtlFailFast(ecx)
0x14000ac4b  xorps   xmm0, xmm0
0x14000ac4e  lea     r13, dword_140023000
0x14000ac55  mov     r8, r13; CallbackContext
0x14000ac58  lea     r9, RegHandle; RegHandle
0x14000ac5f  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000ac66  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x14000ac6a  movdqu  cs:xmmword_140023028, xmm0
0x14000ac72  call    cs:__imp_EventRegister
0x14000ac79  nop     dword ptr [rax+rax+00h]
0x14000ac7e  test    eax, eax
0x14000ac80  jnz     short loc_14000ACA3
0x14000ac82  mov     r8, cs:off_140023008
0x14000ac89  lea     edx, [rax+2]
0x14000ac8c  mov     rcx, cs:RegHandle
0x14000ac93  movzx   r9d, word ptr [r8]
0x14000ac97  call    cs:__imp_EventSetInformation
0x14000ac9e  nop     dword ptr [rax+rax+00h]
0x14000aca3  call    McGenEventRegister_EventRegister
0x14000aca8  mov     eax, cs:dword_140023000
0x14000acae  mov     edi, 4
0x14000acb3  cmp     eax, 5
0x14000acb6  jbe     short loc_14000ACF0
0x14000acb8  lea     rax, [rsp+120h+var_F0]
0x14000acbd  mov     [rsp+120h+var_F0], r15d
0x14000acc2  mov     [rbp+57h+var_50], rax
0x14000acc6  lea     rdx, byte_14001DA33
0x14000accd  lea     rax, [rbp+57h+var_70]
0x14000acd1  mov     [rbp+57h+var_48], rdi
0x14000acd5  mov     [rsp+120h+var_F8], rax
0x14000acda  xor     r9d, r9d
0x14000acdd  xor     r8d, r8d
0x14000ace0  mov     [rsp+120h+var_100], 3
0x14000ace8  mov     rcx, r13
0x14000aceb  call    _tlgWriteTransfer_EventWriteTransfer
0x14000acf0  xor     edx, edx; dwCoInit
0x14000acf2  xor     ecx, ecx; pvReserved
0x14000acf4  call    cs:__imp_CoInitializeEx
0x14000acfb  nop     dword ptr [rax+rax+00h]
0x14000ad00  mov     ebx, eax
0x14000ad02  test    eax, eax
0x14000ad04  js      loc_14000AFAC
0x14000ad0a  lea     r9, [rsp+120h+var_E0]
0x14000ad0f  mov     r14d, 1
0x14000ad15  lea     r8, [rsp+120h+lpName]
0x14000ad1a  lea     rdx, ?c_szTriggerAppId@@3QBGB; "x-wap-application:syncml.dm"
0x14000ad21  lea     rcx, ?c_szTriggerContentType@@3QBGB; "application/vnd.syncml.notification"
0x14000ad28  call    cs:__imp_PushRouter_Open
0x14000ad2f  nop     dword ptr [rax+rax+00h]
0x14000ad34  mov     ebx, eax
0x14000ad36  test    eax, eax
0x14000ad38  jns     short loc_14000AD59
0x14000ad3a  mov     eax, cs:dword_140023000
0x14000ad40  cmp     eax, 5
0x14000ad43  jbe     loc_14000AFAC
0x14000ad49  mov     [rbp+57h+var_48], rdi
0x14000ad4d  lea     rdx, unk_14001DA00
0x14000ad54  jmp     loc_14000AF80
0x14000ad59  mov     r8, [rsp+120h+lpName]; lpName
0x14000ad5e  xor     edx, edx; bInheritHandle
0x14000ad60  mov     ecx, 100000h; dwDesiredAccess
0x14000ad65  call    cs:__imp_OpenEventW
0x14000ad6c  nop     dword ptr [rax+rax+00h]
0x14000ad71  mov     rsi, rax
0x14000ad74  test    rax, rax
0x14000ad77  jnz     short loc_14000AD94
0x14000ad79  call    cs:__imp_GetLastError
0x14000ad80  nop     dword ptr [rax+rax+00h]
0x14000ad85  test    eax, eax
0x14000ad87  mov     ebx, 80070000h
0x14000ad8c  cmovle  ebx, eax
0x14000ad8f  jmp     loc_14000AFAC
0x14000ad94  call    ?IsWvdFeatureEnabled@@YA_NXZ; IsWvdFeatureEnabled(void)
0x14000ad99  test    al, al
0x14000ad9b  jz      loc_14000AE36
0x14000ada1  mov     rdi, [rsp+120h+bstrString]
0x14000ada6  test    rdi, rdi
0x14000ada9  jz      short loc_14000ADD6
0x14000adab  call    cs:__imp_GetLastError
0x14000adb2  nop     dword ptr [rax+rax+00h]
0x14000adb7  mov     rcx, rdi; bstrString
0x14000adba  mov     ebx, eax
0x14000adbc  call    cs:__imp_SysFreeString
0x14000adc3  nop     dword ptr [rax+rax+00h]
0x14000adc8  mov     ecx, ebx; dwErrCode
0x14000adca  call    cs:__imp_SetLastError
0x14000add1  nop     dword ptr [rax+rax+00h]
0x14000add6  lea     rcx, [rsp+120h+bstrString]; unsigned __int16 **
0x14000addb  mov     [rsp+120h+bstrString], r15
0x14000ade0  call    ?QueryWvdEnrollmentId@@YAJPEAPEAG@Z; QueryWvdEnrollmentId(ushort * *)
0x14000ade5  mov     ebx, eax
0x14000ade7  test    eax, eax
0x14000ade9  jns     short loc_14000AE06
0x14000adeb  mov     eax, cs:dword_140023000
0x14000adf1  cmp     eax, 5
0x14000adf4  jbe     loc_14000AFAC
0x14000adfa  lea     rdx, byte_14001D9C5
0x14000ae01  jmp     loc_14000AF78
0x14000ae06  mov     rcx, [rsp+120h+bstrString]; unsigned __int16 *
0x14000ae0b  call    ?InitializeThreadpools@@YAJPEBG@Z; InitializeThreadpools(ushort const *)
0x14000ae10  mov     ebx, eax
0x14000ae12  test    eax, eax
0x14000ae14  jns     short loc_14000AE31
0x14000ae16  mov     eax, cs:dword_140023000
0x14000ae1c  cmp     eax, 5
0x14000ae1f  jbe     loc_14000AFAC
0x14000ae25  lea     rdx, byte_14001D98B
0x14000ae2c  jmp     loc_14000AF78
0x14000ae31  mov     edi, 4
0x14000ae36  mov     edx, 2710h; dwMilliseconds
0x14000ae3b  mov     rcx, rsi; hHandle
0x14000ae3e  call    cs:__imp_WaitForSingleObject
0x14000ae45  nop     dword ptr [rax+rax+00h]
0x14000ae4a  test    eax, eax
0x14000ae4c  jz      loc_14000AEDF
0x14000ae52  cmp     cs:qword_140024308, r15
0x14000ae59  jz      loc_14000AFAC
0x14000ae5f  mov     ecx, r15d
0x14000ae62  xor     eax, eax
0x14000ae64  lock cmpxchg cs:?m_numberOfWorkQueued@ThreadpoolManager@@0JC, ecx; long volatile ThreadpoolManager::m_numberOfWorkQueued
0x14000ae6c  jz      loc_14000AFAC
0x14000ae72  jmp     short loc_14000AEDF
0x14000ae74  test    ebx, ebx
0x14000ae76  js      loc_14000AF66
0x14000ae7c  lea     rcx, [rbp+57h+var_D0]; struct tagPushMsgEx *
0x14000ae80  call    ?HandleMessage@@YAJPEAUtagPushMsgEx@@@Z; HandleMessage(tagPushMsgEx *)
0x14000ae85  test    eax, eax
0x14000ae87  jns     short loc_14000AECF
0x14000ae89  mov     ecx, cs:dword_140023000
0x14000ae8f  cmp     ecx, 5
0x14000ae92  jbe     short loc_14000AECF
0x14000ae94  mov     [rsp+120h+var_F0], eax
0x14000ae98  lea     rdx, byte_14001D8F1
0x14000ae9f  lea     rax, [rsp+120h+var_F0]
0x14000aea4  mov     [rbp+57h+var_48], 4
0x14000aeac  mov     [rbp+57h+var_50], rax
0x14000aeb0  xor     r9d, r9d
0x14000aeb3  lea     rax, [rbp+57h+var_70]
0x14000aeb7  xor     r8d, r8d
0x14000aeba  mov     [rsp+120h+var_F8], rax
0x14000aebf  mov     rcx, r13
0x14000aec2  mov     [rsp+120h+var_100], 3
0x14000aeca  call    _tlgWriteTransfer_EventWriteTransfer
0x14000aecf  lea     rcx, [rbp+57h+var_D0]
0x14000aed3  call    cs:__imp_PushRouter_FreeMessageEx
0x14000aeda  nop     dword ptr [rax+rax+00h]
0x14000aedf  mov     ebx, 50h ; 'P'
0x14000aee4  lea     rcx, [rbp+57h+var_D0]; void *
0x14000aee8  mov     r8d, ebx; Size
0x14000aeeb  xor     edx, edx; Val
0x14000aeed  call    memset_0
0x14000aef2  mov     rcx, [rsp+120h+var_E0]
0x14000aef7  lea     rdx, [rbp+57h+var_D0]
0x14000aefb  mov     [rbp+57h+var_D0], ebx
0x14000aefe  call    cs:__imp_PushRouter_GetMessageEx
0x14000af05  nop     dword ptr [rax+rax+00h]
0x14000af0a  mov     ebx, eax
0x14000af0c  cmp     eax, 530002h
0x14000af11  jnz     loc_14000AE74
0x14000af17  mov     eax, cs:dword_140023000
0x14000af1d  cmp     eax, 5
0x14000af20  jbe     loc_14000AE36
0x14000af26  lea     rax, [rsp+120h+var_F0]
0x14000af2b  mov     [rsp+120h+var_F0], ebx
0x14000af2f  mov     [rbp+57h+var_50], rax
0x14000af33  lea     rdx, byte_14001D95D
0x14000af3a  lea     rax, [rbp+57h+var_70]
0x14000af3e  mov     [rbp+57h+var_48], 4
0x14000af46  mov     [rsp+120h+var_F8], rax
0x14000af4b  xor     r9d, r9d
0x14000af4e  xor     r8d, r8d
0x14000af51  mov     [rsp+120h+var_100], 3
0x14000af59  mov     rcx, r13
0x14000af5c  call    _tlgWriteTransfer_EventWriteTransfer
0x14000af61  jmp     loc_14000AE36
0x14000af66  mov     eax, cs:dword_140023000
0x14000af6c  cmp     eax, 5
0x14000af6f  jbe     short loc_14000AFAC
0x14000af71  lea     rdx, word_14001D922
0x14000af78  mov     [rbp+57h+var_48], 4
0x14000af80  lea     rax, [rsp+120h+var_F0]
0x14000af85  mov     [rbp+57h+var_50], rax
0x14000af89  lea     rax, [rbp+57h+var_70]
0x14000af8d  mov     [rsp+120h+var_F8], rax
0x14000af92  mov     [rsp+120h+var_100], 3
0x14000af9a  xor     r9d, r9d
0x14000af9d  mov     [rsp+120h+var_F0], ebx
0x14000afa1  xor     r8d, r8d
0x14000afa4  mov     rcx, r13
0x14000afa7  call    _tlgWriteTransfer_EventWriteTransfer
0x14000afac  call    ?IsWvdFeatureEnabled@@YA_NXZ; IsWvdFeatureEnabled(void)
0x14000afb1  test    al, al
0x14000afb3  jz      short loc_14000AFD8
0x14000afb5  mov     rcx, cs:qword_140024308
0x14000afbc  mov     cs:qword_140024308, r15
0x14000afc3  test    rcx, rcx
0x14000afc6  jz      short loc_14000AFD8
0x14000afc8  mov     rax, [rcx]
0x14000afcb  mov     edx, 1
0x14000afd0  mov     rax, [rax]
0x14000afd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afd8  lea     rcx, [rbp+57h+var_D0]
0x14000afdc  call    cs:__imp_PushRouter_FreeMessageEx
0x14000afe3  nop     dword ptr [rax+rax+00h]
0x14000afe8  mov     rcx, [rsp+120h+lpName]
0x14000afed  call    cs:__imp_PushRouter_FreeGetMessageEventName
0x14000aff4  nop     dword ptr [rax+rax+00h]
0x14000aff9  mov     rcx, [rsp+120h+var_E0]
0x14000affe  call    cs:__imp_PushRouter_Close
0x14000b005  nop     dword ptr [rax+rax+00h]
0x14000b00a  test    rsi, rsi
0x14000b00d  jz      short loc_14000B01E
0x14000b00f  mov     rcx, rsi; hObject
0x14000b012  call    cs:__imp_CloseHandle
0x14000b019  nop     dword ptr [rax+rax+00h]
0x14000b01e  test    r14d, r14d
0x14000b021  jz      short loc_14000B02F
0x14000b023  call    cs:__imp_CoUninitialize
0x14000b02a  nop     dword ptr [rax+rax+00h]
0x14000b02f  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x14000b034  call    ?IncrementCorrelationVectorForNextDmSession@@YAJPEBG@Z; IncrementCorrelationVectorForNextDmSession(ushort const *)
0x14000b039  call    McGenEventUnregister_EventUnregister
0x14000b03e  mov     rcx, cs:RegHandle; RegHandle
0x14000b045  mov     cs:dword_140023000, r15d
0x14000b04c  mov     cs:RegHandle, r15
0x14000b053  call    cs:__imp_EventUnregister
0x14000b05a  nop     dword ptr [rax+rax+00h]
0x14000b05f  mov     rcx, [rsp+120h+bstrString]; bstrString
0x14000b064  shr     ebx, 1Fh
0x14000b067  test    rcx, rcx
0x14000b06a  jz      short loc_14000B078
0x14000b06c  call    cs:__imp_SysFreeString
0x14000b073  nop     dword ptr [rax+rax+00h]
0x14000b078  mov     eax, ebx
0x14000b07a  mov     rcx, [rbp+57h+var_40]
0x14000b07e  xor     rcx, rsp; StackCookie
0x14000b081  call    __security_check_cookie
0x14000b086  add     rsp, 0F0h
0x14000b08d  pop     r15
0x14000b08f  pop     r14
0x14000b091  pop     r13
0x14000b093  pop     rdi
0x14000b094  pop     rsi
0x14000b095  pop     rbx
0x14000b096  pop     rbp
0x14000b097  retn
```
