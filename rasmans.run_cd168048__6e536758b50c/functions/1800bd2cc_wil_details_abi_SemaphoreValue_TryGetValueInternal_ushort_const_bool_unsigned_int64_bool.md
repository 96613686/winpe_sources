# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800bd2cc`
- end: `0x1800bd576`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800b4ea0`
- `0x1800b524c`

## callees

- `0x1800b7dbc`
- `0x1800bc890`
- `0x1800bc8b0`
- `0x1800bcd78`
- `0x1800bd2cc`
- `0x1800bdbb0`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd3ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd4af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd3ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4c4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800bd360`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800bd3e1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800bd360`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800bd3e1`

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
0x1800bd2cc  push    rbp
0x1800bd2ce  push    rbx
0x1800bd2cf  push    rsi
0x1800bd2d0  push    rdi
0x1800bd2d1  push    r14
0x1800bd2d3  push    r15
0x1800bd2d5  lea     rbp, [rsp-158h]
0x1800bd2dd  sub     rsp, 258h
0x1800bd2e4  mov     rax, cs:__security_cookie
0x1800bd2eb  xor     rax, rsp
0x1800bd2ee  mov     [rbp+180h+var_40], rax
0x1800bd2f5  xor     r15d, r15d
0x1800bd2f8  lea     rax, [rsp+280h+Name]
0x1800bd2fd  mov     [r8], r15
0x1800bd300  mov     r14, r8
0x1800bd303  mov     edx, 104h
0x1800bd308  mov     r9d, 7FFFFFFEh
0x1800bd30e  test    r9, r9
0x1800bd311  jz      short loc_1800BD332
0x1800bd313  movzx   r8d, word ptr [rcx]
0x1800bd317  test    r8w, r8w
0x1800bd31b  jz      short loc_1800BD332
0x1800bd31d  mov     [rax], r8w
0x1800bd321  add     rcx, 2
0x1800bd325  add     rax, 2
0x1800bd329  dec     r9
0x1800bd32c  sub     rdx, 1; unsigned __int64
0x1800bd330  jnz     short loc_1800BD30E
0x1800bd332  test    rdx, rdx
0x1800bd335  lea     rcx, [rax-2]
0x1800bd339  lea     r8, aP0; "_p0"
0x1800bd340  cmovnz  rcx, rax
0x1800bd344  mov     [rcx], r15w
0x1800bd348  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800bd34d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bd352  mov     esi, 1F0003h
0x1800bd357  lea     r8, [rsp+280h+Name]; lpName
0x1800bd35c  mov     ecx, esi; dwDesiredAccess
0x1800bd35e  xor     edx, edx; bInheritHandle
0x1800bd360  call    cs:__imp_OpenSemaphoreW
0x1800bd367  nop     dword ptr [rax+rax+00h]
0x1800bd36c  mov     rbx, rax
0x1800bd36f  test    rax, rax
0x1800bd372  jz      loc_1800BD4C4
0x1800bd378  lea     rdx, [rsp+280h+var_25C]; int *
0x1800bd37d  mov     [rsp+280h+var_25C], r15d
0x1800bd382  mov     rcx, rax; hHandle
0x1800bd385  mov     [rsp+280h+var_260], r15d; int
0x1800bd38a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800bd38f  mov     edi, eax
0x1800bd391  test    eax, eax
0x1800bd393  jns     short loc_1800BD3C7
0x1800bd395  mov     rcx, [rbp+188h]; this
0x1800bd39c  mov     r9d, eax; char *
0x1800bd39f  mov     edx, 0D6h; void *
0x1800bd3a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd3a9  mov     rcx, rbx; hObject
0x1800bd3ac  call    cs:__imp_CloseHandle
0x1800bd3b3  nop     dword ptr [rax+rax+00h]
0x1800bd3b8  test    eax, eax
0x1800bd3ba  jz      loc_1800BD540
0x1800bd3c0  mov     eax, edi
0x1800bd3c2  jmp     loc_1800BD4EA
0x1800bd3c7  lea     r8, asc_1800FC9E4; "h"
0x1800bd3ce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800bd3d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bd3d8  lea     r8, [rsp+280h+Name]; lpName
0x1800bd3dd  xor     edx, edx; bInheritHandle
0x1800bd3df  mov     ecx, esi; dwDesiredAccess
0x1800bd3e1  call    cs:__imp_OpenSemaphoreW
0x1800bd3e8  nop     dword ptr [rax+rax+00h]
0x1800bd3ed  mov     rdi, rax
0x1800bd3f0  test    rax, rax
0x1800bd3f3  jz      loc_1800BD499
0x1800bd3f9  lea     rdx, [rsp+280h+var_260]; int *
0x1800bd3fe  mov     rcx, rax; hHandle
0x1800bd401  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800bd406  mov     esi, eax
0x1800bd408  test    eax, eax
0x1800bd40a  jns     short loc_1800BD455
0x1800bd40c  mov     rcx, [rbp+188h]; this
0x1800bd413  mov     r9d, eax; char *
0x1800bd416  mov     edx, 0DEh; void *
0x1800bd41b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd420  mov     rcx, rdi; hObject
0x1800bd423  call    cs:__imp_CloseHandle
0x1800bd42a  nop     dword ptr [rax+rax+00h]
0x1800bd42f  test    eax, eax
0x1800bd431  jz      loc_1800BD552
0x1800bd437  mov     rcx, rbx; hObject
0x1800bd43a  call    cs:__imp_CloseHandle
0x1800bd441  nop     dword ptr [rax+rax+00h]
0x1800bd446  test    eax, eax
0x1800bd448  jz      loc_1800BD564
0x1800bd44e  mov     eax, esi
0x1800bd450  jmp     loc_1800BD4EA
0x1800bd455  mov     rcx, rdi; hObject
0x1800bd458  call    cs:__imp_CloseHandle
0x1800bd45f  nop     dword ptr [rax+rax+00h]
0x1800bd464  test    eax, eax
0x1800bd466  jz      loc_1800BD50A
0x1800bd46c  movsxd  rax, [rsp+280h+var_25C]
0x1800bd471  movsxd  rcx, [rsp+280h+var_260]
0x1800bd476  shl     rcx, 1Fh
0x1800bd47a  or      rcx, rax
0x1800bd47d  mov     [r14], rcx
0x1800bd480  mov     rcx, rbx; hObject
0x1800bd483  call    cs:__imp_CloseHandle
0x1800bd48a  nop     dword ptr [rax+rax+00h]
0x1800bd48f  test    eax, eax
0x1800bd491  jz      loc_1800BD51C
0x1800bd497  jmp     short loc_1800BD4D5
0x1800bd499  mov     rcx, [rbp+188h]; this
0x1800bd4a0  mov     edx, 0DCh; void *
0x1800bd4a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bd4aa  mov     rcx, rbx; hObject
0x1800bd4ad  mov     edi, eax
0x1800bd4af  call    cs:__imp_CloseHandle
0x1800bd4b6  nop     dword ptr [rax+rax+00h]
0x1800bd4bb  test    eax, eax
0x1800bd4bd  jz      short loc_1800BD52E
0x1800bd4bf  jmp     loc_1800BD3C0
0x1800bd4c4  call    cs:__imp_GetLastError
0x1800bd4cb  nop     dword ptr [rax+rax+00h]
0x1800bd4d0  cmp     eax, 2
0x1800bd4d3  jnz     short loc_1800BD4D9
0x1800bd4d5  xor     eax, eax
0x1800bd4d7  jmp     short loc_1800BD4EA
0x1800bd4d9  mov     rcx, [rbp+188h]; this
0x1800bd4e0  mov     edx, 0D0h; void *
0x1800bd4e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bd4ea  mov     rcx, [rbp+180h+var_40]
0x1800bd4f1  xor     rcx, rsp; StackCookie
0x1800bd4f4  call    __security_check_cookie
0x1800bd4f9  add     rsp, 258h
0x1800bd500  pop     r15
0x1800bd502  pop     r14
0x1800bd504  pop     rdi
0x1800bd505  pop     rsi
0x1800bd506  pop     rbx
0x1800bd507  pop     rbp
0x1800bd508  retn
0x1800bd50a  mov     rcx, [rbp+188h]; this
0x1800bd511  mov     edx, 0A0Bh; void *
0x1800bd516  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800bd51c  mov     rcx, [rbp+188h]; this
0x1800bd523  mov     edx, 0A0Bh; void *
0x1800bd528  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800bd52e  mov     rcx, [rbp+188h]; this
0x1800bd535  mov     edx, 0A0Bh; void *
0x1800bd53a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800bd540  mov     rcx, [rbp+188h]; this
0x1800bd547  mov     edx, 0A0Bh; void *
0x1800bd54c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800bd552  mov     rcx, [rbp+188h]; this
0x1800bd559  mov     edx, 0A0Bh; void *
0x1800bd55e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800bd564  mov     rcx, [rbp+188h]; this
0x1800bd56b  mov     edx, 0A0Bh; void *
0x1800bd570  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
