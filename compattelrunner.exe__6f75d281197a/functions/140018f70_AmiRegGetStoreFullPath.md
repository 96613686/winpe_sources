# AmiRegGetStoreFullPath

- ea: `0x140018f70`
- end: `0x140019252`
- name: `AmiRegGetStoreFullPath`
- size: `738`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140019258`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400093e8`
- `0x1400151b0`
- `0x140018f70`
- `0x14001ac30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001917a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1400191a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001917a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1400191a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400191c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400191c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140019075`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140019075`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140019089`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140019089`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400190ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400190ca`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1400190a9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1400190a9`

## string_xrefs

- `0x140018ff0`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x14001904b`: `AmiOverridePath`
- `0x140019094`: `AmiOverridePath`
- `0x140019025`: `AmiRegGetStoreFullPath`
- `0x14001911e`: `AmiRegGetStoreFullPath`
- `0x1400190dd`: `AppCompat\Programs`
- `0x140019198`: `Amcache.hve`
- `0x14001913d`: `Amcache`
- `0x1400191ce`: `GetSystemWindowsDirectory [%d]`
- `0x140018ffc`: `AppCompatFlags`

## pseudocode

```c
__int64 __fastcall AmiRegGetStoreFullPath(char *a1)
{
  signed int PersistedLocation; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rax
  WCHAR *v9; // rcx
  char *v10; // rcx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v17[264]; // [rsp+680h] [rbp+580h] BYREF

  memset_0(SubKey, 0, 0x20Au);
  memset_0(v17, 0, 0x20Au);
  pcbData[0] = 0;
  Buffer[0] = 0;
  memset_0(a1, 0, 0x208u);
  PersistedLocation = AmiUtilityGetPersistedLocation(
                        (unsigned int)SubKey,
                        261,
                        (unsigned int)L"AppCompatFlags",
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                        1);
  if ( PersistedLocation >= 0 )
  {
    pcbData[0] = 520;
    v6 = 260;
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiOverridePath", 0x20000002u, 0, FileName, pcbData)
      || GetFileAttributesW(FileName) != -1 )
    {
      if ( FileName[0] )
        goto LABEL_20;
    }
    else
    {
      RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiOverridePath");
      FileName[0] = 0;
    }
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      PersistedLocation = GetLastError();
      v4 = "GetSystemWindowsDirectory [%d]";
      v5 = 353;
      v3 = PersistedLocation;
      goto LABEL_3;
    }
    if ( (int)StringCchPrintfW(v17, 0x105u, L"%s\\%s", Buffer, L"AppCompat\\Programs") < 0 )
    {
      v7 = 367;
      goto LABEL_11;
    }
    PersistedLocation = AmiUtilityGetPersistedLocation(
                          (unsigned int)FileName,
                          260,
                          (unsigned int)L"Amcache",
                          (unsigned int)v17,
                          0);
    if ( PersistedLocation < 0 )
    {
      v3 = 111;
      v4 = "AmiUtilityGetPersistedLocation failed [%#x]";
      v5 = 378;
      goto LABEL_3;
    }
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L"\\") )
    {
      v3 = 1287;
      AslLogCallPrintf(1, "AmiRegGetStoreFullPath", 385, "wcscpy_s failed");
      return v3;
    }
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L"Amcache.hve") )
    {
      v3 = 1287;
      AslLogCallPrintf(1, "AmiRegGetStoreFullPath", 392, "wcscpy_s failed");
      return v3;
    }
LABEL_20:
    v8 = 2147483646;
    v9 = FileName;
    do
    {
      if ( !v8 )
        break;
      if ( !*v9 )
        break;
      *(_WORD *)a1 = *v9++;
      a1 += 2;
      --v8;
      --v6;
    }
    while ( v6 );
    v10 = a1 - 2;
    if ( v6 )
      v10 = a1;
    *(_WORD *)v10 = 0;
    if ( v6 )
      return 0;
    v7 = 406;
LABEL_11:
    v3 = 111;
    AslLogCallPrintf(1, "AmiRegGetStoreFullPath", v7, "Buffer overflow");
    return v3;
  }
  v3 = 1287;
  v4 = "AmiUtilityGetPersistedLocation [%#x]";
  v5 = 311;
LABEL_3:
  LODWORD(pdwType) = PersistedLocation;
  AslLogCallPrintf(1, "AmiRegGetStoreFullPath", v5, v4, pdwType);
  return v3;
}

```

## disassembly

