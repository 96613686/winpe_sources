# IkeLoadNlb

- ea: `0x180056304`
- end: `0x1800565b5`
- name: `IkeLoadNlb`
- size: `689`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180054bf4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180056304`
- `0x18005bc40`
- `0x180119010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180056560`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180056560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056375`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056397`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800563b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800563db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056375`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056397`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800563b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800563db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005634a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005634a`

## string_xrefs

- `0x18005633b`: `wlbsctrl.dll`

## pseudocode

```c
__int64 IkeLoadNlb()
{
  LPCRITICAL_SECTION v0; // rbx
  LPCRITICAL_SECTION v1; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  LPCRITICAL_SECTION v3; // rbx
  LPCRITICAL_SECTION v4; // rbx
  LPCRITICAL_SECTION v5; // rbx
  __int64 v6; // rcx
  LPCRITICAL_SECTION v7; // rax
  __int64 v8; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v10; // rcx
  int TlsMmLuid; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // r8d
  int v15; // r9d
  __int64 v17; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-68h] BYREF
  __int64 *v19; // [rsp+60h] [rbp-48h]
  __int64 v20; // [rsp+68h] [rbp-40h]
  _BYTE v21[16]; // [rsp+70h] [rbp-38h] BYREF
  const char *v22; // [rsp+80h] [rbp-28h]
  __int64 v23; // [rsp+88h] [rbp-20h]

  TraceLogHelper("IkeLoadNlb", 1);
  v0 = gIkeExtGlobals;
  v0[75].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)LoadLibraryExW(L"wlbsctrl.dll", 0, 0x800u);
  v1 = gIkeExtGlobals;
  DebugInfo = gIkeExtGlobals[75].DebugInfo;
  if ( DebugInfo )
  {
    *(_QWORD *)&v1[75].LockCount = GetProcAddress((HMODULE)DebugInfo, "WlbsConnectionUp");
    v3 = gIkeExtGlobals;
    v3[75].OwningThread = GetProcAddress((HMODULE)gIkeExtGlobals[75].DebugInfo, "WlbsConnectionDown");
    v4 = gIkeExtGlobals;
    v4[75].LockSemaphore = GetProcAddress((HMODULE)gIkeExtGlobals[75].DebugInfo, "WlbsConnectionReset");
    v5 = gIkeExtGlobals;
    v5[75].SpinCount = (ULONG_PTR)GetProcAddress((HMODULE)gIkeExtGlobals[75].DebugInfo, "WlbsCancelConnectionNotify");
    v7 = gIkeExtGlobals;
    if ( *(_QWORD *)&gIkeExtGlobals[75].LockCount
      && gIkeExtGlobals[75].OwningThread
      && gIkeExtGlobals[75].LockSemaphore
      && gIkeExtGlobals[75].SpinCount )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        TlsPeerAddr = IkeGetTlsPeerAddr(v6);
        TlsMmLuid = IkeGetTlsMmLuid(v10);
        WPP_SF_iS(v8, 81, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v17 = IkeGetTlsMmLuid(v6);
        v19 = &v17;
        v20 = 8;
        v13 = IkeGetTlsPeerAddr(v12);
        tlgCreate1Sz_wchar_t(v21, v13);
        v23 = 28;
        v22 = "NLB registration successful";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&byte_18014E38F,
          v14,
          v15,
          5,
          (__int64)v18);
      }
    }
    else
    {
      if ( gIkeExtGlobals[75].SpinCount )
      {
        ((void (*)(void))gIkeExtGlobals[75].SpinCount)();
        v7 = gIkeExtGlobals;
      }
      *(_QWORD *)&v7[75].LockCount = 0;
      gIkeExtGlobals[75].OwningThread = 0;
      gIkeExtGlobals[75].LockSemaphore = 0;
      gIkeExtGlobals[75].SpinCount = 0;
      FreeLibrary((HMODULE)gIkeExtGlobals[75].DebugInfo);
      gIkeExtGlobals[75].DebugInfo = 0;
    }
  }
  TraceLogHelper("IkeLoadNlb", 0);
  return IkeReturnError(0, "IkeLoadNlb");
}

```

## disassembly

