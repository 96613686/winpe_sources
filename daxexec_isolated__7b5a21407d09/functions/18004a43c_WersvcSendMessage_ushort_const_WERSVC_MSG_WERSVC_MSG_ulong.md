# WersvcSendMessage(ushort const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18004a43c`
- end: `0x18004a82e`
- name: `?WersvcSendMessage@@YAJPEBGPEAU_WERSVC_MSG@@1K@Z`
- size: `1010`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800481c4`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18004a43c`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18004a7a8`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18004a7a8`
- `ntdll!NtAlpcConnectPort` at `0x18004a73f`
- `ntdll!NtAlpcConnectPort` at `0x18004a73f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18004a680`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18004a680`
- `ntdll!NtQuerySystemInformation` at `0x18004a56a`
- `ntdll!NtQuerySystemInformation` at `0x18004a56a`
- `ntdll!NtClose` at `0x18004a621`
- `ntdll!NtClose` at `0x18004a7f8`
- `ntdll!NtClose` at `0x18004a621`
- `ntdll!NtClose` at `0x18004a7f8`
- `ntdll!NtWaitForSingleObject` at `0x18004a60e`
- `ntdll!NtWaitForSingleObject` at `0x18004a60e`
- `ntdll!NtOpenEvent` at `0x18004a5cf`
- `ntdll!NtOpenEvent` at `0x18004a5cf`
- `ntdll!EtwEventWriteNoRegistration` at `0x18004a53e`
- `ntdll!EtwEventWriteNoRegistration` at `0x18004a53e`
- `ntdll!ZwUpdateWnfStateData` at `0x18004a515`
- `ntdll!ZwUpdateWnfStateData` at `0x18004a515`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18004a4e0`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18004a4e0`
- `ntdll!RtlInitUnicodeString` at `0x18004a6bb`
- `ntdll!RtlInitUnicodeString` at `0x18004a6bb`
- `ntdll!RtlFreeSid` at `0x18004a7e3`
- `ntdll!RtlFreeSid` at `0x18004a7e3`

## string_xrefs

- `0x18004a585`: `\KernelObjects\SystemErrorPortReady`
- `0x18004a6b0`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall WersvcSendMessage(const unsigned __int16 *a1, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
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
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+108h] [rbp+8h] BYREF
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
0x18004a43c  mov     [rsp-8+arg_0], rbx
0x18004a441  push    rbp
0x18004a442  push    rsi
0x18004a443  push    rdi
0x18004a444  push    r12
0x18004a446  push    r13
0x18004a448  push    r14
0x18004a44a  push    r15
0x18004a44c  lea     rbp, [rsp-80h]
0x18004a451  sub     rsp, 180h
0x18004a458  mov     rax, cs:__security_cookie
0x18004a45f  xor     rax, rsp
0x18004a462  mov     [rbp+0B0h+var_40], rax
0x18004a466  xorps   xmm0, xmm0
0x18004a469  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x18004a46f  xor     r12d, r12d
0x18004a472  lea     rcx, [rbp+0B0h+var_90]; void *
0x18004a476  mov     r14, r8
0x18004a479  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r12d
0x18004a47d  mov     r15, rdx
0x18004a480  xor     edx, edx; Val
0x18004a482  movups  [rbp+0B0h+var_108], xmm0
0x18004a486  lea     r8d, [r12+48h]; Size
0x18004a48b  movups  [rbp+0B0h+var_F8], xmm0
0x18004a48f  movups  [rbp+0B0h+var_E8], xmm0
0x18004a493  call    memset_0
0x18004a498  xorps   xmm0, xmm0
0x18004a49b  mov     [rbp+0B0h+var_120], r12
0x18004a49f  lea     edi, [r12+1]
0x18004a4a4  mov     [rbp+0B0h+Handle], r12
0x18004a4a8  mov     edx, edi
0x18004a4aa  mov     [rsp+1B0h+var_138], r12
0x18004a4af  lea     r9, [rsp+1B0h+EventHandle]
0x18004a4b4  mov     [rsp+1B0h+var_140], r12
0x18004a4b9  xor     r8d, r8d
0x18004a4bc  mov     [rsp+1B0h+SystemInformation], r12
0x18004a4c1  lea     rcx, WNF_WER_SERVICE_START
0x18004a4c8  mov     dword ptr [rsp+1B0h+EventHandle], r12d
0x18004a4cd  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x18004a4d1  mov     ebx, r12d
0x18004a4d4  mov     [rsp+1B0h+SubAuthority2], 4
0x18004a4dc  movups  [rbp+0B0h+var_A0], xmm0
0x18004a4e0  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18004a4e7  nop     dword ptr [rax+rax+00h]
0x18004a4ec  test    eax, eax
0x18004a4ee  js      short loc_18004A526
0x18004a4f0  cmp     dword ptr [rsp+1B0h+EventHandle], r12d
0x18004a4f5  jz      short loc_18004A526
0x18004a4f7  mov     [rsp+1B0h+SubAuthority4], r12d
0x18004a4fc  lea     rcx, WNF_WER_SERVICE_START
0x18004a503  mov     [rsp+1B0h+SubAuthority3], r12d
0x18004a508  xor     r9d, r9d
0x18004a50b  xor     r8d, r8d
0x18004a50e  mov     qword ptr [rsp+1B0h+SubAuthority2], r12
0x18004a513  xor     edx, edx
0x18004a515  call    cs:__imp_ZwUpdateWnfStateData
0x18004a51c  nop     dword ptr [rax+rax+00h]
0x18004a521  test    eax, eax
0x18004a523  cmovns  ebx, edi
0x18004a526  xorps   xmm0, xmm0
0x18004a529  lea     rdx, [rbp+0B0h+var_A0]
0x18004a52d  xor     r9d, r9d
0x18004a530  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x18004a537  xor     r8d, r8d
0x18004a53a  movups  [rbp+0B0h+var_A0], xmm0
0x18004a53e  call    cs:__imp_EtwEventWriteNoRegistration
0x18004a545  nop     dword ptr [rax+rax+00h]
0x18004a54a  test    eax, eax
0x18004a54c  lea     ecx, [rbx+1]
0x18004a54f  cmovnz  ecx, ebx
0x18004a552  test    ecx, ecx
0x18004a554  jz      loc_18004A7D4
0x18004a55a  xor     r9d, r9d; ReturnLength
0x18004a55d  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x18004a562  lea     r8d, [r9+8]; SystemInformationLength
0x18004a566  lea     ecx, [r9+73h]; SystemInformationClass
0x18004a56a  call    cs:__imp_NtQuerySystemInformation
0x18004a571  nop     dword ptr [rax+rax+00h]
0x18004a576  mov     ebx, eax
0x18004a578  test    eax, eax
0x18004a57a  js      loc_18004A7D9
0x18004a580  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x18004a585  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x18004a58c  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x18004a590  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x18004a594  lea     rax, [rbp+0B0h+var_A0]
0x18004a598  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x18004a5a0  xorps   xmm0, xmm0
0x18004a5a3  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x18004a5a7  mov     edx, 100001h; DesiredAccess
0x18004a5ac  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x18004a5b4  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x18004a5b9  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r12
0x18004a5bd  mov     [rsp+1B0h+EventHandle], r12
0x18004a5c2  mov     [rbp+0B0h+var_128], r12
0x18004a5c6  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x18004a5ca  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004a5cf  call    cs:__imp_NtOpenEvent
0x18004a5d6  nop     dword ptr [rax+rax+00h]
0x18004a5db  mov     ebx, eax
0x18004a5dd  test    eax, eax
0x18004a5df  js      loc_18004A7D9
0x18004a5e5  cmp     esi, 0FFFFFFFFh
0x18004a5e8  jnz     short loc_18004A5EF
0x18004a5ea  mov     dl, dil
0x18004a5ed  jmp     short loc_18004A5FD
0x18004a5ef  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x18004a5f6  mov     dl, r12b
0x18004a5f9  mov     [rbp+0B0h+var_128], rcx
0x18004a5fd  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x18004a602  lea     r8, [rbp+0B0h+var_128]
0x18004a606  test    dl, dl
0x18004a608  cmovnz  r8, r12; Timeout
0x18004a60c  xor     edx, edx; Alertable
0x18004a60e  call    cs:__imp_NtWaitForSingleObject
0x18004a615  nop     dword ptr [rax+rax+00h]
0x18004a61a  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x18004a61f  mov     ebx, eax
0x18004a621  call    cs:__imp_NtClose
0x18004a628  nop     dword ptr [rax+rax+00h]
0x18004a62d  test    ebx, ebx
0x18004a62f  js      loc_18004A7D9
0x18004a635  mov     r13d, 102h
0x18004a63b  cmp     ebx, r13d
0x18004a63e  jnz     short loc_18004A64A
0x18004a640  mov     ebx, 0C0000353h
0x18004a645  jmp     loc_18004A7D9
0x18004a64a  lea     rax, [rsp+1B0h+var_138]
0x18004a64f  xor     r9d, r9d; SubAuthority1
0x18004a652  mov     [rsp+1B0h+Sid], rax; Sid
0x18004a657  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x18004a65b  mov     [rsp+1B0h+SubAuthority7], r12d; SubAuthority7
0x18004a660  mov     dl, dil; SubAuthorityCount
0x18004a663  mov     [rsp+1B0h+SubAuthority6], r12d; SubAuthority6
0x18004a668  mov     [rsp+1B0h+SubAuthority5], r12d; SubAuthority5
0x18004a66d  lea     r8d, [r9+12h]; SubAuthority0
0x18004a671  mov     [rsp+1B0h+SubAuthority4], r12d; SubAuthority4
0x18004a676  mov     [rsp+1B0h+SubAuthority3], r12d; SubAuthority3
0x18004a67b  mov     [rsp+1B0h+SubAuthority2], r12d; SubAuthority2
0x18004a680  call    cs:__imp_RtlAllocateAndInitializeSid
0x18004a687  nop     dword ptr [rax+rax+00h]
0x18004a68c  mov     ebx, eax
0x18004a68e  test    eax, eax
0x18004a690  js      loc_18004A7D9
0x18004a696  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x18004a69b  jz      short loc_18004A6B0
0x18004a69d  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x18004a6a2  mov     dil, r12b
0x18004a6a5  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18004a6ac  mov     [rbp+0B0h+var_120], rcx
0x18004a6b0  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x18004a6b7  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x18004a6bb  call    cs:__imp_RtlInitUnicodeString
0x18004a6c2  nop     dword ptr [rax+rax+00h]
0x18004a6c7  xor     edx, edx; Val
0x18004a6c9  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x18004a6d0  xorps   xmm0, xmm0
0x18004a6d3  mov     qword ptr [rbp+0B0h+var_108+8], r12
0x18004a6d7  lea     rcx, [rbp+0B0h+var_90]; void *
0x18004a6db  mov     dword ptr [rbp+0B0h+var_F8+8], r12d
0x18004a6df  mov     qword ptr [rbp+0B0h+var_F8], r12
0x18004a6e3  lea     r8d, [rdx+48h]; Size
0x18004a6e7  movdqu  [rbp+0B0h+var_E8], xmm0
0x18004a6ec  call    memset_0
0x18004a6f1  mov     rax, [rsp+1B0h+var_138]
0x18004a6f6  lea     rsi, [rbp+0B0h+var_120]
0x18004a6fa  test    dil, dil
0x18004a6fd  mov     [rbp+0B0h+var_80], 578h
0x18004a705  lea     r9, [rbp+0B0h+var_90]
0x18004a709  cmovnz  rsi, r12
0x18004a70d  lea     r8, [rbp+0B0h+var_108]
0x18004a711  mov     [rsp+1B0h+Sid], rsi
0x18004a716  lea     rdx, [rbp+0B0h+DestinationString]
0x18004a71a  mov     qword ptr [rsp+1B0h+SubAuthority7], r12
0x18004a71f  lea     rcx, [rbp+0B0h+Handle]
0x18004a723  mov     qword ptr [rsp+1B0h+SubAuthority6], r12
0x18004a728  mov     qword ptr [rsp+1B0h+SubAuthority5], r12
0x18004a72d  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x18004a732  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x18004a737  mov     [rsp+1B0h+SubAuthority2], 20000h
0x18004a73f  call    cs:__imp_NtAlpcConnectPort
0x18004a746  nop     dword ptr [rax+rax+00h]
0x18004a74b  mov     ebx, eax
0x18004a74d  test    eax, eax
0x18004a74f  js      loc_18004A7D9
0x18004a755  cmp     eax, r13d
0x18004a758  jz      loc_18004A640
0x18004a75e  lea     rcx, [r14+4]; void *
0x18004a762  xor     edx, edx; Val
0x18004a764  mov     r8d, 574h; Size
0x18004a76a  call    memset_0
0x18004a76f  mov     rcx, [rbp+0B0h+Handle]
0x18004a773  lea     rax, [rsp+1B0h+var_140]
0x18004a778  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x18004a77d  mov     edi, 578h
0x18004a782  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x18004a787  xor     r9d, r9d
0x18004a78a  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x18004a78f  mov     r8, r15
0x18004a792  mov     edx, 20000h
0x18004a797  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x18004a79c  mov     dword ptr [r14], 5780550h
0x18004a7a3  mov     [rsp+1B0h+var_140], rdi
0x18004a7a8  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18004a7af  nop     dword ptr [rax+rax+00h]
0x18004a7b4  mov     ebx, eax
0x18004a7b6  test    eax, eax
0x18004a7b8  js      short loc_18004A7D9
0x18004a7ba  cmp     eax, r13d
0x18004a7bd  jz      short loc_18004A7D9
0x18004a7bf  mov     rax, [rsp+1B0h+var_140]
0x18004a7c4  sub     rax, rdi
0x18004a7c7  neg     rax
0x18004a7ca  sbb     ebx, ebx
0x18004a7cc  and     ebx, 0C000021Fh
0x18004a7d2  jmp     short loc_18004A7D9
0x18004a7d4  mov     ebx, 0C0000080h
0x18004a7d9  mov     rcx, [rsp+1B0h+var_138]; Sid
0x18004a7de  test    rcx, rcx
0x18004a7e1  jz      short loc_18004A7EF
0x18004a7e3  call    cs:__imp_RtlFreeSid
0x18004a7ea  nop     dword ptr [rax+rax+00h]
0x18004a7ef  mov     rcx, [rbp+0B0h+Handle]; Handle
0x18004a7f3  test    rcx, rcx
0x18004a7f6  jz      short loc_18004A804
0x18004a7f8  call    cs:__imp_NtClose
0x18004a7ff  nop     dword ptr [rax+rax+00h]
0x18004a804  mov     eax, ebx
0x18004a806  mov     rcx, [rbp+0B0h+var_40]
0x18004a80a  xor     rcx, rsp; StackCookie
0x18004a80d  call    __security_check_cookie
0x18004a812  mov     rbx, [rsp+1B0h+arg_0]
0x18004a81a  add     rsp, 180h
0x18004a821  pop     r15
0x18004a823  pop     r14
0x18004a825  pop     r13
0x18004a827  pop     r12
0x18004a829  pop     rdi
0x18004a82a  pop     rsi
0x18004a82b  pop     rbp
0x18004a82c  retn
```
