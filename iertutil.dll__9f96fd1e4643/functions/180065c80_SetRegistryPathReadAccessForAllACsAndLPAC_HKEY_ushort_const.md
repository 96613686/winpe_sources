# SetRegistryPathReadAccessForAllACsAndLPAC(HKEY__ *,ushort const *)

- ea: `0x180065c80`
- end: `0x180065d6b`
- name: `?SetRegistryPathReadAccessForAllACsAndLPAC@@YAJPEAUHKEY__@@PEBG@Z`
- size: `235`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180065694`
- `0x180065938`
- `0x180065c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065d3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065d3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065ca7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065ca7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d45`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180065d31`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180065d31`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180065cca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180065cca`

## pseudocode

```c
__int64 __fastcall SetRegistryPathReadAccessForAllACsAndLPAC(HKEY a1, const unsigned __int16 *a2)
{
  int LastError; // ebx
  bool v3; // cc
  bool phkResult; // [rsp+20h] [rbp-20h]
  bool phkResulta; // [rsp+20h] [rbp-20h]
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF
  PSID pSid; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  LastError = RegOpenKeyExW(a1, a2, 0, 0x60000u, &hKey);
  if ( LastError )
  {
    v3 = LastError < 0;
LABEL_11:
    if ( !v3 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  Sid = 0;
  if ( ConvertStringSidToSidW(
         L"S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681",
         &Sid)
    || (LastError = GetLastError()) == 0 )
  {
    LastError = SetHandleAccessWithInheritance(hKey, SE_REGISTRY_KEY, Sid, 0x20019u, phkResult);
    if ( !LastError )
    {
      pSid = 0;
      LastError = CreateAllApplicationPackagesSID(&pSid);
      if ( !LastError )
      {
        LastError = SetHandleAccessWithInheritance(hKey, SE_REGISTRY_KEY, pSid, 0x20019u, phkResulta);
        FreeSid(pSid);
      }
    }
    LocalFree(Sid);
  }
  RegCloseKey(hKey);
  v3 = LastError <= 0;
  if ( LastError )
    goto LABEL_11;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180065c80  mov     [rsp-8+arg_0], rbx
0x180065c85  push    rbp
0x180065c86  mov     rbp, rsp
0x180065c89  sub     rsp, 40h
0x180065c8d  lea     rax, [rbp+hKey]
0x180065c91  mov     [rbp+hKey], 0
0x180065c99  mov     r9d, 60000h; samDesired
0x180065c9f  mov     qword ptr [rsp+40h+phkResult], rax; bool
0x180065ca4  xor     r8d, r8d; ulOptions
0x180065ca7  call    cs:__imp_RegOpenKeyExW
0x180065cad  mov     ebx, eax
0x180065caf  test    eax, eax
0x180065cb1  jnz     loc_180065D51
0x180065cb7  lea     rdx, [rbp+Sid]; Sid
0x180065cbb  mov     [rbp+Sid], 0
0x180065cc3  lea     rcx, aS1153102410653; "S-1-15-3-1024-1065365936-1281604716-351"...
0x180065cca  call    cs:__imp_ConvertStringSidToSidW
0x180065cd0  test    eax, eax
0x180065cd2  jnz     short loc_180065CE0
0x180065cd4  call    cs:__imp_GetLastError
0x180065cda  mov     ebx, eax
0x180065cdc  test    eax, eax
0x180065cde  jnz     short loc_180065D41
0x180065ce0  mov     r8, [rbp+Sid]; void *
0x180065ce4  mov     r9d, 20019h; unsigned int
0x180065cea  mov     rcx, [rbp+hKey]; handle
0x180065cee  mov     edx, 4; ObjectType
0x180065cf3  call    SetHandleAccessWithInheritance
0x180065cf8  mov     ebx, eax
0x180065cfa  test    eax, eax
0x180065cfc  jnz     short loc_180065D37
0x180065cfe  lea     rcx, [rbp+pSid]; pSid
0x180065d02  mov     [rbp+pSid], 0
0x180065d0a  call    ?CreateAllApplicationPackagesSID@@YAKPEAPEAX@Z; CreateAllApplicationPackagesSID(void * *)
0x180065d0f  mov     ebx, eax
0x180065d11  test    eax, eax
0x180065d13  jnz     short loc_180065D37
0x180065d15  mov     r8, [rbp+pSid]; void *
0x180065d19  lea     edx, [rax+4]; ObjectType
0x180065d1c  mov     rcx, [rbp+hKey]; handle
0x180065d20  mov     r9d, 20019h; unsigned int
0x180065d26  call    SetHandleAccessWithInheritance
0x180065d2b  mov     rcx, [rbp+pSid]; pSid
0x180065d2f  mov     ebx, eax
0x180065d31  call    cs:__imp_FreeSid
0x180065d37  mov     rcx, [rbp+Sid]; hMem
0x180065d3b  call    cs:__imp_LocalFree
0x180065d41  mov     rcx, [rbp+hKey]; hKey
0x180065d45  call    cs:__imp_RegCloseKey
0x180065d4b  test    ebx, ebx
0x180065d4d  jnz     short loc_180065D53
0x180065d4f  jmp     short loc_180065D5E
0x180065d51  test    ebx, ebx
0x180065d53  jle     short loc_180065D5E
0x180065d55  movzx   ebx, bx
0x180065d58  or      ebx, 80070000h
0x180065d5e  mov     eax, ebx
0x180065d60  mov     rbx, [rsp+40h+arg_0]
0x180065d65  add     rsp, 40h
0x180065d69  pop     rbp
0x180065d6a  retn
```
