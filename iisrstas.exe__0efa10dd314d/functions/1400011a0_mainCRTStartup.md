# __mainCRTStartup

- ea: `0x1400011a0`
- end: `0x140001347`
- name: `__mainCRTStartup`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001350`

## callees

- `0x1400011a0`
- `0x1400013fe`
- `0x1400014b0`
- `0x140001510`
- `0x140001677`
- `0x140002a40`
- `0x140005500`

## import_xrefs

- `msvcrt!_cexit` at `0x140001302`
- `msvcrt!_cexit` at `0x140001331`
- `msvcrt!_cexit` at `0x140001302`
- `msvcrt!_cexit` at `0x140001331`
- `msvcrt!_exit` at `0x140001321`
- `msvcrt!_exit` at `0x140001321`
- `msvcrt!exit` at `0x1400012f3`
- `msvcrt!exit` at `0x1400012f3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400011d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400011d9`

## pseudocode

```c
int _mainCRTStartup()
{
  PVOID StackBase; // rbx
  int v1; // esi
  signed __int64 v2; // rax
  int v3; // eax
  __int64 *i; // rdi
  int result; // eax

  StackBase = NtCurrentTeb()->NtTib.StackBase;
  v1 = 0;
  while ( 1 )
  {
    v2 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
    if ( !v2 )
      break;
    if ( (PVOID)v2 == StackBase )
    {
      v1 = 1;
      break;
    }
    Sleep(0x3E8u);
  }
  if ( _native_startup_state == 1 )
  {
    amsg_exit_0(31);
LABEL_18:
    if ( _native_startup_state == 1 )
    {
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v1 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
    result = main(argc, (const char **)argv, (const char **)envp);
    dword_14000A1C0 = result;
    if ( !dword_14000A1E0 )
      exit(result);
    if ( !dword_14000A1C4 )
    {
      _cexit();
      return dword_14000A1C0;
    }
    return result;
  }
  v3 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_14000A1C4 = 1;
    goto LABEL_18;
  }
  _native_startup_state = 1;
  for ( i = &_xi_a; i < &_xi_z; ++i )
  {
    if ( v3 )
      return 255;
    if ( *i )
      v3 = _guard_dispatch_icall_fptr();
  }
  if ( !v3 )
    goto LABEL_18;
  return 255;
}

