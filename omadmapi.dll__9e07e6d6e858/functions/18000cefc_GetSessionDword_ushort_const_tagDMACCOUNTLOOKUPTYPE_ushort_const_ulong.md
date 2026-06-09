# GetSessionDword(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort const *,ulong *)

- ea: `0x18000cefc`
- end: `0x18000d0a7`
- name: `?GetSessionDword@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@0PEAK@Z`
- size: `427`
- prototype: `int __high(const unsigned __int16 *, enum tagDMACCOUNTLOOKUPTYPE, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fa20`

## callees

- `0x18000cefc`
- `0x18000f47c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d023`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d023`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000cfba`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000cfba`
- `DMCmnUtils!BigStrcat` at `0x18000cfe9`
- `DMCmnUtils!BigStrcat` at `0x18000cfe9`
- `DMCmnUtils!CopyString` at `0x18000cf91`
- `DMCmnUtils!CopyString` at `0x18000cf91`

## pseudocode

```c
__int64 __fastcall GetSessionDword(__int16 *a1, int a2, __int64 a3, BYTE *a4)
{
  int AccountIDFromLookupID; // ebx
  WCHAR *v6; // rdi
  HLOCAL v8; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v10; // rdx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v17; // [rsp+74h] [rbp+34h]

  v17 = HIDWORD(a3);
  hKey = 0;
  Type = 0;
  cbData = 4;
  hMem = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, (unsigned __int16 **)&hMem);
LABEL_12:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_3;
    goto LABEL_13;
  }
  if ( a2 != 1 )
  {
LABEL_2:
    AccountIDFromLookupID = -2147024809;
LABEL_3:
    v6 = 0;
    goto LABEL_4;
  }
  AccountIDFromLookupID = CopyString((const unsigned __int16 *)a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_12;
LABEL_13:
  v8 = hMem;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v10 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v10 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v6 = BigStrcat(3u, v10, L"\\", v8);
  if ( v6 )
  {
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20119u, &hKey);
    AccountIDFromLookupID = v11;
    if ( v11 > 0 )
      AccountIDFromLookupID = (unsigned __int16)v11 | 0x80070000;
    if ( AccountIDFromLookupID >= 0 )
    {
      v12 = RegQueryValueExW(hKey, L"NextSessionId", 0, &Type, a4, &cbData);
      if ( v12 )
      {
        if ( v12 > 0 )
          AccountIDFromLookupID = (unsigned __int16)v12 | 0x80070000;
        else
          AccountIDFromLookupID = v12;
      }
      else if ( Type != 4 || cbData != 4 )
      {
        AccountIDFromLookupID = -2147418113;
      }
    }
  }
  else
  {
    AccountIDFromLookupID = -2147024882;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v6);
  LocalFree(hMem);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x18000cefc  mov     [rsp-18h+arg_8], rbx
