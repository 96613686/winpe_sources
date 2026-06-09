# __CRTDLL_INIT

- ea: `0x180007a24`
- end: `0x180007b57`
- name: `__CRTDLL_INIT`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800079e0`

## callees

- `0x180007a24`
- `0x180007c78`
- `0x180007d70`
- `0x18001ce74`
- `0x18001d300`
- `0x18001d50c`
- `0x18001d804`
- `0x18001da98`
- `0x180024278`
- `0x180033cf8`
- `0x180033dd0`
- `0x18003d7a4`
- `0x18003d860`
- `0x18003d874`
- `0x18003e004`
- `0x18003e0fc`
- `0x18003e264`
- `0x18003f628`

## import_xrefs

- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180007b20`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180007b20`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180007af3`
- `api-ms-win-core-fibers-l1-1-0!FlsGetValue` at `0x180007af3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180007a61`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180007a61`

## pseudocode

```c
__int64 __fastcall _CRTDLL_INIT(__int64 a1, int a2, __int64 a3)
{
  void *v5; // rax
  void *v6; // rbx

  if ( a2 == 1 )
  {
    if ( !(unsigned int)core_crt_dll_init() )
      return 0;
    if ( (int)ioinit() < 0 )
    {
LABEL_4:
      mtterm();
      heap_term();
      return 0;
    }
    aenvptr = (char *)_crtGetEnvironmentStringsA();
    acmdln = GetCommandLineA();
    wcmdln = _crtGetCommandLineW();
    _initmbctable();
    if ( (int)setenvp() < 0 || (unsigned int)cinit(0) )
    {
      ioterm();
      goto LABEL_4;
    }
    ++dword_18009E17C;
  }
  else if ( a2 )
  {
    if ( a2 == 2 )
    {
      CrtSetReportMode();
      if ( !FlsGetValue(_flsindex) )
      {
        v5 = (void *)calloc_crt(1, 736);
        v6 = v5;
        if ( !v5 )
          return 0;
        if ( !FlsSetValue(_flsindex, v5) )
        {
          free(v6);
          return 0;
        }
        initptd(v6, 0);
      }
    }
    else if ( a2 == 3 )
    {
      freeptd(0);
    }
  }
  else
  {
    if ( dword_18009E17C <= 0 )
      return 0;
    --dword_18009E17C;
    if ( !C_Termination_Done )
      cexit();
    _crtdll_callstaticterminators();
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
0x180007a24  push    rbx
0x180007a26  sub     rsp, 20h
0x180007a2a  mov     rbx, r8
0x180007a2d  cmp     edx, 1
0x180007a30  jnz     short loc_180007AA5
0x180007a32  call    _core_crt_dll_init
0x180007a37  test    eax, eax
0x180007a39  jz      short loc_180007A4E
0x180007a3b  call    _ioinit
0x180007a40  test    eax, eax
0x180007a42  jns     short loc_180007A55
0x180007a44  call    _mtterm
0x180007a49  call    _heap_term
0x180007a4e  xor     eax, eax
0x180007a50  jmp     loc_180007B51
0x180007a55  call    __crtGetEnvironmentStringsA
0x180007a5a  mov     cs:_aenvptr, rax
0x180007a61  call    cs:__imp_GetCommandLineA
0x180007a67  mov     cs:_acmdln, rax
0x180007a6e  call    __crtGetCommandLineW
0x180007a73  mov     cs:_wcmdln, rax
0x180007a7a  call    __initmbctable
0x180007a7f  call    _setenvp
0x180007a84  test    eax, eax
0x180007a86  js      short loc_180007A9E
0x180007a88  xor     ecx, ecx
0x180007a8a  call    _cinit
0x180007a8f  test    eax, eax
0x180007a91  jnz     short loc_180007A9E
0x180007a93  inc     cs:dword_18009E17C
0x180007a99  jmp     loc_180007B4C
0x180007a9e  call    _ioterm
0x180007aa3  jmp     short loc_180007A44
0x180007aa5  test    edx, edx
0x180007aa7  jnz     short loc_180007AE3
0x180007aa9  mov     eax, cs:dword_18009E17C
0x180007aaf  test    eax, eax
0x180007ab1  jle     short loc_180007A4E
0x180007ab3  dec     eax
0x180007ab5  cmp     cs:_C_Termination_Done, edx
0x180007abb  mov     cs:dword_18009E17C, eax
0x180007ac1  jnz     short loc_180007AC8
0x180007ac3  call    _cexit
0x180007ac8  call    __crtdll_callstaticterminators
0x180007acd  test    rbx, rbx
0x180007ad0  jnz     short loc_180007B4C
0x180007ad2  call    _ioterm
0x180007ad7  call    _mtterm
0x180007adc  call    _heap_term
0x180007ae1  jmp     short loc_180007B4C
0x180007ae3  cmp     edx, 2
0x180007ae6  jnz     short loc_180007B40
0x180007ae8  call    _CrtSetReportMode
0x180007aed  mov     ecx, cs:__flsindex; dwFlsIndex
0x180007af3  call    cs:__imp_FlsGetValue
0x180007af9  test    rax, rax
0x180007afc  jnz     short loc_180007B4C
0x180007afe  mov     edx, 2E0h
0x180007b03  lea     ecx, [rax+1]
0x180007b06  call    _calloc_crt
0x180007b0b  mov     rbx, rax
0x180007b0e  test    rax, rax
0x180007b11  jz      loc_180007A4E
0x180007b17  mov     ecx, cs:__flsindex; dwFlsIndex
0x180007b1d  mov     rdx, rax; lpFlsData
0x180007b20  call    cs:__imp_FlsSetValue
0x180007b26  mov     rcx, rbx; Block
0x180007b29  test    eax, eax
0x180007b2b  jz      short loc_180007B36
0x180007b2d  xor     edx, edx
0x180007b2f  call    _initptd
0x180007b34  jmp     short loc_180007B4C
0x180007b36  call    free
0x180007b3b  jmp     loc_180007A4E
0x180007b40  cmp     edx, 3
0x180007b43  jnz     short loc_180007B4C
0x180007b45  xor     ecx, ecx; lpFlsData
0x180007b47  call    _freeptd
0x180007b4c  mov     eax, 1
0x180007b51  add     rsp, 20h
0x180007b55  pop     rbx
0x180007b56  retn
```
