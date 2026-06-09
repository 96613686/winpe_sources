# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005d14`
- end: `0x180006016`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `770`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005788`
- `0x180006aa0`

## callees

- `0x180004d20`
- `0x180005cf8`
- `0x180005d14`
- `0x18000601c`
- `0x180006180`
- `0x1800061ac`
- `0x18000c6e4`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005dd6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005e4d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005dd6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eda`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  wil::details *v14; // rax
  wil::details *v15; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  void *v21; // rbx
  unsigned int v22; // r8d
  const char *v23; // r9
  int v24; // eax
  void *v25; // rdx
  int v26; // esi
  unsigned int v28; // r8d
  const char *v29; // r9
  const unsigned __int16 *v30; // r9
  __int64 v31; // rcx
  WCHAR *v32; // rdx
  __int64 v33; // rax
  WCHAR *v34; // rcx
  WCHAR *v35; // rax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rsi
  WCHAR *v38; // rdx
  int v39; // [rsp+20h] [rbp-E0h] BYREF
  int v40; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v41; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v42; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
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
    v30 = L"_p0";
    v31 = 2147483646;
    v32 = &Name[v13];
    v33 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v31 )
          break;
        if ( !*v30 )
          break;
        *v32++ = *v30++;
        --v31;
        --v33;
      }
      while ( v33 );
    }
    v34 = v32 - 1;
    if ( v33 )
      v34 = v32;
    *v34 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v14;
  v15 = v14;
  if ( !v14 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v28, v29);
    LastError = 0;
    goto LABEL_44;
  }
  v40 = 0;
  v39 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v40);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v39);
LABEL_44:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
  v18 = 260;
  v19 = Name;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v20 = (260 - v18) & -(__int64)(v18 != 0);
  if ( v18 )
  {
    v35 = &Name[v20];
    v36 = L"h";
    v37 = 260 - v20;
    if ( 260 != v20 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v36 )
          break;
        *v35++ = *v36++;
        --v5;
        --v37;
      }
      while ( v37 );
    }
    v38 = v35 - 1;
    if ( v37 )
      v38 = v35;
    *v38 = 0;
  }
  v41 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v41;
  if ( (unsigned __int8)____8V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__YA_NAEBV__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___0___T_Z(&v41) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v22, v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    goto LABEL_44;
  }
  v24 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v39);
  v26 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v24, v39);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    LastError = v26;
    goto LABEL_44;
  }
  if ( v21 )
    wil::details::CloseHandle((wil::details *)v21, v25);
  *a3 = v40 | (unsigned __int64)((__int64)v39 << 31);
  wil::details::CloseHandle(v15, v25);
  return 0;
}

