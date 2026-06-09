# _SetupNetworkDefaultProfilePath(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)

- ea: `0x1800168ec`
- end: `0x180016bbc`
- name: `?_SetupNetworkDefaultProfilePath@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(struct _PROFILEINFOW *, const struct _SN_ONLOGON_PARAMS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017364`

## callees

- `0x180004170`
- `0x1800053a0`
- `0x180010f30`
- `0x1800111a0`
- `0x1800168ec`
- `0x1800212a0`
- `0x18002d2d8`
- `0x18003a730`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800169ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800169ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001699b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001699b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180016a99`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180016a99`
- `ntdll!RtlQueryEnvironmentVariable` at `0x180016959`
- `ntdll!RtlQueryEnvironmentVariable` at `0x1800169ec`
- `ntdll!RtlQueryEnvironmentVariable` at `0x180016959`
- `ntdll!RtlQueryEnvironmentVariable` at `0x1800169ec`
- `ntdll!RtlNtStatusToDosError` at `0x180016961`
- `ntdll!RtlNtStatusToDosError` at `0x1800169f4`
- `ntdll!RtlNtStatusToDosError` at `0x180016961`
- `ntdll!RtlNtStatusToDosError` at `0x1800169f4`

## string_xrefs

- `0x180016a3f`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180016ae8`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180016b2b`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

## pseudocode

```c
__int64 __fastcall _SetupNetworkDefaultProfilePath(struct _PROFILEINFOW *a1, const struct _SN_ONLOGON_PARAMS *a2)
{
  __int64 v2; // rsi
  void *v4; // rdi
  NTSTATUS EnvironmentVariable; // eax
  signed int v6; // eax
  signed int v7; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax
  NTSTATUS v10; // eax
  signed int v11; // eax
  void *v12; // rsi
  unsigned __int64 v14; // rax
  int RoamingVersionExtension; // eax
  int v16; // eax
  int v17; // [rsp+20h] [rbp-59h]
  DWORD nSize[2]; // [rsp+30h] [rbp-49h] BYREF
  WCHAR *v19; // [rsp+38h] [rbp-41h] BYREF
  __int64 v20; // [rsp+40h] [rbp-39h]
  __int64 v21; // [rsp+48h] [rbp-31h]
  unsigned __int16 *v22; // [rsp+50h] [rbp-29h] BYREF
  __int64 v23; // [rsp+58h] [rbp-21h]
  __int64 v24; // [rsp+60h] [rbp-19h]
  LPVOID v25; // [rsp+68h] [rbp-11h] BYREF
  __int64 v26; // [rsp+70h] [rbp-9h]
  __int64 v27; // [rsp+78h] [rbp-1h]
  WCHAR Buffer[16]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = *((_QWORD *)a2 + 4);
  v25 = 0;
  v26 = -1;
  v27 = -1;
  *(_QWORD *)nSize = 0;
  v17 = 0;
  v4 = 0;
  EnvironmentVariable = RtlQueryEnvironmentVariable(v2, L"LOGONSERVER", 11, 0);
  v6 = RtlNtStatusToDosError(EnvironmentVariable);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 != -2147024774 )
    goto LABEL_12;
  v25 = 0;
  if ( !is_mul_ok(*(unsigned __int64 *)nSize, 2u) )
  {
    v7 = -2147024362;
    goto LABEL_12;
  }
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 2LL * *(_QWORD *)nSize);
  v25 = v9;
  v7 = -2147024882;
  v4 = v9;
  if ( v9 )
  {
    v17 = nSize[0];
    v10 = RtlQueryEnvironmentVariable(v2, L"LOGONSERVER", 11, v9);
    v11 = RtlNtStatusToDosError(v10);
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 < 0 )
    {
      ResultFromHeapFree(v4);
      v4 = 0;
      v25 = 0;
LABEL_12:
      v12 = 0;
      goto LABEL_13;
    }
  }
  v12 = v4;
LABEL_13:
  if ( v7 != -2147024693 )
  {
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)v7,
        v17);
      if ( v12 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v4);
      return (unsigned int)v7;
    }
    nSize[0] = 16;
    if ( v12 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v12 + v14) );
    }
    else
    {
      v14 = 0;
    }
    v26 = v14;
    if ( v14 <= 2
      || !GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize)
      || !StringIsEqual((const unsigned __int16 *)v12 + 2, Buffer) )
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v22);
      v23 = -1;
      v24 = -1;
      RoamingVersionExtension = GetRoamingVersionExtension(&v22);
      v7 = RoamingVersionExtension;
      if ( RoamingVersionExtension < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A5,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)RoamingVersionExtension,
          v17);
LABEL_30:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v22);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
        return (unsigned int)v7;
      }
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v16 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
              &v19,
              L"%s\\NETLOGON\\Default User%s",
              v4,
              v22);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v16,
          v17);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v19);
        goto LABEL_30;
      }
      a1->lpDefaultPath = v19;
      v19 = 0;
      v21 = 0;
      v20 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v19);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v22);
    }
  }
  if ( v12 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v4);
  return 0;
}

```

