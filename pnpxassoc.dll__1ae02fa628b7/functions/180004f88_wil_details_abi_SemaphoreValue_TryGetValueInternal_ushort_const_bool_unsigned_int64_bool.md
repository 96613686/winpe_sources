# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180004f88`
- end: `0x1800051f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000314c`
- `0x18001085c`

## callees

- `0x180004140`
- `0x180004b10`
- `0x180004b30`
- `0x180004e4c`
- `0x180004f88`
- `0x18000534c`
- `0x180012e00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005149`
- `KERNEL32!GetLastError` at `0x180005149`
- `KERNEL32!OpenSemaphoreW` at `0x18000501c`
- `KERNEL32!OpenSemaphoreW` at `0x180005091`
- `KERNEL32!OpenSemaphoreW` at `0x18000501c`
- `KERNEL32!OpenSemaphoreW` at `0x180005091`
- `KERNEL32!CloseHandle` at `0x180005062`
- `KERNEL32!CloseHandle` at `0x1800050cd`
- `KERNEL32!CloseHandle` at `0x1800050de`
- `KERNEL32!CloseHandle` at `0x1800050f3`
- `KERNEL32!CloseHandle` at `0x180005118`
- `KERNEL32!CloseHandle` at `0x18000513a`
- `KERNEL32!CloseHandle` at `0x180005062`
- `KERNEL32!CloseHandle` at `0x1800050cd`
- `KERNEL32!CloseHandle` at `0x1800050de`
- `KERNEL32!CloseHandle` at `0x1800050f3`
- `KERNEL32!CloseHandle` at `0x180005118`
- `KERNEL32!CloseHandle` at `0x18000513a`

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
0x180004f88  push    rbp
0x180004f8a  push    rbx
0x180004f8b  push    rsi
0x180004f8c  push    rdi
0x180004f8d  push    r14
0x180004f8f  push    r15
0x180004f91  lea     rbp, [rsp-158h]
0x180004f99  sub     rsp, 258h
0x180004fa0  mov     rax, cs:__security_cookie
0x180004fa7  xor     rax, rsp
0x180004faa  mov     [rbp+180h+var_40], rax
0x180004fb1  xor     r15d, r15d
0x180004fb4  lea     rax, [rsp+280h+Name]
0x180004fb9  mov     [r8], r15
0x180004fbc  mov     r14, r8
0x180004fbf  mov     edx, 104h
0x180004fc4  mov     r9d, 7FFFFFFEh
0x180004fca  test    r9, r9
0x180004fcd  jz      short loc_180004FEE
0x180004fcf  movzx   r8d, word ptr [rcx]
0x180004fd3  test    r8w, r8w
0x180004fd7  jz      short loc_180004FEE
0x180004fd9  mov     [rax], r8w
0x180004fdd  add     rcx, 2
0x180004fe1  add     rax, 2
0x180004fe5  dec     r9
0x180004fe8  sub     rdx, 1; unsigned __int64
0x180004fec  jnz     short loc_180004FCA
0x180004fee  test    rdx, rdx
0x180004ff1  lea     rcx, [rax-2]
0x180004ff5  lea     r8, aP0; "_p0"
0x180004ffc  cmovnz  rcx, rax
0x180005000  mov     [rcx], r15w
0x180005004  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005009  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000500e  mov     esi, 1F0003h
0x180005013  lea     r8, [rsp+280h+Name]; lpName
0x180005018  mov     ecx, esi; dwDesiredAccess
0x18000501a  xor     edx, edx; bInheritHandle
0x18000501c  call    cs:__imp_OpenSemaphoreW
0x180005022  mov     rbx, rax
0x180005025  test    rax, rax
0x180005028  jz      loc_180005149
0x18000502e  lea     rdx, [rsp+280h+var_25C]; int *
0x180005033  mov     [rsp+280h+var_25C], r15d
0x180005038  mov     rcx, rax; hHandle
0x18000503b  mov     [rsp+280h+var_260], r15d; int
0x180005040  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005045  mov     edi, eax
0x180005047  test    eax, eax
0x180005049  jns     short loc_180005077
0x18000504b  mov     rcx, [rbp+188h]; this
0x180005052  mov     r9d, eax; char *
0x180005055  mov     edx, 0D6h; void *
0x18000505a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000505f  mov     rcx, rbx; hObject
0x180005062  call    cs:__imp_CloseHandle
0x180005068  test    eax, eax
0x18000506a  jz      loc_1800051BE
0x180005070  mov     eax, edi
0x180005072  jmp     loc_180005169
0x180005077  lea     r8, asc_180016548; "h"
0x18000507e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005083  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005088  lea     r8, [rsp+280h+Name]; lpName
0x18000508d  xor     edx, edx; bInheritHandle
0x18000508f  mov     ecx, esi; dwDesiredAccess
0x180005091  call    cs:__imp_OpenSemaphoreW
0x180005097  mov     rdi, rax
0x18000509a  test    rax, rax
0x18000509d  jz      loc_180005124
0x1800050a3  lea     rdx, [rsp+280h+var_260]; int *
0x1800050a8  mov     rcx, rax; hHandle
0x1800050ab  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800050b0  mov     esi, eax
0x1800050b2  test    eax, eax
0x1800050b4  jns     short loc_1800050F0
0x1800050b6  mov     rcx, [rbp+188h]; this
0x1800050bd  mov     r9d, eax; char *
0x1800050c0  mov     edx, 0DEh; void *
0x1800050c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050ca  mov     rcx, rdi; hObject
0x1800050cd  call    cs:__imp_CloseHandle
0x1800050d3  test    eax, eax
0x1800050d5  jz      loc_1800051D0
0x1800050db  mov     rcx, rbx; hObject
0x1800050de  call    cs:__imp_CloseHandle
0x1800050e4  test    eax, eax
0x1800050e6  jz      loc_1800051E2
0x1800050ec  mov     eax, esi
0x1800050ee  jmp     short loc_180005169
0x1800050f0  mov     rcx, rdi; hObject
0x1800050f3  call    cs:__imp_CloseHandle
0x1800050f9  test    eax, eax
0x1800050fb  jz      loc_180005188
0x180005101  movsxd  rax, [rsp+280h+var_25C]
0x180005106  movsxd  rcx, [rsp+280h+var_260]
0x18000510b  shl     rcx, 1Fh
0x18000510f  or      rcx, rax
0x180005112  mov     [r14], rcx
0x180005115  mov     rcx, rbx; hObject
0x180005118  call    cs:__imp_CloseHandle
0x18000511e  test    eax, eax
0x180005120  jz      short loc_18000519A
0x180005122  jmp     short loc_180005154
0x180005124  mov     rcx, [rbp+188h]; this
0x18000512b  mov     edx, 0DCh; void *
0x180005130  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005135  mov     rcx, rbx; hObject
0x180005138  mov     edi, eax
0x18000513a  call    cs:__imp_CloseHandle
0x180005140  test    eax, eax
0x180005142  jz      short loc_1800051AC
0x180005144  jmp     loc_180005070
0x180005149  call    cs:__imp_GetLastError
0x18000514f  cmp     eax, 2
0x180005152  jnz     short loc_180005158
0x180005154  xor     eax, eax
0x180005156  jmp     short loc_180005169
0x180005158  mov     rcx, [rbp+188h]; this
0x18000515f  mov     edx, 0D0h; void *
0x180005164  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005169  mov     rcx, [rbp+180h+var_40]
0x180005170  xor     rcx, rsp; StackCookie
0x180005173  call    __security_check_cookie
0x180005178  add     rsp, 258h
0x18000517f  pop     r15
0x180005181  pop     r14
0x180005183  pop     rdi
0x180005184  pop     rsi
0x180005185  pop     rbx
0x180005186  pop     rbp
0x180005187  retn
0x180005188  mov     rcx, [rbp+188h]; this
0x18000518f  mov     edx, 0A0Bh; void *
0x180005194  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000519a  mov     rcx, [rbp+188h]; this
0x1800051a1  mov     edx, 0A0Bh; void *
0x1800051a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051ac  mov     rcx, [rbp+188h]; this
0x1800051b3  mov     edx, 0A0Bh; void *
0x1800051b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051be  mov     rcx, [rbp+188h]; this
0x1800051c5  mov     edx, 0A0Bh; void *
0x1800051ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051d0  mov     rcx, [rbp+188h]; this
0x1800051d7  mov     edx, 0A0Bh; void *
0x1800051dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051e2  mov     rcx, [rbp+188h]; this
0x1800051e9  mov     edx, 0A0Bh; void *
0x1800051ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
