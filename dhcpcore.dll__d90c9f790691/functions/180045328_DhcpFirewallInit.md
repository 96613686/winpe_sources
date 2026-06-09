# DhcpFirewallInit

- ea: `0x180045328`
- end: `0x1800454c9`
- name: `DhcpFirewallInit`
- size: `417`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025350`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x18001c0d8`
- `0x180045328`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800453dd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800453dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045481`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004546a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004546a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180045400`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180045400`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800453a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800453b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800453a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800453b2`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18004542c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18004542c`

## pseudocode

```c
__int64 DhcpFirewallInit()
{
  HANDLE v0; // rsi
  unsigned int LastErrorOrUnknown; // ebx
  _QWORD *v2; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v4; // rax
  HMODULE phModule; // [rsp+68h] [rbp+28h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v8; // [rsp+78h] [rbp+38h] BYREF

  v0 = DhcpGlobalFirewallReadyEvent;
  v8 = 0;
  TargetHandle = 0;
  phModule = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 12, WPP_52380679383138217cb423d182f11bb5_Traceguids, 68);
  if ( v0 )
  {
    v8 = DhcpAlloc(0x18u);
    v2 = v8;
    if ( v8 )
    {
      CurrentProcess = GetCurrentProcess();
      v4 = GetCurrentProcess();
      if ( DuplicateHandle(v4, v0, CurrentProcess, &TargetHandle, 0, 0, 2u)
        && GetModuleHandleExW(4u, (LPCWSTR)DhcpFirewallAddPortCallback, &phModule)
        && (*(_WORD *)v2 = 68,
            v2[1] = TargetHandle,
            v2[2] = phModule,
            TrySubmitThreadpoolCallback(DhcpFirewallAddPortCallback, v2, 0)) )
      {
        LastErrorOrUnknown = 0;
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_(1028, 13, WPP_52380679383138217cb423d182f11bb5_Traceguids);
        phModule = 0;
        TargetHandle = 0;
        v8 = 0;
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
  }
  else
  {
    LastErrorOrUnknown = 87;
  }
  if ( phModule )
  {
    FreeLibrary(phModule);
    phModule = 0;
  }
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  DhcpPunycodeFree(&v8);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 14, WPP_52380679383138217cb423d182f11bb5_Traceguids, LastErrorOrUnknown);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x180045328  mov     [rsp-18h+arg_0], rbx
0x18004532d  mov     [rsp-18h+phModule], rdx
0x180045332  push    rbp
0x180045333  push    rsi
0x180045334  push    rdi
0x180045335  mov     rbp, rsp
0x180045338  sub     rsp, 40h
0x18004533c  mov     rsi, cs:DhcpGlobalFirewallReadyEvent
0x180045343  mov     [rbp+arg_18], 0
0x18004534b  mov     [rbp+TargetHandle], 0
0x180045353  mov     [rbp+phModule], 0
0x18004535b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045362  jz      short loc_18004537E
0x180045364  mov     edx, 0Ch
0x180045369  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x180045370  mov     ecx, 404h
0x180045375  lea     r9d, [rdx+38h]
0x180045379  call    WPP_SF_d
0x18004537e  test    rsi, rsi
0x180045381  jnz     short loc_18004538B
0x180045383  lea     ebx, [rsi+57h]
0x180045386  jmp     loc_180045461
0x18004538b  mov     ecx, 18h
0x180045390  call    DhcpAlloc
0x180045395  mov     [rbp+arg_18], rax
0x180045399  mov     rdi, rax
0x18004539c  test    rax, rax
0x18004539f  jnz     short loc_1800453A9
0x1800453a1  lea     ebx, [rax+8]
0x1800453a4  jmp     loc_180045461
0x1800453a9  call    cs:__imp_GetCurrentProcess
0x1800453af  mov     rbx, rax
0x1800453b2  call    cs:__imp_GetCurrentProcess
0x1800453b8  mov     [rsp+40h+dwOptions], 2; dwOptions
0x1800453c0  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1800453c4  mov     rcx, rax; hSourceProcessHandle
0x1800453c7  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x1800453cf  mov     r8, rbx; hTargetProcessHandle
0x1800453d2  mov     [rsp+40h+dwDesiredAccess], 0; dwDesiredAccess
0x1800453da  mov     rdx, rsi; hSourceHandle
0x1800453dd  call    cs:__imp_DuplicateHandle
0x1800453e3  test    eax, eax
0x1800453e5  jnz     short loc_1800453F0
0x1800453e7  call    GetLastErrorOrUnknown
0x1800453ec  mov     ebx, eax
0x1800453ee  jmp     short loc_180045461
0x1800453f0  lea     r8, [rbp+phModule]; phModule
0x1800453f4  mov     ecx, 4; dwFlags
0x1800453f9  lea     rdx, DhcpFirewallAddPortCallback; lpModuleName
0x180045400  call    cs:__imp_GetModuleHandleExW
0x180045406  test    eax, eax
0x180045408  jz      short loc_1800453E7
0x18004540a  mov     word ptr [rdi], 44h ; 'D'
0x18004540f  lea     rcx, DhcpFirewallAddPortCallback; pfns
0x180045416  mov     rax, [rbp+TargetHandle]
0x18004541a  xor     r8d, r8d; pcbe
0x18004541d  mov     [rdi+8], rax
0x180045421  mov     rdx, rdi; pv
0x180045424  mov     rax, [rbp+phModule]
0x180045428  mov     [rdi+10h], rax
0x18004542c  call    cs:__imp_TrySubmitThreadpoolCallback
0x180045432  test    eax, eax
0x180045434  jz      short loc_1800453E7
0x180045436  xor     ebx, ebx
0x180045438  test    byte ptr cs:xmmword_1800616A0, 10h
0x18004543f  jz      short loc_180045455
0x180045441  lea     edx, [rbx+0Dh]
0x180045444  mov     ecx, 404h
0x180045449  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x180045450  call    WPP_SF_
0x180045455  mov     [rbp+phModule], rbx
0x180045459  mov     [rbp+TargetHandle], rbx
0x18004545d  mov     [rbp+arg_18], rbx
0x180045461  mov     rcx, [rbp+phModule]; hLibModule
0x180045465  test    rcx, rcx
0x180045468  jz      short loc_180045478
0x18004546a  call    cs:__imp_FreeLibrary
0x180045470  mov     [rbp+phModule], 0
0x180045478  mov     rcx, [rbp+TargetHandle]; hObject
0x18004547c  test    rcx, rcx
0x18004547f  jz      short loc_18004548F
0x180045481  call    cs:__imp_CloseHandle
0x180045487  mov     [rbp+TargetHandle], 0
0x18004548f  lea     rcx, [rbp+arg_18]
0x180045493  call    DhcpPunycodeFree
0x180045498  test    byte ptr cs:xmmword_1800616A0, 10h
0x18004549f  jz      short loc_1800454BA
0x1800454a1  mov     edx, 0Eh
0x1800454a6  lea     r8, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x1800454ad  mov     ecx, 404h
0x1800454b2  mov     r9d, ebx
0x1800454b5  call    WPP_SF_D
0x1800454ba  mov     eax, ebx
0x1800454bc  mov     rbx, [rsp+40h+arg_0]
0x1800454c1  add     rsp, 40h
0x1800454c5  pop     rdi
0x1800454c6  pop     rsi
0x1800454c7  pop     rbp
0x1800454c8  retn
```
