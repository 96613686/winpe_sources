# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ff0c`
- end: `0x180010181`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c8ec`

## callees

- `0x180001f90`
- `0x180007988`
- `0x18000d8e8`
- `0x18000ef14`
- `0x18000ef34`
- `0x18000ff0c`
- `0x1800103a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100d6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ffa3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001001e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ffa3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001001e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001005a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001006b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ffe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001005a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001006b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100c7`

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
0x18000ff0c  push    rbp
0x18000ff0e  push    rbx
0x18000ff0f  push    rsi
0x18000ff10  push    rdi
0x18000ff11  push    r14
0x18000ff13  push    r15
0x18000ff15  lea     rbp, [rsp-158h]
0x18000ff1d  sub     rsp, 258h
0x18000ff24  mov     rax, cs:__security_cookie
0x18000ff2b  xor     rax, rsp
0x18000ff2e  mov     [rbp+180h+var_40], rax
0x18000ff35  xor     r15d, r15d
0x18000ff38  lea     rax, [rsp+280h+Name]
0x18000ff3d  mov     esi, 104h
0x18000ff42  mov     [r8], r15
0x18000ff45  mov     edx, esi
0x18000ff47  mov     r14, r8
0x18000ff4a  mov     r9d, 7FFFFFFEh
0x18000ff50  test    r9, r9
0x18000ff53  jz      short loc_18000FF74
0x18000ff55  movzx   r8d, word ptr [rcx]
0x18000ff59  test    r8w, r8w
0x18000ff5d  jz      short loc_18000FF74
0x18000ff5f  mov     [rax], r8w
0x18000ff63  add     rcx, 2
0x18000ff67  add     rax, 2
0x18000ff6b  dec     r9
0x18000ff6e  sub     rdx, 1
0x18000ff72  jnz     short loc_18000FF50
0x18000ff74  test    rdx, rdx
0x18000ff77  lea     rcx, [rax-2]
0x18000ff7b  lea     r8, aP0; "_p0"
0x18000ff82  mov     rdx, rsi; unsigned __int64
0x18000ff85  cmovnz  rcx, rax
0x18000ff89  mov     [rcx], r15w
0x18000ff8d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ff92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ff97  lea     r8, [rsp+280h+Name]; lpName
0x18000ff9c  xor     edx, edx; bInheritHandle
0x18000ff9e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ffa3  call    cs:__imp_OpenSemaphoreW
0x18000ffa9  mov     rbx, rax
0x18000ffac  test    rax, rax
0x18000ffaf  jz      loc_1800100D6
0x18000ffb5  lea     rdx, [rsp+280h+var_25C]; int *
0x18000ffba  mov     [rsp+280h+var_25C], r15d
0x18000ffbf  mov     rcx, rax; hHandle
0x18000ffc2  mov     [rsp+280h+var_260], r15d; int
0x18000ffc7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ffcc  mov     edi, eax
0x18000ffce  test    eax, eax
0x18000ffd0  jns     short loc_18000FFFE
0x18000ffd2  mov     rcx, [rbp+188h]; this
0x18000ffd9  mov     r9d, eax; char *
0x18000ffdc  mov     edx, 0D6h; void *
0x18000ffe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffe6  mov     rcx, rbx; hObject
0x18000ffe9  call    cs:__imp_CloseHandle
0x18000ffef  test    eax, eax
0x18000fff1  jz      loc_18001014B
0x18000fff7  mov     eax, edi
0x18000fff9  jmp     loc_1800100F6
0x18000fffe  lea     r8, asc_1800157E0; "h"
0x180010005  mov     rdx, rsi; unsigned __int64
0x180010008  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001000d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010012  lea     r8, [rsp+280h+Name]; lpName
0x180010017  xor     edx, edx; bInheritHandle
0x180010019  mov     ecx, 1F0003h; dwDesiredAccess
0x18001001e  call    cs:__imp_OpenSemaphoreW
0x180010024  mov     rdi, rax
0x180010027  test    rax, rax
0x18001002a  jz      loc_1800100B1
0x180010030  lea     rdx, [rsp+280h+var_260]; int *
0x180010035  mov     rcx, rax; hHandle
0x180010038  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001003d  mov     esi, eax
0x18001003f  test    eax, eax
0x180010041  jns     short loc_18001007D
0x180010043  mov     rcx, [rbp+188h]; this
0x18001004a  mov     r9d, eax; char *
0x18001004d  mov     edx, 0DEh; void *
0x180010052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010057  mov     rcx, rdi; hObject
0x18001005a  call    cs:__imp_CloseHandle
0x180010060  test    eax, eax
0x180010062  jz      loc_18001015D
0x180010068  mov     rcx, rbx; hObject
0x18001006b  call    cs:__imp_CloseHandle
0x180010071  test    eax, eax
0x180010073  jz      loc_18001016F
0x180010079  mov     eax, esi
0x18001007b  jmp     short loc_1800100F6
0x18001007d  mov     rcx, rdi; hObject
0x180010080  call    cs:__imp_CloseHandle
0x180010086  test    eax, eax
0x180010088  jz      loc_180010115
0x18001008e  movsxd  rax, [rsp+280h+var_25C]
0x180010093  movsxd  rcx, [rsp+280h+var_260]
0x180010098  shl     rcx, 1Fh
0x18001009c  or      rcx, rax
0x18001009f  mov     [r14], rcx
0x1800100a2  mov     rcx, rbx; hObject
0x1800100a5  call    cs:__imp_CloseHandle
0x1800100ab  test    eax, eax
0x1800100ad  jz      short loc_180010127
0x1800100af  jmp     short loc_1800100E1
0x1800100b1  mov     rcx, [rbp+188h]; this
0x1800100b8  mov     edx, 0DCh; void *
0x1800100bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800100c2  mov     rcx, rbx; hObject
0x1800100c5  mov     edi, eax
0x1800100c7  call    cs:__imp_CloseHandle
0x1800100cd  test    eax, eax
0x1800100cf  jz      short loc_180010139
0x1800100d1  jmp     loc_18000FFF7
0x1800100d6  call    cs:__imp_GetLastError
0x1800100dc  cmp     eax, 2
0x1800100df  jnz     short loc_1800100E5
0x1800100e1  xor     eax, eax
0x1800100e3  jmp     short loc_1800100F6
0x1800100e5  mov     rcx, [rbp+188h]; this
0x1800100ec  mov     edx, 0D0h; void *
0x1800100f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800100f6  mov     rcx, [rbp+180h+var_40]
0x1800100fd  xor     rcx, rsp; StackCookie
0x180010100  call    __security_check_cookie
0x180010105  add     rsp, 258h
0x18001010c  pop     r15
0x18001010e  pop     r14
0x180010110  pop     rdi
0x180010111  pop     rsi
0x180010112  pop     rbx
0x180010113  pop     rbp
0x180010114  retn
0x180010115  mov     rcx, [rbp+188h]; this
0x18001011c  mov     edx, 0A0Bh; void *
0x180010121  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010127  mov     rcx, [rbp+188h]; this
0x18001012e  mov     edx, 0A0Bh; void *
0x180010133  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010139  mov     rcx, [rbp+188h]; this
0x180010140  mov     edx, 0A0Bh; void *
0x180010145  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001014b  mov     rcx, [rbp+188h]; this
0x180010152  mov     edx, 0A0Bh; void *
0x180010157  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001015d  mov     rcx, [rbp+188h]; this
0x180010164  mov     edx, 0A0Bh; void *
0x180010169  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001016f  mov     rcx, [rbp+188h]; this
0x180010176  mov     edx, 0A0Bh; void *
0x18001017b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
