# WriteSecurityQuestionData(ushort const *,ushort const *)

- ea: `0x180032884`
- end: `0x180032af5`
- name: `?WriteSecurityQuestionData@@YAJPEBG0@Z`
- size: `625`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031100`
- `0x180032270`

## callees

- `0x180008524`
- `0x180031f90`
- `0x180031fb0`
- `0x180031fd0`
- `0x180031ff0`
- `0x180032244`
- `0x180032884`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180032a19`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180032a19`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180032a27`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180032a27`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800329e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800329e8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800328ce`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800328ce`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180032906`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180032906`
- `ntdll!RtlInitUnicodeString` at `0x180032a84`
- `ntdll!RtlInitUnicodeString` at `0x180032a84`
- `SAMLIB!SamOpenDomain` at `0x1800329ae`
- `SAMLIB!SamOpenDomain` at `0x1800329ae`
- `SAMLIB!SamOpenUser` at `0x180032a41`
- `SAMLIB!SamOpenUser` at `0x180032a41`
- `SAMLIB!SamSetInformationUser` at `0x180032a97`
- `SAMLIB!SamSetInformationUser` at `0x180032a97`
- `SAMLIB!SamConnect` at `0x180032966`
- `SAMLIB!SamConnect` at `0x180032966`

## string_xrefs

- `0x1800328df`: `shell\oobe\machine\plugins\localuser\localusertasks.cpp`
- `0x180032917`: `shell\oobe\machine\plugins\localuser\localusertasks.cpp`
- `0x180032977`: `shell\oobe\machine\plugins\localuser\localusertasks.cpp`
- `0x1800329bf`: `shell\oobe\machine\plugins\localuser\localusertasks.cpp`
- `0x1800329f6`: `shell\oobe\machine\plugins\localuser\localusertasks.cpp`
- `0x180032a50`: `shell\oobe\machine\plugins\localuser\localusertasks.cpp`

## pseudocode

```c
__int64 __fastcall WriteSecurityQuestionData(LPCWSTR StringSid, PCWSTR SourceString)
{
  NTSTATUS v4; // eax
  unsigned int LastError; // ebx
  NTSTATUS v6; // eax
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  PSID v10; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-29h] BYREF
  PSID Sid; // [rsp+28h] [rbp-21h] BYREF
  __int64 v18; // [rsp+30h] [rbp-19h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+27h] BYREF
  __int64 v22; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  PVOID Buffer; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+7Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  PolicyHandle = 0;
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v4 >= 0 )
  {
    Buffer = 0;
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    if ( v6 >= 0 )
    {
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v25 = 0;
      v7 = SamConnect(0, &v25, 32, &ObjectAttributes);
      if ( v7 >= 0 )
      {
        v16 = 0;
        v8 = SamOpenDomain(v25, 0x2000000, *((_QWORD *)Buffer + 2), &v16);
        if ( v8 >= 0 )
        {
          Sid = 0;
          if ( ConvertStringSidToSidW(StringSid, &Sid) )
          {
            v10 = Sid;
            SidSubAuthorityCount = GetSidSubAuthorityCount(Sid);
            v12 = *GetSidSubAuthority(v10, (unsigned int)*SidSubAuthorityCount - 1);
            v18 = 0;
            v13 = SamOpenUser(v16, 0x2000000, v12, &v18);
            if ( v13 >= 0 )
            {
              DestinationString = 0;
              v22 = 0;
              RtlInitUnicodeString((PUNICODE_STRING)&DestinationString.Buffer, SourceString);
              v13 = SamSetInformationUser(v18, 30, &DestinationString);
              if ( v13 >= 0 )
              {
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
                wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(&Sid);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buffer);
                LastError = 0;
                goto LABEL_21;
              }
              v14 = 96;
            }
            else
            {
              v14 = 88;
            }
            LastError = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)v14,
                          (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localusertasks.cpp",
                          (const char *)(unsigned int)v13,
                          v16);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x4F,
                          (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localusertasks.cpp",
                          v9);
          }
          wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(&Sid);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x4C,
                        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localusertasks.cpp",
                        (const char *)(unsigned int)v8,
                        v16);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x44,
                      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localusertasks.cpp",
                      (const char *)(unsigned int)v7,
                      v16);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x3B,
                    (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localusertasks.cpp",
                    (const char *)(unsigned int)v6,
                    v16);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buffer);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x34,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localusertasks.cpp",
                  (const char *)(unsigned int)v4,
                  v16);
  }
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return LastError;
}

