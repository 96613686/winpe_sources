# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000545c`
- end: `0x1800056d6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002e48`

## callees

- `0x180001520`
- `0x180003dd4`
- `0x1800049d4`
- `0x1800049f4`
- `0x1800052d0`
- `0x18000545c`
- `0x18000582c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800054f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000556c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800054f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000556c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000562b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000562b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000553d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000561c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000553d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000561c`

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
0x18000545c  push    rbp
0x18000545e  push    rbx
0x18000545f  push    rsi
0x180005460  push    rdi
0x180005461  push    r14
0x180005463  push    r15
0x180005465  lea     rbp, [rsp-158h]
0x18000546d  sub     rsp, 258h
0x180005474  mov     rax, cs:__security_cookie
0x18000547b  xor     rax, rsp
0x18000547e  mov     [rbp+180h+var_40], rax
0x180005485  xor     r15d, r15d
0x180005488  lea     rax, [rsp+280h+Name]
0x18000548d  mov     [r8], r15
0x180005490  mov     r14, r8
0x180005493  mov     edx, 104h
0x180005498  mov     r9d, 7FFFFFFEh
0x18000549e  test    r9, r9
0x1800054a1  jz      short loc_1800054C2
0x1800054a3  movzx   r8d, word ptr [rcx]
0x1800054a7  test    r8w, r8w
0x1800054ab  jz      short loc_1800054C2
0x1800054ad  mov     [rax], r8w
0x1800054b1  add     rcx, 2
0x1800054b5  add     rax, 2
0x1800054b9  dec     r9
0x1800054bc  sub     rdx, 1; unsigned __int64
0x1800054c0  jnz     short loc_18000549E
0x1800054c2  test    rdx, rdx
0x1800054c5  lea     rcx, [rax-2]
0x1800054c9  lea     r8, aP0; "_p0"
0x1800054d0  cmovnz  rcx, rax
0x1800054d4  mov     [rcx], r15w
0x1800054d8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800054dd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800054e2  mov     esi, 1F0003h
0x1800054e7  lea     r8, [rsp+280h+Name]; lpName
0x1800054ec  mov     ecx, esi; dwDesiredAccess
0x1800054ee  xor     edx, edx; bInheritHandle
0x1800054f0  call    cs:__imp_OpenSemaphoreW
0x1800054f6  mov     rbx, rax
0x1800054f9  test    rax, rax
0x1800054fc  jz      loc_18000562B
0x180005502  lea     rdx, [rsp+280h+var_25C]; int *
0x180005507  mov     [rsp+280h+var_25C], r15d
0x18000550c  mov     rcx, rax; hHandle
0x18000550f  mov     [rsp+280h+var_260], r15d; int
0x180005514  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005519  mov     edi, eax
0x18000551b  test    eax, eax
0x18000551d  jns     short loc_180005552
0x18000551f  mov     rcx, [rbp+188h]; this
0x180005526  lea     r8, aWil; "wil"
0x18000552d  mov     r9d, eax; char *
0x180005530  mov     edx, 0D6h; void *
0x180005535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000553a  mov     rcx, rbx; hObject
0x18000553d  call    cs:__imp_CloseHandle
0x180005543  test    eax, eax
0x180005545  jz      loc_1800056A0
0x18000554b  mov     eax, edi
0x18000554d  jmp     loc_18000564B
0x180005552  lea     r8, asc_18000D960; "h"
0x180005559  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000555e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005563  lea     r8, [rsp+280h+Name]; lpName
0x180005568  xor     edx, edx; bInheritHandle
0x18000556a  mov     ecx, esi; dwDesiredAccess
0x18000556c  call    cs:__imp_OpenSemaphoreW
0x180005572  mov     rdi, rax
0x180005575  test    rax, rax
0x180005578  jz      loc_180005606
0x18000557e  lea     rdx, [rsp+280h+var_260]; int *
0x180005583  mov     rcx, rax; hHandle
0x180005586  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000558b  mov     esi, eax
0x18000558d  test    eax, eax
0x18000558f  jns     short loc_1800055D2
0x180005591  mov     rcx, [rbp+188h]; this
0x180005598  lea     r8, aWil; "wil"
0x18000559f  mov     r9d, eax; char *
0x1800055a2  mov     edx, 0DEh; void *
0x1800055a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055ac  mov     rcx, rdi; hObject
0x1800055af  call    cs:__imp_CloseHandle
0x1800055b5  test    eax, eax
0x1800055b7  jz      loc_1800056B2
0x1800055bd  mov     rcx, rbx; hObject
0x1800055c0  call    cs:__imp_CloseHandle
0x1800055c6  test    eax, eax
0x1800055c8  jz      loc_1800056C4
0x1800055ce  mov     eax, esi
0x1800055d0  jmp     short loc_18000564B
0x1800055d2  mov     rcx, rdi; hObject
0x1800055d5  call    cs:__imp_CloseHandle
0x1800055db  test    eax, eax
0x1800055dd  jz      loc_18000566A
0x1800055e3  movsxd  rax, [rsp+280h+var_25C]
0x1800055e8  movsxd  rcx, [rsp+280h+var_260]
0x1800055ed  shl     rcx, 1Fh
0x1800055f1  or      rcx, rax
0x1800055f4  mov     [r14], rcx
0x1800055f7  mov     rcx, rbx; hObject
0x1800055fa  call    cs:__imp_CloseHandle
0x180005600  test    eax, eax
0x180005602  jz      short loc_18000567C
0x180005604  jmp     short loc_180005636
0x180005606  mov     rcx, [rbp+188h]; this
0x18000560d  mov     edx, 0DCh; void *
0x180005612  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005617  mov     rcx, rbx; hObject
0x18000561a  mov     edi, eax
0x18000561c  call    cs:__imp_CloseHandle
0x180005622  test    eax, eax
0x180005624  jz      short loc_18000568E
0x180005626  jmp     loc_18000554B
0x18000562b  call    cs:__imp_GetLastError
0x180005631  cmp     eax, 2
0x180005634  jnz     short loc_18000563A
0x180005636  xor     eax, eax
0x180005638  jmp     short loc_18000564B
0x18000563a  mov     rcx, [rbp+188h]; this
0x180005641  mov     edx, 0D0h; void *
0x180005646  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000564b  mov     rcx, [rbp+180h+var_40]
0x180005652  xor     rcx, rsp; StackCookie
0x180005655  call    __security_check_cookie
0x18000565a  add     rsp, 258h
0x180005661  pop     r15
0x180005663  pop     r14
0x180005665  pop     rdi
0x180005666  pop     rsi
0x180005667  pop     rbx
0x180005668  pop     rbp
0x180005669  retn
0x18000566a  mov     rcx, [rbp+188h]; this
0x180005671  mov     edx, 0A0Bh; void *
0x180005676  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000567c  mov     rcx, [rbp+188h]; this
0x180005683  mov     edx, 0A0Bh; void *
0x180005688  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000568e  mov     rcx, [rbp+188h]; this
0x180005695  mov     edx, 0A0Bh; void *
0x18000569a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800056a0  mov     rcx, [rbp+188h]; this
0x1800056a7  mov     edx, 0A0Bh; void *
0x1800056ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800056b2  mov     rcx, [rbp+188h]; this
0x1800056b9  mov     edx, 0A0Bh; void *
0x1800056be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800056c4  mov     rcx, [rbp+188h]; this
0x1800056cb  mov     edx, 0A0Bh; void *
0x1800056d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
