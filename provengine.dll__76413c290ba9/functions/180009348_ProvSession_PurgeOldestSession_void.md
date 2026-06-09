# ProvSession::PurgeOldestSession(void)

- ea: `0x180009348`
- end: `0x1800095cf`
- name: `?PurgeOldestSession@ProvSession@@AEAAJXZ`
- size: `647`
- prototype: `__int64 __fastcall(ProvSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18000a4e4`

## callees

- `0x1800010c8`
- `0x180009348`
- `0x1800098dc`
- `0x180009900`
- `0x180033218`
- `0x180033354`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800093c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009487`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009570`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800095a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800093c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009487`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009570`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800095a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000942f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000942f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094c8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800094fb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800094fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProvSession::PurgeOldestSession(HKEY *this)
{
  int SzValue; // eax
  signed int v3; // ebx
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  int v7; // eax
  const unsigned __int16 *v8; // r8
  HKEY v9; // rsi
  DWORD LastError; // ebx
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  signed int v16; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v17[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h]
  unsigned __int64 v19; // [rsp+58h] [rbp-21h]
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 v21; // [rsp+78h] [rbp-1h]
  char v22[32]; // [rsp+80h] [rbp+7h] BYREF
  signed int *v23; // [rsp+A0h] [rbp+27h]
  __int64 v24; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v21 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  SzValue = RegGetSzValue(this[11], L"FirstSession", lpSubKey);
  v3 = SzValue;
  if ( SzValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
      (const char *)(unsigned int)SzValue,
      phkResult);
LABEL_3:
    if ( v21 >= 8 )
      operator delete((void *)lpSubKey[0]);
    return (unsigned int)v3;
  }
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( v21 >= 8 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(this[11], v5, 0, 0x20019u, &hKey);
  if ( v6 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x17D,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
           (const char *)v6,
           phkResulta);
LABEL_10:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_3;
  }
  v19 = 7;
  v18 = 0;
  LOWORD(v17[0]) = 0;
  v7 = RegGetSzValue(hKey, L"NextSession", v17);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
      (const char *)(unsigned int)v7,
      phkResulta);
