# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009324`
- end: `0x180009631`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `781`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180007a94`
- `0x180007fa8`

## callees

- `0x180007b88`
- `0x180009324`
- `0x180009638`
- `0x180009790`
- `0x1800269d4`
- `0x1800273e8`
- `0x18002e5f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800093e6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800094ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800093e6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800094ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  WCHAR *v8; // rax
  WCHAR v9; // r8
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  wil::details *v14; // rax
  wil::details *v15; // rdi
  const char *v16; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v20; // rdx
  WCHAR *v21; // rax
  __int64 v22; // r8
  wil::details *v23; // rax
  const char *v24; // r9
  wil::details *v25; // rbx
  __int64 v26; // rcx
  const unsigned __int16 *v27; // r9
  __int64 v28; // rax
  WCHAR *v29; // rdx
  unsigned __int16 v30; // r8
  WCHAR *v31; // rcx
  int v32; // eax
  void *v33; // rdx
  unsigned int v34; // esi
  void *v35; // rdx
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rsi
  WCHAR *v38; // rax
  unsigned __int16 v39; // dx
  WCHAR *v40; // rdx
  void *v41; // rdx
  void *v42; // rdx
  int v43; // [rsp+20h] [rbp-E0h] BYREF
  int v44; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v45; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v46; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  v5 = 2147483646;
  v6 = 2147483646;
  v7 = 260;
  v8 = Name;
  do
  {
    if ( !v6 )
      break;
    v9 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v8++ = v9;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  v11 = 260;
  v12 = Name;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v26 = 2147483646;
    v27 = L"_p0";
    v28 = 260 - v13;
    v29 = &Name[v13];
    if ( v13 != 260 )
    {
      do
      {
        if ( !v26 )
          break;
        v30 = *v27;
        if ( !*v27 )
          break;
        ++v27;
        *v29++ = v30;
        --v26;
        --v28;
      }
      while ( v28 );
    }
    v31 = v29 - 1;
    if ( v28 )
      v31 = v29;
    *v31 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v15 = v14;
  v46 = v14;
  if ( !v14 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v16);
    LastError = 0;
    goto LABEL_21;
  }
  v44 = 0;
  v43 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v44);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v43);
    goto LABEL_21;
  }
  v20 = 260;
  v21 = Name;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v20;
  }
  while ( v20 );
  v22 = (260 - v20) & -(__int64)(v20 != 0);
  if ( v20 )
  {
    v36 = L"h";
    v37 = 260 - v22;
    v38 = &Name[v22];
    if ( 260 != v22 )
    {
      do
      {
        if ( !v5 )
          break;
        v39 = *v36;
        if ( !*v36 )
          break;
        ++v36;
        *v38++ = v39;
        --v5;
        --v37;
      }
      while ( v37 );
    }
    v40 = v38 - 1;
    if ( v37 )
      v40 = v38;
    *v40 = 0;
  }
  v23 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v23;
  v45 = v23;
  if ( !v23 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v24);
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v45);
LABEL_21:
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v46);
    return LastError;
  }
  v32 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v23, &v43);
  v34 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v32, v43);
    wil::details::CloseHandle(v25, v41);
    wil::details::CloseHandle(v15, v42);
    return v34;
  }
  else
  {
    wil::details::CloseHandle(v25, v33);
    *a3 = v44 | (unsigned __int64)((__int64)v43 << 31);
    wil::details::CloseHandle(v15, v35);
    return 0;
  }
}

