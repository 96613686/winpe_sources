# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000952c`
- end: `0x180009798`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a88`

## callees

- `0x180001ef0`
- `0x180006d10`
- `0x180008364`
- `0x180008384`
- `0x1800093b8`
- `0x18000952c`
- `0x1800099b8`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800095c0`
- `KERNEL32!OpenSemaphoreW` at `0x180009635`
- `KERNEL32!OpenSemaphoreW` at `0x1800095c0`
- `KERNEL32!OpenSemaphoreW` at `0x180009635`
- `KERNEL32!GetLastError` at `0x1800096ed`
- `KERNEL32!GetLastError` at `0x1800096ed`
- `KERNEL32!CloseHandle` at `0x180009606`
- `KERNEL32!CloseHandle` at `0x180009671`
- `KERNEL32!CloseHandle` at `0x180009682`
- `KERNEL32!CloseHandle` at `0x180009697`
- `KERNEL32!CloseHandle` at `0x1800096bc`
- `KERNEL32!CloseHandle` at `0x1800096de`
- `KERNEL32!CloseHandle` at `0x180009606`
- `KERNEL32!CloseHandle` at `0x180009671`
- `KERNEL32!CloseHandle` at `0x180009682`
- `KERNEL32!CloseHandle` at `0x180009697`
- `KERNEL32!CloseHandle` at `0x1800096bc`
- `KERNEL32!CloseHandle` at `0x1800096de`

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
0x18000952c  push    rbp
0x18000952e  push    rbx
0x18000952f  push    rsi
0x180009530  push    rdi
0x180009531  push    r14
0x180009533  push    r15
0x180009535  lea     rbp, [rsp-158h]
0x18000953d  sub     rsp, 258h
0x180009544  mov     rax, cs:__security_cookie
0x18000954b  xor     rax, rsp
0x18000954e  mov     [rbp+180h+var_40], rax
0x180009555  xor     r15d, r15d
0x180009558  lea     rax, [rsp+280h+Name]
0x18000955d  mov     [r8], r15
0x180009560  mov     r14, r8
0x180009563  mov     edx, 104h
0x180009568  mov     r9d, 7FFFFFFEh
0x18000956e  test    r9, r9
0x180009571  jz      short loc_180009592
0x180009573  movzx   r8d, word ptr [rcx]
0x180009577  test    r8w, r8w
0x18000957b  jz      short loc_180009592
0x18000957d  mov     [rax], r8w
0x180009581  add     rcx, 2
0x180009585  add     rax, 2
0x180009589  dec     r9
0x18000958c  sub     rdx, 1; unsigned __int64
0x180009590  jnz     short loc_18000956E
0x180009592  test    rdx, rdx
0x180009595  lea     rcx, [rax-2]
0x180009599  lea     r8, aP0; "_p0"
0x1800095a0  cmovnz  rcx, rax
0x1800095a4  mov     [rcx], r15w
0x1800095a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800095ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800095b2  mov     esi, 1F0003h
0x1800095b7  lea     r8, [rsp+280h+Name]; lpName
0x1800095bc  mov     ecx, esi; dwDesiredAccess
0x1800095be  xor     edx, edx; bInheritHandle
0x1800095c0  call    cs:__imp_OpenSemaphoreW
0x1800095c6  mov     rbx, rax
0x1800095c9  test    rax, rax
0x1800095cc  jz      loc_1800096ED
0x1800095d2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800095d7  mov     [rsp+280h+var_25C], r15d
0x1800095dc  mov     rcx, rax; hHandle
0x1800095df  mov     [rsp+280h+var_260], r15d; int
0x1800095e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800095e9  mov     edi, eax
0x1800095eb  test    eax, eax
0x1800095ed  jns     short loc_18000961B
0x1800095ef  mov     rcx, [rbp+188h]; this
0x1800095f6  mov     r9d, eax; char *
0x1800095f9  mov     edx, 0D6h; void *
0x1800095fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009603  mov     rcx, rbx; hObject
0x180009606  call    cs:__imp_CloseHandle
0x18000960c  test    eax, eax
0x18000960e  jz      loc_180009762
0x180009614  mov     eax, edi
0x180009616  jmp     loc_18000970D
0x18000961b  lea     r8, asc_18000D1F8; "h"
0x180009622  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009627  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000962c  lea     r8, [rsp+280h+Name]; lpName
0x180009631  xor     edx, edx; bInheritHandle
0x180009633  mov     ecx, esi; dwDesiredAccess
0x180009635  call    cs:__imp_OpenSemaphoreW
0x18000963b  mov     rdi, rax
0x18000963e  test    rax, rax
0x180009641  jz      loc_1800096C8
0x180009647  lea     rdx, [rsp+280h+var_260]; int *
0x18000964c  mov     rcx, rax; hHandle
0x18000964f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009654  mov     esi, eax
0x180009656  test    eax, eax
0x180009658  jns     short loc_180009694
0x18000965a  mov     rcx, [rbp+188h]; this
0x180009661  mov     r9d, eax; char *
0x180009664  mov     edx, 0DEh; void *
0x180009669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000966e  mov     rcx, rdi; hObject
0x180009671  call    cs:__imp_CloseHandle
0x180009677  test    eax, eax
0x180009679  jz      loc_180009774
0x18000967f  mov     rcx, rbx; hObject
0x180009682  call    cs:__imp_CloseHandle
0x180009688  test    eax, eax
0x18000968a  jz      loc_180009786
0x180009690  mov     eax, esi
0x180009692  jmp     short loc_18000970D
0x180009694  mov     rcx, rdi; hObject
0x180009697  call    cs:__imp_CloseHandle
0x18000969d  test    eax, eax
0x18000969f  jz      loc_18000972C
0x1800096a5  movsxd  rax, [rsp+280h+var_25C]
0x1800096aa  movsxd  rcx, [rsp+280h+var_260]
0x1800096af  shl     rcx, 1Fh
0x1800096b3  or      rcx, rax
0x1800096b6  mov     [r14], rcx
0x1800096b9  mov     rcx, rbx; hObject
0x1800096bc  call    cs:__imp_CloseHandle
0x1800096c2  test    eax, eax
0x1800096c4  jz      short loc_18000973E
0x1800096c6  jmp     short loc_1800096F8
0x1800096c8  mov     rcx, [rbp+188h]; this
0x1800096cf  mov     edx, 0DCh; void *
0x1800096d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800096d9  mov     rcx, rbx; hObject
0x1800096dc  mov     edi, eax
0x1800096de  call    cs:__imp_CloseHandle
0x1800096e4  test    eax, eax
0x1800096e6  jz      short loc_180009750
0x1800096e8  jmp     loc_180009614
0x1800096ed  call    cs:__imp_GetLastError
0x1800096f3  cmp     eax, 2
0x1800096f6  jnz     short loc_1800096FC
0x1800096f8  xor     eax, eax
0x1800096fa  jmp     short loc_18000970D
0x1800096fc  mov     rcx, [rbp+188h]; this
0x180009703  mov     edx, 0D0h; void *
0x180009708  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000970d  mov     rcx, [rbp+180h+var_40]
0x180009714  xor     rcx, rsp; StackCookie
0x180009717  call    __security_check_cookie
0x18000971c  add     rsp, 258h
0x180009723  pop     r15
0x180009725  pop     r14
0x180009727  pop     rdi
0x180009728  pop     rsi
0x180009729  pop     rbx
0x18000972a  pop     rbp
0x18000972b  retn
0x18000972c  mov     rcx, [rbp+188h]; this
0x180009733  mov     edx, 0A0Bh; void *
0x180009738  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000973e  mov     rcx, [rbp+188h]; this
0x180009745  mov     edx, 0A0Bh; void *
0x18000974a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009750  mov     rcx, [rbp+188h]; this
0x180009757  mov     edx, 0A0Bh; void *
0x18000975c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009762  mov     rcx, [rbp+188h]; this
0x180009769  mov     edx, 0A0Bh; void *
0x18000976e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009774  mov     rcx, [rbp+188h]; this
0x18000977b  mov     edx, 0A0Bh; void *
0x180009780  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009786  mov     rcx, [rbp+188h]; this
0x18000978d  mov     edx, 0A0Bh; void *
0x180009792  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
