# _GetAppContainerFolderPath(void *,ushort * *)

- ea: `0x18000a914`
- end: `0x18000aa3f`
- name: `?_GetAppContainerFolderPath@@YAJPEAXPEAPEAG@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x180001ab8`
- `0x180005b60`
- `0x18000a914`
- `0x18000cf24`
- `0x18000dc34`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa0d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a95d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a95d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a97a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a97a`

## string_xrefs

- `0x18000a9d5`: `minio\profapi\path.cpp`
- `0x18000a9f0`: `minio\profapi\path.cpp`
- `0x18000aa1f`: `minio\profapi\path.cpp`

## pseudocode

```c
__int64 __fastcall _GetAppContainerFolderPath(void *a1, unsigned __int16 **a2)
{
  const char *v4; // r9
  const char *v5; // r9
  int AppContainerPath; // eax
  unsigned int LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-88h]
  LPWSTR StringSid; // [rsp+30h] [rbp-78h] BYREF
  DWORD v11; // [rsp+38h] [rbp-70h] BYREF
  PSID Sid[10]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a2 = 0;
  v11 = 76;
  if ( !GetTokenInformation(a1, TokenAppContainerSid, Sid, 0x4Cu, &v11) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xCB,
             (unsigned int)"minio\\profapi\\path.cpp",
             v4);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCF,
                  (unsigned int)"minio\\profapi\\path.cpp",
                  v5);
    if ( StringSid )
      LocalFree(StringSid);
    return LastError;
  }
  AppContainerPath = _GetAppContainerPath(a1, StringSid, a2);
  LastError = AppContainerPath;
  if ( AppContainerPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)(unsigned int)AppContainerPath,
      ReturnLength);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>((void **)&StringSid);
    return LastError;
  }
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x18000a914  mov     r11, rsp
0x18000a917  mov     [r11+18h], rbx
0x18000a91b  push    rdi
0x18000a91c  sub     rsp, 0A0h
0x18000a923  mov     rax, cs:__security_cookie
0x18000a92a  xor     rax, rsp
0x18000a92d  mov     [rsp+0A8h+var_18], rax
0x18000a935  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18000a93b  mov     qword ptr [rdx], 0
0x18000a942  mov     rdi, rdx
0x18000a945  mov     [r11-70h], r9d
0x18000a949  lea     rax, [r11-70h]
0x18000a94d  mov     rbx, rcx
0x18000a950  lea     r8, [r11-68h]; TokenInformation
0x18000a954  mov     qword ptr [rsp+0A8h+ReturnLength], rax; int
0x18000a959  lea     edx, [r9-2Dh]; TokenInformationClass
0x18000a95d  call    cs:__imp_GetTokenInformation
0x18000a963  test    eax, eax
0x18000a965  jz      short loc_18000A9CD
0x18000a967  mov     rcx, [rsp+0A8h+Sid]; Sid
0x18000a96c  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x18000a971  mov     [rsp+0A8h+StringSid], 0
0x18000a97a  call    cs:__imp_ConvertSidToStringSidW
0x18000a980  test    eax, eax
0x18000a982  jz      short loc_18000A9E8
0x18000a984  mov     rdx, [rsp+0A8h+StringSid]; unsigned __int16 *
0x18000a989  mov     r8, rdi; unsigned __int16 **
0x18000a98c  mov     rcx, rbx; void *
0x18000a98f  call    ?_GetAppContainerPath@@YAJPEAXPEBGPEAPEAG@Z; _GetAppContainerPath(void *,ushort const *,ushort * *)
0x18000a994  mov     ebx, eax
0x18000a996  test    eax, eax
0x18000a998  js      short loc_18000AA17
0x18000a99a  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x18000a99f  test    rcx, rcx
0x18000a9a2  jz      short loc_18000A9AA
0x18000a9a4  call    cs:__imp_LocalFree
0x18000a9aa  xor     eax, eax
0x18000a9ac  mov     rcx, [rsp+0A8h+var_18]
0x18000a9b4  xor     rcx, rsp; StackCookie
0x18000a9b7  call    __security_check_cookie
0x18000a9bc  mov     rbx, [rsp+0A8h+arg_10]
0x18000a9c4  add     rsp, 0A0h
0x18000a9cb  pop     rdi
0x18000a9cc  retn
0x18000a9cd  mov     rcx, [rsp+0A8h]; this
0x18000a9d5  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x18000a9dc  mov     edx, 0CBh; void *
0x18000a9e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a9e6  jmp     short loc_18000A9AC
0x18000a9e8  mov     rcx, [rsp+0A8h]; this
0x18000a9f0  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x18000a9f7  mov     edx, 0CFh; void *
0x18000a9fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000aa01  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x18000aa06  mov     ebx, eax
0x18000aa08  test    rcx, rcx
0x18000aa0b  jz      short loc_18000AA13
0x18000aa0d  call    cs:__imp_LocalFree
0x18000aa13  mov     eax, ebx
0x18000aa15  jmp     short loc_18000A9AC
0x18000aa17  mov     rcx, [rsp+0A8h]; this
0x18000aa1f  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x18000aa26  mov     r9d, ebx; char *
0x18000aa29  mov     edx, 0D0h; void *
0x18000aa2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa33  lea     rcx, [rsp+0A8h+StringSid]
0x18000aa38  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18000aa3d  jmp     short loc_18000AA13
```
