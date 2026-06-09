# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000553c`
- end: `0x1800057a8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800030c8`

## callees

- `0x180001510`
- `0x180004004`
- `0x180004a64`
- `0x180004a84`
- `0x180005360`
- `0x18000553c`
- `0x1800058fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005645`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005692`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005692`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ee`

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
0x18000553c  push    rbp
0x18000553e  push    rbx
0x18000553f  push    rsi
0x180005540  push    rdi
0x180005541  push    r14
0x180005543  push    r15
0x180005545  lea     rbp, [rsp-158h]
0x18000554d  sub     rsp, 258h
0x180005554  mov     rax, cs:__security_cookie
0x18000555b  xor     rax, rsp
0x18000555e  mov     [rbp+180h+var_40], rax
0x180005565  xor     r15d, r15d
0x180005568  lea     rax, [rsp+280h+Name]
0x18000556d  mov     [r8], r15
0x180005570  mov     r14, r8
0x180005573  mov     edx, 104h
0x180005578  mov     r9d, 7FFFFFFEh
0x18000557e  test    r9, r9
0x180005581  jz      short loc_1800055A2
0x180005583  movzx   r8d, word ptr [rcx]
0x180005587  test    r8w, r8w
0x18000558b  jz      short loc_1800055A2
0x18000558d  mov     [rax], r8w
0x180005591  add     rcx, 2
0x180005595  add     rax, 2
0x180005599  dec     r9
0x18000559c  sub     rdx, 1; unsigned __int64
0x1800055a0  jnz     short loc_18000557E
0x1800055a2  test    rdx, rdx
0x1800055a5  lea     rcx, [rax-2]
0x1800055a9  lea     r8, aP0; "_p0"
0x1800055b0  cmovnz  rcx, rax
0x1800055b4  mov     [rcx], r15w
0x1800055b8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800055bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800055c2  mov     esi, 1F0003h
0x1800055c7  lea     r8, [rsp+280h+Name]; lpName
0x1800055cc  mov     ecx, esi; dwDesiredAccess
0x1800055ce  xor     edx, edx; bInheritHandle
0x1800055d0  call    cs:__imp_OpenSemaphoreW
0x1800055d6  mov     rbx, rax
0x1800055d9  test    rax, rax
0x1800055dc  jz      loc_1800056FD
0x1800055e2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800055e7  mov     [rsp+280h+var_25C], r15d
0x1800055ec  mov     rcx, rax; hHandle
0x1800055ef  mov     [rsp+280h+var_260], r15d; int
0x1800055f4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800055f9  mov     edi, eax
0x1800055fb  test    eax, eax
0x1800055fd  jns     short loc_18000562B
0x1800055ff  mov     rcx, [rbp+188h]; this
0x180005606  mov     r9d, eax; char *
0x180005609  mov     edx, 0D6h; void *
0x18000560e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005613  mov     rcx, rbx; hObject
0x180005616  call    cs:__imp_CloseHandle
0x18000561c  test    eax, eax
0x18000561e  jz      loc_180005772
0x180005624  mov     eax, edi
0x180005626  jmp     loc_18000571D
0x18000562b  lea     r8, asc_1800219E8; "h"
0x180005632  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005637  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000563c  lea     r8, [rsp+280h+Name]; lpName
0x180005641  xor     edx, edx; bInheritHandle
0x180005643  mov     ecx, esi; dwDesiredAccess
0x180005645  call    cs:__imp_OpenSemaphoreW
0x18000564b  mov     rdi, rax
0x18000564e  test    rax, rax
0x180005651  jz      loc_1800056D8
0x180005657  lea     rdx, [rsp+280h+var_260]; int *
0x18000565c  mov     rcx, rax; hHandle
0x18000565f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005664  mov     esi, eax
0x180005666  test    eax, eax
0x180005668  jns     short loc_1800056A4
0x18000566a  mov     rcx, [rbp+188h]; this
0x180005671  mov     r9d, eax; char *
0x180005674  mov     edx, 0DEh; void *
0x180005679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000567e  mov     rcx, rdi; hObject
0x180005681  call    cs:__imp_CloseHandle
0x180005687  test    eax, eax
0x180005689  jz      loc_180005784
0x18000568f  mov     rcx, rbx; hObject
0x180005692  call    cs:__imp_CloseHandle
0x180005698  test    eax, eax
0x18000569a  jz      loc_180005796
0x1800056a0  mov     eax, esi
0x1800056a2  jmp     short loc_18000571D
0x1800056a4  mov     rcx, rdi; hObject
0x1800056a7  call    cs:__imp_CloseHandle
0x1800056ad  test    eax, eax
0x1800056af  jz      loc_18000573C
0x1800056b5  movsxd  rax, [rsp+280h+var_25C]
0x1800056ba  movsxd  rcx, [rsp+280h+var_260]
0x1800056bf  shl     rcx, 1Fh
0x1800056c3  or      rcx, rax
0x1800056c6  mov     [r14], rcx
0x1800056c9  mov     rcx, rbx; hObject
0x1800056cc  call    cs:__imp_CloseHandle
0x1800056d2  test    eax, eax
0x1800056d4  jz      short loc_18000574E
0x1800056d6  jmp     short loc_180005708
0x1800056d8  mov     rcx, [rbp+188h]; this
0x1800056df  mov     edx, 0DCh; void *
0x1800056e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800056e9  mov     rcx, rbx; hObject
0x1800056ec  mov     edi, eax
0x1800056ee  call    cs:__imp_CloseHandle
0x1800056f4  test    eax, eax
0x1800056f6  jz      short loc_180005760
0x1800056f8  jmp     loc_180005624
0x1800056fd  call    cs:__imp_GetLastError
0x180005703  cmp     eax, 2
0x180005706  jnz     short loc_18000570C
0x180005708  xor     eax, eax
0x18000570a  jmp     short loc_18000571D
0x18000570c  mov     rcx, [rbp+188h]; this
0x180005713  mov     edx, 0D0h; void *
0x180005718  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000571d  mov     rcx, [rbp+180h+var_40]
0x180005724  xor     rcx, rsp; StackCookie
0x180005727  call    __security_check_cookie
0x18000572c  add     rsp, 258h
0x180005733  pop     r15
0x180005735  pop     r14
0x180005737  pop     rdi
0x180005738  pop     rsi
0x180005739  pop     rbx
0x18000573a  pop     rbp
0x18000573b  retn
0x18000573c  mov     rcx, [rbp+188h]; this
0x180005743  mov     edx, 0A0Bh; void *
0x180005748  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000574e  mov     rcx, [rbp+188h]; this
0x180005755  mov     edx, 0A0Bh; void *
0x18000575a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005760  mov     rcx, [rbp+188h]; this
0x180005767  mov     edx, 0A0Bh; void *
0x18000576c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005772  mov     rcx, [rbp+188h]; this
0x180005779  mov     edx, 0A0Bh; void *
0x18000577e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005784  mov     rcx, [rbp+188h]; this
0x18000578b  mov     edx, 0A0Bh; void *
0x180005790  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005796  mov     rcx, [rbp+188h]; this
0x18000579d  mov     edx, 0A0Bh; void *
0x1800057a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
