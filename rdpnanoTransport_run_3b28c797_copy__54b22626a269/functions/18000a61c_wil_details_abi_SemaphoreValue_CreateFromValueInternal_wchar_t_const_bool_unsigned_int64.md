# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000a61c`
- end: `0x18000a804`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `488`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b930`

## callees

- `0x18000a61c`
- `0x18000b15c`
- `0x18000be70`
- `0x18000c568`
- `0x18000cba4`
- `0x18000ccf4`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a753`
- `KERNEL32!GetLastError` at `0x18000a7be`
- `KERNEL32!GetLastError` at `0x18000a753`
- `KERNEL32!GetLastError` at `0x18000a7be`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a6fc`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a79b`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a6fc`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a79b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        char a3,
        unsigned __int64 a4)
{
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  signed __int64 v10; // r9
  LONG v11; // edi
  WCHAR v12; // ax
  WCHAR *v13; // rax
  LONG v14; // r8d
  unsigned __int64 v15; // rbp
  LONG v16; // ebx
  wil::details *v17; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // ebx
  __int64 v20; // rdx
  wil::details::in1diag3 *v21; // rcx
  wil::details *v23; // rcx
  HANDLE v24; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( a3 )
  {
    if ( (a4 & 0xC000000000000000uLL) == 0 )
      goto LABEL_3;
LABEL_26:
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  }
  if ( (a4 & 0xFFFFFFFF80000000uLL) != 0 )
    goto LABEL_26;
LABEL_3:
  v8 = 260;
  v9 = Name;
  v10 = (char *)a2 - (char *)Name;
  v11 = 1;
  do
  {
    if ( v8 == -2147483386 )
      break;
    v12 = *(WCHAR *)((char *)v9 + v10);
    if ( !v12 )
      break;
    *v9++ = v12;
    --v8;
  }
  while ( v8 );
  v13 = v9 - 1;
  if ( v8 )
    v13 = v9;
  *v13 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v14 = 1;
  v15 = a4 >> 31;
  v16 = a4 & 0x7FFFFFFF;
  if ( v16 )
    v14 = v16;
  Semaphore = CreateSemaphoreExW(0, v16, v14, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v17);
    if ( LastErrorFailHr < 0 )
    {
      v20 = 136;
LABEL_14:
      v21 = retaddr;
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        v21,
        (void *)v20,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  if ( a3 )
  {
    StringCchCatW(Name, 0x104u, L"h");
    if ( (_DWORD)v15 )
      v11 = v15;
    v24 = CreateSemaphoreExW(0, v15, v11, Name, 0, 0x1F0003u);
    if ( v24 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v24);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
      if ( LastErrorFailHr < 0 )
      {
        v20 = 141;
        goto LABEL_14;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a61c  mov     [rsp+arg_8], rbx
0x18000a621  mov     [rsp+arg_10], rbp
0x18000a626  push    rsi
0x18000a627  push    rdi
0x18000a628  push    r12
0x18000a62a  push    r14
0x18000a62c  push    r15
0x18000a62e  mov     eax, 250h
0x18000a633  call    _alloca_probe
0x18000a638  sub     rsp, rax
0x18000a63b  mov     rax, cs:__security_cookie
0x18000a642  xor     rax, rsp
0x18000a645  mov     [rsp+278h+var_38], rax
0x18000a64d  xor     r15d, r15d
0x18000a650  mov     rbx, r9
0x18000a653  mov     r14b, r8b
0x18000a656  mov     r9, rdx
0x18000a659  mov     rsi, rcx
0x18000a65c  test    r8b, r8b
0x18000a65f  jnz     loc_18000A73B
0x18000a665  test    rbx, 0FFFFFFFF80000000h
0x18000a66c  jnz     loc_18000A7FE
0x18000a672  mov     r12d, 104h
0x18000a678  lea     rax, [rsp+278h+Name]
0x18000a67d  mov     edx, r12d
0x18000a680  lea     rcx, [rsp+278h+Name]
0x18000a685  sub     r9, rax
0x18000a688  mov     edi, 1
0x18000a68d  lea     rax, [rdx+7FFFFEFAh]
0x18000a694  test    rax, rax
0x18000a697  jz      short loc_18000A6AF
0x18000a699  movzx   eax, word ptr [rcx+r9]
0x18000a69e  test    ax, ax
0x18000a6a1  jz      short loc_18000A6AF
0x18000a6a3  mov     [rcx], ax
0x18000a6a6  add     rcx, 2
0x18000a6aa  sub     rdx, rdi
0x18000a6ad  jnz     short loc_18000A68D
0x18000a6af  test    rdx, rdx
0x18000a6b2  lea     rax, [rcx-2]
0x18000a6b6  lea     r8, aP0; "_p0"
0x18000a6bd  mov     rdx, r12; unsigned __int64
0x18000a6c0  cmovnz  rax, rcx
0x18000a6c4  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18000a6c9  mov     [rax], r15w
0x18000a6cd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a6d2  mov     rbp, rbx
0x18000a6d5  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a6dd  mov     r8d, edi
0x18000a6e0  shr     rbp, 1Fh
0x18000a6e4  and     ebx, 7FFFFFFFh
0x18000a6ea  mov     [rsp+278h+dwFlags], r15d; int
0x18000a6ef  lea     r9, [rsp+278h+Name]; lpName
0x18000a6f4  mov     edx, ebx; lInitialCount
0x18000a6f6  cmova   r8d, ebx; lMaximumCount
0x18000a6fa  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a6fc  call    cs:__imp_CreateSemaphoreExW
0x18000a702  mov     rbx, rax
0x18000a705  test    rax, rax
0x18000a708  jnz     short loc_18000A753
0x18000a70a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a70f  mov     ebx, eax
0x18000a711  test    eax, eax
0x18000a713  jns     short loc_18000A764
0x18000a715  mov     edx, 88h; void *
0x18000a71a  mov     rcx, [rsp+278h]; this
0x18000a722  lea     r8, aWil; "wil"
0x18000a729  mov     r9d, ebx; char *
0x18000a72c  lfence
0x18000a72f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a734  mov     eax, ebx
0x18000a736  jmp     loc_18000A7D2
0x18000a73b  mov     rax, 0C000000000000000h
0x18000a745  test    rax, rbx
0x18000a748  jnz     loc_18000A7FE
0x18000a74e  jmp     loc_18000A672
0x18000a753  call    cs:__imp_GetLastError
0x18000a759  mov     rdx, rbx
0x18000a75c  mov     rcx, rsi
0x18000a75f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a764  test    r14b, r14b
0x18000a767  jz      short loc_18000A7D0
0x18000a769  lea     r8, asc_1803D4BD0; "h"
0x18000a770  mov     rdx, r12; unsigned __int64
0x18000a773  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18000a778  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a77d  test    ebp, ebp
0x18000a77f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a787  lea     r9, [rsp+278h+Name]; lpName
0x18000a78c  mov     [rsp+278h+dwFlags], r15d; dwFlags
0x18000a791  cmovnz  edi, ebp
0x18000a794  mov     edx, ebp; lInitialCount
0x18000a796  mov     r8d, edi; lMaximumCount
0x18000a799  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a79b  call    cs:__imp_CreateSemaphoreExW
0x18000a7a1  mov     rbx, rax
0x18000a7a4  test    rax, rax
0x18000a7a7  jnz     short loc_18000A7BE
0x18000a7a9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a7ae  mov     ebx, eax
0x18000a7b0  test    eax, eax
0x18000a7b2  jns     short loc_18000A7D0
0x18000a7b4  mov     edx, 8Dh
0x18000a7b9  jmp     loc_18000A71A
0x18000a7be  call    cs:__imp_GetLastError
0x18000a7c4  lea     rcx, [rsi+8]
0x18000a7c8  mov     rdx, rbx
0x18000a7cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a7d0  xor     eax, eax
0x18000a7d2  mov     rcx, [rsp+278h+var_38]
0x18000a7da  xor     rcx, rsp; StackCookie
0x18000a7dd  call    __security_check_cookie
0x18000a7e2  lea     r11, [rsp+278h+var_28]
0x18000a7ea  mov     rbx, [r11+38h]
0x18000a7ee  mov     rbp, [r11+40h]
0x18000a7f2  mov     rsp, r11
0x18000a7f5  pop     r15
0x18000a7f7  pop     r14
0x18000a7f9  pop     r12
0x18000a7fb  pop     rdi
0x18000a7fc  pop     rsi
0x18000a7fd  retn
0x18000a7fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
