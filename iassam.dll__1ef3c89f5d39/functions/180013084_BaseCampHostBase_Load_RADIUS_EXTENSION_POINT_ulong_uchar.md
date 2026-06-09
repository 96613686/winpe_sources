# BaseCampHostBase::Load(_RADIUS_EXTENSION_POINT,ulong *,uchar * *)

- ea: `0x180013084`
- end: `0x1800133b5`
- name: `?Load@BaseCampHostBase@@IEAAKW4_RADIUS_EXTENSION_POINT@@PEAKPEAPEAE@Z`
- size: `817`
- prototype: `unsigned int(BaseCampHostBase *__hidden this, enum _RADIUS_EXTENSION_POINT, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180012c74`

## callees

- `0x18000c4a4`
- `0x18000e754`
- `0x180013084`
- `0x18001426c`
- `0x1800254a0`

## import_xrefs

- `msvcrt!malloc` at `0x180013168`
- `msvcrt!malloc` at `0x180013168`
- `ADVAPI32!RegCloseKey` at `0x180013393`
- `ADVAPI32!RegCloseKey` at `0x180013393`
- `ADVAPI32!RegOpenKeyW` at `0x18001311f`
- `ADVAPI32!RegOpenKeyW` at `0x18001311f`
- `ADVAPI32!RegQueryValueExW` at `0x180013153`
- `ADVAPI32!RegQueryValueExW` at `0x180013194`
- `ADVAPI32!RegQueryValueExW` at `0x180013153`
- `ADVAPI32!RegQueryValueExW` at `0x180013194`

## string_xrefs

- `0x1800130b1`: `ExtensionDLLs`
- `0x1800130aa`: `AuthorizationDLLs`
- `0x180013111`: `System\CurrentControlSet\Services\AuthSrv\Parameters`
- `0x1800132fd`: `System\CurrentControlSet\Services\AuthSrv\Parameters`
- `0x18001334f`: `System\CurrentControlSet\Services\AuthSrv\Parameters`
- `0x180013307`: `%S doesn't exist; no extensions loaded.`
- `0x180013359`: `RegOpenKeyW for %S failed with error %ld.`
- `0x1800131c5`: `%S registry value is not of type REG_MULTI_SZ.`

## pseudocode

```c
__int64 __fastcall BaseCampHostBase::Load(
        BaseCampHostBase *this,
        enum _RADIUS_EXTENSION_POINT a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  const WCHAR *v6; // rdi
  int v7; // r9d
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned __int8 *lpData; // rax
  int v11; // r9d
  int v12; // r9d
  int v13; // edx
  int v14; // r9d
  __int64 result; // rax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  BaseCampHostBase *cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  cbData = this;
  phkResult = 0;
  v6 = L"ExtensionDLLs";
  if ( a2 )
    v6 = L"AuthorizationDLLs";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Loading %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
      v7,
      (__int64)v6);
  }
  v8 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\AuthSrv\\Parameters", &phkResult);
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_39;
      }
      v6 = L"System\\CurrentControlSet\\Services\\AuthSrv\\Parameters";
      WppDbgPrint("RegOpenKeyW for %S failed with error %ld.");
      v13 = 12;
      goto LABEL_38;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("%S doesn't exist; no extensions loaded.");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
        v14,
        (__int64)L"System\\CurrentControlSet\\Services\\AuthSrv\\Parameters");
    }
  }
  else
  {
    Type = 0;
    LODWORD(cbData) = 0;
    v8 = RegQueryValueExW(phkResult, v6, 0, &Type, 0, (LPDWORD)&cbData);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_39;
      }
      WppDbgPrint("RegQueryValueExW for %S failed with error %ld.");
      v13 = 13;
      goto LABEL_38;
    }
    v9 = (unsigned int)cbData;
    lpData = (unsigned __int8 *)malloc((unsigned int)cbData);
    *a4 = lpData;
    if ( lpData )
    {
      *a3 = v9;
      v8 = RegQueryValueExW(phkResult, v6, 0, &Type, lpData, a3);
      if ( !v8 )
      {
        if ( Type != 7 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WppDbgPrint("%S registry value is not of type REG_MULTI_SZ.");
            WPP_SF_sS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
              v11,
              (__int64)v6);
          }
          v8 = 13;
        }
        goto LABEL_39;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_39;
      }
      WppDbgPrint("RegQueryValueExW for %S failed with error %ld.");
      v13 = 15;
LABEL_38:
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
        v12,
        (__int64)v6,
        v8);
      goto LABEL_39;
    }
    v8 = 14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("BaseCampHostBase::Load: Not enough memory");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids, "NPSSVC");
    }
  }
LABEL_39:
  if ( phkResult )
    RegCloseKey(phkResult);
  result = 0;
  if ( v8 != 2 )
    return v8;
  return result;
}

```

## disassembly

