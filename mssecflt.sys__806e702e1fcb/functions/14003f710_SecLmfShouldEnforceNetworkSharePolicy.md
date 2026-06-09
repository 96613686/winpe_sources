# SecLmfShouldEnforceNetworkSharePolicy

- ea: `0x14003f710`
- end: `0x14003fa27`
- name: `SecLmfShouldEnforceNetworkSharePolicy`
- size: `791`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003fa28`

## callees

- `0x140009c58`
- `0x140011650`
- `0x1400119c0`
- `0x140026a80`
- `0x140029598`
- `0x14003e234`
- `0x14003f710`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14003f827`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003f827`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003f9f0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003f9f0`
- `ntoskrnl!SeAccessCheck` at `0x14003f935`
- `ntoskrnl!SeAccessCheck` at `0x14003f935`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003f8ed`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003f8ed`
- `ntoskrnl!RtlIpv4AddressToStringW` at `0x14003f7e6`
- `ntoskrnl!RtlIpv4AddressToStringW` at `0x14003f7e6`
- `ntoskrnl!RtlIpv6AddressToStringW` at `0x14003f802`
- `ntoskrnl!RtlIpv6AddressToStringW` at `0x14003f802`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003f817`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003f817`

## pseudocode

```c
bool __fastcall SecLmfShouldEnforceNetworkSharePolicy(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  bool v4; // r15
  ACCESS_MASK v5; // r12d
  unsigned int i; // edi
  _QWORD *v7; // rdx
  unsigned int v8; // esi
  void *v9; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  char v11; // bl
  int AccessStatus; // [rsp+70h] [rbp-90h] BYREF
  DWORD GrantedAccess; // [rsp+74h] [rbp-8Ch] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+88h] [rbp-78h] BYREF
  WCHAR S[72]; // [rsp+B0h] [rbp-50h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  v4 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(S, 0, 0x82u);
  DestinationString = 0;
  if ( SecLmfInitialized )
  {
    if ( SecLmfNetworkSharePolicyConfigCount )
    {
      v5 = *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16);
      if ( (unsigned int)SecPopulateFileShareContext(*(PFLT_FILTER *)(a2 + 8)) - 2 <= 1 )
      {
        RtlInitUnicodeString(&DestinationString, S);
        SeCaptureSubjectContext(&SubjectContext);
        for ( i = 0; i < SecLmfNetworkSharePolicyConfigCount; ++i )
        {
          if ( !*((_BYTE *)SecLmfNetworkSharePolicyConfig + 72 * i + 8)
            || (v5 & *((_DWORD *)SecLmfNetworkSharePolicyConfig + 18 * i + 3)) == 0
            || *((_BYTE *)SecLmfNetworkSharePolicyConfig + 72 * i + 11) )
          {
            continue;
          }
          if ( *((_BYTE *)SecLmfNetworkSharePolicyConfig + 72 * i + 10) )
          {
            if ( (unsigned __int8)SecIsInNameArray(*((_QWORD *)SecLmfNetworkSharePolicyConfig + 9 * i + 3), 0) )
              continue;
          }
          else if ( !(unsigned __int8)SecIsInNameArray(*((_QWORD *)SecLmfNetworkSharePolicyConfig + 9 * i + 2), 0) )
          {
            continue;
          }
          v7 = SecLmfNetworkSharePolicyConfig;
          if ( *((_DWORD *)SecLmfNetworkSharePolicyConfig + 18 * i + 8) )
          {
            v8 = 0;
            while ( 1 )
            {
              v9 = *(void **)(v7[9 * i + 5] + 8LL * v8);
              GenericMapping = IoGetFileObjectGenericMapping();
              if ( !SeAccessCheck(v9, &SubjectContext, 0, v5, 0, 0, GenericMapping, 1, &GrantedAccess, &AccessStatus) )
                break;
              v7 = SecLmfNetworkSharePolicyConfig;
              if ( ++v8 >= *((_DWORD *)SecLmfNetworkSharePolicyConfig + 18 * i + 8) )
                goto LABEL_22;
            }
          }
          if ( *((_BYTE *)SecLmfNetworkSharePolicyConfig + 72 * i + 48) )
          {
            if ( !(unsigned __int8)SecIsInNameArray(
                                     *((_QWORD *)SecLmfNetworkSharePolicyConfig + 9 * i + 8),
                                     &DestinationString) )
            {
LABEL_21:
              v11 = *((_BYTE *)SecLmfNetworkSharePolicyConfig + 72 * i + 9);
              v4 = v11 == 0;
              SecAuditFileAccessBlock(
                CallbackData,
                *((_DWORD *)SecLmfNetworkSharePolicyConfig + 18 * i + 1),
                (__int64)&Event56);
              if ( !v11 )
                break;
            }
          }
          else if ( (unsigned __int8)SecIsInNameArray(
                                       *((_QWORD *)SecLmfNetworkSharePolicyConfig + 9 * i + 7),
                                       &DestinationString) )
          {
            goto LABEL_21;
          }
LABEL_22:
          ;
        }
        SeReleaseSubjectContext(&SubjectContext);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14003f710  mov     [rsp-8+arg_10], rbx
0x14003f715  push    rbp
0x14003f716  push    rsi
0x14003f717  push    rdi
0x14003f718  push    r12
0x14003f71a  push    r13
0x14003f71c  push    r14
0x14003f71e  push    r15
0x14003f720  lea     rbp, [rsp-50h]
0x14003f725  sub     rsp, 150h
0x14003f72c  mov     rax, cs:__security_cookie
0x14003f733  xor     rax, rsp
0x14003f736  mov     [rbp+80h+var_40], rax
0x14003f73a  xor     r14d, r14d
0x14003f73d  mov     [rsp+180h+var_128], rdx
0x14003f742  xorps   xmm0, xmm0
0x14003f745  mov     [rsp+180h+var_118], r14
0x14003f74a  mov     rsi, rdx
0x14003f74d  mov     [rsp+180h+var_120], r14
0x14003f752  mov     r13, rcx
0x14003f755  mov     [rsp+180h+var_10C], r14d
0x14003f75a  xor     edx, edx; Val
0x14003f75c  mov     [rsp+180h+var_110], r14d
0x14003f761  lea     rcx, [rbp+80h+S]; void *
0x14003f765  mov     r8d, 82h; Size
0x14003f76b  mov     r15b, r14b
0x14003f76e  movups  xmmword ptr [rbp+80h+SubjectContext.ClientToken], xmm0
0x14003f772  movups  xmmword ptr [rbp+80h+SubjectContext.PrimaryToken], xmm0
0x14003f776  call    memset
0x14003f77b  cmp     cs:SecLmfInitialized, r14b
0x14003f782  xorps   xmm0, xmm0
0x14003f785  movups  xmmword ptr [rsp+180h+DestinationString.Length], xmm0
0x14003f78a  jz      loc_14003F9FC
0x14003f790  cmp     cs:SecLmfNetworkSharePolicyConfigCount, r14d
0x14003f797  jz      loc_14003F9FC
0x14003f79d  mov     rax, [r13+10h]
0x14003f7a1  lea     r9, [rsp+180h+var_120]
0x14003f7a6  lea     r8, [rsp+180h+var_118]
0x14003f7ab  mov     rdx, r13
0x14003f7ae  mov     rcx, [rax+18h]
0x14003f7b2  mov     r12d, [rcx+10h]
0x14003f7b6  mov     rcx, [rsi+8]; Filter
0x14003f7ba  call    SecPopulateFileShareContext
0x14003f7bf  add     eax, 0FFFFFFFEh
0x14003f7c2  cmp     eax, 1
0x14003f7c5  ja      loc_14003F9FC
0x14003f7cb  mov     rcx, [rsp+180h+var_120]
0x14003f7d0  test    rcx, rcx
0x14003f7d3  jz      short loc_14003F80E
0x14003f7d5  movzx   eax, word ptr [rcx]
0x14003f7d8  cmp     ax, 2
0x14003f7dc  jnz     short loc_14003F7F4
0x14003f7de  add     rcx, 4; Addr
0x14003f7e2  lea     rdx, [rbp+80h+S]; S
0x14003f7e6  call    cs:__imp_RtlIpv4AddressToStringW
0x14003f7ed  nop     dword ptr [rax+rax+00h]
0x14003f7f2  jmp     short loc_14003F80E
0x14003f7f4  cmp     ax, 17h
0x14003f7f8  jnz     short loc_14003F80E
0x14003f7fa  add     rcx, 8; Addr
0x14003f7fe  lea     rdx, [rbp+80h+S]; S
0x14003f802  call    cs:__imp_RtlIpv6AddressToStringW
0x14003f809  nop     dword ptr [rax+rax+00h]
0x14003f80e  lea     rdx, [rbp+80h+S]; SourceString
0x14003f812  lea     rcx, [rsp+180h+DestinationString]; DestinationString
0x14003f817  call    cs:__imp_RtlInitUnicodeString
0x14003f81e  nop     dword ptr [rax+rax+00h]
0x14003f823  lea     rcx, [rbp+80h+SubjectContext]; SubjectContext
0x14003f827  call    cs:__imp_SeCaptureSubjectContext
0x14003f82e  nop     dword ptr [rax+rax+00h]
0x14003f833  cmp     cs:SecLmfNetworkSharePolicyConfigCount, r14d
0x14003f83a  mov     edi, r14d
0x14003f83d  jz      loc_14003F9EC
0x14003f843  mov     rcx, cs:SecLmfNetworkSharePolicyConfig
0x14003f84a  mov     eax, edi
0x14003f84c  lea     rbx, [rax+rax*8]
0x14003f850  cmp     [rcx+rbx*8+8], r14b
0x14003f855  jz      loc_14003F9D9
0x14003f85b  test    [rcx+rbx*8+0Ch], r12d
0x14003f860  jz      loc_14003F9D9
0x14003f866  cmp     [rcx+rbx*8+0Bh], r14b
0x14003f86b  jz      short loc_14003F888
0x14003f86d  mov     rcx, [rsp+180h+var_120]
0x14003f872  test    rcx, rcx
0x14003f875  jz      loc_14003F9D9
0x14003f87b  call    SecNetIsIpAddressInTableAvl
0x14003f880  test    al, al
0x14003f882  jnz     loc_14003F9D9
0x14003f888  mov     rcx, cs:SecLmfNetworkSharePolicyConfig
0x14003f88f  mov     rdx, [rsp+180h+var_118]
0x14003f894  cmp     [rcx+rbx*8+0Ah], r14b
0x14003f899  jnz     short loc_14003F8AF
0x14003f89b  mov     rcx, [rcx+rbx*8+10h]
0x14003f8a0  call    SecIsInNameArray
0x14003f8a5  test    al, al
0x14003f8a7  jz      loc_14003F9D9
0x14003f8ad  jmp     short loc_14003F8C1
0x14003f8af  mov     rcx, [rcx+rbx*8+18h]
0x14003f8b4  call    SecIsInNameArray
0x14003f8b9  test    al, al
0x14003f8bb  jnz     loc_14003F9D9
0x14003f8c1  mov     rdx, cs:SecLmfNetworkSharePolicyConfig
0x14003f8c8  mov     eax, edi
0x14003f8ca  lea     rcx, [rax+rax*8]
0x14003f8ce  cmp     [rdx+rcx*8+20h], r14d
0x14003f8d3  jbe     loc_14003F962
0x14003f8d9  mov     eax, edi
0x14003f8db  mov     esi, r14d
0x14003f8de  lea     r14, [rax+rax*8]
0x14003f8e2  mov     rax, [rdx+r14*8+28h]
0x14003f8e7  mov     ecx, esi
0x14003f8e9  mov     rbx, [rax+rcx*8]
0x14003f8ed  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003f8f4  nop     dword ptr [rax+rax+00h]
0x14003f8f9  lea     rcx, [rsp+180h+var_110]
0x14003f8fe  mov     r9d, r12d; DesiredAccess
0x14003f901  mov     [rsp+180h+AccessStatus], rcx; AccessStatus
0x14003f906  lea     rdx, [rbp+80h+SubjectContext]; SubjectSecurityContext
0x14003f90a  lea     rcx, [rsp+180h+var_10C]
0x14003f90f  xor     r8d, r8d; SubjectContextLocked
0x14003f912  mov     [rsp+180h+GrantedAccess], rcx; GrantedAccess
0x14003f917  mov     rcx, rbx; SecurityDescriptor
0x14003f91a  mov     [rsp+180h+AccessMode], 1; AccessMode
0x14003f91f  mov     [rsp+180h+GenericMapping], rax; GenericMapping
0x14003f924  mov     [rsp+180h+Privileges], 0; Privileges
0x14003f92d  mov     [rsp+180h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14003f935  call    cs:__imp_SeAccessCheck
0x14003f93c  nop     dword ptr [rax+rax+00h]
0x14003f941  test    al, al
0x14003f943  jz      short loc_14003F95A
0x14003f945  mov     rdx, cs:SecLmfNetworkSharePolicyConfig
0x14003f94c  inc     esi
0x14003f94e  cmp     esi, [rdx+r14*8+20h]
0x14003f953  jb      short loc_14003F8E2
0x14003f955  xor     r14d, r14d
0x14003f958  jmp     short loc_14003F9D9
0x14003f95a  mov     rsi, [rsp+180h+var_128]
0x14003f95f  xor     r14d, r14d
0x14003f962  mov     eax, edi
0x14003f964  lea     rdx, [rsp+180h+DestinationString]
0x14003f969  lea     rcx, [rax+rax*8]
0x14003f96d  mov     rax, cs:SecLmfNetworkSharePolicyConfig
0x14003f974  cmp     [rax+rcx*8+30h], r14b
0x14003f979  jnz     short loc_14003F98B
0x14003f97b  mov     rcx, [rax+rcx*8+38h]
0x14003f980  call    SecIsInNameArray
0x14003f985  test    al, al
0x14003f987  jz      short loc_14003F9D9
0x14003f989  jmp     short loc_14003F999
0x14003f98b  mov     rcx, [rax+rcx*8+40h]
0x14003f990  call    SecIsInNameArray
0x14003f995  test    al, al
0x14003f997  jnz     short loc_14003F9D9
0x14003f999  mov     eax, edi
0x14003f99b  lea     rdx, Event56
0x14003f9a2  mov     [rsp+180h+Privileges], rdx; __int64
0x14003f9a7  mov     r9b, 1
0x14003f9aa  mov     rdx, rsi
0x14003f9ad  lea     rcx, [rax+rax*8]
0x14003f9b1  mov     rax, cs:SecLmfNetworkSharePolicyConfig
0x14003f9b8  mov     bl, [rax+rcx*8+9]
0x14003f9bc  mov     eax, [rax+rcx*8+4]
0x14003f9c0  test    bl, bl
0x14003f9c2  mov     rcx, r13; CallbackData
0x14003f9c5  mov     [rsp+180h+PreviouslyGrantedAccess], eax; int
0x14003f9c9  setz    r15b
0x14003f9cd  mov     r8b, r15b
0x14003f9d0  call    SecAuditFileAccessBlock
0x14003f9d5  test    bl, bl
0x14003f9d7  jz      short loc_14003F9EC
0x14003f9d9  mov     rsi, [rsp+180h+var_128]
0x14003f9de  inc     edi
0x14003f9e0  cmp     edi, cs:SecLmfNetworkSharePolicyConfigCount
0x14003f9e6  jb      loc_14003F843
0x14003f9ec  lea     rcx, [rbp+80h+SubjectContext]; SubjectContext
0x14003f9f0  call    cs:__imp_SeReleaseSubjectContext
0x14003f9f7  nop     dword ptr [rax+rax+00h]
0x14003f9fc  mov     al, r15b
0x14003f9ff  mov     rcx, [rbp+80h+var_40]
0x14003fa03  xor     rcx, rsp; StackCookie
0x14003fa06  call    __security_check_cookie
0x14003fa0b  mov     rbx, [rsp+180h+arg_10]
0x14003fa13  add     rsp, 150h
0x14003fa1a  pop     r15
0x14003fa1c  pop     r14
0x14003fa1e  pop     r13
0x14003fa20  pop     r12
0x14003fa22  pop     rdi
0x14003fa23  pop     rsi
0x14003fa24  pop     rbp
0x14003fa25  retn
```
