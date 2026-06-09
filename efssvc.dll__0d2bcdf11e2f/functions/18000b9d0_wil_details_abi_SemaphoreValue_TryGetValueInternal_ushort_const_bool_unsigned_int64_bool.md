# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b9d0`
- end: `0x18000bc7a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009a10`

## callees

- `0x18000a58c`
- `0x18000b604`
- `0x18000b624`
- `0x18000b88c`
- `0x18000b9d0`
- `0x18000bd6c`
- `0x18000d1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbc8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba64`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bae5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba64`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbb3`

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
0x18000b9d0  push    rbp
0x18000b9d2  push    rbx
0x18000b9d3  push    rsi
0x18000b9d4  push    rdi
0x18000b9d5  push    r14
0x18000b9d7  push    r15
0x18000b9d9  lea     rbp, [rsp-158h]
0x18000b9e1  sub     rsp, 258h
0x18000b9e8  mov     rax, cs:__security_cookie
0x18000b9ef  xor     rax, rsp
0x18000b9f2  mov     [rbp+180h+var_40], rax
0x18000b9f9  xor     r15d, r15d
0x18000b9fc  lea     rax, [rsp+280h+Name]
0x18000ba01  mov     [r8], r15
0x18000ba04  mov     r14, r8
0x18000ba07  mov     edx, 104h
0x18000ba0c  mov     r9d, 7FFFFFFEh
0x18000ba12  test    r9, r9
0x18000ba15  jz      short loc_18000BA36
0x18000ba17  movzx   r8d, word ptr [rcx]
0x18000ba1b  test    r8w, r8w
0x18000ba1f  jz      short loc_18000BA36
0x18000ba21  mov     [rax], r8w
0x18000ba25  add     rcx, 2
0x18000ba29  add     rax, 2
0x18000ba2d  dec     r9
0x18000ba30  sub     rdx, 1; unsigned __int64
0x18000ba34  jnz     short loc_18000BA12
0x18000ba36  test    rdx, rdx
0x18000ba39  lea     rcx, [rax-2]
0x18000ba3d  lea     r8, aP0; "_p0"
0x18000ba44  cmovnz  rcx, rax
0x18000ba48  mov     [rcx], r15w
0x18000ba4c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ba51  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ba56  mov     esi, 1F0003h
0x18000ba5b  lea     r8, [rsp+280h+Name]; lpName
0x18000ba60  mov     ecx, esi; dwDesiredAccess
0x18000ba62  xor     edx, edx; bInheritHandle
0x18000ba64  call    cs:__imp_OpenSemaphoreW
0x18000ba6b  nop     dword ptr [rax+rax+00h]
0x18000ba70  mov     rbx, rax
0x18000ba73  test    rax, rax
0x18000ba76  jz      loc_18000BBC8
0x18000ba7c  lea     rdx, [rsp+280h+var_25C]; int *
0x18000ba81  mov     [rsp+280h+var_25C], r15d
0x18000ba86  mov     rcx, rax; hHandle
0x18000ba89  mov     [rsp+280h+var_260], r15d; int
0x18000ba8e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ba93  mov     edi, eax
0x18000ba95  test    eax, eax
0x18000ba97  jns     short loc_18000BACB
0x18000ba99  mov     rcx, [rbp+188h]; this
0x18000baa0  mov     r9d, eax; char *
0x18000baa3  mov     edx, 0D6h; void *
0x18000baa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000baad  mov     rcx, rbx; hObject
0x18000bab0  call    cs:__imp_CloseHandle
0x18000bab7  nop     dword ptr [rax+rax+00h]
0x18000babc  test    eax, eax
0x18000babe  jz      loc_18000BC44
0x18000bac4  mov     eax, edi
0x18000bac6  jmp     loc_18000BBEE
0x18000bacb  lea     r8, asc_180014150; "h"
0x18000bad2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bad7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000badc  lea     r8, [rsp+280h+Name]; lpName
0x18000bae1  xor     edx, edx; bInheritHandle
0x18000bae3  mov     ecx, esi; dwDesiredAccess
0x18000bae5  call    cs:__imp_OpenSemaphoreW
0x18000baec  nop     dword ptr [rax+rax+00h]
0x18000baf1  mov     rdi, rax
0x18000baf4  test    rax, rax
0x18000baf7  jz      loc_18000BB9D
0x18000bafd  lea     rdx, [rsp+280h+var_260]; int *
0x18000bb02  mov     rcx, rax; hHandle
0x18000bb05  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bb0a  mov     esi, eax
0x18000bb0c  test    eax, eax
0x18000bb0e  jns     short loc_18000BB59
0x18000bb10  mov     rcx, [rbp+188h]; this
0x18000bb17  mov     r9d, eax; char *
0x18000bb1a  mov     edx, 0DEh; void *
0x18000bb1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb24  mov     rcx, rdi; hObject
0x18000bb27  call    cs:__imp_CloseHandle
0x18000bb2e  nop     dword ptr [rax+rax+00h]
0x18000bb33  test    eax, eax
0x18000bb35  jz      loc_18000BC56
0x18000bb3b  mov     rcx, rbx; hObject
0x18000bb3e  call    cs:__imp_CloseHandle
0x18000bb45  nop     dword ptr [rax+rax+00h]
0x18000bb4a  test    eax, eax
0x18000bb4c  jz      loc_18000BC68
0x18000bb52  mov     eax, esi
0x18000bb54  jmp     loc_18000BBEE
0x18000bb59  mov     rcx, rdi; hObject
0x18000bb5c  call    cs:__imp_CloseHandle
0x18000bb63  nop     dword ptr [rax+rax+00h]
0x18000bb68  test    eax, eax
0x18000bb6a  jz      loc_18000BC0E
0x18000bb70  movsxd  rax, [rsp+280h+var_25C]
0x18000bb75  movsxd  rcx, [rsp+280h+var_260]
0x18000bb7a  shl     rcx, 1Fh
0x18000bb7e  or      rcx, rax
0x18000bb81  mov     [r14], rcx
0x18000bb84  mov     rcx, rbx; hObject
0x18000bb87  call    cs:__imp_CloseHandle
0x18000bb8e  nop     dword ptr [rax+rax+00h]
0x18000bb93  test    eax, eax
0x18000bb95  jz      loc_18000BC20
0x18000bb9b  jmp     short loc_18000BBD9
0x18000bb9d  mov     rcx, [rbp+188h]; this
0x18000bba4  mov     edx, 0DCh; void *
0x18000bba9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bbae  mov     rcx, rbx; hObject
0x18000bbb1  mov     edi, eax
0x18000bbb3  call    cs:__imp_CloseHandle
0x18000bbba  nop     dword ptr [rax+rax+00h]
0x18000bbbf  test    eax, eax
0x18000bbc1  jz      short loc_18000BC32
0x18000bbc3  jmp     loc_18000BAC4
0x18000bbc8  call    cs:__imp_GetLastError
0x18000bbcf  nop     dword ptr [rax+rax+00h]
0x18000bbd4  cmp     eax, 2
0x18000bbd7  jnz     short loc_18000BBDD
0x18000bbd9  xor     eax, eax
0x18000bbdb  jmp     short loc_18000BBEE
0x18000bbdd  mov     rcx, [rbp+188h]; this
0x18000bbe4  mov     edx, 0D0h; void *
0x18000bbe9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bbee  mov     rcx, [rbp+180h+var_40]
0x18000bbf5  xor     rcx, rsp; StackCookie
0x18000bbf8  call    __security_check_cookie
0x18000bbfd  add     rsp, 258h
0x18000bc04  pop     r15
0x18000bc06  pop     r14
0x18000bc08  pop     rdi
0x18000bc09  pop     rsi
0x18000bc0a  pop     rbx
0x18000bc0b  pop     rbp
0x18000bc0c  retn
0x18000bc0e  mov     rcx, [rbp+188h]; this
0x18000bc15  mov     edx, 0A0Bh; void *
0x18000bc1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc20  mov     rcx, [rbp+188h]; this
0x18000bc27  mov     edx, 0A0Bh; void *
0x18000bc2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc32  mov     rcx, [rbp+188h]; this
0x18000bc39  mov     edx, 0A0Bh; void *
0x18000bc3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc44  mov     rcx, [rbp+188h]; this
0x18000bc4b  mov     edx, 0A0Bh; void *
0x18000bc50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc56  mov     rcx, [rbp+188h]; this
0x18000bc5d  mov     edx, 0A0Bh; void *
0x18000bc62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc68  mov     rcx, [rbp+188h]; this
0x18000bc6f  mov     edx, 0A0Bh; void *
0x18000bc74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
