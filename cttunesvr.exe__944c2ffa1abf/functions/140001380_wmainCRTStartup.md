# __wmainCRTStartup

- ea: `0x140001380`
- end: `0x1400015df`
- name: `__wmainCRTStartup`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400015f0`

## callees

- `0x140001380`
- `0x140001afe`
- `0x140001bb0`
- `0x140001c10`
- `0x140001d77`
- `0x140001d83`
- `0x1400063fc`
- `0x140006630`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400013ea`
- `KERNEL32!Sleep` at `0x1400013ea`
- `KERNEL32!GetStartupInfoW` at `0x1400013b2`
- `KERNEL32!GetStartupInfoW` at `0x1400013b2`
- `msvcrt!_cexit` at `0x140001571`
- `msvcrt!_cexit` at `0x1400015c2`
- `msvcrt!_cexit` at `0x140001571`
- `msvcrt!_cexit` at `0x1400015c2`
- `msvcrt!_exit` at `0x1400015b2`
- `msvcrt!_exit` at `0x1400015b2`
- `msvcrt!exit` at `0x140001562`
- `msvcrt!exit` at `0x140001562`
- `msvcrt!_wcmdln` at `0x1400014e4`

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
    result = wWinMain((HINSTANCE)0x140000000LL, 0, v7, wShowWindow);
    dword_14000B220 = result;
    if ( !dword_14000B240 )
      exit(result);
    if ( !dword_14000B224 )
    {
      _cexit();
      return dword_14000B220;
    }
    return result;
  }
  if ( _native_startup_state )
  {
    dword_14000B224 = 1;
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
0x140001380  push    rbx
0x140001382  push    rsi
0x140001383  push    rdi
0x140001384  push    r12
0x140001386  push    r14
0x140001388  push    r15
0x14000138a  sub     rsp, 0B8h
0x140001391  xor     eax, eax
0x140001393  mov     dword ptr [rsp+0E8h+StartupInfo+4], eax
0x140001397  xor     edx, edx; Val
0x140001399  lea     r8d, [rax+64h]; Size
0x14000139d  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x1400013a2  call    memset_0
0x1400013a7  xor     r15d, r15d
0x1400013aa  mov     esi, r15d
0x1400013ad  lea     rcx, [rsp+0E8h+StartupInfo]; lpStartupInfo
0x1400013b2  call    cs:__imp_GetStartupInfoW
0x1400013b8  nop
0x1400013b9  mov     rax, gs:30h
0x1400013c2  mov     rbx, [rax+8]
0x1400013c6  mov     r14d, r15d
0x1400013c9  xor     eax, eax
0x1400013cb  lock cmpxchg cs:__native_startup_lock, rbx
0x1400013d4  jz      short loc_1400013F2
0x1400013d6  cmp     rax, rbx
0x1400013d9  jnz     short loc_1400013E5
0x1400013db  mov     ebx, 1
0x1400013e0  mov     r14d, ebx
0x1400013e3  jmp     short loc_1400013F7
0x1400013e5  mov     ecx, 3E8h; dwMilliseconds
0x1400013ea  call    cs:__imp_Sleep
0x1400013f0  jmp     short loc_1400013C9
0x1400013f2  mov     ebx, 1
0x1400013f7  mov     eax, cs:__native_startup_state
0x1400013fd  cmp     eax, ebx
0x1400013ff  jnz     short loc_14000140F
0x140001401  mov     edi, 1Fh
0x140001406  mov     ecx, edi
0x140001408  call    _amsg_exit_0
0x14000140d  jmp     short loc_14000147B
0x14000140f  mov     eax, cs:__native_startup_state
0x140001415  test    eax, eax
0x140001417  jnz     short loc_140001470
0x140001419  mov     cs:__native_startup_state, ebx
0x14000141f  lea     r12, __xi_z
0x140001426  lea     rdi, __xi_a
0x14000142d  mov     [rsp+0E8h+var_B0], rdi
0x140001432  mov     eax, r15d
0x140001435  mov     [rsp+0E8h+var_C8], eax
0x140001439  cmp     rdi, r12
0x14000143c  jnb     short loc_140001462
0x14000143e  test    eax, eax
0x140001440  jnz     short loc_140001466
0x140001442  cmp     [rdi], r15
0x140001445  jz      short loc_140001457
0x140001447  mov     rax, [rdi]
0x14000144a  mov     rcx, cs:__guard_dispatch_icall_fptr
0x140001451  call    rcx ; _guard_dispatch_icall_nop
0x140001453  mov     [rsp+0E8h+var_C8], eax
0x140001457  add     rdi, 8
0x14000145b  mov     [rsp+0E8h+var_B0], rdi
0x140001460  jmp     short loc_140001439
0x140001462  test    eax, eax
0x140001464  jz      short loc_140001476
0x140001466  mov     eax, 0FFh
0x14000146b  jmp     loc_1400015CE
0x140001470  mov     cs:dword_14000B224, ebx
0x140001476  mov     edi, 1Fh
0x14000147b  mov     eax, cs:__native_startup_state
0x140001481  cmp     eax, ebx
0x140001483  jnz     short loc_1400014A2
0x140001485  lea     rdx, __xc_z; Last
0x14000148c  lea     rcx, __xc_a; First
0x140001493  call    _initterm_0
0x140001498  mov     cs:__native_startup_state, 2
0x1400014a2  test    r14d, r14d
0x1400014a5  jnz     short loc_1400014B1
0x1400014a7  mov     rax, r15
0x1400014aa  xchg    rax, cs:__native_startup_lock
0x1400014b1  cmp     cs:__dyn_tls_init_callback, r15
0x1400014b8  jz      short loc_1400014E4
0x1400014ba  lea     rcx, __dyn_tls_init_callback
0x1400014c1  call    _IsNonwritableInCurrentImage
0x1400014c6  test    eax, eax
0x1400014c8  jz      short loc_1400014E4
0x1400014ca  xor     r8d, r8d
0x1400014cd  lea     edx, [r8+2]
0x1400014d1  xor     ecx, ecx
0x1400014d3  mov     rax, cs:__dyn_tls_init_callback
0x1400014da  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400014e1  call    r9 ; _guard_dispatch_icall_nop
0x1400014e4  mov     rax, cs:__imp__wcmdln
0x1400014eb  mov     rcx, [rax]
0x1400014ee  test    rcx, rcx
0x1400014f1  jnz     short loc_1400014FD
0x1400014f3  mov     eax, 0FFh
0x1400014f8  jmp     loc_1400015CE
0x1400014fd  mov     [rsp+0E8h+var_C0], rcx
0x140001502  movzx   eax, word ptr [rcx]
0x140001505  cmp     ax, 20h ; ' '
0x140001509  ja      short loc_14000157F
0x14000150b  test    ax, ax
0x14000150e  jz      short loc_140001514
0x140001510  test    esi, esi
0x140001512  jnz     short loc_14000157F
0x140001514  sub     ax, bx
0x140001517  cmp     ax, di
0x14000151a  ja      short loc_14000152A
0x14000151c  add     rcx, 2
0x140001520  mov     [rsp+0E8h+var_C0], rcx
0x140001525  movzx   eax, word ptr [rcx]
0x140001528  jmp     short loc_140001514
0x14000152a  test    byte ptr [rsp+0E8h+StartupInfo.dwFlags], bl
0x14000152e  movzx   eax, [rsp+0E8h+StartupInfo.wShowWindow]
0x140001536  mov     r9d, 0Ah
0x14000153c  cmovnz  r9d, eax; nShowCmd
0x140001540  mov     r8, rcx; lpCmdLine
0x140001543  xor     edx, edx; hPrevInstance
0x140001545  lea     rcx, cs:140000000h; hInstance
0x14000154c  call    wWinMain
0x140001551  mov     cs:dword_14000B220, eax
0x140001557  cmp     cs:dword_14000B240, r15d
0x14000155e  jnz     short loc_140001568
0x140001560  mov     ecx, eax; Code
0x140001562  call    cs:__imp_exit
0x140001568  cmp     cs:dword_14000B224, r15d
0x14000156f  jnz     short loc_14000157D
0x140001571  call    cs:__imp__cexit
0x140001577  mov     eax, cs:dword_14000B220
0x14000157d  jmp     short loc_1400015CE
0x14000157f  cmp     ax, 22h ; '"'
0x140001583  jnz     short loc_140001593
0x140001585  mov     eax, r15d
0x140001588  test    esi, esi
0x14000158a  setz    al
0x14000158d  mov     esi, eax
0x14000158f  mov     [rsp+0E8h+var_B8], eax
0x140001593  add     rcx, 2
0x140001597  mov     [rsp+0E8h+var_C0], rcx
0x14000159c  jmp     loc_140001502
0x1400015a1  mov     cs:dword_14000B220, eax
0x1400015a7  cmp     cs:dword_14000B240, 0
0x1400015ae  jnz     short loc_1400015B9
0x1400015b0  mov     ecx, eax; Code
0x1400015b2  call    cs:__imp__exit
0x1400015b9  cmp     cs:dword_14000B224, 0
0x1400015c0  jnz     short loc_1400015CE
0x1400015c2  call    cs:__imp__cexit
0x1400015c8  mov     eax, cs:dword_14000B220
0x1400015ce  add     rsp, 0B8h
0x1400015d5  pop     r15
0x1400015d7  pop     r14
0x1400015d9  pop     r12
0x1400015db  pop     rdi
0x1400015dc  pop     rsi
0x1400015dd  pop     rbx
0x1400015de  retn
0x140006700  push    rbp
0x140006702  sub     rsp, 20h
0x140006706  mov     rbp, rdx
0x140006709  mov     rdx, rcx
0x14000670c  mov     rcx, [rcx]
0x14000670f  mov     ecx, [rcx]
0x140006711  call    _XcptFilter_0
0x140006716  nop
0x140006717  add     rsp, 20h
0x14000671b  pop     rbp
0x14000671c  retn
```
