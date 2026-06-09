# _SetupNetworkDefaultProfilePath(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)

- ea: `0x18001e380`
- end: `0x18001e64f`
- name: `?_SetupNetworkDefaultProfilePath@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z`
- size: `719`
- prototype: `__int64 __fastcall(struct _PROFILEINFOW *, const struct _SN_ONLOGON_PARAMS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ce78`

## callees

- `0x180005370`
- `0x18000b060`
- `0x18000d030`
- `0x18000e1a0`
- `0x18001e380`
- `0x18001e658`
- `0x180024260`
- `0x180030ad0`
- `0x18003bc70`
- `0x18005041c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e452`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e43b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e43b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001e526`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001e526`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001e3ed`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001e498`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001e3ed`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18001e498`
- `ntdll!RtlNtStatusToDosError` at `0x18001e3fb`
- `ntdll!RtlNtStatusToDosError` at `0x18001e3fb`

## pseudocode

```c
__int64 __fastcall _SetupNetworkDefaultProfilePath(struct _PROFILEINFOW *a1, const struct _SN_ONLOGON_PARAMS *a2)
{
  __int64 v2; // rsi
  unsigned __int16 *v4; // rdi
  NTSTATUS EnvironmentVariable; // eax
  signed int v6; // eax
  signed int v7; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax
  int v10; // eax
  unsigned __int64 v11; // rax
  int RoamingVersionExtension; // eax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-59h]
  DWORD nSize[2]; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-41h] BYREF
  __int64 v18; // [rsp+40h] [rbp-39h]
  __int64 v19; // [rsp+48h] [rbp-31h]
  WCHAR *v20; // [rsp+50h] [rbp-29h] BYREF
  __int64 v21; // [rsp+58h] [rbp-21h]
  __int64 v22; // [rsp+60h] [rbp-19h]
  unsigned __int16 *v23; // [rsp+68h] [rbp-11h] BYREF
  __int64 v24; // [rsp+70h] [rbp-9h]
  __int64 v25; // [rsp+78h] [rbp-1h]
  WCHAR Buffer[16]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = *((_QWORD *)a2 + 4);
  v23 = 0;
  v24 = -1;
  v25 = -1;
  *(_QWORD *)nSize = 0;
  v15 = 0;
  v4 = 0;
  EnvironmentVariable = RtlQueryEnvironmentVariable(v2, L"LOGONSERVER", 11, 0);
  v6 = RtlNtStatusToDosError(EnvironmentVariable);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 == -2147024774 )
  {
    v23 = 0;
    if ( is_mul_ok(*(unsigned __int64 *)nSize, 2u) )
    {
      ProcessHeap = GetProcessHeap();
      v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2LL * *(_QWORD *)nSize);
      v23 = v9;
      v7 = -2147024882;
      v4 = v9;
      if ( v9 )
      {
        v15 = nSize[0];
        v10 = RtlQueryEnvironmentVariable(v2, L"LOGONSERVER", 11, v9);
        v7 = ResultFromWin32FromStatus(v10);
        if ( v7 < 0 )
        {
          ResultFromHeapFree(v4);
          v4 = 0;
          v23 = 0;
        }
      }
    }
    else
    {
      v7 = -2147024362;
    }
  }
  if ( v7 != -2147024693 )
  {
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29A,
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)v7,
        v15);
LABEL_25:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v23);
      return (unsigned int)v7;
    }
    nSize[0] = 16;
    if ( v4 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v4[v11] );
    }
    else
    {
      v11 = 0;
    }
    v24 = v11;
    if ( v11 <= 2 || !GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize) || !StringIsEqual(v4 + 2, Buffer) )
    {
      v17 = 0;
      v18 = 0;
      v19 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
      v18 = -1;
      v19 = -1;
      RoamingVersionExtension = GetRoamingVersionExtension(&v17);
      v7 = RoamingVersionExtension;
      if ( RoamingVersionExtension < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A5,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)RoamingVersionExtension,
          v15);
LABEL_24:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
        goto LABEL_25;
      }
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
              &v20,
              L"%s\\NETLOGON\\Default User%s",
              v4,
              v17);
      v7 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A8,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)v13,
          v15);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v20);
        goto LABEL_24;
      }
      a1->lpDefaultPath = v20;
      v20 = 0;
      v22 = 0;
      v21 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v20);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
    }
  }
  if ( v4 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v4);
  return 0;
}

```

## disassembly

