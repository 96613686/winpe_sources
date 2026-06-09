# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000742c`
- end: `0x1800076a6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003518`

## callees

- `0x180001510`
- `0x180004a14`
- `0x1800068b4`
- `0x1800068d4`
- `0x1800072c0`
- `0x18000742c`
- `0x1800078c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800074c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000753c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800074c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000753c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000750d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000757f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000750d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000757f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ec`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  __int64 v18; // r8
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
  __int64 v33; // r8
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
0x18000742c  push    rbp
0x18000742e  push    rbx
0x18000742f  push    rsi
0x180007430  push    rdi
0x180007431  push    r14
0x180007433  push    r15
0x180007435  lea     rbp, [rsp-158h]
0x18000743d  sub     rsp, 258h
0x180007444  mov     rax, cs:__security_cookie
0x18000744b  xor     rax, rsp
0x18000744e  mov     [rbp+180h+var_40], rax
0x180007455  xor     r15d, r15d
0x180007458  lea     rax, [rsp+280h+Name]
0x18000745d  mov     [r8], r15
0x180007460  mov     r14, r8
0x180007463  mov     edx, 104h
0x180007468  mov     r9d, 7FFFFFFEh
0x18000746e  test    r9, r9
0x180007471  jz      short loc_180007492
0x180007473  movzx   r8d, word ptr [rcx]
0x180007477  test    r8w, r8w
0x18000747b  jz      short loc_180007492
0x18000747d  mov     [rax], r8w
0x180007481  add     rcx, 2
0x180007485  add     rax, 2
0x180007489  dec     r9
0x18000748c  sub     rdx, 1; unsigned __int64
0x180007490  jnz     short loc_18000746E
0x180007492  test    rdx, rdx
0x180007495  lea     rcx, [rax-2]
0x180007499  lea     r8, aP0; "_p0"
0x1800074a0  cmovnz  rcx, rax
0x1800074a4  mov     [rcx], r15w
0x1800074a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800074ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800074b2  mov     esi, 1F0003h
0x1800074b7  lea     r8, [rsp+280h+Name]; lpName
0x1800074bc  mov     ecx, esi; dwDesiredAccess
0x1800074be  xor     edx, edx; bInheritHandle
0x1800074c0  call    cs:__imp_OpenSemaphoreW
0x1800074c6  mov     rbx, rax
0x1800074c9  test    rax, rax
0x1800074cc  jz      loc_1800075FB
0x1800074d2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800074d7  mov     [rsp+280h+var_25C], r15d
0x1800074dc  mov     rcx, rax; hHandle
0x1800074df  mov     [rsp+280h+var_260], r15d; int
0x1800074e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800074e9  mov     edi, eax
0x1800074eb  test    eax, eax
0x1800074ed  jns     short loc_180007522
0x1800074ef  mov     rcx, [rbp+188h]; this
0x1800074f6  lea     r8, aWil; "wil"
0x1800074fd  mov     r9d, eax; char *
0x180007500  mov     edx, 0D6h; void *
0x180007505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000750a  mov     rcx, rbx; hObject
0x18000750d  call    cs:__imp_CloseHandle
0x180007513  test    eax, eax
0x180007515  jz      loc_180007670
0x18000751b  mov     eax, edi
0x18000751d  jmp     loc_18000761B
0x180007522  lea     r8, asc_18000ABA8; "h"
0x180007529  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000752e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007533  lea     r8, [rsp+280h+Name]; lpName
0x180007538  xor     edx, edx; bInheritHandle
0x18000753a  mov     ecx, esi; dwDesiredAccess
0x18000753c  call    cs:__imp_OpenSemaphoreW
0x180007542  mov     rdi, rax
0x180007545  test    rax, rax
0x180007548  jz      loc_1800075D6
0x18000754e  lea     rdx, [rsp+280h+var_260]; int *
0x180007553  mov     rcx, rax; hHandle
0x180007556  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000755b  mov     esi, eax
0x18000755d  test    eax, eax
0x18000755f  jns     short loc_1800075A2
0x180007561  mov     rcx, [rbp+188h]; this
0x180007568  lea     r8, aWil; "wil"
0x18000756f  mov     r9d, eax; char *
0x180007572  mov     edx, 0DEh; void *
0x180007577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000757c  mov     rcx, rdi; hObject
0x18000757f  call    cs:__imp_CloseHandle
0x180007585  test    eax, eax
0x180007587  jz      loc_180007682
0x18000758d  mov     rcx, rbx; hObject
0x180007590  call    cs:__imp_CloseHandle
0x180007596  test    eax, eax
0x180007598  jz      loc_180007694
0x18000759e  mov     eax, esi
0x1800075a0  jmp     short loc_18000761B
0x1800075a2  mov     rcx, rdi; hObject
0x1800075a5  call    cs:__imp_CloseHandle
0x1800075ab  test    eax, eax
0x1800075ad  jz      loc_18000763A
0x1800075b3  movsxd  rax, [rsp+280h+var_25C]
0x1800075b8  movsxd  rcx, [rsp+280h+var_260]
0x1800075bd  shl     rcx, 1Fh
0x1800075c1  or      rcx, rax
0x1800075c4  mov     [r14], rcx
0x1800075c7  mov     rcx, rbx; hObject
0x1800075ca  call    cs:__imp_CloseHandle
0x1800075d0  test    eax, eax
0x1800075d2  jz      short loc_18000764C
0x1800075d4  jmp     short loc_180007606
0x1800075d6  mov     rcx, [rbp+188h]; this
0x1800075dd  mov     edx, 0DCh; void *
0x1800075e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800075e7  mov     rcx, rbx; hObject
0x1800075ea  mov     edi, eax
0x1800075ec  call    cs:__imp_CloseHandle
0x1800075f2  test    eax, eax
0x1800075f4  jz      short loc_18000765E
0x1800075f6  jmp     loc_18000751B
0x1800075fb  call    cs:__imp_GetLastError
0x180007601  cmp     eax, 2
0x180007604  jnz     short loc_18000760A
0x180007606  xor     eax, eax
0x180007608  jmp     short loc_18000761B
0x18000760a  mov     rcx, [rbp+188h]; this
0x180007611  mov     edx, 0D0h; void *
0x180007616  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000761b  mov     rcx, [rbp+180h+var_40]
0x180007622  xor     rcx, rsp; StackCookie
0x180007625  call    __security_check_cookie
0x18000762a  add     rsp, 258h
0x180007631  pop     r15
0x180007633  pop     r14
0x180007635  pop     rdi
0x180007636  pop     rsi
0x180007637  pop     rbx
0x180007638  pop     rbp
0x180007639  retn
0x18000763a  mov     rcx, [rbp+188h]; this
0x180007641  mov     edx, 0A0Bh; void *
0x180007646  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000764c  mov     rcx, [rbp+188h]; this
0x180007653  mov     edx, 0A0Bh; void *
0x180007658  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000765e  mov     rcx, [rbp+188h]; this
0x180007665  mov     edx, 0A0Bh; void *
0x18000766a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007670  mov     rcx, [rbp+188h]; this
0x180007677  mov     edx, 0A0Bh; void *
0x18000767c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007682  mov     rcx, [rbp+188h]; this
0x180007689  mov     edx, 0A0Bh; void *
0x18000768e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007694  mov     rcx, [rbp+188h]; this
0x18000769b  mov     edx, 0A0Bh; void *
0x1800076a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
