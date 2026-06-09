# __wmainCRTStartup

- ea: `0x140001410`
- end: `0x14000166f`
- name: `__wmainCRTStartup`
- size: `607`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001680`

## callees

- `0x140001410`
- `0x14000172e`
- `0x1400017e0`
- `0x140001850`
- `0x1400019b7`
- `0x1400019cf`
- `0x140002010`
- `0x140006f50`

## import_xrefs

- `msvcrt!_wcmdln` at `0x140001574`
- `msvcrt!_cexit` at `0x140001601`
- `msvcrt!_cexit` at `0x140001652`
- `msvcrt!_cexit` at `0x140001601`
- `msvcrt!_cexit` at `0x140001652`
- `msvcrt!_exit` at `0x140001642`
- `msvcrt!_exit` at `0x140001642`
- `msvcrt!exit` at `0x1400015f2`
- `msvcrt!exit` at `0x1400015f2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000147a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000147a`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001442`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001442`

## pseudocode

```c
int _wmainCRTStartup()
{
  BOOL v0; // esi
  PVOID StackBase; // rbx
  int v2; // r14d
  signed __int64 v3; // rax
  __int64 *v4; // rdi
  int v5; // eax
  int result; // eax
  wchar_t *v7; // rcx
  WCHAR v8; // ax
  int wShowWindow; // r9d
  _STARTUPINFOW StartupInfo; // [rsp+40h] [rbp-A8h] BYREF

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
    v7 = _wcmdln;
    if ( !_wcmdln )
      return 255;
    while ( 1 )
    {
      v8 = *v7;
      if ( *v7 <= 0x20u && (!v8 || !v0) )
        break;
      if ( v8 == 34 )
        v0 = !v0;
      ++v7;
    }
    while ( (unsigned __int16)(v8 - 1) <= 0x1Fu )
      v8 = *++v7;
    wShowWindow = 10;
    if ( (StartupInfo.dwFlags & 1) != 0 )
      wShowWindow = StartupInfo.wShowWindow;
    result = wWinMain(&_ImageBase, 0, v7, wShowWindow);
    dword_14000E320 = result;
    if ( !dword_14000E340 )
      exit(result);
    if ( !dword_14000E324 )
    {
      _cexit();
      return dword_14000E320;
    }
    return result;
  }
  if ( _native_startup_state )
  {
    dword_14000E324 = 1;
    goto LABEL_18;
  }
  _native_startup_state = 1;
  v4 = &_xi_a;
  v5 = 0;
  while ( v4 < &_xi_z )
  {
    if ( v5 )
      return 255;
    if ( *v4 )
      v5 = _guard_dispatch_icall_fptr();
    ++v4;
  }
  if ( !v5 )
    goto LABEL_18;
  return 255;
}

