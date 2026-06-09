# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800051cc`
- end: `0x18000547f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002f5c`

## callees

- `0x180001660`
- `0x180003b38`
- `0x1800048f4`
- `0x180004914`
- `0x180005050`
- `0x1800051cc`
- `0x1800055e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005263`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052ea`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005263`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000532c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000538c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000532c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000538c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053b8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x1800051cc  push    rbp
0x1800051ce  push    rbx
0x1800051cf  push    rsi
0x1800051d0  push    rdi
0x1800051d1  push    r14
0x1800051d3  push    r15
0x1800051d5  lea     rbp, [rsp-158h]
0x1800051dd  sub     rsp, 258h
0x1800051e4  mov     rax, cs:__security_cookie
0x1800051eb  xor     rax, rsp
0x1800051ee  mov     [rbp+180h+var_40], rax
0x1800051f5  xor     r15d, r15d
0x1800051f8  lea     rax, [rsp+280h+Name]
0x1800051fd  mov     esi, 104h
0x180005202  mov     [r8], r15
0x180005205  mov     edx, esi
0x180005207  mov     r14, r8
0x18000520a  mov     r9d, 7FFFFFFEh
0x180005210  test    r9, r9
0x180005213  jz      short loc_180005234
0x180005215  movzx   r8d, word ptr [rcx]
0x180005219  test    r8w, r8w
0x18000521d  jz      short loc_180005234
0x18000521f  mov     [rax], r8w
0x180005223  add     rcx, 2
0x180005227  add     rax, 2
0x18000522b  dec     r9
0x18000522e  sub     rdx, 1
0x180005232  jnz     short loc_180005210
0x180005234  test    rdx, rdx
0x180005237  lea     rcx, [rax-2]
0x18000523b  lea     r8, aP0; "_p0"
0x180005242  mov     rdx, rsi; unsigned __int64
0x180005245  cmovnz  rcx, rax
0x180005249  mov     [rcx], r15w
0x18000524d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005252  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005257  lea     r8, [rsp+280h+Name]; lpName
0x18000525c  xor     edx, edx; bInheritHandle
0x18000525e  mov     ecx, 1F0003h; dwDesiredAccess
0x180005263  call    cs:__imp_OpenSemaphoreW
0x18000526a  nop     dword ptr [rax+rax+00h]
0x18000526f  mov     rbx, rax
0x180005272  test    rax, rax
0x180005275  jz      loc_1800053CD
0x18000527b  lea     rdx, [rsp+280h+var_25C]; int *
0x180005280  mov     [rsp+280h+var_25C], r15d
0x180005285  mov     rcx, rax; hHandle
0x180005288  mov     [rsp+280h+var_260], r15d; int
0x18000528d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005292  mov     edi, eax
0x180005294  test    eax, eax
0x180005296  jns     short loc_1800052CA
0x180005298  mov     rcx, [rbp+188h]; this
0x18000529f  mov     r9d, eax; char *
0x1800052a2  mov     edx, 0D6h; void *
0x1800052a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052ac  mov     rcx, rbx; hObject
0x1800052af  call    cs:__imp_CloseHandle
0x1800052b6  nop     dword ptr [rax+rax+00h]
0x1800052bb  test    eax, eax
0x1800052bd  jz      loc_180005449
0x1800052c3  mov     eax, edi
0x1800052c5  jmp     loc_1800053F3
0x1800052ca  lea     r8, asc_180008868; "h"
0x1800052d1  mov     rdx, rsi; unsigned __int64
0x1800052d4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800052d9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800052de  lea     r8, [rsp+280h+Name]; lpName
0x1800052e3  xor     edx, edx; bInheritHandle
0x1800052e5  mov     ecx, 1F0003h; dwDesiredAccess
0x1800052ea  call    cs:__imp_OpenSemaphoreW
0x1800052f1  nop     dword ptr [rax+rax+00h]
0x1800052f6  mov     rdi, rax
0x1800052f9  test    rax, rax
0x1800052fc  jz      loc_1800053A2
0x180005302  lea     rdx, [rsp+280h+var_260]; int *
0x180005307  mov     rcx, rax; hHandle
0x18000530a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000530f  mov     esi, eax
0x180005311  test    eax, eax
0x180005313  jns     short loc_18000535E
0x180005315  mov     rcx, [rbp+188h]; this
0x18000531c  mov     r9d, eax; char *
0x18000531f  mov     edx, 0DEh; void *
0x180005324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005329  mov     rcx, rdi; hObject
0x18000532c  call    cs:__imp_CloseHandle
0x180005333  nop     dword ptr [rax+rax+00h]
0x180005338  test    eax, eax
0x18000533a  jz      loc_18000545B
0x180005340  mov     rcx, rbx; hObject
0x180005343  call    cs:__imp_CloseHandle
0x18000534a  nop     dword ptr [rax+rax+00h]
0x18000534f  test    eax, eax
0x180005351  jz      loc_18000546D
0x180005357  mov     eax, esi
0x180005359  jmp     loc_1800053F3
0x18000535e  mov     rcx, rdi; hObject
0x180005361  call    cs:__imp_CloseHandle
0x180005368  nop     dword ptr [rax+rax+00h]
0x18000536d  test    eax, eax
0x18000536f  jz      loc_180005413
0x180005375  movsxd  rax, [rsp+280h+var_25C]
0x18000537a  movsxd  rcx, [rsp+280h+var_260]
0x18000537f  shl     rcx, 1Fh
0x180005383  or      rcx, rax
0x180005386  mov     [r14], rcx
0x180005389  mov     rcx, rbx; hObject
0x18000538c  call    cs:__imp_CloseHandle
0x180005393  nop     dword ptr [rax+rax+00h]
0x180005398  test    eax, eax
0x18000539a  jz      loc_180005425
0x1800053a0  jmp     short loc_1800053DE
0x1800053a2  mov     rcx, [rbp+188h]; this
0x1800053a9  mov     edx, 0DCh; void *
0x1800053ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800053b3  mov     rcx, rbx; hObject
0x1800053b6  mov     edi, eax
0x1800053b8  call    cs:__imp_CloseHandle
0x1800053bf  nop     dword ptr [rax+rax+00h]
0x1800053c4  test    eax, eax
0x1800053c6  jz      short loc_180005437
0x1800053c8  jmp     loc_1800052C3
0x1800053cd  call    cs:__imp_GetLastError
0x1800053d4  nop     dword ptr [rax+rax+00h]
0x1800053d9  cmp     eax, 2
0x1800053dc  jnz     short loc_1800053E2
0x1800053de  xor     eax, eax
0x1800053e0  jmp     short loc_1800053F3
0x1800053e2  mov     rcx, [rbp+188h]; this
0x1800053e9  mov     edx, 0D0h; void *
0x1800053ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800053f3  mov     rcx, [rbp+180h+var_40]
0x1800053fa  xor     rcx, rsp; StackCookie
0x1800053fd  call    __security_check_cookie
0x180005402  add     rsp, 258h
0x180005409  pop     r15
0x18000540b  pop     r14
0x18000540d  pop     rdi
0x18000540e  pop     rsi
0x18000540f  pop     rbx
0x180005410  pop     rbp
0x180005411  retn
0x180005413  mov     rcx, [rbp+188h]; this
0x18000541a  mov     edx, 0A0Bh; void *
0x18000541f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005425  mov     rcx, [rbp+188h]; this
0x18000542c  mov     edx, 0A0Bh; void *
0x180005431  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005437  mov     rcx, [rbp+188h]; this
0x18000543e  mov     edx, 0A0Bh; void *
0x180005443  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005449  mov     rcx, [rbp+188h]; this
0x180005450  mov     edx, 0A0Bh; void *
0x180005455  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000545b  mov     rcx, [rbp+188h]; this
0x180005462  mov     edx, 0A0Bh; void *
0x180005467  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000546d  mov     rcx, [rbp+188h]; this
0x180005474  mov     edx, 0A0Bh; void *
0x180005479  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
