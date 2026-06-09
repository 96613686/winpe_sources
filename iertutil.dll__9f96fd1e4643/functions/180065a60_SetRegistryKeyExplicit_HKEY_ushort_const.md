# SetRegistryKeyExplicit(HKEY__ *,ushort const *)

- ea: `0x180065a60`
- end: `0x180065bbb`
- name: `?SetRegistryKeyExplicit@@YAJPEAUHKEY__@@PEBG@Z`
- size: `347`
- prototype: `__int64 __fastcall(HKEY Handle, LPCWSTR StringSecurityDescriptor)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180030a48`
- `0x1800321a0`
- `0x1800329b0`
- `0x180065a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180065aa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180065aa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065b5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065b82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065b8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065b5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065b82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065b8c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180065af2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180065af2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180065a8e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180065a8e`

## pseudocode

```c
__int64 __fastcall SetRegistryKeyExplicit(HKEY Handle, LPCWSTR StringSecurityDescriptor)
{
  DWORD CurrentProcessId; // eax
  int ProcessSid; // eax
  signed int v5; // ebx
  int SIDAcl; // eax
  signed int LastError; // eax
  signed int v8; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL v11; // [rsp+38h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-8h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+78h] [rbp+28h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    v11 = 0;
    CurrentProcessId = GetCurrentProcessId();
    ProcessSid = GetProcessSid(CurrentProcessId, &v11);
    v5 = ProcessSid;
    if ( ProcessSid > 0 )
      v5 = (unsigned __int16)ProcessSid | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_17;
    bDaclPresent = 0;
    bDaclDefaulted = 0;
    pDacl = 0;
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_16;
    }
    if ( !bDaclPresent || !pDacl )
      goto LABEL_13;
    hMem = 0;
    SIDAcl = CreateSIDAcl(pDacl, (struct _ACL **)&hMem, v11, 0xF003Fu, 3u);
    v5 = SIDAcl;
    if ( SIDAcl > 0 )
      v5 = (unsigned __int16)SIDAcl | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_16;
    if ( hMem )
    {
      v5 = SetDacl(Handle, (struct _ACL *)hMem);
      LocalFree(hMem);
    }
    else
    {
LABEL_13:
      v5 = -2147467261;
    }
LABEL_16:
    LocalFree(v11);
LABEL_17:
    LocalFree(SecurityDescriptor);
    return (unsigned int)v5;
  }
  v8 = GetLastError();
  v5 = v8;
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180065a60  mov     [rsp-8+arg_0], rbx
0x180065a65  mov     [rsp-8+arg_8], rsi
0x180065a6a  push    rbp
0x180065a6b  mov     rbp, rsp
0x180065a6e  sub     rsp, 50h
0x180065a72  mov     rax, rdx
0x180065a75  mov     [rbp+SecurityDescriptor], 0
0x180065a7d  xor     r9d, r9d; SecurityDescriptorSize
0x180065a80  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180065a84  mov     rsi, rcx
0x180065a87  mov     rcx, rax; StringSecurityDescriptor
0x180065a8a  lea     edx, [r9+1]; StringSDRevision
0x180065a8e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180065a94  test    eax, eax
0x180065a96  jz      loc_180065B94
0x180065a9c  mov     [rbp+var_18], 0
0x180065aa4  call    cs:__imp_GetCurrentProcessId
0x180065aaa  mov     ecx, eax; dwProcessId
0x180065aac  lea     rdx, [rbp+var_18]; void **
0x180065ab0  call    ?GetProcessSid@@YAKKPEAPEAX@Z; GetProcessSid(ulong,void * *)
0x180065ab5  mov     ebx, eax
0x180065ab7  test    eax, eax
0x180065ab9  jle     short loc_180065AC4
0x180065abb  movzx   ebx, ax
0x180065abe  or      ebx, 80070000h
0x180065ac4  test    ebx, ebx
0x180065ac6  js      loc_180065B88
0x180065acc  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180065ad0  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180065ad4  lea     r8, [rbp+pDacl]; pDacl
0x180065ad8  mov     [rbp+bDaclPresent], 0
0x180065adf  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180065ae3  mov     [rbp+bDaclDefaulted], 0
0x180065aea  mov     [rbp+pDacl], 0
0x180065af2  call    cs:__imp_GetSecurityDescriptorDacl
0x180065af8  test    eax, eax
0x180065afa  jz      short loc_180065B69
0x180065afc  cmp     [rbp+bDaclPresent], 0
0x180065b00  jz      short loc_180065B62
0x180065b02  mov     rcx, [rbp+pDacl]; pAcl
0x180065b06  test    rcx, rcx
0x180065b09  jz      short loc_180065B62
0x180065b0b  mov     r8, [rbp+var_18]; void *
0x180065b0f  lea     rdx, [rbp+hMem]; struct _ACL **
0x180065b13  mov     r9d, 0F003Fh; unsigned int
0x180065b19  mov     [rbp+hMem], 0
0x180065b21  mov     [rsp+50h+var_30], 3; unsigned int
0x180065b29  call    ?CreateSIDAcl@@YAKPEAU_ACL@@PEAPEAU1@PEAXKK@Z; CreateSIDAcl(_ACL *,_ACL * *,void *,ulong,ulong)
0x180065b2e  mov     ebx, eax
0x180065b30  test    eax, eax
0x180065b32  jle     short loc_180065B3D
0x180065b34  movzx   ebx, ax
0x180065b37  or      ebx, 80070000h
0x180065b3d  test    ebx, ebx
0x180065b3f  js      short loc_180065B7E
0x180065b41  cmp     [rbp+hMem], 0
0x180065b46  jz      short loc_180065B62
0x180065b48  mov     rdx, [rbp+hMem]; Source
0x180065b4c  mov     rcx, rsi; Handle
0x180065b4f  call    ?SetDacl@@YAJPEAXPEAU_ACL@@@Z; SetDacl(void *,_ACL *)
0x180065b54  mov     rcx, [rbp+hMem]; hMem
0x180065b58  mov     ebx, eax
0x180065b5a  call    cs:__imp_LocalFree
0x180065b60  jmp     short loc_180065B7E
0x180065b62  mov     ebx, 80004003h
0x180065b67  jmp     short loc_180065B7E
0x180065b69  call    cs:__imp_GetLastError
0x180065b6f  mov     ebx, eax
0x180065b71  test    eax, eax
0x180065b73  jle     short loc_180065B7E
0x180065b75  movzx   ebx, ax
0x180065b78  or      ebx, 80070000h
0x180065b7e  mov     rcx, [rbp+var_18]; hMem
0x180065b82  call    cs:__imp_LocalFree
0x180065b88  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180065b8c  call    cs:__imp_LocalFree
0x180065b92  jmp     short loc_180065BA9
0x180065b94  call    cs:__imp_GetLastError
0x180065b9a  mov     ebx, eax
0x180065b9c  test    eax, eax
0x180065b9e  jle     short loc_180065BA9
0x180065ba0  movzx   ebx, ax
0x180065ba3  or      ebx, 80070000h
0x180065ba9  mov     rsi, [rsp+50h+arg_8]
0x180065bae  mov     eax, ebx
0x180065bb0  mov     rbx, [rsp+50h+arg_0]
0x180065bb5  add     rsp, 50h
0x180065bb9  pop     rbp
0x180065bba  retn
```
