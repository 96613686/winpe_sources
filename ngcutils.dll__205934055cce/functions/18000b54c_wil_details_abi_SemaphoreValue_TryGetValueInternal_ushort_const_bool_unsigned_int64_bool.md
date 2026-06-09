# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b54c`
- end: `0x18000b7e4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006ce8`
- `0x1800070c4`

## callees

- `0x180003080`
- `0x1800086b4`
- `0x18000a594`
- `0x18000a5b4`
- `0x18000b004`
- `0x18000b54c`
- `0x18000be2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b5e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b665`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b5e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b723`

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
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000b54c  push    rbp
0x18000b54e  push    rbx
0x18000b54f  push    rsi
0x18000b550  push    rdi
0x18000b551  push    r14
0x18000b553  push    r15
0x18000b555  lea     rbp, [rsp-158h]
0x18000b55d  sub     rsp, 258h
0x18000b564  mov     rax, cs:__security_cookie
0x18000b56b  xor     rax, rsp
0x18000b56e  mov     [rbp+180h+var_40], rax
0x18000b575  xor     r15d, r15d
0x18000b578  lea     rax, [rsp+280h+Name]
0x18000b57d  mov     esi, 104h
0x18000b582  mov     [r8], r15
0x18000b585  mov     edx, esi
0x18000b587  mov     r14, r8
0x18000b58a  mov     r9d, 7FFFFFFEh
0x18000b590  test    r9, r9
0x18000b593  jz      short loc_18000B5B4
0x18000b595  movzx   r8d, word ptr [rcx]
0x18000b599  test    r8w, r8w
0x18000b59d  jz      short loc_18000B5B4
0x18000b59f  mov     [rax], r8w
0x18000b5a3  add     rcx, 2
0x18000b5a7  add     rax, 2
0x18000b5ab  dec     r9
0x18000b5ae  sub     rdx, 1
0x18000b5b2  jnz     short loc_18000B590
0x18000b5b4  test    rdx, rdx
0x18000b5b7  lea     rcx, [rax-2]
0x18000b5bb  lea     r8, aP0; "_p0"
0x18000b5c2  mov     rdx, rsi; unsigned __int64
0x18000b5c5  cmovnz  rcx, rax
0x18000b5c9  mov     [rcx], r15w
0x18000b5cd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b5d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b5d7  lea     r8, [rsp+280h+Name]; lpName
0x18000b5dc  xor     edx, edx; bInheritHandle
0x18000b5de  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b5e3  call    cs:__imp_OpenSemaphoreW
0x18000b5e9  mov     rbx, rax
0x18000b5ec  test    rax, rax
0x18000b5ef  jz      loc_18000B732
0x18000b5f5  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b5fa  mov     [rsp+280h+var_25C], r15d
0x18000b5ff  mov     rcx, rax; hHandle
0x18000b602  mov     [rsp+280h+var_260], r15d; int
0x18000b607  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b60c  mov     edi, eax
0x18000b60e  test    eax, eax
0x18000b610  jns     short loc_18000B645
0x18000b612  mov     rcx, [rbp+188h]; this
0x18000b619  lea     r8, aWil; "wil"
0x18000b620  mov     r9d, eax; char *
0x18000b623  mov     edx, 0D6h; void *
0x18000b628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b62d  mov     rcx, rbx; hObject
0x18000b630  call    cs:__imp_CloseHandle
0x18000b636  test    eax, eax
0x18000b638  jz      loc_18000B7AE
0x18000b63e  mov     eax, edi
0x18000b640  jmp     loc_18000B759
0x18000b645  lea     r8, asc_180064860; "h"
0x18000b64c  mov     rdx, rsi; unsigned __int64
0x18000b64f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b654  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b659  lea     r8, [rsp+280h+Name]; lpName
0x18000b65e  xor     edx, edx; bInheritHandle
0x18000b660  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b665  call    cs:__imp_OpenSemaphoreW
0x18000b66b  mov     rdi, rax
0x18000b66e  test    rax, rax
0x18000b671  jz      loc_18000B706
0x18000b677  lea     rdx, [rsp+280h+var_260]; int *
0x18000b67c  mov     rcx, rax; hHandle
0x18000b67f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b684  mov     esi, eax
0x18000b686  test    eax, eax
0x18000b688  jns     short loc_18000B6CE
0x18000b68a  mov     rcx, [rbp+188h]; this
0x18000b691  lea     r8, aWil; "wil"
0x18000b698  mov     r9d, eax; char *
0x18000b69b  mov     edx, 0DEh; void *
0x18000b6a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6a5  mov     rcx, rdi; hObject
0x18000b6a8  call    cs:__imp_CloseHandle
0x18000b6ae  test    eax, eax
0x18000b6b0  jz      loc_18000B7C0
0x18000b6b6  mov     rcx, rbx; hObject
0x18000b6b9  call    cs:__imp_CloseHandle
0x18000b6bf  test    eax, eax
0x18000b6c1  jz      loc_18000B7D2
0x18000b6c7  mov     eax, esi
0x18000b6c9  jmp     loc_18000B759
0x18000b6ce  mov     rcx, rdi; hObject
0x18000b6d1  call    cs:__imp_CloseHandle
0x18000b6d7  test    eax, eax
0x18000b6d9  jz      loc_18000B778
0x18000b6df  movsxd  rax, [rsp+280h+var_25C]
0x18000b6e4  movsxd  rcx, [rsp+280h+var_260]
0x18000b6e9  shl     rcx, 1Fh
0x18000b6ed  or      rcx, rax
0x18000b6f0  mov     [r14], rcx
0x18000b6f3  mov     rcx, rbx; hObject
0x18000b6f6  call    cs:__imp_CloseHandle
0x18000b6fc  test    eax, eax
0x18000b6fe  jz      loc_18000B78A
0x18000b704  jmp     short loc_18000B73D
0x18000b706  mov     rcx, [rbp+188h]; this
0x18000b70d  lea     r8, aWil; "wil"
0x18000b714  mov     edx, 0DCh; void *
0x18000b719  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b71e  mov     rcx, rbx; hObject
0x18000b721  mov     edi, eax
0x18000b723  call    cs:__imp_CloseHandle
0x18000b729  test    eax, eax
0x18000b72b  jz      short loc_18000B79C
0x18000b72d  jmp     loc_18000B63E
0x18000b732  call    cs:__imp_GetLastError
0x18000b738  cmp     eax, 2
0x18000b73b  jnz     short loc_18000B741
0x18000b73d  xor     eax, eax
0x18000b73f  jmp     short loc_18000B759
0x18000b741  mov     rcx, [rbp+188h]; this
0x18000b748  lea     r8, aWil; "wil"
0x18000b74f  mov     edx, 0D0h; void *
0x18000b754  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b759  mov     rcx, [rbp+180h+var_40]
0x18000b760  xor     rcx, rsp; StackCookie
0x18000b763  call    __security_check_cookie
0x18000b768  add     rsp, 258h
0x18000b76f  pop     r15
0x18000b771  pop     r14
0x18000b773  pop     rdi
0x18000b774  pop     rsi
0x18000b775  pop     rbx
0x18000b776  pop     rbp
0x18000b777  retn
0x18000b778  mov     rcx, [rbp+188h]; this
0x18000b77f  mov     edx, 0A0Bh; void *
0x18000b784  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b78a  mov     rcx, [rbp+188h]; this
0x18000b791  mov     edx, 0A0Bh; void *
0x18000b796  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b79c  mov     rcx, [rbp+188h]; this
0x18000b7a3  mov     edx, 0A0Bh; void *
0x18000b7a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b7ae  mov     rcx, [rbp+188h]; this
0x18000b7b5  mov     edx, 0A0Bh; void *
0x18000b7ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b7c0  mov     rcx, [rbp+188h]; this
0x18000b7c7  mov     edx, 0A0Bh; void *
0x18000b7cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b7d2  mov     rcx, [rbp+188h]; this
0x18000b7d9  mov     edx, 0A0Bh; void *
0x18000b7de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
