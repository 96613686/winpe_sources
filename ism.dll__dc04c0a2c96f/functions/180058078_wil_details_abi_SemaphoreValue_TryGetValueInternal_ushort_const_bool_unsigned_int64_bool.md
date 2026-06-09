# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180058078`
- end: `0x18005838a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `786`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800576c4`
- `0x18008e97c`

## callees

- `0x180058078`
- `0x180058390`
- `0x18008daac`
- `0x18008ead4`
- `0x180099dd4`
- `0x180099df0`
- `0x1800f0990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058203`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058129`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800581a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180058129`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800581a0`

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
  wil::details *v15; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  HANDLE v21; // rax
  const char *v22; // r9
  void *v23; // rdx
  const char *v25; // r9
  const unsigned __int16 *v26; // r9
  __int64 v27; // rcx
  WCHAR *v28; // rdx
  __int64 v29; // rax
  WCHAR *v30; // rcx
  WCHAR *v31; // rax
  const unsigned __int16 *v32; // rcx
  __int64 v33; // rsi
  WCHAR *v34; // rdx
  int v35; // eax
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v38; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v39[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v26 = L"_p0";
    v27 = 2147483646;
    v28 = &Name[v13];
    v29 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v27 )
          break;
        if ( !*v26 )
          break;
        *v28++ = *v26++;
        --v27;
        --v29;
      }
      while ( v29 );
    }
    v30 = v28 - 1;
    if ( v29 )
      v30 = v28;
    *v30 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v39[0] = v14;
  v15 = v14;
  if ( v14 )
  {
    v37 = 0;
    v36 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v37);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v36);
LABEL_44:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v39);
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
      v31 = &Name[v20];
      v32 = L"h";
      v33 = 260 - v20;
      if ( 260 != v20 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v32 )
            break;
          *v31++ = *v32++;
          --v5;
          --v33;
        }
        while ( v33 );
      }
      v34 = v31 - 1;
      if ( v33 )
        v34 = v31;
      *v34 = 0;
    }
    v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v38 = v21;
    if ( !v21 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
      wil::details::CloseHandle(v15, v23);
      return LastError;
    }
    v35 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v36);
    LastError = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v35,
        v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v38);
      goto LABEL_44;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v38);
    *a3 = v37 | (unsigned __int64)((__int64)v36 << 31);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v39);
    return 0;
  }
  else
  {
    if ( GetLastError() == 2 )
    {
      LastError = 0;
      goto LABEL_44;
    }
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
  }
}

```

## disassembly

