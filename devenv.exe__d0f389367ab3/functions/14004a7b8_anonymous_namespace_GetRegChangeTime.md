# _anonymous_namespace_::GetRegChangeTime

- ea: `0x14004a7b8`
- end: `0x14004ab72`
- name: `_anonymous_namespace_::GetRegChangeTime`
- size: `954`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hToken, __int64, int, char)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140047554`
- `0x14004a7b8`
- `0x14004bd64`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002f00`
- `0x140003160`
- `0x140007740`
- `0x14001e390`
- `0x14002143c`
- `0x14004a7b8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004ab3b`
- `ADVAPI32!RegCloseKey` at `0x14004ab3b`
- `ADVAPI32!RegOpenKeyExW` at `0x14004a840`
- `ADVAPI32!RegOpenKeyExW` at `0x14004a840`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14004a89a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14004a89a`
- `ADVAPI32!RegEnumKeyW` at `0x14004aa66`
- `ADVAPI32!RegEnumKeyW` at `0x14004aa66`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004a819`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004a819`
- `ADVAPI32!RevertToSelf` at `0x14004ab46`
- `ADVAPI32!RevertToSelf` at `0x14004ab46`
- `KERNEL32!CompareFileTime` at `0x14004a8ce`
- `KERNEL32!CompareFileTime` at `0x14004a8ce`

## string_xrefs

- `0x14004aa16`: `Services`
- `0x14004a975`: `CLSID`
- `0x14004a98c`: `HandleInComingCall`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::GetRegChangeTime(
        HKEY a1,
        __int64 a2,
        const WCHAR *a3,
        FILETIME *a4,
        HANDLE hToken,
        __int64 a6,
        int a7,
        char a8)
{
  unsigned int v12; // r14d
  BOOL v13; // eax
  _BOOL8 v14; // rbx
  LSTATUS v15; // eax
  LSTATUS v16; // edi
  DWORD v17; // edi
  __int64 v18; // r8
  _QWORD *v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // r8
  _QWORD *v22; // rdx
  bool v24; // [rsp+60h] [rbp-A0h]
  int v25[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  HANDLE v28; // [rsp+80h] [rbp-80h]
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  v27 = a2;
  v28 = hToken;
  v26 = a6;
  v12 = 0;
  hKey = 0;
  v13 = ImpersonateLoggedOnUser(hToken);
  v14 = v13;
  v24 = v13;
  v15 = RegOpenKeyExW(a1, a3, 0, 0x20019u, &hKey);
  if ( v15 )
  {
    v12 = (unsigned __int16)v15 | 0x80070000;
    if ( v15 <= 0 )
      v12 = v15;
  }
  else
  {
    v16 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
    if ( !wcsicmp_0(a3, L"Initialization") )
      goto LABEL_6;
    if ( v16 )
    {
      v17 = 0;
    }
    else
    {
      v17 = 0;
      if ( CompareFileTime(&ftLastWriteTime, a4) > 0 )
      {
        *(_QWORD *)v25 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          v25,
          a2);
        if ( *(_DWORD *)(*(_QWORD *)v25 - 16LL) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            a6,
            L"%s\\%s",
            *(_QWORD *)v25,
            a3);
        }
        else
        {
          if ( a3 )
          {
            v18 = -1;
            do
              ++v18;
            while ( a3[v18] );
          }
          ATL::CSimpleStringT<unsigned short,0>::SetString(a6, a3);
        }
        *a4 = ftLastWriteTime;
        v19 = (_QWORD *)(*(_QWORD *)v25 - 24LL);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v25 - 24LL + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
        }
      }
    }
    if ( a8
      || wcsicmp_0(a3, L"CLSID")
      && wcsicmp_0(a3, L"HandleInComingCall")
      && wcsicmp_0(a3, L"Editors")
      && wcsicmp_0(a3, L"ProgId")
      && wcsicmp_0(a3, L"Projects")
      && wcsicmp_0(a3, L"ToolWindows")
      && wcsicmp_0(a3, L"ShellFileAssociations")
      && wcsicmp_0(a3, L"Services") )
    {
      if ( a7 > 0 )
      {
        _mm_lfence();
        v20 = v26;
        while ( 1 )
        {
          memset_0(SubKey, 0, 0x208u);
          if ( RegEnumKeyW(hKey, v17, SubKey, 0x104u) )
            break;
          *(_QWORD *)v25 = 0;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            v25,
            v27);
          if ( *(_DWORD *)(*(_QWORD *)v25 - 16LL) )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              v25,
              L"\\%s",
              a3);
          }
          else
          {
            if ( a3 )
            {
              v21 = -1;
              do
                ++v21;
              while ( a3[v21] );
            }
            ATL::CSimpleStringT<unsigned short,0>::SetString(v25, a3);
          }
          v12 = anonymous_namespace_::GetRegChangeTime((int)hKey, v25[0], (int)SubKey, (int)a4, v28, v20, a7 - 1, a8);
          v22 = (_QWORD *)(*(_QWORD *)v25 - 24LL);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v25 - 24LL + 16), 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
          }
          ++v17;
        }
        LOBYTE(v14) = v24;
      }
    }
    else
    {
LABEL_6:
      v12 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( v14 )
    RevertToSelf();
  return v12;
}

```

