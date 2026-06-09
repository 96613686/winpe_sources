# CPath::VerifyAccess(char const *)

- ea: `0x1800a66f4`
- end: `0x1800a6883`
- name: `?VerifyAccess@CPath@@SAJPEBD@Z`
- size: `399`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18009b880`
- `0x1800d55e8`
- `0x1800dae88`

## callees

- `0x180008618`
- `0x180008b1c`
- `0x18000933c`
- `0x18000ef98`
- `0x1800a6520`
- `0x1800a66f4`
- `0x1800a979c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a6847`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a6847`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800a6783`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800a681c`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800a6783`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800a681c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a67d5`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a67d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPath::VerifyAccess(const char *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  const WCHAR *v4; // rcx
  WCHAR *v5; // rcx
  DWORD v6; // eax
  int LastError; // eax
  const WCHAR *v8; // rcx
  const char *v9; // r9
  int psidGroup; // [rsp+28h] [rbp-E0h]
  unsigned int psidGroupa; // [rsp+28h] [rbp-E0h]
  struct _ACL pDacl; // [rsp+48h] [rbp-C0h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp-A0h]
  WCHAR TempFileName[264]; // [rsp+78h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v2 = CPath::Create(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    UTF8toWstr(lpPathName, a1, 0);
    v4 = (const WCHAR *)lpPathName;
    if ( v15 > 7 )
      v4 = lpPathName[0];
    if ( !GetTempFileNameW(v4, L"do", 0, TempFileName) )
    {
      pDacl = (struct _ACL)524292LL;
      v5 = (WCHAR *)lpPathName;
      if ( v15 > 7 )
        v5 = (WCHAR *)lpPathName[0];
      v6 = SetNamedSecurityInfoW(v5, SE_FILE_OBJECT, 0x20000004u, 0, 0, &pDacl, 0);
      if ( v6 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x23F,
                      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
                      (const char *)v6,
                      psidGroupa);
LABEL_14:
        v3 = LastError;
LABEL_16:
        std::wstring::~wstring(lpPathName);
        return v3;
      }
      v8 = (const WCHAR *)lpPathName;
      if ( v15 > 7 )
        v8 = lpPathName[0];
      if ( !GetTempFileNameW(v8, L"do", 0, TempFileName) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x242,
                      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
                      v9);
        goto LABEL_14;
      }
    }
    DeleteFileW(TempFileName);
    v3 = 0;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x223,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
    (const char *)(unsigned int)v2,
    psidGroup);
  return v3;
}

```

## disassembly

```asm
0x1800a66f4  mov     rax, rsp
0x1800a66f7  mov     [rax+10h], rbx
0x1800a66fb  mov     [rax+18h], rsi
0x1800a66ff  mov     [rax+20h], rdi
0x1800a6703  push    rbp
0x1800a6704  lea     rbp, [rax-198h]
0x1800a670b  sub     rsp, 290h
0x1800a6712  mov     rax, cs:__security_cookie
0x1800a6719  xor     rax, rsp
0x1800a671c  mov     [rbp+190h+var_10], rax
0x1800a6723  mov     rdi, rcx
0x1800a6726  call    ?Create@CPath@@SAJPEBD@Z; CPath::Create(char const *)
0x1800a672b  mov     ebx, eax
0x1800a672d  xor     esi, esi
0x1800a672f  test    eax, eax
0x1800a6731  jns     short loc_1800A6753
0x1800a6733  mov     rcx, [rbp+198h]; this
0x1800a673a  mov     r9d, eax; char *
0x1800a673d  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a6744  mov     edx, 223h; void *
0x1800a6749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a674e  jmp     loc_1800A6859
0x1800a6753  xor     r8d, r8d
0x1800a6756  mov     rdx, rdi
0x1800a6759  lea     rcx, [rsp+290h+lpPathName]
0x1800a675e  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800a6763  lea     rcx, [rsp+290h+lpPathName]
0x1800a6768  cmp     [rsp+290h+var_230], 7
0x1800a676e  cmova   rcx, [rsp+290h+lpPathName]; lpPathName
0x1800a6774  lea     r9, [rsp+290h+TempFileName]; lpTempFileName
0x1800a6779  xor     r8d, r8d; uUnique
0x1800a677c  lea     rdx, PrefixString; "do"
0x1800a6783  call    cs:__imp_GetTempFileNameW
0x1800a6789  test    eax, eax
0x1800a678b  jnz     loc_1800A6842
0x1800a6791  mov     qword ptr [rsp+290h+var_250.AclRevision], rsi
0x1800a6796  mov     [rsp+290h+var_250.AclRevision], 4
0x1800a679b  mov     dword ptr [rsp+290h+var_250.AclSize], 8
0x1800a67a3  lea     rcx, [rsp+290h+lpPathName]
0x1800a67a8  cmp     [rsp+290h+var_230], 7
0x1800a67ae  cmova   rcx, [rsp+290h+lpPathName]; pObjectName
0x1800a67b4  mov     [rsp+290h+pSacl], rsi; pSacl
0x1800a67b9  lea     rax, [rsp+290h+var_250]
0x1800a67be  mov     [rsp+290h+pDacl], rax; pDacl
0x1800a67c3  mov     [rsp+290h+psidGroup], rsi; unsigned int
0x1800a67c8  xor     r9d, r9d; psidOwner
0x1800a67cb  lea     edx, [r9+1]; ObjectType
0x1800a67cf  mov     r8d, 20000004h; SecurityInfo
0x1800a67d5  call    cs:__imp_SetNamedSecurityInfoW
0x1800a67db  test    eax, eax
0x1800a67dd  jz      short loc_1800A67FC
0x1800a67df  mov     rcx, [rbp+198h]; this
0x1800a67e6  mov     r9d, eax; char *
0x1800a67e9  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a67f0  mov     edx, 23Fh; void *
0x1800a67f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a67fa  jmp     short loc_1800A683E
0x1800a67fc  lea     rcx, [rsp+290h+lpPathName]
0x1800a6801  cmp     [rsp+290h+var_230], 7
0x1800a6807  cmova   rcx, [rsp+290h+lpPathName]; lpPathName
0x1800a680d  lea     r9, [rsp+290h+TempFileName]; lpTempFileName
0x1800a6812  xor     r8d, r8d; uUnique
0x1800a6815  lea     rdx, PrefixString; "do"
0x1800a681c  call    cs:__imp_GetTempFileNameW
0x1800a6822  test    eax, eax
0x1800a6824  jnz     short loc_1800A6842
0x1800a6826  mov     rcx, [rbp+198h]; this
0x1800a682d  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a6834  mov     edx, 242h; void *
0x1800a6839  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a683e  mov     ebx, eax
0x1800a6840  jmp     short loc_1800A684F
0x1800a6842  lea     rcx, [rsp+290h+TempFileName]; lpFileName
0x1800a6847  call    cs:__imp_DeleteFileW
0x1800a684d  mov     ebx, esi
0x1800a684f  lea     rcx, [rsp+290h+lpPathName]
0x1800a6854  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a6859  mov     eax, ebx
0x1800a685b  mov     rcx, [rbp+190h+var_10]
0x1800a6862  xor     rcx, rsp; StackCookie
0x1800a6865  call    __security_check_cookie
0x1800a686a  lea     r11, [rsp+290h+var_s0]
0x1800a6872  mov     rbx, [r11+18h]
0x1800a6876  mov     rsi, [r11+20h]
0x1800a687a  mov     rdi, [r11+28h]
0x1800a687e  mov     rsp, r11
0x1800a6881  pop     rbp
0x1800a6882  retn
```
