# CMbaeInternal::_SetAppMarkedAsInstalled(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800305d0`
- end: `0x180030789`
- name: `?_SetAppMarkedAsInstalled@CMbaeInternal@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `441`
- prototype: `__int64 __fastcall(CMbaeInternal *, const WCHAR *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18002f1e0`

## callees

- `0x180009474`
- `0x18002d2e0`
- `0x18002f894`
- `0x1800305d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800306db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003074e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003076a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800306db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003074e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003076a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030693`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030693`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800306ff`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800306ff`

## pseudocode

```c
__int64 __fastcall CMbaeInternal::_SetAppMarkedAsInstalled(CMbaeInternal *a1, const WCHAR *a2, char a3)
{
  int UserInstalledAppsKey; // eax
  unsigned int v6; // edi
  const WCHAR *v8; // rdx
  HKEY v9; // rbx
  LSTATUS v10; // eax
  unsigned int v11; // edi
  const WCHAR *v12; // r8
  HKEY v13; // rbx
  LSTATUS v14; // eax
  unsigned int v15; // edi
  int lpData; // [rsp+20h] [rbp-38h]
  int lpDataa; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  unsigned int *v19; // [rsp+38h] [rbp-20h] BYREF
  char v20; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v22; // [rsp+60h] [rbp+8h] BYREF
  int v23; // [rsp+64h] [rbp+Ch]
  int Data; // [rsp+78h] [rbp+20h] BYREF

  v23 = HIDWORD(a1);
  v22 = 0;
  v19 = &v22;
  v20 = 1;
  hKey = 0;
  UserInstalledAppsKey = CMbaeInternal::_GetUserInstalledAppsKey(a1, 0x20006u, &hKey);
  v6 = UserInstalledAppsKey;
  if ( UserInstalledAppsKey >= 0 )
  {
    if ( a3 )
    {
      Data = 0;
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const WCHAR **)a2;
      v8 = a2;
      v9 = hKey;
      v10 = RegSetValueExW(hKey, v8, 0, 4u, (const BYTE *)&Data, 4u);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v22 = v11;
      if ( (v11 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x34A,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
          (const char *)v11,
          lpDataa);
      wil::details::lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___::_lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___(&v19);
      if ( v9 )
        RegCloseKey(v9);
      return v11;
    }
    else
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const WCHAR **)a2;
      v12 = a2;
      v13 = hKey;
      v14 = RegDeleteKeyValueW(hKey, 0, v12);
      v15 = v14;
      if ( (v14 & 0xFFFFFFFD) != 0 )
      {
        if ( v14 > 0 )
          v15 = (unsigned __int16)v14 | 0x80070000;
        v22 = v15;
        if ( (v15 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x352,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
            (const char *)v15,
            lpData);
        wil::details::lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___::_lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___(&v19);
        if ( v13 )
          RegCloseKey(v13);
        return v15;
      }
      else
      {
        wil::details::lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___::_lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___(&v19);
        if ( v13 )
          RegCloseKey(v13);
        return 0;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x344,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
      (const char *)(unsigned int)UserInstalledAppsKey,
      lpData);
    wil::details::lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___::_lambda_call__CMbaeInternal::_SetAppMarkedAsInstalled_::_3_::_lambda_1___(&v19);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
}

```

## disassembly

```asm
0x1800305d0  mov     r11, rsp
0x1800305d3  mov     [r11+10h], rbx
0x1800305d7  mov     [r11+18h], rsi
0x1800305db  mov     [r11+8], rcx
0x1800305df  push    rdi
0x1800305e0  sub     rsp, 50h
0x1800305e4  mov     sil, r8b
0x1800305e7  mov     rbx, rdx
0x1800305ea  mov     [rsp+58h+arg_0], 0
0x1800305f2  lea     rax, [r11+8]
0x1800305f6  mov     [r11-20h], rax
0x1800305fa  mov     [rsp+58h+var_18], 1
0x1800305ff  mov     qword ptr [r11-28h], 0
0x180030607  lea     r8, [r11-28h]; HKEY *
0x18003060b  mov     edx, 20006h; unsigned int
0x180030610  call    ?_GetUserInstalledAppsKey@CMbaeInternal@@AEAAJKPEAPEAUHKEY__@@@Z; CMbaeInternal::_GetUserInstalledAppsKey(ulong,HKEY__ * *)
0x180030615  mov     edi, eax
0x180030617  test    eax, eax
0x180030619  jns     short loc_180030655
0x18003061b  mov     rcx, [rsp+58h]; this
0x180030620  mov     r9d, eax; char *
0x180030623  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003062a  mov     edx, 344h; void *
0x18003062f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030634  lea     rcx, [rsp+58h+var_20]
0x180030639  call    wil__details__lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1______lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1___
0x18003063e  mov     rcx, [rsp+58h+hKey]; hKey
0x180030643  test    rcx, rcx
0x180030646  jz      short loc_18003064E
0x180030648  call    cs:__imp_RegCloseKey
0x18003064e  mov     eax, edi
0x180030650  jmp     loc_180030778
0x180030655  test    sil, sil
0x180030658  jz      loc_1800306E8
0x18003065e  mov     [rsp+58h+Data], 0
0x180030666  cmp     qword ptr [rbx+18h], 7
0x18003066b  jbe     short loc_180030670
0x18003066d  mov     rbx, [rbx]
0x180030670  mov     r9d, 4; dwType
0x180030676  mov     [rsp+58h+cbData], r9d; cbData
0x18003067b  lea     rax, [rsp+58h+Data]
0x180030680  mov     [rsp+58h+lpData], rax; int
0x180030685  xor     r8d, r8d; Reserved
0x180030688  mov     rdx, rbx; lpValueName
0x18003068b  mov     rbx, [rsp+58h+hKey]
0x180030690  mov     rcx, rbx; hKey
0x180030693  call    cs:__imp_RegSetValueExW
0x180030699  mov     edi, eax
0x18003069b  test    eax, eax
0x18003069d  jle     short loc_1800306A8
0x18003069f  movzx   edi, ax
0x1800306a2  or      edi, 80070000h
0x1800306a8  mov     [rsp+58h+arg_0], edi
0x1800306ac  test    edi, edi
0x1800306ae  jns     short loc_1800306C9
0x1800306b0  mov     rcx, [rsp+58h]; this
0x1800306b5  mov     r9d, edi; char *
0x1800306b8  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800306bf  mov     edx, 34Ah; void *
0x1800306c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800306c9  lea     rcx, [rsp+58h+var_20]
0x1800306ce  call    wil__details__lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1______lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1___
0x1800306d3  test    rbx, rbx
0x1800306d6  jz      short loc_1800306E1
0x1800306d8  mov     rcx, rbx; hKey
0x1800306db  call    cs:__imp_RegCloseKey
0x1800306e1  mov     eax, edi
0x1800306e3  jmp     loc_180030778
0x1800306e8  cmp     qword ptr [rbx+18h], 7
0x1800306ed  jbe     short loc_1800306F2
0x1800306ef  mov     rbx, [rbx]
0x1800306f2  mov     r8, rbx; lpValueName
0x1800306f5  xor     edx, edx; lpSubKey
0x1800306f7  mov     rbx, [rsp+58h+hKey]
0x1800306fc  mov     rcx, rbx; hKey
0x1800306ff  call    cs:__imp_RegDeleteKeyValueW
0x180030705  mov     edi, eax
0x180030707  test    eax, 0FFFFFFFDh
0x18003070c  jz      short loc_180030758
0x18003070e  test    eax, eax
0x180030710  jle     short loc_18003071B
0x180030712  movzx   edi, ax
0x180030715  or      edi, 80070000h
0x18003071b  mov     [rsp+58h+arg_0], edi
0x18003071f  test    edi, edi
0x180030721  jns     short loc_18003073C
0x180030723  mov     rcx, [rsp+58h]; this
0x180030728  mov     r9d, edi; char *
0x18003072b  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180030732  mov     edx, 352h; void *
0x180030737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003073c  lea     rcx, [rsp+58h+var_20]
0x180030741  call    wil__details__lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1______lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1___
0x180030746  test    rbx, rbx
0x180030749  jz      short loc_180030754
0x18003074b  mov     rcx, rbx; hKey
0x18003074e  call    cs:__imp_RegCloseKey
0x180030754  mov     eax, edi
0x180030756  jmp     short loc_180030778
0x180030758  lea     rcx, [rsp+58h+var_20]
0x18003075d  call    wil__details__lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1______lambda_call__CMbaeInternal___SetAppMarkedAsInstalled____3____lambda_1___
0x180030762  test    rbx, rbx
0x180030765  jz      short loc_180030770
0x180030767  mov     rcx, rbx; hKey
0x18003076a  call    cs:__imp_RegCloseKey
0x180030770  xor     eax, eax
0x180030772  jmp     short loc_180030778
0x180030774  mov     eax, [rsp+58h+arg_0]
0x180030778  mov     rbx, [rsp+58h+arg_8]
0x18003077d  mov     rsi, [rsp+58h+arg_10]
0x180030782  add     rsp, 50h
0x180030786  pop     rdi
0x180030787  retn
```
