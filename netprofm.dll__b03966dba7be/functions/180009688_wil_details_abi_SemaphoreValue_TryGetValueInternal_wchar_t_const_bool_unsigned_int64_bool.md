# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009688`
- end: `0x180009973`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `747`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800093c8`
- `0x18000c550`

## callees

- `0x180009688`
- `0x18000997c`
- `0x180009af0`
- `0x18000c5d4`
- `0x18000c818`
- `0x18000c924`
- `0x1800120d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009794`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009868`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009794`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009912`

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
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const wchar_t *v27; // rcx
  __int64 v28; // rsi
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  int v33; // eax
  unsigned int v34; // esi
  void *v35; // rdx
  void *v36; // rdx
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h] BYREF
  int v40; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v41; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v42[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v41 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v38);
    goto LABEL_40;
  }
  v40 = 0;
  v39 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v40);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v39);
LABEL_40:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    return LastError;
  }
  v23 = 260;
  v24 = Name;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = (260 - v23) & -(__int64)(v23 != 0);
  if ( v23 )
  {
    v26 = &Name[v25];
    v27 = L"h";
    v28 = 260 - v25;
    if ( 260 != v25 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v27 )
          break;
        *v26++ = *v27++;
        --v5;
        --v28;
      }
      while ( v28 );
    }
    v29 = v26 - 1;
    if ( v28 )
      v29 = v26;
    *v29 = 0;
  }
  v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42[0] = v30;
  v32 = v30;
  if ( !v30 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v42);
    goto LABEL_40;
  }
  v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v39);
  v34 = v33;
  if ( v33 >= 0 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v42);
    *a3 = v40 | (unsigned __int64)((__int64)v39 << 31);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v33, v39);
    wil::details::CloseHandle(v32, v35);
    wil::details::CloseHandle(v20, v36);
    return v34;
  }
}

