# WLANApiDynamicDllProxy::Initialize(wchar_t const *)

- ea: `0x1800ff340`
- end: `0x1800ff570`
- name: `?Initialize@WLANApiDynamicDllProxy@@UEAAXPEB_W@Z`
- size: `560`
- prototype: `void(WLANApiDynamicDllProxy *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180014fb0`
- `0x180018968`
- `0x180052d80`
- `0x180055c20`
- `0x18008c000`
- `0x1800ff340`
- `0x1800ff6f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff432`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff447`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff45c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff471`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff486`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff432`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff447`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff45c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff471`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ff486`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ff362`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ff362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff51c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800ff391`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800ff391`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ff415`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ff415`

## string_xrefs

- `0x1800ff428`: `WlanOpenHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WLANApiDynamicDllProxy::Initialize(WLANApiDynamicDllProxy *this, const wchar_t *a2)
{
  char *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  UINT SystemDirectoryW; // ebp
  __int64 v8; // r8
  __int64 v9; // r9
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // r9
  char LastError; // al
  char *v16; // [rsp+40h] [rbp-28h] BYREF

  v4 = (char *)this + 584;
  AcquireSRWLockExclusive((PSRWLOCK)this + 73);
  v16 = v4;
  if ( a2 && *a2 )
  {
    SystemDirectoryW = GetSystemDirectoryW((LPWSTR)this + 28, 0x105u);
    if ( SystemDirectoryW >= 0x105 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v8, v9);
    if ( SystemDirectoryW - 1 <= 0x103
      && StringCchCatW((wchar_t *)this + 28, 0x105u, L"\\") >= 0
      && StringCchCatW((wchar_t *)this + 28, 0x105u, a2) >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_28acc163d5ad327ac4b0702f09d11475_Traceguids,
          (char *)this + 56);
      LibraryW = LoadLibraryW((LPCWSTR)this + 28);
      *((_QWORD *)this + 1) = LibraryW;
      if ( LibraryW )
      {
        *((_QWORD *)this + 2) = GetProcAddress(LibraryW, "WlanOpenHandle");
        *((_QWORD *)this + 3) = GetProcAddress(*((HMODULE *)this + 1), "WlanCloseHandle");
        *((_QWORD *)this + 4) = GetProcAddress(*((HMODULE *)this + 1), "WlanEnumInterfaces");
        *((_QWORD *)this + 5) = GetProcAddress(*((HMODULE *)this + 1), "WlanQueryInterface");
        ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "WlanFreeMemory");
        *((_QWORD *)this + 6) = ProcAddress;
        v14 = *((_QWORD *)this + 2);
        if ( !v14 || !*((_QWORD *)this + 3) || !*((_QWORD *)this + 4) || !*((_QWORD *)this + 5) || !ProcAddress )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_qqqqq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              v13,
              v14,
              *((_QWORD *)this + 3),
              *((_QWORD *)this + 4),
              *((_QWORD *)this + 5),
              (__int64)ProcAddress);
          *((_QWORD *)this + 2) = 0;
          *((_QWORD *)this + 3) = 0;
          *((_QWORD *)this + 4) = 0;
          *((_QWORD *)this + 5) = 0;
          *((_QWORD *)this + 6) = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_28acc163d5ad327ac4b0702f09d11475_Traceguids,
            (_DWORD)this + 56,
            LastError);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
}

```

## disassembly

