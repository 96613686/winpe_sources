# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000813c`
- end: `0x1800083cb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d50`
- `0x180016630`

## callees

- `0x180006578`
- `0x180007684`
- `0x1800076a4`
- `0x180007e24`
- `0x18000813c`
- `0x18000873c`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800081d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000824c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800081d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000824c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000821d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000828f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000830a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000821d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000828f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000830a`

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
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000813c  push    rbp
0x18000813e  push    rbx
0x18000813f  push    rsi
0x180008140  push    rdi
0x180008141  push    r14
0x180008143  push    r15
0x180008145  lea     rbp, [rsp-158h]
0x18000814d  sub     rsp, 258h
0x180008154  mov     rax, cs:__security_cookie
0x18000815b  xor     rax, rsp
0x18000815e  mov     [rbp+180h+var_40], rax
0x180008165  xor     r15d, r15d
0x180008168  lea     rax, [rsp+280h+Name]
0x18000816d  mov     [r8], r15
0x180008170  mov     r14, r8
0x180008173  mov     edx, 104h
0x180008178  mov     r9d, 7FFFFFFEh
0x18000817e  test    r9, r9
0x180008181  jz      short loc_1800081A2
0x180008183  movzx   r8d, word ptr [rcx]
0x180008187  test    r8w, r8w
0x18000818b  jz      short loc_1800081A2
0x18000818d  mov     [rax], r8w
0x180008191  add     rcx, 2
0x180008195  add     rax, 2
0x180008199  dec     r9
0x18000819c  sub     rdx, 1; unsigned __int64
0x1800081a0  jnz     short loc_18000817E
0x1800081a2  test    rdx, rdx
0x1800081a5  lea     rcx, [rax-2]
0x1800081a9  lea     r8, aP0; "_p0"
0x1800081b0  cmovnz  rcx, rax
0x1800081b4  mov     [rcx], r15w
0x1800081b8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800081bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800081c2  mov     esi, 1F0003h
0x1800081c7  lea     r8, [rsp+280h+Name]; lpName
0x1800081cc  mov     ecx, esi; dwDesiredAccess
0x1800081ce  xor     edx, edx; bInheritHandle
0x1800081d0  call    cs:__imp_OpenSemaphoreW
0x1800081d6  mov     rbx, rax
0x1800081d9  test    rax, rax
0x1800081dc  jz      loc_180008319
0x1800081e2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800081e7  mov     [rsp+280h+var_25C], r15d
0x1800081ec  mov     rcx, rax; hHandle
0x1800081ef  mov     [rsp+280h+var_260], r15d; int
0x1800081f4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800081f9  mov     edi, eax
0x1800081fb  test    eax, eax
0x1800081fd  jns     short loc_180008232
0x1800081ff  mov     rcx, [rbp+188h]; this
0x180008206  lea     r8, aWil; "wil"
0x18000820d  mov     r9d, eax; char *
0x180008210  mov     edx, 0D6h; void *
0x180008215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000821a  mov     rcx, rbx; hObject
0x18000821d  call    cs:__imp_CloseHandle
0x180008223  test    eax, eax
0x180008225  jz      loc_180008395
0x18000822b  mov     eax, edi
0x18000822d  jmp     loc_180008340
0x180008232  lea     r8, asc_180042360; "h"
0x180008239  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000823e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008243  lea     r8, [rsp+280h+Name]; lpName
0x180008248  xor     edx, edx; bInheritHandle
0x18000824a  mov     ecx, esi; dwDesiredAccess
0x18000824c  call    cs:__imp_OpenSemaphoreW
0x180008252  mov     rdi, rax
0x180008255  test    rax, rax
0x180008258  jz      loc_1800082ED
0x18000825e  lea     rdx, [rsp+280h+var_260]; int *
0x180008263  mov     rcx, rax; hHandle
0x180008266  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000826b  mov     esi, eax
0x18000826d  test    eax, eax
0x18000826f  jns     short loc_1800082B5
0x180008271  mov     rcx, [rbp+188h]; this
0x180008278  lea     r8, aWil; "wil"
0x18000827f  mov     r9d, eax; char *
0x180008282  mov     edx, 0DEh; void *
0x180008287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000828c  mov     rcx, rdi; hObject
0x18000828f  call    cs:__imp_CloseHandle
0x180008295  test    eax, eax
0x180008297  jz      loc_1800083A7
0x18000829d  mov     rcx, rbx; hObject
0x1800082a0  call    cs:__imp_CloseHandle
0x1800082a6  test    eax, eax
0x1800082a8  jz      loc_1800083B9
0x1800082ae  mov     eax, esi
0x1800082b0  jmp     loc_180008340
0x1800082b5  mov     rcx, rdi; hObject
0x1800082b8  call    cs:__imp_CloseHandle
0x1800082be  test    eax, eax
0x1800082c0  jz      loc_18000835F
0x1800082c6  movsxd  rax, [rsp+280h+var_25C]
0x1800082cb  movsxd  rcx, [rsp+280h+var_260]
0x1800082d0  shl     rcx, 1Fh
0x1800082d4  or      rcx, rax
0x1800082d7  mov     [r14], rcx
0x1800082da  mov     rcx, rbx; hObject
0x1800082dd  call    cs:__imp_CloseHandle
0x1800082e3  test    eax, eax
0x1800082e5  jz      loc_180008371
0x1800082eb  jmp     short loc_180008324
0x1800082ed  mov     rcx, [rbp+188h]; this
0x1800082f4  lea     r8, aWil; "wil"
0x1800082fb  mov     edx, 0DCh; void *
0x180008300  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008305  mov     rcx, rbx; hObject
0x180008308  mov     edi, eax
0x18000830a  call    cs:__imp_CloseHandle
0x180008310  test    eax, eax
0x180008312  jz      short loc_180008383
0x180008314  jmp     loc_18000822B
0x180008319  call    cs:__imp_GetLastError
0x18000831f  cmp     eax, 2
0x180008322  jnz     short loc_180008328
0x180008324  xor     eax, eax
0x180008326  jmp     short loc_180008340
0x180008328  mov     rcx, [rbp+188h]; this
0x18000832f  lea     r8, aWil; "wil"
0x180008336  mov     edx, 0D0h; void *
0x18000833b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008340  mov     rcx, [rbp+180h+var_40]
0x180008347  xor     rcx, rsp; StackCookie
0x18000834a  call    __security_check_cookie
0x18000834f  add     rsp, 258h
0x180008356  pop     r15
0x180008358  pop     r14
0x18000835a  pop     rdi
0x18000835b  pop     rsi
0x18000835c  pop     rbx
0x18000835d  pop     rbp
0x18000835e  retn
0x18000835f  mov     rcx, [rbp+188h]; this
0x180008366  mov     edx, 0A0Bh; void *
0x18000836b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008371  mov     rcx, [rbp+188h]; this
0x180008378  mov     edx, 0A0Bh; void *
0x18000837d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008383  mov     rcx, [rbp+188h]; this
0x18000838a  mov     edx, 0A0Bh; void *
0x18000838f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008395  mov     rcx, [rbp+188h]; this
0x18000839c  mov     edx, 0A0Bh; void *
0x1800083a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083a7  mov     rcx, [rbp+188h]; this
0x1800083ae  mov     edx, 0A0Bh; void *
0x1800083b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083b9  mov     rcx, [rbp+188h]; this
0x1800083c0  mov     edx, 0A0Bh; void *
0x1800083c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
