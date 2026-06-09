# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ed4c`
- end: `0x18000f061`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `789`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c93c`
- `0x18001628c`

## callees

- `0x1800053a0`
- `0x18000d928`
- `0x18000e214`
- `0x18000e234`
- `0x18000eba8`
- `0x18000ed4c`
- `0x18000f1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000edee`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee7c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000edee`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eedc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eefa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eedc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eefa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef58`

## string_xrefs

- `0x18000efd2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000efeb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f004`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f01d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f036`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f04f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  int v27; // [rsp+28h] [rbp-E0h] BYREF
  int v28[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v26);
    return 0;
  }
  v28[0] = 0;
  v27 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v28);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v27);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DD,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DD,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v27);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DD,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    *a3 = ((__int64)v27 << 31) | v28[0];
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DD,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (unsigned int)"wil", (const char *)(unsigned int)v19, v27);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9DD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9DD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  return v20;
}

```

## disassembly

```asm
0x18000ed4c  mov     rax, rsp
0x18000ed4f  mov     [rax+8], rbx
0x18000ed53  mov     [rax+10h], rsi
0x18000ed57  mov     [rax+20h], rdi
0x18000ed5b  push    rbp
0x18000ed5c  push    r14
0x18000ed5e  push    r15
0x18000ed60  lea     rbp, [rax-168h]
0x18000ed67  sub     rsp, 250h
0x18000ed6e  mov     rax, cs:__security_cookie
0x18000ed75  xor     rax, rsp
0x18000ed78  mov     [rbp+160h+var_20], rax
0x18000ed7f  xor     r15d, r15d
0x18000ed82  lea     rax, [rsp+260h+Name]
0x18000ed87  mov     esi, 104h
0x18000ed8c  mov     [r8], r15
0x18000ed8f  mov     r9d, esi
0x18000ed92  lea     rdx, [rsp+260h+Name]
0x18000ed97  sub     rcx, rax
0x18000ed9a  mov     r14, r8
0x18000ed9d  lea     rax, [r9+7FFFFEFAh]
0x18000eda4  test    rax, rax
0x18000eda7  jz      short loc_18000EDBF
0x18000eda9  movzx   eax, word ptr [rcx+rdx]
0x18000edad  test    ax, ax
0x18000edb0  jz      short loc_18000EDBF
0x18000edb2  mov     [rdx], ax
0x18000edb5  add     rdx, 2
0x18000edb9  sub     r9, 1
0x18000edbd  jnz     short loc_18000ED9D
0x18000edbf  lea     rax, [rdx-2]
0x18000edc3  test    r9, r9
0x18000edc6  lea     r8, aP0; "_p0"
0x18000edcd  cmovnz  rax, rdx
0x18000edd1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000edd6  mov     rdx, rsi; unsigned __int64
0x18000edd9  mov     [rax], r15w
0x18000eddd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ede2  lea     r8, [rsp+260h+Name]; lpName
0x18000ede7  xor     edx, edx; bInheritHandle
0x18000ede9  mov     ecx, 1F0003h; dwDesiredAccess
0x18000edee  call    cs:__imp_OpenSemaphoreW
0x18000edf5  nop     dword ptr [rax+rax+00h]
0x18000edfa  mov     rbx, rax
0x18000edfd  test    rax, rax
0x18000ee00  jz      loc_18000EF71
0x18000ee06  lea     rdx, [rsp+260h+var_23C]; int *
0x18000ee0b  mov     [rsp+260h+var_23C], r15d
0x18000ee10  mov     rcx, rax; hHandle
0x18000ee13  mov     [rsp+260h+var_240], r15d; int
0x18000ee18  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ee1d  mov     edi, eax
0x18000ee1f  test    eax, eax
0x18000ee21  jns     short loc_18000EE5C
0x18000ee23  mov     rcx, [rbp+168h]; this
0x18000ee2a  lea     r8, aWil; "wil"
0x18000ee31  mov     r9d, eax; char *
0x18000ee34  mov     edx, 0D3h; void *
0x18000ee39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee3e  mov     rcx, rbx; hObject
0x18000ee41  call    cs:__imp_CloseHandle
0x18000ee48  nop     dword ptr [rax+rax+00h]
0x18000ee4d  test    eax, eax
0x18000ee4f  jz      loc_18000F016
0x18000ee55  mov     eax, edi
0x18000ee57  jmp     loc_18000EF9E
0x18000ee5c  lea     r8, asc_1800D5AE0; "h"
0x18000ee63  mov     rdx, rsi; unsigned __int64
0x18000ee66  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ee6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee70  lea     r8, [rsp+260h+Name]; lpName
0x18000ee75  xor     edx, edx; bInheritHandle
0x18000ee77  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ee7c  call    cs:__imp_OpenSemaphoreW
0x18000ee83  nop     dword ptr [rax+rax+00h]
0x18000ee88  mov     rdi, rax
0x18000ee8b  test    rax, rax
0x18000ee8e  jz      loc_18000EF3B
0x18000ee94  lea     rdx, [rsp+260h+var_240]; int *
0x18000ee99  mov     rcx, rax; hHandle
0x18000ee9c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000eea1  mov     esi, eax
0x18000eea3  test    eax, eax
0x18000eea5  jns     short loc_18000EEF7
0x18000eea7  mov     rcx, [rbp+168h]; this
0x18000eeae  lea     r8, aWil; "wil"
0x18000eeb5  mov     r9d, eax; char *
0x18000eeb8  mov     edx, 0DBh; void *
0x18000eebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eec2  mov     rcx, rdi; hObject
0x18000eec5  call    cs:__imp_CloseHandle
0x18000eecc  nop     dword ptr [rax+rax+00h]
0x18000eed1  test    eax, eax
0x18000eed3  jz      loc_18000F02F
0x18000eed9  mov     rcx, rbx; hObject
0x18000eedc  call    cs:__imp_CloseHandle
0x18000eee3  nop     dword ptr [rax+rax+00h]
0x18000eee8  test    eax, eax
0x18000eeea  jz      loc_18000F048
0x18000eef0  mov     eax, esi
0x18000eef2  jmp     loc_18000EF9E
0x18000eef7  mov     rcx, rdi; hObject
0x18000eefa  call    cs:__imp_CloseHandle
0x18000ef01  nop     dword ptr [rax+rax+00h]
0x18000ef06  test    eax, eax
0x18000ef08  jz      loc_18000EFCB
0x18000ef0e  movsxd  rcx, [rsp+260h+var_240]
0x18000ef13  movsxd  rax, [rsp+260h+var_23C]
0x18000ef18  shl     rcx, 1Fh
0x18000ef1c  or      rax, rcx
0x18000ef1f  mov     rcx, rbx; hObject
0x18000ef22  mov     [r14], rax
0x18000ef25  call    cs:__imp_CloseHandle
0x18000ef2c  nop     dword ptr [rax+rax+00h]
0x18000ef31  test    eax, eax
0x18000ef33  jz      loc_18000EFE4
0x18000ef39  jmp     short loc_18000EF82
0x18000ef3b  mov     rcx, [rbp+168h]; this
0x18000ef42  lea     r8, aWil; "wil"
0x18000ef49  mov     edx, 0D9h; void *
0x18000ef4e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ef53  mov     rcx, rbx; hObject
0x18000ef56  mov     edi, eax
0x18000ef58  call    cs:__imp_CloseHandle
0x18000ef5f  nop     dword ptr [rax+rax+00h]
0x18000ef64  test    eax, eax
0x18000ef66  jz      loc_18000EFFD
0x18000ef6c  jmp     loc_18000EE55
0x18000ef71  call    cs:__imp_GetLastError
0x18000ef78  nop     dword ptr [rax+rax+00h]
0x18000ef7d  cmp     eax, 2
0x18000ef80  jnz     short loc_18000EF86
0x18000ef82  xor     eax, eax
0x18000ef84  jmp     short loc_18000EF9E
0x18000ef86  mov     rcx, [rbp+168h]; this
0x18000ef8d  lea     r8, aWil; "wil"
0x18000ef94  mov     edx, 0CDh; void *
0x18000ef99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ef9e  mov     rcx, [rbp+160h+var_20]
0x18000efa5  xor     rcx, rsp; StackCookie
0x18000efa8  call    __security_check_cookie
0x18000efad  lea     r11, [rsp+260h+var_10]
0x18000efb5  mov     rbx, [r11+20h]
0x18000efb9  mov     rsi, [r11+28h]
0x18000efbd  mov     rdi, [r11+38h]
0x18000efc1  mov     rsp, r11
0x18000efc4  pop     r15
0x18000efc6  pop     r14
0x18000efc8  pop     rbp
0x18000efc9  retn
0x18000efcb  mov     rcx, [rbp+168h]; this
0x18000efd2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000efd9  mov     edx, 9DDh; void *
0x18000efde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000efe4  mov     rcx, [rbp+168h]; this
0x18000efeb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000eff2  mov     edx, 9DDh; void *
0x18000eff7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000effd  mov     rcx, [rbp+168h]; this
0x18000f004  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f00b  mov     edx, 9DDh; void *
0x18000f010  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f016  mov     rcx, [rbp+168h]; this
0x18000f01d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f024  mov     edx, 9DDh; void *
0x18000f029  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f02f  mov     rcx, [rbp+168h]; this
0x18000f036  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f03d  mov     edx, 9DDh; void *
0x18000f042  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f048  mov     rcx, [rbp+168h]; this
0x18000f04f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f056  mov     edx, 9DDh; void *
0x18000f05b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
