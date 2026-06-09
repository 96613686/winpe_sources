# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000986c`
- end: `0x140009ad8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140004668`
- `0x140004a0c`

## callees

- `0x140001ba0`
- `0x1400064d4`
- `0x1400088d4`
- `0x1400088f4`
- `0x140009338`
- `0x14000986c`
- `0x14000a12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009900`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009975`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009900`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009a1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009a1e`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x14000986c  push    rbp
0x14000986e  push    rbx
0x14000986f  push    rsi
0x140009870  push    rdi
0x140009871  push    r14
0x140009873  push    r15
0x140009875  lea     rbp, [rsp-158h]
0x14000987d  sub     rsp, 258h
0x140009884  mov     rax, cs:__security_cookie
0x14000988b  xor     rax, rsp
0x14000988e  mov     [rbp+180h+var_40], rax
0x140009895  xor     r15d, r15d
0x140009898  lea     rax, [rsp+280h+Name]
0x14000989d  mov     [r8], r15
0x1400098a0  mov     r14, r8
0x1400098a3  mov     edx, 104h
0x1400098a8  mov     r9d, 7FFFFFFEh
0x1400098ae  test    r9, r9
0x1400098b1  jz      short loc_1400098D2
0x1400098b3  movzx   r8d, word ptr [rcx]
0x1400098b7  test    r8w, r8w
0x1400098bb  jz      short loc_1400098D2
0x1400098bd  mov     [rax], r8w
0x1400098c1  add     rcx, 2
0x1400098c5  add     rax, 2
0x1400098c9  dec     r9
0x1400098cc  sub     rdx, 1; unsigned __int64
0x1400098d0  jnz     short loc_1400098AE
0x1400098d2  test    rdx, rdx
0x1400098d5  lea     rcx, [rax-2]
0x1400098d9  lea     r8, aP0; "_p0"
0x1400098e0  cmovnz  rcx, rax
0x1400098e4  mov     [rcx], r15w
0x1400098e8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400098ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400098f2  mov     esi, 1F0003h
0x1400098f7  lea     r8, [rsp+280h+Name]; lpName
0x1400098fc  mov     ecx, esi; dwDesiredAccess
0x1400098fe  xor     edx, edx; bInheritHandle
0x140009900  call    cs:__imp_OpenSemaphoreW
0x140009906  mov     rbx, rax
0x140009909  test    rax, rax
0x14000990c  jz      loc_140009A2D
0x140009912  lea     rdx, [rsp+280h+var_25C]; int *
0x140009917  mov     [rsp+280h+var_25C], r15d
0x14000991c  mov     rcx, rax; hHandle
0x14000991f  mov     [rsp+280h+var_260], r15d; int
0x140009924  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140009929  mov     edi, eax
0x14000992b  test    eax, eax
0x14000992d  jns     short loc_14000995B
0x14000992f  mov     rcx, [rbp+188h]; this
0x140009936  mov     r9d, eax; char *
0x140009939  mov     edx, 0D6h; void *
0x14000993e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009943  mov     rcx, rbx; hObject
0x140009946  call    cs:__imp_CloseHandle
0x14000994c  test    eax, eax
0x14000994e  jz      loc_140009AA2
0x140009954  mov     eax, edi
0x140009956  jmp     loc_140009A4D
0x14000995b  lea     r8, asc_1400AD188; "h"
0x140009962  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009967  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000996c  lea     r8, [rsp+280h+Name]; lpName
0x140009971  xor     edx, edx; bInheritHandle
0x140009973  mov     ecx, esi; dwDesiredAccess
0x140009975  call    cs:__imp_OpenSemaphoreW
0x14000997b  mov     rdi, rax
0x14000997e  test    rax, rax
0x140009981  jz      loc_140009A08
0x140009987  lea     rdx, [rsp+280h+var_260]; int *
0x14000998c  mov     rcx, rax; hHandle
0x14000998f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140009994  mov     esi, eax
0x140009996  test    eax, eax
0x140009998  jns     short loc_1400099D4
0x14000999a  mov     rcx, [rbp+188h]; this
0x1400099a1  mov     r9d, eax; char *
0x1400099a4  mov     edx, 0DEh; void *
0x1400099a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400099ae  mov     rcx, rdi; hObject
0x1400099b1  call    cs:__imp_CloseHandle
0x1400099b7  test    eax, eax
0x1400099b9  jz      loc_140009AB4
0x1400099bf  mov     rcx, rbx; hObject
0x1400099c2  call    cs:__imp_CloseHandle
0x1400099c8  test    eax, eax
0x1400099ca  jz      loc_140009AC6
0x1400099d0  mov     eax, esi
0x1400099d2  jmp     short loc_140009A4D
0x1400099d4  mov     rcx, rdi; hObject
0x1400099d7  call    cs:__imp_CloseHandle
0x1400099dd  test    eax, eax
0x1400099df  jz      loc_140009A6C
0x1400099e5  movsxd  rax, [rsp+280h+var_25C]
0x1400099ea  movsxd  rcx, [rsp+280h+var_260]
0x1400099ef  shl     rcx, 1Fh
0x1400099f3  or      rcx, rax
0x1400099f6  mov     [r14], rcx
0x1400099f9  mov     rcx, rbx; hObject
0x1400099fc  call    cs:__imp_CloseHandle
0x140009a02  test    eax, eax
0x140009a04  jz      short loc_140009A7E
0x140009a06  jmp     short loc_140009A38
0x140009a08  mov     rcx, [rbp+188h]; this
0x140009a0f  mov     edx, 0DCh; void *
0x140009a14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009a19  mov     rcx, rbx; hObject
0x140009a1c  mov     edi, eax
0x140009a1e  call    cs:__imp_CloseHandle
0x140009a24  test    eax, eax
0x140009a26  jz      short loc_140009A90
0x140009a28  jmp     loc_140009954
0x140009a2d  call    cs:__imp_GetLastError
0x140009a33  cmp     eax, 2
0x140009a36  jnz     short loc_140009A3C
0x140009a38  xor     eax, eax
0x140009a3a  jmp     short loc_140009A4D
0x140009a3c  mov     rcx, [rbp+188h]; this
0x140009a43  mov     edx, 0D0h; void *
0x140009a48  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009a4d  mov     rcx, [rbp+180h+var_40]
0x140009a54  xor     rcx, rsp; StackCookie
0x140009a57  call    __security_check_cookie
0x140009a5c  add     rsp, 258h
0x140009a63  pop     r15
0x140009a65  pop     r14
0x140009a67  pop     rdi
0x140009a68  pop     rsi
0x140009a69  pop     rbx
0x140009a6a  pop     rbp
0x140009a6b  retn
0x140009a6c  mov     rcx, [rbp+188h]; this
0x140009a73  mov     edx, 0A0Bh; void *
0x140009a78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a7e  mov     rcx, [rbp+188h]; this
0x140009a85  mov     edx, 0A0Bh; void *
0x140009a8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a90  mov     rcx, [rbp+188h]; this
0x140009a97  mov     edx, 0A0Bh; void *
0x140009a9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009aa2  mov     rcx, [rbp+188h]; this
0x140009aa9  mov     edx, 0A0Bh; void *
0x140009aae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009ab4  mov     rcx, [rbp+188h]; this
0x140009abb  mov     edx, 0A0Bh; void *
0x140009ac0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009ac6  mov     rcx, [rbp+188h]; this
0x140009acd  mov     edx, 0A0Bh; void *
0x140009ad2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
