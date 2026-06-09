# dllmain_crt_process_attach

- ea: `0x1003a81b`
- end: `0x1003a924`
- name: `dllmain_crt_process_attach`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1003a7c0`

## callees

- `0x1002d510`
- `0x1003a81b`
- `0x1003ac5e`
- `0x1003ac98`
- `0x1003acc9`
- `0x1003ad88`
- `0x1003ae58`
- `0x1003aef5`
- `0x1003b059`
- `0x1003b07d`
- `0x1003b0a0`
- `0x1003b0ac`
- `0x1003b0be`
- `0x1003b130`
- `0x1003b4cf`
- `0x1003b4db`

## pseudocode

```c
int __cdecl dllmain_crt_process_attach(int a1, int a2)
{
  char v2; // bl
  _DWORD *dyn_tls_init_callback; // eax
  _DWORD *v4; // esi
  char v6; // [esp+13h] [ebp-1Dh]

  if ( !(unsigned __int8)__scrt_initialize_crt(0) )
    return 0;
  v6 = __scrt_acquire_startup_lock();
  v2 = 1;
  if ( __scrt_current_native_startup_state )
    __scrt_fastfail(7);
  __scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)__scrt_dllmain_before_initialize_c() )
  {
    _RTC_Initialize();
    __scrt_initialize_type_info();
    __scrt_initialize_default_local_stdio_options();
    if ( !_initterm_e((_PIFV *)&__xi_a, (_PIFV *)&__xi_z) )
    {
      if ( (unsigned __int8)__scrt_dllmain_after_initialize_c() )
      {
        _initterm((_PVFV *)&__xc_a, (_PVFV *)&__xc_z);
        __scrt_current_native_startup_state = 2;
        v2 = 0;
      }
    }
  }
  __scrt_release_startup_lock(v6);
  if ( v2 )
    return 0;
  dyn_tls_init_callback = (_DWORD *)__scrt_get_dyn_tls_init_callback();
  v4 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)__scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      ((void (__thiscall *)(_DWORD, int, int, int))*v4)(*v4, a1, 2, a2);
  }
  ++dword_1003D210;
  return 1;
}

```

## disassembly

```asm
0x1003a81b  push    10h
0x1003a81d  push    offset stru_1003BD90
0x1003a822  call    __SEH_prolog4
0x1003a827  push    0
0x1003a829  call    ___scrt_initialize_crt
0x1003a82e  pop     ecx
0x1003a82f  test    al, al
0x1003a831  jz      loc_1003A90B
0x1003a837  call    ___scrt_acquire_startup_lock
0x1003a83c  mov     byte ptr [ebp+var_1D], al
0x1003a83f  mov     bl, 1
0x1003a841  mov     [ebp+var_19], bl
0x1003a844  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1003a84b  cmp     ___scrt_current_native_startup_state, 0
0x1003a852  jnz     loc_1003A91D
0x1003a858  mov     ___scrt_current_native_startup_state, 1
0x1003a862  call    ___scrt_dllmain_before_initialize_c
0x1003a867  test    al, al
0x1003a869  jz      short loc_1003A8B8
0x1003a86b  call    __RTC_Initialize
0x1003a870  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1003a875  call    ___scrt_initialize_default_local_stdio_options
0x1003a87a  push    offset ___xi_z; Last
0x1003a87f  push    offset ___xi_a; First
0x1003a884  call    __initterm_e
0x1003a889  pop     ecx
0x1003a88a  pop     ecx
0x1003a88b  test    eax, eax
0x1003a88d  jnz     short loc_1003A8B8
0x1003a88f  call    ___scrt_dllmain_after_initialize_c
0x1003a894  test    al, al
0x1003a896  jz      short loc_1003A8B8
0x1003a898  push    offset ___xc_z; Last
0x1003a89d  push    offset ___xc_a; First
0x1003a8a2  call    __initterm
0x1003a8a7  pop     ecx
0x1003a8a8  pop     ecx
0x1003a8a9  mov     ___scrt_current_native_startup_state, 2
0x1003a8b3  xor     bl, bl
0x1003a8b5  mov     [ebp+var_19], bl
0x1003a8b8  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003a8bf  call    loc_1003A901
0x1003a8c4  test    bl, bl
0x1003a8c6  jnz     short loc_1003A90B
0x1003a8c8  call    ___scrt_get_dyn_tls_init_callback
0x1003a8cd  mov     esi, eax
0x1003a8cf  cmp     dword ptr [esi], 0
0x1003a8d2  jz      short loc_1003A8F3
0x1003a8d4  push    esi
0x1003a8d5  call    ___scrt_is_nonwritable_in_current_image
0x1003a8da  pop     ecx
0x1003a8db  test    al, al
0x1003a8dd  jz      short loc_1003A8F3
0x1003a8df  push    [ebp+arg_4]
0x1003a8e2  push    2
0x1003a8e4  push    [ebp+arg_0]
0x1003a8e7  mov     esi, [esi]
0x1003a8e9  mov     ecx, esi; this
0x1003a8eb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003a8f1  call    esi
0x1003a8f3  inc     dword_1003D210
0x1003a8f9  xor     eax, eax
0x1003a8fb  inc     eax
0x1003a8fc  jmp     short loc_1003A90D
0x1003a8fe  mov     bl, [ebp+var_19]
0x1003a901  push    [ebp+var_1D]
0x1003a904  call    ___scrt_release_startup_lock
0x1003a909  pop     ecx
0x1003a90a  retn
0x1003a90b  xor     eax, eax
0x1003a90d  mov     ecx, [ebp+ms_exc.registration.Next]
0x1003a910  mov     large fs:0, ecx
0x1003a917  pop     ecx
0x1003a918  pop     edi
0x1003a919  pop     esi
0x1003a91a  pop     ebx
0x1003a91b  leave
0x1003a91c  retn
0x1003a91d  push    7
0x1003a91f  call    ___scrt_fastfail
```
