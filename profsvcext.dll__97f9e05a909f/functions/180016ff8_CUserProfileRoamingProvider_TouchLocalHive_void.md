# CUserProfileRoamingProvider::_TouchLocalHive(void)

- ea: `0x180016ff8`
- end: `0x180017275`
- name: `?_TouchLocalHive@CUserProfileRoamingProvider@@AEAAJXZ`
- size: `637`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012314`

## callees

- `0x180005234`
- `0x180005424`
- `0x18000547c`
- `0x180006a9c`
- `0x180011454`
- `0x18001375c`
- `0x180013af4`
- `0x180016ff8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001719c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001719c`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800171de`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800171de`

## string_xrefs

- `0x1800170a9`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18001714d`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800171ec`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180017247`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_TouchLocalHive(CUserProfileRoamingProvider *this)
{
  const unsigned __int16 *v2; // rax
  int *v3; // r8
  int ProfileListKeyNameFromSid; // eax
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  HANDLE FileW; // rax
  const char *v11; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-29h]
  _QWORD v14[3]; // [rsp+40h] [rbp-9h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+58h] [rbp+Fh] BYREF
  unsigned __int16 *v16; // [rsp+70h] [rbp+27h] BYREF
  __int64 v17; // [rsp+78h] [rbp+2Fh]
  __int64 v18; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  HANDLE v20; // [rsp+B0h] [rbp+67h] BYREF
  FILETIME LastWriteTime; // [rsp+B8h] [rbp+6Fh] BYREF

  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 8) == 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 1) == 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x800) == 0 )
  {
    v16 = 0;
    v17 = 0;
    v18 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v16);
    v17 = -1;
    v18 = -1;
    v2 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
    ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(v2, &v16, v3);
    LastError = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97E,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)ProfileListKeyNameFromSid,
        dwCreationDisposition);
LABEL_20:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v16);
      return LastError;
    }
    memset(v14, 0, sizeof(v14));
    v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
           v14,
           v5,
           v16,
           L"CentralProfile");
    LastError = v7;
    if ( v7 < 0 )
    {
      if ( v7 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9AA,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)(unsigned int)v7,
          dwCreationDisposition);
        goto LABEL_13;
      }
    }
    else
    {
      if ( v14[0] && *(_WORD *)v14[0] )
        goto LABEL_9;
      memset(lpFileName, 0, sizeof(lpFileName));
      v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
      v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             lpFileName,
             L"%s\\%s",
             v8,
             L"ntuser.dat");
      LastError = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x98E,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)(unsigned int)v9,
          dwCreationDisposition);
LABEL_12:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
LABEL_13:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v14);
        goto LABEL_20;
      }
      FileW = CreateFileW(lpFileName[0], 0x40000000u, 1u, 0, 3u, 0x80u, 0);
      v20 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
LABEL_9:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v14);
        LastError = 1;
        goto LABEL_20;
      }
      LastWriteTime = (FILETIME)119600064000000000LL;
      if ( !SetFileTime(FileW, 0, 0, &LastWriteTime) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x9A6,
                      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                      v11);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
        goto LABEL_12;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v14);
    LastError = 0;
    goto LABEL_20;
  }
  return 1;
}

