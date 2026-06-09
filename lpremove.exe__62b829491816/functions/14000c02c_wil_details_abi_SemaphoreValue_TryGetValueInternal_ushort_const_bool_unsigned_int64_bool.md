# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000c02c`
- end: `0x14000c2a6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005ce8`
- `0x1400060b8`

## callees

- `0x140002190`
- `0x140007b84`
- `0x14000a8f4`
- `0x14000a914`
- `0x14000bc1c`
- `0x14000c02c`
- `0x14000cdfc`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x14000c0c0`
- `KERNEL32!OpenSemaphoreW` at `0x14000c13c`
- `KERNEL32!OpenSemaphoreW` at `0x14000c0c0`
- `KERNEL32!OpenSemaphoreW` at `0x14000c13c`
- `KERNEL32!CloseHandle` at `0x14000c10d`
- `KERNEL32!CloseHandle` at `0x14000c17f`
- `KERNEL32!CloseHandle` at `0x14000c190`
- `KERNEL32!CloseHandle` at `0x14000c1a5`
- `KERNEL32!CloseHandle` at `0x14000c1ca`
- `KERNEL32!CloseHandle` at `0x14000c1ec`
- `KERNEL32!CloseHandle` at `0x14000c10d`
- `KERNEL32!CloseHandle` at `0x14000c17f`
- `KERNEL32!CloseHandle` at `0x14000c190`
- `KERNEL32!CloseHandle` at `0x14000c1a5`
- `KERNEL32!CloseHandle` at `0x14000c1ca`
- `KERNEL32!CloseHandle` at `0x14000c1ec`
- `KERNEL32!GetLastError` at `0x14000c1fb`
- `KERNEL32!GetLastError` at `0x14000c1fb`

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
0x14000c02c  push    rbp
0x14000c02e  push    rbx
0x14000c02f  push    rsi
0x14000c030  push    rdi
0x14000c031  push    r14
0x14000c033  push    r15
0x14000c035  lea     rbp, [rsp-158h]
0x14000c03d  sub     rsp, 258h
0x14000c044  mov     rax, cs:__security_cookie
0x14000c04b  xor     rax, rsp
0x14000c04e  mov     [rbp+180h+var_40], rax
0x14000c055  xor     r15d, r15d
0x14000c058  lea     rax, [rsp+280h+Name]
0x14000c05d  mov     [r8], r15
0x14000c060  mov     r14, r8
0x14000c063  mov     edx, 104h
0x14000c068  mov     r9d, 7FFFFFFEh
0x14000c06e  test    r9, r9
0x14000c071  jz      short loc_14000C092
0x14000c073  movzx   r8d, word ptr [rcx]
0x14000c077  test    r8w, r8w
0x14000c07b  jz      short loc_14000C092
0x14000c07d  mov     [rax], r8w
0x14000c081  add     rcx, 2
0x14000c085  add     rax, 2
0x14000c089  dec     r9
0x14000c08c  sub     rdx, 1; unsigned __int64
0x14000c090  jnz     short loc_14000C06E
0x14000c092  test    rdx, rdx
0x14000c095  lea     rcx, [rax-2]
0x14000c099  lea     r8, aP0; "_p0"
0x14000c0a0  cmovnz  rcx, rax
0x14000c0a4  mov     [rcx], r15w
0x14000c0a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c0ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c0b2  mov     esi, 1F0003h
0x14000c0b7  lea     r8, [rsp+280h+Name]; lpName
0x14000c0bc  mov     ecx, esi; dwDesiredAccess
0x14000c0be  xor     edx, edx; bInheritHandle
0x14000c0c0  call    cs:__imp_OpenSemaphoreW
0x14000c0c6  mov     rbx, rax
0x14000c0c9  test    rax, rax
0x14000c0cc  jz      loc_14000C1FB
0x14000c0d2  lea     rdx, [rsp+280h+var_25C]; int *
0x14000c0d7  mov     [rsp+280h+var_25C], r15d
0x14000c0dc  mov     rcx, rax; hHandle
0x14000c0df  mov     [rsp+280h+var_260], r15d; int
0x14000c0e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c0e9  mov     edi, eax
0x14000c0eb  test    eax, eax
0x14000c0ed  jns     short loc_14000C122
0x14000c0ef  mov     rcx, [rbp+188h]; this
0x14000c0f6  lea     r8, aWil; "wil"
0x14000c0fd  mov     r9d, eax; char *
0x14000c100  mov     edx, 0D6h; void *
0x14000c105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c10a  mov     rcx, rbx; hObject
0x14000c10d  call    cs:__imp_CloseHandle
0x14000c113  test    eax, eax
0x14000c115  jz      loc_14000C270
0x14000c11b  mov     eax, edi
0x14000c11d  jmp     loc_14000C21B
0x14000c122  lea     r8, asc_140013250; "h"
0x14000c129  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c12e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c133  lea     r8, [rsp+280h+Name]; lpName
0x14000c138  xor     edx, edx; bInheritHandle
0x14000c13a  mov     ecx, esi; dwDesiredAccess
0x14000c13c  call    cs:__imp_OpenSemaphoreW
0x14000c142  mov     rdi, rax
0x14000c145  test    rax, rax
0x14000c148  jz      loc_14000C1D6
0x14000c14e  lea     rdx, [rsp+280h+var_260]; int *
0x14000c153  mov     rcx, rax; hHandle
0x14000c156  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c15b  mov     esi, eax
0x14000c15d  test    eax, eax
0x14000c15f  jns     short loc_14000C1A2
0x14000c161  mov     rcx, [rbp+188h]; this
0x14000c168  lea     r8, aWil; "wil"
0x14000c16f  mov     r9d, eax; char *
0x14000c172  mov     edx, 0DEh; void *
0x14000c177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c17c  mov     rcx, rdi; hObject
0x14000c17f  call    cs:__imp_CloseHandle
0x14000c185  test    eax, eax
0x14000c187  jz      loc_14000C282
0x14000c18d  mov     rcx, rbx; hObject
0x14000c190  call    cs:__imp_CloseHandle
0x14000c196  test    eax, eax
0x14000c198  jz      loc_14000C294
0x14000c19e  mov     eax, esi
0x14000c1a0  jmp     short loc_14000C21B
0x14000c1a2  mov     rcx, rdi; hObject
0x14000c1a5  call    cs:__imp_CloseHandle
0x14000c1ab  test    eax, eax
0x14000c1ad  jz      loc_14000C23A
0x14000c1b3  movsxd  rax, [rsp+280h+var_25C]
0x14000c1b8  movsxd  rcx, [rsp+280h+var_260]
0x14000c1bd  shl     rcx, 1Fh
0x14000c1c1  or      rcx, rax
0x14000c1c4  mov     [r14], rcx
0x14000c1c7  mov     rcx, rbx; hObject
0x14000c1ca  call    cs:__imp_CloseHandle
0x14000c1d0  test    eax, eax
0x14000c1d2  jz      short loc_14000C24C
0x14000c1d4  jmp     short loc_14000C206
0x14000c1d6  mov     rcx, [rbp+188h]; this
0x14000c1dd  mov     edx, 0DCh; void *
0x14000c1e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c1e7  mov     rcx, rbx; hObject
0x14000c1ea  mov     edi, eax
0x14000c1ec  call    cs:__imp_CloseHandle
0x14000c1f2  test    eax, eax
0x14000c1f4  jz      short loc_14000C25E
0x14000c1f6  jmp     loc_14000C11B
0x14000c1fb  call    cs:__imp_GetLastError
0x14000c201  cmp     eax, 2
0x14000c204  jnz     short loc_14000C20A
0x14000c206  xor     eax, eax
0x14000c208  jmp     short loc_14000C21B
0x14000c20a  mov     rcx, [rbp+188h]; this
0x14000c211  mov     edx, 0D0h; void *
0x14000c216  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c21b  mov     rcx, [rbp+180h+var_40]
0x14000c222  xor     rcx, rsp; StackCookie
0x14000c225  call    __security_check_cookie
0x14000c22a  add     rsp, 258h
0x14000c231  pop     r15
0x14000c233  pop     r14
0x14000c235  pop     rdi
0x14000c236  pop     rsi
0x14000c237  pop     rbx
0x14000c238  pop     rbp
0x14000c239  retn
0x14000c23a  mov     rcx, [rbp+188h]; this
0x14000c241  mov     edx, 0A0Bh; void *
0x14000c246  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c24c  mov     rcx, [rbp+188h]; this
0x14000c253  mov     edx, 0A0Bh; void *
0x14000c258  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c25e  mov     rcx, [rbp+188h]; this
0x14000c265  mov     edx, 0A0Bh; void *
0x14000c26a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c270  mov     rcx, [rbp+188h]; this
0x14000c277  mov     edx, 0A0Bh; void *
0x14000c27c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c282  mov     rcx, [rbp+188h]; this
0x14000c289  mov     edx, 0A0Bh; void *
0x14000c28e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c294  mov     rcx, [rbp+188h]; this
0x14000c29b  mov     edx, 0A0Bh; void *
0x14000c2a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
