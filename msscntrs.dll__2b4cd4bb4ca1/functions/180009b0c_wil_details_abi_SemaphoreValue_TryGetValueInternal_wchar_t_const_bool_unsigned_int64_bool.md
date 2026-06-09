# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009b0c`
- end: `0x180009d86`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800050b8`
- `0x180005488`

## callees

- `0x1800024a0`
- `0x180006a14`
- `0x180008b74`
- `0x180008b94`
- `0x1800095d8`
- `0x180009b0c`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009ba0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c1c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009ba0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009caa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009caa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ccc`

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
  StringCchCatW(Name, v6, (wchar_t *)L"_p0");
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
  StringCchCatW(Name, v12, (wchar_t *)L"h");
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
0x180009b0c  push    rbp
0x180009b0e  push    rbx
0x180009b0f  push    rsi
0x180009b10  push    rdi
0x180009b11  push    r14
0x180009b13  push    r15
0x180009b15  lea     rbp, [rsp-158h]
0x180009b1d  sub     rsp, 258h
0x180009b24  mov     rax, cs:__security_cookie
0x180009b2b  xor     rax, rsp
0x180009b2e  mov     [rbp+180h+var_40], rax
0x180009b35  xor     r15d, r15d
0x180009b38  lea     rax, [rsp+280h+Name]
0x180009b3d  mov     [r8], r15
0x180009b40  mov     r14, r8
0x180009b43  mov     edx, 104h
0x180009b48  mov     r9d, 7FFFFFFEh
0x180009b4e  test    r9, r9
0x180009b51  jz      short loc_180009B72
0x180009b53  movzx   r8d, word ptr [rcx]
0x180009b57  test    r8w, r8w
0x180009b5b  jz      short loc_180009B72
0x180009b5d  mov     [rax], r8w
0x180009b61  add     rcx, 2
0x180009b65  add     rax, 2
0x180009b69  dec     r9
0x180009b6c  sub     rdx, 1; unsigned __int64
0x180009b70  jnz     short loc_180009B4E
0x180009b72  test    rdx, rdx
0x180009b75  lea     rcx, [rax-2]
0x180009b79  lea     r8, aP0; "_p0"
0x180009b80  cmovnz  rcx, rax
0x180009b84  mov     [rcx], r15w
0x180009b88  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180009b8d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009b92  mov     esi, 1F0003h
0x180009b97  lea     r8, [rsp+280h+Name]; lpName
0x180009b9c  mov     ecx, esi; dwDesiredAccess
0x180009b9e  xor     edx, edx; bInheritHandle
0x180009ba0  call    cs:__imp_OpenSemaphoreW
0x180009ba6  mov     rbx, rax
0x180009ba9  test    rax, rax
0x180009bac  jz      loc_180009CDB
0x180009bb2  lea     rdx, [rsp+280h+var_25C]; int *
0x180009bb7  mov     [rsp+280h+var_25C], r15d
0x180009bbc  mov     rcx, rax; hHandle
0x180009bbf  mov     [rsp+280h+var_260], r15d; int
0x180009bc4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009bc9  mov     edi, eax
0x180009bcb  test    eax, eax
0x180009bcd  jns     short loc_180009C02
0x180009bcf  mov     rcx, [rbp+188h]; this
0x180009bd6  lea     r8, aWil; "wil"
0x180009bdd  mov     r9d, eax; char *
0x180009be0  mov     edx, 0D6h; void *
0x180009be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bea  mov     rcx, rbx; hObject
0x180009bed  call    cs:__imp_CloseHandle
0x180009bf3  test    eax, eax
0x180009bf5  jz      loc_180009D50
0x180009bfb  mov     eax, edi
0x180009bfd  jmp     loc_180009CFB
0x180009c02  lea     r8, asc_18001A4A8; "h"
0x180009c09  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180009c0e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009c13  lea     r8, [rsp+280h+Name]; lpName
0x180009c18  xor     edx, edx; bInheritHandle
0x180009c1a  mov     ecx, esi; dwDesiredAccess
0x180009c1c  call    cs:__imp_OpenSemaphoreW
0x180009c22  mov     rdi, rax
0x180009c25  test    rax, rax
0x180009c28  jz      loc_180009CB6
0x180009c2e  lea     rdx, [rsp+280h+var_260]; int *
0x180009c33  mov     rcx, rax; hHandle
0x180009c36  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c3b  mov     esi, eax
0x180009c3d  test    eax, eax
0x180009c3f  jns     short loc_180009C82
0x180009c41  mov     rcx, [rbp+188h]; this
0x180009c48  lea     r8, aWil; "wil"
0x180009c4f  mov     r9d, eax; char *
0x180009c52  mov     edx, 0DEh; void *
0x180009c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c5c  mov     rcx, rdi; hObject
0x180009c5f  call    cs:__imp_CloseHandle
0x180009c65  test    eax, eax
0x180009c67  jz      loc_180009D62
0x180009c6d  mov     rcx, rbx; hObject
0x180009c70  call    cs:__imp_CloseHandle
0x180009c76  test    eax, eax
0x180009c78  jz      loc_180009D74
0x180009c7e  mov     eax, esi
0x180009c80  jmp     short loc_180009CFB
0x180009c82  mov     rcx, rdi; hObject
0x180009c85  call    cs:__imp_CloseHandle
0x180009c8b  test    eax, eax
0x180009c8d  jz      loc_180009D1A
0x180009c93  movsxd  rax, [rsp+280h+var_25C]
0x180009c98  movsxd  rcx, [rsp+280h+var_260]
0x180009c9d  shl     rcx, 1Fh
0x180009ca1  or      rcx, rax
0x180009ca4  mov     [r14], rcx
0x180009ca7  mov     rcx, rbx; hObject
0x180009caa  call    cs:__imp_CloseHandle
0x180009cb0  test    eax, eax
0x180009cb2  jz      short loc_180009D2C
0x180009cb4  jmp     short loc_180009CE6
0x180009cb6  mov     rcx, [rbp+188h]; this
0x180009cbd  mov     edx, 0DCh; void *
0x180009cc2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009cc7  mov     rcx, rbx; hObject
0x180009cca  mov     edi, eax
0x180009ccc  call    cs:__imp_CloseHandle
0x180009cd2  test    eax, eax
0x180009cd4  jz      short loc_180009D3E
0x180009cd6  jmp     loc_180009BFB
0x180009cdb  call    cs:__imp_GetLastError
0x180009ce1  cmp     eax, 2
0x180009ce4  jnz     short loc_180009CEA
0x180009ce6  xor     eax, eax
0x180009ce8  jmp     short loc_180009CFB
0x180009cea  mov     rcx, [rbp+188h]; this
0x180009cf1  mov     edx, 0D0h; void *
0x180009cf6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009cfb  mov     rcx, [rbp+180h+var_40]
0x180009d02  xor     rcx, rsp; StackCookie
0x180009d05  call    __security_check_cookie
0x180009d0a  add     rsp, 258h
0x180009d11  pop     r15
0x180009d13  pop     r14
0x180009d15  pop     rdi
0x180009d16  pop     rsi
0x180009d17  pop     rbx
0x180009d18  pop     rbp
0x180009d19  retn
0x180009d1a  mov     rcx, [rbp+188h]; this
0x180009d21  mov     edx, 0A0Bh; void *
0x180009d26  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d2c  mov     rcx, [rbp+188h]; this
0x180009d33  mov     edx, 0A0Bh; void *
0x180009d38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d3e  mov     rcx, [rbp+188h]; this
0x180009d45  mov     edx, 0A0Bh; void *
0x180009d4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d50  mov     rcx, [rbp+188h]; this
0x180009d57  mov     edx, 0A0Bh; void *
0x180009d5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d62  mov     rcx, [rbp+188h]; this
0x180009d69  mov     edx, 0A0Bh; void *
0x180009d6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d74  mov     rcx, [rbp+188h]; this
0x180009d7b  mov     edx, 0A0Bh; void *
0x180009d80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
