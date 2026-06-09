# COsInfo::GetPortableOs(void)

- ea: `0x1800618d0`
- end: `0x180061b00`
- name: `?GetPortableOs@COsInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014f2c`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800618d0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800618f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800618f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006195e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006195e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ae6`

## string_xrefs

- `0x1800618ed`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COsInfo::GetPortableOs(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v5; // eax
  const wchar_t *v6; // rdx
  unsigned __int64 v7; // r8
  signed int v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  signed int v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  signed int v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  signed int v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  signed int LastError; // eax
  int v22; // edx
  unsigned int v23; // r8d
  const int *v24; // [rsp+28h] [rbp-20h] BYREF
  HMODULE v25; // [rsp+30h] [rbp-18h]
  char v26; // [rsp+80h] [rbp+38h] BYREF

  v26 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v25 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlCheckPortableOperatingSystem");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(char *))ProcAddress)(&v26);
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      if ( v5 < 0 )
      {
        if ( v5 == -1073741275 )
        {
          std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"0", 1u);
          v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
          if ( v25 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v22, v23);
            JUMPOUT(0x180061AFFLL);
          }
        }
        else
        {
          std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
          v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
          if ( v25 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24) )
          {
            v9 = GetLastError();
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
            __debugbreak();
          }
        }
      }
      else
      {
        v6 = L"1";
        if ( !v26 )
          v6 = L"0";
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
        std::wstring::_Construct<1,unsigned short const *>((char **)a2, v6, v7);
        v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( v25 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24) )
        {
          v18 = GetLastError();
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
          __debugbreak();
        }
      }
    }
    else
    {
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
      v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v25 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24) )
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
        __debugbreak();
      }
    }
  }
  else
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
    v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v25 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
      __debugbreak();
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800618d0  push    rbp
0x1800618d2  push    rbx
0x1800618d3  push    rsi
0x1800618d4  push    rdi
0x1800618d5  mov     rbp, rsp
0x1800618d8  sub     rsp, 48h
0x1800618dc  mov     rbx, rdx
0x1800618df  xor     edi, edi
0x1800618e1  mov     [rbp+arg_10], dil
0x1800618e5  xor     edx, edx; hFile
0x1800618e7  mov     r8d, 800h; dwFlags
0x1800618ed  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800618f4  call    cs:__imp_LoadLibraryExW
0x1800618fa  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180061901  mov     [rbp+var_20], rsi
0x180061905  mov     [rbp+var_18], rax
0x180061909  test    rax, rax
0x18006190c  jnz     short loc_180061954
0x18006190e  xorps   xmm0, xmm0
0x180061911  movups  xmmword ptr [rbx], xmm0
0x180061914  mov     [rbx+10h], rdi
0x180061918  mov     [rbx+18h], rdi
0x18006191c  lea     r8d, [rdi+1]
0x180061920  lea     rdx, asc_1801B4764; "#"
0x180061927  mov     rcx, rbx
0x18006192a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006192f  nop
0x180061930  mov     [rbp+var_20], rsi
0x180061934  cmp     [rbp+var_18], rdi
0x180061938  jz      loc_180061A72
0x18006193e  lea     rcx, [rbp+var_20]
0x180061942  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180061947  test    al, al
0x180061949  jz      loc_180061A98
0x18006194f  jmp     loc_180061A72
0x180061954  lea     rdx, aRtlcheckportab; "RtlCheckPortableOperatingSystem"
0x18006195b  mov     rcx, rax; hModule
0x18006195e  call    cs:__imp_GetProcAddress
0x180061964  test    rax, rax
0x180061967  jnz     short loc_1800619AF
0x180061969  xorps   xmm0, xmm0
0x18006196c  movups  xmmword ptr [rbx], xmm0
0x18006196f  mov     [rbx+10h], rdi
0x180061973  mov     [rbx+18h], rdi
0x180061977  lea     r8d, [rax+1]
0x18006197b  lea     rdx, asc_1801B4764; "#"
0x180061982  mov     rcx, rbx
0x180061985  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006198a  nop
0x18006198b  mov     [rbp+var_20], rsi
0x18006198f  cmp     [rbp+var_18], rdi
0x180061993  jz      loc_180061A72
0x180061999  lea     rcx, [rbp+var_20]
0x18006199d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800619a2  test    al, al
0x1800619a4  jz      loc_180061AB2
0x1800619aa  jmp     loc_180061A72
0x1800619af  lea     rcx, [rbp+arg_10]
0x1800619b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619b8  xorps   xmm0, xmm0
0x1800619bb  movups  xmmword ptr [rbx], xmm0
0x1800619be  mov     [rbx+10h], rdi
0x1800619c2  mov     [rbx+18h], rdi
0x1800619c6  test    eax, eax
0x1800619c8  js      short loc_180061A14
0x1800619ca  lea     rdx, a1_0; "1"
0x1800619d1  lea     rax, a0_0; "0"
0x1800619d8  cmp     [rbp+arg_10], dil
0x1800619dc  cmovz   rdx, rax
0x1800619e0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800619e4  inc     r8
0x1800619e7  cmp     [rdx+r8*2], di
0x1800619ec  jnz     short loc_1800619E4
0x1800619ee  mov     rcx, rbx
0x1800619f1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800619f6  nop
0x1800619f7  mov     [rbp+var_20], rsi
0x1800619fb  cmp     [rbp+var_18], rdi
0x1800619ff  jz      short loc_180061A72
0x180061a01  lea     rcx, [rbp+var_20]
0x180061a05  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180061a0a  test    al, al
0x180061a0c  jz      loc_180061ACC
0x180061a12  jmp     short loc_180061A72
0x180061a14  mov     r8d, 1
0x180061a1a  mov     rcx, rbx
0x180061a1d  cmp     eax, 0C0000225h
0x180061a22  jnz     short loc_180061A4E
0x180061a24  lea     rdx, a0_0; "0"
0x180061a2b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180061a30  nop
0x180061a31  mov     [rbp+var_20], rsi
0x180061a35  cmp     [rbp+var_18], rdi
0x180061a39  jz      short loc_180061A72
0x180061a3b  lea     rcx, [rbp+var_20]
0x180061a3f  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180061a44  test    al, al
0x180061a46  jz      loc_180061AE6
0x180061a4c  jmp     short loc_180061A72
0x180061a4e  lea     rdx, asc_1801B4764; "#"
0x180061a55  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180061a5a  nop
0x180061a5b  mov     [rbp+var_20], rsi
0x180061a5f  cmp     [rbp+var_18], rdi
0x180061a63  jz      short loc_180061A72
0x180061a65  lea     rcx, [rbp+var_20]
0x180061a69  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180061a6e  test    al, al
0x180061a70  jz      short loc_180061A7E
0x180061a72  mov     rax, rbx
0x180061a75  add     rsp, 48h
0x180061a79  pop     rdi
0x180061a7a  pop     rsi
0x180061a7b  pop     rbx
0x180061a7c  pop     rbp
0x180061a7d  retn
0x180061a7e  call    cs:__imp_GetLastError
0x180061a84  test    eax, eax
0x180061a86  jle     short loc_180061A90
0x180061a88  movzx   eax, ax
0x180061a8b  or      eax, 80070000h
0x180061a90  mov     ecx, eax; this
0x180061a92  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180061a97  int     3; Trap to Debugger
0x180061a98  call    cs:__imp_GetLastError
0x180061a9e  test    eax, eax
0x180061aa0  jle     short loc_180061AAA
0x180061aa2  movzx   eax, ax
0x180061aa5  or      eax, 80070000h
0x180061aaa  mov     ecx, eax; this
0x180061aac  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180061ab1  int     3; Trap to Debugger
0x180061ab2  call    cs:__imp_GetLastError
0x180061ab8  test    eax, eax
0x180061aba  jle     short loc_180061AC4
0x180061abc  movzx   eax, ax
0x180061abf  or      eax, 80070000h
0x180061ac4  mov     ecx, eax; this
0x180061ac6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180061acb  int     3; Trap to Debugger
0x180061acc  call    cs:__imp_GetLastError
0x180061ad2  test    eax, eax
0x180061ad4  jle     short loc_180061ADE
0x180061ad6  movzx   eax, ax
0x180061ad9  or      eax, 80070000h
0x180061ade  mov     ecx, eax; this
0x180061ae0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180061ae5  int     3; Trap to Debugger
0x180061ae6  call    cs:__imp_GetLastError
0x180061aec  test    eax, eax
0x180061aee  jle     short loc_180061AF8
0x180061af0  movzx   eax, ax
0x180061af3  or      eax, 80070000h
0x180061af8  mov     ecx, eax; this
0x180061afa  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
