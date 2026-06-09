# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000766c`
- end: `0x1800078e6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004998`
- `0x180009954`

## callees

- `0x1800021d0`
- `0x180005bd4`
- `0x180006b84`
- `0x180006ba4`
- `0x1800074e4`
- `0x18000766c`
- `0x180007a3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007700`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000777c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007700`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000777c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000783b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000783b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000780a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000782c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000774d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000780a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000782c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000766c  push    rbp
0x18000766e  push    rbx
0x18000766f  push    rsi
0x180007670  push    rdi
0x180007671  push    r14
0x180007673  push    r15
0x180007675  lea     rbp, [rsp-158h]
0x18000767d  sub     rsp, 258h
0x180007684  mov     rax, cs:__security_cookie
0x18000768b  xor     rax, rsp
0x18000768e  mov     [rbp+180h+var_40], rax
0x180007695  xor     r15d, r15d
0x180007698  lea     rax, [rsp+280h+Name]
0x18000769d  mov     [r8], r15
0x1800076a0  mov     r14, r8
0x1800076a3  mov     edx, 104h
0x1800076a8  mov     r9d, 7FFFFFFEh
0x1800076ae  test    r9, r9
0x1800076b1  jz      short loc_1800076D2
0x1800076b3  movzx   r8d, word ptr [rcx]
0x1800076b7  test    r8w, r8w
0x1800076bb  jz      short loc_1800076D2
0x1800076bd  mov     [rax], r8w
0x1800076c1  add     rcx, 2
0x1800076c5  add     rax, 2
0x1800076c9  dec     r9
0x1800076cc  sub     rdx, 1; unsigned __int64
0x1800076d0  jnz     short loc_1800076AE
0x1800076d2  test    rdx, rdx
0x1800076d5  lea     rcx, [rax-2]
0x1800076d9  lea     r8, aP0; "_p0"
0x1800076e0  cmovnz  rcx, rax
0x1800076e4  mov     [rcx], r15w
0x1800076e8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800076ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800076f2  mov     esi, 1F0003h
0x1800076f7  lea     r8, [rsp+280h+Name]; lpName
0x1800076fc  mov     ecx, esi; dwDesiredAccess
0x1800076fe  xor     edx, edx; bInheritHandle
0x180007700  call    cs:__imp_OpenSemaphoreW
0x180007706  mov     rbx, rax
0x180007709  test    rax, rax
0x18000770c  jz      loc_18000783B
0x180007712  lea     rdx, [rsp+280h+var_25C]; int *
0x180007717  mov     [rsp+280h+var_25C], r15d
0x18000771c  mov     rcx, rax; hHandle
0x18000771f  mov     [rsp+280h+var_260], r15d; int
0x180007724  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007729  mov     edi, eax
0x18000772b  test    eax, eax
0x18000772d  jns     short loc_180007762
0x18000772f  mov     rcx, [rbp+188h]; this
0x180007736  lea     r8, aWil; "wil"
0x18000773d  mov     r9d, eax; char *
0x180007740  mov     edx, 0D6h; void *
0x180007745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000774a  mov     rcx, rbx; hObject
0x18000774d  call    cs:__imp_CloseHandle
0x180007753  test    eax, eax
0x180007755  jz      loc_1800078B0
0x18000775b  mov     eax, edi
0x18000775d  jmp     loc_18000785B
0x180007762  lea     r8, asc_180037770; "h"
0x180007769  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000776e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007773  lea     r8, [rsp+280h+Name]; lpName
0x180007778  xor     edx, edx; bInheritHandle
0x18000777a  mov     ecx, esi; dwDesiredAccess
0x18000777c  call    cs:__imp_OpenSemaphoreW
0x180007782  mov     rdi, rax
0x180007785  test    rax, rax
0x180007788  jz      loc_180007816
0x18000778e  lea     rdx, [rsp+280h+var_260]; int *
0x180007793  mov     rcx, rax; hHandle
0x180007796  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000779b  mov     esi, eax
0x18000779d  test    eax, eax
0x18000779f  jns     short loc_1800077E2
0x1800077a1  mov     rcx, [rbp+188h]; this
0x1800077a8  lea     r8, aWil; "wil"
0x1800077af  mov     r9d, eax; char *
0x1800077b2  mov     edx, 0DEh; void *
0x1800077b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077bc  mov     rcx, rdi; hObject
0x1800077bf  call    cs:__imp_CloseHandle
0x1800077c5  test    eax, eax
0x1800077c7  jz      loc_1800078C2
0x1800077cd  mov     rcx, rbx; hObject
0x1800077d0  call    cs:__imp_CloseHandle
0x1800077d6  test    eax, eax
0x1800077d8  jz      loc_1800078D4
0x1800077de  mov     eax, esi
0x1800077e0  jmp     short loc_18000785B
0x1800077e2  mov     rcx, rdi; hObject
0x1800077e5  call    cs:__imp_CloseHandle
0x1800077eb  test    eax, eax
0x1800077ed  jz      loc_18000787A
0x1800077f3  movsxd  rax, [rsp+280h+var_25C]
0x1800077f8  movsxd  rcx, [rsp+280h+var_260]
0x1800077fd  shl     rcx, 1Fh
0x180007801  or      rcx, rax
0x180007804  mov     [r14], rcx
0x180007807  mov     rcx, rbx; hObject
0x18000780a  call    cs:__imp_CloseHandle
0x180007810  test    eax, eax
0x180007812  jz      short loc_18000788C
0x180007814  jmp     short loc_180007846
0x180007816  mov     rcx, [rbp+188h]; this
0x18000781d  mov     edx, 0DCh; void *
0x180007822  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007827  mov     rcx, rbx; hObject
0x18000782a  mov     edi, eax
0x18000782c  call    cs:__imp_CloseHandle
0x180007832  test    eax, eax
0x180007834  jz      short loc_18000789E
0x180007836  jmp     loc_18000775B
0x18000783b  call    cs:__imp_GetLastError
0x180007841  cmp     eax, 2
0x180007844  jnz     short loc_18000784A
0x180007846  xor     eax, eax
0x180007848  jmp     short loc_18000785B
0x18000784a  mov     rcx, [rbp+188h]; this
0x180007851  mov     edx, 0D0h; void *
0x180007856  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000785b  mov     rcx, [rbp+180h+var_40]
0x180007862  xor     rcx, rsp; StackCookie
0x180007865  call    __security_check_cookie
0x18000786a  add     rsp, 258h
0x180007871  pop     r15
0x180007873  pop     r14
0x180007875  pop     rdi
0x180007876  pop     rsi
0x180007877  pop     rbx
0x180007878  pop     rbp
0x180007879  retn
0x18000787a  mov     rcx, [rbp+188h]; this
0x180007881  mov     edx, 0A0Bh; void *
0x180007886  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000788c  mov     rcx, [rbp+188h]; this
0x180007893  mov     edx, 0A0Bh; void *
0x180007898  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000789e  mov     rcx, [rbp+188h]; this
0x1800078a5  mov     edx, 0A0Bh; void *
0x1800078aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078b0  mov     rcx, [rbp+188h]; this
0x1800078b7  mov     edx, 0A0Bh; void *
0x1800078bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078c2  mov     rcx, [rbp+188h]; this
0x1800078c9  mov     edx, 0A0Bh; void *
0x1800078ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078d4  mov     rcx, [rbp+188h]; this
0x1800078db  mov     edx, 0A0Bh; void *
0x1800078e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
