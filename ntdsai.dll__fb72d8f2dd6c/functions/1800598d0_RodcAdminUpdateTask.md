# RodcAdminUpdateTask

- ea: `0x1800598d0`
- end: `0x180059b33`
- name: `RodcAdminUpdateTask`
- size: `611`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006330`
- `0x180037638`
- `0x1800598d0`
- `0x180173e2c`
- `0x1801c4a34`
- `0x1801d0ea0`
- `0x1801d2a7c`
- `0x1801d614c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800598f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800598f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800599de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800599de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059af4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059af4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059ae4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059ae4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059aa3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180059aa3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180059a50`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180059a50`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180059a32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180059a32`
- `ntdll!RtlValidSid` at `0x1800599c6`
- `ntdll!RtlValidSid` at `0x1800599c6`

## string_xrefs

- `0x180059a44`: `RepairAdmin`
- `0x180059a97`: `RepairAdmin`

## pseudocode

```c
int __fastcall RodcAdminUpdateTask(__int64 a1, __int64 a2, _DWORD *a3)
{
  char *Value; // rax
  int v5; // esi
  _QWORD *v6; // rdi
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rax
  LSTATUS v11; // [rsp+50h] [rbp-58h]
  HKEY hKey; // [rsp+60h] [rbp-48h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-40h] BYREF
  _QWORD v14[7]; // [rsp+70h] [rbp-38h] BYREF
  int v15; // [rsp+C8h] [rbp+20h] BYREF

  v14[0] = 0;
  Value = (char *)TlsGetValue(dwTSindex);
  v5 = (int)Value;
  v14[2] = Value;
  StringSid = 0;
  v15 = 0;
  hKey = 0;
  if ( dword_18052B32C )
  {
    v14[1] = Value;
    if ( !qword_18052B430 )
      goto LABEL_24;
    v6 = Value + 5576;
    DBOpen2(1, Value + 5576);
    v11 = DBFindDSName(*v6, qword_18052B430);
    if ( !v11 )
    {
      v15 = 0;
      v11 = DBGetAttVal(*v6, 1, 590477, 0, (__int64)&v15, (__int64)v14);
      if ( v11 == 8995 )
      {
        v11 = 0;
      }
      else if ( !v11 && RtlValidSid((PSID)(v14[0] + 24LL)) )
      {
        ConvertSidToStringSidW((PSID)(v14[0] + 24LL), &StringSid);
      }
    }
    DBClose(*v6, 1);
    LODWORD(Value) = v11;
    if ( !v11 )
    {
      v11 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Lsa\\RODCROLES",
              0,
              0,
              0,
              0x2001Bu,
              0,
              &hKey,
              0);
      LODWORD(Value) = v11;
      if ( !v11 )
      {
        v11 = RegDeleteValueW(hKey, L"RepairAdmin");
        LODWORD(Value) = v11;
        if ( v11 == 2 )
          v11 = 0;
        if ( StringSid )
        {
          v9 = -1;
          do
            ++v9;
          while ( StringSid[v9] );
          LODWORD(Value) = RegSetValueExW(hKey, L"RepairAdmin", 0, 1u, (const BYTE *)StringSid, 2 * v9);
          v11 = (int)Value;
        }
      }
    }
    if ( hKey )
      LODWORD(Value) = RegCloseKey(hKey);
    if ( StringSid )
      LODWORD(Value) = (unsigned int)LocalFree(StringSid);
    if ( v14[0] )
      LODWORD(Value) = THFreeAux(v5, v14[0], v7, v8, 51323860);
    if ( v11 )
LABEL_24:
      *a3 = 180;
  }
  return (int)Value;
}

