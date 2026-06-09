# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001b034`
- end: `0x18001b272`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c4d0`

## callees

- `0x180008618`
- `0x18000933c`
- `0x18000a4e0`
- `0x180019d90`
- `0x18001aec0`
- `0x18001b034`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b22d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b0d6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b19f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b0d6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b19f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // [rsp+28h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = (char *)a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v12);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v26 = 0;
  v27[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v26);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    goto LABEL_13;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v27);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v22, v23);
      LastError = 0;
      *a3 = v26 | (unsigned __int64)((__int64)v27[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v19,
        v26);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v20, v21);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v24, v25);
  return LastError;
}

```

## disassembly

```asm
0x18001b034  mov     rax, rsp
0x18001b037  mov     [rax+8], rbx
0x18001b03b  mov     [rax+10h], rsi
0x18001b03f  mov     [rax+20h], rdi
0x18001b043  push    rbp
0x18001b044  push    r14
0x18001b046  push    r15
0x18001b048  lea     rbp, [rax-168h]
0x18001b04f  sub     rsp, 250h
0x18001b056  mov     rax, cs:__security_cookie
0x18001b05d  xor     rax, rsp
0x18001b060  mov     [rbp+160h+var_20], rax
0x18001b067  xor     r15d, r15d
0x18001b06a  lea     rax, [rsp+260h+Name]
0x18001b06f  mov     edi, 104h
0x18001b074  mov     [r8], r15
0x18001b077  mov     r9d, edi
0x18001b07a  lea     rdx, [rsp+260h+Name]
0x18001b07f  sub     rcx, rax
0x18001b082  mov     r14, r8
0x18001b085  lea     rax, [r9+7FFFFEFAh]
0x18001b08c  test    rax, rax
0x18001b08f  jz      short loc_18001B0A7
0x18001b091  movzx   eax, word ptr [rdx+rcx]
0x18001b095  test    ax, ax
0x18001b098  jz      short loc_18001B0A7
0x18001b09a  mov     [rdx], ax
0x18001b09d  add     rdx, 2
0x18001b0a1  sub     r9, 1
0x18001b0a5  jnz     short loc_18001B085
0x18001b0a7  lea     rax, [rdx-2]
0x18001b0ab  test    r9, r9
0x18001b0ae  lea     r8, aP0; "_p0"
0x18001b0b5  cmovnz  rax, rdx
0x18001b0b9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18001b0be  mov     rdx, rdi; unsigned __int64
0x18001b0c1  mov     [rax], r15w
0x18001b0c5  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001b0ca  lea     r8, [rsp+260h+Name]; lpName
0x18001b0cf  xor     edx, edx; bInheritHandle
0x18001b0d1  mov     ecx, 1F0003h; dwDesiredAccess
0x18001b0d6  call    cs:__imp_OpenSemaphoreW
0x18001b0dc  mov     rsi, rax
0x18001b0df  test    rax, rax
0x18001b0e2  jnz     short loc_18001B110
0x18001b0e4  call    cs:__imp_GetLastError
0x18001b0ea  cmp     eax, 2
0x18001b0ed  jnz     short loc_18001B0F4
0x18001b0ef  mov     ebx, r15d
0x18001b0f2  jmp     short loc_18001B148
0x18001b0f4  mov     rcx, [rbp+168h]; this
0x18001b0fb  lea     r8, aWil; "wil"
0x18001b102  mov     edx, 0CDh; void *
0x18001b107  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b10c  mov     ebx, eax
0x18001b10e  jmp     short loc_18001B148
0x18001b110  lea     rdx, [rsp+260h+var_240]; int *
0x18001b115  mov     [rsp+260h+var_240], r15d; int
0x18001b11a  mov     rcx, rsi; hHandle
0x18001b11d  mov     [rsp+260h+var_23C], r15d
0x18001b122  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001b127  mov     ebx, eax
0x18001b129  test    eax, eax
0x18001b12b  jns     short loc_18001B17F
0x18001b12d  mov     rcx, [rbp+168h]; this
0x18001b134  lea     r8, aWil; "wil"
0x18001b13b  mov     r9d, eax; char *
0x18001b13e  mov     edx, 0D3h; void *
0x18001b143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b148  test    rsi, rsi
0x18001b14b  jnz     loc_18001B22A
0x18001b151  mov     eax, ebx
0x18001b153  mov     rcx, [rbp+160h+var_20]
0x18001b15a  xor     rcx, rsp; StackCookie
0x18001b15d  call    __security_check_cookie
0x18001b162  lea     r11, [rsp+260h+var_10]
0x18001b16a  mov     rbx, [r11+20h]
0x18001b16e  mov     rsi, [r11+28h]
0x18001b172  mov     rdi, [r11+38h]
0x18001b176  mov     rsp, r11
0x18001b179  pop     r15
0x18001b17b  pop     r14
0x18001b17d  pop     rbp
0x18001b17e  retn
0x18001b17f  lea     r8, asc_18012BE10; "h"
0x18001b186  mov     rdx, rdi; unsigned __int64
0x18001b189  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18001b18e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001b193  lea     r8, [rsp+260h+Name]; lpName
0x18001b198  xor     edx, edx; bInheritHandle
0x18001b19a  mov     ecx, 1F0003h; dwDesiredAccess
0x18001b19f  call    cs:__imp_OpenSemaphoreW
0x18001b1a5  mov     rdi, rax
0x18001b1a8  test    rax, rax
0x18001b1ab  jnz     short loc_18001B1C9
0x18001b1ad  mov     rcx, [rbp+168h]; this
0x18001b1b4  lea     r8, aWil; "wil"
0x18001b1bb  mov     edx, 0D9h; void *
0x18001b1c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b1c5  mov     ebx, eax
0x18001b1c7  jmp     short loc_18001B22A
0x18001b1c9  lea     rdx, [rsp+260h+var_23C]; int *
0x18001b1ce  mov     rcx, rdi; hHandle
0x18001b1d1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001b1d6  mov     ebx, eax
0x18001b1d8  test    eax, eax
0x18001b1da  jns     short loc_18001B206
0x18001b1dc  mov     rcx, [rbp+168h]; this
0x18001b1e3  lea     r8, aWil; "wil"
0x18001b1ea  mov     r9d, eax; char *
0x18001b1ed  mov     edx, 0DBh; void *
0x18001b1f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1f7  mov     rcx, rdi; hObject
0x18001b1fa  call    cs:__imp_CloseHandle
0x18001b200  test    eax, eax
0x18001b202  jz      short loc_18001B24E
0x18001b204  jmp     short loc_18001B22A
0x18001b206  mov     rcx, rdi; hObject
0x18001b209  call    cs:__imp_CloseHandle
0x18001b20f  test    eax, eax
0x18001b211  jz      short loc_18001B23C
0x18001b213  movsxd  rcx, [rsp+260h+var_23C]
0x18001b218  mov     ebx, r15d
0x18001b21b  movsxd  rax, [rsp+260h+var_240]
0x18001b220  shl     rcx, 1Fh
0x18001b224  or      rcx, rax
0x18001b227  mov     [r14], rcx
0x18001b22a  mov     rcx, rsi; hObject
0x18001b22d  call    cs:__imp_CloseHandle
0x18001b233  test    eax, eax
0x18001b235  jz      short loc_18001B260
0x18001b237  jmp     loc_18001B151
0x18001b23c  mov     rcx, [rbp+168h]; this
0x18001b243  mov     edx, 9D1h; void *
0x18001b248  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001b24e  mov     rcx, [rbp+168h]; this
0x18001b255  mov     edx, 9D1h; void *
0x18001b25a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001b260  mov     rcx, [rbp+168h]; this
0x18001b267  mov     edx, 9D1h; void *
0x18001b26c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
