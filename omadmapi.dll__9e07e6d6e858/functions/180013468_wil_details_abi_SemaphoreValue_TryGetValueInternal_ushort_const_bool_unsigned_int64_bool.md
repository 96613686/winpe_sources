# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180013468`
- end: `0x180013737`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a8a4`
- `0x18000ac80`

## callees

- `0x1800031b0`
- `0x18000d260`
- `0x180011b78`
- `0x180011b98`
- `0x180012ef0`
- `0x180013468`
- `0x180013cf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001367e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001367e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800134ff`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001358d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800134ff`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001358d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001360b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001360b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013669`

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
0x180013468  push    rbp
0x18001346a  push    rbx
0x18001346b  push    rsi
0x18001346c  push    rdi
0x18001346d  push    r14
0x18001346f  push    r15
0x180013471  lea     rbp, [rsp-158h]
0x180013479  sub     rsp, 258h
0x180013480  mov     rax, cs:__security_cookie
0x180013487  xor     rax, rsp
0x18001348a  mov     [rbp+180h+var_40], rax
0x180013491  xor     r15d, r15d
0x180013494  lea     rax, [rsp+280h+Name]
0x180013499  mov     esi, 104h
0x18001349e  mov     [r8], r15
0x1800134a1  mov     edx, esi
0x1800134a3  mov     r14, r8
0x1800134a6  mov     r9d, 7FFFFFFEh
0x1800134ac  test    r9, r9
0x1800134af  jz      short loc_1800134D0
0x1800134b1  movzx   r8d, word ptr [rcx]
0x1800134b5  test    r8w, r8w
0x1800134b9  jz      short loc_1800134D0
0x1800134bb  mov     [rax], r8w
0x1800134bf  add     rcx, 2
0x1800134c3  add     rax, 2
0x1800134c7  dec     r9
0x1800134ca  sub     rdx, 1
0x1800134ce  jnz     short loc_1800134AC
0x1800134d0  test    rdx, rdx
0x1800134d3  lea     rcx, [rax-2]
0x1800134d7  lea     r8, aP0; "_p0"
0x1800134de  mov     rdx, rsi; unsigned __int64
0x1800134e1  cmovnz  rcx, rax
0x1800134e5  mov     [rcx], r15w
0x1800134e9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800134ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800134f3  lea     r8, [rsp+280h+Name]; lpName
0x1800134f8  xor     edx, edx; bInheritHandle
0x1800134fa  mov     ecx, 1F0003h; dwDesiredAccess
0x1800134ff  call    cs:__imp_OpenSemaphoreW
0x180013506  nop     dword ptr [rax+rax+00h]
0x18001350b  mov     rbx, rax
0x18001350e  test    rax, rax
0x180013511  jz      loc_18001367E
0x180013517  lea     rdx, [rsp+280h+var_25C]; int *
0x18001351c  mov     [rsp+280h+var_25C], r15d
0x180013521  mov     rcx, rax; hHandle
0x180013524  mov     [rsp+280h+var_260], r15d; int
0x180013529  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001352e  mov     edi, eax
0x180013530  test    eax, eax
0x180013532  jns     short loc_18001356D
0x180013534  mov     rcx, [rbp+188h]; this
0x18001353b  lea     r8, aWil; "wil"
0x180013542  mov     r9d, eax; char *
0x180013545  mov     edx, 0D6h; void *
0x18001354a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001354f  mov     rcx, rbx; hObject
0x180013552  call    cs:__imp_CloseHandle
0x180013559  nop     dword ptr [rax+rax+00h]
0x18001355e  test    eax, eax
0x180013560  jz      loc_180013701
0x180013566  mov     eax, edi
0x180013568  jmp     loc_1800136AB
0x18001356d  lea     r8, asc_180028B30; "h"
0x180013574  mov     rdx, rsi; unsigned __int64
0x180013577  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001357c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013581  lea     r8, [rsp+280h+Name]; lpName
0x180013586  xor     edx, edx; bInheritHandle
0x180013588  mov     ecx, 1F0003h; dwDesiredAccess
0x18001358d  call    cs:__imp_OpenSemaphoreW
0x180013594  nop     dword ptr [rax+rax+00h]
0x180013599  mov     rdi, rax
0x18001359c  test    rax, rax
0x18001359f  jz      loc_18001364C
0x1800135a5  lea     rdx, [rsp+280h+var_260]; int *
0x1800135aa  mov     rcx, rax; hHandle
0x1800135ad  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800135b2  mov     esi, eax
0x1800135b4  test    eax, eax
0x1800135b6  jns     short loc_180013608
0x1800135b8  mov     rcx, [rbp+188h]; this
0x1800135bf  lea     r8, aWil; "wil"
0x1800135c6  mov     r9d, eax; char *
0x1800135c9  mov     edx, 0DEh; void *
0x1800135ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800135d3  mov     rcx, rdi; hObject
0x1800135d6  call    cs:__imp_CloseHandle
0x1800135dd  nop     dword ptr [rax+rax+00h]
0x1800135e2  test    eax, eax
0x1800135e4  jz      loc_180013713
0x1800135ea  mov     rcx, rbx; hObject
0x1800135ed  call    cs:__imp_CloseHandle
0x1800135f4  nop     dword ptr [rax+rax+00h]
0x1800135f9  test    eax, eax
0x1800135fb  jz      loc_180013725
0x180013601  mov     eax, esi
0x180013603  jmp     loc_1800136AB
0x180013608  mov     rcx, rdi; hObject
0x18001360b  call    cs:__imp_CloseHandle
0x180013612  nop     dword ptr [rax+rax+00h]
0x180013617  test    eax, eax
0x180013619  jz      loc_1800136CB
0x18001361f  movsxd  rax, [rsp+280h+var_25C]
0x180013624  movsxd  rcx, [rsp+280h+var_260]
0x180013629  shl     rcx, 1Fh
0x18001362d  or      rcx, rax
0x180013630  mov     [r14], rcx
0x180013633  mov     rcx, rbx; hObject
0x180013636  call    cs:__imp_CloseHandle
0x18001363d  nop     dword ptr [rax+rax+00h]
0x180013642  test    eax, eax
0x180013644  jz      loc_1800136DD
0x18001364a  jmp     short loc_18001368F
0x18001364c  mov     rcx, [rbp+188h]; this
0x180013653  lea     r8, aWil; "wil"
0x18001365a  mov     edx, 0DCh; void *
0x18001365f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013664  mov     rcx, rbx; hObject
0x180013667  mov     edi, eax
0x180013669  call    cs:__imp_CloseHandle
0x180013670  nop     dword ptr [rax+rax+00h]
0x180013675  test    eax, eax
0x180013677  jz      short loc_1800136EF
0x180013679  jmp     loc_180013566
0x18001367e  call    cs:__imp_GetLastError
0x180013685  nop     dword ptr [rax+rax+00h]
0x18001368a  cmp     eax, 2
0x18001368d  jnz     short loc_180013693
0x18001368f  xor     eax, eax
0x180013691  jmp     short loc_1800136AB
0x180013693  mov     rcx, [rbp+188h]; this
0x18001369a  lea     r8, aWil; "wil"
0x1800136a1  mov     edx, 0D0h; void *
0x1800136a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800136ab  mov     rcx, [rbp+180h+var_40]
0x1800136b2  xor     rcx, rsp; StackCookie
0x1800136b5  call    __security_check_cookie
0x1800136ba  add     rsp, 258h
0x1800136c1  pop     r15
0x1800136c3  pop     r14
0x1800136c5  pop     rdi
0x1800136c6  pop     rsi
0x1800136c7  pop     rbx
0x1800136c8  pop     rbp
0x1800136c9  retn
0x1800136cb  mov     rcx, [rbp+188h]; this
0x1800136d2  mov     edx, 0A0Bh; void *
0x1800136d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800136dd  mov     rcx, [rbp+188h]; this
0x1800136e4  mov     edx, 0A0Bh; void *
0x1800136e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800136ef  mov     rcx, [rbp+188h]; this
0x1800136f6  mov     edx, 0A0Bh; void *
0x1800136fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013701  mov     rcx, [rbp+188h]; this
0x180013708  mov     edx, 0A0Bh; void *
0x18001370d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013713  mov     rcx, [rbp+188h]; this
0x18001371a  mov     edx, 0A0Bh; void *
0x18001371f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013725  mov     rcx, [rbp+188h]; this
0x18001372c  mov     edx, 0A0Bh; void *
0x180013731  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
