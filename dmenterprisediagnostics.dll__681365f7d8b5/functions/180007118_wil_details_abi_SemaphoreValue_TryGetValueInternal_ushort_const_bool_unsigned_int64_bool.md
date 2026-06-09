# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007118`
- end: `0x1800072e9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003d2c`

## callees

- `0x180001800`
- `0x180003bb8`
- `0x180004d90`
- `0x180005bf4`
- `0x180005c14`
- `0x180006be0`
- `0x180006c6c`
- `0x180007118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007181`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000722d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007181`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000722d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007197`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x180007118  mov     [rsp-8+arg_8], rbx
0x18000711d  push    rbp
0x18000711e  push    rdi
0x18000711f  push    r14
0x180007121  lea     rbp, [rsp-160h]
0x180007129  sub     rsp, 260h
0x180007130  mov     rax, cs:__security_cookie
0x180007137  xor     rax, rsp
0x18000713a  mov     [rbp+170h+var_20], rax
0x180007141  mov     rdi, r8
0x180007144  mov     qword ptr [r8], 0
0x18000714b  mov     r8, rcx; unsigned __int16 *
0x18000714e  mov     r14d, 104h
0x180007154  mov     edx, r14d; unsigned __int64
0x180007157  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000715c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007161  lea     r8, aP0; "_p0"
0x180007168  mov     edx, r14d; unsigned __int64
0x18000716b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007170  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007175  lea     r8, [rsp+270h+Name]; lpName
0x18000717a  xor     edx, edx; bInheritHandle
0x18000717c  mov     ecx, 1F0003h; dwDesiredAccess
0x180007181  call    cs:__imp_OpenSemaphoreW
0x180007188  nop     dword ptr [rax+rax+00h]
0x18000718d  mov     [rsp+270h+var_240], rax
0x180007192  test    rax, rax
0x180007195  jnz     short loc_1800071CA
0x180007197  call    cs:__imp_GetLastError
0x18000719e  nop     dword ptr [rax+rax+00h]
0x1800071a3  cmp     eax, 2
0x1800071a6  jz      loc_1800072B7
0x1800071ac  mov     rcx, [rbp+178h]; this
0x1800071b3  lea     r8, aWil; "wil"
0x1800071ba  lea     edx, [r14-34h]; void *
0x1800071be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800071c3  mov     ebx, eax
0x1800071c5  jmp     loc_1800072B9
0x1800071ca  lea     rdx, [rsp+270h+var_24C]; int *
0x1800071cf  mov     [rsp+270h+var_24C], 0
0x1800071d7  mov     rcx, rax; hHandle
0x1800071da  mov     [rsp+270h+var_250], 0; int
0x1800071e2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800071e7  mov     ebx, eax
0x1800071e9  test    eax, eax
0x1800071eb  jns     short loc_18000720D
0x1800071ed  mov     rcx, [rbp+178h]; this
0x1800071f4  lea     r8, aWil; "wil"
0x1800071fb  mov     r9d, eax; char *
0x1800071fe  mov     edx, 0D6h; void *
0x180007203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007208  jmp     loc_1800072B9
0x18000720d  lea     r8, asc_18002A6A0; "h"
0x180007214  mov     rdx, r14; unsigned __int64
0x180007217  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000721c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007221  lea     r8, [rsp+270h+Name]; lpName
0x180007226  xor     edx, edx; bInheritHandle
0x180007228  mov     ecx, 1F0003h; dwDesiredAccess
0x18000722d  call    cs:__imp_OpenSemaphoreW
0x180007234  nop     dword ptr [rax+rax+00h]
0x180007239  mov     [rsp+270h+var_248], rax
0x18000723e  test    rax, rax
0x180007241  jnz     short loc_180007269
0x180007243  mov     rcx, [rbp+178h]; this
0x18000724a  lea     r8, aWil; "wil"
0x180007251  mov     edx, 0DCh; void *
0x180007256  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000725b  mov     ebx, eax
0x18000725d  lea     rcx, [rsp+270h+var_248]
0x180007262  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007267  jmp     short loc_1800072B9
0x180007269  lea     rdx, [rsp+270h+var_250]; int *
0x18000726e  mov     rcx, rax; hHandle
0x180007271  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007276  mov     ebx, eax
0x180007278  test    eax, eax
0x18000727a  jns     short loc_180007299
0x18000727c  mov     rcx, [rbp+178h]; this
0x180007283  lea     r8, aWil; "wil"
0x18000728a  mov     r9d, eax; char *
0x18000728d  mov     edx, 0DEh; void *
0x180007292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007297  jmp     short loc_18000725D
0x180007299  lea     rcx, [rsp+270h+var_248]
0x18000729e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800072a3  movsxd  rcx, [rsp+270h+var_250]
0x1800072a8  movsxd  rax, [rsp+270h+var_24C]
0x1800072ad  shl     rcx, 1Fh
0x1800072b1  or      rcx, rax
0x1800072b4  mov     [rdi], rcx
0x1800072b7  xor     ebx, ebx
0x1800072b9  lea     rcx, [rsp+270h+var_240]
0x1800072be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800072c3  mov     eax, ebx
0x1800072c5  mov     rcx, [rbp+170h+var_20]
0x1800072cc  xor     rcx, rsp; StackCookie
0x1800072cf  call    __security_check_cookie
0x1800072d4  mov     rbx, [rsp+270h+arg_8]
0x1800072dc  add     rsp, 260h
0x1800072e3  pop     r14
0x1800072e5  pop     rdi
0x1800072e6  pop     rbp
0x1800072e7  retn
```
