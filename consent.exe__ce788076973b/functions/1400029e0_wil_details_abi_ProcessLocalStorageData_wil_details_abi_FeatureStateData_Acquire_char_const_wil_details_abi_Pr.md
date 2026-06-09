# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400029e0`
- end: `0x140002e8e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1198`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14001671c`

## callees

- `0x1400029e0`
- `0x140002ea0`
- `0x14000df54`
- `0x14000e4dc`
- `0x14000e558`
- `0x14000eeb8`
- `0x14000f588`
- `0x14000fb48`
- `0x140011bd8`
- `0x140016968`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002a79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002a79`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002a4f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002a4f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002b1f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002c88`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002b1f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002a0b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  __int64 v4; // rdi
  wil::details *Mutex; // rax
  wil::details *v6; // rcx
  wil::details *v7; // rsi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details *v12; // r14
  WCHAR *v13; // r8
  WCHAR *v14; // rax
  __int64 v15; // r15
  unsigned __int64 v16; // r12
  __int64 v17; // rcx
  __int64 v18; // rdx
  bool v19; // zf
  WCHAR *v20; // rcx
  __int64 v21; // rdx
  WCHAR *v22; // rax
  wil::details *v23; // rax
  wil::details *v24; // rbx
  void *v25; // rdx
  const char *v26; // r9
  unsigned int LastError; // ebp
  void *v28; // rdx
  int ValueFromSemaphore; // eax
  void *v31; // rdx
  WCHAR *v32; // rax
  WCHAR *v33; // rdx
  wil::details *v34; // rax
  const char *v35; // r9
  wil::details *v36; // rdi
  int v37; // eax
  void *v38; // rdx
  void *v39; // rdx
  _DWORD *v40; // rcx
  void *v41; // rdx
  __int64 v42; // rcx
  WCHAR *v43; // r8
  const unsigned __int16 *v44; // r9
  WCHAR *v45; // rcx
  WCHAR *v46; // r8
  const unsigned __int16 *v47; // rcx
  void *v48; // rdx
  void *v49; // rdx
  void *v50; // rdx
  int v51; // eax
  unsigned int v52; // ebx
  int v53; // [rsp+20h] [rbp-488h]
  int v54; // [rsp+20h] [rbp-488h]
  int v55; // [rsp+20h] [rbp-488h]
  int v56; // [rsp+30h] [rbp-478h] BYREF
  int v57; // [rsp+34h] [rbp-474h] BYREF
  wil::details *v58; // [rsp+38h] [rbp-470h]
  WCHAR v59[260]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR Name[264]; // [rsp+250h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v4 = 260;
  v53 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v58 = Mutex;
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v7;
  }
  v13 = Name;
  v14 = v59;
  v15 = 2147483646;
  v16 = 0;
  v17 = 2147483646;
  v18 = 260;
  do
  {
    if ( !v17 )
      break;
    if ( !*v13 )
      break;
    *v14++ = *v13++;
    --v17;
    --v18;
  }
  while ( v18 );
  v19 = v18 == 0;
  v20 = v14 - 1;
  v21 = 260;
  if ( !v19 )
    v20 = v14;
  v22 = v59;
  *v20 = 0;
  while ( *v22 )
  {
    ++v22;
    if ( !--v21 )
      goto LABEL_14;
  }
  v42 = 2147483646;
  v43 = Name - v21 + 3;
  v44 = L"_p0";
  do
  {
    if ( !v42 )
      break;
    if ( !*v44 )
      break;
    *v43++ = *v44++;
    --v42;
    --v21;
  }
  while ( v21 );
  v45 = v43 - 1;
  if ( v21 )
    v45 = v43;
  *v45 = 0;
LABEL_14:
  v23 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, v59);
  v24 = v23;
  if ( v23 )
  {
    v57 = 0;
    v56 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v23, &v57);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        304);
      wil::details::CloseHandle(v24, v31);
      goto LABEL_18;
    }
    v32 = v59;
    while ( *v32 )
    {
      ++v32;
      if ( !--v4 )
        goto LABEL_31;
    }
    v46 = Name - v4 + 3;
    v47 = L"h";
    do
    {
      if ( !v15 )
        break;
      if ( !*v47 )
        break;
      *v46++ = *v47++;
      --v15;
      --v4;
    }
    while ( v4 );
    v33 = v46 - 1;
    if ( v4 )
      v33 = v46;
    *v33 = 0;
LABEL_31:
    v34 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, v59);
    v36 = v34;
    if ( v34 )
    {
      v37 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v34, &v56);
      LastError = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v37,
          304);
        wil::details::CloseHandle(v36, v49);
        wil::details::CloseHandle(v24, v50);
        goto LABEL_18;
      }
      wil::details::CloseHandle(v36, v38);
      v16 = v57 | (unsigned __int64)((__int64)v56 << 31);
      wil::details::CloseHandle(v24, v39);
      goto LABEL_34;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v35);
    wil::details::CloseHandle(v24, v41);
  }
  else
  {
    if ( GetLastError() == 2 )
      goto LABEL_34;
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v26);
  }
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (unsigned int)"wil", (const char *)LastError, v53);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastError, v54);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)LastError, v55);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v28);
    wil::details::CloseHandle(v7, v28);
    return LastError;
  }
LABEL_34:
  v40 = (_DWORD *)(4 * v16);
  if ( 4 * v16 )
  {
    *a2 = v40;
    ++*v40;
LABEL_36:
    if ( v12 )
      wil::details::ReleaseMutex(v12, v25);
    if ( v7 )
      wil::details::CloseHandle(v7, v25);
    return 0;
  }
  v51 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v52 = v51;
  if ( v51 >= 0 )
  {
    v7 = v58;
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v51, 304);
  if ( v12 )
    wil::details::ReleaseMutex(v12, v48);
  if ( v58 )
    wil::details::CloseHandle(v58, v48);
  return v52;
}

```

