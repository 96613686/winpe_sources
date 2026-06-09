# CRemoveAdminProfileTask::RunTask(void)

- ea: `0x18003bd30`
- end: `0x18003bec7`
- name: `?RunTask@CRemoveAdminProfileTask@@UEAAJXZ`
- size: `407`
- prototype: `__int64 __fastcall(CRemoveAdminProfileTask *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x180018a04`
- `0x180026b68`
- `0x18003bd30`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003bd94`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003bde6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003bd94`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003bde6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003bdd6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003bdd6`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003bda5`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003bda5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003bdc2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003bdc2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003bdff`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003bdff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003be94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003be94`
- `USERENV!DeleteProfileW` at `0x18003be24`
- `USERENV!DeleteProfileW` at `0x18003be24`
- `samcli!NetUserModalsGet` at `0x18003bd75`
- `samcli!NetUserModalsGet` at `0x18003bd75`
- `netutils!NetApiBufferFree` at `0x18003bea7`
- `netutils!NetApiBufferFree` at `0x18003bea7`

## string_xrefs

- `0x18003be2e`: `Successfully removed Administrator profile`
- `0x18003be67`: `Failed to delete Admin profile %s with hr=0x%08X`

## pseudocode

```c
__int64 __fastcall CRemoveAdminProfileTask::RunTask(CRemoveAdminProfileTask *this)
{
  unsigned int v1; // ebx
  DWORD v2; // edi
  DWORD SidLengthRequired; // eax
  __int64 v4; // rcx
  unsigned int Error; // eax
  LPWSTR StringSid; // [rsp+20h] [rbp-39h] BYREF
  LPBYTE bufptr; // [rsp+28h] [rbp-31h] BYREF
  _BYTE pDestinationSid[80]; // [rsp+30h] [rbp-29h] BYREF

  v1 = -2147467259;
  UnattendLogW(0, L"Removing Administrator Profile");
  bufptr = 0;
  if ( !NetUserModalsGet(0, 2u, &bufptr) && bufptr )
  {
    v2 = *GetSidSubAuthorityCount(*((PSID *)bufptr + 1));
    SidLengthRequired = GetSidLengthRequired(v2 + 1);
    if ( SidLengthRequired <= 0x44 )
    {
      if ( CopySid(SidLengthRequired, pDestinationSid, *((PSID *)bufptr + 1))
        && (*GetSidSubAuthority(pDestinationSid, v2) = 500,
            *GetSidSubAuthorityCount(pDestinationSid) = v2 + 1,
            StringSid = 0,
            ConvertSidToStringSidW(pDestinationSid, &StringSid)) )
      {
        OOBEStartService(L"profsvc", 1);
        if ( DeleteProfileW(StringSid, 0, 0) )
        {
          UnattendLogW(0, L"Successfully removed Administrator profile");
          v1 = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          v1 = Error;
          if ( Error == -2147024894 )
          {
            v1 = 0;
            UnattendLogW(0, L"Admin profile %s was not found.", StringSid);
          }
          else
          {
            UnattendLogW(2, L"Failed to delete Admin profile %s with hr=0x%08X", StringSid, Error);
          }
        }
        if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v4, RemoveAdminProfile_Info, v1);
        LocalFree(StringSid);
      }
      else
      {
        v1 = ResultFromKnownLastError();
      }
    }
    NetApiBufferFree(bufptr);
  }
  return v1;
}

```

## disassembly

