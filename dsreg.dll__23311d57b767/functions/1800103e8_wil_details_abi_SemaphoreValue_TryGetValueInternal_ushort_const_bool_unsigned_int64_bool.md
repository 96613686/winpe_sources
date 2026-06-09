# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800103e8`
- end: `0x180010638`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `592`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180010140`
- `0x1800300a8`

## callees

- `0x180010340`
- `0x1800103e8`
- `0x1800107f0`
- `0x18001db30`
- `0x18003012c`
- `0x180030150`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800104eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001055a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800104eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001055a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rax
  WCHAR *v17; // rcx
  HANDLE v18; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v21; // rax
  unsigned int v22; // r8d
  const char *v23; // r9
  int v24; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h] BYREF
  int v29; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v30; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
    v15 = &Name[v13];
    v16 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v5;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v31[0] = v18;
  if ( v18 )
  {
    v29 = 0;
    v28 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v29);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v30 = v21;
      if ( v21 )
      {
        v24 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v28);
        LastError = v24;
        if ( v24 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
          *a3 = v29 | (unsigned __int64)((__int64)v28 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v31);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v24,
          v28);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v22, v23);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v28);
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_29:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v31);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v26, v27);
}

```

## disassembly

```asm
0x1800103e8  mov     [rsp-8+arg_0], rbx
0x1800103ed  mov     [rsp-8+arg_8], rsi
0x1800103f2  push    rbp
0x1800103f3  push    rdi
0x1800103f4  push    r15
0x1800103f6  lea     rbp, [rsp-160h]
0x1800103fe  sub     rsp, 260h
0x180010405  mov     rax, cs:__security_cookie
0x18001040c  xor     rax, rsp
0x18001040f  mov     [rbp+170h+var_20], rax
0x180010416  xor     esi, esi
0x180010418  lea     rax, [rsp+270h+Name]
0x18001041d  mov     r10d, 7FFFFFFEh
0x180010423  mov     [r8], rsi
0x180010426  mov     r15d, 104h
0x18001042c  mov     r9d, r10d
0x18001042f  mov     edx, r15d
0x180010432  mov     rdi, r8
0x180010435  test    r9, r9
0x180010438  jz      short loc_180010459
0x18001043a  movzx   r8d, word ptr [rcx]
0x18001043e  test    r8w, r8w
0x180010442  jz      short loc_180010459
0x180010444  mov     [rax], r8w
0x180010448  add     rcx, 2
0x18001044c  add     rax, 2
0x180010450  dec     r9
0x180010453  sub     rdx, 1
0x180010457  jnz     short loc_180010435
0x180010459  test    rdx, rdx
0x18001045c  lea     rcx, [rax-2]
0x180010460  mov     rdx, r15
0x180010463  cmovnz  rcx, rax
0x180010467  lea     rax, [rsp+270h+Name]
0x18001046c  mov     [rcx], si
0x18001046f  cmp     [rax], si
0x180010472  jz      short loc_18001047E
0x180010474  add     rax, 2
0x180010478  sub     rdx, 1
0x18001047c  jnz     short loc_18001046F
0x18001047e  mov     rcx, r15
0x180010481  mov     rax, rdx
0x180010484  sub     rcx, rdx
0x180010487  neg     rax
0x18001048a  sbb     r8, r8
0x18001048d  and     r8, rcx
0x180010490  test    rdx, rdx
0x180010493  jz      short loc_1800104DF
0x180010495  mov     rax, r15
0x180010498  lea     rdx, [rsp+270h+Name]
0x18001049d  lea     rcx, aP0; "_p0"
0x1800104a4  lea     rdx, [rdx+r8*2]
0x1800104a8  sub     rax, r8
0x1800104ab  jz      short loc_1800104D1
0x1800104ad  test    r10, r10
0x1800104b0  jz      short loc_1800104D1
0x1800104b2  movzx   r8d, word ptr [rcx]
0x1800104b6  test    r8w, r8w
0x1800104ba  jz      short loc_1800104D1
0x1800104bc  mov     [rdx], r8w
0x1800104c0  add     rcx, 2
0x1800104c4  add     rdx, 2
0x1800104c8  dec     r10
0x1800104cb  sub     rax, 1
0x1800104cf  jnz     short loc_1800104AD
0x1800104d1  test    rax, rax
0x1800104d4  lea     rcx, [rdx-2]
0x1800104d8  cmovnz  rcx, rdx
0x1800104dc  mov     [rcx], si
0x1800104df  lea     r8, [rsp+270h+Name]; lpName
0x1800104e4  xor     edx, edx; bInheritHandle
0x1800104e6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800104eb  call    cs:__imp_OpenSemaphoreW
0x1800104f1  mov     [rsp+270h+var_240], rax
0x1800104f6  test    rax, rax
0x1800104f9  jz      loc_1800105E5
0x1800104ff  lea     rdx, [rsp+270h+var_24C]; int *
0x180010504  mov     [rsp+270h+var_24C], esi
0x180010508  mov     rcx, rax; hHandle
0x18001050b  mov     [rsp+270h+var_250], esi; int
0x18001050f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010514  mov     ebx, eax
0x180010516  test    eax, eax
0x180010518  jns     short loc_18001053A
0x18001051a  mov     rcx, [rbp+178h]; this
0x180010521  lea     r8, aWil; "wil"
0x180010528  mov     r9d, eax; char *
0x18001052b  mov     edx, 0D6h; void *
0x180010530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010535  jmp     loc_1800105F2
0x18001053a  lea     r8, asc_1800C7190; "h"
0x180010541  mov     rdx, r15; unsigned __int64
0x180010544  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010549  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001054e  lea     r8, [rsp+270h+Name]; lpName
0x180010553  xor     edx, edx; bInheritHandle
0x180010555  mov     ecx, 1F0003h; dwDesiredAccess
0x18001055a  call    cs:__imp_OpenSemaphoreW
0x180010560  mov     [rsp+270h+var_248], rax
0x180010565  test    rax, rax
0x180010568  jz      short loc_1800105C6
0x18001056a  lea     rdx, [rsp+270h+var_250]; int *
0x18001056f  mov     rcx, rax; hHandle
0x180010572  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010577  mov     ebx, eax
0x180010579  test    eax, eax
0x18001057b  jns     short loc_18001059A
0x18001057d  mov     rcx, [rbp+178h]; this
0x180010584  lea     r8, aWil; "wil"
0x18001058b  mov     r9d, eax; char *
0x18001058e  mov     edx, 0DEh; void *
0x180010593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010598  jmp     short loc_1800105D9
0x18001059a  lea     rcx, [rsp+270h+var_248]
0x18001059f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800105a4  movsxd  rax, [rsp+270h+var_24C]
0x1800105a9  movsxd  rcx, [rsp+270h+var_250]
0x1800105ae  shl     rcx, 1Fh
0x1800105b2  or      rcx, rax
0x1800105b5  mov     [rdi], rcx
0x1800105b8  lea     rcx, [rsp+270h+var_240]
0x1800105bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800105c2  xor     eax, eax
0x1800105c4  jmp     short loc_180010611
0x1800105c6  mov     rcx, [rbp+178h]; this
0x1800105cd  mov     edx, 0DCh; void *
0x1800105d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800105d7  mov     ebx, eax
0x1800105d9  lea     rcx, [rsp+270h+var_248]
0x1800105de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800105e3  jmp     short loc_1800105F2
0x1800105e5  call    cs:__imp_GetLastError
0x1800105eb  cmp     eax, 2
0x1800105ee  jnz     short loc_180010600
0x1800105f0  mov     ebx, esi
0x1800105f2  lea     rcx, [rsp+270h+var_240]
0x1800105f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800105fc  mov     eax, ebx
0x1800105fe  jmp     short loc_180010611
0x180010600  mov     rcx, [rbp+178h]; this
0x180010607  mov     edx, 0D0h; void *
0x18001060c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010611  mov     rcx, [rbp+170h+var_20]
0x180010618  xor     rcx, rsp; StackCookie
0x18001061b  call    __security_check_cookie
0x180010620  lea     r11, [rsp+270h+var_10]
0x180010628  mov     rbx, [r11+20h]
0x18001062c  mov     rsi, [r11+28h]
0x180010630  mov     rsp, r11
0x180010633  pop     r15
0x180010635  pop     rdi
0x180010636  pop     rbp
0x180010637  retn
```
