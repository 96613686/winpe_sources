# CLogonTaskFramework::_LaunchFSIAIfNecessary(void)

- ea: `0x140044f90`
- end: `0x14004525f`
- name: `?_LaunchFSIAIfNecessary@CLogonTaskFramework@@AEAAXXZ`
- size: `719`
- prototype: `void __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400ac52c`

## callees

- `0x14001b2c8`
- `0x140044f90`
- `0x140045268`
- `0x140045290`
- `0x1400468fc`
- `0x14013af98`
- `0x14013ed48`
- `0x140142638`
- `0x140155a3c`
- `0x140156d54`
- `0x1401ab2e8`
- `0x1401b0624`
- `0x1401c5e68`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004519b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004519b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400451f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140045200`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400451f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140045200`
- `SHELL32!__imp_SHCreateSessionKey` at `0x14004512a`
- `SHELL32!__imp_SHCreateSessionKey` at `0x14004512a`

## string_xrefs

- `0x1400450c8`: `shell\lib\logontasks\logontasks.cpp`
- `0x140045141`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400451b2`: `shell\lib\logontasks\logontasks.cpp`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids);
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
        WPP_SF_(v2[2], 57, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids);
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
            (void *)0x323F,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)v12,
            dwOptionsa);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids);
          RegCloseKey(phkResult);
        }
        RegCloseKey(hKey);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x323C,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v11,
          dwOptions);
      }
      phkResult = (HKEY)this;
      Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalAddRef(&phkResult);
      v13 = lambda_9609d88871ac87110aa0e16a579485f7_::_lambda_9609d88871ac87110aa0e16a579485f7_(v18, &v22, &phkResult);
      Windows::Internal::ComTaskPool::QueueTask__lambda_9609d88871ac87110aa0e16a579485f7___(v14, v13);
      lambda_9609d88871ac87110aa0e16a579485f7_::__lambda_9609d88871ac87110aa0e16a579485f7_(v18);
      Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(&phkResult);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3235,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)LogonAnimation,
        dwOptions);
    }
  }
}

```

## disassembly

