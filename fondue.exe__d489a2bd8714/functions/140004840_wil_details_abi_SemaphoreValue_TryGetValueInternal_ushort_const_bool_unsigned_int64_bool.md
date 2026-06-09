# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140004840`
- end: `0x140004aac`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002ab8`

## callees

- `0x1400039f0`
- `0x140004434`
- `0x140004454`
- `0x140004704`
- `0x140004840`
- `0x140004c0c`
- `0x140004cd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004a01`
- `KERNEL32!GetLastError` at `0x140004a01`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400048d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140004949`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400048d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140004949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000491a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000491a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049f2`

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
0x140004840  push    rbp
0x140004842  push    rbx
0x140004843  push    rsi
0x140004844  push    rdi
0x140004845  push    r14
0x140004847  push    r15
0x140004849  lea     rbp, [rsp-158h]
0x140004851  sub     rsp, 258h
0x140004858  mov     rax, cs:__security_cookie
0x14000485f  xor     rax, rsp
0x140004862  mov     [rbp+180h+var_40], rax
0x140004869  xor     r15d, r15d
0x14000486c  lea     rax, [rsp+280h+Name]
0x140004871  mov     [r8], r15
0x140004874  mov     r14, r8
0x140004877  mov     edx, 104h
0x14000487c  mov     r9d, 7FFFFFFEh
0x140004882  test    r9, r9
0x140004885  jz      short loc_1400048A6
0x140004887  movzx   r8d, word ptr [rcx]
0x14000488b  test    r8w, r8w
0x14000488f  jz      short loc_1400048A6
0x140004891  mov     [rax], r8w
0x140004895  add     rcx, 2
0x140004899  add     rax, 2
0x14000489d  dec     r9
0x1400048a0  sub     rdx, 1; unsigned __int64
0x1400048a4  jnz     short loc_140004882
0x1400048a6  test    rdx, rdx
0x1400048a9  lea     rcx, [rax-2]
0x1400048ad  lea     r8, aP0; "_p0"
0x1400048b4  cmovnz  rcx, rax
0x1400048b8  mov     [rcx], r15w
0x1400048bc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400048c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400048c6  mov     esi, 1F0003h
0x1400048cb  lea     r8, [rsp+280h+Name]; lpName
0x1400048d0  mov     ecx, esi; dwDesiredAccess
0x1400048d2  xor     edx, edx; bInheritHandle
0x1400048d4  call    cs:__imp_OpenSemaphoreW
0x1400048da  mov     rbx, rax
0x1400048dd  test    rax, rax
0x1400048e0  jz      loc_140004A01
0x1400048e6  lea     rdx, [rsp+280h+var_25C]; int *
0x1400048eb  mov     [rsp+280h+var_25C], r15d
0x1400048f0  mov     rcx, rax; hHandle
0x1400048f3  mov     [rsp+280h+var_260], r15d; int
0x1400048f8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400048fd  mov     edi, eax
0x1400048ff  test    eax, eax
0x140004901  jns     short loc_14000492F
0x140004903  mov     rcx, [rbp+188h]; this
0x14000490a  mov     r9d, eax; char *
0x14000490d  mov     edx, 0D6h; void *
0x140004912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004917  mov     rcx, rbx; hObject
0x14000491a  call    cs:__imp_CloseHandle
0x140004920  test    eax, eax
0x140004922  jz      loc_140004A76
0x140004928  mov     eax, edi
0x14000492a  jmp     loc_140004A21
0x14000492f  lea     r8, asc_140006890; "h"
0x140004936  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000493b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004940  lea     r8, [rsp+280h+Name]; lpName
0x140004945  xor     edx, edx; bInheritHandle
0x140004947  mov     ecx, esi; dwDesiredAccess
0x140004949  call    cs:__imp_OpenSemaphoreW
0x14000494f  mov     rdi, rax
0x140004952  test    rax, rax
0x140004955  jz      loc_1400049DC
0x14000495b  lea     rdx, [rsp+280h+var_260]; int *
0x140004960  mov     rcx, rax; hHandle
0x140004963  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140004968  mov     esi, eax
0x14000496a  test    eax, eax
0x14000496c  jns     short loc_1400049A8
0x14000496e  mov     rcx, [rbp+188h]; this
0x140004975  mov     r9d, eax; char *
0x140004978  mov     edx, 0DEh; void *
0x14000497d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004982  mov     rcx, rdi; hObject
0x140004985  call    cs:__imp_CloseHandle
0x14000498b  test    eax, eax
0x14000498d  jz      loc_140004A88
0x140004993  mov     rcx, rbx; hObject
0x140004996  call    cs:__imp_CloseHandle
0x14000499c  test    eax, eax
0x14000499e  jz      loc_140004A9A
0x1400049a4  mov     eax, esi
0x1400049a6  jmp     short loc_140004A21
0x1400049a8  mov     rcx, rdi; hObject
0x1400049ab  call    cs:__imp_CloseHandle
0x1400049b1  test    eax, eax
0x1400049b3  jz      loc_140004A40
0x1400049b9  movsxd  rax, [rsp+280h+var_25C]
0x1400049be  movsxd  rcx, [rsp+280h+var_260]
0x1400049c3  shl     rcx, 1Fh
0x1400049c7  or      rcx, rax
0x1400049ca  mov     [r14], rcx
0x1400049cd  mov     rcx, rbx; hObject
0x1400049d0  call    cs:__imp_CloseHandle
0x1400049d6  test    eax, eax
0x1400049d8  jz      short loc_140004A52
0x1400049da  jmp     short loc_140004A0C
0x1400049dc  mov     rcx, [rbp+188h]; this
0x1400049e3  mov     edx, 0DCh; void *
0x1400049e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400049ed  mov     rcx, rbx; hObject
0x1400049f0  mov     edi, eax
0x1400049f2  call    cs:__imp_CloseHandle
0x1400049f8  test    eax, eax
0x1400049fa  jz      short loc_140004A64
0x1400049fc  jmp     loc_140004928
0x140004a01  call    cs:__imp_GetLastError
0x140004a07  cmp     eax, 2
0x140004a0a  jnz     short loc_140004A10
0x140004a0c  xor     eax, eax
0x140004a0e  jmp     short loc_140004A21
0x140004a10  mov     rcx, [rbp+188h]; this
0x140004a17  mov     edx, 0D0h; void *
0x140004a1c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004a21  mov     rcx, [rbp+180h+var_40]
0x140004a28  xor     rcx, rsp; StackCookie
0x140004a2b  call    __security_check_cookie
0x140004a30  add     rsp, 258h
0x140004a37  pop     r15
0x140004a39  pop     r14
0x140004a3b  pop     rdi
0x140004a3c  pop     rsi
0x140004a3d  pop     rbx
0x140004a3e  pop     rbp
0x140004a3f  retn
0x140004a40  mov     rcx, [rbp+188h]; this
0x140004a47  mov     edx, 0A0Bh; void *
0x140004a4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a52  mov     rcx, [rbp+188h]; this
0x140004a59  mov     edx, 0A0Bh; void *
0x140004a5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a64  mov     rcx, [rbp+188h]; this
0x140004a6b  mov     edx, 0A0Bh; void *
0x140004a70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a76  mov     rcx, [rbp+188h]; this
0x140004a7d  mov     edx, 0A0Bh; void *
0x140004a82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a88  mov     rcx, [rbp+188h]; this
0x140004a8f  mov     edx, 0A0Bh; void *
0x140004a94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004a9a  mov     rcx, [rbp+188h]; this
0x140004aa1  mov     edx, 0A0Bh; void *
0x140004aa6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