```

## disassembly

```asm
0x180009688  mov     [rsp-8+arg_0], rbx
0x18000968d  mov     [rsp-8+arg_8], rsi
0x180009692  push    rbp
0x180009693  push    rdi
0x180009694  push    r12
0x180009696  push    r14
0x180009698  push    r15
0x18000969a  lea     rbp, [rsp-160h]
0x1800096a2  sub     rsp, 260h
0x1800096a9  mov     rax, cs:__security_cookie
0x1800096b0  xor     rax, rsp
0x1800096b3  mov     [rbp+180h+var_30], rax
0x1800096ba  xor     r12d, r12d
0x1800096bd  lea     rax, [rsp+280h+Name]
0x1800096c2  mov     r14d, 7FFFFFFEh
0x1800096c8  mov     [r8], r12
0x1800096cb  mov     esi, 104h
0x1800096d0  mov     r9d, r14d
0x1800096d3  mov     edx, esi
0x1800096d5  mov     r15, r8
0x1800096d8  test    r9, r9
0x1800096db  jz      short loc_1800096FC
0x1800096dd  movzx   r8d, word ptr [rcx]
0x1800096e1  test    r8w, r8w
0x1800096e5  jz      short loc_1800096FC
0x1800096e7  mov     [rax], r8w
0x1800096eb  add     rcx, 2
0x1800096ef  add     rax, 2
0x1800096f3  dec     r9
0x1800096f6  sub     rdx, 1
0x1800096fa  jnz     short loc_1800096D8
0x1800096fc  test    rdx, rdx
0x1800096ff  lea     rcx, [rax-2]
0x180009703  mov     rdx, rsi
0x180009706  cmovnz  rcx, rax
0x18000970a  lea     rax, [rsp+280h+Name]
0x18000970f  mov     [rcx], r12w
0x180009713  cmp     [rax], r12w
0x180009717  jz      short loc_180009723
0x180009719  add     rax, 2
0x18000971d  sub     rdx, 1
0x180009721  jnz     short loc_180009713
0x180009723  mov     rcx, rsi
0x180009726  mov     rax, rdx
0x180009729  sub     rcx, rdx
0x18000972c  neg     rax
0x18000972f  sbb     r8, r8
0x180009732  and     r8, rcx
0x180009735  test    rdx, rdx
0x180009738  jz      short loc_180009788
0x18000973a  mov     rax, rsi
0x18000973d  lea     rdx, [rsp+280h+Name]
0x180009742  lea     r9, aP0; "_p0"
0x180009749  mov     rcx, r14
0x18000974c  lea     rdx, [rdx+r8*2]
0x180009750  sub     rax, r8
0x180009753  jz      short loc_180009779
0x180009755  test    rcx, rcx
0x180009758  jz      short loc_180009779
0x18000975a  movzx   r8d, word ptr [r9]
0x18000975e  test    r8w, r8w
0x180009762  jz      short loc_180009779
0x180009764  mov     [rdx], r8w
0x180009768  add     r9, 2
0x18000976c  add     rdx, 2
0x180009770  dec     rcx
0x180009773  sub     rax, 1
0x180009777  jnz     short loc_180009755
0x180009779  test    rax, rax
0x18000977c  lea     rcx, [rdx-2]
0x180009780  cmovnz  rcx, rdx
0x180009784  mov     [rcx], r12w
0x180009788  lea     r8, [rsp+280h+Name]; lpName
0x18000978d  xor     edx, edx; bInheritHandle
0x18000978f  mov     ecx, 1F0003h; dwDesiredAccess
0x180009794  call    cs:__imp_OpenSemaphoreW
0x18000979a  mov     [rsp+280h+var_258], rax
0x18000979f  mov     rdi, rax
0x1800097a2  test    rax, rax
0x1800097a5  jz      loc_180009912
0x1800097ab  lea     rdx, [rsp+280h+var_25C]; int *
0x1800097b0  mov     [rsp+280h+var_25C], r12d
0x1800097b5  mov     rcx, rax; hHandle
0x1800097b8  mov     [rsp+280h+var_260], r12d; int
0x1800097bd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800097c2  mov     ebx, eax
0x1800097c4  test    eax, eax
0x1800097c6  jns     short loc_1800097E8
0x1800097c8  mov     rcx, [rbp+188h]; this
0x1800097cf  lea     r8, aWil; "wil"
0x1800097d6  mov     r9d, eax; char *
0x1800097d9  mov     edx, 0D6h; void *
0x1800097de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097e3  jmp     loc_18000993C
0x1800097e8  mov     rdx, rsi
0x1800097eb  lea     rax, [rsp+280h+Name]
0x1800097f0  cmp     [rax], r12w
0x1800097f4  jz      short loc_180009800
0x1800097f6  add     rax, 2
0x1800097fa  sub     rdx, 1
0x1800097fe  jnz     short loc_1800097F0
0x180009800  mov     rcx, rsi
0x180009803  mov     rax, rdx
0x180009806  sub     rcx, rdx
0x180009809  neg     rax
0x18000980c  sbb     r8, r8
0x18000980f  and     r8, rcx
0x180009812  test    rdx, rdx
0x180009815  jz      short loc_18000985C
0x180009817  lea     rax, [rsp+280h+Name]
0x18000981c  lea     rax, [rax+r8*2]
0x180009820  lea     rcx, asc_180046650; "h"
0x180009827  sub     rsi, r8
0x18000982a  jz      short loc_18000984D
0x18000982c  test    r14, r14
0x18000982f  jz      short loc_18000984D
0x180009831  movzx   edx, word ptr [rcx]
0x180009834  test    dx, dx
0x180009837  jz      short loc_18000984D
0x180009839  mov     [rax], dx
0x18000983c  add     rcx, 2
0x180009840  add     rax, 2
0x180009844  dec     r14
0x180009847  sub     rsi, 1
0x18000984b  jnz     short loc_18000982C
0x18000984d  test    rsi, rsi
0x180009850  lea     rdx, [rax-2]
0x180009854  cmovnz  rdx, rax
0x180009858  mov     [rdx], r12w
0x18000985c  lea     r8, [rsp+280h+Name]; lpName
0x180009861  xor     edx, edx; bInheritHandle
0x180009863  mov     ecx, 1F0003h; dwDesiredAccess
0x180009868  call    cs:__imp_OpenSemaphoreW
0x18000986e  mov     [rsp+280h+var_250], rax
0x180009873  mov     rbx, rax
0x180009876  test    rax, rax
0x180009879  jz      short loc_1800098EC
0x18000987b  lea     rdx, [rsp+280h+var_260]; int *
0x180009880  mov     rcx, rax; hHandle
0x180009883  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009888  mov     esi, eax
0x18000988a  test    eax, eax
0x18000988c  jns     short loc_1800098C0
0x18000988e  mov     rcx, [rbp+188h]; this
0x180009895  lea     r8, aWil; "wil"
0x18000989c  mov     r9d, eax; char *
0x18000989f  mov     edx, 0DEh; void *
0x1800098a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098a9  mov     rcx, rbx; this
0x1800098ac  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800098b1  mov     rcx, rdi; this
0x1800098b4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800098b9  mov     eax, esi
0x1800098bb  jmp     loc_180009948
0x1800098c0  lea     rcx, [rsp+280h+var_250]
0x1800098c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098ca  movsxd  rax, [rsp+280h+var_25C]
0x1800098cf  movsxd  rcx, [rsp+280h+var_260]
0x1800098d4  shl     rcx, 1Fh
0x1800098d8  or      rcx, rax
0x1800098db  mov     [r15], rcx
0x1800098de  lea     rcx, [rsp+280h+var_258]
0x1800098e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098e8  xor     eax, eax
0x1800098ea  jmp     short loc_180009948
0x1800098ec  mov     rcx, [rbp+188h]; this
0x1800098f3  lea     r8, aWil; "wil"
0x1800098fa  mov     edx, 0DCh; void *
0x1800098ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009904  lea     rcx, [rsp+280h+var_250]
0x180009909  mov     ebx, eax
0x18000990b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009910  jmp     short loc_18000993C
0x180009912  call    cs:__imp_GetLastError
0x180009918  cmp     eax, 2
0x18000991b  jnz     short loc_180009922
0x18000991d  mov     ebx, r12d
0x180009920  jmp     short loc_18000993C
0x180009922  mov     rcx, [rbp+188h]; this
0x180009929  lea     r8, aWil; "wil"
0x180009930  mov     edx, 0D0h; void *
0x180009935  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000993a  mov     ebx, eax
0x18000993c  lea     rcx, [rsp+280h+var_258]
0x180009941  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009946  mov     eax, ebx
0x180009948  mov     rcx, [rbp+180h+var_30]
0x18000994f  xor     rcx, rsp; StackCookie
0x180009952  call    __security_check_cookie
0x180009957  lea     r11, [rsp+280h+var_20]
0x18000995f  mov     rbx, [r11+30h]
0x180009963  mov     rsi, [r11+38h]
0x180009967  mov     rsp, r11
0x18000996a  pop     r15
0x18000996c  pop     r14
0x18000996e  pop     r12
0x180009970  pop     rdi
0x180009971  pop     rbp
0x180009972  retn
```
