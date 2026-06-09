# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180025aac`
- end: `0x180025d65`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c684`
- `0x18001ca7c`

## callees

- `0x18001e070`
- `0x180024f48`
- `0x180024f68`
- `0x180025528`
- `0x180025aac`
- `0x180026398`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025b4b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025bf3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025b4b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025cba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025cba`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  unsigned int LastError; // edi
  unsigned int v19; // r8d
  const char *v20; // r9
  HANDLE v21; // rax
  unsigned int v22; // r8d
  const char *v23; // r9
  void *v24; // rdi
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // esi
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+28h] [rbp-E0h] BYREF
  int v39[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v12, v13);
    return 0;
  }
  v39[0] = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v17, (const char *)(unsigned int)ValueFromSemaphore, v38);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v19, v20);
    return LastError;
  }
  StringCchCatW(Name, v16, L"h");
  v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v21;
  if ( !v21 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v22, v23);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v25, v26);
    return LastError;
  }
  v27 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v38);
  v29 = v27;
  if ( v27 >= 0 )
  {
    if ( !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
    *a3 = v39[0] | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v36, v37);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v28, (const char *)(unsigned int)v27, v38);
  if ( !CloseHandle(v24) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v30, v31);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v32, v33);
  return v29;
}

```

## disassembly

```asm
0x180025aac  mov     rax, rsp
0x180025aaf  mov     [rax+8], rbx
0x180025ab3  mov     [rax+10h], rsi
0x180025ab7  mov     [rax+20h], rdi
0x180025abb  push    rbp
0x180025abc  push    r14
0x180025abe  push    r15
0x180025ac0  lea     rbp, [rax-168h]
0x180025ac7  sub     rsp, 250h
0x180025ace  mov     rax, cs:__security_cookie
0x180025ad5  xor     rax, rsp
0x180025ad8  mov     [rbp+160h+var_20], rax
0x180025adf  xor     r15d, r15d
0x180025ae2  lea     rax, [rsp+260h+Name]
0x180025ae7  mov     [r8], r15
0x180025aea  lea     rdx, [rsp+260h+Name]
0x180025aef  sub     rcx, rax
0x180025af2  mov     r14, r8
0x180025af5  mov     r9d, 104h
0x180025afb  lea     rax, [r9+7FFFFEFAh]
0x180025b02  test    rax, rax
0x180025b05  jz      short loc_180025B1D
0x180025b07  movzx   eax, word ptr [rcx+rdx]
0x180025b0b  test    ax, ax
0x180025b0e  jz      short loc_180025B1D
0x180025b10  mov     [rdx], ax
0x180025b13  add     rdx, 2; unsigned __int64
0x180025b17  sub     r9, 1
0x180025b1b  jnz     short loc_180025AFB
0x180025b1d  test    r9, r9
0x180025b20  lea     rax, [rdx-2]
0x180025b24  lea     r8, aP0; "_p0"
0x180025b2b  cmovnz  rax, rdx
0x180025b2f  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180025b34  mov     [rax], r15w
0x180025b38  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025b3d  mov     esi, 1F0003h
0x180025b42  lea     r8, [rsp+260h+Name]; lpName
0x180025b47  mov     ecx, esi; dwDesiredAccess
0x180025b49  xor     edx, edx; bInheritHandle
0x180025b4b  call    cs:__imp_OpenSemaphoreW
0x180025b52  nop     dword ptr [rax+rax+00h]
0x180025b57  mov     rbx, rax
0x180025b5a  test    rax, rax
0x180025b5d  jnz     short loc_180025B8A
0x180025b5f  call    cs:__imp_GetLastError
0x180025b66  nop     dword ptr [rax+rax+00h]
0x180025b6b  cmp     eax, 2
0x180025b6e  jz      loc_180025CCA
0x180025b74  mov     rcx, [rbp+168h]; this
0x180025b7b  mov     edx, 0CDh; void *
0x180025b80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025b85  jmp     loc_180025CCC
0x180025b8a  lea     rdx, [rsp+260h+var_23C]; int *
0x180025b8f  mov     [rsp+260h+var_23C], r15d
0x180025b94  mov     rcx, rbx; hHandle
0x180025b97  mov     [rsp+260h+var_240], r15d; int
0x180025b9c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180025ba1  mov     edi, eax
0x180025ba3  test    eax, eax
0x180025ba5  jns     short loc_180025BD9
0x180025ba7  mov     rcx, [rbp+168h]; this
0x180025bae  mov     r9d, eax; char *
0x180025bb1  mov     edx, 0D3h; void *
0x180025bb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025bbb  mov     rcx, rbx; hObject
0x180025bbe  call    cs:__imp_CloseHandle
0x180025bc5  nop     dword ptr [rax+rax+00h]
0x180025bca  test    eax, eax
0x180025bcc  jz      loc_180025D1D
0x180025bd2  mov     eax, edi
0x180025bd4  jmp     loc_180025CCC
0x180025bd9  lea     r8, asc_180035100; "h"
0x180025be0  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180025be5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025bea  lea     r8, [rsp+260h+Name]; lpName
0x180025bef  xor     edx, edx; bInheritHandle
0x180025bf1  mov     ecx, esi; dwDesiredAccess
0x180025bf3  call    cs:__imp_OpenSemaphoreW
0x180025bfa  nop     dword ptr [rax+rax+00h]
0x180025bff  mov     rdi, rax
0x180025c02  test    rax, rax
0x180025c05  jnz     short loc_180025C33
0x180025c07  mov     rcx, [rbp+168h]; this
0x180025c0e  mov     edx, 0D9h; void *
0x180025c13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025c18  mov     rcx, rbx; hObject
0x180025c1b  mov     edi, eax
0x180025c1d  call    cs:__imp_CloseHandle
0x180025c24  nop     dword ptr [rax+rax+00h]
0x180025c29  test    eax, eax
0x180025c2b  jz      loc_180025D0B
0x180025c31  jmp     short loc_180025BD2
0x180025c33  lea     rdx, [rsp+260h+var_240]; int *
0x180025c38  mov     rcx, rdi; hHandle
0x180025c3b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180025c40  mov     esi, eax
0x180025c42  test    eax, eax
0x180025c44  jns     short loc_180025C8C
0x180025c46  mov     rcx, [rbp+168h]; this
0x180025c4d  mov     r9d, eax; char *
0x180025c50  mov     edx, 0DBh; void *
0x180025c55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c5a  mov     rcx, rdi; hObject
0x180025c5d  call    cs:__imp_CloseHandle
0x180025c64  nop     dword ptr [rax+rax+00h]
0x180025c69  test    eax, eax
0x180025c6b  jz      loc_180025D2F
0x180025c71  mov     rcx, rbx; hObject
0x180025c74  call    cs:__imp_CloseHandle
0x180025c7b  nop     dword ptr [rax+rax+00h]
0x180025c80  test    eax, eax
0x180025c82  jz      loc_180025D41
0x180025c88  mov     eax, esi
0x180025c8a  jmp     short loc_180025CCC
0x180025c8c  mov     rcx, rdi; hObject
0x180025c8f  call    cs:__imp_CloseHandle
0x180025c96  nop     dword ptr [rax+rax+00h]
0x180025c9b  test    eax, eax
0x180025c9d  jz      loc_180025D53
0x180025ca3  movsxd  rax, [rsp+260h+var_23C]
0x180025ca8  movsxd  rcx, [rsp+260h+var_240]
0x180025cad  shl     rcx, 1Fh
0x180025cb1  or      rcx, rax
0x180025cb4  mov     [r14], rcx
0x180025cb7  mov     rcx, rbx; hObject
0x180025cba  call    cs:__imp_CloseHandle
0x180025cc1  nop     dword ptr [rax+rax+00h]
0x180025cc6  test    eax, eax
0x180025cc8  jz      short loc_180025CF9
0x180025cca  xor     eax, eax
0x180025ccc  mov     rcx, [rbp+160h+var_20]
0x180025cd3  xor     rcx, rsp; StackCookie
0x180025cd6  call    __security_check_cookie
0x180025cdb  lea     r11, [rsp+260h+var_10]
0x180025ce3  mov     rbx, [r11+20h]
0x180025ce7  mov     rsi, [r11+28h]
0x180025ceb  mov     rdi, [r11+38h]
0x180025cef  mov     rsp, r11
0x180025cf2  pop     r15
0x180025cf4  pop     r14
0x180025cf6  pop     rbp
0x180025cf7  retn
0x180025cf9  mov     rcx, [rbp+168h]; this
0x180025d00  mov     edx, 9DDh; void *
0x180025d05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180025d0b  mov     rcx, [rbp+168h]; this
0x180025d12  mov     edx, 9DDh; void *
0x180025d17  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180025d1d  mov     rcx, [rbp+168h]; this
0x180025d24  mov     edx, 9DDh; void *
0x180025d29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180025d2f  mov     rcx, [rbp+168h]; this
0x180025d36  mov     edx, 9DDh; void *
0x180025d3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180025d41  mov     rcx, [rbp+168h]; this
0x180025d48  mov     edx, 9DDh; void *
0x180025d4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180025d53  mov     rcx, [rbp+168h]; this
0x180025d5a  mov     edx, 9DDh; void *
0x180025d5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
