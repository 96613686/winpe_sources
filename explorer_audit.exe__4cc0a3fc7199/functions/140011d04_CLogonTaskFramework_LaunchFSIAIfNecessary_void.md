# CLogonTaskFramework::_LaunchFSIAIfNecessary(void)

- ea: `0x140011d04`
- end: `0x140011fba`
- name: `?_LaunchFSIAIfNecessary@CLogonTaskFramework@@AEAAXXZ`
- size: `694`
- prototype: `void __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400a6450`

## callees

- `0x1400103bc`
- `0x140011d04`
- `0x140011fc0`
- `0x140011fe4`
- `0x14001eba8`
- `0x14012f27c`
- `0x140132d70`
- `0x1401362b4`
- `0x14014b294`
- `0x14014cac8`
- `0x1401ab044`
- `0x1401b21e8`
- `0x1401c726c`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140011f08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140011f08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011f57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011f61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011f57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011f61`
- `SHELL32!__imp_SHCreateSessionKey` at `0x140011e9d`
- `SHELL32!__imp_SHCreateSessionKey` at `0x140011e9d`

## string_xrefs

- `0x140011e3b`: `shell\lib\logontasks\logontasks.cpp`
- `0x140011eae`: `shell\lib\logontasks\logontasks.cpp`
- `0x140011f19`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLogonTaskFramework::_LaunchFSIAIfNecessary(CLogonTaskFramework *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // edx
  char *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  HKEY v7; // rcx
  __int64 v8; // rcx
  int LogonAnimation; // eax
  __int64 v10; // rdi
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-50h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-50h]
  char v17; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v18[24]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HKEY hKey; // [rsp+90h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+28h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 26) )
    goto LABEL_9;
  v3 = *((_DWORD *)this + 54);
  if ( (*((_BYTE *)this + 216) & 0x42) != 0x42 )
  {
    if ( (v3 & 0x4000) == 0 )
      goto LABEL_9;
    if ( !(unsigned __int8)CLogonTaskFramework::s_IsFSIAAllowed(v3) )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
        WPP_SF_(v2[2], 57, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids);
      return;
    }
  }
  v4 = (char *)CreateRefCountedObj<CFirstLogonAnimation,>(&hKey);
  v5 = 0;
  if ( &v17 != v4 )
  {
    v5 = *(_QWORD *)v4;
    *(_QWORD *)v4 = 0;
  }
  v6 = *((_QWORD *)this + 26);
  *((_QWORD *)this + 26) = v5;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = hKey;
  if ( hKey )
  {
    hKey = 0;
    (*(void (__fastcall **)(HKEY))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *((_QWORD *)this + 26);
  if ( v8 )
  {
    LogonAnimation = CFirstLogonAnimation::BeginFirstLogonAnimation(v8 + 8, (*((_DWORD *)this + 54) & 4 | 0x10u) >> 1);
    if ( LogonAnimation >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids);
      v10 = *((_QWORD *)this + 26);
      v22 = v10;
      Microsoft::WRL::ComPtr<CRefCountedObject<CFirstLogonAnimation>>::InternalAddRef(&v22);
      hKey = 0;
      v11 = SHCreateSessionKey(131078, &hKey);
      if ( v11 >= 0 )
      {
        phkResult = 0;
        v12 = RegCreateKeyExW(hKey, L"FSIAInProgress", 0, 0, 1u, 0x20006u, 0, &phkResult, 0);
        if ( v12 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x3221,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)v12,
            dwOptionsa);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids);
          RegCloseKey(phkResult);
        }
        RegCloseKey(hKey);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x321E,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v11,
          dwOptions);
      }
      phkResult = (HKEY)this;
      Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalAddRef(&phkResult);
      v13 = lambda_12229195b8a499289218596ddbcbecfd_::_lambda_12229195b8a499289218596ddbcbecfd_(v18, &v22, &phkResult);
      Windows::Internal::ComTaskPool::QueueTask__lambda_12229195b8a499289218596ddbcbecfd___(v14, v13);
      lambda_12229195b8a499289218596ddbcbecfd_::__lambda_12229195b8a499289218596ddbcbecfd_(v18);
      Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(&phkResult);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3217,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)LogonAnimation,
        dwOptions);
    }
  }
}

```

## disassembly

