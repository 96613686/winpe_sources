# EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)

- ea: `0x180074034`
- end: `0x1800741c6`
- name: `?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z`
- size: `402`
- prototype: `__int64 __fastcall(unsigned int, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800752d8`

## callees

- `0x180017988`
- `0x1800179ac`
- `0x18003eb5c`
- `0x180040b60`
- `0x180074034`
- `0x180074540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800740b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800740b1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007418a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007418a`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800740a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180074146`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800740a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180074146`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetFeatureStatusCache(unsigned int a1, bool *a2, bool *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int ProcessEnvName; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  DWORD EnvironmentVariableW; // eax
  __int64 v11; // rdi
  signed int LastError; // eax
  const WCHAR *v13; // rbx
  const char *v14; // r9
  bool v15; // al
  int lpString2; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR lpBuffer; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR lpName; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 )
  {
    if ( !a3 )
    {
      v5 = 57;
      goto LABEL_3;
    }
    lpName = 0;
    ProcessEnvName = EnterpriseFeatureControl::GetProcessEnvName(a1, (unsigned __int16 **)&lpName);
    v6 = ProcessEnvName;
    if ( ProcessEnvName < 0 )
    {
      v8 = (unsigned int)ProcessEnvName;
      v9 = 60;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)v8,
        lpString2);
      goto LABEL_25;
    }
    EnvironmentVariableW = GetEnvironmentVariableW(lpName, 0, 0);
    v11 = EnvironmentVariableW;
    if ( EnvironmentVariableW )
      goto LABEL_16;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
    {
LABEL_16:
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpBuffer,
        0,
        v11);
      v13 = lpBuffer;
      if ( lpBuffer )
      {
        if ( GetEnvironmentVariableW(lpName, lpBuffer, v11) )
        {
          if ( v13 )
            v15 = CompareStringW(0x7Fu, 0, v13, -1, L"1", -1) == 2;
          else
            v15 = 0;
          *a3 = v15;
          *a2 = 1;
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
          v6 = 0;
          goto LABEL_25;
        }
        v6 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x48,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               v14);
      }
      else
      {
        v6 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
          (const char *)0x8007000ELL,
          lpString2);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
    }
    else
    {
      if ( v6 != -2147024693 )
      {
        v8 = v6;
        v9 = 65;
        goto LABEL_15;
      }
      v6 = -2147024693;
    }
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpName);
    return v6;
  }
  v5 = 56;
LABEL_3:
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)0x80004003LL,
    lpString2);
  return v6;
}