```asm
0x180013084  mov     [rsp-28h+arg_10], rbx
0x180013089  mov     [rsp-28h+cbData], rcx
0x18001308e  push    rbp
0x18001308f  push    rsi
0x180013090  push    rdi
0x180013091  push    r13
0x180013093  push    r14
0x180013095  mov     rbp, rsp
0x180013098  sub     rsp, 40h
0x18001309c  mov     r14, r9
0x18001309f  mov     rsi, r8
0x1800130a2  mov     [rbp+phkResult], 0
0x1800130aa  lea     rax, aAuthorizationd; "AuthorizationDLLs"
0x1800130b1  lea     rdi, aExtensiondlls; "ExtensionDLLs"
0x1800130b8  test    edx, edx
0x1800130ba  cmovnz  rdi, rax
0x1800130be  lea     r13, WPP_GLOBAL_Control
0x1800130c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800130cc  cmp     rax, r13
0x1800130cf  jz      short loc_18001310D
0x1800130d1  cmp     byte ptr [rax+19h], 4
0x1800130d5  jb      short loc_18001310D
0x1800130d7  test    byte ptr [rax+1Ch], 4
0x1800130db  jz      short loc_18001310D
0x1800130dd  mov     rdx, rdi
0x1800130e0  lea     rcx, aLoadingS; "Loading %S"
0x1800130e7  call    WppDbgPrint
0x1800130ec  mov     edx, 0Ah
0x1800130f1  mov     [rsp+40h+lpData], rdi
0x1800130f6  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x1800130fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180013104  mov     rcx, [rcx+10h]
0x180013108  call    WPP_SF_sS
0x18001310d  lea     r8, [rbp+phkResult]; phkResult
0x180013111  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Au"...
0x180013118  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001311f  call    cs:__imp_RegOpenKeyW
0x180013125  mov     ebx, eax
0x180013127  xor     ecx, ecx
0x180013129  test    eax, eax
0x18001312b  jnz     loc_1800132D4
0x180013131  mov     [rbp+Type], ecx
0x180013134  mov     dword ptr [rbp+cbData], ecx
0x180013137  lea     rax, [rbp+cbData]
0x18001313b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180013140  mov     [rsp+40h+lpData], rcx; lpData
0x180013145  lea     r9, [rbp+Type]; lpType
0x180013149  xor     r8d, r8d; lpReserved
0x18001314c  mov     rdx, rdi; lpValueName
0x18001314f  mov     rcx, [rbp+phkResult]; hKey
0x180013153  call    cs:__imp_RegQueryValueExW
0x180013159  mov     ebx, eax
0x18001315b  test    eax, eax
0x18001315d  jnz     loc_180013294
0x180013163  mov     ebx, dword ptr [rbp+cbData]
0x180013166  mov     ecx, ebx; Size
0x180013168  call    cs:__imp_malloc
0x18001316e  mov     [r14], rax
0x180013171  test    rax, rax
0x180013174  jz      loc_18001323A
0x18001317a  mov     [rsi], ebx
0x18001317c  mov     [rsp+40h+lpcbData], rsi; lpcbData
0x180013181  mov     [rsp+40h+lpData], rax; lpData
0x180013186  lea     r9, [rbp+Type]; lpType
0x18001318a  xor     r8d, r8d; lpReserved
0x18001318d  mov     rdx, rdi; lpValueName
0x180013190  mov     rcx, [rbp+phkResult]; hKey
0x180013194  call    cs:__imp_RegQueryValueExW
0x18001319a  mov     ebx, eax
0x18001319c  test    eax, eax
0x18001319e  jnz     short loc_1800131FA
0x1800131a0  cmp     [rbp+Type], 7
0x1800131a4  jz      loc_18001338A
0x1800131aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800131b1  cmp     rax, r13
0x1800131b4  jz      short loc_1800131F0
0x1800131b6  cmp     byte ptr [rax+19h], 2
0x1800131ba  jb      short loc_1800131F0
0x1800131bc  test    byte ptr [rax+1Ch], 4
0x1800131c0  jz      short loc_1800131F0
0x1800131c2  mov     rdx, rdi
0x1800131c5  lea     rcx, aSRegistryValue; "%S registry value is not of type REG_MU"...
0x1800131cc  call    WppDbgPrint
0x1800131d1  lea     edx, [rbx+10h]
0x1800131d4  mov     [rsp+40h+lpData], rdi
0x1800131d9  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x1800131e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131e7  mov     rcx, [rcx+10h]
0x1800131eb  call    WPP_SF_sS
0x1800131f0  mov     ebx, 0Dh
0x1800131f5  jmp     loc_18001338A
0x1800131fa  mov     rax, cs:WPP_GLOBAL_Control
0x180013201  cmp     rax, r13
0x180013204  jz      loc_18001338A
0x18001320a  cmp     byte ptr [rax+19h], 2
0x18001320e  jb      loc_18001338A
0x180013214  test    byte ptr [rax+1Ch], 4
0x180013218  jz      loc_18001338A
0x18001321e  mov     r8d, ebx
0x180013221  mov     rdx, rdi
0x180013224  lea     rcx, aRegqueryvaluee; "RegQueryValueExW for %S failed with err"...
0x18001322b  call    WppDbgPrint
0x180013230  mov     edx, 0Fh
0x180013235  jmp     loc_18001336A
0x18001323a  mov     ebx, 0Eh
0x18001323f  mov     rax, cs:WPP_GLOBAL_Control
0x180013246  cmp     rax, r13
0x180013249  jz      loc_18001338A
0x18001324f  cmp     byte ptr [rax+19h], 2
0x180013253  jb      loc_18001338A
0x180013259  test    byte ptr [rax+1Ch], 4
0x18001325d  jz      loc_18001338A
0x180013263  lea     rcx, aBasecamphostba; "BaseCampHostBase::Load: Not enough memo"...
0x18001326a  call    WppDbgPrint
0x18001326f  mov     edx, ebx
0x180013271  lea     r9, aNpssvc; "NPSSVC"
0x180013278  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x18001327f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013286  mov     rcx, [rcx+10h]
0x18001328a  call    WPP_SF_s
0x18001328f  jmp     loc_18001338A
0x180013294  mov     rax, cs:WPP_GLOBAL_Control
0x18001329b  cmp     rax, r13
0x18001329e  jz      loc_18001338A
0x1800132a4  cmp     byte ptr [rax+19h], 2
0x1800132a8  jb      loc_18001338A
0x1800132ae  test    byte ptr [rax+1Ch], 4
0x1800132b2  jz      loc_18001338A
0x1800132b8  mov     r8d, ebx
0x1800132bb  mov     rdx, rdi
0x1800132be  lea     rcx, aRegqueryvaluee; "RegQueryValueExW for %S failed with err"...
0x1800132c5  call    WppDbgPrint
0x1800132ca  mov     edx, 0Dh
0x1800132cf  jmp     loc_18001336A
0x1800132d4  cmp     ebx, 2
0x1800132d7  jnz     short loc_180013334
0x1800132d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800132e0  cmp     rax, r13
0x1800132e3  jz      loc_18001338A
0x1800132e9  cmp     byte ptr [rax+19h], 4
0x1800132ed  jb      loc_18001338A
0x1800132f3  test    byte ptr [rax+1Ch], 4
0x1800132f7  jz      loc_18001338A
0x1800132fd  lea     rdi, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Au"...
0x180013304  mov     rdx, rdi
0x180013307  lea     rcx, aSDoesnTExistNo; "%S doesn't exist; no extensions loaded."
0x18001330e  call    WppDbgPrint
0x180013313  lea     edx, [rbx+9]
0x180013316  mov     [rsp+40h+lpData], rdi
0x18001331b  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013322  mov     rcx, cs:WPP_GLOBAL_Control
0x180013329  mov     rcx, [rcx+10h]
0x18001332d  call    WPP_SF_sS
0x180013332  jmp     short loc_18001338A
0x180013334  mov     rax, cs:WPP_GLOBAL_Control
0x18001333b  cmp     rax, r13
0x18001333e  jz      short loc_18001338A
0x180013340  cmp     byte ptr [rax+19h], 2
0x180013344  jb      short loc_18001338A
0x180013346  test    byte ptr [rax+1Ch], 4
0x18001334a  jz      short loc_18001338A
0x18001334c  mov     r8d, ebx
0x18001334f  lea     rdi, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Au"...
0x180013356  mov     rdx, rdi
0x180013359  lea     rcx, aRegopenkeywFor; "RegOpenKeyW for %S failed with error %l"...
0x180013360  call    WppDbgPrint
0x180013365  mov     edx, 0Ch
0x18001336a  mov     dword ptr [rsp+40h+lpcbData], ebx
0x18001336e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013375  mov     [rsp+40h+lpData], rdi
0x18001337a  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013381  mov     rcx, [rcx+10h]
0x180013385  call    WPP_SF_sSl
0x18001338a  mov     rcx, [rbp+phkResult]; hKey
0x18001338e  test    rcx, rcx
0x180013391  jz      short loc_180013399
0x180013393  call    cs:__imp_RegCloseKey
0x180013399  xor     eax, eax
0x18001339b  cmp     ebx, 2
0x18001339e  cmovnz  eax, ebx
0x1800133a1  mov     rbx, [rsp+40h+arg_10]
0x1800133a9  add     rsp, 40h
0x1800133ad  pop     r14
0x1800133af  pop     r13
0x1800133b1  pop     rdi
0x1800133b2  pop     rsi
0x1800133b3  pop     rbp
0x1800133b4  retn
```
