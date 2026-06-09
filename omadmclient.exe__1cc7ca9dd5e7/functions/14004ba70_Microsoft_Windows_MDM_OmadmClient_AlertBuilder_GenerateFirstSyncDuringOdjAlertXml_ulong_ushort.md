# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateFirstSyncDuringOdjAlertXml(ulong,ushort * *)

- ea: `0x14004ba70`
- end: `0x14004bb90`
- name: `?GenerateFirstSyncDuringOdjAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJKPEAPEAG@Z`
- size: `288`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004ba70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bb28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bb28`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004bb18`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004bb18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004bb4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004bb4f`

## string_xrefs

- `0x14004bae0`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft/MDM/OdjSync</Type></Meta><Data>%2</Data></Item></Alert>`
- `0x14004ba85`: `GenerateFirstSyncDuringOdjAlertXml`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateFirstSyncDuringOdjAlertXml(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        unsigned int a2,
        unsigned __int16 **a3)
{
  unsigned __int64 v3; // rdi
  unsigned int v5; // ebx
  signed int LastError; // eax
  va_list Arguments[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v9[3]; // [rsp+50h] [rbp-30h] BYREF
  int v10; // [rsp+68h] [rbp-18h]
  int *v11; // [rsp+70h] [rbp-10h]
  int v12; // [rsp+A0h] [rbp+20h] BYREF
  unsigned __int16 *Buffer; // [rsp+A8h] [rbp+28h] BYREF

  v3 = a2;
  v9[1] = "GenerateFirstSyncDuringOdjAlertXml";
  v12 = 0;
  v9[0] = 0;
  v9[2] = COmaDmLogger::GetLogger();
  v11 = &v12;
  v10 = 2;
  if ( a3 )
  {
    *a3 = 0;
    Arguments[1] = (va_list)L"device";
    Arguments[0] = (va_list)v3;
    Buffer = 0;
    if ( FormatMessageW(
           0x2500u,
           L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft/MDM/OdjSy"
            "nc</Type></Meta><Data>%2</Data></Item></Alert>",
           0,
           0,
           (LPWSTR)&Buffer,
           0x100u,
           Arguments) )
    {
      *a3 = Buffer;
      v5 = v12;
      Buffer = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v12 = v5;
      if ( Buffer )
        LocalFree(Buffer);
    }
  }
  else
  {
    v5 = -805306128;
    v12 = -805306128;
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v9);
  return v5;
}

```

## disassembly

```asm
0x14004ba70  mov     [rsp-8+arg_0], rbx
0x14004ba75  mov     [rsp-8+arg_8], rdi
0x14004ba7a  push    rbp
0x14004ba7b  mov     rbp, rsp
0x14004ba7e  sub     rsp, 80h
0x14004ba85  lea     rax, aGeneratefirsts; "GenerateFirstSyncDuringOdjAlertXml"
0x14004ba8c  mov     edi, edx
0x14004ba8e  mov     [rbp+var_28], rax
0x14004ba92  mov     rbx, r8
0x14004ba95  mov     [rbp+arg_10], 0
0x14004ba9c  mov     [rbp+var_30], 0
0x14004baa4  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004baa9  mov     [rbp+var_20], rax
0x14004baad  lea     rax, [rbp+arg_10]
0x14004bab1  mov     [rbp+var_10], rax
0x14004bab5  mov     [rbp+var_18], 2
0x14004babc  test    rbx, rbx
0x14004babf  jnz     short loc_14004BACE
0x14004bac1  mov     ebx, 0D00000F0h
0x14004bac6  mov     [rbp+arg_10], ebx
0x14004bac9  jmp     loc_14004BB6F
0x14004bace  lea     rax, aDevice_0; "device"
0x14004bad5  mov     qword ptr [rbx], 0
0x14004badc  mov     [rbp+var_38], rax
0x14004bae0  lea     rdx, ?gc_szFirstSyncDuringOdjTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004bae7  lea     rax, [rbp+var_40]
0x14004baeb  mov     [rbp+var_40], rdi
0x14004baef  mov     [rsp+80h+Arguments], rax; Arguments
0x14004baf4  xor     r9d, r9d; dwLanguageId
0x14004baf7  lea     rax, [rbp+Buffer]
0x14004bafb  mov     [rsp+80h+nSize], 100h; nSize
0x14004bb03  xor     r8d, r8d; dwMessageId
0x14004bb06  mov     [rsp+80h+lpBuffer], rax; lpBuffer
0x14004bb0b  mov     ecx, 2500h; dwFlags
0x14004bb10  mov     [rbp+Buffer], 0
0x14004bb18  call    cs:__imp_FormatMessageW
0x14004bb1f  nop     dword ptr [rax+rax+00h]
0x14004bb24  test    eax, eax
0x14004bb26  jnz     short loc_14004BB5D
0x14004bb28  call    cs:__imp_GetLastError
0x14004bb2f  nop     dword ptr [rax+rax+00h]
0x14004bb34  mov     ebx, eax
0x14004bb36  test    eax, eax
0x14004bb38  jle     short loc_14004BB43
0x14004bb3a  movzx   ebx, ax
0x14004bb3d  or      ebx, 80070000h
0x14004bb43  mov     rcx, [rbp+Buffer]; hMem
0x14004bb47  mov     [rbp+arg_10], ebx
0x14004bb4a  test    rcx, rcx
0x14004bb4d  jz      short loc_14004BB6F
0x14004bb4f  call    cs:__imp_LocalFree
0x14004bb56  nop     dword ptr [rax+rax+00h]
0x14004bb5b  jmp     short loc_14004BB6F
0x14004bb5d  mov     rax, [rbp+Buffer]
0x14004bb61  mov     [rbx], rax
0x14004bb64  mov     ebx, [rbp+arg_10]
0x14004bb67  mov     [rbp+Buffer], 0
0x14004bb6f  lea     rcx, [rbp+var_30]; this
0x14004bb73  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004bb78  lea     r11, [rsp+80h+var_s0]
0x14004bb80  mov     eax, ebx
0x14004bb82  mov     rbx, [r11+10h]
0x14004bb86  mov     rdi, [r11+18h]
0x14004bb8a  mov     rsp, r11
0x14004bb8d  pop     rbp
0x14004bb8e  retn
```
