# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006d7c`
- end: `0x180006fff`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800046a8`
- `0x180012254`

## callees

- `0x1800022e0`
- `0x1800056f4`
- `0x180006274`
- `0x180006294`
- `0x180006bd4`
- `0x180006d7c`
- `0x18000715c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e95`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f45`

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
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
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
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
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
0x180006d7c  push    rbp
0x180006d7e  push    rbx
0x180006d7f  push    rsi
0x180006d80  push    rdi
0x180006d81  push    r14
0x180006d83  push    r15
0x180006d85  lea     rbp, [rsp-158h]
0x180006d8d  sub     rsp, 258h
0x180006d94  mov     rax, cs:__security_cookie
0x180006d9b  xor     rax, rsp
0x180006d9e  mov     [rbp+180h+var_40], rax
0x180006da5  xor     r15d, r15d
0x180006da8  lea     rax, [rsp+280h+Name]
0x180006dad  mov     esi, 104h
0x180006db2  mov     [r8], r15
0x180006db5  mov     edx, esi
0x180006db7  mov     r14, r8
0x180006dba  mov     r9d, 7FFFFFFEh
0x180006dc0  test    r9, r9
0x180006dc3  jz      short loc_180006DE4
0x180006dc5  movzx   r8d, word ptr [rcx]
0x180006dc9  test    r8w, r8w
0x180006dcd  jz      short loc_180006DE4
0x180006dcf  mov     [rax], r8w
0x180006dd3  add     rcx, 2
0x180006dd7  add     rax, 2
0x180006ddb  dec     r9
0x180006dde  sub     rdx, 1
0x180006de2  jnz     short loc_180006DC0
0x180006de4  test    rdx, rdx
0x180006de7  lea     rcx, [rax-2]
0x180006deb  lea     r8, aP0; "_p0"
0x180006df2  mov     rdx, rsi; unsigned __int64
0x180006df5  cmovnz  rcx, rax
0x180006df9  mov     [rcx], r15w
0x180006dfd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e02  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006e07  lea     r8, [rsp+280h+Name]; lpName
0x180006e0c  xor     edx, edx; bInheritHandle
0x180006e0e  mov     ecx, 1F0003h; dwDesiredAccess
0x180006e13  call    cs:__imp_OpenSemaphoreW
0x180006e19  mov     rbx, rax
0x180006e1c  test    rax, rax
0x180006e1f  jz      loc_180006F54
0x180006e25  lea     rdx, [rsp+280h+var_25C]; int *
0x180006e2a  mov     [rsp+280h+var_25C], r15d
0x180006e2f  mov     rcx, rax; hHandle
0x180006e32  mov     [rsp+280h+var_260], r15d; int
0x180006e37  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006e3c  mov     edi, eax
0x180006e3e  test    eax, eax
0x180006e40  jns     short loc_180006E75
0x180006e42  mov     rcx, [rbp+188h]; this
0x180006e49  lea     r8, aWil; "wil"
0x180006e50  mov     r9d, eax; char *
0x180006e53  mov     edx, 0D6h; void *
0x180006e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e5d  mov     rcx, rbx; hObject
0x180006e60  call    cs:__imp_CloseHandle
0x180006e66  test    eax, eax
0x180006e68  jz      loc_180006FC9
0x180006e6e  mov     eax, edi
0x180006e70  jmp     loc_180006F74
0x180006e75  lea     r8, asc_180021FB8; "h"
0x180006e7c  mov     rdx, rsi; unsigned __int64
0x180006e7f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006e89  lea     r8, [rsp+280h+Name]; lpName
0x180006e8e  xor     edx, edx; bInheritHandle
0x180006e90  mov     ecx, 1F0003h; dwDesiredAccess
0x180006e95  call    cs:__imp_OpenSemaphoreW
0x180006e9b  mov     rdi, rax
0x180006e9e  test    rax, rax
0x180006ea1  jz      loc_180006F2F
0x180006ea7  lea     rdx, [rsp+280h+var_260]; int *
0x180006eac  mov     rcx, rax; hHandle
0x180006eaf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006eb4  mov     esi, eax
0x180006eb6  test    eax, eax
0x180006eb8  jns     short loc_180006EFB
0x180006eba  mov     rcx, [rbp+188h]; this
0x180006ec1  lea     r8, aWil; "wil"
0x180006ec8  mov     r9d, eax; char *
0x180006ecb  mov     edx, 0DEh; void *
0x180006ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ed5  mov     rcx, rdi; hObject
0x180006ed8  call    cs:__imp_CloseHandle
0x180006ede  test    eax, eax
0x180006ee0  jz      loc_180006FDB
0x180006ee6  mov     rcx, rbx; hObject
0x180006ee9  call    cs:__imp_CloseHandle
0x180006eef  test    eax, eax
0x180006ef1  jz      loc_180006FED
0x180006ef7  mov     eax, esi
0x180006ef9  jmp     short loc_180006F74
0x180006efb  mov     rcx, rdi; hObject
0x180006efe  call    cs:__imp_CloseHandle
0x180006f04  test    eax, eax
0x180006f06  jz      loc_180006F93
0x180006f0c  movsxd  rax, [rsp+280h+var_25C]
0x180006f11  movsxd  rcx, [rsp+280h+var_260]
0x180006f16  shl     rcx, 1Fh
0x180006f1a  or      rcx, rax
0x180006f1d  mov     [r14], rcx
0x180006f20  mov     rcx, rbx; hObject
0x180006f23  call    cs:__imp_CloseHandle
0x180006f29  test    eax, eax
0x180006f2b  jz      short loc_180006FA5
0x180006f2d  jmp     short loc_180006F5F
0x180006f2f  mov     rcx, [rbp+188h]; this
0x180006f36  mov     edx, 0DCh; void *
0x180006f3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f40  mov     rcx, rbx; hObject
0x180006f43  mov     edi, eax
0x180006f45  call    cs:__imp_CloseHandle
0x180006f4b  test    eax, eax
0x180006f4d  jz      short loc_180006FB7
0x180006f4f  jmp     loc_180006E6E
0x180006f54  call    cs:__imp_GetLastError
0x180006f5a  cmp     eax, 2
0x180006f5d  jnz     short loc_180006F63
0x180006f5f  xor     eax, eax
0x180006f61  jmp     short loc_180006F74
0x180006f63  mov     rcx, [rbp+188h]; this
0x180006f6a  mov     edx, 0D0h; void *
0x180006f6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f74  mov     rcx, [rbp+180h+var_40]
0x180006f7b  xor     rcx, rsp; StackCookie
0x180006f7e  call    __security_check_cookie
0x180006f83  add     rsp, 258h
0x180006f8a  pop     r15
0x180006f8c  pop     r14
0x180006f8e  pop     rdi
0x180006f8f  pop     rsi
0x180006f90  pop     rbx
0x180006f91  pop     rbp
0x180006f92  retn
0x180006f93  mov     rcx, [rbp+188h]; this
0x180006f9a  mov     edx, 0A0Bh; void *
0x180006f9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fa5  mov     rcx, [rbp+188h]; this
0x180006fac  mov     edx, 0A0Bh; void *
0x180006fb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fb7  mov     rcx, [rbp+188h]; this
0x180006fbe  mov     edx, 0A0Bh; void *
0x180006fc3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fc9  mov     rcx, [rbp+188h]; this
0x180006fd0  mov     edx, 0A0Bh; void *
0x180006fd5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fdb  mov     rcx, [rbp+188h]; this
0x180006fe2  mov     edx, 0A0Bh; void *
0x180006fe7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fed  mov     rcx, [rbp+188h]; this
0x180006ff4  mov     edx, 0A0Bh; void *
0x180006ff9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
