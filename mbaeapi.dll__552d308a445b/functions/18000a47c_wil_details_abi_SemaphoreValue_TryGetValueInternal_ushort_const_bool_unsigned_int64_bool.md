# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a47c`
- end: `0x18000a714`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005cc8`
- `0x18000609c`

## callees

- `0x1800024e0`
- `0x180007634`
- `0x180009454`
- `0x180009474`
- `0x180009ec4`
- `0x18000a47c`
- `0x18000ad5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a513`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a595`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a513`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a560`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a560`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a653`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000a47c  push    rbp
0x18000a47e  push    rbx
0x18000a47f  push    rsi
0x18000a480  push    rdi
0x18000a481  push    r14
0x18000a483  push    r15
0x18000a485  lea     rbp, [rsp-158h]
0x18000a48d  sub     rsp, 258h
0x18000a494  mov     rax, cs:__security_cookie
0x18000a49b  xor     rax, rsp
0x18000a49e  mov     [rbp+180h+var_40], rax
0x18000a4a5  xor     r15d, r15d
0x18000a4a8  lea     rax, [rsp+280h+Name]
0x18000a4ad  mov     esi, 104h
0x18000a4b2  mov     [r8], r15
0x18000a4b5  mov     edx, esi
0x18000a4b7  mov     r14, r8
0x18000a4ba  mov     r9d, 7FFFFFFEh
0x18000a4c0  test    r9, r9
0x18000a4c3  jz      short loc_18000A4E4
0x18000a4c5  movzx   r8d, word ptr [rcx]
0x18000a4c9  test    r8w, r8w
0x18000a4cd  jz      short loc_18000A4E4
0x18000a4cf  mov     [rax], r8w
0x18000a4d3  add     rcx, 2
0x18000a4d7  add     rax, 2
0x18000a4db  dec     r9
0x18000a4de  sub     rdx, 1
0x18000a4e2  jnz     short loc_18000A4C0
0x18000a4e4  test    rdx, rdx
0x18000a4e7  lea     rcx, [rax-2]
0x18000a4eb  lea     r8, aP0; "_p0"
0x18000a4f2  mov     rdx, rsi; unsigned __int64
0x18000a4f5  cmovnz  rcx, rax
0x18000a4f9  mov     [rcx], r15w
0x18000a4fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a502  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a507  lea     r8, [rsp+280h+Name]; lpName
0x18000a50c  xor     edx, edx; bInheritHandle
0x18000a50e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a513  call    cs:__imp_OpenSemaphoreW
0x18000a519  mov     rbx, rax
0x18000a51c  test    rax, rax
0x18000a51f  jz      loc_18000A662
0x18000a525  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a52a  mov     [rsp+280h+var_25C], r15d
0x18000a52f  mov     rcx, rax; hHandle
0x18000a532  mov     [rsp+280h+var_260], r15d; int
0x18000a537  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a53c  mov     edi, eax
0x18000a53e  test    eax, eax
0x18000a540  jns     short loc_18000A575
0x18000a542  mov     rcx, [rbp+188h]; this
0x18000a549  lea     r8, aWil; "wil"
0x18000a550  mov     r9d, eax; char *
0x18000a553  mov     edx, 0D6h; void *
0x18000a558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a55d  mov     rcx, rbx; hObject
0x18000a560  call    cs:__imp_CloseHandle
0x18000a566  test    eax, eax
0x18000a568  jz      loc_18000A6DE
0x18000a56e  mov     eax, edi
0x18000a570  jmp     loc_18000A689
0x18000a575  lea     r8, asc_180065A98; "h"
0x18000a57c  mov     rdx, rsi; unsigned __int64
0x18000a57f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a584  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a589  lea     r8, [rsp+280h+Name]; lpName
0x18000a58e  xor     edx, edx; bInheritHandle
0x18000a590  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a595  call    cs:__imp_OpenSemaphoreW
0x18000a59b  mov     rdi, rax
0x18000a59e  test    rax, rax
0x18000a5a1  jz      loc_18000A636
0x18000a5a7  lea     rdx, [rsp+280h+var_260]; int *
0x18000a5ac  mov     rcx, rax; hHandle
0x18000a5af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a5b4  mov     esi, eax
0x18000a5b6  test    eax, eax
0x18000a5b8  jns     short loc_18000A5FE
0x18000a5ba  mov     rcx, [rbp+188h]; this
0x18000a5c1  lea     r8, aWil; "wil"
0x18000a5c8  mov     r9d, eax; char *
0x18000a5cb  mov     edx, 0DEh; void *
0x18000a5d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5d5  mov     rcx, rdi; hObject
0x18000a5d8  call    cs:__imp_CloseHandle
0x18000a5de  test    eax, eax
0x18000a5e0  jz      loc_18000A6F0
0x18000a5e6  mov     rcx, rbx; hObject
0x18000a5e9  call    cs:__imp_CloseHandle
0x18000a5ef  test    eax, eax
0x18000a5f1  jz      loc_18000A702
0x18000a5f7  mov     eax, esi
0x18000a5f9  jmp     loc_18000A689
0x18000a5fe  mov     rcx, rdi; hObject
0x18000a601  call    cs:__imp_CloseHandle
0x18000a607  test    eax, eax
0x18000a609  jz      loc_18000A6A8
0x18000a60f  movsxd  rax, [rsp+280h+var_25C]
0x18000a614  movsxd  rcx, [rsp+280h+var_260]
0x18000a619  shl     rcx, 1Fh
0x18000a61d  or      rcx, rax
0x18000a620  mov     [r14], rcx
0x18000a623  mov     rcx, rbx; hObject
0x18000a626  call    cs:__imp_CloseHandle
0x18000a62c  test    eax, eax
0x18000a62e  jz      loc_18000A6BA
0x18000a634  jmp     short loc_18000A66D
0x18000a636  mov     rcx, [rbp+188h]; this
0x18000a63d  lea     r8, aWil; "wil"
0x18000a644  mov     edx, 0DCh; void *
0x18000a649  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a64e  mov     rcx, rbx; hObject
0x18000a651  mov     edi, eax
0x18000a653  call    cs:__imp_CloseHandle
0x18000a659  test    eax, eax
0x18000a65b  jz      short loc_18000A6CC
0x18000a65d  jmp     loc_18000A56E
0x18000a662  call    cs:__imp_GetLastError
0x18000a668  cmp     eax, 2
0x18000a66b  jnz     short loc_18000A671
0x18000a66d  xor     eax, eax
0x18000a66f  jmp     short loc_18000A689
0x18000a671  mov     rcx, [rbp+188h]; this
0x18000a678  lea     r8, aWil; "wil"
0x18000a67f  mov     edx, 0D0h; void *
0x18000a684  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a689  mov     rcx, [rbp+180h+var_40]
0x18000a690  xor     rcx, rsp; StackCookie
0x18000a693  call    __security_check_cookie
0x18000a698  add     rsp, 258h
0x18000a69f  pop     r15
0x18000a6a1  pop     r14
0x18000a6a3  pop     rdi
0x18000a6a4  pop     rsi
0x18000a6a5  pop     rbx
0x18000a6a6  pop     rbp
0x18000a6a7  retn
0x18000a6a8  mov     rcx, [rbp+188h]; this
0x18000a6af  mov     edx, 0A0Bh; void *
0x18000a6b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6ba  mov     rcx, [rbp+188h]; this
0x18000a6c1  mov     edx, 0A0Bh; void *
0x18000a6c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6cc  mov     rcx, [rbp+188h]; this
0x18000a6d3  mov     edx, 0A0Bh; void *
0x18000a6d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6de  mov     rcx, [rbp+188h]; this
0x18000a6e5  mov     edx, 0A0Bh; void *
0x18000a6ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6f0  mov     rcx, [rbp+188h]; this
0x18000a6f7  mov     edx, 0A0Bh; void *
0x18000a6fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a702  mov     rcx, [rbp+188h]; this
0x18000a709  mov     edx, 0A0Bh; void *
0x18000a70e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
