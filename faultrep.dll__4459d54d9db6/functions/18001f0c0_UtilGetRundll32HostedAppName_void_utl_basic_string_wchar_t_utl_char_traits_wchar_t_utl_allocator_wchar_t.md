# UtilGetRundll32HostedAppName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18001f0c0`
- end: `0x18001f6c0`
- name: `?UtilGetRundll32HostedAppName@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1536`
- prototype: `__int64 __fastcall(HANDLE hProcess, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180018d98`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a9a4`
- `0x180016f80`
- `0x18001f0c0`
- `0x18003a6b4`
- `0x18003b2e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f2e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f2e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f565`
- `ntdll!wcschr` at `0x18001f27b`
- `ntdll!wcschr` at `0x18001f2d1`
- `ntdll!wcschr` at `0x18001f27b`
- `ntdll!wcschr` at `0x18001f2d1`
- `ntdll!wcsrchr` at `0x18001f2c0`
- `ntdll!wcsrchr` at `0x18001f4d5`
- `ntdll!wcsrchr` at `0x18001f2c0`
- `ntdll!wcsrchr` at `0x18001f4d5`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18001f3ea`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18001f3ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5eb`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18001f2f8`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18001f2f8`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18001f1b0`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18001f1b0`

## pseudocode

```c
__int64 __fastcall UtilGetRundll32HostedAppName(HANDLE hProcess, __int64 a2)
{
  LPWSTR *v4; // r15
  _WORD *v5; // rcx
  _WORD *v6; // r8
  unsigned int ProcessCommandLine; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int i; // edx
  const wchar_t *v13; // r14
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  HANDLE CurrentProcess; // rax
  int WindowsDirectory; // eax
  __int64 v18; // r9
  int v19; // ebx
  const WCHAR *v20; // r12
  DWORD v21; // eax
  __int64 v22; // rax
  __int64 v23; // rsi
  WCHAR *v24; // rdx
  wchar_t v25; // cx
  WCHAR *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  signed int LastError; // eax
  _WORD v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  int pNumArgs; // [rsp+34h] [rbp-CCh] BYREF
  void *v33[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v34[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v35[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v36[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpCmdLine[2]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v38[8]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpPath[3]; // [rsp+98h] [rbp-68h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  lpCmdLine[0] = v38;
  lpCmdLine[1] = v38;
  v38[0] = 0;
  v4 = 0;
  pNumArgs = 0;
  v31[0] = 0;
  v5 = v34;
  v33[0] = v34;
  v33[1] = v34;
  v34[0] = 0;
  v6 = v36;
  v35[0] = v36;
  v35[1] = v36;
  v36[0] = 0;
  if ( hProcess && a2 )
  {
    Buffer[0] = 0;
    ProcessCommandLine = UtilGetProcessCommandLine(hProcess, (__int64)lpCmdLine);
    if ( (ProcessCommandLine & 0x80000000) != 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v9 = 64;
      goto LABEL_77;
    }
    v4 = CommandLineToArgvW(lpCmdLine[0], &pNumArgs);
    lpPath[0] = (LPCWSTR)v4;
    if ( v4 )
    {
      if ( pNumArgs < 2 )
      {
        ProcessCommandLine = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_79;
        v11 = 66;
        goto LABEL_12;
      }
      for ( i = 1; i < pNumArgs; ++i )
      {
        if ( ((*v4[i] - 45) & 0xFFFD) != 0 )
          break;
      }
      if ( i == pNumArgs )
      {
        ProcessCommandLine = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_79;
        v11 = 67;
        goto LABEL_12;
      }
      v13 = v4[i];
      v14 = wcschr(v13, 0x2Cu);
      if ( !v14 )
      {
        ProcessCommandLine = -2147467259;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_79;
        v11 = 68;
LABEL_12:
        WPP_SF_(v10[2], v11, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
        goto LABEL_79;
      }
      *v14 = 0;
      v15 = wcsrchr(v13, 0x2Eu);
      if ( !wcschr(v13, 0x5Cu) )
      {
        CurrentProcess = GetCurrentProcess();
        if ( !(unsigned int)IsWow64Process2(CurrentProcess, v31, 0) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              69,
              WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              ProcessCommandLine);
          v31[0] = 0;
        }
        WindowsDirectory = UtilGetWindowsDirectory(v33);
        ProcessCommandLine = WindowsDirectory;
        if ( WindowsDirectory < 0 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_79;
          v9 = 70;
          goto LABEL_34;
        }
        WindowsDirectory = UtilGetSystemDirectory2(v35, v31[0]);
        ProcessCommandLine = WindowsDirectory;
        if ( WindowsDirectory >= 0 )
        {
          lpPath[0] = (LPCWSTR)v33[0];
          lpPath[1] = (LPCWSTR)v35[0];
          v19 = 0;
          v20 = L".dll";
          if ( v15 )
            v20 = 0;
          while ( 1 )
          {
            v21 = SearchPathW(lpPath[v19], v13, v20, 0x104u, Buffer, 0);
            if ( v21 > 0x104 )
              break;
            if ( v21 )
              goto LABEL_60;
            if ( (unsigned int)++v19 >= 2 )
            {
              ProcessCommandLine = -2147024894;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v11 = 73;
                goto LABEL_12;
              }
              goto LABEL_79;
            }
          }
          ProcessCommandLine = -2147024774;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 72;
            goto LABEL_12;
          }
          goto LABEL_79;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 71;
LABEL_34:
          v18 = (unsigned int)WindowsDirectory;
LABEL_78:
          WPP_SF_d(v8[2], v9, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v18);
          goto LABEL_79;
        }
        goto LABEL_79;
      }
      v22 = 2147483646;
      v23 = 260;
      v24 = Buffer;
      do
      {
        if ( !v22 )
          break;
        v25 = *v13;
        if ( !*v13 )
          break;
        ++v13;
        *v24++ = v25;
        --v22;
        --v23;
      }
      while ( v23 );
      ProcessCommandLine = v23 == 0 ? 0x8007007A : 0;
      v26 = v24 - 1;
      if ( v23 )
        v26 = v24;
      *v26 = 0;
      if ( v23 )
      {
LABEL_60:
        if ( !wcsrchr(Buffer, 0x2Eu) )
        {
          WindowsDirectory = StringCchCatW(Buffer, v27, (wchar_t *)L".dll");
          ProcessCommandLine = WindowsDirectory;
          if ( WindowsDirectory < 0 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_79;
            v9 = 75;
            goto LABEL_34;
          }
        }
        v28 = -1;
        do
          ++v28;
        while ( Buffer[v28] );
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a2,
                                 Buffer,
                                 v28) )
        {
          ProcessCommandLine = -2147024882;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_79;
          v9 = 76;
          v18 = 2147942414LL;
          goto LABEL_78;
        }
        ProcessCommandLine = 0;
LABEL_79:
        if ( v35[0] != v36 )
          operator delete(v35[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v33[0] != v34 )
          operator delete(v33[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v4 )
          LocalFree(v4);
        if ( lpCmdLine[0] != v38 )
          operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
        return ProcessCommandLine;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v9 = 74;
    }
    else
    {
      LastError = GetLastError();
      ProcessCommandLine = LastError;
      if ( LastError > 0 )
        ProcessCommandLine = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v9 = 65;
    }
LABEL_77:
    v18 = ProcessCommandLine;
    goto LABEL_78;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    v5 = v33[0];
    v6 = v35[0];
  }
  if ( v6 != v36 )
  {
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v33[0];
  }
  if ( v5 != v34 )
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpCmdLine[0] != v38 )
    operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001f0c0  mov     [rsp-8+arg_10], rbx
0x18001f0c5  push    rbp
0x18001f0c6  push    rsi
0x18001f0c7  push    rdi
0x18001f0c8  push    r12
0x18001f0ca  push    r13
0x18001f0cc  push    r14
0x18001f0ce  push    r15
0x18001f0d0  lea     rbp, [rsp-1D0h]
0x18001f0d8  sub     rsp, 2D0h
0x18001f0df  mov     rax, cs:__security_cookie
0x18001f0e6  xor     rax, rsp
0x18001f0e9  mov     [rbp+200h+var_40], rax
0x18001f0f0  mov     r13, rdx
0x18001f0f3  mov     r9, rcx
0x18001f0f6  lea     rax, [rbp+200h+var_278]
0x18001f0fa  mov     [rsp+300h+lpCmdLine], rax
0x18001f0ff  lea     rax, [rbp+200h+var_278]
0x18001f103  mov     [rbp+200h+var_280], rax
0x18001f107  xor     r12d, r12d
0x18001f10a  mov     [rbp+200h+var_278], r12w
0x18001f10f  mov     r15d, r12d
0x18001f112  mov     [rsp+300h+pNumArgs], r12d
0x18001f117  mov     [rsp+300h+var_2D0], r12w
0x18001f11d  lea     rcx, [rsp+300h+var_2B8]
0x18001f122  mov     [rsp+300h+var_2C8], rcx
0x18001f127  lea     rax, [rsp+300h+var_2B8]
0x18001f12c  mov     [rsp+300h+var_2C0], rax
0x18001f131  mov     [rsp+300h+var_2B8], r12w
0x18001f137  lea     r8, [rsp+300h+var_298]
0x18001f13c  mov     [rsp+300h+var_2A8], r8
0x18001f141  lea     rax, [rsp+300h+var_298]
0x18001f146  mov     [rsp+300h+var_2A0], rax
0x18001f14b  mov     [rsp+300h+var_298], r12w
0x18001f151  test    r9, r9
0x18001f154  jz      loc_18001F60F
0x18001f15a  test    rdx, rdx
0x18001f15d  jz      loc_18001F60F
0x18001f163  mov     [rbp+200h+Buffer], r12w
0x18001f168  lea     rdx, [rsp+300h+lpCmdLine]
0x18001f16d  mov     rcx, r9; hProcess
0x18001f170  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001f175  mov     ebx, eax
0x18001f177  test    eax, eax
0x18001f179  jns     short loc_18001F1A6
0x18001f17b  lea     rdi, WPP_GLOBAL_Control
0x18001f182  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f189  cmp     rcx, rdi
0x18001f18c  jz      loc_18001F5AC
0x18001f192  test    byte ptr [rcx+1Ch], 1
0x18001f196  jz      loc_18001F5AC
0x18001f19c  lea     edx, [r12+40h]
0x18001f1a1  jmp     loc_18001F598
0x18001f1a6  lea     rdx, [rsp+300h+pNumArgs]; pNumArgs
0x18001f1ab  mov     rcx, [rsp+300h+lpCmdLine]; lpCmdLine
0x18001f1b0  call    cs:__imp_CommandLineToArgvW
0x18001f1b6  mov     r15, rax
0x18001f1b9  mov     [rbp+200h+lpPath], rax
0x18001f1bd  test    rax, rax
0x18001f1c0  jz      loc_18001F565
0x18001f1c6  mov     r8d, [rsp+300h+pNumArgs]
0x18001f1cb  cmp     r8d, 2
0x18001f1cf  jge     short loc_18001F211
0x18001f1d1  mov     ebx, 80004005h
0x18001f1d6  lea     rdi, WPP_GLOBAL_Control
0x18001f1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1e4  cmp     rcx, rdi
0x18001f1e7  jz      loc_18001F5AC
0x18001f1ed  test    byte ptr [rcx+1Ch], 1
0x18001f1f1  jz      loc_18001F5AC
0x18001f1f7  mov     edx, 42h ; 'B'
0x18001f1fc  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001f203  mov     rcx, [rcx+10h]
0x18001f207  call    WPP_SF_
0x18001f20c  jmp     loc_18001F5AC
0x18001f211  mov     edx, 1
0x18001f216  cmp     edx, r8d
0x18001f219  jge     short loc_18001F23D
0x18001f21b  movsxd  rax, edx
0x18001f21e  mov     rcx, [r15+rax*8]
0x18001f222  movzx   eax, word ptr [rcx]
0x18001f225  sub     ax, 2Dh ; '-'
0x18001f229  mov     ecx, 0FFFDh
0x18001f22e  test    cx, ax
0x18001f231  jnz     short loc_18001F23A
0x18001f233  inc     edx
0x18001f235  cmp     edx, r8d
0x18001f238  jl      short loc_18001F21B
0x18001f23a  cmp     edx, r8d
0x18001f23d  jnz     short loc_18001F26C
0x18001f23f  mov     ebx, 80004005h
0x18001f244  lea     rdi, WPP_GLOBAL_Control
0x18001f24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f252  cmp     rcx, rdi
0x18001f255  jz      loc_18001F5AC
0x18001f25b  test    byte ptr [rcx+1Ch], 1
0x18001f25f  jz      loc_18001F5AC
0x18001f265  mov     edx, 43h ; 'C'
0x18001f26a  jmp     short loc_18001F1FC
0x18001f26c  movsxd  rax, edx
0x18001f26f  mov     r14, [r15+rax*8]
0x18001f273  mov     edx, 2Ch ; ','; Ch
0x18001f278  mov     rcx, r14; Str
0x18001f27b  call    cs:__imp_wcschr
0x18001f281  test    rax, rax
0x18001f284  jnz     short loc_18001F2B4
0x18001f286  mov     ebx, 80004005h
0x18001f28b  lea     rdi, WPP_GLOBAL_Control
0x18001f292  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f299  cmp     rcx, rdi
0x18001f29c  jz      loc_18001F5AC
0x18001f2a2  test    byte ptr [rcx+1Ch], 1
0x18001f2a6  jz      loc_18001F5AC
0x18001f2ac  lea     edx, [rax+44h]
0x18001f2af  jmp     loc_18001F1FC
0x18001f2b4  mov     [rax], r12w
0x18001f2b8  mov     edx, 2Eh ; '.'; Ch
0x18001f2bd  mov     rcx, r14; Str
0x18001f2c0  call    cs:__imp_wcsrchr
0x18001f2c6  mov     rsi, rax
0x18001f2c9  mov     edx, 5Ch ; '\'; Ch
0x18001f2ce  mov     rcx, r14; Str
0x18001f2d1  call    cs:__imp_wcschr
0x18001f2d7  lea     rdi, WPP_GLOBAL_Control
0x18001f2de  test    rax, rax
0x18001f2e1  jnz     loc_18001F453
0x18001f2e7  call    cs:__imp_GetCurrentProcess
0x18001f2ed  mov     rcx, rax
0x18001f2f0  xor     r8d, r8d
0x18001f2f3  lea     rdx, [rsp+300h+var_2D0]
0x18001f2f8  call    cs:__imp_IsWow64Process2
0x18001f2fe  test    eax, eax
0x18001f300  jnz     short loc_18001F330
0x18001f302  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f309  cmp     rcx, rdi
0x18001f30c  jz      short loc_18001F32A
0x18001f30e  test    byte ptr [rcx+1Ch], 1
0x18001f312  jz      short loc_18001F32A
0x18001f314  lea     edx, [rax+45h]
0x18001f317  mov     r9d, ebx
0x18001f31a  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001f321  mov     rcx, [rcx+10h]
0x18001f325  call    WPP_SF_d
0x18001f32a  mov     [rsp+300h+var_2D0], r12w
0x18001f330  lea     rcx, [rsp+300h+var_2C8]
0x18001f335  call    ?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001f33a  mov     ebx, eax
0x18001f33c  test    eax, eax
0x18001f33e  jns     short loc_18001F367
0x18001f340  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f347  cmp     rcx, rdi
0x18001f34a  jz      loc_18001F5AC
0x18001f350  test    byte ptr [rcx+1Ch], 1
0x18001f354  jz      loc_18001F5AC
0x18001f35a  mov     edx, 46h ; 'F'
0x18001f35f  mov     r9d, eax
0x18001f362  jmp     loc_18001F59B
0x18001f367  movzx   edx, [rsp+300h+var_2D0]
0x18001f36c  lea     rcx, [rsp+300h+var_2A8]
0x18001f371  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x18001f376  mov     ebx, eax
0x18001f378  test    eax, eax
0x18001f37a  jns     short loc_18001F39D
0x18001f37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f383  cmp     rcx, rdi
0x18001f386  jz      loc_18001F5AC
0x18001f38c  test    byte ptr [rcx+1Ch], 1
0x18001f390  jz      loc_18001F5AC
0x18001f396  mov     edx, 47h ; 'G'
0x18001f39b  jmp     short loc_18001F35F
0x18001f39d  mov     rax, [rsp+300h+var_2C8]
0x18001f3a2  mov     [rbp+200h+lpPath], rax
0x18001f3a6  mov     rax, [rsp+300h+var_2A8]
0x18001f3ab  mov     [rbp+200h+var_260], rax
0x18001f3af  mov     ebx, r12d
0x18001f3b2  lea     r12, aDll; ".dll"
0x18001f3b9  xor     eax, eax
0x18001f3bb  test    rsi, rsi
0x18001f3be  cmovnz  r12, rax
0x18001f3c2  mov     esi, 104h
0x18001f3c7  movsxd  rcx, ebx
0x18001f3ca  mov     [rsp+300h+lpFilePart], 0; lpFilePart
0x18001f3d3  lea     rax, [rbp+200h+Buffer]
0x18001f3d7  mov     [rsp+300h+lpBuffer], rax; lpBuffer
0x18001f3dc  mov     r9d, esi; nBufferLength
0x18001f3df  mov     r8, r12; lpExtension
0x18001f3e2  mov     rdx, r14; lpFileName
0x18001f3e5  mov     rcx, [rbp+rcx*8+200h+lpPath]; lpPath
0x18001f3ea  call    cs:__imp_SearchPathW
0x18001f3f0  cmp     eax, esi
0x18001f3f2  ja      short loc_18001F42A
0x18001f3f4  test    eax, eax
0x18001f3f6  jnz     loc_18001F4C9
0x18001f3fc  inc     ebx
0x18001f3fe  cmp     ebx, 2
0x18001f401  jb      short loc_18001F3C7
0x18001f403  mov     ebx, 80070002h
0x18001f408  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f40f  cmp     rcx, rdi
0x18001f412  jz      loc_18001F5AC
0x18001f418  test    byte ptr [rcx+1Ch], 1
0x18001f41c  jz      loc_18001F5AC
0x18001f422  lea     edx, [rax+49h]
0x18001f425  jmp     loc_18001F1FC
0x18001f42a  mov     ebx, 8007007Ah
0x18001f42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f436  cmp     rcx, rdi
0x18001f439  jz      loc_18001F5AC
0x18001f43f  test    byte ptr [rcx+1Ch], 1
0x18001f443  jz      loc_18001F5AC
0x18001f449  mov     edx, 48h ; 'H'
0x18001f44e  jmp     loc_18001F1FC
0x18001f453  mov     eax, 7FFFFFFEh
0x18001f458  mov     esi, 104h
0x18001f45d  lea     rdx, [rbp+200h+Buffer]
0x18001f461  test    rax, rax
0x18001f464  jz      short loc_18001F483
0x18001f466  movzx   ecx, word ptr [r14]
0x18001f46a  test    cx, cx
0x18001f46d  jz      short loc_18001F483
0x18001f46f  add     r14, 2
0x18001f473  mov     [rdx], cx
0x18001f476  add     rdx, 2
0x18001f47a  dec     rax
0x18001f47d  sub     rsi, 1
0x18001f481  jnz     short loc_18001F461
0x18001f483  mov     rax, rsi
0x18001f486  neg     rax
0x18001f489  sbb     ecx, ecx
0x18001f48b  not     ecx
0x18001f48d  mov     ebx, 8007007Ah
0x18001f492  and     ebx, ecx
0x18001f494  lea     rcx, [rdx-2]
0x18001f498  test    rsi, rsi
0x18001f49b  cmovnz  rcx, rdx
0x18001f49f  mov     [rcx], r12w
0x18001f4a3  jnz     short loc_18001F4CC
0x18001f4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4ac  cmp     rcx, rdi
0x18001f4af  jz      loc_18001F5AC
0x18001f4b5  test    byte ptr [rcx+1Ch], 1
0x18001f4b9  jz      loc_18001F5AC
0x18001f4bf  mov     edx, 4Ah ; 'J'
0x18001f4c4  jmp     loc_18001F598
0x18001f4c9  xor     r12d, r12d
0x18001f4cc  mov     edx, 2Eh ; '.'; Ch
0x18001f4d1  lea     rcx, [rbp+200h+Buffer]; Str
0x18001f4d5  call    cs:__imp_wcsrchr
0x18001f4db  test    rax, rax
0x18001f4de  jnz     short loc_18001F51A
0x18001f4e0  lea     r8, aDll; ".dll"
0x18001f4e7  lea     rcx, [rbp+200h+Buffer]; wchar_t *
0x18001f4eb  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001f4f0  mov     ebx, eax
0x18001f4f2  test    eax, eax
0x18001f4f4  jns     short loc_18001F51A
0x18001f4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4fd  cmp     rcx, rdi
0x18001f500  jz      loc_18001F5AC
0x18001f506  test    byte ptr [rcx+1Ch], 1
0x18001f50a  jz      loc_18001F5AC
0x18001f510  mov     edx, 4Bh ; 'K'
0x18001f515  jmp     loc_18001F35F
0x18001f51a  lea     rax, [rbp+200h+Buffer]
0x18001f51e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f522  inc     r8
0x18001f525  cmp     [rax+r8*2], r12w
0x18001f52a  jnz     short loc_18001F522
0x18001f52c  lea     rdx, [rbp+200h+Buffer]
0x18001f530  mov     rcx, r13
0x18001f533  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001f538  test    al, al
0x18001f53a  jnz     short loc_18001F560
0x18001f53c  mov     ebx, 8007000Eh
0x18001f541  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f548  cmp     rcx, rdi
0x18001f54b  jz      short loc_18001F5AC
0x18001f54d  test    byte ptr [rcx+1Ch], 1
0x18001f551  jz      short loc_18001F5AC
0x18001f553  mov     edx, 4Ch ; 'L'
0x18001f558  mov     r9d, 8007000Eh
0x18001f55e  jmp     short loc_18001F59B
0x18001f560  mov     ebx, r12d
0x18001f563  jmp     short loc_18001F5AC
0x18001f565  call    cs:__imp_GetLastError
0x18001f56b  mov     ebx, eax
0x18001f56d  test    eax, eax
0x18001f56f  jle     short loc_18001F57A
0x18001f571  movzx   ebx, ax
0x18001f574  or      ebx, 80070000h
0x18001f57a  lea     rdi, WPP_GLOBAL_Control
0x18001f581  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f588  cmp     rcx, rdi
0x18001f58b  jz      short loc_18001F5AC
0x18001f58d  test    byte ptr [rcx+1Ch], 1
0x18001f591  jz      short loc_18001F5AC
0x18001f593  mov     edx, 41h ; 'A'
0x18001f598  mov     r9d, ebx
0x18001f59b  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001f5a2  mov     rcx, [rcx+10h]
  ... truncated ...
```
