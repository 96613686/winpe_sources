# DfsUpdateRootRemoteServerName(ushort const *,ushort const *,ushort const *,ushort const *,uchar)

- ea: `0x14003ea74`
- end: `0x14003ec90`
- name: `?DfsUpdateRootRemoteServerName@@YAKPEBG000E@Z`
- size: `540`
- prototype: `unsigned int __usercall@<eax>(PCWSTR SourceString@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int8)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x14000c2bc`
- `0x14000dd80`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x14000aed8`
- `0x140032e44`
- `0x140032eac`
- `0x1400333f0`
- `0x14003e95c`
- `0x14003ea74`
- `0x140049758`
- `0x14004ac38`
- `0x140058a38`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14003eacc`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003eacc`
- `ntdll!RtlNtStatusToDosError` at `0x14003eae0`
- `ntdll!RtlNtStatusToDosError` at `0x14003eae0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14003ec29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14003ec29`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14003ec13`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14003ec13`
- `WLDAP32!__imp_ldap_modify_sW` at `0x14003ebfb`
- `WLDAP32!__imp_ldap_modify_sW` at `0x14003ebfb`

## pseudocode

```c
__int64 __fastcall DfsUpdateRootRemoteServerName(
        PCWSTR SourceString,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 a5)
{
  int inited; // eax
  ULONG NamespaceDn; // edi
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  int v16; // eax
  unsigned int LastError; // eax
  struct CLocalMachine *Instance; // rax
  CLdap *v19; // rcx
  signed int v20; // ebx
  CLdap *v21; // rcx
  PWSTR dn; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v25; // [rsp+40h] [rbp-C0h]
  _QWORD *v26; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  LDAPModW *mods[2]; // [rsp+70h] [rbp-90h] BYREF
  LDAP *ld[132]; // [rsp+80h] [rbp-80h] BYREF

  DestinationString = 0;
  CLdap::CLdap((CLdap *)ld);
  dn = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
  {
    NamespaceDn = RtlNtStatusToDosError(inited);
    goto LABEL_23;
  }
  NamespaceDn = DfsMakeNamespaceDn(&DestinationString, 0, &dn);
  if ( !NamespaceDn )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    NamespaceDn = 2;
    v13 = v11 + v12 + 4;
    v14 = (unsigned __int16 *)operator new(saturated_mul(v13, 2u));
    v15 = v14;
    if ( !v14 )
    {
      NamespaceDn = 8;
      goto LABEL_21;
    }
    v16 = StringCchPrintfW(v14, v13, L"\\\\%s\\%s", a3, a4);
    if ( v16 >= 0 )
    {
      Instance = CLocalMachine::_GetInstance(0);
      if ( (unsigned int)CLdap::Bind((CLdap *)ld, *((const unsigned __int16 **)Instance + 6), a2) )
      {
        v24[0] = a5 == 0;
        v25 = L"remoteServerName";
        v26 = v28;
        mods[0] = (LDAPModW *)v24;
        v24[1] = 0;
        v28[0] = v15;
        v28[1] = 0;
        mods[1] = 0;
        v20 = ldap_modify_sW(ld[0], dn, mods);
        TlsSetValue(CLdap::gm_LdapErrorTlsIndex, (LPVOID)v20);
        if ( v20 )
        {
          if ( (unsigned int)TlsGetValue(CLdap::gm_LdapErrorTlsIndex) != 16 )
            NamespaceDn = CLdap::GetLastError(v21);
        }
        else
        {
          NamespaceDn = 0;
        }
        goto LABEL_20;
      }
      LastError = CLdap::GetLastError(v19);
    }
    else
    {
      LastError = DfsGetErrorFromHr(v16);
    }
    NamespaceDn = LastError;
LABEL_20:
    operator delete(v15);
  }
LABEL_21:
  if ( dn )
    operator delete(dn);
LABEL_23:
  CLdap::Deinit((CLdap *)ld);
  return NamespaceDn;
}

