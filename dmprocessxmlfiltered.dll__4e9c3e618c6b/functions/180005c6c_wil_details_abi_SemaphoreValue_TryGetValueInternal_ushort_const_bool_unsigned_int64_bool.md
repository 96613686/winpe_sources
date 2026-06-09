# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005c6c`
- end: `0x180005ee6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800034b8`

## callees

- `0x180001520`
- `0x1800045e4`
- `0x180005204`
- `0x180005224`
- `0x180005b00`
- `0x180005c6c`
- `0x18000603c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e3b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d7c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e2c`

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
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x180005c6c  push    rbp
0x180005c6e  push    rbx
0x180005c6f  push    rsi
0x180005c70  push    rdi
0x180005c71  push    r14
0x180005c73  push    r15
0x180005c75  lea     rbp, [rsp-158h]
0x180005c7d  sub     rsp, 258h
0x180005c84  mov     rax, cs:__security_cookie
0x180005c8b  xor     rax, rsp
0x180005c8e  mov     [rbp+180h+var_40], rax
0x180005c95  xor     r15d, r15d
0x180005c98  lea     rax, [rsp+280h+Name]
0x180005c9d  mov     [r8], r15
0x180005ca0  mov     r14, r8
0x180005ca3  mov     edx, 104h
0x180005ca8  mov     r9d, 7FFFFFFEh
0x180005cae  test    r9, r9
0x180005cb1  jz      short loc_180005CD2
0x180005cb3  movzx   r8d, word ptr [rcx]
0x180005cb7  test    r8w, r8w
0x180005cbb  jz      short loc_180005CD2
0x180005cbd  mov     [rax], r8w
0x180005cc1  add     rcx, 2
0x180005cc5  add     rax, 2
0x180005cc9  dec     r9
0x180005ccc  sub     rdx, 1; unsigned __int64
0x180005cd0  jnz     short loc_180005CAE
0x180005cd2  test    rdx, rdx
0x180005cd5  lea     rcx, [rax-2]
0x180005cd9  lea     r8, aP0; "_p0"
0x180005ce0  cmovnz  rcx, rax
0x180005ce4  mov     [rcx], r15w
0x180005ce8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005ced  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005cf2  mov     esi, 1F0003h
0x180005cf7  lea     r8, [rsp+280h+Name]; lpName
0x180005cfc  mov     ecx, esi; dwDesiredAccess
0x180005cfe  xor     edx, edx; bInheritHandle
0x180005d00  call    cs:__imp_OpenSemaphoreW
0x180005d06  mov     rbx, rax
0x180005d09  test    rax, rax
0x180005d0c  jz      loc_180005E3B
0x180005d12  lea     rdx, [rsp+280h+var_25C]; int *
0x180005d17  mov     [rsp+280h+var_25C], r15d
0x180005d1c  mov     rcx, rax; hHandle
0x180005d1f  mov     [rsp+280h+var_260], r15d; int
0x180005d24  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005d29  mov     edi, eax
0x180005d2b  test    eax, eax
0x180005d2d  jns     short loc_180005D62
0x180005d2f  mov     rcx, [rbp+188h]; this
0x180005d36  lea     r8, aWil; "wil"
0x180005d3d  mov     r9d, eax; char *
0x180005d40  mov     edx, 0D6h; void *
0x180005d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d4a  mov     rcx, rbx; hObject
0x180005d4d  call    cs:__imp_CloseHandle
0x180005d53  test    eax, eax
0x180005d55  jz      loc_180005EB0
0x180005d5b  mov     eax, edi
0x180005d5d  jmp     loc_180005E5B
0x180005d62  lea     r8, asc_1800099A8; "h"
0x180005d69  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005d6e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005d73  lea     r8, [rsp+280h+Name]; lpName
0x180005d78  xor     edx, edx; bInheritHandle
0x180005d7a  mov     ecx, esi; dwDesiredAccess
0x180005d7c  call    cs:__imp_OpenSemaphoreW
0x180005d82  mov     rdi, rax
0x180005d85  test    rax, rax
0x180005d88  jz      loc_180005E16
0x180005d8e  lea     rdx, [rsp+280h+var_260]; int *
0x180005d93  mov     rcx, rax; hHandle
0x180005d96  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005d9b  mov     esi, eax
0x180005d9d  test    eax, eax
0x180005d9f  jns     short loc_180005DE2
0x180005da1  mov     rcx, [rbp+188h]; this
0x180005da8  lea     r8, aWil; "wil"
0x180005daf  mov     r9d, eax; char *
0x180005db2  mov     edx, 0DEh; void *
0x180005db7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005dbc  mov     rcx, rdi; hObject
0x180005dbf  call    cs:__imp_CloseHandle
0x180005dc5  test    eax, eax
0x180005dc7  jz      loc_180005EC2
0x180005dcd  mov     rcx, rbx; hObject
0x180005dd0  call    cs:__imp_CloseHandle
0x180005dd6  test    eax, eax
0x180005dd8  jz      loc_180005ED4
0x180005dde  mov     eax, esi
0x180005de0  jmp     short loc_180005E5B
0x180005de2  mov     rcx, rdi; hObject
0x180005de5  call    cs:__imp_CloseHandle
0x180005deb  test    eax, eax
0x180005ded  jz      loc_180005E7A
0x180005df3  movsxd  rax, [rsp+280h+var_25C]
0x180005df8  movsxd  rcx, [rsp+280h+var_260]
0x180005dfd  shl     rcx, 1Fh
0x180005e01  or      rcx, rax
0x180005e04  mov     [r14], rcx
0x180005e07  mov     rcx, rbx; hObject
0x180005e0a  call    cs:__imp_CloseHandle
0x180005e10  test    eax, eax
0x180005e12  jz      short loc_180005E8C
0x180005e14  jmp     short loc_180005E46
0x180005e16  mov     rcx, [rbp+188h]; this
0x180005e1d  mov     edx, 0DCh; void *
0x180005e22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005e27  mov     rcx, rbx; hObject
0x180005e2a  mov     edi, eax
0x180005e2c  call    cs:__imp_CloseHandle
0x180005e32  test    eax, eax
0x180005e34  jz      short loc_180005E9E
0x180005e36  jmp     loc_180005D5B
0x180005e3b  call    cs:__imp_GetLastError
0x180005e41  cmp     eax, 2
0x180005e44  jnz     short loc_180005E4A
0x180005e46  xor     eax, eax
0x180005e48  jmp     short loc_180005E5B
0x180005e4a  mov     rcx, [rbp+188h]; this
0x180005e51  mov     edx, 0D0h; void *
0x180005e56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005e5b  mov     rcx, [rbp+180h+var_40]
0x180005e62  xor     rcx, rsp; StackCookie
0x180005e65  call    __security_check_cookie
0x180005e6a  add     rsp, 258h
0x180005e71  pop     r15
0x180005e73  pop     r14
0x180005e75  pop     rdi
0x180005e76  pop     rsi
0x180005e77  pop     rbx
0x180005e78  pop     rbp
0x180005e79  retn
0x180005e7a  mov     rcx, [rbp+188h]; this
0x180005e81  mov     edx, 0A0Bh; void *
0x180005e86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e8c  mov     rcx, [rbp+188h]; this
0x180005e93  mov     edx, 0A0Bh; void *
0x180005e98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e9e  mov     rcx, [rbp+188h]; this
0x180005ea5  mov     edx, 0A0Bh; void *
0x180005eaa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005eb0  mov     rcx, [rbp+188h]; this
0x180005eb7  mov     edx, 0A0Bh; void *
0x180005ebc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ec2  mov     rcx, [rbp+188h]; this
0x180005ec9  mov     edx, 0A0Bh; void *
0x180005ece  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ed4  mov     rcx, [rbp+188h]; this
0x180005edb  mov     edx, 0A0Bh; void *
0x180005ee0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
