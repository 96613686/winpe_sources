# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180012870`
- end: `0x180012b1a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009fdc`
- `0x180016708`

## callees

- `0x180002690`
- `0x18000b654`
- `0x18000e3f4`
- `0x18000e414`
- `0x180012590`
- `0x180012870`
- `0x1800134a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012904`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012985`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012904`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a53`

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
0x180012870  push    rbp
0x180012872  push    rbx
0x180012873  push    rsi
0x180012874  push    rdi
0x180012875  push    r14
0x180012877  push    r15
0x180012879  lea     rbp, [rsp-158h]
0x180012881  sub     rsp, 258h
0x180012888  mov     rax, cs:__security_cookie
0x18001288f  xor     rax, rsp
0x180012892  mov     [rbp+180h+var_40], rax
0x180012899  xor     r15d, r15d
0x18001289c  lea     rax, [rsp+280h+Name]
0x1800128a1  mov     [r8], r15
0x1800128a4  mov     r14, r8
0x1800128a7  mov     edx, 104h
0x1800128ac  mov     r9d, 7FFFFFFEh
0x1800128b2  test    r9, r9
0x1800128b5  jz      short loc_1800128D6
0x1800128b7  movzx   r8d, word ptr [rcx]
0x1800128bb  test    r8w, r8w
0x1800128bf  jz      short loc_1800128D6
0x1800128c1  mov     [rax], r8w
0x1800128c5  add     rcx, 2
0x1800128c9  add     rax, 2
0x1800128cd  dec     r9
0x1800128d0  sub     rdx, 1; unsigned __int64
0x1800128d4  jnz     short loc_1800128B2
0x1800128d6  test    rdx, rdx
0x1800128d9  lea     rcx, [rax-2]
0x1800128dd  lea     r8, aP0; "_p0"
0x1800128e4  cmovnz  rcx, rax
0x1800128e8  mov     [rcx], r15w
0x1800128ec  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800128f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800128f6  mov     esi, 1F0003h
0x1800128fb  lea     r8, [rsp+280h+Name]; lpName
0x180012900  mov     ecx, esi; dwDesiredAccess
0x180012902  xor     edx, edx; bInheritHandle
0x180012904  call    cs:__imp_OpenSemaphoreW
0x18001290b  nop     dword ptr [rax+rax+00h]
0x180012910  mov     rbx, rax
0x180012913  test    rax, rax
0x180012916  jz      loc_180012A68
0x18001291c  lea     rdx, [rsp+280h+var_25C]; int *
0x180012921  mov     [rsp+280h+var_25C], r15d
0x180012926  mov     rcx, rax; hHandle
0x180012929  mov     [rsp+280h+var_260], r15d; int
0x18001292e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012933  mov     edi, eax
0x180012935  test    eax, eax
0x180012937  jns     short loc_18001296B
0x180012939  mov     rcx, [rbp+188h]; this
0x180012940  mov     r9d, eax; char *
0x180012943  mov     edx, 0D6h; void *
0x180012948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001294d  mov     rcx, rbx; hObject
0x180012950  call    cs:__imp_CloseHandle
0x180012957  nop     dword ptr [rax+rax+00h]
0x18001295c  test    eax, eax
0x18001295e  jz      loc_180012AE4
0x180012964  mov     eax, edi
0x180012966  jmp     loc_180012A8E
0x18001296b  lea     r8, asc_18004C780; "h"
0x180012972  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180012977  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001297c  lea     r8, [rsp+280h+Name]; lpName
0x180012981  xor     edx, edx; bInheritHandle
0x180012983  mov     ecx, esi; dwDesiredAccess
0x180012985  call    cs:__imp_OpenSemaphoreW
0x18001298c  nop     dword ptr [rax+rax+00h]
0x180012991  mov     rdi, rax
0x180012994  test    rax, rax
0x180012997  jz      loc_180012A3D
0x18001299d  lea     rdx, [rsp+280h+var_260]; int *
0x1800129a2  mov     rcx, rax; hHandle
0x1800129a5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800129aa  mov     esi, eax
0x1800129ac  test    eax, eax
0x1800129ae  jns     short loc_1800129F9
0x1800129b0  mov     rcx, [rbp+188h]; this
0x1800129b7  mov     r9d, eax; char *
0x1800129ba  mov     edx, 0DEh; void *
0x1800129bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129c4  mov     rcx, rdi; hObject
0x1800129c7  call    cs:__imp_CloseHandle
0x1800129ce  nop     dword ptr [rax+rax+00h]
0x1800129d3  test    eax, eax
0x1800129d5  jz      loc_180012AF6
0x1800129db  mov     rcx, rbx; hObject
0x1800129de  call    cs:__imp_CloseHandle
0x1800129e5  nop     dword ptr [rax+rax+00h]
0x1800129ea  test    eax, eax
0x1800129ec  jz      loc_180012B08
0x1800129f2  mov     eax, esi
0x1800129f4  jmp     loc_180012A8E
0x1800129f9  mov     rcx, rdi; hObject
0x1800129fc  call    cs:__imp_CloseHandle
0x180012a03  nop     dword ptr [rax+rax+00h]
0x180012a08  test    eax, eax
0x180012a0a  jz      loc_180012AAE
0x180012a10  movsxd  rax, [rsp+280h+var_25C]
0x180012a15  movsxd  rcx, [rsp+280h+var_260]
0x180012a1a  shl     rcx, 1Fh
0x180012a1e  or      rcx, rax
0x180012a21  mov     [r14], rcx
0x180012a24  mov     rcx, rbx; hObject
0x180012a27  call    cs:__imp_CloseHandle
0x180012a2e  nop     dword ptr [rax+rax+00h]
0x180012a33  test    eax, eax
0x180012a35  jz      loc_180012AC0
0x180012a3b  jmp     short loc_180012A79
0x180012a3d  mov     rcx, [rbp+188h]; this
0x180012a44  mov     edx, 0DCh; void *
0x180012a49  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012a4e  mov     rcx, rbx; hObject
0x180012a51  mov     edi, eax
0x180012a53  call    cs:__imp_CloseHandle
0x180012a5a  nop     dword ptr [rax+rax+00h]
0x180012a5f  test    eax, eax
0x180012a61  jz      short loc_180012AD2
0x180012a63  jmp     loc_180012964
0x180012a68  call    cs:__imp_GetLastError
0x180012a6f  nop     dword ptr [rax+rax+00h]
0x180012a74  cmp     eax, 2
0x180012a77  jnz     short loc_180012A7D
0x180012a79  xor     eax, eax
0x180012a7b  jmp     short loc_180012A8E
0x180012a7d  mov     rcx, [rbp+188h]; this
0x180012a84  mov     edx, 0D0h; void *
0x180012a89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012a8e  mov     rcx, [rbp+180h+var_40]
0x180012a95  xor     rcx, rsp; StackCookie
0x180012a98  call    __security_check_cookie
0x180012a9d  add     rsp, 258h
0x180012aa4  pop     r15
0x180012aa6  pop     r14
0x180012aa8  pop     rdi
0x180012aa9  pop     rsi
0x180012aaa  pop     rbx
0x180012aab  pop     rbp
0x180012aac  retn
0x180012aae  mov     rcx, [rbp+188h]; this
0x180012ab5  mov     edx, 0A0Bh; void *
0x180012aba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012ac0  mov     rcx, [rbp+188h]; this
0x180012ac7  mov     edx, 0A0Bh; void *
0x180012acc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012ad2  mov     rcx, [rbp+188h]; this
0x180012ad9  mov     edx, 0A0Bh; void *
0x180012ade  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012ae4  mov     rcx, [rbp+188h]; this
0x180012aeb  mov     edx, 0A0Bh; void *
0x180012af0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012af6  mov     rcx, [rbp+188h]; this
0x180012afd  mov     edx, 0A0Bh; void *
0x180012b02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012b08  mov     rcx, [rbp+188h]; this
0x180012b0f  mov     edx, 0A0Bh; void *
0x180012b14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