```asm
0x140018f70  mov     [rsp-8+arg_8], rbx
0x140018f75  mov     [rsp-8+arg_10], rsi
0x140018f7a  push    rbp
0x140018f7b  push    rdi
0x140018f7c  push    r14
0x140018f7e  lea     rbp, [rsp-7A0h]
0x140018f86  sub     rsp, 8A0h
0x140018f8d  mov     rax, cs:__security_cookie
0x140018f94  xor     rax, rsp
0x140018f97  mov     [rbp+7B0h+var_20], rax
0x140018f9e  mov     rdi, rcx
0x140018fa1  mov     ebx, 20Ah
0x140018fa6  mov     r8d, ebx; Size
0x140018fa9  lea     rcx, [rbp+7B0h+SubKey]; void *
0x140018fb0  xor     edx, edx; Val
0x140018fb2  call    memset_0
0x140018fb7  mov     r8d, ebx; Size
0x140018fba  lea     rcx, [rbp+7B0h+var_230]; void *
0x140018fc1  xor     edx, edx; Val
0x140018fc3  call    memset_0
0x140018fc8  xor     esi, esi
0x140018fca  mov     ebx, 208h
0x140018fcf  mov     r8d, ebx; Size
0x140018fd2  mov     [rsp+8B0h+var_870], esi
0x140018fd6  xor     edx, edx; Val
0x140018fd8  mov     [rbp+7B0h+Buffer], si
0x140018fdf  mov     rcx, rdi; void *
0x140018fe2  call    memset_0
0x140018fe7  lea     r14d, [rsi+1]
0x140018feb  mov     edx, 105h
0x140018ff0  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140018ff7  mov     dword ptr [rsp+8B0h+pdwType], r14d
0x140018ffc  lea     r8, aAppcompatflags; "AppCompatFlags"
0x140019003  lea     rcx, [rbp+7B0h+SubKey]
0x14001900a  call    AmiUtilityGetPersistedLocation
0x14001900f  test    eax, eax
0x140019011  jns     short loc_14001903D
0x140019013  mov     ebx, 507h
0x140019018  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x14001901f  mov     r8d, 137h
0x140019025  lea     rdx, aAmireggetstore; "AmiRegGetStoreFullPath"
0x14001902c  mov     dword ptr [rsp+8B0h+pdwType], eax
0x140019030  mov     ecx, r14d
0x140019033  call    AslLogCallPrintf
0x140019038  jmp     loc_140019229
0x14001903d  lea     rax, [rsp+8B0h+var_870]
0x140019042  mov     [rsp+8B0h+var_870], ebx
0x140019046  mov     [rsp+8B0h+pcbData], rax; pcbData
0x14001904b  lea     r8, ValueName; "AmiOverridePath"
0x140019052  lea     rax, [rsp+8B0h+FileName]
0x140019057  mov     r9d, 20000002h; dwFlags
0x14001905d  mov     [rsp+8B0h+pvData], rax; pvData
0x140019062  lea     rdx, [rbp+7B0h+SubKey]; lpSubKey
0x140019069  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140019070  mov     [rsp+8B0h+pdwType], rsi; pdwType
0x140019075  call    cs:__imp_RegGetValueW
0x14001907b  mov     ebx, 104h
0x140019080  test    eax, eax
0x140019082  jnz     short loc_1400190B6
0x140019084  lea     rcx, [rsp+8B0h+FileName]; lpFileName
0x140019089  call    cs:__imp_GetFileAttributesW
0x14001908f  cmp     eax, 0FFFFFFFFh
0x140019092  jnz     short loc_1400190B6
0x140019094  lea     r8, ValueName; "AmiOverridePath"
0x14001909b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400190a2  lea     rdx, [rbp+7B0h+SubKey]; lpSubKey
0x1400190a9  call    cs:__imp_RegDeleteKeyValueW
0x1400190af  mov     [rsp+8B0h+FileName], si
0x1400190b4  jmp     short loc_1400190C1
0x1400190b6  cmp     [rsp+8B0h+FileName], si
0x1400190bb  jnz     loc_1400191E2
0x1400190c1  mov     edx, ebx; uSize
0x1400190c3  lea     rcx, [rbp+7B0h+Buffer]; lpBuffer
0x1400190ca  call    cs:__imp_GetSystemWindowsDirectoryW
0x1400190d0  dec     eax
0x1400190d2  cmp     eax, 103h
0x1400190d7  ja      loc_1400191C8
0x1400190dd  lea     rax, aAppcompatProgr_0; "AppCompat\\Programs"
0x1400190e4  mov     edx, 105h; unsigned __int64
0x1400190e9  lea     r9, [rbp+7B0h+Buffer]
0x1400190f0  mov     [rsp+8B0h+pdwType], rax
0x1400190f5  lea     r8, aSS_1; "%s\\%s"
0x1400190fc  lea     rcx, [rbp+7B0h+var_230]; unsigned __int16 *
0x140019103  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140019108  test    eax, eax
0x14001910a  jns     short loc_140019132
0x14001910c  mov     r8d, 16Fh
0x140019112  lea     r9, aBufferOverflow; "Buffer overflow"
0x140019119  mov     ebx, 6Fh ; 'o'
0x14001911e  lea     rdx, aAmireggetstore; "AmiRegGetStoreFullPath"
0x140019125  mov     ecx, r14d
0x140019128  call    AslLogCallPrintf
0x14001912d  jmp     loc_140019229
0x140019132  lea     r9, [rbp+7B0h+var_230]
0x140019139  mov     dword ptr [rsp+8B0h+pdwType], esi
0x14001913d  lea     r8, aAmcache; "Amcache"
0x140019144  mov     edx, ebx
0x140019146  lea     rcx, [rsp+8B0h+FileName]
0x14001914b  call    AmiUtilityGetPersistedLocation
0x140019150  test    eax, eax
0x140019152  jns     short loc_14001916B
0x140019154  mov     ebx, 6Fh ; 'o'
0x140019159  lea     r9, aAmiutilitygetp_0; "AmiUtilityGetPersistedLocation failed ["...
0x140019160  mov     r8d, 17Ah
0x140019166  jmp     loc_140019025
0x14001916b  lea     r8, Source; "\\"
0x140019172  mov     rdx, rbx
0x140019175  lea     rcx, [rsp+8B0h+FileName]
0x14001917a  call    cs:__imp__o_wcscat_s
0x140019180  test    eax, eax
0x140019182  jz      short loc_140019198
0x140019184  mov     ebx, 507h
0x140019189  lea     r9, aWcscpySFailed; "wcscpy_s failed"
0x140019190  mov     r8d, 181h
0x140019196  jmp     short loc_14001911E
0x140019198  lea     r8, aAmcacheHve; "Amcache.hve"
0x14001919f  mov     rdx, rbx
0x1400191a2  lea     rcx, [rsp+8B0h+FileName]
0x1400191a7  call    cs:__imp__o_wcscat_s
0x1400191ad  test    eax, eax
0x1400191af  jz      short loc_1400191E2
0x1400191b1  mov     ebx, 507h
0x1400191b6  lea     r9, aWcscpySFailed; "wcscpy_s failed"
0x1400191bd  mov     r8d, 188h
0x1400191c3  jmp     loc_14001911E
0x1400191c8  call    cs:__imp_GetLastError
0x1400191ce  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x1400191d5  mov     r8d, 161h
0x1400191db  mov     ebx, eax
0x1400191dd  jmp     loc_140019025
0x1400191e2  mov     eax, 7FFFFFFEh
0x1400191e7  lea     rcx, [rsp+8B0h+FileName]
0x1400191ec  test    rax, rax
0x1400191ef  jz      short loc_14001920C
0x1400191f1  movzx   edx, word ptr [rcx]
0x1400191f4  test    dx, dx
0x1400191f7  jz      short loc_14001920C
0x1400191f9  mov     [rdi], dx
0x1400191fc  add     rcx, 2
0x140019200  add     rdi, 2
0x140019204  sub     rax, r14
0x140019207  sub     rbx, r14
0x14001920a  jnz     short loc_1400191EC
0x14001920c  test    rbx, rbx
0x14001920f  lea     rcx, [rdi-2]
0x140019213  cmovnz  rcx, rdi
0x140019217  mov     [rcx], si
0x14001921a  jnz     short loc_140019227
0x14001921c  mov     r8d, 196h
0x140019222  jmp     loc_140019112
0x140019227  mov     ebx, esi
0x140019229  mov     eax, ebx
0x14001922b  mov     rcx, [rbp+7B0h+var_20]
0x140019232  xor     rcx, rsp; StackCookie
0x140019235  call    __security_check_cookie
0x14001923a  lea     r11, [rsp+8B0h+var_10]
0x140019242  mov     rbx, [r11+28h]
0x140019246  mov     rsi, [r11+30h]
0x14001924a  mov     rsp, r11
0x14001924d  pop     r14
0x14001924f  pop     rdi
0x140019250  pop     rbp
0x140019251  retn
```
