# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000734c`
- end: `0x180007612`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004bb0`
- `0x180014454`

## callees

- `0x180005c98`
- `0x180006954`
- `0x180006974`
- `0x180007144`
- `0x18000734c`
- `0x180007834`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007559`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007468`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007544`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007544`

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
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
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
0x18000734c  push    rbp
0x18000734e  push    rbx
0x18000734f  push    rsi
0x180007350  push    rdi
0x180007351  push    r14
0x180007353  push    r15
0x180007355  lea     rbp, [rsp-158h]
0x18000735d  sub     rsp, 258h
0x180007364  mov     rax, cs:__security_cookie
0x18000736b  xor     rax, rsp
0x18000736e  mov     [rbp+180h+var_40], rax
0x180007375  xor     r15d, r15d
0x180007378  lea     rax, [rsp+280h+Name]
0x18000737d  mov     [r8], r15
0x180007380  mov     r14, r8
0x180007383  mov     edx, 104h
0x180007388  mov     r9d, 7FFFFFFEh
0x18000738e  test    r9, r9
0x180007391  jz      short loc_1800073B2
0x180007393  movzx   r8d, word ptr [rcx]
0x180007397  test    r8w, r8w
0x18000739b  jz      short loc_1800073B2
0x18000739d  mov     [rax], r8w
0x1800073a1  add     rcx, 2
0x1800073a5  add     rax, 2
0x1800073a9  dec     r9
0x1800073ac  sub     rdx, 1; unsigned __int64
0x1800073b0  jnz     short loc_18000738E
0x1800073b2  test    rdx, rdx
0x1800073b5  lea     rcx, [rax-2]
0x1800073b9  lea     r8, aP0; "_p0"
0x1800073c0  cmovnz  rcx, rax
0x1800073c4  mov     [rcx], r15w
0x1800073c8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800073cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800073d2  mov     esi, 1F0003h
0x1800073d7  lea     r8, [rsp+280h+Name]; lpName
0x1800073dc  mov     ecx, esi; dwDesiredAccess
0x1800073de  xor     edx, edx; bInheritHandle
0x1800073e0  call    cs:__imp_OpenSemaphoreW
0x1800073e7  nop     dword ptr [rax+rax+00h]
0x1800073ec  mov     rbx, rax
0x1800073ef  test    rax, rax
0x1800073f2  jz      loc_180007559
0x1800073f8  lea     rdx, [rsp+280h+var_25C]; int *
0x1800073fd  mov     [rsp+280h+var_25C], r15d
0x180007402  mov     rcx, rax; hHandle
0x180007405  mov     [rsp+280h+var_260], r15d; int
0x18000740a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000740f  mov     edi, eax
0x180007411  test    eax, eax
0x180007413  jns     short loc_18000744E
0x180007415  mov     rcx, [rbp+188h]; this
0x18000741c  lea     r8, aWil; "wil"
0x180007423  mov     r9d, eax; char *
0x180007426  mov     edx, 0D6h; void *
0x18000742b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007430  mov     rcx, rbx; hObject
0x180007433  call    cs:__imp_CloseHandle
0x18000743a  nop     dword ptr [rax+rax+00h]
0x18000743f  test    eax, eax
0x180007441  jz      loc_1800075DC
0x180007447  mov     eax, edi
0x180007449  jmp     loc_180007586
0x18000744e  lea     r8, asc_18003C0A8; "h"
0x180007455  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000745a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000745f  lea     r8, [rsp+280h+Name]; lpName
0x180007464  xor     edx, edx; bInheritHandle
0x180007466  mov     ecx, esi; dwDesiredAccess
0x180007468  call    cs:__imp_OpenSemaphoreW
0x18000746f  nop     dword ptr [rax+rax+00h]
0x180007474  mov     rdi, rax
0x180007477  test    rax, rax
0x18000747a  jz      loc_180007527
0x180007480  lea     rdx, [rsp+280h+var_260]; int *
0x180007485  mov     rcx, rax; hHandle
0x180007488  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000748d  mov     esi, eax
0x18000748f  test    eax, eax
0x180007491  jns     short loc_1800074E3
0x180007493  mov     rcx, [rbp+188h]; this
0x18000749a  lea     r8, aWil; "wil"
0x1800074a1  mov     r9d, eax; char *
0x1800074a4  mov     edx, 0DEh; void *
0x1800074a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074ae  mov     rcx, rdi; hObject
0x1800074b1  call    cs:__imp_CloseHandle
0x1800074b8  nop     dword ptr [rax+rax+00h]
0x1800074bd  test    eax, eax
0x1800074bf  jz      loc_1800075EE
0x1800074c5  mov     rcx, rbx; hObject
0x1800074c8  call    cs:__imp_CloseHandle
0x1800074cf  nop     dword ptr [rax+rax+00h]
0x1800074d4  test    eax, eax
0x1800074d6  jz      loc_180007600
0x1800074dc  mov     eax, esi
0x1800074de  jmp     loc_180007586
0x1800074e3  mov     rcx, rdi; hObject
0x1800074e6  call    cs:__imp_CloseHandle
0x1800074ed  nop     dword ptr [rax+rax+00h]
0x1800074f2  test    eax, eax
0x1800074f4  jz      loc_1800075A6
0x1800074fa  movsxd  rax, [rsp+280h+var_25C]
0x1800074ff  movsxd  rcx, [rsp+280h+var_260]
0x180007504  shl     rcx, 1Fh
0x180007508  or      rcx, rax
0x18000750b  mov     [r14], rcx
0x18000750e  mov     rcx, rbx; hObject
0x180007511  call    cs:__imp_CloseHandle
0x180007518  nop     dword ptr [rax+rax+00h]
0x18000751d  test    eax, eax
0x18000751f  jz      loc_1800075B8
0x180007525  jmp     short loc_18000756A
0x180007527  mov     rcx, [rbp+188h]; this
0x18000752e  lea     r8, aWil; "wil"
0x180007535  mov     edx, 0DCh; void *
0x18000753a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000753f  mov     rcx, rbx; hObject
0x180007542  mov     edi, eax
0x180007544  call    cs:__imp_CloseHandle
0x18000754b  nop     dword ptr [rax+rax+00h]
0x180007550  test    eax, eax
0x180007552  jz      short loc_1800075CA
0x180007554  jmp     loc_180007447
0x180007559  call    cs:__imp_GetLastError
0x180007560  nop     dword ptr [rax+rax+00h]
0x180007565  cmp     eax, 2
0x180007568  jnz     short loc_18000756E
0x18000756a  xor     eax, eax
0x18000756c  jmp     short loc_180007586
0x18000756e  mov     rcx, [rbp+188h]; this
0x180007575  lea     r8, aWil; "wil"
0x18000757c  mov     edx, 0D0h; void *
0x180007581  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007586  mov     rcx, [rbp+180h+var_40]
0x18000758d  xor     rcx, rsp; StackCookie
0x180007590  call    __security_check_cookie
0x180007595  add     rsp, 258h
0x18000759c  pop     r15
0x18000759e  pop     r14
0x1800075a0  pop     rdi
0x1800075a1  pop     rsi
0x1800075a2  pop     rbx
0x1800075a3  pop     rbp
0x1800075a4  retn
0x1800075a6  mov     rcx, [rbp+188h]; this
0x1800075ad  mov     edx, 0A0Bh; void *
0x1800075b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075b8  mov     rcx, [rbp+188h]; this
0x1800075bf  mov     edx, 0A0Bh; void *
0x1800075c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075ca  mov     rcx, [rbp+188h]; this
0x1800075d1  mov     edx, 0A0Bh; void *
0x1800075d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075dc  mov     rcx, [rbp+188h]; this
0x1800075e3  mov     edx, 0A0Bh; void *
0x1800075e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075ee  mov     rcx, [rbp+188h]; this
0x1800075f5  mov     edx, 0A0Bh; void *
0x1800075fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007600  mov     rcx, [rbp+188h]; this
0x180007607  mov     edx, 0A0Bh; void *
0x18000760c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
