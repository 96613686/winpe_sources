# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800152b8`
- end: `0x18001559a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `738`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008cc4`
- `0x1800090b8`

## callees

- `0x1800026b0`
- `0x18000dbc8`
- `0x180011384`
- `0x1800113a4`
- `0x180013fb8`
- `0x1800152b8`
- `0x1800162e8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800153aa`
- `KERNEL32!CloseHandle` at `0x180015428`
- `KERNEL32!CloseHandle` at `0x18001543f`
- `KERNEL32!CloseHandle` at `0x18001545d`
- `KERNEL32!CloseHandle` at `0x180015488`
- `KERNEL32!CloseHandle` at `0x1800154bb`
- `KERNEL32!CloseHandle` at `0x1800153aa`
- `KERNEL32!CloseHandle` at `0x180015428`
- `KERNEL32!CloseHandle` at `0x18001543f`
- `KERNEL32!CloseHandle` at `0x18001545d`
- `KERNEL32!CloseHandle` at `0x180015488`
- `KERNEL32!CloseHandle` at `0x1800154bb`
- `KERNEL32!OpenSemaphoreW` at `0x180015357`
- `KERNEL32!OpenSemaphoreW` at `0x1800153df`
- `KERNEL32!OpenSemaphoreW` at `0x180015357`
- `KERNEL32!OpenSemaphoreW` at `0x1800153df`
- `KERNEL32!GetLastError` at `0x1800154d4`
- `KERNEL32!GetLastError` at `0x1800154d4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  const char *v33; // r9
  int v34; // [rsp+28h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v19);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v34);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v27, v28);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (unsigned int)"wil", (const char *)(unsigned int)v21, v34);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v23, v24);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x1800152b8  mov     rax, rsp
0x1800152bb  mov     [rax+8], rbx
0x1800152bf  mov     [rax+10h], rsi
0x1800152c3  mov     [rax+20h], rdi
0x1800152c7  push    rbp
0x1800152c8  push    r14
0x1800152ca  push    r15
0x1800152cc  lea     rbp, [rax-168h]
0x1800152d3  sub     rsp, 250h
0x1800152da  mov     rax, cs:__security_cookie
0x1800152e1  xor     rax, rsp
0x1800152e4  mov     [rbp+160h+var_20], rax
0x1800152eb  xor     r15d, r15d
0x1800152ee  lea     rax, [rsp+260h+Name]
0x1800152f3  mov     [r8], r15
0x1800152f6  lea     rdx, [rsp+260h+Name]
0x1800152fb  sub     rcx, rax
0x1800152fe  mov     r14, r8
0x180015301  mov     r9d, 104h
0x180015307  lea     rax, [r9+7FFFFEFAh]
0x18001530e  test    rax, rax
0x180015311  jz      short loc_180015329
0x180015313  movzx   eax, word ptr [rcx+rdx]
0x180015317  test    ax, ax
0x18001531a  jz      short loc_180015329
0x18001531c  mov     [rdx], ax
0x18001531f  add     rdx, 2; unsigned __int64
0x180015323  sub     r9, 1
0x180015327  jnz     short loc_180015307
0x180015329  test    r9, r9
0x18001532c  lea     rax, [rdx-2]
0x180015330  lea     r8, aP0; "_p0"
0x180015337  cmovnz  rax, rdx
0x18001533b  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180015340  mov     [rax], r15w
0x180015344  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015349  mov     esi, 1F0003h
0x18001534e  lea     r8, [rsp+260h+Name]; lpName
0x180015353  mov     ecx, esi; dwDesiredAccess
0x180015355  xor     edx, edx; bInheritHandle
0x180015357  call    cs:__imp_OpenSemaphoreW
0x18001535e  nop     dword ptr [rax+rax+00h]
0x180015363  mov     rbx, rax
0x180015366  test    rax, rax
0x180015369  jz      loc_1800154D4
0x18001536f  lea     rdx, [rsp+260h+var_23C]; int *
0x180015374  mov     [rsp+260h+var_23C], r15d
0x180015379  mov     rcx, rax; hHandle
0x18001537c  mov     [rsp+260h+var_240], r15d; int
0x180015381  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015386  mov     edi, eax
0x180015388  test    eax, eax
0x18001538a  jns     short loc_1800153C5
0x18001538c  mov     rcx, [rbp+168h]; this
0x180015393  lea     r8, aWil; "wil"
0x18001539a  mov     r9d, eax; char *
0x18001539d  mov     edx, 0D3h; void *
0x1800153a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153a7  mov     rcx, rbx; hObject
0x1800153aa  call    cs:__imp_CloseHandle
0x1800153b1  nop     dword ptr [rax+rax+00h]
0x1800153b6  test    eax, eax
0x1800153b8  jz      loc_180015564
0x1800153be  mov     eax, edi
0x1800153c0  jmp     loc_180015501
0x1800153c5  lea     r8, asc_1800264F8; "h"
0x1800153cc  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800153d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800153d6  lea     r8, [rsp+260h+Name]; lpName
0x1800153db  xor     edx, edx; bInheritHandle
0x1800153dd  mov     ecx, esi; dwDesiredAccess
0x1800153df  call    cs:__imp_OpenSemaphoreW
0x1800153e6  nop     dword ptr [rax+rax+00h]
0x1800153eb  mov     rdi, rax
0x1800153ee  test    rax, rax
0x1800153f1  jz      loc_18001549E
0x1800153f7  lea     rdx, [rsp+260h+var_240]; int *
0x1800153fc  mov     rcx, rax; hHandle
0x1800153ff  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015404  mov     esi, eax
0x180015406  test    eax, eax
0x180015408  jns     short loc_18001545A
0x18001540a  mov     rcx, [rbp+168h]; this
0x180015411  lea     r8, aWil; "wil"
0x180015418  mov     r9d, eax; char *
0x18001541b  mov     edx, 0DBh; void *
0x180015420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015425  mov     rcx, rdi; hObject
0x180015428  call    cs:__imp_CloseHandle
0x18001542f  nop     dword ptr [rax+rax+00h]
0x180015434  test    eax, eax
0x180015436  jz      loc_180015576
0x18001543c  mov     rcx, rbx; hObject
0x18001543f  call    cs:__imp_CloseHandle
0x180015446  nop     dword ptr [rax+rax+00h]
0x18001544b  test    eax, eax
0x18001544d  jz      loc_180015588
0x180015453  mov     eax, esi
0x180015455  jmp     loc_180015501
0x18001545a  mov     rcx, rdi; hObject
0x18001545d  call    cs:__imp_CloseHandle
0x180015464  nop     dword ptr [rax+rax+00h]
0x180015469  test    eax, eax
0x18001546b  jz      loc_18001552E
0x180015471  movsxd  rax, [rsp+260h+var_23C]
0x180015476  movsxd  rcx, [rsp+260h+var_240]
0x18001547b  shl     rcx, 1Fh
0x18001547f  or      rcx, rax
0x180015482  mov     [r14], rcx
0x180015485  mov     rcx, rbx; hObject
0x180015488  call    cs:__imp_CloseHandle
0x18001548f  nop     dword ptr [rax+rax+00h]
0x180015494  test    eax, eax
0x180015496  jz      loc_180015540
0x18001549c  jmp     short loc_1800154E5
0x18001549e  mov     rcx, [rbp+168h]; this
0x1800154a5  lea     r8, aWil; "wil"
0x1800154ac  mov     edx, 0D9h; void *
0x1800154b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800154b6  mov     rcx, rbx; hObject
0x1800154b9  mov     edi, eax
0x1800154bb  call    cs:__imp_CloseHandle
0x1800154c2  nop     dword ptr [rax+rax+00h]
0x1800154c7  test    eax, eax
0x1800154c9  jz      loc_180015552
0x1800154cf  jmp     loc_1800153BE
0x1800154d4  call    cs:__imp_GetLastError
0x1800154db  nop     dword ptr [rax+rax+00h]
0x1800154e0  cmp     eax, 2
0x1800154e3  jnz     short loc_1800154E9
0x1800154e5  xor     eax, eax
0x1800154e7  jmp     short loc_180015501
0x1800154e9  mov     rcx, [rbp+168h]; this
0x1800154f0  lea     r8, aWil; "wil"
0x1800154f7  mov     edx, 0CDh; void *
0x1800154fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015501  mov     rcx, [rbp+160h+var_20]
0x180015508  xor     rcx, rsp; StackCookie
0x18001550b  call    __security_check_cookie
0x180015510  lea     r11, [rsp+260h+var_10]
0x180015518  mov     rbx, [r11+20h]
0x18001551c  mov     rsi, [r11+28h]
0x180015520  mov     rdi, [r11+38h]
0x180015524  mov     rsp, r11
0x180015527  pop     r15
0x180015529  pop     r14
0x18001552b  pop     rbp
0x18001552c  retn
0x18001552e  mov     rcx, [rbp+168h]; this
0x180015535  mov     edx, 9DDh; void *
0x18001553a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015540  mov     rcx, [rbp+168h]; this
0x180015547  mov     edx, 9DDh; void *
0x18001554c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015552  mov     rcx, [rbp+168h]; this
0x180015559  mov     edx, 9DDh; void *
0x18001555e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015564  mov     rcx, [rbp+168h]; this
0x18001556b  mov     edx, 9DDh; void *
0x180015570  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015576  mov     rcx, [rbp+168h]; this
0x18001557d  mov     edx, 9DDh; void *
0x180015582  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015588  mov     rcx, [rbp+168h]; this
0x18001558f  mov     edx, 9DDh; void *
0x180015594  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
