# HrGetProfileCategoryInProfileStore(_GUID const *,ulong *)

- ea: `0x18005b598`
- end: `0x18005b779`
- name: `?HrGetProfileCategoryInProfileStore@@YAJPEBU_GUID@@PEAK@Z`
- size: `481`
- prototype: `__int64 __fastcall(GUID *rguid, unsigned int *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180083c70`
- `0x1800a3bd4`
- `0x1800c1258`
- `0x1800c6864`
- `0x1800cc120`
- `0x1800d635c`
- `0x1800d67ec`

## callees

- `0x18000fab0`
- `0x180014cc0`
- `0x180015650`
- `0x1800307cc`
- `0x18004c5bc`
- `0x18005b598`
- `0x1800a88a0`
- `0x1800a9738`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b749`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005b5e1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005b5e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005b657`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005b657`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b6fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b6fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b69c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b69c`

## string_xrefs

- `0x18005b678`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`
- `0x18005b6b1`: `onecore\net\netprofiles\service\src\host\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall HrGetProfileCategoryInProfileStore(GUID *rguid, unsigned int *a2)
{
  int v4; // ebx
  const char *v5; // r9
  int Value; // eax
  unsigned int v7; // eax
  __int64 result; // rax
  unsigned int lpData; // [rsp+20h] [rbp-98h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-80h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-78h] BYREF
  DWORD cbData[3]; // [rsp+44h] [rbp-74h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *a2 = 0;
  memset_0(sz, 0, 0x4Eu);
  StringFromGUID2(rguid, sz, 39);
  lpCriticalSection = 0;
  NetworkPropertyMaps::LockProfileStore(&lpCriticalSection);
  *(_DWORD *)Data = 0;
  hKey = 0;
  v4 = HrOpenProfileKey(sz, 0x20019u, &hKey);
  if ( !v4 )
  {
    cbData[0] = 4;
    Value = RegQueryValueExW(hKey, L"Category", 0, 0, Data, cbData);
    if ( Value > 0 )
      Value = (unsigned __int16)Value | 0x80070000;
    if ( Value < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x48A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
        (const char *)(unsigned int)Value,
        lpData);
    if ( *(_DWORD *)Data == 2 )
    {
      v7 = RegDeleteValueW(hKey, L"Category");
      if ( v7 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x48D,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
          (const char *)v7,
          lpData);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
      *(_DWORD *)Data = 0;
    }
    RegCloseKey(hKey);
    goto LABEL_15;
  }
  if ( v4 >= 0 )
  {
LABEL_15:
    *a2 = *(_DWORD *)Data;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
LABEL_19:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  result = (unsigned int)v4;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      cbData[0] = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x49F,
                    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
                    v5);
      result = cbData[0];
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18005b598  mov     [rsp+arg_10], rbx
0x18005b59d  push    rdi
0x18005b59e  sub     rsp, 0B0h
0x18005b5a5  mov     rax, cs:__security_cookie
0x18005b5ac  xor     rax, rsp
0x18005b5af  mov     [rsp+0B8h+var_18], rax
0x18005b5b7  mov     rdi, rdx
0x18005b5ba  mov     rbx, rcx
0x18005b5bd  mov     dword ptr [rdx], 0
0x18005b5c3  xor     edx, edx; Val
0x18005b5c5  lea     r8d, [rdx+4Eh]; Size
0x18005b5c9  lea     rcx, [rsp+0B8h+sz]; void *
0x18005b5ce  call    memset_0
0x18005b5d3  mov     r8d, 27h ; '''; cchMax
0x18005b5d9  lea     rdx, [rsp+0B8h+sz]; lpsz
0x18005b5de  mov     rcx, rbx; rguid
0x18005b5e1  call    cs:__imp_StringFromGUID2
0x18005b5e7  mov     [rsp+0B8h+lpCriticalSection], 0
0x18005b5f0  lea     rcx, [rsp+0B8h+lpCriticalSection]
0x18005b5f5  call    ?LockProfileStore@NetworkPropertyMaps@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; NetworkPropertyMaps::LockProfileStore(void)
0x18005b5fa  mov     dword ptr [rsp+0B8h+Data], 0
0x18005b602  mov     [rsp+0B8h+hKey], 0
0x18005b60b  lea     r8, [rsp+0B8h+hKey]; HKEY *
0x18005b610  mov     edx, 20019h; unsigned int
0x18005b615  lea     rcx, [rsp+0B8h+sz]; wchar_t *
0x18005b61a  call    ?HrOpenProfileKey@@YAJPEB_WKPEAPEAUHKEY__@@@Z; HrOpenProfileKey(wchar_t const *,ulong,HKEY__ * *)
0x18005b61f  mov     ebx, eax
0x18005b621  test    eax, eax
0x18005b623  jnz     loc_18005B705
0x18005b629  mov     [rsp+0B8h+cbData], 4
0x18005b631  lea     rax, [rsp+0B8h+cbData]
0x18005b636  mov     [rsp+0B8h+lpcbData], rax; lpcbData
0x18005b63b  lea     rax, [rsp+0B8h+Data]
0x18005b640  mov     [rsp+0B8h+lpData], rax; unsigned int
0x18005b645  xor     r9d, r9d; lpType
0x18005b648  xor     r8d, r8d; lpReserved
0x18005b64b  lea     rdx, aCategory; "Category"
0x18005b652  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18005b657  call    cs:__imp_RegQueryValueExW
0x18005b65d  test    eax, eax
0x18005b65f  jle     short loc_18005B669
0x18005b661  movzx   eax, ax
0x18005b664  or      eax, 80070000h
0x18005b669  mov     rcx, [rsp+0B8h]; this
0x18005b671  test    eax, eax
0x18005b673  jns     short loc_18005B689
0x18005b675  mov     r9d, eax; char *
0x18005b678  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x18005b67f  mov     edx, 48Ah; void *
0x18005b684  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b689  cmp     dword ptr [rsp+0B8h+Data], 2
0x18005b68e  jnz     short loc_18005B6F8
0x18005b690  lea     rdx, aCategory; "Category"
0x18005b697  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18005b69c  call    cs:__imp_RegDeleteValueW
0x18005b6a2  mov     rcx, [rsp+0B8h]; this
0x18005b6aa  test    eax, eax
0x18005b6ac  jz      short loc_18005B6C2
0x18005b6ae  mov     r9d, eax; char *
0x18005b6b1  lea     r8, aOnecoreNetNetp_19; "onecore\\net\\netprofiles\\service\\src"...
0x18005b6b8  mov     edx, 48Dh; void *
0x18005b6bd  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005b6c2  lea     rax, WPP_GLOBAL_Control
0x18005b6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b6d0  cmp     rcx, rax
0x18005b6d3  jz      short loc_18005B6F0
0x18005b6d5  test    byte ptr [rcx+1Ch], 2
0x18005b6d9  jz      short loc_18005B6F0
0x18005b6db  mov     edx, 3Eh ; '>'
0x18005b6e0  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18005b6e7  mov     rcx, [rcx+10h]
0x18005b6eb  call    WPP_SF_
0x18005b6f0  mov     dword ptr [rsp+0B8h+Data], 0
0x18005b6f8  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18005b6fd  call    cs:__imp_RegCloseKey
0x18005b703  jmp     short loc_18005B709
0x18005b705  test    ebx, ebx
0x18005b707  js      short loc_18005B711
0x18005b709  mov     eax, dword ptr [rsp+0B8h+Data]
0x18005b70d  mov     [rdi], eax
0x18005b70f  jmp     short loc_18005B73F
0x18005b711  lea     rax, WPP_GLOBAL_Control
0x18005b718  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b71f  cmp     rcx, rax
0x18005b722  jz      short loc_18005B73F
0x18005b724  test    byte ptr [rcx+1Ch], 1
0x18005b728  jz      short loc_18005B73F
0x18005b72a  mov     edx, 3Fh ; '?'
0x18005b72f  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18005b736  mov     rcx, [rcx+10h]
0x18005b73a  call    WPP_SF_
0x18005b73f  mov     rcx, [rsp+0B8h+lpCriticalSection]; lpCriticalSection
0x18005b744  test    rcx, rcx
0x18005b747  jz      short loc_18005B74F
0x18005b749  call    cs:__imp_LeaveCriticalSection
0x18005b74f  mov     eax, ebx
0x18005b751  jmp     short loc_18005B757
0x18005b753  mov     eax, [rsp+0B8h+cbData]
0x18005b757  mov     rcx, [rsp+0B8h+var_18]
0x18005b75f  xor     rcx, rsp; StackCookie
0x18005b762  call    __security_check_cookie
0x18005b767  mov     rbx, [rsp+0B8h+arg_10]
0x18005b76f  add     rsp, 0B0h
0x18005b776  pop     rdi
0x18005b777  retn
```
