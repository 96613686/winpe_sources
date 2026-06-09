# SetLocalMachineAccount

- ea: `0x180013a0c`
- end: `0x180013b13`
- name: `SetLocalMachineAccount`
- size: `263`
- prototype: `__int64 __fastcall(LPCWSTR lpBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006b70`
- `0x180012460`

## callees

- `0x1800138b0`
- `0x180013a0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a32`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180013a28`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x180013a28`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180013a91`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180013aef`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180013a91`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180013aef`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180013aff`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180013aff`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180013a89`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180013a89`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180013ae7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180013ae7`

## pseudocode

```c
__int64 __fastcall SetLocalMachineAccount(LPCWSTR lpBuffer, __int64 a2)
{
  ULONG v3; // ebx
  PVOID v4; // rdi
  NTSTATUS v5; // eax
  ULONG v6; // eax
  NTSTATUS v7; // eax
  struct _LSA_UNICODE_STRING SystemName; // [rsp+20h] [rbp-29h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+30h] [rbp-19h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+40h] [rbp-9h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  PVOID PolicyHandle; // [rsp+C0h] [rbp+77h] BYREF

  if ( SetComputerNameExW(ComputerNamePhysicalDnsHostname, lpBuffer) )
  {
    v3 = 0;
    if ( a2 )
    {
      PolicyHandle = 0;
      SystemName = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      if ( (unsigned int)InitUnicodeString(&SystemName, 0) )
      {
        v5 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0xF0FFFu, &PolicyHandle);
        v6 = LsaNtStatusToWinError(v5);
        v4 = PolicyHandle;
        if ( v6 )
          v4 = 0;
      }
      else
      {
        v4 = 0;
      }
      KeyName = 0;
      PrivateData = 0;
      if ( (unsigned int)InitUnicodeString(&KeyName, L"$MACHINE.ACC")
        && (unsigned int)InitUnicodeString(&PrivateData, a2) )
      {
        v7 = LsaStorePrivateData(v4, &KeyName, &PrivateData);
        v3 = LsaNtStatusToWinError(v7);
      }
      else
      {
        v3 = 87;
      }
      if ( v4 )
        LsaClose(v4);
    }
  }
  else
  {
    return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x180013a0c  push    rbp
0x180013a0e  push    rbx
0x180013a0f  push    rsi
0x180013a10  push    rdi
0x180013a11  lea     rbp, [rsp-3Fh]
0x180013a16  sub     rsp, 88h
0x180013a1d  mov     rsi, rdx
0x180013a20  mov     rdx, rcx; lpBuffer
0x180013a23  mov     ecx, 5; NameType
0x180013a28  call    cs:__imp_SetComputerNameExW
0x180013a2e  test    eax, eax
0x180013a30  jnz     short loc_180013A3F
0x180013a32  call    cs:__imp_GetLastError
0x180013a38  mov     ebx, eax
0x180013a3a  jmp     loc_180013B05
0x180013a3f  xor     ebx, ebx
0x180013a41  test    rsi, rsi
0x180013a44  jz      loc_180013B05
0x180013a4a  xorps   xmm1, xmm1
0x180013a4d  mov     [rbp+57h+PolicyHandle], rbx
0x180013a51  xorps   xmm0, xmm0
0x180013a54  lea     rcx, [rbp+57h+SystemName]
0x180013a58  xor     edx, edx
0x180013a5a  movups  xmmword ptr [rbp+57h+SystemName.Length], xmm0
0x180013a5e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180013a62  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180013a66  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180013a6a  call    InitUnicodeString
0x180013a6f  test    eax, eax
0x180013a71  jnz     short loc_180013A77
0x180013a73  xor     edi, edi
0x180013a75  jmp     short loc_180013AA3
0x180013a77  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180013a7b  mov     r8d, 0F0FFFh; DesiredAccess
0x180013a81  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180013a85  lea     rcx, [rbp+57h+SystemName]; SystemName
0x180013a89  call    cs:__imp_LsaOpenPolicy
0x180013a8f  mov     ecx, eax; Status
0x180013a91  call    cs:__imp_LsaNtStatusToWinError
0x180013a97  mov     rdi, [rbp+57h+PolicyHandle]
0x180013a9b  xor     ecx, ecx
0x180013a9d  test    eax, eax
0x180013a9f  cmovnz  rdi, rcx
0x180013aa3  xorps   xmm0, xmm0
0x180013aa6  lea     rdx, aMachineAcc; "$MACHINE.ACC"
0x180013aad  xorps   xmm1, xmm1
0x180013ab0  lea     rcx, [rbp+57h+KeyName]
0x180013ab4  movups  xmmword ptr [rbp+57h+KeyName.Length], xmm0
0x180013ab8  movups  xmmword ptr [rbp+57h+PrivateData.Length], xmm1
0x180013abc  call    InitUnicodeString
0x180013ac1  test    eax, eax
0x180013ac3  jnz     short loc_180013ACC
0x180013ac5  mov     ebx, 57h ; 'W'
0x180013aca  jmp     short loc_180013AF7
0x180013acc  mov     rdx, rsi
0x180013acf  lea     rcx, [rbp+57h+PrivateData]
0x180013ad3  call    InitUnicodeString
0x180013ad8  test    eax, eax
0x180013ada  jz      short loc_180013AC5
0x180013adc  lea     r8, [rbp+57h+PrivateData]; PrivateData
0x180013ae0  mov     rcx, rdi; PolicyHandle
0x180013ae3  lea     rdx, [rbp+57h+KeyName]; KeyName
0x180013ae7  call    cs:__imp_LsaStorePrivateData
0x180013aed  mov     ecx, eax; Status
0x180013aef  call    cs:__imp_LsaNtStatusToWinError
0x180013af5  mov     ebx, eax
0x180013af7  test    rdi, rdi
0x180013afa  jz      short loc_180013B05
0x180013afc  mov     rcx, rdi; ObjectHandle
0x180013aff  call    cs:__imp_LsaClose
0x180013b05  mov     eax, ebx
0x180013b07  add     rsp, 88h
0x180013b0e  pop     rdi
0x180013b0f  pop     rsi
0x180013b10  pop     rbx
0x180013b11  pop     rbp
0x180013b12  retn
```
