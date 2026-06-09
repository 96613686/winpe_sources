# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007bac`
- end: `0x140007e3b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400039d8`
- `0x140003da8`

## callees

- `0x140001570`
- `0x140005264`
- `0x140006cc4`
- `0x140006ce4`
- `0x140007728`
- `0x140007bac`
- `0x1400083bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007c40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007cbc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007c40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007d7a`

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
0x140007bac  push    rbp
0x140007bae  push    rbx
0x140007baf  push    rsi
0x140007bb0  push    rdi
0x140007bb1  push    r14
0x140007bb3  push    r15
0x140007bb5  lea     rbp, [rsp-158h]
0x140007bbd  sub     rsp, 258h
0x140007bc4  mov     rax, cs:__security_cookie
0x140007bcb  xor     rax, rsp
0x140007bce  mov     [rbp+180h+var_40], rax
0x140007bd5  xor     r15d, r15d
0x140007bd8  lea     rax, [rsp+280h+Name]
0x140007bdd  mov     [r8], r15
0x140007be0  mov     r14, r8
0x140007be3  mov     edx, 104h
0x140007be8  mov     r9d, 7FFFFFFEh
0x140007bee  test    r9, r9
0x140007bf1  jz      short loc_140007C12
0x140007bf3  movzx   r8d, word ptr [rcx]
0x140007bf7  test    r8w, r8w
0x140007bfb  jz      short loc_140007C12
0x140007bfd  mov     [rax], r8w
0x140007c01  add     rcx, 2
0x140007c05  add     rax, 2
0x140007c09  dec     r9
0x140007c0c  sub     rdx, 1; unsigned __int64
0x140007c10  jnz     short loc_140007BEE
0x140007c12  test    rdx, rdx
0x140007c15  lea     rcx, [rax-2]
0x140007c19  lea     r8, aP0; "_p0"
0x140007c20  cmovnz  rcx, rax
0x140007c24  mov     [rcx], r15w
0x140007c28  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007c2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007c32  mov     esi, 1F0003h
0x140007c37  lea     r8, [rsp+280h+Name]; lpName
0x140007c3c  mov     ecx, esi; dwDesiredAccess
0x140007c3e  xor     edx, edx; bInheritHandle
0x140007c40  call    cs:__imp_OpenSemaphoreW
0x140007c46  mov     rbx, rax
0x140007c49  test    rax, rax
0x140007c4c  jz      loc_140007D89
0x140007c52  lea     rdx, [rsp+280h+var_25C]; int *
0x140007c57  mov     [rsp+280h+var_25C], r15d
0x140007c5c  mov     rcx, rax; hHandle
0x140007c5f  mov     [rsp+280h+var_260], r15d; int
0x140007c64  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007c69  mov     edi, eax
0x140007c6b  test    eax, eax
0x140007c6d  jns     short loc_140007CA2
0x140007c6f  mov     rcx, [rbp+188h]; this
0x140007c76  lea     r8, aWil; "wil"
0x140007c7d  mov     r9d, eax; char *
0x140007c80  mov     edx, 0D6h; void *
0x140007c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007c8a  mov     rcx, rbx; hObject
0x140007c8d  call    cs:__imp_CloseHandle
0x140007c93  test    eax, eax
0x140007c95  jz      loc_140007E05
0x140007c9b  mov     eax, edi
0x140007c9d  jmp     loc_140007DB0
0x140007ca2  lea     r8, asc_140021490; "h"
0x140007ca9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007cae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007cb3  lea     r8, [rsp+280h+Name]; lpName
0x140007cb8  xor     edx, edx; bInheritHandle
0x140007cba  mov     ecx, esi; dwDesiredAccess
0x140007cbc  call    cs:__imp_OpenSemaphoreW
0x140007cc2  mov     rdi, rax
0x140007cc5  test    rax, rax
0x140007cc8  jz      loc_140007D5D
0x140007cce  lea     rdx, [rsp+280h+var_260]; int *
0x140007cd3  mov     rcx, rax; hHandle
0x140007cd6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007cdb  mov     esi, eax
0x140007cdd  test    eax, eax
0x140007cdf  jns     short loc_140007D25
0x140007ce1  mov     rcx, [rbp+188h]; this
0x140007ce8  lea     r8, aWil; "wil"
0x140007cef  mov     r9d, eax; char *
0x140007cf2  mov     edx, 0DEh; void *
0x140007cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007cfc  mov     rcx, rdi; hObject
0x140007cff  call    cs:__imp_CloseHandle
0x140007d05  test    eax, eax
0x140007d07  jz      loc_140007E17
0x140007d0d  mov     rcx, rbx; hObject
0x140007d10  call    cs:__imp_CloseHandle
0x140007d16  test    eax, eax
0x140007d18  jz      loc_140007E29
0x140007d1e  mov     eax, esi
0x140007d20  jmp     loc_140007DB0
0x140007d25  mov     rcx, rdi; hObject
0x140007d28  call    cs:__imp_CloseHandle
0x140007d2e  test    eax, eax
0x140007d30  jz      loc_140007DCF
0x140007d36  movsxd  rax, [rsp+280h+var_25C]
0x140007d3b  movsxd  rcx, [rsp+280h+var_260]
0x140007d40  shl     rcx, 1Fh
0x140007d44  or      rcx, rax
0x140007d47  mov     [r14], rcx
0x140007d4a  mov     rcx, rbx; hObject
0x140007d4d  call    cs:__imp_CloseHandle
0x140007d53  test    eax, eax
0x140007d55  jz      loc_140007DE1
0x140007d5b  jmp     short loc_140007D94
0x140007d5d  mov     rcx, [rbp+188h]; this
0x140007d64  lea     r8, aWil; "wil"
0x140007d6b  mov     edx, 0DCh; void *
0x140007d70  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007d75  mov     rcx, rbx; hObject
0x140007d78  mov     edi, eax
0x140007d7a  call    cs:__imp_CloseHandle
0x140007d80  test    eax, eax
0x140007d82  jz      short loc_140007DF3
0x140007d84  jmp     loc_140007C9B
0x140007d89  call    cs:__imp_GetLastError
0x140007d8f  cmp     eax, 2
0x140007d92  jnz     short loc_140007D98
0x140007d94  xor     eax, eax
0x140007d96  jmp     short loc_140007DB0
0x140007d98  mov     rcx, [rbp+188h]; this
0x140007d9f  lea     r8, aWil; "wil"
0x140007da6  mov     edx, 0D0h; void *
0x140007dab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007db0  mov     rcx, [rbp+180h+var_40]
0x140007db7  xor     rcx, rsp; StackCookie
0x140007dba  call    __security_check_cookie
0x140007dbf  add     rsp, 258h
0x140007dc6  pop     r15
0x140007dc8  pop     r14
0x140007dca  pop     rdi
0x140007dcb  pop     rsi
0x140007dcc  pop     rbx
0x140007dcd  pop     rbp
0x140007dce  retn
0x140007dcf  mov     rcx, [rbp+188h]; this
0x140007dd6  mov     edx, 0A0Bh; void *
0x140007ddb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007de1  mov     rcx, [rbp+188h]; this
0x140007de8  mov     edx, 0A0Bh; void *
0x140007ded  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007df3  mov     rcx, [rbp+188h]; this
0x140007dfa  mov     edx, 0A0Bh; void *
0x140007dff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007e05  mov     rcx, [rbp+188h]; this
0x140007e0c  mov     edx, 0A0Bh; void *
0x140007e11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007e17  mov     rcx, [rbp+188h]; this
0x140007e1e  mov     edx, 0A0Bh; void *
0x140007e23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007e29  mov     rcx, [rbp+188h]; this
0x140007e30  mov     edx, 0A0Bh; void *
0x140007e35  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
