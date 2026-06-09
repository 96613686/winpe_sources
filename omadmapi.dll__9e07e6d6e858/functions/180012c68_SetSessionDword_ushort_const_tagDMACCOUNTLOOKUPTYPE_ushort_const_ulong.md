# SetSessionDword(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort const *,ulong)

- ea: `0x180012c68`
- end: `0x180012dfb`
- name: `?SetSessionDword@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@0K@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fa20`

## callees

- `0x18000f47c`
- `0x180012c68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012dd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012dd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012de1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012d98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012d98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012d66`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012d66`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012cdd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012cdd`
- `DMCmnUtils!BigStrcat` at `0x180012d0c`
- `DMCmnUtils!BigStrcat` at `0x180012d0c`
- `DMCmnUtils!CopyString` at `0x180012cae`
- `DMCmnUtils!CopyString` at `0x180012cae`

## pseudocode

```c
__int64 __fastcall SetSessionDword(const unsigned __int16 *a1, int a2, __int64 a3, int a4)
{
  WCHAR *v4; // rbx
  signed int AccountIDFromLookupID; // edi
  HLOCAL v6; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v8; // rdx
  LSTATUS v9; // eax
  bool v10; // cc
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  v4 = 0;
  hKey = 0;
  hMem = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, &hMem);
    goto LABEL_8;
  }
  if ( a2 != 1 )
  {
LABEL_2:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_18;
  }
  AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( AccountIDFromLookupID < 0 )
  {
LABEL_8:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_18;
  }
  v6 = hMem;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v8 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v4 = BigStrcat(3u, v8, L"\\", v6);
  if ( v4 )
  {
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, 0, 0x2011Fu, 0, &hKey, 0);
    v10 = v9 <= 0;
    if ( v9 || (v9 = RegSetValueExW(hKey, L"NextSessionId", 0, 4u, (const BYTE *)&Data, 4u), v10 = v9 <= 0, v9) )
    {
      if ( v10 )
        AccountIDFromLookupID = v9;
      else
        AccountIDFromLookupID = (unsigned __int16)v9 | 0x80070000;
    }
  }
  else
  {
    AccountIDFromLookupID = -2147024882;
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v4);
  LocalFree(hMem);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x180012c68  mov     rax, rsp
0x180012c6b  mov     [rax+10h], rbx
0x180012c6f  mov     [rax+20h], r9d
0x180012c73  mov     [rax+18h], r8
0x180012c77  push    rdi
0x180012c78  sub     rsp, 50h
0x180012c7c  xor     ebx, ebx
0x180012c7e  mov     qword ptr [rax+8], 0
0x180012c86  mov     qword ptr [rax+18h], 0
0x180012c8e  test    rcx, rcx
0x180012c91  jnz     short loc_180012C9D
0x180012c93  mov     edi, 80070057h
0x180012c98  jmp     loc_180012DB7
0x180012c9d  test    edx, edx
0x180012c9f  jz      short loc_180012CC2
0x180012ca1  cmp     edx, 1
0x180012ca4  jnz     short loc_180012C93
0x180012ca6  lea     r8, [rsp+58h+hMem]
0x180012cab  or      edx, 0FFFFFFFFh
0x180012cae  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180012cb5  nop     dword ptr [rax+rax+00h]
0x180012cba  mov     edi, eax
0x180012cbc  test    eax, eax
0x180012cbe  js      short loc_180012CD0
0x180012cc0  jmp     short loc_180012CD8
0x180012cc2  lea     r8, [rsp+58h+hMem]
0x180012cc7  xor     edx, edx
0x180012cc9  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x180012cce  mov     edi, eax
0x180012cd0  test    edi, edi
0x180012cd2  js      loc_180012DB7
0x180012cd8  mov     rbx, [rsp+58h+hMem]
0x180012cdd  call    cs:__imp_RtlIsStateSeparationEnabled
0x180012ce4  nop     dword ptr [rax+rax+00h]
0x180012ce9  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x180012cf0  mov     r9, rbx
0x180012cf3  test    al, al
0x180012cf5  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180012cfc  lea     r8, asc_1800273F4; "\\"
0x180012d03  cmovz   rdx, rcx
0x180012d07  mov     ecx, 3
0x180012d0c  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x180012d13  nop     dword ptr [rax+rax+00h]
0x180012d18  mov     rbx, rax
0x180012d1b  test    rax, rax
0x180012d1e  jnz     short loc_180012D2A
0x180012d20  mov     edi, 8007000Eh
0x180012d25  jmp     loc_180012DB7
0x180012d2a  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180012d33  lea     rax, [rsp+58h+hKey]
0x180012d38  mov     [rsp+58h+phkResult], rax; phkResult
0x180012d3d  xor     r9d, r9d; lpClass
0x180012d40  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180012d49  xor     r8d, r8d; Reserved
0x180012d4c  mov     [rsp+58h+samDesired], 2011Fh; samDesired
0x180012d54  mov     rdx, rbx; lpSubKey
0x180012d57  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012d5e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180012d66  call    cs:__imp_RegCreateKeyExW
0x180012d6d  nop     dword ptr [rax+rax+00h]
0x180012d72  test    eax, eax
0x180012d74  jnz     short loc_180012DA8
0x180012d76  mov     rcx, [rsp+58h+hKey]; hKey
0x180012d7b  lea     r9d, [rax+4]; dwType
0x180012d7f  lea     rax, [rsp+58h+Data]
0x180012d84  mov     [rsp+58h+samDesired], r9d; cbData
0x180012d89  xor     r8d, r8d; Reserved
0x180012d8c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180012d91  lea     rdx, ValueName; "NextSessionId"
0x180012d98  call    cs:__imp_RegSetValueExW
0x180012d9f  nop     dword ptr [rax+rax+00h]
0x180012da4  test    eax, eax
0x180012da6  jz      short loc_180012DB7
0x180012da8  jg      short loc_180012DAE
0x180012daa  mov     edi, eax
0x180012dac  jmp     short loc_180012DB7
0x180012dae  movzx   edi, ax
0x180012db1  or      edi, 80070000h
0x180012db7  mov     rcx, [rsp+58h+hKey]; hKey
0x180012dbc  test    rcx, rcx
0x180012dbf  jz      short loc_180012DCD
0x180012dc1  call    cs:__imp_RegCloseKey
0x180012dc8  nop     dword ptr [rax+rax+00h]
0x180012dcd  mov     rcx, rbx; hMem
0x180012dd0  call    cs:__imp_LocalFree
0x180012dd7  nop     dword ptr [rax+rax+00h]
0x180012ddc  mov     rcx, [rsp+58h+hMem]; hMem
0x180012de1  call    cs:__imp_LocalFree
0x180012de8  nop     dword ptr [rax+rax+00h]
0x180012ded  mov     rbx, [rsp+58h+arg_8]
0x180012df2  mov     eax, edi
0x180012df4  add     rsp, 50h
0x180012df8  pop     rdi
0x180012df9  retn
```