```

## disassembly

```asm
0x180016ff8  mov     [rsp-8+arg_10], rbx
0x180016ffd  push    rbp
0x180016ffe  push    rsi
0x180016fff  push    rdi
0x180017000  lea     rbp, [rsp-47h]
0x180017005  sub     rsp, 90h
0x18001700c  mov     rdi, rcx
0x18001700f  mov     rcx, [rcx+8]
0x180017013  mov     rax, [rcx]
0x180017016  mov     rax, [rax+10h]
0x18001701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701f  test    al, 8
0x180017021  jnz     loc_18001725D
0x180017027  mov     rcx, [rdi+8]
0x18001702b  mov     rax, [rcx]
0x18001702e  mov     rax, [rax+10h]
0x180017032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017037  test    al, 1
0x180017039  jnz     loc_18001725D
0x18001703f  mov     rcx, [rdi+8]
0x180017043  mov     rax, [rcx]
0x180017046  mov     rax, [rax+10h]
0x18001704a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001704f  bt      eax, 0Bh
0x180017053  jb      loc_18001725D
0x180017059  xor     esi, esi
0x18001705b  mov     [rbp+57h+var_30], rsi
0x18001705f  mov     [rbp+57h+var_28], rsi
0x180017063  mov     [rbp+57h+var_20], rsi
0x180017067  lea     rcx, [rbp+57h+var_30]
0x18001706b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017070  mov     [rbp+57h+var_28], 0FFFFFFFFFFFFFFFFh
0x180017078  mov     [rbp+57h+var_20], 0FFFFFFFFFFFFFFFFh
0x180017080  mov     rcx, [rdi+8]
0x180017084  mov     rax, [rcx]
0x180017087  mov     rax, [rax+20h]
0x18001708b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017090  lea     rdx, [rbp+57h+var_30]; unsigned __int16 **
0x180017094  mov     rcx, rax; unsigned __int16 *
0x180017097  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18001709c  mov     ebx, eax
0x18001709e  test    eax, eax
0x1800170a0  jns     short loc_1800170BF
0x1800170a2  mov     rcx, [rbp+5Fh]; this
0x1800170a6  mov     r9d, eax; char *
0x1800170a9  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800170b0  mov     edx, 97Eh; void *
0x1800170b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800170ba  jmp     loc_18001722C
0x1800170bf  mov     [rbp+57h+var_60], rsi
0x1800170c3  mov     [rbp+57h+var_58], rsi
0x1800170c7  mov     [rbp+57h+var_50], rsi
0x1800170cb  lea     r9, aCentralprofile; "CentralProfile"
0x1800170d2  mov     r8, [rbp+57h+var_30]
0x1800170d6  lea     rcx, [rbp+57h+var_60]
0x1800170da  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800170df  mov     ebx, eax
0x1800170e1  test    eax, eax
0x1800170e3  js      loc_180017239
0x1800170e9  mov     rax, [rbp+57h+var_60]
0x1800170ed  test    rax, rax
0x1800170f0  jz      short loc_18001710A
0x1800170f2  cmp     [rax], si
0x1800170f5  jz      short loc_18001710A
0x1800170f7  lea     rcx, [rbp+57h+var_60]
0x1800170fb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017100  mov     ebx, 1
0x180017105  jmp     loc_18001722C
0x18001710a  mov     [rbp+57h+lpFileName], rsi
0x18001710e  mov     [rbp+57h+var_40], rsi
0x180017112  mov     [rbp+57h+var_38], rsi
0x180017116  mov     rcx, [rdi+8]
0x18001711a  mov     rax, [rcx]
0x18001711d  mov     rax, [rax+48h]
0x180017121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017126  mov     r8, rax
0x180017129  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180017130  lea     rdx, aSS; "%s\\%s"
0x180017137  lea     rcx, [rbp+57h+lpFileName]
0x18001713b  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180017140  mov     ebx, eax
0x180017142  test    eax, eax
0x180017144  jns     short loc_180017177
0x180017146  mov     rcx, [rbp+5Fh]; this
0x18001714a  mov     r9d, eax; char *
0x18001714d  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180017154  mov     edx, 98Eh; void *
0x180017159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001715e  nop
0x18001715f  lea     rcx, [rbp+57h+lpFileName]
0x180017163  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017168  nop
0x180017169  lea     rcx, [rbp+57h+var_60]
0x18001716d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017172  jmp     loc_18001722C
0x180017177  mov     [rsp+0A0h+hTemplateFile], rsi; hTemplateFile
0x18001717c  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180017184  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001718c  xor     r9d, r9d; lpSecurityAttributes
0x18001718f  mov     edx, 40000000h; dwDesiredAccess
0x180017194  lea     r8d, [r9+1]; dwShareMode
0x180017198  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18001719c  call    cs:__imp_CreateFileW
0x1800171a2  mov     [rbp+57h+arg_0], rax
0x1800171a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800171aa  jnz     short loc_1800171C4
0x1800171ac  lea     rcx, [rbp+57h+arg_0]
0x1800171b0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800171b5  nop
0x1800171b6  lea     rcx, [rbp+57h+lpFileName]
0x1800171ba  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800171bf  jmp     loc_1800170F7
0x1800171c4  mov     rcx, 1A8E79FE1D58000h
0x1800171ce  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], rcx
0x1800171d2  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x1800171d6  xor     r8d, r8d; lpLastAccessTime
0x1800171d9  xor     edx, edx; lpCreationTime
0x1800171db  mov     rcx, rax; hFile
0x1800171de  call    cs:__imp_SetFileTime
0x1800171e4  test    eax, eax
0x1800171e6  jnz     short loc_18001720D
0x1800171e8  mov     rcx, [rbp+5Fh]; this
0x1800171ec  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800171f3  mov     edx, 9A6h; void *
0x1800171f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800171fd  mov     ebx, eax
0x1800171ff  lea     rcx, [rbp+57h+arg_0]
0x180017203  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017208  jmp     loc_18001715F
0x18001720d  lea     rcx, [rbp+57h+arg_0]
0x180017211  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017216  nop
0x180017217  lea     rcx, [rbp+57h+lpFileName]
0x18001721b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017220  nop
0x180017221  lea     rcx, [rbp+57h+var_60]
0x180017225  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001722a  mov     ebx, esi
0x18001722c  lea     rcx, [rbp+57h+var_30]
0x180017230  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017235  mov     eax, ebx
0x180017237  jmp     short loc_180017262
0x180017239  cmp     eax, 80070002h
0x18001723e  jz      short loc_180017221
0x180017240  mov     rcx, [rbp+5Fh]; this
0x180017244  mov     r9d, eax; char *
0x180017247  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18001724e  mov     edx, 9AAh; void *
0x180017253  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017258  jmp     loc_180017169
0x18001725d  mov     eax, 1
0x180017262  mov     rbx, [rsp+0A0h+arg_10]
0x18001726a  add     rsp, 90h
0x180017271  pop     rdi
0x180017272  pop     rsi
0x180017273  pop     rbp
0x180017274  retn
```
