# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005f2c`
- end: `0x1800061a1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bf8`
- `0x18000cf30`

## callees

- `0x180004ad8`
- `0x180005a2c`
- `0x180005a4c`
- `0x180005c94`
- `0x180005f2c`
- `0x1800062fc`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000607a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000608b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000607a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000608b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060e7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005fc3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000603e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005fc3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000603e`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180005f2c  push    rbp
0x180005f2e  push    rbx
0x180005f2f  push    rsi
0x180005f30  push    rdi
0x180005f31  push    r14
0x180005f33  push    r15
0x180005f35  lea     rbp, [rsp-158h]
0x180005f3d  sub     rsp, 258h
0x180005f44  mov     rax, cs:__security_cookie
0x180005f4b  xor     rax, rsp
0x180005f4e  mov     [rbp+180h+var_40], rax
0x180005f55  xor     r15d, r15d
0x180005f58  lea     rax, [rsp+280h+Name]
0x180005f5d  mov     esi, 104h
0x180005f62  mov     [r8], r15
0x180005f65  mov     edx, esi
0x180005f67  mov     r14, r8
0x180005f6a  mov     r9d, 7FFFFFFEh
0x180005f70  test    r9, r9
0x180005f73  jz      short loc_180005F94
0x180005f75  movzx   r8d, word ptr [rcx]
0x180005f79  test    r8w, r8w
0x180005f7d  jz      short loc_180005F94
0x180005f7f  mov     [rax], r8w
0x180005f83  add     rcx, 2
0x180005f87  add     rax, 2
0x180005f8b  dec     r9
0x180005f8e  sub     rdx, 1
0x180005f92  jnz     short loc_180005F70
0x180005f94  test    rdx, rdx
0x180005f97  lea     rcx, [rax-2]
0x180005f9b  lea     r8, aP0; "_p0"
0x180005fa2  mov     rdx, rsi; unsigned __int64
0x180005fa5  cmovnz  rcx, rax
0x180005fa9  mov     [rcx], r15w
0x180005fad  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005fb2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005fb7  lea     r8, [rsp+280h+Name]; lpName
0x180005fbc  xor     edx, edx; bInheritHandle
0x180005fbe  mov     ecx, 1F0003h; dwDesiredAccess
0x180005fc3  call    cs:__imp_OpenSemaphoreW
0x180005fc9  mov     rbx, rax
0x180005fcc  test    rax, rax
0x180005fcf  jz      loc_1800060F6
0x180005fd5  lea     rdx, [rsp+280h+var_25C]; int *
0x180005fda  mov     [rsp+280h+var_25C], r15d
0x180005fdf  mov     rcx, rax; hHandle
0x180005fe2  mov     [rsp+280h+var_260], r15d; int
0x180005fe7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005fec  mov     edi, eax
0x180005fee  test    eax, eax
0x180005ff0  jns     short loc_18000601E
0x180005ff2  mov     rcx, [rbp+188h]; this
0x180005ff9  mov     r9d, eax; char *
0x180005ffc  mov     edx, 0D6h; void *
0x180006001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006006  mov     rcx, rbx; hObject
0x180006009  call    cs:__imp_CloseHandle
0x18000600f  test    eax, eax
0x180006011  jz      loc_18000616B
0x180006017  mov     eax, edi
0x180006019  jmp     loc_180006116
0x18000601e  lea     r8, asc_180017CA8; "h"
0x180006025  mov     rdx, rsi; unsigned __int64
0x180006028  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000602d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006032  lea     r8, [rsp+280h+Name]; lpName
0x180006037  xor     edx, edx; bInheritHandle
0x180006039  mov     ecx, 1F0003h; dwDesiredAccess
0x18000603e  call    cs:__imp_OpenSemaphoreW
0x180006044  mov     rdi, rax
0x180006047  test    rax, rax
0x18000604a  jz      loc_1800060D1
0x180006050  lea     rdx, [rsp+280h+var_260]; int *
0x180006055  mov     rcx, rax; hHandle
0x180006058  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000605d  mov     esi, eax
0x18000605f  test    eax, eax
0x180006061  jns     short loc_18000609D
0x180006063  mov     rcx, [rbp+188h]; this
0x18000606a  mov     r9d, eax; char *
0x18000606d  mov     edx, 0DEh; void *
0x180006072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006077  mov     rcx, rdi; hObject
0x18000607a  call    cs:__imp_CloseHandle
0x180006080  test    eax, eax
0x180006082  jz      loc_18000617D
0x180006088  mov     rcx, rbx; hObject
0x18000608b  call    cs:__imp_CloseHandle
0x180006091  test    eax, eax
0x180006093  jz      loc_18000618F
0x180006099  mov     eax, esi
0x18000609b  jmp     short loc_180006116
0x18000609d  mov     rcx, rdi; hObject
0x1800060a0  call    cs:__imp_CloseHandle
0x1800060a6  test    eax, eax
0x1800060a8  jz      loc_180006135
0x1800060ae  movsxd  rax, [rsp+280h+var_25C]
0x1800060b3  movsxd  rcx, [rsp+280h+var_260]
0x1800060b8  shl     rcx, 1Fh
0x1800060bc  or      rcx, rax
0x1800060bf  mov     [r14], rcx
0x1800060c2  mov     rcx, rbx; hObject
0x1800060c5  call    cs:__imp_CloseHandle
0x1800060cb  test    eax, eax
0x1800060cd  jz      short loc_180006147
0x1800060cf  jmp     short loc_180006101
0x1800060d1  mov     rcx, [rbp+188h]; this
0x1800060d8  mov     edx, 0DCh; void *
0x1800060dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800060e2  mov     rcx, rbx; hObject
0x1800060e5  mov     edi, eax
0x1800060e7  call    cs:__imp_CloseHandle
0x1800060ed  test    eax, eax
0x1800060ef  jz      short loc_180006159
0x1800060f1  jmp     loc_180006017
0x1800060f6  call    cs:__imp_GetLastError
0x1800060fc  cmp     eax, 2
0x1800060ff  jnz     short loc_180006105
0x180006101  xor     eax, eax
0x180006103  jmp     short loc_180006116
0x180006105  mov     rcx, [rbp+188h]; this
0x18000610c  mov     edx, 0D0h; void *
0x180006111  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006116  mov     rcx, [rbp+180h+var_40]
0x18000611d  xor     rcx, rsp; StackCookie
0x180006120  call    __security_check_cookie
0x180006125  add     rsp, 258h
0x18000612c  pop     r15
0x18000612e  pop     r14
0x180006130  pop     rdi
0x180006131  pop     rsi
0x180006132  pop     rbx
0x180006133  pop     rbp
0x180006134  retn
0x180006135  mov     rcx, [rbp+188h]; this
0x18000613c  mov     edx, 0A0Bh; void *
0x180006141  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006147  mov     rcx, [rbp+188h]; this
0x18000614e  mov     edx, 0A0Bh; void *
0x180006153  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006159  mov     rcx, [rbp+188h]; this
0x180006160  mov     edx, 0A0Bh; void *
0x180006165  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000616b  mov     rcx, [rbp+188h]; this
0x180006172  mov     edx, 0A0Bh; void *
0x180006177  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000617d  mov     rcx, [rbp+188h]; this
0x180006184  mov     edx, 0A0Bh; void *
0x180006189  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000618f  mov     rcx, [rbp+188h]; this
0x180006196  mov     edx, 0A0Bh; void *
0x18000619b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
