# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800085f8`
- end: `0x180008864`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800039e4`
- `0x180003d88`

## callees

- `0x180001630`
- `0x180005580`
- `0x180007bb4`
- `0x180007bd4`
- `0x180007fec`
- `0x1800085f8`
- `0x180008ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000868c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008701`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000868c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000873d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000874e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000873d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000874e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087aa`

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
0x1800085f8  push    rbp
0x1800085fa  push    rbx
0x1800085fb  push    rsi
0x1800085fc  push    rdi
0x1800085fd  push    r14
0x1800085ff  push    r15
0x180008601  lea     rbp, [rsp-158h]
0x180008609  sub     rsp, 258h
0x180008610  mov     rax, cs:__security_cookie
0x180008617  xor     rax, rsp
0x18000861a  mov     [rbp+180h+var_40], rax
0x180008621  xor     r15d, r15d
0x180008624  lea     rax, [rsp+280h+Name]
0x180008629  mov     [r8], r15
0x18000862c  mov     r14, r8
0x18000862f  mov     edx, 104h
0x180008634  mov     r9d, 7FFFFFFEh
0x18000863a  test    r9, r9
0x18000863d  jz      short loc_18000865E
0x18000863f  movzx   r8d, word ptr [rcx]
0x180008643  test    r8w, r8w
0x180008647  jz      short loc_18000865E
0x180008649  mov     [rax], r8w
0x18000864d  add     rcx, 2
0x180008651  add     rax, 2
0x180008655  dec     r9
0x180008658  sub     rdx, 1; unsigned __int64
0x18000865c  jnz     short loc_18000863A
0x18000865e  test    rdx, rdx
0x180008661  lea     rcx, [rax-2]
0x180008665  lea     r8, aP0; "_p0"
0x18000866c  cmovnz  rcx, rax
0x180008670  mov     [rcx], r15w
0x180008674  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008679  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000867e  mov     esi, 1F0003h
0x180008683  lea     r8, [rsp+280h+Name]; lpName
0x180008688  mov     ecx, esi; dwDesiredAccess
0x18000868a  xor     edx, edx; bInheritHandle
0x18000868c  call    cs:__imp_OpenSemaphoreW
0x180008692  mov     rbx, rax
0x180008695  test    rax, rax
0x180008698  jz      loc_1800087B9
0x18000869e  lea     rdx, [rsp+280h+var_25C]; int *
0x1800086a3  mov     [rsp+280h+var_25C], r15d
0x1800086a8  mov     rcx, rax; hHandle
0x1800086ab  mov     [rsp+280h+var_260], r15d; int
0x1800086b0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800086b5  mov     edi, eax
0x1800086b7  test    eax, eax
0x1800086b9  jns     short loc_1800086E7
0x1800086bb  mov     rcx, [rbp+188h]; this
0x1800086c2  mov     r9d, eax; char *
0x1800086c5  mov     edx, 0D6h; void *
0x1800086ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086cf  mov     rcx, rbx; hObject
0x1800086d2  call    cs:__imp_CloseHandle
0x1800086d8  test    eax, eax
0x1800086da  jz      loc_18000882E
0x1800086e0  mov     eax, edi
0x1800086e2  jmp     loc_1800087D9
0x1800086e7  lea     r8, asc_18000ECA0; "h"
0x1800086ee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800086f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800086f8  lea     r8, [rsp+280h+Name]; lpName
0x1800086fd  xor     edx, edx; bInheritHandle
0x1800086ff  mov     ecx, esi; dwDesiredAccess
0x180008701  call    cs:__imp_OpenSemaphoreW
0x180008707  mov     rdi, rax
0x18000870a  test    rax, rax
0x18000870d  jz      loc_180008794
0x180008713  lea     rdx, [rsp+280h+var_260]; int *
0x180008718  mov     rcx, rax; hHandle
0x18000871b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008720  mov     esi, eax
0x180008722  test    eax, eax
0x180008724  jns     short loc_180008760
0x180008726  mov     rcx, [rbp+188h]; this
0x18000872d  mov     r9d, eax; char *
0x180008730  mov     edx, 0DEh; void *
0x180008735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000873a  mov     rcx, rdi; hObject
0x18000873d  call    cs:__imp_CloseHandle
0x180008743  test    eax, eax
0x180008745  jz      loc_180008840
0x18000874b  mov     rcx, rbx; hObject
0x18000874e  call    cs:__imp_CloseHandle
0x180008754  test    eax, eax
0x180008756  jz      loc_180008852
0x18000875c  mov     eax, esi
0x18000875e  jmp     short loc_1800087D9
0x180008760  mov     rcx, rdi; hObject
0x180008763  call    cs:__imp_CloseHandle
0x180008769  test    eax, eax
0x18000876b  jz      loc_1800087F8
0x180008771  movsxd  rax, [rsp+280h+var_25C]
0x180008776  movsxd  rcx, [rsp+280h+var_260]
0x18000877b  shl     rcx, 1Fh
0x18000877f  or      rcx, rax
0x180008782  mov     [r14], rcx
0x180008785  mov     rcx, rbx; hObject
0x180008788  call    cs:__imp_CloseHandle
0x18000878e  test    eax, eax
0x180008790  jz      short loc_18000880A
0x180008792  jmp     short loc_1800087C4
0x180008794  mov     rcx, [rbp+188h]; this
0x18000879b  mov     edx, 0DCh; void *
0x1800087a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800087a5  mov     rcx, rbx; hObject
0x1800087a8  mov     edi, eax
0x1800087aa  call    cs:__imp_CloseHandle
0x1800087b0  test    eax, eax
0x1800087b2  jz      short loc_18000881C
0x1800087b4  jmp     loc_1800086E0
0x1800087b9  call    cs:__imp_GetLastError
0x1800087bf  cmp     eax, 2
0x1800087c2  jnz     short loc_1800087C8
0x1800087c4  xor     eax, eax
0x1800087c6  jmp     short loc_1800087D9
0x1800087c8  mov     rcx, [rbp+188h]; this
0x1800087cf  mov     edx, 0D0h; void *
0x1800087d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800087d9  mov     rcx, [rbp+180h+var_40]
0x1800087e0  xor     rcx, rsp; StackCookie
0x1800087e3  call    __security_check_cookie
0x1800087e8  add     rsp, 258h
0x1800087ef  pop     r15
0x1800087f1  pop     r14
0x1800087f3  pop     rdi
0x1800087f4  pop     rsi
0x1800087f5  pop     rbx
0x1800087f6  pop     rbp
0x1800087f7  retn
0x1800087f8  mov     rcx, [rbp+188h]; this
0x1800087ff  mov     edx, 0A0Bh; void *
0x180008804  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000880a  mov     rcx, [rbp+188h]; this
0x180008811  mov     edx, 0A0Bh; void *
0x180008816  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000881c  mov     rcx, [rbp+188h]; this
0x180008823  mov     edx, 0A0Bh; void *
0x180008828  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000882e  mov     rcx, [rbp+188h]; this
0x180008835  mov     edx, 0A0Bh; void *
0x18000883a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008840  mov     rcx, [rbp+188h]; this
0x180008847  mov     edx, 0A0Bh; void *
0x18000884c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008852  mov     rcx, [rbp+188h]; this
0x180008859  mov     edx, 0A0Bh; void *
0x18000885e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