```asm
0x180058078  mov     [rsp-8+arg_0], rbx
0x18005807d  mov     [rsp-8+arg_8], rsi
0x180058082  push    rbp
0x180058083  push    rdi
0x180058084  push    r12
0x180058086  push    r14
0x180058088  push    r15
0x18005808a  lea     rbp, [rsp-160h]
0x180058092  sub     rsp, 260h
0x180058099  mov     rax, cs:__security_cookie
0x1800580a0  xor     rax, rsp
0x1800580a3  mov     [rbp+180h+var_30], rax
0x1800580aa  xor     r12d, r12d
0x1800580ad  lea     rax, [rsp+280h+Name]
0x1800580b2  mov     r14d, 7FFFFFFEh
0x1800580b8  mov     [r8], r12
0x1800580bb  mov     esi, 104h
0x1800580c0  mov     r9d, r14d
0x1800580c3  mov     edx, esi
0x1800580c5  mov     r15, r8
0x1800580c8  test    r9, r9
0x1800580cb  jz      short loc_1800580DB
0x1800580cd  movzx   r8d, word ptr [rcx]
0x1800580d1  test    r8w, r8w
0x1800580d5  jnz     loc_1800582A0
0x1800580db  test    rdx, rdx
0x1800580de  lea     rcx, [rax-2]
0x1800580e2  mov     rdx, rsi
0x1800580e5  cmovnz  rcx, rax
0x1800580e9  lea     rax, [rsp+280h+Name]
0x1800580ee  mov     [rcx], r12w
0x1800580f2  cmp     [rax], r12w
0x1800580f6  jz      short loc_180058102
0x1800580f8  add     rax, 2
0x1800580fc  sub     rdx, 1
0x180058100  jnz     short loc_1800580F2
0x180058102  mov     rcx, rsi
0x180058105  mov     rax, rdx
0x180058108  sub     rcx, rdx
0x18005810b  neg     rax
0x18005810e  sbb     r8, r8
0x180058111  and     r8, rcx
0x180058114  test    rdx, rdx
0x180058117  jnz     loc_18005822C
0x18005811d  lea     r8, [rsp+280h+Name]; lpName
0x180058122  xor     edx, edx; bInheritHandle
0x180058124  mov     ecx, 1F0003h; dwDesiredAccess
0x180058129  call    cs:__imp_OpenSemaphoreW
0x18005812f  mov     [rsp+280h+var_250], rax
0x180058134  mov     rbx, rax
0x180058137  test    rax, rax
0x18005813a  jz      loc_180058203
0x180058140  lea     rdx, [rsp+280h+var_25C]; int *
0x180058145  mov     [rsp+280h+var_25C], r12d
0x18005814a  mov     rcx, rax; hHandle
0x18005814d  mov     [rsp+280h+var_260], r12d; int
0x180058152  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180058157  mov     edi, eax
0x180058159  test    eax, eax
0x18005815b  js      loc_1800582F2
0x180058161  mov     rdx, rsi
0x180058164  lea     rax, [rsp+280h+Name]
0x180058169  cmp     [rax], r12w
0x18005816d  jz      short loc_180058179
0x18005816f  add     rax, 2
0x180058173  sub     rdx, 1
0x180058177  jnz     short loc_180058169
0x180058179  mov     rcx, rsi
0x18005817c  mov     rax, rdx
0x18005817f  sub     rcx, rdx
0x180058182  neg     rax
0x180058185  sbb     r8, r8
0x180058188  and     r8, rcx
0x18005818b  test    rdx, rdx
0x18005818e  jnz     loc_18005826A
0x180058194  lea     r8, [rsp+280h+Name]; lpName
0x180058199  xor     edx, edx; bInheritHandle
0x18005819b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800581a0  call    cs:__imp_OpenSemaphoreW
0x1800581a6  mov     [rsp+280h+var_258], rax
0x1800581ab  test    rax, rax
0x1800581ae  jnz     loc_18005830F
0x1800581b4  mov     rcx, [rbp+188h]; this
0x1800581bb  lea     r8, aWil; "wil"
0x1800581c2  mov     edx, 0DCh; void *
0x1800581c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800581cc  mov     rcx, rbx; this
0x1800581cf  mov     edi, eax
0x1800581d1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800581d6  mov     eax, edi
0x1800581d8  mov     rcx, [rbp+180h+var_30]
0x1800581df  xor     rcx, rsp; StackCookie
0x1800581e2  call    __security_check_cookie
0x1800581e7  lea     r11, [rsp+280h+var_20]
0x1800581ef  mov     rbx, [r11+30h]
0x1800581f3  mov     rsi, [r11+38h]
0x1800581f7  mov     rsp, r11
0x1800581fa  pop     r15
0x1800581fc  pop     r14
0x1800581fe  pop     r12
0x180058200  pop     rdi
0x180058201  pop     rbp
0x180058202  retn
0x180058203  call    cs:__imp_GetLastError
0x180058209  cmp     eax, 2
0x18005820c  jz      loc_180058378
0x180058212  mov     rcx, [rbp+188h]; this
0x180058219  lea     r8, aWil; "wil"
0x180058220  mov     edx, 0D0h; void *
0x180058225  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005822a  jmp     short loc_1800581D8
0x18005822c  mov     rax, rsi
0x18005822f  lea     rdx, [rsp+280h+Name]
0x180058234  lea     r9, aP0; "_p0"
0x18005823b  mov     rcx, r14
0x18005823e  lea     rdx, [rdx+r8*2]
0x180058242  sub     rax, r8
0x180058245  jz      short loc_180058256
0x180058247  test    rcx, rcx
0x18005824a  jz      short loc_180058256
0x18005824c  movzx   r8d, word ptr [r9]
0x180058250  test    r8w, r8w
0x180058254  jnz     short loc_1800582BE
0x180058256  test    rax, rax
0x180058259  lea     rcx, [rdx-2]
0x18005825d  cmovnz  rcx, rdx
0x180058261  mov     [rcx], r12w
0x180058265  jmp     loc_18005811D
0x18005826a  lea     rax, [rsp+280h+Name]
0x18005826f  lea     rax, [rax+r8*2]
0x180058273  lea     rcx, asc_1801F0300; "h"
0x18005827a  sub     rsi, r8
0x18005827d  jz      short loc_18005828C
0x18005827f  test    r14, r14
0x180058282  jz      short loc_18005828C
0x180058284  movzx   edx, word ptr [rcx]
0x180058287  test    dx, dx
0x18005828a  jnz     short loc_1800582DC
0x18005828c  test    rsi, rsi
0x18005828f  lea     rdx, [rax-2]
0x180058293  cmovnz  rdx, rax
0x180058297  mov     [rdx], r12w
0x18005829b  jmp     loc_180058194
0x1800582a0  mov     [rax], r8w
0x1800582a4  add     rcx, 2
0x1800582a8  add     rax, 2
0x1800582ac  dec     r9
0x1800582af  sub     rdx, 1
0x1800582b3  jnz     loc_1800580C8
0x1800582b9  jmp     loc_1800580DB
0x1800582be  mov     [rdx], r8w
0x1800582c2  add     r9, 2
0x1800582c6  add     rdx, 2
0x1800582ca  dec     rcx
0x1800582cd  sub     rax, 1
0x1800582d1  jnz     loc_180058247
0x1800582d7  jmp     loc_180058256
0x1800582dc  mov     [rax], dx
0x1800582df  add     rcx, 2
0x1800582e3  add     rax, 2
0x1800582e7  dec     r14
0x1800582ea  sub     rsi, 1
0x1800582ee  jnz     short loc_18005827F
0x1800582f0  jmp     short loc_18005828C
0x1800582f2  mov     rcx, [rbp+188h]; this
0x1800582f9  lea     r8, aWil; "wil"
0x180058300  mov     r9d, eax; char *
0x180058303  mov     edx, 0D6h; void *
0x180058308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005830d  jmp     short loc_18005837B
0x18005830f  lea     rdx, [rsp+280h+var_260]; int *
0x180058314  mov     rcx, rax; hHandle
0x180058317  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005831c  mov     edi, eax
0x18005831e  test    eax, eax
0x180058320  jns     short loc_180058349
0x180058322  mov     rcx, [rbp+188h]; this
0x180058329  lea     r8, aWil; "wil"
0x180058330  mov     r9d, eax; char *
0x180058333  mov     edx, 0DEh; void *
0x180058338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005833d  lea     rcx, [rsp+280h+var_258]
0x180058342  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058347  jmp     short loc_18005837B
0x180058349  lea     rcx, [rsp+280h+var_258]
0x18005834e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058353  movsxd  rax, [rsp+280h+var_25C]
0x180058358  movsxd  rcx, [rsp+280h+var_260]
0x18005835d  shl     rcx, 1Fh
0x180058361  or      rcx, rax
0x180058364  mov     [r15], rcx
0x180058367  lea     rcx, [rsp+280h+var_250]
0x18005836c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058371  xor     eax, eax
0x180058373  jmp     loc_1800581D8
0x180058378  mov     edi, r12d
0x18005837b  lea     rcx, [rsp+280h+var_250]
0x180058380  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058385  jmp     loc_1800581D6
```
