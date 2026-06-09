# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18011681c`
- end: `0x1801169be`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1801167a8`

## callees

- `0x180046c60`
- `0x180110e9c`
- `0x180112f14`
- `0x180115f90`
- `0x180115fb0`
- `0x180116404`
- `0x18011681c`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116895`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180116885`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180116917`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180116885`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180116917`

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
0x18011681c  mov     [rsp-8+arg_8], rbx
0x180116821  push    rbp
0x180116822  push    rdi
0x180116823  push    r14
0x180116825  lea     rbp, [rsp-160h]
0x18011682d  sub     rsp, 260h
0x180116834  mov     rax, cs:__security_cookie
0x18011683b  xor     rax, rsp
0x18011683e  mov     [rbp+170h+var_20], rax
0x180116845  mov     rdi, r8
0x180116848  mov     qword ptr [r8], 0
0x18011684f  mov     r8, rcx; unsigned __int16 *
0x180116852  mov     r14d, 104h
0x180116858  mov     edx, r14d; unsigned __int64
0x18011685b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180116860  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180116865  lea     r8, aP0; "_p0"
0x18011686c  mov     edx, r14d; unsigned __int64
0x18011686f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180116874  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180116879  lea     r8, [rsp+270h+Name]; lpName
0x18011687e  xor     edx, edx; bInheritHandle
0x180116880  mov     ecx, 1F0003h; dwDesiredAccess
0x180116885  call    cs:__imp_OpenSemaphoreW
0x18011688b  mov     [rsp+270h+var_240], rax
0x180116890  test    rax, rax
0x180116893  jnz     short loc_1801168BB
0x180116895  call    cs:__imp_GetLastError
0x18011689b  cmp     eax, 2
0x18011689e  jz      loc_18011698D
0x1801168a4  mov     rcx, [rbp+178h]; this
0x1801168ab  lea     edx, [r14-34h]; void *
0x1801168af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801168b4  mov     ebx, eax
0x1801168b6  jmp     loc_18011698F
0x1801168bb  lea     rdx, [rsp+270h+var_24C]; int *
0x1801168c0  mov     [rsp+270h+var_24C], 0
0x1801168c8  mov     rcx, rax; hHandle
0x1801168cb  mov     [rsp+270h+var_250], 0; int
0x1801168d3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1801168d8  mov     ebx, eax
0x1801168da  test    eax, eax
0x1801168dc  jns     short loc_1801168F7
0x1801168de  mov     rcx, [rbp+178h]; this
0x1801168e5  mov     r9d, eax; char *
0x1801168e8  mov     edx, 0D6h; void *
0x1801168ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801168f2  jmp     loc_18011698F
0x1801168f7  lea     r8, asc_180150930; "h"
0x1801168fe  mov     rdx, r14; unsigned __int64
0x180116901  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180116906  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18011690b  lea     r8, [rsp+270h+Name]; lpName
0x180116910  xor     edx, edx; bInheritHandle
0x180116912  mov     ecx, 1F0003h; dwDesiredAccess
0x180116917  call    cs:__imp_OpenSemaphoreW
0x18011691d  mov     [rsp+270h+var_248], rax
0x180116922  test    rax, rax
0x180116925  jnz     short loc_180116946
0x180116927  mov     rcx, [rbp+178h]; this
0x18011692e  mov     edx, 0DCh; void *
0x180116933  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180116938  mov     ebx, eax
0x18011693a  lea     rcx, [rsp+270h+var_248]
0x18011693f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180116944  jmp     short loc_18011698F
0x180116946  lea     rdx, [rsp+270h+var_250]; int *
0x18011694b  mov     rcx, rax; hHandle
0x18011694e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180116953  mov     ebx, eax
0x180116955  test    eax, eax
0x180116957  jns     short loc_18011696F
0x180116959  mov     rcx, [rbp+178h]; this
0x180116960  mov     r9d, eax; char *
0x180116963  mov     edx, 0DEh; void *
0x180116968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011696d  jmp     short loc_18011693A
0x18011696f  lea     rcx, [rsp+270h+var_248]
0x180116974  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180116979  movsxd  rcx, [rsp+270h+var_250]
0x18011697e  movsxd  rax, [rsp+270h+var_24C]
0x180116983  shl     rcx, 1Fh
0x180116987  or      rcx, rax
0x18011698a  mov     [rdi], rcx
0x18011698d  xor     ebx, ebx
0x18011698f  lea     rcx, [rsp+270h+var_240]
0x180116994  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180116999  mov     eax, ebx
0x18011699b  mov     rcx, [rbp+170h+var_20]
0x1801169a2  xor     rcx, rsp; StackCookie
0x1801169a5  call    __security_check_cookie
0x1801169aa  mov     rbx, [rsp+270h+arg_8]
0x1801169b2  add     rsp, 260h
0x1801169b9  pop     r14
0x1801169bb  pop     rdi
0x1801169bc  pop     rbp
0x1801169bd  retn
```
