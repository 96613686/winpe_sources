# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000abec`
- end: `0x18000aebb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a1c`
- `0x180005df8`

## callees

- `0x180003270`
- `0x180007474`
- `0x180009c44`
- `0x180009c64`
- `0x18000a534`
- `0x18000abec`
- `0x18000b5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac83`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ad11`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac83`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ad11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aded`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000abec  push    rbp
0x18000abee  push    rbx
0x18000abef  push    rsi
0x18000abf0  push    rdi
0x18000abf1  push    r14
0x18000abf3  push    r15
0x18000abf5  lea     rbp, [rsp-158h]
0x18000abfd  sub     rsp, 258h
0x18000ac04  mov     rax, cs:__security_cookie
0x18000ac0b  xor     rax, rsp
0x18000ac0e  mov     [rbp+180h+var_40], rax
0x18000ac15  xor     r15d, r15d
0x18000ac18  lea     rax, [rsp+280h+Name]
0x18000ac1d  mov     esi, 104h
0x18000ac22  mov     [r8], r15
0x18000ac25  mov     edx, esi
0x18000ac27  mov     r14, r8
0x18000ac2a  mov     r9d, 7FFFFFFEh
0x18000ac30  test    r9, r9
0x18000ac33  jz      short loc_18000AC54
0x18000ac35  movzx   r8d, word ptr [rcx]
0x18000ac39  test    r8w, r8w
0x18000ac3d  jz      short loc_18000AC54
0x18000ac3f  mov     [rax], r8w
0x18000ac43  add     rcx, 2
0x18000ac47  add     rax, 2
0x18000ac4b  dec     r9
0x18000ac4e  sub     rdx, 1
0x18000ac52  jnz     short loc_18000AC30
0x18000ac54  test    rdx, rdx
0x18000ac57  lea     rcx, [rax-2]
0x18000ac5b  lea     r8, aP0; "_p0"
0x18000ac62  mov     rdx, rsi; unsigned __int64
0x18000ac65  cmovnz  rcx, rax
0x18000ac69  mov     [rcx], r15w
0x18000ac6d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ac72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ac77  lea     r8, [rsp+280h+Name]; lpName
0x18000ac7c  xor     edx, edx; bInheritHandle
0x18000ac7e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ac83  call    cs:__imp_OpenSemaphoreW
0x18000ac8a  nop     dword ptr [rax+rax+00h]
0x18000ac8f  mov     rbx, rax
0x18000ac92  test    rax, rax
0x18000ac95  jz      loc_18000AE02
0x18000ac9b  lea     rdx, [rsp+280h+var_25C]; int *
0x18000aca0  mov     [rsp+280h+var_25C], r15d
0x18000aca5  mov     rcx, rax; hHandle
0x18000aca8  mov     [rsp+280h+var_260], r15d; int
0x18000acad  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000acb2  mov     edi, eax
0x18000acb4  test    eax, eax
0x18000acb6  jns     short loc_18000ACF1
0x18000acb8  mov     rcx, [rbp+188h]; this
0x18000acbf  lea     r8, aWil; "wil"
0x18000acc6  mov     r9d, eax; char *
0x18000acc9  mov     edx, 0D6h; void *
0x18000acce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acd3  mov     rcx, rbx; hObject
0x18000acd6  call    cs:__imp_CloseHandle
0x18000acdd  nop     dword ptr [rax+rax+00h]
0x18000ace2  test    eax, eax
0x18000ace4  jz      loc_18000AE85
0x18000acea  mov     eax, edi
0x18000acec  jmp     loc_18000AE2F
0x18000acf1  lea     r8, asc_18005C560; "h"
0x18000acf8  mov     rdx, rsi; unsigned __int64
0x18000acfb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ad00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ad05  lea     r8, [rsp+280h+Name]; lpName
0x18000ad0a  xor     edx, edx; bInheritHandle
0x18000ad0c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ad11  call    cs:__imp_OpenSemaphoreW
0x18000ad18  nop     dword ptr [rax+rax+00h]
0x18000ad1d  mov     rdi, rax
0x18000ad20  test    rax, rax
0x18000ad23  jz      loc_18000ADD0
0x18000ad29  lea     rdx, [rsp+280h+var_260]; int *
0x18000ad2e  mov     rcx, rax; hHandle
0x18000ad31  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ad36  mov     esi, eax
0x18000ad38  test    eax, eax
0x18000ad3a  jns     short loc_18000AD8C
0x18000ad3c  mov     rcx, [rbp+188h]; this
0x18000ad43  lea     r8, aWil; "wil"
0x18000ad4a  mov     r9d, eax; char *
0x18000ad4d  mov     edx, 0DEh; void *
0x18000ad52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad57  mov     rcx, rdi; hObject
0x18000ad5a  call    cs:__imp_CloseHandle
0x18000ad61  nop     dword ptr [rax+rax+00h]
0x18000ad66  test    eax, eax
0x18000ad68  jz      loc_18000AE97
0x18000ad6e  mov     rcx, rbx; hObject
0x18000ad71  call    cs:__imp_CloseHandle
0x18000ad78  nop     dword ptr [rax+rax+00h]
0x18000ad7d  test    eax, eax
0x18000ad7f  jz      loc_18000AEA9
0x18000ad85  mov     eax, esi
0x18000ad87  jmp     loc_18000AE2F
0x18000ad8c  mov     rcx, rdi; hObject
0x18000ad8f  call    cs:__imp_CloseHandle
0x18000ad96  nop     dword ptr [rax+rax+00h]
0x18000ad9b  test    eax, eax
0x18000ad9d  jz      loc_18000AE4F
0x18000ada3  movsxd  rax, [rsp+280h+var_25C]
0x18000ada8  movsxd  rcx, [rsp+280h+var_260]
0x18000adad  shl     rcx, 1Fh
0x18000adb1  or      rcx, rax
0x18000adb4  mov     [r14], rcx
0x18000adb7  mov     rcx, rbx; hObject
0x18000adba  call    cs:__imp_CloseHandle
0x18000adc1  nop     dword ptr [rax+rax+00h]
0x18000adc6  test    eax, eax
0x18000adc8  jz      loc_18000AE61
0x18000adce  jmp     short loc_18000AE13
0x18000add0  mov     rcx, [rbp+188h]; this
0x18000add7  lea     r8, aWil; "wil"
0x18000adde  mov     edx, 0DCh; void *
0x18000ade3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ade8  mov     rcx, rbx; hObject
0x18000adeb  mov     edi, eax
0x18000aded  call    cs:__imp_CloseHandle
0x18000adf4  nop     dword ptr [rax+rax+00h]
0x18000adf9  test    eax, eax
0x18000adfb  jz      short loc_18000AE73
0x18000adfd  jmp     loc_18000ACEA
0x18000ae02  call    cs:__imp_GetLastError
0x18000ae09  nop     dword ptr [rax+rax+00h]
0x18000ae0e  cmp     eax, 2
0x18000ae11  jnz     short loc_18000AE17
0x18000ae13  xor     eax, eax
0x18000ae15  jmp     short loc_18000AE2F
0x18000ae17  mov     rcx, [rbp+188h]; this
0x18000ae1e  lea     r8, aWil; "wil"
0x18000ae25  mov     edx, 0D0h; void *
0x18000ae2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ae2f  mov     rcx, [rbp+180h+var_40]
0x18000ae36  xor     rcx, rsp; StackCookie
0x18000ae39  call    __security_check_cookie
0x18000ae3e  add     rsp, 258h
0x18000ae45  pop     r15
0x18000ae47  pop     r14
0x18000ae49  pop     rdi
0x18000ae4a  pop     rsi
0x18000ae4b  pop     rbx
0x18000ae4c  pop     rbp
0x18000ae4d  retn
0x18000ae4f  mov     rcx, [rbp+188h]; this
0x18000ae56  mov     edx, 0A0Bh; void *
0x18000ae5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ae61  mov     rcx, [rbp+188h]; this
0x18000ae68  mov     edx, 0A0Bh; void *
0x18000ae6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ae73  mov     rcx, [rbp+188h]; this
0x18000ae7a  mov     edx, 0A0Bh; void *
0x18000ae7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ae85  mov     rcx, [rbp+188h]; this
0x18000ae8c  mov     edx, 0A0Bh; void *
0x18000ae91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ae97  mov     rcx, [rbp+188h]; this
0x18000ae9e  mov     edx, 0A0Bh; void *
0x18000aea3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aea9  mov     rcx, [rbp+188h]; this
0x18000aeb0  mov     edx, 0A0Bh; void *
0x18000aeb5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
