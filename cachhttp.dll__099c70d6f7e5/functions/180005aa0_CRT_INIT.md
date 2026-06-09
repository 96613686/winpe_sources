# _CRT_INIT

- ea: `0x180005aa0`
- end: `0x180005cc5`
- name: `_CRT_INIT`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005d14`

## callees

- `0x180005aa0`
- `0x180005f56`
- `0x180005fc0`
- `0x180006134`
- `0x180008c30`

## import_xrefs

- `msvcrt!free` at `0x180005b7f`
- `msvcrt!free` at `0x180005b7f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005aeb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005bdf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005aeb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005bdf`

## pseudocode

```c
__int64 __fastcall CRT_INIT(__int64 a1, int a2, __int64 a3)
{
  int v5; // ebp
  PVOID StackBase; // rdi
  signed __int64 v7; // rax
  void (**v8)(void); // rsi
  void (**v9)(void); // rdi
  void *v10; // r15
  __int64 v11; // r14
  void (*v12)(void); // rax
  int v13; // esi
  PVOID v14; // rdi
  signed __int64 v15; // rax
  __int64 (**v16)(void); // rdi
  int v17; // eax

  if ( !a2 )
  {
    if ( dword_18000E0A0 > 0 )
    {
      --dword_18000E0A0;
      v5 = 0;
      StackBase = NtCurrentTeb()->NtTib.StackBase;
      while ( 1 )
      {
        v7 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
        if ( !v7 )
          break;
        if ( (PVOID)v7 == StackBase )
        {
          v5 = 1;
          break;
        }
        Sleep(0x3E8u);
      }
      if ( _native_startup_state == 2 )
      {
        v8 = (void (**)(void))_onexitbegin;
        if ( _onexitbegin )
        {
          v9 = (void (**)(void))_onexitend;
          v10 = _onexitbegin;
          v11 = _onexitend;
          while ( --v9 >= v8 )
          {
            v12 = *v9;
            if ( *v9 )
            {
              *v9 = 0;
              v12();
              if ( v10 != _onexitbegin || v11 != _onexitend )
              {
                v10 = _onexitbegin;
                v8 = (void (**)(void))_onexitbegin;
                v11 = _onexitend;
                v9 = (void (**)(void))_onexitend;
              }
            }
          }
          free(v8);
          _onexitend = 0;
          _onexitbegin = 0;
        }
        _native_startup_state = 0;
        if ( !v5 )
          _InterlockedExchange64(&_native_startup_lock, 0);
      }
      else
      {
        amsg_exit_0(31);
      }
      return 1;
    }
    return 0;
  }
  if ( a2 == 1 )
  {
    v13 = 0;
    v14 = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v15 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)v14, 0);
      if ( !v15 )
        break;
      if ( (PVOID)v15 == v14 )
      {
        v13 = 1;
        break;
      }
      Sleep(0x3E8u);
    }
    if ( _native_startup_state )
    {
      amsg_exit_0(31);
    }
    else
    {
      v16 = (__int64 (**)(void))&_xi_a;
      _native_startup_state = 1;
      v17 = 0;
      if ( &_xi_a < &_xi_z )
      {
        while ( !v17 )
        {
          if ( *v16 )
            v17 = (*v16)();
          if ( ++v16 >= (__int64 (**)(void))&_xi_z )
          {
            if ( !v17 )
              goto LABEL_37;
            return 0;
          }
        }
        return 0;
      }
LABEL_37:
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v13 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      ((void (__fastcall *)(__int64, __int64, __int64))_dyn_tls_init_callback)(a1, 2, a3);
    ++dword_18000E0A0;
  }
  return 1;
}

