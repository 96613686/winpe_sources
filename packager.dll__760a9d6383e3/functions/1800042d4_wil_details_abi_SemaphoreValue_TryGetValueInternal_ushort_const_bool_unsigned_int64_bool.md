# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800042d4`
- end: `0x180004540`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800024d4`

## callees

- `0x180003410`
- `0x180003e54`
- `0x180003e74`
- `0x180004124`
- `0x1800042d4`
- `0x18000469c`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004368`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800043dd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004368`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800043dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000442a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000443f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000442a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000443f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004486`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x1800042d4  push    rbp
0x1800042d6  push    rbx
0x1800042d7  push    rsi
0x1800042d8  push    rdi
0x1800042d9  push    r14
0x1800042db  push    r15
0x1800042dd  lea     rbp, [rsp-158h]
0x1800042e5  sub     rsp, 258h
0x1800042ec  mov     rax, cs:__security_cookie
0x1800042f3  xor     rax, rsp
0x1800042f6  mov     [rbp+180h+var_40], rax
0x1800042fd  xor     r15d, r15d
0x180004300  lea     rax, [rsp+280h+Name]
0x180004305  mov     [r8], r15
0x180004308  mov     r14, r8
0x18000430b  mov     edx, 104h
0x180004310  mov     r9d, 7FFFFFFEh
0x180004316  test    r9, r9
0x180004319  jz      short loc_18000433A
0x18000431b  movzx   r8d, word ptr [rcx]
0x18000431f  test    r8w, r8w
0x180004323  jz      short loc_18000433A
0x180004325  mov     [rax], r8w
0x180004329  add     rcx, 2
0x18000432d  add     rax, 2
0x180004331  dec     r9
0x180004334  sub     rdx, 1; unsigned __int64
0x180004338  jnz     short loc_180004316
0x18000433a  test    rdx, rdx
0x18000433d  lea     rcx, [rax-2]
0x180004341  lea     r8, aP0; "_p0"
0x180004348  cmovnz  rcx, rax
0x18000434c  mov     [rcx], r15w
0x180004350  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004355  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000435a  mov     esi, 1F0003h
0x18000435f  lea     r8, [rsp+280h+Name]; lpName
0x180004364  mov     ecx, esi; dwDesiredAccess
0x180004366  xor     edx, edx; bInheritHandle
0x180004368  call    cs:__imp_OpenSemaphoreW
0x18000436e  mov     rbx, rax
0x180004371  test    rax, rax
0x180004374  jz      loc_180004495
0x18000437a  lea     rdx, [rsp+280h+var_25C]; int *
0x18000437f  mov     [rsp+280h+var_25C], r15d
0x180004384  mov     rcx, rax; hHandle
0x180004387  mov     [rsp+280h+var_260], r15d; int
0x18000438c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004391  mov     edi, eax
0x180004393  test    eax, eax
0x180004395  jns     short loc_1800043C3
0x180004397  mov     rcx, [rbp+188h]; this
0x18000439e  mov     r9d, eax; char *
0x1800043a1  mov     edx, 0D6h; void *
0x1800043a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043ab  mov     rcx, rbx; hObject
0x1800043ae  call    cs:__imp_CloseHandle
0x1800043b4  test    eax, eax
0x1800043b6  jz      loc_18000450A
0x1800043bc  mov     eax, edi
0x1800043be  jmp     loc_1800044B5
0x1800043c3  lea     r8, asc_1800102A8; "h"
0x1800043ca  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800043cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800043d4  lea     r8, [rsp+280h+Name]; lpName
0x1800043d9  xor     edx, edx; bInheritHandle
0x1800043db  mov     ecx, esi; dwDesiredAccess
0x1800043dd  call    cs:__imp_OpenSemaphoreW
0x1800043e3  mov     rdi, rax
0x1800043e6  test    rax, rax
0x1800043e9  jz      loc_180004470
0x1800043ef  lea     rdx, [rsp+280h+var_260]; int *
0x1800043f4  mov     rcx, rax; hHandle
0x1800043f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800043fc  mov     esi, eax
0x1800043fe  test    eax, eax
0x180004400  jns     short loc_18000443C
0x180004402  mov     rcx, [rbp+188h]; this
0x180004409  mov     r9d, eax; char *
0x18000440c  mov     edx, 0DEh; void *
0x180004411  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004416  mov     rcx, rdi; hObject
0x180004419  call    cs:__imp_CloseHandle
0x18000441f  test    eax, eax
0x180004421  jz      loc_18000451C
0x180004427  mov     rcx, rbx; hObject
0x18000442a  call    cs:__imp_CloseHandle
0x180004430  test    eax, eax
0x180004432  jz      loc_18000452E
0x180004438  mov     eax, esi
0x18000443a  jmp     short loc_1800044B5
0x18000443c  mov     rcx, rdi; hObject
0x18000443f  call    cs:__imp_CloseHandle
0x180004445  test    eax, eax
0x180004447  jz      loc_1800044D4
0x18000444d  movsxd  rax, [rsp+280h+var_25C]
0x180004452  movsxd  rcx, [rsp+280h+var_260]
0x180004457  shl     rcx, 1Fh
0x18000445b  or      rcx, rax
0x18000445e  mov     [r14], rcx
0x180004461  mov     rcx, rbx; hObject
0x180004464  call    cs:__imp_CloseHandle
0x18000446a  test    eax, eax
0x18000446c  jz      short loc_1800044E6
0x18000446e  jmp     short loc_1800044A0
0x180004470  mov     rcx, [rbp+188h]; this
0x180004477  mov     edx, 0DCh; void *
0x18000447c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004481  mov     rcx, rbx; hObject
0x180004484  mov     edi, eax
0x180004486  call    cs:__imp_CloseHandle
0x18000448c  test    eax, eax
0x18000448e  jz      short loc_1800044F8
0x180004490  jmp     loc_1800043BC
0x180004495  call    cs:__imp_GetLastError
0x18000449b  cmp     eax, 2
0x18000449e  jnz     short loc_1800044A4
0x1800044a0  xor     eax, eax
0x1800044a2  jmp     short loc_1800044B5
0x1800044a4  mov     rcx, [rbp+188h]; this
0x1800044ab  mov     edx, 0D0h; void *
0x1800044b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800044b5  mov     rcx, [rbp+180h+var_40]
0x1800044bc  xor     rcx, rsp; StackCookie
0x1800044bf  call    __security_check_cookie
0x1800044c4  add     rsp, 258h
0x1800044cb  pop     r15
0x1800044cd  pop     r14
0x1800044cf  pop     rdi
0x1800044d0  pop     rsi
0x1800044d1  pop     rbx
0x1800044d2  pop     rbp
0x1800044d3  retn
0x1800044d4  mov     rcx, [rbp+188h]; this
0x1800044db  mov     edx, 0A0Bh; void *
0x1800044e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044e6  mov     rcx, [rbp+188h]; this
0x1800044ed  mov     edx, 0A0Bh; void *
0x1800044f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044f8  mov     rcx, [rbp+188h]; this
0x1800044ff  mov     edx, 0A0Bh; void *
0x180004504  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000450a  mov     rcx, [rbp+188h]; this
0x180004511  mov     edx, 0A0Bh; void *
0x180004516  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000451c  mov     rcx, [rbp+188h]; this
0x180004523  mov     edx, 0A0Bh; void *
0x180004528  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000452e  mov     rcx, [rbp+188h]; this
0x180004535  mov     edx, 0A0Bh; void *
0x18000453a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
