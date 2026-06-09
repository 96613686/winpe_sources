# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006bfc`
- end: `0x180006e68`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037d4`

## callees

- `0x180001be0`
- `0x180004b84`
- `0x180005cb4`
- `0x180005cd4`
- `0x180006a90`
- `0x180006bfc`
- `0x1800075e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006c90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d05`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006c90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dae`

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
  __int64 v19; // r8
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
  __int64 v35; // r8
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
0x180006bfc  push    rbp
0x180006bfe  push    rbx
0x180006bff  push    rsi
0x180006c00  push    rdi
0x180006c01  push    r14
0x180006c03  push    r15
0x180006c05  lea     rbp, [rsp-158h]
0x180006c0d  sub     rsp, 258h
0x180006c14  mov     rax, cs:__security_cookie
0x180006c1b  xor     rax, rsp
0x180006c1e  mov     [rbp+180h+var_40], rax
0x180006c25  xor     r15d, r15d
0x180006c28  lea     rax, [rsp+280h+Name]
0x180006c2d  mov     [r8], r15
0x180006c30  mov     r14, r8
0x180006c33  mov     edx, 104h
0x180006c38  mov     r9d, 7FFFFFFEh
0x180006c3e  test    r9, r9
0x180006c41  jz      short loc_180006C62
0x180006c43  movzx   r8d, word ptr [rcx]
0x180006c47  test    r8w, r8w
0x180006c4b  jz      short loc_180006C62
0x180006c4d  mov     [rax], r8w
0x180006c51  add     rcx, 2
0x180006c55  add     rax, 2
0x180006c59  dec     r9
0x180006c5c  sub     rdx, 1; unsigned __int64
0x180006c60  jnz     short loc_180006C3E
0x180006c62  test    rdx, rdx
0x180006c65  lea     rcx, [rax-2]
0x180006c69  lea     r8, aP0; "_p0"
0x180006c70  cmovnz  rcx, rax
0x180006c74  mov     [rcx], r15w
0x180006c78  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006c7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006c82  mov     esi, 1F0003h
0x180006c87  lea     r8, [rsp+280h+Name]; lpName
0x180006c8c  mov     ecx, esi; dwDesiredAccess
0x180006c8e  xor     edx, edx; bInheritHandle
0x180006c90  call    cs:__imp_OpenSemaphoreW
0x180006c96  mov     rbx, rax
0x180006c99  test    rax, rax
0x180006c9c  jz      loc_180006DBD
0x180006ca2  lea     rdx, [rsp+280h+var_25C]; int *
0x180006ca7  mov     [rsp+280h+var_25C], r15d
0x180006cac  mov     rcx, rax; hHandle
0x180006caf  mov     [rsp+280h+var_260], r15d; int
0x180006cb4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006cb9  mov     edi, eax
0x180006cbb  test    eax, eax
0x180006cbd  jns     short loc_180006CEB
0x180006cbf  mov     rcx, [rbp+188h]; this
0x180006cc6  mov     r9d, eax; char *
0x180006cc9  mov     edx, 0D6h; void *
0x180006cce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cd3  mov     rcx, rbx; hObject
0x180006cd6  call    cs:__imp_CloseHandle
0x180006cdc  test    eax, eax
0x180006cde  jz      loc_180006E32
0x180006ce4  mov     eax, edi
0x180006ce6  jmp     loc_180006DDD
0x180006ceb  lea     r8, asc_18000AB38; "h"
0x180006cf2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006cf7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006cfc  lea     r8, [rsp+280h+Name]; lpName
0x180006d01  xor     edx, edx; bInheritHandle
0x180006d03  mov     ecx, esi; dwDesiredAccess
0x180006d05  call    cs:__imp_OpenSemaphoreW
0x180006d0b  mov     rdi, rax
0x180006d0e  test    rax, rax
0x180006d11  jz      loc_180006D98
0x180006d17  lea     rdx, [rsp+280h+var_260]; int *
0x180006d1c  mov     rcx, rax; hHandle
0x180006d1f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006d24  mov     esi, eax
0x180006d26  test    eax, eax
0x180006d28  jns     short loc_180006D64
0x180006d2a  mov     rcx, [rbp+188h]; this
0x180006d31  mov     r9d, eax; char *
0x180006d34  mov     edx, 0DEh; void *
0x180006d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d3e  mov     rcx, rdi; hObject
0x180006d41  call    cs:__imp_CloseHandle
0x180006d47  test    eax, eax
0x180006d49  jz      loc_180006E44
0x180006d4f  mov     rcx, rbx; hObject
0x180006d52  call    cs:__imp_CloseHandle
0x180006d58  test    eax, eax
0x180006d5a  jz      loc_180006E56
0x180006d60  mov     eax, esi
0x180006d62  jmp     short loc_180006DDD
0x180006d64  mov     rcx, rdi; hObject
0x180006d67  call    cs:__imp_CloseHandle
0x180006d6d  test    eax, eax
0x180006d6f  jz      loc_180006DFC
0x180006d75  movsxd  rax, [rsp+280h+var_25C]
0x180006d7a  movsxd  rcx, [rsp+280h+var_260]
0x180006d7f  shl     rcx, 1Fh
0x180006d83  or      rcx, rax
0x180006d86  mov     [r14], rcx
0x180006d89  mov     rcx, rbx; hObject
0x180006d8c  call    cs:__imp_CloseHandle
0x180006d92  test    eax, eax
0x180006d94  jz      short loc_180006E0E
0x180006d96  jmp     short loc_180006DC8
0x180006d98  mov     rcx, [rbp+188h]; this
0x180006d9f  mov     edx, 0DCh; void *
0x180006da4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006da9  mov     rcx, rbx; hObject
0x180006dac  mov     edi, eax
0x180006dae  call    cs:__imp_CloseHandle
0x180006db4  test    eax, eax
0x180006db6  jz      short loc_180006E20
0x180006db8  jmp     loc_180006CE4
0x180006dbd  call    cs:__imp_GetLastError
0x180006dc3  cmp     eax, 2
0x180006dc6  jnz     short loc_180006DCC
0x180006dc8  xor     eax, eax
0x180006dca  jmp     short loc_180006DDD
0x180006dcc  mov     rcx, [rbp+188h]; this
0x180006dd3  mov     edx, 0D0h; void *
0x180006dd8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006ddd  mov     rcx, [rbp+180h+var_40]
0x180006de4  xor     rcx, rsp; StackCookie
0x180006de7  call    __security_check_cookie
0x180006dec  add     rsp, 258h
0x180006df3  pop     r15
0x180006df5  pop     r14
0x180006df7  pop     rdi
0x180006df8  pop     rsi
0x180006df9  pop     rbx
0x180006dfa  pop     rbp
0x180006dfb  retn
0x180006dfc  mov     rcx, [rbp+188h]; this
0x180006e03  mov     edx, 0A0Bh; void *
0x180006e08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e0e  mov     rcx, [rbp+188h]; this
0x180006e15  mov     edx, 0A0Bh; void *
0x180006e1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e20  mov     rcx, [rbp+188h]; this
0x180006e27  mov     edx, 0A0Bh; void *
0x180006e2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e32  mov     rcx, [rbp+188h]; this
0x180006e39  mov     edx, 0A0Bh; void *
0x180006e3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e44  mov     rcx, [rbp+188h]; this
0x180006e4b  mov     edx, 0A0Bh; void *
0x180006e50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e56  mov     rcx, [rbp+188h]; this
0x180006e5d  mov     edx, 0A0Bh; void *
0x180006e62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
