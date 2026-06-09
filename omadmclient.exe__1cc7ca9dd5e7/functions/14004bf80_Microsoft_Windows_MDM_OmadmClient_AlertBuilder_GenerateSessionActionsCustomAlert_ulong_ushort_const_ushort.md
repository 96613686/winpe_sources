# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateSessionActionsCustomAlert(ulong,ushort const *,ushort * *)

- ea: `0x14004bf80`
- end: `0x14004c08f`
- name: `?GenerateSessionActionsCustomAlert@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJKPEBGPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004bf80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c030`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004c020`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004c020`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004c057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004c057`

## string_xrefs

- `0x14004bfed`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft/MDM/CustomAlert</Type></Meta><Data>%2</Data></Item></Alert>`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateSessionActionsCustomAlert(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int64 v4; // rsi
  unsigned int v7; // ebx
  signed int LastError; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-9h] BYREF
  va_list Arguments[2]; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v12[3]; // [rsp+58h] [rbp+Fh] BYREF
  int v13; // [rsp+70h] [rbp+27h]
  int *v14; // [rsp+78h] [rbp+2Fh]
  int v15; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = a2;
  v12[1] = "GenerateSessionActionsCustomAlert";
  v15 = 0;
  v12[0] = 0;
  v12[2] = COmaDmLogger::GetLogger();
  v14 = &v15;
  v13 = 2;
  if ( a4 )
  {
    *a4 = 0;
    Arguments[0] = (va_list)v4;
    Arguments[1] = (va_list)a3;
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(
           0x2500u,
           L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft/MDM/Custo"
            "mAlert</Type></Meta><Data>%2</Data></Item></Alert>",
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
    v7 = -805306126;
    v15 = -805306126;
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v12);
  return v7;
}

```

## disassembly

```asm
0x14004bf80  push    rbp
0x14004bf82  push    rbx
0x14004bf83  push    rsi
0x14004bf84  push    rdi
0x14004bf85  lea     rbp, [rsp-3Fh]
0x14004bf8a  sub     rsp, 88h
0x14004bf91  lea     rax, aGeneratesessio; "GenerateSessionActionsCustomAlert"
0x14004bf98  mov     esi, edx
0x14004bf9a  mov     [rbp+57h+var_40], rax
0x14004bf9e  mov     rbx, r9
0x14004bfa1  mov     rdi, r8
0x14004bfa4  mov     [rbp+57h+arg_18], 0
0x14004bfab  mov     [rbp+57h+var_48], 0
0x14004bfb3  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004bfb8  mov     [rbp+57h+var_38], rax
0x14004bfbc  lea     rax, [rbp+57h+arg_18]
0x14004bfc0  mov     [rbp+57h+var_28], rax
0x14004bfc4  mov     [rbp+57h+var_30], 2
0x14004bfcb  test    rbx, rbx
0x14004bfce  jnz     short loc_14004BFDD
0x14004bfd0  mov     ebx, 0D00000F2h
0x14004bfd5  mov     [rbp+57h+arg_18], ebx
0x14004bfd8  jmp     loc_14004C077
0x14004bfdd  lea     rax, [rbp+57h+var_58]
0x14004bfe1  mov     qword ptr [rbx], 0
0x14004bfe8  mov     [rsp+0A0h+Arguments], rax; Arguments
0x14004bfed  lea     rdx, ?gc_szSessionActionsCustomAlertBody@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004bff4  lea     rax, [rbp+57h+Buffer]
0x14004bff8  mov     [rsp+0A0h+nSize], 100h; nSize
0x14004c000  xor     r9d, r9d; dwLanguageId
0x14004c003  mov     [rsp+0A0h+lpBuffer], rax; lpBuffer
0x14004c008  xor     r8d, r8d; dwMessageId
0x14004c00b  mov     [rbp+57h+var_58], rsi
0x14004c00f  mov     ecx, 2500h; dwFlags
0x14004c014  mov     [rbp+57h+var_50], rdi
0x14004c018  mov     qword ptr [rbp+57h+Buffer], 0
0x14004c020  call    cs:__imp_FormatMessageW
0x14004c027  nop     dword ptr [rax+rax+00h]
0x14004c02c  test    eax, eax
0x14004c02e  jnz     short loc_14004C065
0x14004c030  call    cs:__imp_GetLastError
0x14004c037  nop     dword ptr [rax+rax+00h]
0x14004c03c  mov     ebx, eax
0x14004c03e  test    eax, eax
0x14004c040  jle     short loc_14004C04B
0x14004c042  movzx   ebx, ax
0x14004c045  or      ebx, 80070000h
0x14004c04b  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x14004c04f  mov     [rbp+57h+arg_18], ebx
0x14004c052  test    rcx, rcx
0x14004c055  jz      short loc_14004C077
0x14004c057  call    cs:__imp_LocalFree
0x14004c05e  nop     dword ptr [rax+rax+00h]
0x14004c063  jmp     short loc_14004C077
0x14004c065  mov     rax, qword ptr [rbp+57h+Buffer]
0x14004c069  mov     [rbx], rax
0x14004c06c  mov     ebx, [rbp+57h+arg_18]
0x14004c06f  mov     qword ptr [rbp+57h+Buffer], 0
0x14004c077  lea     rcx, [rbp+57h+var_48]; this
0x14004c07b  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004c080  mov     eax, ebx
0x14004c082  add     rsp, 88h
0x14004c089  pop     rdi
0x14004c08a  pop     rsi
0x14004c08b  pop     rbx
0x14004c08c  pop     rbp
0x14004c08d  retn
```
