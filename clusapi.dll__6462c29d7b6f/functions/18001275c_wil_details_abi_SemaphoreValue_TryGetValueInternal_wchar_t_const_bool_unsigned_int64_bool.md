# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001275c`
- end: `0x1800128fe`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800126e8`

## callees

- `0x180002f50`
- `0x18000ede0`
- `0x1800102c4`
- `0x180011c2c`
- `0x180011c4c`
- `0x18001230c`
- `0x18001236c`
- `0x18001275c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800127c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012857`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800127c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127d5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18001275c  mov     [rsp-8+arg_8], rbx
0x180012761  push    rbp
0x180012762  push    rdi
0x180012763  push    r14
0x180012765  lea     rbp, [rsp-160h]
0x18001276d  sub     rsp, 260h
0x180012774  mov     rax, cs:__security_cookie
0x18001277b  xor     rax, rsp
0x18001277e  mov     [rbp+170h+var_20], rax
0x180012785  mov     rdi, r8
0x180012788  mov     qword ptr [r8], 0
0x18001278f  mov     r8, rcx; wchar_t *
0x180012792  mov     r14d, 104h
0x180012798  mov     edx, r14d; unsigned __int64
0x18001279b  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800127a0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800127a5  lea     r8, aP0; "_p0"
0x1800127ac  mov     edx, r14d; unsigned __int64
0x1800127af  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800127b4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800127b9  lea     r8, [rsp+270h+Name]; lpName
0x1800127be  xor     edx, edx; bInheritHandle
0x1800127c0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800127c5  call    cs:__imp_OpenSemaphoreW
0x1800127cb  mov     [rsp+270h+var_240], rax
0x1800127d0  test    rax, rax
0x1800127d3  jnz     short loc_1800127FB
0x1800127d5  call    cs:__imp_GetLastError
0x1800127db  cmp     eax, 2
0x1800127de  jz      loc_1800128CD
0x1800127e4  mov     rcx, [rbp+178h]; this
0x1800127eb  lea     edx, [r14-34h]; void *
0x1800127ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800127f4  mov     ebx, eax
0x1800127f6  jmp     loc_1800128CF
0x1800127fb  lea     rdx, [rsp+270h+var_24C]; int *
0x180012800  mov     [rsp+270h+var_24C], 0
0x180012808  mov     rcx, rax; hHandle
0x18001280b  mov     [rsp+270h+var_250], 0; int
0x180012813  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012818  mov     ebx, eax
0x18001281a  test    eax, eax
0x18001281c  jns     short loc_180012837
0x18001281e  mov     rcx, [rbp+178h]; this
0x180012825  mov     r9d, eax; char *
0x180012828  mov     edx, 0D6h; void *
0x18001282d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012832  jmp     loc_1800128CF
0x180012837  lea     r8, asc_1800C47A0; "h"
0x18001283e  mov     rdx, r14; unsigned __int64
0x180012841  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180012846  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001284b  lea     r8, [rsp+270h+Name]; lpName
0x180012850  xor     edx, edx; bInheritHandle
0x180012852  mov     ecx, 1F0003h; dwDesiredAccess
0x180012857  call    cs:__imp_OpenSemaphoreW
0x18001285d  mov     [rsp+270h+var_248], rax
0x180012862  test    rax, rax
0x180012865  jnz     short loc_180012886
0x180012867  mov     rcx, [rbp+178h]; this
0x18001286e  mov     edx, 0DCh; void *
0x180012873  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012878  mov     ebx, eax
0x18001287a  lea     rcx, [rsp+270h+var_248]
0x18001287f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012884  jmp     short loc_1800128CF
0x180012886  lea     rdx, [rsp+270h+var_250]; int *
0x18001288b  mov     rcx, rax; hHandle
0x18001288e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012893  mov     ebx, eax
0x180012895  test    eax, eax
0x180012897  jns     short loc_1800128AF
0x180012899  mov     rcx, [rbp+178h]; this
0x1800128a0  mov     r9d, eax; char *
0x1800128a3  mov     edx, 0DEh; void *
0x1800128a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128ad  jmp     short loc_18001287A
0x1800128af  lea     rcx, [rsp+270h+var_248]
0x1800128b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800128b9  movsxd  rcx, [rsp+270h+var_250]
0x1800128be  movsxd  rax, [rsp+270h+var_24C]
0x1800128c3  shl     rcx, 1Fh
0x1800128c7  or      rcx, rax
0x1800128ca  mov     [rdi], rcx
0x1800128cd  xor     ebx, ebx
0x1800128cf  lea     rcx, [rsp+270h+var_240]
0x1800128d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800128d9  mov     eax, ebx
0x1800128db  mov     rcx, [rbp+170h+var_20]
0x1800128e2  xor     rcx, rsp; StackCookie
0x1800128e5  call    __security_check_cookie
0x1800128ea  mov     rbx, [rsp+270h+arg_8]
0x1800128f2  add     rsp, 260h
0x1800128f9  pop     r14
0x1800128fb  pop     rdi
0x1800128fc  pop     rbp
0x1800128fd  retn
```
