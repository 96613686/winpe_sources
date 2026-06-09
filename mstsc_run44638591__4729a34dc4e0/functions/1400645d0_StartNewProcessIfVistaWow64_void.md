# StartNewProcessIfVistaWow64(void)

- ea: `0x1400645d0`
- end: `0x1400647e7`
- name: `?StartNewProcessIfVistaWow64@@YAHXZ`
- size: `535`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14006590c`

## callees

- `0x140004703`
- `0x140008940`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x140063878`
- `0x1400645d0`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x14006473e`
- `KERNEL32!GetCommandLineW` at `0x14006473e`
- `KERNEL32!GetSystemDirectoryW` at `0x140064662`
- `KERNEL32!GetSystemDirectoryW` at `0x140064662`
- `KERNEL32!GetCurrentProcess` at `0x14006461e`
- `KERNEL32!GetCurrentProcess` at `0x14006461e`
- `KERNEL32!GetModuleHandleW` at `0x1400645f8`
- `KERNEL32!GetModuleHandleW` at `0x1400645f8`
- `KERNEL32!GetProcAddress` at `0x140064608`
- `KERNEL32!GetProcAddress` at `0x140064608`

## pseudocode

```c
__int64 StartNewProcessIfVistaWow64(void)
{
  unsigned int v0; // edi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rbx
  HANDLE CurrentProcess; // rax
  int v4; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  int v7; // eax
  char v8; // bl
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  WCHAR *CommandLineW; // rax
  int v13; // eax
  _DWORD v15[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  v0 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernel32");
  v15[0] = 0;
  ProcAddress = GetProcAddress(ModuleHandleW, "IsWow64Process");
  if ( !ProcAddress )
    return v0;
  CurrentProcess = GetCurrentProcess();
  v4 = ((__int64 (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(CurrentProcess, v15);
  if ( v4 )
    v4 = v15[0];
  if ( !v4 )
    return v0;
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 18;
LABEL_10:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
        CurrentThreadActivityIdPrefix);
      return v0;
    }
    return v0;
  }
  v7 = StringCchCatW(Buffer, 0x104u, L"\\mstsc.exe");
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v0;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 19;
    v11 = "StringCchCat failed";
    goto LABEL_16;
  }
  CommandLineW = GetCommandLineW();
  if ( CommandLineW )
  {
    v13 = LaunchClientProcessFromWow64(Buffer, CommandLineW);
    v8 = v13;
    if ( v13 >= 0 )
      return 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v0;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 21;
    v11 = "LaunchClientProcessFromWow64 failed";
LABEL_16:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      v9,
      (__int64)v11,
      v8);
    return v0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 20;
    goto LABEL_10;
  }
  return v0;
}

