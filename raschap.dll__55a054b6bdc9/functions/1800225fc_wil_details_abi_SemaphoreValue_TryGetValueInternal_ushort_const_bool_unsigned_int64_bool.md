# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800225fc`
- end: `0x180022798`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180022588`

## callees

- `0x180013b20`
- `0x18001bc7c`
- `0x18001f100`
- `0x1800205e4`
- `0x180021b5c`
- `0x180021b7c`
- `0x1800225fc`
- `0x180023444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022670`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022660`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800226f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022660`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800226f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x1800225fc  mov     [rsp-8+arg_8], rbx
0x180022601  mov     [rsp-8+arg_18], rdi
0x180022606  push    rbp
0x180022607  lea     rbp, [rsp-160h]
0x18002260f  sub     rsp, 260h
0x180022616  mov     rax, cs:__security_cookie
0x18002261d  xor     rax, rsp
0x180022620  mov     [rbp+160h+var_10], rax
0x180022627  mov     rdi, r8
0x18002262a  mov     qword ptr [r8], 0
0x180022631  mov     r8, rcx; pszSrc
0x180022634  mov     edx, 104h; cchDest
0x180022639  lea     rcx, [rsp+260h+pszDest]; pszDest
0x18002263e  call    StringCchCopyW
0x180022643  lea     r8, aP0; "_p0"
0x18002264a  lea     rcx, [rsp+260h+pszDest]; pszDest
0x18002264f  call    StringCchCatW
0x180022654  lea     r8, [rsp+260h+pszDest]; lpName
0x180022659  xor     edx, edx; bInheritHandle
0x18002265b  mov     ecx, 1F0003h; dwDesiredAccess
0x180022660  call    cs:__imp_OpenSemaphoreW
0x180022666  mov     [rsp+260h+var_230], rax
0x18002266b  test    rax, rax
0x18002266e  jnz     short loc_180022697
0x180022670  call    cs:__imp_GetLastError
0x180022676  cmp     eax, 2
0x180022679  jz      loc_180022766
0x18002267f  mov     rcx, [rbp+168h]; this
0x180022686  mov     edx, 0D0h; void *
0x18002268b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022690  mov     ebx, eax
0x180022692  jmp     loc_180022768
0x180022697  mov     [rsp+260h+var_23C], 0
0x18002269f  mov     [rsp+260h+var_240], 0; int
0x1800226a7  lea     rdx, [rsp+260h+var_23C]; int *
0x1800226ac  mov     rcx, rax; hHandle
0x1800226af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800226b4  mov     ebx, eax
0x1800226b6  test    eax, eax
0x1800226b8  jns     short loc_1800226D3
0x1800226ba  mov     rcx, [rbp+168h]; this
0x1800226c1  mov     r9d, eax; char *
0x1800226c4  mov     edx, 0D6h; void *
0x1800226c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226ce  jmp     loc_180022768
0x1800226d3  lea     r8, asc_18002B268; "h"
0x1800226da  lea     rcx, [rsp+260h+pszDest]; pszDest
0x1800226df  call    StringCchCatW
0x1800226e4  lea     r8, [rsp+260h+pszDest]; lpName
0x1800226e9  xor     edx, edx; bInheritHandle
0x1800226eb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800226f0  call    cs:__imp_OpenSemaphoreW
0x1800226f6  mov     [rsp+260h+var_238], rax
0x1800226fb  test    rax, rax
0x1800226fe  jnz     short loc_18002271F
0x180022700  mov     rcx, [rbp+168h]; this
0x180022707  mov     edx, 0DCh; void *
0x18002270c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022711  mov     ebx, eax
0x180022713  lea     rcx, [rsp+260h+var_238]
0x180022718  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002271d  jmp     short loc_180022768
0x18002271f  lea     rdx, [rsp+260h+var_240]; int *
0x180022724  mov     rcx, rax; hHandle
0x180022727  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002272c  mov     ebx, eax
0x18002272e  test    eax, eax
0x180022730  jns     short loc_180022748
0x180022732  mov     rcx, [rbp+168h]; this
0x180022739  mov     r9d, eax; char *
0x18002273c  mov     edx, 0DEh; void *
0x180022741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022746  jmp     short loc_180022713
0x180022748  lea     rcx, [rsp+260h+var_238]
0x18002274d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022752  movsxd  rcx, [rsp+260h+var_240]
0x180022757  shl     rcx, 1Fh
0x18002275b  movsxd  rax, [rsp+260h+var_23C]
0x180022760  or      rcx, rax
0x180022763  mov     [rdi], rcx
0x180022766  xor     ebx, ebx
0x180022768  lea     rcx, [rsp+260h+var_230]
0x18002276d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022772  mov     eax, ebx
0x180022774  mov     rcx, [rbp+160h+var_10]
0x18002277b  xor     rcx, rsp; StackCookie
0x18002277e  call    __security_check_cookie
0x180022783  lea     r11, [rsp+260h+var_s0]
0x18002278b  mov     rbx, [r11+18h]
0x18002278f  mov     rdi, [r11+28h]
0x180022793  mov     rsp, r11
0x180022796  pop     rbp
0x180022797  retn
```
