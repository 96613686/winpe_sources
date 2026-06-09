# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003942c`
- end: `0x180039676`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `586`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800390d4`
- `0x180039158`

## callees

- `0x1800161b8`
- `0x18003942c`
- `0x18003967c`
- `0x1800397d8`
- `0x180039804`
- `0x18004a490`
- `0x18004d900`
- `0x1800555d8`
- `0x180055684`
- `0x1800556a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395ff`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800394b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003951b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800394b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003951b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  const wchar_t *v6; // rcx
  size_t *v7; // r8
  size_t v8; // r9
  size_t *v9; // r8
  wil::details *v10; // rax
  wil::details *v11; // rdi
  int ValueFromSemaphore; // eax
  size_t v13; // rdx
  size_t v14; // r9
  unsigned int v15; // esi
  size_t *v16; // r8
  wil::details *v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  wil::details *v20; // rbx
  int v21; // eax
  void *v22; // rdx
  void *v23; // rdx
  unsigned int LastError; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  size_t v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  size_t pcchDestLength; // [rsp+38h] [rbp-C8h] BYREF
  size_t v31; // [rsp+40h] [rbp-C0h] BYREF
  wil::details *v32; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  if ( StringValidateDestW(a1, 0x104u, (const size_t)a3) < 0 )
    pszDest[0] = 0;
  else
    StringCopyWorkerW(pszDest, v5, v7, v6, v28);
  pcchDestLength = 0;
  if ( StringValidateDestAndLengthW(pszDest, v5, &pcchDestLength, v8) >= 0 )
    StringCopyWorkerW(&pszDest[pcchDestLength], 260 - pcchDestLength, v9, L"_p0", v28);
  v10 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v32 = v10;
  v11 = v10;
  if ( v10 )
  {
    LODWORD(pcchDestLength) = 0;
    v29 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, (int *)&pcchDestLength);
    v15 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v28);
    }
    else
    {
      v31 = 0;
      if ( StringValidateDestAndLengthW(pszDest, v13, &v31, v14) >= 0 )
        StringCopyWorkerW(&pszDest[v31], 260 - v31, v16, L"h", v28);
      v17 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v31 = (size_t)v17;
      v20 = v17;
      if ( !v17 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
        goto LABEL_12;
      }
      v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v29);
      v15 = v21;
      if ( v21 >= 0 )
      {
        wil::details::CloseHandle(v20, v22);
        *a3 = (int)pcchDestLength | (unsigned __int64)((__int64)v29 << 31);
        LastError = 0;
LABEL_12:
        wil::details::CloseHandle(v11, v23);
        return LastError;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v21,
        v28);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
    }
  }
  else if ( GetLastError() == 2 )
  {
    v15 = 0;
  }
  else
  {
    v15 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v26, v27);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v32);
  return v15;
}

```

## disassembly

