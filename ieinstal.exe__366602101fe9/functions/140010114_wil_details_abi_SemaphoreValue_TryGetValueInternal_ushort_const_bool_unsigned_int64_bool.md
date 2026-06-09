# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140010114`
- end: `0x1400103c7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000e5f8`

## callees

- `0x140004314`
- `0x14000f07c`
- `0x14000fe30`
- `0x14000fe50`
- `0x140010114`
- `0x1400104bc`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400101f7`
- `KERNEL32!CloseHandle` at `0x140010274`
- `KERNEL32!CloseHandle` at `0x14001028b`
- `KERNEL32!CloseHandle` at `0x1400102a9`
- `KERNEL32!CloseHandle` at `0x1400102d4`
- `KERNEL32!CloseHandle` at `0x140010300`
- `KERNEL32!CloseHandle` at `0x1400101f7`
- `KERNEL32!CloseHandle` at `0x140010274`
- `KERNEL32!CloseHandle` at `0x14001028b`
- `KERNEL32!CloseHandle` at `0x1400102a9`
- `KERNEL32!CloseHandle` at `0x1400102d4`
- `KERNEL32!CloseHandle` at `0x140010300`
- `KERNEL32!OpenSemaphoreW` at `0x1400101ab`
- `KERNEL32!OpenSemaphoreW` at `0x140010232`
- `KERNEL32!OpenSemaphoreW` at `0x1400101ab`
- `KERNEL32!OpenSemaphoreW` at `0x140010232`
- `KERNEL32!GetLastError` at `0x140010315`
- `KERNEL32!GetLastError` at `0x140010315`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x140010114  push    rbp
0x140010116  push    rbx
0x140010117  push    rsi
0x140010118  push    rdi
0x140010119  push    r14
0x14001011b  push    r15
0x14001011d  lea     rbp, [rsp-158h]
0x140010125  sub     rsp, 258h
0x14001012c  mov     rax, cs:__security_cookie
0x140010133  xor     rax, rsp
0x140010136  mov     [rbp+180h+var_40], rax
0x14001013d  xor     r15d, r15d
0x140010140  lea     rax, [rsp+280h+Name]
0x140010145  mov     esi, 104h
0x14001014a  mov     [r8], r15
0x14001014d  mov     edx, esi
0x14001014f  mov     r14, r8
0x140010152  mov     r9d, 7FFFFFFEh
0x140010158  test    r9, r9
0x14001015b  jz      short loc_14001017C
0x14001015d  movzx   r8d, word ptr [rcx]
0x140010161  test    r8w, r8w
0x140010165  jz      short loc_14001017C
0x140010167  mov     [rax], r8w
0x14001016b  add     rcx, 2
0x14001016f  add     rax, 2
0x140010173  dec     r9
0x140010176  sub     rdx, 1
0x14001017a  jnz     short loc_140010158
0x14001017c  test    rdx, rdx
0x14001017f  lea     rcx, [rax-2]
0x140010183  lea     r8, aP0; "_p0"
0x14001018a  mov     rdx, rsi; unsigned __int64
0x14001018d  cmovnz  rcx, rax
0x140010191  mov     [rcx], r15w
0x140010195  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14001019a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001019f  lea     r8, [rsp+280h+Name]; lpName
0x1400101a4  xor     edx, edx; bInheritHandle
0x1400101a6  mov     ecx, 1F0003h; dwDesiredAccess
0x1400101ab  call    cs:__imp_OpenSemaphoreW
0x1400101b2  nop     dword ptr [rax+rax+00h]
0x1400101b7  mov     rbx, rax
0x1400101ba  test    rax, rax
0x1400101bd  jz      loc_140010315
0x1400101c3  lea     rdx, [rsp+280h+var_25C]; int *
0x1400101c8  mov     [rsp+280h+var_25C], r15d
0x1400101cd  mov     rcx, rax; hHandle
0x1400101d0  mov     [rsp+280h+var_260], r15d; int
0x1400101d5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400101da  mov     edi, eax
0x1400101dc  test    eax, eax
0x1400101de  jns     short loc_140010212
0x1400101e0  mov     rcx, [rbp+188h]; this
0x1400101e7  mov     r9d, eax; char *
0x1400101ea  mov     edx, 0D6h; void *
0x1400101ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400101f4  mov     rcx, rbx; hObject
0x1400101f7  call    cs:__imp_CloseHandle
0x1400101fe  nop     dword ptr [rax+rax+00h]
0x140010203  test    eax, eax
0x140010205  jz      loc_140010391
0x14001020b  mov     eax, edi
0x14001020d  jmp     loc_14001033B
0x140010212  lea     r8, asc_140013960; "h"
0x140010219  mov     rdx, rsi; unsigned __int64
0x14001021c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140010221  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010226  lea     r8, [rsp+280h+Name]; lpName
0x14001022b  xor     edx, edx; bInheritHandle
0x14001022d  mov     ecx, 1F0003h; dwDesiredAccess
0x140010232  call    cs:__imp_OpenSemaphoreW
0x140010239  nop     dword ptr [rax+rax+00h]
0x14001023e  mov     rdi, rax
0x140010241  test    rax, rax
0x140010244  jz      loc_1400102EA
0x14001024a  lea     rdx, [rsp+280h+var_260]; int *
0x14001024f  mov     rcx, rax; hHandle
0x140010252  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140010257  mov     esi, eax
0x140010259  test    eax, eax
0x14001025b  jns     short loc_1400102A6
0x14001025d  mov     rcx, [rbp+188h]; this
0x140010264  mov     r9d, eax; char *
0x140010267  mov     edx, 0DEh; void *
0x14001026c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010271  mov     rcx, rdi; hObject
0x140010274  call    cs:__imp_CloseHandle
0x14001027b  nop     dword ptr [rax+rax+00h]
0x140010280  test    eax, eax
0x140010282  jz      loc_1400103A3
0x140010288  mov     rcx, rbx; hObject
0x14001028b  call    cs:__imp_CloseHandle
0x140010292  nop     dword ptr [rax+rax+00h]
0x140010297  test    eax, eax
0x140010299  jz      loc_1400103B5
0x14001029f  mov     eax, esi
0x1400102a1  jmp     loc_14001033B
0x1400102a6  mov     rcx, rdi; hObject
0x1400102a9  call    cs:__imp_CloseHandle
0x1400102b0  nop     dword ptr [rax+rax+00h]
0x1400102b5  test    eax, eax
0x1400102b7  jz      loc_14001035B
0x1400102bd  movsxd  rax, [rsp+280h+var_25C]
0x1400102c2  movsxd  rcx, [rsp+280h+var_260]
0x1400102c7  shl     rcx, 1Fh
0x1400102cb  or      rcx, rax
0x1400102ce  mov     [r14], rcx
0x1400102d1  mov     rcx, rbx; hObject
0x1400102d4  call    cs:__imp_CloseHandle
0x1400102db  nop     dword ptr [rax+rax+00h]
0x1400102e0  test    eax, eax
0x1400102e2  jz      loc_14001036D
0x1400102e8  jmp     short loc_140010326
0x1400102ea  mov     rcx, [rbp+188h]; this
0x1400102f1  mov     edx, 0DCh; void *
0x1400102f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400102fb  mov     rcx, rbx; hObject
0x1400102fe  mov     edi, eax
0x140010300  call    cs:__imp_CloseHandle
0x140010307  nop     dword ptr [rax+rax+00h]
0x14001030c  test    eax, eax
0x14001030e  jz      short loc_14001037F
0x140010310  jmp     loc_14001020B
0x140010315  call    cs:__imp_GetLastError
0x14001031c  nop     dword ptr [rax+rax+00h]
0x140010321  cmp     eax, 2
0x140010324  jnz     short loc_14001032A
0x140010326  xor     eax, eax
0x140010328  jmp     short loc_14001033B
0x14001032a  mov     rcx, [rbp+188h]; this
0x140010331  mov     edx, 0D0h; void *
0x140010336  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001033b  mov     rcx, [rbp+180h+var_40]
0x140010342  xor     rcx, rsp; StackCookie
0x140010345  call    __security_check_cookie
0x14001034a  add     rsp, 258h
0x140010351  pop     r15
0x140010353  pop     r14
0x140010355  pop     rdi
0x140010356  pop     rsi
0x140010357  pop     rbx
0x140010358  pop     rbp
0x140010359  retn
0x14001035b  mov     rcx, [rbp+188h]; this
0x140010362  mov     edx, 0A0Bh; void *
0x140010367  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001036d  mov     rcx, [rbp+188h]; this
0x140010374  mov     edx, 0A0Bh; void *
0x140010379  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001037f  mov     rcx, [rbp+188h]; this
0x140010386  mov     edx, 0A0Bh; void *
0x14001038b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010391  mov     rcx, [rbp+188h]; this
0x140010398  mov     edx, 0A0Bh; void *
0x14001039d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400103a3  mov     rcx, [rbp+188h]; this
0x1400103aa  mov     edx, 0A0Bh; void *
0x1400103af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400103b5  mov     rcx, [rbp+188h]; this
0x1400103bc  mov     edx, 0A0Bh; void *
0x1400103c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
