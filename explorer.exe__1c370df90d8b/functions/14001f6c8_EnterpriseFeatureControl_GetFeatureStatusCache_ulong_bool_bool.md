# EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)

- ea: `0x14001f6c8`
- end: `0x14001f8ca`
- name: `?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z`
- size: `514`
- prototype: `__int64 __fastcall(unsigned int, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f554`

## callees

- `0x14001f6c8`
- `0x14001fb80`
- `0x140020434`
- `0x1400954e0`
- `0x1400959e4`
- `0x1400987b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f7a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001f720`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001f720`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001f883`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001f883`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001f799`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001f834`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001f799`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001f834`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetFeatureStatusCache(int a1, bool *a2, bool *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  DWORD CurrentProcessId; // eax
  int v10; // eax
  WCHAR *v11; // rbx
  DWORD EnvironmentVariableW; // eax
  __int64 v13; // rdx
  __int64 v14; // rsi
  signed int LastError; // eax
  unsigned int v16; // edi
  unsigned int v17; // esi
  __int64 v18; // rdx
  WCHAR *v19; // rdi
  const char *v20; // r9
  bool v21; // al
  int lpString2; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCWSTR lpName; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v6 = 56;
LABEL_3:
    v7 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v7,
      lpString2);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 57;
    goto LABEL_3;
  }
  lpName = 0;
  CurrentProcessId = GetCurrentProcessId();
  v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpName,
          L"EFC_%lu_%lu",
          CurrentProcessId,
          __ROR4__(_byteswap_ulong(a1 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)(unsigned int)v10,
      lpString2);
    if ( lpName )
      MemoryFree((void *)lpName);
    v6 = 60;
    goto LABEL_4;
  }
  v11 = (WCHAR *)lpName;
  EnvironmentVariableW = GetEnvironmentVariableW(lpName, 0, 0);
  v14 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (v16 & 0x80000000) != 0 )
    {
      v17 = -2147024693;
      if ( v16 == -2147024693 )
      {
LABEL_16:
        if ( v11 )
          MemoryFree(v11);
        return v17;
      }
      v18 = 65;
      goto LABEL_20;
    }
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    v13,
    v14);
  v19 = (WCHAR *)lpName;
  if ( !lpName )
  {
    v16 = -2147024882;
    v18 = 69;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v16,
      lpString2);
    if ( v11 )
      MemoryFree(v11);
    return v16;
  }
  if ( !GetEnvironmentVariableW(v11, (LPWSTR)lpName, v14) )
  {
    v17 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
            v20);
    MemoryFree(v19);
    goto LABEL_16;
  }
  if ( v19 )
    v21 = CompareStringW(0x7Fu, 0, v19, -1, L"1", -1) == 2;
  else
    v21 = 0;
  *a3 = v21;
  *a2 = 1;
  if ( v19 )
    MemoryFree(v19);
  if ( v11 )
    MemoryFree(v11);
  return 0;
}

```

## disassembly

