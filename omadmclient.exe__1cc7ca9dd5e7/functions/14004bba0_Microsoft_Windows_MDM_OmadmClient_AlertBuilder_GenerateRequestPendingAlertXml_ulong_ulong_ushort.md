# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateRequestPendingAlertXml(ulong,ulong,ushort * *)

- ea: `0x14004bba0`
- end: `0x14004bcaf`
- name: `?GenerateRequestPendingAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJKKPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004bba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bc50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bc50`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004bc40`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004bc40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004bc77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004bc77`

## string_xrefs

- `0x14004bc0d`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">Reversed-Domain-Name:com.microsoft.mdm.requestpending</Type></Meta><Data>%2!d!</Data></Item></Alert>`
- `0x14004bbb1`: `GenerateRequestPendingAlertXml`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateRequestPendingAlertXml(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebx
  signed int LastError; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-9h] BYREF
  va_list Arguments[2]; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v12[3]; // [rsp+58h] [rbp+Fh] BYREF
  int v13; // [rsp+70h] [rbp+27h]
  int *v14; // [rsp+78h] [rbp+2Fh]
  int v15; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = a3;
  v12[1] = "GenerateRequestPendingAlertXml";
  v6 = a2;
  v15 = 0;
  v12[0] = 0;
  v12[2] = COmaDmLogger::GetLogger();
  v14 = &v15;
  v13 = 2;
  if ( a4 )
  {
    *a4 = 0;
    Arguments[0] = (va_list)v6;
    Arguments[1] = (va_list)v4;
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(
           0x2500u,
           L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">Reversed-Domain-Name:co"
            "m.microsoft.mdm.requestpending</Type></Meta><Data>%2!d!</Data></Item></Alert>",
           0,
           0,
           Buffer,
           0x100u,
           Arguments) )
    {
      *a4 = *(unsigned __int16 **)Buffer;
      v7 = v15;
      *(_QWORD *)Buffer = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v15 = v7;
      if ( *(_QWORD *)Buffer )
        LocalFree(*(HLOCAL *)Buffer);
    }
  }
  else
  {
    v7 = -805306127;
    v15 = -805306127;
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v12);
  return v7;
}

```

## disassembly

```asm
0x14004bba0  push    rbp
0x14004bba2  push    rbx
0x14004bba3  push    rsi
0x14004bba4  push    rdi
0x14004bba5  lea     rbp, [rsp-3Fh]
0x14004bbaa  sub     rsp, 88h
0x14004bbb1  lea     rax, aGeneratereques; "GenerateRequestPendingAlertXml"
0x14004bbb8  mov     edi, r8d
0x14004bbbb  mov     [rbp+57h+var_40], rax
0x14004bbbf  mov     rbx, r9
0x14004bbc2  mov     esi, edx
0x14004bbc4  mov     [rbp+57h+arg_18], 0
0x14004bbcb  mov     [rbp+57h+var_48], 0
0x14004bbd3  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004bbd8  mov     [rbp+57h+var_38], rax
0x14004bbdc  lea     rax, [rbp+57h+arg_18]
0x14004bbe0  mov     [rbp+57h+var_28], rax
0x14004bbe4  mov     [rbp+57h+var_30], 2
0x14004bbeb  test    rbx, rbx
0x14004bbee  jnz     short loc_14004BBFD
0x14004bbf0  mov     ebx, 0D00000F1h
0x14004bbf5  mov     [rbp+57h+arg_18], ebx
0x14004bbf8  jmp     loc_14004BC97
0x14004bbfd  lea     rax, [rbp+57h+var_58]
0x14004bc01  mov     qword ptr [rbx], 0
0x14004bc08  mov     [rsp+0A0h+Arguments], rax; Arguments
0x14004bc0d  lea     rdx, ?gc_szRequestPendingAlert@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004bc14  lea     rax, [rbp+57h+Buffer]
0x14004bc18  mov     [rsp+0A0h+nSize], 100h; nSize
0x14004bc20  xor     r9d, r9d; dwLanguageId
0x14004bc23  mov     [rsp+0A0h+lpBuffer], rax; lpBuffer
0x14004bc28  xor     r8d, r8d; dwMessageId
0x14004bc2b  mov     [rbp+57h+var_58], rsi
0x14004bc2f  mov     ecx, 2500h; dwFlags
0x14004bc34  mov     [rbp+57h+var_50], rdi
0x14004bc38  mov     qword ptr [rbp+57h+Buffer], 0
0x14004bc40  call    cs:__imp_FormatMessageW
0x14004bc47  nop     dword ptr [rax+rax+00h]
0x14004bc4c  test    eax, eax
0x14004bc4e  jnz     short loc_14004BC85
0x14004bc50  call    cs:__imp_GetLastError
0x14004bc57  nop     dword ptr [rax+rax+00h]
0x14004bc5c  mov     ebx, eax
0x14004bc5e  test    eax, eax
0x14004bc60  jle     short loc_14004BC6B
0x14004bc62  movzx   ebx, ax
0x14004bc65  or      ebx, 80070000h
0x14004bc6b  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x14004bc6f  mov     [rbp+57h+arg_18], ebx
0x14004bc72  test    rcx, rcx
0x14004bc75  jz      short loc_14004BC97
0x14004bc77  call    cs:__imp_LocalFree
0x14004bc7e  nop     dword ptr [rax+rax+00h]
0x14004bc83  jmp     short loc_14004BC97
0x14004bc85  mov     rax, qword ptr [rbp+57h+Buffer]
0x14004bc89  mov     [rbx], rax
0x14004bc8c  mov     ebx, [rbp+57h+arg_18]
0x14004bc8f  mov     qword ptr [rbp+57h+Buffer], 0
0x14004bc97  lea     rcx, [rbp+57h+var_48]; this
0x14004bc9b  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004bca0  mov     eax, ebx
0x14004bca2  add     rsp, 88h
0x14004bca9  pop     rdi
0x14004bcaa  pop     rsi
0x14004bcab  pop     rbx
0x14004bcac  pop     rbp
0x14004bcad  retn
```
