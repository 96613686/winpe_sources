# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000969c`
- end: `0x180009934`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004418`
- `0x1800047e8`

## callees

- `0x180001cf0`
- `0x180005d94`
- `0x1800081a4`
- `0x1800081c4`
- `0x180008fe8`
- `0x18000969c`
- `0x18000a13c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009882`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009733`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800097b5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009733`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800097b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009873`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000969c  push    rbp
0x18000969e  push    rbx
0x18000969f  push    rsi
0x1800096a0  push    rdi
0x1800096a1  push    r14
0x1800096a3  push    r15
0x1800096a5  lea     rbp, [rsp-158h]
0x1800096ad  sub     rsp, 258h
0x1800096b4  mov     rax, cs:__security_cookie
0x1800096bb  xor     rax, rsp
0x1800096be  mov     [rbp+180h+var_40], rax
0x1800096c5  xor     r15d, r15d
0x1800096c8  lea     rax, [rsp+280h+Name]
0x1800096cd  mov     esi, 104h
0x1800096d2  mov     [r8], r15
0x1800096d5  mov     edx, esi
0x1800096d7  mov     r14, r8
0x1800096da  mov     r9d, 7FFFFFFEh
0x1800096e0  test    r9, r9
0x1800096e3  jz      short loc_180009704
0x1800096e5  movzx   r8d, word ptr [rcx]
0x1800096e9  test    r8w, r8w
0x1800096ed  jz      short loc_180009704
0x1800096ef  mov     [rax], r8w
0x1800096f3  add     rcx, 2
0x1800096f7  add     rax, 2
0x1800096fb  dec     r9
0x1800096fe  sub     rdx, 1
0x180009702  jnz     short loc_1800096E0
0x180009704  test    rdx, rdx
0x180009707  lea     rcx, [rax-2]
0x18000970b  lea     r8, aP0; "_p0"
0x180009712  mov     rdx, rsi; unsigned __int64
0x180009715  cmovnz  rcx, rax
0x180009719  mov     [rcx], r15w
0x18000971d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009722  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009727  lea     r8, [rsp+280h+Name]; lpName
0x18000972c  xor     edx, edx; bInheritHandle
0x18000972e  mov     ecx, 1F0003h; dwDesiredAccess
0x180009733  call    cs:__imp_OpenSemaphoreW
0x180009739  mov     rbx, rax
0x18000973c  test    rax, rax
0x18000973f  jz      loc_180009882
0x180009745  lea     rdx, [rsp+280h+var_25C]; int *
0x18000974a  mov     [rsp+280h+var_25C], r15d
0x18000974f  mov     rcx, rax; hHandle
0x180009752  mov     [rsp+280h+var_260], r15d; int
0x180009757  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000975c  mov     edi, eax
0x18000975e  test    eax, eax
0x180009760  jns     short loc_180009795
0x180009762  mov     rcx, [rbp+188h]; this
0x180009769  lea     r8, aWil; "wil"
0x180009770  mov     r9d, eax; char *
0x180009773  mov     edx, 0D6h; void *
0x180009778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000977d  mov     rcx, rbx; hObject
0x180009780  call    cs:__imp_CloseHandle
0x180009786  test    eax, eax
0x180009788  jz      loc_1800098FE
0x18000978e  mov     eax, edi
0x180009790  jmp     loc_1800098A9
0x180009795  lea     r8, asc_180015D00; "h"
0x18000979c  mov     rdx, rsi; unsigned __int64
0x18000979f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800097a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097a9  lea     r8, [rsp+280h+Name]; lpName
0x1800097ae  xor     edx, edx; bInheritHandle
0x1800097b0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800097b5  call    cs:__imp_OpenSemaphoreW
0x1800097bb  mov     rdi, rax
0x1800097be  test    rax, rax
0x1800097c1  jz      loc_180009856
0x1800097c7  lea     rdx, [rsp+280h+var_260]; int *
0x1800097cc  mov     rcx, rax; hHandle
0x1800097cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800097d4  mov     esi, eax
0x1800097d6  test    eax, eax
0x1800097d8  jns     short loc_18000981E
0x1800097da  mov     rcx, [rbp+188h]; this
0x1800097e1  lea     r8, aWil; "wil"
0x1800097e8  mov     r9d, eax; char *
0x1800097eb  mov     edx, 0DEh; void *
0x1800097f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097f5  mov     rcx, rdi; hObject
0x1800097f8  call    cs:__imp_CloseHandle
0x1800097fe  test    eax, eax
0x180009800  jz      loc_180009910
0x180009806  mov     rcx, rbx; hObject
0x180009809  call    cs:__imp_CloseHandle
0x18000980f  test    eax, eax
0x180009811  jz      loc_180009922
0x180009817  mov     eax, esi
0x180009819  jmp     loc_1800098A9
0x18000981e  mov     rcx, rdi; hObject
0x180009821  call    cs:__imp_CloseHandle
0x180009827  test    eax, eax
0x180009829  jz      loc_1800098C8
0x18000982f  movsxd  rax, [rsp+280h+var_25C]
0x180009834  movsxd  rcx, [rsp+280h+var_260]
0x180009839  shl     rcx, 1Fh
0x18000983d  or      rcx, rax
0x180009840  mov     [r14], rcx
0x180009843  mov     rcx, rbx; hObject
0x180009846  call    cs:__imp_CloseHandle
0x18000984c  test    eax, eax
0x18000984e  jz      loc_1800098DA
0x180009854  jmp     short loc_18000988D
0x180009856  mov     rcx, [rbp+188h]; this
0x18000985d  lea     r8, aWil; "wil"
0x180009864  mov     edx, 0DCh; void *
0x180009869  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000986e  mov     rcx, rbx; hObject
0x180009871  mov     edi, eax
0x180009873  call    cs:__imp_CloseHandle
0x180009879  test    eax, eax
0x18000987b  jz      short loc_1800098EC
0x18000987d  jmp     loc_18000978E
0x180009882  call    cs:__imp_GetLastError
0x180009888  cmp     eax, 2
0x18000988b  jnz     short loc_180009891
0x18000988d  xor     eax, eax
0x18000988f  jmp     short loc_1800098A9
0x180009891  mov     rcx, [rbp+188h]; this
0x180009898  lea     r8, aWil; "wil"
0x18000989f  mov     edx, 0D0h; void *
0x1800098a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800098a9  mov     rcx, [rbp+180h+var_40]
0x1800098b0  xor     rcx, rsp; StackCookie
0x1800098b3  call    __security_check_cookie
0x1800098b8  add     rsp, 258h
0x1800098bf  pop     r15
0x1800098c1  pop     r14
0x1800098c3  pop     rdi
0x1800098c4  pop     rsi
0x1800098c5  pop     rbx
0x1800098c6  pop     rbp
0x1800098c7  retn
0x1800098c8  mov     rcx, [rbp+188h]; this
0x1800098cf  mov     edx, 0A0Bh; void *
0x1800098d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098da  mov     rcx, [rbp+188h]; this
0x1800098e1  mov     edx, 0A0Bh; void *
0x1800098e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098ec  mov     rcx, [rbp+188h]; this
0x1800098f3  mov     edx, 0A0Bh; void *
0x1800098f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098fe  mov     rcx, [rbp+188h]; this
0x180009905  mov     edx, 0A0Bh; void *
0x18000990a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009910  mov     rcx, [rbp+188h]; this
0x180009917  mov     edx, 0A0Bh; void *
0x18000991c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009922  mov     rcx, [rbp+188h]; this
0x180009929  mov     edx, 0A0Bh; void *
0x18000992e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
