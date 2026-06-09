# UddpDisableUnsignedBootDriver

- ea: `0x1800b0e88`
- end: `0x1800b10e1`
- name: `UddpDisableUnsignedBootDriver`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800319f0`
- `0x1800b0c98`

## callees

- `0x18000c018`
- `0x180012920`
- `0x180013334`
- `0x180013540`
- `0x180038e34`
- `0x1800b0e88`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800b10bb`
- `ntdll!RtlFreeHeap` at `0x1800b10bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b0fda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b0fda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1038`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1038`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b0f2d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b0f5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b0f2d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b0f5c`

## string_xrefs

- `0x1800b0f88`: `SYSTEM\CurrentControlSet\Services`
- `0x1800b0fe8`: `Failed to open key to disable Driver: '%ls' [%d]`

## pseudocode

```c
BOOLEAN __fastcall UddpDisableUnsignedBootDriver(__int64 a1)
{
  WCHAR *v2; // rbp
  const char *v3; // r9
  int v4; // r8d
  const WCHAR *ServiceRegStringValue; // rax
  unsigned __int64 v6; // rsi
  BOOL v7; // edi
  const unsigned __int16 *v8; // rsi
  const char *v9; // r9
  int v10; // r8d
  LSTATUS v11; // edi
  BYTE Data[8]; // [rsp+30h] [rbp-2A8h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-2A0h] BYREF
  WCHAR SubKey[296]; // [rsp+40h] [rbp-298h] BYREF

  if ( (unsigned int)UddpGetServiceRegDWORDValue(*(LPCWSTR *)(a1 + 16), L"Start") )
  {
    v2 = 0;
    v3 = "Not a Boot Driver: '%ls'";
    v4 = 2606;
LABEL_19:
    AslLogCallPrintf(3, (unsigned int)"UddpDisableUnsignedBootDriver", v4, (_DWORD)v3);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  }
  ServiceRegStringValue = (const WCHAR *)UddpGetServiceRegStringValue(*(LPCWSTR *)(a1 + 16), L"Group", 2u);
  v2 = (WCHAR *)ServiceRegStringValue;
  if ( !ServiceRegStringValue )
    goto LABEL_8;
  v6 = -1;
  do
    ++v6;
  while ( ServiceRegStringValue[v6] );
  if ( v6 == 6 && CompareStringOrdinal(ServiceRegStringValue, 6, L"filter", 6, 1) == 2 )
  {
LABEL_8:
    v7 = 1;
  }
  else
  {
    v7 = 0;
    if ( v6 >= 8 )
      v7 = CompareStringOrdinal(v2, 8, L"FsFilter", 8, 1) == 2;
  }
  v8 = *(const unsigned __int16 **)(a1 + 16);
  if ( !v7 )
  {
    v3 = "Not a Filter Driver: '%ls'";
    v4 = 2689;
    goto LABEL_19;
  }
  phkResult = 0;
  *(_DWORD *)Data = 4;
  StringCchCopyW(SubKey, 0x122u, L"SYSTEM\\CurrentControlSet\\Services");
  StringCchCatW(SubKey, 0x122u, L"\\");
  StringCchCatW(SubKey, 0x122u, v8);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 2u, &phkResult) )
  {
    v9 = "Failed to open key to disable Driver: '%ls' [%d]";
    v10 = 2668;
  }
  else
  {
    v11 = RegSetValueExW(phkResult, L"Start", 0, 4u, Data, 4u);
    RegCloseKey(phkResult);
    if ( !v11 )
    {
      v3 = "Disabled Driver: '%ls'";
      v4 = 2687;
      goto LABEL_19;
    }
    v9 = "Failed to set value to disable Driver: '%ls' [%d]";
    v10 = 2683;
  }
  AslLogCallPrintf(1, (unsigned int)"UddpDisableUnsignedBootDriver", v10, (_DWORD)v9);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
}

```

## disassembly

