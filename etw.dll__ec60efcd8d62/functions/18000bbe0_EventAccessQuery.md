# EventAccessQuery

- ea: `0x18000bbe0`
- end: `0x18000bf52`
- name: `EventAccessQuery`
- size: `882`
- prototype: `ULONG __stdcall(LPGUID Guid, PSECURITY_DESCRIPTOR Buffer, PULONG BufferSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013e28`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001ee2`
- `0x180002ec4`
- `0x1800086c0`
- `0x18000bbe0`
- `0x180013d90`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000bdb9`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000bdb9`
- `ntdll!RtlQueryRegistryValueWithFallback` at `0x18000be3b`
- `ntdll!RtlQueryRegistryValueWithFallback` at `0x18000be3b`
- `ntdll!RtlSetLastWin32Error` at `0x18000bef7`
- `ntdll!RtlSetLastWin32Error` at `0x18000bef7`
- `ntdll!RtlInitUnicodeString` at `0x18000be14`
- `ntdll!RtlInitUnicodeString` at `0x18000be14`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000beb0`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000beb0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bc71`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bc71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bedc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bedc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bd7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bd7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bddf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be8c`

## string_xrefs

- `0x18000bd6d`: `SYSTEM\CurrentControlSet\Control\WMI\Security`
- `0x18000bd9c`: `ETWSecurityPath`

## pseudocode

```c
ULONG __stdcall EventAccessQuery(LPGUID Guid, PSECURITY_DESCRIPTOR Buffer, PULONG BufferSize)
{
  GUID *v6; // rax
  ULONG v7; // ebx
  unsigned int v8; // edx
  LSTATUS v9; // eax
  ULONG v10; // ebx
  NTSTATUS v11; // eax
  unsigned int v12; // edx
  HKEY v13; // rcx
  ULONG Value; // eax
  LSTATUS v16; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+70h] [rbp-90h] BYREF
  char v22; // [rsp+74h] [rbp-8Ch]
  GUID ActivityId; // [rsp+78h] [rbp-88h] BYREF
  __int128 v24; // [rsp+98h] [rbp-68h] BYREF
  char v25; // [rsp+A8h] [rbp-58h]
  GUID v26; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[32]; // [rsp+C0h] [rbp-40h] BYREF
  GUID *v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  WCHAR SourceString[40]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[264]; // [rsp+140h] [rbp+40h] BYREF

  v19 = 0;
  phkResult = 0;
  v16 = 0;
  hKey = 0;
  v21 = 0;
  v22 = 0;
  DestinationString = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v21 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    if ( Guid )
    {
      v6 = &v26;
      v26 = *Guid;
    }
    else
    {
      v6 = (GUID *)&v24;
      v24 = 0;
    }
    v28 = v6;
    v29 = 16;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_18001D020,
      (unsigned int)byte_180018FEB,
      (unsigned int)&ActivityId,
      0,
      3,
      (__int64)v27);
  }
  v25 = 1;
  *(_QWORD *)&v24 = &v21;
  *((_QWORD *)&v24 + 1) = &v16;
  if ( Guid && BufferSize )
  {
    phkResult = 0;
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Security", 0, 1u, &hKey);
    v7 = v16;
    if ( !v16 )
    {
      if ( (unsigned int)RtlGetPersistedStateLocation(L"ETWSecurityPath", 0, 0, 0, SubKey, 520, &v19) )
      {
        v9 = v16;
      }
      else
      {
        v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, v7 + 1, &phkResult);
        v16 = v9;
      }
      if ( v9 )
      {
        v16 = 0;
        phkResult = 0;
      }
      v10 = *BufferSize;
      EtwpGuidToString(SourceString, v8, Guid);
      RtlInitUnicodeString(&DestinationString, SourceString);
      v11 = RtlQueryRegistryValueWithFallback(phkResult, hKey, &DestinationString, *BufferSize, 0, Buffer, BufferSize);
      if ( v11 != -1073741772
        || *(_QWORD *)&Guid->Data1 == *(_QWORD *)&DefaultTraceSecurityGuid.Data1
        && *(_QWORD *)Guid->Data4 == *(_QWORD *)DefaultTraceSecurityGuid.Data4 )
      {
        Value = RtlNtStatusToDosError_0(v11);
      }
      else
      {
        EtwpGuidToString(SourceString, v12, &DefaultTraceSecurityGuid);
        v13 = hKey;
        *BufferSize = v10;
        Value = RegQueryValueExW(v13, SourceString, 0, 0, (LPBYTE)Buffer, BufferSize);
      }
      v16 = Value;
      if ( !Value )
      {
        if ( Buffer )
        {
          if ( !RtlValidRelativeSecurityDescriptor(Buffer, *BufferSize, 0) )
            v16 = 1338;
        }
        else
        {
          v16 = 234;
        }
      }
      RegCloseKey(hKey);
      RegCloseKey(phkResult);
      v7 = v16;
    }
  }
  else
  {
    v7 = 87;
    v16 = 87;
  }
  if ( v7 )
  {
    RtlSetLastWin32Error(v7);
    v7 = v16;
  }
  lambda_07ba1716ab68ca04fe7cfd773dae453f_::operator()(&v24);
  if ( v21 == 1 )
  {
    v21 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return v7;
}

```

