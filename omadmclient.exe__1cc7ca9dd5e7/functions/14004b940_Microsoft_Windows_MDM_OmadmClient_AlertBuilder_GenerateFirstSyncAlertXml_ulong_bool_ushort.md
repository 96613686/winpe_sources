# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateFirstSyncAlertXml(ulong,bool,ushort * *)

- ea: `0x14004b940`
- end: `0x14004ba64`
- name: `?GenerateFirstSyncAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJK_NPEAPEAG@Z`
- size: `292`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, unsigned int, bool, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004b940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ba05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ba05`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004b9f5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004b9f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004ba2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004ba2c`

## string_xrefs

- `0x14004b9c5`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft/MDM/BootstrapSync</Type></Meta><Data>%2</Data></Item></Alert>`
- `0x14004b951`: `GenerateFirstSyncAlertXml`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateFirstSyncAlertXml(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        unsigned int a2,
        char a3,
        unsigned __int16 **a4)
{
  unsigned __int64 v4; // rsi
  unsigned int v7; // ebx
  const wchar_t *v8; // rax
  signed int LastError; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-9h] BYREF
  va_list Arguments[2]; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v13[3]; // [rsp+58h] [rbp+Fh] BYREF
  int v14; // [rsp+70h] [rbp+27h]
  int *v15; // [rsp+78h] [rbp+2Fh]
  int v16; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = a2;
  v13[1] = "GenerateFirstSyncAlertXml";
  v16 = 0;
  v13[0] = 0;
  v13[2] = COmaDmLogger::GetLogger();
  v15 = &v16;
  v14 = 2;
  if ( a4 )
  {
    *a4 = 0;
    Arguments[0] = (va_list)v4;
    v8 = L"device";
    *(_QWORD *)Buffer = 0;
    if ( !a3 )
      v8 = L"user";
    Arguments[1] = (va_list)v8;
    if ( FormatMessageW(
           0x2500u,
           L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft/MDM/Boots"
            "trapSync</Type></Meta><Data>%2</Data></Item></Alert>",
           0,
           0,
           Buffer,
           0x100u,
           Arguments) )
    {
      *a4 = *(unsigned __int16 **)Buffer;
      v7 = v16;
      *(_QWORD *)Buffer = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v16 = v7;
      if ( *(_QWORD *)Buffer )
        LocalFree(*(HLOCAL *)Buffer);
    }
  }
  else
  {
    v7 = -805306126;
    v16 = -805306126;
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v13);
  return v7;
}

```

## disassembly

```asm
0x14004b940  push    rbp
0x14004b942  push    rbx
0x14004b943  push    rsi
0x14004b944  push    rdi
0x14004b945  lea     rbp, [rsp-3Fh]
0x14004b94a  sub     rsp, 88h
0x14004b951  lea     rax, aGeneratefirsts_0; "GenerateFirstSyncAlertXml"
0x14004b958  mov     esi, edx
0x14004b95a  mov     [rbp+57h+var_40], rax
0x14004b95e  mov     rbx, r9
0x14004b961  mov     dil, r8b
0x14004b964  mov     [rbp+57h+arg_18], 0
0x14004b96b  mov     [rbp+57h+var_48], 0
0x14004b973  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004b978  mov     [rbp+57h+var_38], rax
0x14004b97c  lea     rax, [rbp+57h+arg_18]
0x14004b980  mov     [rbp+57h+var_28], rax
0x14004b984  mov     [rbp+57h+var_30], 2
0x14004b98b  test    rbx, rbx
0x14004b98e  jnz     short loc_14004B99D
0x14004b990  mov     ebx, 0D00000F2h
0x14004b995  mov     [rbp+57h+arg_18], ebx
0x14004b998  jmp     loc_14004BA4C
0x14004b99d  lea     rcx, aUser; "user"
0x14004b9a4  mov     qword ptr [rbx], 0
0x14004b9ab  test    dil, dil
0x14004b9ae  mov     [rbp+57h+var_58], rsi
0x14004b9b2  lea     rax, aDevice_0; "device"
0x14004b9b9  mov     qword ptr [rbp+57h+Buffer], 0
0x14004b9c1  cmovz   rax, rcx
0x14004b9c5  lea     rdx, ?gc_szFirstSyncTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004b9cc  mov     [rbp+57h+var_50], rax
0x14004b9d0  xor     r9d, r9d; dwLanguageId
0x14004b9d3  lea     rax, [rbp+57h+var_58]
0x14004b9d7  xor     r8d, r8d; dwMessageId
0x14004b9da  mov     [rsp+0A0h+Arguments], rax; Arguments
0x14004b9df  mov     ecx, 2500h; dwFlags
0x14004b9e4  lea     rax, [rbp+57h+Buffer]
0x14004b9e8  mov     [rsp+0A0h+nSize], 100h; nSize
0x14004b9f0  mov     [rsp+0A0h+lpBuffer], rax; lpBuffer
0x14004b9f5  call    cs:__imp_FormatMessageW
0x14004b9fc  nop     dword ptr [rax+rax+00h]
0x14004ba01  test    eax, eax
0x14004ba03  jnz     short loc_14004BA3A
0x14004ba05  call    cs:__imp_GetLastError
0x14004ba0c  nop     dword ptr [rax+rax+00h]
0x14004ba11  mov     ebx, eax
0x14004ba13  test    eax, eax
0x14004ba15  jle     short loc_14004BA20
0x14004ba17  movzx   ebx, ax
0x14004ba1a  or      ebx, 80070000h
0x14004ba20  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x14004ba24  mov     [rbp+57h+arg_18], ebx
0x14004ba27  test    rcx, rcx
0x14004ba2a  jz      short loc_14004BA4C
0x14004ba2c  call    cs:__imp_LocalFree
0x14004ba33  nop     dword ptr [rax+rax+00h]
0x14004ba38  jmp     short loc_14004BA4C
0x14004ba3a  mov     rax, qword ptr [rbp+57h+Buffer]
0x14004ba3e  mov     [rbx], rax
0x14004ba41  mov     ebx, [rbp+57h+arg_18]
0x14004ba44  mov     qword ptr [rbp+57h+Buffer], 0
0x14004ba4c  lea     rcx, [rbp+57h+var_48]; this
0x14004ba50  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004ba55  mov     eax, ebx
0x14004ba57  add     rsp, 88h
0x14004ba5e  pop     rdi
0x14004ba5f  pop     rsi
0x14004ba60  pop     rbx
0x14004ba61  pop     rbp
0x14004ba62  retn
```
