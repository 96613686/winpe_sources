# EEDBManager::SetEnrollmentAadSendDeviceToken(_GUID,int)

- ea: `0x18003ff08`
- end: `0x18003ffb8`
- name: `?SetEnrollmentAadSendDeviceToken@EEDBManager@@SAJU_GUID@@H@Z`
- size: `176`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180040b90`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18003ff08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ff59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ffaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ff59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ffaa`

## string_xrefs

- `0x18003ff73`: `AADSendDeviceToken`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetEnrollmentAadSendDeviceToken(struct _GUID *a1, int a2)
{
  LSTATUS v3; // eax
  HKEY v4; // rcx
  unsigned int v5; // ebx
  LSTATUS v7; // eax
  struct _GUID v8; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = *a1;
  v3 = EEDBManager::OpenEnrollmentKey(&v8, 131078, 0, &hKey);
  v4 = hKey;
  v5 = v3;
  if ( v3 < 0 )
  {
LABEL_2:
    if ( v4 )
      RegCloseKey(v4);
    return v5;
  }
  v7 = RegSetValueExW(hKey, L"AADSendDeviceToken", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    v4 = hKey;
    goto LABEL_2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003ff08  mov     [rsp+Data], edx
0x18003ff0c  push    rbx
0x18003ff0d  sub     rsp, 40h
0x18003ff11  mov     rbx, rcx
0x18003ff14  mov     [rsp+48h+hKey], 0
0x18003ff1d  lea     rcx, [rsp+48h+hKey]
0x18003ff22  xor     edx, edx
0x18003ff24  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003ff29  movaps  xmm0, xmmword ptr [rbx]
0x18003ff2c  lea     r9, [rsp+48h+hKey]; HKEY *
0x18003ff31  xor     r8d, r8d; unsigned __int16 *
0x18003ff34  movdqa  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18003ff3a  mov     edx, 20006h; unsigned int
0x18003ff3f  lea     rcx, [rsp+48h+var_18]; struct _GUID
0x18003ff44  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18003ff49  mov     rcx, [rsp+48h+hKey]; hKey
0x18003ff4e  mov     ebx, eax
0x18003ff50  test    eax, eax
0x18003ff52  jns     short loc_18003FF63
0x18003ff54  test    rcx, rcx
0x18003ff57  jz      short loc_18003FF5F
0x18003ff59  call    cs:__imp_RegCloseKey
0x18003ff5f  mov     eax, ebx
0x18003ff61  jmp     short loc_18003FFB2
0x18003ff63  mov     r9d, 4; dwType
0x18003ff69  lea     rax, [rsp+48h+Data]
0x18003ff6e  mov     [rsp+48h+cbData], r9d; cbData
0x18003ff73  lea     rdx, aAadsenddevicet; "AADSendDeviceToken"
0x18003ff7a  xor     r8d, r8d; Reserved
0x18003ff7d  mov     [rsp+48h+lpData], rax; lpData
0x18003ff82  call    cs:__imp_RegSetValueExW
0x18003ff88  mov     ebx, eax
0x18003ff8a  test    eax, eax
0x18003ff8c  jz      short loc_18003FFA0
0x18003ff8e  jle     short loc_18003FF99
0x18003ff90  movzx   ebx, ax
0x18003ff93  or      ebx, 80070000h
0x18003ff99  mov     rcx, [rsp+48h+hKey]
0x18003ff9e  jmp     short loc_18003FF54
0x18003ffa0  mov     rcx, [rsp+48h+hKey]; hKey
0x18003ffa5  test    rcx, rcx
0x18003ffa8  jz      short loc_18003FFB0
0x18003ffaa  call    cs:__imp_RegCloseKey
0x18003ffb0  xor     eax, eax
0x18003ffb2  add     rsp, 40h
0x18003ffb6  pop     rbx
0x18003ffb7  retn
```
