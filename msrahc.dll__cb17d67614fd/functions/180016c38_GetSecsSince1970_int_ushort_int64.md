# GetSecsSince1970(int,ushort * *,__int64 *)

- ea: `0x180016c38`
- end: `0x180016ea5`
- name: `?GetSecsSince1970@@YAJHPEAPEAGPEA_J@Z`
- size: `621`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011344`

## callees

- `0x180014660`
- `0x180014c24`
- `0x180016730`
- `0x18001692c`
- `0x180016c38`
- `0x180016eac`
- `0x180017340`
- `0x18001a5a2`
- `0x18001a5e0`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x180016d3b`
- `WS2_32!__imp_WSAGetLastError` at `0x180016d3b`
- `WS2_32!__imp_WSAStartup` at `0x180016d31`
- `WS2_32!__imp_WSAStartup` at `0x180016d31`
- `WS2_32!__imp_WSACleanup` at `0x180016e77`
- `WS2_32!__imp_WSACleanup` at `0x180016e77`
- `KERNEL32!GetProcessHeap` at `0x180016e48`
- `KERNEL32!GetProcessHeap` at `0x180016e63`
- `KERNEL32!GetProcessHeap` at `0x180016e48`
- `KERNEL32!GetProcessHeap` at `0x180016e63`
- `KERNEL32!HeapFree` at `0x180016e58`
- `KERNEL32!HeapFree` at `0x180016e71`
- `KERNEL32!HeapFree` at `0x180016e58`
- `KERNEL32!HeapFree` at `0x180016e71`

## string_xrefs

- `0x180016ceb`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016d0f`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016d83`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016e06`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016e2b`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016ce0`: `ReadTimeSourceFromReg`

## pseudocode

```c
__int64 __fastcall GetSecsSince1970(__int64 a1, unsigned __int16 **a2, unsigned __int64 *a3)
{
  signed int TimeSyncSource; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  unsigned int v8; // ebx
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  signed int RegistryValue; // edi
  unsigned int v12; // r9d
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  signed int NTPSrvAddr; // eax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  unsigned int *v20; // rsi
  unsigned int v21; // edi
  unsigned int v22; // r9d
  HANDLE ProcessHeap; // rax
  HANDLE v24; // rax
  int Error; // [rsp+28h] [rbp-D8h]
  unsigned int v27; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v30; // [rsp+48h] [rbp-B8h] BYREF
  struct WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  *a3 = 0;
  *a2 = 0;
  lpMem = 0;
  v30 = 0;
  v27 = 0;
  TimeSyncSource = GetTimeSyncSource(a2);
  v8 = TimeSyncSource;
  if ( TimeSyncSource == 1 )
  {
    v29 = 0;
    *a2 = 0;
    RegistryValue = GetRegistryValue((__int64)v7, (BYTE **)&v29);
    if ( RegistryValue < 0 )
    {
      v12 = 990;
LABEL_6:
      CEventLogger::LogError(
        v10,
        v9,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        v12,
        L"ReadTimeSourceFromReg",
        RegistryValue);
      v8 = RegistryValue;
      CEventLogger::LogError(
        v14,
        v13,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        0x7Bu,
        L"GetSecsSince1970",
        RegistryValue);
      return v8;
    }
    RegistryValue = ParseTimeSource(v29, a2);
    if ( RegistryValue < 0 )
    {
      v12 = 994;
      goto LABEL_6;
    }
    v8 = RegistryValue;
  }
  else if ( TimeSyncSource < 0 )
  {
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x7Fu,
      L"GetSecsSince1970",
      TimeSyncSource);
    return v8;
  }
  if ( WSAStartup(2u, &WSAData) )
  {
    Error = WSAGetLastError();
    CEventLogger::LogError(
      v16,
      v15,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x88u,
      L"GetSecsSince1970",
      Error);
    return v8;
  }
  NTPSrvAddr = GetNTPSrvAddr(*a2, (struct sockaddr_storage **)&lpMem, &v30, &v27);
  v20 = v30;
  v8 = NTPSrvAddr;
  if ( NTPSrvAddr < 0 )
  {
    CEventLogger::LogError(
      v19,
      v18,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x90u,
      L"GetSecsSince1970",
      NTPSrvAddr);
    goto LABEL_26;
  }
  if ( !v27 )
  {
    v22 = 145;
LABEL_25:
    CEventLogger::LogError(
      v19,
      v18,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      v22,
      L"GetSecsSince1970",
      0);
    v8 = -2147467259;
LABEL_26:
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    goto LABEL_28;
  }
  if ( lpMem )
  {
    if ( v30 )
    {
      v21 = 0;
      while ( (int)GetNTPSrvTime((const struct sockaddr *)lpMem + 8 * (unsigned __int64)v21, v20[v21], a3) < 0 )
      {
        if ( ++v21 )
        {
          v22 = 167;
          goto LABEL_25;
        }
      }
      goto LABEL_26;
    }
    v22 = 147;
    goto LABEL_25;
  }
  CEventLogger::LogError(
    v19,
    v18,
    L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
    0x92u,
    L"GetSecsSince1970",
    0);
  v8 = -2147467259;
