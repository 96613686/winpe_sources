# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18000cd5c`
- end: `0x18000cf20`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `452`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c93c`
- `0x18001628c`

## callees

- `0x1800053a0`
- `0x18000cd5c`
- `0x18000d508`
- `0x18000e234`
- `0x18000eba8`
- `0x18000f1b8`
- `0x18000f2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000ce23`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000ceac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000ce23`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000ceac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ced5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ced5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        char *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v4; // rbx
  signed __int64 v5; // r8
  WCHAR *v6; // rcx
  __int64 v7; // rdx
  LONG v8; // edi
  WCHAR v9; // ax
  WCHAR *v10; // rax
  LONG v11; // r8d
  unsigned __int64 v12; // rsi
  LONG v13; // ebx
  wil::details *v14; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  wil::details *v19; // rcx
  HANDLE v20; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v4 = a3 >> 2;
  v5 = a2 - (char *)Name;
  v6 = Name;
  v7 = 260;
  v8 = 1;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v9 = *(WCHAR *)((char *)v6 + v5);
    if ( !v9 )
      break;
    *v6++ = v9;
    --v7;
  }
  while ( v7 );
  v10 = v6 - 1;
  if ( v7 )
    v10 = v6;
  *v10 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v11 = 1;
  v12 = v4 >> 31;
  v13 = v4 & 0x7FFFFFFF;
  if ( v13 )
    v11 = v13;
  Semaphore = CreateSemaphoreExW(0, v13, v11, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
LABEL_15:
    StringCchCatW(Name, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v8 = v12;
    v20 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v20 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v20);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v19);
      v17 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v18 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v17 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v18 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"wil",
    (const char *)(unsigned int)LastErrorFailHr,
    dwFlags);
  return v17;
}

```

## disassembly

```asm
0x18000cd5c  mov     [rsp+arg_8], rbx
0x18000cd61  push    rbp
0x18000cd62  push    rsi
0x18000cd63  push    rdi
0x18000cd64  push    r14
0x18000cd66  push    r15
0x18000cd68  sub     rsp, 250h
0x18000cd6f  mov     rax, cs:__security_cookie
0x18000cd76  xor     rax, rsp
0x18000cd79  mov     [rsp+278h+var_38], rax
0x18000cd81  mov     rbx, r8
0x18000cd84  mov     rbp, rcx
0x18000cd87  mov     r8, rdx
0x18000cd8a  test    bl, 3
0x18000cd8d  jnz     loc_18000CF1A
0x18000cd93  lea     rax, [rsp+278h+Name]
0x18000cd98  shr     rbx, 2
0x18000cd9c  sub     r8, rax
0x18000cd9f  lea     rcx, [rsp+278h+Name]
0x18000cda4  xor     r14d, r14d
0x18000cda7  mov     r15d, 104h
0x18000cdad  mov     edx, r15d
0x18000cdb0  lea     edi, [r14+1]
0x18000cdb4  lea     rax, [rdx+7FFFFEFAh]
0x18000cdbb  test    rax, rax
0x18000cdbe  jz      short loc_18000CDD6
0x18000cdc0  movzx   eax, word ptr [r8+rcx]
0x18000cdc5  test    ax, ax
0x18000cdc8  jz      short loc_18000CDD6
0x18000cdca  mov     [rcx], ax
0x18000cdcd  add     rcx, 2
0x18000cdd1  sub     rdx, rdi
0x18000cdd4  jnz     short loc_18000CDB4
0x18000cdd6  test    rdx, rdx
0x18000cdd9  lea     rax, [rcx-2]
0x18000cddd  lea     r8, aP0; "_p0"
0x18000cde4  mov     rdx, r15; unsigned __int64
0x18000cde7  cmovnz  rax, rcx
0x18000cdeb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000cdf0  mov     [rax], r14w
0x18000cdf4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cdf9  mov     rsi, rbx
0x18000cdfc  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000ce04  mov     r8d, edi
0x18000ce07  shr     rsi, 1Fh
0x18000ce0b  and     ebx, 7FFFFFFFh
0x18000ce11  mov     [rsp+278h+dwFlags], r14d; int
0x18000ce16  lea     r9, [rsp+278h+Name]; lpName
0x18000ce1b  mov     edx, ebx; lInitialCount
0x18000ce1d  cmova   r8d, ebx; lMaximumCount
0x18000ce21  xor     ecx, ecx; lpSemaphoreAttributes
0x18000ce23  call    cs:__imp_CreateSemaphoreExW
0x18000ce2a  nop     dword ptr [rax+rax+00h]
0x18000ce2f  mov     rbx, rax
0x18000ce32  test    rax, rax
0x18000ce35  jnz     short loc_18000CE63
0x18000ce37  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ce3c  mov     ebx, eax
0x18000ce3e  test    eax, eax
0x18000ce40  jns     short loc_18000CE7A
0x18000ce42  mov     edx, 88h; void *
0x18000ce47  mov     rcx, [rsp+278h]; this
0x18000ce4f  lea     r8, aWil; "wil"
0x18000ce56  mov     r9d, eax; char *
0x18000ce59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce5e  jmp     loc_18000CEF0
0x18000ce63  call    cs:__imp_GetLastError
0x18000ce6a  nop     dword ptr [rax+rax+00h]
0x18000ce6f  mov     rdx, rbx
0x18000ce72  mov     rcx, rbp
0x18000ce75  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ce7a  lea     r8, asc_1800D5AE0; "h"
0x18000ce81  mov     rdx, r15; unsigned __int64
0x18000ce84  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000ce89  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ce8e  test    esi, esi
0x18000ce90  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000ce98  lea     r9, [rsp+278h+Name]; lpName
0x18000ce9d  mov     [rsp+278h+dwFlags], r14d; dwFlags
0x18000cea2  cmovnz  edi, esi
0x18000cea5  mov     edx, esi; lInitialCount
0x18000cea7  mov     r8d, edi; lMaximumCount
0x18000ceaa  xor     ecx, ecx; lpSemaphoreAttributes
0x18000ceac  call    cs:__imp_CreateSemaphoreExW
0x18000ceb3  nop     dword ptr [rax+rax+00h]
0x18000ceb8  mov     rbx, rax
0x18000cebb  test    rax, rax
0x18000cebe  jnz     short loc_18000CED5
0x18000cec0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000cec5  mov     ebx, eax
0x18000cec7  test    eax, eax
0x18000cec9  jns     short loc_18000CEED
0x18000cecb  mov     edx, 8Dh
0x18000ced0  jmp     loc_18000CE47
0x18000ced5  call    cs:__imp_GetLastError
0x18000cedc  nop     dword ptr [rax+rax+00h]
0x18000cee1  mov     rdx, rbx
0x18000cee4  lea     rcx, [rbp+8]
0x18000cee8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ceed  mov     ebx, r14d
0x18000cef0  mov     eax, ebx
0x18000cef2  mov     rcx, [rsp+278h+var_38]
0x18000cefa  xor     rcx, rsp; StackCookie
0x18000cefd  call    __security_check_cookie
0x18000cf02  mov     rbx, [rsp+278h+arg_8]
0x18000cf0a  add     rsp, 250h
0x18000cf11  pop     r15
0x18000cf13  pop     r14
0x18000cf15  pop     rdi
0x18000cf16  pop     rsi
0x18000cf17  pop     rbp
0x18000cf18  retn
0x18000cf1a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
