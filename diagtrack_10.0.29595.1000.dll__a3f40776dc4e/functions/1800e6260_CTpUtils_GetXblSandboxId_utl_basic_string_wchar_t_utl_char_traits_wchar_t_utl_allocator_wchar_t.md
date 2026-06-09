# CTpUtils::GetXblSandboxId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800e6260`
- end: `0x1800e65cc`
- name: `?GetXblSandboxId@CTpUtils@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180191a0c`

## callees

- `0x1800b1300`
- `0x1800e3c84`
- `0x1800e3f00`
- `0x1800e4410`
- `0x1800e4454`
- `0x1800e4a40`
- `0x1800e4c98`
- `0x1800e6260`
- `0x1800e65d4`
- `0x18020aac0`
- `0x18020afa4`
- `0x18020bab8`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e64f8`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e64f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e6317`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e6317`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e62c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e62c5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800e62a5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800e62a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6419`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e63f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e63f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6559`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e645e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e64c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e645e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e64c4`

## string_xrefs

- `0x1800e62be`: `XboxLiveTitleId.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTpUtils::GetXblSandboxId(__int64 a1)
{
  HMODULE Library; // rax
  signed int String; // ebx
  FARPROC ProcAddress; // rbx
  int v5; // eax
  HKEY v6; // rcx
  HKEY v7; // rbx
  LSTATUS ValueW; // eax
  size_t v9; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-B0h] BYREF
  char *v14; // [rsp+58h] [rbp-A8h]
  char v15; // [rsp+60h] [rbp-A0h] BYREF
  void *v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v17; // [rsp+78h] [rbp-88h]
  char v18; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v20[24]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t v21[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v16);
  pcbData = 0;
  RtlGetDeviceFamilyInfoEnum(0, &pcbData, 0);
  if ( pcbData == 5 )
  {
    Library = LoadLibraryExW(L"XboxLiveTitleId.dll", 0, 0x800u);
    hKey = (HKEY)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetSystemXboxLiveInfo");
      if ( ProcAddress )
      {
        memset_0(v19, 0, 0x48u);
        v5 = ((__int64 (__fastcall *)(__int64, _BYTE *))ProcAddress)(1, v19);
        String = v5;
        if ( v5 )
        {
          if ( v5 > 0 )
            String = (unsigned __int16)v5 | 0x80070000;
        }
        else
        {
          String = 0;
          *(_OWORD *)v21 = 0;
          v22 = 0;
          StringCchPrintfW(v21, 0x10u, L"%S", v20);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v16);
        }
      }
      else
      {
        String = -2147467263;
      }
    }
    else
    {
      String = UtilRegGetString(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\GameCore", L"SandboxId", (__int64)&v16, 0, 1);
    }
    Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hKey);
    goto LABEL_32;
  }
  pcbData = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pvData);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&pvData) )
    goto LABEL_12;
  v6 = hKey;
  hKey = 0;
  if ( v6 )
    RegCloseKey(v6);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\XboxLive", 0, 0x101u, &hKey)
    || (v7 = hKey, pcbData = 0, RegGetValueW(hKey, 0, L"Sandbox", 2u, 0, 0, &pcbData)) )
  {
LABEL_25:
    String = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(&v16, &pvData);
    goto LABEL_26;
  }
  v14 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v7, 0, L"Sandbox", 2u, 0, pvData, &pcbData);
    String = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        String = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_21;
    }
    v9 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
    if ( v9 > (v14 - (_BYTE *)pvData) >> 1 )
      __int2c();
    v14 = (char *)pvData + 2 * v9;
    *(_WORD *)v14 = 0;
    goto LABEL_25;
  }
LABEL_12:
  String = -2147024882;
LABEL_21:
  v17 = v16;
  *(_WORD *)v16 = 0;
LABEL_26:
  if ( pvData != &v15 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  if ( String < 0 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&v16);
    String = 0;
  }
LABEL_32:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
    a1,
    v16,
    (v17 - (_BYTE *)v16) >> 1);
  if ( v16 != &v18 )
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800e6260  mov     [rsp-8+arg_8], rbx
0x1800e6265  mov     [rsp-8+arg_10], rdi
0x1800e626a  push    rbp
0x1800e626b  lea     rbp, [rsp-10h]
0x1800e6270  sub     rsp, 110h
0x1800e6277  mov     rax, cs:__security_cookie
0x1800e627e  xor     rax, rsp
0x1800e6281  mov     [rbp+10h+var_10], rax
0x1800e6285  mov     rdi, rcx
0x1800e6288  lea     rcx, [rsp+110h+var_A0]
0x1800e628d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800e6292  nop
0x1800e6293  mov     [rsp+110h+var_D0], 0
0x1800e629b  xor     r8d, r8d
0x1800e629e  lea     rdx, [rsp+110h+var_D0]
0x1800e62a3  xor     ecx, ecx
0x1800e62a5  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800e62ab  cmp     [rsp+110h+var_D0], 5
0x1800e62b0  jnz     loc_1800E63A5
0x1800e62b6  xor     edx, edx; hFile
0x1800e62b8  mov     r8d, 800h; dwFlags
0x1800e62be  lea     rcx, aXboxlivetitlei; "XboxLiveTitleId.dll"
0x1800e62c5  call    cs:__imp_LoadLibraryExW
0x1800e62cb  mov     [rsp+110h+hKey], rax
0x1800e62d0  test    rax, rax
0x1800e62d3  jnz     short loc_1800E630D
0x1800e62d5  mov     byte ptr [rsp+110h+pcbData], 1; char
0x1800e62da  mov     byte ptr [rsp+110h+pvData], al; char
0x1800e62de  lea     rax, [rsp+110h+var_A0]
0x1800e62e3  mov     [rsp+110h+phkResult], rax; __int64
0x1800e62e8  lea     r9, aRetail; "RETAIL"
0x1800e62ef  lea     r8, aSandboxid; "SandboxId"
0x1800e62f6  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\GameCore"
0x1800e62fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e6304  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800e6309  mov     ebx, eax
0x1800e630b  jmp     short loc_1800E632A
0x1800e630d  lea     rdx, aGetsystemxboxl; "GetSystemXboxLiveInfo"
0x1800e6314  mov     rcx, rax; hModule
0x1800e6317  call    cs:__imp_GetProcAddress
0x1800e631d  mov     rbx, rax
0x1800e6320  test    rax, rax
0x1800e6323  jnz     short loc_1800E6339
0x1800e6325  mov     ebx, 80004001h
0x1800e632a  lea     rcx, [rsp+110h+hKey]
0x1800e632f  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x1800e6334  jmp     loc_1800E6576
0x1800e6339  xor     edx, edx; Val
0x1800e633b  lea     r8d, [rdx+48h]; Size
0x1800e633f  lea     rcx, [rbp+10h+var_80]; void *
0x1800e6343  call    memset_0
0x1800e6348  mov     r8d, 48h ; 'H'
0x1800e634e  lea     rdx, [rbp+10h+var_80]
0x1800e6352  lea     ecx, [r8-47h]
0x1800e6356  mov     rax, rbx
0x1800e6359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e635e  mov     ebx, eax
0x1800e6360  test    eax, eax
0x1800e6362  jz      short loc_1800E6371
0x1800e6364  jle     short loc_1800E632A
0x1800e6366  movzx   ebx, ax
0x1800e6369  or      ebx, 80070000h
0x1800e636f  jmp     short loc_1800E632A
0x1800e6371  xor     ebx, ebx
0x1800e6373  xorps   xmm0, xmm0
0x1800e6376  movups  xmmword ptr [rbp+10h+var_30], xmm0
0x1800e637a  movups  [rbp+10h+var_20], xmm0
0x1800e637e  lea     r9, [rbp+10h+var_48]
0x1800e6382  lea     r8, aS_9; "%S"
0x1800e6389  lea     edx, [rbx+10h]; unsigned __int64
0x1800e638c  lea     rcx, [rbp+10h+var_30]; wchar_t *
0x1800e6390  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800e6395  lea     rdx, [rbp+10h+var_30]
0x1800e6399  lea     rcx, [rsp+110h+var_A0]
0x1800e639e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e63a3  jmp     short loc_1800E632A
0x1800e63a5  mov     [rsp+110h+var_D0], 0
0x1800e63ad  mov     [rsp+110h+hKey], 0
0x1800e63b6  lea     rcx, [rsp+110h+var_C0]
0x1800e63bb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800e63c0  lea     rdx, aRetail; "RETAIL"
0x1800e63c7  lea     rcx, [rsp+110h+var_C0]
0x1800e63cc  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e63d1  test    al, al
0x1800e63d3  jnz     short loc_1800E63DF
0x1800e63d5  mov     ebx, 8007000Eh
0x1800e63da  jmp     loc_1800E64DB
0x1800e63df  mov     rcx, [rsp+110h+hKey]; hKey
0x1800e63e4  mov     [rsp+110h+hKey], 0
0x1800e63ed  test    rcx, rcx
0x1800e63f0  jz      short loc_1800E63F8
0x1800e63f2  call    cs:__imp_RegCloseKey
0x1800e63f8  lea     rax, [rsp+110h+hKey]
0x1800e63fd  mov     [rsp+110h+phkResult], rax; phkResult
0x1800e6402  mov     r9d, 101h; samDesired
0x1800e6408  xor     r8d, r8d; ulOptions
0x1800e640b  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\XboxLive"
0x1800e6412  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e6419  call    cs:__imp_RegOpenKeyExW
0x1800e641f  test    eax, eax
0x1800e6421  jnz     loc_1800E6523
0x1800e6427  mov     rbx, [rsp+110h+hKey]
0x1800e642c  mov     [rsp+110h+var_D0], eax
0x1800e6430  lea     rax, [rsp+110h+var_D0]
0x1800e6435  mov     [rsp+110h+pcbData], rax; pcbData
0x1800e643a  mov     [rsp+110h+pvData], 0; pvData
0x1800e6443  mov     [rsp+110h+phkResult], 0; pdwType
0x1800e644c  mov     r9d, 2; dwFlags
0x1800e6452  lea     r8, aSandbox; "Sandbox"
0x1800e6459  xor     edx, edx; lpSubKey
0x1800e645b  mov     rcx, rbx; hkey
0x1800e645e  call    cs:__imp_RegGetValueW
0x1800e6464  test    eax, eax
0x1800e6466  jnz     loc_1800E6523
0x1800e646c  mov     rcx, [rsp+110h+var_C0]
0x1800e6471  mov     [rsp+110h+var_B8], rcx
0x1800e6476  mov     [rcx], ax
0x1800e6479  mov     edx, [rsp+110h+var_D0]
0x1800e647d  shr     rdx, 1
0x1800e6480  inc     rdx
0x1800e6483  lea     rcx, [rsp+110h+var_C0]
0x1800e6488  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800e648d  test    al, al
0x1800e648f  jz      loc_1800E63D5
0x1800e6495  lea     rax, [rsp+110h+var_D0]
0x1800e649a  mov     [rsp+110h+pcbData], rax; pcbData
0x1800e649f  mov     rax, [rsp+110h+var_C0]
0x1800e64a4  mov     [rsp+110h+pvData], rax; pvData
0x1800e64a9  mov     [rsp+110h+phkResult], 0; pdwType
0x1800e64b2  mov     r9d, 2; dwFlags
0x1800e64b8  lea     r8, aSandbox; "Sandbox"
0x1800e64bf  xor     edx, edx; lpSubKey
0x1800e64c1  mov     rcx, rbx; hkey
0x1800e64c4  call    cs:__imp_RegGetValueW
0x1800e64ca  mov     ebx, eax
0x1800e64cc  test    eax, eax
0x1800e64ce  jz      short loc_1800E64EC
0x1800e64d0  jle     short loc_1800E64DB
0x1800e64d2  movzx   ebx, ax
0x1800e64d5  or      ebx, 80070000h
0x1800e64db  mov     rcx, [rsp+110h+var_A0]
0x1800e64e0  mov     [rsp+110h+var_98], rcx
0x1800e64e5  xor     eax, eax
0x1800e64e7  mov     [rcx], ax
0x1800e64ea  jmp     short loc_1800E6534
0x1800e64ec  mov     edx, [rsp+110h+var_D0]
0x1800e64f0  shr     rdx, 1; MaxCount
0x1800e64f3  mov     rcx, [rsp+110h+var_C0]; Source
0x1800e64f8  call    cs:__imp_wcsnlen
0x1800e64fe  mov     rcx, [rsp+110h+var_B8]
0x1800e6503  mov     rdx, [rsp+110h+var_C0]
0x1800e6508  sub     rcx, rdx
0x1800e650b  sar     rcx, 1
0x1800e650e  cmp     rax, rcx
0x1800e6511  jbe     short loc_1800E6515
0x1800e6513  int     2Ch; Windows NT - assertion failure
0x1800e6515  lea     rcx, [rdx+rax*2]
0x1800e6519  mov     [rsp+110h+var_B8], rcx
0x1800e651e  xor     eax, eax
0x1800e6520  mov     [rcx], ax
0x1800e6523  xor     ebx, ebx
0x1800e6525  lea     rdx, [rsp+110h+var_C0]
0x1800e652a  lea     rcx, [rsp+110h+var_A0]
0x1800e652f  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800e6534  lea     rax, [rsp+110h+var_B0]
0x1800e6539  mov     rcx, [rsp+110h+var_C0]; void *
0x1800e653e  cmp     rcx, rax
0x1800e6541  jz      short loc_1800E654F
0x1800e6543  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e654a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e654f  mov     rcx, [rsp+110h+hKey]; hKey
0x1800e6554  test    rcx, rcx
0x1800e6557  jz      short loc_1800E655F
0x1800e6559  call    cs:__imp_RegCloseKey
0x1800e655f  test    ebx, ebx
0x1800e6561  jns     short loc_1800E6576
0x1800e6563  lea     rdx, aRetail; "RETAIL"
0x1800e656a  lea     rcx, [rsp+110h+var_A0]
0x1800e656f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e6574  xor     ebx, ebx
0x1800e6576  mov     r8, [rsp+110h+var_98]
0x1800e657b  mov     rdx, [rsp+110h+var_A0]
0x1800e6580  sub     r8, rdx
0x1800e6583  sar     r8, 1
0x1800e6586  mov     rcx, rdi
0x1800e6589  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800e658e  nop
0x1800e658f  lea     rax, [rbp+10h+var_90]
0x1800e6593  mov     rcx, [rsp+110h+var_A0]; void *
0x1800e6598  cmp     rcx, rax
0x1800e659b  jz      short loc_1800E65A9
0x1800e659d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e65a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e65a9  mov     eax, ebx
0x1800e65ab  mov     rcx, [rbp+10h+var_10]
0x1800e65af  xor     rcx, rsp; StackCookie
0x1800e65b2  call    __security_check_cookie
0x1800e65b7  lea     r11, [rsp+110h+var_s0]
0x1800e65bf  mov     rbx, [r11+18h]
0x1800e65c3  mov     rdi, [r11+20h]
0x1800e65c7  mov     rsp, r11
0x1800e65ca  pop     rbp
0x1800e65cb  retn
```
