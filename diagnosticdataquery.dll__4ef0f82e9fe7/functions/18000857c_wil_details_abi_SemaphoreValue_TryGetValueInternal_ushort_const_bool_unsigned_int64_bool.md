# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000857c`
- end: `0x1800087f6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800060c8`

## callees

- `0x180001500`
- `0x180007054`
- `0x180007ae4`
- `0x180007b04`
- `0x1800083e0`
- `0x18000857c`
- `0x18000894c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008610`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000868c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008610`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000868c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000874b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000874b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000865d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000871a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000873c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000865d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000871a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000873c`

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
0x18000857c  push    rbp
0x18000857e  push    rbx
0x18000857f  push    rsi
0x180008580  push    rdi
0x180008581  push    r14
0x180008583  push    r15
0x180008585  lea     rbp, [rsp-158h]
0x18000858d  sub     rsp, 258h
0x180008594  mov     rax, cs:__security_cookie
0x18000859b  xor     rax, rsp
0x18000859e  mov     [rbp+180h+var_40], rax
0x1800085a5  xor     r15d, r15d
0x1800085a8  lea     rax, [rsp+280h+Name]
0x1800085ad  mov     [r8], r15
0x1800085b0  mov     r14, r8
0x1800085b3  mov     edx, 104h
0x1800085b8  mov     r9d, 7FFFFFFEh
0x1800085be  test    r9, r9
0x1800085c1  jz      short loc_1800085E2
0x1800085c3  movzx   r8d, word ptr [rcx]
0x1800085c7  test    r8w, r8w
0x1800085cb  jz      short loc_1800085E2
0x1800085cd  mov     [rax], r8w
0x1800085d1  add     rcx, 2
0x1800085d5  add     rax, 2
0x1800085d9  dec     r9
0x1800085dc  sub     rdx, 1; unsigned __int64
0x1800085e0  jnz     short loc_1800085BE
0x1800085e2  test    rdx, rdx
0x1800085e5  lea     rcx, [rax-2]
0x1800085e9  lea     r8, aP0; "_p0"
0x1800085f0  cmovnz  rcx, rax
0x1800085f4  mov     [rcx], r15w
0x1800085f8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800085fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008602  mov     esi, 1F0003h
0x180008607  lea     r8, [rsp+280h+Name]; lpName
0x18000860c  mov     ecx, esi; dwDesiredAccess
0x18000860e  xor     edx, edx; bInheritHandle
0x180008610  call    cs:__imp_OpenSemaphoreW
0x180008616  mov     rbx, rax
0x180008619  test    rax, rax
0x18000861c  jz      loc_18000874B
0x180008622  lea     rdx, [rsp+280h+var_25C]; int *
0x180008627  mov     [rsp+280h+var_25C], r15d
0x18000862c  mov     rcx, rax; hHandle
0x18000862f  mov     [rsp+280h+var_260], r15d; int
0x180008634  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008639  mov     edi, eax
0x18000863b  test    eax, eax
0x18000863d  jns     short loc_180008672
0x18000863f  mov     rcx, [rbp+188h]; this
0x180008646  lea     r8, aWil; "wil"
0x18000864d  mov     r9d, eax; char *
0x180008650  mov     edx, 0D6h; void *
0x180008655  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000865a  mov     rcx, rbx; hObject
0x18000865d  call    cs:__imp_CloseHandle
0x180008663  test    eax, eax
0x180008665  jz      loc_1800087C0
0x18000866b  mov     eax, edi
0x18000866d  jmp     loc_18000876B
0x180008672  lea     r8, asc_180010550; "h"
0x180008679  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000867e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008683  lea     r8, [rsp+280h+Name]; lpName
0x180008688  xor     edx, edx; bInheritHandle
0x18000868a  mov     ecx, esi; dwDesiredAccess
0x18000868c  call    cs:__imp_OpenSemaphoreW
0x180008692  mov     rdi, rax
0x180008695  test    rax, rax
0x180008698  jz      loc_180008726
0x18000869e  lea     rdx, [rsp+280h+var_260]; int *
0x1800086a3  mov     rcx, rax; hHandle
0x1800086a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800086ab  mov     esi, eax
0x1800086ad  test    eax, eax
0x1800086af  jns     short loc_1800086F2
0x1800086b1  mov     rcx, [rbp+188h]; this
0x1800086b8  lea     r8, aWil; "wil"
0x1800086bf  mov     r9d, eax; char *
0x1800086c2  mov     edx, 0DEh; void *
0x1800086c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086cc  mov     rcx, rdi; hObject
0x1800086cf  call    cs:__imp_CloseHandle
0x1800086d5  test    eax, eax
0x1800086d7  jz      loc_1800087D2
0x1800086dd  mov     rcx, rbx; hObject
0x1800086e0  call    cs:__imp_CloseHandle
0x1800086e6  test    eax, eax
0x1800086e8  jz      loc_1800087E4
0x1800086ee  mov     eax, esi
0x1800086f0  jmp     short loc_18000876B
0x1800086f2  mov     rcx, rdi; hObject
0x1800086f5  call    cs:__imp_CloseHandle
0x1800086fb  test    eax, eax
0x1800086fd  jz      loc_18000878A
0x180008703  movsxd  rax, [rsp+280h+var_25C]
0x180008708  movsxd  rcx, [rsp+280h+var_260]
0x18000870d  shl     rcx, 1Fh
0x180008711  or      rcx, rax
0x180008714  mov     [r14], rcx
0x180008717  mov     rcx, rbx; hObject
0x18000871a  call    cs:__imp_CloseHandle
0x180008720  test    eax, eax
0x180008722  jz      short loc_18000879C
0x180008724  jmp     short loc_180008756
0x180008726  mov     rcx, [rbp+188h]; this
0x18000872d  mov     edx, 0DCh; void *
0x180008732  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008737  mov     rcx, rbx; hObject
0x18000873a  mov     edi, eax
0x18000873c  call    cs:__imp_CloseHandle
0x180008742  test    eax, eax
0x180008744  jz      short loc_1800087AE
0x180008746  jmp     loc_18000866B
0x18000874b  call    cs:__imp_GetLastError
0x180008751  cmp     eax, 2
0x180008754  jnz     short loc_18000875A
0x180008756  xor     eax, eax
0x180008758  jmp     short loc_18000876B
0x18000875a  mov     rcx, [rbp+188h]; this
0x180008761  mov     edx, 0D0h; void *
0x180008766  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000876b  mov     rcx, [rbp+180h+var_40]
0x180008772  xor     rcx, rsp; StackCookie
0x180008775  call    __security_check_cookie
0x18000877a  add     rsp, 258h
0x180008781  pop     r15
0x180008783  pop     r14
0x180008785  pop     rdi
0x180008786  pop     rsi
0x180008787  pop     rbx
0x180008788  pop     rbp
0x180008789  retn
0x18000878a  mov     rcx, [rbp+188h]; this
0x180008791  mov     edx, 0A0Bh; void *
0x180008796  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000879c  mov     rcx, [rbp+188h]; this
0x1800087a3  mov     edx, 0A0Bh; void *
0x1800087a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800087ae  mov     rcx, [rbp+188h]; this
0x1800087b5  mov     edx, 0A0Bh; void *
0x1800087ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800087c0  mov     rcx, [rbp+188h]; this
0x1800087c7  mov     edx, 0A0Bh; void *
0x1800087cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800087d2  mov     rcx, [rbp+188h]; this
0x1800087d9  mov     edx, 0A0Bh; void *
0x1800087de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800087e4  mov     rcx, [rbp+188h]; this
0x1800087eb  mov     edx, 0A0Bh; void *
0x1800087f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
