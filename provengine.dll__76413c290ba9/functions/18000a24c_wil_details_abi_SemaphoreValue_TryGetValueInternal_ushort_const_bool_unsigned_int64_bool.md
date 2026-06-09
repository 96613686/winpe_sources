# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a24c`
- end: `0x18000a4db`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800075e8`
- `0x180011efc`

## callees

- `0x1800087a8`
- `0x1800098bc`
- `0x1800098dc`
- `0x18000a048`
- `0x18000a24c`
- `0x18000ad18`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a2e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a35c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a2e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a32d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a41a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a32d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a41a`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000a24c  push    rbp
0x18000a24e  push    rbx
0x18000a24f  push    rsi
0x18000a250  push    rdi
0x18000a251  push    r14
0x18000a253  push    r15
0x18000a255  lea     rbp, [rsp-158h]
0x18000a25d  sub     rsp, 258h
0x18000a264  mov     rax, cs:__security_cookie
0x18000a26b  xor     rax, rsp
0x18000a26e  mov     [rbp+180h+var_40], rax
0x18000a275  xor     r15d, r15d
0x18000a278  lea     rax, [rsp+280h+Name]
0x18000a27d  mov     [r8], r15
0x18000a280  mov     r14, r8
0x18000a283  mov     edx, 104h
0x18000a288  mov     r9d, 7FFFFFFEh
0x18000a28e  test    r9, r9
0x18000a291  jz      short loc_18000A2B2
0x18000a293  movzx   r8d, word ptr [rcx]
0x18000a297  test    r8w, r8w
0x18000a29b  jz      short loc_18000A2B2
0x18000a29d  mov     [rax], r8w
0x18000a2a1  add     rcx, 2
0x18000a2a5  add     rax, 2
0x18000a2a9  dec     r9
0x18000a2ac  sub     rdx, 1; unsigned __int64
0x18000a2b0  jnz     short loc_18000A28E
0x18000a2b2  test    rdx, rdx
0x18000a2b5  lea     rcx, [rax-2]
0x18000a2b9  lea     r8, aP0; "_p0"
0x18000a2c0  cmovnz  rcx, rax
0x18000a2c4  mov     [rcx], r15w
0x18000a2c8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a2cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a2d2  mov     esi, 1F0003h
0x18000a2d7  lea     r8, [rsp+280h+Name]; lpName
0x18000a2dc  mov     ecx, esi; dwDesiredAccess
0x18000a2de  xor     edx, edx; bInheritHandle
0x18000a2e0  call    cs:__imp_OpenSemaphoreW
0x18000a2e6  mov     rbx, rax
0x18000a2e9  test    rax, rax
0x18000a2ec  jz      loc_18000A429
0x18000a2f2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a2f7  mov     [rsp+280h+var_25C], r15d
0x18000a2fc  mov     rcx, rax; hHandle
0x18000a2ff  mov     [rsp+280h+var_260], r15d; int
0x18000a304  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a309  mov     edi, eax
0x18000a30b  test    eax, eax
0x18000a30d  jns     short loc_18000A342
0x18000a30f  mov     rcx, [rbp+188h]; this
0x18000a316  lea     r8, aWil; "wil"
0x18000a31d  mov     r9d, eax; char *
0x18000a320  mov     edx, 0D6h; void *
0x18000a325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a32a  mov     rcx, rbx; hObject
0x18000a32d  call    cs:__imp_CloseHandle
0x18000a333  test    eax, eax
0x18000a335  jz      loc_18000A4A5
0x18000a33b  mov     eax, edi
0x18000a33d  jmp     loc_18000A450
0x18000a342  lea     r8, asc_18004B1C8; "h"
0x18000a349  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a34e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a353  lea     r8, [rsp+280h+Name]; lpName
0x18000a358  xor     edx, edx; bInheritHandle
0x18000a35a  mov     ecx, esi; dwDesiredAccess
0x18000a35c  call    cs:__imp_OpenSemaphoreW
0x18000a362  mov     rdi, rax
0x18000a365  test    rax, rax
0x18000a368  jz      loc_18000A3FD
0x18000a36e  lea     rdx, [rsp+280h+var_260]; int *
0x18000a373  mov     rcx, rax; hHandle
0x18000a376  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a37b  mov     esi, eax
0x18000a37d  test    eax, eax
0x18000a37f  jns     short loc_18000A3C5
0x18000a381  mov     rcx, [rbp+188h]; this
0x18000a388  lea     r8, aWil; "wil"
0x18000a38f  mov     r9d, eax; char *
0x18000a392  mov     edx, 0DEh; void *
0x18000a397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a39c  mov     rcx, rdi; hObject
0x18000a39f  call    cs:__imp_CloseHandle
0x18000a3a5  test    eax, eax
0x18000a3a7  jz      loc_18000A4B7
0x18000a3ad  mov     rcx, rbx; hObject
0x18000a3b0  call    cs:__imp_CloseHandle
0x18000a3b6  test    eax, eax
0x18000a3b8  jz      loc_18000A4C9
0x18000a3be  mov     eax, esi
0x18000a3c0  jmp     loc_18000A450
0x18000a3c5  mov     rcx, rdi; hObject
0x18000a3c8  call    cs:__imp_CloseHandle
0x18000a3ce  test    eax, eax
0x18000a3d0  jz      loc_18000A46F
0x18000a3d6  movsxd  rax, [rsp+280h+var_25C]
0x18000a3db  movsxd  rcx, [rsp+280h+var_260]
0x18000a3e0  shl     rcx, 1Fh
0x18000a3e4  or      rcx, rax
0x18000a3e7  mov     [r14], rcx
0x18000a3ea  mov     rcx, rbx; hObject
0x18000a3ed  call    cs:__imp_CloseHandle
0x18000a3f3  test    eax, eax
0x18000a3f5  jz      loc_18000A481
0x18000a3fb  jmp     short loc_18000A434
0x18000a3fd  mov     rcx, [rbp+188h]; this
0x18000a404  lea     r8, aWil; "wil"
0x18000a40b  mov     edx, 0DCh; void *
0x18000a410  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a415  mov     rcx, rbx; hObject
0x18000a418  mov     edi, eax
0x18000a41a  call    cs:__imp_CloseHandle
0x18000a420  test    eax, eax
0x18000a422  jz      short loc_18000A493
0x18000a424  jmp     loc_18000A33B
0x18000a429  call    cs:__imp_GetLastError
0x18000a42f  cmp     eax, 2
0x18000a432  jnz     short loc_18000A438
0x18000a434  xor     eax, eax
0x18000a436  jmp     short loc_18000A450
0x18000a438  mov     rcx, [rbp+188h]; this
0x18000a43f  lea     r8, aWil; "wil"
0x18000a446  mov     edx, 0D0h; void *
0x18000a44b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a450  mov     rcx, [rbp+180h+var_40]
0x18000a457  xor     rcx, rsp; StackCookie
0x18000a45a  call    __security_check_cookie
0x18000a45f  add     rsp, 258h
0x18000a466  pop     r15
0x18000a468  pop     r14
0x18000a46a  pop     rdi
0x18000a46b  pop     rsi
0x18000a46c  pop     rbx
0x18000a46d  pop     rbp
0x18000a46e  retn
0x18000a46f  mov     rcx, [rbp+188h]; this
0x18000a476  mov     edx, 0A0Bh; void *
0x18000a47b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a481  mov     rcx, [rbp+188h]; this
0x18000a488  mov     edx, 0A0Bh; void *
0x18000a48d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a493  mov     rcx, [rbp+188h]; this
0x18000a49a  mov     edx, 0A0Bh; void *
0x18000a49f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4a5  mov     rcx, [rbp+188h]; this
0x18000a4ac  mov     edx, 0A0Bh; void *
0x18000a4b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4b7  mov     rcx, [rbp+188h]; this
0x18000a4be  mov     edx, 0A0Bh; void *
0x18000a4c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4c9  mov     rcx, [rbp+188h]; this
0x18000a4d0  mov     edx, 0A0Bh; void *
0x18000a4d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
