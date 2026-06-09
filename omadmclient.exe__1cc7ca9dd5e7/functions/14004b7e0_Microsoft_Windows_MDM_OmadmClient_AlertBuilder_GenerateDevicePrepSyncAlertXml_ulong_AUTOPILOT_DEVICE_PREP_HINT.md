# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateDevicePrepSyncAlertXml(ulong,AUTOPILOT_DEVICE_PREP_HINT,ushort * *)

- ea: `0x14004b7e0`
- end: `0x14004b92e`
- name: `?GenerateDevicePrepSyncAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJKW4AUTOPILOT_DEVICE_PREP_HINT@@PEAPEAG@Z`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004b7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b8cf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004b8bf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004b8bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b8f6`

## string_xrefs

- `0x14004b893`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft/MDM/DevicePrepSync</Type></Meta><Data>%2</Data></Item></Alert>`
- `0x14004b7f1`: `GenerateAutopilotV2AlertXml`
- `0x14004b86d`: `ProvisioningComplete`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateDevicePrepSyncAlertXml(
        __int64 a1,
        unsigned int a2,
        int a3,
        _QWORD *a4)
{
  va_list v4; // rsi
  unsigned int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  const wchar_t *v11; // rax
  signed int LastError; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-9h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-1h] BYREF
  const wchar_t *v16; // [rsp+50h] [rbp+7h]
  _QWORD v17[3]; // [rsp+58h] [rbp+Fh] BYREF
  int v18; // [rsp+70h] [rbp+27h]
  unsigned int *v19; // [rsp+78h] [rbp+2Fh]
  unsigned int v20; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = (va_list)a2;
  v17[1] = "GenerateAutopilotV2AlertXml";
  v20 = 0;
  v17[0] = 0;
  v17[2] = COmaDmLogger::GetLogger();
  v19 = &v20;
  v18 = 2;
  if ( !a4 )
  {
    v7 = -2147467261;
    goto LABEL_18;
  }
  *a4 = 0;
  *(_QWORD *)Buffer = 0;
  v16 = 0;
  Arguments = v4;
  v8 = a3 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
        {
LABEL_17:
          v7 = v20;
          goto LABEL_18;
        }
        v11 = L"ProvisioningComplete";
      }
      else
      {
        v11 = L"ExecutingProvisioning";
      }
    }
    else
    {
      v11 = L"Bootstrapping";
    }
  }
  else
  {
    v11 = L"PendingProvisioning";
  }
  v16 = v11;
  if ( FormatMessageW(
         0x2500u,
         L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft/MDM/DeviceP"
          "repSync</Type></Meta><Data>%2</Data></Item></Alert>",
         0,
         0,
         Buffer,
         0x100u,
         &Arguments) )
  {
    *a4 = *(_QWORD *)Buffer;
    *(_QWORD *)Buffer = 0;
    goto LABEL_17;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  v20 = v7;
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
LABEL_18:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v17);
  return v7;
}

```

## disassembly

```asm
0x14004b7e0  push    rbp
0x14004b7e2  push    rbx
0x14004b7e3  push    rsi
0x14004b7e4  push    rdi
0x14004b7e5  lea     rbp, [rsp-3Fh]
0x14004b7ea  sub     rsp, 88h
0x14004b7f1  lea     rax, aGenerateautopi; "GenerateAutopilotV2AlertXml"
0x14004b7f8  mov     esi, edx
0x14004b7fa  mov     [rbp+57h+var_40], rax
0x14004b7fe  mov     rdi, r9
0x14004b801  mov     ebx, r8d
0x14004b804  mov     [rbp+57h+arg_18], 0
0x14004b80b  mov     [rbp+57h+var_48], 0
0x14004b813  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004b818  mov     [rbp+57h+var_38], rax
0x14004b81c  lea     rax, [rbp+57h+arg_18]
0x14004b820  mov     [rbp+57h+var_28], rax
0x14004b824  mov     [rbp+57h+var_30], 2
0x14004b82b  test    rdi, rdi
0x14004b82e  jnz     short loc_14004B83A
0x14004b830  mov     ebx, 80004003h
0x14004b835  jmp     loc_14004B916
0x14004b83a  mov     qword ptr [rdi], 0
0x14004b841  mov     qword ptr [rbp+57h+Buffer], 0
0x14004b849  mov     [rbp+57h+var_50], 0
0x14004b851  mov     [rbp+57h+var_58], rsi
0x14004b855  sub     ebx, 1
0x14004b858  jz      short loc_14004B888
0x14004b85a  sub     ebx, 1
0x14004b85d  jz      short loc_14004B87F
0x14004b85f  sub     ebx, 1
0x14004b862  jz      short loc_14004B876
0x14004b864  cmp     ebx, 1
0x14004b867  jnz     loc_14004B913
0x14004b86d  lea     rax, aProvisioningco; "ProvisioningComplete"
0x14004b874  jmp     short loc_14004B88F
0x14004b876  lea     rax, aExecutingprovi; "ExecutingProvisioning"
0x14004b87d  jmp     short loc_14004B88F
0x14004b87f  lea     rax, aBootstrapping; "Bootstrapping"
0x14004b886  jmp     short loc_14004B88F
0x14004b888  lea     rax, aPendingprovisi; "PendingProvisioning"
0x14004b88f  mov     [rbp+57h+var_50], rax
0x14004b893  lea     rdx, ?gc_szDevicePrepSyncAlertTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004b89a  lea     rax, [rbp+57h+var_58]
0x14004b89e  xor     r9d, r9d; dwLanguageId
0x14004b8a1  mov     [rsp+0A0h+Arguments], rax; Arguments
0x14004b8a6  xor     r8d, r8d; dwMessageId
0x14004b8a9  lea     rax, [rbp+57h+Buffer]
0x14004b8ad  mov     [rsp+0A0h+nSize], 100h; nSize
0x14004b8b5  mov     ecx, 2500h; dwFlags
0x14004b8ba  mov     [rsp+0A0h+lpBuffer], rax; lpBuffer
0x14004b8bf  call    cs:__imp_FormatMessageW
0x14004b8c6  nop     dword ptr [rax+rax+00h]
0x14004b8cb  test    eax, eax
0x14004b8cd  jnz     short loc_14004B904
0x14004b8cf  call    cs:__imp_GetLastError
0x14004b8d6  nop     dword ptr [rax+rax+00h]
0x14004b8db  mov     ebx, eax
0x14004b8dd  test    eax, eax
0x14004b8df  jle     short loc_14004B8EA
0x14004b8e1  movzx   ebx, ax
0x14004b8e4  or      ebx, 80070000h
0x14004b8ea  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x14004b8ee  mov     [rbp+57h+arg_18], ebx
0x14004b8f1  test    rcx, rcx
0x14004b8f4  jz      short loc_14004B916
0x14004b8f6  call    cs:__imp_LocalFree
0x14004b8fd  nop     dword ptr [rax+rax+00h]
0x14004b902  jmp     short loc_14004B916
0x14004b904  mov     rax, qword ptr [rbp+57h+Buffer]
0x14004b908  mov     [rdi], rax
0x14004b90b  mov     qword ptr [rbp+57h+Buffer], 0
0x14004b913  mov     ebx, [rbp+57h+arg_18]
0x14004b916  lea     rcx, [rbp+57h+var_48]; this
0x14004b91a  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004b91f  mov     eax, ebx
0x14004b921  add     rsp, 88h
0x14004b928  pop     rdi
0x14004b929  pop     rsi
0x14004b92a  pop     rbx
0x14004b92b  pop     rbp
0x14004b92c  retn
```
