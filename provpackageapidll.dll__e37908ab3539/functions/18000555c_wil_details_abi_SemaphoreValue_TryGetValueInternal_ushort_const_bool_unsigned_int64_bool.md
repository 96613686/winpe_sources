# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000555c`
- end: `0x1800057f4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003068`

## callees

- `0x180001510`
- `0x180003ff4`
- `0x180004a64`
- `0x180004a84`
- `0x180005360`
- `0x18000555c`
- `0x18000594c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005742`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055f3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005675`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055f3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005733`

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
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
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
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000555c  push    rbp
0x18000555e  push    rbx
0x18000555f  push    rsi
0x180005560  push    rdi
0x180005561  push    r14
0x180005563  push    r15
0x180005565  lea     rbp, [rsp-158h]
0x18000556d  sub     rsp, 258h
0x180005574  mov     rax, cs:__security_cookie
0x18000557b  xor     rax, rsp
0x18000557e  mov     [rbp+180h+var_40], rax
0x180005585  xor     r15d, r15d
0x180005588  lea     rax, [rsp+280h+Name]
0x18000558d  mov     esi, 104h
0x180005592  mov     [r8], r15
0x180005595  mov     edx, esi
0x180005597  mov     r14, r8
0x18000559a  mov     r9d, 7FFFFFFEh
0x1800055a0  test    r9, r9
0x1800055a3  jz      short loc_1800055C4
0x1800055a5  movzx   r8d, word ptr [rcx]
0x1800055a9  test    r8w, r8w
0x1800055ad  jz      short loc_1800055C4
0x1800055af  mov     [rax], r8w
0x1800055b3  add     rcx, 2
0x1800055b7  add     rax, 2
0x1800055bb  dec     r9
0x1800055be  sub     rdx, 1
0x1800055c2  jnz     short loc_1800055A0
0x1800055c4  test    rdx, rdx
0x1800055c7  lea     rcx, [rax-2]
0x1800055cb  lea     r8, aP0; "_p0"
0x1800055d2  mov     rdx, rsi; unsigned __int64
0x1800055d5  cmovnz  rcx, rax
0x1800055d9  mov     [rcx], r15w
0x1800055dd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800055e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800055e7  lea     r8, [rsp+280h+Name]; lpName
0x1800055ec  xor     edx, edx; bInheritHandle
0x1800055ee  mov     ecx, 1F0003h; dwDesiredAccess
0x1800055f3  call    cs:__imp_OpenSemaphoreW
0x1800055f9  mov     rbx, rax
0x1800055fc  test    rax, rax
0x1800055ff  jz      loc_180005742
0x180005605  lea     rdx, [rsp+280h+var_25C]; int *
0x18000560a  mov     [rsp+280h+var_25C], r15d
0x18000560f  mov     rcx, rax; hHandle
0x180005612  mov     [rsp+280h+var_260], r15d; int
0x180005617  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000561c  mov     edi, eax
0x18000561e  test    eax, eax
0x180005620  jns     short loc_180005655
0x180005622  mov     rcx, [rbp+188h]; this
0x180005629  lea     r8, aWil; "wil"
0x180005630  mov     r9d, eax; char *
0x180005633  mov     edx, 0D6h; void *
0x180005638  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000563d  mov     rcx, rbx; hObject
0x180005640  call    cs:__imp_CloseHandle
0x180005646  test    eax, eax
0x180005648  jz      loc_1800057BE
0x18000564e  mov     eax, edi
0x180005650  jmp     loc_180005769
0x180005655  lea     r8, asc_18001AE78; "h"
0x18000565c  mov     rdx, rsi; unsigned __int64
0x18000565f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005664  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005669  lea     r8, [rsp+280h+Name]; lpName
0x18000566e  xor     edx, edx; bInheritHandle
0x180005670  mov     ecx, 1F0003h; dwDesiredAccess
0x180005675  call    cs:__imp_OpenSemaphoreW
0x18000567b  mov     rdi, rax
0x18000567e  test    rax, rax
0x180005681  jz      loc_180005716
0x180005687  lea     rdx, [rsp+280h+var_260]; int *
0x18000568c  mov     rcx, rax; hHandle
0x18000568f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005694  mov     esi, eax
0x180005696  test    eax, eax
0x180005698  jns     short loc_1800056DE
0x18000569a  mov     rcx, [rbp+188h]; this
0x1800056a1  lea     r8, aWil; "wil"
0x1800056a8  mov     r9d, eax; char *
0x1800056ab  mov     edx, 0DEh; void *
0x1800056b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056b5  mov     rcx, rdi; hObject
0x1800056b8  call    cs:__imp_CloseHandle
0x1800056be  test    eax, eax
0x1800056c0  jz      loc_1800057D0
0x1800056c6  mov     rcx, rbx; hObject
0x1800056c9  call    cs:__imp_CloseHandle
0x1800056cf  test    eax, eax
0x1800056d1  jz      loc_1800057E2
0x1800056d7  mov     eax, esi
0x1800056d9  jmp     loc_180005769
0x1800056de  mov     rcx, rdi; hObject
0x1800056e1  call    cs:__imp_CloseHandle
0x1800056e7  test    eax, eax
0x1800056e9  jz      loc_180005788
0x1800056ef  movsxd  rax, [rsp+280h+var_25C]
0x1800056f4  movsxd  rcx, [rsp+280h+var_260]
0x1800056f9  shl     rcx, 1Fh
0x1800056fd  or      rcx, rax
0x180005700  mov     [r14], rcx
0x180005703  mov     rcx, rbx; hObject
0x180005706  call    cs:__imp_CloseHandle
0x18000570c  test    eax, eax
0x18000570e  jz      loc_18000579A
0x180005714  jmp     short loc_18000574D
0x180005716  mov     rcx, [rbp+188h]; this
0x18000571d  lea     r8, aWil; "wil"
0x180005724  mov     edx, 0DCh; void *
0x180005729  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000572e  mov     rcx, rbx; hObject
0x180005731  mov     edi, eax
0x180005733  call    cs:__imp_CloseHandle
0x180005739  test    eax, eax
0x18000573b  jz      short loc_1800057AC
0x18000573d  jmp     loc_18000564E
0x180005742  call    cs:__imp_GetLastError
0x180005748  cmp     eax, 2
0x18000574b  jnz     short loc_180005751
0x18000574d  xor     eax, eax
0x18000574f  jmp     short loc_180005769
0x180005751  mov     rcx, [rbp+188h]; this
0x180005758  lea     r8, aWil; "wil"
0x18000575f  mov     edx, 0D0h; void *
0x180005764  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005769  mov     rcx, [rbp+180h+var_40]
0x180005770  xor     rcx, rsp; StackCookie
0x180005773  call    __security_check_cookie
0x180005778  add     rsp, 258h
0x18000577f  pop     r15
0x180005781  pop     r14
0x180005783  pop     rdi
0x180005784  pop     rsi
0x180005785  pop     rbx
0x180005786  pop     rbp
0x180005787  retn
0x180005788  mov     rcx, [rbp+188h]; this
0x18000578f  mov     edx, 0A0Bh; void *
0x180005794  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000579a  mov     rcx, [rbp+188h]; this
0x1800057a1  mov     edx, 0A0Bh; void *
0x1800057a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057ac  mov     rcx, [rbp+188h]; this
0x1800057b3  mov     edx, 0A0Bh; void *
0x1800057b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057be  mov     rcx, [rbp+188h]; this
0x1800057c5  mov     edx, 0A0Bh; void *
0x1800057ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057d0  mov     rcx, [rbp+188h]; this
0x1800057d7  mov     edx, 0A0Bh; void *
0x1800057dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057e2  mov     rcx, [rbp+188h]; this
0x1800057e9  mov     edx, 0A0Bh; void *
0x1800057ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
