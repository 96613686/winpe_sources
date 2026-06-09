# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateAadClientAlertXml(ulong,ushort const *,ushort const *,ushort * *)

- ea: `0x14004a730`
- end: `0x14004a87d`
- name: `?GenerateAadClientAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJKPEBG0PEAPEAG@Z`
- size: `333`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004a730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a812`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004a802`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14004a802`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a839`

## string_xrefs

- `0x14004a7d2`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft/MDM/AADDeviceToken</Type></Meta><Data>%2</Data></Item></Alert>`
- `0x14004a7cb`: `<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns="syncml:metinf">com.microsoft/MDM/AADUserToken</Type></Meta><Data>%2</Data></Item></Alert>`
- `0x14004a748`: `GenerateAadClientAlertXml`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateAadClientAlertXml(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  unsigned __int64 v5; // r14
  __int128 v6; // rdi
  unsigned int v7; // ebx
  unsigned __int16 **v8; // rbx
  va_list v9; // rax
  const unsigned __int16 *v10; // rdx
  signed int LastError; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-40h] BYREF
  va_list Arguments[2]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-28h] BYREF
  int v16; // [rsp+70h] [rbp-10h]
  unsigned int *v17; // [rsp+78h] [rbp-8h]
  unsigned int v18; // [rsp+B0h] [rbp+30h] BYREF

  v5 = a2;
  v15[1] = "GenerateAadClientAlertXml";
  *((_QWORD *)&v6 + 1) = a4;
  *(_QWORD *)&v6 = a3;
  v18 = 0;
  v15[0] = 0;
  v15[2] = COmaDmLogger::GetLogger();
  v17 = &v18;
  v16 = 2;
  if ( v6 == 0 )
  {
    v7 = -805306128;
LABEL_5:
    v18 = v7;
    goto LABEL_16;
  }
  v8 = a5;
  if ( !a5 )
  {
    v7 = -805306126;
    goto LABEL_5;
  }
  *a5 = 0;
  v9 = (va_list)v6;
  Arguments[0] = (va_list)v5;
  if ( !(_QWORD)v6 )
    v9 = (va_list)*((_QWORD *)&v6 + 1);
  *(_QWORD *)Buffer = 0;
  Arguments[1] = v9;
  v10 = L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft/MDM/AADUserT"
         "oken</Type></Meta><Data>%2</Data></Item></Alert>";
  if ( !(_QWORD)v6 )
    v10 = L"<Alert><CmdID>%1!d!</CmdID><Data>1224</Data><Item><Meta><Type xmlns=\"syncml:metinf\">com.microsoft/MDM/AADDev"
           "iceToken</Type></Meta><Data>%2</Data></Item></Alert>";
  if ( FormatMessageW(0x2500u, v10, 0, 0, Buffer, 0x100u, Arguments) )
  {
    *v8 = *(unsigned __int16 **)Buffer;
    v7 = v18;
    *(_QWORD *)Buffer = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v18 = v7;
    if ( *(_QWORD *)Buffer )
      LocalFree(*(HLOCAL *)Buffer);
  }
LABEL_16:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v15);
  return v7;
}

```

## disassembly

```asm
0x14004a730  mov     [rsp-18h+arg_0], rbx
0x14004a735  mov     [rsp-18h+arg_8], rsi
0x14004a73a  push    rbp
0x14004a73b  push    rdi
0x14004a73c  push    r14
0x14004a73e  mov     rbp, rsp
0x14004a741  sub     rsp, 80h
0x14004a748  lea     rax, aGenerateaadcli; "GenerateAadClientAlertXml"
0x14004a74f  mov     r14d, edx
0x14004a752  mov     [rbp+var_20], rax
0x14004a756  mov     rsi, r9
0x14004a759  mov     rdi, r8
0x14004a75c  mov     [rbp+arg_10], 0
0x14004a763  mov     [rbp+var_28], 0
0x14004a76b  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004a770  mov     [rbp+var_18], rax
0x14004a774  lea     rax, [rbp+arg_10]
0x14004a778  mov     [rbp+var_8], rax
0x14004a77c  mov     [rbp+var_10], 2
0x14004a783  test    rdi, rdi
0x14004a786  jnz     short loc_14004A794
0x14004a788  test    rsi, rsi
0x14004a78b  jnz     short loc_14004A794
0x14004a78d  mov     ebx, 0D00000F0h
0x14004a792  jmp     short loc_14004A7A2
0x14004a794  mov     rbx, [rbp+arg_20]
0x14004a798  test    rbx, rbx
0x14004a79b  jnz     short loc_14004A7AA
0x14004a79d  mov     ebx, 0D00000F2h
0x14004a7a2  mov     [rbp+arg_10], ebx
0x14004a7a5  jmp     loc_14004A859
0x14004a7aa  test    rdi, rdi
0x14004a7ad  mov     qword ptr [rbx], 0
0x14004a7b4  mov     rax, rdi
0x14004a7b7  mov     [rbp+var_38], r14
0x14004a7bb  cmovz   rax, rsi
0x14004a7bf  mov     qword ptr [rbp+Buffer], 0
0x14004a7c7  mov     [rbp+var_30], rax
0x14004a7cb  lea     rdx, ?gc_szAadAlertUserTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004a7d2  lea     rax, ?gc_szAadAlertDeviceTemplate@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "<Alert><CmdID>%1!d!</CmdID><Data>1224</"...
0x14004a7d9  mov     ecx, 2500h; dwFlags
0x14004a7de  cmovz   rdx, rax; lpSource
0x14004a7e2  lea     rax, [rbp+var_38]
0x14004a7e6  mov     [rsp+80h+Arguments], rax; Arguments
0x14004a7eb  xor     r9d, r9d; dwLanguageId
0x14004a7ee  lea     rax, [rbp+Buffer]
0x14004a7f2  mov     [rsp+80h+nSize], 100h; nSize
0x14004a7fa  xor     r8d, r8d; dwMessageId
0x14004a7fd  mov     [rsp+80h+lpBuffer], rax; lpBuffer
0x14004a802  call    cs:__imp_FormatMessageW
0x14004a809  nop     dword ptr [rax+rax+00h]
0x14004a80e  test    eax, eax
0x14004a810  jnz     short loc_14004A847
0x14004a812  call    cs:__imp_GetLastError
0x14004a819  nop     dword ptr [rax+rax+00h]
0x14004a81e  mov     ebx, eax
0x14004a820  test    eax, eax
0x14004a822  jle     short loc_14004A82D
0x14004a824  movzx   ebx, ax
0x14004a827  or      ebx, 80070000h
0x14004a82d  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x14004a831  mov     [rbp+arg_10], ebx
0x14004a834  test    rcx, rcx
0x14004a837  jz      short loc_14004A859
0x14004a839  call    cs:__imp_LocalFree
0x14004a840  nop     dword ptr [rax+rax+00h]
0x14004a845  jmp     short loc_14004A859
0x14004a847  mov     rax, qword ptr [rbp+Buffer]
0x14004a84b  mov     [rbx], rax
0x14004a84e  mov     ebx, [rbp+arg_10]
0x14004a851  mov     qword ptr [rbp+Buffer], 0
0x14004a859  lea     rcx, [rbp+var_28]; this
0x14004a85d  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004a862  lea     r11, [rsp+80h+var_s0]
0x14004a86a  mov     eax, ebx
0x14004a86c  mov     rbx, [r11+20h]
0x14004a870  mov     rsi, [r11+28h]
0x14004a874  mov     rsp, r11
0x14004a877  pop     r14
0x14004a879  pop     rdi
0x14004a87a  pop     rbp
0x14004a87b  retn
```
