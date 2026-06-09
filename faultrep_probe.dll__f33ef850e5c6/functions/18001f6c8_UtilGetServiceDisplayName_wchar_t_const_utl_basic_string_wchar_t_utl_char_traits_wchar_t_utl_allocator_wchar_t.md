# UtilGetServiceDisplayName(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18001f6c8`
- end: `0x18001f91c`
- name: `?UtilGetServiceDisplayName@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18001f924`

## callees

- `0x180002890`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180019160`
- `0x18001f6c8`
- `0x180049280`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f76b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f76b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f74c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f8ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f74c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f8ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f78f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f78f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f80c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f781`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f781`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f8a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f8a9`

## string_xrefs

- `0x18001f726`: `advapi32.dll`
- `0x18001f761`: `GetServiceDisplayNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetServiceDisplayName(__int64 a1, __int64 a2)
{
  HMODULE v4; // rdi
  _WORD *v5; // rcx
  HMODULE *ModFromSystem; // rax
  unsigned int v7; // ebx
  FARPROC ProcAddress; // rsi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rbp
  signed int LastError; // eax
  signed int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r8
  int v18; // [rsp+30h] [rbp-2058h] BYREF
  HMODULE v19; // [rsp+38h] [rbp-2050h]
  HMODULE hLibModule[2]; // [rsp+40h] [rbp-2048h] BYREF
  _WORD v21[4096]; // [rsp+50h] [rbp-2038h] BYREF

  v4 = 0;
  v19 = 0;
  v18 = 0;
  if ( a1 && a2 )
  {
    v5 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
    *v5 = 0;
    ModFromSystem = (HMODULE *)UtilLoadModFromSystem(hLibModule, L"advapi32.dll");
    v4 = *ModFromSystem;
    *ModFromSystem = 0;
    v19 = v4;
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    if ( !v4 || (ProcAddress = GetProcAddress(v4, "GetServiceDisplayNameW")) == 0 )
    {
      v7 = -2147024846;
      goto LABEL_32;
    }
    v9 = OpenSCManagerW(0, 0, 1u);
    v10 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v7);
      goto LABEL_32;
    }
    v21[0] = 0;
    v18 = 4096;
    if ( ((unsigned int (__fastcall *)(SC_HANDLE, __int64, _WORD *, int *))ProcAddress)(v9, a1, v21, &v18) )
    {
      v16 = -1;
      do
        ++v16;
      while ( v21[v16] );
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              a2,
                              v21) )
      {
        v7 = 0;
        goto LABEL_28;
      }
      v7 = -2147024882;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v14 = 98;
      v15 = 2147942414LL;
    }
    else
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v14 = 97;
      v15 = v7;
    }
    WPP_SF_d(v13[2], v14, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v15);
LABEL_28:
    CloseServiceHandle(v10);
    goto LABEL_32;
  }
  v7 = -2147024809;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
LABEL_32:
  if ( v4 )
    FreeLibrary(v4);
  return v7;
}

```

## disassembly

