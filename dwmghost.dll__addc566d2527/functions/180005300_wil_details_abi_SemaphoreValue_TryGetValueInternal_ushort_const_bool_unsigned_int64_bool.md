# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005300`
- end: `0x1800055b1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `689`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800034ac`

## callees

- `0x180001190`
- `0x1800029d0`
- `0x180004360`
- `0x180004df4`
- `0x180004e14`
- `0x1800051b0`
- `0x180005300`
- `0x18000570c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005397`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005412`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005397`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000545a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000549e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000545a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000549e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054e8`

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
  void *v10; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v12; // r8d
  unsigned int v13; // ebx
  unsigned int v14; // r8d
  const char *v15; // r9
  void *v17; // rbx
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int LastError; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  int v25; // eax
  unsigned int v26; // r8d
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
  int v38; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v39; // [rsp+28h] [rbp-D8h] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38 = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v38);
  v13 = ValueFromSemaphore;
  if ( ValueFromSemaphore >= 0 )
  {
    StringCchCatW(Name, 0x104u, L"h");
    v39 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v39;
    if ( (unsigned __int8)____8V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__YA_NAEBV__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___0___T_Z(&v39) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
      if ( v17 && !CloseHandle(v17) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      if ( !CloseHandle(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      return LastError;
    }
    v25 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v37);
    LastError = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v26, (const char *)(unsigned int)v25, v37);
      if ( v17 && !CloseHandle(v17) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
      if ( !CloseHandle(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      return LastError;
    }
    if ( v17 && !CloseHandle(v17) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    *a3 = v38 | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v37);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
  return v13;
}

```

## disassembly

