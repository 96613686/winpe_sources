# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800083c0`
- end: `0x18000862c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b74`
- `0x180003f18`

## callees

- `0x180001670`
- `0x180005460`
- `0x180007aa4`
- `0x180007ac4`
- `0x180007edc`
- `0x1800083c0`
- `0x180008c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008581`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008454`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800084c9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008454`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800084c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000849a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000852b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000849a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000852b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008572`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x1800083c0  push    rbp
0x1800083c2  push    rbx
0x1800083c3  push    rsi
0x1800083c4  push    rdi
0x1800083c5  push    r14
0x1800083c7  push    r15
0x1800083c9  lea     rbp, [rsp-158h]
0x1800083d1  sub     rsp, 258h
0x1800083d8  mov     rax, cs:__security_cookie
0x1800083df  xor     rax, rsp
0x1800083e2  mov     [rbp+180h+var_40], rax
0x1800083e9  xor     r15d, r15d
0x1800083ec  lea     rax, [rsp+280h+Name]
0x1800083f1  mov     [r8], r15
0x1800083f4  mov     r14, r8
0x1800083f7  mov     edx, 104h
0x1800083fc  mov     r9d, 7FFFFFFEh
0x180008402  test    r9, r9
0x180008405  jz      short loc_180008426
0x180008407  movzx   r8d, word ptr [rcx]
0x18000840b  test    r8w, r8w
0x18000840f  jz      short loc_180008426
0x180008411  mov     [rax], r8w
0x180008415  add     rcx, 2
0x180008419  add     rax, 2
0x18000841d  dec     r9
0x180008420  sub     rdx, 1; unsigned __int64
0x180008424  jnz     short loc_180008402
0x180008426  test    rdx, rdx
0x180008429  lea     rcx, [rax-2]
0x18000842d  lea     r8, aP0; "_p0"
0x180008434  cmovnz  rcx, rax
0x180008438  mov     [rcx], r15w
0x18000843c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008441  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008446  mov     esi, 1F0003h
0x18000844b  lea     r8, [rsp+280h+Name]; lpName
0x180008450  mov     ecx, esi; dwDesiredAccess
0x180008452  xor     edx, edx; bInheritHandle
0x180008454  call    cs:__imp_OpenSemaphoreW
0x18000845a  mov     rbx, rax
0x18000845d  test    rax, rax
0x180008460  jz      loc_180008581
0x180008466  lea     rdx, [rsp+280h+var_25C]; int *
0x18000846b  mov     [rsp+280h+var_25C], r15d
0x180008470  mov     rcx, rax; hHandle
0x180008473  mov     [rsp+280h+var_260], r15d; int
0x180008478  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000847d  mov     edi, eax
0x18000847f  test    eax, eax
0x180008481  jns     short loc_1800084AF
0x180008483  mov     rcx, [rbp+188h]; this
0x18000848a  mov     r9d, eax; char *
0x18000848d  mov     edx, 0D6h; void *
0x180008492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008497  mov     rcx, rbx; hObject
0x18000849a  call    cs:__imp_CloseHandle
0x1800084a0  test    eax, eax
0x1800084a2  jz      loc_1800085F6
0x1800084a8  mov     eax, edi
0x1800084aa  jmp     loc_1800085A1
0x1800084af  lea     r8, asc_18003DBA0; "h"
0x1800084b6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800084bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800084c0  lea     r8, [rsp+280h+Name]; lpName
0x1800084c5  xor     edx, edx; bInheritHandle
0x1800084c7  mov     ecx, esi; dwDesiredAccess
0x1800084c9  call    cs:__imp_OpenSemaphoreW
0x1800084cf  mov     rdi, rax
0x1800084d2  test    rax, rax
0x1800084d5  jz      loc_18000855C
0x1800084db  lea     rdx, [rsp+280h+var_260]; int *
0x1800084e0  mov     rcx, rax; hHandle
0x1800084e3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800084e8  mov     esi, eax
0x1800084ea  test    eax, eax
0x1800084ec  jns     short loc_180008528
0x1800084ee  mov     rcx, [rbp+188h]; this
0x1800084f5  mov     r9d, eax; char *
0x1800084f8  mov     edx, 0DEh; void *
0x1800084fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008502  mov     rcx, rdi; hObject
0x180008505  call    cs:__imp_CloseHandle
0x18000850b  test    eax, eax
0x18000850d  jz      loc_180008608
0x180008513  mov     rcx, rbx; hObject
0x180008516  call    cs:__imp_CloseHandle
0x18000851c  test    eax, eax
0x18000851e  jz      loc_18000861A
0x180008524  mov     eax, esi
0x180008526  jmp     short loc_1800085A1
0x180008528  mov     rcx, rdi; hObject
0x18000852b  call    cs:__imp_CloseHandle
0x180008531  test    eax, eax
0x180008533  jz      loc_1800085C0
0x180008539  movsxd  rax, [rsp+280h+var_25C]
0x18000853e  movsxd  rcx, [rsp+280h+var_260]
0x180008543  shl     rcx, 1Fh
0x180008547  or      rcx, rax
0x18000854a  mov     [r14], rcx
0x18000854d  mov     rcx, rbx; hObject
0x180008550  call    cs:__imp_CloseHandle
0x180008556  test    eax, eax
0x180008558  jz      short loc_1800085D2
0x18000855a  jmp     short loc_18000858C
0x18000855c  mov     rcx, [rbp+188h]; this
0x180008563  mov     edx, 0DCh; void *
0x180008568  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000856d  mov     rcx, rbx; hObject
0x180008570  mov     edi, eax
0x180008572  call    cs:__imp_CloseHandle
0x180008578  test    eax, eax
0x18000857a  jz      short loc_1800085E4
0x18000857c  jmp     loc_1800084A8
0x180008581  call    cs:__imp_GetLastError
0x180008587  cmp     eax, 2
0x18000858a  jnz     short loc_180008590
0x18000858c  xor     eax, eax
0x18000858e  jmp     short loc_1800085A1
0x180008590  mov     rcx, [rbp+188h]; this
0x180008597  mov     edx, 0D0h; void *
0x18000859c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800085a1  mov     rcx, [rbp+180h+var_40]
0x1800085a8  xor     rcx, rsp; StackCookie
0x1800085ab  call    __security_check_cookie
0x1800085b0  add     rsp, 258h
0x1800085b7  pop     r15
0x1800085b9  pop     r14
0x1800085bb  pop     rdi
0x1800085bc  pop     rsi
0x1800085bd  pop     rbx
0x1800085be  pop     rbp
0x1800085bf  retn
0x1800085c0  mov     rcx, [rbp+188h]; this
0x1800085c7  mov     edx, 0A0Bh; void *
0x1800085cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085d2  mov     rcx, [rbp+188h]; this
0x1800085d9  mov     edx, 0A0Bh; void *
0x1800085de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085e4  mov     rcx, [rbp+188h]; this
0x1800085eb  mov     edx, 0A0Bh; void *
0x1800085f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800085f6  mov     rcx, [rbp+188h]; this
0x1800085fd  mov     edx, 0A0Bh; void *
0x180008602  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008608  mov     rcx, [rbp+188h]; this
0x18000860f  mov     edx, 0A0Bh; void *
0x180008614  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000861a  mov     rcx, [rbp+188h]; this
0x180008621  mov     edx, 0A0Bh; void *
0x180008626  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
