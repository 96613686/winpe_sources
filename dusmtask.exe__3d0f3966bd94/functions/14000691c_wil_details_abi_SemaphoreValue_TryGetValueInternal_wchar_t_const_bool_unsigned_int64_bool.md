# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000691c`
- end: `0x140006b88`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003d68`

## callees

- `0x140001470`
- `0x140004cd4`
- `0x1400059a4`
- `0x1400059c4`
- `0x14000676c`
- `0x14000691c`
- `0x140006cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400069b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006a25`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400069b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400069f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006a87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006ace`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400069f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006a87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006ace`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  __int64 v19; // r8
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
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
  __int64 v35; // r8
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
  StringCchCatW(Name, v6, (wchar_t *)L"_p0");
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, (wchar_t *)L"h");
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x14000691c  push    rbp
0x14000691e  push    rbx
0x14000691f  push    rsi
0x140006920  push    rdi
0x140006921  push    r14
0x140006923  push    r15
0x140006925  lea     rbp, [rsp-158h]
0x14000692d  sub     rsp, 258h
0x140006934  mov     rax, cs:__security_cookie
0x14000693b  xor     rax, rsp
0x14000693e  mov     [rbp+180h+var_40], rax
0x140006945  xor     r15d, r15d
0x140006948  lea     rax, [rsp+280h+Name]
0x14000694d  mov     [r8], r15
0x140006950  mov     r14, r8
0x140006953  mov     edx, 104h
0x140006958  mov     r9d, 7FFFFFFEh
0x14000695e  test    r9, r9
0x140006961  jz      short loc_140006982
0x140006963  movzx   r8d, word ptr [rcx]
0x140006967  test    r8w, r8w
0x14000696b  jz      short loc_140006982
0x14000696d  mov     [rax], r8w
0x140006971  add     rcx, 2
0x140006975  add     rax, 2
0x140006979  dec     r9
0x14000697c  sub     rdx, 1; unsigned __int64
0x140006980  jnz     short loc_14000695E
0x140006982  test    rdx, rdx
0x140006985  lea     rcx, [rax-2]
0x140006989  lea     r8, aP0; "_p0"
0x140006990  cmovnz  rcx, rax
0x140006994  mov     [rcx], r15w
0x140006998  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000699d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400069a2  mov     esi, 1F0003h
0x1400069a7  lea     r8, [rsp+280h+Name]; lpName
0x1400069ac  mov     ecx, esi; dwDesiredAccess
0x1400069ae  xor     edx, edx; bInheritHandle
0x1400069b0  call    cs:__imp_OpenSemaphoreW
0x1400069b6  mov     rbx, rax
0x1400069b9  test    rax, rax
0x1400069bc  jz      loc_140006ADD
0x1400069c2  lea     rdx, [rsp+280h+var_25C]; int *
0x1400069c7  mov     [rsp+280h+var_25C], r15d
0x1400069cc  mov     rcx, rax; hHandle
0x1400069cf  mov     [rsp+280h+var_260], r15d; int
0x1400069d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400069d9  mov     edi, eax
0x1400069db  test    eax, eax
0x1400069dd  jns     short loc_140006A0B
0x1400069df  mov     rcx, [rbp+188h]; this
0x1400069e6  mov     r9d, eax; char *
0x1400069e9  mov     edx, 0D6h; void *
0x1400069ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400069f3  mov     rcx, rbx; hObject
0x1400069f6  call    cs:__imp_CloseHandle
0x1400069fc  test    eax, eax
0x1400069fe  jz      loc_140006B52
0x140006a04  mov     eax, edi
0x140006a06  jmp     loc_140006AFD
0x140006a0b  lea     r8, asc_140009AE8; "h"
0x140006a12  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140006a17  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140006a1c  lea     r8, [rsp+280h+Name]; lpName
0x140006a21  xor     edx, edx; bInheritHandle
0x140006a23  mov     ecx, esi; dwDesiredAccess
0x140006a25  call    cs:__imp_OpenSemaphoreW
0x140006a2b  mov     rdi, rax
0x140006a2e  test    rax, rax
0x140006a31  jz      loc_140006AB8
0x140006a37  lea     rdx, [rsp+280h+var_260]; int *
0x140006a3c  mov     rcx, rax; hHandle
0x140006a3f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006a44  mov     esi, eax
0x140006a46  test    eax, eax
0x140006a48  jns     short loc_140006A84
0x140006a4a  mov     rcx, [rbp+188h]; this
0x140006a51  mov     r9d, eax; char *
0x140006a54  mov     edx, 0DEh; void *
0x140006a59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006a5e  mov     rcx, rdi; hObject
0x140006a61  call    cs:__imp_CloseHandle
0x140006a67  test    eax, eax
0x140006a69  jz      loc_140006B64
0x140006a6f  mov     rcx, rbx; hObject
0x140006a72  call    cs:__imp_CloseHandle
0x140006a78  test    eax, eax
0x140006a7a  jz      loc_140006B76
0x140006a80  mov     eax, esi
0x140006a82  jmp     short loc_140006AFD
0x140006a84  mov     rcx, rdi; hObject
0x140006a87  call    cs:__imp_CloseHandle
0x140006a8d  test    eax, eax
0x140006a8f  jz      loc_140006B1C
0x140006a95  movsxd  rax, [rsp+280h+var_25C]
0x140006a9a  movsxd  rcx, [rsp+280h+var_260]
0x140006a9f  shl     rcx, 1Fh
0x140006aa3  or      rcx, rax
0x140006aa6  mov     [r14], rcx
0x140006aa9  mov     rcx, rbx; hObject
0x140006aac  call    cs:__imp_CloseHandle
0x140006ab2  test    eax, eax
0x140006ab4  jz      short loc_140006B2E
0x140006ab6  jmp     short loc_140006AE8
0x140006ab8  mov     rcx, [rbp+188h]; this
0x140006abf  mov     edx, 0DCh; void *
0x140006ac4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006ac9  mov     rcx, rbx; hObject
0x140006acc  mov     edi, eax
0x140006ace  call    cs:__imp_CloseHandle
0x140006ad4  test    eax, eax
0x140006ad6  jz      short loc_140006B40
0x140006ad8  jmp     loc_140006A04
0x140006add  call    cs:__imp_GetLastError
0x140006ae3  cmp     eax, 2
0x140006ae6  jnz     short loc_140006AEC
0x140006ae8  xor     eax, eax
0x140006aea  jmp     short loc_140006AFD
0x140006aec  mov     rcx, [rbp+188h]; this
0x140006af3  mov     edx, 0D0h; void *
0x140006af8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006afd  mov     rcx, [rbp+180h+var_40]
0x140006b04  xor     rcx, rsp; StackCookie
0x140006b07  call    __security_check_cookie
0x140006b0c  add     rsp, 258h
0x140006b13  pop     r15
0x140006b15  pop     r14
0x140006b17  pop     rdi
0x140006b18  pop     rsi
0x140006b19  pop     rbx
0x140006b1a  pop     rbp
0x140006b1b  retn
0x140006b1c  mov     rcx, [rbp+188h]; this
0x140006b23  mov     edx, 0A0Bh; void *
0x140006b28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b2e  mov     rcx, [rbp+188h]; this
0x140006b35  mov     edx, 0A0Bh; void *
0x140006b3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b40  mov     rcx, [rbp+188h]; this
0x140006b47  mov     edx, 0A0Bh; void *
0x140006b4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b52  mov     rcx, [rbp+188h]; this
0x140006b59  mov     edx, 0A0Bh; void *
0x140006b5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b64  mov     rcx, [rbp+188h]; this
0x140006b6b  mov     edx, 0A0Bh; void *
0x140006b70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b76  mov     rcx, [rbp+188h]; this
0x140006b7d  mov     edx, 0A0Bh; void *
0x140006b82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
