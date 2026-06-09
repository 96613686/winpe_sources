# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140016ef8`
- end: `0x140017164`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14001339c`
- `0x140013740`

## callees

- `0x140014bc0`
- `0x140016700`
- `0x140016720`
- `0x140016b40`
- `0x140016ef8`
- `0x1400176dc`
- `0x140018350`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400170b9`
- `KERNEL32!GetLastError` at `0x1400170b9`
- `KERNEL32!OpenSemaphoreW` at `0x140016f8c`
- `KERNEL32!OpenSemaphoreW` at `0x140017001`
- `KERNEL32!OpenSemaphoreW` at `0x140016f8c`
- `KERNEL32!OpenSemaphoreW` at `0x140017001`
- `KERNEL32!CloseHandle` at `0x140016fd2`
- `KERNEL32!CloseHandle` at `0x14001703d`
- `KERNEL32!CloseHandle` at `0x14001704e`
- `KERNEL32!CloseHandle` at `0x140017063`
- `KERNEL32!CloseHandle` at `0x140017088`
- `KERNEL32!CloseHandle` at `0x1400170aa`
- `KERNEL32!CloseHandle` at `0x140016fd2`
- `KERNEL32!CloseHandle` at `0x14001703d`
- `KERNEL32!CloseHandle` at `0x14001704e`
- `KERNEL32!CloseHandle` at `0x140017063`
- `KERNEL32!CloseHandle` at `0x140017088`
- `KERNEL32!CloseHandle` at `0x1400170aa`

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
0x140016ef8  push    rbp
0x140016efa  push    rbx
0x140016efb  push    rsi
0x140016efc  push    rdi
0x140016efd  push    r14
0x140016eff  push    r15
0x140016f01  lea     rbp, [rsp-158h]
0x140016f09  sub     rsp, 258h
0x140016f10  mov     rax, cs:__security_cookie
0x140016f17  xor     rax, rsp
0x140016f1a  mov     [rbp+180h+var_40], rax
0x140016f21  xor     r15d, r15d
0x140016f24  lea     rax, [rsp+280h+Name]
0x140016f29  mov     [r8], r15
0x140016f2c  mov     r14, r8
0x140016f2f  mov     edx, 104h
0x140016f34  mov     r9d, 7FFFFFFEh
0x140016f3a  test    r9, r9
0x140016f3d  jz      short loc_140016F5E
0x140016f3f  movzx   r8d, word ptr [rcx]
0x140016f43  test    r8w, r8w
0x140016f47  jz      short loc_140016F5E
0x140016f49  mov     [rax], r8w
0x140016f4d  add     rcx, 2
0x140016f51  add     rax, 2
0x140016f55  dec     r9
0x140016f58  sub     rdx, 1; unsigned __int64
0x140016f5c  jnz     short loc_140016F3A
0x140016f5e  test    rdx, rdx
0x140016f61  lea     rcx, [rax-2]
0x140016f65  lea     r8, aP0; "_p0"
0x140016f6c  cmovnz  rcx, rax
0x140016f70  mov     [rcx], r15w
0x140016f74  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140016f79  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140016f7e  mov     esi, 1F0003h
0x140016f83  lea     r8, [rsp+280h+Name]; lpName
0x140016f88  mov     ecx, esi; dwDesiredAccess
0x140016f8a  xor     edx, edx; bInheritHandle
0x140016f8c  call    cs:__imp_OpenSemaphoreW
0x140016f92  mov     rbx, rax
0x140016f95  test    rax, rax
0x140016f98  jz      loc_1400170B9
0x140016f9e  lea     rdx, [rsp+280h+var_25C]; int *
0x140016fa3  mov     [rsp+280h+var_25C], r15d
0x140016fa8  mov     rcx, rax; hHandle
0x140016fab  mov     [rsp+280h+var_260], r15d; int
0x140016fb0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140016fb5  mov     edi, eax
0x140016fb7  test    eax, eax
0x140016fb9  jns     short loc_140016FE7
0x140016fbb  mov     rcx, [rbp+188h]; this
0x140016fc2  mov     r9d, eax; char *
0x140016fc5  mov     edx, 0D6h; void *
0x140016fca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016fcf  mov     rcx, rbx; hObject
0x140016fd2  call    cs:__imp_CloseHandle
0x140016fd8  test    eax, eax
0x140016fda  jz      loc_14001712E
0x140016fe0  mov     eax, edi
0x140016fe2  jmp     loc_1400170D9
0x140016fe7  lea     r8, asc_14001CC88; "h"
0x140016fee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140016ff3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140016ff8  lea     r8, [rsp+280h+Name]; lpName
0x140016ffd  xor     edx, edx; bInheritHandle
0x140016fff  mov     ecx, esi; dwDesiredAccess
0x140017001  call    cs:__imp_OpenSemaphoreW
0x140017007  mov     rdi, rax
0x14001700a  test    rax, rax
0x14001700d  jz      loc_140017094
0x140017013  lea     rdx, [rsp+280h+var_260]; int *
0x140017018  mov     rcx, rax; hHandle
0x14001701b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140017020  mov     esi, eax
0x140017022  test    eax, eax
0x140017024  jns     short loc_140017060
0x140017026  mov     rcx, [rbp+188h]; this
0x14001702d  mov     r9d, eax; char *
0x140017030  mov     edx, 0DEh; void *
0x140017035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001703a  mov     rcx, rdi; hObject
0x14001703d  call    cs:__imp_CloseHandle
0x140017043  test    eax, eax
0x140017045  jz      loc_140017140
0x14001704b  mov     rcx, rbx; hObject
0x14001704e  call    cs:__imp_CloseHandle
0x140017054  test    eax, eax
0x140017056  jz      loc_140017152
0x14001705c  mov     eax, esi
0x14001705e  jmp     short loc_1400170D9
0x140017060  mov     rcx, rdi; hObject
0x140017063  call    cs:__imp_CloseHandle
0x140017069  test    eax, eax
0x14001706b  jz      loc_1400170F8
0x140017071  movsxd  rax, [rsp+280h+var_25C]
0x140017076  movsxd  rcx, [rsp+280h+var_260]
0x14001707b  shl     rcx, 1Fh
0x14001707f  or      rcx, rax
0x140017082  mov     [r14], rcx
0x140017085  mov     rcx, rbx; hObject
0x140017088  call    cs:__imp_CloseHandle
0x14001708e  test    eax, eax
0x140017090  jz      short loc_14001710A
0x140017092  jmp     short loc_1400170C4
0x140017094  mov     rcx, [rbp+188h]; this
0x14001709b  mov     edx, 0DCh; void *
0x1400170a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400170a5  mov     rcx, rbx; hObject
0x1400170a8  mov     edi, eax
0x1400170aa  call    cs:__imp_CloseHandle
0x1400170b0  test    eax, eax
0x1400170b2  jz      short loc_14001711C
0x1400170b4  jmp     loc_140016FE0
0x1400170b9  call    cs:__imp_GetLastError
0x1400170bf  cmp     eax, 2
0x1400170c2  jnz     short loc_1400170C8
0x1400170c4  xor     eax, eax
0x1400170c6  jmp     short loc_1400170D9
0x1400170c8  mov     rcx, [rbp+188h]; this
0x1400170cf  mov     edx, 0D0h; void *
0x1400170d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400170d9  mov     rcx, [rbp+180h+var_40]
0x1400170e0  xor     rcx, rsp; StackCookie
0x1400170e3  call    __security_check_cookie
0x1400170e8  add     rsp, 258h
0x1400170ef  pop     r15
0x1400170f1  pop     r14
0x1400170f3  pop     rdi
0x1400170f4  pop     rsi
0x1400170f5  pop     rbx
0x1400170f6  pop     rbp
0x1400170f7  retn
0x1400170f8  mov     rcx, [rbp+188h]; this
0x1400170ff  mov     edx, 0A0Bh; void *
0x140017104  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001710a  mov     rcx, [rbp+188h]; this
0x140017111  mov     edx, 0A0Bh; void *
0x140017116  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001711c  mov     rcx, [rbp+188h]; this
0x140017123  mov     edx, 0A0Bh; void *
0x140017128  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001712e  mov     rcx, [rbp+188h]; this
0x140017135  mov     edx, 0A0Bh; void *
0x14001713a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140017140  mov     rcx, [rbp+188h]; this
0x140017147  mov     edx, 0A0Bh; void *
0x14001714c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140017152  mov     rcx, [rbp+188h]; this
0x140017159  mov     edx, 0A0Bh; void *
0x14001715e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
