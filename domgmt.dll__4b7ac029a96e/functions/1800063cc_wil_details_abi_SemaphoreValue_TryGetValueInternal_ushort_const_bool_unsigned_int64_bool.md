# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800063cc`
- end: `0x18000665b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003db8`

## callees

- `0x180001ba0`
- `0x180004d44`
- `0x180005944`
- `0x180005964`
- `0x180006240`
- `0x1800063cc`
- `0x1800067bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006460`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006460`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000651f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000656d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000659a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000651f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000656d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000659a`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x1800063cc  push    rbp
0x1800063ce  push    rbx
0x1800063cf  push    rsi
0x1800063d0  push    rdi
0x1800063d1  push    r14
0x1800063d3  push    r15
0x1800063d5  lea     rbp, [rsp-158h]
0x1800063dd  sub     rsp, 258h
0x1800063e4  mov     rax, cs:__security_cookie
0x1800063eb  xor     rax, rsp
0x1800063ee  mov     [rbp+180h+var_40], rax
0x1800063f5  xor     r15d, r15d
0x1800063f8  lea     rax, [rsp+280h+Name]
0x1800063fd  mov     [r8], r15
0x180006400  mov     r14, r8
0x180006403  mov     edx, 104h
0x180006408  mov     r9d, 7FFFFFFEh
0x18000640e  test    r9, r9
0x180006411  jz      short loc_180006432
0x180006413  movzx   r8d, word ptr [rcx]
0x180006417  test    r8w, r8w
0x18000641b  jz      short loc_180006432
0x18000641d  mov     [rax], r8w
0x180006421  add     rcx, 2
0x180006425  add     rax, 2
0x180006429  dec     r9
0x18000642c  sub     rdx, 1; unsigned __int64
0x180006430  jnz     short loc_18000640E
0x180006432  test    rdx, rdx
0x180006435  lea     rcx, [rax-2]
0x180006439  lea     r8, aP0; "_p0"
0x180006440  cmovnz  rcx, rax
0x180006444  mov     [rcx], r15w
0x180006448  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000644d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006452  mov     esi, 1F0003h
0x180006457  lea     r8, [rsp+280h+Name]; lpName
0x18000645c  mov     ecx, esi; dwDesiredAccess
0x18000645e  xor     edx, edx; bInheritHandle
0x180006460  call    cs:__imp_OpenSemaphoreW
0x180006466  mov     rbx, rax
0x180006469  test    rax, rax
0x18000646c  jz      loc_1800065A9
0x180006472  lea     rdx, [rsp+280h+var_25C]; int *
0x180006477  mov     [rsp+280h+var_25C], r15d
0x18000647c  mov     rcx, rax; hHandle
0x18000647f  mov     [rsp+280h+var_260], r15d; int
0x180006484  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006489  mov     edi, eax
0x18000648b  test    eax, eax
0x18000648d  jns     short loc_1800064C2
0x18000648f  mov     rcx, [rbp+188h]; this
0x180006496  lea     r8, aWil; "wil"
0x18000649d  mov     r9d, eax; char *
0x1800064a0  mov     edx, 0D6h; void *
0x1800064a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064aa  mov     rcx, rbx; hObject
0x1800064ad  call    cs:__imp_CloseHandle
0x1800064b3  test    eax, eax
0x1800064b5  jz      loc_180006625
0x1800064bb  mov     eax, edi
0x1800064bd  jmp     loc_1800065D0
0x1800064c2  lea     r8, asc_1800106A0; "h"
0x1800064c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800064ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800064d3  lea     r8, [rsp+280h+Name]; lpName
0x1800064d8  xor     edx, edx; bInheritHandle
0x1800064da  mov     ecx, esi; dwDesiredAccess
0x1800064dc  call    cs:__imp_OpenSemaphoreW
0x1800064e2  mov     rdi, rax
0x1800064e5  test    rax, rax
0x1800064e8  jz      loc_18000657D
0x1800064ee  lea     rdx, [rsp+280h+var_260]; int *
0x1800064f3  mov     rcx, rax; hHandle
0x1800064f6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800064fb  mov     esi, eax
0x1800064fd  test    eax, eax
0x1800064ff  jns     short loc_180006545
0x180006501  mov     rcx, [rbp+188h]; this
0x180006508  lea     r8, aWil; "wil"
0x18000650f  mov     r9d, eax; char *
0x180006512  mov     edx, 0DEh; void *
0x180006517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000651c  mov     rcx, rdi; hObject
0x18000651f  call    cs:__imp_CloseHandle
0x180006525  test    eax, eax
0x180006527  jz      loc_180006637
0x18000652d  mov     rcx, rbx; hObject
0x180006530  call    cs:__imp_CloseHandle
0x180006536  test    eax, eax
0x180006538  jz      loc_180006649
0x18000653e  mov     eax, esi
0x180006540  jmp     loc_1800065D0
0x180006545  mov     rcx, rdi; hObject
0x180006548  call    cs:__imp_CloseHandle
0x18000654e  test    eax, eax
0x180006550  jz      loc_1800065EF
0x180006556  movsxd  rax, [rsp+280h+var_25C]
0x18000655b  movsxd  rcx, [rsp+280h+var_260]
0x180006560  shl     rcx, 1Fh
0x180006564  or      rcx, rax
0x180006567  mov     [r14], rcx
0x18000656a  mov     rcx, rbx; hObject
0x18000656d  call    cs:__imp_CloseHandle
0x180006573  test    eax, eax
0x180006575  jz      loc_180006601
0x18000657b  jmp     short loc_1800065B4
0x18000657d  mov     rcx, [rbp+188h]; this
0x180006584  lea     r8, aWil; "wil"
0x18000658b  mov     edx, 0DCh; void *
0x180006590  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006595  mov     rcx, rbx; hObject
0x180006598  mov     edi, eax
0x18000659a  call    cs:__imp_CloseHandle
0x1800065a0  test    eax, eax
0x1800065a2  jz      short loc_180006613
0x1800065a4  jmp     loc_1800064BB
0x1800065a9  call    cs:__imp_GetLastError
0x1800065af  cmp     eax, 2
0x1800065b2  jnz     short loc_1800065B8
0x1800065b4  xor     eax, eax
0x1800065b6  jmp     short loc_1800065D0
0x1800065b8  mov     rcx, [rbp+188h]; this
0x1800065bf  lea     r8, aWil; "wil"
0x1800065c6  mov     edx, 0D0h; void *
0x1800065cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800065d0  mov     rcx, [rbp+180h+var_40]
0x1800065d7  xor     rcx, rsp; StackCookie
0x1800065da  call    __security_check_cookie
0x1800065df  add     rsp, 258h
0x1800065e6  pop     r15
0x1800065e8  pop     r14
0x1800065ea  pop     rdi
0x1800065eb  pop     rsi
0x1800065ec  pop     rbx
0x1800065ed  pop     rbp
0x1800065ee  retn
0x1800065ef  mov     rcx, [rbp+188h]; this
0x1800065f6  mov     edx, 0A0Bh; void *
0x1800065fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006601  mov     rcx, [rbp+188h]; this
0x180006608  mov     edx, 0A0Bh; void *
0x18000660d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006613  mov     rcx, [rbp+188h]; this
0x18000661a  mov     edx, 0A0Bh; void *
0x18000661f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006625  mov     rcx, [rbp+188h]; this
0x18000662c  mov     edx, 0A0Bh; void *
0x180006631  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006637  mov     rcx, [rbp+188h]; this
0x18000663e  mov     edx, 0A0Bh; void *
0x180006643  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006649  mov     rcx, [rbp+188h]; this
0x180006650  mov     edx, 0A0Bh; void *
0x180006655  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