```asm
0x18001e380  mov     [rsp-8+arg_10], rbx
0x18001e385  mov     [rsp-8+arg_18], rsi
0x18001e38a  push    rbp
0x18001e38b  push    rdi
0x18001e38c  push    r12
0x18001e38e  push    r14
0x18001e390  push    r15
0x18001e392  lea     rbp, [rsp-37h]
0x18001e397  sub     rsp, 0B0h
0x18001e39e  mov     rax, cs:__security_cookie
0x18001e3a5  xor     rax, rsp
0x18001e3a8  mov     [rbp+57h+var_28], rax
0x18001e3ac  mov     rsi, [rdx+20h]
0x18001e3b0  lea     rax, [rbp+57h+nSize]
0x18001e3b4  xor     r15d, r15d
0x18001e3b7  mov     [rsp+0D0h+var_A8], rax
0x18001e3bc  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001e3c0  mov     [rbp+57h+var_68], r15
0x18001e3c4  mov     r14, rcx
0x18001e3c7  mov     [rbp+57h+var_60], r12
0x18001e3cb  xor     r9d, r9d
0x18001e3ce  mov     [rbp+57h+var_58], r12
0x18001e3d2  lea     rdx, aLogonserver; "LOGONSERVER"
0x18001e3d9  mov     qword ptr [rbp+57h+nSize], r15
0x18001e3dd  lea     r8d, [r12+0Ch]
0x18001e3e2  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x18001e3e7  mov     rcx, rsi
0x18001e3ea  mov     edi, r15d
0x18001e3ed  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001e3f4  nop     dword ptr [rax+rax+00h]
0x18001e3f9  mov     ecx, eax; Status
0x18001e3fb  call    cs:__imp_RtlNtStatusToDosError
0x18001e402  nop     dword ptr [rax+rax+00h]
0x18001e407  mov     ebx, eax
0x18001e409  test    eax, eax
0x18001e40b  jle     short loc_18001E416
0x18001e40d  movzx   ebx, ax
0x18001e410  or      ebx, 80070000h
0x18001e416  cmp     ebx, 8007007Ah
0x18001e41c  jnz     loc_18001E4C7
0x18001e422  mov     eax, 2
0x18001e427  mov     [rbp+57h+var_68], r15
0x18001e42b  mul     qword ptr [rbp+57h+nSize]
0x18001e42f  mov     rbx, rax
0x18001e432  test    rdx, rdx
0x18001e435  jnz     loc_18001E4C2
0x18001e43b  call    cs:__imp_GetProcessHeap
0x18001e442  nop     dword ptr [rax+rax+00h]
0x18001e447  mov     r8, rbx; dwBytes
0x18001e44a  mov     edx, 8; dwFlags
0x18001e44f  mov     rcx, rax; hHeap
0x18001e452  call    cs:__imp_HeapAlloc
0x18001e459  nop     dword ptr [rax+rax+00h]
0x18001e45e  test    rax, rax
0x18001e461  mov     [rbp+57h+var_68], rax
0x18001e465  mov     ebx, 8007000Eh
0x18001e46a  mov     rdi, rax
0x18001e46d  cmovnz  ebx, r15d
0x18001e471  jz      short loc_18001E4C7
0x18001e473  lea     rax, [rbp+57h+nSize]
0x18001e477  mov     r9, rdi
0x18001e47a  mov     [rsp+0D0h+var_A8], rax
0x18001e47f  lea     rdx, aLogonserver; "LOGONSERVER"
0x18001e486  mov     rax, qword ptr [rbp+57h+nSize]
0x18001e48a  mov     r8d, 0Bh
0x18001e490  mov     rcx, rsi
0x18001e493  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18001e498  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001e49f  nop     dword ptr [rax+rax+00h]
0x18001e4a4  mov     ecx, eax; int
0x18001e4a6  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18001e4ab  mov     ebx, eax
0x18001e4ad  test    eax, eax
0x18001e4af  jns     short loc_18001E4C7
0x18001e4b1  mov     rcx, rdi; lpMem
0x18001e4b4  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001e4b9  mov     rdi, r15
0x18001e4bc  mov     [rbp+57h+var_68], r15
0x18001e4c0  jmp     short loc_18001E4C7
0x18001e4c2  mov     ebx, 80070216h
0x18001e4c7  cmp     ebx, 800700CBh
0x18001e4cd  jz      loc_18001E617
0x18001e4d3  test    ebx, ebx
0x18001e4d5  jns     short loc_18001E4F4
0x18001e4d7  mov     rcx, [rbp+5Fh]; this
0x18001e4db  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001e4e2  mov     r9d, ebx; char *
0x18001e4e5  mov     edx, 29Ah; void *
0x18001e4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4ef  jmp     loc_18001E5E4
0x18001e4f4  mov     [rbp+57h+nSize], 10h
0x18001e4fb  test    rdi, rdi
0x18001e4fe  jz      short loc_18001E50F
0x18001e500  mov     rax, r12
0x18001e503  inc     rax
0x18001e506  cmp     [rdi+rax*2], r15w
0x18001e50b  jnz     short loc_18001E503
0x18001e50d  jmp     short loc_18001E512
0x18001e50f  mov     rax, r15
0x18001e512  mov     [rbp+57h+var_60], rax
0x18001e516  cmp     rax, 2
0x18001e51a  jbe     short loc_18001E54B
0x18001e51c  lea     r8, [rbp+57h+nSize]; nSize
0x18001e520  xor     ecx, ecx; NameType
0x18001e522  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18001e526  call    cs:__imp_GetComputerNameExW
0x18001e52d  nop     dword ptr [rax+rax+00h]
0x18001e532  test    eax, eax
0x18001e534  jz      short loc_18001E54B
0x18001e536  lea     rcx, [rdi+4]; unsigned __int16 *
0x18001e53a  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x18001e53e  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18001e543  test    eax, eax
0x18001e545  jnz     loc_18001E617
0x18001e54b  lea     rcx, [rbp+57h+var_98]
0x18001e54f  mov     [rbp+57h+var_98], r15
0x18001e553  mov     [rbp+57h+var_90], r15
0x18001e557  mov     [rbp+57h+var_88], r15
0x18001e55b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e560  lea     rcx, [rbp+57h+var_98]; unsigned __int16 **
0x18001e564  mov     [rbp+57h+var_90], r12
0x18001e568  mov     [rbp+57h+var_88], r12
0x18001e56c  call    ?GetRoamingVersionExtension@@YAJPEAPEAG@Z; GetRoamingVersionExtension(ushort * *)
0x18001e571  mov     ebx, eax
0x18001e573  test    eax, eax
0x18001e575  jns     short loc_18001E591
0x18001e577  mov     rcx, [rbp+5Fh]; this
0x18001e57b  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001e582  mov     r9d, eax; char *
0x18001e585  mov     edx, 2A5h; void *
0x18001e58a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e58f  jmp     short loc_18001E5DB
0x18001e591  mov     r9, [rbp+57h+var_98]
0x18001e595  lea     rdx, aSNetlogonDefau; "%s\\NETLOGON\\Default User%s"
0x18001e59c  mov     r8, rdi
0x18001e59f  mov     [rbp+57h+var_80], r15
0x18001e5a3  lea     rcx, [rbp+57h+var_80]
0x18001e5a7  mov     [rbp+57h+var_78], r15
0x18001e5ab  mov     [rbp+57h+var_70], r15
0x18001e5af  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001e5b4  mov     ebx, eax
0x18001e5b6  test    eax, eax
0x18001e5b8  jns     short loc_18001E5F1
0x18001e5ba  mov     rcx, [rbp+5Fh]; this
0x18001e5be  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001e5c5  mov     r9d, eax; char *
0x18001e5c8  mov     edx, 2A8h; void *
0x18001e5cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5d2  lea     rcx, [rbp+57h+var_80]
0x18001e5d6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e5db  lea     rcx, [rbp+57h+var_98]
0x18001e5df  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e5e4  lea     rcx, [rbp+57h+var_68]
0x18001e5e8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e5ed  mov     eax, ebx
0x18001e5ef  jmp     short loc_18001E626
0x18001e5f1  mov     rax, [rbp+57h+var_80]
0x18001e5f5  lea     rcx, [rbp+57h+var_80]
0x18001e5f9  mov     [r14+18h], rax
0x18001e5fd  mov     [rbp+57h+var_80], r15
0x18001e601  mov     [rbp+57h+var_70], r15
0x18001e605  mov     [rbp+57h+var_78], r15
0x18001e609  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e60e  lea     rcx, [rbp+57h+var_98]
0x18001e612  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001e617  test    rdi, rdi
0x18001e61a  jz      short loc_18001E624
0x18001e61c  mov     rcx, rdi
0x18001e61f  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001e624  xor     eax, eax
0x18001e626  mov     rcx, [rbp+57h+var_28]
0x18001e62a  xor     rcx, rsp; StackCookie
0x18001e62d  call    __security_check_cookie
0x18001e632  lea     r11, [rsp+0D0h+var_20]
0x18001e63a  mov     rbx, [r11+40h]
0x18001e63e  mov     rsi, [r11+48h]
0x18001e642  mov     rsp, r11
0x18001e645  pop     r15
0x18001e647  pop     r14
0x18001e649  pop     r12
0x18001e64b  pop     rdi
0x18001e64c  pop     rbp
0x18001e64d  retn
```