```

## disassembly

```asm
0x1400011a0  push    rbx
0x1400011a2  push    rsi
0x1400011a3  push    rdi
0x1400011a4  push    r15
0x1400011a6  sub     rsp, 38h
0x1400011aa  mov     rax, gs:30h
0x1400011b3  mov     rbx, [rax+8]
0x1400011b7  xor     esi, esi
0x1400011b9  xor     eax, eax
0x1400011bb  lock cmpxchg cs:__native_startup_lock, rbx
0x1400011c4  jz      short loc_1400011E1
0x1400011c6  cmp     rax, rbx
0x1400011c9  jnz     short loc_1400011D4
0x1400011cb  mov     ebx, 1
0x1400011d0  mov     esi, ebx
0x1400011d2  jmp     short loc_1400011E6
0x1400011d4  mov     ecx, 3E8h; dwMilliseconds
0x1400011d9  call    cs:__imp_Sleep
0x1400011df  jmp     short loc_1400011B9
0x1400011e1  mov     ebx, 1
0x1400011e6  mov     eax, cs:__native_startup_state
0x1400011ec  cmp     eax, ebx
0x1400011ee  jnz     short loc_1400011FC
0x1400011f0  mov     ecx, 1Fh
0x1400011f5  call    _amsg_exit_0
0x1400011fa  jmp     short loc_140001261
0x1400011fc  mov     eax, cs:__native_startup_state
0x140001202  test    eax, eax
0x140001204  jnz     short loc_14000125B
0x140001206  mov     cs:__native_startup_state, ebx
0x14000120c  lea     r15, __xi_z
0x140001213  lea     rdi, __xi_a
0x14000121a  mov     [rsp+58h+var_30], rdi
0x14000121f  mov     [rsp+58h+var_38], eax
0x140001223  cmp     rdi, r15
0x140001226  jnb     short loc_14000124D
0x140001228  test    eax, eax
0x14000122a  jnz     short loc_140001251
0x14000122c  cmp     qword ptr [rdi], 0
0x140001230  jz      short loc_140001242
0x140001232  mov     rax, [rdi]
0x140001235  mov     rcx, cs:__guard_dispatch_icall_fptr
0x14000123c  call    rcx ; _guard_dispatch_icall_nop
0x14000123e  mov     [rsp+58h+var_38], eax
0x140001242  add     rdi, 8
0x140001246  mov     [rsp+58h+var_30], rdi
0x14000124b  jmp     short loc_140001223
0x14000124d  test    eax, eax
0x14000124f  jz      short loc_140001261
0x140001251  mov     eax, 0FFh
0x140001256  jmp     loc_14000133D
0x14000125b  mov     cs:dword_14000A1C4, ebx
0x140001261  mov     eax, cs:__native_startup_state
0x140001267  cmp     eax, ebx
0x140001269  jnz     short loc_140001288
0x14000126b  lea     rdx, __xc_z; Last
0x140001272  lea     rcx, __xc_a; First
0x140001279  call    _initterm_0
0x14000127e  mov     cs:__native_startup_state, 2
0x140001288  test    esi, esi
0x14000128a  jnz     short loc_140001295
0x14000128c  xor     eax, eax
0x14000128e  xchg    rax, cs:__native_startup_lock
0x140001295  cmp     cs:__dyn_tls_init_callback, 0
0x14000129d  jz      short loc_1400012C9
0x14000129f  lea     rcx, __dyn_tls_init_callback
0x1400012a6  call    _IsNonwritableInCurrentImage
0x1400012ab  test    eax, eax
0x1400012ad  jz      short loc_1400012C9
0x1400012af  xor     r8d, r8d
0x1400012b2  lea     edx, [r8+2]
0x1400012b6  xor     ecx, ecx
0x1400012b8  mov     rax, cs:__dyn_tls_init_callback
0x1400012bf  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400012c6  call    r9 ; _guard_dispatch_icall_nop
0x1400012c9  mov     r8, cs:envp; envp
0x1400012d0  mov     rdx, cs:argv; argv
0x1400012d7  mov     ecx, cs:argc; argc
0x1400012dd  call    main
0x1400012e2  mov     cs:dword_14000A1C0, eax
0x1400012e8  cmp     cs:dword_14000A1E0, 0
0x1400012ef  jnz     short loc_1400012F9
0x1400012f1  mov     ecx, eax; Code
0x1400012f3  call    cs:__imp_exit
0x1400012f9  cmp     cs:dword_14000A1C4, 0
0x140001300  jnz     short loc_14000130E
0x140001302  call    cs:__imp__cexit
0x140001308  mov     eax, cs:dword_14000A1C0
0x14000130e  jmp     short loc_14000133D
0x140001310  mov     cs:dword_14000A1C0, eax
0x140001316  cmp     cs:dword_14000A1E0, 0
0x14000131d  jnz     short loc_140001328
0x14000131f  mov     ecx, eax; Code
0x140001321  call    cs:__imp__exit
0x140001328  cmp     cs:dword_14000A1C4, 0
0x14000132f  jnz     short loc_14000133D
0x140001331  call    cs:__imp__cexit
0x140001337  mov     eax, cs:dword_14000A1C0
0x14000133d  add     rsp, 38h
0x140001341  pop     r15
0x140001343  pop     rdi
0x140001344  pop     rsi
0x140001345  pop     rbx
0x140001346  retn
0x1400055d0  push    rbp
0x1400055d2  sub     rsp, 20h
0x1400055d6  mov     rbp, rdx
0x1400055d9  mov     rdx, rcx
0x1400055dc  mov     rcx, [rcx]
0x1400055df  mov     ecx, [rcx]
0x1400055e1  call    _XcptFilter_0
0x1400055e6  nop
0x1400055e7  add     rsp, 20h
0x1400055eb  pop     rbp
0x1400055ec  retn
```
