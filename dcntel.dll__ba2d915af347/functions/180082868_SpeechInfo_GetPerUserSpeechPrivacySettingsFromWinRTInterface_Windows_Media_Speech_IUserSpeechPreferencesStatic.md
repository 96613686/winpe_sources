# SpeechInfo::GetPerUserSpeechPrivacySettingsFromWinRTInterface(Windows::Media::Speech::IUserSpeechPreferencesStatics *,ushort const *,int &)

- ea: `0x180082868`
- end: `0x1800829f3`
- name: `?GetPerUserSpeechPrivacySettingsFromWinRTInterface@SpeechInfo@@CAXPEAUIUserSpeechPreferencesStatics@Speech@Media@Windows@@PEBGAEAH@Z`
- size: `395`
- prototype: `void __fastcall(struct Windows::Media::Speech::IUserSpeechPreferencesStatics *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180082e1c`

## callees

- `0x180008dc0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180082868`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800828c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800828c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800828e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800828e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800829d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800829d8`

## string_xrefs

- `0x1800828de`: `WindowsCreateStringReference`
- `0x1800828b9`: `api-ms-win-core-winrt-string-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SpeechInfo::GetPerUserSpeechPrivacySettingsFromWinRTInterface(
        struct Windows::Media::Speech::IUserSpeechPreferencesStatics *a1,
        const unsigned __int16 *a2,
        int *a3)
{
  __int64 v6; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v9; // rcx
  signed int LastError; // eax
  int v11; // edx
  unsigned int v12; // r8d
  _BYTE v13[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  int v15; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  const int *v17; // [rsp+50h] [rbp-30h] BYREF
  HMODULE v18; // [rsp+58h] [rbp-28h]
  __int64 v19; // [rsp+60h] [rbp-20h] BYREF
  __int128 v20; // [rsp+68h] [rbp-18h]

  v6 = -1;
  *a3 = -1;
  v14 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v17 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v18 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WindowsCreateStringReference");
    if ( ProcAddress )
    {
      do
        ++v6;
      while ( a2[v6] );
      if ( ((int (__fastcall *)(const unsigned __int16 *, _QWORD, __int64 *, __int64 *))ProcAddress)(
             a2,
             (unsigned int)v6,
             &v19,
             &v16) >= 0 )
      {
        if ( a1 )
        {
          if ( (*(int (__fastcall **)(struct Windows::Media::Speech::IUserSpeechPreferencesStatics *, __int64, __int64 *))(*(_QWORD *)a1 + 72LL))(
                 a1,
                 v16,
                 &v14) >= 0 )
          {
            v13[0] = 0;
            v15 = 0;
            if ( (*(int (__fastcall **)(__int64, _BYTE *, int *))(*(_QWORD *)v14 + 96LL))(v14, v13, &v15) >= 0 )
              *a3 = v13[0] != 0;
          }
        }
      }
    }
  }
  v17 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v18 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v17) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v11, v12);
      JUMPOUT(0x1800829F2LL);
    }
    v18 = 0;
  }
  v9 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
}

