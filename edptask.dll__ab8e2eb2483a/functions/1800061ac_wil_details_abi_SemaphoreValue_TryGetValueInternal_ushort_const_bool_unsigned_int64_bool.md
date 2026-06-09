# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800061ac`
- end: `0x180006426`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003d40`
- `0x180007e80`

## callees

- `0x180004cb4`
- `0x1800056a4`
- `0x1800056c4`
- `0x1800060c8`
- `0x1800061ac`
- `0x1800067a0`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006240`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800062bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006240`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800062bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000637b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000637b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000628d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000634a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000636c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000628d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000634a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000636c`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x1800061ac  push    rbp
0x1800061ae  push    rbx
0x1800061af  push    rsi
0x1800061b0  push    rdi
0x1800061b1  push    r14
0x1800061b3  push    r15
0x1800061b5  lea     rbp, [rsp-158h]
0x1800061bd  sub     rsp, 258h
0x1800061c4  mov     rax, cs:__security_cookie
0x1800061cb  xor     rax, rsp
0x1800061ce  mov     [rbp+180h+var_40], rax
0x1800061d5  xor     r15d, r15d
0x1800061d8  lea     rax, [rsp+280h+Name]
0x1800061dd  mov     [r8], r15
0x1800061e0  mov     r14, r8
0x1800061e3  mov     edx, 104h
0x1800061e8  mov     r9d, 7FFFFFFEh
0x1800061ee  test    r9, r9
0x1800061f1  jz      short loc_180006212
0x1800061f3  movzx   r8d, word ptr [rcx]
0x1800061f7  test    r8w, r8w
0x1800061fb  jz      short loc_180006212
0x1800061fd  mov     [rax], r8w
0x180006201  add     rcx, 2
0x180006205  add     rax, 2
0x180006209  dec     r9
0x18000620c  sub     rdx, 1; unsigned __int64
0x180006210  jnz     short loc_1800061EE
0x180006212  test    rdx, rdx
0x180006215  lea     rcx, [rax-2]
0x180006219  lea     r8, aP0; "_p0"
0x180006220  cmovnz  rcx, rax
0x180006224  mov     [rcx], r15w
0x180006228  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000622d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006232  mov     esi, 1F0003h
0x180006237  lea     r8, [rsp+280h+Name]; lpName
0x18000623c  mov     ecx, esi; dwDesiredAccess
0x18000623e  xor     edx, edx; bInheritHandle
0x180006240  call    cs:__imp_OpenSemaphoreW
0x180006246  mov     rbx, rax
0x180006249  test    rax, rax
0x18000624c  jz      loc_18000637B
0x180006252  lea     rdx, [rsp+280h+var_25C]; int *
0x180006257  mov     [rsp+280h+var_25C], r15d
0x18000625c  mov     rcx, rax; hHandle
0x18000625f  mov     [rsp+280h+var_260], r15d; int
0x180006264  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006269  mov     edi, eax
0x18000626b  test    eax, eax
0x18000626d  jns     short loc_1800062A2
0x18000626f  mov     rcx, [rbp+188h]; this
0x180006276  lea     r8, aWil; "wil"
0x18000627d  mov     r9d, eax; char *
0x180006280  mov     edx, 0D6h; void *
0x180006285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000628a  mov     rcx, rbx; hObject
0x18000628d  call    cs:__imp_CloseHandle
0x180006293  test    eax, eax
0x180006295  jz      loc_1800063F0
0x18000629b  mov     eax, edi
0x18000629d  jmp     loc_18000639B
0x1800062a2  lea     r8, asc_180017B10; "h"
0x1800062a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800062ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800062b3  lea     r8, [rsp+280h+Name]; lpName
0x1800062b8  xor     edx, edx; bInheritHandle
0x1800062ba  mov     ecx, esi; dwDesiredAccess
0x1800062bc  call    cs:__imp_OpenSemaphoreW
0x1800062c2  mov     rdi, rax
0x1800062c5  test    rax, rax
0x1800062c8  jz      loc_180006356
0x1800062ce  lea     rdx, [rsp+280h+var_260]; int *
0x1800062d3  mov     rcx, rax; hHandle
0x1800062d6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800062db  mov     esi, eax
0x1800062dd  test    eax, eax
0x1800062df  jns     short loc_180006322
0x1800062e1  mov     rcx, [rbp+188h]; this
0x1800062e8  lea     r8, aWil; "wil"
0x1800062ef  mov     r9d, eax; char *
0x1800062f2  mov     edx, 0DEh; void *
0x1800062f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062fc  mov     rcx, rdi; hObject
0x1800062ff  call    cs:__imp_CloseHandle
0x180006305  test    eax, eax
0x180006307  jz      loc_180006402
0x18000630d  mov     rcx, rbx; hObject
0x180006310  call    cs:__imp_CloseHandle
0x180006316  test    eax, eax
0x180006318  jz      loc_180006414
0x18000631e  mov     eax, esi
0x180006320  jmp     short loc_18000639B
0x180006322  mov     rcx, rdi; hObject
0x180006325  call    cs:__imp_CloseHandle
0x18000632b  test    eax, eax
0x18000632d  jz      loc_1800063BA
0x180006333  movsxd  rax, [rsp+280h+var_25C]
0x180006338  movsxd  rcx, [rsp+280h+var_260]
0x18000633d  shl     rcx, 1Fh
0x180006341  or      rcx, rax
0x180006344  mov     [r14], rcx
0x180006347  mov     rcx, rbx; hObject
0x18000634a  call    cs:__imp_CloseHandle
0x180006350  test    eax, eax
0x180006352  jz      short loc_1800063CC
0x180006354  jmp     short loc_180006386
0x180006356  mov     rcx, [rbp+188h]; this
0x18000635d  mov     edx, 0DCh; void *
0x180006362  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006367  mov     rcx, rbx; hObject
0x18000636a  mov     edi, eax
0x18000636c  call    cs:__imp_CloseHandle
0x180006372  test    eax, eax
0x180006374  jz      short loc_1800063DE
0x180006376  jmp     loc_18000629B
0x18000637b  call    cs:__imp_GetLastError
0x180006381  cmp     eax, 2
0x180006384  jnz     short loc_18000638A
0x180006386  xor     eax, eax
0x180006388  jmp     short loc_18000639B
0x18000638a  mov     rcx, [rbp+188h]; this
0x180006391  mov     edx, 0D0h; void *
0x180006396  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000639b  mov     rcx, [rbp+180h+var_40]
0x1800063a2  xor     rcx, rsp; StackCookie
0x1800063a5  call    __security_check_cookie
0x1800063aa  add     rsp, 258h
0x1800063b1  pop     r15
0x1800063b3  pop     r14
0x1800063b5  pop     rdi
0x1800063b6  pop     rsi
0x1800063b7  pop     rbx
0x1800063b8  pop     rbp
0x1800063b9  retn
0x1800063ba  mov     rcx, [rbp+188h]; this
0x1800063c1  mov     edx, 0A0Bh; void *
0x1800063c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063cc  mov     rcx, [rbp+188h]; this
0x1800063d3  mov     edx, 0A0Bh; void *
0x1800063d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063de  mov     rcx, [rbp+188h]; this
0x1800063e5  mov     edx, 0A0Bh; void *
0x1800063ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063f0  mov     rcx, [rbp+188h]; this
0x1800063f7  mov     edx, 0A0Bh; void *
0x1800063fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006402  mov     rcx, [rbp+188h]; this
0x180006409  mov     edx, 0A0Bh; void *
0x18000640e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006414  mov     rcx, [rbp+188h]; this
0x18000641b  mov     edx, 0A0Bh; void *
0x180006420  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
