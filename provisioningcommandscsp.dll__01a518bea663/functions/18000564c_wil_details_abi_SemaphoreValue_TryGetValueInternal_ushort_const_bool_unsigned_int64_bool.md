# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000564c`
- end: `0x1800058c6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003140`

## callees

- `0x1800040c4`
- `0x180004d84`
- `0x180004da4`
- `0x1800054c0`
- `0x18000564c`
- `0x180005b10`
- `0x18000c600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800056e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000575c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800056e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000575c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000581b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000581b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000572d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000579f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000580c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000572d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000579f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000580c`

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
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000564c  push    rbp
0x18000564e  push    rbx
0x18000564f  push    rsi
0x180005650  push    rdi
0x180005651  push    r14
0x180005653  push    r15
0x180005655  lea     rbp, [rsp-158h]
0x18000565d  sub     rsp, 258h
0x180005664  mov     rax, cs:__security_cookie
0x18000566b  xor     rax, rsp
0x18000566e  mov     [rbp+180h+var_40], rax
0x180005675  xor     r15d, r15d
0x180005678  lea     rax, [rsp+280h+Name]
0x18000567d  mov     [r8], r15
0x180005680  mov     r14, r8
0x180005683  mov     edx, 104h
0x180005688  mov     r9d, 7FFFFFFEh
0x18000568e  test    r9, r9
0x180005691  jz      short loc_1800056B2
0x180005693  movzx   r8d, word ptr [rcx]
0x180005697  test    r8w, r8w
0x18000569b  jz      short loc_1800056B2
0x18000569d  mov     [rax], r8w
0x1800056a1  add     rcx, 2
0x1800056a5  add     rax, 2
0x1800056a9  dec     r9
0x1800056ac  sub     rdx, 1; unsigned __int64
0x1800056b0  jnz     short loc_18000568E
0x1800056b2  test    rdx, rdx
0x1800056b5  lea     rcx, [rax-2]
0x1800056b9  lea     r8, aP0; "_p0"
0x1800056c0  cmovnz  rcx, rax
0x1800056c4  mov     [rcx], r15w
0x1800056c8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800056cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800056d2  mov     esi, 1F0003h
0x1800056d7  lea     r8, [rsp+280h+Name]; lpName
0x1800056dc  mov     ecx, esi; dwDesiredAccess
0x1800056de  xor     edx, edx; bInheritHandle
0x1800056e0  call    cs:__imp_OpenSemaphoreW
0x1800056e6  mov     rbx, rax
0x1800056e9  test    rax, rax
0x1800056ec  jz      loc_18000581B
0x1800056f2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800056f7  mov     [rsp+280h+var_25C], r15d
0x1800056fc  mov     rcx, rax; hHandle
0x1800056ff  mov     [rsp+280h+var_260], r15d; int
0x180005704  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005709  mov     edi, eax
0x18000570b  test    eax, eax
0x18000570d  jns     short loc_180005742
0x18000570f  mov     rcx, [rbp+188h]; this
0x180005716  lea     r8, aWil; "wil"
0x18000571d  mov     r9d, eax; char *
0x180005720  mov     edx, 0D6h; void *
0x180005725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000572a  mov     rcx, rbx; hObject
0x18000572d  call    cs:__imp_CloseHandle
0x180005733  test    eax, eax
0x180005735  jz      loc_180005890
0x18000573b  mov     eax, edi
0x18000573d  jmp     loc_18000583B
0x180005742  lea     r8, asc_18000FEB8; "h"
0x180005749  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000574e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005753  lea     r8, [rsp+280h+Name]; lpName
0x180005758  xor     edx, edx; bInheritHandle
0x18000575a  mov     ecx, esi; dwDesiredAccess
0x18000575c  call    cs:__imp_OpenSemaphoreW
0x180005762  mov     rdi, rax
0x180005765  test    rax, rax
0x180005768  jz      loc_1800057F6
0x18000576e  lea     rdx, [rsp+280h+var_260]; int *
0x180005773  mov     rcx, rax; hHandle
0x180005776  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000577b  mov     esi, eax
0x18000577d  test    eax, eax
0x18000577f  jns     short loc_1800057C2
0x180005781  mov     rcx, [rbp+188h]; this
0x180005788  lea     r8, aWil; "wil"
0x18000578f  mov     r9d, eax; char *
0x180005792  mov     edx, 0DEh; void *
0x180005797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000579c  mov     rcx, rdi; hObject
0x18000579f  call    cs:__imp_CloseHandle
0x1800057a5  test    eax, eax
0x1800057a7  jz      loc_1800058A2
0x1800057ad  mov     rcx, rbx; hObject
0x1800057b0  call    cs:__imp_CloseHandle
0x1800057b6  test    eax, eax
0x1800057b8  jz      loc_1800058B4
0x1800057be  mov     eax, esi
0x1800057c0  jmp     short loc_18000583B
0x1800057c2  mov     rcx, rdi; hObject
0x1800057c5  call    cs:__imp_CloseHandle
0x1800057cb  test    eax, eax
0x1800057cd  jz      loc_18000585A
0x1800057d3  movsxd  rax, [rsp+280h+var_25C]
0x1800057d8  movsxd  rcx, [rsp+280h+var_260]
0x1800057dd  shl     rcx, 1Fh
0x1800057e1  or      rcx, rax
0x1800057e4  mov     [r14], rcx
0x1800057e7  mov     rcx, rbx; hObject
0x1800057ea  call    cs:__imp_CloseHandle
0x1800057f0  test    eax, eax
0x1800057f2  jz      short loc_18000586C
0x1800057f4  jmp     short loc_180005826
0x1800057f6  mov     rcx, [rbp+188h]; this
0x1800057fd  mov     edx, 0DCh; void *
0x180005802  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005807  mov     rcx, rbx; hObject
0x18000580a  mov     edi, eax
0x18000580c  call    cs:__imp_CloseHandle
0x180005812  test    eax, eax
0x180005814  jz      short loc_18000587E
0x180005816  jmp     loc_18000573B
0x18000581b  call    cs:__imp_GetLastError
0x180005821  cmp     eax, 2
0x180005824  jnz     short loc_18000582A
0x180005826  xor     eax, eax
0x180005828  jmp     short loc_18000583B
0x18000582a  mov     rcx, [rbp+188h]; this
0x180005831  mov     edx, 0D0h; void *
0x180005836  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000583b  mov     rcx, [rbp+180h+var_40]
0x180005842  xor     rcx, rsp; StackCookie
0x180005845  call    __security_check_cookie
0x18000584a  add     rsp, 258h
0x180005851  pop     r15
0x180005853  pop     r14
0x180005855  pop     rdi
0x180005856  pop     rsi
0x180005857  pop     rbx
0x180005858  pop     rbp
0x180005859  retn
0x18000585a  mov     rcx, [rbp+188h]; this
0x180005861  mov     edx, 0A0Bh; void *
0x180005866  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000586c  mov     rcx, [rbp+188h]; this
0x180005873  mov     edx, 0A0Bh; void *
0x180005878  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000587e  mov     rcx, [rbp+188h]; this
0x180005885  mov     edx, 0A0Bh; void *
0x18000588a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005890  mov     rcx, [rbp+188h]; this
0x180005897  mov     edx, 0A0Bh; void *
0x18000589c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058a2  mov     rcx, [rbp+188h]; this
0x1800058a9  mov     edx, 0A0Bh; void *
0x1800058ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058b4  mov     rcx, [rbp+188h]; this
0x1800058bb  mov     edx, 0A0Bh; void *
0x1800058c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