```asm
0x14001f6c8  mov     [rsp+arg_0], rbx
0x14001f6cd  mov     [rsp+arg_10], rsi
0x14001f6d2  push    rdi
0x14001f6d3  push    r14
0x14001f6d5  push    r15
0x14001f6d7  sub     rsp, 30h
0x14001f6db  mov     r14, r8
0x14001f6de  mov     r15, rdx
0x14001f6e1  mov     ebx, ecx
0x14001f6e3  test    rdx, rdx
0x14001f6e6  jnz     short loc_14001F70C
0x14001f6e8  lea     edx, [r15+38h]; void *
0x14001f6ec  mov     ebx, 80004003h
0x14001f6f1  mov     rcx, [rsp+48h]; this
0x14001f6f6  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x14001f6fd  mov     r9d, ebx; char *
0x14001f700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f705  mov     eax, ebx
0x14001f707  jmp     loc_14001F8B6
0x14001f70c  test    r14, r14
0x14001f70f  jnz     short loc_14001F717
0x14001f711  lea     edx, [r14+39h]
0x14001f715  jmp     short loc_14001F6EC
0x14001f717  mov     [rsp+48h+lpName], 0
0x14001f720  call    cs:__imp_GetCurrentProcessId
0x14001f726  xor     ebx, 74161A4Eh
0x14001f72c  lea     rdx, aEfcLuLu; "EFC_%lu_%lu"
0x14001f733  bswap   ebx
0x14001f735  xor     ebx, 8FB23D4Fh
0x14001f73b  lea     rcx, [rsp+48h+lpName]
0x14001f740  ror     ebx, 0FFh
0x14001f743  mov     r8d, eax
0x14001f746  xor     ebx, 833EA8FFh
0x14001f74c  mov     r9d, ebx
0x14001f74f  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x14001f754  mov     ebx, eax
0x14001f756  test    eax, eax
0x14001f758  jns     short loc_14001F78C
0x14001f75a  mov     rcx, [rsp+48h]; this
0x14001f75f  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x14001f766  mov     r9d, eax; char *
0x14001f769  mov     edx, 26h ; '&'; void *
0x14001f76e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f773  mov     rcx, [rsp+48h+lpName]; void *
0x14001f778  test    rcx, rcx
0x14001f77b  jz      short loc_14001F782
0x14001f77d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x14001f782  mov     edx, 3Ch ; '<'
0x14001f787  jmp     loc_14001F6F1
0x14001f78c  mov     rbx, [rsp+48h+lpName]
0x14001f791  xor     r8d, r8d; nSize
0x14001f794  mov     rcx, rbx; lpName
0x14001f797  xor     edx, edx; lpBuffer
0x14001f799  call    cs:__imp_GetEnvironmentVariableW
0x14001f79f  mov     esi, eax
0x14001f7a1  test    eax, eax
0x14001f7a3  jnz     short loc_14001F808
0x14001f7a5  call    cs:__imp_GetLastError
0x14001f7ab  mov     edi, eax
0x14001f7ad  test    eax, eax
0x14001f7af  jle     short loc_14001F7BA
0x14001f7b1  movzx   edi, ax
0x14001f7b4  or      edi, 80070000h
0x14001f7ba  test    edi, edi
0x14001f7bc  jns     short loc_14001F808
0x14001f7be  mov     esi, 800700CBh
0x14001f7c3  cmp     edi, esi
0x14001f7c5  jnz     short loc_14001F7DB
0x14001f7c7  test    rbx, rbx
0x14001f7ca  jz      short loc_14001F7D4
0x14001f7cc  mov     rcx, rbx; void *
0x14001f7cf  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x14001f7d4  mov     eax, esi
0x14001f7d6  jmp     loc_14001F8B6
0x14001f7db  mov     edx, 41h ; 'A'; void *
0x14001f7e0  mov     rcx, [rsp+48h]; this
0x14001f7e5  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x14001f7ec  mov     r9d, edi; char *
0x14001f7ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f7f4  test    rbx, rbx
0x14001f7f7  jz      short loc_14001F801
0x14001f7f9  mov     rcx, rbx; void *
0x14001f7fc  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x14001f801  mov     eax, edi
0x14001f803  jmp     loc_14001F8B6
0x14001f808  mov     r8, rsi
0x14001f80b  lea     rcx, [rsp+48h+lpName]
0x14001f810  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14001f815  mov     rdi, [rsp+48h+lpName]
0x14001f81a  test    rdi, rdi
0x14001f81d  jnz     short loc_14001F82B
0x14001f81f  mov     edi, 8007000Eh
0x14001f824  mov     edx, 45h ; 'E'
0x14001f829  jmp     short loc_14001F7E0
0x14001f82b  mov     r8d, esi; nSize
0x14001f82e  mov     rdx, rdi; lpBuffer
0x14001f831  mov     rcx, rbx; lpName
0x14001f834  call    cs:__imp_GetEnvironmentVariableW
0x14001f83a  test    eax, eax
0x14001f83c  jnz     short loc_14001F861
0x14001f83e  mov     rcx, [rsp+48h]; this
0x14001f843  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x14001f84a  lea     edx, [rax+48h]; void *
0x14001f84d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001f852  mov     rcx, rdi; void *
0x14001f855  mov     esi, eax
0x14001f857  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x14001f85c  jmp     loc_14001F7C7
0x14001f861  test    rdi, rdi
0x14001f864  jz      short loc_14001F891
0x14001f866  xor     edx, edx; dwCmpFlags
0x14001f868  lea     rax, a1; "1"
0x14001f86f  or      r9d, 0FFFFFFFFh; cchCount1
0x14001f873  mov     r8, rdi; lpString1
0x14001f876  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x14001f87b  mov     [rsp+48h+lpString2], rax; lpString2
0x14001f880  lea     ecx, [rdx+7Fh]; Locale
0x14001f883  call    cs:__imp_CompareStringW
0x14001f889  cmp     eax, 2
0x14001f88c  setz    al
0x14001f88f  jmp     short loc_14001F893
0x14001f891  xor     al, al
0x14001f893  mov     [r14], al
0x14001f896  mov     byte ptr [r15], 1
0x14001f89a  test    rdi, rdi
0x14001f89d  jz      short loc_14001F8A7
0x14001f89f  mov     rcx, rdi; void *
0x14001f8a2  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x14001f8a7  test    rbx, rbx
0x14001f8aa  jz      short loc_14001F8B4
0x14001f8ac  mov     rcx, rbx; void *
0x14001f8af  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x14001f8b4  xor     eax, eax
0x14001f8b6  mov     rbx, [rsp+48h+arg_0]
0x14001f8bb  mov     rsi, [rsp+48h+arg_10]
0x14001f8c0  add     rsp, 30h
0x14001f8c4  pop     r15
0x14001f8c6  pop     r14
0x14001f8c8  pop     rdi
0x14001f8c9  retn
```