## disassembly

```asm
0x1400029e0  push    rbx
0x1400029e2  push    rbp
0x1400029e3  push    rsi
0x1400029e4  push    rdi
0x1400029e5  push    r13
0x1400029e7  sub     rsp, 480h
0x1400029ee  mov     rax, cs:__security_cookie
0x1400029f5  xor     rax, rsp
0x1400029f8  mov     [rsp+4A8h+var_48], rax
0x140002a00  xor     ebp, ebp
0x140002a02  mov     r13, rdx
0x140002a05  mov     [rdx], rbp
0x140002a08  mov     rbx, rcx
0x140002a0b  call    cs:__imp_GetCurrentProcessId
0x140002a11  mov     edi, 104h
0x140002a16  mov     [rsp+4A8h+var_480], rbx
0x140002a1b  mov     r9d, eax
0x140002a1e  mov     [rsp+4A8h+var_488], 130h; int
0x140002a26  mov     edx, edi; unsigned __int64
0x140002a28  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002a2f  lea     rcx, [rsp+4A8h+Name]; unsigned __int16 *
0x140002a37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002a3c  mov     r9d, 1F0001h; dwDesiredAccess
0x140002a42  lea     rdx, [rsp+4A8h+Name]; lpName
0x140002a4a  xor     r8d, r8d; dwFlags
0x140002a4d  xor     ecx, ecx; lpMutexAttributes
0x140002a4f  call    cs:__imp_CreateMutexExW
0x140002a55  mov     [rsp+4A8h+var_470], rax
0x140002a5a  mov     rsi, rax
0x140002a5d  test    rax, rax
0x140002a60  jz      loc_140002BFC
0x140002a66  xor     r8d, r8d; bAlertable
0x140002a69  mov     [rsp+4A8h+var_30], r14
0x140002a71  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140002a76  mov     rcx, rax; hHandle
0x140002a79  call    cs:__imp_WaitForSingleObjectEx
0x140002a7f  cmp     eax, 102h
0x140002a84  jz      loc_140002D06
0x140002a8a  test    eax, 0FFFFFF7Fh
0x140002a8f  jnz     loc_140002E12
0x140002a95  mov     r14, rsi
0x140002a98  mov     [rsp+4A8h+arg_10], r12
0x140002aa0  lea     r8, [rsp+4A8h+Name]
0x140002aa8  mov     [rsp+4A8h+var_38], r15
0x140002ab0  lea     rax, [rsp+4A8h+var_468]
0x140002ab5  mov     r15d, 7FFFFFFEh
0x140002abb  mov     r12, rbp
0x140002abe  mov     ecx, r15d
0x140002ac1  mov     rdx, rdi
0x140002ac4  test    rcx, rcx
0x140002ac7  jz      short loc_140002AE8
0x140002ac9  movzx   r9d, word ptr [r8]
0x140002acd  test    r9w, r9w
0x140002ad1  jz      short loc_140002AE8
0x140002ad3  mov     [rax], r9w
0x140002ad7  add     r8, 2
0x140002adb  add     rax, 2
0x140002adf  dec     rcx
0x140002ae2  sub     rdx, 1
0x140002ae6  jnz     short loc_140002AC4
0x140002ae8  test    rdx, rdx
0x140002aeb  lea     rcx, [rax-2]
0x140002aef  mov     rdx, rdi
0x140002af2  cmovnz  rcx, rax
0x140002af6  lea     rax, [rsp+4A8h+var_468]
0x140002afb  mov     [rcx], bp
0x140002afe  xchg    ax, ax
0x140002b00  cmp     [rax], bp
0x140002b03  jz      loc_140002D36
0x140002b09  add     rax, 2
0x140002b0d  sub     rdx, 1
0x140002b11  jnz     short loc_140002B00
0x140002b13  lea     r8, [rsp+4A8h+var_468]; lpName
0x140002b18  xor     edx, edx; bInheritHandle
0x140002b1a  mov     ecx, 1F0003h; dwDesiredAccess
0x140002b1f  call    cs:__imp_OpenSemaphoreW
0x140002b25  mov     rbx, rax
0x140002b28  test    rax, rax
0x140002b2b  jnz     loc_140002C0D
0x140002b31  call    cs:__imp_GetLastError
0x140002b37  cmp     eax, 2
0x140002b3a  jz      loc_140002CCE
0x140002b40  mov     rcx, [rsp+4A8h]; this
0x140002b48  lea     r8, aWil; "wil"
0x140002b4f  mov     edx, 0D0h; void *
0x140002b54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140002b59  mov     ebp, eax
0x140002b5b  test    ebp, ebp
0x140002b5d  jns     loc_140002CCE
0x140002b63  mov     rcx, [rsp+4A8h]; this
0x140002b6b  lea     r8, aWil; "wil"
0x140002b72  mov     r9d, ebp; char *
0x140002b75  mov     edx, 66h ; 'f'; void *
0x140002b7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002b7f  mov     rcx, [rsp+4A8h]; this
0x140002b87  lea     r8, aWil; "wil"
0x140002b8e  mov     r9d, ebp; char *
0x140002b91  mov     edx, 6Fh ; 'o'; void *
0x140002b96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002b9b  mov     rcx, [rsp+4A8h]; this
0x140002ba3  lea     r8, aWil; "wil"
0x140002baa  mov     r9d, ebp; char *
0x140002bad  mov     edx, 12Eh; void *
0x140002bb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002bb7  test    r14, r14
0x140002bba  jnz     short loc_140002C03
0x140002bbc  mov     rcx, rsi; this
0x140002bbf  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002bc4  mov     eax, ebp
0x140002bc6  mov     r12, [rsp+4A8h+arg_10]
0x140002bce  mov     r15, [rsp+4A8h+var_38]
0x140002bd6  mov     r14, [rsp+4A8h+var_30]
0x140002bde  mov     rcx, [rsp+4A8h+var_48]
0x140002be6  xor     rcx, rsp; StackCookie
0x140002be9  call    __security_check_cookie
0x140002bee  add     rsp, 480h
0x140002bf5  pop     r13
0x140002bf7  pop     rdi
0x140002bf8  pop     rsi
0x140002bf9  pop     rbp
0x140002bfa  pop     rbx
0x140002bfb  retn
0x140002bfc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002c01  jmp     short loc_140002BDE
0x140002c03  mov     rcx, r14; this
0x140002c06  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x140002c0b  jmp     short loc_140002BBC
0x140002c0d  lea     rdx, [rsp+4A8h+var_474]; int *
0x140002c12  mov     [rsp+4A8h+var_474], ebp
0x140002c16  mov     rcx, rbx; hHandle
0x140002c19  mov     [rsp+4A8h+var_478], ebp
0x140002c1d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140002c22  mov     ebp, eax
0x140002c24  test    eax, eax
0x140002c26  jns     short loc_140002C51
0x140002c28  mov     rcx, [rsp+4A8h]; this
0x140002c30  lea     r8, aWil; "wil"
0x140002c37  mov     r9d, eax; char *
0x140002c3a  mov     edx, 0D6h; void *
0x140002c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c44  mov     rcx, rbx; this
0x140002c47  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002c4c  jmp     loc_140002B63
0x140002c51  lea     rax, [rsp+4A8h+var_468]
0x140002c56  cmp     [rax], r12w
0x140002c5a  jz      loc_140002D8A
0x140002c60  add     rax, 2
0x140002c64  sub     rdi, 1
0x140002c68  jnz     short loc_140002C56
0x140002c6a  jmp     short loc_140002C7C
0x140002c6c  test    rdi, rdi
0x140002c6f  lea     rdx, [r8-2]
0x140002c73  cmovnz  rdx, r8
0x140002c77  xor     eax, eax
0x140002c79  mov     [rdx], ax
0x140002c7c  lea     r8, [rsp+4A8h+var_468]; lpName
0x140002c81  xor     edx, edx; bInheritHandle
0x140002c83  mov     ecx, 1F0003h; dwDesiredAccess
0x140002c88  call    cs:__imp_OpenSemaphoreW
0x140002c8e  mov     rdi, rax
0x140002c91  test    rax, rax
0x140002c94  jz      short loc_140002D0E
0x140002c96  lea     rdx, [rsp+4A8h+var_478]; int *
0x140002c9b  mov     rcx, rax; hHandle
0x140002c9e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140002ca3  mov     ebp, eax
0x140002ca5  test    eax, eax
0x140002ca7  js      loc_140002E20
0x140002cad  mov     rcx, rdi; this
0x140002cb0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002cb5  movsxd  rax, [rsp+4A8h+var_474]
0x140002cba  mov     rcx, rbx; this
0x140002cbd  movsxd  r12, [rsp+4A8h+var_478]
0x140002cc2  shl     r12, 1Fh
0x140002cc6  or      r12, rax
0x140002cc9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002cce  lea     rcx, ds:0[r12*4]
0x140002cd6  test    rcx, rcx
0x140002cd9  jz      loc_140002E51
0x140002cdf  mov     [r13+0], rcx
0x140002ce3  mov     eax, [rcx]
0x140002ce5  inc     eax
0x140002ce7  mov     [rcx], eax
0x140002ce9  test    r14, r14
0x140002cec  jz      short loc_140002CF6
0x140002cee  mov     rcx, r14; this
0x140002cf1  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x140002cf6  test    rsi, rsi
0x140002cf9  jnz     loc_140002E81
0x140002cff  xor     eax, eax
0x140002d01  jmp     loc_140002BC6
0x140002d06  mov     r14, rbp
0x140002d09  jmp     loc_140002A98
0x140002d0e  mov     rcx, [rsp+4A8h]; this
0x140002d16  lea     r8, aWil; "wil"
0x140002d1d  mov     edx, 0DCh; void *
0x140002d22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140002d27  mov     rcx, rbx; this
0x140002d2a  mov     ebp, eax
0x140002d2c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002d31  jmp     loc_140002B5B
0x140002d36  lea     rax, [rdx+rdx]
0x140002d3a  mov     rcx, r15
0x140002d3d  lea     r8, [rsp+4A8h+var_260]
0x140002d45  sub     r8, rax
0x140002d48  lea     r9, aP0; "_p0"
0x140002d4f  test    rdx, rdx
0x140002d52  jz      short loc_140002D77
0x140002d54  test    rcx, rcx
0x140002d57  jz      short loc_140002D77
0x140002d59  movzx   eax, word ptr [r9]
0x140002d5d  test    ax, ax
0x140002d60  jz      short loc_140002D77
0x140002d62  mov     [r8], ax
0x140002d66  add     r9, 2
0x140002d6a  add     r8, 2
0x140002d6e  dec     rcx
0x140002d71  sub     rdx, 1
0x140002d75  jnz     short loc_140002D54
0x140002d77  test    rdx, rdx
0x140002d7a  lea     rcx, [r8-2]
0x140002d7e  cmovnz  rcx, r8
0x140002d82  mov     [rcx], bp
0x140002d85  jmp     loc_140002B13
0x140002d8a  lea     rax, [rdi+rdi]
0x140002d8e  lea     r8, [rsp+4A8h+var_260]
0x140002d96  sub     r8, rax
0x140002d99  lea     rcx, asc_140021060; "h"
0x140002da0  test    rdi, rdi
0x140002da3  jz      loc_140002C6C
0x140002da9  test    r15, r15
0x140002dac  jz      loc_140002C6C
0x140002db2  movzx   eax, word ptr [rcx]
0x140002db5  test    ax, ax
0x140002db8  jz      loc_140002C6C
0x140002dbe  mov     [r8], ax
0x140002dc2  add     rcx, 2
0x140002dc6  add     r8, 2
0x140002dca  dec     r15
0x140002dcd  sub     rdi, 1
0x140002dd1  jnz     short loc_140002DA9
0x140002dd3  jmp     loc_140002C6C
0x140002dd8  mov     rcx, [rsp+4A8h]; this
0x140002de0  lea     r8, aWil; "wil"
0x140002de7  mov     r9d, ebx; char *
0x140002dea  mov     edx, 137h; void *
0x140002def  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002df4  test    r14, r14
0x140002df7  jz      short loc_140002E01
0x140002df9  mov     rcx, r14; this
0x140002dfc  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x140002e01  mov     rcx, [rsp+4A8h+var_470]; this
0x140002e06  test    rcx, rcx
0x140002e09  jnz     short loc_140002E7A
0x140002e0b  mov     eax, ebx
0x140002e0d  jmp     loc_140002BC6
0x140002e12  mov     rcx, [rsp+4A8h]; this
0x140002e1a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140002e20  mov     rcx, [rsp+4A8h]; this
0x140002e28  lea     r8, aWil; "wil"
0x140002e2f  mov     r9d, eax; char *
0x140002e32  mov     edx, 0DEh; void *
0x140002e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e3c  mov     rcx, rdi; this
0x140002e3f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002e44  mov     rcx, rbx; this
0x140002e47  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002e4c  jmp     loc_140002B63
0x140002e51  mov     r8, r13
0x140002e54  lea     rdx, [rsp+4A8h+var_470]
0x140002e59  lea     rcx, [rsp+4A8h+Name]; unsigned __int16 *
0x140002e61  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140002e66  mov     ebx, eax
0x140002e68  test    eax, eax
0x140002e6a  js      loc_140002DD8
0x140002e70  mov     rsi, [rsp+4A8h+var_470]
0x140002e75  jmp     loc_140002CE9
0x140002e7a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002e7f  jmp     short loc_140002E0B
0x140002e81  mov     rcx, rsi; this
0x140002e84  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002e89  jmp     loc_140002CFF
```
