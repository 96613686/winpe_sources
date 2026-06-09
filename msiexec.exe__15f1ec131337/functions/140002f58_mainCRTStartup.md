# __mainCRTStartup

- ea: `0x140002f58`
- end: `0x14000319a`
- name: `__mainCRTStartup`
- size: `578`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002f40`

## callees

- `0x1400010d0`
- `0x140002f58`
- `0x1400035ee`
- `0x1400036a0`
- `0x140003710`
- `0x140003877`
- `0x140003883`
- `0x140009860`

## import_xrefs

- `KERNEL32!Sleep` at `0x140002fc9`
- `KERNEL32!Sleep` at `0x140002fc9`
- `KERNEL32!GetStartupInfoW` at `0x140002f82`
- `KERNEL32!GetStartupInfoW` at `0x140002f82`
- `msvcrt!_cexit` at `0x140003121`
- `msvcrt!_cexit` at `0x140003181`
- `msvcrt!_cexit` at `0x140003121`
- `msvcrt!_cexit` at `0x140003181`
- `msvcrt!_ismbblead` at `0x140003141`
- `msvcrt!_ismbblead` at `0x140003141`
- `msvcrt!_acmdln` at `0x1400030a7`
- `msvcrt!_exit` at `0x140003171`
- `msvcrt!_exit` at `0x140003171`
- `msvcrt!exit` at `0x140003112`
- `msvcrt!exit` at `0x140003112`

## pseudocode

```c
__int64 _mainCRTStartup()
{
  BOOL v0; // edi
  PVOID StackBase; // rbx
  int v2; // esi
  signed __int64 v3; // rax
  int v4; // eax
  __int64 *i; // rbx
  char *j; // rbx
  unsigned int v8; // ecx
  int wShowWindow; // r9d
  _STARTUPINFOW StartupInfo; // [rsp+40h] [rbp-98h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  v0 = 0;
  GetStartupInfoW(&StartupInfo);
  StackBase = NtCurrentTeb()->NtTib.StackBase;
  v2 = 0;
  while ( 1 )
  {
    v3 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
    if ( !v3 )
      break;
    if ( (PVOID)v3 == StackBase )
    {
      v2 = 1;
      break;
    }
    Sleep(0x3E8u);
  }
  if ( _native_startup_state == 1 )
  {
    amsg_exit_0(31);
    goto LABEL_18;
  }
  v4 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_1400101C4 = 1;
    goto LABEL_18;
  }
  _native_startup_state = 1;
  for ( i = &_xi_a; i < &_xi_z; ++i )
  {
    if ( v4 )
      return 255;
    if ( *i )
      v4 = _guard_dispatch_icall_fptr();
  }
  if ( !v4 )
  {
LABEL_18:
    if ( _native_startup_state == 1 )
    {
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v2 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
    for ( j = _acmdln; ; ++j )
    {
      v8 = (unsigned __int8)*j;
      if ( (unsigned __int8)v8 <= 0x20u && (!(_BYTE)v8 || !v0) )
        break;
      if ( (_BYTE)v8 == 34 )
        v0 = !v0;
      if ( _ismbblead(v8) )
        ++j;
    }
    while ( (unsigned __int8)(v8 - 1) <= 0x1Fu )
      LOBYTE(v8) = *++j;
    wShowWindow = 10;
    if ( (StartupInfo.dwFlags & 1) != 0 )
      wShowWindow = StartupInfo.wShowWindow;
    WinMain(&_ImageBase, 0, j, wShowWindow);
  }
  return 255;
}