```asm
0x140011d04  mov     [rsp-18h+arg_18], rbx
0x140011d09  push    rbp
0x140011d0a  push    rdi
0x140011d0b  push    r15
0x140011d0d  mov     rbp, rsp
0x140011d10  sub     rsp, 70h
0x140011d14  mov     rbx, rcx
0x140011d17  lea     r15, WPP_GLOBAL_Control
0x140011d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d25  cmp     rcx, r15
0x140011d28  jz      short loc_140011D4C
0x140011d2a  test    byte ptr [rcx+1Ch], 8
0x140011d2e  jz      short loc_140011D4C
0x140011d30  mov     edx, 35h ; '5'
0x140011d35  lea     r8, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x140011d3c  mov     rcx, [rcx+10h]
0x140011d40  call    WPP_SF_
0x140011d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d4c  cmp     qword ptr [rbx+0D0h], 0
0x140011d54  jnz     short loc_140011D7D
0x140011d56  mov     edx, [rbx+0D8h]
0x140011d5c  mov     eax, edx
0x140011d5e  and     eax, 42h
0x140011d61  cmp     al, 42h ; 'B'
0x140011d63  jz      short loc_140011DAE
0x140011d65  bt      edx, 0Eh
0x140011d69  jnb     short loc_140011D7D
0x140011d6b  mov     ecx, edx
0x140011d6d  call    ?s_IsFSIAAllowed@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z; CLogonTaskFramework::s_IsFSIAAllowed(LogonTypeFlags)
0x140011d72  test    al, al
0x140011d74  jnz     short loc_140011DAE
0x140011d76  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d7d  cmp     rcx, r15
0x140011d80  jz      short loc_140011D9D
0x140011d82  test    byte ptr [rcx+1Ch], 8
0x140011d86  jz      short loc_140011D9D
0x140011d88  mov     edx, 39h ; '9'
0x140011d8d  lea     r8, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x140011d94  mov     rcx, [rcx+10h]
0x140011d98  call    WPP_SF_
0x140011d9d  mov     rbx, [rsp+70h+arg_18]
0x140011da5  add     rsp, 70h
0x140011da9  pop     r15
0x140011dab  pop     rdi
0x140011dac  pop     rbp
0x140011dad  retn
0x140011dae  lea     rcx, [rbp+hKey]
0x140011db2  call    ??$CreateRefCountedObj@VCFirstLogonAnimation@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VCFirstLogonAnimation@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<CFirstLogonAnimation,>(void)
0x140011db7  xor     ecx, ecx
0x140011db9  lea     rdx, [rbp+var_20]
0x140011dbd  cmp     rdx, rax
0x140011dc0  jz      short loc_140011DCC
0x140011dc2  mov     rcx, [rax]
0x140011dc5  mov     qword ptr [rax], 0
0x140011dcc  mov     rdx, [rbx+0D0h]
0x140011dd3  mov     [rbx+0D0h], rcx
0x140011dda  test    rdx, rdx
0x140011ddd  jz      short loc_140011DEF
0x140011ddf  mov     rax, [rdx]
0x140011de2  mov     rcx, rdx
0x140011de5  mov     rax, [rax+10h]
0x140011de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011dee  nop
0x140011def  mov     rcx, [rbp+hKey]
0x140011df3  test    rcx, rcx
0x140011df6  jz      short loc_140011E0D
0x140011df8  mov     [rbp+hKey], 0
0x140011e00  mov     rax, [rcx]
0x140011e03  mov     rax, [rax+10h]
0x140011e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e0c  nop
0x140011e0d  mov     rcx, [rbx+0D0h]
0x140011e14  test    rcx, rcx
0x140011e17  jz      short loc_140011D9D
0x140011e19  mov     edx, [rbx+0D8h]
0x140011e1f  and     edx, 4
0x140011e22  or      edx, 10h
0x140011e25  shr     edx, 1
0x140011e27  add     rcx, 8
0x140011e2b  call    ?BeginFirstLogonAnimation@CFirstLogonAnimation@@QEAAJW4LogonAnimationFlags@@@Z; CFirstLogonAnimation::BeginFirstLogonAnimation(LogonAnimationFlags)
0x140011e30  mov     rcx, [rbp+18h]; this
0x140011e34  test    eax, eax
0x140011e36  jns     short loc_140011E51
0x140011e38  mov     r9d, eax; char *
0x140011e3b  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140011e42  mov     edx, 3217h; void *
0x140011e47  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140011e4c  jmp     loc_140011D9D
0x140011e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e58  cmp     rcx, r15
0x140011e5b  jz      short loc_140011E78
0x140011e5d  test    byte ptr [rcx+1Ch], 8
0x140011e61  jz      short loc_140011E78
0x140011e63  mov     edx, 36h ; '6'
0x140011e68  lea     r8, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x140011e6f  mov     rcx, [rcx+10h]
0x140011e73  call    WPP_SF_
0x140011e78  mov     rdi, [rbx+0D0h]
0x140011e7f  mov     [rbp+arg_10], rdi
0x140011e83  lea     rcx, [rbp+arg_10]
0x140011e87  call    ?InternalAddRef@?$ComPtr@V?$CRefCountedObject@VCFirstLogonAnimation@@@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CRefCountedObject<CFirstLogonAnimation>>::InternalAddRef(void)
0x140011e8c  mov     [rbp+hKey], 0
0x140011e94  lea     rdx, [rbp+hKey]
0x140011e98  mov     ecx, 20006h
0x140011e9d  call    cs:__imp_SHCreateSessionKey
0x140011ea3  mov     rcx, [rbp+18h]; this
0x140011ea7  test    eax, eax
0x140011ea9  jns     short loc_140011EC4
0x140011eab  mov     r9d, eax; char *
0x140011eae  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140011eb5  mov     edx, 321Eh; void *
0x140011eba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140011ebf  jmp     loc_140011F67
0x140011ec4  mov     [rbp+arg_8], 0
0x140011ecc  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x140011ed5  lea     rax, [rbp+arg_8]
0x140011ed9  mov     [rsp+70h+phkResult], rax; phkResult
0x140011ede  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140011ee7  mov     [rsp+70h+samDesired], 20006h; samDesired
0x140011eef  mov     [rsp+70h+dwOptions], 1; unsigned int
0x140011ef7  xor     r9d, r9d; lpClass
0x140011efa  xor     r8d, r8d; Reserved
0x140011efd  lea     rdx, aFsiainprogress; "FSIAInProgress"
0x140011f04  mov     rcx, [rbp+hKey]; hKey
0x140011f08  call    cs:__imp_RegCreateKeyExW
0x140011f0e  mov     rcx, [rbp+18h]; this
0x140011f12  test    eax, eax
0x140011f14  jz      short loc_140011F2C
0x140011f16  mov     r9d, eax; char *
0x140011f19  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140011f20  mov     edx, 3221h; void *
0x140011f25  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140011f2a  jmp     short loc_140011F5D
0x140011f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f33  cmp     rcx, r15
0x140011f36  jz      short loc_140011F53
0x140011f38  test    byte ptr [rcx+1Ch], 8
0x140011f3c  jz      short loc_140011F53
0x140011f3e  mov     edx, 37h ; '7'
0x140011f43  lea     r8, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x140011f4a  mov     rcx, [rcx+10h]
0x140011f4e  call    WPP_SF_
0x140011f53  mov     rcx, [rbp+arg_8]; hKey
0x140011f57  call    cs:__imp_RegCloseKey
0x140011f5d  mov     rcx, [rbp+hKey]; hKey
0x140011f61  call    cs:__imp_RegCloseKey
0x140011f67  mov     [rbp+arg_8], rbx
0x140011f6b  lea     rcx, [rbp+arg_8]
0x140011f6f  call    ?InternalAddRef@?$ComPtr@VCLogonTaskFramework@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalAddRef(void)
0x140011f74  lea     r8, [rbp+arg_8]
0x140011f78  lea     rdx, [rbp+arg_10]
0x140011f7c  lea     rcx, [rbp+var_18]
0x140011f80  call    _lambda_12229195b8a499289218596ddbcbecfd____lambda_12229195b8a499289218596ddbcbecfd_
0x140011f85  mov     rdx, rax
0x140011f88  call    Windows__Internal__ComTaskPool__QueueTask__lambda_12229195b8a499289218596ddbcbecfd___
0x140011f8d  lea     rcx, [rbp+var_18]
0x140011f91  call    _lambda_12229195b8a499289218596ddbcbecfd_____lambda_12229195b8a499289218596ddbcbecfd_
0x140011f96  lea     rcx, [rbp+arg_8]
0x140011f9a  call    ?InternalRelease@?$ComPtr@VCLogonTaskFramework@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(void)
0x140011f9f  nop
0x140011fa0  test    rdi, rdi
0x140011fa3  jz      short loc_140011FB5
0x140011fa5  mov     rax, [rdi]
0x140011fa8  mov     rcx, rdi
0x140011fab  mov     rax, [rax+10h]
0x140011faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011fb4  nop
0x140011fb5  jmp     loc_140011D9D
```
