# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14001ae94`
- end: `0x14001b036`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001ae20`

## callees

- `0x140004648`
- `0x14000c9b0`
- `0x1400172f8`
- `0x14001885c`
- `0x14001a39c`
- `0x14001a3bc`
- `0x14001ae94`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x14001aefd`
- `KERNEL32!OpenSemaphoreW` at `0x14001af8f`
- `KERNEL32!OpenSemaphoreW` at `0x14001aefd`
- `KERNEL32!OpenSemaphoreW` at `0x14001af8f`
- `KERNEL32!GetLastError` at `0x14001af0d`
- `KERNEL32!GetLastError` at `0x14001af0d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int v15; // r8d
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14);
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
0x14001ae94  mov     [rsp-8+arg_8], rbx
0x14001ae99  push    rbp
0x14001ae9a  push    rdi
0x14001ae9b  push    r14
0x14001ae9d  lea     rbp, [rsp-160h]
0x14001aea5  sub     rsp, 260h
0x14001aeac  mov     rax, cs:__security_cookie
0x14001aeb3  xor     rax, rsp
0x14001aeb6  mov     [rbp+170h+var_20], rax
0x14001aebd  mov     rdi, r8
0x14001aec0  mov     qword ptr [r8], 0
0x14001aec7  mov     r8, rcx; wchar_t *
0x14001aeca  mov     r14d, 104h
0x14001aed0  mov     edx, r14d; unsigned __int64
0x14001aed3  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001aed8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001aedd  lea     r8, aP0; "_p0"
0x14001aee4  mov     edx, r14d; unsigned __int64
0x14001aee7  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001aeec  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001aef1  lea     r8, [rsp+270h+Name]; lpName
0x14001aef6  xor     edx, edx; bInheritHandle
0x14001aef8  mov     ecx, 1F0003h; dwDesiredAccess
0x14001aefd  call    cs:__imp_OpenSemaphoreW
0x14001af03  mov     [rsp+270h+var_240], rax
0x14001af08  test    rax, rax
0x14001af0b  jnz     short loc_14001AF33
0x14001af0d  call    cs:__imp_GetLastError
0x14001af13  cmp     eax, 2
0x14001af16  jz      loc_14001B005
0x14001af1c  mov     rcx, [rbp+178h]; this
0x14001af23  lea     edx, [r14-34h]; void *
0x14001af27  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001af2c  mov     ebx, eax
0x14001af2e  jmp     loc_14001B007
0x14001af33  mov     [rsp+270h+var_24C], 0
0x14001af3b  mov     [rsp+270h+var_250], 0; int
0x14001af43  lea     rdx, [rsp+270h+var_24C]; int *
0x14001af48  mov     rcx, rax; hHandle
0x14001af4b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14001af50  mov     ebx, eax
0x14001af52  test    eax, eax
0x14001af54  jns     short loc_14001AF6F
0x14001af56  mov     rcx, [rbp+178h]; this
0x14001af5d  mov     r9d, eax; char *
0x14001af60  mov     edx, 0D6h; void *
0x14001af65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001af6a  jmp     loc_14001B007
0x14001af6f  lea     r8, asc_140023148; "h"
0x14001af76  mov     rdx, r14; unsigned __int64
0x14001af79  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001af7e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001af83  lea     r8, [rsp+270h+Name]; lpName
0x14001af88  xor     edx, edx; bInheritHandle
0x14001af8a  mov     ecx, 1F0003h; dwDesiredAccess
0x14001af8f  call    cs:__imp_OpenSemaphoreW
0x14001af95  mov     [rsp+270h+var_248], rax
0x14001af9a  test    rax, rax
0x14001af9d  jnz     short loc_14001AFBE
0x14001af9f  mov     rcx, [rbp+178h]; this
0x14001afa6  mov     edx, 0DCh; void *
0x14001afab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001afb0  mov     ebx, eax
0x14001afb2  lea     rcx, [rsp+270h+var_248]
0x14001afb7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001afbc  jmp     short loc_14001B007
0x14001afbe  lea     rdx, [rsp+270h+var_250]; int *
0x14001afc3  mov     rcx, rax; hHandle
0x14001afc6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14001afcb  mov     ebx, eax
0x14001afcd  test    eax, eax
0x14001afcf  jns     short loc_14001AFE7
0x14001afd1  mov     rcx, [rbp+178h]; this
0x14001afd8  mov     r9d, eax; char *
0x14001afdb  mov     edx, 0DEh; void *
0x14001afe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001afe5  jmp     short loc_14001AFB2
0x14001afe7  lea     rcx, [rsp+270h+var_248]
0x14001afec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001aff1  movsxd  rcx, [rsp+270h+var_250]
0x14001aff6  shl     rcx, 1Fh
0x14001affa  movsxd  rax, [rsp+270h+var_24C]
0x14001afff  or      rcx, rax
0x14001b002  mov     [rdi], rcx
0x14001b005  xor     ebx, ebx
0x14001b007  lea     rcx, [rsp+270h+var_240]
0x14001b00c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001b011  mov     eax, ebx
0x14001b013  mov     rcx, [rbp+170h+var_20]
0x14001b01a  xor     rcx, rsp; StackCookie
0x14001b01d  call    __security_check_cookie
0x14001b022  mov     rbx, [rsp+270h+arg_8]
0x14001b02a  add     rsp, 260h
0x14001b031  pop     r14
0x14001b033  pop     rdi
0x14001b034  pop     rbp
0x14001b035  retn
```
