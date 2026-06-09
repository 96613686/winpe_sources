# DhcpFirewallCleanup

- ea: `0x180045168`
- end: `0x180045281`
- name: `DhcpFirewallCleanup`
- size: `281`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c660`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x18001c0d8`
- `0x180045168`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004523a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004523a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800451d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800451d0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800451fd`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800451fd`

## pseudocode

```c
__int64 DhcpFirewallCleanup()
{
  _QWORD *v0; // rbx
  unsigned int LastErrorOrUnknown; // ebx
  __int64 result; // rax
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF
  _QWORD *v4; // [rsp+40h] [rbp+18h] BYREF

  phModule = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 15, WPP_52380679383138217cb423d182f11bb5_Traceguids, 68);
  v4 = DhcpAlloc(0x18u);
  v0 = v4;
  if ( v4 )
  {
    if ( GetModuleHandleExW(4u, (LPCWSTR)DhcpFirewallDelPortCallback, &phModule)
      && (*(_WORD *)v0 = 68, v0[2] = phModule, TrySubmitThreadpoolCallback(DhcpFirewallDelPortCallback, v0, 0)) )
    {
      LastErrorOrUnknown = 0;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_(1028, 16, WPP_52380679383138217cb423d182f11bb5_Traceguids);
      v4 = 0;
      phModule = 0;
    }
    else
    {
      LastErrorOrUnknown = GetLastErrorOrUnknown();
    }
  }
  else
  {
    LastErrorOrUnknown = 8;
  }
  if ( phModule )
  {
    FreeLibrary(phModule);
    phModule = 0;
  }
  result = DhcpPunycodeFree(&v4);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    return WPP_SF_D(1028, 17, WPP_52380679383138217cb423d182f11bb5_Traceguids, LastErrorOrUnknown);
  return result;
}

```

## disassembly

```asm
0x180045168  mov     [rsp+arg_0], rbx
0x18004516d  push    r15
0x18004516f  sub     rsp, 20h
0x180045173  mov     [rsp+28h+phModule], 0
0x18004517c  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045183  mov     r15d, 44h ; 'D'
0x180045189  jz      short loc_1800451A3
0x18004518b  lea     edx, [r15-35h]
0x18004518f  mov     ecx, 404h
0x180045194  mov     r9d, r15d
0x180045197  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18004519e  call    WPP_SF_d
0x1800451a3  mov     ecx, 18h
0x1800451a8  call    DhcpAlloc
0x1800451ad  mov     [rsp+28h+arg_10], rax
0x1800451b2  mov     rbx, rax
0x1800451b5  test    rax, rax
0x1800451b8  jnz     short loc_1800451BF
0x1800451ba  lea     ebx, [rax+8]
0x1800451bd  jmp     short loc_180045230
0x1800451bf  lea     r8, [rsp+28h+phModule]; phModule
0x1800451c4  mov     ecx, 4; dwFlags
0x1800451c9  lea     rdx, DhcpFirewallDelPortCallback; lpModuleName
0x1800451d0  call    cs:__imp_GetModuleHandleExW
0x1800451d6  test    eax, eax
0x1800451d8  jnz     short loc_1800451E3
0x1800451da  call    GetLastErrorOrUnknown
0x1800451df  mov     ebx, eax
0x1800451e1  jmp     short loc_180045230
0x1800451e3  mov     [rbx], r15w
0x1800451e7  lea     rcx, DhcpFirewallDelPortCallback; pfns
0x1800451ee  mov     rax, [rsp+28h+phModule]
0x1800451f3  xor     r8d, r8d; pcbe
0x1800451f6  mov     rdx, rbx; pv
0x1800451f9  mov     [rbx+10h], rax
0x1800451fd  call    cs:__imp_TrySubmitThreadpoolCallback
0x180045203  test    eax, eax
0x180045205  jz      short loc_1800451DA
0x180045207  xor     ebx, ebx
0x180045209  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045210  jz      short loc_180045226
0x180045212  lea     edx, [rbx+10h]
0x180045215  mov     ecx, 404h
0x18004521a  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x180045221  call    WPP_SF_
0x180045226  mov     [rsp+28h+arg_10], rbx
0x18004522b  mov     [rsp+28h+phModule], rbx
0x180045230  mov     rcx, [rsp+28h+phModule]; hLibModule
0x180045235  test    rcx, rcx
0x180045238  jz      short loc_180045249
0x18004523a  call    cs:__imp_FreeLibrary
0x180045240  mov     [rsp+28h+phModule], 0
0x180045249  lea     rcx, [rsp+28h+arg_10]
0x18004524e  call    DhcpPunycodeFree
0x180045253  test    byte ptr cs:xmmword_1800616A0, 10h
0x18004525a  jz      short loc_180045275
0x18004525c  mov     edx, 11h
0x180045261  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x180045268  mov     ecx, 404h
0x18004526d  mov     r9d, ebx
0x180045270  call    WPP_SF_D
0x180045275  mov     rbx, [rsp+28h+arg_0]
0x18004527a  add     rsp, 20h
0x18004527e  pop     r15
0x180045280  retn
```