LABEL_28:
  if ( v20 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v20);
  }
  WSACleanup();
  return v8;
}

```

## disassembly

```asm
0x180016c38  mov     [rsp-8+arg_0], rbx
0x180016c3d  push    rbp
0x180016c3e  push    rsi
0x180016c3f  push    rdi
0x180016c40  push    r12
0x180016c42  push    r15
0x180016c44  lea     rbp, [rsp-100h]
0x180016c4c  sub     rsp, 200h
0x180016c53  mov     rax, cs:__security_cookie
0x180016c5a  xor     rax, rsp
0x180016c5d  mov     [rbp+120h+var_30], rax
0x180016c64  mov     r15, r8
0x180016c67  lea     rcx, [rsp+220h+WSAData]; void *
0x180016c6c  mov     rsi, rdx
0x180016c6f  mov     r8d, 198h; Size
0x180016c75  xor     edx, edx; Val
0x180016c77  call    memset_0
0x180016c7c  xor     r12d, r12d
0x180016c7f  mov     rcx, rsi; unsigned __int16 **
0x180016c82  mov     [r15], r12
0x180016c85  mov     [rsi], r12
0x180016c88  mov     [rsp+220h+lpMem], r12
0x180016c8d  mov     [rsp+220h+var_1D8], r12
0x180016c92  mov     [rsp+220h+var_1F0], r12d
0x180016c97  call    ?GetTimeSyncSource@@YAJPEAPEAG@Z; GetTimeSyncSource(ushort * *)
0x180016c9c  mov     ebx, eax
0x180016c9e  cmp     eax, 1
0x180016ca1  jnz     loc_180016D4D
0x180016ca7  lea     rdx, [rsp+220h+var_1E0]
0x180016cac  mov     [rsp+220h+var_1E0], r12
0x180016cb1  mov     [rsi], r12
0x180016cb4  call    ?GetRegistryValue@@YAJPEAGPEAPEAGW4_RAREGHIVE@@@Z; GetRegistryValue(ushort *,ushort * *,_RAREGHIVE)
0x180016cb9  mov     edi, eax
0x180016cbb  test    eax, eax
0x180016cbd  jns     short loc_180016CC7
0x180016cbf  mov     r9d, 3DEh
0x180016cc5  jmp     short loc_180016CE0
0x180016cc7  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x180016ccc  mov     rdx, rsi; unsigned __int16 **
0x180016ccf  call    ?ParseTimeSource@@YAJPEAGPEAPEAG@Z; ParseTimeSource(ushort *,ushort * *)
0x180016cd4  mov     edi, eax
0x180016cd6  test    eax, eax
0x180016cd8  jns     short loc_180016D25
0x180016cda  mov     r9d, 3E2h; unsigned int
0x180016ce0  lea     rax, aReadtimesource; "ReadTimeSourceFromReg"
0x180016ce7  mov     [rsp+220h+var_1F8], edi; unsigned int
0x180016ceb  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016cf2  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x180016cf7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016cfc  mov     r9d, 7Bh ; '{'; unsigned int
0x180016d02  mov     [rsp+220h+var_1F8], edi; unsigned int
0x180016d06  mov     ebx, edi
0x180016d08  lea     rax, aGetsecssince19; "GetSecsSince1970"
0x180016d0f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016d16  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x180016d1b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016d20  jmp     loc_180016E7D
0x180016d25  mov     ebx, edi
0x180016d27  mov     ecx, 2; wVersionRequested
0x180016d2c  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x180016d31  call    cs:__imp_WSAStartup
0x180016d37  test    eax, eax
0x180016d39  jz      short loc_180016D5D
0x180016d3b  call    cs:__imp_WSAGetLastError
0x180016d41  mov     [rsp+220h+var_1F8], eax
0x180016d45  mov     r9d, 88h
0x180016d4b  jmp     short loc_180016D08
0x180016d4d  test    eax, eax
0x180016d4f  jns     short loc_180016D27
0x180016d51  mov     [rsp+220h+var_1F8], eax
0x180016d55  mov     r9d, 7Fh
0x180016d5b  jmp     short loc_180016D08
0x180016d5d  mov     rcx, [rsi]; unsigned __int16 *
0x180016d60  lea     r9, [rsp+220h+var_1F0]; unsigned int *
0x180016d65  lea     r8, [rsp+220h+var_1D8]; unsigned int **
0x180016d6a  lea     rdx, [rsp+220h+lpMem]; struct sockaddr_storage **
0x180016d6f  call    ?GetNTPSrvAddr@@YAJPEAGPEAPEAUsockaddr_storage@@PEAPEAIPEAI@Z; GetNTPSrvAddr(ushort *,sockaddr_storage * *,uint * *,uint *)
0x180016d74  mov     rsi, [rsp+220h+var_1D8]
0x180016d79  mov     ebx, eax
0x180016d7b  test    eax, eax
0x180016d7d  jns     short loc_180016DA6
0x180016d7f  mov     [rsp+220h+var_1F8], eax; unsigned int
0x180016d83  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016d8a  lea     rax, aGetsecssince19; "GetSecsSince1970"
0x180016d91  mov     r9d, 90h; unsigned int
0x180016d97  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x180016d9c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016da1  jmp     loc_180016E41
0x180016da6  cmp     [rsp+220h+var_1F0], r12d
0x180016dab  jbe     short loc_180016E19
0x180016dad  cmp     [rsp+220h+lpMem], r12
0x180016db2  jz      short loc_180016DEF
0x180016db4  test    rsi, rsi
0x180016db7  jz      short loc_180016DE7
0x180016db9  mov     edi, r12d
0x180016dbc  mov     edx, edi
0x180016dbe  mov     r8, r15; __int64 *
0x180016dc1  mov     ecx, edi
0x180016dc3  shl     rcx, 7
0x180016dc7  add     rcx, [rsp+220h+lpMem]; name
0x180016dcc  mov     edx, [rsi+rdx*4]; namelen
0x180016dcf  call    ?GetNTPSrvTime@@YAJPEAUsockaddr_storage@@IPEA_J@Z; GetNTPSrvTime(sockaddr_storage *,uint,__int64 *)
0x180016dd4  test    eax, eax
0x180016dd6  jns     short loc_180016E41
0x180016dd8  inc     edi
0x180016dda  cmp     edi, 1
0x180016ddd  jb      short loc_180016DBC
0x180016ddf  mov     r9d, 0A7h
0x180016de5  jmp     short loc_180016E1F
0x180016de7  mov     r9d, 93h
0x180016ded  jmp     short loc_180016E1F
0x180016def  lea     rax, aGetsecssince19; "GetSecsSince1970"
0x180016df6  mov     [rsp+220h+var_1F8], r12d; unsigned int
0x180016dfb  mov     r9d, 92h; unsigned int
0x180016e01  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x180016e06  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016e0d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016e12  mov     ebx, 80004005h
0x180016e17  jmp     short loc_180016E5E
0x180016e19  mov     r9d, 91h; unsigned int
0x180016e1f  lea     rax, aGetsecssince19; "GetSecsSince1970"
0x180016e26  mov     [rsp+220h+var_1F8], r12d; unsigned int
0x180016e2b  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016e32  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x180016e37  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016e3c  mov     ebx, 80004005h
0x180016e41  cmp     [rsp+220h+lpMem], r12
0x180016e46  jz      short loc_180016E5E
0x180016e48  call    cs:__imp_GetProcessHeap
0x180016e4e  mov     r8, [rsp+220h+lpMem]; lpMem
0x180016e53  xor     edx, edx; dwFlags
0x180016e55  mov     rcx, rax; hHeap
0x180016e58  call    cs:__imp_HeapFree
0x180016e5e  test    rsi, rsi
0x180016e61  jz      short loc_180016E77
0x180016e63  call    cs:__imp_GetProcessHeap
0x180016e69  mov     r8, rsi; lpMem
0x180016e6c  xor     edx, edx; dwFlags
0x180016e6e  mov     rcx, rax; hHeap
0x180016e71  call    cs:__imp_HeapFree
0x180016e77  call    cs:__imp_WSACleanup
0x180016e7d  mov     eax, ebx
0x180016e7f  mov     rcx, [rbp+120h+var_30]
0x180016e86  xor     rcx, rsp; StackCookie
0x180016e89  call    __security_check_cookie
0x180016e8e  mov     rbx, [rsp+220h+arg_0]
0x180016e96  add     rsp, 200h
0x180016e9d  pop     r15
0x180016e9f  pop     r12
0x180016ea1  pop     rdi
0x180016ea2  pop     rsi
0x180016ea3  pop     rbp
0x180016ea4  retn
```
