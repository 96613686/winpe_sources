# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800082bc`
- end: `0x1800084e8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007654`
- `0x18000870c`

## callees

- `0x1800082bc`
- `0x18001ce34`
- `0x18003109c`
- `0x180042854`
- `0x1802004e0`
- `0x18020fca0`
- `0x180228490`
- `0x18022afec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000838d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800083fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000838d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800083fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848e`

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
  bool v8; // zf
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // r8
  HANDLE v13; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v16; // rax
  const char *v17; // r9
  int v18; // eax
  const char *v20; // r9
  size_t v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
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
  v8 = v5 == 0;
  v9 = v4 - 1;
  v10 = 260;
  if ( !v8 )
    v9 = v4;
  v11 = Name;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( v10 )
  {
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    StringCopyWorkerW(&Name[v12], 260 - v12, (size_t *)v12, L"_p0", v21);
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v25[0] = v13;
  if ( v13 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v24 = v16;
      if ( v16 )
      {
        v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v22);
        LastError = v18;
        if ( v18 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
          *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          v21);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v21);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v20);
}

```

## disassembly

```asm
0x1800082bc  mov     [rsp-8+arg_0], rbx
0x1800082c1  mov     [rsp-8+arg_8], rsi
0x1800082c6  push    rbp
0x1800082c7  push    rdi
0x1800082c8  push    r14
0x1800082ca  lea     rbp, [rsp-170h]
0x1800082d2  sub     rsp, 270h
0x1800082d9  mov     rax, cs:__security_cookie
0x1800082e0  xor     rax, rsp
0x1800082e3  mov     [rbp+180h+var_20], rax
0x1800082ea  xor     esi, esi
0x1800082ec  lea     rax, [rsp+280h+Name]
0x1800082f1  mov     r14d, 104h
0x1800082f7  mov     [r8], rsi
0x1800082fa  mov     edx, r14d
0x1800082fd  mov     rdi, r8
0x180008300  mov     r9d, 7FFFFFFEh
0x180008306  test    r9, r9
0x180008309  jz      short loc_18000832A
0x18000830b  movzx   r8d, word ptr [rcx]
0x18000830f  test    r8w, r8w
0x180008313  jz      short loc_18000832A
0x180008315  mov     [rax], r8w
0x180008319  add     rcx, 2
0x18000831d  add     rax, 2
0x180008321  dec     r9
0x180008324  sub     rdx, 1
0x180008328  jnz     short loc_180008306
0x18000832a  test    rdx, rdx
0x18000832d  lea     rcx, [rax-2]
0x180008331  mov     rdx, r14
0x180008334  cmovnz  rcx, rax
0x180008338  lea     rax, [rsp+280h+Name]
0x18000833d  mov     [rcx], si
0x180008340  cmp     [rax], si
0x180008343  jz      short loc_18000834F
0x180008345  add     rax, 2
0x180008349  sub     rdx, 1
0x18000834d  jnz     short loc_180008340
0x18000834f  mov     rcx, r14
0x180008352  mov     rax, rdx
0x180008355  sub     rcx, rdx
0x180008358  neg     rax
0x18000835b  sbb     r8, r8
0x18000835e  and     r8, rcx; pcchNewDestLength
0x180008361  test    rdx, rdx
0x180008364  jz      short loc_180008381
0x180008366  mov     rdx, r14
0x180008369  lea     rcx, [rsp+280h+Name]
0x18000836e  sub     rdx, r8; cchDest
0x180008371  lea     rcx, [rcx+r8*2]; pszDest
0x180008375  lea     r9, aP0; "_p0"
0x18000837c  call    StringCopyWorkerW
0x180008381  lea     r8, [rsp+280h+Name]; lpName
0x180008386  xor     edx, edx; bInheritHandle
0x180008388  mov     ecx, 1F0003h; dwDesiredAccess
0x18000838d  call    cs:__imp_OpenSemaphoreW
0x180008393  mov     [rsp+280h+var_240], rax
0x180008398  test    rax, rax
0x18000839b  jz      loc_18000848E
0x1800083a1  lea     rdx, [rsp+280h+var_24C]; int *
0x1800083a6  mov     [rsp+280h+var_24C], esi
0x1800083aa  mov     rcx, rax; hHandle
0x1800083ad  mov     [rsp+280h+var_250], esi
0x1800083b1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800083b6  mov     ebx, eax
0x1800083b8  test    eax, eax
0x1800083ba  jns     short loc_1800083DC
0x1800083bc  mov     rcx, [rbp+188h]; this
0x1800083c3  lea     r8, aWil; "wil"
0x1800083ca  mov     r9d, eax; char *
0x1800083cd  mov     edx, 0D6h; void *
0x1800083d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083d7  jmp     loc_18000849B
0x1800083dc  lea     r8, asc_1802D3550; "h"
0x1800083e3  mov     rdx, r14; unsigned __int64
0x1800083e6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800083eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800083f0  lea     r8, [rsp+280h+Name]; lpName
0x1800083f5  xor     edx, edx; bInheritHandle
0x1800083f7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800083fc  call    cs:__imp_OpenSemaphoreW
0x180008402  mov     [rsp+280h+var_248], rax
0x180008407  test    rax, rax
0x18000840a  jz      short loc_180008468
0x18000840c  lea     rdx, [rsp+280h+var_250]; int *
0x180008411  mov     rcx, rax; hHandle
0x180008414  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008419  mov     ebx, eax
0x18000841b  test    eax, eax
0x18000841d  jns     short loc_18000843C
0x18000841f  mov     rcx, [rbp+188h]; this
0x180008426  lea     r8, aWil; "wil"
0x18000842d  mov     r9d, eax; char *
0x180008430  mov     edx, 0DEh; void *
0x180008435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000843a  jmp     short loc_180008482
0x18000843c  lea     rcx, [rsp+280h+var_248]
0x180008441  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008446  movsxd  rax, [rsp+280h+var_24C]
0x18000844b  movsxd  rcx, [rsp+280h+var_250]
0x180008450  shl     rcx, 1Fh
0x180008454  or      rcx, rax
0x180008457  mov     [rdi], rcx
0x18000845a  lea     rcx, [rsp+280h+var_240]
0x18000845f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008464  xor     eax, eax
0x180008466  jmp     short loc_1800084C1
0x180008468  mov     rcx, [rbp+188h]; this
0x18000846f  lea     r8, aWil; "wil"
0x180008476  mov     edx, 0DCh; void *
0x18000847b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008480  mov     ebx, eax
0x180008482  lea     rcx, [rsp+280h+var_248]
0x180008487  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000848c  jmp     short loc_18000849B
0x18000848e  call    cs:__imp_GetLastError
0x180008494  cmp     eax, 2
0x180008497  jnz     short loc_1800084A9
0x180008499  mov     ebx, esi
0x18000849b  lea     rcx, [rsp+280h+var_240]
0x1800084a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800084a5  mov     eax, ebx
0x1800084a7  jmp     short loc_1800084C1
0x1800084a9  mov     rcx, [rbp+188h]; this
0x1800084b0  lea     r8, aWil; "wil"
0x1800084b7  mov     edx, 0D0h; void *
0x1800084bc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800084c1  mov     rcx, [rbp+180h+var_20]
0x1800084c8  xor     rcx, rsp; StackCookie
0x1800084cb  call    __security_check_cookie
0x1800084d0  lea     r11, [rsp+280h+var_10]
0x1800084d8  mov     rbx, [r11+20h]
0x1800084dc  mov     rsi, [r11+28h]
0x1800084e0  mov     rsp, r11
0x1800084e3  pop     r14
0x1800084e5  pop     rdi
0x1800084e6  pop     rbp
0x1800084e7  retn
```
