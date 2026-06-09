# GetSQMHash(wchar_t *,ulong *)

- ea: `0x18003bb68`
- end: `0x18003bd28`
- name: `?GetSQMHash@@YAXPEA_WPEAK@Z`
- size: `448`
- prototype: `void(wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180040790`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18003180c`
- `0x18003bb68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bc10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bc10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003bc77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003bc77`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18003bbc0`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18003bbc0`

## string_xrefs

- `0x18003bc04`: `SYSTEM\CurrentControlSet\Services\ClusSvc\Parameters`
- `0x18003bbcd`: `Failed to connect to registry on node %ws`
- `0x18003bc2a`: `Failed to get handle to SYSTEM\CurrentControlSet\Services\ClusSvc\Parameters on node %ws`
- `0x18003bc91`: `Failed to get InstanceHash value in registry on node %ws`

## pseudocode

```c
void __fastcall GetSQMHash(wchar_t *a1, BYTE *a2)
{
  LSTATUS v4; // eax
  LSTATUS v5; // edi
  LSTATUS v6; // edi
  DWORD cbData; // [rsp+40h] [rbp-478h] BYREF
  DWORD Type; // [rsp+44h] [rbp-474h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-470h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-468h] BYREF
  ClusRtl::ExceptionMsg *v11; // [rsp+58h] [rbp-460h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+60h] [rbp-458h] BYREF
  _BYTE v13[272]; // [rsp+170h] [rbp-348h] BYREF
  _BYTE v14[272]; // [rsp+280h] [rbp-238h] BYREF
  _BYTE v15[272]; // [rsp+390h] [rbp-128h] BYREF

  phkResult = 0;
  hKey = 0;
  Type = 0;
  cbData = 4;
  v4 = RegConnectRegistryW(a1, HKEY_LOCAL_MACHINE, &phkResult);
  try
  {
    if ( v4 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        v4,
        L"Failed to connect to registry on node %ws",
        a1);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    v5 = RegOpenKeyExW(phkResult, L"SYSTEM\\CurrentControlSet\\Services\\ClusSvc\\Parameters", 0, 1u, &hKey);
    RegCloseKey(phkResult);
    if ( v5 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v13,
        v5,
        L"Failed to get handle to SYSTEM\\CurrentControlSet\\Services\\ClusSvc\\Parameters on node %ws",
        a1);
      throw (ClusRtl::ExceptionMsg *)v13;
    }
    v6 = RegQueryValueExW(hKey, L"InstanceHash", 0, &Type, a2, &cbData);
    RegCloseKey(hKey);
    if ( v6 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v14,
        v6,
        L"Failed to get InstanceHash value in registry on node %ws",
        a1);
      throw (ClusRtl::ExceptionMsg *)v14;
    }
    if ( Type != 4 || cbData != 4 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v15,
        13,
        L"Unexpected reg type (%d) or size of data (%d)");
      throw (ClusRtl::ExceptionMsg *)v15;
    }
  }
  catch ( ClusRtl::ExceptionMsg *v11 )
  {
    TraceMsg(3, 0, L"GetSQMHash", 1101, L"Exception - error %d: %ws", *((_DWORD *)v11 + 64), v11);
  }
}

