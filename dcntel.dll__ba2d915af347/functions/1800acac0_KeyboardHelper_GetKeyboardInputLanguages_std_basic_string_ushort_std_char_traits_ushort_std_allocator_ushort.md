# KeyboardHelper::GetKeyboardInputLanguages(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800acac0`
- end: `0x1800acc0b`
- name: `?GetKeyboardInputLanguages@KeyboardHelper@@UEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180008dc0`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x1800ac980`
- `0x1800acac0`
- `0x1800acc14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800acbc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800acbc1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800acb18`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800acb18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800acb32`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800acb53`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800acb32`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800acb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acb8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acb8a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800acb7f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800acb7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acbaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acbaf`

## pseudocode

```c
__int64 __fastcall KeyboardHelper::GetKeyboardInputLanguages(__int64 a1, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  HANDLE Thread; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  __int64 v8; // rcx
  __int64 KeyboardInputLanguages; // rax
  KeyboardHelper *v10; // rcx
  char *v12[4]; // [rsp+30h] [rbp-38h] BYREF

  if ( *(_QWORD *)(a2 + 24) )
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v4 = (char *)a2;
    else
      v4 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = 1;
    *(_DWORD *)v4 = 35;
  }
  else
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a2,
      1u,
      a3,
      L"#");
  }
  InitializeCriticalSection(&KeyboardHelper::g_cs);
  if ( KeyboardWinRTClient::s_hInit == (HANDLE)-1LL )
    KeyboardWinRTClient::s_hInit = CreateEventW(0, 0, 0, 0);
  if ( KeyboardWinRTClient::s_hUnInit == (HANDLE)-1LL )
    KeyboardWinRTClient::s_hUnInit = CreateEventW(0, 0, 0, 0);
  Thread = CreateThread(0, 0, KeyboardHelper::ThreadProc, 0, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
    WaitForSingleObject(KeyboardWinRTClient::s_hInit, 0x493E0u);
    KeyboardInputLanguages = KeyboardWinRTClient::GetKeyboardInputLanguages(v8, v12);
    std::wstring::operator=(a2, KeyboardInputLanguages);
    std::wstring::~wstring(v12);
    return (unsigned int)KeyboardHelper::Deinitialize(v10);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800acac0  mov     [rsp+arg_0], rbx
0x1800acac5  push    rdi
0x1800acac6  sub     rsp, 60h
0x1800acaca  mov     rax, cs:__security_cookie
0x1800acad1  xor     rax, rsp
0x1800acad4  mov     [rsp+68h+var_18], rax
0x1800acad9  mov     rdi, rdx
0x1800acadc  mov     edx, 1
0x1800acae1  cmp     [rdi+18h], rdx
0x1800acae5  jb      short loc_1800ACB02
0x1800acae7  cmp     qword ptr [rdi+18h], 7
0x1800acaec  jbe     short loc_1800ACAF3
0x1800acaee  mov     rcx, [rdi]
0x1800acaf1  jmp     short loc_1800ACAF6
0x1800acaf3  mov     rcx, rdi
0x1800acaf6  mov     [rdi+10h], rdx
0x1800acafa  mov     dword ptr [rcx], 23h ; '#'
0x1800acb00  jmp     short loc_1800ACB11
0x1800acb02  lea     r9, asc_1801B4764; "#"
0x1800acb09  mov     rcx, rdi
0x1800acb0c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800acb11  lea     rcx, ?g_cs@KeyboardHelper@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800acb18  call    cs:__imp_InitializeCriticalSection
0x1800acb1e  cmp     cs:?s_hInit@KeyboardWinRTClient@@2PEAXEA, 0FFFFFFFFFFFFFFFFh; void * KeyboardWinRTClient::s_hInit
0x1800acb26  jnz     short loc_1800ACB3F
0x1800acb28  xor     r9d, r9d; lpName
0x1800acb2b  xor     r8d, r8d; bInitialState
0x1800acb2e  xor     edx, edx; bManualReset
0x1800acb30  xor     ecx, ecx; lpEventAttributes
0x1800acb32  call    cs:__imp_CreateEventW
0x1800acb38  mov     cs:?s_hInit@KeyboardWinRTClient@@2PEAXEA, rax; void * KeyboardWinRTClient::s_hInit
0x1800acb3f  cmp     cs:?s_hUnInit@KeyboardWinRTClient@@2PEAXEA, 0FFFFFFFFFFFFFFFFh; void * KeyboardWinRTClient::s_hUnInit
0x1800acb47  jnz     short loc_1800ACB60
0x1800acb49  xor     r9d, r9d; lpName
0x1800acb4c  xor     r8d, r8d; bInitialState
0x1800acb4f  xor     edx, edx; bManualReset
0x1800acb51  xor     ecx, ecx; lpEventAttributes
0x1800acb53  call    cs:__imp_CreateEventW
0x1800acb59  mov     cs:?s_hUnInit@KeyboardWinRTClient@@2PEAXEA, rax; void * KeyboardWinRTClient::s_hUnInit
0x1800acb60  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1800acb69  lea     r8, ?ThreadProc@KeyboardHelper@@CAKPEAX@Z; lpStartAddress
0x1800acb70  xor     r9d, r9d; lpParameter
0x1800acb73  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800acb7b  xor     edx, edx; dwStackSize
0x1800acb7d  xor     ecx, ecx; lpThreadAttributes
0x1800acb7f  call    cs:__imp_CreateThread
0x1800acb85  test    rax, rax
0x1800acb88  jnz     short loc_1800ACBAA
0x1800acb8a  call    cs:__imp_GetLastError
0x1800acb90  mov     ebx, eax
0x1800acb92  test    eax, eax
0x1800acb94  jle     short loc_1800ACB9F
0x1800acb96  movzx   ebx, ax
0x1800acb99  or      ebx, 80070000h
0x1800acb9f  test    ebx, ebx
0x1800acba1  js      short loc_1800ACBF1
0x1800acba3  mov     ebx, 80004005h
0x1800acba8  jmp     short loc_1800ACBF1
0x1800acbaa  mov     rcx, rax; hObject
0x1800acbad  xor     ebx, ebx
0x1800acbaf  call    cs:__imp_CloseHandle
0x1800acbb5  mov     rcx, cs:?s_hInit@KeyboardWinRTClient@@2PEAXEA; hHandle
0x1800acbbc  mov     edx, 493E0h; dwMilliseconds
0x1800acbc1  call    cs:__imp_WaitForSingleObject
0x1800acbc7  test    ebx, ebx
0x1800acbc9  js      short loc_1800ACBF1
0x1800acbcb  lea     rdx, [rsp+68h+var_38]
0x1800acbd0  call    ?GetKeyboardInputLanguages@KeyboardWinRTClient@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; KeyboardWinRTClient::GetKeyboardInputLanguages(void)
0x1800acbd5  mov     rdx, rax
0x1800acbd8  mov     rcx, rdi
0x1800acbdb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800acbe0  lea     rcx, [rsp+68h+var_38]
0x1800acbe5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800acbea  call    ?Deinitialize@KeyboardHelper@@AEAAJXZ; KeyboardHelper::Deinitialize(void)
0x1800acbef  mov     ebx, eax
0x1800acbf1  mov     eax, ebx
0x1800acbf3  mov     rcx, [rsp+68h+var_18]
0x1800acbf8  xor     rcx, rsp; StackCookie
0x1800acbfb  call    __security_check_cookie
0x1800acc00  mov     rbx, [rsp+68h+arg_0]
0x1800acc05  add     rsp, 60h
0x1800acc09  pop     rdi
0x1800acc0a  retn
```
