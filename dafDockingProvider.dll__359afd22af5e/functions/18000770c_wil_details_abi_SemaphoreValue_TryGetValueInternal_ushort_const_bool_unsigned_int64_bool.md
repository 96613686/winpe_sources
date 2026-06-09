# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000770c`
- end: `0x180007978`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037a8`
- `0x180003b4c`

## callees

- `0x180004f04`
- `0x180006a84`
- `0x180006aa4`
- `0x180007328`
- `0x18000770c`
- `0x180007eec`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800077a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007815`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800077a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000789c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000789c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078be`

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
0x18000770c  push    rbp
0x18000770e  push    rbx
0x18000770f  push    rsi
0x180007710  push    rdi
0x180007711  push    r14
0x180007713  push    r15
0x180007715  lea     rbp, [rsp-158h]
0x18000771d  sub     rsp, 258h
0x180007724  mov     rax, cs:__security_cookie
0x18000772b  xor     rax, rsp
0x18000772e  mov     [rbp+180h+var_40], rax
0x180007735  xor     r15d, r15d
0x180007738  lea     rax, [rsp+280h+Name]
0x18000773d  mov     [r8], r15
0x180007740  mov     r14, r8
0x180007743  mov     edx, 104h
0x180007748  mov     r9d, 7FFFFFFEh
0x18000774e  test    r9, r9
0x180007751  jz      short loc_180007772
0x180007753  movzx   r8d, word ptr [rcx]
0x180007757  test    r8w, r8w
0x18000775b  jz      short loc_180007772
0x18000775d  mov     [rax], r8w
0x180007761  add     rcx, 2
0x180007765  add     rax, 2
0x180007769  dec     r9
0x18000776c  sub     rdx, 1; unsigned __int64
0x180007770  jnz     short loc_18000774E
0x180007772  test    rdx, rdx
0x180007775  lea     rcx, [rax-2]
0x180007779  lea     r8, aP0; "_p0"
0x180007780  cmovnz  rcx, rax
0x180007784  mov     [rcx], r15w
0x180007788  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000778d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007792  mov     esi, 1F0003h
0x180007797  lea     r8, [rsp+280h+Name]; lpName
0x18000779c  mov     ecx, esi; dwDesiredAccess
0x18000779e  xor     edx, edx; bInheritHandle
0x1800077a0  call    cs:__imp_OpenSemaphoreW
0x1800077a6  mov     rbx, rax
0x1800077a9  test    rax, rax
0x1800077ac  jz      loc_1800078CD
0x1800077b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800077b7  mov     [rsp+280h+var_25C], r15d
0x1800077bc  mov     rcx, rax; hHandle
0x1800077bf  mov     [rsp+280h+var_260], r15d; int
0x1800077c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800077c9  mov     edi, eax
0x1800077cb  test    eax, eax
0x1800077cd  jns     short loc_1800077FB
0x1800077cf  mov     rcx, [rbp+188h]; this
0x1800077d6  mov     r9d, eax; char *
0x1800077d9  mov     edx, 0D6h; void *
0x1800077de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077e3  mov     rcx, rbx; hObject
0x1800077e6  call    cs:__imp_CloseHandle
0x1800077ec  test    eax, eax
0x1800077ee  jz      loc_180007942
0x1800077f4  mov     eax, edi
0x1800077f6  jmp     loc_1800078ED
0x1800077fb  lea     r8, asc_1800210C8; "h"
0x180007802  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007807  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000780c  lea     r8, [rsp+280h+Name]; lpName
0x180007811  xor     edx, edx; bInheritHandle
0x180007813  mov     ecx, esi; dwDesiredAccess
0x180007815  call    cs:__imp_OpenSemaphoreW
0x18000781b  mov     rdi, rax
0x18000781e  test    rax, rax
0x180007821  jz      loc_1800078A8
0x180007827  lea     rdx, [rsp+280h+var_260]; int *
0x18000782c  mov     rcx, rax; hHandle
0x18000782f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007834  mov     esi, eax
0x180007836  test    eax, eax
0x180007838  jns     short loc_180007874
0x18000783a  mov     rcx, [rbp+188h]; this
0x180007841  mov     r9d, eax; char *
0x180007844  mov     edx, 0DEh; void *
0x180007849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000784e  mov     rcx, rdi; hObject
0x180007851  call    cs:__imp_CloseHandle
0x180007857  test    eax, eax
0x180007859  jz      loc_180007954
0x18000785f  mov     rcx, rbx; hObject
0x180007862  call    cs:__imp_CloseHandle
0x180007868  test    eax, eax
0x18000786a  jz      loc_180007966
0x180007870  mov     eax, esi
0x180007872  jmp     short loc_1800078ED
0x180007874  mov     rcx, rdi; hObject
0x180007877  call    cs:__imp_CloseHandle
0x18000787d  test    eax, eax
0x18000787f  jz      loc_18000790C
0x180007885  movsxd  rax, [rsp+280h+var_25C]
0x18000788a  movsxd  rcx, [rsp+280h+var_260]
0x18000788f  shl     rcx, 1Fh
0x180007893  or      rcx, rax
0x180007896  mov     [r14], rcx
0x180007899  mov     rcx, rbx; hObject
0x18000789c  call    cs:__imp_CloseHandle
0x1800078a2  test    eax, eax
0x1800078a4  jz      short loc_18000791E
0x1800078a6  jmp     short loc_1800078D8
0x1800078a8  mov     rcx, [rbp+188h]; this
0x1800078af  mov     edx, 0DCh; void *
0x1800078b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800078b9  mov     rcx, rbx; hObject
0x1800078bc  mov     edi, eax
0x1800078be  call    cs:__imp_CloseHandle
0x1800078c4  test    eax, eax
0x1800078c6  jz      short loc_180007930
0x1800078c8  jmp     loc_1800077F4
0x1800078cd  call    cs:__imp_GetLastError
0x1800078d3  cmp     eax, 2
0x1800078d6  jnz     short loc_1800078DC
0x1800078d8  xor     eax, eax
0x1800078da  jmp     short loc_1800078ED
0x1800078dc  mov     rcx, [rbp+188h]; this
0x1800078e3  mov     edx, 0D0h; void *
0x1800078e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800078ed  mov     rcx, [rbp+180h+var_40]
0x1800078f4  xor     rcx, rsp; StackCookie
0x1800078f7  call    __security_check_cookie
0x1800078fc  add     rsp, 258h
0x180007903  pop     r15
0x180007905  pop     r14
0x180007907  pop     rdi
0x180007908  pop     rsi
0x180007909  pop     rbx
0x18000790a  pop     rbp
0x18000790b  retn
0x18000790c  mov     rcx, [rbp+188h]; this
0x180007913  mov     edx, 0A0Bh; void *
0x180007918  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000791e  mov     rcx, [rbp+188h]; this
0x180007925  mov     edx, 0A0Bh; void *
0x18000792a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007930  mov     rcx, [rbp+188h]; this
0x180007937  mov     edx, 0A0Bh; void *
0x18000793c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007942  mov     rcx, [rbp+188h]; this
0x180007949  mov     edx, 0A0Bh; void *
0x18000794e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007954  mov     rcx, [rbp+188h]; this
0x18000795b  mov     edx, 0A0Bh; void *
0x180007960  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007966  mov     rcx, [rbp+188h]; this
0x18000796d  mov     edx, 0A0Bh; void *
0x180007972  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