```

## disassembly

```asm
0x180009324  mov     [rsp-8+arg_0], rbx
0x180009329  mov     [rsp-8+arg_8], rsi
0x18000932e  push    rbp
0x18000932f  push    rdi
0x180009330  push    r12
0x180009332  push    r14
0x180009334  push    r15
0x180009336  lea     rbp, [rsp-160h]
0x18000933e  sub     rsp, 260h
0x180009345  mov     rax, cs:__security_cookie
0x18000934c  xor     rax, rsp
0x18000934f  mov     [rbp+180h+var_30], rax
0x180009356  mov     r15, r8
0x180009359  xor     r12d, r12d
0x18000935c  mov     [r8], r12
0x18000935f  mov     r14d, 7FFFFFFEh
0x180009365  mov     r9d, r14d
0x180009368  mov     esi, 104h
0x18000936d  mov     edx, esi
0x18000936f  lea     rax, [rsp+280h+Name]
0x180009374  test    r9, r9
0x180009377  jz      short loc_180009398
0x180009379  movzx   r8d, word ptr [rcx]
0x18000937d  test    r8w, r8w
0x180009381  jz      short loc_180009398
0x180009383  add     rcx, 2
0x180009387  mov     [rax], r8w
0x18000938b  add     rax, 2
0x18000938f  dec     r9
0x180009392  sub     rdx, 1
0x180009396  jnz     short loc_180009374
0x180009398  lea     rcx, [rax-2]
0x18000939c  test    rdx, rdx
0x18000939f  cmovnz  rcx, rax
0x1800093a3  mov     [rcx], r12w
0x1800093a7  mov     rdx, rsi
0x1800093aa  lea     rax, [rsp+280h+Name]
0x1800093af  cmp     [rax], r12w
0x1800093b3  jz      short loc_1800093BF
0x1800093b5  add     rax, 2
0x1800093b9  sub     rdx, 1
0x1800093bd  jnz     short loc_1800093AF
0x1800093bf  mov     rax, rdx
0x1800093c2  mov     rcx, rsi
0x1800093c5  sub     rcx, rdx
0x1800093c8  neg     rax
0x1800093cb  sbb     r8, r8
0x1800093ce  and     r8, rcx
0x1800093d1  test    rdx, rdx
0x1800093d4  jnz     loc_1800094F9
0x1800093da  lea     r8, [rsp+280h+Name]; lpName
0x1800093df  xor     edx, edx; bInheritHandle
0x1800093e1  mov     ecx, 1F0003h; dwDesiredAccess
0x1800093e6  call    cs:__imp_OpenSemaphoreW
0x1800093ec  mov     rdi, rax
0x1800093ef  mov     [rsp+280h+var_250], rax
0x1800093f4  test    rax, rax
0x1800093f7  jnz     short loc_18000944C
0x1800093f9  call    cs:__imp_GetLastError
0x1800093ff  cmp     eax, 2
0x180009402  jz      loc_180009628
0x180009408  mov     rcx, [rbp+188h]; this
0x18000940f  lea     r8, aWil; "wil"
0x180009416  mov     edx, 0D0h; void *
0x18000941b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009420  nop
0x180009421  mov     rcx, [rbp+180h+var_30]
0x180009428  xor     rcx, rsp; StackCookie
0x18000942b  call    __security_check_cookie
0x180009430  lea     r11, [rsp+280h+var_20]
0x180009438  mov     rbx, [r11+30h]
0x18000943c  mov     rsi, [r11+38h]
0x180009440  mov     rsp, r11
0x180009443  pop     r15
0x180009445  pop     r14
0x180009447  pop     r12
0x180009449  pop     rdi
0x18000944a  pop     rbp
0x18000944b  retn
0x18000944c  mov     [rsp+280h+var_25C], r12d
0x180009451  mov     [rsp+280h+var_260], r12d; int
0x180009456  lea     rdx, [rsp+280h+var_25C]; int *
0x18000945b  mov     rcx, rdi; hHandle
0x18000945e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009463  mov     ebx, eax
0x180009465  test    eax, eax
0x180009467  js      loc_180009608
0x18000946d  mov     rdx, rsi
0x180009470  lea     rax, [rsp+280h+Name]
0x180009475  cmp     [rax], r12w
0x180009479  jz      short loc_180009485
0x18000947b  add     rax, 2
0x18000947f  sub     rdx, 1
0x180009483  jnz     short loc_180009475
0x180009485  mov     rax, rdx
0x180009488  mov     rcx, rsi
0x18000948b  sub     rcx, rdx
0x18000948e  neg     rax
0x180009491  sbb     r8, r8
0x180009494  and     r8, rcx
0x180009497  test    rdx, rdx
0x18000949a  jnz     loc_18000958A
0x1800094a0  lea     r8, [rsp+280h+Name]; lpName
0x1800094a5  xor     edx, edx; bInheritHandle
0x1800094a7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800094ac  call    cs:__imp_OpenSemaphoreW
0x1800094b2  mov     rbx, rax
0x1800094b5  mov     [rsp+280h+var_258], rax
0x1800094ba  test    rax, rax
0x1800094bd  jnz     loc_18000954C
0x1800094c3  mov     rcx, [rbp+188h]; this
0x1800094ca  lea     r8, aWil; "wil"
0x1800094d1  mov     edx, 0DCh; void *
0x1800094d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800094db  mov     ebx, eax
0x1800094dd  lea     rcx, [rsp+280h+var_258]
0x1800094e2  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x1800094e7  nop
0x1800094e8  lea     rcx, [rsp+280h+var_250]
0x1800094ed  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x1800094f2  mov     eax, ebx
0x1800094f4  jmp     loc_180009421
0x1800094f9  mov     rcx, r14
0x1800094fc  lea     r9, aP0; "_p0"
0x180009503  mov     rax, rsi
0x180009506  sub     rax, r8
0x180009509  lea     rdx, [rsp+280h+Name]
0x18000950e  lea     rdx, [rdx+r8*2]
0x180009512  jz      short loc_180009538
0x180009514  test    rcx, rcx
0x180009517  jz      short loc_180009538
0x180009519  movzx   r8d, word ptr [r9]
0x18000951d  test    r8w, r8w
0x180009521  jz      short loc_180009538
0x180009523  add     r9, 2
0x180009527  mov     [rdx], r8w
0x18000952b  add     rdx, 2
0x18000952f  dec     rcx
0x180009532  sub     rax, 1
0x180009536  jnz     short loc_180009514
0x180009538  lea     rcx, [rdx-2]
0x18000953c  test    rax, rax
0x18000953f  cmovnz  rcx, rdx
0x180009543  mov     [rcx], r12w
0x180009547  jmp     loc_1800093DA
0x18000954c  lea     rdx, [rsp+280h+var_260]; int *
0x180009551  mov     rcx, rbx; hHandle
0x180009554  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009559  mov     esi, eax
0x18000955b  test    eax, eax
0x18000955d  js      short loc_1800095D4
0x18000955f  mov     rcx, rbx; this
0x180009562  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180009567  movsxd  rcx, [rsp+280h+var_260]
0x18000956c  shl     rcx, 1Fh
0x180009570  movsxd  rax, [rsp+280h+var_25C]
0x180009575  or      rcx, rax
0x180009578  mov     [r15], rcx
0x18000957b  mov     rcx, rdi; this
0x18000957e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180009583  xor     eax, eax
0x180009585  jmp     loc_180009421
0x18000958a  lea     rcx, asc_180088488; "h"
0x180009591  sub     rsi, r8
0x180009594  lea     rax, [rsp+280h+Name]
0x180009599  lea     rax, [rax+r8*2]
0x18000959d  jz      short loc_1800095C0
0x18000959f  test    r14, r14
0x1800095a2  jz      short loc_1800095C0
0x1800095a4  movzx   edx, word ptr [rcx]
0x1800095a7  test    dx, dx
0x1800095aa  jz      short loc_1800095C0
0x1800095ac  add     rcx, 2
0x1800095b0  mov     [rax], dx
0x1800095b3  add     rax, 2
0x1800095b7  dec     r14
0x1800095ba  sub     rsi, 1
0x1800095be  jnz     short loc_18000959F
0x1800095c0  lea     rdx, [rax-2]
0x1800095c4  test    rsi, rsi
0x1800095c7  cmovnz  rdx, rax
0x1800095cb  mov     [rdx], r12w
0x1800095cf  jmp     loc_1800094A0
0x1800095d4  mov     rcx, [rbp+188h]; this
0x1800095db  mov     r9d, esi; char *
0x1800095de  lea     r8, aWil; "wil"
0x1800095e5  mov     edx, 0DEh; void *
0x1800095ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095ef  nop
0x1800095f0  mov     rcx, rbx; this
0x1800095f3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800095f8  nop
0x1800095f9  mov     rcx, rdi; this
0x1800095fc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180009601  mov     eax, esi
0x180009603  jmp     loc_180009421
0x180009608  mov     rcx, [rbp+188h]; this
0x18000960f  mov     r9d, eax; char *
0x180009612  lea     r8, aWil; "wil"
0x180009619  mov     edx, 0D6h; void *
0x18000961e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009623  jmp     loc_1800094E8
0x180009628  mov     ebx, r12d
0x18000962b  jmp     loc_1800094E8
```
