# _lambda_9b936dc34a186e2f55ee034f75ab9bf7_::operator()

- ea: `0x1800ac664`
- end: `0x1800ac8e5`
- name: `_lambda_9b936dc34a186e2f55ee034f75ab9bf7_::operator()`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800acfe0`

## callees

- `0x180013708`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002b470`
- `0x1800ac664`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ac6a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ac6a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac747`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac76a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac747`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac76a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ac841`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ac85a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ac841`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ac85a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac8bf`

## string_xrefs

- `0x1800ac6a1`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800ac73c`: `WindowsDeleteString`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_9b936dc34a186e2f55ee034f75ab9bf7_::operator()(__int64 **a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v5)(__int64, __int64 *); // r14
  __int64 *v6; // rbx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 *v9; // rax
  _WORD *v10; // rcx
  FARPROC ProcAddress; // r15
  FARPROC v12; // r14
  unsigned int v13; // esi
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // r12
  __int64 v16; // rcx
  void *v17; // rax
  BOOL v18; // eax
  unsigned int v19; // r8d
  const char *v20; // r9
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rcx
  signed int LastError; // eax
  int v25; // edx
  unsigned int v26; // r8d
  __int64 v27; // [rsp+20h] [rbp-20h] BYREF
  __int64 v28; // [rsp+28h] [rbp-18h] BYREF
  const int *v29; // [rsp+30h] [rbp-10h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned int v32; // [rsp+88h] [rbp+48h] BYREF
  int v33; // [rsp+8Ch] [rbp+4Ch]
  int v34; // [rsp+98h] [rbp+58h] BYREF

  v33 = HIDWORD(a2);
  v27 = 0;
  v32 = 0;
  v28 = 0;
  v34 = 0;
  v29 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  if ( hModule )
  {
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 48LL);
    v6 = *a1;
    v7 = **a1;
    if ( v7 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v5(a3, v6);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)**a1 + 56LL))(**a1, &v32);
      if ( v8 >= 0 )
      {
        v9 = *a1;
        if ( (unsigned __int64)(*a1)[7] <= 7 )
          v10 = v9 + 4;
        else
          v10 = (_WORD *)v9[4];
        v9[6] = 0;
        *v10 = 0;
        ProcAddress = GetProcAddress(hModule, "WindowsDeleteString");
        if ( ProcAddress && (v12 = GetProcAddress(hModule, "WindowsGetStringRawBuffer")) != 0 )
        {
          v13 = 0;
          if ( v32 )
          {
            while ( 1 )
            {
              v14 = **a1;
              v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 48LL);
              v16 = v27;
              if ( v27 )
              {
                v27 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              }
              v8 = v15(v14, v13, &v27);
              if ( v8 < 0 )
                break;
              v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 192LL))(v27, &v28);
              if ( v8 < 0 )
                break;
              v17 = (void *)((__int64 (__fastcall *)(__int64, int *))v12)(v28, &v34);
              if ( v34 )
              {
                std::wstring::append(*a1 + 4, v17);
                std::wstring::append(*a1 + 4, L";");
              }
              ((void (__fastcall *)(__int64))ProcAddress)(v28);
              if ( ++v13 >= v32 )
                goto LABEL_20;
            }
          }
          else
          {
LABEL_20:
            v18 = SetEvent((HANDLE)(*a1)[2]);
            v21 = retaddr;
            if ( !v18 )
              goto LABEL_33;
            SetEvent(KeyboardWinRTClient::s_hInit);
          }
        }
        else
        {
          v8 = -2147467263;
        }
      }
    }
  }
  else
  {
    v8 = 126;
  }
  v29 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( !hModule )
    goto LABEL_27;
  if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v29) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v25, v26);
LABEL_33:
    wil::details::in1diag3::_FailFast_GetLastError(v21, (void *)0xA01, v19, v20);
  }
  hModule = 0;
LABEL_27:
  v22 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ac664  mov     [rsp-38h+arg_0], rbx
