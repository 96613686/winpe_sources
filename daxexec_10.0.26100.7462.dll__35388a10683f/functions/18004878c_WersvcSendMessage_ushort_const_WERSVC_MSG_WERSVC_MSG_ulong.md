# WersvcSendMessage(ushort const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18004878c`
- end: `0x180048b67`
- name: `?WersvcSendMessage@@YAJPEBGPEAU_WERSVC_MSG@@1K@Z`
- size: `987`
- prototype: `int(const unsigned __int16 *, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180046504`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18004878c`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x180048ae8`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180048ae8`
- `ntdll!NtAlpcConnectPort` at `0x180048a83`
- `ntdll!NtAlpcConnectPort` at `0x180048a83`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800489d2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800489d2`
- `ntdll!NtQuerySystemInformation` at `0x1800488bc`
- `ntdll!NtQuerySystemInformation` at `0x1800488bc`
- `ntdll!NtClose` at `0x180048973`
- `ntdll!NtClose` at `0x180048b31`
- `ntdll!NtClose` at `0x180048973`
- `ntdll!NtClose` at `0x180048b31`
- `ntdll!NtWaitForSingleObject` at `0x180048960`
- `ntdll!NtWaitForSingleObject` at `0x180048960`
- `ntdll!NtOpenEvent` at `0x180048921`
- `ntdll!NtOpenEvent` at `0x180048921`
- `ntdll!EtwEventWriteNoRegistration` at `0x18004888a`
- `ntdll!EtwEventWriteNoRegistration` at `0x18004888a`
- `ntdll!ZwUpdateWnfStateData` at `0x180048861`
- `ntdll!ZwUpdateWnfStateData` at `0x180048861`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18004882c`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18004882c`
- `ntdll!RtlInitUnicodeString` at `0x180048a0d`
- `ntdll!RtlInitUnicodeString` at `0x180048a0d`
- `ntdll!RtlFreeSid` at `0x180048b1c`
- `ntdll!RtlFreeSid` at `0x180048b1c`

## string_xrefs

