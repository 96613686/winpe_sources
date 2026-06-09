# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d36c`
- end: `0x18000d5d8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b59c`

## callees

- `0x180001ce0`
- `0x18000c520`
- `0x18000cf64`
- `0x18000cf84`
- `0x18000d230`
- `0x18000d36c`
- `0x18000d72c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d52d`
- `KERNEL32!GetLastError` at `0x18000d52d`
- `KERNEL32!CloseHandle` at `0x18000d446`
- `KERNEL32!CloseHandle` at `0x18000d4b1`
- `KERNEL32!CloseHandle` at `0x18000d4c2`
- `KERNEL32!CloseHandle` at `0x18000d4d7`
- `KERNEL32!CloseHandle` at `0x18000d4fc`
- `KERNEL32!CloseHandle` at `0x18000d51e`
- `KERNEL32!CloseHandle` at `0x18000d446`
- `KERNEL32!CloseHandle` at `0x18000d4b1`
- `KERNEL32!CloseHandle` at `0x18000d4c2`
- `KERNEL32!CloseHandle` at `0x18000d4d7`
- `KERNEL32!CloseHandle` at `0x18000d4fc`
- `KERNEL32!CloseHandle` at `0x18000d51e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d475`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d475`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  __int64 v19; // r8
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int64 v35; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000d36c  push    rbp
0x18000d36e  push    rbx
0x18000d36f  push    rsi
0x18000d370  push    rdi
0x18000d371  push    r14
0x18000d373  push    r15
0x18000d375  lea     rbp, [rsp-158h]
0x18000d37d  sub     rsp, 258h
0x18000d384  mov     rax, cs:__security_cookie
0x18000d38b  xor     rax, rsp
0x18000d38e  mov     [rbp+180h+var_40], rax
0x18000d395  xor     r15d, r15d
0x18000d398  lea     rax, [rsp+280h+Name]
0x18000d39d  mov     [r8], r15
0x18000d3a0  mov     r14, r8
0x18000d3a3  mov     edx, 104h
0x18000d3a8  mov     r9d, 7FFFFFFEh
0x18000d3ae  test    r9, r9
0x18000d3b1  jz      short loc_18000D3D2
0x18000d3b3  movzx   r8d, word ptr [rcx]
0x18000d3b7  test    r8w, r8w
0x18000d3bb  jz      short loc_18000D3D2
0x18000d3bd  mov     [rax], r8w
0x18000d3c1  add     rcx, 2
0x18000d3c5  add     rax, 2
0x18000d3c9  dec     r9
0x18000d3cc  sub     rdx, 1; unsigned __int64
0x18000d3d0  jnz     short loc_18000D3AE
0x18000d3d2  test    rdx, rdx
0x18000d3d5  lea     rcx, [rax-2]
0x18000d3d9  lea     r8, aP0; "_p0"
0x18000d3e0  cmovnz  rcx, rax
0x18000d3e4  mov     [rcx], r15w
0x18000d3e8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d3ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d3f2  mov     esi, 1F0003h
0x18000d3f7  lea     r8, [rsp+280h+Name]; lpName
0x18000d3fc  mov     ecx, esi; dwDesiredAccess
0x18000d3fe  xor     edx, edx; bInheritHandle
0x18000d400  call    cs:__imp_OpenSemaphoreW
0x18000d406  mov     rbx, rax
0x18000d409  test    rax, rax
0x18000d40c  jz      loc_18000D52D
0x18000d412  lea     rdx, [rsp+280h+var_25C]; int *
0x18000d417  mov     [rsp+280h+var_25C], r15d
0x18000d41c  mov     rcx, rax; hHandle
0x18000d41f  mov     [rsp+280h+var_260], r15d; int
0x18000d424  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d429  mov     edi, eax
0x18000d42b  test    eax, eax
0x18000d42d  jns     short loc_18000D45B
0x18000d42f  mov     rcx, [rbp+188h]; this
0x18000d436  mov     r9d, eax; char *
0x18000d439  mov     edx, 0D6h; void *
0x18000d43e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d443  mov     rcx, rbx; hObject
0x18000d446  call    cs:__imp_CloseHandle
0x18000d44c  test    eax, eax
0x18000d44e  jz      loc_18000D5A2
0x18000d454  mov     eax, edi
0x18000d456  jmp     loc_18000D54D
0x18000d45b  lea     r8, asc_18000FD88; "h"
0x18000d462  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d467  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d46c  lea     r8, [rsp+280h+Name]; lpName
0x18000d471  xor     edx, edx; bInheritHandle
0x18000d473  mov     ecx, esi; dwDesiredAccess
0x18000d475  call    cs:__imp_OpenSemaphoreW
0x18000d47b  mov     rdi, rax
0x18000d47e  test    rax, rax
0x18000d481  jz      loc_18000D508
0x18000d487  lea     rdx, [rsp+280h+var_260]; int *
0x18000d48c  mov     rcx, rax; hHandle
0x18000d48f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d494  mov     esi, eax
0x18000d496  test    eax, eax
0x18000d498  jns     short loc_18000D4D4
0x18000d49a  mov     rcx, [rbp+188h]; this
0x18000d4a1  mov     r9d, eax; char *
0x18000d4a4  mov     edx, 0DEh; void *
0x18000d4a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4ae  mov     rcx, rdi; hObject
0x18000d4b1  call    cs:__imp_CloseHandle
0x18000d4b7  test    eax, eax
0x18000d4b9  jz      loc_18000D5B4
0x18000d4bf  mov     rcx, rbx; hObject
0x18000d4c2  call    cs:__imp_CloseHandle
0x18000d4c8  test    eax, eax
0x18000d4ca  jz      loc_18000D5C6
0x18000d4d0  mov     eax, esi
0x18000d4d2  jmp     short loc_18000D54D
0x18000d4d4  mov     rcx, rdi; hObject
0x18000d4d7  call    cs:__imp_CloseHandle
0x18000d4dd  test    eax, eax
0x18000d4df  jz      loc_18000D56C
0x18000d4e5  movsxd  rax, [rsp+280h+var_25C]
0x18000d4ea  movsxd  rcx, [rsp+280h+var_260]
0x18000d4ef  shl     rcx, 1Fh
0x18000d4f3  or      rcx, rax
0x18000d4f6  mov     [r14], rcx
0x18000d4f9  mov     rcx, rbx; hObject
0x18000d4fc  call    cs:__imp_CloseHandle
0x18000d502  test    eax, eax
0x18000d504  jz      short loc_18000D57E
0x18000d506  jmp     short loc_18000D538
0x18000d508  mov     rcx, [rbp+188h]; this
0x18000d50f  mov     edx, 0DCh; void *
0x18000d514  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d519  mov     rcx, rbx; hObject
0x18000d51c  mov     edi, eax
0x18000d51e  call    cs:__imp_CloseHandle
0x18000d524  test    eax, eax
0x18000d526  jz      short loc_18000D590
0x18000d528  jmp     loc_18000D454
0x18000d52d  call    cs:__imp_GetLastError
0x18000d533  cmp     eax, 2
0x18000d536  jnz     short loc_18000D53C
0x18000d538  xor     eax, eax
0x18000d53a  jmp     short loc_18000D54D
0x18000d53c  mov     rcx, [rbp+188h]; this
0x18000d543  mov     edx, 0D0h; void *
0x18000d548  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d54d  mov     rcx, [rbp+180h+var_40]
0x18000d554  xor     rcx, rsp; StackCookie
0x18000d557  call    __security_check_cookie
0x18000d55c  add     rsp, 258h
0x18000d563  pop     r15
0x18000d565  pop     r14
0x18000d567  pop     rdi
0x18000d568  pop     rsi
0x18000d569  pop     rbx
0x18000d56a  pop     rbp
0x18000d56b  retn
0x18000d56c  mov     rcx, [rbp+188h]; this
0x18000d573  mov     edx, 0A0Bh; void *
0x18000d578  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d57e  mov     rcx, [rbp+188h]; this
0x18000d585  mov     edx, 0A0Bh; void *
0x18000d58a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d590  mov     rcx, [rbp+188h]; this
0x18000d597  mov     edx, 0A0Bh; void *
0x18000d59c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d5a2  mov     rcx, [rbp+188h]; this
0x18000d5a9  mov     edx, 0A0Bh; void *
0x18000d5ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d5b4  mov     rcx, [rbp+188h]; this
0x18000d5bb  mov     edx, 0A0Bh; void *
0x18000d5c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d5c6  mov     rcx, [rbp+188h]; this
0x18000d5cd  mov     edx, 0A0Bh; void *
0x18000d5d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
