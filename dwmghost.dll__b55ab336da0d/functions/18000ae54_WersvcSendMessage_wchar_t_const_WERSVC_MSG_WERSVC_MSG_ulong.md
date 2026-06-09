# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18000ae54`
- end: `0x18000b1f3`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `927`
- prototype: `int(const wchar_t *, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18000a9c4`
- `0x18000b1fc`

## callees

- `0x180001190`
- `0x180001962`
- `0x18000ae54`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18000afcf`
- `ntdll!NtOpenEvent` at `0x18000afcf`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000af4a`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000af4a`
- `ntdll!ZwUpdateWnfStateData` at `0x18000af27`
- `ntdll!ZwUpdateWnfStateData` at `0x18000af27`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000b06e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000b06e`
- `ntdll!NtQuerySystemInformation` at `0x18000af70`
- `ntdll!NtQuerySystemInformation` at `0x18000af70`
- `ntdll!RtlInitUnicodeString` at `0x18000b0a3`
- `ntdll!RtlInitUnicodeString` at `0x18000b0a3`
- `ntdll!NtAlpcConnectPort` at `0x18000b121`
- `ntdll!NtAlpcConnectPort` at `0x18000b121`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000b180`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000b180`
- `ntdll!RtlFreeSid` at `0x18000b1b5`
- `ntdll!RtlFreeSid` at `0x18000b1b5`
- `ntdll!NtClose` at `0x18000b015`
- `ntdll!NtClose` at `0x18000b1c4`
- `ntdll!NtClose` at `0x18000b015`
- `ntdll!NtClose` at `0x18000b1c4`
- `ntdll!NtWaitForSingleObject` at `0x18000b008`
- `ntdll!NtWaitForSingleObject` at `0x18000b008`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000aef8`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000aef8`

## string_xrefs

