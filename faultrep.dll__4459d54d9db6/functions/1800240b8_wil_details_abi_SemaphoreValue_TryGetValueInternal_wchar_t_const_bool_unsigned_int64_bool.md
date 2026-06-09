# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800240b8`
- end: `0x180024347`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180021234`
- `0x180021604`

## callees

- `0x180002890`
- `0x18000a9a4`
- `0x18000e30c`
- `0x1800225d8`
- `0x180023ad8`
- `0x1800240b8`
- `0x180024774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024295`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002414c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800241c8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002414c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800241c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002420b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002421c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002420b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002421c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024286`

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
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, v6, (wchar_t *)L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, (wchar_t *)L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x1800240b8  push    rbp
0x1800240ba  push    rbx
0x1800240bb  push    rsi
0x1800240bc  push    rdi
0x1800240bd  push    r14
0x1800240bf  push    r15
0x1800240c1  lea     rbp, [rsp-158h]
0x1800240c9  sub     rsp, 258h
0x1800240d0  mov     rax, cs:__security_cookie
0x1800240d7  xor     rax, rsp
0x1800240da  mov     [rbp+180h+var_40], rax
0x1800240e1  xor     r15d, r15d
0x1800240e4  lea     rax, [rsp+280h+Name]
0x1800240e9  mov     [r8], r15
0x1800240ec  mov     r14, r8
0x1800240ef  mov     edx, 104h
0x1800240f4  mov     r9d, 7FFFFFFEh
0x1800240fa  test    r9, r9
0x1800240fd  jz      short loc_18002411E
0x1800240ff  movzx   r8d, word ptr [rcx]
0x180024103  test    r8w, r8w
0x180024107  jz      short loc_18002411E
0x180024109  mov     [rax], r8w
0x18002410d  add     rcx, 2
0x180024111  add     rax, 2
0x180024115  dec     r9
0x180024118  sub     rdx, 1; unsigned __int64
0x18002411c  jnz     short loc_1800240FA
0x18002411e  test    rdx, rdx
0x180024121  lea     rcx, [rax-2]
0x180024125  lea     r8, aP0; "_p0"
0x18002412c  cmovnz  rcx, rax
0x180024130  mov     [rcx], r15w
0x180024134  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180024139  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002413e  mov     esi, 1F0003h
0x180024143  lea     r8, [rsp+280h+Name]; lpName
0x180024148  mov     ecx, esi; dwDesiredAccess
0x18002414a  xor     edx, edx; bInheritHandle
0x18002414c  call    cs:__imp_OpenSemaphoreW
0x180024152  mov     rbx, rax
0x180024155  test    rax, rax
0x180024158  jz      loc_180024295
0x18002415e  lea     rdx, [rsp+280h+var_25C]; int *
0x180024163  mov     [rsp+280h+var_25C], r15d
0x180024168  mov     rcx, rax; hHandle
0x18002416b  mov     [rsp+280h+var_260], r15d; int
0x180024170  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180024175  mov     edi, eax
0x180024177  test    eax, eax
0x180024179  jns     short loc_1800241AE
0x18002417b  mov     rcx, [rbp+188h]; this
0x180024182  lea     r8, aWil; "wil"
0x180024189  mov     r9d, eax; char *
0x18002418c  mov     edx, 0D6h; void *
0x180024191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024196  mov     rcx, rbx; hObject
0x180024199  call    cs:__imp_CloseHandle
0x18002419f  test    eax, eax
0x1800241a1  jz      loc_180024311
0x1800241a7  mov     eax, edi
0x1800241a9  jmp     loc_1800242BC
0x1800241ae  lea     r8, asc_1800538C0; "h"
0x1800241b5  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800241ba  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800241bf  lea     r8, [rsp+280h+Name]; lpName
0x1800241c4  xor     edx, edx; bInheritHandle
0x1800241c6  mov     ecx, esi; dwDesiredAccess
0x1800241c8  call    cs:__imp_OpenSemaphoreW
0x1800241ce  mov     rdi, rax
0x1800241d1  test    rax, rax
0x1800241d4  jz      loc_180024269
0x1800241da  lea     rdx, [rsp+280h+var_260]; int *
0x1800241df  mov     rcx, rax; hHandle
0x1800241e2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800241e7  mov     esi, eax
0x1800241e9  test    eax, eax
0x1800241eb  jns     short loc_180024231
0x1800241ed  mov     rcx, [rbp+188h]; this
0x1800241f4  lea     r8, aWil; "wil"
0x1800241fb  mov     r9d, eax; char *
0x1800241fe  mov     edx, 0DEh; void *
0x180024203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024208  mov     rcx, rdi; hObject
0x18002420b  call    cs:__imp_CloseHandle
0x180024211  test    eax, eax
0x180024213  jz      loc_180024323
0x180024219  mov     rcx, rbx; hObject
0x18002421c  call    cs:__imp_CloseHandle
0x180024222  test    eax, eax
0x180024224  jz      loc_180024335
0x18002422a  mov     eax, esi
0x18002422c  jmp     loc_1800242BC
0x180024231  mov     rcx, rdi; hObject
0x180024234  call    cs:__imp_CloseHandle
0x18002423a  test    eax, eax
0x18002423c  jz      loc_1800242DB
0x180024242  movsxd  rax, [rsp+280h+var_25C]
0x180024247  movsxd  rcx, [rsp+280h+var_260]
0x18002424c  shl     rcx, 1Fh
0x180024250  or      rcx, rax
0x180024253  mov     [r14], rcx
0x180024256  mov     rcx, rbx; hObject
0x180024259  call    cs:__imp_CloseHandle
0x18002425f  test    eax, eax
0x180024261  jz      loc_1800242ED
0x180024267  jmp     short loc_1800242A0
0x180024269  mov     rcx, [rbp+188h]; this
0x180024270  lea     r8, aWil; "wil"
0x180024277  mov     edx, 0DCh; void *
0x18002427c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024281  mov     rcx, rbx; hObject
0x180024284  mov     edi, eax
0x180024286  call    cs:__imp_CloseHandle
0x18002428c  test    eax, eax
0x18002428e  jz      short loc_1800242FF
0x180024290  jmp     loc_1800241A7
0x180024295  call    cs:__imp_GetLastError
0x18002429b  cmp     eax, 2
0x18002429e  jnz     short loc_1800242A4
0x1800242a0  xor     eax, eax
0x1800242a2  jmp     short loc_1800242BC
0x1800242a4  mov     rcx, [rbp+188h]; this
0x1800242ab  lea     r8, aWil; "wil"
0x1800242b2  mov     edx, 0D0h; void *
0x1800242b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800242bc  mov     rcx, [rbp+180h+var_40]
0x1800242c3  xor     rcx, rsp; StackCookie
0x1800242c6  call    __security_check_cookie
0x1800242cb  add     rsp, 258h
0x1800242d2  pop     r15
0x1800242d4  pop     r14
0x1800242d6  pop     rdi
0x1800242d7  pop     rsi
0x1800242d8  pop     rbx
0x1800242d9  pop     rbp
0x1800242da  retn
0x1800242db  mov     rcx, [rbp+188h]; this
0x1800242e2  mov     edx, 0A0Bh; void *
0x1800242e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800242ed  mov     rcx, [rbp+188h]; this
0x1800242f4  mov     edx, 0A0Bh; void *
0x1800242f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800242ff  mov     rcx, [rbp+188h]; this
0x180024306  mov     edx, 0A0Bh; void *
0x18002430b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024311  mov     rcx, [rbp+188h]; this
0x180024318  mov     edx, 0A0Bh; void *
0x18002431d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024323  mov     rcx, [rbp+188h]; this
0x18002432a  mov     edx, 0A0Bh; void *
0x18002432f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024335  mov     rcx, [rbp+188h]; this
0x18002433c  mov     edx, 0A0Bh; void *
0x180024341  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
