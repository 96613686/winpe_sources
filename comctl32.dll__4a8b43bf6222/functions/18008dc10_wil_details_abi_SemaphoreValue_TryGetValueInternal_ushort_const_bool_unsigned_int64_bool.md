# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18008dc10`
- end: `0x18008de7c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18008bee0`

## callees

- `0x1800115f0`
- `0x18008ce20`
- `0x18008d894`
- `0x18008d8b4`
- `0x18008db60`
- `0x18008dc10`
- `0x18008dfdc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008dcea`
- `KERNEL32!CloseHandle` at `0x18008dd55`
- `KERNEL32!CloseHandle` at `0x18008dd66`
- `KERNEL32!CloseHandle` at `0x18008dd7b`
- `KERNEL32!CloseHandle` at `0x18008dda0`
- `KERNEL32!CloseHandle` at `0x18008ddc2`
- `KERNEL32!CloseHandle` at `0x18008dcea`
- `KERNEL32!CloseHandle` at `0x18008dd55`
- `KERNEL32!CloseHandle` at `0x18008dd66`
- `KERNEL32!CloseHandle` at `0x18008dd7b`
- `KERNEL32!CloseHandle` at `0x18008dda0`
- `KERNEL32!CloseHandle` at `0x18008ddc2`
- `KERNEL32!GetLastError` at `0x18008ddd1`
- `KERNEL32!GetLastError` at `0x18008ddd1`
- `KERNEL32!OpenSemaphoreW` at `0x18008dca4`
- `KERNEL32!OpenSemaphoreW` at `0x18008dd19`
- `KERNEL32!OpenSemaphoreW` at `0x18008dca4`
- `KERNEL32!OpenSemaphoreW` at `0x18008dd19`

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
0x18008dc10  push    rbp
0x18008dc12  push    rbx
0x18008dc13  push    rsi
0x18008dc14  push    rdi
0x18008dc15  push    r14
0x18008dc17  push    r15
0x18008dc19  lea     rbp, [rsp-158h]
0x18008dc21  sub     rsp, 258h
0x18008dc28  mov     rax, cs:__security_cookie
0x18008dc2f  xor     rax, rsp
0x18008dc32  mov     [rbp+180h+var_40], rax
0x18008dc39  xor     r15d, r15d
0x18008dc3c  lea     rax, [rsp+280h+Name]
0x18008dc41  mov     [r8], r15
0x18008dc44  mov     r14, r8
0x18008dc47  mov     edx, 104h
0x18008dc4c  mov     r9d, 7FFFFFFEh
0x18008dc52  test    r9, r9
0x18008dc55  jz      short loc_18008DC76
0x18008dc57  movzx   r8d, word ptr [rcx]
0x18008dc5b  test    r8w, r8w
0x18008dc5f  jz      short loc_18008DC76
0x18008dc61  mov     [rax], r8w
0x18008dc65  add     rcx, 2
0x18008dc69  add     rax, 2
0x18008dc6d  dec     r9
0x18008dc70  sub     rdx, 1; unsigned __int64
0x18008dc74  jnz     short loc_18008DC52
0x18008dc76  test    rdx, rdx
0x18008dc79  lea     rcx, [rax-2]
0x18008dc7d  lea     r8, aP0; "_p0"
0x18008dc84  cmovnz  rcx, rax
0x18008dc88  mov     [rcx], r15w
0x18008dc8c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18008dc91  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008dc96  mov     esi, 1F0003h
0x18008dc9b  lea     r8, [rsp+280h+Name]; lpName
0x18008dca0  mov     ecx, esi; dwDesiredAccess
0x18008dca2  xor     edx, edx; bInheritHandle
0x18008dca4  call    cs:__imp_OpenSemaphoreW
0x18008dcaa  mov     rbx, rax
0x18008dcad  test    rax, rax
0x18008dcb0  jz      loc_18008DDD1
0x18008dcb6  lea     rdx, [rsp+280h+var_25C]; int *
0x18008dcbb  mov     [rsp+280h+var_25C], r15d
0x18008dcc0  mov     rcx, rax; hHandle
0x18008dcc3  mov     [rsp+280h+var_260], r15d; int
0x18008dcc8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18008dccd  mov     edi, eax
0x18008dccf  test    eax, eax
0x18008dcd1  jns     short loc_18008DCFF
0x18008dcd3  mov     rcx, [rbp+188h]; this
0x18008dcda  mov     r9d, eax; char *
0x18008dcdd  mov     edx, 0D6h; void *
0x18008dce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dce7  mov     rcx, rbx; hObject
0x18008dcea  call    cs:__imp_CloseHandle
0x18008dcf0  test    eax, eax
0x18008dcf2  jz      loc_18008DE46
0x18008dcf8  mov     eax, edi
0x18008dcfa  jmp     loc_18008DDF1
0x18008dcff  lea     r8, asc_18009B408; "h"
0x18008dd06  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18008dd0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008dd10  lea     r8, [rsp+280h+Name]; lpName
0x18008dd15  xor     edx, edx; bInheritHandle
0x18008dd17  mov     ecx, esi; dwDesiredAccess
0x18008dd19  call    cs:__imp_OpenSemaphoreW
0x18008dd1f  mov     rdi, rax
0x18008dd22  test    rax, rax
0x18008dd25  jz      loc_18008DDAC
0x18008dd2b  lea     rdx, [rsp+280h+var_260]; int *
0x18008dd30  mov     rcx, rax; hHandle
0x18008dd33  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18008dd38  mov     esi, eax
0x18008dd3a  test    eax, eax
0x18008dd3c  jns     short loc_18008DD78
0x18008dd3e  mov     rcx, [rbp+188h]; this
0x18008dd45  mov     r9d, eax; char *
0x18008dd48  mov     edx, 0DEh; void *
0x18008dd4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dd52  mov     rcx, rdi; hObject
0x18008dd55  call    cs:__imp_CloseHandle
0x18008dd5b  test    eax, eax
0x18008dd5d  jz      loc_18008DE58
0x18008dd63  mov     rcx, rbx; hObject
0x18008dd66  call    cs:__imp_CloseHandle
0x18008dd6c  test    eax, eax
0x18008dd6e  jz      loc_18008DE6A
0x18008dd74  mov     eax, esi
0x18008dd76  jmp     short loc_18008DDF1
0x18008dd78  mov     rcx, rdi; hObject
0x18008dd7b  call    cs:__imp_CloseHandle
0x18008dd81  test    eax, eax
0x18008dd83  jz      loc_18008DE10
0x18008dd89  movsxd  rax, [rsp+280h+var_25C]
0x18008dd8e  movsxd  rcx, [rsp+280h+var_260]
0x18008dd93  shl     rcx, 1Fh
0x18008dd97  or      rcx, rax
0x18008dd9a  mov     [r14], rcx
0x18008dd9d  mov     rcx, rbx; hObject
0x18008dda0  call    cs:__imp_CloseHandle
0x18008dda6  test    eax, eax
0x18008dda8  jz      short loc_18008DE22
0x18008ddaa  jmp     short loc_18008DDDC
0x18008ddac  mov     rcx, [rbp+188h]; this
0x18008ddb3  mov     edx, 0DCh; void *
0x18008ddb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008ddbd  mov     rcx, rbx; hObject
0x18008ddc0  mov     edi, eax
0x18008ddc2  call    cs:__imp_CloseHandle
0x18008ddc8  test    eax, eax
0x18008ddca  jz      short loc_18008DE34
0x18008ddcc  jmp     loc_18008DCF8
0x18008ddd1  call    cs:__imp_GetLastError
0x18008ddd7  cmp     eax, 2
0x18008ddda  jnz     short loc_18008DDE0
0x18008dddc  xor     eax, eax
0x18008ddde  jmp     short loc_18008DDF1
0x18008dde0  mov     rcx, [rbp+188h]; this
0x18008dde7  mov     edx, 0D0h; void *
0x18008ddec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008ddf1  mov     rcx, [rbp+180h+var_40]
0x18008ddf8  xor     rcx, rsp; StackCookie
0x18008ddfb  call    __security_check_cookie
0x18008de00  add     rsp, 258h
0x18008de07  pop     r15
0x18008de09  pop     r14
0x18008de0b  pop     rdi
0x18008de0c  pop     rsi
0x18008de0d  pop     rbx
0x18008de0e  pop     rbp
0x18008de0f  retn
0x18008de10  mov     rcx, [rbp+188h]; this
0x18008de17  mov     edx, 0A0Bh; void *
0x18008de1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008de22  mov     rcx, [rbp+188h]; this
0x18008de29  mov     edx, 0A0Bh; void *
0x18008de2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008de34  mov     rcx, [rbp+188h]; this
0x18008de3b  mov     edx, 0A0Bh; void *
0x18008de40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008de46  mov     rcx, [rbp+188h]; this
0x18008de4d  mov     edx, 0A0Bh; void *
0x18008de52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008de58  mov     rcx, [rbp+188h]; this
0x18008de5f  mov     edx, 0A0Bh; void *
0x18008de64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008de6a  mov     rcx, [rbp+188h]; this
0x18008de71  mov     edx, 0A0Bh; void *
0x18008de76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
