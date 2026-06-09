# I_CertGetAutoUpdateLastSyncTime

- ea: `0x180009428`
- end: `0x180009529`
- name: `I_CertGetAutoUpdateLastSyncTime`
- size: `257`
- prototype: `__int64 __fastcall(int, BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008df0`

## callees

- `0x180009428`
- `0x180009530`
- `0x1800095e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800094b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800094b9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800094c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800094c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000949c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000949c`

## pseudocode

```c
__int64 __fastcall I_CertGetAutoUpdateLastSyncTime(int a1, BYTE *a2)
{
  int v3; // ecx
  const WCHAR *v4; // rdi
  HKEY updated; // rbx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  int v9; // ecx
  DWORD v10; // ecx
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  Type = 0;
  cbData = 0;
  v3 = a1 - 5;
  if ( v3 )
  {
    v9 = v3 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
      {
        updated = 0;
        v10 = -2147024809;
        goto LABEL_13;
      }
      v4 = L"PinRulesLastSyncTime";
    }
    else
    {
      v4 = L"DisallowedCertLastSyncTime";
    }
  }
  else
  {
    v4 = L"LastSyncTime";
  }
  updated = OpenAutoUpdateKey(HKEY_LOCAL_MACHINE);
  if ( !updated )
  {
LABEL_14:
    v7 = 0;
    *(_QWORD *)a2 = 0;
    goto LABEL_9;
  }
  cbData = 8;
  v6 = RegQueryValueExW(updated, v4, 0, &Type, a2, &cbData);
  if ( v6 )
  {
    v10 = v6;
    goto LABEL_13;
  }
  if ( Type != 3
    || cbData != 8
    || (GetSystemTimeAsFileTime(&SystemTimeAsFileTime), CompareFileTime((const FILETIME *)a2, &SystemTimeAsFileTime) > 0) )
  {
    v10 = 13;
LABEL_13:
    SetLastError(v10);
    goto LABEL_14;
  }
  v7 = 1;
LABEL_9:
  CloseRegistryKey(updated);
  return v7;
}

```

## disassembly

```asm
0x180009428  mov     rax, rsp
0x18000942b  mov     [rax+18h], r8d
0x18000942f  push    rbx
0x180009430  push    rsi
0x180009431  push    rdi
0x180009432  sub     rsp, 30h
0x180009436  mov     qword ptr [rax+20h], 0
0x18000943e  mov     rsi, rdx
0x180009441  mov     dword ptr [rax+8], 0
0x180009448  mov     dword ptr [rax+18h], 0
0x18000944f  sub     ecx, 5
0x180009452  jnz     loc_1800094E8
0x180009458  lea     rdi, aLastsynctime; "LastSyncTime"
0x18000945f  mov     rcx, 0FFFFFFFF80000002h
0x180009466  call    _OpenAutoUpdateKey
0x18000946b  mov     rbx, rax
0x18000946e  test    rax, rax
0x180009471  jz      loc_180009504
0x180009477  lea     rax, [rsp+48h+cbData]
0x18000947c  mov     [rsp+48h+cbData], 8
0x180009484  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180009489  lea     r9, [rsp+48h+Type]; lpType
0x18000948e  xor     r8d, r8d; lpReserved
0x180009491  mov     [rsp+48h+lpData], rsi; lpData
0x180009496  mov     rdx, rdi; lpValueName
0x180009499  mov     rcx, rbx; hKey
0x18000949c  call    cs:__imp_RegQueryValueExW
0x1800094a2  test    eax, eax
0x1800094a4  jnz     short loc_180009525
0x1800094a6  cmp     [rsp+48h+Type], 3
0x1800094ab  jnz     short loc_1800094F9
0x1800094ad  cmp     [rsp+48h+cbData], 8
0x1800094b2  jnz     short loc_1800094F9
0x1800094b4  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800094b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800094bf  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x1800094c4  mov     rcx, rsi; lpFileTime1
0x1800094c7  call    cs:__imp_CompareFileTime
0x1800094cd  test    eax, eax
0x1800094cf  jg      short loc_1800094F9
0x1800094d1  mov     edi, 1
0x1800094d6  mov     rcx, rbx; hKey
0x1800094d9  call    _CloseRegistryKey
0x1800094de  mov     eax, edi
0x1800094e0  add     rsp, 30h
0x1800094e4  pop     rdi
0x1800094e5  pop     rsi
0x1800094e6  pop     rbx
0x1800094e7  retn
0x1800094e8  sub     ecx, 1
0x1800094eb  jnz     short loc_18000950B
0x1800094ed  lea     rdi, aDisallowedcert_1; "DisallowedCertLastSyncTime"
0x1800094f4  jmp     loc_18000945F
0x1800094f9  mov     ecx, 0Dh; dwErrCode
0x1800094fe  call    cs:__imp_SetLastError
0x180009504  xor     edi, edi
0x180009506  mov     [rsi], rdi
0x180009509  jmp     short loc_1800094D6
0x18000950b  cmp     ecx, 1
0x18000950e  jnz     short loc_18000951C
0x180009510  lea     rdi, aPinruleslastsy; "PinRulesLastSyncTime"
0x180009517  jmp     loc_18000945F
0x18000951c  xor     ebx, ebx
0x18000951e  mov     ecx, 80070057h
0x180009523  jmp     short loc_1800094FE
0x180009525  mov     ecx, eax
0x180009527  jmp     short loc_1800094FE
```
