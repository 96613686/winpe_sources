# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18000ca34`
- end: `0x18000cdcc`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `920`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18000c44c`
- `0x18000cde0`
- `0x18002b9cc`
- `0x180045fa4`
- `0x1800484a0`

## callees

- `0x180002890`
- `0x180003474`
- `0x18000ca34`

## import_xrefs

- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000cad9`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000cad9`
- `ntdll!ZwUpdateWnfStateData` at `0x18000cb08`
- `ntdll!ZwUpdateWnfStateData` at `0x18000cb08`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000cb2b`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000cb2b`
- `ntdll!NtQuerySystemInformation` at `0x18000cb51`
- `ntdll!NtQuerySystemInformation` at `0x18000cb51`
- `ntdll!NtOpenEvent` at `0x18000cbb0`
- `ntdll!NtOpenEvent` at `0x18000cbb0`
- `ntdll!NtWaitForSingleObject` at `0x18000cbe9`
- `ntdll!NtWaitForSingleObject` at `0x18000cbe9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000cc4c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000cc4c`
- `ntdll!RtlInitUnicodeString` at `0x18000cc7d`
- `ntdll!RtlInitUnicodeString` at `0x18000cc7d`
- `ntdll!NtAlpcConnectPort` at `0x18000ccfd`
- `ntdll!NtAlpcConnectPort` at `0x18000ccfd`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000cd5a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000cd5a`
- `ntdll!RtlFreeSid` at `0x18000cd8e`
- `ntdll!RtlFreeSid` at `0x18000cd8e`
- `ntdll!NtClose` at `0x18000cbf6`
- `ntdll!NtClose` at `0x18000cd9d`
- `ntdll!NtClose` at `0x18000cbf6`
- `ntdll!NtClose` at `0x18000cd9d`

## string_xrefs