```

## disassembly

```asm
0x180082868  push    rbp
0x18008286a  push    rbx
0x18008286b  push    rsi
0x18008286c  push    rdi
0x18008286d  push    r12
0x18008286f  push    r14
0x180082871  push    r15
0x180082873  mov     rbp, rsp
0x180082876  sub     rsp, 80h
0x18008287d  mov     rax, cs:__security_cookie
0x180082884  xor     rax, rsp
0x180082887  mov     [rbp+var_8], rax
0x18008288b  mov     r14, r8
0x18008288e  mov     rsi, rdx
0x180082891  mov     rdi, rcx
0x180082894  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180082898  mov     [r8], ebx
0x18008289b  xor     r15d, r15d
0x18008289e  mov     [rbp+var_48], r15
0x1800828a2  mov     [rbp+var_38], r15
0x1800828a6  mov     [rbp+var_20], r15
0x1800828aa  xorps   xmm0, xmm0
0x1800828ad  movups  [rbp+var_18], xmm0
0x1800828b1  xor     edx, edx; hFile
0x1800828b3  mov     r8d, 800h; dwFlags
0x1800828b9  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800828c0  call    cs:__imp_LoadLibraryExW
0x1800828c6  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800828cd  mov     [rbp+var_30], r12
0x1800828d1  mov     [rbp+var_28], rax
0x1800828d5  test    rax, rax
0x1800828d8  jz      loc_180082985
0x1800828de  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800828e5  mov     rcx, rax; hModule
0x1800828e8  call    cs:__imp_GetProcAddress
0x1800828ee  test    rax, rax
0x1800828f1  jz      loc_180082985
0x1800828f7  inc     rbx
0x1800828fa  cmp     [rsi+rbx*2], r15w
0x1800828ff  jnz     short loc_1800828F7
0x180082901  lea     r9, [rbp+var_38]
0x180082905  lea     r8, [rbp+var_20]
0x180082909  mov     edx, ebx
0x18008290b  mov     rcx, rsi
0x18008290e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082913  test    eax, eax
0x180082915  js      short loc_180082985
0x180082917  test    rdi, rdi
0x18008291a  jz      short loc_180082985
0x18008291c  mov     rax, [rdi]
0x18008291f  mov     rbx, [rax+48h]
0x180082923  mov     rcx, [rbp+var_48]
0x180082927  test    rcx, rcx
0x18008292a  jz      short loc_18008293D
0x18008292c  mov     [rbp+var_48], r15
0x180082930  mov     rdx, [rcx]
0x180082933  mov     rax, [rdx+10h]
0x180082937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008293c  nop
0x18008293d  lea     r8, [rbp+var_48]
0x180082941  mov     rdx, [rbp+var_38]
0x180082945  mov     rcx, rdi
0x180082948  mov     rax, rbx
0x18008294b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082950  test    eax, eax
0x180082952  js      short loc_180082985
0x180082954  mov     [rbp+var_50], r15b
0x180082958  mov     [rbp+var_40], r15d
0x18008295c  mov     rcx, [rbp+var_48]
0x180082960  mov     rax, [rcx]
0x180082963  lea     r8, [rbp+var_40]
0x180082967  lea     rdx, [rbp+var_50]
0x18008296b  mov     rax, [rax+60h]
0x18008296f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082974  test    eax, eax
0x180082976  js      short loc_180082985
0x180082978  mov     eax, r15d
0x18008297b  cmp     [rbp+var_50], r15b
0x18008297f  setnz   al
0x180082982  mov     [r14], eax
0x180082985  mov     [rbp+var_30], r12
0x180082989  cmp     [rbp+var_28], r15
0x18008298d  jz      short loc_1800829A0
0x18008298f  lea     rcx, [rbp+var_30]
0x180082993  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180082998  test    al, al
0x18008299a  jz      short loc_1800829D8
0x18008299c  mov     [rbp+var_28], r15
0x1800829a0  mov     rcx, [rbp+var_48]
0x1800829a4  test    rcx, rcx
0x1800829a7  jz      short loc_1800829BA
0x1800829a9  mov     [rbp+var_48], r15
0x1800829ad  mov     rax, [rcx]
0x1800829b0  mov     rax, [rax+10h]
0x1800829b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800829b9  nop
0x1800829ba  mov     rcx, [rbp+var_8]
0x1800829be  xor     rcx, rsp; StackCookie
0x1800829c1  call    __security_check_cookie
0x1800829c6  add     rsp, 80h
0x1800829cd  pop     r15
0x1800829cf  pop     r14
0x1800829d1  pop     r12
0x1800829d3  pop     rdi
0x1800829d4  pop     rsi
0x1800829d5  pop     rbx
0x1800829d6  pop     rbp
0x1800829d7  retn
0x1800829d8  call    cs:__imp_GetLastError
0x1800829de  nop
0x1800829df  test    eax, eax
0x1800829e1  jle     short loc_1800829EB
0x1800829e3  movzx   eax, ax
0x1800829e6  or      eax, 80070000h
0x1800829eb  mov     ecx, eax; this
0x1800829ed  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