```asm
0x1800ff340  mov     [rsp+arg_10], rbx
0x1800ff345  mov     [rsp+arg_18], rbp
0x1800ff34a  push    rsi
0x1800ff34b  push    rdi
0x1800ff34c  push    r15
0x1800ff34e  sub     rsp, 50h
0x1800ff352  mov     rsi, rdx
0x1800ff355  mov     rdi, rcx
0x1800ff358  lea     rbx, [rcx+248h]
0x1800ff35f  mov     rcx, rbx; SRWLock
0x1800ff362  call    cs:__imp_AcquireSRWLockExclusive
0x1800ff368  mov     [rsp+68h+var_28], rbx
0x1800ff36d  test    rsi, rsi
0x1800ff370  jz      loc_1800FF551
0x1800ff376  xor     eax, eax
0x1800ff378  cmp     ax, [rsi]
0x1800ff37b  jz      loc_1800FF551
0x1800ff381  lea     rbx, [rdi+38h]
0x1800ff385  mov     r15d, 105h
0x1800ff38b  mov     edx, r15d; uSize
0x1800ff38e  mov     rcx, rbx; lpBuffer
0x1800ff391  call    cs:__imp_GetSystemDirectoryW
0x1800ff397  mov     ebp, eax
0x1800ff399  cmp     eax, r15d
0x1800ff39c  jb      short loc_1800FF3A3
0x1800ff39e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ff3a3  lea     eax, [rbp-1]
0x1800ff3a6  cmp     eax, 103h
0x1800ff3ab  ja      loc_1800FF551
0x1800ff3b1  lea     r8, asc_18015E03C; "\\"
0x1800ff3b8  mov     rdx, r15; unsigned __int64
0x1800ff3bb  mov     rcx, rbx; wchar_t *
0x1800ff3be  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800ff3c3  test    eax, eax
0x1800ff3c5  js      loc_1800FF551
0x1800ff3cb  mov     r8, rsi; wchar_t *
0x1800ff3ce  mov     rdx, r15; unsigned __int64
0x1800ff3d1  mov     rcx, rbx; wchar_t *
0x1800ff3d4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800ff3d9  test    eax, eax
0x1800ff3db  js      loc_1800FF551
0x1800ff3e1  lea     rsi, WPP_GLOBAL_Control
0x1800ff3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff3ef  cmp     rcx, rsi
0x1800ff3f2  jz      short loc_1800FF412
0x1800ff3f4  test    byte ptr [rcx+1Ch], 4
0x1800ff3f8  jz      short loc_1800FF412
0x1800ff3fa  mov     edx, 0Ah
0x1800ff3ff  mov     r9, rbx
0x1800ff402  lea     r8, WPP_28acc163d5ad327ac4b0702f09d11475_Traceguids
0x1800ff409  mov     rcx, [rcx+10h]
0x1800ff40d  call    WPP_SF_S
0x1800ff412  mov     rcx, rbx; lpLibFileName
0x1800ff415  call    cs:__imp_LoadLibraryW
0x1800ff41b  mov     [rdi+8], rax
0x1800ff41f  test    rax, rax
0x1800ff422  jz      loc_1800FF51C
0x1800ff428  lea     rdx, aWlanopenhandle_0; "WlanOpenHandle"
0x1800ff42f  mov     rcx, rax; hModule
0x1800ff432  call    cs:__imp_GetProcAddress
0x1800ff438  mov     [rdi+10h], rax
0x1800ff43c  lea     rdx, aWlanclosehandl_0; "WlanCloseHandle"
0x1800ff443  mov     rcx, [rdi+8]; hModule
0x1800ff447  call    cs:__imp_GetProcAddress
0x1800ff44d  mov     [rdi+18h], rax
0x1800ff451  lea     rdx, aWlanenuminterf_0; "WlanEnumInterfaces"
0x1800ff458  mov     rcx, [rdi+8]; hModule
0x1800ff45c  call    cs:__imp_GetProcAddress
0x1800ff462  mov     [rdi+20h], rax
0x1800ff466  lea     rdx, aWlanqueryinter_0; "WlanQueryInterface"
0x1800ff46d  mov     rcx, [rdi+8]; hModule
0x1800ff471  call    cs:__imp_GetProcAddress
0x1800ff477  mov     [rdi+28h], rax
0x1800ff47b  lea     rdx, aWlanfreememory_0; "WlanFreeMemory"
0x1800ff482  mov     rcx, [rdi+8]; hModule
0x1800ff486  call    cs:__imp_GetProcAddress
0x1800ff48c  mov     [rdi+30h], rax
0x1800ff490  mov     r9, [rdi+10h]
0x1800ff494  test    r9, r9
0x1800ff497  jz      short loc_1800FF4B7
0x1800ff499  cmp     qword ptr [rdi+18h], 0
0x1800ff49e  jz      short loc_1800FF4B7
0x1800ff4a0  cmp     qword ptr [rdi+20h], 0
0x1800ff4a5  jz      short loc_1800FF4B7
0x1800ff4a7  cmp     qword ptr [rdi+28h], 0
0x1800ff4ac  jz      short loc_1800FF4B7
0x1800ff4ae  test    rax, rax
0x1800ff4b1  jnz     loc_1800FF551
0x1800ff4b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff4be  cmp     rcx, rsi
0x1800ff4c1  jz      short loc_1800FF4F2
0x1800ff4c3  test    byte ptr [rcx+1Ch], 1
0x1800ff4c7  jz      short loc_1800FF4F2
0x1800ff4c9  mov     [rsp+68h+var_30], rax
0x1800ff4ce  mov     rax, [rdi+28h]
0x1800ff4d2  mov     [rsp+68h+var_38], rax
0x1800ff4d7  mov     rax, [rdi+20h]
0x1800ff4db  mov     [rsp+68h+var_40], rax
0x1800ff4e0  mov     rax, [rdi+18h]
0x1800ff4e4  mov     [rsp+68h+var_48], rax
0x1800ff4e9  mov     rcx, [rcx+10h]
0x1800ff4ed  call    WPP_SF_qqqqq
0x1800ff4f2  mov     qword ptr [rdi+10h], 0
0x1800ff4fa  mov     qword ptr [rdi+18h], 0
0x1800ff502  mov     qword ptr [rdi+20h], 0
0x1800ff50a  mov     qword ptr [rdi+28h], 0
0x1800ff512  mov     qword ptr [rdi+30h], 0
0x1800ff51a  jmp     short loc_1800FF551
0x1800ff51c  call    cs:__imp_GetLastError
0x1800ff522  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff529  cmp     rcx, rsi
0x1800ff52c  jz      short loc_1800FF551
0x1800ff52e  test    byte ptr [rcx+1Ch], 1
0x1800ff532  jz      short loc_1800FF551
0x1800ff534  mov     edx, 0Ch
0x1800ff539  mov     dword ptr [rsp+68h+var_48], eax
0x1800ff53d  mov     r9, rbx
0x1800ff540  lea     r8, WPP_28acc163d5ad327ac4b0702f09d11475_Traceguids
0x1800ff547  mov     rcx, [rcx+10h]
0x1800ff54b  call    WPP_SF_Sd
0x1800ff550  nop
0x1800ff551  lea     rcx, [rsp+68h+var_28]
0x1800ff556  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ff55b  lea     r11, [rsp+68h+var_18]
0x1800ff560  mov     rbx, [r11+30h]
0x1800ff564  mov     rbp, [r11+38h]
0x1800ff568  mov     rsp, r11
0x1800ff56b  pop     r15
0x1800ff56d  pop     rdi
0x1800ff56e  pop     rsi
0x1800ff56f  retn
```
