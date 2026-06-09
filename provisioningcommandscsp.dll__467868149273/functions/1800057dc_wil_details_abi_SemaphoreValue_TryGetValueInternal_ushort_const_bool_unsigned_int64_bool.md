# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800057dc`
- end: `0x180005a94`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `696`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800031d4`

## callees

- `0x180003ea0`
- `0x180004ec4`
- `0x180004ee4`
- `0x18000563c`
- `0x1800057dc`
- `0x180005cf8`
- `0x18000ccc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005870`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058f8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005870`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800058f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
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
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x1800057dc  push    rbp
0x1800057de  push    rbx
0x1800057df  push    rsi
0x1800057e0  push    rdi
0x1800057e1  push    r14
0x1800057e3  push    r15
0x1800057e5  lea     rbp, [rsp-158h]
0x1800057ed  sub     rsp, 258h
0x1800057f4  mov     rax, cs:__security_cookie
0x1800057fb  xor     rax, rsp
0x1800057fe  mov     [rbp+180h+var_40], rax
0x180005805  xor     r15d, r15d
0x180005808  lea     rax, [rsp+280h+Name]
0x18000580d  mov     [r8], r15
0x180005810  mov     r14, r8
0x180005813  mov     edx, 104h
0x180005818  mov     r9d, 7FFFFFFEh
0x18000581e  test    r9, r9
0x180005821  jz      short loc_180005842
0x180005823  movzx   r8d, word ptr [rcx]
0x180005827  test    r8w, r8w
0x18000582b  jz      short loc_180005842
0x18000582d  mov     [rax], r8w
0x180005831  add     rcx, 2
0x180005835  add     rax, 2
0x180005839  dec     r9
0x18000583c  sub     rdx, 1; unsigned __int64
0x180005840  jnz     short loc_18000581E
0x180005842  test    rdx, rdx
0x180005845  lea     rcx, [rax-2]
0x180005849  lea     r8, aP0; "_p0"
0x180005850  cmovnz  rcx, rax
0x180005854  mov     [rcx], r15w
0x180005858  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000585d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005862  mov     esi, 1F0003h
0x180005867  lea     r8, [rsp+280h+Name]; lpName
0x18000586c  mov     ecx, esi; dwDesiredAccess
0x18000586e  xor     edx, edx; bInheritHandle
0x180005870  call    cs:__imp_OpenSemaphoreW
0x180005877  nop     dword ptr [rax+rax+00h]
0x18000587c  mov     rbx, rax
0x18000587f  test    rax, rax
0x180005882  jz      loc_1800059E2
0x180005888  lea     rdx, [rsp+280h+var_25C]; int *
0x18000588d  mov     [rsp+280h+var_25C], r15d
0x180005892  mov     rcx, rax; hHandle
0x180005895  mov     [rsp+280h+var_260], r15d; int
0x18000589a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000589f  mov     edi, eax
0x1800058a1  test    eax, eax
0x1800058a3  jns     short loc_1800058DE
0x1800058a5  mov     rcx, [rbp+188h]; this
0x1800058ac  lea     r8, aWil; "wil"
0x1800058b3  mov     r9d, eax; char *
0x1800058b6  mov     edx, 0D6h; void *
0x1800058bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058c0  mov     rcx, rbx; hObject
0x1800058c3  call    cs:__imp_CloseHandle
0x1800058ca  nop     dword ptr [rax+rax+00h]
0x1800058cf  test    eax, eax
0x1800058d1  jz      loc_180005A5E
0x1800058d7  mov     eax, edi
0x1800058d9  jmp     loc_180005A08
0x1800058de  lea     r8, asc_18000FEB8; "h"
0x1800058e5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800058ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800058ef  lea     r8, [rsp+280h+Name]; lpName
0x1800058f4  xor     edx, edx; bInheritHandle
0x1800058f6  mov     ecx, esi; dwDesiredAccess
0x1800058f8  call    cs:__imp_OpenSemaphoreW
0x1800058ff  nop     dword ptr [rax+rax+00h]
0x180005904  mov     rdi, rax
0x180005907  test    rax, rax
0x18000590a  jz      loc_1800059B7
0x180005910  lea     rdx, [rsp+280h+var_260]; int *
0x180005915  mov     rcx, rax; hHandle
0x180005918  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000591d  mov     esi, eax
0x18000591f  test    eax, eax
0x180005921  jns     short loc_180005973
0x180005923  mov     rcx, [rbp+188h]; this
0x18000592a  lea     r8, aWil; "wil"
0x180005931  mov     r9d, eax; char *
0x180005934  mov     edx, 0DEh; void *
0x180005939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000593e  mov     rcx, rdi; hObject
0x180005941  call    cs:__imp_CloseHandle
0x180005948  nop     dword ptr [rax+rax+00h]
0x18000594d  test    eax, eax
0x18000594f  jz      loc_180005A70
0x180005955  mov     rcx, rbx; hObject
0x180005958  call    cs:__imp_CloseHandle
0x18000595f  nop     dword ptr [rax+rax+00h]
0x180005964  test    eax, eax
0x180005966  jz      loc_180005A82
0x18000596c  mov     eax, esi
0x18000596e  jmp     loc_180005A08
0x180005973  mov     rcx, rdi; hObject
0x180005976  call    cs:__imp_CloseHandle
0x18000597d  nop     dword ptr [rax+rax+00h]
0x180005982  test    eax, eax
0x180005984  jz      loc_180005A28
0x18000598a  movsxd  rax, [rsp+280h+var_25C]
0x18000598f  movsxd  rcx, [rsp+280h+var_260]
0x180005994  shl     rcx, 1Fh
0x180005998  or      rcx, rax
0x18000599b  mov     [r14], rcx
0x18000599e  mov     rcx, rbx; hObject
0x1800059a1  call    cs:__imp_CloseHandle
0x1800059a8  nop     dword ptr [rax+rax+00h]
0x1800059ad  test    eax, eax
0x1800059af  jz      loc_180005A3A
0x1800059b5  jmp     short loc_1800059F3
0x1800059b7  mov     rcx, [rbp+188h]; this
0x1800059be  mov     edx, 0DCh; void *
0x1800059c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800059c8  mov     rcx, rbx; hObject
0x1800059cb  mov     edi, eax
0x1800059cd  call    cs:__imp_CloseHandle
0x1800059d4  nop     dword ptr [rax+rax+00h]
0x1800059d9  test    eax, eax
0x1800059db  jz      short loc_180005A4C
0x1800059dd  jmp     loc_1800058D7
0x1800059e2  call    cs:__imp_GetLastError
0x1800059e9  nop     dword ptr [rax+rax+00h]
0x1800059ee  cmp     eax, 2
0x1800059f1  jnz     short loc_1800059F7
0x1800059f3  xor     eax, eax
0x1800059f5  jmp     short loc_180005A08
0x1800059f7  mov     rcx, [rbp+188h]; this
0x1800059fe  mov     edx, 0D0h; void *
0x180005a03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005a08  mov     rcx, [rbp+180h+var_40]
0x180005a0f  xor     rcx, rsp; StackCookie
0x180005a12  call    __security_check_cookie
0x180005a17  add     rsp, 258h
0x180005a1e  pop     r15
0x180005a20  pop     r14
0x180005a22  pop     rdi
0x180005a23  pop     rsi
0x180005a24  pop     rbx
0x180005a25  pop     rbp
0x180005a26  retn
0x180005a28  mov     rcx, [rbp+188h]; this
0x180005a2f  mov     edx, 0A0Bh; void *
0x180005a34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a3a  mov     rcx, [rbp+188h]; this
0x180005a41  mov     edx, 0A0Bh; void *
0x180005a46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a4c  mov     rcx, [rbp+188h]; this
0x180005a53  mov     edx, 0A0Bh; void *
0x180005a58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a5e  mov     rcx, [rbp+188h]; this
0x180005a65  mov     edx, 0A0Bh; void *
0x180005a6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a70  mov     rcx, [rbp+188h]; this
0x180005a77  mov     edx, 0A0Bh; void *
0x180005a7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a82  mov     rcx, [rbp+188h]; this
0x180005a89  mov     edx, 0A0Bh; void *
0x180005a8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
