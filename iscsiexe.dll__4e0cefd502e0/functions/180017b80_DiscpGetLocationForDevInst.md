# DiscpGetLocationForDevInst

- ea: `0x180017b80`
- end: `0x180017cc4`
- name: `DiscpGetLocationForDevInst`
- size: `324`
- prototype: `__int64 __fastcall(DEVINST dnDevInst, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180017ccc`

## callees

- `0x180017b80`

## import_xrefs

- `ISCSIUM!DiscpGetRegistryValue` at `0x180017bfb`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180017bfb`
- `ISCSIUM!DiscpAllocMemory` at `0x180017c1d`
- `ISCSIUM!DiscpAllocMemory` at `0x180017c5e`
- `ISCSIUM!DiscpAllocMemory` at `0x180017c1d`
- `ISCSIUM!DiscpAllocMemory` at `0x180017c5e`
- `ISCSIUM!DiscpFreeMemory` at `0x180017c55`
- `ISCSIUM!DiscpFreeMemory` at `0x180017c9d`
- `ISCSIUM!DiscpFreeMemory` at `0x180017c55`
- `ISCSIUM!DiscpFreeMemory` at `0x180017c9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c07`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180017bce`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180017bce`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x180017c47`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x180017c86`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x180017c47`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x180017c86`

## pseudocode

```c
__int64 __fastcall DiscpGetLocationForDevInst(DEVINST dnDevInst, _QWORD *a2)
{
  unsigned int RegistryValue; // ebx
  void *v5; // rdi
  CONFIGRET DevNode_Registry_PropertyW; // eax
  int phkDevice; // [rsp+20h] [rbp-30h]
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  ULONG pulLength; // [rsp+80h] [rbp+30h] BYREF
  ULONG pulRegDataType; // [rsp+88h] [rbp+38h] BYREF

  pulLength = 0;
  hKey = 0;
  pulRegDataType = 0;
  if ( !CM_Open_DevNode_Key(dnDevInst, 0x20019u, 0, 1u, &hKey, 1u) )
  {
    LOBYTE(phkDevice) = 0;
    RegistryValue = DiscpGetRegistryValue(hKey, 0, L"LocationInformationOverride", 1, phkDevice, a2, &pulLength);
    RegCloseKey(hKey);
    if ( !RegistryValue )
      return RegistryValue;
  }
  pulLength = 520;
  v5 = (void *)DiscpAllocMemory(520);
  if ( !v5 )
    return 8;
  RegistryValue = 0;
  DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(dnDevInst, 0xEu, &pulRegDataType, v5, &pulLength, 0);
  if ( DevNode_Registry_PropertyW != 26 )
    goto LABEL_7;
  DiscpFreeMemory(v5);
  v5 = (void *)DiscpAllocMemory(pulLength);
  if ( !v5 )
    return 8;
  DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(dnDevInst, 0xEu, &pulRegDataType, v5, &pulLength, 0);
LABEL_7:
  if ( DevNode_Registry_PropertyW )
  {
    if ( v5 )
    {
      DiscpFreeMemory(v5);
      return (unsigned int)-268500981;
    }
  }
  else
  {
    *a2 = v5;
  }
  return RegistryValue;
}

