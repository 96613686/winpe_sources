# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c70c`
- end: `0x18000c978`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008828`
- `0x180008bcc`

## callees

- `0x180006018`
- `0x18000a034`
- `0x18000bbb4`
- `0x18000bbd4`
- `0x18000c70c`
- `0x18000ceec`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000c7e6`
- `KERNEL32!CloseHandle` at `0x18000c851`
- `KERNEL32!CloseHandle` at `0x18000c862`
- `KERNEL32!CloseHandle` at `0x18000c877`
- `KERNEL32!CloseHandle` at `0x18000c89c`
- `KERNEL32!CloseHandle` at `0x18000c8be`
- `KERNEL32!CloseHandle` at `0x18000c7e6`
- `KERNEL32!CloseHandle` at `0x18000c851`
- `KERNEL32!CloseHandle` at `0x18000c862`
- `KERNEL32!CloseHandle` at `0x18000c877`
- `KERNEL32!CloseHandle` at `0x18000c89c`
- `KERNEL32!CloseHandle` at `0x18000c8be`
- `KERNEL32!OpenSemaphoreW` at `0x18000c7a0`
- `KERNEL32!OpenSemaphoreW` at `0x18000c815`
- `KERNEL32!OpenSemaphoreW` at `0x18000c7a0`
- `KERNEL32!OpenSemaphoreW` at `0x18000c815`
- `KERNEL32!GetLastError` at `0x18000c8cd`
- `KERNEL32!GetLastError` at `0x18000c8cd`

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
0x18000c70c  push    rbp
0x18000c70e  push    rbx
0x18000c70f  push    rsi
0x18000c710  push    rdi
0x18000c711  push    r14
0x18000c713  push    r15
0x18000c715  lea     rbp, [rsp-158h]
0x18000c71d  sub     rsp, 258h
0x18000c724  mov     rax, cs:__security_cookie
0x18000c72b  xor     rax, rsp
0x18000c72e  mov     [rbp+180h+var_40], rax
0x18000c735  xor     r15d, r15d
0x18000c738  lea     rax, [rsp+280h+Name]
0x18000c73d  mov     [r8], r15
0x18000c740  mov     r14, r8
0x18000c743  mov     edx, 104h
0x18000c748  mov     r9d, 7FFFFFFEh
0x18000c74e  test    r9, r9
0x18000c751  jz      short loc_18000C772
0x18000c753  movzx   r8d, word ptr [rcx]
0x18000c757  test    r8w, r8w
0x18000c75b  jz      short loc_18000C772
0x18000c75d  mov     [rax], r8w
0x18000c761  add     rcx, 2
0x18000c765  add     rax, 2
0x18000c769  dec     r9
0x18000c76c  sub     rdx, 1; unsigned __int64
0x18000c770  jnz     short loc_18000C74E
0x18000c772  test    rdx, rdx
0x18000c775  lea     rcx, [rax-2]
0x18000c779  lea     r8, aP0; "_p0"
0x18000c780  cmovnz  rcx, rax
0x18000c784  mov     [rcx], r15w
0x18000c788  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c78d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c792  mov     esi, 1F0003h
0x18000c797  lea     r8, [rsp+280h+Name]; lpName
0x18000c79c  mov     ecx, esi; dwDesiredAccess
0x18000c79e  xor     edx, edx; bInheritHandle
0x18000c7a0  call    cs:__imp_OpenSemaphoreW
0x18000c7a6  mov     rbx, rax
0x18000c7a9  test    rax, rax
0x18000c7ac  jz      loc_18000C8CD
0x18000c7b2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c7b7  mov     [rsp+280h+var_25C], r15d
0x18000c7bc  mov     rcx, rax; hHandle
0x18000c7bf  mov     [rsp+280h+var_260], r15d; int
0x18000c7c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c7c9  mov     edi, eax
0x18000c7cb  test    eax, eax
0x18000c7cd  jns     short loc_18000C7FB
0x18000c7cf  mov     rcx, [rbp+188h]; this
0x18000c7d6  mov     r9d, eax; char *
0x18000c7d9  mov     edx, 0D6h; void *
0x18000c7de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7e3  mov     rcx, rbx; hObject
0x18000c7e6  call    cs:__imp_CloseHandle
0x18000c7ec  test    eax, eax
0x18000c7ee  jz      loc_18000C942
0x18000c7f4  mov     eax, edi
0x18000c7f6  jmp     loc_18000C8ED
0x18000c7fb  lea     r8, asc_180019D00; "h"
0x18000c802  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c807  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c80c  lea     r8, [rsp+280h+Name]; lpName
0x18000c811  xor     edx, edx; bInheritHandle
0x18000c813  mov     ecx, esi; dwDesiredAccess
0x18000c815  call    cs:__imp_OpenSemaphoreW
0x18000c81b  mov     rdi, rax
0x18000c81e  test    rax, rax
0x18000c821  jz      loc_18000C8A8
0x18000c827  lea     rdx, [rsp+280h+var_260]; int *
0x18000c82c  mov     rcx, rax; hHandle
0x18000c82f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c834  mov     esi, eax
0x18000c836  test    eax, eax
0x18000c838  jns     short loc_18000C874
0x18000c83a  mov     rcx, [rbp+188h]; this
0x18000c841  mov     r9d, eax; char *
0x18000c844  mov     edx, 0DEh; void *
0x18000c849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c84e  mov     rcx, rdi; hObject
0x18000c851  call    cs:__imp_CloseHandle
0x18000c857  test    eax, eax
0x18000c859  jz      loc_18000C954
0x18000c85f  mov     rcx, rbx; hObject
0x18000c862  call    cs:__imp_CloseHandle
0x18000c868  test    eax, eax
0x18000c86a  jz      loc_18000C966
0x18000c870  mov     eax, esi
0x18000c872  jmp     short loc_18000C8ED
0x18000c874  mov     rcx, rdi; hObject
0x18000c877  call    cs:__imp_CloseHandle
0x18000c87d  test    eax, eax
0x18000c87f  jz      loc_18000C90C
0x18000c885  movsxd  rax, [rsp+280h+var_25C]
0x18000c88a  movsxd  rcx, [rsp+280h+var_260]
0x18000c88f  shl     rcx, 1Fh
0x18000c893  or      rcx, rax
0x18000c896  mov     [r14], rcx
0x18000c899  mov     rcx, rbx; hObject
0x18000c89c  call    cs:__imp_CloseHandle
0x18000c8a2  test    eax, eax
0x18000c8a4  jz      short loc_18000C91E
0x18000c8a6  jmp     short loc_18000C8D8
0x18000c8a8  mov     rcx, [rbp+188h]; this
0x18000c8af  mov     edx, 0DCh; void *
0x18000c8b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c8b9  mov     rcx, rbx; hObject
0x18000c8bc  mov     edi, eax
0x18000c8be  call    cs:__imp_CloseHandle
0x18000c8c4  test    eax, eax
0x18000c8c6  jz      short loc_18000C930
0x18000c8c8  jmp     loc_18000C7F4
0x18000c8cd  call    cs:__imp_GetLastError
0x18000c8d3  cmp     eax, 2
0x18000c8d6  jnz     short loc_18000C8DC
0x18000c8d8  xor     eax, eax
0x18000c8da  jmp     short loc_18000C8ED
0x18000c8dc  mov     rcx, [rbp+188h]; this
0x18000c8e3  mov     edx, 0D0h; void *
0x18000c8e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c8ed  mov     rcx, [rbp+180h+var_40]
0x18000c8f4  xor     rcx, rsp; StackCookie
0x18000c8f7  call    __security_check_cookie
0x18000c8fc  add     rsp, 258h
0x18000c903  pop     r15
0x18000c905  pop     r14
0x18000c907  pop     rdi
0x18000c908  pop     rsi
0x18000c909  pop     rbx
0x18000c90a  pop     rbp
0x18000c90b  retn
0x18000c90c  mov     rcx, [rbp+188h]; this
0x18000c913  mov     edx, 0A0Bh; void *
0x18000c918  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c91e  mov     rcx, [rbp+188h]; this
0x18000c925  mov     edx, 0A0Bh; void *
0x18000c92a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c930  mov     rcx, [rbp+188h]; this
0x18000c937  mov     edx, 0A0Bh; void *
0x18000c93c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c942  mov     rcx, [rbp+188h]; this
0x18000c949  mov     edx, 0A0Bh; void *
0x18000c94e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c954  mov     rcx, [rbp+188h]; this
0x18000c95b  mov     edx, 0A0Bh; void *
0x18000c960  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c966  mov     rcx, [rbp+188h]; this
0x18000c96d  mov     edx, 0A0Bh; void *
0x18000c972  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
