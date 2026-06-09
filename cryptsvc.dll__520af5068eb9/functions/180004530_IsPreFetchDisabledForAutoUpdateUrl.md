# IsPreFetchDisabledForAutoUpdateUrl

- ea: `0x180004530`
- end: `0x180004847`
- name: `IsPreFetchDisabledForAutoUpdateUrl`
- size: `791`
- prototype: `__int64 __fastcall(int, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f950`

## callees

- `0x180004530`
- `0x180004850`
- `0x18000495c`
- `0x18000a980`
- `0x18000cab4`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004703`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004754`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004805`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000481c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000482c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004703`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004754`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004805`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000481c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000482c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004674`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800046d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000474c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800046d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000474c`
- `CRYPT32!I_CertSrvProtectFunction` at `0x180004589`
- `CRYPT32!I_CertSrvProtectFunction` at `0x180004589`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045f1`

## string_xrefs

- `0x18000462d`: `http://ctldl.windowsupdate.com/msdownload/update/v3/static/trustedr/en/flight`
- `0x180004626`: `http://ctldl.windowsupdate.com/msdownload/update/v3/static/trustedr/en`
- `0x1800045e3`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
__int64 __fastcall IsPreFetchDisabledForAutoUpdateUrl(int a1, char *a2)
{
  HKEY v2; // r13
  char *v5; // r12
  BYTE *v6; // r15
  const wchar_t *v7; // r14
  LSTATUS v8; // eax
  __int64 v9; // rdx
  const wchar_t *v10; // rbp
  __int64 v11; // rsi
  __int64 v12; // rbx
  size_t v13; // rbx
  int v14; // esi
  DWORD LastError; // ebx
  DWORD v16; // ebx
  signed __int64 v17; // r8
  int v18; // eax
  int v19; // edx
  BOOL v20; // edi
  DWORD v21; // ebx
  BYTE *SZValueFromRegistry; // rax
  int v24; // ebx
  HKEY hKey; // [rsp+A0h] [rbp+18h] BYREF

  v2 = 0;
  if ( a1 != 7 && (unsigned int)(a1 - 5) >= 2 )
    return 0;
  if ( (unsigned int)I_CertSrvProtectFunction(0) && !IsDisallowedCertAutoUpdateEnabled()
    || a1 == 7 && IsPinRulesAutoUpdateDisabled() )
  {
    return 1;
  }
  v5 = 0;
  v6 = 0;
  if ( a1 == 5 )
  {
    v7 = L"authrootstl.cab";
  }
  else
  {
    v24 = a1 - 6;
    if ( v24 )
    {
      if ( v24 != 1 )
      {
        SetLastError(0x80070057);
LABEL_43:
        v14 = 0;
        goto LABEL_17;
      }
      v7 = L"pinrulesstl.cab";
    }
    else
    {
      v7 = L"disallowedcertstl.cab";
    }
  }
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
         0,
         0x20119u,
         &hKey);
  if ( v8 )
  {
    hKey = 0;
    SetLastError(v8);
  }
  v2 = hKey;
  if ( hKey && (SZValueFromRegistry = ReadSZValueFromRegistry(hKey, v9), (v6 = SZValueFromRegistry) != 0) )
  {
    v10 = (const wchar_t *)SZValueFromRegistry;
  }
  else
  {
    v10 = L"http://ctldl.windowsupdate.com/msdownload/update/v3/static/trustedr/en/flight";
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedRoots_Flighting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedRoots_Flighting>::GetImpl'::`2'::impl) )
      v10 = L"http://ctldl.windowsupdate.com/msdownload/update/v3/static/trustedr/en";
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( (unsigned int)v12 > 0xFFFF )
  {
    SetLastError(0x216u);
    goto LABEL_43;
  }
  do
    ++v11;
  while ( v7[v11] );
  v5 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v11 + v12 + 2));
  if ( !v5 )
  {
    SetLastError(0x8007000E);
    goto LABEL_43;
  }
  v13 = 2LL * (unsigned int)v12;
  memcpy_0(v5, v10, v13);
  *(_WORD *)&v5[v13] = 47;
  memcpy_0(&v5[v13 + 2], v7, 2LL * (unsigned int)(v11 + 1));
  v14 = 1;
LABEL_17:
  if ( v6 )
  {
    LastError = GetLastError();
    LocalFree(v6);
    SetLastError(LastError);
  }
  if ( v2 )
  {
    v16 = GetLastError();
    RegCloseKey(v2);
    SetLastError(v16);
  }
  if ( !v14 )
    return 0;
  v17 = v5 - a2;
  do
  {
    v18 = *(unsigned __int16 *)&a2[v17];
    v19 = *(unsigned __int16 *)a2 - v18;
    if ( v19 )
      break;
    a2 += 2;
  }
  while ( v18 );
  v20 = v19 != 0;
  if ( v5 )
  {
    v21 = GetLastError();
    LocalFree(v5);
    SetLastError(v21);
  }
  return v20;
}

