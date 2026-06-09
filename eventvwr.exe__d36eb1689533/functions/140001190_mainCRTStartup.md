# __mainCRTStartup

- ea: `0x140001190`
- end: `0x140001337`
- name: `__mainCRTStartup`
- size: `423`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001340`

## callees

- `0x140001190`
- `0x1400013ee`
- `0x1400014a0`
- `0x140001500`
- `0x140001667`
- `0x1400023ac`
- `0x140002cf0`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400011c9`
- `KERNEL32!Sleep` at `0x1400011c9`
- `msvcrt!_cexit` at `0x1400012f2`
- `msvcrt!_cexit` at `0x140001321`
- `msvcrt!_cexit` at `0x1400012f2`
- `msvcrt!_cexit` at `0x140001321`
- `msvcrt!_exit` at `0x140001311`
- `msvcrt!_exit` at `0x140001311`
- `msvcrt!exit` at `0x1400012e3`
- `msvcrt!exit` at `0x1400012e3`

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
    dword_1400060A0 = result;
    if ( !dword_1400060C0 )
      exit(result);
    if ( !dword_1400060A4 )
    {
      _cexit();
      return dword_1400060A0;
    }
    return result;
  }
  v3 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_1400060A4 = 1;
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
0x140001190  push    rbx
0x140001192  push    rsi
0x140001193  push    rdi
0x140001194  push    r15
0x140001196  sub     rsp, 38h
0x14000119a  mov     rax, gs:30h
0x1400011a3  mov     rbx, [rax+8]
0x1400011a7  xor     esi, esi
0x1400011a9  xor     eax, eax
0x1400011ab  lock cmpxchg cs:__native_startup_lock, rbx
0x1400011b4  jz      short loc_1400011D1
0x1400011b6  cmp     rax, rbx
0x1400011b9  jnz     short loc_1400011C4
0x1400011bb  mov     ebx, 1
0x1400011c0  mov     esi, ebx
0x1400011c2  jmp     short loc_1400011D6
0x1400011c4  mov     ecx, 3E8h; dwMilliseconds
0x1400011c9  call    cs:__imp_Sleep
0x1400011cf  jmp     short loc_1400011A9
0x1400011d1  mov     ebx, 1
0x1400011d6  mov     eax, cs:__native_startup_state
0x1400011dc  cmp     eax, ebx
0x1400011de  jnz     short loc_1400011EC
0x1400011e0  mov     ecx, 1Fh
0x1400011e5  call    _amsg_exit_0
0x1400011ea  jmp     short loc_140001251
0x1400011ec  mov     eax, cs:__native_startup_state
0x1400011f2  test    eax, eax
0x1400011f4  jnz     short loc_14000124B
0x1400011f6  mov     cs:__native_startup_state, ebx
0x1400011fc  lea     r15, __xi_z
0x140001203  lea     rdi, __xi_a
0x14000120a  mov     [rsp+58h+var_30], rdi
0x14000120f  mov     [rsp+58h+var_38], eax
0x140001213  cmp     rdi, r15
0x140001216  jnb     short loc_14000123D
0x140001218  test    eax, eax
0x14000121a  jnz     short loc_140001241
0x14000121c  cmp     qword ptr [rdi], 0
0x140001220  jz      short loc_140001232
0x140001222  mov     rax, [rdi]
0x140001225  mov     rcx, cs:__guard_dispatch_icall_fptr
0x14000122c  call    rcx ; _guard_dispatch_icall_nop
0x14000122e  mov     [rsp+58h+var_38], eax
0x140001232  add     rdi, 8
0x140001236  mov     [rsp+58h+var_30], rdi
0x14000123b  jmp     short loc_140001213
0x14000123d  test    eax, eax
0x14000123f  jz      short loc_140001251
0x140001241  mov     eax, 0FFh
0x140001246  jmp     loc_14000132D
0x14000124b  mov     cs:dword_1400060A4, ebx
0x140001251  mov     eax, cs:__native_startup_state
0x140001257  cmp     eax, ebx
0x140001259  jnz     short loc_140001278
0x14000125b  lea     rdx, __xc_z; Last
0x140001262  lea     rcx, __xc_a; First
0x140001269  call    _initterm_0
0x14000126e  mov     cs:__native_startup_state, 2
0x140001278  test    esi, esi
0x14000127a  jnz     short loc_140001285
0x14000127c  xor     eax, eax
0x14000127e  xchg    rax, cs:__native_startup_lock
0x140001285  cmp     cs:__dyn_tls_init_callback, 0
0x14000128d  jz      short loc_1400012B9
0x14000128f  lea     rcx, __dyn_tls_init_callback
0x140001296  call    _IsNonwritableInCurrentImage
0x14000129b  test    eax, eax
0x14000129d  jz      short loc_1400012B9
0x14000129f  xor     r8d, r8d
0x1400012a2  lea     edx, [r8+2]
0x1400012a6  xor     ecx, ecx
0x1400012a8  mov     rax, cs:__dyn_tls_init_callback
0x1400012af  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400012b6  call    r9 ; _guard_dispatch_icall_nop
0x1400012b9  mov     r8, cs:envp; envp
0x1400012c0  mov     rdx, cs:argv; argv
0x1400012c7  mov     ecx, cs:argc; argc
0x1400012cd  call    main
0x1400012d2  mov     cs:dword_1400060A0, eax
0x1400012d8  cmp     cs:dword_1400060C0, 0
0x1400012df  jnz     short loc_1400012E9
0x1400012e1  mov     ecx, eax; Code
0x1400012e3  call    cs:__imp_exit
0x1400012e9  cmp     cs:dword_1400060A4, 0
0x1400012f0  jnz     short loc_1400012FE
0x1400012f2  call    cs:__imp__cexit
0x1400012f8  mov     eax, cs:dword_1400060A0
0x1400012fe  jmp     short loc_14000132D
0x140001300  mov     cs:dword_1400060A0, eax
0x140001306  cmp     cs:dword_1400060C0, 0
0x14000130d  jnz     short loc_140001318
0x14000130f  mov     ecx, eax; Code
0x140001311  call    cs:__imp__exit
0x140001318  cmp     cs:dword_1400060A4, 0
0x14000131f  jnz     short loc_14000132D
0x140001321  call    cs:__imp__cexit
0x140001327  mov     eax, cs:dword_1400060A0
0x14000132d  add     rsp, 38h
0x140001331  pop     r15
0x140001333  pop     rdi
0x140001334  pop     rsi
0x140001335  pop     rbx
0x140001336  retn
0x140002dc0  push    rbp
0x140002dc2  sub     rsp, 20h
0x140002dc6  mov     rbp, rdx
0x140002dc9  mov     rdx, rcx
0x140002dcc  mov     rcx, [rcx]
0x140002dcf  mov     ecx, [rcx]
0x140002dd1  call    _XcptFilter_0
0x140002dd6  nop
0x140002dd7  add     rsp, 20h
0x140002ddb  pop     rbp
0x140002ddc  retn
```
