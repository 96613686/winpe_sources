# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800085ec`
- end: `0x180008884`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ac8`
- `0x180003e98`

## callees

- `0x1800016d0`
- `0x180005434`
- `0x180007664`
- `0x180007684`
- `0x1800080c8`
- `0x1800085ec`
- `0x180008ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008683`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008705`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008683`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087c3`

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
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x1800085ec  push    rbp
0x1800085ee  push    rbx
0x1800085ef  push    rsi
0x1800085f0  push    rdi
0x1800085f1  push    r14
0x1800085f3  push    r15
0x1800085f5  lea     rbp, [rsp-158h]
0x1800085fd  sub     rsp, 258h
0x180008604  mov     rax, cs:__security_cookie
0x18000860b  xor     rax, rsp
0x18000860e  mov     [rbp+180h+var_40], rax
0x180008615  xor     r15d, r15d
0x180008618  lea     rax, [rsp+280h+Name]
0x18000861d  mov     esi, 104h
0x180008622  mov     [r8], r15
0x180008625  mov     edx, esi
0x180008627  mov     r14, r8
0x18000862a  mov     r9d, 7FFFFFFEh
0x180008630  test    r9, r9
0x180008633  jz      short loc_180008654
0x180008635  movzx   r8d, word ptr [rcx]
0x180008639  test    r8w, r8w
0x18000863d  jz      short loc_180008654
0x18000863f  mov     [rax], r8w
0x180008643  add     rcx, 2
0x180008647  add     rax, 2
0x18000864b  dec     r9
0x18000864e  sub     rdx, 1
0x180008652  jnz     short loc_180008630
0x180008654  test    rdx, rdx
0x180008657  lea     rcx, [rax-2]
0x18000865b  lea     r8, aP0; "_p0"
0x180008662  mov     rdx, rsi; unsigned __int64
0x180008665  cmovnz  rcx, rax
0x180008669  mov     [rcx], r15w
0x18000866d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008672  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008677  lea     r8, [rsp+280h+Name]; lpName
0x18000867c  xor     edx, edx; bInheritHandle
0x18000867e  mov     ecx, 1F0003h; dwDesiredAccess
0x180008683  call    cs:__imp_OpenSemaphoreW
0x180008689  mov     rbx, rax
0x18000868c  test    rax, rax
0x18000868f  jz      loc_1800087D2
0x180008695  lea     rdx, [rsp+280h+var_25C]; int *
0x18000869a  mov     [rsp+280h+var_25C], r15d
0x18000869f  mov     rcx, rax; hHandle
0x1800086a2  mov     [rsp+280h+var_260], r15d; int
0x1800086a7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800086ac  mov     edi, eax
0x1800086ae  test    eax, eax
0x1800086b0  jns     short loc_1800086E5
0x1800086b2  mov     rcx, [rbp+188h]; this
0x1800086b9  lea     r8, aWil; "wil"
0x1800086c0  mov     r9d, eax; char *
0x1800086c3  mov     edx, 0D6h; void *
0x1800086c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086cd  mov     rcx, rbx; hObject
0x1800086d0  call    cs:__imp_CloseHandle
0x1800086d6  test    eax, eax
0x1800086d8  jz      loc_18000884E
0x1800086de  mov     eax, edi
0x1800086e0  jmp     loc_1800087F9
0x1800086e5  lea     r8, asc_180025338; "h"
0x1800086ec  mov     rdx, rsi; unsigned __int64
0x1800086ef  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800086f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800086f9  lea     r8, [rsp+280h+Name]; lpName
0x1800086fe  xor     edx, edx; bInheritHandle
0x180008700  mov     ecx, 1F0003h; dwDesiredAccess
0x180008705  call    cs:__imp_OpenSemaphoreW
0x18000870b  mov     rdi, rax
0x18000870e  test    rax, rax
0x180008711  jz      loc_1800087A6
0x180008717  lea     rdx, [rsp+280h+var_260]; int *
0x18000871c  mov     rcx, rax; hHandle
0x18000871f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008724  mov     esi, eax
0x180008726  test    eax, eax
0x180008728  jns     short loc_18000876E
0x18000872a  mov     rcx, [rbp+188h]; this
0x180008731  lea     r8, aWil; "wil"
0x180008738  mov     r9d, eax; char *
0x18000873b  mov     edx, 0DEh; void *
0x180008740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008745  mov     rcx, rdi; hObject
0x180008748  call    cs:__imp_CloseHandle
0x18000874e  test    eax, eax
0x180008750  jz      loc_180008860
0x180008756  mov     rcx, rbx; hObject
0x180008759  call    cs:__imp_CloseHandle
0x18000875f  test    eax, eax
0x180008761  jz      loc_180008872
0x180008767  mov     eax, esi
0x180008769  jmp     loc_1800087F9
0x18000876e  mov     rcx, rdi; hObject
0x180008771  call    cs:__imp_CloseHandle
0x180008777  test    eax, eax
0x180008779  jz      loc_180008818
0x18000877f  movsxd  rax, [rsp+280h+var_25C]
0x180008784  movsxd  rcx, [rsp+280h+var_260]
0x180008789  shl     rcx, 1Fh
0x18000878d  or      rcx, rax
0x180008790  mov     [r14], rcx
0x180008793  mov     rcx, rbx; hObject
0x180008796  call    cs:__imp_CloseHandle
0x18000879c  test    eax, eax
0x18000879e  jz      loc_18000882A
0x1800087a4  jmp     short loc_1800087DD
0x1800087a6  mov     rcx, [rbp+188h]; this
0x1800087ad  lea     r8, aWil; "wil"
0x1800087b4  mov     edx, 0DCh; void *
0x1800087b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800087be  mov     rcx, rbx; hObject
0x1800087c1  mov     edi, eax
0x1800087c3  call    cs:__imp_CloseHandle
0x1800087c9  test    eax, eax
0x1800087cb  jz      short loc_18000883C
0x1800087cd  jmp     loc_1800086DE
0x1800087d2  call    cs:__imp_GetLastError
0x1800087d8  cmp     eax, 2
0x1800087db  jnz     short loc_1800087E1
0x1800087dd  xor     eax, eax
0x1800087df  jmp     short loc_1800087F9
0x1800087e1  mov     rcx, [rbp+188h]; this
0x1800087e8  lea     r8, aWil; "wil"
0x1800087ef  mov     edx, 0D0h; void *
0x1800087f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800087f9  mov     rcx, [rbp+180h+var_40]
0x180008800  xor     rcx, rsp; StackCookie
0x180008803  call    __security_check_cookie
0x180008808  add     rsp, 258h
0x18000880f  pop     r15
0x180008811  pop     r14
0x180008813  pop     rdi
0x180008814  pop     rsi
0x180008815  pop     rbx
0x180008816  pop     rbp
0x180008817  retn
0x180008818  mov     rcx, [rbp+188h]; this
0x18000881f  mov     edx, 0A0Bh; void *
0x180008824  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000882a  mov     rcx, [rbp+188h]; this
0x180008831  mov     edx, 0A0Bh; void *
0x180008836  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000883c  mov     rcx, [rbp+188h]; this
0x180008843  mov     edx, 0A0Bh; void *
0x180008848  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000884e  mov     rcx, [rbp+188h]; this
0x180008855  mov     edx, 0A0Bh; void *
0x18000885a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008860  mov     rcx, [rbp+188h]; this
0x180008867  mov     edx, 0A0Bh; void *
0x18000886c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008872  mov     rcx, [rbp+188h]; this
0x180008879  mov     edx, 0A0Bh; void *
0x18000887e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