```asm
0x18003bd30  push    rbp
0x18003bd32  push    rbx
0x18003bd33  push    rsi
0x18003bd34  push    rdi
0x18003bd35  lea     rbp, [rsp-3Fh]
0x18003bd3a  sub     rsp, 98h
0x18003bd41  mov     rax, cs:__security_cookie
0x18003bd48  xor     rax, rsp
0x18003bd4b  mov     [rbp+57h+var_30], rax
0x18003bd4f  lea     rdx, aRemovingAdmini; "Removing Administrator Profile"
0x18003bd56  xor     ecx, ecx
0x18003bd58  mov     ebx, 80004005h
0x18003bd5d  call    UnattendLogW
0x18003bd62  lea     r8, [rbp+57h+bufptr]; bufptr
0x18003bd66  mov     [rbp+57h+bufptr], 0
0x18003bd6e  mov     edx, 2; level
0x18003bd73  xor     ecx, ecx; servername
0x18003bd75  call    cs:__imp_NetUserModalsGet
0x18003bd7b  test    eax, eax
0x18003bd7d  jnz     loc_18003BEAD
0x18003bd83  mov     rcx, [rbp+57h+bufptr]
0x18003bd87  test    rcx, rcx
0x18003bd8a  jz      loc_18003BEAD
0x18003bd90  mov     rcx, [rcx+8]; pSid
0x18003bd94  call    cs:__imp_GetSidSubAuthorityCount
0x18003bd9a  movzx   edi, byte ptr [rax]
0x18003bd9d  lea     eax, [rdi+1]
0x18003bda0  mov     cl, al; nSubAuthorityCount
0x18003bda2  mov     sil, al
0x18003bda5  call    cs:__imp_GetSidLengthRequired
0x18003bdab  cmp     eax, 44h ; 'D'
0x18003bdae  ja      loc_18003BEA3
0x18003bdb4  mov     r8, [rbp+57h+bufptr]
0x18003bdb8  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x18003bdbc  mov     ecx, eax; nDestinationSidLength
0x18003bdbe  mov     r8, [r8+8]; pSourceSid
0x18003bdc2  call    cs:__imp_CopySid
0x18003bdc8  test    eax, eax
0x18003bdca  jz      loc_18003BE9C
0x18003bdd0  mov     edx, edi; nSubAuthority
0x18003bdd2  lea     rcx, [rbp+57h+pDestinationSid]; pSid
0x18003bdd6  call    cs:__imp_GetSidSubAuthority
0x18003bddc  lea     rcx, [rbp+57h+pDestinationSid]; pSid
0x18003bde0  mov     dword ptr [rax], 1F4h
0x18003bde6  call    cs:__imp_GetSidSubAuthorityCount
0x18003bdec  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18003bdf0  lea     rcx, [rbp+57h+pDestinationSid]; Sid
0x18003bdf4  mov     [rax], sil
0x18003bdf7  mov     [rbp+57h+StringSid], 0
0x18003bdff  call    cs:__imp_ConvertSidToStringSidW
0x18003be05  test    eax, eax
0x18003be07  jz      loc_18003BE9C
0x18003be0d  mov     dl, 1; bool
0x18003be0f  lea     rcx, aProfsvc; "profsvc"
0x18003be16  call    ?OOBEStartService@@YAJPEBG_N@Z; OOBEStartService(ushort const *,bool)
0x18003be1b  mov     rcx, [rbp+57h+StringSid]; lpSidString
0x18003be1f  xor     r8d, r8d; lpComputerName
0x18003be22  xor     edx, edx; lpProfilePath
0x18003be24  call    cs:__imp_DeleteProfileW
0x18003be2a  test    eax, eax
0x18003be2c  jz      short loc_18003BE40
0x18003be2e  lea     rdx, aSuccessfullyRe_0; "Successfully removed Administrator prof"...
0x18003be35  xor     ecx, ecx
0x18003be37  call    UnattendLogW
0x18003be3c  xor     ebx, ebx
0x18003be3e  jmp     short loc_18003BE78
0x18003be40  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003be45  mov     r8, [rbp+57h+StringSid]
0x18003be49  mov     ebx, eax
0x18003be4b  cmp     eax, 80070002h
0x18003be50  jnz     short loc_18003BE64
0x18003be52  xor     ebx, ebx
0x18003be54  lea     rdx, aAdminProfileSW; "Admin profile %s was not found."
0x18003be5b  xor     ecx, ecx
0x18003be5d  call    UnattendLogW
0x18003be62  jmp     short loc_18003BE78
0x18003be64  mov     r9d, eax
0x18003be67  lea     rdx, aFailedToDelete_1; "Failed to delete Admin profile %s with "...
0x18003be6e  mov     ecx, 2
0x18003be73  call    UnattendLogW
0x18003be78  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x18003be7f  jz      short loc_18003BE90
0x18003be81  mov     r8d, ebx
0x18003be84  lea     rdx, RemoveAdminProfile_Info
0x18003be8b  call    McTemplateU0q_EventWriteTransfer
0x18003be90  mov     rcx, [rbp+57h+StringSid]; hMem
0x18003be94  call    cs:__imp_LocalFree
0x18003be9a  jmp     short loc_18003BEA3
0x18003be9c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003bea1  mov     ebx, eax
0x18003bea3  mov     rcx, [rbp+57h+bufptr]; Buffer
0x18003bea7  call    cs:__imp_NetApiBufferFree
0x18003bead  mov     eax, ebx
0x18003beaf  mov     rcx, [rbp+57h+var_30]
0x18003beb3  xor     rcx, rsp; StackCookie
0x18003beb6  call    __security_check_cookie
0x18003bebb  add     rsp, 98h
0x18003bec2  pop     rdi
0x18003bec3  pop     rsi
0x18003bec4  pop     rbx
0x18003bec5  pop     rbp
0x18003bec6  retn
```