```asm
0x140044f90  mov     [rsp-18h+arg_18], rbx
0x140044f95  push    rbp
0x140044f96  push    rdi
0x140044f97  push    r15
0x140044f99  mov     rbp, rsp
0x140044f9c  sub     rsp, 70h
0x140044fa0  mov     rbx, rcx
0x140044fa3  lea     r15, WPP_GLOBAL_Control
0x140044faa  mov     rcx, cs:WPP_GLOBAL_Control
0x140044fb1  cmp     rcx, r15
0x140044fb4  jz      short loc_140044FD8
0x140044fb6  test    byte ptr [rcx+1Ch], 8
0x140044fba  jz      short loc_140044FD8
0x140044fbc  mov     edx, 35h ; '5'
0x140044fc1  lea     r8, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x140044fc8  mov     rcx, [rcx+10h]
0x140044fcc  call    WPP_SF_
0x140044fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140044fd8  cmp     qword ptr [rbx+0D0h], 0
0x140044fe0  jnz     short loc_140045009
0x140044fe2  mov     edx, [rbx+0D8h]
0x140044fe8  mov     eax, edx
0x140044fea  and     eax, 42h
0x140044fed  cmp     al, 42h ; 'B'
0x140044fef  jz      short loc_14004503B
0x140044ff1  bt      edx, 0Eh
0x140044ff5  jnb     short loc_140045009
0x140044ff7  mov     ecx, edx
0x140044ff9  call    ?s_IsFSIAAllowed@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z; CLogonTaskFramework::s_IsFSIAAllowed(LogonTypeFlags)
0x140044ffe  test    al, al
0x140045000  jnz     short loc_14004503B
0x140045002  mov     rcx, cs:WPP_GLOBAL_Control
0x140045009  cmp     rcx, r15
0x14004500c  jz      short loc_140045029
0x14004500e  test    byte ptr [rcx+1Ch], 8
0x140045012  jz      short loc_140045029
0x140045014  mov     edx, 39h ; '9'
0x140045019  lea     r8, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x140045020  mov     rcx, [rcx+10h]
0x140045024  call    WPP_SF_
0x140045029  mov     rbx, [rsp+70h+arg_18]
0x140045031  add     rsp, 70h
0x140045035  pop     r15
0x140045037  pop     rdi
0x140045038  pop     rbp
0x140045039  retn
0x14004503b  lea     rcx, [rbp+hKey]
0x14004503f  call    ??$CreateRefCountedObj@VCFirstLogonAnimation@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VCFirstLogonAnimation@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<CFirstLogonAnimation,>(void)
0x140045044  xor     ecx, ecx
0x140045046  lea     rdx, [rbp+var_20]
0x14004504a  cmp     rdx, rax
0x14004504d  jz      short loc_140045059
0x14004504f  mov     rcx, [rax]
0x140045052  mov     qword ptr [rax], 0
0x140045059  mov     rdx, [rbx+0D0h]
0x140045060  mov     [rbx+0D0h], rcx
0x140045067  test    rdx, rdx
0x14004506a  jz      short loc_14004507C
0x14004506c  mov     rax, [rdx]
0x14004506f  mov     rcx, rdx
0x140045072  mov     rax, [rax+10h]
0x140045076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004507b  nop
0x14004507c  mov     rcx, [rbp+hKey]
0x140045080  test    rcx, rcx
0x140045083  jz      short loc_14004509A
0x140045085  mov     [rbp+hKey], 0
0x14004508d  mov     rax, [rcx]
0x140045090  mov     rax, [rax+10h]
0x140045094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045099  nop
0x14004509a  mov     rcx, [rbx+0D0h]
0x1400450a1  test    rcx, rcx
0x1400450a4  jz      short loc_140045029
0x1400450a6  mov     edx, [rbx+0D8h]
0x1400450ac  and     edx, 4
0x1400450af  or      edx, 10h
0x1400450b2  shr     edx, 1
0x1400450b4  add     rcx, 8
0x1400450b8  call    ?BeginFirstLogonAnimation@CFirstLogonAnimation@@QEAAJW4LogonAnimationFlags@@@Z; CFirstLogonAnimation::BeginFirstLogonAnimation(LogonAnimationFlags)
0x1400450bd  mov     rcx, [rbp+18h]; this
0x1400450c1  test    eax, eax
0x1400450c3  jns     short loc_1400450DE
0x1400450c5  mov     r9d, eax; char *
0x1400450c8  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400450cf  mov     edx, 3235h; void *
0x1400450d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400450d9  jmp     loc_140045029
0x1400450de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400450e5  cmp     rcx, r15
0x1400450e8  jz      short loc_140045105
0x1400450ea  test    byte ptr [rcx+1Ch], 8
0x1400450ee  jz      short loc_140045105
0x1400450f0  mov     edx, 36h ; '6'
0x1400450f5  lea     r8, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x1400450fc  mov     rcx, [rcx+10h]
0x140045100  call    WPP_SF_
0x140045105  mov     rdi, [rbx+0D0h]
0x14004510c  mov     [rbp+arg_10], rdi
0x140045110  lea     rcx, [rbp+arg_10]
0x140045114  call    ?InternalAddRef@?$ComPtr@V?$CRefCountedObject@VCFirstLogonAnimation@@@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CRefCountedObject<CFirstLogonAnimation>>::InternalAddRef(void)
0x140045119  mov     [rbp+hKey], 0
0x140045121  lea     rdx, [rbp+hKey]
0x140045125  mov     ecx, 20006h
0x14004512a  call    cs:__imp_SHCreateSessionKey
0x140045131  nop     dword ptr [rax+rax+00h]
0x140045136  mov     rcx, [rbp+18h]; this
0x14004513a  test    eax, eax
0x14004513c  jns     short loc_140045157
0x14004513e  mov     r9d, eax; char *
0x140045141  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140045148  mov     edx, 323Ch; void *
0x14004514d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140045152  jmp     loc_14004520C
0x140045157  mov     [rbp+arg_8], 0
0x14004515f  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x140045168  lea     rax, [rbp+arg_8]
0x14004516c  mov     [rsp+70h+phkResult], rax; phkResult
0x140045171  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004517a  mov     [rsp+70h+samDesired], 20006h; samDesired
0x140045182  mov     [rsp+70h+dwOptions], 1; unsigned int
0x14004518a  xor     r9d, r9d; lpClass
0x14004518d  xor     r8d, r8d; Reserved
0x140045190  lea     rdx, aFsiainprogress; "FSIAInProgress"
0x140045197  mov     rcx, [rbp+hKey]; hKey
0x14004519b  call    cs:__imp_RegCreateKeyExW
0x1400451a2  nop     dword ptr [rax+rax+00h]
0x1400451a7  mov     rcx, [rbp+18h]; this
0x1400451ab  test    eax, eax
0x1400451ad  jz      short loc_1400451C5
0x1400451af  mov     r9d, eax; char *
0x1400451b2  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400451b9  mov     edx, 323Fh; void *
0x1400451be  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400451c3  jmp     short loc_1400451FC
0x1400451c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400451cc  cmp     rcx, r15
0x1400451cf  jz      short loc_1400451EC
0x1400451d1  test    byte ptr [rcx+1Ch], 8
0x1400451d5  jz      short loc_1400451EC
0x1400451d7  mov     edx, 37h ; '7'
0x1400451dc  lea     r8, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x1400451e3  mov     rcx, [rcx+10h]
0x1400451e7  call    WPP_SF_
0x1400451ec  mov     rcx, [rbp+arg_8]; hKey
0x1400451f0  call    cs:__imp_RegCloseKey
0x1400451f7  nop     dword ptr [rax+rax+00h]
0x1400451fc  mov     rcx, [rbp+hKey]; hKey
0x140045200  call    cs:__imp_RegCloseKey
0x140045207  nop     dword ptr [rax+rax+00h]
0x14004520c  mov     [rbp+arg_8], rbx
0x140045210  lea     rcx, [rbp+arg_8]
0x140045214  call    ?InternalAddRef@?$ComPtr@VCLogonTaskFramework@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalAddRef(void)
0x140045219  lea     r8, [rbp+arg_8]
0x14004521d  lea     rdx, [rbp+arg_10]
0x140045221  lea     rcx, [rbp+var_18]
0x140045225  call    _lambda_9609d88871ac87110aa0e16a579485f7____lambda_9609d88871ac87110aa0e16a579485f7_
0x14004522a  mov     rdx, rax
0x14004522d  call    Windows__Internal__ComTaskPool__QueueTask__lambda_9609d88871ac87110aa0e16a579485f7___
0x140045232  lea     rcx, [rbp+var_18]
0x140045236  call    _lambda_9609d88871ac87110aa0e16a579485f7_____lambda_9609d88871ac87110aa0e16a579485f7_
0x14004523b  lea     rcx, [rbp+arg_8]
0x14004523f  call    ?InternalRelease@?$ComPtr@VCLogonTaskFramework@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(void)
0x140045244  nop
0x140045245  test    rdi, rdi
0x140045248  jz      short loc_14004525A
0x14004524a  mov     rax, [rdi]
0x14004524d  mov     rcx, rdi
0x140045250  mov     rax, [rax+10h]
0x140045254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045259  nop
0x14004525a  jmp     loc_140045029
```