LABEL_14:
    if ( v19 >= 8 )
      operator delete(v17[0]);
    v19 = 7;
    v18 = 0;
    LOWORD(v17[0]) = 0;
    goto LABEL_10;
  }
  v8 = (const unsigned __int16 *)v17;
  if ( v19 >= 8 )
    v8 = v17[0];
  RegSetSzValue(this[11], L"FirstSession", v8);
  v9 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v9);
    SetLastError(LastError);
  }
  hKey = 0;
  v11 = (const WCHAR *)lpSubKey;
  if ( v21 >= 8 )
    v11 = lpSubKey[0];
  v12 = RegDeleteKeyW(this[11], v11);
  v3 = v12;
  if ( v12 > 0 )
    v3 = (unsigned __int16)v12 | 0x80070000;
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      v16 = v3;
      v23 = &v16;
      v24 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E3F1, 0, 0, 3, v22);
    }
    goto LABEL_14;
  }
  if ( v19 >= 8 )
    operator delete(v17[0]);
  v19 = 7;
  v18 = 0;
  LOWORD(v17[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v21 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180009348  mov     [rsp-8+arg_8], rbx
0x18000934d  mov     [rsp-8+arg_10], rsi
0x180009352  push    rbp
0x180009353  push    rdi
0x180009354  push    r15
0x180009356  lea     rbp, [rsp-47h]
0x18000935b  sub     rsp, 0C0h
0x180009362  mov     rax, cs:__security_cookie
0x180009369  xor     rax, rsp
0x18000936c  mov     [rbp+57h+var_20], rax
0x180009370  mov     rdi, rcx
0x180009373  mov     r15d, 7
0x180009379  mov     [rbp+57h+var_58], r15
0x18000937d  mov     [rbp+57h+var_60], 0
0x180009385  xor     eax, eax
0x180009387  mov     word ptr [rbp+57h+lpSubKey], ax
0x18000938b  lea     r8, [rbp+57h+lpSubKey]; void *
0x18000938f  lea     rdx, aFirstsession; "FirstSession"
0x180009396  mov     rcx, [rcx+58h]; hKey
0x18000939a  call    ?RegGetSzValue@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegGetSzValue(HKEY__ *,ushort const *,std::wstring &)
0x18000939f  mov     ebx, eax
0x1800093a1  test    eax, eax
0x1800093a3  jns     short loc_1800093D6
0x1800093a5  mov     rcx, [rbp+5Fh]; this
0x1800093a9  mov     r9d, eax; char *
0x1800093ac  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800093b3  mov     edx, 173h; void *
0x1800093b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800093bd  nop
0x1800093be  cmp     [rbp+57h+var_58], 8
0x1800093c3  jb      short loc_1800093CF
0x1800093c5  mov     rcx, [rbp+57h+lpSubKey]
0x1800093c9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800093cf  mov     eax, ebx
0x1800093d1  jmp     loc_1800095AB
0x1800093d6  mov     [rbp+57h+hKey], 0
0x1800093de  lea     rdx, [rbp+57h+lpSubKey]
0x1800093e2  cmp     [rbp+57h+var_58], 8
0x1800093e7  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800093ec  lea     rax, [rbp+57h+hKey]
0x1800093f0  mov     [rsp+0D0h+phkResult], rax; int
0x1800093f5  mov     r9d, 20019h; samDesired
0x1800093fb  xor     r8d, r8d; ulOptions
0x1800093fe  mov     rcx, [rdi+58h]; hKey
0x180009402  call    cs:__imp_RegOpenKeyExW
0x180009408  test    eax, eax
0x18000940a  jz      short loc_180009437
0x18000940c  mov     rcx, [rbp+5Fh]; this
0x180009410  mov     r9d, eax; char *
0x180009413  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000941a  mov     edx, 17Dh; void *
0x18000941f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009424  mov     ebx, eax
0x180009426  mov     rcx, [rbp+57h+hKey]; hKey
0x18000942a  test    rcx, rcx
0x18000942d  jz      short loc_1800093BE
0x18000942f  call    cs:__imp_RegCloseKey
0x180009435  jmp     short loc_1800093BE
0x180009437  mov     [rbp+57h+var_78], r15
0x18000943b  mov     [rbp+57h+var_80], 0
0x180009443  xor     eax, eax
0x180009445  mov     word ptr [rbp+57h+var_90], ax
0x180009449  lea     r8, [rbp+57h+var_90]; void *
0x18000944d  lea     rdx, aNextsession; "NextSession"
0x180009454  mov     rcx, [rbp+57h+hKey]; hKey
0x180009458  call    ?RegGetSzValue@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegGetSzValue(HKEY__ *,ushort const *,std::wstring &)
0x18000945d  mov     ebx, eax
0x18000945f  test    eax, eax
0x180009461  jns     short loc_1800094A1
0x180009463  mov     rcx, [rbp+5Fh]; this
0x180009467  mov     r9d, eax; char *
0x18000946a  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180009471  mov     edx, 180h; void *
0x180009476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000947b  nop
0x18000947c  cmp     [rbp+57h+var_78], 8
0x180009481  jb      short loc_18000948D
0x180009483  mov     rcx, [rbp+57h+var_90]
0x180009487  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000948d  mov     [rbp+57h+var_78], r15
0x180009491  mov     [rbp+57h+var_80], 0
0x180009499  xor     eax, eax
0x18000949b  mov     word ptr [rbp+57h+var_90], ax
0x18000949f  jmp     short loc_180009426
0x1800094a1  lea     r8, [rbp+57h+var_90]
0x1800094a5  cmp     [rbp+57h+var_78], 8
0x1800094aa  cmovnb  r8, [rbp+57h+var_90]; unsigned __int16 *
0x1800094af  lea     rdx, aFirstsession; "FirstSession"
0x1800094b6  mov     rcx, [rdi+58h]; HKEY
0x1800094ba  call    ?RegSetSzValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetSzValue(HKEY__ *,ushort const *,ushort const *)
0x1800094bf  mov     rsi, [rbp+57h+hKey]
0x1800094c3  test    rsi, rsi
0x1800094c6  jz      short loc_1800094E1
0x1800094c8  call    cs:__imp_GetLastError
0x1800094ce  mov     ebx, eax
0x1800094d0  mov     rcx, rsi; hKey
0x1800094d3  call    cs:__imp_RegCloseKey
0x1800094d9  mov     ecx, ebx; dwErrCode
0x1800094db  call    cs:__imp_SetLastError
0x1800094e1  mov     [rbp+57h+hKey], 0
0x1800094e9  lea     rdx, [rbp+57h+lpSubKey]
0x1800094ed  cmp     [rbp+57h+var_58], 8
0x1800094f2  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800094f7  mov     rcx, [rdi+58h]; hKey
0x1800094fb  call    cs:__imp_RegDeleteKeyW
0x180009501  mov     ebx, eax
0x180009503  test    eax, eax
0x180009505  jle     short loc_180009510
0x180009507  movzx   ebx, ax
0x18000950a  or      ebx, 80070000h
0x180009510  test    ebx, ebx
0x180009512  jns     short loc_180009565
0x180009514  mov     eax, cs:dword_18005A000
0x18000951a  cmp     eax, 3
0x18000951d  jbe     loc_18000947C
0x180009523  mov     [rbp+57h+var_98], ebx
0x180009526  lea     rax, [rbp+57h+var_98]
0x18000952a  mov     [rbp+57h+var_30], rax
0x18000952e  mov     [rbp+57h+var_28], 4
0x180009536  lea     rax, [rbp+57h+var_50]
0x18000953a  mov     [rsp+0D0h+var_A8], rax
0x18000953f  mov     dword ptr [rsp+0D0h+phkResult], 3
0x180009547  xor     r9d, r9d
0x18000954a  xor     r8d, r8d
0x18000954d  lea     rdx, byte_18004E3F1
0x180009554  lea     rcx, dword_18005A000
0x18000955b  call    _tlgWriteTransfer_EventWriteTransfer
0x180009560  jmp     loc_18000947C
0x180009565  cmp     [rbp+57h+var_78], 8
0x18000956a  jb      short loc_180009576
0x18000956c  mov     rcx, [rbp+57h+var_90]
0x180009570  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009576  mov     [rbp+57h+var_78], r15
0x18000957a  mov     [rbp+57h+var_80], 0
0x180009582  xor     eax, eax
0x180009584  mov     word ptr [rbp+57h+var_90], ax
0x180009588  mov     rcx, [rbp+57h+hKey]; hKey
0x18000958c  test    rcx, rcx
0x18000958f  jz      short loc_180009598
0x180009591  call    cs:__imp_RegCloseKey
0x180009597  nop
0x180009598  cmp     [rbp+57h+var_58], 8
0x18000959d  jb      short loc_1800095A9
0x18000959f  mov     rcx, [rbp+57h+lpSubKey]
0x1800095a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800095a9  xor     eax, eax
0x1800095ab  mov     rcx, [rbp+57h+var_20]
0x1800095af  xor     rcx, rsp; StackCookie
0x1800095b2  call    __security_check_cookie
0x1800095b7  lea     r11, [rsp+0D0h+var_10]
0x1800095bf  mov     rbx, [r11+28h]
0x1800095c3  mov     rsi, [r11+30h]
0x1800095c7  mov     rsp, r11
0x1800095ca  pop     r15
0x1800095cc  pop     rdi
0x1800095cd  pop     rbp
0x1800095ce  retn
```
