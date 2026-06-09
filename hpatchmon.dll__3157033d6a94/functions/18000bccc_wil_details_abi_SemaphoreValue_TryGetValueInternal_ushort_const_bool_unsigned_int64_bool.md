# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bccc`
- end: `0x18000bf38`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800048f8`
- `0x180004c9c`

## callees

- `0x180002270`
- `0x180006e44`
- `0x180009964`
- `0x180009984`
- `0x18000b68c`
- `0x18000bccc`
- `0x18000c58c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be8d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bd60`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bdd5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bd60`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bdd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bda6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bda6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be7e`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
0x18000bccc  push    rbp
0x18000bcce  push    rbx
0x18000bccf  push    rsi
0x18000bcd0  push    rdi
0x18000bcd1  push    r14
0x18000bcd3  push    r15
0x18000bcd5  lea     rbp, [rsp-158h]
0x18000bcdd  sub     rsp, 258h
0x18000bce4  mov     rax, cs:__security_cookie
0x18000bceb  xor     rax, rsp
0x18000bcee  mov     [rbp+180h+var_40], rax
0x18000bcf5  xor     r15d, r15d
0x18000bcf8  lea     rax, [rsp+280h+Name]
0x18000bcfd  mov     [r8], r15
0x18000bd00  mov     r14, r8
0x18000bd03  mov     edx, 104h
0x18000bd08  mov     r9d, 7FFFFFFEh
0x18000bd0e  test    r9, r9
0x18000bd11  jz      short loc_18000BD32
0x18000bd13  movzx   r8d, word ptr [rcx]
0x18000bd17  test    r8w, r8w
0x18000bd1b  jz      short loc_18000BD32
0x18000bd1d  mov     [rax], r8w
0x18000bd21  add     rcx, 2
0x18000bd25  add     rax, 2
0x18000bd29  dec     r9
0x18000bd2c  sub     rdx, 1; unsigned __int64
0x18000bd30  jnz     short loc_18000BD0E
0x18000bd32  test    rdx, rdx
0x18000bd35  lea     rcx, [rax-2]
0x18000bd39  lea     r8, aP0; "_p0"
0x18000bd40  cmovnz  rcx, rax
0x18000bd44  mov     [rcx], r15w
0x18000bd48  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bd4d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bd52  mov     esi, 1F0003h
0x18000bd57  lea     r8, [rsp+280h+Name]; lpName
0x18000bd5c  mov     ecx, esi; dwDesiredAccess
0x18000bd5e  xor     edx, edx; bInheritHandle
0x18000bd60  call    cs:__imp_OpenSemaphoreW
0x18000bd66  mov     rbx, rax
0x18000bd69  test    rax, rax
0x18000bd6c  jz      loc_18000BE8D
0x18000bd72  lea     rdx, [rsp+280h+var_25C]; int *
0x18000bd77  mov     [rsp+280h+var_25C], r15d
0x18000bd7c  mov     rcx, rax; hHandle
0x18000bd7f  mov     [rsp+280h+var_260], r15d; int
0x18000bd84  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bd89  mov     edi, eax
0x18000bd8b  test    eax, eax
0x18000bd8d  jns     short loc_18000BDBB
0x18000bd8f  mov     rcx, [rbp+188h]; this
0x18000bd96  mov     r9d, eax; char *
0x18000bd99  mov     edx, 0D6h; void *
0x18000bd9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bda3  mov     rcx, rbx; hObject
0x18000bda6  call    cs:__imp_CloseHandle
0x18000bdac  test    eax, eax
0x18000bdae  jz      loc_18000BF02
0x18000bdb4  mov     eax, edi
0x18000bdb6  jmp     loc_18000BEAD
0x18000bdbb  lea     r8, asc_180016F00; "h"
0x18000bdc2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bdc7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bdcc  lea     r8, [rsp+280h+Name]; lpName
0x18000bdd1  xor     edx, edx; bInheritHandle
0x18000bdd3  mov     ecx, esi; dwDesiredAccess
0x18000bdd5  call    cs:__imp_OpenSemaphoreW
0x18000bddb  mov     rdi, rax
0x18000bdde  test    rax, rax
0x18000bde1  jz      loc_18000BE68
0x18000bde7  lea     rdx, [rsp+280h+var_260]; int *
0x18000bdec  mov     rcx, rax; hHandle
0x18000bdef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bdf4  mov     esi, eax
0x18000bdf6  test    eax, eax
0x18000bdf8  jns     short loc_18000BE34
0x18000bdfa  mov     rcx, [rbp+188h]; this
0x18000be01  mov     r9d, eax; char *
0x18000be04  mov     edx, 0DEh; void *
0x18000be09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be0e  mov     rcx, rdi; hObject
0x18000be11  call    cs:__imp_CloseHandle
0x18000be17  test    eax, eax
0x18000be19  jz      loc_18000BF14
0x18000be1f  mov     rcx, rbx; hObject
0x18000be22  call    cs:__imp_CloseHandle
0x18000be28  test    eax, eax
0x18000be2a  jz      loc_18000BF26
0x18000be30  mov     eax, esi
0x18000be32  jmp     short loc_18000BEAD
0x18000be34  mov     rcx, rdi; hObject
0x18000be37  call    cs:__imp_CloseHandle
0x18000be3d  test    eax, eax
0x18000be3f  jz      loc_18000BECC
0x18000be45  movsxd  rax, [rsp+280h+var_25C]
0x18000be4a  movsxd  rcx, [rsp+280h+var_260]
0x18000be4f  shl     rcx, 1Fh
0x18000be53  or      rcx, rax
0x18000be56  mov     [r14], rcx
0x18000be59  mov     rcx, rbx; hObject
0x18000be5c  call    cs:__imp_CloseHandle
0x18000be62  test    eax, eax
0x18000be64  jz      short loc_18000BEDE
0x18000be66  jmp     short loc_18000BE98
0x18000be68  mov     rcx, [rbp+188h]; this
0x18000be6f  mov     edx, 0DCh; void *
0x18000be74  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be79  mov     rcx, rbx; hObject
0x18000be7c  mov     edi, eax
0x18000be7e  call    cs:__imp_CloseHandle
0x18000be84  test    eax, eax
0x18000be86  jz      short loc_18000BEF0
0x18000be88  jmp     loc_18000BDB4
0x18000be8d  call    cs:__imp_GetLastError
0x18000be93  cmp     eax, 2
0x18000be96  jnz     short loc_18000BE9C
0x18000be98  xor     eax, eax
0x18000be9a  jmp     short loc_18000BEAD
0x18000be9c  mov     rcx, [rbp+188h]; this
0x18000bea3  mov     edx, 0D0h; void *
0x18000bea8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bead  mov     rcx, [rbp+180h+var_40]
0x18000beb4  xor     rcx, rsp; StackCookie
0x18000beb7  call    __security_check_cookie
0x18000bebc  add     rsp, 258h
0x18000bec3  pop     r15
0x18000bec5  pop     r14
0x18000bec7  pop     rdi
0x18000bec8  pop     rsi
0x18000bec9  pop     rbx
0x18000beca  pop     rbp
0x18000becb  retn
0x18000becc  mov     rcx, [rbp+188h]; this
0x18000bed3  mov     edx, 0A0Bh; void *
0x18000bed8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bede  mov     rcx, [rbp+188h]; this
0x18000bee5  mov     edx, 0A0Bh; void *
0x18000beea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bef0  mov     rcx, [rbp+188h]; this
0x18000bef7  mov     edx, 0A0Bh; void *
0x18000befc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf02  mov     rcx, [rbp+188h]; this
0x18000bf09  mov     edx, 0A0Bh; void *
0x18000bf0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf14  mov     rcx, [rbp+188h]; this
0x18000bf1b  mov     edx, 0A0Bh; void *
0x18000bf20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf26  mov     rcx, [rbp+188h]; this
0x18000bf2d  mov     edx, 0A0Bh; void *
0x18000bf32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
