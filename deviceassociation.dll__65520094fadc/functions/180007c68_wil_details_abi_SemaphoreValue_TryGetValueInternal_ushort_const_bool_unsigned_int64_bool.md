# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007c68`
- end: `0x180007ed4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000410c`
- `0x1800044b0`

## callees

- `0x180005930`
- `0x180007470`
- `0x180007490`
- `0x1800078b0`
- `0x180007c68`
- `0x18000844c`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007cfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d71`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007cfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007df8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007df8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e1a`

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
0x180007c68  push    rbp
0x180007c6a  push    rbx
0x180007c6b  push    rsi
0x180007c6c  push    rdi
0x180007c6d  push    r14
0x180007c6f  push    r15
0x180007c71  lea     rbp, [rsp-158h]
0x180007c79  sub     rsp, 258h
0x180007c80  mov     rax, cs:__security_cookie
0x180007c87  xor     rax, rsp
0x180007c8a  mov     [rbp+180h+var_40], rax
0x180007c91  xor     r15d, r15d
0x180007c94  lea     rax, [rsp+280h+Name]
0x180007c99  mov     [r8], r15
0x180007c9c  mov     r14, r8
0x180007c9f  mov     edx, 104h
0x180007ca4  mov     r9d, 7FFFFFFEh
0x180007caa  test    r9, r9
0x180007cad  jz      short loc_180007CCE
0x180007caf  movzx   r8d, word ptr [rcx]
0x180007cb3  test    r8w, r8w
0x180007cb7  jz      short loc_180007CCE
0x180007cb9  mov     [rax], r8w
0x180007cbd  add     rcx, 2
0x180007cc1  add     rax, 2
0x180007cc5  dec     r9
0x180007cc8  sub     rdx, 1; unsigned __int64
0x180007ccc  jnz     short loc_180007CAA
0x180007cce  test    rdx, rdx
0x180007cd1  lea     rcx, [rax-2]
0x180007cd5  lea     r8, aP0; "_p0"
0x180007cdc  cmovnz  rcx, rax
0x180007ce0  mov     [rcx], r15w
0x180007ce4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007ce9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007cee  mov     esi, 1F0003h
0x180007cf3  lea     r8, [rsp+280h+Name]; lpName
0x180007cf8  mov     ecx, esi; dwDesiredAccess
0x180007cfa  xor     edx, edx; bInheritHandle
0x180007cfc  call    cs:__imp_OpenSemaphoreW
0x180007d02  mov     rbx, rax
0x180007d05  test    rax, rax
0x180007d08  jz      loc_180007E29
0x180007d0e  lea     rdx, [rsp+280h+var_25C]; int *
0x180007d13  mov     [rsp+280h+var_25C], r15d
0x180007d18  mov     rcx, rax; hHandle
0x180007d1b  mov     [rsp+280h+var_260], r15d; int
0x180007d20  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007d25  mov     edi, eax
0x180007d27  test    eax, eax
0x180007d29  jns     short loc_180007D57
0x180007d2b  mov     rcx, [rbp+188h]; this
0x180007d32  mov     r9d, eax; char *
0x180007d35  mov     edx, 0D6h; void *
0x180007d3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d3f  mov     rcx, rbx; hObject
0x180007d42  call    cs:__imp_CloseHandle
0x180007d48  test    eax, eax
0x180007d4a  jz      loc_180007E9E
0x180007d50  mov     eax, edi
0x180007d52  jmp     loc_180007E49
0x180007d57  lea     r8, asc_1800108E0; "h"
0x180007d5e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007d63  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d68  lea     r8, [rsp+280h+Name]; lpName
0x180007d6d  xor     edx, edx; bInheritHandle
0x180007d6f  mov     ecx, esi; dwDesiredAccess
0x180007d71  call    cs:__imp_OpenSemaphoreW
0x180007d77  mov     rdi, rax
0x180007d7a  test    rax, rax
0x180007d7d  jz      loc_180007E04
0x180007d83  lea     rdx, [rsp+280h+var_260]; int *
0x180007d88  mov     rcx, rax; hHandle
0x180007d8b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007d90  mov     esi, eax
0x180007d92  test    eax, eax
0x180007d94  jns     short loc_180007DD0
0x180007d96  mov     rcx, [rbp+188h]; this
0x180007d9d  mov     r9d, eax; char *
0x180007da0  mov     edx, 0DEh; void *
0x180007da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007daa  mov     rcx, rdi; hObject
0x180007dad  call    cs:__imp_CloseHandle
0x180007db3  test    eax, eax
0x180007db5  jz      loc_180007EB0
0x180007dbb  mov     rcx, rbx; hObject
0x180007dbe  call    cs:__imp_CloseHandle
0x180007dc4  test    eax, eax
0x180007dc6  jz      loc_180007EC2
0x180007dcc  mov     eax, esi
0x180007dce  jmp     short loc_180007E49
0x180007dd0  mov     rcx, rdi; hObject
0x180007dd3  call    cs:__imp_CloseHandle
0x180007dd9  test    eax, eax
0x180007ddb  jz      loc_180007E68
0x180007de1  movsxd  rax, [rsp+280h+var_25C]
0x180007de6  movsxd  rcx, [rsp+280h+var_260]
0x180007deb  shl     rcx, 1Fh
0x180007def  or      rcx, rax
0x180007df2  mov     [r14], rcx
0x180007df5  mov     rcx, rbx; hObject
0x180007df8  call    cs:__imp_CloseHandle
0x180007dfe  test    eax, eax
0x180007e00  jz      short loc_180007E7A
0x180007e02  jmp     short loc_180007E34
0x180007e04  mov     rcx, [rbp+188h]; this
0x180007e0b  mov     edx, 0DCh; void *
0x180007e10  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007e15  mov     rcx, rbx; hObject
0x180007e18  mov     edi, eax
0x180007e1a  call    cs:__imp_CloseHandle
0x180007e20  test    eax, eax
0x180007e22  jz      short loc_180007E8C
0x180007e24  jmp     loc_180007D50
0x180007e29  call    cs:__imp_GetLastError
0x180007e2f  cmp     eax, 2
0x180007e32  jnz     short loc_180007E38
0x180007e34  xor     eax, eax
0x180007e36  jmp     short loc_180007E49
0x180007e38  mov     rcx, [rbp+188h]; this
0x180007e3f  mov     edx, 0D0h; void *
0x180007e44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007e49  mov     rcx, [rbp+180h+var_40]
0x180007e50  xor     rcx, rsp; StackCookie
0x180007e53  call    __security_check_cookie
0x180007e58  add     rsp, 258h
0x180007e5f  pop     r15
0x180007e61  pop     r14
0x180007e63  pop     rdi
0x180007e64  pop     rsi
0x180007e65  pop     rbx
0x180007e66  pop     rbp
0x180007e67  retn
0x180007e68  mov     rcx, [rbp+188h]; this
0x180007e6f  mov     edx, 0A0Bh; void *
0x180007e74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e7a  mov     rcx, [rbp+188h]; this
0x180007e81  mov     edx, 0A0Bh; void *
0x180007e86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e8c  mov     rcx, [rbp+188h]; this
0x180007e93  mov     edx, 0A0Bh; void *
0x180007e98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e9e  mov     rcx, [rbp+188h]; this
0x180007ea5  mov     edx, 0A0Bh; void *
0x180007eaa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007eb0  mov     rcx, [rbp+188h]; this
0x180007eb7  mov     edx, 0A0Bh; void *
0x180007ebc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007ec2  mov     rcx, [rbp+188h]; this
0x180007ec9  mov     edx, 0A0Bh; void *
0x180007ece  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
