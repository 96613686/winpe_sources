# COsInfo::GetAssignedAccessStatus(void)

- ea: `0x1800567a0`
- end: `0x180056a08`
- name: `?GetAssignedAccessStatus@COsInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009ef0`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800567a0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005681a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005681a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056842`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056856`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056842`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800569ee`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800568be`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800568be`

## string_xrefs

- `0x180056838`: `WindowsCreateStringReference`
- `0x180056813`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18005687d`: `Windows.Internal.AssignedAccess.AssignedAccessStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall COsInfo::GetAssignedAccessStatus(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  FARPROC v5; // rax
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rsi
  int v7; // ebx
  _WORD *v8; // rax
  __int64 v9; // r8
  unsigned __int64 v10; // rdx
  char *v11; // rsi
  __int64 v12; // rbx
  signed int LastError; // eax
  int v15; // edx
  unsigned int v16; // r8d
  __int64 v17; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  int v19; // [rsp+40h] [rbp-29h]
  const int *v20; // [rsp+48h] [rbp-21h] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-19h]
  _QWORD v22[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1h] BYREF
  __int128 v24; // [rsp+70h] [rbp+7h]

  v22[1] = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
  v19 = 1;
  v17 = 0;
  v22[0] = 0;
  v23 = 0;
  v24 = 0;
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WindowsCreateStringReference");
    v5 = GetProcAddress(hModule, "WindowsGetStringRawBuffer");
    v6 = (__int64 (__fastcall *)(_QWORD, _QWORD))v5;
    if ( ProcAddress )
    {
      if ( v5 )
      {
        if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *, _QWORD *))ProcAddress)(
               L"Windows.Internal.AssignedAccess.AssignedAccessStatus",
               52,
               &v23,
               v22) >= 0 )
        {
          v17 = 0;
          v18 = 0;
          if ( (int)RoActivateInstance(v22[0], &v18) >= 0 )
          {
            if ( !memcmp_0(
                    &GUID_a3b975f3_840a_49ce_abf3_b1f2c4457208,
                    &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                    0x10u) )
            {
              v17 = v18;
            }
            else
            {
              v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
                     v18,
                     &GUID_a3b975f3_840a_49ce_abf3_b1f2c4457208,
                     &v17);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              if ( v7 < 0 )
                goto LABEL_19;
            }
            v18 = 0;
            if ( v17 && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 48LL))(v17, &v18) >= 0 )
            {
              v8 = (_WORD *)v6(v18, 0);
              v10 = -1;
              do
                ++v10;
              while ( v8[v10] );
              if ( v10 > *(_QWORD *)(a2 + 24) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  (char **)a2,
                  v10,
                  v9,
                  v8);
              }
              else
              {
                if ( *(_QWORD *)(a2 + 24) <= 7u )
                  v11 = (char *)a2;
                else
                  v11 = *(char **)a2;
                *(_QWORD *)(a2 + 16) = v10;
                v12 = 2 * v10;
                memmove_0(v11, v8, 2 * v10);
                *(_WORD *)&v11[v12] = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_19:
  v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v20) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v15, v16);
      JUMPOUT(0x180056A07LL);
    }
    hModule = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return a2;
}

