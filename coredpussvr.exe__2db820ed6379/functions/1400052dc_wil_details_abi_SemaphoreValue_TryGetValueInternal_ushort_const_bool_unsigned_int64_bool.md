# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400052dc`
- end: `0x140005586`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000308c`

## callees

- `0x140001500`
- `0x140003c68`
- `0x140004a14`
- `0x140004a34`
- `0x140005170`
- `0x1400052dc`
- `0x1400056e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005370`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400053f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005370`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400053f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400054d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400054d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400053bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000544a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400054bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400053bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000544a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400054bf`

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
0x1400052dc  push    rbp
0x1400052de  push    rbx
0x1400052df  push    rsi
0x1400052e0  push    rdi
0x1400052e1  push    r14
0x1400052e3  push    r15
0x1400052e5  lea     rbp, [rsp-158h]
0x1400052ed  sub     rsp, 258h
0x1400052f4  mov     rax, cs:__security_cookie
0x1400052fb  xor     rax, rsp
0x1400052fe  mov     [rbp+180h+var_40], rax
0x140005305  xor     r15d, r15d
0x140005308  lea     rax, [rsp+280h+Name]
0x14000530d  mov     [r8], r15
0x140005310  mov     r14, r8
0x140005313  mov     edx, 104h
0x140005318  mov     r9d, 7FFFFFFEh
0x14000531e  test    r9, r9
0x140005321  jz      short loc_140005342
0x140005323  movzx   r8d, word ptr [rcx]
0x140005327  test    r8w, r8w
0x14000532b  jz      short loc_140005342
0x14000532d  mov     [rax], r8w
0x140005331  add     rcx, 2
0x140005335  add     rax, 2
0x140005339  dec     r9
0x14000533c  sub     rdx, 1; unsigned __int64
0x140005340  jnz     short loc_14000531E
0x140005342  test    rdx, rdx
0x140005345  lea     rcx, [rax-2]
0x140005349  lea     r8, aP0; "_p0"
0x140005350  cmovnz  rcx, rax
0x140005354  mov     [rcx], r15w
0x140005358  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000535d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005362  mov     esi, 1F0003h
0x140005367  lea     r8, [rsp+280h+Name]; lpName
0x14000536c  mov     ecx, esi; dwDesiredAccess
0x14000536e  xor     edx, edx; bInheritHandle
0x140005370  call    cs:__imp_OpenSemaphoreW
0x140005377  nop     dword ptr [rax+rax+00h]
0x14000537c  mov     rbx, rax
0x14000537f  test    rax, rax
0x140005382  jz      loc_1400054D4
0x140005388  lea     rdx, [rsp+280h+var_25C]; int *
0x14000538d  mov     [rsp+280h+var_25C], r15d
0x140005392  mov     rcx, rax; hHandle
0x140005395  mov     [rsp+280h+var_260], r15d; int
0x14000539a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000539f  mov     edi, eax
0x1400053a1  test    eax, eax
0x1400053a3  jns     short loc_1400053D7
0x1400053a5  mov     rcx, [rbp+188h]; this
0x1400053ac  mov     r9d, eax; char *
0x1400053af  mov     edx, 0D6h; void *
0x1400053b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400053b9  mov     rcx, rbx; hObject
0x1400053bc  call    cs:__imp_CloseHandle
0x1400053c3  nop     dword ptr [rax+rax+00h]
0x1400053c8  test    eax, eax
0x1400053ca  jz      loc_140005550
0x1400053d0  mov     eax, edi
0x1400053d2  jmp     loc_1400054FA
0x1400053d7  lea     r8, asc_14000BDA0; "h"
0x1400053de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400053e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400053e8  lea     r8, [rsp+280h+Name]; lpName
0x1400053ed  xor     edx, edx; bInheritHandle
0x1400053ef  mov     ecx, esi; dwDesiredAccess
0x1400053f1  call    cs:__imp_OpenSemaphoreW
0x1400053f8  nop     dword ptr [rax+rax+00h]
0x1400053fd  mov     rdi, rax
0x140005400  test    rax, rax
0x140005403  jz      loc_1400054A9
0x140005409  lea     rdx, [rsp+280h+var_260]; int *
0x14000540e  mov     rcx, rax; hHandle
0x140005411  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005416  mov     esi, eax
0x140005418  test    eax, eax
0x14000541a  jns     short loc_140005465
0x14000541c  mov     rcx, [rbp+188h]; this
0x140005423  mov     r9d, eax; char *
0x140005426  mov     edx, 0DEh; void *
0x14000542b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005430  mov     rcx, rdi; hObject
0x140005433  call    cs:__imp_CloseHandle
0x14000543a  nop     dword ptr [rax+rax+00h]
0x14000543f  test    eax, eax
0x140005441  jz      loc_140005562
0x140005447  mov     rcx, rbx; hObject
0x14000544a  call    cs:__imp_CloseHandle
0x140005451  nop     dword ptr [rax+rax+00h]
0x140005456  test    eax, eax
0x140005458  jz      loc_140005574
0x14000545e  mov     eax, esi
0x140005460  jmp     loc_1400054FA
0x140005465  mov     rcx, rdi; hObject
0x140005468  call    cs:__imp_CloseHandle
0x14000546f  nop     dword ptr [rax+rax+00h]
0x140005474  test    eax, eax
0x140005476  jz      loc_14000551A
0x14000547c  movsxd  rax, [rsp+280h+var_25C]
0x140005481  movsxd  rcx, [rsp+280h+var_260]
0x140005486  shl     rcx, 1Fh
0x14000548a  or      rcx, rax
0x14000548d  mov     [r14], rcx
0x140005490  mov     rcx, rbx; hObject
0x140005493  call    cs:__imp_CloseHandle
0x14000549a  nop     dword ptr [rax+rax+00h]
0x14000549f  test    eax, eax
0x1400054a1  jz      loc_14000552C
0x1400054a7  jmp     short loc_1400054E5
0x1400054a9  mov     rcx, [rbp+188h]; this
0x1400054b0  mov     edx, 0DCh; void *
0x1400054b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400054ba  mov     rcx, rbx; hObject
0x1400054bd  mov     edi, eax
0x1400054bf  call    cs:__imp_CloseHandle
0x1400054c6  nop     dword ptr [rax+rax+00h]
0x1400054cb  test    eax, eax
0x1400054cd  jz      short loc_14000553E
0x1400054cf  jmp     loc_1400053D0
0x1400054d4  call    cs:__imp_GetLastError
0x1400054db  nop     dword ptr [rax+rax+00h]
0x1400054e0  cmp     eax, 2
0x1400054e3  jnz     short loc_1400054E9
0x1400054e5  xor     eax, eax
0x1400054e7  jmp     short loc_1400054FA
0x1400054e9  mov     rcx, [rbp+188h]; this
0x1400054f0  mov     edx, 0D0h; void *
0x1400054f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400054fa  mov     rcx, [rbp+180h+var_40]
0x140005501  xor     rcx, rsp; StackCookie
0x140005504  call    __security_check_cookie
0x140005509  add     rsp, 258h
0x140005510  pop     r15
0x140005512  pop     r14
0x140005514  pop     rdi
0x140005515  pop     rsi
0x140005516  pop     rbx
0x140005517  pop     rbp
0x140005518  retn
0x14000551a  mov     rcx, [rbp+188h]; this
0x140005521  mov     edx, 0A0Bh; void *
0x140005526  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000552c  mov     rcx, [rbp+188h]; this
0x140005533  mov     edx, 0A0Bh; void *
0x140005538  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000553e  mov     rcx, [rbp+188h]; this
0x140005545  mov     edx, 0A0Bh; void *
0x14000554a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005550  mov     rcx, [rbp+188h]; this
0x140005557  mov     edx, 0A0Bh; void *
0x14000555c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005562  mov     rcx, [rbp+188h]; this
0x140005569  mov     edx, 0A0Bh; void *
0x14000556e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005574  mov     rcx, [rbp+188h]; this
0x14000557b  mov     edx, 0A0Bh; void *
0x140005580  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
