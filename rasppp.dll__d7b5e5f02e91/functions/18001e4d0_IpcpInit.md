# IpcpInit

- ea: `0x18001e4d0`
- end: `0x18001e5aa`
- name: `IpcpInit`
- size: `218`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001e4d0`
- `0x180031dec`
- `0x18003216c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001e555`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001e555`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e582`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e582`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x18001e521`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x18001e521`

## string_xrefs

- `0x18001e506`: `SYSTEM\CurrentControlSet\Services\RasMan\PPP\ControlProtocols\BuiltIn`
- `0x18001e549`: `MaxMSIPCPOptionCfgCnt`

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
    if ( !dword_18004D584 )
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
    ++dword_18004D584;
  }
  else
  {
    --dword_18004D584;
    HelperUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x18001e4d0  push    rbp
0x18001e4d2  mov     rbp, rsp
0x18001e4d5  sub     rsp, 30h
0x18001e4d9  test    ecx, ecx
0x18001e4db  jz      loc_18001E596
0x18001e4e1  call    HelperInitialize
0x18001e4e6  test    eax, eax
0x18001e4e8  jnz     loc_18001E5A3
0x18001e4ee  cmp     cs:dword_18004D584, eax
0x18001e4f4  jnz     loc_18001E58E
0x18001e4fa  lea     r8, [rbp+phkResult]; phkResult
0x18001e4fe  mov     [rbp+phkResult], 0
0x18001e506  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18001e50d  mov     [rbp+Type], eax
0x18001e510  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e517  mov     [rbp+Data], eax
0x18001e51a  mov     [rbp+cbData], 4
0x18001e521  call    cs:__imp_RegOpenKeyA
0x18001e528  nop     dword ptr [rax+rax+00h]
0x18001e52d  test    eax, eax
0x18001e52f  jnz     short loc_18001E58E
0x18001e531  mov     rcx, [rbp+phkResult]; hKey
0x18001e535  lea     rax, [rbp+cbData]
0x18001e539  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001e53e  lea     r9, [rbp+Type]; lpType
0x18001e542  lea     rax, [rbp+Data]
0x18001e546  xor     r8d, r8d; lpReserved
0x18001e549  lea     rdx, aMaxmsipcpoptio; "MaxMSIPCPOptionCfgCnt"
0x18001e550  mov     [rsp+30h+lpData], rax; lpData
0x18001e555  call    cs:__imp_RegQueryValueExA
0x18001e55c  nop     dword ptr [rax+rax+00h]
0x18001e561  test    eax, eax
0x18001e563  jnz     short loc_18001E57E
0x18001e565  cmp     [rbp+Type], 4
0x18001e569  jnz     short loc_18001E57E
0x18001e56b  cmp     [rbp+cbData], 4
0x18001e56f  jnz     short loc_18001E57E
0x18001e571  mov     eax, [rbp+Data]
0x18001e574  test    eax, eax
0x18001e576  jz      short loc_18001E57E
0x18001e578  mov     cs:DwMaxMSOptionCfgCnt, eax
0x18001e57e  mov     rcx, [rbp+phkResult]; hKey
0x18001e582  call    cs:__imp_RegCloseKey
0x18001e589  nop     dword ptr [rax+rax+00h]
0x18001e58e  inc     cs:dword_18004D584
0x18001e594  jmp     short loc_18001E5A1
0x18001e596  dec     cs:dword_18004D584
0x18001e59c  call    HelperUninitialize
0x18001e5a1  xor     eax, eax
0x18001e5a3  add     rsp, 30h
0x18001e5a7  pop     rbp
0x18001e5a8  retn
```