0x1800ac669  mov     [rsp-38h+arg_8], rdx
0x1800ac66e  push    rbp
0x1800ac66f  push    rsi
0x1800ac670  push    rdi
0x1800ac671  push    r12
0x1800ac673  push    r13
0x1800ac675  push    r14
0x1800ac677  push    r15
0x1800ac679  mov     rbp, rsp
0x1800ac67c  sub     rsp, 40h
0x1800ac680  mov     rsi, r8
0x1800ac683  mov     rdi, rcx
0x1800ac686  xor     r13d, r13d
0x1800ac689  mov     [rbp+var_20], r13
0x1800ac68d  mov     dword ptr [rbp+arg_8], r13d
0x1800ac691  mov     [rbp+var_18], r13
0x1800ac695  mov     [rbp+arg_18], r13d
0x1800ac699  xor     edx, edx; hFile
0x1800ac69b  mov     r8d, 800h; dwFlags
0x1800ac6a1  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800ac6a8  call    cs:__imp_LoadLibraryExW
0x1800ac6ae  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800ac6b5  mov     [rbp+var_10], r12
0x1800ac6b9  mov     [rbp+hModule], rax
0x1800ac6bd  test    rax, rax
0x1800ac6c0  jz      loc_1800AC86B
0x1800ac6c6  mov     rax, [rsi]
0x1800ac6c9  mov     r14, [rax+30h]
0x1800ac6cd  mov     rbx, [rdi]
0x1800ac6d0  mov     rcx, [rbx]
0x1800ac6d3  test    rcx, rcx
0x1800ac6d6  jz      short loc_1800AC6E8
0x1800ac6d8  mov     [rbx], r13
0x1800ac6db  mov     r8, [rcx]
0x1800ac6de  mov     rax, [r8+10h]
0x1800ac6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac6e7  nop
0x1800ac6e8  mov     rdx, rbx
0x1800ac6eb  mov     rcx, rsi
0x1800ac6ee  mov     rax, r14
0x1800ac6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac6f6  mov     ebx, eax
0x1800ac6f8  test    eax, eax
0x1800ac6fa  js      loc_1800AC870
0x1800ac700  mov     rax, [rdi]
0x1800ac703  mov     rcx, [rax]
0x1800ac706  mov     rax, [rcx]
0x1800ac709  lea     rdx, [rbp+arg_8]
0x1800ac70d  mov     rax, [rax+38h]
0x1800ac711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac716  mov     ebx, eax
0x1800ac718  test    eax, eax
0x1800ac71a  js      loc_1800AC870
0x1800ac720  mov     rax, [rdi]
0x1800ac723  cmp     qword ptr [rax+38h], 7
0x1800ac728  jbe     short loc_1800AC730
0x1800ac72a  mov     rcx, [rax+20h]
0x1800ac72e  jmp     short loc_1800AC734
0x1800ac730  lea     rcx, [rax+20h]
0x1800ac734  mov     [rax+30h], r13
0x1800ac738  mov     [rcx], r13w
0x1800ac73c  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x1800ac743  mov     rcx, [rbp+hModule]; hModule
0x1800ac747  call    cs:__imp_GetProcAddress
0x1800ac74d  mov     r15, rax
0x1800ac750  test    rax, rax
0x1800ac753  jnz     short loc_1800AC75F
0x1800ac755  mov     ebx, 80004001h
0x1800ac75a  jmp     loc_1800AC870
0x1800ac75f  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x1800ac766  mov     rcx, [rbp+hModule]; hModule
0x1800ac76a  call    cs:__imp_GetProcAddress
0x1800ac770  mov     r14, rax
0x1800ac773  test    rax, rax
0x1800ac776  jz      short loc_1800AC755
0x1800ac778  mov     esi, r13d
0x1800ac77b  cmp     dword ptr [rbp+arg_8], r13d
0x1800ac77f  jbe     loc_1800AC83A
0x1800ac785  mov     rax, [rdi]
0x1800ac788  mov     rbx, [rax]
0x1800ac78b  mov     rax, [rbx]
0x1800ac78e  mov     r12, [rax+30h]
0x1800ac792  mov     rcx, [rbp+var_20]
0x1800ac796  test    rcx, rcx
0x1800ac799  jz      short loc_1800AC7AC
0x1800ac79b  mov     [rbp+var_20], r13
0x1800ac79f  mov     rdx, [rcx]
0x1800ac7a2  mov     rax, [rdx+10h]
0x1800ac7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7ab  nop
0x1800ac7ac  lea     r8, [rbp+var_20]
0x1800ac7b0  mov     edx, esi
0x1800ac7b2  mov     rcx, rbx
0x1800ac7b5  mov     rax, r12
0x1800ac7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7bd  mov     ebx, eax
0x1800ac7bf  test    eax, eax
0x1800ac7c1  js      loc_1800AC862
0x1800ac7c7  mov     rcx, [rbp+var_20]
0x1800ac7cb  mov     rax, [rcx]
0x1800ac7ce  lea     rdx, [rbp+var_18]
0x1800ac7d2  mov     rax, [rax+0C0h]
0x1800ac7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7de  mov     ebx, eax
0x1800ac7e0  test    eax, eax
0x1800ac7e2  js      short loc_1800AC862
0x1800ac7e4  lea     rdx, [rbp+arg_18]
0x1800ac7e8  mov     rcx, [rbp+var_18]
0x1800ac7ec  mov     rax, r14
0x1800ac7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7f4  cmp     [rbp+arg_18], r13d
0x1800ac7f8  jbe     short loc_1800AC81C
0x1800ac7fa  mov     rcx, [rdi]
0x1800ac7fd  add     rcx, 20h ; ' '; Src
0x1800ac801  mov     rdx, rax; void *
0x1800ac804  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800ac809  mov     rcx, [rdi]
0x1800ac80c  add     rcx, 20h ; ' '; Src
0x1800ac810  lea     rdx, asc_1801B9DA0; ";"
0x1800ac817  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800ac81c  mov     rcx, [rbp+var_18]
0x1800ac820  mov     rax, r15
0x1800ac823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac828  inc     esi
0x1800ac82a  cmp     esi, dword ptr [rbp+arg_8]
0x1800ac82d  jb      loc_1800AC785
0x1800ac833  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800ac83a  mov     rcx, [rdi]
0x1800ac83d  mov     rcx, [rcx+10h]; hEvent
0x1800ac841  call    cs:__imp_SetEvent
0x1800ac847  mov     rcx, [rbp+38h]
0x1800ac84b  test    eax, eax
0x1800ac84d  jz      loc_1800AC8DA
0x1800ac853  mov     rcx, cs:?s_hInit@KeyboardWinRTClient@@2PEAXEA; hEvent
0x1800ac85a  call    cs:__imp_SetEvent
0x1800ac860  jmp     short loc_1800AC870
0x1800ac862  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800ac869  jmp     short loc_1800AC870
0x1800ac86b  mov     ebx, 7Eh ; '~'
0x1800ac870  mov     [rbp+var_10], r12
0x1800ac874  cmp     [rbp+hModule], r13
0x1800ac878  jz      short loc_1800AC88B
0x1800ac87a  lea     rcx, [rbp+var_10]
0x1800ac87e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800ac883  test    al, al
0x1800ac885  jz      short loc_1800AC8BF
0x1800ac887  mov     [rbp+hModule], r13
0x1800ac88b  mov     rcx, [rbp+var_20]
0x1800ac88f  test    rcx, rcx
0x1800ac892  jz      short loc_1800AC8A5
0x1800ac894  mov     [rbp+var_20], r13
0x1800ac898  mov     rax, [rcx]
0x1800ac89b  mov     rax, [rax+10h]
0x1800ac89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8a4  nop
0x1800ac8a5  mov     eax, ebx
0x1800ac8a7  mov     rbx, [rsp+40h+arg_0]
0x1800ac8af  add     rsp, 40h
0x1800ac8b3  pop     r15
0x1800ac8b5  pop     r14
0x1800ac8b7  pop     r13
0x1800ac8b9  pop     r12
0x1800ac8bb  pop     rdi
0x1800ac8bc  pop     rsi
0x1800ac8bd  pop     rbp
0x1800ac8be  retn
0x1800ac8bf  call    cs:__imp_GetLastError
0x1800ac8c5  nop
0x1800ac8c6  test    eax, eax
0x1800ac8c8  jle     short loc_1800AC8D2
0x1800ac8ca  movzx   eax, ax
0x1800ac8cd  or      eax, 80070000h
0x1800ac8d2  mov     ecx, eax; this
0x1800ac8d4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800ac8d9  nop
0x1800ac8da  mov     edx, 0A01h; void *
0x1800ac8df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
