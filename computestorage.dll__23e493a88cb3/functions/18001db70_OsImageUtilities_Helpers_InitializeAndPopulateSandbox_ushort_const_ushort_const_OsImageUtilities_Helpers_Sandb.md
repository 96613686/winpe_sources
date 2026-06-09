# OsImageUtilities::Helpers::InitializeAndPopulateSandbox(ushort const *,ushort const *,OsImageUtilities::Helpers::SandboxOptions const &,_WC_NESTING_MODE)

- ea: `0x18001db70`
- end: `0x18001ddb8`
- name: `?InitializeAndPopulateSandbox@Helpers@OsImageUtilities@@YAXPEBG0AEBUSandboxOptions@12@W4_WC_NESTING_MODE@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180002690`
- `0x180008a8c`
- `0x180008fac`
- `0x18000971c`
- `0x18000a578`
- `0x1800127bc`
- `0x180012838`
- `0x18001db70`
- `0x1800207ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001dc52`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001dc52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc63`
- `wc_storage!WcCreateSandboxStubFiles` at `0x18001dce1`
- `wc_storage!WcCreateSandboxStubFiles` at `0x18001dce1`
- `wc_storage!WcInitializeSandbox` at `0x18001dc06`
- `wc_storage!WcInitializeSandbox` at `0x18001dc06`

## string_xrefs

- `0x18001dd05`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001dd77`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001dda6`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001dcf6`: `relative path: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall OsImageUtilities::Helpers::InitializeAndPopulateSandbox(
        const WCHAR *a1,
        const WCHAR *a2,
        unsigned __int64 *a3,
        unsigned int a4)
{
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  const char *v11; // r9
  unsigned __int64 i; // rsi
  const WCHAR *v13; // rcx
  DWORD LastError; // eax
  unsigned __int64 v15; // rax
  const char *v16; // rbx
  char v17; // cl
  char **v18; // rax
  LPCWSTR *v19; // r9
  unsigned int SandboxStubFiles; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r8
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-99h]
  char *v28; // [rsp+28h] [rbp-91h]
  LPCWSTR lpFileName[3]; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int64 v30; // [rsp+58h] [rbp-61h]
  __int128 v31; // [rsp+60h] [rbp-59h] BYREF
  __int64 v32; // [rsp+70h] [rbp-49h]
  __int128 v33; // [rsp+78h] [rbp-41h] BYREF
  __int64 v34; // [rsp+88h] [rbp-31h]
  __int128 v35; // [rsp+90h] [rbp-29h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-19h]
  char *Src[4]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v35 = 0;
  v36 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v35, 17);
  v33 = 0;
  v34 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v33, 18);
  v31 = 0;
  v32 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v31, 10);
  v8 = WcInitializeSandbox(a1, a3[2], (__int64)(a3[3] - a3[2]) >> 5, a4);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v27);
  for ( i = 0; i < *a3; ++i )
  {
    Vml::CombineFilePath(lpFileName, a2, *(PCWSTR *)(a3[1] + 16 * i));
    v13 = (const WCHAR *)lpFileName;
    if ( v30 > 7 )
      v13 = lpFileName[0];
    if ( GetFileAttributesW(v13) == -1 )
    {
      LastError = GetLastError();
      if ( LastError - 2 > 1 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
          (const char *)LastError,
          (unsigned int)"%ws",
          *(const char **)(a3[1] + 16 * i));
    }
    else
    {
      Vml::CombineFilePath(Src, a1, *(PCWSTR *)(a3[1] + 16 * i));
      v15 = a3[1];
      v16 = *(const char **)(v15 + 16 * i);
      v17 = *(_BYTE *)(v15 + 16 * i + 8);
      v18 = Src;
      if ( Src[3] > (char *)7 )
        v18 = (char **)Src[0];
      v19 = lpFileName;
      if ( v30 > 7 )
        v19 = (LPCWSTR *)lpFileName[0];
      LOBYTE(v28) = v17;
      SandboxStubFiles = WcCreateSandboxStubFiles(a1, a3[2], (__int64)(a3[3] - a3[2]) >> 5, v19, v18, v28, a4);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)SandboxStubFiles,
        (int)"relative path: %ws",
        v16);
      std::wstring::~wstring(Src);
    }
    std::wstring::~wstring((char **)lpFileName);
  }
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v31, v9, v10, v11);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v33, v21, v22, v23);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v35, v24, v25, v26);
}

```

