# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000942c`
- end: `0x1400096f2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400042a4`
- `0x140004680`

## callees

- `0x140005c90`
- `0x1400084e4`
- `0x140008504`
- `0x140008df0`
- `0x14000942c`
- `0x140009e20`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009639`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400094c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009548`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400094c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009624`

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
0x14000942c  push    rbp
0x14000942e  push    rbx
0x14000942f  push    rsi
0x140009430  push    rdi
0x140009431  push    r14
0x140009433  push    r15
0x140009435  lea     rbp, [rsp-158h]
0x14000943d  sub     rsp, 258h
0x140009444  mov     rax, cs:__security_cookie
0x14000944b  xor     rax, rsp
0x14000944e  mov     [rbp+180h+var_40], rax
0x140009455  xor     r15d, r15d
0x140009458  lea     rax, [rsp+280h+Name]
0x14000945d  mov     [r8], r15
0x140009460  mov     r14, r8
0x140009463  mov     edx, 104h
0x140009468  mov     r9d, 7FFFFFFEh
0x14000946e  test    r9, r9
0x140009471  jz      short loc_140009492
0x140009473  movzx   r8d, word ptr [rcx]
0x140009477  test    r8w, r8w
0x14000947b  jz      short loc_140009492
0x14000947d  mov     [rax], r8w
0x140009481  add     rcx, 2
0x140009485  add     rax, 2
0x140009489  dec     r9
0x14000948c  sub     rdx, 1; unsigned __int64
0x140009490  jnz     short loc_14000946E
0x140009492  test    rdx, rdx
0x140009495  lea     rcx, [rax-2]
0x140009499  lea     r8, aP0; "_p0"
0x1400094a0  cmovnz  rcx, rax
0x1400094a4  mov     [rcx], r15w
0x1400094a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400094ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400094b2  mov     esi, 1F0003h
0x1400094b7  lea     r8, [rsp+280h+Name]; lpName
0x1400094bc  mov     ecx, esi; dwDesiredAccess
0x1400094be  xor     edx, edx; bInheritHandle
0x1400094c0  call    cs:__imp_OpenSemaphoreW
0x1400094c7  nop     dword ptr [rax+rax+00h]
0x1400094cc  mov     rbx, rax
0x1400094cf  test    rax, rax
0x1400094d2  jz      loc_140009639
0x1400094d8  lea     rdx, [rsp+280h+var_25C]; int *
0x1400094dd  mov     [rsp+280h+var_25C], r15d
0x1400094e2  mov     rcx, rax; hHandle
0x1400094e5  mov     [rsp+280h+var_260], r15d; int
0x1400094ea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400094ef  mov     edi, eax
0x1400094f1  test    eax, eax
0x1400094f3  jns     short loc_14000952E
0x1400094f5  mov     rcx, [rbp+188h]; this
0x1400094fc  lea     r8, aWil; "wil"
0x140009503  mov     r9d, eax; char *
0x140009506  mov     edx, 0D6h; void *
0x14000950b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009510  mov     rcx, rbx; hObject
0x140009513  call    cs:__imp_CloseHandle
0x14000951a  nop     dword ptr [rax+rax+00h]
0x14000951f  test    eax, eax
0x140009521  jz      loc_1400096BC
0x140009527  mov     eax, edi
0x140009529  jmp     loc_140009666
0x14000952e  lea     r8, asc_14001A420; "h"
0x140009535  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000953a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000953f  lea     r8, [rsp+280h+Name]; lpName
0x140009544  xor     edx, edx; bInheritHandle
0x140009546  mov     ecx, esi; dwDesiredAccess
0x140009548  call    cs:__imp_OpenSemaphoreW
0x14000954f  nop     dword ptr [rax+rax+00h]
0x140009554  mov     rdi, rax
0x140009557  test    rax, rax
0x14000955a  jz      loc_140009607
0x140009560  lea     rdx, [rsp+280h+var_260]; int *
0x140009565  mov     rcx, rax; hHandle
0x140009568  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000956d  mov     esi, eax
0x14000956f  test    eax, eax
0x140009571  jns     short loc_1400095C3
0x140009573  mov     rcx, [rbp+188h]; this
0x14000957a  lea     r8, aWil; "wil"
0x140009581  mov     r9d, eax; char *
0x140009584  mov     edx, 0DEh; void *
0x140009589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000958e  mov     rcx, rdi; hObject
0x140009591  call    cs:__imp_CloseHandle
0x140009598  nop     dword ptr [rax+rax+00h]
0x14000959d  test    eax, eax
0x14000959f  jz      loc_1400096CE
0x1400095a5  mov     rcx, rbx; hObject
0x1400095a8  call    cs:__imp_CloseHandle
0x1400095af  nop     dword ptr [rax+rax+00h]
0x1400095b4  test    eax, eax
0x1400095b6  jz      loc_1400096E0
0x1400095bc  mov     eax, esi
0x1400095be  jmp     loc_140009666
0x1400095c3  mov     rcx, rdi; hObject
0x1400095c6  call    cs:__imp_CloseHandle
0x1400095cd  nop     dword ptr [rax+rax+00h]
0x1400095d2  test    eax, eax
0x1400095d4  jz      loc_140009686
0x1400095da  movsxd  rax, [rsp+280h+var_25C]
0x1400095df  movsxd  rcx, [rsp+280h+var_260]
0x1400095e4  shl     rcx, 1Fh
0x1400095e8  or      rcx, rax
0x1400095eb  mov     [r14], rcx
0x1400095ee  mov     rcx, rbx; hObject
0x1400095f1  call    cs:__imp_CloseHandle
0x1400095f8  nop     dword ptr [rax+rax+00h]
0x1400095fd  test    eax, eax
0x1400095ff  jz      loc_140009698
0x140009605  jmp     short loc_14000964A
0x140009607  mov     rcx, [rbp+188h]; this
0x14000960e  lea     r8, aWil; "wil"
0x140009615  mov     edx, 0DCh; void *
0x14000961a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000961f  mov     rcx, rbx; hObject
0x140009622  mov     edi, eax
0x140009624  call    cs:__imp_CloseHandle
0x14000962b  nop     dword ptr [rax+rax+00h]
0x140009630  test    eax, eax
0x140009632  jz      short loc_1400096AA
0x140009634  jmp     loc_140009527
0x140009639  call    cs:__imp_GetLastError
0x140009640  nop     dword ptr [rax+rax+00h]
0x140009645  cmp     eax, 2
0x140009648  jnz     short loc_14000964E
0x14000964a  xor     eax, eax
0x14000964c  jmp     short loc_140009666
0x14000964e  mov     rcx, [rbp+188h]; this
0x140009655  lea     r8, aWil; "wil"
0x14000965c  mov     edx, 0D0h; void *
0x140009661  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009666  mov     rcx, [rbp+180h+var_40]
0x14000966d  xor     rcx, rsp; StackCookie
0x140009670  call    __security_check_cookie
0x140009675  add     rsp, 258h
0x14000967c  pop     r15
0x14000967e  pop     r14
0x140009680  pop     rdi
0x140009681  pop     rsi
0x140009682  pop     rbx
0x140009683  pop     rbp
0x140009684  retn
0x140009686  mov     rcx, [rbp+188h]; this
0x14000968d  mov     edx, 0A0Bh; void *
0x140009692  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009698  mov     rcx, [rbp+188h]; this
0x14000969f  mov     edx, 0A0Bh; void *
0x1400096a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096aa  mov     rcx, [rbp+188h]; this
0x1400096b1  mov     edx, 0A0Bh; void *
0x1400096b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096bc  mov     rcx, [rbp+188h]; this
0x1400096c3  mov     edx, 0A0Bh; void *
0x1400096c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096ce  mov     rcx, [rbp+188h]; this
0x1400096d5  mov     edx, 0A0Bh; void *
0x1400096da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096e0  mov     rcx, [rbp+188h]; this
0x1400096e7  mov     edx, 0A0Bh; void *
0x1400096ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
