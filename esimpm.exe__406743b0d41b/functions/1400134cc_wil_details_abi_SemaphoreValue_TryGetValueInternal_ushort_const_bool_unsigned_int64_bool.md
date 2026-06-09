# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1400134cc`
- end: `0x140013738`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000eb58`
- `0x14000eefc`

## callees

- `0x140002f60`
- `0x140010444`
- `0x140012534`
- `0x140012554`
- `0x140012f98`
- `0x1400134cc`
- `0x140013d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140013560`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400135d5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140013560`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400135d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001368d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001368d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400135a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001365c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001367e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400135a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001365c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001367e`

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
0x1400134cc  push    rbp
0x1400134ce  push    rbx
0x1400134cf  push    rsi
0x1400134d0  push    rdi
0x1400134d1  push    r14
0x1400134d3  push    r15
0x1400134d5  lea     rbp, [rsp-158h]
0x1400134dd  sub     rsp, 258h
0x1400134e4  mov     rax, cs:__security_cookie
0x1400134eb  xor     rax, rsp
0x1400134ee  mov     [rbp+180h+var_40], rax
0x1400134f5  xor     r15d, r15d
0x1400134f8  lea     rax, [rsp+280h+Name]
0x1400134fd  mov     [r8], r15
0x140013500  mov     r14, r8
0x140013503  mov     edx, 104h
0x140013508  mov     r9d, 7FFFFFFEh
0x14001350e  test    r9, r9
0x140013511  jz      short loc_140013532
0x140013513  movzx   r8d, word ptr [rcx]
0x140013517  test    r8w, r8w
0x14001351b  jz      short loc_140013532
0x14001351d  mov     [rax], r8w
0x140013521  add     rcx, 2
0x140013525  add     rax, 2
0x140013529  dec     r9
0x14001352c  sub     rdx, 1; unsigned __int64
0x140013530  jnz     short loc_14001350E
0x140013532  test    rdx, rdx
0x140013535  lea     rcx, [rax-2]
0x140013539  lea     r8, aP0; "_p0"
0x140013540  cmovnz  rcx, rax
0x140013544  mov     [rcx], r15w
0x140013548  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14001354d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140013552  mov     esi, 1F0003h
0x140013557  lea     r8, [rsp+280h+Name]; lpName
0x14001355c  mov     ecx, esi; dwDesiredAccess
0x14001355e  xor     edx, edx; bInheritHandle
0x140013560  call    cs:__imp_OpenSemaphoreW
0x140013566  mov     rbx, rax
0x140013569  test    rax, rax
0x14001356c  jz      loc_14001368D
0x140013572  lea     rdx, [rsp+280h+var_25C]; int *
0x140013577  mov     [rsp+280h+var_25C], r15d
0x14001357c  mov     rcx, rax; hHandle
0x14001357f  mov     [rsp+280h+var_260], r15d; int
0x140013584  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140013589  mov     edi, eax
0x14001358b  test    eax, eax
0x14001358d  jns     short loc_1400135BB
0x14001358f  mov     rcx, [rbp+188h]; this
0x140013596  mov     r9d, eax; char *
0x140013599  mov     edx, 0D6h; void *
0x14001359e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400135a3  mov     rcx, rbx; hObject
0x1400135a6  call    cs:__imp_CloseHandle
0x1400135ac  test    eax, eax
0x1400135ae  jz      loc_140013702
0x1400135b4  mov     eax, edi
0x1400135b6  jmp     loc_1400136AD
0x1400135bb  lea     r8, asc_14005E780; "h"
0x1400135c2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400135c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400135cc  lea     r8, [rsp+280h+Name]; lpName
0x1400135d1  xor     edx, edx; bInheritHandle
0x1400135d3  mov     ecx, esi; dwDesiredAccess
0x1400135d5  call    cs:__imp_OpenSemaphoreW
0x1400135db  mov     rdi, rax
0x1400135de  test    rax, rax
0x1400135e1  jz      loc_140013668
0x1400135e7  lea     rdx, [rsp+280h+var_260]; int *
0x1400135ec  mov     rcx, rax; hHandle
0x1400135ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400135f4  mov     esi, eax
0x1400135f6  test    eax, eax
0x1400135f8  jns     short loc_140013634
0x1400135fa  mov     rcx, [rbp+188h]; this
0x140013601  mov     r9d, eax; char *
0x140013604  mov     edx, 0DEh; void *
0x140013609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001360e  mov     rcx, rdi; hObject
0x140013611  call    cs:__imp_CloseHandle
0x140013617  test    eax, eax
0x140013619  jz      loc_140013714
0x14001361f  mov     rcx, rbx; hObject
0x140013622  call    cs:__imp_CloseHandle
0x140013628  test    eax, eax
0x14001362a  jz      loc_140013726
0x140013630  mov     eax, esi
0x140013632  jmp     short loc_1400136AD
0x140013634  mov     rcx, rdi; hObject
0x140013637  call    cs:__imp_CloseHandle
0x14001363d  test    eax, eax
0x14001363f  jz      loc_1400136CC
0x140013645  movsxd  rax, [rsp+280h+var_25C]
0x14001364a  movsxd  rcx, [rsp+280h+var_260]
0x14001364f  shl     rcx, 1Fh
0x140013653  or      rcx, rax
0x140013656  mov     [r14], rcx
0x140013659  mov     rcx, rbx; hObject
0x14001365c  call    cs:__imp_CloseHandle
0x140013662  test    eax, eax
0x140013664  jz      short loc_1400136DE
0x140013666  jmp     short loc_140013698
0x140013668  mov     rcx, [rbp+188h]; this
0x14001366f  mov     edx, 0DCh; void *
0x140013674  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140013679  mov     rcx, rbx; hObject
0x14001367c  mov     edi, eax
0x14001367e  call    cs:__imp_CloseHandle
0x140013684  test    eax, eax
0x140013686  jz      short loc_1400136F0
0x140013688  jmp     loc_1400135B4
0x14001368d  call    cs:__imp_GetLastError
0x140013693  cmp     eax, 2
0x140013696  jnz     short loc_14001369C
0x140013698  xor     eax, eax
0x14001369a  jmp     short loc_1400136AD
0x14001369c  mov     rcx, [rbp+188h]; this
0x1400136a3  mov     edx, 0D0h; void *
0x1400136a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400136ad  mov     rcx, [rbp+180h+var_40]
0x1400136b4  xor     rcx, rsp; StackCookie
0x1400136b7  call    __security_check_cookie
0x1400136bc  add     rsp, 258h
0x1400136c3  pop     r15
0x1400136c5  pop     r14
0x1400136c7  pop     rdi
0x1400136c8  pop     rsi
0x1400136c9  pop     rbx
0x1400136ca  pop     rbp
0x1400136cb  retn
0x1400136cc  mov     rcx, [rbp+188h]; this
0x1400136d3  mov     edx, 0A0Bh; void *
0x1400136d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136de  mov     rcx, [rbp+188h]; this
0x1400136e5  mov     edx, 0A0Bh; void *
0x1400136ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136f0  mov     rcx, [rbp+188h]; this
0x1400136f7  mov     edx, 0A0Bh; void *
0x1400136fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013702  mov     rcx, [rbp+188h]; this
0x140013709  mov     edx, 0A0Bh; void *
0x14001370e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013714  mov     rcx, [rbp+188h]; this
0x14001371b  mov     edx, 0A0Bh; void *
0x140013720  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013726  mov     rcx, [rbp+188h]; this
0x14001372d  mov     edx, 0A0Bh; void *
0x140013732  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
