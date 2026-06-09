# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ac9c`
- end: `0x18000af1f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008798`

## callees

- `0x180006580`
- `0x1800096b4`
- `0x18000a194`
- `0x18000a1b4`
- `0x18000aaf4`
- `0x18000ac9c`
- `0x18000b07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ad33`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000adb5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ad33`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000adb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae65`

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
  unsigned int v17; // r8d
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
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
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v34);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000ac9c  push    rbp
0x18000ac9e  push    rbx
0x18000ac9f  push    rsi
0x18000aca0  push    rdi
0x18000aca1  push    r14
0x18000aca3  push    r15
0x18000aca5  lea     rbp, [rsp-158h]
0x18000acad  sub     rsp, 258h
0x18000acb4  mov     rax, cs:__security_cookie
0x18000acbb  xor     rax, rsp
0x18000acbe  mov     [rbp+180h+var_40], rax
0x18000acc5  xor     r15d, r15d
0x18000acc8  lea     rax, [rsp+280h+Name]
0x18000accd  mov     esi, 104h
0x18000acd2  mov     [r8], r15
0x18000acd5  mov     edx, esi
0x18000acd7  mov     r14, r8
0x18000acda  mov     r9d, 7FFFFFFEh
0x18000ace0  test    r9, r9
0x18000ace3  jz      short loc_18000AD04
0x18000ace5  movzx   r8d, word ptr [rcx]
0x18000ace9  test    r8w, r8w
0x18000aced  jz      short loc_18000AD04
0x18000acef  mov     [rax], r8w
0x18000acf3  add     rcx, 2
0x18000acf7  add     rax, 2
0x18000acfb  dec     r9
0x18000acfe  sub     rdx, 1
0x18000ad02  jnz     short loc_18000ACE0
0x18000ad04  test    rdx, rdx
0x18000ad07  lea     rcx, [rax-2]
0x18000ad0b  lea     r8, aP0; "_p0"
0x18000ad12  mov     rdx, rsi; unsigned __int64
0x18000ad15  cmovnz  rcx, rax
0x18000ad19  mov     [rcx], r15w
0x18000ad1d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ad22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ad27  lea     r8, [rsp+280h+Name]; lpName
0x18000ad2c  xor     edx, edx; bInheritHandle
0x18000ad2e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ad33  call    cs:__imp_OpenSemaphoreW
0x18000ad39  mov     rbx, rax
0x18000ad3c  test    rax, rax
0x18000ad3f  jz      loc_18000AE74
0x18000ad45  lea     rdx, [rsp+280h+var_25C]; int *
0x18000ad4a  mov     [rsp+280h+var_25C], r15d
0x18000ad4f  mov     rcx, rax; hHandle
0x18000ad52  mov     [rsp+280h+var_260], r15d; int
0x18000ad57  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ad5c  mov     edi, eax
0x18000ad5e  test    eax, eax
0x18000ad60  jns     short loc_18000AD95
0x18000ad62  mov     rcx, [rbp+188h]; this
0x18000ad69  lea     r8, aWil; "wil"
0x18000ad70  mov     r9d, eax; char *
0x18000ad73  mov     edx, 0D6h; void *
0x18000ad78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad7d  mov     rcx, rbx; hObject
0x18000ad80  call    cs:__imp_CloseHandle
0x18000ad86  test    eax, eax
0x18000ad88  jz      loc_18000AEE9
0x18000ad8e  mov     eax, edi
0x18000ad90  jmp     loc_18000AE94
0x18000ad95  lea     r8, asc_18008EE50; "h"
0x18000ad9c  mov     rdx, rsi; unsigned __int64
0x18000ad9f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ada4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ada9  lea     r8, [rsp+280h+Name]; lpName
0x18000adae  xor     edx, edx; bInheritHandle
0x18000adb0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000adb5  call    cs:__imp_OpenSemaphoreW
0x18000adbb  mov     rdi, rax
0x18000adbe  test    rax, rax
0x18000adc1  jz      loc_18000AE4F
0x18000adc7  lea     rdx, [rsp+280h+var_260]; int *
0x18000adcc  mov     rcx, rax; hHandle
0x18000adcf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000add4  mov     esi, eax
0x18000add6  test    eax, eax
0x18000add8  jns     short loc_18000AE1B
0x18000adda  mov     rcx, [rbp+188h]; this
0x18000ade1  lea     r8, aWil; "wil"
0x18000ade8  mov     r9d, eax; char *
0x18000adeb  mov     edx, 0DEh; void *
0x18000adf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adf5  mov     rcx, rdi; hObject
0x18000adf8  call    cs:__imp_CloseHandle
0x18000adfe  test    eax, eax
0x18000ae00  jz      loc_18000AEFB
0x18000ae06  mov     rcx, rbx; hObject
0x18000ae09  call    cs:__imp_CloseHandle
0x18000ae0f  test    eax, eax
0x18000ae11  jz      loc_18000AF0D
0x18000ae17  mov     eax, esi
0x18000ae19  jmp     short loc_18000AE94
0x18000ae1b  mov     rcx, rdi; hObject
0x18000ae1e  call    cs:__imp_CloseHandle
0x18000ae24  test    eax, eax
0x18000ae26  jz      loc_18000AEB3
0x18000ae2c  movsxd  rax, [rsp+280h+var_25C]
0x18000ae31  movsxd  rcx, [rsp+280h+var_260]
0x18000ae36  shl     rcx, 1Fh
0x18000ae3a  or      rcx, rax
0x18000ae3d  mov     [r14], rcx
0x18000ae40  mov     rcx, rbx; hObject
0x18000ae43  call    cs:__imp_CloseHandle
0x18000ae49  test    eax, eax
0x18000ae4b  jz      short loc_18000AEC5
0x18000ae4d  jmp     short loc_18000AE7F
0x18000ae4f  mov     rcx, [rbp+188h]; this
0x18000ae56  mov     edx, 0DCh; void *
0x18000ae5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ae60  mov     rcx, rbx; hObject
0x18000ae63  mov     edi, eax
0x18000ae65  call    cs:__imp_CloseHandle
0x18000ae6b  test    eax, eax
0x18000ae6d  jz      short loc_18000AED7
0x18000ae6f  jmp     loc_18000AD8E
0x18000ae74  call    cs:__imp_GetLastError
0x18000ae7a  cmp     eax, 2
0x18000ae7d  jnz     short loc_18000AE83
0x18000ae7f  xor     eax, eax
0x18000ae81  jmp     short loc_18000AE94
0x18000ae83  mov     rcx, [rbp+188h]; this
0x18000ae8a  mov     edx, 0D0h; void *
0x18000ae8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ae94  mov     rcx, [rbp+180h+var_40]
0x18000ae9b  xor     rcx, rsp; StackCookie
0x18000ae9e  call    __security_check_cookie
0x18000aea3  add     rsp, 258h
0x18000aeaa  pop     r15
0x18000aeac  pop     r14
0x18000aeae  pop     rdi
0x18000aeaf  pop     rsi
0x18000aeb0  pop     rbx
0x18000aeb1  pop     rbp
0x18000aeb2  retn
0x18000aeb3  mov     rcx, [rbp+188h]; this
0x18000aeba  mov     edx, 0A0Bh; void *
0x18000aebf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aec5  mov     rcx, [rbp+188h]; this
0x18000aecc  mov     edx, 0A0Bh; void *
0x18000aed1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aed7  mov     rcx, [rbp+188h]; this
0x18000aede  mov     edx, 0A0Bh; void *
0x18000aee3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aee9  mov     rcx, [rbp+188h]; this
0x18000aef0  mov     edx, 0A0Bh; void *
0x18000aef5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aefb  mov     rcx, [rbp+188h]; this
0x18000af02  mov     edx, 0A0Bh; void *
0x18000af07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000af0d  mov     rcx, [rbp+188h]; this
0x18000af14  mov     edx, 0A0Bh; void *
0x18000af19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
