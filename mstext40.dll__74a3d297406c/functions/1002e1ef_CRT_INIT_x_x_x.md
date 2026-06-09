# _CRT_INIT(x,x,x)

- ea: `0x1002e1ef`
- end: `0x1002e2e4`
- name: `__CRT_INIT@12`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1002e384`
- `0x1002e492`

## callees

- `0x1002df32`
- `0x1002e1ef`
- `0x1002f065`
- `0x1002f122`
- `0x1002f1d5`
- `0x1002f24b`
- `0x100302d8`
- `0x100302f7`
- `0x100336b6`
- `0x100339eb`
- `0x10033a00`
- `0x10033a85`
- `0x10033bae`
- `0x10033bbd`
- `0x100344f8`
- `0x100347ac`
- `0x100347fe`
- `0x10034a2d`
- `0x10034baa`
- `0x10034c37`
- `0x10034c80`
- `0x10034cc5`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x1002e228`
- `KERNEL32!GetCommandLineA` at `0x1002e228`
- `KERNEL32!GetCurrentThreadId` at `0x1002e32f`
- `KERNEL32!GetCurrentThreadId` at `0x1002e32f`

## pseudocode

```c
int __stdcall _CRT_INIT(int a1, int a2, int a3)
{
  DWORD *v4; // eax
  DWORD *v5; // esi

  if ( a2 == 1 )
  {
    if ( !_heap_init() )
      return 0;
    if ( !_mtinit() )
    {
LABEL_5:
      _heap_term();
      return 0;
    }
    _RTC_Initialize();
    _acmdln = GetCommandLineA();
    _aenvptr = (char *)__crtGetEnvironmentStringsA();
    if ( _ioinit() < 0 )
    {
LABEL_7:
      _mtterm();
      goto LABEL_5;
    }
    if ( _setargv() < 0 || _setenvp() < 0 || _cinit(0) )
    {
      _ioterm();
      goto LABEL_7;
    }
    ++dword_10044700;
  }
  else if ( a2 )
  {
    if ( a2 == 2 )
    {
      if ( !__crtFlsGetValue(__flsindex) )
      {
        v4 = (DWORD *)_calloc_crt(1, 956);
        v5 = v4;
        if ( !v4 )
          return 0;
        if ( !__crtFlsSetValue(__flsindex, v4) )
        {
          free(v5);
          return 0;
        }
        _initptd(v5, 0);
        *v5 = GetCurrentThreadId();
        v5[1] = -1;
      }
    }
    else if ( a2 == 3 )
    {
      _freeptd(0);
    }
  }
  else
  {
    if ( dword_10044700 <= 0 )
      return 0;
    --dword_10044700;
    if ( !_C_Termination_Done )
      _cexit();
    __freeCrtMemory();
    if ( !a3 )
    {
      _ioterm();
      _mtterm();
      _heap_term();
      if ( __flsindex != -1 )
        _mtterm();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1002e1ef  push    8
0x1002e1f1  push    offset stru_1003CF10
0x1002e1f6  call    __SEH_prolog4
0x1002e1fb  mov     eax, [ebp+arg_4]
0x1002e1fe  cmp     eax, 1
0x1002e201  jnz     short loc_1002E27D
0x1002e203  call    __heap_init
0x1002e208  test    eax, eax
0x1002e20a  jnz     short loc_1002E213
0x1002e20c  xor     eax, eax
0x1002e20e  jmp     loc_1002E359
0x1002e213  call    __mtinit
0x1002e218  test    eax, eax
0x1002e21a  jnz     short loc_1002E223
0x1002e21c  call    __heap_term
0x1002e221  jmp     short loc_1002E20C
0x1002e223  call    __RTC_Initialize
0x1002e228  call    ds:__imp__GetCommandLineA@0
0x1002e22e  mov     __acmdln, eax
0x1002e233  call    ___crtGetEnvironmentStringsA
0x1002e238  mov     __aenvptr, eax
0x1002e23d  call    __ioinit
0x1002e242  test    eax, eax
0x1002e244  jns     short loc_1002E24D
0x1002e246  call    __mtterm
0x1002e24b  jmp     short loc_1002E21C
0x1002e24d  call    __setargv
0x1002e252  test    eax, eax
0x1002e254  js      short loc_1002E276
0x1002e256  call    __setenvp
0x1002e25b  test    eax, eax
0x1002e25d  js      short loc_1002E276
0x1002e25f  push    0
0x1002e261  call    __cinit
0x1002e266  pop     ecx
0x1002e267  test    eax, eax
0x1002e269  jnz     short loc_1002E276
0x1002e26b  inc     dword_10044700
0x1002e271  jmp     loc_1002E356
0x1002e276  call    __ioterm
0x1002e27b  jmp     short loc_1002E246
0x1002e27d  test    eax, eax
0x1002e27f  jnz     short loc_1002E2E6
0x1002e281  mov     eax, dword_10044700
0x1002e286  test    eax, eax
0x1002e288  jle     short loc_1002E20C
0x1002e28a  dec     eax
0x1002e28b  mov     dword_10044700, eax
0x1002e290  and     [ebp+ms_exc.registration.TryLevel], 0
0x1002e294  cmp     __C_Termination_Done, 0
0x1002e29b  jnz     short loc_1002E2A2
0x1002e29d  call    __cexit
0x1002e2a2  call    ___freeCrtMemory
0x1002e2a7  mov     esi, [ebp+arg_8]
0x1002e2aa  test    esi, esi
0x1002e2ac  jnz     short loc_1002E2BD
0x1002e2ae  call    __ioterm
0x1002e2b3  call    __mtterm
0x1002e2b8  call    __heap_term
0x1002e2bd  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1002e2c4  call    loc_1002E2D1
0x1002e2c9  jmp     loc_1002E356
0x1002e2ce  mov     esi, [ebp+arg_8]
0x1002e2d1  test    esi, esi
0x1002e2d3  jnz     short loc_1002E2E3
0x1002e2d5  cmp     ___flsindex, 0FFFFFFFFh
0x1002e2dc  jz      short loc_1002E2E3
0x1002e2de  call    __mtterm
0x1002e2e3  retn
0x1002e2e6  cmp     eax, 2
0x1002e2e9  jnz     short loc_1002E349
0x1002e2eb  push    ___flsindex; dwTlsIndex
0x1002e2f1  call    ___crtFlsGetValue
0x1002e2f6  pop     ecx
0x1002e2f7  test    eax, eax
0x1002e2f9  jnz     short loc_1002E356
0x1002e2fb  push    3BCh
0x1002e300  push    1
0x1002e302  call    __calloc_crt
0x1002e307  pop     ecx
0x1002e308  pop     ecx
0x1002e309  mov     esi, eax
0x1002e30b  test    esi, esi
0x1002e30d  jz      loc_1002E20C
0x1002e313  push    esi; lpTlsValue
0x1002e314  push    ___flsindex; dwTlsIndex
0x1002e31a  call    ___crtFlsSetValue
0x1002e31f  pop     ecx
0x1002e320  pop     ecx
0x1002e321  test    eax, eax
0x1002e323  jz      short loc_1002E33D
0x1002e325  push    0
0x1002e327  push    esi
0x1002e328  call    __initptd
0x1002e32d  pop     ecx
0x1002e32e  pop     ecx
0x1002e32f  call    ds:__imp__GetCurrentThreadId@0
0x1002e335  mov     [esi], eax
0x1002e337  or      dword ptr [esi+4], 0FFFFFFFFh
0x1002e33b  jmp     short loc_1002E356
0x1002e33d  push    esi; Block
0x1002e33e  call    _free
0x1002e343  pop     ecx
0x1002e344  jmp     loc_1002E20C
0x1002e349  cmp     eax, 3
0x1002e34c  jnz     short loc_1002E356
0x1002e34e  push    0; Block
0x1002e350  call    __freeptd
0x1002e355  pop     ecx
0x1002e356  xor     eax, eax
0x1002e358  inc     eax
0x1002e359  call    __SEH_epilog4
0x1002e35e  retn    0Ch
```
