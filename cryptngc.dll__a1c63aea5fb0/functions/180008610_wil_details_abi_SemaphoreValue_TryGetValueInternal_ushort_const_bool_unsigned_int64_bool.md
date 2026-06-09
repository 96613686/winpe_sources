# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008610`
- end: `0x180008924`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `788`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007460`
- `0x180008358`

## callees

- `0x180006538`
- `0x180008610`
- `0x18000892c`
- `0x180008a84`
- `0x180008ee4`
- `0x180028360`
- `0x180031878`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800086fe`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008802`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800086fe`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088bf`

## string_xrefs

- `0x180008888`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800088d1`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // r9
  __int64 v5; // rbp
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r10
  WCHAR *v10; // rcx
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  _WORD *v14; // r9
  const unsigned __int16 *v15; // r8
  _WORD *v16; // rcx
  HANDLE v17; // rax
  void *v18; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v20; // esi
  WCHAR *v22; // rax
  _WORD *v23; // r8
  const unsigned __int16 *v24; // rcx
  _WORD *v25; // rdx
  wil::details *v26; // rax
  const char *v27; // r9
  wil::details *v28; // rbx
  int v29; // eax
  void *v30; // rdx
  const char *v31; // r9
  unsigned int LastError; // ebx
  const char *v33; // r9
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-258h] BYREF
  int v36; // [rsp+24h] [rbp-254h] BYREF
  HANDLE v37; // [rsp+28h] [rbp-250h] BYREF
  wil::details *v38; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Name[260]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v40[8]; // [rsp+248h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  v8 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v10 = v4 - 1;
  v11 = 260;
  if ( v8 )
    v10 = v4;
  *v10 = 0;
  v12 = Name;
  while ( *v12 )
  {
    ++v12;
    if ( !--v11 )
      goto LABEL_18;
  }
  v13 = 2147483646;
  v14 = &v40[-2 * v11];
  v15 = L"_p0";
  do
  {
    if ( !v13 )
      break;
    if ( !*v15 )
      break;
    *v14++ = *v15++;
    --v13;
    --v11;
  }
  while ( v11 );
  v16 = v14 - 1;
  if ( v11 )
    v16 = v14;
  *v16 = 0;
LABEL_18:
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v37 = v17;
  v18 = v17;
  if ( v17 )
  {
    v36 = 0;
    v35 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
    v20 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v35);
LABEL_21:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v37);
      return v20;
    }
    v22 = Name;
    while ( *v22 )
    {
      ++v22;
      if ( !--v6 )
        goto LABEL_33;
    }
    v23 = &v40[-2 * v6];
    v24 = L"h";
    do
    {
      if ( !v5 )
        break;
      if ( !*v24 )
        break;
      *v23++ = *v24++;
      --v5;
      --v6;
    }
    while ( v6 );
    v25 = v23 - 1;
    if ( v6 )
      v25 = v23;
    *v25 = 0;
LABEL_33:
    v26 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v38 = v26;
    v28 = v26;
    if ( v26 )
    {
      v29 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v26, &v35);
      v20 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v29,
          v35);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v38);
        goto LABEL_21;
      }
      wil::details::CloseHandle(v28, v30);
      *a3 = v36 | (unsigned __int64)((__int64)v35 << 31);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v31);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v27);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v33);
      return LastError;
    }
  }
  else if ( GetLastError() == 2 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v37);
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v34);
  }
}

