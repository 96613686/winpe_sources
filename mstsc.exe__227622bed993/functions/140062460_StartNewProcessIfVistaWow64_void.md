# StartNewProcessIfVistaWow64(void)

- ea: `0x140062460`
- end: `0x140062677`
- name: `?StartNewProcessIfVistaWow64@@YAHXZ`
- size: `535`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x140004703`
- `0x140008940`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x140061708`
- `0x140062460`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x1400625ce`
- `KERNEL32!GetCommandLineW` at `0x1400625ce`
- `KERNEL32!GetSystemDirectoryW` at `0x1400624f2`
- `KERNEL32!GetSystemDirectoryW` at `0x1400624f2`
- `KERNEL32!GetCurrentProcess` at `0x1400624ae`
- `KERNEL32!GetCurrentProcess` at `0x1400624ae`
- `KERNEL32!GetModuleHandleW` at `0x140062488`
- `KERNEL32!GetModuleHandleW` at `0x140062488`
- `KERNEL32!GetProcAddress` at `0x140062498`
- `KERNEL32!GetProcAddress` at `0x140062498`

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
0x140062460  mov     [rsp+arg_0], rbx
0x140062465  push    rdi
0x140062466  sub     rsp, 260h
0x14006246d  mov     rax, cs:__security_cookie
0x140062474  xor     rax, rsp
0x140062477  mov     [rsp+268h+var_18], rax
0x14006247f  lea     rcx, aKernel32; "kernel32"
0x140062486  xor     edi, edi
0x140062488  call    cs:__imp_GetModuleHandleW
0x14006248e  mov     rcx, rax; hModule
0x140062491  lea     rdx, aIswow64process; "IsWow64Process"
0x140062498  call    cs:__imp_GetProcAddress
0x14006249e  mov     [rsp+268h+var_238], edi
0x1400624a2  mov     rbx, rax
0x1400624a5  test    rax, rax
0x1400624a8  jz      loc_140062654
0x1400624ae  call    cs:__imp_GetCurrentProcess
0x1400624b4  mov     rcx, rax
0x1400624b7  lea     rdx, [rsp+268h+var_238]
0x1400624bc  mov     rax, rbx
0x1400624bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400624c4  test    eax, eax
0x1400624c6  jz      short loc_1400624CC
0x1400624c8  mov     eax, [rsp+268h+var_238]
0x1400624cc  test    eax, eax
0x1400624ce  jz      loc_140062654
0x1400624d4  xor     edx, edx; Val
0x1400624d6  lea     rcx, [rsp+268h+Buffer]; void *
0x1400624db  mov     r8d, 208h; Size
0x1400624e1  call    memset_0
0x1400624e6  mov     ebx, 104h
0x1400624eb  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x1400624f0  mov     edx, ebx; uSize
0x1400624f2  call    cs:__imp_GetSystemDirectoryW
0x1400624f8  test    eax, eax
0x1400624fa  jnz     short loc_140062550
0x1400624fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140062503  lea     rax, WPP_GLOBAL_Control
0x14006250a  cmp     rcx, rax
0x14006250d  jz      loc_140062654
0x140062513  test    byte ptr [rcx+1Ch], 8
0x140062517  jz      loc_140062654
0x14006251d  cmp     byte ptr [rcx+19h], 2
0x140062521  jb      loc_140062654
0x140062527  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006252c  mov     edx, 12h
0x140062531  mov     rcx, cs:WPP_GLOBAL_Control
0x140062538  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x14006253f  mov     r9d, eax
0x140062542  mov     rcx, [rcx+10h]
0x140062546  call    WPP_SF_d
0x14006254b  jmp     loc_140062654
0x140062550  lea     r8, aMstscExe_0; "\\mstsc.exe"
0x140062557  mov     rdx, rbx; unsigned __int64
0x14006255a  lea     rcx, [rsp+268h+Buffer]; unsigned __int16 *
0x14006255f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140062564  mov     ebx, eax
0x140062566  test    eax, eax
0x140062568  jns     short loc_1400625CE
0x14006256a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062571  lea     rax, WPP_GLOBAL_Control
0x140062578  cmp     rcx, rax
0x14006257b  jz      loc_140062654
0x140062581  test    byte ptr [rcx+1Ch], 8
0x140062585  jz      loc_140062654
0x14006258b  cmp     byte ptr [rcx+19h], 2
0x14006258f  jb      loc_140062654
0x140062595  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006259a  mov     edx, 13h
0x14006259f  lea     rcx, aStringcchcatFa_5; "StringCchCat failed"
0x1400625a6  mov     [rsp+268h+var_240], ebx
0x1400625aa  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x1400625b1  mov     [rsp+268h+var_248], rcx
0x1400625b6  mov     r9d, eax
0x1400625b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400625c0  mov     rcx, [rcx+10h]
0x1400625c4  call    WPP_SF_DsD
0x1400625c9  jmp     loc_140062654
0x1400625ce  call    cs:__imp_GetCommandLineW
0x1400625d4  test    rax, rax
0x1400625d7  jnz     short loc_140062607
0x1400625d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400625e0  lea     rax, WPP_GLOBAL_Control
0x1400625e7  cmp     rcx, rax
0x1400625ea  jz      short loc_140062654
0x1400625ec  test    byte ptr [rcx+1Ch], 8
0x1400625f0  jz      short loc_140062654
0x1400625f2  cmp     byte ptr [rcx+19h], 2
0x1400625f6  jb      short loc_140062654
0x1400625f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400625fd  mov     edx, 14h
0x140062602  jmp     loc_140062531
0x140062607  mov     rdx, rax; lpCommandLine
0x14006260a  lea     rcx, [rsp+268h+Buffer]; lpApplicationName
0x14006260f  call    ?LaunchClientProcessFromWow64@@YAJPEBGPEAG@Z; LaunchClientProcessFromWow64(ushort const *,ushort *)
0x140062614  mov     ebx, eax
0x140062616  test    eax, eax
0x140062618  jns     short loc_14006264F
0x14006261a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062621  lea     rax, WPP_GLOBAL_Control
0x140062628  cmp     rcx, rax
0x14006262b  jz      short loc_140062654
0x14006262d  test    byte ptr [rcx+1Ch], 8
0x140062631  jz      short loc_140062654
0x140062633  cmp     byte ptr [rcx+19h], 2
0x140062637  jb      short loc_140062654
0x140062639  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006263e  mov     edx, 15h
0x140062643  lea     rcx, aLaunchclientpr; "LaunchClientProcessFromWow64 failed"
0x14006264a  jmp     loc_1400625A6
0x14006264f  mov     edi, 1
0x140062654  mov     eax, edi
0x140062656  mov     rcx, [rsp+268h+var_18]
0x14006265e  xor     rcx, rsp; StackCookie
0x140062661  call    __security_check_cookie
0x140062666  mov     rbx, [rsp+268h+arg_0]
0x14006266e  add     rsp, 260h
0x140062675  pop     rdi
0x140062676  retn
```
