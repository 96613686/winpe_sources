# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000615c`
- end: `0x1800063eb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a68`

## callees

- `0x180001540`
- `0x180004a34`
- `0x180005514`
- `0x18000553c`
- `0x180005fcc`
- `0x18000615c`
- `0x180006740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800061f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000626c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800061f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000626c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000623d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000632a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000623d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000632a`

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
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
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
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
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
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000615c  push    rbp
0x18000615e  push    rbx
0x18000615f  push    rsi
0x180006160  push    rdi
0x180006161  push    r14
0x180006163  push    r15
0x180006165  lea     rbp, [rsp-158h]
0x18000616d  sub     rsp, 258h
0x180006174  mov     rax, cs:__security_cookie
0x18000617b  xor     rax, rsp
0x18000617e  mov     [rbp+180h+var_40], rax
0x180006185  xor     r15d, r15d
0x180006188  lea     rax, [rsp+280h+Name]
0x18000618d  mov     [r8], r15
0x180006190  mov     r14, r8
0x180006193  mov     edx, 104h
0x180006198  mov     r9d, 7FFFFFFEh
0x18000619e  test    r9, r9
0x1800061a1  jz      short loc_1800061C2
0x1800061a3  movzx   r8d, word ptr [rcx]
0x1800061a7  test    r8w, r8w
0x1800061ab  jz      short loc_1800061C2
0x1800061ad  mov     [rax], r8w
0x1800061b1  add     rcx, 2
0x1800061b5  add     rax, 2
0x1800061b9  dec     r9
0x1800061bc  sub     rdx, 1; unsigned __int64
0x1800061c0  jnz     short loc_18000619E
0x1800061c2  test    rdx, rdx
0x1800061c5  lea     rcx, [rax-2]
0x1800061c9  lea     r8, aP0; "_p0"
0x1800061d0  cmovnz  rcx, rax
0x1800061d4  mov     [rcx], r15w
0x1800061d8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800061dd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800061e2  mov     esi, 1F0003h
0x1800061e7  lea     r8, [rsp+280h+Name]; lpName
0x1800061ec  mov     ecx, esi; dwDesiredAccess
0x1800061ee  xor     edx, edx; bInheritHandle
0x1800061f0  call    cs:__imp_OpenSemaphoreW
0x1800061f6  mov     rbx, rax
0x1800061f9  test    rax, rax
0x1800061fc  jz      loc_180006339
0x180006202  lea     rdx, [rsp+280h+var_25C]; int *
0x180006207  mov     [rsp+280h+var_25C], r15d
0x18000620c  mov     rcx, rax; hHandle
0x18000620f  mov     [rsp+280h+var_260], r15d; int
0x180006214  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006219  mov     edi, eax
0x18000621b  test    eax, eax
0x18000621d  jns     short loc_180006252
0x18000621f  mov     rcx, [rbp+188h]; this
0x180006226  lea     r8, aWil; "wil"
0x18000622d  mov     r9d, eax; char *
0x180006230  mov     edx, 0D6h; void *
0x180006235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000623a  mov     rcx, rbx; hObject
0x18000623d  call    cs:__imp_CloseHandle
0x180006243  test    eax, eax
0x180006245  jz      loc_1800063B5
0x18000624b  mov     eax, edi
0x18000624d  jmp     loc_180006360
0x180006252  lea     r8, asc_180017FD0; "h"
0x180006259  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000625e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006263  lea     r8, [rsp+280h+Name]; lpName
0x180006268  xor     edx, edx; bInheritHandle
0x18000626a  mov     ecx, esi; dwDesiredAccess
0x18000626c  call    cs:__imp_OpenSemaphoreW
0x180006272  mov     rdi, rax
0x180006275  test    rax, rax
0x180006278  jz      loc_18000630D
0x18000627e  lea     rdx, [rsp+280h+var_260]; int *
0x180006283  mov     rcx, rax; hHandle
0x180006286  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000628b  mov     esi, eax
0x18000628d  test    eax, eax
0x18000628f  jns     short loc_1800062D5
0x180006291  mov     rcx, [rbp+188h]; this
0x180006298  lea     r8, aWil; "wil"
0x18000629f  mov     r9d, eax; char *
0x1800062a2  mov     edx, 0DEh; void *
0x1800062a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062ac  mov     rcx, rdi; hObject
0x1800062af  call    cs:__imp_CloseHandle
0x1800062b5  test    eax, eax
0x1800062b7  jz      loc_1800063C7
0x1800062bd  mov     rcx, rbx; hObject
0x1800062c0  call    cs:__imp_CloseHandle
0x1800062c6  test    eax, eax
0x1800062c8  jz      loc_1800063D9
0x1800062ce  mov     eax, esi
0x1800062d0  jmp     loc_180006360
0x1800062d5  mov     rcx, rdi; hObject
0x1800062d8  call    cs:__imp_CloseHandle
0x1800062de  test    eax, eax
0x1800062e0  jz      loc_18000637F
0x1800062e6  movsxd  rax, [rsp+280h+var_25C]
0x1800062eb  movsxd  rcx, [rsp+280h+var_260]
0x1800062f0  shl     rcx, 1Fh
0x1800062f4  or      rcx, rax
0x1800062f7  mov     [r14], rcx
0x1800062fa  mov     rcx, rbx; hObject
0x1800062fd  call    cs:__imp_CloseHandle
0x180006303  test    eax, eax
0x180006305  jz      loc_180006391
0x18000630b  jmp     short loc_180006344
0x18000630d  mov     rcx, [rbp+188h]; this
0x180006314  lea     r8, aWil; "wil"
0x18000631b  mov     edx, 0DCh; void *
0x180006320  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006325  mov     rcx, rbx; hObject
0x180006328  mov     edi, eax
0x18000632a  call    cs:__imp_CloseHandle
0x180006330  test    eax, eax
0x180006332  jz      short loc_1800063A3
0x180006334  jmp     loc_18000624B
0x180006339  call    cs:__imp_GetLastError
0x18000633f  cmp     eax, 2
0x180006342  jnz     short loc_180006348
0x180006344  xor     eax, eax
0x180006346  jmp     short loc_180006360
0x180006348  mov     rcx, [rbp+188h]; this
0x18000634f  lea     r8, aWil; "wil"
0x180006356  mov     edx, 0D0h; void *
0x18000635b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006360  mov     rcx, [rbp+180h+var_40]
0x180006367  xor     rcx, rsp; StackCookie
0x18000636a  call    __security_check_cookie
0x18000636f  add     rsp, 258h
0x180006376  pop     r15
0x180006378  pop     r14
0x18000637a  pop     rdi
0x18000637b  pop     rsi
0x18000637c  pop     rbx
0x18000637d  pop     rbp
0x18000637e  retn
0x18000637f  mov     rcx, [rbp+188h]; this
0x180006386  mov     edx, 0A0Bh; void *
0x18000638b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006391  mov     rcx, [rbp+188h]; this
0x180006398  mov     edx, 0A0Bh; void *
0x18000639d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063a3  mov     rcx, [rbp+188h]; this
0x1800063aa  mov     edx, 0A0Bh; void *
0x1800063af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063b5  mov     rcx, [rbp+188h]; this
0x1800063bc  mov     edx, 0A0Bh; void *
0x1800063c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063c7  mov     rcx, [rbp+188h]; this
0x1800063ce  mov     edx, 0A0Bh; void *
0x1800063d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063d9  mov     rcx, [rbp+188h]; this
0x1800063e0  mov     edx, 0A0Bh; void *
0x1800063e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
