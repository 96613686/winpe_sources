# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008138`
- end: `0x1800082f0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006858`

## callees

- `0x180003270`
- `0x180003290`
- `0x180005020`
- `0x180006704`
- `0x18000738c`
- `0x180007ebc`
- `0x180007f38`
- `0x180008138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000819c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000823a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000819c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000823a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180008138  mov     [rsp-8+arg_8], rbx
0x18000813d  mov     [rsp-8+arg_18], rdi
0x180008142  push    rbp
0x180008143  lea     rbp, [rsp-160h]
0x18000814b  sub     rsp, 260h
0x180008152  mov     rax, cs:__security_cookie
0x180008159  xor     rax, rsp
0x18000815c  mov     [rbp+160h+var_10], rax
0x180008163  mov     rdi, r8
0x180008166  mov     qword ptr [r8], 0
0x18000816d  mov     r8, rcx; unsigned __int16 *
0x180008170  mov     edx, 104h; unsigned __int64
0x180008175  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000817a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000817f  lea     r8, aP0; "_p0"
0x180008186  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000818b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008190  lea     r8, [rsp+260h+Name]; lpName
0x180008195  xor     edx, edx; bInheritHandle
0x180008197  mov     ecx, 1F0003h; dwDesiredAccess
0x18000819c  call    cs:__imp_OpenSemaphoreW
0x1800081a2  mov     [rsp+260h+var_230], rax
0x1800081a7  test    rax, rax
0x1800081aa  jnz     short loc_1800081DA
0x1800081ac  call    cs:__imp_GetLastError
0x1800081b2  cmp     eax, 2
0x1800081b5  jz      loc_1800082BE
0x1800081bb  mov     rcx, [rbp+168h]; this
0x1800081c2  lea     r8, aWil; "wil"
0x1800081c9  mov     edx, 0D0h; void *
0x1800081ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800081d3  mov     ebx, eax
0x1800081d5  jmp     loc_1800082C0
0x1800081da  lea     rdx, [rsp+260h+var_23C]; int *
0x1800081df  mov     [rsp+260h+var_23C], 0
0x1800081e7  mov     rcx, rax; hHandle
0x1800081ea  mov     [rsp+260h+var_240], 0; int
0x1800081f2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800081f7  mov     ebx, eax
0x1800081f9  test    eax, eax
0x1800081fb  jns     short loc_18000821D
0x1800081fd  mov     rcx, [rbp+168h]; this
0x180008204  lea     r8, aWil; "wil"
0x18000820b  mov     r9d, eax; char *
0x18000820e  mov     edx, 0D6h; void *
0x180008213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008218  jmp     loc_1800082C0
0x18000821d  lea     r8, asc_18000D3C8; "h"
0x180008224  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008229  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000822e  lea     r8, [rsp+260h+Name]; lpName
0x180008233  xor     edx, edx; bInheritHandle
0x180008235  mov     ecx, 1F0003h; dwDesiredAccess
0x18000823a  call    cs:__imp_OpenSemaphoreW
0x180008240  mov     [rsp+260h+var_238], rax
0x180008245  test    rax, rax
0x180008248  jnz     short loc_180008270
0x18000824a  mov     rcx, [rbp+168h]; this
0x180008251  lea     r8, aWil; "wil"
0x180008258  mov     edx, 0DCh; void *
0x18000825d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008262  mov     ebx, eax
0x180008264  lea     rcx, [rsp+260h+var_238]
0x180008269  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000826e  jmp     short loc_1800082C0
0x180008270  lea     rdx, [rsp+260h+var_240]; int *
0x180008275  mov     rcx, rax; hHandle
0x180008278  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000827d  mov     ebx, eax
0x18000827f  test    eax, eax
0x180008281  jns     short loc_1800082A0
0x180008283  mov     rcx, [rbp+168h]; this
0x18000828a  lea     r8, aWil; "wil"
0x180008291  mov     r9d, eax; char *
0x180008294  mov     edx, 0DEh; void *
0x180008299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000829e  jmp     short loc_180008264
0x1800082a0  lea     rcx, [rsp+260h+var_238]
0x1800082a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800082aa  movsxd  rcx, [rsp+260h+var_240]
0x1800082af  movsxd  rax, [rsp+260h+var_23C]
0x1800082b4  shl     rcx, 1Fh
0x1800082b8  or      rcx, rax
0x1800082bb  mov     [rdi], rcx
0x1800082be  xor     ebx, ebx
0x1800082c0  lea     rcx, [rsp+260h+var_230]
0x1800082c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800082ca  mov     eax, ebx
0x1800082cc  mov     rcx, [rbp+160h+var_10]
0x1800082d3  xor     rcx, rsp; StackCookie
0x1800082d6  call    __security_check_cookie
0x1800082db  lea     r11, [rsp+260h+var_s0]
0x1800082e3  mov     rbx, [r11+18h]
0x1800082e7  mov     rdi, [r11+28h]
0x1800082eb  mov     rsp, r11
0x1800082ee  pop     rbp
0x1800082ef  retn
```