```

## disassembly

```asm
0x1800598d0  mov     rax, rsp
0x1800598d3  mov     [rax+8], rbx
0x1800598d7  mov     [rax+18h], r8
0x1800598db  push    rsi
0x1800598dc  push    rdi
0x1800598dd  push    r14
0x1800598df  sub     rsp, 90h
0x1800598e6  mov     r14, r8
0x1800598e9  xor     ebx, ebx
0x1800598eb  mov     [rax-38h], rbx
0x1800598ef  mov     [rax-58h], ebx
0x1800598f2  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1800598f8  call    cs:__imp_TlsGetValue
0x1800598fe  mov     rsi, rax
0x180059901  mov     [rsp+0A8h+var_28], rax
0x180059909  mov     [rsp+0A8h+StringSid], rbx
0x18005990e  mov     [rsp+0A8h+var_54], ebx
0x180059912  mov     [rsp+0A8h+var_50], ebx
0x180059916  mov     [rsp+0A8h+arg_18], ebx
0x18005991d  mov     [rsp+0A8h+hKey], rbx
0x180059922  cmp     cs:dword_18052B32C, ebx
0x180059928  jz      loc_180059B1F
0x18005992e  mov     [rsp+0A8h+var_30], rax
0x180059933  cmp     cs:qword_18052B430, rbx
0x18005993a  jz      loc_180059B18
0x180059940  lea     rdi, [rax+15C8h]
0x180059947  mov     rdx, rdi
0x18005994a  lea     ecx, [rbx+1]
0x18005994d  call    DBOpen2
0x180059952  nop
0x180059953  mov     rdx, cs:qword_18052B430
0x18005995a  mov     rcx, [rdi]
0x18005995d  call    DBFindDSName
0x180059962  mov     [rsp+0A8h+var_58], eax
0x180059966  mov     eax, [rsp+0A8h+var_58]
0x18005996a  test    eax, eax
0x18005996c  jnz     short loc_1800599E5
0x18005996e  mov     [rsp+0A8h+arg_18], ebx
0x180059975  lea     rax, [rsp+0A8h+var_38]
0x18005997a  mov     qword ptr [rsp+0A8h+samDesired], rax
0x18005997f  lea     rax, [rsp+0A8h+arg_18]
0x180059987  mov     qword ptr [rsp+0A8h+dwOptions], rax
0x18005998c  xor     r9d, r9d
0x18005998f  lea     edx, [rbx+1]
0x180059992  mov     r8d, 9028Dh
0x180059998  mov     rcx, [rdi]
0x18005999b  call    DBGetAttVal
0x1800599a0  mov     [rsp+0A8h+var_58], eax
0x1800599a4  mov     eax, [rsp+0A8h+var_58]
0x1800599a8  cmp     eax, 2323h
0x1800599ad  jnz     short loc_1800599B5
0x1800599af  mov     [rsp+0A8h+var_58], ebx
0x1800599b3  jmp     short loc_1800599E5
0x1800599b5  mov     eax, [rsp+0A8h+var_58]
0x1800599b9  test    eax, eax
0x1800599bb  jnz     short loc_1800599E5
0x1800599bd  mov     rcx, [rsp+0A8h+var_38]
0x1800599c2  add     rcx, 18h; Sid
0x1800599c6  call    cs:__imp_RtlValidSid
0x1800599cc  test    al, al
0x1800599ce  jz      short loc_1800599E5
0x1800599d0  mov     rcx, [rsp+0A8h+var_38]
0x1800599d5  add     rcx, 18h; Sid
0x1800599d9  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x1800599de  call    cs:__imp_ConvertSidToStringSidW
0x1800599e4  nop
0x1800599e5  mov     edx, 1
0x1800599ea  mov     rcx, [rdi]
0x1800599ed  call    DBClose
0x1800599f2  mov     eax, [rsp+0A8h+var_58]
0x1800599f6  test    eax, eax
0x1800599f8  jnz     loc_180059AAD
0x1800599fe  mov     [rsp+0A8h+lpdwDisposition], rbx; lpdwDisposition
0x180059a03  lea     rax, [rsp+0A8h+hKey]
0x180059a08  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180059a0d  mov     [rsp+0A8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180059a12  mov     [rsp+0A8h+samDesired], 2001Bh; samDesired
0x180059a1a  mov     [rsp+0A8h+dwOptions], ebx; dwOptions
0x180059a1e  xor     r9d, r9d; lpClass
0x180059a21  xor     r8d, r8d; Reserved
0x180059a24  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"...
0x180059a2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180059a32  call    cs:__imp_RegCreateKeyExW
0x180059a38  mov     [rsp+0A8h+var_58], eax
0x180059a3c  mov     eax, [rsp+0A8h+var_58]
0x180059a40  test    eax, eax
0x180059a42  jnz     short loc_180059AAD
0x180059a44  lea     rdx, ValueName; "RepairAdmin"
0x180059a4b  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180059a50  call    cs:__imp_RegDeleteValueW
0x180059a56  mov     [rsp+0A8h+var_58], eax
0x180059a5a  mov     eax, [rsp+0A8h+var_58]
0x180059a5e  cmp     eax, 2
0x180059a61  jnz     short loc_180059A67
0x180059a63  mov     [rsp+0A8h+var_58], ebx
0x180059a67  mov     rcx, [rsp+0A8h+StringSid]
0x180059a6c  test    rcx, rcx
0x180059a6f  jz      short loc_180059AAD
0x180059a71  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059a75  inc     rax
0x180059a78  cmp     [rcx+rax*2], bx
0x180059a7c  jnz     short loc_180059A75
0x180059a7e  add     eax, eax
0x180059a80  mov     [rsp+0A8h+samDesired], eax; cbData
0x180059a84  mov     rax, [rsp+0A8h+StringSid]
0x180059a89  mov     qword ptr [rsp+0A8h+dwOptions], rax; lpData
0x180059a8e  mov     r9d, 1; dwType
0x180059a94  xor     r8d, r8d; Reserved
0x180059a97  lea     rdx, ValueName; "RepairAdmin"
0x180059a9e  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180059aa3  call    cs:__imp_RegSetValueExW
0x180059aa9  mov     [rsp+0A8h+var_58], eax
0x180059aad  mov     edi, [rsp+0A8h+var_58]
0x180059ab1  jmp     short loc_180059ADA
0x180059ab3  mov     r9d, [rsp+0A8h+var_54]
0x180059ab8  xor     r8d, r8d
0x180059abb  mov     edi, [rsp+0A8h+var_58]
0x180059abf  mov     edx, edi
0x180059ac1  mov     ecx, [rsp+0A8h+var_50]
0x180059ac5  call    HandleDirExceptionsEx
0x180059aca  mov     r14, [rsp+0A8h+arg_10]
0x180059ad2  mov     rsi, [rsp+0A8h+var_28]
0x180059ada  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180059adf  test    rcx, rcx
0x180059ae2  jz      short loc_180059AEA
0x180059ae4  call    cs:__imp_RegCloseKey
0x180059aea  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x180059aef  test    rcx, rcx
0x180059af2  jz      short loc_180059AFA
0x180059af4  call    cs:__imp_LocalFree
0x180059afa  mov     rdx, [rsp+0A8h+var_38]
0x180059aff  test    rdx, rdx
0x180059b02  jz      short loc_180059B14
0x180059b04  mov     [rsp+0A8h+dwOptions], 30F23D4h
0x180059b0c  mov     rcx, rsi
0x180059b0f  call    THFreeAux
0x180059b14  test    edi, edi
0x180059b16  jz      short loc_180059B1F
0x180059b18  mov     dword ptr [r14], 0B4h
0x180059b1f  mov     rbx, [rsp+0A8h+arg_0]
0x180059b27  add     rsp, 90h
0x180059b2e  pop     r14
0x180059b30  pop     rdi
0x180059b31  pop     rsi
0x180059b32  retn
0x180455ad1  push    rbp
0x180455ad3  sub     rsp, 50h
0x180455ad7  mov     rbp, rdx
0x180455ada  mov     edx, 1
0x180455adf  mov     rcx, [rbp+78h]
0x180455ae3  mov     rcx, [rcx+15C8h]
0x180455aea  call    DBClose
0x180455aef  nop
0x180455af0  add     rsp, 50h
0x180455af4  pop     rbp
0x180455af5  retn
0x180455af7  push    rbp
0x180455af9  sub     rsp, 50h
0x180455afd  mov     rbp, rdx
0x180455b00  lea     rax, [rbp+54h]
0x180455b04  mov     [rsp+58h+var_30], rax
0x180455b09  mov     [rsp+58h+var_38], 0
0x180455b12  lea     r9, [rbp+50h]
0x180455b16  lea     r8, [rbp+88h]
0x180455b1d  lea     rdx, [rbp+58h]
0x180455b21  call    GetExceptionDataEx
0x180455b26  nop
0x180455b27  add     rsp, 50h
0x180455b2b  pop     rbp
0x180455b2c  retn
```