```

## disassembly

```asm
0x180005aa0  push    rbp
0x180005aa2  push    rsi
0x180005aa3  push    rdi
0x180005aa4  push    r14
0x180005aa6  push    r15
0x180005aa8  sub     rsp, 20h
0x180005aac  mov     rbp, r8
0x180005aaf  mov     r14, rcx
0x180005ab2  test    edx, edx
0x180005ab4  jnz     loc_180005BBB
0x180005aba  mov     eax, cs:dword_18000E0A0
0x180005ac0  test    eax, eax
0x180005ac2  jle     loc_180005C4E
0x180005ac8  dec     eax
0x180005aca  mov     cs:dword_18000E0A0, eax
0x180005ad0  xor     ebp, ebp
0x180005ad2  mov     rax, gs:30h
0x180005adb  mov     rdi, [rax+8]
0x180005adf  jmp     short loc_180005AF1
0x180005ae1  cmp     rax, rdi
0x180005ae4  jz      short loc_180005B00
0x180005ae6  mov     ecx, 3E8h; dwMilliseconds
0x180005aeb  call    cs:__imp_Sleep
0x180005af1  xor     eax, eax
0x180005af3  lock cmpxchg cs:__native_startup_lock, rdi
0x180005afc  jnz     short loc_180005AE1
0x180005afe  jmp     short loc_180005B05
0x180005b00  mov     ebp, 1
0x180005b05  mov     eax, cs:__native_startup_state
0x180005b0b  cmp     eax, 2
0x180005b0e  jz      short loc_180005B1F
0x180005b10  mov     ecx, 1Fh
0x180005b15  call    _amsg_exit_0
0x180005b1a  jmp     loc_180005CB4
0x180005b1f  mov     rsi, cs:__onexitbegin
0x180005b26  test    rsi, rsi
0x180005b29  jz      short loc_180005B9B
0x180005b2b  mov     rdi, cs:__onexitend
0x180005b32  mov     r15, rsi
0x180005b35  mov     r14, rdi
0x180005b38  sub     rdi, 8
0x180005b3c  cmp     rdi, rsi
0x180005b3f  jb      short loc_180005B7C
0x180005b41  mov     rax, [rdi]
0x180005b44  test    rax, rax
0x180005b47  jz      short loc_180005B38
0x180005b49  mov     qword ptr [rdi], 0
0x180005b50  call    cs:__guard_dispatch_icall_fptr
0x180005b56  mov     rcx, cs:__onexitbegin
0x180005b5d  mov     rax, cs:__onexitend
0x180005b64  cmp     r15, rcx
0x180005b67  jnz     short loc_180005B6E
0x180005b69  cmp     r14, rax
0x180005b6c  jz      short loc_180005B38
0x180005b6e  mov     r15, rcx
0x180005b71  mov     rsi, rcx
0x180005b74  mov     r14, rax
0x180005b77  mov     rdi, rax
0x180005b7a  jmp     short loc_180005B38
0x180005b7c  mov     rcx, rsi; Block
0x180005b7f  call    cs:__imp_free
0x180005b85  mov     cs:__onexitend, 0
0x180005b90  mov     cs:__onexitbegin, 0
0x180005b9b  mov     cs:__native_startup_state, 0
0x180005ba5  test    ebp, ebp
0x180005ba7  jnz     loc_180005CB4
0x180005bad  xor     eax, eax
0x180005baf  xchg    rax, cs:__native_startup_lock
0x180005bb6  jmp     loc_180005CB4
0x180005bbb  cmp     edx, 1
0x180005bbe  jnz     loc_180005CB4
0x180005bc4  mov     rax, gs:30h
0x180005bcd  xor     esi, esi
0x180005bcf  mov     rdi, [rax+8]
0x180005bd3  jmp     short loc_180005BE5
0x180005bd5  cmp     rax, rdi
0x180005bd8  jz      short loc_180005BF4
0x180005bda  mov     ecx, 3E8h; dwMilliseconds
0x180005bdf  call    cs:__imp_Sleep
0x180005be5  xor     eax, eax
0x180005be7  lock cmpxchg cs:__native_startup_lock, rdi
0x180005bf0  jnz     short loc_180005BD5
0x180005bf2  jmp     short loc_180005BF9
0x180005bf4  mov     esi, 1
0x180005bf9  mov     eax, cs:__native_startup_state
0x180005bff  test    eax, eax
0x180005c01  jz      short loc_180005C0F
0x180005c03  mov     ecx, 1Fh
0x180005c08  call    _amsg_exit_0
0x180005c0d  jmp     short loc_180005C6F
0x180005c0f  lea     rdi, __xi_a
0x180005c16  mov     cs:__native_startup_state, 1
0x180005c20  xor     eax, eax
0x180005c22  lea     r15, __xi_z
0x180005c29  cmp     rdi, r15
0x180005c2c  jnb     short loc_180005C52
0x180005c2e  test    eax, eax
0x180005c30  jnz     short loc_180005C4E
0x180005c32  cmp     qword ptr [rdi], 0
0x180005c36  jz      short loc_180005C41
0x180005c38  mov     rax, [rdi]
0x180005c3b  call    cs:__guard_dispatch_icall_fptr
0x180005c41  add     rdi, 8
0x180005c45  cmp     rdi, r15
0x180005c48  jb      short loc_180005C2E
0x180005c4a  test    eax, eax
0x180005c4c  jz      short loc_180005C52
0x180005c4e  xor     eax, eax
0x180005c50  jmp     short loc_180005CB9
0x180005c52  lea     rdx, __xc_z; Last
0x180005c59  lea     rcx, __xc_a; First
0x180005c60  call    _initterm_0
0x180005c65  mov     cs:__native_startup_state, 2
0x180005c6f  test    esi, esi
0x180005c71  jnz     short loc_180005C7C
0x180005c73  xor     eax, eax
0x180005c75  xchg    rax, cs:__native_startup_lock
0x180005c7c  cmp     cs:__dyn_tls_init_callback, 0
0x180005c84  jz      short loc_180005CAE
0x180005c86  lea     rcx, __dyn_tls_init_callback
0x180005c8d  call    _IsNonwritableInCurrentImage
0x180005c92  test    eax, eax
0x180005c94  jz      short loc_180005CAE
0x180005c96  mov     rax, cs:__dyn_tls_init_callback
0x180005c9d  mov     r8, rbp
0x180005ca0  mov     edx, 2
0x180005ca5  mov     rcx, r14
0x180005ca8  call    cs:__guard_dispatch_icall_fptr
0x180005cae  inc     cs:dword_18000E0A0
0x180005cb4  mov     eax, 1
0x180005cb9  add     rsp, 20h
0x180005cbd  pop     r15
0x180005cbf  pop     r14
0x180005cc1  pop     rdi
0x180005cc2  pop     rsi
0x180005cc3  pop     rbp
0x180005cc4  retn
```