## disassembly

```asm
0x1800168ec  mov     [rsp-8+arg_10], rbx
0x1800168f1  mov     [rsp-8+arg_18], rsi
0x1800168f6  push    rbp
0x1800168f7  push    rdi
0x1800168f8  push    r12
0x1800168fa  push    r14
0x1800168fc  push    r15
0x1800168fe  lea     rbp, [rsp-37h]
0x180016903  sub     rsp, 0B0h
0x18001690a  mov     rax, cs:__security_cookie
0x180016911  xor     rax, rsp
0x180016914  mov     [rbp+57h+var_28], rax
0x180016918  mov     rsi, [rdx+20h]
0x18001691c  lea     rax, [rbp+57h+nSize]
0x180016920  xor     r15d, r15d
0x180016923  mov     [rsp+0D0h+var_A8], rax
0x180016928  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001692c  mov     [rbp+57h+var_68], r15
0x180016930  mov     r14, rcx
0x180016933  mov     [rbp+57h+var_60], r12
0x180016937  xor     r9d, r9d
0x18001693a  mov     [rbp+57h+var_58], r12
0x18001693e  lea     rdx, aLogonserver; "LOGONSERVER"
0x180016945  mov     qword ptr [rbp+57h+nSize], r15
0x180016949  lea     r8d, [r12+0Ch]
0x18001694e  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x180016953  mov     rcx, rsi
0x180016956  mov     edi, r15d
0x180016959  call    cs:__imp_RtlQueryEnvironmentVariable
0x18001695f  mov     ecx, eax; Status
0x180016961  call    cs:__imp_RtlNtStatusToDosError
0x180016967  mov     ebx, eax
0x180016969  test    eax, eax
0x18001696b  jle     short loc_180016976
0x18001696d  movzx   ebx, ax
0x180016970  or      ebx, 80070000h
0x180016976  cmp     ebx, 8007007Ah
0x18001697c  jnz     loc_180016A28
0x180016982  mov     eax, 2
0x180016987  mov     [rbp+57h+var_68], r15
0x18001698b  mul     qword ptr [rbp+57h+nSize]
0x18001698f  mov     rbx, rax
0x180016992  test    rdx, rdx
0x180016995  jnz     loc_180016A23
0x18001699b  call    cs:__imp_GetProcessHeap
0x1800169a1  mov     r8, rbx; dwBytes
0x1800169a4  mov     edx, 8; dwFlags
0x1800169a9  mov     rcx, rax; hHeap
0x1800169ac  call    cs:__imp_HeapAlloc
0x1800169b2  test    rax, rax
0x1800169b5  mov     [rbp+57h+var_68], rax
0x1800169b9  mov     ebx, 8007000Eh
0x1800169be  mov     rdi, rax
0x1800169c1  cmovnz  ebx, r15d
0x1800169c5  jz      short loc_180016A1E
0x1800169c7  lea     rax, [rbp+57h+nSize]
0x1800169cb  mov     r9, rdi
0x1800169ce  mov     [rsp+0D0h+var_A8], rax
0x1800169d3  lea     rdx, aLogonserver; "LOGONSERVER"
0x1800169da  mov     rax, qword ptr [rbp+57h+nSize]
0x1800169de  mov     r8d, 0Bh
0x1800169e4  mov     rcx, rsi
0x1800169e7  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800169ec  call    cs:__imp_RtlQueryEnvironmentVariable
0x1800169f2  mov     ecx, eax; Status
0x1800169f4  call    cs:__imp_RtlNtStatusToDosError
0x1800169fa  mov     ebx, eax
0x1800169fc  test    eax, eax
0x1800169fe  jle     short loc_180016A09
0x180016a00  movzx   ebx, ax
0x180016a03  or      ebx, 80070000h
0x180016a09  test    ebx, ebx
0x180016a0b  jns     short loc_180016A1E
0x180016a0d  mov     rcx, rdi; lpMem
0x180016a10  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180016a15  mov     rdi, r15
0x180016a18  mov     [rbp+57h+var_68], r15
0x180016a1c  jmp     short loc_180016A28
0x180016a1e  mov     rsi, rdi
0x180016a21  jmp     short loc_180016A2B
0x180016a23  mov     ebx, 80070216h
0x180016a28  mov     rsi, r15
0x180016a2b  cmp     ebx, 800700CBh
0x180016a31  jz      loc_180016B85
0x180016a37  test    ebx, ebx
0x180016a39  jns     short loc_180016A67
0x180016a3b  mov     rcx, [rbp+5Fh]; this
0x180016a3f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016a46  mov     r9d, ebx; char *
0x180016a49  mov     edx, 29Ah; void *
0x180016a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a53  test    rsi, rsi
0x180016a56  jz      short loc_180016A60
0x180016a58  mov     rcx, rdi
0x180016a5b  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180016a60  mov     eax, ebx
0x180016a62  jmp     loc_180016B94
0x180016a67  mov     [rbp+57h+nSize], 10h
0x180016a6e  test    rsi, rsi
0x180016a71  jz      short loc_180016A82
0x180016a73  mov     rax, r12
0x180016a76  inc     rax
0x180016a79  cmp     [rsi+rax*2], r15w
0x180016a7e  jnz     short loc_180016A76
0x180016a80  jmp     short loc_180016A85
0x180016a82  mov     rax, r15
0x180016a85  mov     [rbp+57h+var_60], rax
0x180016a89  cmp     rax, 2
0x180016a8d  jbe     short loc_180016AB8
0x180016a8f  lea     r8, [rbp+57h+nSize]; nSize
0x180016a93  xor     ecx, ecx; NameType
0x180016a95  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180016a99  call    cs:__imp_GetComputerNameExW
0x180016a9f  test    eax, eax
0x180016aa1  jz      short loc_180016AB8
0x180016aa3  lea     rcx, [rsi+4]; unsigned __int16 *
0x180016aa7  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x180016aab  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180016ab0  test    eax, eax
0x180016ab2  jnz     loc_180016B85
0x180016ab8  lea     rcx, [rbp+57h+var_80]
0x180016abc  mov     [rbp+57h+var_80], r15
0x180016ac0  mov     [rbp+57h+var_78], r15
0x180016ac4  mov     [rbp+57h+var_70], r15
0x180016ac8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016acd  lea     rcx, [rbp+57h+var_80]; unsigned __int16 **
0x180016ad1  mov     [rbp+57h+var_78], r12
0x180016ad5  mov     [rbp+57h+var_70], r12
0x180016ad9  call    ?GetRoamingVersionExtension@@YAJPEAPEAG@Z; GetRoamingVersionExtension(ushort * *)
0x180016ade  mov     ebx, eax
0x180016ae0  test    eax, eax
0x180016ae2  jns     short loc_180016AFE
0x180016ae4  mov     rcx, [rbp+5Fh]; this
0x180016ae8  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016aef  mov     r9d, eax; char *
0x180016af2  mov     edx, 2A5h; void *
0x180016af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016afc  jmp     short loc_180016B48
0x180016afe  mov     r9, [rbp+57h+var_80]
0x180016b02  lea     rdx, aSNetlogonDefau; "%s\\NETLOGON\\Default User%s"
0x180016b09  mov     r8, rdi
0x180016b0c  mov     [rbp+57h+var_98], r15
0x180016b10  lea     rcx, [rbp+57h+var_98]
0x180016b14  mov     [rbp+57h+var_90], r15
0x180016b18  mov     [rbp+57h+var_88], r15
0x180016b1c  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180016b21  mov     ebx, eax
0x180016b23  test    eax, eax
0x180016b25  jns     short loc_180016B5F
0x180016b27  mov     rcx, [rbp+5Fh]; this
0x180016b2b  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016b32  mov     r9d, eax; char *
0x180016b35  mov     edx, 2A8h; void *
0x180016b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b3f  lea     rcx, [rbp+57h+var_98]
0x180016b43  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016b48  lea     rcx, [rbp+57h+var_80]
0x180016b4c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016b51  lea     rcx, [rbp+57h+var_68]
0x180016b55  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016b5a  jmp     loc_180016A60
0x180016b5f  mov     rax, [rbp+57h+var_98]
0x180016b63  lea     rcx, [rbp+57h+var_98]
0x180016b67  mov     [r14+18h], rax
0x180016b6b  mov     [rbp+57h+var_98], r15
0x180016b6f  mov     [rbp+57h+var_88], r15
0x180016b73  mov     [rbp+57h+var_90], r15
0x180016b77  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016b7c  lea     rcx, [rbp+57h+var_80]
0x180016b80  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016b85  test    rsi, rsi
0x180016b88  jz      short loc_180016B92
0x180016b8a  mov     rcx, rdi
0x180016b8d  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180016b92  xor     eax, eax
0x180016b94  mov     rcx, [rbp+57h+var_28]
0x180016b98  xor     rcx, rsp; StackCookie
0x180016b9b  call    __security_check_cookie
0x180016ba0  lea     r11, [rsp+0D0h+var_20]
0x180016ba8  mov     rbx, [r11+40h]
0x180016bac  mov     rsi, [r11+48h]
0x180016bb0  mov     rsp, r11
0x180016bb3  pop     r15
0x180016bb5  pop     r14
0x180016bb7  pop     r12
0x180016bb9  pop     rdi
0x180016bba  pop     rbp
0x180016bbb  retn
```