```asm
0x180056304  mov     [rsp+arg_0], rbx
0x180056309  push    rdi
0x18005630a  sub     rsp, 0A0h
0x180056311  mov     rax, cs:__security_cookie
0x180056318  xor     rax, rsp
0x18005631b  mov     [rsp+0A8h+var_18], rax
0x180056323  mov     edx, 1
0x180056328  lea     rcx, aIkeloadnlb; "IkeLoadNlb"
0x18005632f  call    TraceLogHelper
0x180056334  mov     rbx, cs:gIkeExtGlobals
0x18005633b  lea     rcx, LibFileName; "wlbsctrl.dll"
0x180056342  xor     edx, edx; hFile
0x180056344  mov     r8d, 800h; dwFlags
0x18005634a  call    cs:__imp_LoadLibraryExW
0x180056350  mov     [rbx+0BB8h], rax
0x180056357  mov     rbx, cs:gIkeExtGlobals
0x18005635e  mov     rcx, [rbx+0BB8h]; hModule
0x180056365  test    rcx, rcx
0x180056368  jz      loc_180056578
0x18005636e  lea     rdx, ProcName; "WlbsConnectionUp"
0x180056375  call    cs:__imp_GetProcAddress
0x18005637b  mov     [rbx+0BC0h], rax
0x180056382  lea     rdx, aWlbsconnection_0; "WlbsConnectionDown"
0x180056389  mov     rbx, cs:gIkeExtGlobals
0x180056390  mov     rcx, [rbx+0BB8h]; hModule
0x180056397  call    cs:__imp_GetProcAddress
0x18005639d  mov     [rbx+0BC8h], rax
0x1800563a4  lea     rdx, aWlbsconnection_1; "WlbsConnectionReset"
0x1800563ab  mov     rbx, cs:gIkeExtGlobals
0x1800563b2  mov     rcx, [rbx+0BB8h]; hModule
0x1800563b9  call    cs:__imp_GetProcAddress
0x1800563bf  mov     [rbx+0BD0h], rax
0x1800563c6  lea     rdx, aWlbscancelconn; "WlbsCancelConnectionNotify"
0x1800563cd  mov     rbx, cs:gIkeExtGlobals
0x1800563d4  mov     rcx, [rbx+0BB8h]; hModule
0x1800563db  call    cs:__imp_GetProcAddress
0x1800563e1  mov     [rbx+0BD8h], rax
0x1800563e8  mov     rax, cs:gIkeExtGlobals
0x1800563ef  cmp     qword ptr [rax+0BC0h], 0
0x1800563f7  jz      loc_1800564F6
0x1800563fd  cmp     qword ptr [rax+0BC8h], 0
0x180056405  jz      loc_1800564F6
0x18005640b  cmp     qword ptr [rax+0BD0h], 0
0x180056413  jz      loc_1800564F6
0x180056419  cmp     qword ptr [rax+0BD8h], 0
0x180056421  jz      loc_1800564F6
0x180056427  mov     rdi, cs:WPP_GLOBAL_Control
0x18005642e  lea     rax, WPP_GLOBAL_Control
0x180056435  cmp     rdi, rax
0x180056438  jz      short loc_180056473
0x18005643a  cmp     byte ptr [rdi+19h], 4
0x18005643e  jb      short loc_180056473
0x180056440  test    byte ptr [rdi+1Ch], 10h
0x180056444  jz      short loc_180056473
0x180056446  mov     rdi, [rdi+10h]
0x18005644a  call    IkeGetTlsPeerAddr
0x18005644f  mov     rbx, rax
0x180056452  call    IkeGetTlsMmLuid
0x180056457  mov     r9, rax
0x18005645a  mov     [rsp+0A8h+var_88], rbx
0x18005645f  mov     edx, 51h ; 'Q'
0x180056464  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x18005646b  mov     rcx, rdi
0x18005646e  call    WPP_SF_iS
0x180056473  mov     eax, cs:dword_180173278
0x180056479  cmp     eax, 4
0x18005647c  jbe     loc_180056578
0x180056482  call    IkeGetTlsMmLuid
0x180056487  mov     [rsp+0A8h+var_78], rax
0x18005648c  lea     rax, [rsp+0A8h+var_78]
0x180056491  mov     [rsp+0A8h+var_48], rax
0x180056496  mov     [rsp+0A8h+var_40], 8
0x18005649f  call    IkeGetTlsPeerAddr
0x1800564a4  mov     rdx, rax
0x1800564a7  lea     rcx, [rsp+0A8h+var_38]
0x1800564ac  call    _tlgCreate1Sz_wchar_t
0x1800564b1  lea     rcx, aNlbRegistratio; "NLB registration successful"
0x1800564b8  mov     [rsp+0A8h+var_20], 1Ch
0x1800564c4  lea     rax, [rsp+0A8h+var_68]
0x1800564c9  mov     [rsp+0A8h+var_28], rcx
0x1800564d1  mov     [rsp+0A8h+var_80], rax
0x1800564d6  lea     rcx, dword_180173278
0x1800564dd  lea     rdx, byte_18014E38F
0x1800564e4  mov     dword ptr [rsp+0A8h+var_88], 5
0x1800564ec  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800564f1  jmp     loc_180056578
0x1800564f6  mov     rcx, [rax+0BD8h]
0x1800564fd  test    rcx, rcx
0x180056500  jz      short loc_180056511
0x180056502  mov     rax, rcx
0x180056505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005650a  mov     rax, cs:gIkeExtGlobals
0x180056511  mov     qword ptr [rax+0BC0h], 0
0x18005651c  mov     rax, cs:gIkeExtGlobals
0x180056523  mov     qword ptr [rax+0BC8h], 0
0x18005652e  mov     rax, cs:gIkeExtGlobals
0x180056535  mov     qword ptr [rax+0BD0h], 0
0x180056540  mov     rax, cs:gIkeExtGlobals
0x180056547  mov     qword ptr [rax+0BD8h], 0
0x180056552  mov     rcx, cs:gIkeExtGlobals
0x180056559  mov     rcx, [rcx+0BB8h]; hLibModule
0x180056560  call    cs:__imp_FreeLibrary
0x180056566  mov     rax, cs:gIkeExtGlobals
0x18005656d  mov     qword ptr [rax+0BB8h], 0
0x180056578  xor     edx, edx
0x18005657a  lea     rcx, aIkeloadnlb; "IkeLoadNlb"
0x180056581  call    TraceLogHelper
0x180056586  lea     rdx, aIkeloadnlb; "IkeLoadNlb"
0x18005658d  xor     ecx, ecx
0x18005658f  call    IkeReturnError
0x180056594  mov     rcx, [rsp+0A8h+var_18]
0x18005659c  xor     rcx, rsp; StackCookie
0x18005659f  call    __security_check_cookie
0x1800565a4  mov     rbx, [rsp+0A8h+arg_0]
0x1800565ac  add     rsp, 0A0h
0x1800565b3  pop     rdi
0x1800565b4  retn
```
