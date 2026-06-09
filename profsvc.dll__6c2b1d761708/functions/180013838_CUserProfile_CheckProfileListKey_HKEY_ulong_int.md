# CUserProfile::CheckProfileListKey(HKEY__ * *,ulong *,int *)

- ea: `0x180013838`
- end: `0x180013a93`
- name: `?CheckProfileListKey@CUserProfile@@IEAAJPEAPEAUHKEY__@@PEAKPEAH@Z`
- size: `603`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, HKEY *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e63c`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x1800130d0`
- `0x1800133d4`
- `0x180013770`
- `0x180013838`
- `0x180030ad0`
- `0x180031060`
- `0x180037544`
- `0x180040bcc`
- `0x180045494`
- `0x180051820`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800138b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800138b9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800139c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800139c9`

## string_xrefs

- `0x18001389b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001390c`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001396e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800139e0`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180013a1d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180013a46`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::CheckProfileListKey(CUserProfile *this, HKEY *a2, unsigned int *a3, int *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // esi
  int OldKeyFromGuid; // eax
  HKEY v12; // rdx
  int ProfileListKeyNameFromSid; // eax
  unsigned int v14; // eax
  int v15; // eax
  const unsigned __int16 *v16; // r8
  int v17; // eax
  HKEY v18; // rax
  int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int v26; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v26 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = CUserProfile::RestoreKeyFromBackup(this, *((const unsigned __int16 **)this + 6), &hKey, &v26);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = 0;
    if ( !hKey )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      OldKeyFromGuid = CUserProfile::GetOldKeyFromGuid(
                         this,
                         *((HANDLE *)this + 3),
                         *((const unsigned __int16 **)this + 6),
                         &hKey,
                         &v26);
      v9 = OldKeyFromGuid;
      if ( OldKeyFromGuid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x450,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)OldKeyFromGuid,
          dwOptionsa);
LABEL_19:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v9;
      }
      v12 = hKey;
      if ( !hKey )
      {
        lpSubKey = 0;
        v23 = 0;
        v24 = 0;
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
        v23 = -1;
        v24 = -1;
        ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(
                                      *((LPCWCH *)this + 6),
                                      (unsigned __int16 **)&lpSubKey,
                                      (int *)this + 10);
        v9 = ProfileListKeyNameFromSid;
        if ( ProfileListKeyNameFromSid < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x457,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)ProfileListKeyNameFromSid,
            dwOptionsa);
LABEL_10:
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
          goto LABEL_19;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
        if ( v14 )
        {
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x460,
                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                 (const char *)v14,
                 dwOptionsa);
          goto LABEL_10;
        }
        v10 = 1;
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
        v12 = hKey;
      }
      v15 = CUserProfile::CheckUserPrefrenceKey(this, v12, v10);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x465,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v15,
          dwOptionsa);
      v17 = SetOldSidString(*((void **)this + 3), *((const unsigned __int16 **)this + 6), v16);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x468,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v17,
          dwOptionsa);
    }
    v18 = hKey;
    hKey = 0;
    *a2 = v18;
    *a3 = v26;
    *a4 = v10;
    v9 = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x449,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v8,
    dwOptions);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180013838  mov     [rsp-38h+arg_10], rbx
0x18001383d  push    rbp
0x18001383e  push    rsi
0x18001383f  push    rdi
0x180013840  push    r12
0x180013842  push    r13
0x180013844  push    r14
0x180013846  push    r15
0x180013848  mov     rbp, rsp
0x18001384b  sub     rsp, 70h
0x18001384f  mov     r14, r9
0x180013852  mov     r15, r8
0x180013855  mov     r12, rdx
0x180013858  mov     rdi, rcx
0x18001385b  xor     r13d, r13d
0x18001385e  mov     [rdx], r13
0x180013861  mov     [r8], r13d
0x180013864  mov     [r9], r13d
0x180013867  mov     [rbp+arg_0], r13d
0x18001386b  mov     [rbp+hKey], r13
0x18001386f  xor     edx, edx
0x180013871  lea     rcx, [rbp+hKey]
0x180013875  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001387a  lea     r9, [rbp+arg_0]; unsigned int *
0x18001387e  lea     r8, [rbp+hKey]; HKEY *
0x180013882  mov     rdx, [rdi+30h]; unsigned __int16 *
0x180013886  mov     rcx, rdi; this
0x180013889  call    ?RestoreKeyFromBackup@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::RestoreKeyFromBackup(ushort const *,HKEY__ * *,ulong *)
0x18001388e  mov     ebx, eax
0x180013890  test    eax, eax
0x180013892  jns     short loc_1800138CA
0x180013894  mov     rcx, [rbp+38h]; this
0x180013898  mov     r9d, eax; char *
0x18001389b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800138a2  mov     edx, 449h; void *
0x1800138a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138ac  mov     rcx, [rbp+hKey]; hKey
0x1800138b0  test    rcx, rcx
0x1800138b3  jz      loc_180013A78
0x1800138b9  call    cs:__imp_RegCloseKey
0x1800138c0  nop     dword ptr [rax+rax+00h]
0x1800138c5  jmp     loc_180013A78
0x1800138ca  mov     esi, r13d
0x1800138cd  cmp     [rbp+hKey], r13
0x1800138d1  jnz     loc_180013A57
0x1800138d7  xor     edx, edx
0x1800138d9  lea     rcx, [rbp+hKey]
0x1800138dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800138e2  lea     rax, [rbp+arg_0]
0x1800138e6  mov     qword ptr [rsp+70h+dwOptions], rax; int
0x1800138eb  lea     r9, [rbp+hKey]; HKEY *
0x1800138ef  mov     r8, [rdi+30h]; unsigned __int16 *
0x1800138f3  mov     rdx, [rdi+18h]; TokenHandle
0x1800138f7  mov     rcx, rdi; this
0x1800138fa  call    ?GetOldKeyFromGuid@CUserProfile@@IEAAJPEAXPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::GetOldKeyFromGuid(void *,ushort const *,HKEY__ * *,ulong *)
0x1800138ff  mov     ebx, eax
0x180013901  test    eax, eax
0x180013903  jns     short loc_180013922
0x180013905  mov     rcx, [rbp+38h]; this
0x180013909  mov     r9d, eax; char *
0x18001390c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013913  mov     edx, 450h; void *
0x180013918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001391d  jmp     loc_180013A6F
0x180013922  mov     rdx, [rbp+hKey]
0x180013926  test    rdx, rdx
0x180013929  jnz     loc_180013A07
0x18001392f  mov     [rbp+lpSubKey], r13
0x180013933  mov     [rbp+var_18], r13
0x180013937  mov     [rbp+var_10], r13
0x18001393b  lea     rcx, [rbp+lpSubKey]
0x18001393f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013944  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013948  mov     [rbp+var_18], rax
0x18001394c  mov     [rbp+var_10], rax
0x180013950  lea     r8, [rdi+28h]; int *
0x180013954  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x180013958  mov     rcx, [rdi+30h]; lpString1
0x18001395c  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180013961  mov     ebx, eax
0x180013963  test    eax, eax
0x180013965  jns     short loc_18001398D
0x180013967  mov     rcx, [rbp+38h]; this
0x18001396b  mov     r9d, eax; char *
0x18001396e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013975  mov     edx, 457h; void *
0x18001397a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001397f  lea     rcx, [rbp+lpSubKey]
0x180013983  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013988  jmp     loc_180013A6F
0x18001398d  xor     edx, edx
0x18001398f  lea     rcx, [rbp+hKey]
0x180013993  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013998  mov     [rsp+70h+lpdwDisposition], r13; lpdwDisposition
0x18001399d  lea     rax, [rbp+hKey]
0x1800139a1  mov     [rsp+70h+phkResult], rax; phkResult
0x1800139a6  mov     [rsp+70h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800139ab  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x1800139b3  mov     [rsp+70h+dwOptions], r13d; int
0x1800139b8  xor     r9d, r9d; lpClass
0x1800139bb  xor     r8d, r8d; Reserved
0x1800139be  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800139c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800139c9  call    cs:__imp_RegCreateKeyExW
0x1800139d0  nop     dword ptr [rax+rax+00h]
0x1800139d5  test    eax, eax
0x1800139d7  jz      short loc_1800139F5
0x1800139d9  mov     rcx, [rbp+38h]; this
0x1800139dd  mov     r9d, eax; char *
0x1800139e0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800139e7  mov     edx, 460h; void *
0x1800139ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800139f1  mov     ebx, eax
0x1800139f3  jmp     short loc_18001397F
0x1800139f5  mov     esi, 1
0x1800139fa  lea     rcx, [rbp+lpSubKey]
0x1800139fe  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013a03  mov     rdx, [rbp+hKey]; HKEY
0x180013a07  mov     r8d, esi; int
0x180013a0a  mov     rcx, rdi; this
0x180013a0d  call    ?CheckUserPrefrenceKey@CUserProfile@@IEAAJPEAUHKEY__@@H@Z; CUserProfile::CheckUserPrefrenceKey(HKEY__ *,int)
0x180013a12  test    eax, eax
0x180013a14  jns     short loc_180013A2E
0x180013a16  mov     rcx, [rbp+38h]; this
0x180013a1a  mov     r9d, eax; char *
0x180013a1d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013a24  mov     edx, 465h; void *
0x180013a29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013a2e  mov     rdx, [rdi+30h]; unsigned __int16 *
0x180013a32  mov     rcx, [rdi+18h]; void *
0x180013a36  call    ?SetOldSidString@@YAJPEAXPEBG1@Z; SetOldSidString(void *,ushort const *,ushort const *)
0x180013a3b  test    eax, eax
0x180013a3d  jns     short loc_180013A57
0x180013a3f  mov     rcx, [rbp+38h]; this
0x180013a43  mov     r9d, eax; char *
0x180013a46  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013a4d  mov     edx, 468h; void *
0x180013a52  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013a57  mov     rax, [rbp+hKey]
0x180013a5b  mov     [rbp+hKey], r13
0x180013a5f  mov     [r12], rax
0x180013a63  mov     eax, [rbp+arg_0]
0x180013a66  mov     [r15], eax
0x180013a69  mov     [r14], esi
0x180013a6c  mov     ebx, r13d
0x180013a6f  lea     rcx, [rbp+hKey]
0x180013a73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013a78  mov     eax, ebx
0x180013a7a  mov     rbx, [rsp+70h+arg_10]
0x180013a82  add     rsp, 70h
0x180013a86  pop     r15
0x180013a88  pop     r14
0x180013a8a  pop     r13
0x180013a8c  pop     r12
0x180013a8e  pop     rdi
0x180013a8f  pop     rsi
0x180013a90  pop     rbp
0x180013a91  retn
```
