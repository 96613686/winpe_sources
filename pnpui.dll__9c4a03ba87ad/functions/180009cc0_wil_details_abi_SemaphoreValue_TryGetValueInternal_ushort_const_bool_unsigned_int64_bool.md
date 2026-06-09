# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009cc0`
- end: `0x180009f35`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d1c`
- `0x1800050c0`

## callees

- `0x180003550`
- `0x180006d6c`
- `0x180009534`
- `0x180009554`
- `0x180009cc0`
- `0x18000a57c`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e8a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009d57`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009dd2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009d57`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e7b`

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
0x180009cc0  push    rbp
0x180009cc2  push    rbx
0x180009cc3  push    rsi
0x180009cc4  push    rdi
0x180009cc5  push    r14
0x180009cc7  push    r15
0x180009cc9  lea     rbp, [rsp-158h]
0x180009cd1  sub     rsp, 258h
0x180009cd8  mov     rax, cs:__security_cookie
0x180009cdf  xor     rax, rsp
0x180009ce2  mov     [rbp+180h+var_40], rax
0x180009ce9  xor     r15d, r15d
0x180009cec  lea     rax, [rsp+280h+Name]
0x180009cf1  mov     esi, 104h
0x180009cf6  mov     [r8], r15
0x180009cf9  mov     edx, esi
0x180009cfb  mov     r14, r8
0x180009cfe  mov     r9d, 7FFFFFFEh
0x180009d04  test    r9, r9
0x180009d07  jz      short loc_180009D28
0x180009d09  movzx   r8d, word ptr [rcx]
0x180009d0d  test    r8w, r8w
0x180009d11  jz      short loc_180009D28
0x180009d13  mov     [rax], r8w
0x180009d17  add     rcx, 2
0x180009d1b  add     rax, 2
0x180009d1f  dec     r9
0x180009d22  sub     rdx, 1
0x180009d26  jnz     short loc_180009D04
0x180009d28  test    rdx, rdx
0x180009d2b  lea     rcx, [rax-2]
0x180009d2f  lea     r8, aP0; "_p0"
0x180009d36  mov     rdx, rsi; unsigned __int64
0x180009d39  cmovnz  rcx, rax
0x180009d3d  mov     [rcx], r15w
0x180009d41  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009d46  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009d4b  lea     r8, [rsp+280h+Name]; lpName
0x180009d50  xor     edx, edx; bInheritHandle
0x180009d52  mov     ecx, 1F0003h; dwDesiredAccess
0x180009d57  call    cs:__imp_OpenSemaphoreW
0x180009d5d  mov     rbx, rax
0x180009d60  test    rax, rax
0x180009d63  jz      loc_180009E8A
0x180009d69  lea     rdx, [rsp+280h+var_25C]; int *
0x180009d6e  mov     [rsp+280h+var_25C], r15d
0x180009d73  mov     rcx, rax; hHandle
0x180009d76  mov     [rsp+280h+var_260], r15d; int
0x180009d7b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009d80  mov     edi, eax
0x180009d82  test    eax, eax
0x180009d84  jns     short loc_180009DB2
0x180009d86  mov     rcx, [rbp+188h]; this
0x180009d8d  mov     r9d, eax; char *
0x180009d90  mov     edx, 0D6h; void *
0x180009d95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d9a  mov     rcx, rbx; hObject
0x180009d9d  call    cs:__imp_CloseHandle
0x180009da3  test    eax, eax
0x180009da5  jz      loc_180009EFF
0x180009dab  mov     eax, edi
0x180009dad  jmp     loc_180009EAA
0x180009db2  lea     r8, asc_180010150; "h"
0x180009db9  mov     rdx, rsi; unsigned __int64
0x180009dbc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009dc1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009dc6  lea     r8, [rsp+280h+Name]; lpName
0x180009dcb  xor     edx, edx; bInheritHandle
0x180009dcd  mov     ecx, 1F0003h; dwDesiredAccess
0x180009dd2  call    cs:__imp_OpenSemaphoreW
0x180009dd8  mov     rdi, rax
0x180009ddb  test    rax, rax
0x180009dde  jz      loc_180009E65
0x180009de4  lea     rdx, [rsp+280h+var_260]; int *
0x180009de9  mov     rcx, rax; hHandle
0x180009dec  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009df1  mov     esi, eax
0x180009df3  test    eax, eax
0x180009df5  jns     short loc_180009E31
0x180009df7  mov     rcx, [rbp+188h]; this
0x180009dfe  mov     r9d, eax; char *
0x180009e01  mov     edx, 0DEh; void *
0x180009e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e0b  mov     rcx, rdi; hObject
0x180009e0e  call    cs:__imp_CloseHandle
0x180009e14  test    eax, eax
0x180009e16  jz      loc_180009F11
0x180009e1c  mov     rcx, rbx; hObject
0x180009e1f  call    cs:__imp_CloseHandle
0x180009e25  test    eax, eax
0x180009e27  jz      loc_180009F23
0x180009e2d  mov     eax, esi
0x180009e2f  jmp     short loc_180009EAA
0x180009e31  mov     rcx, rdi; hObject
0x180009e34  call    cs:__imp_CloseHandle
0x180009e3a  test    eax, eax
0x180009e3c  jz      loc_180009EC9
0x180009e42  movsxd  rax, [rsp+280h+var_25C]
0x180009e47  movsxd  rcx, [rsp+280h+var_260]
0x180009e4c  shl     rcx, 1Fh
0x180009e50  or      rcx, rax
0x180009e53  mov     [r14], rcx
0x180009e56  mov     rcx, rbx; hObject
0x180009e59  call    cs:__imp_CloseHandle
0x180009e5f  test    eax, eax
0x180009e61  jz      short loc_180009EDB
0x180009e63  jmp     short loc_180009E95
0x180009e65  mov     rcx, [rbp+188h]; this
0x180009e6c  mov     edx, 0DCh; void *
0x180009e71  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009e76  mov     rcx, rbx; hObject
0x180009e79  mov     edi, eax
0x180009e7b  call    cs:__imp_CloseHandle
0x180009e81  test    eax, eax
0x180009e83  jz      short loc_180009EED
0x180009e85  jmp     loc_180009DAB
0x180009e8a  call    cs:__imp_GetLastError
0x180009e90  cmp     eax, 2
0x180009e93  jnz     short loc_180009E99
0x180009e95  xor     eax, eax
0x180009e97  jmp     short loc_180009EAA
0x180009e99  mov     rcx, [rbp+188h]; this
0x180009ea0  mov     edx, 0D0h; void *
0x180009ea5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009eaa  mov     rcx, [rbp+180h+var_40]
0x180009eb1  xor     rcx, rsp; StackCookie
0x180009eb4  call    __security_check_cookie
0x180009eb9  add     rsp, 258h
0x180009ec0  pop     r15
0x180009ec2  pop     r14
0x180009ec4  pop     rdi
0x180009ec5  pop     rsi
0x180009ec6  pop     rbx
0x180009ec7  pop     rbp
0x180009ec8  retn
0x180009ec9  mov     rcx, [rbp+188h]; this
0x180009ed0  mov     edx, 0A0Bh; void *
0x180009ed5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009edb  mov     rcx, [rbp+188h]; this
0x180009ee2  mov     edx, 0A0Bh; void *
0x180009ee7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009eed  mov     rcx, [rbp+188h]; this
0x180009ef4  mov     edx, 0A0Bh; void *
0x180009ef9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009eff  mov     rcx, [rbp+188h]; this
0x180009f06  mov     edx, 0A0Bh; void *
0x180009f0b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009f11  mov     rcx, [rbp+188h]; this
0x180009f18  mov     edx, 0A0Bh; void *
0x180009f1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009f23  mov     rcx, [rbp+188h]; this
0x180009f2a  mov     edx, 0A0Bh; void *
0x180009f2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
