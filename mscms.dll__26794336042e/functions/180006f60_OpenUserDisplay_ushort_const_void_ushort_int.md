# OpenUserDisplay(ushort const *,void * *,ushort *,int)

- ea: `0x180006f60`
- end: `0x180007165`
- name: `?OpenUserDisplay@@YAHPEBGPEAPEAXPEAGH@Z`
- size: `517`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006a50`
- `0x180006f60`
- `0x18000716c`
- `0x180007bb0`
- `0x18000efbc`
- `0x18001cd90`
- `0x18004da68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ff3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ff3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006fdf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800070d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006fdf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800070d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000712b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000712b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800070fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800070fa`

## pseudocode

```c
__int64 __fastcall OpenUserDisplay(unsigned __int16 *a1, HKEY *a2, unsigned __int16 *a3, int a4)
{
  REGSAM samDesired; // ebx
  unsigned int v8; // edi
  LSTATUS v9; // eax
  const unsigned __int16 *v10; // rax
  __int64 v11; // rdx
  REGSAM v12; // r9d
  LSTATUS v13; // eax
  __int64 result; // rax
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  void *v17; // [rsp+60h] [rbp-10h]
  HKEY v18; // [rsp+A8h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+B8h] [rbp+48h] BYREF

  phkResult = 0;
  hKey = 0;
  v18 = 0;
  v17 = 0;
  samDesired = a4 != 0 ? 8 : 4;
  v8 = 0;
  if ( a4 )
  {
    v9 = RegOpenKeyExW(HKEY_CURRENT_USER, gszICMRegPath, 0, samDesired, &phkResult);
  }
  else
  {
    dwDisposition = 0;
    v9 = RegCreateKeyExW(HKEY_CURRENT_USER, gszICMRegPath, 0, 0, 0, samDesired, 0, &phkResult, &dwDisposition);
  }
  if ( v9
    || (v9 = CreateOrOpenKey(
               (_DWORD)phkResult,
               (unsigned int)gszDisplayProfileAssociations,
               a4 == 0,
               samDesired,
               (__int64)&hKey)) != 0 )
  {
    SetLastError(v9);
  }
  else
  {
    v10 = (const unsigned __int16 *)wcsistr(a1);
    if ( v10 )
      a1 = (unsigned __int16 *)v10;
    LOBYTE(v11) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::GetImpl'::`2'::impl,
      v11);
    if ( (int)OpenDisplayMux(a1, 1, &v18) >= 0
      || (unsigned int)OpenDisplay(a1)
      && (v12 = a4 != 0 ? 1 : 3, hKey)
      && a1
      && (a4
        ? (v13 = RegOpenKeyExW(hKey, a1, 0, v12, &v18))
        : (dwDisposition = 0, v13 = RegCreateKeyExW(hKey, a1, 0, 0, 0, v12, 0, &v18, &dwDisposition)),
          !v13) )
    {
      v8 = 1;
    }
    else
    {
      v18 = 0;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v8 && v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( v17 )
    CloseUserDevice(v17);
  result = v8;
  *a2 = v18;
  return result;
}

```

## disassembly

```asm
0x180006f60  mov     r11, rsp
0x180006f63  mov     [r11+8], rbx
0x180006f67  mov     [r11+18h], rsi
0x180006f6b  push    rbp
0x180006f6c  push    rdi
0x180006f6d  push    r12
0x180006f6f  push    r14
0x180006f71  push    r15
0x180006f73  mov     rbp, rsp
0x180006f76  sub     rsp, 70h
0x180006f7a  xor     r12d, r12d
0x180006f7d  mov     eax, r9d
0x180006f80  neg     eax
0x180006f82  mov     [rbp+var_20], r12
0x180006f86  mov     r15, rdx
0x180006f89  mov     [rbp+hKey], r12
0x180006f8d  sbb     ebx, ebx
0x180006f8f  mov     [rbp+arg_8], r12
0x180006f93  and     ebx, 4
0x180006f96  mov     [rbp+var_10], r12
0x180006f9a  add     ebx, 4
0x180006f9d  lea     rdx, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180006fa4  xor     r8d, r8d; ulOptions
0x180006fa7  mov     rsi, rcx
0x180006faa  mov     r14d, r9d
0x180006fad  mov     edi, r12d
0x180006fb0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006fb7  test    r9d, r9d
0x180006fba  jnz     short loc_180006FE7
0x180006fbc  lea     rax, [rbp+dwDisposition]
0x180006fc0  mov     [rbp+dwDisposition], r12d
0x180006fc4  mov     [r11-58h], rax
0x180006fc8  xor     r9d, r9d; lpClass
0x180006fcb  lea     rax, [rbp+var_20]
0x180006fcf  mov     [r11-60h], rax
0x180006fd3  mov     [r11-68h], r12
0x180006fd7  mov     [rsp+70h+samDesired], ebx; samDesired
0x180006fdb  mov     [r11-78h], r12d
0x180006fdf  call    cs:__imp_RegCreateKeyExW
0x180006fe5  jmp     short loc_180006FF9
0x180006fe7  lea     rax, [rbp+var_20]
0x180006feb  mov     r9d, ebx; samDesired
0x180006fee  mov     [rsp+70h+phkResult], rax; phkResult
0x180006ff3  call    cs:__imp_RegOpenKeyExW
0x180006ff9  test    eax, eax
0x180006ffb  jnz     loc_1800070F8
0x180007001  mov     rcx, [rbp+var_20]
0x180007005  lea     rax, [rbp+hKey]
0x180007009  mov     r8d, r12d
0x18000700c  mov     [rsp+70h+phkResult], rax
0x180007011  test    r14d, r14d
0x180007014  lea     rdx, gszDisplayProfileAssociations; "ProfileAssociations\\Display"
0x18000701b  mov     r9d, ebx
0x18000701e  setz    r8b
0x180007022  call    CreateOrOpenKey
0x180007027  test    eax, eax
0x180007029  jnz     loc_1800070F8
0x18000702f  mov     rcx, rsi
0x180007032  call    wcsistr
0x180007037  test    rax, rax
0x18000703a  cmovnz  rsi, rax
0x18000703e  mov     ebx, 1
0x180007043  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation> `wil::Feature<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::GetImpl(void)'::`2'::impl
0x18000704a  mov     dl, bl
0x18000704c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisplayMux_ColorProfileMitigation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180007051  lea     r8, [rbp+arg_8]; HKEY *
0x180007055  mov     edx, ebx; int
0x180007057  mov     rcx, rsi; unsigned __int16 *
0x18000705a  call    ?OpenDisplayMux@@YAJPEBGHPEAPEAUHKEY__@@@Z; OpenDisplayMux(ushort const *,int,HKEY__ * *)
0x18000705f  test    eax, eax
0x180007061  js      short loc_18000706A
0x180007063  mov     edi, ebx
0x180007065  jmp     loc_180007100
0x18000706a  mov     r9d, ebx
0x18000706d  lea     rdx, [rbp+var_10]
0x180007071  xor     r8d, r8d
0x180007074  mov     rcx, rsi; Str
0x180007077  call    OpenDisplay
0x18000707c  test    eax, eax
0x18000707e  jnz     short loc_180007086
0x180007080  mov     [rbp+arg_8], r12
0x180007084  jmp     short loc_180007100
0x180007086  mov     rcx, [rbp+hKey]; hKey
0x18000708a  mov     eax, r14d
0x18000708d  neg     eax
0x18000708f  sbb     r9d, r9d
0x180007092  and     r9d, 0FFFFFFFEh
0x180007096  add     r9d, 3; samDesired
0x18000709a  test    rcx, rcx
0x18000709d  jz      short loc_180007080
0x18000709f  test    rsi, rsi
0x1800070a2  jz      short loc_180007080
0x1800070a4  xor     r8d, r8d; ulOptions
0x1800070a7  mov     rdx, rsi; lpSubKey
0x1800070aa  test    r14d, r14d
0x1800070ad  jnz     short loc_1800070DF
0x1800070af  lea     rax, [rbp+dwDisposition]
0x1800070b3  mov     [rbp+dwDisposition], r12d
0x1800070b7  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1800070bc  lea     rax, [rbp+arg_8]
0x1800070c0  mov     [rsp+70h+var_38], rax; phkResult
0x1800070c5  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800070ca  mov     [rsp+70h+samDesired], r9d; samDesired
0x1800070cf  xor     r9d, r9d; lpClass
0x1800070d2  mov     dword ptr [rsp+70h+phkResult], r12d; dwOptions
0x1800070d7  call    cs:__imp_RegCreateKeyExW
0x1800070dd  jmp     short loc_1800070EE
0x1800070df  lea     rax, [rbp+arg_8]
0x1800070e3  mov     [rsp+70h+phkResult], rax; phkResult
0x1800070e8  call    cs:__imp_RegOpenKeyExW
0x1800070ee  test    eax, eax
0x1800070f0  jz      loc_180007063
0x1800070f6  jmp     short loc_180007080
0x1800070f8  mov     ecx, eax; dwErrCode
0x1800070fa  call    cs:__imp_SetLastError
0x180007100  mov     rcx, [rbp+var_20]; hKey
0x180007104  test    rcx, rcx
0x180007107  jz      short loc_18000710F
0x180007109  call    cs:__imp_RegCloseKey
0x18000710f  mov     rcx, [rbp+hKey]; hKey
0x180007113  test    rcx, rcx
0x180007116  jz      short loc_18000711E
0x180007118  call    cs:__imp_RegCloseKey
0x18000711e  test    edi, edi
0x180007120  jnz     short loc_180007135
0x180007122  mov     rcx, [rbp+arg_8]; hKey
0x180007126  test    rcx, rcx
0x180007129  jz      short loc_180007135
0x18000712b  call    cs:__imp_RegCloseKey
0x180007131  mov     [rbp+arg_8], r12
0x180007135  mov     rcx, [rbp+var_10]; void *
0x180007139  test    rcx, rcx
0x18000713c  jz      short loc_180007143
0x18000713e  call    ?CloseUserDevice@@YAHPEAX@Z; CloseUserDevice(void *)
0x180007143  mov     rcx, [rbp+arg_8]
0x180007147  lea     r11, [rsp+70h+var_s0]
0x18000714c  mov     rbx, [r11+30h]
0x180007150  mov     eax, edi
0x180007152  mov     rsi, [r11+40h]
0x180007156  mov     [r15], rcx
0x180007159  mov     rsp, r11
0x18000715c  pop     r15
0x18000715e  pop     r14
0x180007160  pop     r12
0x180007162  pop     rdi
0x180007163  pop     rbp
0x180007164  retn
```