## disassembly

```asm
0x18001db70  push    rbp
0x18001db72  push    rbx
0x18001db73  push    rsi
0x18001db74  push    rdi
0x18001db75  push    r12
0x18001db77  push    r13
0x18001db79  push    r14
0x18001db7b  push    r15
0x18001db7d  lea     rbp, [rsp-1Fh]
0x18001db82  sub     rsp, 0D8h
0x18001db89  mov     rax, cs:__security_cookie
0x18001db90  xor     rax, rsp
0x18001db93  mov     [rbp+57h+var_48], rax
0x18001db97  mov     r13d, r9d
0x18001db9a  mov     rdi, r8
0x18001db9d  mov     r15, rdx
0x18001dba0  mov     r12, rcx
0x18001dba3  xorps   xmm0, xmm0
0x18001dba6  xor     eax, eax
0x18001dba8  movups  [rbp+57h+var_80], xmm0
0x18001dbac  mov     [rbp+57h+var_70], rax
0x18001dbb0  lea     edx, [rax+11h]; int
0x18001dbb3  lea     rcx, [rbp+57h+var_80]; this
0x18001dbb7  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001dbbc  nop
0x18001dbbd  xorps   xmm0, xmm0
0x18001dbc0  xor     eax, eax
0x18001dbc2  movups  [rbp+57h+var_98], xmm0
0x18001dbc6  mov     [rbp+57h+var_88], rax
0x18001dbca  lea     edx, [rax+12h]; int
0x18001dbcd  lea     rcx, [rbp+57h+var_98]; this
0x18001dbd1  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001dbd6  nop
0x18001dbd7  xorps   xmm0, xmm0
0x18001dbda  xor     eax, eax
0x18001dbdc  movups  [rbp+57h+var_B0], xmm0
0x18001dbe0  mov     [rbp+57h+var_A0], rax
0x18001dbe4  lea     edx, [rax+0Ah]; int
0x18001dbe7  lea     rcx, [rbp+57h+var_B0]; this
0x18001dbeb  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001dbf0  nop
0x18001dbf1  mov     rdx, [rdi+10h]
0x18001dbf5  mov     r8, [rdi+18h]
0x18001dbf9  sub     r8, rdx
0x18001dbfc  sar     r8, 5
0x18001dc00  mov     r9d, r13d
0x18001dc03  mov     rcx, r12
0x18001dc06  call    cs:__imp_WcInitializeSandbox
0x18001dc0d  nop     dword ptr [rax+rax+00h]
0x18001dc12  mov     rcx, [rbp+5Fh]; this
0x18001dc16  test    eax, eax
0x18001dc18  js      loc_18001DD74
0x18001dc1e  xor     esi, esi
0x18001dc20  cmp     [rdi], rsi
0x18001dc23  jbe     loc_18001DD36
0x18001dc29  mov     r14, rsi
0x18001dc2c  add     r14, r14
0x18001dc2f  mov     r8, [rdi+8]
0x18001dc33  mov     r8, [r8+r14*8]; pszMore
0x18001dc37  mov     rdx, r15; pszPathIn
0x18001dc3a  lea     rcx, [rbp+57h+lpFileName]; Src
0x18001dc3e  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001dc43  nop
0x18001dc44  lea     rcx, [rbp+57h+lpFileName]
0x18001dc48  cmp     [rbp+57h+var_B8], 7
0x18001dc4d  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18001dc52  call    cs:__imp_GetFileAttributesW
0x18001dc59  nop     dword ptr [rax+rax+00h]
0x18001dc5e  cmp     eax, 0FFFFFFFFh
0x18001dc61  jnz     short loc_18001DC83
0x18001dc63  call    cs:__imp_GetLastError
0x18001dc6a  nop     dword ptr [rax+rax+00h]
0x18001dc6f  mov     r9d, eax; char *
0x18001dc72  lea     ecx, [rax-2]
0x18001dc75  cmp     ecx, 1
0x18001dc78  ja      loc_18001DD89
0x18001dc7e  jmp     loc_18001DD21
0x18001dc83  mov     r8, [rdi+8]
0x18001dc87  mov     r8, [r8+r14*8]; pszMore
0x18001dc8b  mov     rdx, r12; pszPathIn
0x18001dc8e  lea     rcx, [rbp+57h+Src]; Src
0x18001dc92  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001dc97  nop
0x18001dc98  mov     rax, [rdi+8]
0x18001dc9c  mov     rbx, [rax+r14*8]
0x18001dca0  mov     cl, [rax+r14*8+8]
0x18001dca5  lea     rax, [rbp+57h+Src]
0x18001dca9  cmp     [rbp+57h+var_50], 7
0x18001dcae  cmova   rax, [rbp+57h+Src]
0x18001dcb3  lea     r9, [rbp+57h+lpFileName]
0x18001dcb7  cmp     [rbp+57h+var_B8], 7
0x18001dcbc  cmova   r9, [rbp+57h+lpFileName]
0x18001dcc1  mov     rdx, [rdi+10h]
0x18001dcc5  mov     r8, [rdi+18h]
0x18001dcc9  sub     r8, rdx
0x18001dccc  sar     r8, 5
0x18001dcd0  mov     [rsp+110h+var_E0], r13d
0x18001dcd5  mov     byte ptr [rsp+110h+var_E8], cl
0x18001dcd9  mov     qword ptr [rsp+110h+var_F0], rax
0x18001dcde  mov     rcx, r12
0x18001dce1  call    cs:__imp_WcCreateSandboxStubFiles
0x18001dce8  nop     dword ptr [rax+rax+00h]
0x18001dced  mov     rcx, [rbp+5Fh]; this
0x18001dcf1  mov     [rsp+110h+var_E8], rbx; char *
0x18001dcf6  lea     rdx, aRelativePathWs; "relative path: %ws"
0x18001dcfd  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18001dd02  mov     r9d, eax; char *
0x18001dd05  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001dd0c  mov     edx, 132h; void *
0x18001dd11  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001dd16  nop
0x18001dd17  lea     rcx, [rbp+57h+Src]
0x18001dd1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dd20  nop
0x18001dd21  lea     rcx, [rbp+57h+lpFileName]
0x18001dd25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dd2a  inc     rsi
0x18001dd2d  cmp     rsi, [rdi]
0x18001dd30  jb      loc_18001DC29
0x18001dd36  lea     rcx, [rbp+57h+var_B0]; this
0x18001dd3a  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001dd3f  nop
0x18001dd40  lea     rcx, [rbp+57h+var_98]; this
0x18001dd44  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001dd49  nop
0x18001dd4a  lea     rcx, [rbp+57h+var_80]; this
0x18001dd4e  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001dd53  mov     rcx, [rbp+57h+var_48]
0x18001dd57  xor     rcx, rsp; StackCookie
0x18001dd5a  call    __security_check_cookie
0x18001dd5f  add     rsp, 0D8h
0x18001dd66  pop     r15
0x18001dd68  pop     r14
0x18001dd6a  pop     r13
0x18001dd6c  pop     r12
0x18001dd6e  pop     rdi
0x18001dd6f  pop     rsi
0x18001dd70  pop     rbx
0x18001dd71  pop     rbp
0x18001dd72  retn
0x18001dd74  mov     r9d, eax; char *
0x18001dd77  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001dd7e  mov     edx, 118h; void *
0x18001dd83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dd89  mov     rax, [rdi+8]
0x18001dd8d  mov     rcx, [rbp+5Fh]; this
0x18001dd91  mov     rax, [rax+r14*8]
0x18001dd95  mov     [rsp+110h+var_E8], rax; char *
0x18001dd9a  lea     rax, aWs; "%ws"
0x18001dda1  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x18001dda6  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001ddad  mov     edx, 122h; void *
0x18001ddb2  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