```asm
0x1800b0e88  push    rbx
0x1800b0e8a  push    rbp
0x1800b0e8b  push    rsi
0x1800b0e8c  push    rdi
0x1800b0e8d  push    r14
0x1800b0e8f  push    r15
0x1800b0e91  sub     rsp, 2A8h
0x1800b0e98  mov     rax, cs:__security_cookie
0x1800b0e9f  xor     rax, rsp
0x1800b0ea2  mov     [rsp+2D8h+var_48], rax
0x1800b0eaa  mov     r14, rcx
0x1800b0ead  lea     rdx, aStart; "Start"
0x1800b0eb4  mov     rcx, [rcx+10h]; lpSubKey
0x1800b0eb8  call    UddpGetServiceRegDWORDValue
0x1800b0ebd  mov     rcx, [r14+10h]; lpSubKey
0x1800b0ec1  xor     r15d, r15d
0x1800b0ec4  test    eax, eax
0x1800b0ec6  jz      short loc_1800B0EE2
0x1800b0ec8  mov     ebp, r15d
0x1800b0ecb  mov     qword ptr [rsp+2D8h+bIgnoreCase], rcx
0x1800b0ed0  lea     r9, aNotABootDriver; "Not a Boot Driver: '%ls'"
0x1800b0ed7  mov     r8d, 0A2Eh
0x1800b0edd  jmp     loc_1800B1098
0x1800b0ee2  mov     r8d, 2; dwFlags
0x1800b0ee8  lea     rdx, aGroup; "Group"
0x1800b0eef  call    UddpGetServiceRegStringValue
0x1800b0ef4  mov     rbp, rax
0x1800b0ef7  test    rax, rax
0x1800b0efa  jnz     short loc_1800B0F01
0x1800b0efc  lea     ebx, [rax+1]
0x1800b0eff  jmp     short loc_1800B0F38
0x1800b0f01  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b0f05  inc     rsi
0x1800b0f08  cmp     [rax+rsi*2], r15w
0x1800b0f0d  jnz     short loc_1800B0F05
0x1800b0f0f  mov     ebx, 1
0x1800b0f14  cmp     rsi, 6
0x1800b0f18  jnz     short loc_1800B0F3C
0x1800b0f1a  mov     r9d, esi; cchCount2
0x1800b0f1d  mov     [rsp+2D8h+bIgnoreCase], ebx; bIgnoreCase
0x1800b0f21  lea     r8, aFilter; "filter"
0x1800b0f28  mov     edx, esi; cchCount1
0x1800b0f2a  mov     rcx, rbp; lpString1
0x1800b0f2d  call    cs:__imp_CompareStringOrdinal
0x1800b0f33  cmp     eax, 2
0x1800b0f36  jnz     short loc_1800B0F3C
0x1800b0f38  mov     edi, ebx
0x1800b0f3a  jmp     short loc_1800B0F68
0x1800b0f3c  mov     edi, r15d
0x1800b0f3f  cmp     rsi, 8
0x1800b0f43  jb      short loc_1800B0F68
0x1800b0f45  mov     r9d, 8; cchCount2
0x1800b0f4b  mov     [rsp+2D8h+bIgnoreCase], ebx; bIgnoreCase
0x1800b0f4f  mov     edx, r9d; cchCount1
0x1800b0f52  lea     r8, aFsfilter; "FsFilter"
0x1800b0f59  mov     rcx, rbp; lpString1
0x1800b0f5c  call    cs:__imp_CompareStringOrdinal
0x1800b0f62  cmp     eax, 2
0x1800b0f65  cmovz   edi, ebx
0x1800b0f68  mov     rsi, [r14+10h]
0x1800b0f6c  test    edi, edi
0x1800b0f6e  jz      loc_1800B1086
0x1800b0f74  mov     edi, 122h
0x1800b0f79  mov     [rsp+2D8h+phkResult], r15
0x1800b0f7e  mov     edx, edi; unsigned __int64
0x1800b0f80  mov     dword ptr [rsp+2D8h+Data], 4
0x1800b0f88  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services"
0x1800b0f8f  lea     rcx, [rsp+2D8h+SubKey]; unsigned __int16 *
0x1800b0f94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b0f99  lea     r8, SubBlock; "\\"
0x1800b0fa0  mov     edx, edi; unsigned __int64
0x1800b0fa2  lea     rcx, [rsp+2D8h+SubKey]; unsigned __int16 *
0x1800b0fa7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b0fac  mov     r8, rsi; unsigned __int16 *
0x1800b0faf  lea     rcx, [rsp+2D8h+SubKey]; unsigned __int16 *
0x1800b0fb4  mov     edx, edi; unsigned __int64
0x1800b0fb6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b0fbb  lea     rax, [rsp+2D8h+phkResult]
0x1800b0fc0  mov     r9d, 2; samDesired
0x1800b0fc6  xor     r8d, r8d; ulOptions
0x1800b0fc9  mov     qword ptr [rsp+2D8h+bIgnoreCase], rax; phkResult
0x1800b0fce  lea     rdx, [rsp+2D8h+SubKey]; lpSubKey
0x1800b0fd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b0fda  call    cs:__imp_RegOpenKeyExW
0x1800b0fe0  test    eax, eax
0x1800b0fe2  jz      short loc_1800B1011
0x1800b0fe4  mov     [rsp+2D8h+cbData], eax
0x1800b0fe8  lea     r9, aFailedToOpenKe_3; "Failed to open key to disable Driver: '"...
0x1800b0fef  mov     rax, [r14+10h]
0x1800b0ff3  lea     rdx, aUddpdisableuns; "UddpDisableUnsignedBootDriver"
0x1800b0ffa  mov     qword ptr [rsp+2D8h+bIgnoreCase], rax
0x1800b0fff  mov     r8d, 0A6Ch
0x1800b1005  mov     ecx, ebx
0x1800b1007  call    AslLogCallPrintf
0x1800b100c  jmp     loc_1800B10A9
0x1800b1011  mov     rcx, [rsp+2D8h+phkResult]; hKey
0x1800b1016  lea     rax, [rsp+2D8h+Data]
0x1800b101b  mov     [rsp+2D8h+cbData], 4; cbData
0x1800b1023  lea     rdx, aStart; "Start"
0x1800b102a  mov     r9d, 4; dwType
0x1800b1030  mov     qword ptr [rsp+2D8h+bIgnoreCase], rax; lpData
0x1800b1035  xor     r8d, r8d; Reserved
0x1800b1038  call    cs:__imp_RegSetValueExW
0x1800b103e  mov     rcx, [rsp+2D8h+phkResult]; hKey
0x1800b1043  mov     edi, eax
0x1800b1045  call    cs:__imp_RegCloseKey
0x1800b104b  mov     rcx, [r14+10h]
0x1800b104f  lea     rdx, aUddpdisableuns; "UddpDisableUnsignedBootDriver"
0x1800b1056  test    edi, edi
0x1800b1058  jz      short loc_1800B1072
0x1800b105a  mov     [rsp+2D8h+cbData], edi
0x1800b105e  lea     r9, aFailedToSetVal_0; "Failed to set value to disable Driver: "...
0x1800b1065  mov     qword ptr [rsp+2D8h+bIgnoreCase], rcx
0x1800b106a  mov     r8d, 0A7Bh
0x1800b1070  jmp     short loc_1800B1005
0x1800b1072  mov     qword ptr [rsp+2D8h+bIgnoreCase], rcx
0x1800b1077  lea     r9, aDisabledDriver; "Disabled Driver: '%ls'"
0x1800b107e  mov     r8d, 0A7Fh
0x1800b1084  jmp     short loc_1800B109F
0x1800b1086  mov     qword ptr [rsp+2D8h+bIgnoreCase], rsi
0x1800b108b  lea     r9, aNotAFilterDriv; "Not a Filter Driver: '%ls'"
0x1800b1092  mov     r8d, 0A81h
0x1800b1098  lea     rdx, aUddpdisableuns; "UddpDisableUnsignedBootDriver"
0x1800b109f  mov     ecx, 3
0x1800b10a4  call    AslLogCallPrintf
0x1800b10a9  mov     rcx, gs:60h
0x1800b10b2  mov     r8, rbp; P
0x1800b10b5  xor     edx, edx; Flags
0x1800b10b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800b10bb  call    cs:__imp_RtlFreeHeap
0x1800b10c1  mov     rcx, [rsp+2D8h+var_48]
0x1800b10c9  xor     rcx, rsp; StackCookie
0x1800b10cc  call    __security_check_cookie
0x1800b10d1  add     rsp, 2A8h
0x1800b10d8  pop     r15
0x1800b10da  pop     r14
0x1800b10dc  pop     rdi
0x1800b10dd  pop     rsi
0x1800b10de  pop     rbp
0x1800b10df  pop     rbx
0x1800b10e0  retn
```