## disassembly

```asm
0x14004a7b8  push    rbp
0x14004a7ba  push    rbx
0x14004a7bb  push    rsi
0x14004a7bc  push    rdi
0x14004a7bd  push    r12
0x14004a7bf  push    r13
0x14004a7c1  push    r14
0x14004a7c3  push    r15
0x14004a7c5  lea     rbp, [rsp-1C8h]
0x14004a7cd  sub     rsp, 2C8h
0x14004a7d4  mov     rax, cs:__security_cookie
0x14004a7db  xor     rax, rsp
0x14004a7de  mov     [rbp+200h+var_50], rax
0x14004a7e5  mov     r13, r9
0x14004a7e8  mov     rsi, r8
0x14004a7eb  mov     r12, rdx
0x14004a7ee  mov     [rsp+300h+var_288], rdx
0x14004a7f3  mov     rdi, rcx
0x14004a7f6  mov     rax, [rbp+200h+hToken]
0x14004a7fd  mov     [rbp+200h+var_280], rax
0x14004a801  mov     r15, [rbp+200h+arg_28]
0x14004a808  mov     [rsp+300h+var_290], r15
0x14004a80d  xor     ebx, ebx
0x14004a80f  mov     r14d, ebx
0x14004a812  mov     [rbp+200h+hKey], rbx
0x14004a816  mov     rcx, rax; hToken
0x14004a819  call    cs:__imp_ImpersonateLoggedOnUser
0x14004a81f  test    eax, eax
0x14004a821  setnz   bl
0x14004a824  mov     [rsp+300h+var_2A0], bl
0x14004a828  lea     rax, [rbp+200h+hKey]
0x14004a82c  mov     [rsp+300h+phkResult], rax; phkResult
0x14004a831  mov     r9d, 20019h; samDesired
0x14004a837  xor     r8d, r8d; ulOptions
0x14004a83a  mov     rdx, rsi; lpSubKey
0x14004a83d  mov     rcx, rdi; hKey
0x14004a840  call    cs:__imp_RegOpenKeyExW
0x14004a846  xor     edi, edi
0x14004a848  test    eax, eax
0x14004a84a  jz      short loc_14004A862
0x14004a84c  movzx   r14d, ax
0x14004a850  or      r14d, 80070000h
0x14004a857  test    eax, eax
0x14004a859  cmovle  r14d, eax
0x14004a85d  jmp     loc_14004AB42
0x14004a862  lea     rax, [rbp+200h+ftLastWriteTime]
0x14004a866  mov     [rsp+300h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14004a86b  mov     [rsp+300h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x14004a870  mov     [rsp+300h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x14004a875  mov     [rsp+300h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x14004a87a  mov     [rsp+300h+lpcValues], rdi; lpcValues
0x14004a87f  mov     [rsp+300h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x14004a884  mov     [rsp+300h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x14004a889  mov     [rsp+300h+phkResult], rdi; lpcSubKeys
0x14004a88e  xor     r9d, r9d; lpReserved
0x14004a891  xor     r8d, r8d; lpcchClass
0x14004a894  xor     edx, edx; lpClass
0x14004a896  mov     rcx, [rbp+200h+hKey]; hKey
0x14004a89a  call    cs:__imp_RegQueryInfoKeyW
0x14004a8a0  mov     edi, eax
0x14004a8a2  lea     rdx, aInitialization; "Initialization"
0x14004a8a9  mov     rcx, rsi; String1
0x14004a8ac  call    _wcsicmp_0
0x14004a8b1  test    eax, eax
0x14004a8b3  jnz     short loc_14004A8BF
0x14004a8b5  xor     edi, edi
0x14004a8b7  mov     r14d, edi
0x14004a8ba  jmp     loc_14004AB32
0x14004a8bf  test    edi, edi
0x14004a8c1  jnz     loc_14004A963
0x14004a8c7  mov     rdx, r13; lpFileTime2
0x14004a8ca  lea     rcx, [rbp+200h+ftLastWriteTime]; lpFileTime1
0x14004a8ce  call    cs:__imp_CompareFileTime
0x14004a8d4  xor     edi, edi
0x14004a8d6  test    eax, eax
0x14004a8d8  jle     loc_14004A965
0x14004a8de  mov     qword ptr [rsp+300h+var_298], rdi
0x14004a8e3  mov     rdx, r12
0x14004a8e6  lea     rcx, [rsp+300h+var_298]
0x14004a8eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004a8f0  mov     r8, qword ptr [rsp+300h+var_298]
0x14004a8f5  cmp     [r8-10h], edi
0x14004a8f9  jnz     short loc_14004A925
0x14004a8fb  nop     dword ptr [rax+rax+00h]
0x14004a900  test    rsi, rsi
0x14004a903  jnz     short loc_14004A90A
0x14004a905  mov     r8d, edi
0x14004a908  jmp     short loc_14004A918
0x14004a90a  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004a90e  inc     r8
0x14004a911  cmp     [rsi+r8*2], di
0x14004a916  jnz     short loc_14004A90E
0x14004a918  mov     rdx, rsi
0x14004a91b  mov     rcx, r15
0x14004a91e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14004a923  jmp     short loc_14004A937
0x14004a925  mov     r9, rsi
0x14004a928  lea     rdx, aSS_2; "%s\\%s"
0x14004a92f  mov     rcx, r15
0x14004a932  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14004a937  mov     rax, qword ptr [rbp+200h+ftLastWriteTime.dwLowDateTime]
0x14004a93b  mov     [r13+0], rax
0x14004a93f  mov     rdx, qword ptr [rsp+300h+var_298]
0x14004a944  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004a948  or      eax, 0FFFFFFFFh
0x14004a94b  lock xadd [rdx+10h], eax
0x14004a950  sub     eax, 1
0x14004a953  jg      short loc_14004A965
0x14004a955  lfence
0x14004a958  mov     rcx, [rdx]
0x14004a95b  mov     rax, [rcx]
0x14004a95e  call    qword ptr [rax+8]
0x14004a961  jmp     short loc_14004A965
0x14004a963  xor     edi, edi
0x14004a965  mov     r12b, [rbp+200h+arg_38]
0x14004a96c  test    r12b, r12b
0x14004a96f  jnz     loc_14004AA2D
0x14004a975  lea     rdx, aClsid_1; "CLSID"
0x14004a97c  mov     rcx, rsi; String1
0x14004a97f  call    _wcsicmp_0
0x14004a984  test    eax, eax
0x14004a986  jz      loc_14004A8B7
0x14004a98c  lea     rdx, aHandleincoming; "HandleInComingCall"
0x14004a993  mov     rcx, rsi; String1
0x14004a996  call    _wcsicmp_0
0x14004a99b  test    eax, eax
0x14004a99d  jz      loc_14004A8B7
0x14004a9a3  lea     rdx, aEditors; "Editors"
0x14004a9aa  mov     rcx, rsi; String1
0x14004a9ad  call    _wcsicmp_0
0x14004a9b2  test    eax, eax
0x14004a9b4  jz      loc_14004A8B7
0x14004a9ba  lea     rdx, aProgid; "ProgId"
0x14004a9c1  mov     rcx, rsi; String1
0x14004a9c4  call    _wcsicmp_0
0x14004a9c9  test    eax, eax
0x14004a9cb  jz      loc_14004A8B7
0x14004a9d1  lea     rdx, aProjects; "Projects"
0x14004a9d8  mov     rcx, rsi; String1
0x14004a9db  call    _wcsicmp_0
0x14004a9e0  test    eax, eax
0x14004a9e2  jz      loc_14004A8B7
0x14004a9e8  lea     rdx, aToolwindows; "ToolWindows"
0x14004a9ef  mov     rcx, rsi; String1
0x14004a9f2  call    _wcsicmp_0
0x14004a9f7  test    eax, eax
0x14004a9f9  jz      loc_14004A8B7
0x14004a9ff  lea     rdx, aShellfileassoc; "ShellFileAssociations"
0x14004aa06  mov     rcx, rsi; String1
0x14004aa09  call    _wcsicmp_0
0x14004aa0e  test    eax, eax
0x14004aa10  jz      loc_14004A8B7
0x14004aa16  lea     rdx, aServices; "Services"
0x14004aa1d  mov     rcx, rsi; String1
0x14004aa20  call    _wcsicmp_0
0x14004aa25  test    eax, eax
0x14004aa27  jz      loc_14004A8B7
0x14004aa2d  mov     r15d, [rbp+200h+arg_30]
0x14004aa34  test    r15d, r15d
0x14004aa37  jle     loc_14004AB32
0x14004aa3d  lfence
0x14004aa40  mov     rbx, [rsp+300h+var_290]
0x14004aa45  xor     edx, edx; Val
0x14004aa47  mov     r8d, 208h; Size
0x14004aa4d  lea     rcx, [rbp+200h+SubKey]; void *
0x14004aa51  call    memset_0
0x14004aa56  mov     r9d, 104h; cchName
0x14004aa5c  lea     r8, [rbp+200h+SubKey]; lpName
0x14004aa60  mov     edx, edi; dwIndex
0x14004aa62  mov     rcx, [rbp+200h+hKey]; hKey
0x14004aa66  call    cs:__imp_RegEnumKeyW
0x14004aa6c  test    eax, eax
0x14004aa6e  jnz     loc_14004AB2E
0x14004aa74  xor     r14d, r14d
0x14004aa77  mov     qword ptr [rsp+300h+var_298], r14
0x14004aa7c  mov     rdx, [rsp+300h+var_288]
0x14004aa81  lea     rcx, [rsp+300h+var_298]
0x14004aa86  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004aa8b  nop
0x14004aa8c  mov     rax, qword ptr [rsp+300h+var_298]
0x14004aa91  cmp     [rax-10h], r14d
0x14004aa95  jnz     short loc_14004AABE
0x14004aa97  test    rsi, rsi
0x14004aa9a  jnz     short loc_14004AAA1
0x14004aa9c  mov     r8d, r14d
0x14004aa9f  jmp     short loc_14004AAAF
0x14004aaa1  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004aaa5  inc     r8
0x14004aaa8  cmp     [rsi+r8*2], r14w
0x14004aaad  jnz     short loc_14004AAA5
0x14004aaaf  mov     rdx, rsi
0x14004aab2  lea     rcx, [rsp+300h+var_298]
0x14004aab7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14004aabc  jmp     short loc_14004AAD2
0x14004aabe  mov     r8, rsi
0x14004aac1  lea     rdx, aS_4; "\\%s"
0x14004aac8  lea     rcx, [rsp+300h+var_298]
0x14004aacd  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14004aad2  lea     eax, [r15-1]
0x14004aad6  mov     byte ptr [rsp+300h+lpcValues], r12b; char
0x14004aadb  mov     dword ptr [rsp+300h+lpcbMaxClassLen], eax; int
0x14004aadf  mov     [rsp+300h+lpcbMaxSubKeyLen], rbx; __int64
0x14004aae4  mov     rax, [rbp+200h+var_280]
0x14004aae8  mov     [rsp+300h+phkResult], rax; hToken
0x14004aaed  mov     r9, r13; int
0x14004aaf0  lea     r8, [rbp+200h+SubKey]; int
0x14004aaf4  mov     rdx, qword ptr [rsp+300h+var_298]; int
0x14004aaf9  mov     rcx, [rbp+200h+hKey]; int
0x14004aafd  call    _anonymous_namespace___GetRegChangeTime
0x14004ab02  mov     r14d, eax
0x14004ab05  mov     rdx, qword ptr [rsp+300h+var_298]
0x14004ab0a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004ab0e  or      eax, 0FFFFFFFFh
0x14004ab11  lock xadd [rdx+10h], eax
0x14004ab16  sub     eax, 1
0x14004ab19  jg      short loc_14004AB27
0x14004ab1b  lfence
0x14004ab1e  mov     rcx, [rdx]
0x14004ab21  mov     rax, [rcx]
0x14004ab24  call    qword ptr [rax+8]
0x14004ab27  inc     edi
0x14004ab29  jmp     loc_14004AA45
0x14004ab2e  mov     bl, [rsp+300h+var_2A0]
0x14004ab32  mov     rcx, [rbp+200h+hKey]; hKey
0x14004ab36  test    rcx, rcx
0x14004ab39  jz      short loc_14004AB42
0x14004ab3b  call    cs:__imp_RegCloseKey
0x14004ab41  nop
0x14004ab42  test    bl, bl
0x14004ab44  jz      short loc_14004AB4C
0x14004ab46  call    cs:__imp_RevertToSelf
0x14004ab4c  mov     eax, r14d
0x14004ab4f  mov     rcx, [rbp+200h+var_50]
0x14004ab56  xor     rcx, rsp; StackCookie
0x14004ab59  call    __security_check_cookie
0x14004ab5e  add     rsp, 2C8h
0x14004ab65  pop     r15
0x14004ab67  pop     r14
0x14004ab69  pop     r13
0x14004ab6b  pop     r12
0x14004ab6d  pop     rdi
0x14004ab6e  pop     rsi
0x14004ab6f  pop     rbx
0x14004ab70  pop     rbp
0x14004ab71  retn
```
