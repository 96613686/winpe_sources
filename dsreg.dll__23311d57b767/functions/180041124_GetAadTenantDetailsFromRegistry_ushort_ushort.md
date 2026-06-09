# GetAadTenantDetailsFromRegistry(ushort * *,ushort * *)

- ea: `0x180041124`
- end: `0x18004140f`
- name: `?GetAadTenantDetailsFromRegistry@@YAJPEAPEAG0@Z`
- size: `747`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d100`

## callees

- `0x180006750`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000ddf0`
- `0x180012948`
- `0x1800307c4`
- `0x180041124`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800411eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800411eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800413c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800413c5`

## string_xrefs

- `0x180041283`: `RegReadStringValue`
- `0x1800412d9`: `RegReadStringValue`
- `0x18004133e`: `CopyStringW`
- `0x180041381`: `CopyStringW`
- `0x180041205`: `RegOpenKeyExW`
- `0x180041231`: `RegOpenKeyExW`
- `0x18004116a`: `GetAadTenantDetailsFromRegistry`
- `0x180041184`: `GetAadTenantDetailsFromRegistry`
- `0x1800411a6`: `GetAadTenantDetailsFromRegistry`
- `0x18004121b`: `GetAadTenantDetailsFromRegistry`
- `0x18004123f`: `GetAadTenantDetailsFromRegistry`
- `0x18004128a`: `GetAadTenantDetailsFromRegistry`
- `0x1800412e0`: `GetAadTenantDetailsFromRegistry`
- `0x180041345`: `GetAadTenantDetailsFromRegistry`
- `0x180041394`: `GetAadTenantDetailsFromRegistry`
- `0x1800413e5`: `GetAadTenantDetailsFromRegistry`
- `0x180041222`: `%s: Cannot open AAD tenant info registry key "%s". RegOpenKeyExW failed with error code: 0x%08x.`
- `0x1800413a0`: `%s: Either tenant name or tenant ID is empty in the registry.`

## pseudocode

```c
__int64 __fastcall GetAadTenantDetailsFromRegistry(unsigned __int16 **a1, unsigned __int16 **a2)
{
  int v4; // edi
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r14
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rdx
  int v14; // eax
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *Source; // [rsp+80h] [rbp+50h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp+58h] BYREF

  hKey = 0;
  Source = 0;
  v4 = 0;
  v18 = 0;
  v5 = 0;
  v6 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetAadTenantDetailsFromRegistry", L"ppszTenantId");
    v8 = L"ppszTenantId";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetAadTenantDetailsFromRegistry", v8);
    goto LABEL_25;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetAadTenantDetailsFromRegistry", L"ppszTenantName");
    v8 = L"ppszTenantName";
    goto LABEL_3;
  }
  *a1 = 0;
  *a2 = 0;
  v7 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD", 0, 0x20019u, &hKey);
  v4 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
      Logger::WriteRegistryFailureEvent(
        v9,
        L"RegOpenKeyExW",
        L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD");
    Logger::TraceInformation(
      L"%s: Cannot open AAD tenant info registry key \"%s\". RegOpenKeyExW failed with error code: 0x%08x.",
      L"GetAadTenantDetailsFromRegistry",
      L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD",
      (unsigned int)v4);
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"GetAadTenantDetailsFromRegistry",
      L"RegOpenKeyExW",
      (unsigned int)v4);
  }
  else
  {
    v10 = RegReadStringValue(
            hKey,
            0,
            L"TenantId",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD",
            2u,
            &Source);
    v4 = v10;
    if ( v10 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"GetAadTenantDetailsFromRegistry",
        L"RegReadStringValue",
        v10);
      v5 = Source;
    }
    else
    {
      v11 = RegReadStringValue(
              hKey,
              0,
              L"TenantName",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ\\AAD",
              2u,
              &v18);
      v4 = v11;
      if ( v11 )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"GetAadTenantDetailsFromRegistry",
          L"RegReadStringValue",
          v11);
        v5 = Source;
        v6 = v18;
      }
      else
      {
        v6 = v18;
        v5 = Source;
        if ( v18 && Source )
        {
          v12 = -1;
          v13 = -1;
          do
            ++v13;
          while ( Source[v13] );
          v7 = CopyStringW(Source, v13, a1);
          if ( (v7 & 0x80000000) == 0 )
          {
            do
              ++v12;
            while ( v6[v12] );
            v14 = CopyStringW(v6, v12, a2);
            v7 = v14;
            if ( v14 < 0 )
              Logger::TraceError(
                L"%s: %s failed with error code: 0x%08x.",
                L"GetAadTenantDetailsFromRegistry",
                L"CopyStringW",
                (unsigned int)v14);
          }
          else
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"GetAadTenantDetailsFromRegistry",
              L"CopyStringW",
              v7);
          }
        }
        else
        {
          v7 = 1;
          Logger::TraceInformation(
            L"%s: Either tenant name or tenant ID is empty in the registry.",
            L"GetAadTenantDetailsFromRegistry");
        }
      }
    }
  }
