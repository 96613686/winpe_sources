# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180009670`
- end: `0x18000989a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008ea8`
- `0x180009278`

## callees

- `0x180005e40`
- `0x180009670`
- `0x18000aa58`
- `0x18000d184`
- `0x18000dbc8`
- `0x18000eaac`
- `0x18000eabc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009734`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800097d7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009734`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800097d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000979b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009836`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000979b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000977e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000981f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000977e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000981f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000978a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000982a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000978a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000982a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009670  mov     [rsp+arg_8], rbx
0x180009675  mov     [rsp+arg_10], rbp
0x18000967a  push    rsi
0x18000967b  push    rdi
0x18000967c  push    r12
0x18000967e  push    r14
0x180009680  push    r15
0x180009682  sub     rsp, 250h
0x180009689  mov     rax, cs:__security_cookie
0x180009690  xor     rax, rsp
0x180009693  mov     [rsp+278h+var_38], rax
0x18000969b  mov     rax, 0C000000000000000h
0x1800096a5  mov     rbp, r9
0x1800096a8  mov     r8, rdx
0x1800096ab  mov     rbx, rcx
0x1800096ae  test    rax, r9
0x1800096b1  jnz     loc_180009881
0x1800096b7  xor     r12d, r12d
0x1800096ba  lea     rax, [rsp+278h+Name]
0x1800096bf  mov     ecx, 7FFFFFFEh
0x1800096c4  mov     edx, 104h
0x1800096c9  lea     esi, [r12+1]
0x1800096ce  test    rcx, rcx
0x1800096d1  jz      short loc_1800096F1
0x1800096d3  movzx   r9d, word ptr [r8]
0x1800096d7  test    r9w, r9w
0x1800096db  jz      short loc_1800096F1
0x1800096dd  mov     [rax], r9w
0x1800096e1  add     r8, 2
0x1800096e5  add     rax, 2
0x1800096e9  sub     rcx, rsi
0x1800096ec  sub     rdx, rsi; unsigned __int64
0x1800096ef  jnz     short loc_1800096CE
0x1800096f1  test    rdx, rdx
0x1800096f4  lea     rcx, [rax-2]
0x1800096f8  lea     r8, aP0; "_p0"
0x1800096ff  cmovnz  rcx, rax
0x180009703  mov     [rcx], r12w
0x180009707  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000970c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009711  mov     edx, ebp
0x180009713  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000971b  and     edx, 7FFFFFFFh; lInitialCount
0x180009721  mov     [rsp+278h+dwFlags], r12d; int
0x180009726  mov     r8d, esi
0x180009729  lea     r9, [rsp+278h+Name]; lpName
0x18000972e  cmova   r8d, edx; lMaximumCount
0x180009732  xor     ecx, ecx; lpSemaphoreAttributes
0x180009734  call    cs:__imp_CreateSemaphoreExW
0x18000973a  mov     r15, rax
0x18000973d  test    rax, rax
0x180009740  jnz     short loc_180009770
0x180009742  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009747  mov     edi, eax
0x180009749  test    eax, eax
0x18000974b  jns     short loc_1800097A4
0x18000974d  mov     rcx, [rsp+278h]; this
0x180009755  lea     r8, aWil; "wil"
0x18000975c  mov     r9d, eax; char *
0x18000975f  mov     edx, 8Bh; void *
0x180009764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009769  mov     eax, edi
0x18000976b  jmp     loc_180009842
0x180009770  call    cs:__imp_GetLastError
0x180009776  mov     rdi, [rbx]
0x180009779  test    rdi, rdi
0x18000977c  jz      short loc_1800097A1
0x18000977e  call    cs:__imp_GetLastError
0x180009784  mov     rcx, rdi; hObject
0x180009787  mov     r14d, eax
0x18000978a  call    cs:__imp_CloseHandle
0x180009790  test    eax, eax
0x180009792  jz      loc_180009887
0x180009798  mov     ecx, r14d; dwErrCode
0x18000979b  call    cs:__imp_SetLastError
0x1800097a1  mov     [rbx], r15
0x1800097a4  lea     r8, asc_18011E3C8; "h"
0x1800097ab  shr     rbp, 1Fh
0x1800097af  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800097b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097b9  test    ebp, ebp
0x1800097bb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800097c3  lea     r9, [rsp+278h+Name]; lpName
0x1800097c8  mov     [rsp+278h+dwFlags], r12d; int
0x1800097cd  cmovnz  esi, ebp
0x1800097d0  mov     edx, ebp; lInitialCount
0x1800097d2  mov     r8d, esi; lMaximumCount
0x1800097d5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800097d7  call    cs:__imp_CreateSemaphoreExW
0x1800097dd  mov     rsi, rax
0x1800097e0  test    rax, rax
0x1800097e3  jnz     short loc_180009810
0x1800097e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800097ea  mov     ebx, eax
0x1800097ec  test    eax, eax
0x1800097ee  jns     short loc_180009840
0x1800097f0  mov     rcx, [rsp+278h]; this
0x1800097f8  lea     r8, aWil; "wil"
0x1800097ff  mov     r9d, eax; char *
0x180009802  mov     edx, 90h; void *
0x180009807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000980c  mov     eax, ebx
0x18000980e  jmp     short loc_180009842
0x180009810  call    cs:__imp_GetLastError
0x180009816  mov     rdi, [rbx+8]
0x18000981a  test    rdi, rdi
0x18000981d  jz      short loc_18000983C
0x18000981f  call    cs:__imp_GetLastError
0x180009825  mov     rcx, rdi; hObject
0x180009828  mov     ebp, eax
0x18000982a  call    cs:__imp_CloseHandle
0x180009830  test    eax, eax
0x180009832  jz      short loc_18000986E
0x180009834  mov     ecx, ebp; dwErrCode
0x180009836  call    cs:__imp_SetLastError
0x18000983c  mov     [rbx+8], rsi
0x180009840  xor     eax, eax
0x180009842  mov     rcx, [rsp+278h+var_38]
0x18000984a  xor     rcx, rsp; StackCookie
0x18000984d  call    __security_check_cookie
0x180009852  lea     r11, [rsp+278h+var_28]
0x18000985a  mov     rbx, [r11+38h]
0x18000985e  mov     rbp, [r11+40h]
0x180009862  mov     rsp, r11
0x180009865  pop     r15
0x180009867  pop     r14
0x180009869  pop     r12
0x18000986b  pop     rdi
0x18000986c  pop     rsi
0x18000986d  retn
0x18000986e  mov     rcx, [rsp+278h]; this
0x180009876  mov     edx, 0A0Bh; void *
0x18000987b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009881  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009887  mov     rcx, [rsp+278h]; this
0x18000988f  mov     edx, 0A0Bh; void *
0x180009894  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
