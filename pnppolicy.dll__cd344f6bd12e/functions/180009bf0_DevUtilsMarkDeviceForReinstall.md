# DevUtilsMarkDeviceForReinstall

- ea: `0x180009bf0`
- end: `0x180009c97`
- name: `DevUtilsMarkDeviceForReinstall`
- size: `167`
- prototype: `__int64 __fastcall(__int64 dnDevInst, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180001da8`

## callees

- `0x1800096a8`
- `0x180009bf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c61`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180009c4d`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180009c4d`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_Registry_PropertyW` at `0x180009c3e`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_Registry_PropertyW` at `0x180009c3e`
- `DEVRTL!DevRtlWriteTextLog` at `0x180009c82`
- `DEVRTL!DevRtlWriteTextLog` at `0x180009c82`

## string_xrefs

- `0x180009c67`: `Unable to mark device for reinstall. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall DevUtilsMarkDeviceForReinstall(__int64 dnDevInst, __int64 a2)
{
  DWORD LastError; // ebx
  DEVINST v4; // esi
  int ConfigFlags; // eax
  DWORD v6; // edi
  CONFIGRET v7; // eax
  int v9; // [rsp+60h] [rbp+18h] BYREF
  int Buffer; // [rsp+68h] [rbp+20h] BYREF

  LastError = 0;
  v9 = 0;
  v4 = dnDevInst;
  ConfigFlags = DevUtilsGetConfigFlags(dnDevInst, &v9);
  if ( ConfigFlags )
    ConfigFlags = v9;
  else
    v9 = 0;
  if ( (ConfigFlags & 0x20) == 0 )
  {
    v6 = 0;
    Buffer = ConfigFlags | 0x20;
    v7 = CM_Set_DevNode_Registry_PropertyW(v4, 0xBu, &Buffer, 4u, 0);
    if ( v7 )
      v6 = CM_MapCrToWin32Err(v7, 0xDu);
    SetLastError(v6);
    if ( v6 )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(a2, 512, 2, "Unable to mark device for reinstall. Error = 0x%08X", LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180009bf0  mov     [rsp+arg_0], rbx
0x180009bf5  push    rbp
0x180009bf6  push    rsi
0x180009bf7  push    rdi
0x180009bf8  sub     rsp, 30h
0x180009bfc  mov     rbp, rdx
0x180009bff  xor     ebx, ebx
0x180009c01  lea     rdx, [rsp+48h+arg_10]
0x180009c06  mov     [rsp+48h+arg_10], ebx
0x180009c0a  mov     esi, ecx
0x180009c0c  call    DevUtilsGetConfigFlags
0x180009c11  test    eax, eax
0x180009c13  jnz     short loc_180009C1B
0x180009c15  mov     [rsp+48h+arg_10], eax
0x180009c19  jmp     short loc_180009C1F
0x180009c1b  mov     eax, [rsp+48h+arg_10]
0x180009c1f  test    al, 20h
0x180009c21  jnz     short loc_180009C88
0x180009c23  xor     edi, edi
0x180009c25  mov     [rsp+48h+ulFlags], ebx; ulFlags
0x180009c29  or      eax, 20h
0x180009c2c  lea     r8, [rsp+48h+Buffer]; Buffer
0x180009c31  mov     ecx, esi; dnDevInst
0x180009c33  mov     [rsp+48h+Buffer], eax
0x180009c37  lea     r9d, [rdi+4]; ulLength
0x180009c3b  lea     edx, [rdi+0Bh]; ulProperty
0x180009c3e  call    cs:__imp_CM_Set_DevNode_Registry_PropertyW
0x180009c44  test    eax, eax
0x180009c46  jz      short loc_180009C55
0x180009c48  lea     edx, [rdi+0Dh]; DefaultErr
0x180009c4b  mov     ecx, eax; CmReturnCode
0x180009c4d  call    cs:__imp_CM_MapCrToWin32Err
0x180009c53  mov     edi, eax
0x180009c55  mov     ecx, edi; dwErrCode
0x180009c57  call    cs:__imp_SetLastError
0x180009c5d  test    edi, edi
0x180009c5f  jz      short loc_180009C88
0x180009c61  call    cs:__imp_GetLastError
0x180009c67  lea     r9, aUnableToMarkDe; "Unable to mark device for reinstall. Er"...
0x180009c6e  mov     edx, 200h
0x180009c73  mov     r8d, 2
0x180009c79  mov     [rsp+48h+ulFlags], eax
0x180009c7d  mov     rcx, rbp
0x180009c80  mov     ebx, eax
0x180009c82  call    cs:__imp_DevRtlWriteTextLog
0x180009c88  mov     eax, ebx
0x180009c8a  mov     rbx, [rsp+48h+arg_0]
0x180009c8f  add     rsp, 30h
0x180009c93  pop     rdi
0x180009c94  pop     rsi
0x180009c95  pop     rbp
0x180009c96  retn
```
