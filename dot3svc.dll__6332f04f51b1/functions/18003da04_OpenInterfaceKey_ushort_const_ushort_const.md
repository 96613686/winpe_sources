# OpenInterfaceKey(ushort const *,ushort const *)

- ea: `0x18003da04`
- end: `0x18003db5a`
- name: `?OpenInterfaceKey@@YAPEAUHKEY__@@PEBG0@Z`
- size: `342`
- prototype: `HKEY __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d5f8`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180036dfc`
- `0x18003da04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003da7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dabc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003da7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dabc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003db02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003db02`

## pseudocode

```c
HKEY __fastcall OpenInterfaceKey(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // eax
  DWORD v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  phkResult = (HKEY)a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_43c25e6966dd323a74f103f30608f523_Traceguids);
  }
  hKey = 0;
  phkResult = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Wlansvc\\MigrationData\\Upgrade\\EAPOL\\Parameters\\Interfaces",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
    {
      v6 = 11;
LABEL_12:
      WPP_SF_d(v5[1].Flink, v6, WPP_43c25e6966dd323a74f103f30608f523_Traceguids, v3);
    }
  }
  else
  {
    v3 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult);
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v6 = 12;
        goto LABEL_12;
      }
    }
  }
  SafeCloseKey(&hKey);
  if ( v4 )
  {
    SetLastError(v4);
    SafeCloseKey(&phkResult);
    phkResult = 0;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 13, WPP_43c25e6966dd323a74f103f30608f523_Traceguids, v4);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18003da04  mov     [rsp+arg_8], rbx
0x18003da09  mov     [rsp+arg_18], rsi
0x18003da0e  mov     [rsp+arg_0], rcx
0x18003da13  push    rdi
0x18003da14  sub     rsp, 30h
0x18003da18  mov     rdi, rdx
0x18003da1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da22  lea     rsi, WPP_GLOBAL_Control
0x18003da29  cmp     rcx, rsi
0x18003da2c  jz      short loc_18003DA49
0x18003da2e  test    byte ptr [rcx+1Ch], 10h
0x18003da32  jz      short loc_18003DA49
0x18003da34  mov     rcx, [rcx+10h]
0x18003da38  lea     r8, WPP_43c25e6966dd323a74f103f30608f523_Traceguids
0x18003da3f  mov     edx, 0Ah
0x18003da44  call    WPP_SF_
0x18003da49  lea     rax, [rsp+38h+hKey]
0x18003da4e  mov     [rsp+38h+hKey], 0
0x18003da57  mov     r9d, 20019h; samDesired
0x18003da5d  mov     [rsp+38h+phkResult], rax; phkResult
0x18003da62  xor     r8d, r8d; ulOptions
0x18003da65  mov     [rsp+38h+arg_0], 0
0x18003da6e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Wlansvc\\Migration"...
0x18003da75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003da7c  call    cs:__imp_RegOpenKeyExW
0x18003da82  mov     ebx, eax
0x18003da84  test    eax, eax
0x18003da86  jz      short loc_18003DAA1
0x18003da88  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da8f  cmp     rcx, rsi
0x18003da92  jz      short loc_18003DAF2
0x18003da94  test    byte ptr [rcx+1Ch], 2
0x18003da98  jz      short loc_18003DAF2
0x18003da9a  mov     edx, 0Bh
0x18003da9f  jmp     short loc_18003DADF
0x18003daa1  mov     rcx, [rsp+38h+hKey]; hKey
0x18003daa6  lea     rax, [rsp+38h+arg_0]
0x18003daab  mov     r9d, 20019h; samDesired
0x18003dab1  mov     [rsp+38h+phkResult], rax; phkResult
0x18003dab6  xor     r8d, r8d; ulOptions
0x18003dab9  mov     rdx, rdi; lpSubKey
0x18003dabc  call    cs:__imp_RegOpenKeyExW
0x18003dac2  mov     ebx, eax
0x18003dac4  test    eax, eax
0x18003dac6  jz      short loc_18003DAF2
0x18003dac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dacf  cmp     rcx, rsi
0x18003dad2  jz      short loc_18003DAF2
0x18003dad4  test    byte ptr [rcx+1Ch], 2
0x18003dad8  jz      short loc_18003DAF2
0x18003dada  mov     edx, 0Ch
0x18003dadf  mov     rcx, [rcx+10h]
0x18003dae3  lea     r8, WPP_43c25e6966dd323a74f103f30608f523_Traceguids
0x18003daea  mov     r9d, eax
0x18003daed  call    WPP_SF_d
0x18003daf2  lea     rcx, [rsp+38h+hKey]; HKEY *
0x18003daf7  call    ?SafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * &)
0x18003dafc  test    ebx, ebx
0x18003dafe  jz      short loc_18003DB1B
0x18003db00  mov     ecx, ebx; dwErrCode
0x18003db02  call    cs:__imp_SetLastError
0x18003db08  lea     rcx, [rsp+38h+arg_0]; HKEY *
0x18003db0d  call    ?SafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * &)
0x18003db12  mov     [rsp+38h+arg_0], 0
0x18003db1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db22  cmp     rcx, rsi
0x18003db25  jz      short loc_18003DB45
0x18003db27  test    byte ptr [rcx+1Ch], 10h
0x18003db2b  jz      short loc_18003DB45
0x18003db2d  mov     rcx, [rcx+10h]
0x18003db31  lea     r8, WPP_43c25e6966dd323a74f103f30608f523_Traceguids
0x18003db38  mov     edx, 0Dh
0x18003db3d  mov     r9d, ebx
0x18003db40  call    WPP_SF_d
0x18003db45  mov     rax, [rsp+38h+arg_0]
0x18003db4a  mov     rbx, [rsp+38h+arg_8]
0x18003db4f  mov     rsi, [rsp+38h+arg_18]
0x18003db54  add     rsp, 30h
0x18003db58  pop     rdi
0x18003db59  retn
```
