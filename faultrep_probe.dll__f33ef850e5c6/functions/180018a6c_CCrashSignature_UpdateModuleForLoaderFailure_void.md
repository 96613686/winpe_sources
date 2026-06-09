# CCrashSignature::UpdateModuleForLoaderFailure(void)

- ea: `0x180018a6c`
- end: `0x180018d91`
- name: `?UpdateModuleForLoaderFailure@CCrashSignature@@AEAAJXZ`
- size: `805`
- prototype: `__int64 __fastcall(CCrashSignature *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x180017498`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x18000be60`
- `0x180016414`
- `0x180018a6c`
- `0x180019160`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018b09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018b09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018d65`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d0b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180018bad`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180018bad`

## string_xrefs

- `0x180018ab1`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCrashSignature::UpdateModuleForLoaderFailure(CCrashSignature *this)
{
  unsigned int v2; // ebx
  __int64 (*ProcAddress)(void); // rax
  signed int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const void *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  signed int LastError; // eax
  HMODULE hModule; // [rsp+30h] [rbp-69h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-61h] BYREF
  int Buffer; // [rsp+40h] [rbp-59h] BYREF
  _WORD v17[32]; // [rsp+44h] [rbp-55h] BYREF
  _WORD v18[38]; // [rsp+84h] [rbp-15h] BYREF

  memset_0(&Buffer, 0, 0x84u);
  NumberOfBytesRead = 0;
  UtilLoadModFromSystem(&hModule, L"ntdll.dll");
  if ( !hModule )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
    v2 = -2147023739;
    goto LABEL_51;
  }
  ProcAddress = GetProcAddress(hModule, "LdrGetFailureData");
  if ( ProcAddress )
  {
    v7 = (const void *)ProcAddress();
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
      v2 = -2147467259;
      goto LABEL_51;
    }
    if ( ReadProcessMemory(*((HANDLE *)this + 1), v7, &Buffer, 0x84u, &NumberOfBytesRead) && NumberOfBytesRead == 132 )
    {
      if ( Buffer != *((_DWORD *)this + 88) )
      {
        v2 = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
        goto LABEL_51;
      }
      v17[31] = 0;
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( v17[v9] );
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              (char *)this + 200,
                              v17) )
      {
        v11 = -1;
        do
          ++v11;
        while ( v17[v11] );
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                (char *)this + 232,
                                v17) )
        {
          if ( *((_DWORD *)this + 88) == -1073741511 && v18[0] )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
              (char *)this + 232,
              33);
            do
              ++v8;
            while ( v18[v8] );
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
              (char *)this + 232,
              v18);
          }
          v2 = 0;
          goto LABEL_51;
        }
        v2 = -2147024882;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_51;
        v6 = 33;
      }
      else
      {
        v2 = -2147024882;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_51;
        v6 = 32;
      }
      v10 = 2147942414LL;
LABEL_50:
      WPP_SF_d(v5[2], v6, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids, v10);
      goto LABEL_51;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v2 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 30;
      goto LABEL_49;
    }
  }
  else
  {
    v4 = GetLastError();
    v2 = v4;
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 28;
LABEL_49:
      v10 = v2;
      goto LABEL_50;
    }
  }
LABEL_51:
  if ( hModule )
    FreeLibrary(hModule);
  return v2;
}

