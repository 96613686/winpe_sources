# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140009124`
- end: `0x140009390`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003ecc`

## callees

- `0x140001fa0`
- `0x140005f2c`
- `0x140007d3c`
- `0x140007d5c`
- `0x140008ec8`
- `0x140009124`
- `0x140009a2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400092e5`
- `KERNEL32!GetLastError` at `0x1400092e5`
- `KERNEL32!CloseHandle` at `0x1400091fe`
- `KERNEL32!CloseHandle` at `0x140009269`
- `KERNEL32!CloseHandle` at `0x14000927a`
- `KERNEL32!CloseHandle` at `0x14000928f`
- `KERNEL32!CloseHandle` at `0x1400092b4`
- `KERNEL32!CloseHandle` at `0x1400092d6`
- `KERNEL32!CloseHandle` at `0x1400091fe`
- `KERNEL32!CloseHandle` at `0x140009269`
- `KERNEL32!CloseHandle` at `0x14000927a`
- `KERNEL32!CloseHandle` at `0x14000928f`
- `KERNEL32!CloseHandle` at `0x1400092b4`
- `KERNEL32!CloseHandle` at `0x1400092d6`
- `KERNEL32!OpenSemaphoreW` at `0x1400091b8`
- `KERNEL32!OpenSemaphoreW` at `0x14000922d`
- `KERNEL32!OpenSemaphoreW` at `0x1400091b8`
- `KERNEL32!OpenSemaphoreW` at `0x14000922d`

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
0x140009124  push    rbp
0x140009126  push    rbx
0x140009127  push    rsi
0x140009128  push    rdi
0x140009129  push    r14
0x14000912b  push    r15
0x14000912d  lea     rbp, [rsp-158h]
0x140009135  sub     rsp, 258h
0x14000913c  mov     rax, cs:__security_cookie
0x140009143  xor     rax, rsp
0x140009146  mov     [rbp+180h+var_40], rax
0x14000914d  xor     r15d, r15d
0x140009150  lea     rax, [rsp+280h+Name]
0x140009155  mov     [r8], r15
0x140009158  mov     r14, r8
0x14000915b  mov     edx, 104h
0x140009160  mov     r9d, 7FFFFFFEh
0x140009166  test    r9, r9
0x140009169  jz      short loc_14000918A
0x14000916b  movzx   r8d, word ptr [rcx]
0x14000916f  test    r8w, r8w
0x140009173  jz      short loc_14000918A
0x140009175  mov     [rax], r8w
0x140009179  add     rcx, 2
0x14000917d  add     rax, 2
0x140009181  dec     r9
0x140009184  sub     rdx, 1; unsigned __int64
0x140009188  jnz     short loc_140009166
0x14000918a  test    rdx, rdx
0x14000918d  lea     rcx, [rax-2]
0x140009191  lea     r8, aP0; "_p0"
0x140009198  cmovnz  rcx, rax
0x14000919c  mov     [rcx], r15w
0x1400091a0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400091a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400091aa  mov     esi, 1F0003h
0x1400091af  lea     r8, [rsp+280h+Name]; lpName
0x1400091b4  mov     ecx, esi; dwDesiredAccess
0x1400091b6  xor     edx, edx; bInheritHandle
0x1400091b8  call    cs:__imp_OpenSemaphoreW
0x1400091be  mov     rbx, rax
0x1400091c1  test    rax, rax
0x1400091c4  jz      loc_1400092E5
0x1400091ca  lea     rdx, [rsp+280h+var_25C]; int *
0x1400091cf  mov     [rsp+280h+var_25C], r15d
0x1400091d4  mov     rcx, rax; hHandle
0x1400091d7  mov     [rsp+280h+var_260], r15d; int
0x1400091dc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400091e1  mov     edi, eax
0x1400091e3  test    eax, eax
0x1400091e5  jns     short loc_140009213
0x1400091e7  mov     rcx, [rbp+188h]; this
0x1400091ee  mov     r9d, eax; char *
0x1400091f1  mov     edx, 0D6h; void *
0x1400091f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091fb  mov     rcx, rbx; hObject
0x1400091fe  call    cs:__imp_CloseHandle
0x140009204  test    eax, eax
0x140009206  jz      loc_14000935A
0x14000920c  mov     eax, edi
0x14000920e  jmp     loc_140009305
0x140009213  lea     r8, asc_140012488; "h"
0x14000921a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000921f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009224  lea     r8, [rsp+280h+Name]; lpName
0x140009229  xor     edx, edx; bInheritHandle
0x14000922b  mov     ecx, esi; dwDesiredAccess
0x14000922d  call    cs:__imp_OpenSemaphoreW
0x140009233  mov     rdi, rax
0x140009236  test    rax, rax
0x140009239  jz      loc_1400092C0
0x14000923f  lea     rdx, [rsp+280h+var_260]; int *
0x140009244  mov     rcx, rax; hHandle
0x140009247  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000924c  mov     esi, eax
0x14000924e  test    eax, eax
0x140009250  jns     short loc_14000928C
0x140009252  mov     rcx, [rbp+188h]; this
0x140009259  mov     r9d, eax; char *
0x14000925c  mov     edx, 0DEh; void *
0x140009261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009266  mov     rcx, rdi; hObject
0x140009269  call    cs:__imp_CloseHandle
0x14000926f  test    eax, eax
0x140009271  jz      loc_14000936C
0x140009277  mov     rcx, rbx; hObject
0x14000927a  call    cs:__imp_CloseHandle
0x140009280  test    eax, eax
0x140009282  jz      loc_14000937E
0x140009288  mov     eax, esi
0x14000928a  jmp     short loc_140009305
0x14000928c  mov     rcx, rdi; hObject
0x14000928f  call    cs:__imp_CloseHandle
0x140009295  test    eax, eax
0x140009297  jz      loc_140009324
0x14000929d  movsxd  rax, [rsp+280h+var_25C]
0x1400092a2  movsxd  rcx, [rsp+280h+var_260]
0x1400092a7  shl     rcx, 1Fh
0x1400092ab  or      rcx, rax
0x1400092ae  mov     [r14], rcx
0x1400092b1  mov     rcx, rbx; hObject
0x1400092b4  call    cs:__imp_CloseHandle
0x1400092ba  test    eax, eax
0x1400092bc  jz      short loc_140009336
0x1400092be  jmp     short loc_1400092F0
0x1400092c0  mov     rcx, [rbp+188h]; this
0x1400092c7  mov     edx, 0DCh; void *
0x1400092cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400092d1  mov     rcx, rbx; hObject
0x1400092d4  mov     edi, eax
0x1400092d6  call    cs:__imp_CloseHandle
0x1400092dc  test    eax, eax
0x1400092de  jz      short loc_140009348
0x1400092e0  jmp     loc_14000920C
0x1400092e5  call    cs:__imp_GetLastError
0x1400092eb  cmp     eax, 2
0x1400092ee  jnz     short loc_1400092F4
0x1400092f0  xor     eax, eax
0x1400092f2  jmp     short loc_140009305
0x1400092f4  mov     rcx, [rbp+188h]; this
0x1400092fb  mov     edx, 0D0h; void *
0x140009300  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009305  mov     rcx, [rbp+180h+var_40]
0x14000930c  xor     rcx, rsp; StackCookie
0x14000930f  call    __security_check_cookie
0x140009314  add     rsp, 258h
0x14000931b  pop     r15
0x14000931d  pop     r14
0x14000931f  pop     rdi
0x140009320  pop     rsi
0x140009321  pop     rbx
0x140009322  pop     rbp
0x140009323  retn
0x140009324  mov     rcx, [rbp+188h]; this
0x14000932b  mov     edx, 0A0Bh; void *
0x140009330  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009336  mov     rcx, [rbp+188h]; this
0x14000933d  mov     edx, 0A0Bh; void *
0x140009342  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009348  mov     rcx, [rbp+188h]; this
0x14000934f  mov     edx, 0A0Bh; void *
0x140009354  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000935a  mov     rcx, [rbp+188h]; this
0x140009361  mov     edx, 0A0Bh; void *
0x140009366  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000936c  mov     rcx, [rbp+188h]; this
0x140009373  mov     edx, 0A0Bh; void *
0x140009378  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000937e  mov     rcx, [rbp+188h]; this
0x140009385  mov     edx, 0A0Bh; void *
0x14000938a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