```

## disassembly

```asm
0x180032884  mov     [rsp-8+arg_0], rbx
0x180032889  push    rbp
0x18003288a  push    rsi
0x18003288b  push    rdi
0x18003288c  lea     rbp, [rsp-47h]
0x180032891  sub     rsp, 90h
0x180032898  mov     rdi, rdx
0x18003289b  mov     rbx, rcx
0x18003289e  xor     esi, esi
0x1800328a0  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800328a8  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rsi
0x1800328ac  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800328b0  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x1800328b4  xorps   xmm0, xmm0
0x1800328b7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800328bc  mov     [rbp+57h+PolicyHandle], rsi
0x1800328c0  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800328c4  lea     r8d, [rsi+1]; DesiredAccess
0x1800328c8  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800328cc  xor     ecx, ecx; SystemName
0x1800328ce  call    cs:__imp_LsaOpenPolicy
0x1800328d4  test    eax, eax
0x1800328d6  jns     short loc_1800328F5
0x1800328d8  mov     rcx, [rbp+5Fh]; this
0x1800328dc  mov     r9d, eax; char *
0x1800328df  lea     r8, aShellOobeMachi_21; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800328e6  lea     edx, [rsi+34h]; void *
0x1800328e9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800328ee  mov     ebx, eax
0x1800328f0  jmp     loc_180032AD7
0x1800328f5  mov     [rbp+57h+Buffer], rsi
0x1800328f9  lea     r8, [rbp+57h+Buffer]; Buffer
0x1800328fd  mov     edx, 5; InformationClass
0x180032902  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180032906  call    cs:__imp_LsaQueryInformationPolicy
0x18003290c  test    eax, eax
0x18003290e  jns     short loc_180032938
0x180032910  mov     rcx, [rbp+5Fh]; this
0x180032914  mov     r9d, eax; char *
0x180032917  lea     r8, aShellOobeMachi_21; "shell\\oobe\\machine\\plugins\\localuse"...
0x18003291e  mov     edx, 3Bh ; ';'; void *
0x180032923  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180032928  mov     ebx, eax
0x18003292a  lea     rcx, [rbp+57h+Buffer]
0x18003292e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032933  jmp     loc_180032AD7
0x180032938  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003293f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180032943  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180032946  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18003294a  xorps   xmm0, xmm0
0x18003294d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180032952  mov     [rbp+57h+arg_18], rsi
0x180032956  lea     r9, [rbp+57h+ObjectAttributes]
0x18003295a  mov     r8d, 20h ; ' '
0x180032960  lea     rdx, [rbp+57h+arg_18]
0x180032964  xor     ecx, ecx
0x180032966  call    cs:__imp_SamConnect
0x18003296c  test    eax, eax
0x18003296e  jns     short loc_180032995
0x180032970  mov     rcx, [rbp+5Fh]; this
0x180032974  mov     r9d, eax; char *
0x180032977  lea     r8, aShellOobeMachi_21; "shell\\oobe\\machine\\plugins\\localuse"...
0x18003297e  mov     edx, 44h ; 'D'; void *
0x180032983  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180032988  mov     ebx, eax
0x18003298a  lea     rcx, [rbp+57h+arg_18]
0x18003298e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032993  jmp     short loc_18003292A
0x180032995  mov     [rbp+57h+var_80], rsi
0x180032999  lea     r9, [rbp+57h+var_80]
0x18003299d  mov     r8, [rbp+57h+Buffer]
0x1800329a1  mov     r8, [r8+10h]
0x1800329a5  mov     edx, 2000000h
0x1800329aa  mov     rcx, [rbp+57h+arg_18]
0x1800329ae  call    cs:__imp_SamOpenDomain
0x1800329b4  test    eax, eax
0x1800329b6  jns     short loc_1800329DD
0x1800329b8  mov     rcx, [rbp+5Fh]; this
0x1800329bc  mov     r9d, eax; char *
0x1800329bf  lea     r8, aShellOobeMachi_21; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800329c6  mov     edx, 4Ch ; 'L'; void *
0x1800329cb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800329d0  mov     ebx, eax
0x1800329d2  lea     rcx, [rbp+57h+var_80]
0x1800329d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800329db  jmp     short loc_18003298A
0x1800329dd  mov     [rbp+57h+Sid], rsi
0x1800329e1  lea     rdx, [rbp+57h+Sid]; Sid
0x1800329e5  mov     rcx, rbx; StringSid
0x1800329e8  call    cs:__imp_ConvertStringSidToSidW
0x1800329ee  test    eax, eax
0x1800329f0  jnz     short loc_180032A12
0x1800329f2  mov     rcx, [rbp+5Fh]; this
0x1800329f6  lea     r8, aShellOobeMachi_21; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800329fd  lea     edx, [rax+4Fh]; void *
0x180032a00  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032a05  mov     ebx, eax
0x180032a07  lea     rcx, [rbp+57h+Sid]
0x180032a0b  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x180032a10  jmp     short loc_1800329D2
0x180032a12  mov     rbx, [rbp+57h+Sid]
0x180032a16  mov     rcx, rbx; pSid
0x180032a19  call    cs:__imp_GetSidSubAuthorityCount
0x180032a1f  movzx   edx, byte ptr [rax]
0x180032a22  dec     edx; nSubAuthority
0x180032a24  mov     rcx, rbx; pSid
0x180032a27  call    cs:__imp_GetSidSubAuthority
0x180032a2d  mov     r8d, [rax]
0x180032a30  mov     [rbp+57h+var_70], rsi
0x180032a34  lea     r9, [rbp+57h+var_70]
0x180032a38  mov     edx, 2000000h
0x180032a3d  mov     rcx, [rbp+57h+var_80]
0x180032a41  call    cs:__imp_SamOpenUser
0x180032a47  test    eax, eax
0x180032a49  jns     short loc_180032A70
0x180032a4b  mov     edx, 58h ; 'X'; void *
0x180032a50  lea     r8, aShellOobeMachi_21; "shell\\oobe\\machine\\plugins\\localuse"...
0x180032a57  mov     r9d, eax; char *
0x180032a5a  mov     rcx, [rbp+5Fh]; this
0x180032a5e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180032a63  mov     ebx, eax
0x180032a65  lea     rcx, [rbp+57h+var_70]
0x180032a69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032a6e  jmp     short loc_180032A07
0x180032a70  xorps   xmm0, xmm0
0x180032a73  xor     eax, eax
0x180032a75  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180032a79  mov     [rbp+57h+var_20], rax
0x180032a7d  mov     rdx, rdi; SourceString
0x180032a80  lea     rcx, [rbp+57h+DestinationString.Buffer]; DestinationString
0x180032a84  call    cs:__imp_RtlInitUnicodeString
0x180032a8a  lea     r8, [rbp+57h+DestinationString]
0x180032a8e  mov     edx, 1Eh
0x180032a93  mov     rcx, [rbp+57h+var_70]
0x180032a97  call    cs:__imp_SamSetInformationUser
0x180032a9d  test    eax, eax
0x180032a9f  jns     short loc_180032AA8
0x180032aa1  mov     edx, 60h ; '`'
0x180032aa6  jmp     short loc_180032A50
0x180032aa8  lea     rcx, [rbp+57h+var_70]
0x180032aac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032ab1  lea     rcx, [rbp+57h+Sid]
0x180032ab5  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x180032aba  lea     rcx, [rbp+57h+var_80]
0x180032abe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032ac3  lea     rcx, [rbp+57h+arg_18]
0x180032ac7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032acc  lea     rcx, [rbp+57h+Buffer]
0x180032ad0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032ad5  mov     ebx, esi
0x180032ad7  lea     rcx, [rbp+57h+PolicyHandle]
0x180032adb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180032ae0  mov     eax, ebx
0x180032ae2  mov     rbx, [rsp+0A0h+arg_0]
0x180032aea  add     rsp, 90h
0x180032af1  pop     rdi
0x180032af2  pop     rsi
0x180032af3  pop     rbp
0x180032af4  retn
```