```

## disassembly

```asm
0x18003bb68  mov     [rsp+arg_10], rbx
0x18003bb6d  mov     [rsp+arg_18], rsi
0x18003bb72  push    rdi
0x18003bb73  sub     rsp, 4B0h
0x18003bb7a  mov     rax, cs:__security_cookie
0x18003bb81  xor     rax, rsp
0x18003bb84  mov     [rsp+4B8h+var_18], rax
0x18003bb8c  mov     rsi, rdx
0x18003bb8f  mov     rbx, rcx
0x18003bb92  mov     [rsp+4B8h+phkResult], 0
0x18003bb9b  mov     [rsp+4B8h+hKey], 0
0x18003bba4  mov     [rsp+4B8h+Type], 0
0x18003bbac  mov     [rsp+4B8h+cbData], 4
0x18003bbb4  lea     r8, [rsp+4B8h+phkResult]; phkResult
0x18003bbb9  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18003bbc0  call    cs:__imp_RegConnectRegistryW
0x18003bbc6  test    eax, eax
0x18003bbc8  jz      short loc_18003BBF1
0x18003bbca  mov     r9, rbx
0x18003bbcd  lea     r8, aFailedToConnec_1; "Failed to connect to registry on node %"...
0x18003bbd4  mov     edx, eax; int
0x18003bbd6  lea     rcx, [rsp+4B8h+pExceptionObject]; this
0x18003bbdb  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18003bbe0  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18003bbe7  lea     rcx, [rsp+4B8h+pExceptionObject]; pExceptionObject
0x18003bbec  call    _CxxThrowException_0
0x18003bbf1  lea     rax, [rsp+4B8h+hKey]
0x18003bbf6  mov     [rsp+4B8h+var_498], rax; phkResult
0x18003bbfb  mov     r9d, 1; samDesired
0x18003bc01  xor     r8d, r8d; ulOptions
0x18003bc04  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Cl"...
0x18003bc0b  mov     rcx, [rsp+4B8h+phkResult]; hKey
0x18003bc10  call    cs:__imp_RegOpenKeyExW
0x18003bc16  mov     edi, eax
0x18003bc18  mov     rcx, [rsp+4B8h+phkResult]; hKey
0x18003bc1d  call    cs:__imp_RegCloseKey
0x18003bc23  test    edi, edi
0x18003bc25  jz      short loc_18003BC54
0x18003bc27  mov     r9, rbx
0x18003bc2a  lea     r8, aFailedToGetHan_3; "Failed to get handle to SYSTEM\\Current"...
0x18003bc31  mov     edx, edi; int
0x18003bc33  lea     rcx, [rsp+4B8h+var_348]; this
0x18003bc3b  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18003bc40  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18003bc47  lea     rcx, [rsp+4B8h+var_348]; pExceptionObject
0x18003bc4f  call    _CxxThrowException_0
0x18003bc54  lea     rax, [rsp+4B8h+cbData]
0x18003bc59  mov     [rsp+4B8h+lpcbData], rax; lpcbData
0x18003bc5e  mov     [rsp+4B8h+var_498], rsi; lpData
0x18003bc63  lea     r9, [rsp+4B8h+Type]; lpType
0x18003bc68  xor     r8d, r8d; lpReserved
0x18003bc6b  lea     rdx, ValueName; "InstanceHash"
0x18003bc72  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18003bc77  call    cs:__imp_RegQueryValueExW
0x18003bc7d  mov     edi, eax
0x18003bc7f  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18003bc84  call    cs:__imp_RegCloseKey
0x18003bc8a  test    edi, edi
0x18003bc8c  jz      short loc_18003BCBB
0x18003bc8e  mov     r9, rbx
0x18003bc91  lea     r8, aFailedToGetIns; "Failed to get InstanceHash value in reg"...
0x18003bc98  mov     edx, edi; int
0x18003bc9a  lea     rcx, [rsp+4B8h+var_238]; this
0x18003bca2  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18003bca7  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18003bcae  lea     rcx, [rsp+4B8h+var_238]; pExceptionObject
0x18003bcb6  call    _CxxThrowException_0
0x18003bcbb  mov     r9d, [rsp+4B8h+Type]
0x18003bcc0  mov     eax, [rsp+4B8h+cbData]
0x18003bcc4  cmp     r9d, 4
0x18003bcc8  jnz     short loc_18003BCD1
0x18003bcca  cmp     eax, r9d
0x18003bccd  jnz     short loc_18003BCD1
0x18003bccf  jmp     short loc_18003BD03
0x18003bcd1  mov     dword ptr [rsp+4B8h+var_498], eax
0x18003bcd5  lea     r8, aUnexpectedRegT; "Unexpected reg type (%d) or size of dat"...
0x18003bcdc  mov     edx, 0Dh; int
0x18003bce1  lea     rcx, [rsp+4B8h+var_128]; this
0x18003bce9  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x18003bcee  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18003bcf5  lea     rcx, [rsp+4B8h+var_128]; pExceptionObject
0x18003bcfd  call    _CxxThrowException_0
0x18003bd03  mov     rcx, [rsp+4B8h+var_18]
0x18003bd0b  xor     rcx, rsp; StackCookie
0x18003bd0e  call    __security_check_cookie
0x18003bd13  lea     r11, [rsp+4B8h+var_8]
0x18003bd1b  mov     rbx, [r11+20h]
0x18003bd1f  mov     rsi, [r11+28h]
0x18003bd23  mov     rsp, r11
0x18003bd26  pop     rdi
0x18003bd27  retn
```
