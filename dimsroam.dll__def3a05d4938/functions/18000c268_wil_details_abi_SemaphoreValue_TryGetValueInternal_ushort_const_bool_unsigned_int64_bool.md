# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c268`
- end: `0x18000c4d4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000870c`
- `0x180008ab0`

## callees

- `0x180009f30`
- `0x18000ba70`
- `0x18000ba90`
- `0x18000beb0`
- `0x18000c268`
- `0x18000ca4c`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c41a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c41a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c2fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c371`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c2fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c371`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
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
0x18000c268  push    rbp
0x18000c26a  push    rbx
0x18000c26b  push    rsi
0x18000c26c  push    rdi
0x18000c26d  push    r14
0x18000c26f  push    r15
0x18000c271  lea     rbp, [rsp-158h]
0x18000c279  sub     rsp, 258h
0x18000c280  mov     rax, cs:__security_cookie
0x18000c287  xor     rax, rsp
0x18000c28a  mov     [rbp+180h+var_40], rax
0x18000c291  xor     r15d, r15d
0x18000c294  lea     rax, [rsp+280h+Name]
0x18000c299  mov     [r8], r15
0x18000c29c  mov     r14, r8
0x18000c29f  mov     edx, 104h
0x18000c2a4  mov     r9d, 7FFFFFFEh
0x18000c2aa  test    r9, r9
0x18000c2ad  jz      short loc_18000C2CE
0x18000c2af  movzx   r8d, word ptr [rcx]
0x18000c2b3  test    r8w, r8w
0x18000c2b7  jz      short loc_18000C2CE
0x18000c2b9  mov     [rax], r8w
0x18000c2bd  add     rcx, 2
0x18000c2c1  add     rax, 2
0x18000c2c5  dec     r9
0x18000c2c8  sub     rdx, 1; unsigned __int64
0x18000c2cc  jnz     short loc_18000C2AA
0x18000c2ce  test    rdx, rdx
0x18000c2d1  lea     rcx, [rax-2]
0x18000c2d5  lea     r8, aP0; "_p0"
0x18000c2dc  cmovnz  rcx, rax
0x18000c2e0  mov     [rcx], r15w
0x18000c2e4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c2e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c2ee  mov     esi, 1F0003h
0x18000c2f3  lea     r8, [rsp+280h+Name]; lpName
0x18000c2f8  mov     ecx, esi; dwDesiredAccess
0x18000c2fa  xor     edx, edx; bInheritHandle
0x18000c2fc  call    cs:__imp_OpenSemaphoreW
0x18000c302  mov     rbx, rax
0x18000c305  test    rax, rax
0x18000c308  jz      loc_18000C429
0x18000c30e  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c313  mov     [rsp+280h+var_25C], r15d
0x18000c318  mov     rcx, rax; hHandle
0x18000c31b  mov     [rsp+280h+var_260], r15d; int
0x18000c320  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c325  mov     edi, eax
0x18000c327  test    eax, eax
0x18000c329  jns     short loc_18000C357
0x18000c32b  mov     rcx, [rbp+188h]; this
0x18000c332  mov     r9d, eax; char *
0x18000c335  mov     edx, 0D6h; void *
0x18000c33a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c33f  mov     rcx, rbx; hObject
0x18000c342  call    cs:__imp_CloseHandle
0x18000c348  test    eax, eax
0x18000c34a  jz      loc_18000C49E
0x18000c350  mov     eax, edi
0x18000c352  jmp     loc_18000C449
0x18000c357  lea     r8, asc_180010238; "h"
0x18000c35e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c363  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c368  lea     r8, [rsp+280h+Name]; lpName
0x18000c36d  xor     edx, edx; bInheritHandle
0x18000c36f  mov     ecx, esi; dwDesiredAccess
0x18000c371  call    cs:__imp_OpenSemaphoreW
0x18000c377  mov     rdi, rax
0x18000c37a  test    rax, rax
0x18000c37d  jz      loc_18000C404
0x18000c383  lea     rdx, [rsp+280h+var_260]; int *
0x18000c388  mov     rcx, rax; hHandle
0x18000c38b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c390  mov     esi, eax
0x18000c392  test    eax, eax
0x18000c394  jns     short loc_18000C3D0
0x18000c396  mov     rcx, [rbp+188h]; this
0x18000c39d  mov     r9d, eax; char *
0x18000c3a0  mov     edx, 0DEh; void *
0x18000c3a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3aa  mov     rcx, rdi; hObject
0x18000c3ad  call    cs:__imp_CloseHandle
0x18000c3b3  test    eax, eax
0x18000c3b5  jz      loc_18000C4B0
0x18000c3bb  mov     rcx, rbx; hObject
0x18000c3be  call    cs:__imp_CloseHandle
0x18000c3c4  test    eax, eax
0x18000c3c6  jz      loc_18000C4C2
0x18000c3cc  mov     eax, esi
0x18000c3ce  jmp     short loc_18000C449
0x18000c3d0  mov     rcx, rdi; hObject
0x18000c3d3  call    cs:__imp_CloseHandle
0x18000c3d9  test    eax, eax
0x18000c3db  jz      loc_18000C468
0x18000c3e1  movsxd  rax, [rsp+280h+var_25C]
0x18000c3e6  movsxd  rcx, [rsp+280h+var_260]
0x18000c3eb  shl     rcx, 1Fh
0x18000c3ef  or      rcx, rax
0x18000c3f2  mov     [r14], rcx
0x18000c3f5  mov     rcx, rbx; hObject
0x18000c3f8  call    cs:__imp_CloseHandle
0x18000c3fe  test    eax, eax
0x18000c400  jz      short loc_18000C47A
0x18000c402  jmp     short loc_18000C434
0x18000c404  mov     rcx, [rbp+188h]; this
0x18000c40b  mov     edx, 0DCh; void *
0x18000c410  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c415  mov     rcx, rbx; hObject
0x18000c418  mov     edi, eax
0x18000c41a  call    cs:__imp_CloseHandle
0x18000c420  test    eax, eax
0x18000c422  jz      short loc_18000C48C
0x18000c424  jmp     loc_18000C350
0x18000c429  call    cs:__imp_GetLastError
0x18000c42f  cmp     eax, 2
0x18000c432  jnz     short loc_18000C438
0x18000c434  xor     eax, eax
0x18000c436  jmp     short loc_18000C449
0x18000c438  mov     rcx, [rbp+188h]; this
0x18000c43f  mov     edx, 0D0h; void *
0x18000c444  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c449  mov     rcx, [rbp+180h+var_40]
0x18000c450  xor     rcx, rsp; StackCookie
0x18000c453  call    __security_check_cookie
0x18000c458  add     rsp, 258h
0x18000c45f  pop     r15
0x18000c461  pop     r14
0x18000c463  pop     rdi
0x18000c464  pop     rsi
0x18000c465  pop     rbx
0x18000c466  pop     rbp
0x18000c467  retn
0x18000c468  mov     rcx, [rbp+188h]; this
0x18000c46f  mov     edx, 0A0Bh; void *
0x18000c474  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c47a  mov     rcx, [rbp+188h]; this
0x18000c481  mov     edx, 0A0Bh; void *
0x18000c486  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c48c  mov     rcx, [rbp+188h]; this
0x18000c493  mov     edx, 0A0Bh; void *
0x18000c498  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c49e  mov     rcx, [rbp+188h]; this
0x18000c4a5  mov     edx, 0A0Bh; void *
0x18000c4aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c4b0  mov     rcx, [rbp+188h]; this
0x18000c4b7  mov     edx, 0A0Bh; void *
0x18000c4bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c4c2  mov     rcx, [rbp+188h]; this
0x18000c4c9  mov     edx, 0A0Bh; void *
0x18000c4ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
