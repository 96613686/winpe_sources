# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000902c`
- end: `0x18000930e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `738`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800043ec`
- `0x1800047e4`

## callees

- `0x1800017a0`
- `0x180005c5c`
- `0x180007f94`
- `0x180007fb4`
- `0x180008a50`
- `0x18000902c`
- `0x180009944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800090cb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009153`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800090cb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000911e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000919c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000922f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000911e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000919c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000922f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  const char *v33; // r9
  int v34; // [rsp+28h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v19);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v34);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v27, v28);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (unsigned int)"wil", (const char *)(unsigned int)v21, v34);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v23, v24);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000902c  mov     rax, rsp
0x18000902f  mov     [rax+8], rbx
0x180009033  mov     [rax+10h], rsi
0x180009037  mov     [rax+20h], rdi
0x18000903b  push    rbp
0x18000903c  push    r14
0x18000903e  push    r15
0x180009040  lea     rbp, [rax-168h]
0x180009047  sub     rsp, 250h
0x18000904e  mov     rax, cs:__security_cookie
0x180009055  xor     rax, rsp
0x180009058  mov     [rbp+160h+var_20], rax
0x18000905f  xor     r15d, r15d
0x180009062  lea     rax, [rsp+260h+Name]
0x180009067  mov     [r8], r15
0x18000906a  lea     rdx, [rsp+260h+Name]
0x18000906f  sub     rcx, rax
0x180009072  mov     r14, r8
0x180009075  mov     r9d, 104h
0x18000907b  lea     rax, [r9+7FFFFEFAh]
0x180009082  test    rax, rax
0x180009085  jz      short loc_18000909D
0x180009087  movzx   eax, word ptr [rcx+rdx]
0x18000908b  test    ax, ax
0x18000908e  jz      short loc_18000909D
0x180009090  mov     [rdx], ax
0x180009093  add     rdx, 2; unsigned __int64
0x180009097  sub     r9, 1
0x18000909b  jnz     short loc_18000907B
0x18000909d  test    r9, r9
0x1800090a0  lea     rax, [rdx-2]
0x1800090a4  lea     r8, aP0; "_p0"
0x1800090ab  cmovnz  rax, rdx
0x1800090af  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800090b4  mov     [rax], r15w
0x1800090b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800090bd  mov     esi, 1F0003h
0x1800090c2  lea     r8, [rsp+260h+Name]; lpName
0x1800090c7  mov     ecx, esi; dwDesiredAccess
0x1800090c9  xor     edx, edx; bInheritHandle
0x1800090cb  call    cs:__imp_OpenSemaphoreW
0x1800090d2  nop     dword ptr [rax+rax+00h]
0x1800090d7  mov     rbx, rax
0x1800090da  test    rax, rax
0x1800090dd  jz      loc_180009248
0x1800090e3  lea     rdx, [rsp+260h+var_23C]; int *
0x1800090e8  mov     [rsp+260h+var_23C], r15d
0x1800090ed  mov     rcx, rax; hHandle
0x1800090f0  mov     [rsp+260h+var_240], r15d; int
0x1800090f5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800090fa  mov     edi, eax
0x1800090fc  test    eax, eax
0x1800090fe  jns     short loc_180009139
0x180009100  mov     rcx, [rbp+168h]; this
0x180009107  lea     r8, aWil; "wil"
0x18000910e  mov     r9d, eax; char *
0x180009111  mov     edx, 0D3h; void *
0x180009116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000911b  mov     rcx, rbx; hObject
0x18000911e  call    cs:__imp_CloseHandle
0x180009125  nop     dword ptr [rax+rax+00h]
0x18000912a  test    eax, eax
0x18000912c  jz      loc_1800092D8
0x180009132  mov     eax, edi
0x180009134  jmp     loc_180009275
0x180009139  lea     r8, asc_18003CCF0; "h"
0x180009140  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009145  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000914a  lea     r8, [rsp+260h+Name]; lpName
0x18000914f  xor     edx, edx; bInheritHandle
0x180009151  mov     ecx, esi; dwDesiredAccess
0x180009153  call    cs:__imp_OpenSemaphoreW
0x18000915a  nop     dword ptr [rax+rax+00h]
0x18000915f  mov     rdi, rax
0x180009162  test    rax, rax
0x180009165  jz      loc_180009212
0x18000916b  lea     rdx, [rsp+260h+var_240]; int *
0x180009170  mov     rcx, rax; hHandle
0x180009173  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009178  mov     esi, eax
0x18000917a  test    eax, eax
0x18000917c  jns     short loc_1800091CE
0x18000917e  mov     rcx, [rbp+168h]; this
0x180009185  lea     r8, aWil; "wil"
0x18000918c  mov     r9d, eax; char *
0x18000918f  mov     edx, 0DBh; void *
0x180009194  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009199  mov     rcx, rdi; hObject
0x18000919c  call    cs:__imp_CloseHandle
0x1800091a3  nop     dword ptr [rax+rax+00h]
0x1800091a8  test    eax, eax
0x1800091aa  jz      loc_1800092EA
0x1800091b0  mov     rcx, rbx; hObject
0x1800091b3  call    cs:__imp_CloseHandle
0x1800091ba  nop     dword ptr [rax+rax+00h]
0x1800091bf  test    eax, eax
0x1800091c1  jz      loc_1800092FC
0x1800091c7  mov     eax, esi
0x1800091c9  jmp     loc_180009275
0x1800091ce  mov     rcx, rdi; hObject
0x1800091d1  call    cs:__imp_CloseHandle
0x1800091d8  nop     dword ptr [rax+rax+00h]
0x1800091dd  test    eax, eax
0x1800091df  jz      loc_1800092A2
0x1800091e5  movsxd  rax, [rsp+260h+var_23C]
0x1800091ea  movsxd  rcx, [rsp+260h+var_240]
0x1800091ef  shl     rcx, 1Fh
0x1800091f3  or      rcx, rax
0x1800091f6  mov     [r14], rcx
0x1800091f9  mov     rcx, rbx; hObject
0x1800091fc  call    cs:__imp_CloseHandle
0x180009203  nop     dword ptr [rax+rax+00h]
0x180009208  test    eax, eax
0x18000920a  jz      loc_1800092B4
0x180009210  jmp     short loc_180009259
0x180009212  mov     rcx, [rbp+168h]; this
0x180009219  lea     r8, aWil; "wil"
0x180009220  mov     edx, 0D9h; void *
0x180009225  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000922a  mov     rcx, rbx; hObject
0x18000922d  mov     edi, eax
0x18000922f  call    cs:__imp_CloseHandle
0x180009236  nop     dword ptr [rax+rax+00h]
0x18000923b  test    eax, eax
0x18000923d  jz      loc_1800092C6
0x180009243  jmp     loc_180009132
0x180009248  call    cs:__imp_GetLastError
0x18000924f  nop     dword ptr [rax+rax+00h]
0x180009254  cmp     eax, 2
0x180009257  jnz     short loc_18000925D
0x180009259  xor     eax, eax
0x18000925b  jmp     short loc_180009275
0x18000925d  mov     rcx, [rbp+168h]; this
0x180009264  lea     r8, aWil; "wil"
0x18000926b  mov     edx, 0CDh; void *
0x180009270  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009275  mov     rcx, [rbp+160h+var_20]
0x18000927c  xor     rcx, rsp; StackCookie
0x18000927f  call    __security_check_cookie
0x180009284  lea     r11, [rsp+260h+var_10]
0x18000928c  mov     rbx, [r11+20h]
0x180009290  mov     rsi, [r11+28h]
0x180009294  mov     rdi, [r11+38h]
0x180009298  mov     rsp, r11
0x18000929b  pop     r15
0x18000929d  pop     r14
0x18000929f  pop     rbp
0x1800092a0  retn
0x1800092a2  mov     rcx, [rbp+168h]; this
0x1800092a9  mov     edx, 9DDh; void *
0x1800092ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092b4  mov     rcx, [rbp+168h]; this
0x1800092bb  mov     edx, 9DDh; void *
0x1800092c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092c6  mov     rcx, [rbp+168h]; this
0x1800092cd  mov     edx, 9DDh; void *
0x1800092d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092d8  mov     rcx, [rbp+168h]; this
0x1800092df  mov     edx, 9DDh; void *
0x1800092e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092ea  mov     rcx, [rbp+168h]; this
0x1800092f1  mov     edx, 9DDh; void *
0x1800092f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092fc  mov     rcx, [rbp+168h]; this
0x180009303  mov     edx, 9DDh; void *
0x180009308  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