```

## disassembly

```asm
0x1400645d0  mov     [rsp+arg_0], rbx
0x1400645d5  push    rdi
0x1400645d6  sub     rsp, 260h
0x1400645dd  mov     rax, cs:__security_cookie
0x1400645e4  xor     rax, rsp
0x1400645e7  mov     [rsp+268h+var_18], rax
0x1400645ef  lea     rcx, aKernel32; "kernel32"
0x1400645f6  xor     edi, edi
0x1400645f8  call    cs:__imp_GetModuleHandleW
0x1400645fe  mov     rcx, rax; hModule
0x140064601  lea     rdx, aIswow64process; "IsWow64Process"
0x140064608  call    cs:__imp_GetProcAddress
0x14006460e  mov     [rsp+268h+var_238], edi
0x140064612  mov     rbx, rax
0x140064615  test    rax, rax
0x140064618  jz      loc_1400647C4
0x14006461e  call    cs:__imp_GetCurrentProcess
0x140064624  mov     rcx, rax
0x140064627  lea     rdx, [rsp+268h+var_238]
0x14006462c  mov     rax, rbx
0x14006462f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064634  test    eax, eax
0x140064636  jz      short loc_14006463C
0x140064638  mov     eax, [rsp+268h+var_238]
0x14006463c  test    eax, eax
0x14006463e  jz      loc_1400647C4
0x140064644  xor     edx, edx; Val
0x140064646  lea     rcx, [rsp+268h+Buffer]; void *
0x14006464b  mov     r8d, 208h; Size
0x140064651  call    memset_0
0x140064656  mov     ebx, 104h
0x14006465b  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x140064660  mov     edx, ebx; uSize
0x140064662  call    cs:__imp_GetSystemDirectoryW
0x140064668  test    eax, eax
0x14006466a  jnz     short loc_1400646C0
0x14006466c  mov     rcx, cs:WPP_GLOBAL_Control
0x140064673  lea     rax, WPP_GLOBAL_Control
0x14006467a  cmp     rcx, rax
0x14006467d  jz      loc_1400647C4
0x140064683  test    byte ptr [rcx+1Ch], 8
0x140064687  jz      loc_1400647C4
0x14006468d  cmp     byte ptr [rcx+19h], 2
0x140064691  jb      loc_1400647C4
0x140064697  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006469c  mov     edx, 12h
0x1400646a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400646a8  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400646af  mov     r9d, eax
0x1400646b2  mov     rcx, [rcx+10h]
0x1400646b6  call    WPP_SF_d
0x1400646bb  jmp     loc_1400647C4
0x1400646c0  lea     r8, aMstscExe_0; "\\mstsc.exe"
0x1400646c7  mov     rdx, rbx; unsigned __int64
0x1400646ca  lea     rcx, [rsp+268h+Buffer]; unsigned __int16 *
0x1400646cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400646d4  mov     ebx, eax
0x1400646d6  test    eax, eax
0x1400646d8  jns     short loc_14006473E
0x1400646da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400646e1  lea     rax, WPP_GLOBAL_Control
0x1400646e8  cmp     rcx, rax
0x1400646eb  jz      loc_1400647C4
0x1400646f1  test    byte ptr [rcx+1Ch], 8
0x1400646f5  jz      loc_1400647C4
0x1400646fb  cmp     byte ptr [rcx+19h], 2
0x1400646ff  jb      loc_1400647C4
0x140064705  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006470a  mov     edx, 13h
0x14006470f  lea     rcx, aStringcchcatFa_5; "StringCchCat failed"
0x140064716  mov     [rsp+268h+var_240], ebx
0x14006471a  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140064721  mov     [rsp+268h+var_248], rcx
0x140064726  mov     r9d, eax
0x140064729  mov     rcx, cs:WPP_GLOBAL_Control
0x140064730  mov     rcx, [rcx+10h]
0x140064734  call    WPP_SF_DsD
0x140064739  jmp     loc_1400647C4
0x14006473e  call    cs:__imp_GetCommandLineW
0x140064744  test    rax, rax
0x140064747  jnz     short loc_140064777
0x140064749  mov     rcx, cs:WPP_GLOBAL_Control
0x140064750  lea     rax, WPP_GLOBAL_Control
0x140064757  cmp     rcx, rax
0x14006475a  jz      short loc_1400647C4
0x14006475c  test    byte ptr [rcx+1Ch], 8
0x140064760  jz      short loc_1400647C4
0x140064762  cmp     byte ptr [rcx+19h], 2
0x140064766  jb      short loc_1400647C4
0x140064768  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006476d  mov     edx, 14h
0x140064772  jmp     loc_1400646A1
0x140064777  mov     rdx, rax; lpCommandLine
0x14006477a  lea     rcx, [rsp+268h+Buffer]; lpApplicationName
0x14006477f  call    ?LaunchClientProcessFromWow64@@YAJPEBGPEAG@Z; LaunchClientProcessFromWow64(ushort const *,ushort *)
0x140064784  mov     ebx, eax
0x140064786  test    eax, eax
0x140064788  jns     short loc_1400647BF
0x14006478a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064791  lea     rax, WPP_GLOBAL_Control
0x140064798  cmp     rcx, rax
0x14006479b  jz      short loc_1400647C4
0x14006479d  test    byte ptr [rcx+1Ch], 8
0x1400647a1  jz      short loc_1400647C4
0x1400647a3  cmp     byte ptr [rcx+19h], 2
0x1400647a7  jb      short loc_1400647C4
0x1400647a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400647ae  mov     edx, 15h
0x1400647b3  lea     rcx, aLaunchclientpr; "LaunchClientProcessFromWow64 failed"
0x1400647ba  jmp     loc_140064716
0x1400647bf  mov     edi, 1
0x1400647c4  mov     eax, edi
0x1400647c6  mov     rcx, [rsp+268h+var_18]
0x1400647ce  xor     rcx, rsp; StackCookie
0x1400647d1  call    __security_check_cookie
0x1400647d6  mov     rbx, [rsp+268h+arg_0]
0x1400647de  add     rsp, 260h
0x1400647e5  pop     rdi
0x1400647e6  retn
```
