# __wmainCRTStartup

- ea: `0x140001160`
- end: `0x140001307`
- name: `__wmainCRTStartup`
- size: `423`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001310`

## callees

- `0x140001160`
- `0x14000139e`
- `0x140001450`
- `0x1400014c0`
- `0x140001627`
- `0x1400019b8`
- `0x140002030`

## import_xrefs

- `msvcrt!_exit` at `0x1400012e1`
- `msvcrt!_exit` at `0x1400012e1`
- `msvcrt!exit` at `0x1400012b3`
- `msvcrt!exit` at `0x1400012b3`
- `msvcrt!_cexit` at `0x1400012c2`
- `msvcrt!_cexit` at `0x1400012f1`
- `msvcrt!_cexit` at `0x1400012c2`
- `msvcrt!_cexit` at `0x1400012f1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140001199`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140001199`

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
    result = wmain((unsigned int)dword_140005148, (_QWORD *)qword_140005150);
    dword_140005140 = result;
    if ( !dword_140005160 )
      exit(result);
    if ( !dword_140005144 )
    {
      _cexit();
      return (unsigned int)dword_140005140;
    }
    return result;
  }
  v3 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_140005144 = 1;
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
0x140001160  push    rbx
0x140001162  push    rsi
0x140001163  push    rdi
0x140001164  push    r15
0x140001166  sub     rsp, 38h
0x14000116a  mov     rax, gs:30h
0x140001173  mov     rbx, [rax+8]
0x140001177  xor     esi, esi
0x140001179  xor     eax, eax
0x14000117b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001184  jz      short loc_1400011A1
0x140001186  cmp     rax, rbx
0x140001189  jnz     short loc_140001194
0x14000118b  mov     ebx, 1
0x140001190  mov     esi, ebx
0x140001192  jmp     short loc_1400011A6
0x140001194  mov     ecx, 3E8h; dwMilliseconds
0x140001199  call    cs:__imp_Sleep
0x14000119f  jmp     short loc_140001179
0x1400011a1  mov     ebx, 1
0x1400011a6  mov     eax, cs:__native_startup_state
0x1400011ac  cmp     eax, ebx
0x1400011ae  jnz     short loc_1400011BC
0x1400011b0  mov     ecx, 1Fh
0x1400011b5  call    _amsg_exit_0
0x1400011ba  jmp     short loc_140001221
0x1400011bc  mov     eax, cs:__native_startup_state
0x1400011c2  test    eax, eax
0x1400011c4  jnz     short loc_14000121B
0x1400011c6  mov     cs:__native_startup_state, ebx
0x1400011cc  lea     r15, __xi_z
0x1400011d3  lea     rdi, __xi_a
0x1400011da  mov     [rsp+58h+var_30], rdi
0x1400011df  mov     [rsp+58h+var_38], eax
0x1400011e3  cmp     rdi, r15
0x1400011e6  jnb     short loc_14000120D
0x1400011e8  test    eax, eax
0x1400011ea  jnz     short loc_140001211
0x1400011ec  cmp     qword ptr [rdi], 0
0x1400011f0  jz      short loc_140001202
0x1400011f2  mov     rax, [rdi]
0x1400011f5  mov     rcx, cs:__guard_dispatch_icall_fptr
0x1400011fc  call    rcx ; _guard_dispatch_icall_nop
0x1400011fe  mov     [rsp+58h+var_38], eax
0x140001202  add     rdi, 8
0x140001206  mov     [rsp+58h+var_30], rdi
0x14000120b  jmp     short loc_1400011E3
0x14000120d  test    eax, eax
0x14000120f  jz      short loc_140001221
0x140001211  mov     eax, 0FFh
0x140001216  jmp     loc_1400012FD
0x14000121b  mov     cs:dword_140005144, ebx
0x140001221  mov     eax, cs:__native_startup_state
0x140001227  cmp     eax, ebx
0x140001229  jnz     short loc_140001248
0x14000122b  lea     rdx, __xc_z; Last
0x140001232  lea     rcx, __xc_a; First
0x140001239  call    _initterm_0
0x14000123e  mov     cs:__native_startup_state, 2
0x140001248  test    esi, esi
0x14000124a  jnz     short loc_140001255
0x14000124c  xor     eax, eax
0x14000124e  xchg    rax, cs:__native_startup_lock
0x140001255  cmp     cs:__dyn_tls_init_callback, 0
0x14000125d  jz      short loc_140001289
0x14000125f  lea     rcx, __dyn_tls_init_callback
0x140001266  call    _IsNonwritableInCurrentImage
0x14000126b  test    eax, eax
0x14000126d  jz      short loc_140001289
0x14000126f  xor     r8d, r8d
0x140001272  lea     edx, [r8+2]
0x140001276  xor     ecx, ecx
0x140001278  mov     rax, cs:__dyn_tls_init_callback
0x14000127f  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001286  call    r9 ; _guard_dispatch_icall_nop
0x140001289  mov     r8, cs:qword_140005158
0x140001290  mov     rdx, cs:qword_140005150
0x140001297  mov     ecx, cs:dword_140005148
0x14000129d  call    wmain
0x1400012a2  mov     cs:dword_140005140, eax
0x1400012a8  cmp     cs:dword_140005160, 0
0x1400012af  jnz     short loc_1400012B9
0x1400012b1  mov     ecx, eax; Code
0x1400012b3  call    cs:__imp_exit
0x1400012b9  cmp     cs:dword_140005144, 0
0x1400012c0  jnz     short loc_1400012CE
0x1400012c2  call    cs:__imp__cexit
0x1400012c8  mov     eax, cs:dword_140005140
0x1400012ce  jmp     short loc_1400012FD
0x1400012d0  mov     cs:dword_140005140, eax
0x1400012d6  cmp     cs:dword_140005160, 0
0x1400012dd  jnz     short loc_1400012E8
0x1400012df  mov     ecx, eax; Code
0x1400012e1  call    cs:__imp__exit
0x1400012e8  cmp     cs:dword_140005144, 0
0x1400012ef  jnz     short loc_1400012FD
0x1400012f1  call    cs:__imp__cexit
0x1400012f7  mov     eax, cs:dword_140005140
0x1400012fd  add     rsp, 38h
0x140001301  pop     r15
0x140001303  pop     rdi
0x140001304  pop     rsi
0x140001305  pop     rbx
0x140001306  retn
0x140002070  push    rbp
0x140002072  sub     rsp, 20h
0x140002076  mov     rbp, rdx
0x140002079  mov     rdx, rcx
0x14000207c  mov     rcx, [rcx]
0x14000207f  mov     ecx, [rcx]
0x140002081  call    _XcptFilter_0
0x140002086  nop
0x140002087  add     rsp, 20h
0x14000208b  pop     rbp
0x14000208c  retn
```