```

## disassembly

```asm
0x180005d14  mov     [rsp-8+arg_0], rbx
0x180005d19  mov     [rsp-8+arg_8], rsi
0x180005d1e  push    rbp
0x180005d1f  push    rdi
0x180005d20  push    r12
0x180005d22  push    r14
0x180005d24  push    r15
0x180005d26  lea     rbp, [rsp-160h]
0x180005d2e  sub     rsp, 260h
0x180005d35  mov     rax, cs:__security_cookie
0x180005d3c  xor     rax, rsp
0x180005d3f  mov     [rbp+180h+var_30], rax
0x180005d46  xor     r12d, r12d
0x180005d49  lea     rax, [rsp+280h+Name]
0x180005d4e  mov     r14d, 7FFFFFFEh
0x180005d54  mov     [r8], r12
0x180005d57  mov     esi, 104h
0x180005d5c  mov     r9d, r14d
0x180005d5f  mov     edx, esi
0x180005d61  mov     r15, r8
0x180005d64  test    r9, r9
0x180005d67  jz      short loc_180005D88
0x180005d69  movzx   r8d, word ptr [rcx]
0x180005d6d  test    r8w, r8w
0x180005d71  jz      short loc_180005D88
0x180005d73  mov     [rax], r8w
0x180005d77  add     rcx, 2
0x180005d7b  add     rax, 2
0x180005d7f  dec     r9
0x180005d82  sub     rdx, 1
0x180005d86  jnz     short loc_180005D64
0x180005d88  test    rdx, rdx
0x180005d8b  lea     rcx, [rax-2]
0x180005d8f  mov     rdx, rsi
0x180005d92  cmovnz  rcx, rax
0x180005d96  lea     rax, [rsp+280h+Name]
0x180005d9b  mov     [rcx], r12w
0x180005d9f  cmp     [rax], r12w
0x180005da3  jz      short loc_180005DAF
0x180005da5  add     rax, 2
0x180005da9  sub     rdx, 1
0x180005dad  jnz     short loc_180005D9F
0x180005daf  mov     rcx, rsi
0x180005db2  mov     rax, rdx
0x180005db5  sub     rcx, rdx
0x180005db8  neg     rax
0x180005dbb  sbb     r8, r8
0x180005dbe  and     r8, rcx
0x180005dc1  test    rdx, rdx
0x180005dc4  jnz     loc_180005EFC
0x180005dca  lea     r8, [rsp+280h+Name]; lpName
0x180005dcf  xor     edx, edx; bInheritHandle
0x180005dd1  mov     ecx, 1F0003h; dwDesiredAccess
0x180005dd6  call    cs:__imp_OpenSemaphoreW
0x180005ddc  mov     [rsp+280h+var_250], rax
0x180005de1  mov     rdi, rax
0x180005de4  test    rax, rax
0x180005de7  jz      loc_180005EDA
0x180005ded  lea     rdx, [rsp+280h+var_25C]; int *
0x180005df2  mov     [rsp+280h+var_25C], r12d
0x180005df7  mov     rcx, rax; hHandle
0x180005dfa  mov     [rsp+280h+var_260], r12d; int
0x180005dff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005e04  mov     ebx, eax
0x180005e06  test    eax, eax
0x180005e08  js      loc_180005F9D
0x180005e0e  mov     rdx, rsi
0x180005e11  lea     rax, [rsp+280h+Name]
0x180005e16  cmp     [rax], r12w
0x180005e1a  jz      short loc_180005E26
0x180005e1c  add     rax, 2
0x180005e20  sub     rdx, 1
0x180005e24  jnz     short loc_180005E16
0x180005e26  mov     rcx, rsi
0x180005e29  mov     rax, rdx
0x180005e2c  sub     rcx, rdx
0x180005e2f  neg     rax
0x180005e32  sbb     r8, r8
0x180005e35  and     r8, rcx
0x180005e38  test    rdx, rdx
0x180005e3b  jnz     loc_180005F2B
0x180005e41  lea     r8, [rsp+280h+Name]; lpName
0x180005e46  xor     edx, edx; bInheritHandle
0x180005e48  mov     ecx, 1F0003h; dwDesiredAccess
0x180005e4d  call    cs:__imp_OpenSemaphoreW
0x180005e53  lea     rcx, [rsp+280h+var_258]
0x180005e58  mov     [rsp+280h+var_258], rax
0x180005e5d  mov     rbx, rax
0x180005e60  call    ??$?8V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$T@Z
0x180005e65  test    al, al
0x180005e67  jnz     loc_180005FBA
0x180005e6d  lea     rdx, [rsp+280h+var_260]; int *
0x180005e72  mov     rcx, rbx; hHandle
0x180005e75  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005e7a  mov     esi, eax
0x180005e7c  test    eax, eax
0x180005e7e  js      loc_180005FD9
0x180005e84  test    rbx, rbx
0x180005e87  jz      short loc_180005E91
0x180005e89  mov     rcx, rbx; this
0x180005e8c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005e91  movsxd  rax, [rsp+280h+var_25C]
0x180005e96  movsxd  rcx, [rsp+280h+var_260]
0x180005e9b  shl     rcx, 1Fh
0x180005e9f  or      rcx, rax
0x180005ea2  mov     [r15], rcx
0x180005ea5  mov     rcx, rdi; this
0x180005ea8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005ead  xor     eax, eax
0x180005eaf  mov     rcx, [rbp+180h+var_30]
0x180005eb6  xor     rcx, rsp; StackCookie
0x180005eb9  call    __security_check_cookie
0x180005ebe  lea     r11, [rsp+280h+var_20]
0x180005ec6  mov     rbx, [r11+30h]
0x180005eca  mov     rsi, [r11+38h]
0x180005ece  mov     rsp, r11
0x180005ed1  pop     r15
0x180005ed3  pop     r14
0x180005ed5  pop     r12
0x180005ed7  pop     rdi
0x180005ed8  pop     rbp
0x180005ed9  retn
0x180005eda  call    cs:__imp_GetLastError
0x180005ee0  cmp     eax, 2
0x180005ee3  jz      loc_180006002
0x180005ee9  mov     rcx, [rbp+188h]; this
0x180005ef0  mov     edx, 0D0h; void *
0x180005ef5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005efa  jmp     short loc_180005EAF
0x180005efc  mov     rax, rsi
0x180005eff  lea     rdx, [rsp+280h+Name]
0x180005f04  lea     r9, aP0; "_p0"
0x180005f0b  mov     rcx, r14
0x180005f0e  lea     rdx, [rdx+r8*2]
0x180005f12  sub     rax, r8
0x180005f15  jnz     short loc_180005F54
0x180005f17  test    rax, rax
0x180005f1a  lea     rcx, [rdx-2]
0x180005f1e  cmovnz  rcx, rdx
0x180005f22  mov     [rcx], r12w
0x180005f26  jmp     loc_180005DCA
0x180005f2b  lea     rax, [rsp+280h+Name]
0x180005f30  lea     rax, [rax+r8*2]
0x180005f34  lea     rcx, asc_180019390; "h"
0x180005f3b  sub     rsi, r8
0x180005f3e  jnz     short loc_180005F7A
0x180005f40  test    rsi, rsi
0x180005f43  lea     rdx, [rax-2]
0x180005f47  cmovnz  rdx, rax
0x180005f4b  mov     [rdx], r12w
0x180005f4f  jmp     loc_180005E41
0x180005f54  test    rcx, rcx
0x180005f57  jz      short loc_180005F17
0x180005f59  movzx   r8d, word ptr [r9]
0x180005f5d  test    r8w, r8w
0x180005f61  jz      short loc_180005F17
0x180005f63  mov     [rdx], r8w
0x180005f67  add     r9, 2
0x180005f6b  add     rdx, 2
0x180005f6f  dec     rcx
0x180005f72  sub     rax, 1
0x180005f76  jz      short loc_180005F17
0x180005f78  jmp     short loc_180005F54
0x180005f7a  test    r14, r14
0x180005f7d  jz      short loc_180005F40
0x180005f7f  movzx   edx, word ptr [rcx]
0x180005f82  test    dx, dx
0x180005f85  jz      short loc_180005F40
0x180005f87  mov     [rax], dx
0x180005f8a  add     rcx, 2
0x180005f8e  add     rax, 2
0x180005f92  dec     r14
0x180005f95  sub     rsi, 1
0x180005f99  jz      short loc_180005F40
0x180005f9b  jmp     short loc_180005F7A
0x180005f9d  mov     rcx, [rbp+188h]; this
0x180005fa4  lea     r8, aWil; "wil"
0x180005fab  mov     r9d, eax; char *
0x180005fae  mov     edx, 0D6h; void *
0x180005fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fb8  jmp     short loc_180006005
0x180005fba  mov     rcx, [rbp+188h]; this
0x180005fc1  mov     edx, 0DCh; void *
0x180005fc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005fcb  lea     rcx, [rsp+280h+var_258]
0x180005fd0  mov     ebx, eax
0x180005fd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005fd7  jmp     short loc_180006005
0x180005fd9  mov     rcx, [rbp+188h]; this
0x180005fe0  lea     r8, aWil; "wil"
0x180005fe7  mov     r9d, esi; char *
0x180005fea  mov     edx, 0DEh; void *
0x180005fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ff4  lea     rcx, [rsp+280h+var_258]
0x180005ff9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005ffe  mov     ebx, esi
0x180006000  jmp     short loc_180006005
0x180006002  mov     ebx, r12d
0x180006005  lea     rcx, [rsp+280h+var_250]
0x18000600a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000600f  mov     eax, ebx
0x180006011  jmp     loc_180005EAF
```
