# CMDMPushConfiguration::ComputeNextRenewal(_ULARGE_INTEGER,_SYSTEMTIME *,int *)

- ea: `0x1800271ac`
- end: `0x18002738e`
- name: `?ComputeNextRenewal@CMDMPushConfiguration@@AEAAJT_ULARGE_INTEGER@@PEAU_SYSTEMTIME@@PEAH@Z`
- size: `482`
- prototype: `int(CMDMPushConfiguration *__hidden this, union _ULARGE_INTEGER, struct _SYSTEMTIME *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029994`

## callees

- `0x1800039f0`
- `0x18000ba94`
- `0x18000bab4`
- `0x1800271ac`
- `0x18002cbdc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800271dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800271dd`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180027319`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180027319`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027334`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027334`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800271f3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800271f3`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::ComputeNextRenewal(
        CMDMPushConfiguration *this,
        union _ULARGE_INTEGER a2,
        struct _SYSTEMTIME *a3,
        int *a4)
{
  CMDMPushConfiguration *v7; // rcx
  const char *v8; // r9
  __int64 v9; // rdx
  struct _FILETIME v11; // rax
  bool v12; // cc
  unsigned __int64 v13; // rdi
  __int64 v14; // rdx
  int RandomMinutes; // ebx
  ULONGLONG v16; // rbx
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-38h] BYREF
  FILETIME v20; // [rsp+30h] [rbp-30h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v9 = 1702;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
             v8);
  }
  v18 = (unsigned __int64)FileTime;
  v11 = FileTime;
  v12 = *(_QWORD *)&FileTime <= a2.QuadPart;
  if ( *(_QWORD *)&FileTime <= a2.QuadPart )
  {
    *a4 = 0;
    if ( !v12 )
    {
      v14 = 1728;
      goto LABEL_28;
    }
    if ( a2.QuadPart - *(_QWORD *)&v11 >= c_ullChannelRenewalThreshold )
    {
      if ( a2.QuadPart < c_ullChannelRenewalThreshold )
      {
        v14 = 1742;
        goto LABEL_28;
      }
      v16 = a2.QuadPart - c_ullChannelRenewalThreshold;
    }
    else
    {
      v17 = *(_QWORD *)&v11 + c_ull3Hours;
      if ( *(_QWORD *)&v11 + c_ull3Hours < *(_QWORD *)&v11 )
      {
        v14 = 1733;
        goto LABEL_28;
      }
      v18 = 0;
      RandomMinutes = CMDMPushConfiguration::GetRandomMinutes(
                        (CMDMPushConfiguration *)(a2.QuadPart - *(_QWORD *)&v11),
                        2u,
                        &v18);
      if ( RandomMinutes < 0 )
      {
        v14 = 1736;
        goto LABEL_29;
      }
      v16 = v17 + v18;
      if ( v17 + v18 < v17 )
      {
        v14 = 1737;
        goto LABEL_28;
      }
    }
  }
  else
  {
    *a4 = 1;
    v13 = *(_QWORD *)&v11 + c_ull20Hours;
    if ( *(_QWORD *)&v11 + c_ull20Hours < *(_QWORD *)&v11 )
    {
      v14 = 1716;
LABEL_28:
      RandomMinutes = -2147024362;
      goto LABEL_29;
    }
    v18 = 0;
    RandomMinutes = CMDMPushConfiguration::GetRandomMinutes(v7, 8u, &v18);
    if ( RandomMinutes < 0 )
    {
      v14 = 1719;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)RandomMinutes,
        v18);
      return (unsigned int)RandomMinutes;
    }
    v16 = v13 + v18;
    if ( v13 + v18 < v13 )
    {
      v14 = 1720;
      goto LABEL_28;
    }
  }
  v18 = v16;
  v20 = (FILETIME)v16;
  LocalFileTime = 0;
  if ( !FileTimeToLocalFileTime(&v20, &LocalFileTime) )
  {
    v9 = 1752;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
             v8);
  }
  if ( !FileTimeToSystemTime(&LocalFileTime, a3) )
  {
    v9 = 1753;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
             v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800271ac  mov     [rsp-18h+arg_0], rbx
0x1800271b1  push    rbp
0x1800271b2  push    rsi
0x1800271b3  push    rdi
0x1800271b4  mov     rbp, rsp
0x1800271b7  sub     rsp, 60h
0x1800271bb  mov     rax, cs:__security_cookie
0x1800271c2  xor     rax, rsp
0x1800271c5  mov     [rbp+var_10], rax
0x1800271c9  xorps   xmm0, xmm0
0x1800271cc  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800271d0  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800271d4  mov     rdi, r9
0x1800271d7  mov     rsi, r8
0x1800271da  mov     rbx, rdx
0x1800271dd  call    cs:__imp_GetSystemTime
0x1800271e3  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800271e7  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800271ef  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800271f3  call    cs:__imp_SystemTimeToFileTime
0x1800271f9  test    eax, eax
0x1800271fb  jnz     short loc_180027217
0x1800271fd  mov     edx, 6A6h; void *
0x180027202  mov     rcx, [rbp+18h]; this
0x180027206  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002720d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027212  jmp     loc_180027372
0x180027217  mov     eax, [rbp+FileTime.dwHighDateTime]
0x18002721a  mov     dword ptr [rbp+var_40+4], eax
0x18002721d  mov     eax, [rbp+FileTime.dwLowDateTime]
0x180027220  mov     dword ptr [rbp+var_40], eax
0x180027223  mov     rax, [rbp+var_40]
0x180027227  cmp     rax, rbx
0x18002722a  jbe     short loc_180027287
0x18002722c  mov     dword ptr [rdi], 1
0x180027232  mov     rdi, cs:?c_ull20Hours@@3_KA; unsigned __int64 c_ull20Hours
0x180027239  add     rdi, rax
0x18002723c  cmp     rdi, rax
0x18002723f  jnb     short loc_18002724B
0x180027241  mov     edx, 6B4h
0x180027246  jmp     loc_180027358
0x18002724b  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18002724f  mov     [rbp+var_40], 0
0x180027257  mov     edx, 8; unsigned int
0x18002725c  call    ?GetRandomMinutes@CMDMPushConfiguration@@AEAAJKPEA_K@Z; CMDMPushConfiguration::GetRandomMinutes(ulong,unsigned __int64 *)
0x180027261  mov     ebx, eax
0x180027263  test    eax, eax
0x180027265  jns     short loc_180027271
0x180027267  mov     edx, 6B7h
0x18002726c  jmp     loc_18002735D
0x180027271  mov     rbx, [rbp+var_40]
0x180027275  add     rbx, rdi
0x180027278  cmp     rbx, rdi
0x18002727b  jnb     short loc_1800272FC
0x18002727d  mov     edx, 6B8h
0x180027282  jmp     loc_180027358
0x180027287  mov     dword ptr [rdi], 0
0x18002728d  ja      loc_180027353
0x180027293  mov     rdx, cs:?c_ullChannelRenewalThreshold@@3_KA; unsigned __int64 c_ullChannelRenewalThreshold
0x18002729a  mov     rcx, rbx
0x18002729d  sub     rcx, rax; this
0x1800272a0  cmp     rcx, rdx
0x1800272a3  jnb     short loc_1800272F4
0x1800272a5  mov     rdi, cs:?c_ull3Hours@@3_KA; unsigned __int64 c_ull3Hours
0x1800272ac  add     rdi, rax
0x1800272af  cmp     rdi, rax
0x1800272b2  jnb     short loc_1800272BE
0x1800272b4  mov     edx, 6C5h
0x1800272b9  jmp     loc_180027358
0x1800272be  lea     r8, [rbp+var_40]; unsigned __int64 *
0x1800272c2  mov     [rbp+var_40], 0
0x1800272ca  mov     edx, 2; unsigned int
0x1800272cf  call    ?GetRandomMinutes@CMDMPushConfiguration@@AEAAJKPEA_K@Z; CMDMPushConfiguration::GetRandomMinutes(ulong,unsigned __int64 *)
0x1800272d4  mov     ebx, eax
0x1800272d6  test    eax, eax
0x1800272d8  jns     short loc_1800272E1
0x1800272da  mov     edx, 6C8h
0x1800272df  jmp     short loc_18002735D
0x1800272e1  mov     rbx, [rbp+var_40]
0x1800272e5  add     rbx, rdi
0x1800272e8  cmp     rbx, rdi
0x1800272eb  jnb     short loc_1800272FC
0x1800272ed  mov     edx, 6C9h
0x1800272f2  jmp     short loc_180027358
0x1800272f4  cmp     rbx, rdx
0x1800272f7  jb      short loc_18002734C
0x1800272f9  sub     rbx, rdx
0x1800272fc  mov     [rbp+var_40], rbx
0x180027300  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x180027304  mov     eax, dword ptr [rbp+var_40+4]
0x180027307  lea     rcx, [rbp+var_30]; lpFileTime
0x18002730b  mov     [rbp+var_30.dwHighDateTime], eax
0x18002730e  mov     [rbp+var_30.dwLowDateTime], ebx
0x180027311  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x180027319  call    cs:__imp_FileTimeToLocalFileTime
0x18002731f  test    eax, eax
0x180027321  jnz     short loc_18002732D
0x180027323  mov     edx, 6D8h
0x180027328  jmp     loc_180027202
0x18002732d  mov     rdx, rsi; lpSystemTime
0x180027330  lea     rcx, [rbp+LocalFileTime]; lpFileTime
0x180027334  call    cs:__imp_FileTimeToSystemTime
0x18002733a  test    eax, eax
0x18002733c  jnz     short loc_180027348
0x18002733e  mov     edx, 6D9h
0x180027343  jmp     loc_180027202
0x180027348  xor     eax, eax
0x18002734a  jmp     short loc_180027372
0x18002734c  mov     edx, 6CEh
0x180027351  jmp     short loc_180027358
0x180027353  mov     edx, 6C0h; void *
0x180027358  mov     ebx, 80070216h
0x18002735d  mov     rcx, [rbp+18h]; this
0x180027361  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x180027368  mov     r9d, ebx; char *
0x18002736b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027370  mov     eax, ebx
0x180027372  mov     rcx, [rbp+var_10]
0x180027376  xor     rcx, rsp; StackCookie
0x180027379  call    __security_check_cookie
0x18002737e  mov     rbx, [rsp+60h+arg_0]
0x180027386  add     rsp, 60h
0x18002738a  pop     rdi
0x18002738b  pop     rsi
0x18002738c  pop     rbp
0x18002738d  retn
```
