# LoadProfileBasic

- ea: `0x180009f90`
- end: `0x18000a1ba`
- name: `LoadProfileBasic`
- size: `554`
- prototype: `__int64 __fastcall(void *, HKEY *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callees

- `0x180003fdc`
- `0x180005b60`
- `0x1800064b0`
- `0x180009f90`
- `0x18000a1c0`
- `0x18000a214`
- `0x18000d23c`
- `0x18001064c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a034`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a106`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a034`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a106`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a0b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a186`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a0b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a186`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a08a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a08a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a155`
- `ext-ms-win-profile-extender-l1-1-0!LoadProfileExtender` at `0x18000a0db`
- `ext-ms-win-profile-extender-l1-1-0!LoadProfileExtender` at `0x18000a0db`

## pseudocode

```c
__int64 __fastcall LoadProfileBasic(void *a1, HKEY *a2)
{
  int SidString; // eax
  unsigned int ProfileExtender; // ebx
  unsigned __int16 *v7; // rdi
  RTL_SRWLOCK *v8; // rbx
  int ServiceProfile; // eax
  unsigned int v10; // esi
  unsigned int v11; // eax
  WCHAR *v12; // rcx
  int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  LPCWSTR lpSubKey[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a1 )
    return 2147942487LL;
  lpSubKey[0] = 0;
  lpSubKey[1] = (LPCWSTR)-1LL;
  lpSubKey[2] = (LPCWSTR)-1LL;
  SidString = GetSidString(a1, (unsigned __int16 **)lpSubKey);
  ProfileExtender = SidString;
  if ( SidString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x219,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)SidString,
      phkResult);
    v12 = (WCHAR *)lpSubKey[0];
    if ( !lpSubKey[0] )
      return ProfileExtender;
    goto LABEL_21;
  }
  v7 = (unsigned __int16 *)lpSubKey[0];
  if ( StringIsEqual(lpSubKey[0], L"S-1-5-18") )
    goto LABEL_11;
  if ( StringIsEqual(v7, L"S-1-5-19") || StringIsEqual(v7, L"S-1-5-20") )
  {
    if ( StringIsEqual(v7, L"S-1-5-19") )
    {
      v8 = &g_srwLocalServiceLock;
      AcquireSRWLockExclusive(&g_srwLocalServiceLock);
    }
    else
    {
      v8 = &g_srwNetworkServiceLock;
      AcquireSRWLockExclusive(&g_srwNetworkServiceLock);
    }
    ServiceProfile = _LoadServiceProfile(v7);
    v10 = ServiceProfile;
    if ( ServiceProfile < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"minio\\profapi\\load.cpp",
        (const char *)(unsigned int)ServiceProfile,
        phkResult);
      if ( v8 )
        ReleaseSRWLockExclusive(v8);
      goto LABEL_31;
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
LABEL_11:
    if ( !a2 || (v11 = RegOpenKeyExW(HKEY_USERS, v7, 0, 0x2001Fu, a2)) == 0 )
    {
      if ( v7 )
        LocalFree(v7);
      return 0;
    }
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x234,
            (unsigned int)"minio\\profapi\\load.cpp",
            (const char *)v11,
            phkResulta);
LABEL_31:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(lpSubKey);
    return v10;
  }
  if ( (unsigned __int8)IsUnloadProfileExtenderPresent() )
  {
    ProfileExtender = LoadProfileExtender(a1);
    if ( (ProfileExtender & 0x80000000) != 0 )
    {
      if ( !v7 )
        return ProfileExtender;
      v12 = v7;
LABEL_21:
      LocalFree(v12);
      return ProfileExtender;
    }
    goto LABEL_11;
  }
  if ( v7 )
    LocalFree(v7);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180009f90  mov     [rsp+arg_8], rbx