```

## disassembly

```asm
0x140002f58  push    rbx
0x140002f5a  push    rsi
0x140002f5b  push    rdi
0x140002f5c  push    r15
0x140002f5e  sub     rsp, 0B8h
0x140002f65  xor     eax, eax
0x140002f67  mov     dword ptr [rsp+0D8h+StartupInfo+4], eax
0x140002f6b  xor     edx, edx; Val
0x140002f6d  lea     r8d, [rax+64h]; Size
0x140002f71  lea     rcx, [rsp+0D8h+StartupInfo]; void *
0x140002f76  call    memset_0
0x140002f7b  xor     edi, edi
0x140002f7d  lea     rcx, [rsp+0D8h+StartupInfo]; lpStartupInfo
0x140002f82  call    cs:__imp_GetStartupInfoW
0x140002f88  nop
0x140002f89  mov     rax, gs:30h
0x140002f92  mov     rbx, [rax+8]
0x140002f96  xor     esi, esi
0x140002f98  xor     eax, eax
0x140002f9a  lock cmpxchg cs:__native_startup_lock, rbx
0x140002fa3  jz      short loc_140002FAF
0x140002fa5  cmp     rax, rbx
0x140002fa8  jnz     short loc_140002FC4
0x140002faa  mov     esi, 1
0x140002faf  mov     eax, cs:__native_startup_state
0x140002fb5  cmp     eax, 1
0x140002fb8  jnz     short loc_140002FD1
0x140002fba  lea     ecx, [rax+1Eh]
0x140002fbd  call    _amsg_exit_0
0x140002fc2  jmp     short loc_14000303E
0x140002fc4  mov     ecx, 3E8h; dwMilliseconds
0x140002fc9  call    cs:__imp_Sleep
0x140002fcf  jmp     short loc_140002F98
0x140002fd1  mov     eax, cs:__native_startup_state
0x140002fd7  test    eax, eax
0x140002fd9  jnz     short loc_140003034
0x140002fdb  mov     cs:__native_startup_state, 1
0x140002fe5  lea     r15, __xi_z
0x140002fec  lea     rbx, __xi_a
0x140002ff3  mov     [rsp+0D8h+var_A0], rbx
0x140002ff8  mov     [rsp+0D8h+var_B8], eax
0x140002ffc  cmp     rbx, r15
0x140002fff  jnb     short loc_140003026
0x140003001  test    eax, eax
0x140003003  jnz     short loc_14000302A
0x140003005  cmp     qword ptr [rbx], 0
0x140003009  jz      short loc_14000301B
0x14000300b  mov     rax, [rbx]
0x14000300e  mov     rcx, cs:__guard_dispatch_icall_fptr
0x140003015  call    rcx ; _guard_dispatch_icall_nop
0x140003017  mov     [rsp+0D8h+var_B8], eax
0x14000301b  add     rbx, 8
0x14000301f  mov     [rsp+0D8h+var_A0], rbx
0x140003024  jmp     short loc_140002FFC
0x140003026  test    eax, eax
0x140003028  jz      short loc_14000303E
0x14000302a  mov     eax, 0FFh
0x14000302f  jmp     loc_14000318D
0x140003034  mov     cs:dword_1400101C4, 1
0x14000303e  mov     eax, cs:__native_startup_state
0x140003044  cmp     eax, 1
0x140003047  jnz     short loc_140003066
0x140003049  lea     rdx, __xc_z; Last
0x140003050  lea     rcx, __xc_a; First
0x140003057  call    _initterm_0
0x14000305c  mov     cs:__native_startup_state, 2
0x140003066  test    esi, esi
0x140003068  jnz     short loc_140003073
0x14000306a  xor     eax, eax
0x14000306c  xchg    rax, cs:__native_startup_lock
0x140003073  cmp     cs:__dyn_tls_init_callback, 0
0x14000307b  jz      short loc_1400030A7
0x14000307d  lea     rcx, __dyn_tls_init_callback
0x140003084  call    _IsNonwritableInCurrentImage
0x140003089  test    eax, eax
0x14000308b  jz      short loc_1400030A7
0x14000308d  xor     r8d, r8d
0x140003090  lea     edx, [r8+2]
0x140003094  xor     ecx, ecx
0x140003096  mov     rax, cs:__dyn_tls_init_callback
0x14000309d  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400030a4  call    r9 ; _guard_dispatch_icall_nop
0x1400030a7  mov     rax, cs:__imp__acmdln
0x1400030ae  mov     rbx, [rax]
0x1400030b1  mov     [rsp+0D8h+var_B0], rbx
0x1400030b6  movzx   ecx, byte ptr [rbx]; Ch
0x1400030b9  cmp     cl, 20h ; ' '
0x1400030bc  ja      short loc_14000312F
0x1400030be  test    cl, cl
0x1400030c0  jz      short loc_1400030C6
0x1400030c2  test    edi, edi
0x1400030c4  jnz     short loc_14000312F
0x1400030c6  dec     cl
0x1400030c8  cmp     cl, 1Fh
0x1400030cb  ja      short loc_1400030D9
0x1400030cd  inc     rbx
0x1400030d0  mov     [rsp+0D8h+var_B0], rbx
0x1400030d5  mov     cl, [rbx]
0x1400030d7  jmp     short loc_1400030C6
0x1400030d9  test    byte ptr [rsp+0D8h+StartupInfo.dwFlags], 1
0x1400030de  movzx   eax, [rsp+0D8h+StartupInfo.wShowWindow]
0x1400030e6  mov     r9d, 0Ah
0x1400030ec  cmovnz  r9d, eax; nShowCmd
0x1400030f0  mov     r8, rbx; lpCmdLine
0x1400030f3  xor     edx, edx; hPrevInstance
0x1400030f5  lea     rcx, __ImageBase; hInstance
0x1400030fc  call    WinMain
0x140003101  mov     cs:dword_1400101C0, eax
0x140003107  cmp     cs:dword_1400101E0, 0
0x14000310e  jnz     short loc_140003118
0x140003110  mov     ecx, eax; Code
0x140003112  call    cs:__imp_exit
0x140003118  cmp     cs:dword_1400101C4, 0
0x14000311f  jnz     short loc_14000312D
0x140003121  call    cs:__imp__cexit
0x140003127  mov     eax, cs:dword_1400101C0
0x14000312d  jmp     short loc_14000318D
0x14000312f  cmp     cl, 22h ; '"'
0x140003132  jnz     short loc_140003141
0x140003134  xor     eax, eax
0x140003136  test    edi, edi
0x140003138  setz    al
0x14000313b  mov     edi, eax
0x14000313d  mov     [rsp+0D8h+var_A8], eax
0x140003141  call    cs:__imp__ismbblead
0x140003147  test    eax, eax
0x140003149  jz      short loc_140003153
0x14000314b  inc     rbx
0x14000314e  mov     [rsp+0D8h+var_B0], rbx
0x140003153  inc     rbx
0x140003156  mov     [rsp+0D8h+var_B0], rbx
0x14000315b  jmp     loc_1400030B6
0x140003160  mov     cs:dword_1400101C0, eax
0x140003166  cmp     cs:dword_1400101E0, 0
0x14000316d  jnz     short loc_140003178
0x14000316f  mov     ecx, eax; Code
0x140003171  call    cs:__imp__exit
0x140003178  cmp     cs:dword_1400101C4, 0
0x14000317f  jnz     short loc_14000318D
0x140003181  call    cs:__imp__cexit
0x140003187  mov     eax, cs:dword_1400101C0
0x14000318d  add     rsp, 0B8h
0x140003194  pop     r15
0x140003196  pop     rdi
0x140003197  pop     rsi
0x140003198  pop     rbx
0x140003199  retn
0x14000999f  push    rbp
0x1400099a1  sub     rsp, 20h
0x1400099a5  mov     rbp, rdx
0x1400099a8  mov     rdx, rcx
0x1400099ab  mov     rcx, [rcx]
0x1400099ae  mov     ecx, [rcx]
0x1400099b0  call    _XcptFilter_0
0x1400099b5  nop
0x1400099b6  add     rsp, 20h
0x1400099ba  pop     rbp
0x1400099bb  retn
```
