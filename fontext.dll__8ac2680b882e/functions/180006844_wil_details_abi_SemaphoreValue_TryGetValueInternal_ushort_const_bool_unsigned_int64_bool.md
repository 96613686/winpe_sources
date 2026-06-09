# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006844`
- end: `0x1800069f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800067c0`

## callees

- `0x180004be0`
- `0x180005884`
- `0x1800062b0`
- `0x1800062d0`
- `0x180006598`
- `0x180006624`
- `0x180006844`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800068ad`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006946`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800068ad`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068bd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180006844  mov     [rsp-8+arg_8], rbx
0x180006849  push    rbp
0x18000684a  push    rdi
0x18000684b  push    r14
0x18000684d  lea     rbp, [rsp-160h]
0x180006855  sub     rsp, 260h
0x18000685c  mov     rax, cs:__security_cookie
0x180006863  xor     rax, rsp
0x180006866  mov     [rbp+170h+var_20], rax
0x18000686d  mov     rdi, r8
0x180006870  mov     qword ptr [r8], 0
0x180006877  mov     r8, rcx; unsigned __int16 *
0x18000687a  mov     r14d, 104h
0x180006880  mov     edx, r14d; unsigned __int64
0x180006883  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006888  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000688d  lea     r8, aP0; "_p0"
0x180006894  mov     edx, r14d; unsigned __int64
0x180006897  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000689c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800068a1  lea     r8, [rsp+270h+Name]; lpName
0x1800068a6  xor     edx, edx; bInheritHandle
0x1800068a8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800068ad  call    cs:__imp_OpenSemaphoreW
0x1800068b3  mov     [rsp+270h+var_240], rax
0x1800068b8  test    rax, rax
0x1800068bb  jnz     short loc_1800068E3
0x1800068bd  call    cs:__imp_GetLastError
0x1800068c3  cmp     eax, 2
0x1800068c6  jz      loc_1800069C3
0x1800068cc  mov     rcx, [rbp+178h]; this
0x1800068d3  lea     edx, [r14-34h]; void *
0x1800068d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800068dc  mov     ebx, eax
0x1800068de  jmp     loc_1800069C5
0x1800068e3  lea     rdx, [rsp+270h+var_24C]; int *
0x1800068e8  mov     [rsp+270h+var_24C], 0
0x1800068f0  mov     rcx, rax; hHandle
0x1800068f3  mov     [rsp+270h+var_250], 0; int
0x1800068fb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006900  mov     ebx, eax
0x180006902  test    eax, eax
0x180006904  jns     short loc_180006926
0x180006906  mov     rcx, [rbp+178h]; this
0x18000690d  lea     r8, aWil; "wil"
0x180006914  mov     r9d, eax; char *
0x180006917  mov     edx, 0D6h; void *
0x18000691c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006921  jmp     loc_1800069C5
0x180006926  lea     r8, asc_180037848; "h"
0x18000692d  mov     rdx, r14; unsigned __int64
0x180006930  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006935  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000693a  lea     r8, [rsp+270h+Name]; lpName
0x18000693f  xor     edx, edx; bInheritHandle
0x180006941  mov     ecx, 1F0003h; dwDesiredAccess
0x180006946  call    cs:__imp_OpenSemaphoreW
0x18000694c  mov     [rsp+270h+var_248], rax
0x180006951  test    rax, rax
0x180006954  jnz     short loc_180006975
0x180006956  mov     rcx, [rbp+178h]; this
0x18000695d  mov     edx, 0DCh; void *
0x180006962  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006967  mov     ebx, eax
0x180006969  lea     rcx, [rsp+270h+var_248]
0x18000696e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006973  jmp     short loc_1800069C5
0x180006975  lea     rdx, [rsp+270h+var_250]; int *
0x18000697a  mov     rcx, rax; hHandle
0x18000697d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006982  mov     ebx, eax
0x180006984  test    eax, eax
0x180006986  jns     short loc_1800069A5
0x180006988  mov     rcx, [rbp+178h]; this
0x18000698f  lea     r8, aWil; "wil"
0x180006996  mov     r9d, eax; char *
0x180006999  mov     edx, 0DEh; void *
0x18000699e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069a3  jmp     short loc_180006969
0x1800069a5  lea     rcx, [rsp+270h+var_248]
0x1800069aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800069af  movsxd  rcx, [rsp+270h+var_250]
0x1800069b4  movsxd  rax, [rsp+270h+var_24C]
0x1800069b9  shl     rcx, 1Fh
0x1800069bd  or      rcx, rax
0x1800069c0  mov     [rdi], rcx
0x1800069c3  xor     ebx, ebx
0x1800069c5  lea     rcx, [rsp+270h+var_240]
0x1800069ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800069cf  mov     eax, ebx
0x1800069d1  mov     rcx, [rbp+170h+var_20]
0x1800069d8  xor     rcx, rsp; StackCookie
0x1800069db  call    __security_check_cookie
0x1800069e0  mov     rbx, [rsp+270h+arg_8]
0x1800069e8  add     rsp, 260h
0x1800069ef  pop     r14
0x1800069f1  pop     rdi
0x1800069f2  pop     rbp
0x1800069f3  retn
```