LABEL_25:
  SafeFree(v5);
  SafeFree(v6);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 )
  {
    if ( v4 > 0 )
      v7 = (unsigned __int16)v4 | 0x80070000;
    else
      v7 = v4;
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"GetAadTenantDetailsFromRegistry", v7);
  return v7;
}

```

## disassembly

```asm
0x180041124  mov     [rsp-38h+arg_8], rbx
0x180041129  push    rbp
0x18004112a  push    rsi
0x18004112b  push    rdi
0x18004112c  push    r12
0x18004112e  push    r13
0x180041130  push    r14
0x180041132  push    r15
0x180041134  mov     rbp, rsp
0x180041137  sub     rsp, 30h
0x18004113b  xor     r15d, r15d
0x18004113e  mov     r13, rdx
0x180041141  mov     [rbp+hKey], r15
0x180041145  mov     r12, rcx
0x180041148  mov     [rbp+Source], r15
0x18004114c  mov     edi, r15d
0x18004114f  mov     [rbp+arg_18], r15
0x180041153  mov     esi, r15d
0x180041156  mov     r14d, r15d
0x180041159  test    rcx, rcx
0x18004115c  jnz     short loc_180041195
0x18004115e  lea     r8, aPpsztenantid; "ppszTenantId"
0x180041165  mov     ebx, 80070057h
0x18004116a  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x180041171  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180041178  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004117d  lea     rdx, aPpsztenantid; "ppszTenantId"
0x180041184  lea     rcx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18004118b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180041190  jmp     loc_1800413AC
0x180041195  test    r13, r13
0x180041198  jnz     short loc_1800411C2
0x18004119a  lea     r8, aPpsztenantname; "ppszTenantName"
0x1800411a1  mov     ebx, 80070057h
0x1800411a6  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x1800411ad  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800411b4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800411b9  lea     rdx, aPpsztenantname; "ppszTenantName"
0x1800411c0  jmp     short loc_180041184
0x1800411c2  mov     [rcx], r15
0x1800411c5  lea     rax, [rbp+hKey]
0x1800411c9  mov     [rdx], r15
0x1800411cc  mov     r9d, 20019h; samDesired
0x1800411d2  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800411d9  mov     [rsp+30h+phkResult], rax; phkResult
0x1800411de  xor     r8d, r8d; ulOptions
0x1800411e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800411e8  mov     ebx, r15d
0x1800411eb  call    cs:__imp_RegOpenKeyExW
0x1800411f1  mov     edi, eax
0x1800411f3  test    eax, eax
0x1800411f5  jz      short loc_180041250
0x1800411f7  cmp     eax, 2
0x1800411fa  jz      short loc_180041211
0x1800411fc  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180041203  mov     ecx, eax; unsigned int
0x180041205  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18004120c  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180041211  mov     r9d, edi
0x180041214  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18004121b  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x180041222  lea     rcx, aSCannotOpenAad; "%s: Cannot open AAD tenant info registr"...
0x180041229  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18004122e  mov     r9d, edi
0x180041231  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x180041238  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18004123f  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x180041246  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004124b  jmp     loc_1800413AC
0x180041250  mov     rcx, [rbp+hKey]; hkey
0x180041254  lea     rax, [rbp+Source]
0x180041258  mov     [rsp+30h+var_8], rax; unsigned __int16 **
0x18004125d  lea     r9, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180041264  lea     r8, aTenantid_0; "TenantId"
0x18004126b  mov     dword ptr [rsp+30h+phkResult], 2; dwFlags
0x180041273  xor     edx, edx; lpSubKey
0x180041275  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18004127a  mov     edi, eax
0x18004127c  test    eax, eax
0x18004127e  jz      short loc_1800412A6
0x180041280  mov     r9d, eax
0x180041283  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18004128a  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x180041291  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180041298  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004129d  mov     rsi, [rbp+Source]
0x1800412a1  jmp     loc_1800413AC
0x1800412a6  mov     rcx, [rbp+hKey]; hkey
0x1800412aa  lea     rax, [rbp+arg_18]
0x1800412ae  mov     [rsp+30h+var_8], rax; unsigned __int16 **
0x1800412b3  lea     r9, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800412ba  lea     r8, aTenantname; "TenantName"
0x1800412c1  mov     dword ptr [rsp+30h+phkResult], 2; dwFlags
0x1800412c9  xor     edx, edx; lpSubKey
0x1800412cb  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800412d0  mov     edi, eax
0x1800412d2  test    eax, eax
0x1800412d4  jz      short loc_180041300
0x1800412d6  mov     r9d, eax
0x1800412d9  lea     r8, aRegreadstringv; "RegReadStringValue"
0x1800412e0  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x1800412e7  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800412ee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800412f3  mov     rsi, [rbp+Source]
0x1800412f7  mov     r14, [rbp+arg_18]
0x1800412fb  jmp     loc_1800413AC
0x180041300  mov     r14, [rbp+arg_18]
0x180041304  mov     rsi, [rbp+Source]
0x180041308  test    r14, r14
0x18004130b  jz      loc_180041394
0x180041311  test    rsi, rsi
0x180041314  jz      short loc_180041394
0x180041316  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004131a  mov     rdx, r15
0x18004131d  xor     eax, eax
0x18004131f  inc     rdx; unsigned __int64
0x180041322  cmp     [rsi+rdx*2], ax
0x180041326  jnz     short loc_18004131F
0x180041328  mov     r8, r12; unsigned __int16 **
0x18004132b  mov     rcx, rsi; Source
0x18004132e  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x180041333  mov     ebx, eax
0x180041335  xor     eax, eax
0x180041337  test    ebx, ebx
0x180041339  jns     short loc_18004135D
0x18004133b  mov     r9d, ebx
0x18004133e  lea     r8, aCopystringw; "CopyStringW"
0x180041345  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18004134c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180041353  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180041358  xor     r15d, r15d
0x18004135b  jmp     short loc_1800413AC
0x18004135d  inc     r15
0x180041360  cmp     [r14+r15*2], ax
0x180041365  jnz     short loc_18004135D
0x180041367  mov     r8, r13; unsigned __int16 **
0x18004136a  mov     rdx, r15; unsigned __int64
0x18004136d  mov     rcx, r14; Source
0x180041370  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x180041375  xor     r15d, r15d
0x180041378  mov     ebx, eax
0x18004137a  test    eax, eax
0x18004137c  jns     short loc_1800413AC
0x18004137e  mov     r9d, eax
0x180041381  lea     r8, aCopystringw; "CopyStringW"
0x180041388  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004138f  jmp     loc_18004123F
0x180041394  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x18004139b  mov     ebx, 1
0x1800413a0  lea     rcx, aSEitherTenantN; "%s: Either tenant name or tenant ID is "...
0x1800413a7  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800413ac  mov     rcx, rsi; lpMem
0x1800413af  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800413b4  mov     rcx, r14; lpMem
0x1800413b7  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800413bc  mov     rcx, [rbp+hKey]; hKey
0x1800413c0  test    rcx, rcx
0x1800413c3  jz      short loc_1800413CF
0x1800413c5  call    cs:__imp_RegCloseKey
0x1800413cb  mov     [rbp+hKey], r15
0x1800413cf  test    edi, edi
0x1800413d1  jz      short loc_1800413E2
0x1800413d3  jg      short loc_1800413D9
0x1800413d5  mov     ebx, edi
0x1800413d7  jmp     short loc_1800413E2
0x1800413d9  movzx   ebx, di
0x1800413dc  or      ebx, 80070000h
0x1800413e2  mov     r8d, ebx
0x1800413e5  lea     rdx, aGetaadtenantde; "GetAadTenantDetailsFromRegistry"
0x1800413ec  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800413f3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800413f8  mov     eax, ebx
0x1800413fa  mov     rbx, [rsp+30h+arg_8]
0x1800413ff  add     rsp, 30h
0x180041403  pop     r15
0x180041405  pop     r14
0x180041407  pop     r13
0x180041409  pop     r12
0x18004140b  pop     rdi
0x18004140c  pop     rsi
0x18004140d  pop     rbp
0x18004140e  retn
```
