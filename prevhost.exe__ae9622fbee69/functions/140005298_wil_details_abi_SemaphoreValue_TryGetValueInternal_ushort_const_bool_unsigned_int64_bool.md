# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005298`
- end: `0x140005504`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002b44`

## callees

- `0x140001470`
- `0x140003cf0`
- `0x140004d34`
- `0x140004d54`
- `0x140005000`
- `0x140005298`
- `0x14000565c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005459`
- `KERNEL32!GetLastError` at `0x140005459`
- `KERNEL32!CloseHandle` at `0x140005372`
- `KERNEL32!CloseHandle` at `0x1400053dd`
- `KERNEL32!CloseHandle` at `0x1400053ee`
- `KERNEL32!CloseHandle` at `0x140005403`
- `KERNEL32!CloseHandle` at `0x140005428`
- `KERNEL32!CloseHandle` at `0x14000544a`
- `KERNEL32!CloseHandle` at `0x140005372`
- `KERNEL32!CloseHandle` at `0x1400053dd`
- `KERNEL32!CloseHandle` at `0x1400053ee`
- `KERNEL32!CloseHandle` at `0x140005403`
- `KERNEL32!CloseHandle` at `0x140005428`
- `KERNEL32!CloseHandle` at `0x14000544a`
- `KERNEL32!OpenSemaphoreW` at `0x14000532c`
- `KERNEL32!OpenSemaphoreW` at `0x1400053a1`
- `KERNEL32!OpenSemaphoreW` at `0x14000532c`
- `KERNEL32!OpenSemaphoreW` at `0x1400053a1`

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
0x140005298  push    rbp
0x14000529a  push    rbx
0x14000529b  push    rsi
0x14000529c  push    rdi
0x14000529d  push    r14
0x14000529f  push    r15
0x1400052a1  lea     rbp, [rsp-158h]
0x1400052a9  sub     rsp, 258h
0x1400052b0  mov     rax, cs:__security_cookie
0x1400052b7  xor     rax, rsp
0x1400052ba  mov     [rbp+180h+var_40], rax
0x1400052c1  xor     r15d, r15d
0x1400052c4  lea     rax, [rsp+280h+Name]
0x1400052c9  mov     [r8], r15
0x1400052cc  mov     r14, r8
0x1400052cf  mov     edx, 104h
0x1400052d4  mov     r9d, 7FFFFFFEh
0x1400052da  test    r9, r9
0x1400052dd  jz      short loc_1400052FE
0x1400052df  movzx   r8d, word ptr [rcx]
0x1400052e3  test    r8w, r8w
0x1400052e7  jz      short loc_1400052FE
0x1400052e9  mov     [rax], r8w
0x1400052ed  add     rcx, 2
0x1400052f1  add     rax, 2
0x1400052f5  dec     r9
0x1400052f8  sub     rdx, 1; unsigned __int64
0x1400052fc  jnz     short loc_1400052DA
0x1400052fe  test    rdx, rdx
0x140005301  lea     rcx, [rax-2]
0x140005305  lea     r8, aP0; "_p0"
0x14000530c  cmovnz  rcx, rax
0x140005310  mov     [rcx], r15w
0x140005314  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005319  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000531e  mov     esi, 1F0003h
0x140005323  lea     r8, [rsp+280h+Name]; lpName
0x140005328  mov     ecx, esi; dwDesiredAccess
0x14000532a  xor     edx, edx; bInheritHandle
0x14000532c  call    cs:__imp_OpenSemaphoreW
0x140005332  mov     rbx, rax
0x140005335  test    rax, rax
0x140005338  jz      loc_140005459
0x14000533e  lea     rdx, [rsp+280h+var_25C]; int *
0x140005343  mov     [rsp+280h+var_25C], r15d
0x140005348  mov     rcx, rax; hHandle
0x14000534b  mov     [rsp+280h+var_260], r15d; int
0x140005350  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005355  mov     edi, eax
0x140005357  test    eax, eax
0x140005359  jns     short loc_140005387
0x14000535b  mov     rcx, [rbp+188h]; this
0x140005362  mov     r9d, eax; char *
0x140005365  mov     edx, 0D6h; void *
0x14000536a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000536f  mov     rcx, rbx; hObject
0x140005372  call    cs:__imp_CloseHandle
0x140005378  test    eax, eax
0x14000537a  jz      loc_1400054CE
0x140005380  mov     eax, edi
0x140005382  jmp     loc_140005479
0x140005387  lea     r8, asc_1400079A8; "h"
0x14000538e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005393  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005398  lea     r8, [rsp+280h+Name]; lpName
0x14000539d  xor     edx, edx; bInheritHandle
0x14000539f  mov     ecx, esi; dwDesiredAccess
0x1400053a1  call    cs:__imp_OpenSemaphoreW
0x1400053a7  mov     rdi, rax
0x1400053aa  test    rax, rax
0x1400053ad  jz      loc_140005434
0x1400053b3  lea     rdx, [rsp+280h+var_260]; int *
0x1400053b8  mov     rcx, rax; hHandle
0x1400053bb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400053c0  mov     esi, eax
0x1400053c2  test    eax, eax
0x1400053c4  jns     short loc_140005400
0x1400053c6  mov     rcx, [rbp+188h]; this
0x1400053cd  mov     r9d, eax; char *
0x1400053d0  mov     edx, 0DEh; void *
0x1400053d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400053da  mov     rcx, rdi; hObject
0x1400053dd  call    cs:__imp_CloseHandle
0x1400053e3  test    eax, eax
0x1400053e5  jz      loc_1400054E0
0x1400053eb  mov     rcx, rbx; hObject
0x1400053ee  call    cs:__imp_CloseHandle
0x1400053f4  test    eax, eax
0x1400053f6  jz      loc_1400054F2
0x1400053fc  mov     eax, esi
0x1400053fe  jmp     short loc_140005479
0x140005400  mov     rcx, rdi; hObject
0x140005403  call    cs:__imp_CloseHandle
0x140005409  test    eax, eax
0x14000540b  jz      loc_140005498
0x140005411  movsxd  rax, [rsp+280h+var_25C]
0x140005416  movsxd  rcx, [rsp+280h+var_260]
0x14000541b  shl     rcx, 1Fh
0x14000541f  or      rcx, rax
0x140005422  mov     [r14], rcx
0x140005425  mov     rcx, rbx; hObject
0x140005428  call    cs:__imp_CloseHandle
0x14000542e  test    eax, eax
0x140005430  jz      short loc_1400054AA
0x140005432  jmp     short loc_140005464
0x140005434  mov     rcx, [rbp+188h]; this
0x14000543b  mov     edx, 0DCh; void *
0x140005440  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005445  mov     rcx, rbx; hObject
0x140005448  mov     edi, eax
0x14000544a  call    cs:__imp_CloseHandle
0x140005450  test    eax, eax
0x140005452  jz      short loc_1400054BC
0x140005454  jmp     loc_140005380
0x140005459  call    cs:__imp_GetLastError
0x14000545f  cmp     eax, 2
0x140005462  jnz     short loc_140005468
0x140005464  xor     eax, eax
0x140005466  jmp     short loc_140005479
0x140005468  mov     rcx, [rbp+188h]; this
0x14000546f  mov     edx, 0D0h; void *
0x140005474  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005479  mov     rcx, [rbp+180h+var_40]
0x140005480  xor     rcx, rsp; StackCookie
0x140005483  call    __security_check_cookie
0x140005488  add     rsp, 258h
0x14000548f  pop     r15
0x140005491  pop     r14
0x140005493  pop     rdi
0x140005494  pop     rsi
0x140005495  pop     rbx
0x140005496  pop     rbp
0x140005497  retn
0x140005498  mov     rcx, [rbp+188h]; this
0x14000549f  mov     edx, 0A0Bh; void *
0x1400054a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400054aa  mov     rcx, [rbp+188h]; this
0x1400054b1  mov     edx, 0A0Bh; void *
0x1400054b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400054bc  mov     rcx, [rbp+188h]; this
0x1400054c3  mov     edx, 0A0Bh; void *
0x1400054c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400054ce  mov     rcx, [rbp+188h]; this
0x1400054d5  mov     edx, 0A0Bh; void *
0x1400054da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400054e0  mov     rcx, [rbp+188h]; this
0x1400054e7  mov     edx, 0A0Bh; void *
0x1400054ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400054f2  mov     rcx, [rbp+188h]; this
0x1400054f9  mov     edx, 0A0Bh; void *
0x1400054fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