```asm
0x180005300  push    rbp
0x180005302  push    rbx
0x180005303  push    rsi
0x180005304  push    rdi
0x180005305  push    r14
0x180005307  push    r15
0x180005309  lea     rbp, [rsp-158h]
0x180005311  sub     rsp, 258h
0x180005318  mov     rax, cs:__security_cookie
0x18000531f  xor     rax, rsp
0x180005322  mov     [rbp+180h+var_40], rax
0x180005329  xor     r15d, r15d
0x18000532c  lea     rax, [rsp+280h+Name]
0x180005331  mov     esi, 104h
0x180005336  mov     [r8], r15
0x180005339  mov     edx, esi
0x18000533b  mov     r14, r8
0x18000533e  mov     r9d, 7FFFFFFEh
0x180005344  test    r9, r9
0x180005347  jz      short loc_180005368
0x180005349  movzx   r8d, word ptr [rcx]
0x18000534d  test    r8w, r8w
0x180005351  jz      short loc_180005368
0x180005353  mov     [rax], r8w
0x180005357  add     rcx, 2
0x18000535b  add     rax, 2
0x18000535f  dec     r9
0x180005362  sub     rdx, 1
0x180005366  jnz     short loc_180005344
0x180005368  test    rdx, rdx
0x18000536b  lea     rcx, [rax-2]
0x18000536f  lea     r8, aP0; "_p0"
0x180005376  mov     rdx, rsi; unsigned __int64
0x180005379  cmovnz  rcx, rax
0x18000537d  mov     [rcx], r15w
0x180005381  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005386  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000538b  lea     r8, [rsp+280h+Name]; lpName
0x180005390  xor     edx, edx; bInheritHandle
0x180005392  mov     ecx, 1F0003h; dwDesiredAccess
0x180005397  call    cs:__imp_OpenSemaphoreW
0x18000539d  mov     rdi, rax
0x1800053a0  test    rax, rax
0x1800053a3  jz      loc_1800054F4
0x1800053a9  lea     rdx, [rsp+280h+var_25C]; int *
0x1800053ae  mov     [rsp+280h+var_25C], r15d
0x1800053b3  mov     rcx, rax; hHandle
0x1800053b6  mov     [rsp+280h+var_260], r15d; int
0x1800053bb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800053c0  mov     ebx, eax
0x1800053c2  test    eax, eax
0x1800053c4  jns     short loc_1800053F2
0x1800053c6  mov     rcx, [rbp+188h]; this
0x1800053cd  mov     r9d, eax; char *
0x1800053d0  mov     edx, 0D6h; void *
0x1800053d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053da  mov     rcx, rdi; hObject
0x1800053dd  call    cs:__imp_CloseHandle
0x1800053e3  test    eax, eax
0x1800053e5  jz      loc_180005569
0x1800053eb  mov     eax, ebx
0x1800053ed  jmp     loc_180005514
0x1800053f2  lea     r8, asc_18000E3A0; "h"
0x1800053f9  mov     rdx, rsi; unsigned __int64
0x1800053fc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005401  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005406  lea     r8, [rsp+280h+Name]; lpName
0x18000540b  xor     edx, edx; bInheritHandle
0x18000540d  mov     ecx, 1F0003h; dwDesiredAccess
0x180005412  call    cs:__imp_OpenSemaphoreW
0x180005418  lea     rcx, [rsp+280h+var_258]
0x18000541d  mov     [rsp+280h+var_258], rax
0x180005422  mov     rbx, rax
0x180005425  call    ??$?8V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$T@Z
0x18000542a  test    al, al
0x18000542c  jz      short loc_18000546F
0x18000542e  mov     rcx, [rbp+188h]; this
0x180005435  mov     edx, 0DCh; void *
0x18000543a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000543f  mov     esi, eax
0x180005441  test    rbx, rbx
0x180005444  jz      short loc_180005457
0x180005446  mov     rcx, rbx; hObject
0x180005449  call    cs:__imp_CloseHandle
0x18000544f  test    eax, eax
0x180005451  jz      loc_18000557B
0x180005457  mov     rcx, rdi; hObject
0x18000545a  call    cs:__imp_CloseHandle
0x180005460  test    eax, eax
0x180005462  jz      loc_18000558D
0x180005468  mov     eax, esi
0x18000546a  jmp     loc_180005514
0x18000546f  lea     rdx, [rsp+280h+var_260]; int *
0x180005474  mov     rcx, rbx; hHandle
0x180005477  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000547c  mov     esi, eax
0x18000547e  test    eax, eax
0x180005480  jns     short loc_1800054BF
0x180005482  mov     rcx, [rbp+188h]; this
0x180005489  mov     r9d, eax; char *
0x18000548c  mov     edx, 0DEh; void *
0x180005491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005496  test    rbx, rbx
0x180005499  jz      short loc_1800054AC
0x18000549b  mov     rcx, rbx; hObject
0x18000549e  call    cs:__imp_CloseHandle
0x1800054a4  test    eax, eax
0x1800054a6  jz      loc_18000559F
0x1800054ac  mov     rcx, rdi; hObject
0x1800054af  call    cs:__imp_CloseHandle
0x1800054b5  test    eax, eax
0x1800054b7  jz      loc_180005545
0x1800054bd  jmp     short loc_180005468
0x1800054bf  test    rbx, rbx
0x1800054c2  jz      short loc_1800054D1
0x1800054c4  mov     rcx, rbx; hObject
0x1800054c7  call    cs:__imp_CloseHandle
0x1800054cd  test    eax, eax
0x1800054cf  jz      short loc_180005533
0x1800054d1  movsxd  rax, [rsp+280h+var_25C]
0x1800054d6  movsxd  rcx, [rsp+280h+var_260]
0x1800054db  shl     rcx, 1Fh
0x1800054df  or      rcx, rax
0x1800054e2  mov     [r14], rcx
0x1800054e5  mov     rcx, rdi; hObject
0x1800054e8  call    cs:__imp_CloseHandle
0x1800054ee  test    eax, eax
0x1800054f0  jz      short loc_180005557
0x1800054f2  jmp     short loc_1800054FF
0x1800054f4  call    cs:__imp_GetLastError
0x1800054fa  cmp     eax, 2
0x1800054fd  jnz     short loc_180005503
0x1800054ff  xor     eax, eax
0x180005501  jmp     short loc_180005514
0x180005503  mov     rcx, [rbp+188h]; this
0x18000550a  mov     edx, 0D0h; void *
0x18000550f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005514  mov     rcx, [rbp+180h+var_40]
0x18000551b  xor     rcx, rsp; StackCookie
0x18000551e  call    __security_check_cookie
0x180005523  add     rsp, 258h
0x18000552a  pop     r15
0x18000552c  pop     r14
0x18000552e  pop     rdi
0x18000552f  pop     rsi
0x180005530  pop     rbx
0x180005531  pop     rbp
0x180005532  retn
0x180005533  mov     rcx, [rbp+188h]; this
0x18000553a  mov     edx, 0A0Bh; void *
0x18000553f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005545  mov     rcx, [rbp+188h]; this
0x18000554c  mov     edx, 0A0Bh; void *
0x180005551  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005557  mov     rcx, [rbp+188h]; this
0x18000555e  mov     edx, 0A0Bh; void *
0x180005563  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005569  mov     rcx, [rbp+188h]; this
0x180005570  mov     edx, 0A0Bh; void *
0x180005575  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000557b  mov     rcx, [rbp+188h]; this
0x180005582  mov     edx, 0A0Bh; void *
0x180005587  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000558d  mov     rcx, [rbp+188h]; this
0x180005594  mov     edx, 0A0Bh; void *
0x180005599  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000559f  mov     rcx, [rbp+188h]; this
0x1800055a6  mov     edx, 0A0Bh; void *
0x1800055ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