```

## disassembly

```asm
0x180074034  mov     [rsp+arg_0], rbx
0x180074039  push    rsi
0x18007403a  push    rdi
0x18007403b  push    r14
0x18007403d  sub     rsp, 30h
0x180074041  mov     rsi, r8
0x180074044  mov     r14, rdx
0x180074047  test    rdx, rdx
0x18007404a  jnz     short loc_18007406E
0x18007404c  lea     edx, [r14+38h]; void *
0x180074050  mov     rcx, [rsp+48h]; this
0x180074055  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18007405c  mov     ebx, 80004003h
0x180074061  mov     r9d, ebx; char *
0x180074064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074069  jmp     loc_1800741B6
0x18007406e  test    rsi, rsi
0x180074071  jnz     short loc_180074078
0x180074073  lea     edx, [rsi+39h]
0x180074076  jmp     short loc_180074050
0x180074078  lea     rdx, [rsp+48h+lpName]; unsigned __int16 **
0x18007407d  mov     [rsp+48h+lpName], 0
0x180074086  call    ?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z; EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)
0x18007408b  mov     ebx, eax
0x18007408d  test    eax, eax
0x18007408f  jns     short loc_18007409B
0x180074091  mov     r9d, eax
0x180074094  mov     edx, 3Ch ; '<'
0x180074099  jmp     short loc_1800740E2
0x18007409b  mov     rcx, [rsp+48h+lpName]; lpName
0x1800740a0  xor     r8d, r8d; nSize
0x1800740a3  xor     edx, edx; lpBuffer
0x1800740a5  call    cs:__imp_GetEnvironmentVariableW
0x1800740ab  mov     edi, eax
0x1800740ad  test    eax, eax
0x1800740af  jnz     short loc_1800740F8
0x1800740b1  call    cs:__imp_GetLastError
0x1800740b7  mov     ebx, eax
0x1800740b9  test    eax, eax
0x1800740bb  jle     short loc_1800740C6
0x1800740bd  movzx   ebx, ax
0x1800740c0  or      ebx, 80070000h
0x1800740c6  test    ebx, ebx
0x1800740c8  jns     short loc_1800740F8
0x1800740ca  mov     eax, 800700CBh
0x1800740cf  cmp     ebx, eax
0x1800740d1  jnz     short loc_1800740DA
0x1800740d3  mov     ebx, eax
0x1800740d5  jmp     loc_1800741AC
0x1800740da  mov     r9d, ebx; char *
0x1800740dd  mov     edx, 41h ; 'A'; void *
0x1800740e2  mov     rcx, [rsp+48h]; this
0x1800740e7  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800740ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800740f3  jmp     loc_1800741AC
0x1800740f8  mov     r8, rdi
0x1800740fb  lea     rcx, [rsp+48h+lpBuffer]
0x180074100  xor     edx, edx
0x180074102  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180074107  mov     rbx, [rsp+48h+lpBuffer]
0x18007410c  test    rbx, rbx
0x18007410f  jnz     short loc_18007413B
0x180074111  mov     rcx, [rsp+48h]; this
0x180074116  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18007411d  mov     ebx, 8007000Eh
0x180074122  mov     edx, 45h ; 'E'; void *
0x180074127  mov     r9d, ebx; char *
0x18007412a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007412f  lea     rcx, [rsp+48h+lpBuffer]
0x180074134  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180074139  jmp     short loc_1800741AC
0x18007413b  mov     rcx, [rsp+48h+lpName]; lpName
0x180074140  mov     r8d, edi; nSize
0x180074143  mov     rdx, rbx; lpBuffer
0x180074146  call    cs:__imp_GetEnvironmentVariableW
0x18007414c  test    eax, eax
0x18007414e  jnz     short loc_180074168
0x180074150  mov     rcx, [rsp+48h]; this
0x180074155  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18007415c  lea     edx, [rax+48h]; void *
0x18007415f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180074164  mov     ebx, eax
0x180074166  jmp     short loc_18007412F
0x180074168  test    rbx, rbx
0x18007416b  jz      short loc_180074198
0x18007416d  xor     edx, edx; dwCmpFlags
0x18007416f  lea     rax, a1; "1"
0x180074176  or      r9d, 0FFFFFFFFh; cchCount1
0x18007417a  mov     r8, rbx; lpString1
0x18007417d  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180074182  mov     [rsp+48h+lpString2], rax; lpString2
0x180074187  lea     ecx, [rdx+7Fh]; Locale
0x18007418a  call    cs:__imp_CompareStringW
0x180074190  cmp     eax, 2
0x180074193  setz    al
0x180074196  jmp     short loc_18007419A
0x180074198  xor     al, al
0x18007419a  lea     rcx, [rsp+48h+lpBuffer]
0x18007419f  mov     [rsi], al
0x1800741a1  mov     byte ptr [r14], 1
0x1800741a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800741aa  xor     ebx, ebx
0x1800741ac  lea     rcx, [rsp+48h+lpName]
0x1800741b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800741b6  mov     eax, ebx
0x1800741b8  mov     rbx, [rsp+48h+arg_0]
0x1800741bd  add     rsp, 30h
0x1800741c1  pop     r14
0x1800741c3  pop     rdi
0x1800741c4  pop     rsi
0x1800741c5  retn
```
