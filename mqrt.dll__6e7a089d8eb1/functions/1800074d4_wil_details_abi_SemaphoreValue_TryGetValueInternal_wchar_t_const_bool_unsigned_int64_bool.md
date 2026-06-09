# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800074d4`
- end: `0x180007676`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007460`

## callees

- `0x180003900`
- `0x180004d48`
- `0x18000683c`
- `0x18000685c`
- `0x180006f5c`
- `0x180006fdc`
- `0x1800074d4`
- `0x180023ca0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000754d`
- `KERNEL32!GetLastError` at `0x18000754d`
- `KERNEL32!OpenSemaphoreW` at `0x18000753d`
- `KERNEL32!OpenSemaphoreW` at `0x1800075cf`
- `KERNEL32!OpenSemaphoreW` at `0x18000753d`
- `KERNEL32!OpenSemaphoreW` at `0x1800075cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800074d4  mov     [rsp-8+arg_8], rbx
0x1800074d9  push    rbp
0x1800074da  push    rdi
0x1800074db  push    r14
0x1800074dd  lea     rbp, [rsp-160h]
0x1800074e5  sub     rsp, 260h
0x1800074ec  mov     rax, cs:__security_cookie
0x1800074f3  xor     rax, rsp
0x1800074f6  mov     [rbp+170h+var_20], rax
0x1800074fd  mov     rdi, r8
0x180007500  mov     qword ptr [r8], 0
0x180007507  mov     r8, rcx; wchar_t *
0x18000750a  mov     r14d, 104h
0x180007510  mov     edx, r14d; unsigned __int64
0x180007513  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180007518  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000751d  lea     r8, aP0; "_p0"
0x180007524  mov     edx, r14d; unsigned __int64
0x180007527  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000752c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007531  lea     r8, [rsp+270h+Name]; lpName
0x180007536  xor     edx, edx; bInheritHandle
0x180007538  mov     ecx, 1F0003h; dwDesiredAccess
0x18000753d  call    cs:__imp_OpenSemaphoreW
0x180007543  mov     [rsp+270h+var_240], rax
0x180007548  test    rax, rax
0x18000754b  jnz     short loc_180007573
0x18000754d  call    cs:__imp_GetLastError
0x180007553  cmp     eax, 2
0x180007556  jz      loc_180007645
0x18000755c  mov     rcx, [rbp+178h]; this
0x180007563  lea     edx, [r14-34h]; void *
0x180007567  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000756c  mov     ebx, eax
0x18000756e  jmp     loc_180007647
0x180007573  mov     [rsp+270h+var_24C], 0
0x18000757b  mov     [rsp+270h+var_250], 0; int
0x180007583  lea     rdx, [rsp+270h+var_24C]; int *
0x180007588  mov     rcx, rax; hHandle
0x18000758b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007590  mov     ebx, eax
0x180007592  test    eax, eax
0x180007594  jns     short loc_1800075AF
0x180007596  mov     rcx, [rbp+178h]; this
0x18000759d  mov     r9d, eax; char *
0x1800075a0  mov     edx, 0D6h; void *
0x1800075a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075aa  jmp     loc_180007647
0x1800075af  lea     r8, asc_180031690; "h"
0x1800075b6  mov     rdx, r14; unsigned __int64
0x1800075b9  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800075be  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800075c3  lea     r8, [rsp+270h+Name]; lpName
0x1800075c8  xor     edx, edx; bInheritHandle
0x1800075ca  mov     ecx, 1F0003h; dwDesiredAccess
0x1800075cf  call    cs:__imp_OpenSemaphoreW
0x1800075d5  mov     [rsp+270h+var_248], rax
0x1800075da  test    rax, rax
0x1800075dd  jnz     short loc_1800075FE
0x1800075df  mov     rcx, [rbp+178h]; this
0x1800075e6  mov     edx, 0DCh; void *
0x1800075eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800075f0  mov     ebx, eax
0x1800075f2  lea     rcx, [rsp+270h+var_248]
0x1800075f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800075fc  jmp     short loc_180007647
0x1800075fe  lea     rdx, [rsp+270h+var_250]; int *
0x180007603  mov     rcx, rax; hHandle
0x180007606  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000760b  mov     ebx, eax
0x18000760d  test    eax, eax
0x18000760f  jns     short loc_180007627
0x180007611  mov     rcx, [rbp+178h]; this
0x180007618  mov     r9d, eax; char *
0x18000761b  mov     edx, 0DEh; void *
0x180007620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007625  jmp     short loc_1800075F2
0x180007627  lea     rcx, [rsp+270h+var_248]
0x18000762c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007631  movsxd  rcx, [rsp+270h+var_250]
0x180007636  shl     rcx, 1Fh
0x18000763a  movsxd  rax, [rsp+270h+var_24C]
0x18000763f  or      rcx, rax
0x180007642  mov     [rdi], rcx
0x180007645  xor     ebx, ebx
0x180007647  lea     rcx, [rsp+270h+var_240]
0x18000764c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007651  mov     eax, ebx
0x180007653  mov     rcx, [rbp+170h+var_20]
0x18000765a  xor     rcx, rsp; StackCookie
0x18000765d  call    __security_check_cookie
0x180007662  mov     rbx, [rsp+270h+arg_8]
0x18000766a  add     rsp, 260h
0x180007671  pop     r14
0x180007673  pop     rdi
0x180007674  pop     rbp
0x180007675  retn
```