- `0x18000b098`: `\WindowsErrorReportingServicePort`
- `0x18000af85`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
__int64 __fastcall WersvcSendMessage(const wchar_t *a1, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  char v5; // di
  BOOL v6; // ebx
  int v7; // eax
  int v8; // ecx
  NTSTATUS v9; // ebx
  __int64 v10; // rsi
  char v11; // dl
  union _LARGE_INTEGER *v12; // r8
  __int64 *v13; // rsi
  int v14; // eax
  HANDLE v15; // rcx
  int v16; // eax
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v27; // [rsp+B8h] [rbp-48h]
  __int128 v28; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+108h] [rbp+8h] BYREF
  __int128 v31; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v32[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v33; // [rsp+130h] [rbp+30h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v32, 0, 0x48u);
  v24 = 0;
  v5 = 1;
  Handle = 0;
  Sid = 0;
  v20 = 0;
  SystemInformation = 0;
  LODWORD(EventHandle) = 0;
  DestinationString = 0;
  v6 = 0;
  v31 = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0 && (_DWORD)EventHandle )
    v6 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v31 = 0;
  v7 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v31, 0, 0);
  v8 = v6 + 1;
  if ( v7 )
    v8 = v6;
  if ( v8 )
  {
    v9 = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    if ( v9 >= 0 )
    {
      v10 = (int)SystemInformation;
      *((_QWORD *)&v31 + 1) = L"\\KernelObjects\\SystemErrorPortReady";
      *(_QWORD *)&v31 = 4718662;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v31;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.Attributes, 0, 24);
      EventHandle = 0;
      v23 = 0;
      ObjectAttributes.RootDirectory = 0;
      v9 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
      if ( v9 >= 0 )
      {
        if ( (_DWORD)v10 == -1 )
        {
          v11 = 1;
        }
        else
        {
          v11 = 0;
          v23 = -10000 * v10;
        }
        v12 = (union _LARGE_INTEGER *)&v23;
        if ( v11 )
          v12 = 0;
        v9 = NtWaitForSingleObject(EventHandle, 0, v12);
        NtClose(EventHandle);
        if ( v9 >= 0 )
        {
          if ( v9 == 258 )
          {
LABEL_16:
            v9 = -1073740973;
            goto LABEL_28;
          }
          v9 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
          if ( v9 >= 0 )
          {
            if ( HIDWORD(SystemInformation) != -1 )
            {
              v5 = 0;
              v24 = -10000LL * SHIDWORD(SystemInformation);
            }
            RtlInitUnicodeString(&DestinationString, L"\\WindowsErrorReportingServicePort");
            LODWORD(v26) = 48;
            *((_QWORD *)&v26 + 1) = 0;
            DWORD2(v27) = 0;
            *(_QWORD *)&v27 = 0;
            v28 = 0;
            memset_0(v32, 0, 0x48u);
            v13 = &v24;
            v33 = 1400;
            if ( v5 )
              v13 = 0;
            v14 = NtAlpcConnectPort(&Handle, &DestinationString, &v26, v32, 0x20000, Sid, 0, 0, 0, 0, v13);
            v9 = v14;
            if ( v14 >= 0 )
            {
              if ( v14 == 258 )
                goto LABEL_16;
              memset_0((char *)a3 + 4, 0, 0x574u);
              v15 = Handle;
              *(_DWORD *)a3 = 91751760;
              v20 = 1400;
              v16 = NtAlpcSendWaitReceivePort(v15, 0x20000, a2, 0, a3, &v20, 0, v13);
              v9 = v16;
              if ( v16 >= 0 && v16 != 258 )
                v9 = v20 != 1400 ? 0xC000021F : 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v9 = -1073741696;
  }
LABEL_28:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ae54  mov     [rsp-8+arg_0], rbx
0x18000ae59  push    rbp
0x18000ae5a  push    rsi
0x18000ae5b  push    rdi
0x18000ae5c  push    r12
0x18000ae5e  push    r13
0x18000ae60  push    r14
0x18000ae62  push    r15
0x18000ae64  lea     rbp, [rsp-80h]
0x18000ae69  sub     rsp, 180h
0x18000ae70  mov     rax, cs:__security_cookie
0x18000ae77  xor     rax, rsp
0x18000ae7a  mov     [rbp+0B0h+var_40], rax
0x18000ae7e  xorps   xmm0, xmm0
0x18000ae81  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x18000ae87  xor     r12d, r12d
0x18000ae8a  lea     rcx, [rbp+0B0h+var_90]; void *
0x18000ae8e  mov     r14, r8
0x18000ae91  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r12d
0x18000ae95  mov     r15, rdx
0x18000ae98  xor     edx, edx; Val
0x18000ae9a  movups  [rbp+0B0h+var_108], xmm0
0x18000ae9e  lea     r8d, [r12+48h]; Size
0x18000aea3  movups  [rbp+0B0h+var_F8], xmm0
0x18000aea7  movups  [rbp+0B0h+var_E8], xmm0
0x18000aeab  call    memset_0
0x18000aeb0  xorps   xmm0, xmm0
0x18000aeb3  mov     [rbp+0B0h+var_120], r12
0x18000aeb7  lea     edi, [r12+1]
0x18000aebc  mov     [rbp+0B0h+Handle], r12
0x18000aec0  mov     edx, edi
0x18000aec2  mov     [rsp+1B0h+var_138], r12
0x18000aec7  lea     r9, [rsp+1B0h+EventHandle]
0x18000aecc  mov     [rsp+1B0h+var_140], r12
0x18000aed1  xor     r8d, r8d
0x18000aed4  mov     [rsp+1B0h+SystemInformation], r12
0x18000aed9  lea     rcx, WNF_WER_SERVICE_START
0x18000aee0  mov     dword ptr [rsp+1B0h+EventHandle], r12d
0x18000aee5  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x18000aee9  mov     ebx, r12d
0x18000aeec  mov     [rsp+1B0h+SubAuthority2], 4
0x18000aef4  movups  [rbp+0B0h+var_A0], xmm0
0x18000aef8  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18000aefe  test    eax, eax
0x18000af00  js      short loc_18000AF32
0x18000af02  cmp     dword ptr [rsp+1B0h+EventHandle], r12d
0x18000af07  jz      short loc_18000AF32
0x18000af09  mov     [rsp+1B0h+SubAuthority4], r12d
0x18000af0e  lea     rcx, WNF_WER_SERVICE_START
0x18000af15  mov     [rsp+1B0h+SubAuthority3], r12d
0x18000af1a  xor     r9d, r9d
0x18000af1d  xor     r8d, r8d
0x18000af20  mov     qword ptr [rsp+1B0h+SubAuthority2], r12
0x18000af25  xor     edx, edx
0x18000af27  call    cs:__imp_ZwUpdateWnfStateData
0x18000af2d  test    eax, eax
0x18000af2f  cmovns  ebx, edi
0x18000af32  xorps   xmm0, xmm0
0x18000af35  lea     rdx, [rbp+0B0h+var_A0]
0x18000af39  xor     r9d, r9d
0x18000af3c  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x18000af43  xor     r8d, r8d
0x18000af46  movups  [rbp+0B0h+var_A0], xmm0
0x18000af4a  call    cs:__imp_EtwEventWriteNoRegistration
0x18000af50  test    eax, eax
0x18000af52  lea     ecx, [rbx+1]
0x18000af55  cmovnz  ecx, ebx
0x18000af58  test    ecx, ecx
0x18000af5a  jz      loc_18000B1A6
0x18000af60  xor     r9d, r9d; ReturnLength
0x18000af63  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x18000af68  lea     r8d, [r9+8]; SystemInformationLength
0x18000af6c  lea     ecx, [r9+73h]; SystemInformationClass
0x18000af70  call    cs:__imp_NtQuerySystemInformation
0x18000af76  mov     ebx, eax
0x18000af78  test    eax, eax
0x18000af7a  js      loc_18000B1AB
0x18000af80  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x18000af85  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x18000af8c  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x18000af90  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x18000af94  lea     rax, [rbp+0B0h+var_A0]
0x18000af98  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x18000afa0  xorps   xmm0, xmm0
0x18000afa3  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x18000afa7  mov     edx, 100001h; DesiredAccess
0x18000afac  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x18000afb4  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x18000afb9  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r12
0x18000afbd  mov     [rsp+1B0h+EventHandle], r12
0x18000afc2  mov     [rbp+0B0h+var_128], r12
0x18000afc6  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x18000afca  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000afcf  call    cs:__imp_NtOpenEvent
0x18000afd5  mov     ebx, eax
0x18000afd7  test    eax, eax
0x18000afd9  js      loc_18000B1AB
0x18000afdf  cmp     esi, 0FFFFFFFFh
0x18000afe2  jnz     short loc_18000AFE9
0x18000afe4  mov     dl, dil
0x18000afe7  jmp     short loc_18000AFF7
0x18000afe9  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x18000aff0  mov     dl, r12b
0x18000aff3  mov     [rbp+0B0h+var_128], rcx
0x18000aff7  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x18000affc  lea     r8, [rbp+0B0h+var_128]
0x18000b000  test    dl, dl
0x18000b002  cmovnz  r8, r12; Timeout
0x18000b006  xor     edx, edx; Alertable
0x18000b008  call    cs:__imp_NtWaitForSingleObject
0x18000b00e  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x18000b013  mov     ebx, eax
0x18000b015  call    cs:__imp_NtClose
0x18000b01b  test    ebx, ebx
0x18000b01d  js      loc_18000B1AB
0x18000b023  mov     r13d, 102h
0x18000b029  cmp     ebx, r13d
0x18000b02c  jnz     short loc_18000B038
0x18000b02e  mov     ebx, 0C0000353h
0x18000b033  jmp     loc_18000B1AB
0x18000b038  lea     rax, [rsp+1B0h+var_138]
0x18000b03d  xor     r9d, r9d; SubAuthority1
0x18000b040  mov     [rsp+1B0h+Sid], rax; Sid
0x18000b045  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x18000b049  mov     [rsp+1B0h+SubAuthority7], r12d; SubAuthority7
0x18000b04e  mov     dl, dil; SubAuthorityCount
0x18000b051  mov     [rsp+1B0h+SubAuthority6], r12d; SubAuthority6
0x18000b056  mov     [rsp+1B0h+SubAuthority5], r12d; SubAuthority5
0x18000b05b  lea     r8d, [r9+12h]; SubAuthority0
0x18000b05f  mov     [rsp+1B0h+SubAuthority4], r12d; SubAuthority4
0x18000b064  mov     [rsp+1B0h+SubAuthority3], r12d; SubAuthority3
0x18000b069  mov     [rsp+1B0h+SubAuthority2], r12d; SubAuthority2
0x18000b06e  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000b074  mov     ebx, eax
0x18000b076  test    eax, eax
0x18000b078  js      loc_18000B1AB
0x18000b07e  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x18000b083  jz      short loc_18000B098
0x18000b085  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x18000b08a  mov     dil, r12b
0x18000b08d  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18000b094  mov     [rbp+0B0h+var_120], rcx
0x18000b098  lea     rdx, SourceString; "\\WindowsErrorReportingServicePort"
0x18000b09f  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x18000b0a3  call    cs:__imp_RtlInitUnicodeString
0x18000b0a9  xor     edx, edx; Val
0x18000b0ab  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x18000b0b2  xorps   xmm0, xmm0
0x18000b0b5  mov     qword ptr [rbp+0B0h+var_108+8], r12
0x18000b0b9  lea     rcx, [rbp+0B0h+var_90]; void *
0x18000b0bd  mov     dword ptr [rbp+0B0h+var_F8+8], r12d
0x18000b0c1  mov     qword ptr [rbp+0B0h+var_F8], r12
0x18000b0c5  lea     r8d, [rdx+48h]; Size
0x18000b0c9  movdqu  [rbp+0B0h+var_E8], xmm0
0x18000b0ce  call    memset_0
0x18000b0d3  mov     rax, [rsp+1B0h+var_138]
0x18000b0d8  lea     rsi, [rbp+0B0h+var_120]
0x18000b0dc  test    dil, dil
0x18000b0df  mov     [rbp+0B0h+var_80], 578h
0x18000b0e7  lea     r9, [rbp+0B0h+var_90]
0x18000b0eb  cmovnz  rsi, r12
0x18000b0ef  lea     r8, [rbp+0B0h+var_108]
0x18000b0f3  mov     [rsp+1B0h+Sid], rsi
0x18000b0f8  lea     rdx, [rbp+0B0h+DestinationString]
0x18000b0fc  mov     qword ptr [rsp+1B0h+SubAuthority7], r12
0x18000b101  lea     rcx, [rbp+0B0h+Handle]
0x18000b105  mov     qword ptr [rsp+1B0h+SubAuthority6], r12
0x18000b10a  mov     qword ptr [rsp+1B0h+SubAuthority5], r12
0x18000b10f  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x18000b114  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x18000b119  mov     [rsp+1B0h+SubAuthority2], 20000h
0x18000b121  call    cs:__imp_NtAlpcConnectPort
0x18000b127  mov     ebx, eax
0x18000b129  test    eax, eax
0x18000b12b  js      short loc_18000B1AB
0x18000b12d  cmp     eax, r13d
0x18000b130  jz      loc_18000B02E
0x18000b136  lea     rcx, [r14+4]; void *
0x18000b13a  xor     edx, edx; Val
0x18000b13c  mov     r8d, 574h; Size
0x18000b142  call    memset_0
0x18000b147  mov     rcx, [rbp+0B0h+Handle]
0x18000b14b  lea     rax, [rsp+1B0h+var_140]
0x18000b150  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x18000b155  mov     edi, 578h
0x18000b15a  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x18000b15f  xor     r9d, r9d
0x18000b162  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x18000b167  mov     r8, r15
0x18000b16a  mov     edx, 20000h
0x18000b16f  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x18000b174  mov     dword ptr [r14], 5780550h
0x18000b17b  mov     [rsp+1B0h+var_140], rdi
0x18000b180  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000b186  mov     ebx, eax
0x18000b188  test    eax, eax
0x18000b18a  js      short loc_18000B1AB
0x18000b18c  cmp     eax, r13d
0x18000b18f  jz      short loc_18000B1AB
0x18000b191  mov     rax, [rsp+1B0h+var_140]
0x18000b196  sub     rax, rdi
0x18000b199  neg     rax
0x18000b19c  sbb     ebx, ebx
0x18000b19e  and     ebx, 0C000021Fh
0x18000b1a4  jmp     short loc_18000B1AB
0x18000b1a6  mov     ebx, 0C0000080h
0x18000b1ab  mov     rcx, [rsp+1B0h+var_138]; Sid
0x18000b1b0  test    rcx, rcx
0x18000b1b3  jz      short loc_18000B1BB
0x18000b1b5  call    cs:__imp_RtlFreeSid
0x18000b1bb  mov     rcx, [rbp+0B0h+Handle]; Handle
0x18000b1bf  test    rcx, rcx
0x18000b1c2  jz      short loc_18000B1CA
0x18000b1c4  call    cs:__imp_NtClose
0x18000b1ca  mov     eax, ebx
0x18000b1cc  mov     rcx, [rbp+0B0h+var_40]
0x18000b1d0  xor     rcx, rsp; StackCookie
0x18000b1d3  call    __security_check_cookie
0x18000b1d8  mov     rbx, [rsp+1B0h+arg_0]
0x18000b1e0  add     rsp, 180h
0x18000b1e7  pop     r15
0x18000b1e9  pop     r14
0x18000b1eb  pop     r13
0x18000b1ed  pop     r12
0x18000b1ef  pop     rdi
0x18000b1f0  pop     rsi
0x18000b1f1  pop     rbp
0x18000b1f2  retn
```
