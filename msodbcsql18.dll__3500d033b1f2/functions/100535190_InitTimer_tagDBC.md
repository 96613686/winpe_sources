# InitTimer(tagDBC *)

- ea: `0x100535190`
- end: `0x100535399`
- name: `?InitTimer@@YAFPEAUtagDBC@@@Z`
- size: `521`
- prototype: `__int16 __fastcall(struct tagDBC *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x100534ec8`
- `0x100535024`

## callees

- `0x100520370`
- `0x1005212b4`
- `0x100535190`
- `0x100546a7c`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1005351c0`
- `KERNEL32!LoadLibraryExW` at `0x1005351c0`
- `KERNEL32!GetLastError` at `0x1005351e7`
- `KERNEL32!GetLastError` at `0x100535300`
- `KERNEL32!GetLastError` at `0x1005351e7`
- `KERNEL32!GetLastError` at `0x100535300`
- `KERNEL32!GetProcAddress` at `0x10053522d`
- `KERNEL32!GetProcAddress` at `0x100535248`
- `KERNEL32!GetProcAddress` at `0x100535263`
- `KERNEL32!GetProcAddress` at `0x10053527e`
- `KERNEL32!GetProcAddress` at `0x10053522d`
- `KERNEL32!GetProcAddress` at `0x100535248`
- `KERNEL32!GetProcAddress` at `0x100535263`
- `KERNEL32!GetProcAddress` at `0x10053527e`
- `KERNEL32!FreeLibrary` at `0x100535329`
- `KERNEL32!FreeLibrary` at `0x100535329`

## string_xrefs

- `0x1005351b3`: `WINMM.DLL`

## pseudocode

```c
__int64 __fastcall InitTimer(struct tagDBC *a1)
{
  unsigned __int16 v1; // bx
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int64 v5; // rdx
  unsigned int (*ProcAddress)(unsigned int); // rax
  DWORD v7; // eax
  DWORD v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  if ( g_hTimeLib )
  {
LABEL_19:
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x1B409u, v1);
    return v1;
  }
  Library = LoadLibraryExW(L"WINMM.DLL", 0, 0x800u);
  g_hTimeLib = Library;
  if ( !Library )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 75785);
    LastError = GetLastError();
    PostSQLErrorEx(a1, 0x9CD5u, LastError, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v1 = -1;
    if ( (bidGblFlags & 2) != 0 )
    {
      v5 = 77833;
LABEL_18:
      bidTraceMark(0, v5);
      goto LABEL_19;
    }
    return v1;
  }
  fptimeGetDevCaps = (unsigned int (*)(struct timecaps_tag *, unsigned int))GetProcAddress(Library, "timeGetDevCaps");
  fptimeGetTime = (unsigned int (*)(void))GetProcAddress(g_hTimeLib, "timeGetTime");
  fptimeBeginPeriod = (unsigned int (*)(unsigned int))GetProcAddress(g_hTimeLib, "timeBeginPeriod");
  ProcAddress = (unsigned int (*)(unsigned int))GetProcAddress(g_hTimeLib, "timeEndPeriod");
  fptimeEndPeriod = ProcAddress;
  if ( fptimeGetDevCaps && fptimeGetTime && fptimeBeginPeriod && ProcAddress )
  {
    ((void (__fastcall *)(DWORD *, __int64))fptimeGetDevCaps)(&v9, 8);
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD))fptimeBeginPeriod)(v9) )
      v9 = 0;
    else
      g_SQLPerfData.TimerResolution = v9;
    goto LABEL_19;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceMark(0, 88073);
  v7 = GetLastError();
  PostSQLErrorEx(a1, 0x9CD6u, v7, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
  FreeLibrary(g_hTimeLib);
  g_hTimeLib = 0;
  fptimeGetDevCaps = 0;
  fptimeGetTime = 0;
  fptimeBeginPeriod = 0;
  fptimeEndPeriod = 0;
  v1 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    v5 = 99337;
    goto LABEL_18;
  }
  return v1;
}