- `0x18000cb66`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
__int64 __fastcall WersvcSendMessage(PCWSTR SourceString, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  char v6; // di
  BOOL v7; // ebx
  int v8; // eax
  int v9; // ecx
  NTSTATUS v10; // ebx
  __int64 v11; // rsi
  char v12; // dl
  union _LARGE_INTEGER *v13; // r8
  __int64 *v14; // rsi
  int v15; // eax
  HANDLE v16; // rcx
  int v17; // eax
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-48h]
  __int128 v29; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+108h] [rbp+8h] BYREF
  __int128 v32; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v33[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v34; // [rsp+130h] [rbp+30h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset_0(v33, 0, 0x48u);
  v25 = 0;
  v6 = 1;
  Handle = 0;
  Sid = 0;
  v21 = 0;
  SystemInformation = 0;
  LODWORD(EventHandle) = 0;
  DestinationString = 0;
  v7 = 0;
  v32 = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0 && (_DWORD)EventHandle )
    v7 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v32 = 0;
  v8 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v32, 0, 0);
  v9 = v7 + 1;
  if ( v8 )
    v9 = v7;
  if ( v9 )
  {
    v10 = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    if ( v10 >= 0 )
    {
      v11 = (int)SystemInformation;
      *((_QWORD *)&v32 + 1) = L"\\KernelObjects\\SystemErrorPortReady";
      *(_QWORD *)&v32 = 4718662;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v32;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.Attributes, 0, 24);
      EventHandle = 0;
      v24 = 0;
      ObjectAttributes.RootDirectory = 0;
      v10 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
      if ( v10 >= 0 )
      {
        if ( (_DWORD)v11 == -1 )
        {
          v12 = 1;
        }
        else
        {
          v12 = 0;
          v24 = -10000 * v11;
        }
        v13 = (union _LARGE_INTEGER *)&v24;
        if ( v12 )
          v13 = 0;
        v10 = NtWaitForSingleObject(EventHandle, 0, v13);
        NtClose(EventHandle);
        if ( v10 >= 0 )
        {
          if ( v10 == 258 )
          {
LABEL_16:
            v10 = -1073740973;
            goto LABEL_28;
          }
          v10 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
          if ( v10 >= 0 )
          {
            if ( HIDWORD(SystemInformation) != -1 )
            {
              v6 = 0;
              v25 = -10000LL * SHIDWORD(SystemInformation);
            }
            RtlInitUnicodeString(&DestinationString, SourceString);
            LODWORD(v27) = 48;
            *((_QWORD *)&v27 + 1) = 0;
            DWORD2(v28) = 0;
            *(_QWORD *)&v28 = 0;
            v29 = 0;
            memset_0(v33, 0, 0x48u);
            v14 = &v25;
            if ( v6 )
              v14 = 0;
            v34 = 1400;
            v15 = NtAlpcConnectPort(&Handle, &DestinationString, &v27, v33, 0x20000, Sid, 0, 0, 0, 0, v14);
            v10 = v15;
            if ( v15 >= 0 )
            {
              if ( v15 == 258 )
                goto LABEL_16;
              memset_0((char *)a3 + 4, 0, 0x574u);
              v16 = Handle;
              *(_DWORD *)a3 = 91751760;
              v21 = 1400;
              v17 = NtAlpcSendWaitReceivePort(v16, 0x20000, a2, 0, a3, &v21, 0, v14);
              v10 = v17;
              if ( v17 >= 0 && v17 != 258 )
                v10 = v21 != 1400 ? 0xC000021F : 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = -1073741696;
  }
LABEL_28:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ca34  mov     [rsp-8+arg_18], rbx
0x18000ca39  push    rbp
0x18000ca3a  push    rsi
0x18000ca3b  push    rdi
0x18000ca3c  push    r12
0x18000ca3e  push    r13
0x18000ca40  push    r14
0x18000ca42  push    r15
0x18000ca44  lea     rbp, [rsp-80h]
0x18000ca49  sub     rsp, 180h
0x18000ca50  mov     rax, cs:__security_cookie
0x18000ca57  xor     rax, rsp
0x18000ca5a  mov     [rbp+0B0h+var_40], rax
0x18000ca5e  xorps   xmm0, xmm0
0x18000ca61  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x18000ca67  xor     r13d, r13d
0x18000ca6a  mov     r14, r8
0x18000ca6d  mov     r15, rdx
0x18000ca70  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r13d
0x18000ca74  mov     r12, rcx
0x18000ca77  xor     edx, edx; Val
0x18000ca79  lea     rcx, [rbp+0B0h+var_90]; void *
0x18000ca7d  lea     r8d, [r13+48h]; Size
0x18000ca81  movups  [rbp+0B0h+var_108], xmm0
0x18000ca85  movups  [rbp+0B0h+var_F8], xmm0
0x18000ca89  movups  [rbp+0B0h+var_E8], xmm0
0x18000ca8d  call    memset_0
0x18000ca92  xorps   xmm0, xmm0
0x18000ca95  mov     [rbp+0B0h+var_120], r13
0x18000ca99  lea     edi, [r13+1]
0x18000ca9d  mov     [rbp+0B0h+Handle], r13
0x18000caa1  mov     edx, edi
0x18000caa3  mov     [rsp+1B0h+var_138], r13
0x18000caa8  lea     r9, [rsp+1B0h+EventHandle]
0x18000caad  mov     [rsp+1B0h+var_140], r13
0x18000cab2  xor     r8d, r8d
0x18000cab5  mov     [rsp+1B0h+SystemInformation], r13
0x18000caba  lea     rcx, WNF_WER_SERVICE_START
0x18000cac1  mov     dword ptr [rsp+1B0h+EventHandle], r13d
0x18000cac6  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x18000caca  mov     ebx, r13d
0x18000cacd  mov     [rsp+1B0h+SubAuthority2], 4
0x18000cad5  movups  [rbp+0B0h+var_A0], xmm0
0x18000cad9  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18000cadf  test    eax, eax
0x18000cae1  js      short loc_18000CB13
0x18000cae3  cmp     dword ptr [rsp+1B0h+EventHandle], r13d
0x18000cae8  jz      short loc_18000CB13
0x18000caea  mov     [rsp+1B0h+SubAuthority4], r13d
0x18000caef  lea     rcx, WNF_WER_SERVICE_START
0x18000caf6  mov     [rsp+1B0h+SubAuthority3], r13d
0x18000cafb  xor     r9d, r9d
0x18000cafe  xor     r8d, r8d
0x18000cb01  mov     qword ptr [rsp+1B0h+SubAuthority2], r13
0x18000cb06  xor     edx, edx
0x18000cb08  call    cs:__imp_ZwUpdateWnfStateData
0x18000cb0e  test    eax, eax
0x18000cb10  cmovns  ebx, edi
0x18000cb13  xorps   xmm0, xmm0
0x18000cb16  lea     rdx, [rbp+0B0h+var_A0]
0x18000cb1a  xor     r9d, r9d
0x18000cb1d  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x18000cb24  xor     r8d, r8d
0x18000cb27  movups  [rbp+0B0h+var_A0], xmm0
0x18000cb2b  call    cs:__imp_EtwEventWriteNoRegistration
0x18000cb31  test    eax, eax
0x18000cb33  lea     ecx, [rbx+1]
0x18000cb36  cmovnz  ecx, ebx
0x18000cb39  test    ecx, ecx
0x18000cb3b  jz      loc_18000CD7F
0x18000cb41  xor     r9d, r9d; ReturnLength
0x18000cb44  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x18000cb49  lea     r8d, [r9+8]; SystemInformationLength
0x18000cb4d  lea     ecx, [r9+73h]; SystemInformationClass
0x18000cb51  call    cs:__imp_NtQuerySystemInformation
0x18000cb57  mov     ebx, eax
0x18000cb59  test    eax, eax
0x18000cb5b  js      loc_18000CD84
0x18000cb61  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x18000cb66  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x18000cb6d  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x18000cb71  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x18000cb75  lea     rax, [rbp+0B0h+var_A0]
0x18000cb79  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x18000cb81  xorps   xmm0, xmm0
0x18000cb84  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x18000cb88  mov     edx, 100001h; DesiredAccess
0x18000cb8d  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x18000cb95  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x18000cb9a  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r13
0x18000cb9e  mov     [rsp+1B0h+EventHandle], r13
0x18000cba3  mov     [rbp+0B0h+var_128], r13
0x18000cba7  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r13
0x18000cbab  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000cbb0  call    cs:__imp_NtOpenEvent
0x18000cbb6  mov     ebx, eax
0x18000cbb8  test    eax, eax
0x18000cbba  js      loc_18000CD84
0x18000cbc0  cmp     esi, 0FFFFFFFFh
0x18000cbc3  jnz     short loc_18000CBCA
0x18000cbc5  mov     dl, dil
0x18000cbc8  jmp     short loc_18000CBD8
0x18000cbca  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x18000cbd1  mov     dl, r13b
0x18000cbd4  mov     [rbp+0B0h+var_128], rcx
0x18000cbd8  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x18000cbdd  lea     r8, [rbp+0B0h+var_128]
0x18000cbe1  test    dl, dl
0x18000cbe3  cmovnz  r8, r13; Timeout
0x18000cbe7  xor     edx, edx; Alertable
0x18000cbe9  call    cs:__imp_NtWaitForSingleObject
0x18000cbef  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x18000cbf4  mov     ebx, eax
0x18000cbf6  call    cs:__imp_NtClose
0x18000cbfc  test    ebx, ebx
0x18000cbfe  js      loc_18000CD84
0x18000cc04  cmp     ebx, 102h
0x18000cc0a  jnz     short loc_18000CC16
0x18000cc0c  mov     ebx, 0C0000353h
0x18000cc11  jmp     loc_18000CD84
0x18000cc16  lea     rax, [rsp+1B0h+var_138]
0x18000cc1b  xor     r9d, r9d; SubAuthority1
0x18000cc1e  mov     [rsp+1B0h+Sid], rax; Sid
0x18000cc23  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x18000cc27  mov     [rsp+1B0h+SubAuthority7], r13d; SubAuthority7
0x18000cc2c  mov     dl, dil; SubAuthorityCount
0x18000cc2f  mov     [rsp+1B0h+SubAuthority6], r13d; SubAuthority6
0x18000cc34  mov     [rsp+1B0h+SubAuthority5], r13d; SubAuthority5
0x18000cc39  lea     r8d, [r9+12h]; SubAuthority0
0x18000cc3d  mov     [rsp+1B0h+SubAuthority4], r13d; SubAuthority4
0x18000cc42  mov     [rsp+1B0h+SubAuthority3], r13d; SubAuthority3
0x18000cc47  mov     [rsp+1B0h+SubAuthority2], r13d; SubAuthority2
0x18000cc4c  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000cc52  mov     ebx, eax
0x18000cc54  test    eax, eax
0x18000cc56  js      loc_18000CD84
0x18000cc5c  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x18000cc61  jz      short loc_18000CC76
0x18000cc63  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x18000cc68  mov     dil, r13b
0x18000cc6b  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18000cc72  mov     [rbp+0B0h+var_120], rcx
0x18000cc76  mov     rdx, r12; SourceString
0x18000cc79  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x18000cc7d  call    cs:__imp_RtlInitUnicodeString
0x18000cc83  xor     edx, edx; Val
0x18000cc85  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x18000cc8c  xorps   xmm0, xmm0
0x18000cc8f  mov     qword ptr [rbp+0B0h+var_108+8], r13
0x18000cc93  lea     rcx, [rbp+0B0h+var_90]; void *
0x18000cc97  mov     dword ptr [rbp+0B0h+var_F8+8], r13d
0x18000cc9b  mov     qword ptr [rbp+0B0h+var_F8], r13
0x18000cc9f  lea     r8d, [rdx+48h]; Size
0x18000cca3  movdqu  [rbp+0B0h+var_E8], xmm0
0x18000cca8  call    memset_0
0x18000ccad  mov     rax, [rsp+1B0h+var_138]
0x18000ccb2  lea     rsi, [rbp+0B0h+var_120]
0x18000ccb6  test    dil, dil
0x18000ccb9  lea     r9, [rbp+0B0h+var_90]
0x18000ccbd  mov     r12d, 578h
0x18000ccc3  lea     r8, [rbp+0B0h+var_108]
0x18000ccc7  cmovnz  rsi, r13
0x18000cccb  mov     [rbp+0B0h+var_80], r12
0x18000cccf  mov     [rsp+1B0h+Sid], rsi
0x18000ccd4  lea     rdx, [rbp+0B0h+DestinationString]
0x18000ccd8  mov     qword ptr [rsp+1B0h+SubAuthority7], r13
0x18000ccdd  lea     rcx, [rbp+0B0h+Handle]
0x18000cce1  mov     qword ptr [rsp+1B0h+SubAuthority6], r13
0x18000cce6  mov     qword ptr [rsp+1B0h+SubAuthority5], r13
0x18000cceb  mov     qword ptr [rsp+1B0h+SubAuthority4], r13
0x18000ccf0  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x18000ccf5  mov     [rsp+1B0h+SubAuthority2], 20000h
0x18000ccfd  call    cs:__imp_NtAlpcConnectPort
0x18000cd03  mov     ebx, eax
0x18000cd05  test    eax, eax
0x18000cd07  js      short loc_18000CD84
0x18000cd09  mov     edi, 102h
0x18000cd0e  cmp     eax, edi
0x18000cd10  jz      loc_18000CC0C
0x18000cd16  lea     rcx, [r14+4]; void *
0x18000cd1a  xor     edx, edx; Val
0x18000cd1c  lea     r8d, [r12-4]; Size
0x18000cd21  call    memset_0
0x18000cd26  mov     rcx, [rbp+0B0h+Handle]
0x18000cd2a  lea     rax, [rsp+1B0h+var_140]
0x18000cd2f  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x18000cd34  xor     r9d, r9d
0x18000cd37  mov     qword ptr [rsp+1B0h+SubAuthority4], r13
0x18000cd3c  mov     r8, r15
0x18000cd3f  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x18000cd44  mov     edx, 20000h
0x18000cd49  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x18000cd4e  mov     dword ptr [r14], 5780550h
0x18000cd55  mov     [rsp+1B0h+var_140], r12
0x18000cd5a  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000cd60  mov     ebx, eax
0x18000cd62  test    eax, eax
0x18000cd64  js      short loc_18000CD84
0x18000cd66  cmp     eax, edi
0x18000cd68  jz      short loc_18000CD84
0x18000cd6a  mov     rax, [rsp+1B0h+var_140]
0x18000cd6f  sub     rax, r12
0x18000cd72  neg     rax
0x18000cd75  sbb     ebx, ebx
0x18000cd77  and     ebx, 0C000021Fh
0x18000cd7d  jmp     short loc_18000CD84
0x18000cd7f  mov     ebx, 0C0000080h
0x18000cd84  mov     rcx, [rsp+1B0h+var_138]; Sid
0x18000cd89  test    rcx, rcx
0x18000cd8c  jz      short loc_18000CD94
0x18000cd8e  call    cs:__imp_RtlFreeSid
0x18000cd94  mov     rcx, [rbp+0B0h+Handle]; Handle
0x18000cd98  test    rcx, rcx
0x18000cd9b  jz      short loc_18000CDA3
0x18000cd9d  call    cs:__imp_NtClose
0x18000cda3  mov     eax, ebx
0x18000cda5  mov     rcx, [rbp+0B0h+var_40]
0x18000cda9  xor     rcx, rsp; StackCookie
0x18000cdac  call    __security_check_cookie
0x18000cdb1  mov     rbx, [rsp+1B0h+arg_18]
0x18000cdb9  add     rsp, 180h
0x18000cdc0  pop     r15
0x18000cdc2  pop     r14
0x18000cdc4  pop     r13
0x18000cdc6  pop     r12
0x18000cdc8  pop     rdi
0x18000cdc9  pop     rsi
0x18000cdca  pop     rbp
0x18000cdcb  retn
```