```

## disassembly

```asm
0x180008610  mov     [rsp+arg_8], rbx
0x180008615  mov     [rsp+arg_18], rbp
0x18000861a  push    rdi
0x18000861b  push    r14
0x18000861d  push    r15
0x18000861f  sub     rsp, 260h
0x180008626  mov     rax, cs:__security_cookie
0x18000862d  xor     rax, rsp
0x180008630  mov     [rsp+278h+var_28], rax
0x180008638  xor     r15d, r15d
0x18000863b  lea     r9, [rsp+278h+Name]
0x180008640  mov     ebp, 7FFFFFFEh
0x180008645  mov     [r8], r15
0x180008648  mov     ebx, 104h
0x18000864d  mov     edx, ebp
0x18000864f  mov     r10d, ebx
0x180008652  mov     r14, r8
0x180008655  test    rdx, rdx
0x180008658  jz      short loc_180008677
0x18000865a  movzx   eax, word ptr [rcx]
0x18000865d  test    ax, ax
0x180008660  jz      short loc_180008677
0x180008662  mov     [r9], ax
0x180008666  add     rcx, 2
0x18000866a  add     r9, 2
0x18000866e  dec     rdx
0x180008671  sub     r10, 1
0x180008675  jnz     short loc_180008655
0x180008677  test    r10, r10
0x18000867a  lea     rcx, [r9-2]
0x18000867e  mov     rax, rbx
0x180008681  cmovnz  rcx, r9
0x180008685  mov     [rcx], r15w
0x180008689  lea     rcx, [rsp+278h+Name]
0x18000868e  xchg    ax, ax
0x180008690  cmp     [rcx], r15w
0x180008694  jz      short loc_1800086A2
0x180008696  add     rcx, 2
0x18000869a  sub     rax, 1
0x18000869e  jnz     short loc_180008690
0x1800086a0  jmp     short loc_1800086F2
0x1800086a2  lea     rcx, [rax+rax]
0x1800086a6  mov     rdx, rbp
0x1800086a9  lea     r9, [rsp+278h+var_30]
0x1800086b1  sub     r9, rcx
0x1800086b4  lea     r8, aP0; "_p0"
0x1800086bb  test    rax, rax
0x1800086be  jz      short loc_1800086E3
0x1800086c0  test    rdx, rdx
0x1800086c3  jz      short loc_1800086E3
0x1800086c5  movzx   ecx, word ptr [r8]
0x1800086c9  test    cx, cx
0x1800086cc  jz      short loc_1800086E3
0x1800086ce  mov     [r9], cx
0x1800086d2  add     r8, 2
0x1800086d6  add     r9, 2
0x1800086da  dec     rdx
0x1800086dd  sub     rax, 1
0x1800086e1  jnz     short loc_1800086C0
0x1800086e3  test    rax, rax
0x1800086e6  lea     rcx, [r9-2]
0x1800086ea  cmovnz  rcx, r9
0x1800086ee  mov     [rcx], r15w
0x1800086f2  lea     r8, [rsp+278h+Name]; lpName
0x1800086f7  xor     edx, edx; bInheritHandle
0x1800086f9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800086fe  call    cs:__imp_OpenSemaphoreW
0x180008704  mov     [rsp+278h+var_250], rax
0x180008709  mov     rdi, rax
0x18000870c  test    rax, rax
0x18000870f  jz      loc_1800088EA
0x180008715  lea     rdx, [rsp+278h+var_254]; int *
0x18000871a  mov     [rsp+278h+arg_0], rsi
0x180008722  mov     rcx, rax; hHandle
0x180008725  mov     [rsp+278h+var_254], r15d
0x18000872a  mov     [rsp+278h+var_258], r15d; int
0x18000872f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008734  mov     esi, eax
0x180008736  test    eax, eax
0x180008738  jns     short loc_180008793
0x18000873a  mov     rcx, [rsp+278h]; this
0x180008742  lea     r8, aWil; "wil"
0x180008749  mov     r9d, eax; char *
0x18000874c  mov     edx, 0D6h; void *
0x180008751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008756  lea     rcx, [rsp+278h+var_250]
0x18000875b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008760  mov     eax, esi
0x180008762  mov     rsi, [rsp+278h+arg_0]
0x18000876a  mov     rcx, [rsp+278h+var_28]
0x180008772  xor     rcx, rsp; StackCookie
0x180008775  call    __security_check_cookie
0x18000877a  lea     r11, [rsp+278h+var_18]
0x180008782  mov     rbx, [r11+28h]
0x180008786  mov     rbp, [r11+38h]
0x18000878a  mov     rsp, r11
0x18000878d  pop     r15
0x18000878f  pop     r14
0x180008791  pop     rdi
0x180008792  retn
0x180008793  lea     rax, [rsp+278h+Name]
0x180008798  cmp     [rax], r15w
0x18000879c  jz      short loc_1800087AA
0x18000879e  add     rax, 2
0x1800087a2  sub     rbx, 1
0x1800087a6  jnz     short loc_180008798
0x1800087a8  jmp     short loc_1800087F6
0x1800087aa  lea     rax, [rbx+rbx]
0x1800087ae  lea     r8, [rsp+278h+var_30]
0x1800087b6  sub     r8, rax
0x1800087b9  lea     rcx, asc_180051B20; "h"
0x1800087c0  test    rbx, rbx
0x1800087c3  jz      short loc_1800087E7
0x1800087c5  test    rbp, rbp
0x1800087c8  jz      short loc_1800087E7
0x1800087ca  movzx   eax, word ptr [rcx]
0x1800087cd  test    ax, ax
0x1800087d0  jz      short loc_1800087E7
0x1800087d2  mov     [r8], ax
0x1800087d6  add     rcx, 2
0x1800087da  add     r8, 2
0x1800087de  dec     rbp
0x1800087e1  sub     rbx, 1
0x1800087e5  jnz     short loc_1800087C5
0x1800087e7  test    rbx, rbx
0x1800087ea  lea     rdx, [r8-2]
0x1800087ee  cmovnz  rdx, r8
0x1800087f2  mov     [rdx], r15w
0x1800087f6  lea     r8, [rsp+278h+Name]; lpName
0x1800087fb  xor     edx, edx; bInheritHandle
0x1800087fd  mov     ecx, 1F0003h; dwDesiredAccess
0x180008802  call    cs:__imp_OpenSemaphoreW
0x180008808  mov     [rsp+278h+var_248], rax
0x18000880d  mov     rbx, rax
0x180008810  test    rax, rax
0x180008813  jz      loc_1800088A1
0x180008819  lea     rdx, [rsp+278h+var_258]; int *
0x18000881e  mov     rcx, rax; hHandle
0x180008821  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008826  mov     esi, eax
0x180008828  test    eax, eax
0x18000882a  jns     short loc_180008857
0x18000882c  mov     rcx, [rsp+278h]; this
0x180008834  lea     r8, aWil; "wil"
0x18000883b  mov     r9d, eax; char *
0x18000883e  mov     edx, 0DEh; void *
0x180008843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008848  lea     rcx, [rsp+278h+var_248]
0x18000884d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008852  jmp     loc_180008756
0x180008857  mov     rcx, rbx; this
0x18000885a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000885f  movsxd  rax, [rsp+278h+var_254]
0x180008864  movsxd  rcx, [rsp+278h+var_258]
0x180008869  shl     rcx, 1Fh
0x18000886d  or      rcx, rax
0x180008870  mov     [r14], rcx
0x180008873  mov     rcx, rdi; hObject
0x180008876  call    cs:__imp_CloseHandle
0x18000887c  test    eax, eax
0x18000887e  jnz     short loc_18000889A
0x180008880  mov     rcx, [rsp+278h]; this
0x180008888  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000888f  mov     edx, 0A0Bh; void *
0x180008894  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000889a  xor     eax, eax
0x18000889c  jmp     loc_180008762
0x1800088a1  mov     rcx, [rsp+278h]; this
0x1800088a9  lea     r8, aWil; "wil"
0x1800088b0  mov     edx, 0DCh; void *
0x1800088b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800088ba  mov     rcx, rdi; hObject
0x1800088bd  mov     ebx, eax
0x1800088bf  call    cs:__imp_CloseHandle
0x1800088c5  test    eax, eax
0x1800088c7  jnz     short loc_1800088E3
0x1800088c9  mov     rcx, [rsp+278h]; this
0x1800088d1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800088d8  mov     edx, 0A0Bh; void *
0x1800088dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800088e3  mov     eax, ebx
0x1800088e5  jmp     loc_180008762
0x1800088ea  call    cs:__imp_GetLastError
0x1800088f0  cmp     eax, 2
0x1800088f3  jnz     short loc_180008906
0x1800088f5  lea     rcx, [rsp+278h+var_250]
0x1800088fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800088ff  xor     eax, eax
0x180008901  jmp     loc_18000876A
0x180008906  mov     rcx, [rsp+278h]; this
0x18000890e  lea     r8, aWil; "wil"
0x180008915  mov     edx, 0D0h; void *
0x18000891a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000891f  jmp     loc_18000876A
```