```

## disassembly

```asm
0x180004530  push    rbx
0x180004532  push    rbp
0x180004533  push    rdi
0x180004534  push    r13
0x180004536  sub     rsp, 68h
0x18000453a  xor     r13d, r13d
0x18000453d  mov     rdi, rdx
0x180004540  mov     [rsp+88h+arg_0], r13d
0x180004548  mov     ebx, ecx
0x18000454a  mov     ebp, r13d
0x18000454d  cmp     ecx, 7
0x180004550  jnz     loc_1800047C0
0x180004556  mov     [rsp+88h+var_40], r13
0x18000455b  xor     r9d, r9d
0x18000455e  mov     [rsp+88h+var_48], r13
0x180004563  xor     r8d, r8d
0x180004566  mov     [rsp+88h+var_50], r13
0x18000456b  mov     edx, 0Ch
0x180004570  mov     [rsp+88h+var_58], r13
0x180004575  xor     ecx, ecx
0x180004577  mov     [rsp+88h+var_60], r13d
0x18000457c  mov     [rsp+88h+phkResult], r13
0x180004581  mov     [rsp+88h+arg_8], rsi
0x180004589  call    cs:__imp_I_CertSrvProtectFunction
0x18000458f  test    eax, eax
0x180004591  jnz     loc_1800047D7
0x180004597  cmp     ebx, 7
0x18000459a  jz      loc_1800047A0
0x1800045a0  mov     [rsp+88h+var_28], r12
0x1800045a5  mov     r12, r13
0x1800045a8  mov     [rsp+88h+var_30], r14
0x1800045ad  mov     [rsp+88h+var_38], r15
0x1800045b2  mov     r15, r13
0x1800045b5  cmp     ebx, 5
0x1800045b8  jnz     loc_18000478F
0x1800045be  lea     r14, aAuthrootstlCab; "authrootstl.cab"
0x1800045c5  lea     rax, [rsp+88h+hKey]
0x1800045cd  mov     [rsp+88h+hKey], r13
0x1800045d5  mov     r9d, 20119h; samDesired
0x1800045db  mov     [rsp+88h+phkResult], rax; phkResult
0x1800045e0  xor     r8d, r8d; ulOptions
0x1800045e3  lea     rdx, SubKey; "Software\\Microsoft\\SystemCertificates"...
0x1800045ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800045f1  call    cs:__imp_RegOpenKeyExW
0x1800045f7  test    eax, eax
0x1800045f9  jnz     loc_1800047FB
0x1800045ff  mov     r13, [rsp+88h+hKey]
0x180004607  test    r13, r13
0x18000460a  jnz     loc_180004773
0x180004610  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedRoots_Flighting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedRoots_Flighting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedRoots_Flighting> `wil::Feature<__WilFeatureTraits_Feature_TrustedRoots_Flighting>::GetImpl(void)'::`2'::impl
0x180004617  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedRoots_Flighting@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedRoots_Flighting>::__private_IsEnabled(void)
0x18000461c  test    al, al
0x18000461e  jnz     loc_180004810
0x180004624  test    al, al
0x180004626  lea     rcx, aHttpCtldlWindo; "http://ctldl.windowsupdate.com/msdownlo"...
0x18000462d  lea     rbp, aHttpCtldlWindo_0; "http://ctldl.windowsupdate.com/msdownlo"...
0x180004634  cmovz   rbp, rcx
0x180004638  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000463f  mov     rbx, rsi
0x180004642  inc     rbx
0x180004645  cmp     [rbp+rbx*2+0], r12w
0x18000464b  jnz     short loc_180004642
0x18000464d  cmp     ebx, 0FFFFh
0x180004653  ja      loc_180004817
0x180004659  nop     dword ptr [rax+00000000h]
0x180004660  inc     rsi
0x180004663  cmp     [r14+rsi*2], r12w
0x180004668  jnz     short loc_180004660
0x18000466a  lea     edx, [rbx+2]
0x18000466d  xor     ecx, ecx; uFlags
0x18000466f  add     edx, esi
0x180004671  add     rdx, rdx; uBytes
0x180004674  call    cs:__imp_LocalAlloc
0x18000467a  mov     r12, rax
0x18000467d  test    rax, rax
0x180004680  jz      loc_180004827
0x180004686  mov     eax, ebx
0x180004688  mov     rdx, rbp; Src
0x18000468b  mov     rcx, r12; void *
0x18000468e  lea     rbx, [rax+rax]
0x180004692  mov     r8, rbx; Size
0x180004695  call    memcpy_0
0x18000469a  lea     r8d, [rsi+1]
0x18000469e  mov     word ptr [rbx+r12], 2Fh ; '/'
0x1800046a5  lea     rcx, [rbx+2]
0x1800046a9  add     r8, r8; Size
0x1800046ac  add     rcx, r12; void *
0x1800046af  mov     rdx, r14; Src
0x1800046b2  call    memcpy_0
0x1800046b7  mov     ebp, [rsp+88h+arg_0]
0x1800046be  mov     esi, 1
0x1800046c3  mov     r14, [rsp+88h+var_30]
0x1800046c8  test    r15, r15
0x1800046cb  jz      short loc_1800046E6
0x1800046cd  call    cs:__imp_GetLastError
0x1800046d3  mov     rcx, r15; hMem
0x1800046d6  mov     ebx, eax
0x1800046d8  call    cs:__imp_LocalFree
0x1800046de  mov     ecx, ebx; dwErrCode
0x1800046e0  call    cs:__imp_SetLastError
0x1800046e6  mov     r15, [rsp+88h+var_38]
0x1800046eb  test    r13, r13
0x1800046ee  jz      short loc_180004709
0x1800046f0  call    cs:__imp_GetLastError
0x1800046f6  mov     rcx, r13; hKey
0x1800046f9  mov     ebx, eax
0x1800046fb  call    cs:__imp_RegCloseKey
0x180004701  mov     ecx, ebx; dwErrCode
0x180004703  call    cs:__imp_SetLastError
0x180004709  test    esi, esi
0x18000470b  jz      loc_180004840
0x180004711  mov     r8, r12
0x180004714  sub     r8, rdi
0x180004717  nop     word ptr [rax+rax+00000000h]
0x180004720  movzx   edx, word ptr [rdi]
0x180004723  movzx   eax, word ptr [rdi+r8]
0x180004728  sub     edx, eax
0x18000472a  jnz     short loc_180004734
0x18000472c  add     rdi, 2
0x180004730  test    eax, eax
0x180004732  jnz     short loc_180004720
0x180004734  xor     edi, edi
0x180004736  test    edx, edx
0x180004738  setnz   dil
0x18000473c  test    r12, r12
0x18000473f  jz      short loc_18000475A
0x180004741  call    cs:__imp_GetLastError
0x180004747  mov     rcx, r12; hMem
0x18000474a  mov     ebx, eax
0x18000474c  call    cs:__imp_LocalFree
0x180004752  mov     ecx, ebx; dwErrCode
0x180004754  call    cs:__imp_SetLastError
0x18000475a  mov     eax, edi
0x18000475c  mov     r12, [rsp+88h+var_28]
0x180004761  mov     rsi, [rsp+88h+arg_8]
0x180004769  add     rsp, 68h
0x18000476d  pop     r13
0x18000476f  pop     rdi
0x180004770  pop     rbp
0x180004771  pop     rbx
0x180004772  retn
0x180004773  mov     rcx, r13; hKey
0x180004776  call    _ReadSZValueFromRegistry
0x18000477b  mov     r15, rax
0x18000477e  test    rax, rax
0x180004781  jz      loc_180004610
0x180004787  mov     rbp, rax
0x18000478a  jmp     loc_180004638
0x18000478f  sub     ebx, 6
0x180004792  jnz     short loc_1800047AF
0x180004794  lea     r14, aDisallowedcert; "disallowedcertstl.cab"
0x18000479b  jmp     loc_1800045C5
0x1800047a0  call    IsPinRulesAutoUpdateDisabled
0x1800047a5  test    eax, eax
0x1800047a7  jz      loc_1800045A0
0x1800047ad  jmp     short loc_1800047E4
0x1800047af  cmp     ebx, 1
0x1800047b2  jnz     short loc_1800047EE
0x1800047b4  lea     r14, aPinrulesstlCab; "pinrulesstl.cab"
0x1800047bb  jmp     loc_1800045C5
0x1800047c0  sub     ecx, 5
0x1800047c3  jz      loc_180004556
0x1800047c9  cmp     ecx, 1
0x1800047cc  jz      loc_180004556
0x1800047d2  mov     eax, r13d
0x1800047d5  jmp     short loc_180004769
0x1800047d7  call    IsDisallowedCertAutoUpdateEnabled
0x1800047dc  test    eax, eax
0x1800047de  jnz     loc_180004597
0x1800047e4  mov     eax, 1
0x1800047e9  jmp     loc_180004761
0x1800047ee  mov     ecx, 80070057h; dwErrCode
0x1800047f3  call    cs:__imp_SetLastError
0x1800047f9  jmp     short loc_180004839
0x1800047fb  mov     ecx, eax; dwErrCode
0x1800047fd  mov     [rsp+88h+hKey], r13
0x180004805  call    cs:__imp_SetLastError
0x18000480b  jmp     loc_1800045FF
0x180004810  mov     al, 1
0x180004812  jmp     loc_180004624
0x180004817  mov     ecx, 216h; dwErrCode
0x18000481c  call    cs:__imp_SetLastError
0x180004822  mov     ebp, r12d
0x180004825  jmp     short loc_180004839
0x180004827  mov     ecx, 8007000Eh; dwErrCode
0x18000482c  call    cs:__imp_SetLastError
0x180004832  mov     ebp, [rsp+88h+arg_0]
0x180004839  xor     esi, esi
0x18000483b  jmp     loc_1800046C3
0x180004840  mov     eax, ebp
0x180004842  jmp     loc_18000475C
```
