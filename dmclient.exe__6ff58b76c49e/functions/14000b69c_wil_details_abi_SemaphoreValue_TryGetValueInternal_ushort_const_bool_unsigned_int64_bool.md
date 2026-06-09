# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000b69c`
- end: `0x14000b916`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140004bd0`
- `0x140013330`

## callees

- `0x140007394`
- `0x14000ad74`
- `0x14000ad94`
- `0x14000b514`
- `0x14000b69c`
- `0x14000bc2c`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b730`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b7ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b730`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b86b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b77d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b7ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b83a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b85c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b77d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b7ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b83a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b85c`

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
0x14000b69c  push    rbp
0x14000b69e  push    rbx
0x14000b69f  push    rsi
0x14000b6a0  push    rdi
0x14000b6a1  push    r14
0x14000b6a3  push    r15
0x14000b6a5  lea     rbp, [rsp-158h]
0x14000b6ad  sub     rsp, 258h
0x14000b6b4  mov     rax, cs:__security_cookie
0x14000b6bb  xor     rax, rsp
0x14000b6be  mov     [rbp+180h+var_40], rax
0x14000b6c5  xor     r15d, r15d
0x14000b6c8  lea     rax, [rsp+280h+Name]
0x14000b6cd  mov     [r8], r15
0x14000b6d0  mov     r14, r8
0x14000b6d3  mov     edx, 104h
0x14000b6d8  mov     r9d, 7FFFFFFEh
0x14000b6de  test    r9, r9
0x14000b6e1  jz      short loc_14000B702
0x14000b6e3  movzx   r8d, word ptr [rcx]
0x14000b6e7  test    r8w, r8w
0x14000b6eb  jz      short loc_14000B702
0x14000b6ed  mov     [rax], r8w
0x14000b6f1  add     rcx, 2
0x14000b6f5  add     rax, 2
0x14000b6f9  dec     r9
0x14000b6fc  sub     rdx, 1; unsigned __int64
0x14000b700  jnz     short loc_14000B6DE
0x14000b702  test    rdx, rdx
0x14000b705  lea     rcx, [rax-2]
0x14000b709  lea     r8, aP0; "_p0"
0x14000b710  cmovnz  rcx, rax
0x14000b714  mov     [rcx], r15w
0x14000b718  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000b71d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b722  mov     esi, 1F0003h
0x14000b727  lea     r8, [rsp+280h+Name]; lpName
0x14000b72c  mov     ecx, esi; dwDesiredAccess
0x14000b72e  xor     edx, edx; bInheritHandle
0x14000b730  call    cs:__imp_OpenSemaphoreW
0x14000b736  mov     rbx, rax
0x14000b739  test    rax, rax
0x14000b73c  jz      loc_14000B86B
0x14000b742  lea     rdx, [rsp+280h+var_25C]; int *
0x14000b747  mov     [rsp+280h+var_25C], r15d
0x14000b74c  mov     rcx, rax; hHandle
0x14000b74f  mov     [rsp+280h+var_260], r15d; int
0x14000b754  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b759  mov     edi, eax
0x14000b75b  test    eax, eax
0x14000b75d  jns     short loc_14000B792
0x14000b75f  mov     rcx, [rbp+188h]; this
0x14000b766  lea     r8, aWil; "wil"
0x14000b76d  mov     r9d, eax; char *
0x14000b770  mov     edx, 0D6h; void *
0x14000b775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b77a  mov     rcx, rbx; hObject
0x14000b77d  call    cs:__imp_CloseHandle
0x14000b783  test    eax, eax
0x14000b785  jz      loc_14000B8E0
0x14000b78b  mov     eax, edi
0x14000b78d  jmp     loc_14000B88B
0x14000b792  lea     r8, asc_14001C850; "h"
0x14000b799  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000b79e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b7a3  lea     r8, [rsp+280h+Name]; lpName
0x14000b7a8  xor     edx, edx; bInheritHandle
0x14000b7aa  mov     ecx, esi; dwDesiredAccess
0x14000b7ac  call    cs:__imp_OpenSemaphoreW
0x14000b7b2  mov     rdi, rax
0x14000b7b5  test    rax, rax
0x14000b7b8  jz      loc_14000B846
0x14000b7be  lea     rdx, [rsp+280h+var_260]; int *
0x14000b7c3  mov     rcx, rax; hHandle
0x14000b7c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b7cb  mov     esi, eax
0x14000b7cd  test    eax, eax
0x14000b7cf  jns     short loc_14000B812
0x14000b7d1  mov     rcx, [rbp+188h]; this
0x14000b7d8  lea     r8, aWil; "wil"
0x14000b7df  mov     r9d, eax; char *
0x14000b7e2  mov     edx, 0DEh; void *
0x14000b7e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b7ec  mov     rcx, rdi; hObject
0x14000b7ef  call    cs:__imp_CloseHandle
0x14000b7f5  test    eax, eax
0x14000b7f7  jz      loc_14000B8F2
0x14000b7fd  mov     rcx, rbx; hObject
0x14000b800  call    cs:__imp_CloseHandle
0x14000b806  test    eax, eax
0x14000b808  jz      loc_14000B904
0x14000b80e  mov     eax, esi
0x14000b810  jmp     short loc_14000B88B
0x14000b812  mov     rcx, rdi; hObject
0x14000b815  call    cs:__imp_CloseHandle
0x14000b81b  test    eax, eax
0x14000b81d  jz      loc_14000B8AA
0x14000b823  movsxd  rax, [rsp+280h+var_25C]
0x14000b828  movsxd  rcx, [rsp+280h+var_260]
0x14000b82d  shl     rcx, 1Fh
0x14000b831  or      rcx, rax
0x14000b834  mov     [r14], rcx
0x14000b837  mov     rcx, rbx; hObject
0x14000b83a  call    cs:__imp_CloseHandle
0x14000b840  test    eax, eax
0x14000b842  jz      short loc_14000B8BC
0x14000b844  jmp     short loc_14000B876
0x14000b846  mov     rcx, [rbp+188h]; this
0x14000b84d  mov     edx, 0DCh; void *
0x14000b852  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b857  mov     rcx, rbx; hObject
0x14000b85a  mov     edi, eax
0x14000b85c  call    cs:__imp_CloseHandle
0x14000b862  test    eax, eax
0x14000b864  jz      short loc_14000B8CE
0x14000b866  jmp     loc_14000B78B
0x14000b86b  call    cs:__imp_GetLastError
0x14000b871  cmp     eax, 2
0x14000b874  jnz     short loc_14000B87A
0x14000b876  xor     eax, eax
0x14000b878  jmp     short loc_14000B88B
0x14000b87a  mov     rcx, [rbp+188h]; this
0x14000b881  mov     edx, 0D0h; void *
0x14000b886  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b88b  mov     rcx, [rbp+180h+var_40]
0x14000b892  xor     rcx, rsp; StackCookie
0x14000b895  call    __security_check_cookie
0x14000b89a  add     rsp, 258h
0x14000b8a1  pop     r15
0x14000b8a3  pop     r14
0x14000b8a5  pop     rdi
0x14000b8a6  pop     rsi
0x14000b8a7  pop     rbx
0x14000b8a8  pop     rbp
0x14000b8a9  retn
0x14000b8aa  mov     rcx, [rbp+188h]; this
0x14000b8b1  mov     edx, 0A0Bh; void *
0x14000b8b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b8bc  mov     rcx, [rbp+188h]; this
0x14000b8c3  mov     edx, 0A0Bh; void *
0x14000b8c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b8ce  mov     rcx, [rbp+188h]; this
0x14000b8d5  mov     edx, 0A0Bh; void *
0x14000b8da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b8e0  mov     rcx, [rbp+188h]; this
0x14000b8e7  mov     edx, 0A0Bh; void *
0x14000b8ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b8f2  mov     rcx, [rbp+188h]; this
0x14000b8f9  mov     edx, 0A0Bh; void *
0x14000b8fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000b904  mov     rcx, [rbp+188h]; this
0x14000b90b  mov     edx, 0A0Bh; void *
0x14000b910  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
