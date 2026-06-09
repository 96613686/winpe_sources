# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000de70`
- end: `0x14000e0ea`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140007368`
- `0x140007738`

## callees

- `0x1400022a0`
- `0x140009a44`
- `0x14000c8b4`
- `0x14000c8d4`
- `0x14000da24`
- `0x14000de70`
- `0x1400100ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000df04`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000df80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000df04`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000df80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e03f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dfc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dfd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dfe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e00e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dfc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dfd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dfe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e00e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e030`

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
0x14000de70  push    rbp
0x14000de72  push    rbx
0x14000de73  push    rsi
0x14000de74  push    rdi
0x14000de75  push    r14
0x14000de77  push    r15
0x14000de79  lea     rbp, [rsp-158h]
0x14000de81  sub     rsp, 258h
0x14000de88  mov     rax, cs:__security_cookie
0x14000de8f  xor     rax, rsp
0x14000de92  mov     [rbp+180h+var_40], rax
0x14000de99  xor     r15d, r15d
0x14000de9c  lea     rax, [rsp+280h+Name]
0x14000dea1  mov     [r8], r15
0x14000dea4  mov     r14, r8
0x14000dea7  mov     edx, 104h
0x14000deac  mov     r9d, 7FFFFFFEh
0x14000deb2  test    r9, r9
0x14000deb5  jz      short loc_14000DED6
0x14000deb7  movzx   r8d, word ptr [rcx]
0x14000debb  test    r8w, r8w
0x14000debf  jz      short loc_14000DED6
0x14000dec1  mov     [rax], r8w
0x14000dec5  add     rcx, 2
0x14000dec9  add     rax, 2
0x14000decd  dec     r9
0x14000ded0  sub     rdx, 1; unsigned __int64
0x14000ded4  jnz     short loc_14000DEB2
0x14000ded6  test    rdx, rdx
0x14000ded9  lea     rcx, [rax-2]
0x14000dedd  lea     r8, aP0; "_p0"
0x14000dee4  cmovnz  rcx, rax
0x14000dee8  mov     [rcx], r15w
0x14000deec  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000def1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000def6  mov     esi, 1F0003h
0x14000defb  lea     r8, [rsp+280h+Name]; lpName
0x14000df00  mov     ecx, esi; dwDesiredAccess
0x14000df02  xor     edx, edx; bInheritHandle
0x14000df04  call    cs:__imp_OpenSemaphoreW
0x14000df0a  mov     rbx, rax
0x14000df0d  test    rax, rax
0x14000df10  jz      loc_14000E03F
0x14000df16  lea     rdx, [rsp+280h+var_25C]; int *
0x14000df1b  mov     [rsp+280h+var_25C], r15d
0x14000df20  mov     rcx, rax; hHandle
0x14000df23  mov     [rsp+280h+var_260], r15d; int
0x14000df28  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000df2d  mov     edi, eax
0x14000df2f  test    eax, eax
0x14000df31  jns     short loc_14000DF66
0x14000df33  mov     rcx, [rbp+188h]; this
0x14000df3a  lea     r8, aWil; "wil"
0x14000df41  mov     r9d, eax; char *
0x14000df44  mov     edx, 0D6h; void *
0x14000df49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000df4e  mov     rcx, rbx; hObject
0x14000df51  call    cs:__imp_CloseHandle
0x14000df57  test    eax, eax
0x14000df59  jz      loc_14000E0B4
0x14000df5f  mov     eax, edi
0x14000df61  jmp     loc_14000E05F
0x14000df66  lea     r8, asc_140013EA0; "h"
0x14000df6d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000df72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000df77  lea     r8, [rsp+280h+Name]; lpName
0x14000df7c  xor     edx, edx; bInheritHandle
0x14000df7e  mov     ecx, esi; dwDesiredAccess
0x14000df80  call    cs:__imp_OpenSemaphoreW
0x14000df86  mov     rdi, rax
0x14000df89  test    rax, rax
0x14000df8c  jz      loc_14000E01A
0x14000df92  lea     rdx, [rsp+280h+var_260]; int *
0x14000df97  mov     rcx, rax; hHandle
0x14000df9a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000df9f  mov     esi, eax
0x14000dfa1  test    eax, eax
0x14000dfa3  jns     short loc_14000DFE6
0x14000dfa5  mov     rcx, [rbp+188h]; this
0x14000dfac  lea     r8, aWil; "wil"
0x14000dfb3  mov     r9d, eax; char *
0x14000dfb6  mov     edx, 0DEh; void *
0x14000dfbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000dfc0  mov     rcx, rdi; hObject
0x14000dfc3  call    cs:__imp_CloseHandle
0x14000dfc9  test    eax, eax
0x14000dfcb  jz      loc_14000E0C6
0x14000dfd1  mov     rcx, rbx; hObject
0x14000dfd4  call    cs:__imp_CloseHandle
0x14000dfda  test    eax, eax
0x14000dfdc  jz      loc_14000E0D8
0x14000dfe2  mov     eax, esi
0x14000dfe4  jmp     short loc_14000E05F
0x14000dfe6  mov     rcx, rdi; hObject
0x14000dfe9  call    cs:__imp_CloseHandle
0x14000dfef  test    eax, eax
0x14000dff1  jz      loc_14000E07E
0x14000dff7  movsxd  rax, [rsp+280h+var_25C]
0x14000dffc  movsxd  rcx, [rsp+280h+var_260]
0x14000e001  shl     rcx, 1Fh
0x14000e005  or      rcx, rax
0x14000e008  mov     [r14], rcx
0x14000e00b  mov     rcx, rbx; hObject
0x14000e00e  call    cs:__imp_CloseHandle
0x14000e014  test    eax, eax
0x14000e016  jz      short loc_14000E090
0x14000e018  jmp     short loc_14000E04A
0x14000e01a  mov     rcx, [rbp+188h]; this
0x14000e021  mov     edx, 0DCh; void *
0x14000e026  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e02b  mov     rcx, rbx; hObject
0x14000e02e  mov     edi, eax
0x14000e030  call    cs:__imp_CloseHandle
0x14000e036  test    eax, eax
0x14000e038  jz      short loc_14000E0A2
0x14000e03a  jmp     loc_14000DF5F
0x14000e03f  call    cs:__imp_GetLastError
0x14000e045  cmp     eax, 2
0x14000e048  jnz     short loc_14000E04E
0x14000e04a  xor     eax, eax
0x14000e04c  jmp     short loc_14000E05F
0x14000e04e  mov     rcx, [rbp+188h]; this
0x14000e055  mov     edx, 0D0h; void *
0x14000e05a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e05f  mov     rcx, [rbp+180h+var_40]
0x14000e066  xor     rcx, rsp; StackCookie
0x14000e069  call    __security_check_cookie
0x14000e06e  add     rsp, 258h
0x14000e075  pop     r15
0x14000e077  pop     r14
0x14000e079  pop     rdi
0x14000e07a  pop     rsi
0x14000e07b  pop     rbx
0x14000e07c  pop     rbp
0x14000e07d  retn
0x14000e07e  mov     rcx, [rbp+188h]; this
0x14000e085  mov     edx, 0A0Bh; void *
0x14000e08a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e090  mov     rcx, [rbp+188h]; this
0x14000e097  mov     edx, 0A0Bh; void *
0x14000e09c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e0a2  mov     rcx, [rbp+188h]; this
0x14000e0a9  mov     edx, 0A0Bh; void *
0x14000e0ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e0b4  mov     rcx, [rbp+188h]; this
0x14000e0bb  mov     edx, 0A0Bh; void *
0x14000e0c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e0c6  mov     rcx, [rbp+188h]; this
0x14000e0cd  mov     edx, 0A0Bh; void *
0x14000e0d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e0d8  mov     rcx, [rbp+188h]; this
0x14000e0df  mov     edx, 0A0Bh; void *
0x14000e0e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
