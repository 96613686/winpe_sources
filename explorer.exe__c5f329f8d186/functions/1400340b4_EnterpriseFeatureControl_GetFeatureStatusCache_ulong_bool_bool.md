# EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)

- ea: `0x1400340b4`
- end: `0x1400342d5`
- name: `?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z`
- size: `545`
- prototype: `__int64 __fastcall(unsigned int, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140033f38`

## callees

- `0x1400340b4`
- `0x1400346e8`
- `0x140035030`
- `0x14009ac68`
- `0x14009afa4`
- `0x14009de4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003419d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003419d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003410c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003410c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140034287`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140034287`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14003418b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140034232`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14003418b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140034232`

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
0x1400340b4  mov     [rsp+arg_0], rbx
0x1400340b9  mov     [rsp+arg_10], rsi
0x1400340be  push    rdi
0x1400340bf  push    r14
0x1400340c1  push    r15
0x1400340c3  sub     rsp, 30h
0x1400340c7  mov     r14, r8
0x1400340ca  mov     r15, rdx
0x1400340cd  mov     ebx, ecx
0x1400340cf  test    rdx, rdx
0x1400340d2  jnz     short loc_1400340F8
0x1400340d4  lea     edx, [r15+38h]; void *
0x1400340d8  mov     ebx, 80004003h
0x1400340dd  mov     rcx, [rsp+48h]; this
0x1400340e2  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1400340e9  mov     r9d, ebx; char *
0x1400340ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400340f1  mov     eax, ebx
0x1400340f3  jmp     loc_1400342C0
0x1400340f8  test    r14, r14
0x1400340fb  jnz     short loc_140034103
0x1400340fd  lea     edx, [r14+39h]
0x140034101  jmp     short loc_1400340D8
0x140034103  mov     [rsp+48h+lpName], 0
0x14003410c  call    cs:__imp_GetCurrentProcessId
0x140034113  nop     dword ptr [rax+rax+00h]
0x140034118  xor     ebx, 74161A4Eh
0x14003411e  lea     rdx, aEfcLuLu; "EFC_%lu_%lu"
0x140034125  bswap   ebx
0x140034127  xor     ebx, 8FB23D4Fh
0x14003412d  lea     rcx, [rsp+48h+lpName]
0x140034132  ror     ebx, 0FFh
0x140034135  mov     r8d, eax
0x140034138  xor     ebx, 833EA8FFh
0x14003413e  mov     r9d, ebx
0x140034141  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x140034146  mov     ebx, eax
0x140034148  test    eax, eax
0x14003414a  jns     short loc_14003417E
0x14003414c  mov     rcx, [rsp+48h]; this
0x140034151  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x140034158  mov     r9d, eax; char *
0x14003415b  mov     edx, 26h ; '&'; void *
0x140034160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140034165  mov     rcx, [rsp+48h+lpName]; void *
0x14003416a  test    rcx, rcx
0x14003416d  jz      short loc_140034174
0x14003416f  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x140034174  mov     edx, 3Ch ; '<'
0x140034179  jmp     loc_1400340DD
0x14003417e  mov     rbx, [rsp+48h+lpName]
0x140034183  xor     r8d, r8d; nSize
0x140034186  mov     rcx, rbx; lpName
0x140034189  xor     edx, edx; lpBuffer
0x14003418b  call    cs:__imp_GetEnvironmentVariableW
0x140034192  nop     dword ptr [rax+rax+00h]
0x140034197  mov     esi, eax
0x140034199  test    eax, eax
0x14003419b  jnz     short loc_140034206
0x14003419d  call    cs:__imp_GetLastError
0x1400341a4  nop     dword ptr [rax+rax+00h]
0x1400341a9  mov     edi, eax
0x1400341ab  test    eax, eax
0x1400341ad  jle     short loc_1400341B8
0x1400341af  movzx   edi, ax
0x1400341b2  or      edi, 80070000h
0x1400341b8  test    edi, edi
0x1400341ba  jns     short loc_140034206
0x1400341bc  mov     esi, 800700CBh
0x1400341c1  cmp     edi, esi
0x1400341c3  jnz     short loc_1400341D9
0x1400341c5  test    rbx, rbx
0x1400341c8  jz      short loc_1400341D2
0x1400341ca  mov     rcx, rbx; void *
0x1400341cd  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1400341d2  mov     eax, esi
0x1400341d4  jmp     loc_1400342C0
0x1400341d9  mov     edx, 41h ; 'A'; void *
0x1400341de  mov     rcx, [rsp+48h]; this
0x1400341e3  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1400341ea  mov     r9d, edi; char *
0x1400341ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400341f2  test    rbx, rbx
0x1400341f5  jz      short loc_1400341FF
0x1400341f7  mov     rcx, rbx; void *
0x1400341fa  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1400341ff  mov     eax, edi
0x140034201  jmp     loc_1400342C0
0x140034206  mov     r8, rsi
0x140034209  lea     rcx, [rsp+48h+lpName]
0x14003420e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140034213  mov     rdi, [rsp+48h+lpName]
0x140034218  test    rdi, rdi
0x14003421b  jnz     short loc_140034229
0x14003421d  mov     edi, 8007000Eh
0x140034222  mov     edx, 45h ; 'E'
0x140034227  jmp     short loc_1400341DE
0x140034229  mov     r8d, esi; nSize
0x14003422c  mov     rdx, rdi; lpBuffer
0x14003422f  mov     rcx, rbx; lpName
0x140034232  call    cs:__imp_GetEnvironmentVariableW
0x140034239  nop     dword ptr [rax+rax+00h]
0x14003423e  test    eax, eax
0x140034240  jnz     short loc_140034265
0x140034242  mov     rcx, [rsp+48h]; this
0x140034247  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x14003424e  lea     edx, [rax+48h]; void *
0x140034251  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140034256  mov     rcx, rdi; void *
0x140034259  mov     esi, eax
0x14003425b  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x140034260  jmp     loc_1400341C5
0x140034265  test    rdi, rdi
0x140034268  jz      short loc_14003429B
0x14003426a  xor     edx, edx; dwCmpFlags
0x14003426c  lea     rax, a1; "1"
0x140034273  or      r9d, 0FFFFFFFFh; cchCount1
0x140034277  mov     r8, rdi; lpString1
0x14003427a  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x14003427f  mov     [rsp+48h+lpString2], rax; lpString2
0x140034284  lea     ecx, [rdx+7Fh]; Locale
0x140034287  call    cs:__imp_CompareStringW
0x14003428e  nop     dword ptr [rax+rax+00h]
0x140034293  cmp     eax, 2
0x140034296  setz    al
0x140034299  jmp     short loc_14003429D
0x14003429b  xor     al, al
0x14003429d  mov     [r14], al
0x1400342a0  mov     byte ptr [r15], 1
0x1400342a4  test    rdi, rdi
0x1400342a7  jz      short loc_1400342B1
0x1400342a9  mov     rcx, rdi; void *
0x1400342ac  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1400342b1  test    rbx, rbx
0x1400342b4  jz      short loc_1400342BE
0x1400342b6  mov     rcx, rbx; void *
0x1400342b9  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1400342be  xor     eax, eax
0x1400342c0  mov     rbx, [rsp+48h+arg_0]
0x1400342c5  mov     rsi, [rsp+48h+arg_10]
0x1400342ca  add     rsp, 30h
0x1400342ce  pop     r15
0x1400342d0  pop     r14
0x1400342d2  pop     rdi
0x1400342d3  retn
```
