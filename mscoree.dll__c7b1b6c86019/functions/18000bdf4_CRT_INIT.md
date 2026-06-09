# __CRT_INIT

- ea: `0x18000bdf4`
- end: `0x18000bfbe`
- name: `__CRT_INIT`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000bd64`

## callees

- `0x18000bdf4`
- `0x18000f264`
- `0x18000f834`
- `0x18000f92c`
- `0x18000fa0c`
- `0x18000fa94`
- `0x18000fb9c`
- `0x18000fbb0`
- `0x18000feec`
- `0x18000ff60`
- `0x18000ff88`
- `0x18001022c`
- `0x1800102b0`
- `0x180010628`
- `0x180010770`
- `0x1800108a0`
- `0x180032140`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18000be3a`
- `KERNEL32!GetVersionExW` at `0x18000be3a`
- `KERNEL32!GetCommandLineA` at `0x18000beb5`
- `KERNEL32!GetCommandLineA` at `0x18000beb5`
- `KERNEL32!FlsSetValue` at `0x18000bf74`
- `KERNEL32!FlsSetValue` at `0x18000bf74`

## pseudocode

```c
__int64 __fastcall _CRT_INIT(UtilExecutionEngine *a1, int a2, __int64 a3)
{
  unsigned int v4; // eax
  void *v6; // rax
  void *v7; // rbx
  struct _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  if ( a2 == 1 )
  {
    memset_thunk_772440563353939046(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( !GetVersionExW(&VersionInformation) )
      return 0;
    winmajor = VersionInformation.dwMajorVersion;
    winver = VersionInformation.dwMinorVersion + (VersionInformation.dwMajorVersion << 8);
    osplatform = VersionInformation.dwPlatformId;
    v4 = VersionInformation.dwBuildNumber & 0x7FFF | 0x8000;
    winminor = VersionInformation.dwMinorVersion;
    if ( VersionInformation.dwPlatformId == 2 )
      v4 = VersionInformation.dwBuildNumber & 0x7FFF;
    osver = v4;
    if ( !(unsigned int)heap_init(1) )
      return 0;
    if ( !(unsigned int)mtinit() )
      goto LABEL_7;
    acmdln = GetCommandLineA();
    aenvptr = (char *)_crtGetEnvironmentStringsA();
    if ( (int)ioinit() < 0 )
    {
LABEL_10:
      mtterm();
LABEL_7:
      heap_term();
      return 0;
    }
    if ( (int)setargv() < 0 || (int)setenvp() < 0 || (unsigned int)cinit(0) )
    {
      ioterm();
      goto LABEL_10;
    }
    ++dword_180060020;
  }
  else if ( a2 )
  {
    if ( a2 == 2 )
    {
      UtilExecutionEngine::ClrAllocationDisallowed(a1);
      v6 = calloc(1u, 0x2E0u);
      v7 = v6;
      if ( !v6 )
        return 0;
      if ( !FlsSetValue(_flsindex, v6) )
      {
        free(v7);
        return 0;
      }
      initptd(v7, 0);
    }
    else if ( a2 == 3 )
    {
      freeptd(0);
    }
  }
  else
  {
    if ( dword_180060020 <= 0 )
      return 0;
    --dword_180060020;
    if ( !C_Termination_Done )
      cexit();
    if ( !a3 )
    {
      ioterm();
      mtterm();
      heap_term();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000bdf4  push    rbx
0x18000bdf6  sub     rsp, 150h
0x18000bdfd  mov     rax, cs:__security_cookie
0x18000be04  xor     rax, rsp
0x18000be07  mov     [rsp+158h+var_18], rax
0x18000be0f  mov     rbx, r8
0x18000be12  cmp     edx, 1
0x18000be15  jnz     loc_18000BF0D
0x18000be1b  xor     edx, edx; Val
0x18000be1d  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18000be22  mov     r8d, 110h; Size
0x18000be28  call    memset$thunk$772440563353939046
0x18000be2d  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18000be32  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000be3a  call    cs:__imp_GetVersionExW
0x18000be40  test    eax, eax
0x18000be42  jz      short loc_18000BEAE
0x18000be44  mov     ecx, [rsp+158h+VersionInformation.dwMajorVersion]
0x18000be48  mov     eax, ecx
0x18000be4a  mov     edx, [rsp+158h+VersionInformation.dwMinorVersion]
0x18000be4e  mov     r9d, [rsp+158h+VersionInformation.dwPlatformId]
0x18000be53  mov     r8d, [rsp+158h+VersionInformation.dwBuildNumber]
0x18000be58  shl     eax, 8
0x18000be5b  and     r8d, 7FFFh
0x18000be62  add     eax, edx
0x18000be64  mov     cs:_winmajor, ecx
0x18000be6a  mov     cs:_winver, eax
0x18000be70  mov     ecx, 1
0x18000be75  mov     eax, r8d
0x18000be78  mov     cs:_osplatform, r9d
0x18000be7f  bts     eax, 0Fh
0x18000be83  mov     cs:_winminor, edx
0x18000be89  cmp     r9d, 2
0x18000be8d  cmovz   eax, r8d
0x18000be91  mov     cs:_osver, eax
0x18000be97  call    _heap_init
0x18000be9c  test    eax, eax
0x18000be9e  jz      short loc_18000BEAE
0x18000bea0  call    _mtinit
0x18000bea5  test    eax, eax
0x18000bea7  jnz     short loc_18000BEB5
0x18000bea9  call    _heap_term
0x18000beae  xor     eax, eax
0x18000beb0  jmp     loc_18000BFA5
0x18000beb5  call    cs:__imp_GetCommandLineA
0x18000bebb  mov     cs:_acmdln, rax
0x18000bec2  call    __crtGetEnvironmentStringsA
0x18000bec7  mov     cs:_aenvptr, rax
0x18000bece  call    _ioinit
0x18000bed3  test    eax, eax
0x18000bed5  jns     short loc_18000BEDE
0x18000bed7  call    _mtterm
0x18000bedc  jmp     short loc_18000BEA9
0x18000bede  call    _setargv
0x18000bee3  test    eax, eax
0x18000bee5  js      short loc_18000BF06
0x18000bee7  call    _setenvp
0x18000beec  test    eax, eax
0x18000beee  js      short loc_18000BF06
0x18000bef0  xor     ecx, ecx
0x18000bef2  call    _cinit
0x18000bef7  test    eax, eax
0x18000bef9  jnz     short loc_18000BF06
0x18000befb  inc     cs:dword_180060020
0x18000bf01  jmp     loc_18000BFA0
0x18000bf06  call    _ioterm
0x18000bf0b  jmp     short loc_18000BED7
0x18000bf0d  test    edx, edx
0x18000bf0f  jnz     short loc_18000BF46
0x18000bf11  mov     eax, cs:dword_180060020
0x18000bf17  test    eax, eax
0x18000bf19  jle     short loc_18000BEAE
0x18000bf1b  dec     eax
0x18000bf1d  cmp     cs:_C_Termination_Done, edx
0x18000bf23  mov     cs:dword_180060020, eax
0x18000bf29  jnz     short loc_18000BF30
0x18000bf2b  call    _cexit
0x18000bf30  test    rbx, rbx
0x18000bf33  jnz     short loc_18000BFA0
0x18000bf35  call    _ioterm
0x18000bf3a  call    _mtterm
0x18000bf3f  call    _heap_term
0x18000bf44  jmp     short loc_18000BFA0
0x18000bf46  cmp     edx, 2
0x18000bf49  jnz     short loc_18000BF94
0x18000bf4b  call    ?ClrAllocationDisallowed@UtilExecutionEngine@@EEAAHXZ; UtilExecutionEngine::ClrAllocationDisallowed(void)
0x18000bf50  mov     edx, 2E0h; Size
0x18000bf55  mov     ecx, 1; Count
0x18000bf5a  call    calloc
0x18000bf5f  mov     rbx, rax
0x18000bf62  test    rax, rax
0x18000bf65  jz      loc_18000BEAE
0x18000bf6b  mov     ecx, cs:__flsindex; dwFlsIndex
0x18000bf71  mov     rdx, rax; lpFlsData
0x18000bf74  call    cs:__imp_FlsSetValue
0x18000bf7a  mov     rcx, rbx; Block
0x18000bf7d  test    eax, eax
0x18000bf7f  jz      short loc_18000BF8A
0x18000bf81  xor     edx, edx
0x18000bf83  call    _initptd
0x18000bf88  jmp     short loc_18000BFA0
0x18000bf8a  call    free
0x18000bf8f  jmp     loc_18000BEAE
0x18000bf94  cmp     edx, 3
0x18000bf97  jnz     short loc_18000BFA0
0x18000bf99  xor     ecx, ecx; lpFlsData
0x18000bf9b  call    _freeptd
0x18000bfa0  mov     eax, 1
0x18000bfa5  mov     rcx, [rsp+158h+var_18]
0x18000bfad  xor     rcx, rsp; StackCookie
0x18000bfb0  call    __security_check_cookie
0x18000bfb5  add     rsp, 150h
0x18000bfbc  pop     rbx
0x18000bfbd  retn
```