```asm
0x18003942c  mov     [rsp-8+arg_8], rbx
0x180039431  mov     [rsp-8+arg_18], rsi
0x180039436  push    rbp
0x180039437  push    rdi
0x180039438  push    r14
0x18003943a  lea     rbp, [rsp-170h]
0x180039442  sub     rsp, 270h
0x180039449  mov     rax, cs:__security_cookie
0x180039450  xor     rax, rsp
0x180039453  mov     [rbp+180h+var_20], rax
0x18003945a  mov     ebx, 104h
0x18003945f  mov     qword ptr [r8], 0
0x180039466  mov     edx, ebx; cchDest
0x180039468  mov     r14, r8
0x18003946b  call    StringValidateDestW
0x180039470  test    eax, eax
0x180039472  js      loc_1800395F3
0x180039478  mov     r9, rcx; pszSrc
0x18003947b  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180039480  call    StringCopyWorkerW
0x180039485  lea     r8, [rsp+280h+pcchDestLength]; pcchDestLength
0x18003948a  mov     [rsp+280h+pcchDestLength], 0
0x180039493  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180039498  call    StringValidateDestAndLengthW
0x18003949d  test    eax, eax
0x18003949f  jns     loc_1800395A9
0x1800394a5  lea     r8, [rsp+280h+pszDest]; lpName
0x1800394aa  xor     edx, edx; bInheritHandle
0x1800394ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1800394b1  call    cs:__imp_OpenSemaphoreW
0x1800394b7  mov     [rsp+280h+var_238], rax
0x1800394bc  mov     rdi, rax
0x1800394bf  test    rax, rax
0x1800394c2  jz      loc_1800395FF
0x1800394c8  lea     rdx, [rsp+280h+pcchDestLength]; int *
0x1800394cd  mov     dword ptr [rsp+280h+pcchDestLength], 0
0x1800394d5  mov     rcx, rax; hHandle
0x1800394d8  mov     [rsp+280h+var_250], 0
0x1800394e0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800394e5  mov     esi, eax
0x1800394e7  test    eax, eax
0x1800394e9  js      loc_180039623
0x1800394ef  lea     r8, [rsp+280h+var_240]; pcchDestLength
0x1800394f4  mov     [rsp+280h+var_240], 0
0x1800394fd  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180039502  call    StringValidateDestAndLengthW
0x180039507  test    eax, eax
0x180039509  jns     loc_1800395CE
0x18003950f  lea     r8, [rsp+280h+pszDest]; lpName
0x180039514  xor     edx, edx; bInheritHandle
0x180039516  mov     ecx, 1F0003h; dwDesiredAccess
0x18003951b  call    cs:__imp_OpenSemaphoreW
0x180039521  mov     [rsp+280h+var_240], rax
0x180039526  mov     rbx, rax
0x180039529  test    rax, rax
0x18003952c  jz      short loc_180039594
0x18003952e  lea     rdx, [rsp+280h+var_250]; int *
0x180039533  mov     rcx, rax; hHandle
0x180039536  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003953b  mov     esi, eax
0x18003953d  test    eax, eax
0x18003953f  js      loc_180039640
0x180039545  mov     rcx, rbx; this
0x180039548  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003954d  movsxd  rcx, [rsp+280h+var_250]
0x180039552  movsxd  rax, dword ptr [rsp+280h+pcchDestLength]
0x180039557  shl     rcx, 1Fh
0x18003955b  or      rcx, rax
0x18003955e  mov     [r14], rcx
0x180039561  xor     ebx, ebx
0x180039563  mov     rcx, rdi; this
0x180039566  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003956b  mov     eax, ebx
0x18003956d  mov     rcx, [rbp+180h+var_20]
0x180039574  xor     rcx, rsp; StackCookie
0x180039577  call    __security_check_cookie
0x18003957c  lea     r11, [rsp+280h+var_10]
0x180039584  mov     rbx, [r11+28h]
0x180039588  mov     rsi, [r11+38h]
0x18003958c  mov     rsp, r11
0x18003958f  pop     r14
0x180039591  pop     rdi
0x180039592  pop     rbp
0x180039593  retn
0x180039594  mov     rcx, [rbp+188h]; this
0x18003959b  mov     edx, 0DCh; void *
0x1800395a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800395a5  mov     ebx, eax
0x1800395a7  jmp     short loc_180039563
0x1800395a9  mov     rax, [rsp+280h+pcchDestLength]
0x1800395ae  lea     rcx, [rsp+280h+pszDest]
0x1800395b3  mov     rdx, rbx
0x1800395b6  lea     r9, aP0; "_p0"
0x1800395bd  sub     rdx, rax; cchDest
0x1800395c0  lea     rcx, [rcx+rax*2]; pszDest
0x1800395c4  call    StringCopyWorkerW
0x1800395c9  jmp     loc_1800394A5
0x1800395ce  mov     rax, [rsp+280h+var_240]
0x1800395d3  lea     rcx, [rsp+280h+pszDest]
0x1800395d8  sub     rbx, rax
0x1800395db  lea     r9, asc_1800AF288; "h"
0x1800395e2  mov     rdx, rbx; cchDest
0x1800395e5  lea     rcx, [rcx+rax*2]; pszDest
0x1800395e9  call    StringCopyWorkerW
0x1800395ee  jmp     loc_18003950F
0x1800395f3  xor     eax, eax
0x1800395f5  mov     [rsp+280h+pszDest], ax
0x1800395fa  jmp     loc_180039485
0x1800395ff  call    cs:__imp_GetLastError
0x180039605  cmp     eax, 2
0x180039608  jnz     short loc_18003960E
0x18003960a  xor     esi, esi
0x18003960c  jmp     short loc_180039665
0x18003960e  mov     rcx, [rbp+188h]; this
0x180039615  mov     edx, 0D0h; void *
0x18003961a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003961f  mov     esi, eax
0x180039621  jmp     short loc_180039665
0x180039623  mov     rcx, [rbp+188h]; this
0x18003962a  lea     r8, aWil; "wil"
0x180039631  mov     r9d, eax; char *
0x180039634  mov     edx, 0D6h; void *
0x180039639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003963e  jmp     short loc_180039665
0x180039640  mov     rcx, [rbp+188h]; this
0x180039647  lea     r8, aWil; "wil"
0x18003964e  mov     r9d, eax; char *
0x180039651  mov     edx, 0DEh; void *
0x180039656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003965b  lea     rcx, [rsp+280h+var_240]
0x180039660  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039665  lea     rcx, [rsp+280h+var_238]
0x18003966a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003966f  mov     eax, esi
0x180039671  jmp     loc_18003956D
```
