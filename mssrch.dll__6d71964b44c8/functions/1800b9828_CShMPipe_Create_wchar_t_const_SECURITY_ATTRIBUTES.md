# CShMPipe::Create(wchar_t const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800b9828`
- end: `0x1800b9bde`
- name: `?Create@CShMPipe@@QEAAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `950`
- prototype: `int __fastcall(CShMPipe *this, const wchar_t *lpName, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b9778`

## callees

- `0x180026b58`
- `0x18002751c`
- `0x18004e5d8`
- `0x180056610`
- `0x18006a040`
- `0x18006a618`
- `0x1800b9828`
- `0x1800f8f24`
- `0x1801244c0`
- `0x18012540e`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b99cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b9a2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b9aa4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b99cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b9a2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b9aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b99f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b99f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b98`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b987d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b987d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b9929`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b9929`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800b9b06`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800b9b6d`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800b9b06`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800b9b6d`

## string_xrefs

- `0x1800b9a57`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`
- `0x1800b98bb`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx"`
- `0x1800b994f`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx"`
- `0x1800b9943`: `[UtilCommon] MapViewOfFile() failed! 0x%08x`
- `0x1800b98af`: `[UtilCommon] Failed to create file mapping: %ls. 0x%08x`

## pseudocode

```c
int __fastcall CShMPipe::Create(CShMPipe *this, const wchar_t *lpName, struct _SECURITY_ATTRIBUTES *a3)
{
  HANDLE *v6; // rbx
  HANDLE FileMappingW; // rax
  int result; // eax
  void *v9; // rax
  const wchar_t *LastError; // rbx
  HANDLE EventW; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE SemaphoreW; // rax
  HANDLE v17; // rax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-59h]
  __int64 v19; // [rsp+30h] [rbp-49h] BYREF
  LPCWSTR v20; // [rsp+38h] [rbp-41h]
  unsigned int v21; // [rsp+44h] [rbp-35h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v6 = (HANDLE *)((char *)this + 72);
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, a3, 4u, 0, 0x10000u, lpName);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v6,
    FileMappingW);
  if ( (((unsigned __int64)*v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    CLMString::operator=((char *)this + 152, lpName);
    if ( GetLastError() == 183 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v6,
        0);
      return -2147024665;
    }
    v9 = MapViewOfFile(*v6, 0xF001Fu, 0, 0, 0x10000u);
    *((_QWORD *)this + 10) = v9;
    if ( !v9 )
    {
      LastError = (const wchar_t *)GetLastError();
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\shmpipe.cxx\"",
        (const wchar_t *)0x13F,
        (unsigned int)L"[UtilCommon] MapViewOfFile() failed! 0x%08x",
        LastError);
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
      return (int)LastError;
    }
    memset_0(v9, 0, 0x98u);
    *(_DWORD *)(*((_QWORD *)this + 10) + 128LL) = 65384;
    TLMString<32,32,1024>::TLMString<32,32,1024>(&v19, lpName);
    (*(void (__fastcall **)(__int64 *, const wchar_t *, _QWORD, __int64))(v19 + 32))(&v19, L"DRE", v21, 0xFFFFFFFFLL);
    EventW = CreateEventW(a3, 0, 0, v20);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 88,
      EventW);
    if ( ((*((_QWORD *)this + 11) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v13 = 331;
LABEL_14:
      LODWORD(LastError) = wil::details::in1diag3::Return_GetLastError(
                             retaddr,
                             (void *)v13,
                             (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
                             v12);
LABEL_27:
      TLMString<32,32,1024>::~TLMString<32,32,1024>(&v19);
      return (int)LastError;
    }
    if ( GetLastError() != 183 )
    {
      CLMString::operator=(&v19, lpName);
      CLMString::Append((CLMString *)&v19, L"DAE", 0xFFFFFFFF);
      v14 = CreateEventW(a3, 0, 0, v20);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 96,
        v14);
      if ( ((*((_QWORD *)this + 12) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v13 = 342;
        goto LABEL_14;
      }
      if ( GetLastError() != 183 )
      {
        CLMString::operator=(&v19, lpName);
        CLMString::Append((CLMString *)&v19, L"DSE", 0xFFFFFFFF);
        v15 = CreateEventW(a3, 0, 0, v20);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 104,
          v15);
        if ( ((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v13 = 353;
          goto LABEL_14;
        }
        if ( GetLastError() != 183 )
        {
          CLMString::operator=(&v19, lpName);
          CLMString::Append((CLMString *)&v19, L"TRM", 0xFFFFFFFF);
          SemaphoreW = CreateSemaphoreW(a3, 0, 1, v20);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            (char *)this + 112,
            SemaphoreW);
          if ( ((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            v13 = 366;
            goto LABEL_14;
          }
          if ( GetLastError() != 183 )
          {
            *((_WORD *)this + 4) = 1;
            CLMString::operator=(&v19, lpName);
            CLMString::Append((CLMString *)&v19, L"RCM", 0xFFFFFFFF);
            v17 = CreateSemaphoreW(a3, 1, 1, v20);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              (char *)this + 120,
              v17);
            if ( ((*((_QWORD *)this + 15) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
            {
              v13 = 379;
              goto LABEL_14;
            }
            if ( GetLastError() != 183 )
            {
              LODWORD(LastError) = 0;
              goto LABEL_27;
            }
          }
        }
      }
    }
    LODWORD(LastError) = -2147024665;
    goto LABEL_27;
  }
  dwMaximumSizeLow[0] = GetLastError();
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\shmpipe.cxx\"",
    (const wchar_t *)0x128,
    (unsigned int)L"[UtilCommon] Failed to create file mapping: %ls. 0x%08x",
    lpName,
    *(_QWORD *)dwMaximumSizeLow);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800b9828  mov     [rsp-8+arg_18], rbx
0x1800b982d  push    rbp
0x1800b982e  push    rsi
0x1800b982f  push    rdi
0x1800b9830  push    r12
0x1800b9832  push    r13
0x1800b9834  push    r14
0x1800b9836  push    r15
0x1800b9838  lea     rbp, [rsp-27h]
0x1800b983d  sub     rsp, 0A0h
0x1800b9844  mov     rax, cs:__security_cookie
0x1800b984b  xor     rax, rsp
0x1800b984e  mov     [rbp+57h+var_40], rax
0x1800b9852  mov     r14, r8
0x1800b9855  mov     rsi, rdx
0x1800b9858  mov     rdi, rcx
0x1800b985b  lea     rbx, [rcx+48h]
0x1800b985f  mov     [rsp+0D0h+lpName], rdx; lpName
0x1800b9864  mov     r13d, 10000h
0x1800b986a  mov     [rsp+0D0h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x1800b986f  xor     r9d, r9d; dwMaximumSizeHigh
0x1800b9872  lea     r8d, [r9+4]; flProtect
0x1800b9876  mov     rdx, r14; lpFileMappingAttributes
0x1800b9879  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800b987d  call    cs:__imp_CreateFileMappingW
0x1800b9883  mov     rdx, rax
0x1800b9886  mov     rcx, rbx
0x1800b9889  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b988e  mov     rax, [rbx]
0x1800b9891  mov     r12d, 1
0x1800b9897  add     rax, r12
0x1800b989a  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b98a0  jnz     short loc_1800B98E2
0x1800b98a2  call    cs:__imp_GetLastError
0x1800b98a8  mov     [rsp+0D0h+dwMaximumSizeLow], eax
0x1800b98ac  mov     r9, rsi; wchar_t *
0x1800b98af  lea     r8, aUtilcommonFail_4; "[UtilCommon] Failed to create file mapp"...
0x1800b98b6  mov     edx, 128h; wchar_t *
0x1800b98bb  lea     rcx, aOnecoreuapBase_44; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800b98c2  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800b98c7  call    cs:__imp_GetLastError
0x1800b98cd  test    eax, eax
0x1800b98cf  jle     loc_1800B9BB7
0x1800b98d5  movzx   eax, ax
0x1800b98d8  or      eax, 80070000h
0x1800b98dd  jmp     loc_1800B9BB7
0x1800b98e2  lea     rcx, [rdi+98h]
0x1800b98e9  mov     rdx, rsi
0x1800b98ec  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b98f1  call    cs:__imp_GetLastError
0x1800b98f7  mov     r15d, 0B7h
0x1800b98fd  cmp     eax, r15d
0x1800b9900  jnz     short loc_1800B9916
0x1800b9902  xor     edx, edx
0x1800b9904  mov     rcx, rbx
0x1800b9907  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b990c  mov     eax, 800700E7h
0x1800b9911  jmp     loc_1800B9BB7
0x1800b9916  mov     qword ptr [rsp+0D0h+dwMaximumSizeLow], r13; dwNumberOfBytesToMap
0x1800b991b  xor     r9d, r9d; dwFileOffsetLow
0x1800b991e  xor     r8d, r8d; dwFileOffsetHigh
0x1800b9921  mov     edx, 0F001Fh; dwDesiredAccess
0x1800b9926  mov     rcx, [rbx]; hFileMappingObject
0x1800b9929  call    cs:__imp_MapViewOfFile
0x1800b992f  mov     [rdi+50h], rax
0x1800b9933  test    rax, rax
0x1800b9936  jnz     short loc_1800B9971
0x1800b9938  call    cs:__imp_GetLastError
0x1800b993e  mov     ebx, eax
0x1800b9940  mov     r9d, eax; wchar_t *
0x1800b9943  lea     r8, aUtilcommonMapv; "[UtilCommon] MapViewOfFile() failed! 0x"...
0x1800b994a  mov     edx, 13Fh; wchar_t *
0x1800b994f  lea     rcx, aOnecoreuapBase_44; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800b9956  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800b995b  test    ebx, ebx
0x1800b995d  jle     loc_1800B9BB5
0x1800b9963  movzx   ebx, bx
0x1800b9966  or      ebx, 80070000h
0x1800b996c  jmp     loc_1800B9BB5
0x1800b9971  xor     edx, edx; Val
0x1800b9973  mov     r8d, 98h; Size
0x1800b9979  mov     rcx, rax; void *
0x1800b997c  call    memset_0
0x1800b9981  mov     rax, [rdi+50h]
0x1800b9985  mov     dword ptr [rax+80h], 0FF68h
0x1800b998f  mov     rdx, rsi
0x1800b9992  lea     rcx, [rbp+57h+var_A0]
0x1800b9996  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800b999b  nop
0x1800b999c  mov     rax, [rbp+57h+var_A0]
0x1800b99a0  or      r13d, 0FFFFFFFFh
0x1800b99a4  mov     r9d, r13d
0x1800b99a7  mov     r8d, [rbp+57h+var_8C]
0x1800b99ab  lea     rdx, aDre; "DRE"
0x1800b99b2  lea     rcx, [rbp+57h+var_A0]
0x1800b99b6  mov     rax, [rax+20h]
0x1800b99ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99bf  mov     r9, [rbp+57h+var_98]; lpName
0x1800b99c3  xor     r8d, r8d; bInitialState
0x1800b99c6  xor     edx, edx; bManualReset
0x1800b99c8  mov     rcx, r14; lpEventAttributes
0x1800b99cb  call    cs:__imp_CreateEventW
0x1800b99d1  mov     rdx, rax
0x1800b99d4  lea     rcx, [rdi+58h]
0x1800b99d8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b99dd  mov     rax, [rdi+58h]
0x1800b99e1  add     rax, r12
0x1800b99e4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b99ea  jnz     short loc_1800B99F3
0x1800b99ec  mov     edx, 14Bh
0x1800b99f1  jmp     short loc_1800B9A53
0x1800b99f3  call    cs:__imp_GetLastError
0x1800b99f9  cmp     eax, r15d
0x1800b99fc  jz      loc_1800B9BA7
0x1800b9a02  mov     rdx, rsi
0x1800b9a05  lea     rcx, [rbp+57h+var_A0]
0x1800b9a09  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b9a0e  mov     r8d, r13d; unsigned int
0x1800b9a11  lea     rdx, aDae; "DAE"
0x1800b9a18  lea     rcx, [rbp+57h+var_A0]; this
0x1800b9a1c  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800b9a21  mov     r9, [rbp+57h+var_98]; lpName
0x1800b9a25  xor     r8d, r8d; bInitialState
0x1800b9a28  xor     edx, edx; bManualReset
0x1800b9a2a  mov     rcx, r14; lpEventAttributes
0x1800b9a2d  call    cs:__imp_CreateEventW
0x1800b9a33  mov     rdx, rax
0x1800b9a36  lea     rcx, [rdi+60h]
0x1800b9a3a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b9a3f  mov     rax, [rdi+60h]
0x1800b9a43  add     rax, r12
0x1800b9a46  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b9a4c  jnz     short loc_1800B9A6A
0x1800b9a4e  mov     edx, 156h; void *
0x1800b9a53  mov     rcx, [rbp+5Fh]; this
0x1800b9a57  lea     r8, aOnecoreuapBase_116; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800b9a5e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b9a63  mov     ebx, eax
0x1800b9a65  jmp     loc_1800B9BAC
0x1800b9a6a  call    cs:__imp_GetLastError
0x1800b9a70  cmp     eax, r15d
0x1800b9a73  jz      loc_1800B9BA7
0x1800b9a79  mov     rdx, rsi
0x1800b9a7c  lea     rcx, [rbp+57h+var_A0]
0x1800b9a80  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b9a85  mov     r8d, r13d; unsigned int
0x1800b9a88  lea     rdx, aDse; "DSE"
0x1800b9a8f  lea     rcx, [rbp+57h+var_A0]; this
0x1800b9a93  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800b9a98  mov     r9, [rbp+57h+var_98]; lpName
0x1800b9a9c  xor     r8d, r8d; bInitialState
0x1800b9a9f  xor     edx, edx; bManualReset
0x1800b9aa1  mov     rcx, r14; lpEventAttributes
0x1800b9aa4  call    cs:__imp_CreateEventW
0x1800b9aaa  mov     rdx, rax
0x1800b9aad  lea     rcx, [rdi+68h]
0x1800b9ab1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b9ab6  mov     rax, [rdi+68h]
0x1800b9aba  add     rax, r12
0x1800b9abd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b9ac3  jnz     short loc_1800B9ACC
0x1800b9ac5  mov     edx, 161h
0x1800b9aca  jmp     short loc_1800B9A53
0x1800b9acc  call    cs:__imp_GetLastError
0x1800b9ad2  cmp     eax, r15d
0x1800b9ad5  jz      loc_1800B9BA7
0x1800b9adb  mov     rdx, rsi
0x1800b9ade  lea     rcx, [rbp+57h+var_A0]
0x1800b9ae2  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b9ae7  mov     r8d, r13d; unsigned int
0x1800b9aea  lea     rdx, aTrm; "TRM"
0x1800b9af1  lea     rcx, [rbp+57h+var_A0]; this
0x1800b9af5  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800b9afa  mov     r9, [rbp+57h+var_98]; lpName
0x1800b9afe  mov     r8d, r12d; lMaximumCount
0x1800b9b01  xor     edx, edx; lInitialCount
0x1800b9b03  mov     rcx, r14; lpSemaphoreAttributes
0x1800b9b06  call    cs:__imp_CreateSemaphoreW
0x1800b9b0c  mov     rdx, rax
0x1800b9b0f  lea     rcx, [rdi+70h]
0x1800b9b13  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b9b18  mov     rax, [rdi+70h]
0x1800b9b1c  add     rax, r12
0x1800b9b1f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b9b25  jnz     short loc_1800B9B31
0x1800b9b27  mov     edx, 16Eh
0x1800b9b2c  jmp     loc_1800B9A53
0x1800b9b31  call    cs:__imp_GetLastError
0x1800b9b37  cmp     eax, r15d
0x1800b9b3a  jz      short loc_1800B9BA7
0x1800b9b3c  mov     [rdi+8], r12w
0x1800b9b41  mov     rdx, rsi
0x1800b9b44  lea     rcx, [rbp+57h+var_A0]
0x1800b9b48  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b9b4d  mov     r8d, r13d; unsigned int
0x1800b9b50  lea     rdx, aRcm; "RCM"
0x1800b9b57  lea     rcx, [rbp+57h+var_A0]; this
0x1800b9b5b  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800b9b60  mov     r9, [rbp+57h+var_98]; lpName
0x1800b9b64  mov     r8d, r12d; lMaximumCount
0x1800b9b67  mov     edx, r12d; lInitialCount
0x1800b9b6a  mov     rcx, r14; lpSemaphoreAttributes
0x1800b9b6d  call    cs:__imp_CreateSemaphoreW
0x1800b9b73  mov     rdx, rax
0x1800b9b76  lea     rcx, [rdi+78h]
0x1800b9b7a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b9b7f  mov     rax, [rdi+78h]
0x1800b9b83  add     rax, r12
0x1800b9b86  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b9b8c  jnz     short loc_1800B9B98
0x1800b9b8e  mov     edx, 17Bh
0x1800b9b93  jmp     loc_1800B9A53
0x1800b9b98  call    cs:__imp_GetLastError
0x1800b9b9e  cmp     eax, r15d
0x1800b9ba1  jz      short loc_1800B9BA7
0x1800b9ba3  xor     ebx, ebx
0x1800b9ba5  jmp     short loc_1800B9BAC
0x1800b9ba7  mov     ebx, 800700E7h
0x1800b9bac  lea     rcx, [rbp+57h+var_A0]
0x1800b9bb0  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800b9bb5  mov     eax, ebx
0x1800b9bb7  mov     rcx, [rbp+57h+var_40]
0x1800b9bbb  xor     rcx, rsp; StackCookie
0x1800b9bbe  call    __security_check_cookie
0x1800b9bc3  mov     rbx, [rsp+0D0h+arg_18]
0x1800b9bcb  add     rsp, 0A0h
0x1800b9bd2  pop     r15
0x1800b9bd4  pop     r14
0x1800b9bd6  pop     r13
0x1800b9bd8  pop     r12
0x1800b9bda  pop     rdi
0x1800b9bdb  pop     rsi
0x1800b9bdc  pop     rbp
0x1800b9bdd  retn
```
