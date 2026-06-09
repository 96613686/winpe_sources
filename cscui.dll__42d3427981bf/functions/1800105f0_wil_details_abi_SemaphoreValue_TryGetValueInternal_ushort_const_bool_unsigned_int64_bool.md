# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800105f0`
- end: `0x180010792`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001057c`

## callees

- `0x180003d60`
- `0x18000a6bc`
- `0x18000ee0c`
- `0x18000f98c`
- `0x1800100e0`
- `0x180010398`
- `0x1800105f0`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010669`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010659`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800106eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010659`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800106eb`

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
0x1800105f0  mov     [rsp-8+arg_8], rbx
0x1800105f5  push    rbp
0x1800105f6  push    rdi
0x1800105f7  push    r14
0x1800105f9  lea     rbp, [rsp-160h]
0x180010601  sub     rsp, 260h
0x180010608  mov     rax, cs:__security_cookie
0x18001060f  xor     rax, rsp
0x180010612  mov     [rbp+170h+var_20], rax
0x180010619  mov     rdi, r8
0x18001061c  mov     qword ptr [r8], 0
0x180010623  mov     r8, rcx; unsigned __int16 *
0x180010626  mov     r14d, 104h
0x18001062c  mov     edx, r14d; unsigned __int64
0x18001062f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010634  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010639  lea     r8, aP0; "_p0"
0x180010640  mov     edx, r14d; unsigned __int64
0x180010643  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180010648  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001064d  lea     r8, [rsp+270h+Name]; lpName
0x180010652  xor     edx, edx; bInheritHandle
0x180010654  mov     ecx, 1F0003h; dwDesiredAccess
0x180010659  call    cs:__imp_OpenSemaphoreW
0x18001065f  mov     [rsp+270h+var_240], rax
0x180010664  test    rax, rax
0x180010667  jnz     short loc_18001068F
0x180010669  call    cs:__imp_GetLastError
0x18001066f  cmp     eax, 2
0x180010672  jz      loc_180010761
0x180010678  mov     rcx, [rbp+178h]; this
0x18001067f  lea     edx, [r14-34h]; void *
0x180010683  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010688  mov     ebx, eax
0x18001068a  jmp     loc_180010763
0x18001068f  lea     rdx, [rsp+270h+var_24C]; int *
0x180010694  mov     [rsp+270h+var_24C], 0
0x18001069c  mov     rcx, rax; hHandle
0x18001069f  mov     [rsp+270h+var_250], 0; int
0x1800106a7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800106ac  mov     ebx, eax
0x1800106ae  test    eax, eax
0x1800106b0  jns     short loc_1800106CB
0x1800106b2  mov     rcx, [rbp+178h]; this
0x1800106b9  mov     r9d, eax; char *
0x1800106bc  mov     edx, 0D6h; void *
0x1800106c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106c6  jmp     loc_180010763
0x1800106cb  lea     r8, asc_180055568; "h"
0x1800106d2  mov     rdx, r14; unsigned __int64
0x1800106d5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800106da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800106df  lea     r8, [rsp+270h+Name]; lpName
0x1800106e4  xor     edx, edx; bInheritHandle
0x1800106e6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800106eb  call    cs:__imp_OpenSemaphoreW
0x1800106f1  mov     [rsp+270h+var_248], rax
0x1800106f6  test    rax, rax
0x1800106f9  jnz     short loc_18001071A
0x1800106fb  mov     rcx, [rbp+178h]; this
0x180010702  mov     edx, 0DCh; void *
0x180010707  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001070c  mov     ebx, eax
0x18001070e  lea     rcx, [rsp+270h+var_248]
0x180010713  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010718  jmp     short loc_180010763
0x18001071a  lea     rdx, [rsp+270h+var_250]; int *
0x18001071f  mov     rcx, rax; hHandle
0x180010722  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010727  mov     ebx, eax
0x180010729  test    eax, eax
0x18001072b  jns     short loc_180010743
0x18001072d  mov     rcx, [rbp+178h]; this
0x180010734  mov     r9d, eax; char *
0x180010737  mov     edx, 0DEh; void *
0x18001073c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010741  jmp     short loc_18001070E
0x180010743  lea     rcx, [rsp+270h+var_248]
0x180010748  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001074d  movsxd  rcx, [rsp+270h+var_250]
0x180010752  movsxd  rax, [rsp+270h+var_24C]
0x180010757  shl     rcx, 1Fh
0x18001075b  or      rcx, rax
0x18001075e  mov     [rdi], rcx
0x180010761  xor     ebx, ebx
0x180010763  lea     rcx, [rsp+270h+var_240]
0x180010768  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001076d  mov     eax, ebx
0x18001076f  mov     rcx, [rbp+170h+var_20]
0x180010776  xor     rcx, rsp; StackCookie
0x180010779  call    __security_check_cookie
0x18001077e  mov     rbx, [rsp+270h+arg_8]
0x180010786  add     rsp, 260h
0x18001078d  pop     r14
0x18001078f  pop     rdi
0x180010790  pop     rbp
0x180010791  retn
```
