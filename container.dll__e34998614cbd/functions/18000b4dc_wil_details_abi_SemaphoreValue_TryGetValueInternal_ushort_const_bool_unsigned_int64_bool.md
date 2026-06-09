# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b4dc`
- end: `0x18000b786`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005c6c`
- `0x180006018`

## callees

- `0x180002ad0`
- `0x1800078d8`
- `0x18000a2f4`
- `0x18000a314`
- `0x18000af80`
- `0x18000b4dc`
- `0x18000bdac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b570`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b5f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b570`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b64a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b64a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6bf`

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
0x18000b4dc  push    rbp
0x18000b4de  push    rbx
0x18000b4df  push    rsi
0x18000b4e0  push    rdi
0x18000b4e1  push    r14
0x18000b4e3  push    r15
0x18000b4e5  lea     rbp, [rsp-158h]
0x18000b4ed  sub     rsp, 258h
0x18000b4f4  mov     rax, cs:__security_cookie
0x18000b4fb  xor     rax, rsp
0x18000b4fe  mov     [rbp+180h+var_40], rax
0x18000b505  xor     r15d, r15d
0x18000b508  lea     rax, [rsp+280h+Name]
0x18000b50d  mov     [r8], r15
0x18000b510  mov     r14, r8
0x18000b513  mov     edx, 104h
0x18000b518  mov     r9d, 7FFFFFFEh
0x18000b51e  test    r9, r9
0x18000b521  jz      short loc_18000B542
0x18000b523  movzx   r8d, word ptr [rcx]
0x18000b527  test    r8w, r8w
0x18000b52b  jz      short loc_18000B542
0x18000b52d  mov     [rax], r8w
0x18000b531  add     rcx, 2
0x18000b535  add     rax, 2
0x18000b539  dec     r9
0x18000b53c  sub     rdx, 1; unsigned __int64
0x18000b540  jnz     short loc_18000B51E
0x18000b542  test    rdx, rdx
0x18000b545  lea     rcx, [rax-2]
0x18000b549  lea     r8, aP0; "_p0"
0x18000b550  cmovnz  rcx, rax
0x18000b554  mov     [rcx], r15w
0x18000b558  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b55d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b562  mov     esi, 1F0003h
0x18000b567  lea     r8, [rsp+280h+Name]; lpName
0x18000b56c  mov     ecx, esi; dwDesiredAccess
0x18000b56e  xor     edx, edx; bInheritHandle
0x18000b570  call    cs:__imp_OpenSemaphoreW
0x18000b577  nop     dword ptr [rax+rax+00h]
0x18000b57c  mov     rbx, rax
0x18000b57f  test    rax, rax
0x18000b582  jz      loc_18000B6D4
0x18000b588  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b58d  mov     [rsp+280h+var_25C], r15d
0x18000b592  mov     rcx, rax; hHandle
0x18000b595  mov     [rsp+280h+var_260], r15d; int
0x18000b59a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b59f  mov     edi, eax
0x18000b5a1  test    eax, eax
0x18000b5a3  jns     short loc_18000B5D7
0x18000b5a5  mov     rcx, [rbp+188h]; this
0x18000b5ac  mov     r9d, eax; char *
0x18000b5af  mov     edx, 0D6h; void *
0x18000b5b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5b9  mov     rcx, rbx; hObject
0x18000b5bc  call    cs:__imp_CloseHandle
0x18000b5c3  nop     dword ptr [rax+rax+00h]
0x18000b5c8  test    eax, eax
0x18000b5ca  jz      loc_18000B750
0x18000b5d0  mov     eax, edi
0x18000b5d2  jmp     loc_18000B6FA
0x18000b5d7  lea     r8, asc_180038100; "h"
0x18000b5de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b5e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b5e8  lea     r8, [rsp+280h+Name]; lpName
0x18000b5ed  xor     edx, edx; bInheritHandle
0x18000b5ef  mov     ecx, esi; dwDesiredAccess
0x18000b5f1  call    cs:__imp_OpenSemaphoreW
0x18000b5f8  nop     dword ptr [rax+rax+00h]
0x18000b5fd  mov     rdi, rax
0x18000b600  test    rax, rax
0x18000b603  jz      loc_18000B6A9
0x18000b609  lea     rdx, [rsp+280h+var_260]; int *
0x18000b60e  mov     rcx, rax; hHandle
0x18000b611  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b616  mov     esi, eax
0x18000b618  test    eax, eax
0x18000b61a  jns     short loc_18000B665
0x18000b61c  mov     rcx, [rbp+188h]; this
0x18000b623  mov     r9d, eax; char *
0x18000b626  mov     edx, 0DEh; void *
0x18000b62b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b630  mov     rcx, rdi; hObject
0x18000b633  call    cs:__imp_CloseHandle
0x18000b63a  nop     dword ptr [rax+rax+00h]
0x18000b63f  test    eax, eax
0x18000b641  jz      loc_18000B762
0x18000b647  mov     rcx, rbx; hObject
0x18000b64a  call    cs:__imp_CloseHandle
0x18000b651  nop     dword ptr [rax+rax+00h]
0x18000b656  test    eax, eax
0x18000b658  jz      loc_18000B774
0x18000b65e  mov     eax, esi
0x18000b660  jmp     loc_18000B6FA
0x18000b665  mov     rcx, rdi; hObject
0x18000b668  call    cs:__imp_CloseHandle
0x18000b66f  nop     dword ptr [rax+rax+00h]
0x18000b674  test    eax, eax
0x18000b676  jz      loc_18000B71A
0x18000b67c  movsxd  rax, [rsp+280h+var_25C]
0x18000b681  movsxd  rcx, [rsp+280h+var_260]
0x18000b686  shl     rcx, 1Fh
0x18000b68a  or      rcx, rax
0x18000b68d  mov     [r14], rcx
0x18000b690  mov     rcx, rbx; hObject
0x18000b693  call    cs:__imp_CloseHandle
0x18000b69a  nop     dword ptr [rax+rax+00h]
0x18000b69f  test    eax, eax
0x18000b6a1  jz      loc_18000B72C
0x18000b6a7  jmp     short loc_18000B6E5
0x18000b6a9  mov     rcx, [rbp+188h]; this
0x18000b6b0  mov     edx, 0DCh; void *
0x18000b6b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b6ba  mov     rcx, rbx; hObject
0x18000b6bd  mov     edi, eax
0x18000b6bf  call    cs:__imp_CloseHandle
0x18000b6c6  nop     dword ptr [rax+rax+00h]
0x18000b6cb  test    eax, eax
0x18000b6cd  jz      short loc_18000B73E
0x18000b6cf  jmp     loc_18000B5D0
0x18000b6d4  call    cs:__imp_GetLastError
0x18000b6db  nop     dword ptr [rax+rax+00h]
0x18000b6e0  cmp     eax, 2
0x18000b6e3  jnz     short loc_18000B6E9
0x18000b6e5  xor     eax, eax
0x18000b6e7  jmp     short loc_18000B6FA
0x18000b6e9  mov     rcx, [rbp+188h]; this
0x18000b6f0  mov     edx, 0D0h; void *
0x18000b6f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b6fa  mov     rcx, [rbp+180h+var_40]
0x18000b701  xor     rcx, rsp; StackCookie
0x18000b704  call    __security_check_cookie
0x18000b709  add     rsp, 258h
0x18000b710  pop     r15
0x18000b712  pop     r14
0x18000b714  pop     rdi
0x18000b715  pop     rsi
0x18000b716  pop     rbx
0x18000b717  pop     rbp
0x18000b718  retn
0x18000b71a  mov     rcx, [rbp+188h]; this
0x18000b721  mov     edx, 0A0Bh; void *
0x18000b726  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b72c  mov     rcx, [rbp+188h]; this
0x18000b733  mov     edx, 0A0Bh; void *
0x18000b738  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b73e  mov     rcx, [rbp+188h]; this
0x18000b745  mov     edx, 0A0Bh; void *
0x18000b74a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b750  mov     rcx, [rbp+188h]; this
0x18000b757  mov     edx, 0A0Bh; void *
0x18000b75c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b762  mov     rcx, [rbp+188h]; this
0x18000b769  mov     edx, 0A0Bh; void *
0x18000b76e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b774  mov     rcx, [rbp+188h]; this
0x18000b77b  mov     edx, 0A0Bh; void *
0x18000b780  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