0x18000cf01  mov     qword ptr [rsp-18h+Type], r8
0x18000cf06  push    rbp
0x18000cf07  push    rsi
0x18000cf08  push    rdi
0x18000cf09  mov     rbp, rsp
0x18000cf0c  sub     rsp, 40h
0x18000cf10  mov     [rbp+hKey], 0
0x18000cf18  mov     rsi, r9
0x18000cf1b  mov     [rbp+Type], 0
0x18000cf22  mov     [rbp+cbData], 4
0x18000cf29  mov     [rbp+hMem], 0
0x18000cf31  test    rcx, rcx
0x18000cf34  jnz     short loc_18000CF81
0x18000cf36  mov     ebx, 80070057h
0x18000cf3b  xor     edi, edi
0x18000cf3d  mov     rcx, [rbp+hKey]; hKey
0x18000cf41  test    rcx, rcx
0x18000cf44  jz      short loc_18000CF52
0x18000cf46  call    cs:__imp_RegCloseKey
0x18000cf4d  nop     dword ptr [rax+rax+00h]
0x18000cf52  mov     rcx, rdi; hMem
0x18000cf55  call    cs:__imp_LocalFree
0x18000cf5c  nop     dword ptr [rax+rax+00h]
0x18000cf61  mov     rcx, [rbp+hMem]; hMem
0x18000cf65  call    cs:__imp_LocalFree
0x18000cf6c  nop     dword ptr [rax+rax+00h]
0x18000cf71  mov     eax, ebx
0x18000cf73  mov     rbx, [rsp+40h+arg_8]
0x18000cf78  add     rsp, 40h
0x18000cf7c  pop     rdi
0x18000cf7d  pop     rsi
0x18000cf7e  pop     rbp
0x18000cf7f  retn
0x18000cf81  test    edx, edx
0x18000cf83  jz      short loc_18000CFA5
0x18000cf85  cmp     edx, 1
0x18000cf88  jnz     short loc_18000CF36
0x18000cf8a  lea     r8, [rbp+hMem]
0x18000cf8e  or      edx, 0FFFFFFFFh
0x18000cf91  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000cf98  nop     dword ptr [rax+rax+00h]
0x18000cf9d  mov     ebx, eax
0x18000cf9f  test    eax, eax
0x18000cfa1  js      short loc_18000CFB2
0x18000cfa3  jmp     short loc_18000CFB6
0x18000cfa5  lea     r8, [rbp+hMem]
0x18000cfa9  xor     edx, edx
0x18000cfab  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x18000cfb0  mov     ebx, eax
0x18000cfb2  test    ebx, ebx
0x18000cfb4  js      short loc_18000CF3B
0x18000cfb6  mov     rbx, [rbp+hMem]
0x18000cfba  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000cfc1  nop     dword ptr [rax+rax+00h]
0x18000cfc6  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18000cfcd  mov     r9, rbx
0x18000cfd0  test    al, al
0x18000cfd2  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18000cfd9  lea     r8, asc_1800273F4; "\\"
0x18000cfe0  cmovz   rdx, rcx
0x18000cfe4  mov     ecx, 3
0x18000cfe9  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18000cff0  nop     dword ptr [rax+rax+00h]
0x18000cff5  mov     rdi, rax
0x18000cff8  test    rax, rax
0x18000cffb  jnz     short loc_18000D007
0x18000cffd  mov     ebx, 8007000Eh
0x18000d002  jmp     loc_18000CF3D
0x18000d007  lea     rax, [rbp+hKey]
0x18000d00b  mov     r9d, 20119h; samDesired
0x18000d011  xor     r8d, r8d; ulOptions
0x18000d014  mov     [rsp+40h+phkResult], rax; phkResult
0x18000d019  mov     rdx, rdi; lpSubKey
0x18000d01c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d023  call    cs:__imp_RegOpenKeyExW
0x18000d02a  nop     dword ptr [rax+rax+00h]
0x18000d02f  mov     ebx, eax
0x18000d031  test    eax, eax
0x18000d033  jle     short loc_18000D03E
0x18000d035  movzx   ebx, ax
0x18000d038  or      ebx, 80070000h
0x18000d03e  test    ebx, ebx
0x18000d040  js      loc_18000CF3D
0x18000d046  mov     rcx, [rbp+hKey]; hKey
0x18000d04a  lea     rax, [rbp+cbData]
0x18000d04e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000d053  lea     r9, [rbp+Type]; lpType
0x18000d057  xor     r8d, r8d; lpReserved
0x18000d05a  mov     [rsp+40h+phkResult], rsi; lpData
0x18000d05f  lea     rdx, ValueName; "NextSessionId"
0x18000d066  call    cs:__imp_RegQueryValueExW
0x18000d06d  nop     dword ptr [rax+rax+00h]
0x18000d072  test    eax, eax
0x18000d074  jz      short loc_18000D08D
0x18000d076  jg      short loc_18000D07F
0x18000d078  mov     ebx, eax
0x18000d07a  jmp     loc_18000CF3D
0x18000d07f  movzx   ebx, ax
0x18000d082  or      ebx, 80070000h
0x18000d088  jmp     loc_18000CF3D
0x18000d08d  cmp     [rbp+Type], 4
0x18000d091  jnz     short loc_18000D09D
0x18000d093  cmp     [rbp+cbData], 4
0x18000d097  jz      loc_18000CF3D
0x18000d09d  mov     ebx, 8000FFFFh
0x18000d0a2  jmp     loc_18000CF3D
```