```

## disassembly

```asm
0x180017b80  mov     [rsp-18h+arg_0], rbx
0x180017b85  mov     [rsp-18h+arg_8], rsi
0x180017b8a  push    rbp
0x180017b8b  push    rdi
0x180017b8c  push    r14
0x180017b8e  mov     rbp, rsp
0x180017b91  sub     rsp, 50h
0x180017b95  mov     ebx, 1
0x180017b9a  mov     [rbp+pulLength], 0
0x180017ba1  mov     rsi, rdx
0x180017ba4  mov     [rsp+50h+ulFlags], ebx; ulFlags
0x180017ba8  lea     rax, [rbp+hKey]
0x180017bac  mov     [rbp+hKey], 0
0x180017bb4  mov     r9d, ebx; Disposition
0x180017bb7  mov     [rsp+50h+phkDevice], rax; phkDevice
0x180017bbc  xor     r8d, r8d; ulHardwareProfile
0x180017bbf  mov     [rbp+pulRegDataType], 0
0x180017bc6  mov     edx, 20019h; samDesired
0x180017bcb  mov     r14d, ecx
0x180017bce  call    cs:__imp_CM_Open_DevNode_Key
0x180017bd4  test    eax, eax
0x180017bd6  jnz     short loc_180017C15
0x180017bd8  mov     rcx, [rbp+hKey]
0x180017bdc  lea     rax, [rbp+pulLength]
0x180017be0  mov     [rsp+50h+var_20], rax
0x180017be5  lea     r8, aLocationinform; "LocationInformationOverride"
0x180017bec  mov     qword ptr [rsp+50h+ulFlags], rsi
0x180017bf1  mov     r9d, ebx
0x180017bf4  xor     edx, edx
0x180017bf6  mov     byte ptr [rsp+50h+phkDevice], 0
0x180017bfb  call    cs:__imp_DiscpGetRegistryValue
0x180017c01  mov     rcx, [rbp+hKey]; hKey
0x180017c05  mov     ebx, eax
0x180017c07  call    cs:__imp_RegCloseKey
0x180017c0d  test    ebx, ebx
0x180017c0f  jz      loc_180017CAF
0x180017c15  mov     ecx, 208h
0x180017c1a  mov     [rbp+pulLength], ecx
0x180017c1d  call    cs:__imp_DiscpAllocMemory
0x180017c23  mov     rdi, rax
0x180017c26  test    rax, rax
0x180017c29  jz      short loc_180017CAA
0x180017c2b  xor     ebx, ebx
0x180017c2d  lea     rax, [rbp+pulLength]
0x180017c31  mov     [rsp+50h+ulFlags], ebx; ulFlags
0x180017c35  lea     r8, [rbp+pulRegDataType]; pulRegDataType
0x180017c39  mov     r9, rdi; Buffer
0x180017c3c  mov     [rsp+50h+phkDevice], rax; pulLength
0x180017c41  mov     ecx, r14d; dnDevInst
0x180017c44  lea     edx, [rbx+0Eh]; ulProperty
0x180017c47  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180017c4d  cmp     eax, 1Ah
0x180017c50  jnz     short loc_180017C8C
0x180017c52  mov     rcx, rdi
0x180017c55  call    cs:__imp_DiscpFreeMemory
0x180017c5b  mov     ecx, [rbp+pulLength]
0x180017c5e  call    cs:__imp_DiscpAllocMemory
0x180017c64  mov     rdi, rax
0x180017c67  test    rax, rax
0x180017c6a  jz      short loc_180017CAA
0x180017c6c  lea     rax, [rbp+pulLength]
0x180017c70  mov     [rsp+50h+ulFlags], ebx; ulFlags
0x180017c74  mov     r9, rdi; Buffer
0x180017c77  mov     [rsp+50h+phkDevice], rax; pulLength
0x180017c7c  lea     r8, [rbp+pulRegDataType]; pulRegDataType
0x180017c80  mov     ecx, r14d; dnDevInst
0x180017c83  lea     edx, [rbx+0Eh]; ulProperty
0x180017c86  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180017c8c  test    eax, eax
0x180017c8e  jnz     short loc_180017C95
0x180017c90  mov     [rsi], rdi
0x180017c93  jmp     short loc_180017CAF
0x180017c95  test    rdi, rdi
0x180017c98  jz      short loc_180017CAF
0x180017c9a  mov     rcx, rdi
0x180017c9d  call    cs:__imp_DiscpFreeMemory
0x180017ca3  mov     ebx, 0EFFF000Bh
0x180017ca8  jmp     short loc_180017CAF
0x180017caa  mov     ebx, 8
0x180017caf  mov     rsi, [rsp+50h+arg_8]
0x180017cb4  mov     eax, ebx
0x180017cb6  mov     rbx, [rsp+50h+arg_0]
0x180017cbb  add     rsp, 50h
0x180017cbf  pop     r14
0x180017cc1  pop     rdi
0x180017cc2  pop     rbp
0x180017cc3  retn
```
