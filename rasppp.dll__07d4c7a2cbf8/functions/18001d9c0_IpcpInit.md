# IpcpInit

- ea: `0x18001d9c0`
- end: `0x18001da87`
- name: `IpcpInit`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001d9c0`
- `0x1800308a0`
- `0x180030c0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001da3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001da3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da66`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x18001da11`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x18001da11`

## string_xrefs

- `0x18001d9f6`: `SYSTEM\CurrentControlSet\Services\RasMan\PPP\ControlProtocols\BuiltIn`
- `0x18001da33`: `MaxMSIPCPOptionCfgCnt`

## pseudocode

```c
__int64 __fastcall IpcpInit(int a1)
{
  __int64 result; // rax
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+28h] BYREF

  if ( a1 )
  {
    result = HelperInitialize();
    if ( (_DWORD)result )
      return result;
    if ( !dword_18004C584 )
    {
      phkResult = 0;
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegOpenKeyA(
              HKEY_LOCAL_MACHINE,
              "SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\ControlProtocols\\BuiltIn",
              &phkResult) )
      {
        if ( !RegQueryValueExA(phkResult, "MaxMSIPCPOptionCfgCnt", 0, &Type, (LPBYTE)&Data, &cbData)
          && Type == 4
          && cbData == 4 )
        {
          if ( Data )
            DwMaxMSOptionCfgCnt = Data;
        }
        RegCloseKey(phkResult);
      }
    }
    ++dword_18004C584;
  }
  else
  {
    --dword_18004C584;
    HelperUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x18001d9c0  push    rbp
0x18001d9c2  mov     rbp, rsp
0x18001d9c5  sub     rsp, 30h
0x18001d9c9  test    ecx, ecx
0x18001d9cb  jz      loc_18001DA74
0x18001d9d1  call    HelperInitialize
0x18001d9d6  test    eax, eax
0x18001d9d8  jnz     loc_18001DA81
0x18001d9de  cmp     cs:dword_18004C584, eax
0x18001d9e4  jnz     loc_18001DA6C
0x18001d9ea  lea     r8, [rbp+phkResult]; phkResult
0x18001d9ee  mov     [rbp+phkResult], 0
0x18001d9f6  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18001d9fd  mov     [rbp+Type], eax
0x18001da00  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001da07  mov     [rbp+Data], eax
0x18001da0a  mov     [rbp+cbData], 4
0x18001da11  call    cs:__imp_RegOpenKeyA
0x18001da17  test    eax, eax
0x18001da19  jnz     short loc_18001DA6C
0x18001da1b  mov     rcx, [rbp+phkResult]; hKey
0x18001da1f  lea     rax, [rbp+cbData]
0x18001da23  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001da28  lea     r9, [rbp+Type]; lpType
0x18001da2c  lea     rax, [rbp+Data]
0x18001da30  xor     r8d, r8d; lpReserved
0x18001da33  lea     rdx, aMaxmsipcpoptio; "MaxMSIPCPOptionCfgCnt"
0x18001da3a  mov     [rsp+30h+lpData], rax; lpData
0x18001da3f  call    cs:__imp_RegQueryValueExA
0x18001da45  test    eax, eax
0x18001da47  jnz     short loc_18001DA62
0x18001da49  cmp     [rbp+Type], 4
0x18001da4d  jnz     short loc_18001DA62
0x18001da4f  cmp     [rbp+cbData], 4
0x18001da53  jnz     short loc_18001DA62
0x18001da55  mov     eax, [rbp+Data]
0x18001da58  test    eax, eax
0x18001da5a  jz      short loc_18001DA62
0x18001da5c  mov     cs:DwMaxMSOptionCfgCnt, eax
0x18001da62  mov     rcx, [rbp+phkResult]; hKey
0x18001da66  call    cs:__imp_RegCloseKey
0x18001da6c  inc     cs:dword_18004C584
0x18001da72  jmp     short loc_18001DA7F
0x18001da74  dec     cs:dword_18004C584
0x18001da7a  call    HelperUninitialize
0x18001da7f  xor     eax, eax
0x18001da81  add     rsp, 30h
0x18001da85  pop     rbp
0x18001da86  retn
```
