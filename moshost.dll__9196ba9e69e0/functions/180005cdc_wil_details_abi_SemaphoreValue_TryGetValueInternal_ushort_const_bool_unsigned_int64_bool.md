# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005cdc`
- end: `0x180005f48`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003734`

## callees

- `0x180001d00`
- `0x180004684`
- `0x180005274`
- `0x180005294`
- `0x180005b70`
- `0x180005cdc`
- `0x18000609c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d70`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005de5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005d70`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e8e`

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
  unsigned int v19; // r8d
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
0x180005cdc  push    rbp
0x180005cde  push    rbx
0x180005cdf  push    rsi
0x180005ce0  push    rdi
0x180005ce1  push    r14
0x180005ce3  push    r15
0x180005ce5  lea     rbp, [rsp-158h]
0x180005ced  sub     rsp, 258h
0x180005cf4  mov     rax, cs:__security_cookie
0x180005cfb  xor     rax, rsp
0x180005cfe  mov     [rbp+180h+var_40], rax
0x180005d05  xor     r15d, r15d
0x180005d08  lea     rax, [rsp+280h+Name]
0x180005d0d  mov     [r8], r15
0x180005d10  mov     r14, r8
0x180005d13  mov     edx, 104h
0x180005d18  mov     r9d, 7FFFFFFEh
0x180005d1e  test    r9, r9
0x180005d21  jz      short loc_180005D42
0x180005d23  movzx   r8d, word ptr [rcx]
0x180005d27  test    r8w, r8w
0x180005d2b  jz      short loc_180005D42
0x180005d2d  mov     [rax], r8w
0x180005d31  add     rcx, 2
0x180005d35  add     rax, 2
0x180005d39  dec     r9
0x180005d3c  sub     rdx, 1; unsigned __int64
0x180005d40  jnz     short loc_180005D1E
0x180005d42  test    rdx, rdx
0x180005d45  lea     rcx, [rax-2]
0x180005d49  lea     r8, aP0; "_p0"
0x180005d50  cmovnz  rcx, rax
0x180005d54  mov     [rcx], r15w
0x180005d58  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005d5d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005d62  mov     esi, 1F0003h
0x180005d67  lea     r8, [rsp+280h+Name]; lpName
0x180005d6c  mov     ecx, esi; dwDesiredAccess
0x180005d6e  xor     edx, edx; bInheritHandle
0x180005d70  call    cs:__imp_OpenSemaphoreW
0x180005d76  mov     rbx, rax
0x180005d79  test    rax, rax
0x180005d7c  jz      loc_180005E9D
0x180005d82  lea     rdx, [rsp+280h+var_25C]; int *
0x180005d87  mov     [rsp+280h+var_25C], r15d
0x180005d8c  mov     rcx, rax; hHandle
0x180005d8f  mov     [rsp+280h+var_260], r15d; int
0x180005d94  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005d99  mov     edi, eax
0x180005d9b  test    eax, eax
0x180005d9d  jns     short loc_180005DCB
0x180005d9f  mov     rcx, [rbp+188h]; this
0x180005da6  mov     r9d, eax; char *
0x180005da9  mov     edx, 0D6h; void *
0x180005dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005db3  mov     rcx, rbx; hObject
0x180005db6  call    cs:__imp_CloseHandle
0x180005dbc  test    eax, eax
0x180005dbe  jz      loc_180005F12
0x180005dc4  mov     eax, edi
0x180005dc6  jmp     loc_180005EBD
0x180005dcb  lea     r8, asc_180011328; "h"
0x180005dd2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005dd7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005ddc  lea     r8, [rsp+280h+Name]; lpName
0x180005de1  xor     edx, edx; bInheritHandle
0x180005de3  mov     ecx, esi; dwDesiredAccess
0x180005de5  call    cs:__imp_OpenSemaphoreW
0x180005deb  mov     rdi, rax
0x180005dee  test    rax, rax
0x180005df1  jz      loc_180005E78
0x180005df7  lea     rdx, [rsp+280h+var_260]; int *
0x180005dfc  mov     rcx, rax; hHandle
0x180005dff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005e04  mov     esi, eax
0x180005e06  test    eax, eax
0x180005e08  jns     short loc_180005E44
0x180005e0a  mov     rcx, [rbp+188h]; this
0x180005e11  mov     r9d, eax; char *
0x180005e14  mov     edx, 0DEh; void *
0x180005e19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e1e  mov     rcx, rdi; hObject
0x180005e21  call    cs:__imp_CloseHandle
0x180005e27  test    eax, eax
0x180005e29  jz      loc_180005F24
0x180005e2f  mov     rcx, rbx; hObject
0x180005e32  call    cs:__imp_CloseHandle
0x180005e38  test    eax, eax
0x180005e3a  jz      loc_180005F36
0x180005e40  mov     eax, esi
0x180005e42  jmp     short loc_180005EBD
0x180005e44  mov     rcx, rdi; hObject
0x180005e47  call    cs:__imp_CloseHandle
0x180005e4d  test    eax, eax
0x180005e4f  jz      loc_180005EDC
0x180005e55  movsxd  rax, [rsp+280h+var_25C]
0x180005e5a  movsxd  rcx, [rsp+280h+var_260]
0x180005e5f  shl     rcx, 1Fh
0x180005e63  or      rcx, rax
0x180005e66  mov     [r14], rcx
0x180005e69  mov     rcx, rbx; hObject
0x180005e6c  call    cs:__imp_CloseHandle
0x180005e72  test    eax, eax
0x180005e74  jz      short loc_180005EEE
0x180005e76  jmp     short loc_180005EA8
0x180005e78  mov     rcx, [rbp+188h]; this
0x180005e7f  mov     edx, 0DCh; void *
0x180005e84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005e89  mov     rcx, rbx; hObject
0x180005e8c  mov     edi, eax
0x180005e8e  call    cs:__imp_CloseHandle
0x180005e94  test    eax, eax
0x180005e96  jz      short loc_180005F00
0x180005e98  jmp     loc_180005DC4
0x180005e9d  call    cs:__imp_GetLastError
0x180005ea3  cmp     eax, 2
0x180005ea6  jnz     short loc_180005EAC
0x180005ea8  xor     eax, eax
0x180005eaa  jmp     short loc_180005EBD
0x180005eac  mov     rcx, [rbp+188h]; this
0x180005eb3  mov     edx, 0D0h; void *
0x180005eb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005ebd  mov     rcx, [rbp+180h+var_40]
0x180005ec4  xor     rcx, rsp; StackCookie
0x180005ec7  call    __security_check_cookie
0x180005ecc  add     rsp, 258h
0x180005ed3  pop     r15
0x180005ed5  pop     r14
0x180005ed7  pop     rdi
0x180005ed8  pop     rsi
0x180005ed9  pop     rbx
0x180005eda  pop     rbp
0x180005edb  retn
0x180005edc  mov     rcx, [rbp+188h]; this
0x180005ee3  mov     edx, 0A0Bh; void *
0x180005ee8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005eee  mov     rcx, [rbp+188h]; this
0x180005ef5  mov     edx, 0A0Bh; void *
0x180005efa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005f00  mov     rcx, [rbp+188h]; this
0x180005f07  mov     edx, 0A0Bh; void *
0x180005f0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005f12  mov     rcx, [rbp+188h]; this
0x180005f19  mov     edx, 0A0Bh; void *
0x180005f1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005f24  mov     rcx, [rbp+188h]; this
0x180005f2b  mov     edx, 0A0Bh; void *
0x180005f30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005f36  mov     rcx, [rbp+188h]; this
0x180005f3d  mov     edx, 0A0Bh; void *
0x180005f42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