```

## disassembly

```asm
0x1800567a0  push    rbp
0x1800567a2  push    rbx
0x1800567a3  push    rsi
0x1800567a4  push    rdi
0x1800567a5  push    r14
0x1800567a7  push    r15
0x1800567a9  lea     rbp, [rsp-2Fh]
0x1800567ae  sub     rsp, 98h
0x1800567b5  mov     rax, cs:__security_cookie
0x1800567bc  xor     rax, rsp
0x1800567bf  mov     [rbp+57h+var_40], rax
0x1800567c3  mov     rdi, rdx
0x1800567c6  mov     [rbp+57h+var_60], rdx
0x1800567ca  xor     r14d, r14d
0x1800567cd  mov     [rbp+57h+var_80], r14d
0x1800567d1  xorps   xmm0, xmm0
0x1800567d4  movups  xmmword ptr [rdx], xmm0
0x1800567d7  mov     [rdx+10h], r14
0x1800567db  mov     [rdx+18h], r14
0x1800567df  lea     ebx, [r14+1]
0x1800567e3  mov     r8d, ebx
0x1800567e6  lea     rdx, asc_1801B4764; "#"
0x1800567ed  mov     rcx, rdi
0x1800567f0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800567f5  mov     [rbp+57h+var_80], ebx
0x1800567f8  mov     [rbp+57h+var_90], r14
0x1800567fc  mov     [rbp+57h+var_68], r14
0x180056800  mov     [rbp+57h+var_58], r14
0x180056804  xorps   xmm0, xmm0
0x180056807  movups  [rbp+57h+var_50], xmm0
0x18005680b  xor     edx, edx; hFile
0x18005680d  mov     r8d, 800h; dwFlags
0x180056813  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18005681a  call    cs:__imp_LoadLibraryExW
0x180056820  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180056827  mov     [rbp+57h+var_78], r15
0x18005682b  mov     [rbp+57h+hModule], rax
0x18005682f  test    rax, rax
0x180056832  jz      loc_18005699E
0x180056838  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x18005683f  mov     rcx, rax; hModule
0x180056842  call    cs:__imp_GetProcAddress
0x180056848  mov     rbx, rax
0x18005684b  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x180056852  mov     rcx, [rbp+57h+hModule]; hModule
0x180056856  call    cs:__imp_GetProcAddress
0x18005685c  mov     rsi, rax
0x18005685f  test    rbx, rbx
0x180056862  jz      loc_18005699E
0x180056868  test    rax, rax
0x18005686b  jz      loc_18005699E
0x180056871  lea     r9, [rbp+57h+var_68]
0x180056875  lea     r8, [rbp+57h+var_58]
0x180056879  lea     edx, [r14+34h]
0x18005687d  lea     rcx, ?RuntimeClass_Windows_Internal_AssignedAccess_AssignedAccessStatus@@3QBGB; "Windows.Internal.AssignedAccess.Assigne"...
0x180056884  mov     rax, rbx
0x180056887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005688c  test    eax, eax
0x18005688e  js      loc_18005699E
0x180056894  mov     rcx, [rbp+57h+var_90]
0x180056898  mov     [rbp+57h+var_90], r14
0x18005689c  test    rcx, rcx
0x18005689f  jz      short loc_1800568AE
0x1800568a1  mov     rax, [rcx]
0x1800568a4  mov     rax, [rax+10h]
0x1800568a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568ad  nop
0x1800568ae  mov     [rbp+57h+var_90], r14
0x1800568b2  mov     [rbp+57h+var_88], r14
0x1800568b6  lea     rdx, [rbp+57h+var_88]
0x1800568ba  mov     rcx, [rbp+57h+var_68]
0x1800568be  call    cs:__imp_RoActivateInstance
0x1800568c4  test    eax, eax
0x1800568c6  js      loc_18005699E
0x1800568cc  mov     r8d, 10h; Size
0x1800568d2  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800568d9  lea     rcx, _GUID_a3b975f3_840a_49ce_abf3_b1f2c4457208; Buf1
0x1800568e0  call    memcmp_0
0x1800568e5  test    eax, eax
0x1800568e7  jnz     short loc_1800568F3
0x1800568e9  mov     rax, [rbp+57h+var_88]
0x1800568ed  mov     [rbp+57h+var_90], rax
0x1800568f1  jmp     short loc_180056923
0x1800568f3  mov     rcx, [rbp+57h+var_88]
0x1800568f7  mov     rax, [rcx]
0x1800568fa  lea     r8, [rbp+57h+var_90]
0x1800568fe  lea     rdx, _GUID_a3b975f3_840a_49ce_abf3_b1f2c4457208
0x180056905  mov     rax, [rax]
0x180056908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005690d  mov     ebx, eax
0x18005690f  mov     rcx, [rbp+57h+var_88]
0x180056913  mov     rax, [rcx]
0x180056916  mov     rax, [rax+10h]
0x18005691a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005691f  test    ebx, ebx
0x180056921  js      short loc_18005699E
0x180056923  mov     [rbp+57h+var_88], r14
0x180056927  mov     rcx, [rbp+57h+var_90]
0x18005692b  test    rcx, rcx
0x18005692e  jz      short loc_18005699E
0x180056930  mov     rax, [rcx]
0x180056933  lea     rdx, [rbp+57h+var_88]
0x180056937  mov     rax, [rax+30h]
0x18005693b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056940  test    eax, eax
0x180056942  js      short loc_18005699E
0x180056944  xor     edx, edx
0x180056946  mov     rcx, [rbp+57h+var_88]
0x18005694a  mov     rax, rsi
0x18005694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056952  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056956  inc     rdx
0x180056959  cmp     [rax+rdx*2], r14w
0x18005695e  jnz     short loc_180056956
0x180056960  cmp     rdx, [rdi+18h]
0x180056964  ja      short loc_180056992
0x180056966  cmp     qword ptr [rdi+18h], 7
0x18005696b  jbe     short loc_180056972
0x18005696d  mov     rsi, [rdi]
0x180056970  jmp     short loc_180056975
0x180056972  mov     rsi, rdi
0x180056975  mov     [rdi+10h], rdx
0x180056979  lea     rbx, [rdx+rdx]
0x18005697d  mov     r8, rbx; Size
0x180056980  mov     rdx, rax; Src
0x180056983  mov     rcx, rsi; void *
0x180056986  call    memmove_0
0x18005698b  mov     [rbx+rsi], r14w
0x180056990  jmp     short loc_18005699E
0x180056992  mov     r9, rax
0x180056995  mov     rcx, rdi
0x180056998  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18005699d  nop
0x18005699e  mov     [rbp+57h+var_78], r15
0x1800569a2  cmp     [rbp+57h+hModule], r14
0x1800569a6  jz      short loc_1800569B9
0x1800569a8  lea     rcx, [rbp+57h+var_78]
0x1800569ac  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800569b1  test    al, al
0x1800569b3  jz      short loc_1800569EE
0x1800569b5  mov     [rbp+57h+hModule], r14
0x1800569b9  mov     rcx, [rbp+57h+var_90]
0x1800569bd  test    rcx, rcx
0x1800569c0  jz      short loc_1800569CF
0x1800569c2  mov     rdx, [rcx]
0x1800569c5  mov     rax, [rdx+10h]
0x1800569c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569ce  nop
0x1800569cf  mov     rax, rdi
0x1800569d2  mov     rcx, [rbp+57h+var_40]
0x1800569d6  xor     rcx, rsp; StackCookie
0x1800569d9  call    __security_check_cookie
0x1800569de  add     rsp, 98h
0x1800569e5  pop     r15
0x1800569e7  pop     r14
0x1800569e9  pop     rdi
0x1800569ea  pop     rsi
0x1800569eb  pop     rbx
0x1800569ec  pop     rbp
0x1800569ed  retn
0x1800569ee  call    cs:__imp_GetLastError
0x1800569f4  test    eax, eax
0x1800569f6  jle     short loc_180056A00
0x1800569f8  movzx   eax, ax
0x1800569fb  or      eax, 80070000h
0x180056a00  mov     ecx, eax; this
0x180056a02  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
