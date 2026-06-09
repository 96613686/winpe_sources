# CUserProfileRoamingProvider::_SetLocalNtUserIni(void)

- ea: `0x180008f88`
- end: `0x1800090d7`
- name: `?_SetLocalNtUserIni@CUserProfileRoamingProvider@@AEAAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008258`

## callees

- `0x180005234`
- `0x180005424`
- `0x18000547c`
- `0x180006a9c`
- `0x180008f88`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180009095`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180009095`

## string_xrefs

- `0x180008fcf`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18000902d`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800090a4`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_SetLocalNtUserIni(CUserProfileRoamingProvider *this)
{
  __int64 *v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rax
  int v8; // eax
  const WCHAR *v9; // rax
  const char *v10; // r9
  LPCWSTR lpFileName[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (__int64 *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = (*(__int64 (__fastcall **)(__int64 *))(*v2 + 72))(v2);
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v3 + 200))(v2, v4);
  LastError = v5;
  if ( v5 >= 0 )
  {
    memset(lpFileName, 0, 24);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
    v8 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
           lpFileName,
           L"%s\\%s",
           v7,
           L"ntuser.ini");
    LastError = v8;
    if ( v8 >= 0 )
    {
      if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1))
        && *(_WORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1)) )
      {
        v9 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1));
      }
      else
      {
        v9 = 0;
      }
      if ( WritePrivateProfileStringW(L"General", L"ExclusionList", v9, lpFileName[0]) )
        LastError = 0;
      else
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xAA3,
                      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                      v10);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9D,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v8,
        (int)lpFileName[0]);
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9A,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v5,
      (int)lpFileName[0]);
  }
  return LastError;
}

```

## disassembly

```asm
0x180008f88  mov     [rsp+arg_0], rbx
0x180008f8d  mov     [rsp+arg_8], rsi
0x180008f92  push    rdi
0x180008f93  sub     rsp, 40h
0x180008f97  mov     rsi, rcx
0x180008f9a  mov     rdi, [rcx+8]
0x180008f9e  mov     rbx, [rdi]
0x180008fa1  mov     rcx, rdi
0x180008fa4  mov     rax, [rbx+48h]
0x180008fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fad  mov     rdx, rax
0x180008fb0  mov     rcx, rdi
0x180008fb3  mov     rax, [rbx+0C8h]
0x180008fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fbf  mov     ebx, eax
0x180008fc1  xor     edi, edi
0x180008fc3  test    eax, eax
0x180008fc5  jns     short loc_180008FE5
0x180008fc7  mov     rcx, [rsp+48h]; this
0x180008fcc  mov     r9d, eax; char *
0x180008fcf  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180008fd6  mov     edx, 0A9Ah; void *
0x180008fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fe0  jmp     loc_1800090C5
0x180008fe5  mov     [rsp+48h+lpFileName], rdi; int
0x180008fea  mov     [rsp+48h+var_20], rdi
0x180008fef  mov     [rsp+48h+var_18], rdi
0x180008ff4  mov     rcx, [rsi+8]
0x180008ff8  mov     rax, [rcx]
0x180008ffb  mov     rax, [rax+48h]
0x180008fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009004  mov     r8, rax
0x180009007  lea     r9, ?c_szNTUserIni@@3QBGB; "ntuser.ini"
0x18000900e  lea     rdx, aSS; "%s\\%s"
0x180009015  lea     rcx, [rsp+48h+lpFileName]
0x18000901a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000901f  mov     ebx, eax
0x180009021  test    eax, eax
0x180009023  jns     short loc_180009040
0x180009025  mov     rcx, [rsp+48h]; this
0x18000902a  mov     r9d, eax; char *
0x18000902d  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009034  mov     edx, 0A9Dh; void *
0x180009039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000903e  jmp     short loc_1800090BB
0x180009040  mov     rcx, [rsi+8]
0x180009044  mov     rax, [rcx]
0x180009047  mov     rax, [rax+68h]
0x18000904b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009050  test    rax, rax
0x180009053  jz      short loc_18000907C
0x180009055  mov     rcx, [rsi+8]
0x180009059  mov     rax, [rcx]
0x18000905c  mov     rax, [rax+68h]
0x180009060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009065  cmp     [rax], di
0x180009068  jz      short loc_18000907C
0x18000906a  mov     rcx, [rsi+8]
0x18000906e  mov     rax, [rcx]
0x180009071  mov     rax, [rax+68h]
0x180009075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907a  jmp     short loc_18000907F
0x18000907c  mov     rax, rdi
0x18000907f  mov     r9, [rsp+48h+lpFileName]; lpFileName
0x180009084  mov     r8, rax; lpString
0x180009087  lea     rdx, aExclusionlist; "ExclusionList"
0x18000908e  lea     rcx, aGeneral; "General"
0x180009095  call    cs:__imp_WritePrivateProfileStringW
0x18000909b  test    eax, eax
0x18000909d  jnz     short loc_1800090B9
0x18000909f  mov     rcx, [rsp+48h]; this
0x1800090a4  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800090ab  mov     edx, 0AA3h; void *
0x1800090b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800090b5  mov     ebx, eax
0x1800090b7  jmp     short loc_1800090BB
0x1800090b9  mov     ebx, edi
0x1800090bb  lea     rcx, [rsp+48h+lpFileName]
0x1800090c0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800090c5  mov     eax, ebx
0x1800090c7  mov     rbx, [rsp+48h+arg_0]
0x1800090cc  mov     rsi, [rsp+48h+arg_8]
0x1800090d1  add     rsp, 40h
0x1800090d5  pop     rdi
0x1800090d6  retn
```
