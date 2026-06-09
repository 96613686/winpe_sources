# __wmainCRTStartup

- ea: `0x140001140`
- end: `0x14000139f`
- name: `__wmainCRTStartup`
- size: `607`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400013b0`

## callees

- `0x140001140`
- `0x14000143e`
- `0x1400014f0`
- `0x140001560`
- `0x1400016c7`
- `0x1400016df`
- `0x140001984`
- `0x140001b70`

## import_xrefs

- `KERNEL32!GetStartupInfoW` at `0x140001172`
- `KERNEL32!GetStartupInfoW` at `0x140001172`
- `KERNEL32!Sleep` at `0x1400011aa`
- `KERNEL32!Sleep` at `0x1400011aa`
- `msvcrt!_wcmdln` at `0x1400012a4`
- `msvcrt!_cexit` at `0x140001331`
- `msvcrt!_cexit` at `0x140001382`
- `msvcrt!_cexit` at `0x140001331`
- `msvcrt!_cexit` at `0x140001382`
- `msvcrt!_exit` at `0x140001372`
- `msvcrt!_exit` at `0x140001372`
- `msvcrt!exit` at `0x140001322`
- `msvcrt!exit` at `0x140001322`

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
    dword_1400040A0 = result;
    if ( !dword_1400040C0 )
      exit(result);
    if ( !dword_1400040A4 )
    {
      _cexit();
      return dword_1400040A0;
    }
    return result;
  }
  if ( _native_startup_state )
  {
    dword_1400040A4 = 1;
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
0x140001140  push    rbx
0x140001142  push    rsi
0x140001143  push    rdi
0x140001144  push    r12
0x140001146  push    r14
0x140001148  push    r15
0x14000114a  sub     rsp, 0B8h
0x140001151  xor     eax, eax
0x140001153  mov     dword ptr [rsp+0E8h+StartupInfo+4], eax
0x140001157  xor     edx, edx; Val
0x140001159  lea     r8d, [rax+64h]; Size
0x14000115d  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x140001162  call    memset_0
0x140001167  xor     r15d, r15d
0x14000116a  mov     esi, r15d
0x14000116d  lea     rcx, [rsp+0E8h+StartupInfo]; lpStartupInfo
0x140001172  call    cs:__imp_GetStartupInfoW
0x140001178  nop
0x140001179  mov     rax, gs:30h
0x140001182  mov     rbx, [rax+8]
0x140001186  mov     r14d, r15d
0x140001189  xor     eax, eax
0x14000118b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001194  jz      short loc_1400011B2
0x140001196  cmp     rax, rbx
0x140001199  jnz     short loc_1400011A5
0x14000119b  mov     ebx, 1
0x1400011a0  mov     r14d, ebx
0x1400011a3  jmp     short loc_1400011B7
0x1400011a5  mov     ecx, 3E8h; dwMilliseconds
0x1400011aa  call    cs:__imp_Sleep
0x1400011b0  jmp     short loc_140001189
0x1400011b2  mov     ebx, 1
0x1400011b7  mov     eax, cs:__native_startup_state
0x1400011bd  cmp     eax, ebx
0x1400011bf  jnz     short loc_1400011CF
0x1400011c1  mov     edi, 1Fh
0x1400011c6  mov     ecx, edi
0x1400011c8  call    _amsg_exit_0
0x1400011cd  jmp     short loc_14000123B
0x1400011cf  mov     eax, cs:__native_startup_state
0x1400011d5  test    eax, eax
0x1400011d7  jnz     short loc_140001230
0x1400011d9  mov     cs:__native_startup_state, ebx
0x1400011df  lea     r12, __xi_z
0x1400011e6  lea     rdi, __xi_a
0x1400011ed  mov     [rsp+0E8h+var_B0], rdi
0x1400011f2  mov     eax, r15d
0x1400011f5  mov     [rsp+0E8h+var_C8], eax
0x1400011f9  cmp     rdi, r12
0x1400011fc  jnb     short loc_140001222
0x1400011fe  test    eax, eax
0x140001200  jnz     short loc_140001226
0x140001202  cmp     [rdi], r15
0x140001205  jz      short loc_140001217
0x140001207  mov     rax, [rdi]
0x14000120a  mov     rcx, cs:__guard_dispatch_icall_fptr
0x140001211  call    rcx ; _guard_dispatch_icall_nop
0x140001213  mov     [rsp+0E8h+var_C8], eax
0x140001217  add     rdi, 8
0x14000121b  mov     [rsp+0E8h+var_B0], rdi
0x140001220  jmp     short loc_1400011F9
0x140001222  test    eax, eax
0x140001224  jz      short loc_140001236
0x140001226  mov     eax, 0FFh
0x14000122b  jmp     loc_14000138E
0x140001230  mov     cs:dword_1400040A4, ebx
0x140001236  mov     edi, 1Fh
0x14000123b  mov     eax, cs:__native_startup_state
0x140001241  cmp     eax, ebx
0x140001243  jnz     short loc_140001262
0x140001245  lea     rdx, __xc_z; Last
0x14000124c  lea     rcx, __xc_a; First
0x140001253  call    _initterm_0
0x140001258  mov     cs:__native_startup_state, 2
0x140001262  test    r14d, r14d
0x140001265  jnz     short loc_140001271
0x140001267  mov     rax, r15
0x14000126a  xchg    rax, cs:__native_startup_lock
0x140001271  cmp     cs:__dyn_tls_init_callback, r15
0x140001278  jz      short loc_1400012A4
0x14000127a  lea     rcx, __dyn_tls_init_callback
0x140001281  call    _IsNonwritableInCurrentImage
0x140001286  test    eax, eax
0x140001288  jz      short loc_1400012A4
0x14000128a  xor     r8d, r8d
0x14000128d  lea     edx, [r8+2]
0x140001291  xor     ecx, ecx
0x140001293  mov     rax, cs:__dyn_tls_init_callback
0x14000129a  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400012a1  call    r9 ; _guard_dispatch_icall_nop
0x1400012a4  mov     rax, cs:__imp__wcmdln
0x1400012ab  mov     rcx, [rax]
0x1400012ae  test    rcx, rcx
0x1400012b1  jnz     short loc_1400012BD
0x1400012b3  mov     eax, 0FFh
0x1400012b8  jmp     loc_14000138E
0x1400012bd  mov     [rsp+0E8h+var_C0], rcx
0x1400012c2  movzx   eax, word ptr [rcx]
0x1400012c5  cmp     ax, 20h ; ' '
0x1400012c9  ja      short loc_14000133F
0x1400012cb  test    ax, ax
0x1400012ce  jz      short loc_1400012D4
0x1400012d0  test    esi, esi
0x1400012d2  jnz     short loc_14000133F
0x1400012d4  sub     ax, bx
0x1400012d7  cmp     ax, di
0x1400012da  ja      short loc_1400012EA
0x1400012dc  add     rcx, 2
0x1400012e0  mov     [rsp+0E8h+var_C0], rcx
0x1400012e5  movzx   eax, word ptr [rcx]
0x1400012e8  jmp     short loc_1400012D4
0x1400012ea  test    byte ptr [rsp+0E8h+StartupInfo.dwFlags], bl
0x1400012ee  movzx   eax, [rsp+0E8h+StartupInfo.wShowWindow]
0x1400012f6  mov     r9d, 0Ah
0x1400012fc  cmovnz  r9d, eax; nShowCmd
0x140001300  mov     r8, rcx; lpCmdLine
0x140001303  xor     edx, edx; hPrevInstance
0x140001305  lea     rcx, cs:140000000h; hInstance
0x14000130c  call    wWinMain
0x140001311  mov     cs:dword_1400040A0, eax
0x140001317  cmp     cs:dword_1400040C0, r15d
0x14000131e  jnz     short loc_140001328
0x140001320  mov     ecx, eax; Code
0x140001322  call    cs:__imp_exit
0x140001328  cmp     cs:dword_1400040A4, r15d
0x14000132f  jnz     short loc_14000133D
0x140001331  call    cs:__imp__cexit
0x140001337  mov     eax, cs:dword_1400040A0
0x14000133d  jmp     short loc_14000138E
0x14000133f  cmp     ax, 22h ; '"'
0x140001343  jnz     short loc_140001353
0x140001345  mov     eax, r15d
0x140001348  test    esi, esi
0x14000134a  setz    al
0x14000134d  mov     esi, eax
0x14000134f  mov     [rsp+0E8h+var_B8], eax
0x140001353  add     rcx, 2
0x140001357  mov     [rsp+0E8h+var_C0], rcx
0x14000135c  jmp     loc_1400012C2
0x140001361  mov     cs:dword_1400040A0, eax
0x140001367  cmp     cs:dword_1400040C0, 0
0x14000136e  jnz     short loc_140001379
0x140001370  mov     ecx, eax; Code
0x140001372  call    cs:__imp__exit
0x140001379  cmp     cs:dword_1400040A4, 0
0x140001380  jnz     short loc_14000138E
0x140001382  call    cs:__imp__cexit
0x140001388  mov     eax, cs:dword_1400040A0
0x14000138e  add     rsp, 0B8h
0x140001395  pop     r15
0x140001397  pop     r14
0x140001399  pop     r12
0x14000139b  pop     rdi
0x14000139c  pop     rsi
0x14000139d  pop     rbx
0x14000139e  retn
0x140001be0  push    rbp
0x140001be2  sub     rsp, 20h
0x140001be6  mov     rbp, rdx
0x140001be9  mov     rdx, rcx
0x140001bec  mov     rcx, [rcx]
0x140001bef  mov     ecx, [rcx]
0x140001bf1  call    _XcptFilter_0
0x140001bf6  nop
0x140001bf7  add     rsp, 20h
0x140001bfb  pop     rbp
0x140001bfc  retn
```