- `0x1800488d7`: `\KernelObjects\SystemErrorPortReady`
- `0x180048a02`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
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
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0 && (_DWORD)EventHandle )
    v6 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v31 = 0;
  v7 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v31, 0, 0);
  v8 = v6 + 1;
  if ( v7 )
    v8 = v6;
  if ( !v8 )
  {
    v9 = -1073741696;
    goto LABEL_28;
  }
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
LABEL_17:
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
          v33 = 1400;
          v13 = &v24;
          *((_QWORD *)&v26 + 1) = 0;
          DWORD2(v27) = 0;
          *(_QWORD *)&v27 = 0;
          if ( v5 )
            v13 = 0;
          v28 = 0;
          v14 = NtAlpcConnectPort(&Handle, &DestinationString, &v26, v32, 0x20000, Sid, 0, 0, 0, 0, v13);
          v9 = v14;
          if ( v14 >= 0 )
          {
            if ( v14 == 258 )
              goto LABEL_17;
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
0x18004878c  mov     [rsp-8+arg_0], rbx
0x180048791  push    rbp
0x180048792  push    rsi
0x180048793  push    rdi
0x180048794  push    r12
0x180048796  push    r13
0x180048798  push    r14
0x18004879a  push    r15
0x18004879c  lea     rbp, [rsp-80h]
0x1800487a1  sub     rsp, 180h
0x1800487a8  mov     rax, cs:__security_cookie
0x1800487af  xor     rax, rsp
0x1800487b2  mov     [rbp+0B0h+var_40], rax
0x1800487b6  xorps   xmm0, xmm0
0x1800487b9  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x1800487bf  xor     r12d, r12d
0x1800487c2  lea     rcx, [rbp+0B0h+var_90]; void *
0x1800487c6  mov     r14, r8
0x1800487c9  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r12d
0x1800487cd  mov     r15, rdx
0x1800487d0  xor     edx, edx; Val
0x1800487d2  movups  [rbp+0B0h+var_108], xmm0
0x1800487d6  lea     r8d, [r12+48h]; Size
0x1800487db  movups  [rbp+0B0h+var_F8], xmm0
0x1800487df  movups  [rbp+0B0h+var_E8], xmm0
0x1800487e3  call    memset_0
0x1800487e8  xorps   xmm0, xmm0
0x1800487eb  mov     [rbp+0B0h+var_120], r12
0x1800487ef  lea     edi, [r12+1]
0x1800487f4  mov     [rbp+0B0h+Handle], r12
0x1800487f8  mov     edx, edi
0x1800487fa  mov     [rsp+1B0h+var_138], r12
0x1800487ff  lea     r9, [rsp+1B0h+EventHandle]
0x180048804  mov     [rsp+1B0h+var_140], r12
0x180048809  xor     r8d, r8d
0x18004880c  mov     [rsp+1B0h+SystemInformation], r12
0x180048811  lea     rcx, WNF_WER_SERVICE_START
0x180048818  mov     dword ptr [rsp+1B0h+EventHandle], r12d
0x18004881d  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180048821  mov     ebx, r12d
0x180048824  mov     [rsp+1B0h+SubAuthority2], 4
0x18004882c  call    cs:__imp_ZwQueryWnfStateNameInformation
0x180048833  nop     dword ptr [rax+rax+00h]
0x180048838  test    eax, eax
0x18004883a  js      short loc_180048872
0x18004883c  cmp     dword ptr [rsp+1B0h+EventHandle], r12d
0x180048841  jz      short loc_180048872
0x180048843  mov     [rsp+1B0h+SubAuthority4], r12d
0x180048848  lea     rcx, WNF_WER_SERVICE_START
0x18004884f  mov     [rsp+1B0h+SubAuthority3], r12d
0x180048854  xor     r9d, r9d
0x180048857  xor     r8d, r8d
0x18004885a  mov     qword ptr [rsp+1B0h+SubAuthority2], r12
0x18004885f  xor     edx, edx
0x180048861  call    cs:__imp_ZwUpdateWnfStateData
0x180048868  nop     dword ptr [rax+rax+00h]
0x18004886d  test    eax, eax
0x18004886f  cmovns  ebx, edi
0x180048872  xorps   xmm0, xmm0
0x180048875  lea     rdx, [rbp+0B0h+var_A0]
0x180048879  xor     r9d, r9d
0x18004887c  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x180048883  xor     r8d, r8d
0x180048886  movups  [rbp+0B0h+var_A0], xmm0
0x18004888a  call    cs:__imp_EtwEventWriteNoRegistration
0x180048891  nop     dword ptr [rax+rax+00h]
0x180048896  test    eax, eax
0x180048898  lea     ecx, [rbx+1]
0x18004889b  cmovnz  ecx, ebx
0x18004889e  test    ecx, ecx
0x1800488a0  jnz     short loc_1800488AC
0x1800488a2  mov     ebx, 0C0000080h
0x1800488a7  jmp     loc_180048B12
0x1800488ac  xor     r9d, r9d; ReturnLength
0x1800488af  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x1800488b4  lea     r8d, [r9+8]; SystemInformationLength
0x1800488b8  lea     ecx, [r9+73h]; SystemInformationClass
0x1800488bc  call    cs:__imp_NtQuerySystemInformation
0x1800488c3  nop     dword ptr [rax+rax+00h]
0x1800488c8  mov     ebx, eax
0x1800488ca  test    eax, eax
0x1800488cc  js      loc_180048B12
0x1800488d2  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x1800488d7  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x1800488de  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x1800488e2  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x1800488e6  lea     rax, [rbp+0B0h+var_A0]
0x1800488ea  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x1800488f2  xorps   xmm0, xmm0
0x1800488f5  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x1800488f9  mov     edx, 100001h; DesiredAccess
0x1800488fe  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x180048906  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x18004890b  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r12
0x18004890f  mov     [rsp+1B0h+EventHandle], r12
0x180048914  mov     [rbp+0B0h+var_128], r12
0x180048918  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x18004891c  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180048921  call    cs:__imp_NtOpenEvent
0x180048928  nop     dword ptr [rax+rax+00h]
0x18004892d  mov     ebx, eax
0x18004892f  test    eax, eax
0x180048931  js      loc_180048B12
0x180048937  cmp     esi, 0FFFFFFFFh
0x18004893a  jnz     short loc_180048941
0x18004893c  mov     dl, dil
0x18004893f  jmp     short loc_18004894F
0x180048941  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x180048948  mov     dl, r12b
0x18004894b  mov     [rbp+0B0h+var_128], rcx
0x18004894f  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x180048954  lea     r8, [rbp+0B0h+var_128]
0x180048958  test    dl, dl
0x18004895a  cmovnz  r8, r12; Timeout
0x18004895e  xor     edx, edx; Alertable
0x180048960  call    cs:__imp_NtWaitForSingleObject
0x180048967  nop     dword ptr [rax+rax+00h]
0x18004896c  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x180048971  mov     ebx, eax
0x180048973  call    cs:__imp_NtClose
0x18004897a  nop     dword ptr [rax+rax+00h]
0x18004897f  test    ebx, ebx
0x180048981  js      loc_180048B12
0x180048987  mov     r13d, 102h
0x18004898d  cmp     ebx, r13d
0x180048990  jnz     short loc_18004899C
0x180048992  mov     ebx, 0C0000353h
0x180048997  jmp     loc_180048B12
0x18004899c  lea     rax, [rsp+1B0h+var_138]
0x1800489a1  xor     r9d, r9d; SubAuthority1
0x1800489a4  mov     [rsp+1B0h+Sid], rax; Sid
0x1800489a9  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x1800489ad  mov     [rsp+1B0h+SubAuthority7], r12d; SubAuthority7
0x1800489b2  mov     dl, dil; SubAuthorityCount
0x1800489b5  mov     [rsp+1B0h+SubAuthority6], r12d; SubAuthority6
0x1800489ba  mov     [rsp+1B0h+SubAuthority5], r12d; SubAuthority5
0x1800489bf  lea     r8d, [r9+12h]; SubAuthority0
0x1800489c3  mov     [rsp+1B0h+SubAuthority4], r12d; SubAuthority4
0x1800489c8  mov     [rsp+1B0h+SubAuthority3], r12d; SubAuthority3
0x1800489cd  mov     [rsp+1B0h+SubAuthority2], r12d; SubAuthority2
0x1800489d2  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800489d9  nop     dword ptr [rax+rax+00h]
0x1800489de  mov     ebx, eax
0x1800489e0  test    eax, eax
0x1800489e2  js      loc_180048B12
0x1800489e8  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x1800489ed  jz      short loc_180048A02
0x1800489ef  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x1800489f4  mov     dil, r12b
0x1800489f7  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1800489fe  mov     [rbp+0B0h+var_120], rcx
0x180048a02  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x180048a09  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180048a0d  call    cs:__imp_RtlInitUnicodeString
0x180048a14  nop     dword ptr [rax+rax+00h]
0x180048a19  mov     eax, 578h
0x180048a1e  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x180048a25  mov     [rbp+0B0h+var_80], rax
0x180048a29  lea     rsi, [rbp+0B0h+var_120]
0x180048a2d  mov     rax, [rsp+1B0h+var_138]
0x180048a32  lea     r9, [rbp+0B0h+var_90]
0x180048a36  xorps   xmm0, xmm0
0x180048a39  mov     qword ptr [rbp+0B0h+var_108+8], r12
0x180048a3d  test    dil, dil
0x180048a40  mov     dword ptr [rbp+0B0h+var_F8+8], r12d
0x180048a44  lea     r8, [rbp+0B0h+var_108]
0x180048a48  mov     qword ptr [rbp+0B0h+var_F8], r12
0x180048a4c  cmovnz  rsi, r12
0x180048a50  lea     rdx, [rbp+0B0h+DestinationString]
0x180048a54  mov     [rsp+1B0h+Sid], rsi
0x180048a59  lea     rcx, [rbp+0B0h+Handle]
0x180048a5d  mov     qword ptr [rsp+1B0h+SubAuthority7], r12
0x180048a62  mov     qword ptr [rsp+1B0h+SubAuthority6], r12
0x180048a67  mov     qword ptr [rsp+1B0h+SubAuthority5], r12
0x180048a6c  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x180048a71  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x180048a76  mov     [rsp+1B0h+SubAuthority2], 20000h
0x180048a7e  movdqu  [rbp+0B0h+var_E8], xmm0
0x180048a83  call    cs:__imp_NtAlpcConnectPort
0x180048a8a  nop     dword ptr [rax+rax+00h]
0x180048a8f  mov     ebx, eax
0x180048a91  test    eax, eax
0x180048a93  js      short loc_180048B12
0x180048a95  cmp     eax, r13d
0x180048a98  jz      loc_180048992
0x180048a9e  lea     rcx, [r14+4]; void *
0x180048aa2  xor     edx, edx; Val
0x180048aa4  mov     r8d, 574h; Size
0x180048aaa  call    memset_0
0x180048aaf  mov     rcx, [rbp+0B0h+Handle]
0x180048ab3  lea     rax, [rsp+1B0h+var_140]
0x180048ab8  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x180048abd  mov     edi, 578h
0x180048ac2  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x180048ac7  xor     r9d, r9d
0x180048aca  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x180048acf  mov     r8, r15
0x180048ad2  mov     edx, 20000h
0x180048ad7  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x180048adc  mov     dword ptr [r14], 5780550h
0x180048ae3  mov     [rsp+1B0h+var_140], rdi
0x180048ae8  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180048aef  nop     dword ptr [rax+rax+00h]
0x180048af4  mov     ebx, eax
0x180048af6  test    eax, eax
0x180048af8  js      short loc_180048B12
0x180048afa  cmp     eax, r13d
0x180048afd  jz      short loc_180048B12
0x180048aff  mov     rax, [rsp+1B0h+var_140]
0x180048b04  sub     rax, rdi
0x180048b07  neg     rax
0x180048b0a  sbb     ebx, ebx
0x180048b0c  and     ebx, 0C000021Fh
0x180048b12  mov     rcx, [rsp+1B0h+var_138]; Sid
0x180048b17  test    rcx, rcx
0x180048b1a  jz      short loc_180048B28
0x180048b1c  call    cs:__imp_RtlFreeSid
0x180048b23  nop     dword ptr [rax+rax+00h]
0x180048b28  mov     rcx, [rbp+0B0h+Handle]; Handle
0x180048b2c  test    rcx, rcx
0x180048b2f  jz      short loc_180048B3D
0x180048b31  call    cs:__imp_NtClose
0x180048b38  nop     dword ptr [rax+rax+00h]
0x180048b3d  mov     eax, ebx
0x180048b3f  mov     rcx, [rbp+0B0h+var_40]
0x180048b43  xor     rcx, rsp; StackCookie
0x180048b46  call    __security_check_cookie
0x180048b4b  mov     rbx, [rsp+1B0h+arg_0]
0x180048b53  add     rsp, 180h
0x180048b5a  pop     r15
0x180048b5c  pop     r14
0x180048b5e  pop     r13
0x180048b60  pop     r12
0x180048b62  pop     rdi
0x180048b63  pop     rsi
0x180048b64  pop     rbp
0x180048b65  retn
```
