# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000914c`
- end: `0x1800093b8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008010`

## callees

- `0x1800015b0`
- `0x180008ac0`
- `0x180008e38`
- `0x180008e58`
- `0x18000909c`
- `0x18000914c`
- `0x1800093c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000930d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000930d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800091e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009255`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800091e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092fe`

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
  __int64 v19; // r8
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
  __int64 v35; // r8
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
0x18000914c  push    rbp
0x18000914e  push    rbx
0x18000914f  push    rsi
0x180009150  push    rdi
0x180009151  push    r14
0x180009153  push    r15
0x180009155  lea     rbp, [rsp-158h]
0x18000915d  sub     rsp, 258h
0x180009164  mov     rax, cs:__security_cookie
0x18000916b  xor     rax, rsp
0x18000916e  mov     [rbp+180h+var_40], rax
0x180009175  xor     r15d, r15d
0x180009178  lea     rax, [rsp+280h+Name]
0x18000917d  mov     [r8], r15
0x180009180  mov     r14, r8
0x180009183  mov     edx, 104h
0x180009188  mov     r9d, 7FFFFFFEh
0x18000918e  test    r9, r9
0x180009191  jz      short loc_1800091B2
0x180009193  movzx   r8d, word ptr [rcx]
0x180009197  test    r8w, r8w
0x18000919b  jz      short loc_1800091B2
0x18000919d  mov     [rax], r8w
0x1800091a1  add     rcx, 2
0x1800091a5  add     rax, 2
0x1800091a9  dec     r9
0x1800091ac  sub     rdx, 1; unsigned __int64
0x1800091b0  jnz     short loc_18000918E
0x1800091b2  test    rdx, rdx
0x1800091b5  lea     rcx, [rax-2]
0x1800091b9  lea     r8, aP0; "_p0"
0x1800091c0  cmovnz  rcx, rax
0x1800091c4  mov     [rcx], r15w
0x1800091c8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800091cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800091d2  mov     esi, 1F0003h
0x1800091d7  lea     r8, [rsp+280h+Name]; lpName
0x1800091dc  mov     ecx, esi; dwDesiredAccess
0x1800091de  xor     edx, edx; bInheritHandle
0x1800091e0  call    cs:__imp_OpenSemaphoreW
0x1800091e6  mov     rbx, rax
0x1800091e9  test    rax, rax
0x1800091ec  jz      loc_18000930D
0x1800091f2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800091f7  mov     [rsp+280h+var_25C], r15d
0x1800091fc  mov     rcx, rax; hHandle
0x1800091ff  mov     [rsp+280h+var_260], r15d; int
0x180009204  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009209  mov     edi, eax
0x18000920b  test    eax, eax
0x18000920d  jns     short loc_18000923B
0x18000920f  mov     rcx, [rbp+188h]; this
0x180009216  mov     r9d, eax; char *
0x180009219  mov     edx, 0D6h; void *
0x18000921e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009223  mov     rcx, rbx; hObject
0x180009226  call    cs:__imp_CloseHandle
0x18000922c  test    eax, eax
0x18000922e  jz      loc_180009382
0x180009234  mov     eax, edi
0x180009236  jmp     loc_18000932D
0x18000923b  lea     r8, asc_18000C4B0; "h"
0x180009242  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009247  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000924c  lea     r8, [rsp+280h+Name]; lpName
0x180009251  xor     edx, edx; bInheritHandle
0x180009253  mov     ecx, esi; dwDesiredAccess
0x180009255  call    cs:__imp_OpenSemaphoreW
0x18000925b  mov     rdi, rax
0x18000925e  test    rax, rax
0x180009261  jz      loc_1800092E8
0x180009267  lea     rdx, [rsp+280h+var_260]; int *
0x18000926c  mov     rcx, rax; hHandle
0x18000926f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009274  mov     esi, eax
0x180009276  test    eax, eax
0x180009278  jns     short loc_1800092B4
0x18000927a  mov     rcx, [rbp+188h]; this
0x180009281  mov     r9d, eax; char *
0x180009284  mov     edx, 0DEh; void *
0x180009289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000928e  mov     rcx, rdi; hObject
0x180009291  call    cs:__imp_CloseHandle
0x180009297  test    eax, eax
0x180009299  jz      loc_180009394
0x18000929f  mov     rcx, rbx; hObject
0x1800092a2  call    cs:__imp_CloseHandle
0x1800092a8  test    eax, eax
0x1800092aa  jz      loc_1800093A6
0x1800092b0  mov     eax, esi
0x1800092b2  jmp     short loc_18000932D
0x1800092b4  mov     rcx, rdi; hObject
0x1800092b7  call    cs:__imp_CloseHandle
0x1800092bd  test    eax, eax
0x1800092bf  jz      loc_18000934C
0x1800092c5  movsxd  rax, [rsp+280h+var_25C]
0x1800092ca  movsxd  rcx, [rsp+280h+var_260]
0x1800092cf  shl     rcx, 1Fh
0x1800092d3  or      rcx, rax
0x1800092d6  mov     [r14], rcx
0x1800092d9  mov     rcx, rbx; hObject
0x1800092dc  call    cs:__imp_CloseHandle
0x1800092e2  test    eax, eax
0x1800092e4  jz      short loc_18000935E
0x1800092e6  jmp     short loc_180009318
0x1800092e8  mov     rcx, [rbp+188h]; this
0x1800092ef  mov     edx, 0DCh; void *
0x1800092f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800092f9  mov     rcx, rbx; hObject
0x1800092fc  mov     edi, eax
0x1800092fe  call    cs:__imp_CloseHandle
0x180009304  test    eax, eax
0x180009306  jz      short loc_180009370
0x180009308  jmp     loc_180009234
0x18000930d  call    cs:__imp_GetLastError
0x180009313  cmp     eax, 2
0x180009316  jnz     short loc_18000931C
0x180009318  xor     eax, eax
0x18000931a  jmp     short loc_18000932D
0x18000931c  mov     rcx, [rbp+188h]; this
0x180009323  mov     edx, 0D0h; void *
0x180009328  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000932d  mov     rcx, [rbp+180h+var_40]
0x180009334  xor     rcx, rsp; StackCookie
0x180009337  call    __security_check_cookie
0x18000933c  add     rsp, 258h
0x180009343  pop     r15
0x180009345  pop     r14
0x180009347  pop     rdi
0x180009348  pop     rsi
0x180009349  pop     rbx
0x18000934a  pop     rbp
0x18000934b  retn
0x18000934c  mov     rcx, [rbp+188h]; this
0x180009353  mov     edx, 0A0Bh; void *
0x180009358  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000935e  mov     rcx, [rbp+188h]; this
0x180009365  mov     edx, 0A0Bh; void *
0x18000936a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009370  mov     rcx, [rbp+188h]; this
0x180009377  mov     edx, 0A0Bh; void *
0x18000937c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009382  mov     rcx, [rbp+188h]; this
0x180009389  mov     edx, 0A0Bh; void *
0x18000938e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009394  mov     rcx, [rbp+188h]; this
0x18000939b  mov     edx, 0A0Bh; void *
0x1800093a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800093a6  mov     rcx, [rbp+188h]; this
0x1800093ad  mov     edx, 0A0Bh; void *
0x1800093b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
