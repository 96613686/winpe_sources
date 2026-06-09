# CUserProfileRoamingProvider::_SetNtUserPolTime(ushort const *,int)

- ea: `0x180009588`
- end: `0x180009769`
- name: `?_SetNtUserPolTime@CUserProfileRoamingProvider@@AEAAJPEBGH@Z`
- size: `481`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008258`

## callees

- `0x180005234`
- `0x180005424`
- `0x18000547c`
- `0x180006a9c`
- `0x180009588`
- `0x18000a520`
- `0x180011454`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800096da`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800096da`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180009718`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180009718`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000962d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000962d`

## string_xrefs

- `0x1800095fa`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18000963b`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18000968f`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800096f3`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_SetNtUserPolTime(
        CUserProfileRoamingProvider *this,
        const unsigned __int16 *a2,
        int a3)
{
  const unsigned __int16 *v4; // r9
  int v5; // eax
  unsigned int LastError; // ebx
  const char *v7; // r9
  int v8; // eax
  HANDLE FileW; // rax
  const char *v10; // r9
  __int64 v11; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-39h]
  HANDLE v14; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR v15[3]; // [rsp+48h] [rbp-11h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+60h] [rbp+7h] BYREF
  __int128 FileInformation; // [rsp+78h] [rbp+1Fh] BYREF
  FILETIME LastWriteTime[2]; // [rsp+88h] [rbp+2Fh] BYREF
  int v19; // [rsp+98h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  memset(lpFileName, 0, sizeof(lpFileName));
  v4 = L"ntuser.tmp";
  if ( !a3 )
    v4 = L"ntuser.dat";
  v5 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         a2,
         v4);
  LastError = v5;
  if ( v5 >= 0 )
  {
    v19 = 0;
    FileInformation = 0;
    *(_OWORD *)&LastWriteTime[0].dwLowDateTime = 0;
    if ( GetFileAttributesExW(lpFileName[0], GetFileExInfoStandard, &FileInformation) )
    {
      memset(v15, 0, sizeof(v15));
      v8 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             v15,
             L"%s\\%s",
             a2,
             L"ntuser.pol");
      LastError = v8;
      if ( v8 >= 0 )
      {
        FileW = CreateFileW(v15[0], 0x100u, 7u, 0, 3u, 0x80u, 0);
        v14 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v11 = 2759;
        }
        else
        {
          if ( SetFileTime(FileW, 0, 0, (const FILETIME *)&LastWriteTime[0].dwHighDateTime) )
          {
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v15);
            LastError = 0;
            goto LABEL_16;
          }
          v11 = 2761;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v11,
                      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                      v10);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAC0,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)(unsigned int)v8,
          dwCreationDisposition);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xABC,
                    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                    v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB9,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
  }
LABEL_16:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x180009588  mov     [rsp-8+arg_0], rbx
0x18000958d  mov     [rsp-8+arg_10], rdi
0x180009592  push    rbp
0x180009593  lea     rbp, [rsp-57h]
0x180009598  sub     rsp, 0B0h
0x18000959f  mov     rax, cs:__security_cookie
0x1800095a6  xor     rax, rsp
0x1800095a9  mov     [rbp+57h+var_10], rax
0x1800095ad  test    r8d, r8d
0x1800095b0  mov     [rbp+57h+lpFileName], 0
0x1800095b8  lea     rax, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x1800095bf  mov     [rbp+57h+var_48], 0
0x1800095c7  mov     rdi, rdx
0x1800095ca  mov     [rbp+57h+var_40], 0
0x1800095d2  mov     r8, rdx
0x1800095d5  lea     r9, ?c_szNTUserTmp@@3QBGB; "ntuser.tmp"
0x1800095dc  cmovz   r9, rax
0x1800095e0  lea     rdx, aSS; "%s\\%s"
0x1800095e7  lea     rcx, [rbp+57h+lpFileName]
0x1800095eb  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800095f0  mov     ebx, eax
0x1800095f2  test    eax, eax
0x1800095f4  jns     short loc_180009613
0x1800095f6  mov     rcx, [rbp+5Fh]; this
0x1800095fa  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009601  mov     r9d, eax; char *
0x180009604  mov     edx, 0AB9h; void *
0x180009609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000960e  jmp     loc_18000973D
0x180009613  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180009617  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18000961b  xorps   xmm0, xmm0
0x18000961e  xor     eax, eax
0x180009620  xor     edx, edx; fInfoLevelId
0x180009622  mov     [rbp+57h+var_18], eax
0x180009625  movups  [rbp+57h+FileInformation], xmm0
0x180009629  movups  xmmword ptr [rbp+57h+LastWriteTime.dwLowDateTime], xmm0
0x18000962d  call    cs:__imp_GetFileAttributesExW
0x180009633  test    eax, eax
0x180009635  jnz     short loc_180009653
0x180009637  mov     rcx, [rbp+5Fh]; this
0x18000963b  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009642  mov     edx, 0ABCh; void *
0x180009647  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000964c  mov     ebx, eax
0x18000964e  jmp     loc_18000973D
0x180009653  lea     r9, ?c_szNTUserPol@@3QBGB; "ntuser.pol"
0x18000965a  mov     [rbp+57h+var_68], 0
0x180009662  mov     r8, rdi
0x180009665  mov     [rbp+57h+var_60], 0
0x18000966d  lea     rdx, aSS; "%s\\%s"
0x180009674  mov     [rbp+57h+var_58], 0
0x18000967c  lea     rcx, [rbp+57h+var_68]
0x180009680  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180009685  mov     ebx, eax
0x180009687  test    eax, eax
0x180009689  jns     short loc_1800096B1
0x18000968b  mov     rcx, [rbp+5Fh]; this
0x18000968f  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009696  mov     r9d, eax; char *
0x180009699  mov     edx, 0AC0h; void *
0x18000969e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096a3  lea     rcx, [rbp+57h+var_68]
0x1800096a7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800096ac  jmp     loc_18000973D
0x1800096b1  mov     rcx, [rbp+57h+var_68]; lpFileName
0x1800096b5  xor     r9d, r9d; lpSecurityAttributes
0x1800096b8  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1800096c1  mov     edx, 100h; dwDesiredAccess
0x1800096c6  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800096ce  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800096d6  lea     r8d, [r9+7]; dwShareMode
0x1800096da  call    cs:__imp_CreateFileW
0x1800096e0  mov     [rbp+57h+var_70], rax
0x1800096e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800096e8  jnz     short loc_18000970C
0x1800096ea  mov     edx, 0AC7h; void *
0x1800096ef  mov     rcx, [rbp+5Fh]; this
0x1800096f3  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800096fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800096ff  lea     rcx, [rbp+57h+var_70]
0x180009703  mov     ebx, eax
0x180009705  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000970a  jmp     short loc_1800096A3
0x18000970c  lea     r9, [rbp+57h+LastWriteTime.dwHighDateTime]; lpLastWriteTime
0x180009710  xor     r8d, r8d; lpLastAccessTime
0x180009713  xor     edx, edx; lpCreationTime
0x180009715  mov     rcx, rax; hFile
0x180009718  call    cs:__imp_SetFileTime
0x18000971e  test    eax, eax
0x180009720  jnz     short loc_180009729
0x180009722  mov     edx, 0AC9h
0x180009727  jmp     short loc_1800096EF
0x180009729  lea     rcx, [rbp+57h+var_70]
0x18000972d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009732  lea     rcx, [rbp+57h+var_68]
0x180009736  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000973b  xor     ebx, ebx
0x18000973d  lea     rcx, [rbp+57h+lpFileName]
0x180009741  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009746  mov     eax, ebx
0x180009748  mov     rcx, [rbp+57h+var_10]
0x18000974c  xor     rcx, rsp; StackCookie
0x18000974f  call    __security_check_cookie
0x180009754  lea     r11, [rsp+0B0h+var_s0]
0x18000975c  mov     rbx, [r11+10h]
0x180009760  mov     rdi, [r11+20h]
0x180009764  mov     rsp, r11
0x180009767  pop     rbp
0x180009768  retn
```
