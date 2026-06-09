# __wmainCRTStartup

- ea: `0x1400011c0`
- end: `0x140001367`
- name: `__wmainCRTStartup`
- size: `423`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001370`

## callees

- `0x1400011c0`
- `0x14000140e`
- `0x1400014c0`
- `0x140001530`
- `0x140001697`
- `0x140001834`
- `0x140001940`

## import_xrefs

- `msvcrt!_cexit` at `0x140001322`
- `msvcrt!_cexit` at `0x140001351`
- `msvcrt!_cexit` at `0x140001322`
- `msvcrt!_cexit` at `0x140001351`
- `msvcrt!_exit` at `0x140001341`
- `msvcrt!_exit` at `0x140001341`
- `msvcrt!exit` at `0x140001313`
- `msvcrt!exit` at `0x140001313`
- `KERNEL32!Sleep` at `0x1400011f9`
- `KERNEL32!Sleep` at `0x1400011f9`

## pseudocode

```c
__int64 _wmainCRTStartup()
{
  PVOID StackBase; // rbx
  int v1; // esi
  signed __int64 v2; // rax
  int v3; // eax
  __int64 *i; // rdi
  __int64 result; // rax

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
    result = wmain((unsigned int)dword_140003128, qword_140003130, qword_140003138);
    dword_140003120 = result;
    if ( !dword_140003140 )
      exit(result);
    if ( !dword_140003124 )
    {
      _cexit();
      return (unsigned int)dword_140003120;
    }
    return result;
  }
  v3 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_140003124 = 1;
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
0x1400011c0  push    rbx
0x1400011c2  push    rsi
0x1400011c3  push    rdi
0x1400011c4  push    r15
0x1400011c6  sub     rsp, 38h
0x1400011ca  mov     rax, gs:30h
0x1400011d3  mov     rbx, [rax+8]
0x1400011d7  xor     esi, esi
0x1400011d9  xor     eax, eax
0x1400011db  lock cmpxchg cs:__native_startup_lock, rbx
0x1400011e4  jz      short loc_140001201
0x1400011e6  cmp     rax, rbx
0x1400011e9  jnz     short loc_1400011F4
0x1400011eb  mov     ebx, 1
0x1400011f0  mov     esi, ebx
0x1400011f2  jmp     short loc_140001206
0x1400011f4  mov     ecx, 3E8h; dwMilliseconds
0x1400011f9  call    cs:__imp_Sleep
0x1400011ff  jmp     short loc_1400011D9
0x140001201  mov     ebx, 1
0x140001206  mov     eax, cs:__native_startup_state
0x14000120c  cmp     eax, ebx
0x14000120e  jnz     short loc_14000121C
0x140001210  mov     ecx, 1Fh
0x140001215  call    _amsg_exit_0
0x14000121a  jmp     short loc_140001281
0x14000121c  mov     eax, cs:__native_startup_state
0x140001222  test    eax, eax
0x140001224  jnz     short loc_14000127B
0x140001226  mov     cs:__native_startup_state, ebx
0x14000122c  lea     r15, __xi_z
0x140001233  lea     rdi, __xi_a
0x14000123a  mov     [rsp+58h+var_30], rdi
0x14000123f  mov     [rsp+58h+var_38], eax
0x140001243  cmp     rdi, r15
0x140001246  jnb     short loc_14000126D
0x140001248  test    eax, eax
0x14000124a  jnz     short loc_140001271
0x14000124c  cmp     qword ptr [rdi], 0
0x140001250  jz      short loc_140001262
0x140001252  mov     rax, [rdi]
0x140001255  mov     rcx, cs:__guard_dispatch_icall_fptr
0x14000125c  call    rcx ; _guard_dispatch_icall_nop
0x14000125e  mov     [rsp+58h+var_38], eax
0x140001262  add     rdi, 8
0x140001266  mov     [rsp+58h+var_30], rdi
0x14000126b  jmp     short loc_140001243
0x14000126d  test    eax, eax
0x14000126f  jz      short loc_140001281
0x140001271  mov     eax, 0FFh
0x140001276  jmp     loc_14000135D
0x14000127b  mov     cs:dword_140003124, ebx
0x140001281  mov     eax, cs:__native_startup_state
0x140001287  cmp     eax, ebx
0x140001289  jnz     short loc_1400012A8
0x14000128b  lea     rdx, __xc_z; Last
0x140001292  lea     rcx, __xc_a; First
0x140001299  call    _initterm_0
0x14000129e  mov     cs:__native_startup_state, 2
0x1400012a8  test    esi, esi
0x1400012aa  jnz     short loc_1400012B5
0x1400012ac  xor     eax, eax
0x1400012ae  xchg    rax, cs:__native_startup_lock
0x1400012b5  cmp     cs:__dyn_tls_init_callback, 0
0x1400012bd  jz      short loc_1400012E9
0x1400012bf  lea     rcx, __dyn_tls_init_callback
0x1400012c6  call    _IsNonwritableInCurrentImage
0x1400012cb  test    eax, eax
0x1400012cd  jz      short loc_1400012E9
0x1400012cf  xor     r8d, r8d
0x1400012d2  lea     edx, [r8+2]
0x1400012d6  xor     ecx, ecx
0x1400012d8  mov     rax, cs:__dyn_tls_init_callback
0x1400012df  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400012e6  call    r9 ; _guard_dispatch_icall_nop
0x1400012e9  mov     r8, cs:qword_140003138
0x1400012f0  mov     rdx, cs:qword_140003130
0x1400012f7  mov     ecx, cs:dword_140003128
0x1400012fd  call    wmain
0x140001302  mov     cs:dword_140003120, eax
0x140001308  cmp     cs:dword_140003140, 0
0x14000130f  jnz     short loc_140001319
0x140001311  mov     ecx, eax; Code
0x140001313  call    cs:__imp_exit
0x140001319  cmp     cs:dword_140003124, 0
0x140001320  jnz     short loc_14000132E
0x140001322  call    cs:__imp__cexit
0x140001328  mov     eax, cs:dword_140003120
0x14000132e  jmp     short loc_14000135D
0x140001330  mov     cs:dword_140003120, eax
0x140001336  cmp     cs:dword_140003140, 0
0x14000133d  jnz     short loc_140001348
0x14000133f  mov     ecx, eax; Code
0x140001341  call    cs:__imp__exit
0x140001348  cmp     cs:dword_140003124, 0
0x14000134f  jnz     short loc_14000135D
0x140001351  call    cs:__imp__cexit
0x140001357  mov     eax, cs:dword_140003120
0x14000135d  add     rsp, 38h
0x140001361  pop     r15
0x140001363  pop     rdi
0x140001364  pop     rsi
0x140001365  pop     rbx
0x140001366  retn
0x140001980  push    rbp
0x140001982  sub     rsp, 20h
0x140001986  mov     rbp, rdx
0x140001989  mov     rdx, rcx
0x14000198c  mov     rcx, [rcx]
0x14000198f  mov     ecx, [rcx]
0x140001991  call    _XcptFilter_0
0x140001996  nop
0x140001997  add     rsp, 20h
0x14000199b  pop     rbp
0x14000199c  retn
```