```

## disassembly

```asm
0x14003ea74  push    rbp
0x14003ea76  push    rbx
0x14003ea77  push    rdi
0x14003ea78  push    r12
0x14003ea7a  push    r13
0x14003ea7c  push    r14
0x14003ea7e  push    r15
0x14003ea80  lea     rbp, [rsp-3B0h]
0x14003ea88  sub     rsp, 4B0h
0x14003ea8f  mov     rax, cs:__security_cookie
0x14003ea96  xor     rax, rsp
0x14003ea99  mov     [rbp+3E0h+var_40], rax
0x14003eaa0  mov     rbx, rcx
0x14003eaa3  xorps   xmm0, xmm0
0x14003eaa6  lea     rcx, [rbp+3E0h+ld]; this
0x14003eaaa  mov     r12, r9
0x14003eaad  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x14003eab2  mov     r15, r8
0x14003eab5  mov     r13, rdx
0x14003eab8  call    ??0CLdap@@QEAA@XZ; CLdap::CLdap(void)
0x14003eabd  xor     eax, eax
0x14003eabf  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x14003eac4  mov     rdx, rbx; SourceString
0x14003eac7  mov     [rsp+4E0h+dn], rax
0x14003eacc  call    cs:__imp_RtlInitUnicodeStringEx
0x14003ead3  nop     dword ptr [rax+rax+00h]
0x14003ead8  xor     ebx, ebx
0x14003eada  test    eax, eax
0x14003eadc  jns     short loc_14003EAF3
0x14003eade  mov     ecx, eax; Status
0x14003eae0  call    cs:__imp_RtlNtStatusToDosError
0x14003eae7  nop     dword ptr [rax+rax+00h]
0x14003eaec  mov     edi, eax
0x14003eaee  jmp     loc_14003EC62
0x14003eaf3  lea     r8, [rsp+4E0h+dn]; unsigned __int16 **
0x14003eaf8  xor     edx, edx; unsigned __int8
0x14003eafa  lea     rcx, [rsp+4E0h+DestinationString]; struct _UNICODE_STRING *
0x14003eaff  call    ?DfsMakeNamespaceDn@@YAKPEBU_UNICODE_STRING@@EPEAPEAG@Z; DfsMakeNamespaceDn(_UNICODE_STRING const *,uchar,ushort * *)
0x14003eb04  mov     edi, eax
0x14003eb06  test    eax, eax
0x14003eb08  jnz     loc_14003EC51
0x14003eb0e  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003eb12  mov     rax, r8
0x14003eb15  inc     rax
0x14003eb18  cmp     [r15+rax*2], bx
0x14003eb1d  jnz     short loc_14003EB15
0x14003eb1f  mov     rcx, r8
0x14003eb22  inc     rcx
0x14003eb25  cmp     [r12+rcx*2], bx
0x14003eb2a  jnz     short loc_14003EB22
0x14003eb2c  lea     rbx, [rcx+4]
0x14003eb30  mov     edi, 2
0x14003eb35  add     rbx, rax
0x14003eb38  mov     eax, edi
0x14003eb3a  mul     rbx
0x14003eb3d  cmovo   rax, r8
0x14003eb41  mov     rcx, rax; Size
0x14003eb44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003eb49  mov     r14, rax
0x14003eb4c  test    rax, rax
0x14003eb4f  jnz     short loc_14003EB5B
0x14003eb51  lea     edi, [rax+8]
0x14003eb54  xor     ebx, ebx
0x14003eb56  jmp     loc_14003EC51
0x14003eb5b  mov     r9, r15
0x14003eb5e  mov     [rsp+4E0h+var_4C0], r12
0x14003eb63  lea     r8, aSS_3; "\\\\%s\\%s"
0x14003eb6a  mov     rdx, rbx; unsigned __int64
0x14003eb6d  mov     rcx, r14; unsigned __int16 *
0x14003eb70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003eb75  xor     ebx, ebx
0x14003eb77  test    eax, eax
0x14003eb79  jns     short loc_14003EB89
0x14003eb7b  mov     ecx, eax; int
0x14003eb7d  call    ?DfsGetErrorFromHr@@YAKJ@Z; DfsGetErrorFromHr(long)
0x14003eb82  mov     edi, eax
0x14003eb84  jmp     loc_14003EC49
0x14003eb89  xor     ecx, ecx; unsigned int *
0x14003eb8b  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x14003eb90  mov     r8, r13; unsigned __int16 *
0x14003eb93  lea     rcx, [rbp+3E0h+ld]; this
0x14003eb97  mov     rdx, [rax+30h]; unsigned __int16 *
0x14003eb9b  call    ?Bind@CLdap@@QEAAHPEBG0@Z; CLdap::Bind(ushort const *,ushort const *)
0x14003eba0  test    eax, eax
0x14003eba2  jnz     short loc_14003EBAB
0x14003eba4  call    ?GetLastError@CLdap@@QEAAKXZ; CLdap::GetLastError(void)
0x14003eba9  jmp     short loc_14003EB82
0x14003ebab  cmp     [rbp+3E0h+arg_20], bl
0x14003ebb1  lea     r8, [rsp+4E0h+mods]; mods
0x14003ebb6  mov     rdx, [rsp+4E0h+dn]; dn
0x14003ebbb  mov     eax, ebx
0x14003ebbd  mov     rcx, [rbp+3E0h+ld]; ld
0x14003ebc1  setz    al
0x14003ebc4  mov     [rsp+4E0h+var_4A8], eax
0x14003ebc8  lea     rax, aRemoteserverna; "remoteServerName"
0x14003ebcf  mov     [rsp+4E0h+var_4A0], rax
0x14003ebd4  lea     rax, [rsp+4E0h+var_480]
0x14003ebd9  mov     [rsp+4E0h+var_498], rax
0x14003ebde  lea     rax, [rsp+4E0h+var_4A8]
0x14003ebe3  mov     [rsp+4E0h+mods], rax
0x14003ebe8  mov     [rsp+4E0h+var_4A4], ebx
0x14003ebec  mov     [rsp+4E0h+var_480], r14
0x14003ebf1  mov     [rsp+4E0h+var_478], rbx
0x14003ebf6  mov     [rsp+4E0h+var_468], rbx
0x14003ebfb  call    cs:__imp_ldap_modify_sW
0x14003ec02  nop     dword ptr [rax+rax+00h]
0x14003ec07  mov     ecx, cs:?gm_LdapErrorTlsIndex@CLdap@@0KA; dwTlsIndex
0x14003ec0d  movsxd  rbx, eax
0x14003ec10  mov     rdx, rbx; lpTlsValue
0x14003ec13  call    cs:__imp_TlsSetValue
0x14003ec1a  nop     dword ptr [rax+rax+00h]
0x14003ec1f  test    ebx, ebx
0x14003ec21  jz      short loc_14003EC45
0x14003ec23  mov     ecx, cs:?gm_LdapErrorTlsIndex@CLdap@@0KA; dwTlsIndex
0x14003ec29  call    cs:__imp_TlsGetValue
0x14003ec30  nop     dword ptr [rax+rax+00h]
0x14003ec35  cmp     eax, 10h
0x14003ec38  jz      short loc_14003EC41
0x14003ec3a  call    ?GetLastError@CLdap@@QEAAKXZ; CLdap::GetLastError(void)
0x14003ec3f  mov     edi, eax
0x14003ec41  xor     ebx, ebx
0x14003ec43  jmp     short loc_14003EC49
0x14003ec45  xor     ebx, ebx
0x14003ec47  mov     edi, ebx
0x14003ec49  mov     rcx, r14; Block
0x14003ec4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003ec51  cmp     [rsp+4E0h+dn], rbx
0x14003ec56  jz      short loc_14003EC62
0x14003ec58  mov     rcx, [rsp+4E0h+dn]; Block
0x14003ec5d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003ec62  lea     rcx, [rbp+3E0h+ld]; this
0x14003ec66  call    ?Deinit@CLdap@@AEAAXXZ; CLdap::Deinit(void)
0x14003ec6b  mov     eax, edi
0x14003ec6d  mov     rcx, [rbp+3E0h+var_40]
0x14003ec74  xor     rcx, rsp; StackCookie
0x14003ec77  call    __security_check_cookie
0x14003ec7c  add     rsp, 4B0h
0x14003ec83  pop     r15
0x14003ec85  pop     r14
0x14003ec87  pop     r13
0x14003ec89  pop     r12
0x14003ec8b  pop     rdi
0x14003ec8c  pop     rbx
0x14003ec8d  pop     rbp
0x14003ec8e  retn
```
