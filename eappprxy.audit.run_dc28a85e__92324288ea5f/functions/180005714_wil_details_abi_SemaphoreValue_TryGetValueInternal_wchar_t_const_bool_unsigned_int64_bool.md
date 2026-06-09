# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005714`
- end: `0x1800059be`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000327c`

## callees

- `0x180001780`
- `0x180003e58`
- `0x180004c74`
- `0x180004c94`
- `0x1800053d0`
- `0x180005714`
- `0x180005d88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000590c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000590c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800057a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005829`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800057a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000586b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000586b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058f7`

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
0x180005714  push    rbp
0x180005716  push    rbx
0x180005717  push    rsi
0x180005718  push    rdi
0x180005719  push    r14
0x18000571b  push    r15
0x18000571d  lea     rbp, [rsp-158h]
0x180005725  sub     rsp, 258h
0x18000572c  mov     rax, cs:__security_cookie
0x180005733  xor     rax, rsp
0x180005736  mov     [rbp+180h+var_40], rax
0x18000573d  xor     r15d, r15d
0x180005740  lea     rax, [rsp+280h+Name]
0x180005745  mov     [r8], r15
0x180005748  mov     r14, r8
0x18000574b  mov     edx, 104h
0x180005750  mov     r9d, 7FFFFFFEh
0x180005756  test    r9, r9
0x180005759  jz      short loc_18000577A
0x18000575b  movzx   r8d, word ptr [rcx]
0x18000575f  test    r8w, r8w
0x180005763  jz      short loc_18000577A
0x180005765  mov     [rax], r8w
0x180005769  add     rcx, 2
0x18000576d  add     rax, 2
0x180005771  dec     r9
0x180005774  sub     rdx, 1; unsigned __int64
0x180005778  jnz     short loc_180005756
0x18000577a  test    rdx, rdx
0x18000577d  lea     rcx, [rax-2]
0x180005781  lea     r8, aP0; "_p0"
0x180005788  cmovnz  rcx, rax
0x18000578c  mov     [rcx], r15w
0x180005790  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005795  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000579a  mov     esi, 1F0003h
0x18000579f  lea     r8, [rsp+280h+Name]; lpName
0x1800057a4  mov     ecx, esi; dwDesiredAccess
0x1800057a6  xor     edx, edx; bInheritHandle
0x1800057a8  call    cs:__imp_OpenSemaphoreW
0x1800057af  nop     dword ptr [rax+rax+00h]
0x1800057b4  mov     rbx, rax
0x1800057b7  test    rax, rax
0x1800057ba  jz      loc_18000590C
0x1800057c0  lea     rdx, [rsp+280h+var_25C]; int *
0x1800057c5  mov     [rsp+280h+var_25C], r15d
0x1800057ca  mov     rcx, rax; hHandle
0x1800057cd  mov     [rsp+280h+var_260], r15d; int
0x1800057d2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800057d7  mov     edi, eax
0x1800057d9  test    eax, eax
0x1800057db  jns     short loc_18000580F
0x1800057dd  mov     rcx, [rbp+188h]; this
0x1800057e4  mov     r9d, eax; char *
0x1800057e7  mov     edx, 0D6h; void *
0x1800057ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057f1  mov     rcx, rbx; hObject
0x1800057f4  call    cs:__imp_CloseHandle
0x1800057fb  nop     dword ptr [rax+rax+00h]
0x180005800  test    eax, eax
0x180005802  jz      loc_180005988
0x180005808  mov     eax, edi
0x18000580a  jmp     loc_180005932
0x18000580f  lea     r8, asc_180010B18; "h"
0x180005816  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000581b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180005820  lea     r8, [rsp+280h+Name]; lpName
0x180005825  xor     edx, edx; bInheritHandle
0x180005827  mov     ecx, esi; dwDesiredAccess
0x180005829  call    cs:__imp_OpenSemaphoreW
0x180005830  nop     dword ptr [rax+rax+00h]
0x180005835  mov     rdi, rax
0x180005838  test    rax, rax
0x18000583b  jz      loc_1800058E1
0x180005841  lea     rdx, [rsp+280h+var_260]; int *
0x180005846  mov     rcx, rax; hHandle
0x180005849  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000584e  mov     esi, eax
0x180005850  test    eax, eax
0x180005852  jns     short loc_18000589D
0x180005854  mov     rcx, [rbp+188h]; this
0x18000585b  mov     r9d, eax; char *
0x18000585e  mov     edx, 0DEh; void *
0x180005863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005868  mov     rcx, rdi; hObject
0x18000586b  call    cs:__imp_CloseHandle
0x180005872  nop     dword ptr [rax+rax+00h]
0x180005877  test    eax, eax
0x180005879  jz      loc_18000599A
0x18000587f  mov     rcx, rbx; hObject
0x180005882  call    cs:__imp_CloseHandle
0x180005889  nop     dword ptr [rax+rax+00h]
0x18000588e  test    eax, eax
0x180005890  jz      loc_1800059AC
0x180005896  mov     eax, esi
0x180005898  jmp     loc_180005932
0x18000589d  mov     rcx, rdi; hObject
0x1800058a0  call    cs:__imp_CloseHandle
0x1800058a7  nop     dword ptr [rax+rax+00h]
0x1800058ac  test    eax, eax
0x1800058ae  jz      loc_180005952
0x1800058b4  movsxd  rax, [rsp+280h+var_25C]
0x1800058b9  movsxd  rcx, [rsp+280h+var_260]
0x1800058be  shl     rcx, 1Fh
0x1800058c2  or      rcx, rax
0x1800058c5  mov     [r14], rcx
0x1800058c8  mov     rcx, rbx; hObject
0x1800058cb  call    cs:__imp_CloseHandle
0x1800058d2  nop     dword ptr [rax+rax+00h]
0x1800058d7  test    eax, eax
0x1800058d9  jz      loc_180005964
0x1800058df  jmp     short loc_18000591D
0x1800058e1  mov     rcx, [rbp+188h]; this
0x1800058e8  mov     edx, 0DCh; void *
0x1800058ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800058f2  mov     rcx, rbx; hObject
0x1800058f5  mov     edi, eax
0x1800058f7  call    cs:__imp_CloseHandle
0x1800058fe  nop     dword ptr [rax+rax+00h]
0x180005903  test    eax, eax
0x180005905  jz      short loc_180005976
0x180005907  jmp     loc_180005808
0x18000590c  call    cs:__imp_GetLastError
0x180005913  nop     dword ptr [rax+rax+00h]
0x180005918  cmp     eax, 2
0x18000591b  jnz     short loc_180005921
0x18000591d  xor     eax, eax
0x18000591f  jmp     short loc_180005932
0x180005921  mov     rcx, [rbp+188h]; this
0x180005928  mov     edx, 0D0h; void *
0x18000592d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005932  mov     rcx, [rbp+180h+var_40]
0x180005939  xor     rcx, rsp; StackCookie
0x18000593c  call    __security_check_cookie
0x180005941  add     rsp, 258h
0x180005948  pop     r15
0x18000594a  pop     r14
0x18000594c  pop     rdi
0x18000594d  pop     rsi
0x18000594e  pop     rbx
0x18000594f  pop     rbp
0x180005950  retn
0x180005952  mov     rcx, [rbp+188h]; this
0x180005959  mov     edx, 0A0Bh; void *
0x18000595e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005964  mov     rcx, [rbp+188h]; this
0x18000596b  mov     edx, 0A0Bh; void *
0x180005970  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005976  mov     rcx, [rbp+188h]; this
0x18000597d  mov     edx, 0A0Bh; void *
0x180005982  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005988  mov     rcx, [rbp+188h]; this
0x18000598f  mov     edx, 0A0Bh; void *
0x180005994  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000599a  mov     rcx, [rbp+188h]; this
0x1800059a1  mov     edx, 0A0Bh; void *
0x1800059a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800059ac  mov     rcx, [rbp+188h]; this
0x1800059b3  mov     edx, 0A0Bh; void *
0x1800059b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