```

## disassembly

```asm
0x140001410  push    rbx
0x140001412  push    rsi
0x140001413  push    rdi
0x140001414  push    r12
0x140001416  push    r14
0x140001418  push    r15
0x14000141a  sub     rsp, 0B8h
0x140001421  xor     eax, eax
0x140001423  mov     dword ptr [rsp+0E8h+StartupInfo+4], eax
0x140001427  xor     edx, edx; Val
0x140001429  lea     r8d, [rax+64h]; Size
0x14000142d  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x140001432  call    memset_0
0x140001437  xor     r15d, r15d
0x14000143a  mov     esi, r15d
0x14000143d  lea     rcx, [rsp+0E8h+StartupInfo]; lpStartupInfo
0x140001442  call    cs:__imp_GetStartupInfoW
0x140001448  nop
0x140001449  mov     rax, gs:30h
0x140001452  mov     rbx, [rax+8]
0x140001456  mov     r14d, r15d
0x140001459  xor     eax, eax
0x14000145b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001464  jz      short loc_140001482
0x140001466  cmp     rax, rbx
0x140001469  jnz     short loc_140001475
0x14000146b  mov     ebx, 1
0x140001470  mov     r14d, ebx
0x140001473  jmp     short loc_140001487
0x140001475  mov     ecx, 3E8h; dwMilliseconds
0x14000147a  call    cs:__imp_Sleep
0x140001480  jmp     short loc_140001459
0x140001482  mov     ebx, 1
0x140001487  mov     eax, cs:__native_startup_state
0x14000148d  cmp     eax, ebx
0x14000148f  jnz     short loc_14000149F
0x140001491  mov     edi, 1Fh
0x140001496  mov     ecx, edi
0x140001498  call    _amsg_exit_0
0x14000149d  jmp     short loc_14000150B
0x14000149f  mov     eax, cs:__native_startup_state
0x1400014a5  test    eax, eax
0x1400014a7  jnz     short loc_140001500
0x1400014a9  mov     cs:__native_startup_state, ebx
0x1400014af  lea     r12, __xi_z
0x1400014b6  lea     rdi, __xi_a
0x1400014bd  mov     [rsp+0E8h+var_B0], rdi
0x1400014c2  mov     eax, r15d
0x1400014c5  mov     [rsp+0E8h+var_C8], eax
0x1400014c9  cmp     rdi, r12
0x1400014cc  jnb     short loc_1400014F2
0x1400014ce  test    eax, eax
0x1400014d0  jnz     short loc_1400014F6
0x1400014d2  cmp     [rdi], r15
0x1400014d5  jz      short loc_1400014E7
0x1400014d7  mov     rax, [rdi]
0x1400014da  mov     rcx, cs:__guard_dispatch_icall_fptr
0x1400014e1  call    rcx ; _guard_dispatch_icall_nop
0x1400014e3  mov     [rsp+0E8h+var_C8], eax
0x1400014e7  add     rdi, 8
0x1400014eb  mov     [rsp+0E8h+var_B0], rdi
0x1400014f0  jmp     short loc_1400014C9
0x1400014f2  test    eax, eax
0x1400014f4  jz      short loc_140001506
0x1400014f6  mov     eax, 0FFh
0x1400014fb  jmp     loc_14000165E
0x140001500  mov     cs:dword_14000E324, ebx
0x140001506  mov     edi, 1Fh
0x14000150b  mov     eax, cs:__native_startup_state
0x140001511  cmp     eax, ebx
0x140001513  jnz     short loc_140001532
0x140001515  lea     rdx, __xc_z; Last
0x14000151c  lea     rcx, __xc_a; First
0x140001523  call    _initterm_0
0x140001528  mov     cs:__native_startup_state, 2
0x140001532  test    r14d, r14d
0x140001535  jnz     short loc_140001541
0x140001537  mov     rax, r15
0x14000153a  xchg    rax, cs:__native_startup_lock
0x140001541  cmp     cs:__dyn_tls_init_callback, r15
0x140001548  jz      short loc_140001574
0x14000154a  lea     rcx, __dyn_tls_init_callback
0x140001551  call    _IsNonwritableInCurrentImage
0x140001556  test    eax, eax
0x140001558  jz      short loc_140001574
0x14000155a  xor     r8d, r8d
0x14000155d  lea     edx, [r8+2]
0x140001561  xor     ecx, ecx
0x140001563  mov     rax, cs:__dyn_tls_init_callback
0x14000156a  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001571  call    r9 ; _guard_dispatch_icall_nop
0x140001574  mov     rax, cs:__imp__wcmdln
0x14000157b  mov     rcx, [rax]
0x14000157e  test    rcx, rcx
0x140001581  jnz     short loc_14000158D
0x140001583  mov     eax, 0FFh
0x140001588  jmp     loc_14000165E
0x14000158d  mov     [rsp+0E8h+var_C0], rcx
0x140001592  movzx   eax, word ptr [rcx]
0x140001595  cmp     ax, 20h ; ' '
0x140001599  ja      short loc_14000160F
0x14000159b  test    ax, ax
0x14000159e  jz      short loc_1400015A4
0x1400015a0  test    esi, esi
0x1400015a2  jnz     short loc_14000160F
0x1400015a4  sub     ax, bx
0x1400015a7  cmp     ax, di
0x1400015aa  ja      short loc_1400015BA
0x1400015ac  add     rcx, 2
0x1400015b0  mov     [rsp+0E8h+var_C0], rcx
0x1400015b5  movzx   eax, word ptr [rcx]
0x1400015b8  jmp     short loc_1400015A4
0x1400015ba  test    byte ptr [rsp+0E8h+StartupInfo.dwFlags], bl
0x1400015be  movzx   eax, [rsp+0E8h+StartupInfo.wShowWindow]
0x1400015c6  mov     r9d, 0Ah
0x1400015cc  cmovnz  r9d, eax; nShowCmd
0x1400015d0  mov     r8, rcx; lpCmdLine
0x1400015d3  xor     edx, edx; hPrevInstance
0x1400015d5  lea     rcx, __ImageBase; hInstance
0x1400015dc  call    wWinMain
0x1400015e1  mov     cs:dword_14000E320, eax
0x1400015e7  cmp     cs:dword_14000E340, r15d
0x1400015ee  jnz     short loc_1400015F8
0x1400015f0  mov     ecx, eax; Code
0x1400015f2  call    cs:__imp_exit
0x1400015f8  cmp     cs:dword_14000E324, r15d
0x1400015ff  jnz     short loc_14000160D
0x140001601  call    cs:__imp__cexit
0x140001607  mov     eax, cs:dword_14000E320
0x14000160d  jmp     short loc_14000165E
0x14000160f  cmp     ax, 22h ; '"'
0x140001613  jnz     short loc_140001623
0x140001615  mov     eax, r15d
0x140001618  test    esi, esi
0x14000161a  setz    al
0x14000161d  mov     esi, eax
0x14000161f  mov     [rsp+0E8h+var_B8], eax
0x140001623  add     rcx, 2
0x140001627  mov     [rsp+0E8h+var_C0], rcx
0x14000162c  jmp     loc_140001592
0x140001631  mov     cs:dword_14000E320, eax
0x140001637  cmp     cs:dword_14000E340, 0
0x14000163e  jnz     short loc_140001649
0x140001640  mov     ecx, eax; Code
0x140001642  call    cs:__imp__exit
0x140001649  cmp     cs:dword_14000E324, 0
0x140001650  jnz     short loc_14000165E
0x140001652  call    cs:__imp__cexit
0x140001658  mov     eax, cs:dword_14000E320
0x14000165e  add     rsp, 0B8h
0x140001665  pop     r15
0x140001667  pop     r14
0x140001669  pop     r12
0x14000166b  pop     rdi
0x14000166c  pop     rsi
0x14000166d  pop     rbx
0x14000166e  retn
0x140007020  push    rbp
0x140007022  sub     rsp, 20h
0x140007026  mov     rbp, rdx
0x140007029  mov     rdx, rcx
0x14000702c  mov     rcx, [rcx]
0x14000702f  mov     ecx, [rcx]
0x140007031  call    _XcptFilter_0
0x140007036  nop
0x140007037  add     rsp, 20h
0x14000703b  pop     rbp
0x14000703c  retn
```