## disassembly

```asm
0x18000bbe0  mov     [rsp-8+arg_18], rbx
0x18000bbe5  push    rbp
0x18000bbe6  push    rsi
0x18000bbe7  push    rdi
0x18000bbe8  push    r14
0x18000bbea  push    r15
0x18000bbec  lea     rbp, [rsp-260h]
0x18000bbf4  sub     rsp, 360h
0x18000bbfb  mov     rax, cs:__security_cookie
0x18000bc02  xor     rax, rsp
0x18000bc05  mov     [rbp+280h+var_30], rax
0x18000bc0c  mov     eax, cs:dword_18001D020
0x18000bc12  xor     r15d, r15d
0x18000bc15  mov     [rsp+380h+var_328], r15d
0x18000bc1a  xorps   xmm0, xmm0
0x18000bc1d  mov     [rsp+380h+var_338], r15
0x18000bc22  mov     rsi, r8
0x18000bc25  mov     [rsp+380h+var_340], r15d
0x18000bc2a  mov     r14, rdx
0x18000bc2d  mov     [rsp+380h+hKey], r15
0x18000bc32  lea     ebx, [r15+3]
0x18000bc36  mov     [rsp+380h+var_310], r15d
0x18000bc3b  mov     rdi, rcx
0x18000bc3e  mov     [rsp+380h+var_30C], r15b
0x18000bc43  movups  xmmword ptr [rsp+380h+DestinationString.Length], xmm0
0x18000bc48  cmp     eax, 5
0x18000bc4b  jbe     short loc_18000BC79
0x18000bc4d  mov     rcx, cs:qword_18001D038
0x18000bc54  mov     rax, cs:qword_18001D030
0x18000bc5b  test    al, 10h
0x18000bc5d  jz      short loc_18000BC79
0x18000bc5f  mov     rax, rcx
0x18000bc62  and     eax, 10h
0x18000bc65  cmp     rax, rcx
0x18000bc68  jnz     short loc_18000BC79
0x18000bc6a  lea     rdx, [rsp+380h+ActivityId]; ActivityId
0x18000bc6f  mov     ecx, ebx; ControlCode
0x18000bc71  call    cs:__imp_EventActivityIdControl
0x18000bc77  jmp     short loc_18000BC7E
0x18000bc79  movups  xmmword ptr [rsp+380h+ActivityId.Data1], xmm0
0x18000bc7e  mov     eax, cs:dword_18001D020
0x18000bc84  mov     [rsp+380h+var_310], 1
0x18000bc8c  cmp     eax, 5
0x18000bc8f  jbe     loc_18000BD2D
0x18000bc95  mov     rcx, cs:qword_18001D038
0x18000bc9c  mov     rax, cs:qword_18001D030
0x18000bca3  test    al, 10h
0x18000bca5  jz      loc_18000BD2D
0x18000bcab  mov     rax, rcx
0x18000bcae  and     eax, 10h
0x18000bcb1  cmp     rax, rcx
0x18000bcb4  jnz     short loc_18000BD2D
0x18000bcb6  test    rdi, rdi
0x18000bcb9  jz      short loc_18000BCC9
0x18000bcbb  movups  xmm0, xmmword ptr [rdi]
0x18000bcbe  lea     rax, [rbp+280h+var_2D0]
0x18000bcc2  movdqu  [rbp+280h+var_2D0], xmm0
0x18000bcc7  jmp     short loc_18000BCD4
0x18000bcc9  xorps   xmm0, xmm0
0x18000bccc  lea     rax, [rbp+280h+var_2E8]
0x18000bcd0  movups  [rbp+280h+var_2E8], xmm0
0x18000bcd4  cmp     [rsp+380h+var_30C], r15b
0x18000bcd9  jz      short loc_18000BCF9
0x18000bcdb  cmp     [rbp+280h+var_2F8], r15d
0x18000bcdf  jnz     short loc_18000BCF3
0x18000bce1  cmp     [rbp+280h+var_2F4], r15d
0x18000bce5  jnz     short loc_18000BCF3
0x18000bce7  cmp     [rbp+280h+var_2F0], r15d
0x18000bceb  jnz     short loc_18000BCF3
0x18000bced  cmp     [rbp+280h+var_2EC], r15d
0x18000bcf1  jz      short loc_18000BCF9
0x18000bcf3  lea     r9, [rbp+280h+var_2F8]
0x18000bcf7  jmp     short loc_18000BCFC
0x18000bcf9  mov     r9, r15
0x18000bcfc  mov     [rbp+280h+var_2A0], rax
0x18000bd00  lea     r8, [rsp+380h+ActivityId]
0x18000bd05  lea     rax, [rbp+280h+var_2C0]
0x18000bd09  mov     [rbp+280h+var_298], 10h
0x18000bd11  mov     [rsp+380h+lpcbData], rax
0x18000bd16  lea     rdx, byte_180018FEB
0x18000bd1d  lea     rcx, dword_18001D020
0x18000bd24  mov     dword ptr [rsp+380h+phkResult], ebx
0x18000bd28  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000bd2d  mov     [rbp+280h+var_2D8], 1
0x18000bd31  lea     rax, [rsp+380h+var_310]
0x18000bd36  mov     qword ptr [rbp+280h+var_2E8], rax
0x18000bd3a  lea     rax, [rsp+380h+var_340]
0x18000bd3f  mov     qword ptr [rbp+280h+var_2E8+8], rax
0x18000bd43  test    rdi, rdi
0x18000bd46  jz      loc_18000BEE8
0x18000bd4c  test    rsi, rsi
0x18000bd4f  jz      loc_18000BEE8
0x18000bd55  lea     rax, [rsp+380h+hKey]
0x18000bd5a  mov     [rsp+380h+var_338], r15
0x18000bd5f  mov     r9d, 1; samDesired
0x18000bd65  mov     [rsp+380h+phkResult], rax; phkResult
0x18000bd6a  xor     r8d, r8d; ulOptions
0x18000bd6d  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x18000bd74  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bd7b  call    cs:__imp_RegOpenKeyExW
0x18000bd81  mov     [rsp+380h+var_340], eax
0x18000bd85  mov     ebx, eax
0x18000bd87  test    eax, eax
0x18000bd89  jnz     loc_18000BEF1
0x18000bd8f  lea     rax, [rsp+380h+var_328]
0x18000bd94  xor     r9d, r9d
0x18000bd97  mov     [rsp+380h+var_350], rax
0x18000bd9c  lea     rcx, aEtwsecuritypat; "ETWSecurityPath"
0x18000bda3  lea     rax, [rbp+280h+SubKey]
0x18000bda7  mov     dword ptr [rsp+380h+lpcbData], 208h
0x18000bdaf  xor     r8d, r8d
0x18000bdb2  mov     [rsp+380h+phkResult], rax
0x18000bdb7  xor     edx, edx
0x18000bdb9  call    cs:__imp_RtlGetPersistedStateLocation
0x18000bdbf  test    eax, eax
0x18000bdc1  jnz     short loc_18000BDEB
0x18000bdc3  lea     rax, [rsp+380h+var_338]
0x18000bdc8  xor     r8d, r8d; ulOptions
0x18000bdcb  lea     r9d, [rbx+1]; samDesired
0x18000bdcf  mov     [rsp+380h+phkResult], rax; phkResult
0x18000bdd4  lea     rdx, [rbp+280h+SubKey]; lpSubKey
0x18000bdd8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bddf  call    cs:__imp_RegOpenKeyExW
0x18000bde5  mov     [rsp+380h+var_340], eax
0x18000bde9  jmp     short loc_18000BDEF
0x18000bdeb  mov     eax, [rsp+380h+var_340]
0x18000bdef  test    eax, eax
0x18000bdf1  jz      short loc_18000BDFD
0x18000bdf3  mov     [rsp+380h+var_340], r15d
0x18000bdf8  mov     [rsp+380h+var_338], r15
0x18000bdfd  mov     ebx, [rsi]
0x18000bdff  lea     rcx, [rbp+280h+SourceString]; unsigned __int16 *
0x18000be03  mov     r8, rdi; struct _GUID *
0x18000be06  call    ?EtwpGuidToString@@YAPEAGPEAGKPEBU_GUID@@@Z; EtwpGuidToString(ushort *,ulong,_GUID const *)
0x18000be0b  lea     rdx, [rbp+280h+SourceString]; SourceString
0x18000be0f  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x18000be14  call    cs:__imp_RtlInitUnicodeString
0x18000be1a  mov     r9d, [rsi]
0x18000be1d  lea     r8, [rsp+380h+DestinationString]
0x18000be22  mov     rdx, [rsp+380h+hKey]
0x18000be27  mov     rcx, [rsp+380h+var_338]
0x18000be2c  mov     [rsp+380h+var_350], rsi
0x18000be31  mov     [rsp+380h+lpcbData], r14
0x18000be36  mov     [rsp+380h+phkResult], r15
0x18000be3b  call    cs:__imp_RtlQueryRegistryValueWithFallback
0x18000be41  cmp     eax, 0C0000034h
0x18000be46  jnz     short loc_18000BE94
0x18000be48  mov     rcx, [rdi]
0x18000be4b  cmp     rcx, qword ptr cs:DefaultTraceSecurityGuid.Data1
0x18000be52  jnz     short loc_18000BE61
0x18000be54  mov     rcx, [rdi+8]
0x18000be58  cmp     rcx, qword ptr cs:DefaultTraceSecurityGuid.Data4
0x18000be5f  jz      short loc_18000BE94
0x18000be61  lea     r8, DefaultTraceSecurityGuid; struct _GUID *
0x18000be68  lea     rcx, [rbp+280h+SourceString]; unsigned __int16 *
0x18000be6c  call    ?EtwpGuidToString@@YAPEAGPEAGKPEBU_GUID@@@Z; EtwpGuidToString(ushort *,ulong,_GUID const *)
0x18000be71  mov     rcx, [rsp+380h+hKey]; hKey
0x18000be76  lea     rdx, [rbp+280h+SourceString]; lpValueName
0x18000be7a  xor     r9d, r9d; lpType
0x18000be7d  mov     [rsp+380h+lpcbData], rsi; lpcbData
0x18000be82  xor     r8d, r8d; lpReserved
0x18000be85  mov     [rsi], ebx
0x18000be87  mov     [rsp+380h+phkResult], r14; lpData
0x18000be8c  call    cs:__imp_RegQueryValueExW
0x18000be92  jmp     short loc_18000BE9B
0x18000be94  mov     ecx, eax; Status
0x18000be96  call    RtlNtStatusToDosError_0
0x18000be9b  mov     [rsp+380h+var_340], eax
0x18000be9f  test    eax, eax
0x18000bea1  jnz     short loc_18000BECC
0x18000bea3  test    r14, r14
0x18000bea6  jz      short loc_18000BEC4
0x18000bea8  mov     edx, [rsi]; SecurityDescriptorLength
0x18000beaa  xor     r8d, r8d; RequiredInformation
0x18000bead  mov     rcx, r14; SecurityDescriptorInput
0x18000beb0  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18000beb6  test    al, al
0x18000beb8  jnz     short loc_18000BECC
0x18000beba  mov     [rsp+380h+var_340], 53Ah
0x18000bec2  jmp     short loc_18000BECC
0x18000bec4  mov     [rsp+380h+var_340], 0EAh
0x18000becc  mov     rcx, [rsp+380h+hKey]; hKey
0x18000bed1  call    cs:__imp_RegCloseKey
0x18000bed7  mov     rcx, [rsp+380h+var_338]; hKey
0x18000bedc  call    cs:__imp_RegCloseKey
0x18000bee2  mov     ebx, [rsp+380h+var_340]
0x18000bee6  jmp     short loc_18000BEF1
0x18000bee8  mov     ebx, 57h ; 'W'
0x18000beed  mov     [rsp+380h+var_340], ebx
0x18000bef1  test    ebx, ebx
0x18000bef3  jz      short loc_18000BF01
0x18000bef5  mov     ecx, ebx; LastError
0x18000bef7  call    cs:__imp_RtlSetLastWin32Error
0x18000befd  mov     ebx, [rsp+380h+var_340]
0x18000bf01  lea     rcx, [rbp+280h+var_2E8]
0x18000bf05  call    _lambda_07ba1716ab68ca04fe7cfd773dae453f___operator__
0x18000bf0a  cmp     [rsp+380h+var_310], 1
0x18000bf0f  jnz     short loc_18000BF2A
0x18000bf11  lea     rdx, [rsp+380h+ActivityId]
0x18000bf16  mov     [rsp+380h+var_310], 2
0x18000bf1e  lea     rcx, dword_18001D020
0x18000bf25  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000bf2a  mov     eax, ebx
0x18000bf2c  mov     rcx, [rbp+280h+var_30]
0x18000bf33  xor     rcx, rsp; StackCookie
0x18000bf36  call    __security_check_cookie
0x18000bf3b  mov     rbx, [rsp+380h+arg_18]
0x18000bf43  add     rsp, 360h
0x18000bf4a  pop     r15
0x18000bf4c  pop     r14
0x18000bf4e  pop     rdi
0x18000bf4f  pop     rsi
0x18000bf50  pop     rbp
0x18000bf51  retn
```