```asm
0x18001f6c8  mov     [rsp+arg_10], rbx
0x18001f6cd  push    rbp
0x18001f6ce  push    rsi
0x18001f6cf  push    rdi
0x18001f6d0  push    r14
0x18001f6d2  push    r15
0x18001f6d4  mov     eax, 2060h
0x18001f6d9  call    _alloca_probe
0x18001f6de  sub     rsp, rax
0x18001f6e1  mov     rax, cs:__security_cookie
0x18001f6e8  xor     rax, rsp
0x18001f6eb  mov     [rsp+2088h+var_38], rax
0x18001f6f3  mov     rbx, rdx
0x18001f6f6  mov     r14, rcx
0x18001f6f9  xor     r15d, r15d
0x18001f6fc  mov     edi, r15d
0x18001f6ff  mov     [rsp+2088h+var_2050], r15
0x18001f704  mov     [rsp+2088h+var_2058], r15d
0x18001f709  test    rcx, rcx
0x18001f70c  jz      loc_18001F8B1
0x18001f712  test    rdx, rdx
0x18001f715  jz      loc_18001F8B1
0x18001f71b  mov     rcx, [rdx]
0x18001f71e  mov     [rdx+8], rcx
0x18001f722  mov     [rcx], r15w
0x18001f726  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x18001f72d  lea     rcx, [rsp+2088h+hLibModule]
0x18001f732  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x18001f737  mov     rdi, [rax]
0x18001f73a  mov     [rax], r15
0x18001f73d  mov     [rsp+2088h+var_2050], rdi
0x18001f742  mov     rcx, [rsp+2088h+hLibModule]; hLibModule
0x18001f747  test    rcx, rcx
0x18001f74a  jz      short loc_18001F752
0x18001f74c  call    cs:__imp_FreeLibrary
0x18001f752  test    rdi, rdi
0x18001f755  jnz     short loc_18001F761
0x18001f757  mov     ebx, 80070032h
0x18001f75c  jmp     loc_18001F8E5
0x18001f761  lea     rdx, aGetservicedisp; "GetServiceDisplayNameW"
0x18001f768  mov     rcx, rdi; hModule
0x18001f76b  call    cs:__imp_GetProcAddress
0x18001f771  mov     rsi, rax
0x18001f774  test    rax, rax
0x18001f777  jz      short loc_18001F757
0x18001f779  xor     edx, edx; lpDatabaseName
0x18001f77b  xor     ecx, ecx; lpMachineName
0x18001f77d  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001f781  call    cs:__imp_OpenSCManagerW
0x18001f787  mov     rbp, rax
0x18001f78a  test    rax, rax
0x18001f78d  jnz     short loc_18001F7E2
0x18001f78f  call    cs:__imp_GetLastError
0x18001f795  mov     ebx, eax
0x18001f797  test    eax, eax
0x18001f799  jle     short loc_18001F7A4
0x18001f79b  movzx   ebx, ax
0x18001f79e  or      ebx, 80070000h
0x18001f7a4  lea     rax, WPP_GLOBAL_Control
0x18001f7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7b2  cmp     rcx, rax
0x18001f7b5  jz      loc_18001F8E5
0x18001f7bb  test    byte ptr [rcx+1Ch], 1
0x18001f7bf  jz      loc_18001F8E5
0x18001f7c5  mov     edx, 60h ; '`'
0x18001f7ca  mov     r9d, ebx
0x18001f7cd  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001f7d4  mov     rcx, [rcx+10h]
0x18001f7d8  call    WPP_SF_d
0x18001f7dd  jmp     loc_18001F8E5
0x18001f7e2  mov     [rsp+2088h+var_2038], r15w
0x18001f7e8  mov     [rsp+2088h+var_2058], 1000h
0x18001f7f0  lea     r9, [rsp+2088h+var_2058]
0x18001f7f5  lea     r8, [rsp+2088h+var_2038]
0x18001f7fa  mov     rdx, r14
0x18001f7fd  mov     rcx, rbp
0x18001f800  mov     rax, rsi
0x18001f803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f808  test    eax, eax
0x18001f80a  jnz     short loc_18001F854
0x18001f80c  call    cs:__imp_GetLastError
0x18001f812  mov     ebx, eax
0x18001f814  test    eax, eax
0x18001f816  jle     short loc_18001F821
0x18001f818  movzx   ebx, ax
0x18001f81b  or      ebx, 80070000h
0x18001f821  lea     rax, WPP_GLOBAL_Control
0x18001f828  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f82f  cmp     rcx, rax
0x18001f832  jz      short loc_18001F8A6
0x18001f834  test    byte ptr [rcx+1Ch], 1
0x18001f838  jz      short loc_18001F8A6
0x18001f83a  mov     edx, 61h ; 'a'
0x18001f83f  mov     r9d, ebx
0x18001f842  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001f849  mov     rcx, [rcx+10h]
0x18001f84d  call    WPP_SF_d
0x18001f852  jmp     short loc_18001F8A6
0x18001f854  lea     rax, [rsp+2088h+var_2038]
0x18001f859  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f85d  inc     r8
0x18001f860  cmp     [rax+r8*2], r15w
0x18001f865  jnz     short loc_18001F85D
0x18001f867  lea     rdx, [rsp+2088h+var_2038]
0x18001f86c  mov     rcx, rbx
0x18001f86f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001f874  test    al, al
0x18001f876  jnz     short loc_18001F8A3
0x18001f878  mov     ebx, 8007000Eh
0x18001f87d  lea     rax, WPP_GLOBAL_Control
0x18001f884  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f88b  cmp     rcx, rax
0x18001f88e  jz      short loc_18001F8A6
0x18001f890  test    byte ptr [rcx+1Ch], 1
0x18001f894  jz      short loc_18001F8A6
0x18001f896  mov     edx, 62h ; 'b'
0x18001f89b  mov     r9d, 8007000Eh
0x18001f8a1  jmp     short loc_18001F842
0x18001f8a3  mov     ebx, r15d
0x18001f8a6  mov     rcx, rbp; hSCObject
0x18001f8a9  call    cs:__imp_CloseServiceHandle
0x18001f8af  jmp     short loc_18001F8E5
0x18001f8b1  mov     ebx, 80070057h
0x18001f8b6  lea     rax, WPP_GLOBAL_Control
0x18001f8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8c4  cmp     rcx, rax
0x18001f8c7  jz      short loc_18001F8E5
0x18001f8c9  test    byte ptr [rcx+1Ch], 1
0x18001f8cd  jz      short loc_18001F8E5
0x18001f8cf  mov     edx, 5Fh ; '_'
0x18001f8d4  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001f8db  mov     rcx, [rcx+10h]
0x18001f8df  call    WPP_SF_
0x18001f8e4  nop
0x18001f8e5  test    rdi, rdi
0x18001f8e8  jz      short loc_18001F8F3
0x18001f8ea  mov     rcx, rdi; hLibModule
0x18001f8ed  call    cs:__imp_FreeLibrary
0x18001f8f3  mov     eax, ebx
0x18001f8f5  mov     rcx, [rsp+2088h+var_38]
0x18001f8fd  xor     rcx, rsp; StackCookie
0x18001f900  call    __security_check_cookie
0x18001f905  mov     rbx, [rsp+2088h+arg_10]
0x18001f90d  add     rsp, 2060h
0x18001f914  pop     r15
0x18001f916  pop     r14
0x18001f918  pop     rdi
0x18001f919  pop     rsi
0x18001f91a  pop     rbp
0x18001f91b  retn
```