```

## disassembly

```asm
0x100535190  mov     [rsp+arg_0], rbx
0x100535195  mov     [rsp+arg_10], rsi
0x10053519a  push    rdi
0x10053519b  sub     rsp, 30h
0x10053519f  xor     ebx, ebx
0x1005351a1  mov     rsi, rcx
0x1005351a4  cmp     cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hTimeLib
0x1005351ab  jnz     loc_10053536A
0x1005351b1  xor     edx, edx; hFile
0x1005351b3  lea     rcx, aWinmmDll; "WINMM.DLL"
0x1005351ba  mov     r8d, 800h; dwFlags
0x1005351c0  call    cs:__imp_LoadLibraryExW
0x1005351c6  mov     cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hTimeLib
0x1005351cd  test    rax, rax
0x1005351d0  jnz     short loc_100535223
0x1005351d2  test    byte ptr cs:_bidGblFlags, 2
0x1005351d9  jz      short loc_1005351E7
0x1005351db  mov     edx, 12809h
0x1005351e0  xor     ecx, ecx
0x1005351e2  call    _bidTraceMark
0x1005351e7  call    cs:__imp_GetLastError
0x1005351ed  or      [rsp+38h+var_18], 0FFFFFFFFh
0x1005351f2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1005351f6  mov     r8d, eax; int
0x1005351f9  mov     r9, rdi; unsigned __int64
0x1005351fc  mov     edx, 9CD5h; unsigned __int16
0x100535201  mov     rcx, rsi; struct tagOBJBASE *
0x100535204  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x100535209  test    byte ptr cs:_bidGblFlags, 2
0x100535210  movzx   ebx, di
0x100535213  jz      loc_100535386
0x100535219  mov     edx, 13009h
0x10053521e  jmp     loc_100535363
0x100535223  lea     rdx, aTimegetdevcaps; "timeGetDevCaps"
0x10053522a  mov     rcx, rax; hModule
0x10053522d  call    cs:__imp_GetProcAddress
0x100535233  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hModule
0x10053523a  lea     rdx, aTimegettime; "timeGetTime"
0x100535241  mov     cs:?fptimeGetDevCaps@@3P6AIPEAUtimecaps_tag@@I@ZEA, rax; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x100535248  call    cs:__imp_GetProcAddress
0x10053524e  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hModule
0x100535255  lea     rdx, aTimebeginperio; "timeBeginPeriod"
0x10053525c  mov     cs:?fptimeGetTime@@3P6AKXZEA, rax; ulong (*fptimeGetTime)(void)
0x100535263  call    cs:__imp_GetProcAddress
0x100535269  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hModule
0x100535270  lea     rdx, aTimeendperiod; "timeEndPeriod"
0x100535277  mov     cs:?fptimeBeginPeriod@@3P6AII@ZEA, rax; uint (*fptimeBeginPeriod)(uint)
0x10053527e  call    cs:__imp_GetProcAddress
0x100535284  mov     r8, cs:?fptimeGetDevCaps@@3P6AIPEAUtimecaps_tag@@I@ZEA; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x10053528b  mov     cs:?fptimeEndPeriod@@3P6AII@ZEA, rax; uint (*fptimeEndPeriod)(uint)
0x100535292  test    r8, r8
0x100535295  jz      short loc_1005352EB
0x100535297  cmp     cs:?fptimeGetTime@@3P6AKXZEA, rbx; ulong (*fptimeGetTime)(void)
0x10053529e  jz      short loc_1005352EB
0x1005352a0  cmp     cs:?fptimeBeginPeriod@@3P6AII@ZEA, rbx; uint (*fptimeBeginPeriod)(uint)
0x1005352a7  jz      short loc_1005352EB
0x1005352a9  test    rax, rax
0x1005352ac  jz      short loc_1005352EB
0x1005352ae  mov     edx, 8
0x1005352b3  lea     rcx, [rsp+38h+arg_8]
0x1005352b8  mov     rax, r8
0x1005352bb  call    cs:__guard_dispatch_icall_fptr
0x1005352c1  mov     ecx, [rsp+38h+arg_8]
0x1005352c5  mov     rax, cs:?fptimeBeginPeriod@@3P6AII@ZEA; uint (*fptimeBeginPeriod)(uint)
0x1005352cc  call    cs:__guard_dispatch_icall_fptr
0x1005352d2  test    eax, eax
0x1005352d4  jnz     short loc_1005352E5
0x1005352d6  mov     eax, [rsp+38h+arg_8]
0x1005352da  mov     cs:?g_SQLPerfData@@3Usqlperf@@A.TimerResolution, eax; sqlperf g_SQLPerfData ...
0x1005352e0  jmp     loc_10053536A
0x1005352e5  mov     [rsp+38h+arg_8], ebx
0x1005352e9  jmp     short loc_10053536A
0x1005352eb  test    byte ptr cs:_bidGblFlags, 2
0x1005352f2  jz      short loc_100535300
0x1005352f4  mov     edx, 15809h
0x1005352f9  xor     ecx, ecx
0x1005352fb  call    _bidTraceMark
0x100535300  call    cs:__imp_GetLastError
0x100535306  or      [rsp+38h+var_18], 0FFFFFFFFh
0x10053530b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x10053530f  mov     r8d, eax; int
0x100535312  mov     r9, rdi; unsigned __int64
0x100535315  mov     edx, 9CD6h; unsigned __int16
0x10053531a  mov     rcx, rsi; struct tagOBJBASE *
0x10053531d  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x100535322  mov     rcx, cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA; hLibModule
0x100535329  call    cs:__imp_FreeLibrary
0x10053532f  test    byte ptr cs:_bidGblFlags, 2
0x100535336  mov     cs:?g_hTimeLib@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hTimeLib
0x10053533d  mov     cs:?fptimeGetDevCaps@@3P6AIPEAUtimecaps_tag@@I@ZEA, rbx; uint (*fptimeGetDevCaps)(timecaps_tag *,uint)
0x100535344  mov     cs:?fptimeGetTime@@3P6AKXZEA, rbx; ulong (*fptimeGetTime)(void)
0x10053534b  mov     cs:?fptimeBeginPeriod@@3P6AII@ZEA, rbx; uint (*fptimeBeginPeriod)(uint)
0x100535352  mov     cs:?fptimeEndPeriod@@3P6AII@ZEA, rbx; uint (*fptimeEndPeriod)(uint)
0x100535359  movzx   ebx, di
0x10053535c  jz      short loc_100535386
0x10053535e  mov     edx, 18409h
0x100535363  xor     ecx, ecx
0x100535365  call    _bidTraceMark
0x10053536a  test    byte ptr cs:_bidGblFlags, 2
0x100535371  jz      short loc_100535386
0x100535373  movzx   r8d, bx; __int16
0x100535377  mov     edx, 1B409h; unsigned __int64
0x10053537c  xor     ecx, ecx; unsigned __int64
0x10053537e  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x100535383  movzx   ebx, ax
0x100535386  mov     rsi, [rsp+38h+arg_10]
0x10053538b  movzx   eax, bx
0x10053538e  mov     rbx, [rsp+38h+arg_0]
0x100535393  add     rsp, 30h
0x100535397  pop     rdi
0x100535398  retn
```
