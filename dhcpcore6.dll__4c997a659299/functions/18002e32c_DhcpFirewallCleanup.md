# DhcpFirewallCleanup

- ea: `0x18002e32c`
- end: `0x18002e459`
- name: `DhcpFirewallCleanup`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b314`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18001907c`
- `0x18002e32c`
- `0x1800338c0`
- `0x180033900`
- `0x180033de4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e395`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e395`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e40b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e40b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002e3c8`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002e3c8`

## pseudocode

```c
int DhcpFirewallCleanup()
{
  _QWORD *v0; // rbx
  unsigned int LastErrorOrUnknown; // ebx
  __int64 v2; // rcx
  int result; // eax
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  phModule = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 15, WPP_52380679383138217cb423d182f11bb5_Traceguids, 546);
  v5 = DhcpAlloc(24);
  v0 = (_QWORD *)v5;
  if ( v5 )
  {
    if ( GetModuleHandleExW(4u, (LPCWSTR)DhcpFirewallDelPortCallback, &phModule)
      && (*(_WORD *)v0 = 546, v0[2] = phModule, TrySubmitThreadpoolCallback(DhcpFirewallDelPortCallback, v0, 0)) )
    {
      LastErrorOrUnknown = 0;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 16, WPP_52380679383138217cb423d182f11bb5_Traceguids);
      v5 = 0;
      phModule = 0;
    }
    else
    {
      LastErrorOrUnknown = GetLastErrorOrUnknown(v2);
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
  result = DhcpFree((LPVOID *)&v5);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    return WPP_SF_D(1028, 17, WPP_52380679383138217cb423d182f11bb5_Traceguids, LastErrorOrUnknown);
  return result;
}

```

## disassembly

```asm
0x18002e32c  mov     [rsp+arg_0], rbx
0x18002e331  push    r15
0x18002e333  sub     rsp, 20h
0x18002e337  mov     [rsp+28h+phModule], 0
0x18002e340  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e347  mov     r15d, 222h
0x18002e34d  jz      short loc_18002E368
0x18002e34f  mov     edx, 0Fh
0x18002e354  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e35b  mov     ecx, 404h
0x18002e360  mov     r9d, r15d
0x18002e363  call    WPP_SF_d
0x18002e368  mov     ecx, 18h
0x18002e36d  call    DhcpAlloc
0x18002e372  mov     [rsp+28h+arg_10], rax
0x18002e377  mov     rbx, rax
0x18002e37a  test    rax, rax
0x18002e37d  jnz     short loc_18002E384
0x18002e37f  lea     ebx, [rax+8]
0x18002e382  jmp     short loc_18002E401
0x18002e384  lea     r8, [rsp+28h+phModule]; phModule
0x18002e389  mov     ecx, 4; dwFlags
0x18002e38e  lea     rdx, DhcpFirewallDelPortCallback; lpModuleName
0x18002e395  call    cs:__imp_GetModuleHandleExW
0x18002e39c  nop     dword ptr [rax+rax+00h]
0x18002e3a1  test    eax, eax
0x18002e3a3  jnz     short loc_18002E3AE
0x18002e3a5  call    GetLastErrorOrUnknown
0x18002e3aa  mov     ebx, eax
0x18002e3ac  jmp     short loc_18002E401
0x18002e3ae  mov     [rbx], r15w
0x18002e3b2  lea     rcx, DhcpFirewallDelPortCallback; pfns
0x18002e3b9  mov     rax, [rsp+28h+phModule]
0x18002e3be  xor     r8d, r8d; pcbe
0x18002e3c1  mov     rdx, rbx; pv
0x18002e3c4  mov     [rbx+10h], rax
0x18002e3c8  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002e3cf  nop     dword ptr [rax+rax+00h]
0x18002e3d4  test    eax, eax
0x18002e3d6  jz      short loc_18002E3A5
0x18002e3d8  xor     ebx, ebx
0x18002e3da  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e3e1  jz      short loc_18002E3F7
0x18002e3e3  lea     edx, [rbx+10h]
0x18002e3e6  mov     ecx, 404h
0x18002e3eb  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e3f2  call    WPP_SF_
0x18002e3f7  mov     [rsp+28h+arg_10], rbx
0x18002e3fc  mov     [rsp+28h+phModule], rbx
0x18002e401  mov     rcx, [rsp+28h+phModule]; hLibModule
0x18002e406  test    rcx, rcx
0x18002e409  jz      short loc_18002E420
0x18002e40b  call    cs:__imp_FreeLibrary
0x18002e412  nop     dword ptr [rax+rax+00h]
0x18002e417  mov     [rsp+28h+phModule], 0
0x18002e420  lea     rcx, [rsp+28h+arg_10]
0x18002e425  call    DhcpFree
0x18002e42a  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e431  jz      short loc_18002E44C
0x18002e433  mov     edx, 11h
0x18002e438  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e43f  mov     ecx, 404h
0x18002e444  mov     r9d, ebx
0x18002e447  call    WPP_SF_D
0x18002e44c  mov     rbx, [rsp+28h+arg_0]
0x18002e451  add     rsp, 20h
0x18002e455  pop     r15
0x18002e457  retn
```