0x180009f95  push    rbp
0x180009f96  push    rsi
0x180009f97  push    rdi
0x180009f98  sub     rsp, 50h
0x180009f9c  mov     rbp, rdx
0x180009f9f  mov     rsi, rcx
0x180009fa2  test    rcx, rcx
0x180009fa5  jnz     short loc_180009FB9
0x180009fa7  mov     eax, 80070057h
0x180009fac  mov     rbx, [rsp+68h+arg_8]
0x180009fb1  add     rsp, 50h
0x180009fb5  pop     rdi
0x180009fb6  pop     rsi
0x180009fb7  pop     rbp
0x180009fb8  retn
0x180009fb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009fbd  mov     [rsp+68h+lpSubKey], 0
0x180009fc6  lea     rdx, [rsp+68h+lpSubKey]; unsigned __int16 **
0x180009fcb  mov     [rsp+68h+var_30], rax
0x180009fd0  mov     [rsp+68h+var_28], rax
0x180009fd5  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x180009fda  mov     ebx, eax
0x180009fdc  test    eax, eax
0x180009fde  js      loc_18000A128
0x180009fe4  mov     rdi, [rsp+68h+lpSubKey]
0x180009fe9  lea     rdx, aS1518; "S-1-5-18"
0x180009ff0  mov     rcx, rdi; unsigned __int16 *
0x180009ff3  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180009ff8  test    eax, eax
0x180009ffa  jnz     short loc_18000A06D
0x180009ffc  lea     rdx, aS1519; "S-1-5-19"
0x18000a003  mov     rcx, rdi; unsigned __int16 *
0x18000a006  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18000a00b  test    eax, eax
0x18000a00d  jz      loc_18000A0B8
0x18000a013  lea     rdx, aS1519; "S-1-5-19"
0x18000a01a  mov     rcx, rdi; unsigned __int16 *
0x18000a01d  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18000a022  test    eax, eax
0x18000a024  jz      loc_18000A0FC
0x18000a02a  lea     rbx, ?g_srwLocalServiceLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock g_srwLocalServiceLock
0x18000a031  mov     rcx, rbx; SRWLock
0x18000a034  call    cs:__imp_AcquireSRWLockExclusive
0x18000a03a  lea     rax, [rsp+68h+SRWLock]
0x18000a03f  mov     qword ptr [rax], 0
0x18000a046  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000a04b  test    rcx, rcx
0x18000a04e  jz      short loc_18000A056
0x18000a050  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a056  mov     rcx, rdi; unsigned __int16 *
0x18000a059  call    ?_LoadServiceProfile@@YAJPEBG@Z; _LoadServiceProfile(ushort const *)
0x18000a05e  mov     esi, eax
0x18000a060  test    eax, eax
0x18000a062  js      loc_18000A165
0x18000a068  test    rbx, rbx
0x18000a06b  jnz     short loc_18000A0AD
0x18000a06d  test    rbp, rbp
0x18000a070  jz      short loc_18000A098
0x18000a072  mov     r9d, 2001Fh; samDesired
0x18000a078  mov     qword ptr [rsp+68h+phkResult], rbp; unsigned int
0x18000a07d  xor     r8d, r8d; ulOptions
0x18000a080  mov     rdx, rdi; lpSubKey
0x18000a083  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000a08a  call    cs:__imp_RegOpenKeyExW
0x18000a090  test    eax, eax
0x18000a092  jnz     loc_18000A19D
0x18000a098  test    rdi, rdi
0x18000a09b  jz      short loc_18000A0A6
0x18000a09d  mov     rcx, rdi; hMem
0x18000a0a0  call    cs:__imp_LocalFree
0x18000a0a6  xor     eax, eax
0x18000a0a8  jmp     loc_180009FAC
0x18000a0ad  mov     rcx, rbx; SRWLock
0x18000a0b0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a0b6  jmp     short loc_18000A06D
0x18000a0b8  lea     rdx, aS1520; "S-1-5-20"
0x18000a0bf  mov     rcx, rdi; unsigned __int16 *
0x18000a0c2  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18000a0c7  test    eax, eax
0x18000a0c9  jnz     loc_18000A013
0x18000a0cf  call    IsUnloadProfileExtenderPresent
0x18000a0d4  test    al, al
0x18000a0d6  jz      short loc_18000A14D
0x18000a0d8  mov     rcx, rsi
0x18000a0db  call    cs:__imp_LoadProfileExtender
0x18000a0e1  mov     ebx, eax
0x18000a0e3  test    eax, eax
0x18000a0e5  jns     short loc_18000A06D
0x18000a0e7  test    rdi, rdi
0x18000a0ea  jz      short loc_18000A0F5
0x18000a0ec  mov     rcx, rdi; hMem
0x18000a0ef  call    cs:__imp_LocalFree
0x18000a0f5  mov     eax, ebx
0x18000a0f7  jmp     loc_180009FAC
0x18000a0fc  lea     rbx, ?g_srwNetworkServiceLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock g_srwNetworkServiceLock
0x18000a103  mov     rcx, rbx; SRWLock
0x18000a106  call    cs:__imp_AcquireSRWLockExclusive
0x18000a10c  lea     rax, [rsp+68h+arg_10]
0x18000a114  mov     qword ptr [rax], 0
0x18000a11b  mov     rcx, [rsp+68h+arg_10]
0x18000a123  jmp     loc_18000A04B
0x18000a128  mov     rcx, [rsp+68h]; this
0x18000a12d  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000a134  mov     r9d, ebx; char *
0x18000a137  mov     edx, 219h; void *
0x18000a13c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a141  mov     rcx, [rsp+68h+lpSubKey]
0x18000a146  test    rcx, rcx
0x18000a149  jnz     short loc_18000A0EF
0x18000a14b  jmp     short loc_18000A0F5
0x18000a14d  test    rdi, rdi
0x18000a150  jz      short loc_18000A15B
0x18000a152  mov     rcx, rdi; hMem
0x18000a155  call    cs:__imp_LocalFree
0x18000a15b  mov     eax, 80004001h
0x18000a160  jmp     loc_180009FAC
0x18000a165  mov     rcx, [rsp+68h]; this
0x18000a16a  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000a171  mov     r9d, eax; char *
0x18000a174  mov     edx, 227h; void *
0x18000a179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a17e  test    rbx, rbx
0x18000a181  jz      short loc_18000A18C
0x18000a183  mov     rcx, rbx; SRWLock
0x18000a186  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a18c  lea     rcx, [rsp+68h+lpSubKey]
0x18000a191  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18000a196  mov     eax, esi
0x18000a198  jmp     loc_180009FAC
0x18000a19d  mov     rcx, [rsp+68h]; this
0x18000a1a2  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000a1a9  mov     r9d, eax; char *
0x18000a1ac  mov     edx, 234h; void *
0x18000a1b1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a1b6  mov     esi, eax
0x18000a1b8  jmp     short loc_18000A18C
```
