# EEDBManager::SetMmpcEnrollmentFlag(ulong)

- ea: `0x180040168`
- end: `0x180040237`
- name: `?SetMmpcEnrollmentFlag@EEDBManager@@SAJK@Z`
- size: `207`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035f30`
- `0x18003ace0`
- `0x180040d00`

## callees

- `0x1800071c0`
- `0x180007220`
- `0x180011938`
- `0x180040168`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180040186`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180040186`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040206`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800401d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040229`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800401d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040229`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetMmpcEnrollmentFlag(int a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  char IsStateSeparationEnabled; // al
  const WCHAR *v4; // rcx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  LSTATUS v8; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v2, v1);
  v4 = L"OSData\\Software\\Microsoft\\Enrollments";
  if ( !IsStateSeparationEnabled )
    v4 = L"Software\\Microsoft\\Enrollments";
  v5 = EEDBManager::OpenHKEY(v4, 983103, &hKey);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC86,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\database\\src\\dbmanager.cpp",
      (const char *)(unsigned int)v5,
      lpData);
LABEL_5:
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v8 = RegSetValueExW(hKey, L"MmpcEnrollmentFlag", 0, 4u, (const BYTE *)&Data, 4u);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180040168  mov     [rsp+Data], ecx
0x18004016c  push    rbx
0x18004016d  sub     rsp, 30h
0x180040171  xor     edx, edx
0x180040173  mov     [rsp+38h+hKey], 0
0x18004017c  lea     rcx, [rsp+38h+hKey]
0x180040181  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040186  call    cs:__imp_RtlIsStateSeparationEnabled
0x18004018c  lea     rdx, SubKey; "Software\\Microsoft\\Enrollments"
0x180040193  test    al, al
0x180040195  lea     rcx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x18004019c  cmovz   rcx, rdx; lpSubKey
0x1800401a0  lea     r8, [rsp+38h+hKey]; HKEY *
0x1800401a5  mov     edx, 0F003Fh; unsigned int
0x1800401aa  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x1800401af  mov     ebx, eax
0x1800401b1  test    eax, eax
0x1800401b3  jns     short loc_1800401E2
0x1800401b5  mov     rcx, [rsp+38h]; this
0x1800401ba  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800401c1  mov     r9d, eax; char *
0x1800401c4  mov     edx, 0C86h; void *
0x1800401c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800401ce  mov     rcx, [rsp+38h+hKey]; hKey
0x1800401d3  test    rcx, rcx
0x1800401d6  jz      short loc_1800401DE
0x1800401d8  call    cs:__imp_RegCloseKey
0x1800401de  mov     eax, ebx
0x1800401e0  jmp     short loc_180040231
0x1800401e2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800401e7  lea     rax, [rsp+38h+Data]
0x1800401ec  mov     r9d, 4; dwType
0x1800401f2  lea     rdx, aMmpcenrollment; "MmpcEnrollmentFlag"
0x1800401f9  mov     [rsp+38h+cbData], r9d; cbData
0x1800401fe  xor     r8d, r8d; Reserved
0x180040201  mov     [rsp+38h+lpData], rax; lpData
0x180040206  call    cs:__imp_RegSetValueExW
0x18004020c  mov     ebx, eax
0x18004020e  test    eax, eax
0x180040210  jz      short loc_18004021F
0x180040212  jle     short loc_1800401CE
0x180040214  movzx   ebx, ax
0x180040217  or      ebx, 80070000h
0x18004021d  jmp     short loc_1800401CE
0x18004021f  mov     rcx, [rsp+38h+hKey]; hKey
0x180040224  test    rcx, rcx
0x180040227  jz      short loc_18004022F
0x180040229  call    cs:__imp_RegCloseKey
0x18004022f  xor     eax, eax
0x180040231  add     rsp, 30h
0x180040235  pop     rbx
0x180040236  retn
```
