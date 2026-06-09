# __wmainCRTStartup

- ea: `0x140001220`
- end: `0x14000147f`
- name: `__wmainCRTStartup`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001490`

## callees

- `0x140001220`
- `0x14000151e`
- `0x1400015d0`
- `0x140001640`
- `0x1400017a7`
- `0x1400017bf`
- `0x140001e24`
- `0x140004d10`

## import_xrefs

- `msvcrt!_wcmdln` at `0x140001384`
- `msvcrt!_cexit` at `0x140001411`
- `msvcrt!_cexit` at `0x140001462`
- `msvcrt!_cexit` at `0x140001411`
- `msvcrt!_cexit` at `0x140001462`
- `msvcrt!_exit` at `0x140001452`
- `msvcrt!_exit` at `0x140001452`
- `msvcrt!exit` at `0x140001402`
- `msvcrt!exit` at `0x140001402`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000128a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000128a`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001252`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001252`

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
    dword_140008140 = result;
    if ( !dword_140008160 )
      exit(result);
    if ( !dword_140008144 )
    {
      _cexit();
      return dword_140008140;
    }
    return result;
  }
  if ( _native_startup_state )
  {
    dword_140008144 = 1;
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
0x140001220  push    rbx
0x140001222  push    rsi
0x140001223  push    rdi
0x140001224  push    r12
0x140001226  push    r14
0x140001228  push    r15
0x14000122a  sub     rsp, 0B8h
0x140001231  xor     eax, eax
0x140001233  mov     dword ptr [rsp+0E8h+StartupInfo+4], eax
0x140001237  xor     edx, edx; Val
0x140001239  lea     r8d, [rax+64h]; Size
0x14000123d  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x140001242  call    memset_0
0x140001247  xor     r15d, r15d
0x14000124a  mov     esi, r15d
0x14000124d  lea     rcx, [rsp+0E8h+StartupInfo]; lpStartupInfo
0x140001252  call    cs:__imp_GetStartupInfoW
0x140001258  nop
0x140001259  mov     rax, gs:30h
0x140001262  mov     rbx, [rax+8]
0x140001266  mov     r14d, r15d
0x140001269  xor     eax, eax
0x14000126b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001274  jz      short loc_140001292
0x140001276  cmp     rax, rbx
0x140001279  jnz     short loc_140001285
0x14000127b  mov     ebx, 1
0x140001280  mov     r14d, ebx
0x140001283  jmp     short loc_140001297
0x140001285  mov     ecx, 3E8h; dwMilliseconds
0x14000128a  call    cs:__imp_Sleep
0x140001290  jmp     short loc_140001269
0x140001292  mov     ebx, 1
0x140001297  mov     eax, cs:__native_startup_state
0x14000129d  cmp     eax, ebx
0x14000129f  jnz     short loc_1400012AF
0x1400012a1  mov     edi, 1Fh
0x1400012a6  mov     ecx, edi
0x1400012a8  call    _amsg_exit_0
0x1400012ad  jmp     short loc_14000131B
0x1400012af  mov     eax, cs:__native_startup_state
0x1400012b5  test    eax, eax
0x1400012b7  jnz     short loc_140001310
0x1400012b9  mov     cs:__native_startup_state, ebx
0x1400012bf  lea     r12, __xi_z
0x1400012c6  lea     rdi, __xi_a
0x1400012cd  mov     [rsp+0E8h+var_B0], rdi
0x1400012d2  mov     eax, r15d
0x1400012d5  mov     [rsp+0E8h+var_C8], eax
0x1400012d9  cmp     rdi, r12
0x1400012dc  jnb     short loc_140001302
0x1400012de  test    eax, eax
0x1400012e0  jnz     short loc_140001306
0x1400012e2  cmp     [rdi], r15
0x1400012e5  jz      short loc_1400012F7
0x1400012e7  mov     rax, [rdi]
0x1400012ea  mov     rcx, cs:__guard_dispatch_icall_fptr
0x1400012f1  call    rcx ; _guard_dispatch_icall_nop
0x1400012f3  mov     [rsp+0E8h+var_C8], eax
0x1400012f7  add     rdi, 8
0x1400012fb  mov     [rsp+0E8h+var_B0], rdi
0x140001300  jmp     short loc_1400012D9
0x140001302  test    eax, eax
0x140001304  jz      short loc_140001316
0x140001306  mov     eax, 0FFh
0x14000130b  jmp     loc_14000146E
0x140001310  mov     cs:dword_140008144, ebx
0x140001316  mov     edi, 1Fh
0x14000131b  mov     eax, cs:__native_startup_state
0x140001321  cmp     eax, ebx
0x140001323  jnz     short loc_140001342
0x140001325  lea     rdx, __xc_z; Last
0x14000132c  lea     rcx, __xc_a; First
0x140001333  call    _initterm_0
0x140001338  mov     cs:__native_startup_state, 2
0x140001342  test    r14d, r14d
0x140001345  jnz     short loc_140001351
0x140001347  mov     rax, r15
0x14000134a  xchg    rax, cs:__native_startup_lock
0x140001351  cmp     cs:__dyn_tls_init_callback, r15
0x140001358  jz      short loc_140001384
0x14000135a  lea     rcx, __dyn_tls_init_callback
0x140001361  call    _IsNonwritableInCurrentImage
0x140001366  test    eax, eax
0x140001368  jz      short loc_140001384
0x14000136a  xor     r8d, r8d
0x14000136d  lea     edx, [r8+2]
0x140001371  xor     ecx, ecx
0x140001373  mov     rax, cs:__dyn_tls_init_callback
0x14000137a  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001381  call    r9 ; _guard_dispatch_icall_nop
0x140001384  mov     rax, cs:__imp__wcmdln
0x14000138b  mov     rcx, [rax]
0x14000138e  test    rcx, rcx
0x140001391  jnz     short loc_14000139D
0x140001393  mov     eax, 0FFh
0x140001398  jmp     loc_14000146E
0x14000139d  mov     [rsp+0E8h+var_C0], rcx
0x1400013a2  movzx   eax, word ptr [rcx]
0x1400013a5  cmp     ax, 20h ; ' '
0x1400013a9  ja      short loc_14000141F
0x1400013ab  test    ax, ax
0x1400013ae  jz      short loc_1400013B4
0x1400013b0  test    esi, esi
0x1400013b2  jnz     short loc_14000141F
0x1400013b4  sub     ax, bx
0x1400013b7  cmp     ax, di
0x1400013ba  ja      short loc_1400013CA
0x1400013bc  add     rcx, 2
0x1400013c0  mov     [rsp+0E8h+var_C0], rcx
0x1400013c5  movzx   eax, word ptr [rcx]
0x1400013c8  jmp     short loc_1400013B4
0x1400013ca  test    byte ptr [rsp+0E8h+StartupInfo.dwFlags], bl
0x1400013ce  movzx   eax, [rsp+0E8h+StartupInfo.wShowWindow]
0x1400013d6  mov     r9d, 0Ah
0x1400013dc  cmovnz  r9d, eax; nShowCmd
0x1400013e0  mov     r8, rcx; lpCmdLine
0x1400013e3  xor     edx, edx; hPrevInstance
0x1400013e5  lea     rcx, cs:140000000h; hInstance
0x1400013ec  call    wWinMain
0x1400013f1  mov     cs:dword_140008140, eax
0x1400013f7  cmp     cs:dword_140008160, r15d
0x1400013fe  jnz     short loc_140001408
0x140001400  mov     ecx, eax; Code
0x140001402  call    cs:__imp_exit
0x140001408  cmp     cs:dword_140008144, r15d
0x14000140f  jnz     short loc_14000141D
0x140001411  call    cs:__imp__cexit
0x140001417  mov     eax, cs:dword_140008140
0x14000141d  jmp     short loc_14000146E
0x14000141f  cmp     ax, 22h ; '"'
0x140001423  jnz     short loc_140001433
0x140001425  mov     eax, r15d
0x140001428  test    esi, esi
0x14000142a  setz    al
0x14000142d  mov     esi, eax
0x14000142f  mov     [rsp+0E8h+var_B8], eax
0x140001433  add     rcx, 2
0x140001437  mov     [rsp+0E8h+var_C0], rcx
0x14000143c  jmp     loc_1400013A2
0x140001441  mov     cs:dword_140008140, eax
0x140001447  cmp     cs:dword_140008160, 0
0x14000144e  jnz     short loc_140001459
0x140001450  mov     ecx, eax; Code
0x140001452  call    cs:__imp__exit
0x140001459  cmp     cs:dword_140008144, 0
0x140001460  jnz     short loc_14000146E
0x140001462  call    cs:__imp__cexit
0x140001468  mov     eax, cs:dword_140008140
0x14000146e  add     rsp, 0B8h
0x140001475  pop     r15
0x140001477  pop     r14
0x140001479  pop     r12
0x14000147b  pop     rdi
0x14000147c  pop     rsi
0x14000147d  pop     rbx
0x14000147e  retn
0x140004de0  push    rbp
0x140004de2  sub     rsp, 20h
0x140004de6  mov     rbp, rdx
0x140004de9  mov     rdx, rcx
0x140004dec  mov     rcx, [rcx]
0x140004def  mov     ecx, [rcx]
0x140004df1  call    _XcptFilter_0
0x140004df6  nop
0x140004df7  add     rsp, 20h
0x140004dfb  pop     rbp
0x140004dfc  retn
```