```

## disassembly

```asm
0x180018a6c  mov     [rsp-8+arg_8], rbx
0x180018a71  mov     [rsp-8+arg_10], rsi
0x180018a76  push    rbp
0x180018a77  push    rdi
0x180018a78  push    r15
0x180018a7a  lea     rbp, [rsp-47h]
0x180018a7f  sub     rsp, 0E0h
0x180018a86  mov     rax, cs:__security_cookie
0x180018a8d  xor     rax, rsp
0x180018a90  mov     [rbp+57h+var_20], rax
0x180018a94  mov     rdi, rcx
0x180018a97  mov     ebx, 84h
0x180018a9c  mov     r8d, ebx; Size
0x180018a9f  xor     edx, edx; Val
0x180018aa1  lea     rcx, [rbp+57h+Buffer]; void *
0x180018aa5  call    memset_0
0x180018aaa  xor     r15d, r15d
0x180018aad  mov     [rbp+57h+NumberOfBytesRead], r15
0x180018ab1  lea     rdx, ModuleName; "ntdll.dll"
0x180018ab8  lea     rcx, [rbp+57h+hModule]
0x180018abc  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x180018ac1  nop
0x180018ac2  cmp     [rbp+57h+hModule], r15
0x180018ac6  jnz     short loc_180018AFE
0x180018ac8  lea     rax, WPP_GLOBAL_Control
0x180018acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ad6  cmp     rcx, rax
0x180018ad9  jz      short loc_180018AF4
0x180018adb  test    byte ptr [rcx+1Ch], 1
0x180018adf  jz      short loc_180018AF4
0x180018ae1  lea     edx, [rbx-69h]
0x180018ae4  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018aeb  mov     rcx, [rcx+10h]
0x180018aef  call    WPP_SF_
0x180018af4  mov     ebx, 80070485h
0x180018af9  jmp     loc_180018D5B
0x180018afe  lea     rdx, aLdrgetfailured; "LdrGetFailureData"
0x180018b05  mov     rcx, [rbp+57h+hModule]; hModule
0x180018b09  call    cs:__imp_GetProcAddress
0x180018b0f  test    rax, rax
0x180018b12  jnz     short loc_180018B54
0x180018b14  call    cs:__imp_GetLastError
0x180018b1a  mov     ebx, eax
0x180018b1c  test    eax, eax
0x180018b1e  jle     short loc_180018B29
0x180018b20  movzx   ebx, ax
0x180018b23  or      ebx, 80070000h
0x180018b29  lea     rax, WPP_GLOBAL_Control
0x180018b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b37  cmp     rcx, rax
0x180018b3a  jz      loc_180018D5B
0x180018b40  test    byte ptr [rcx+1Ch], 1
0x180018b44  jz      loc_180018D5B
0x180018b4a  mov     edx, 1Ch
0x180018b4f  jmp     loc_180018D47
0x180018b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b59  test    rax, rax
0x180018b5c  jnz     short loc_180018B96
0x180018b5e  lea     rax, WPP_GLOBAL_Control
0x180018b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b6c  cmp     rcx, rax
0x180018b6f  jz      short loc_180018B8C
0x180018b71  test    byte ptr [rcx+1Ch], 1
0x180018b75  jz      short loc_180018B8C
0x180018b77  mov     edx, 1Dh
0x180018b7c  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018b83  mov     rcx, [rcx+10h]
0x180018b87  call    WPP_SF_
0x180018b8c  mov     ebx, 80004005h
0x180018b91  jmp     loc_180018D5B
0x180018b96  lea     rcx, [rbp+57h+NumberOfBytesRead]
0x180018b9a  mov     [rsp+0F0h+lpNumberOfBytesRead], rcx; lpNumberOfBytesRead
0x180018b9f  mov     r9, rbx; nSize
0x180018ba2  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180018ba6  mov     rdx, rax; lpBaseAddress
0x180018ba9  mov     rcx, [rdi+8]; hProcess
0x180018bad  call    cs:__imp_ReadProcessMemory
0x180018bb3  test    eax, eax
0x180018bb5  jz      loc_180018D0B
0x180018bbb  cmp     [rbp+57h+NumberOfBytesRead], rbx
0x180018bbf  jnz     loc_180018D0B
0x180018bc5  mov     eax, [rdi+160h]
0x180018bcb  cmp     [rbp+57h+Buffer], eax
0x180018bce  jz      short loc_180018C10
0x180018bd0  mov     ebx, 80004005h
0x180018bd5  lea     rax, WPP_GLOBAL_Control
0x180018bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018be3  cmp     rcx, rax
0x180018be6  jz      loc_180018D5B
0x180018bec  test    byte ptr [rcx+1Ch], 1
0x180018bf0  jz      loc_180018D5B
0x180018bf6  mov     edx, 1Fh
0x180018bfb  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018c02  mov     rcx, [rcx+10h]
0x180018c06  call    WPP_SF_
0x180018c0b  jmp     loc_180018D5B
0x180018c10  mov     [rbp+57h+var_6E], r15w
0x180018c15  lea     rax, [rbp+57h+var_AC]
0x180018c19  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018c1d  mov     r8, rbx
0x180018c20  inc     r8
0x180018c23  cmp     [rax+r8*2], r15w
0x180018c28  jnz     short loc_180018C20
0x180018c2a  lea     rcx, [rdi+0C8h]
0x180018c31  lea     rdx, [rbp+57h+var_AC]
0x180018c35  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180018c3a  test    al, al
0x180018c3c  jnz     short loc_180018C74
0x180018c3e  mov     ebx, 8007000Eh
0x180018c43  lea     rax, WPP_GLOBAL_Control
0x180018c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c51  cmp     rcx, rax
0x180018c54  jz      loc_180018D5B
0x180018c5a  test    byte ptr [rcx+1Ch], 1
0x180018c5e  jz      loc_180018D5B
0x180018c64  mov     edx, 20h ; ' '
0x180018c69  mov     r9d, 8007000Eh
0x180018c6f  jmp     loc_180018D4A
0x180018c74  lea     rsi, [rdi+0E8h]
0x180018c7b  lea     rax, [rbp+57h+var_AC]
0x180018c7f  mov     r8, rbx
0x180018c82  inc     r8
0x180018c85  cmp     [rax+r8*2], r15w
0x180018c8a  jnz     short loc_180018C82
0x180018c8c  lea     rdx, [rbp+57h+var_AC]
0x180018c90  mov     rcx, rsi
0x180018c93  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180018c98  test    al, al
0x180018c9a  jnz     short loc_180018CC9
0x180018c9c  mov     ebx, 8007000Eh
0x180018ca1  lea     rax, WPP_GLOBAL_Control
0x180018ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180018caf  cmp     rcx, rax
0x180018cb2  jz      loc_180018D5B
0x180018cb8  test    byte ptr [rcx+1Ch], 1
0x180018cbc  jz      loc_180018D5B
0x180018cc2  mov     edx, 21h ; '!'
0x180018cc7  jmp     short loc_180018C69
0x180018cc9  cmp     dword ptr [rdi+160h], 0C0000139h
0x180018cd3  jnz     short loc_180018D06
0x180018cd5  cmp     [rbp+57h+var_6C], r15w
0x180018cda  jz      short loc_180018D06
0x180018cdc  mov     edx, 21h ; '!'
0x180018ce1  mov     rcx, rsi
0x180018ce4  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180018ce9  lea     rax, [rbp+57h+var_6C]
0x180018ced  inc     rbx
0x180018cf0  cmp     [rax+rbx*2], r15w
0x180018cf5  jnz     short loc_180018CED
0x180018cf7  mov     r8, rbx
0x180018cfa  lea     rdx, [rbp+57h+var_6C]
0x180018cfe  mov     rcx, rsi
0x180018d01  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180018d06  mov     ebx, r15d
0x180018d09  jmp     short loc_180018D5B
0x180018d0b  call    cs:__imp_GetLastError
0x180018d11  test    eax, eax
0x180018d13  jle     short loc_180018D1D
0x180018d15  movzx   eax, ax
0x180018d18  or      eax, 80070000h
0x180018d1d  mov     ebx, 80004005h
0x180018d22  test    eax, eax
0x180018d24  cmovns  eax, ebx
0x180018d27  mov     ebx, eax
0x180018d29  lea     rax, WPP_GLOBAL_Control
0x180018d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d37  cmp     rcx, rax
0x180018d3a  jz      short loc_180018D5B
0x180018d3c  test    byte ptr [rcx+1Ch], 1
0x180018d40  jz      short loc_180018D5B
0x180018d42  mov     edx, 1Eh
0x180018d47  mov     r9d, ebx
0x180018d4a  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180018d51  mov     rcx, [rcx+10h]
0x180018d55  call    WPP_SF_d
0x180018d5a  nop
0x180018d5b  cmp     [rbp+57h+hModule], r15
0x180018d5f  jz      short loc_180018D6B
0x180018d61  mov     rcx, [rbp+57h+hModule]; hLibModule
0x180018d65  call    cs:__imp_FreeLibrary
0x180018d6b  mov     eax, ebx
0x180018d6d  mov     rcx, [rbp+57h+var_20]
0x180018d71  xor     rcx, rsp; StackCookie
0x180018d74  call    __security_check_cookie
0x180018d79  lea     r11, [rsp+0F0h+var_10]
0x180018d81  mov     rbx, [r11+28h]
0x180018d85  mov     rsi, [r11+30h]
0x180018d89  mov     rsp, r11
0x180018d8c  pop     r15
0x180018d8e  pop     rdi
0x180018d8f  pop     rbp
0x180018d90  retn
```
