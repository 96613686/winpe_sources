# dllmain_crt_process_attach

- ea: `0x1005e06b`
- end: `0x1005e174`
- name: `dllmain_crt_process_attach`
- size: `265`
- prototype: `int __cdecl(void *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1005e010`

## callees

- `0x1000eb60`
- `0x1005e06b`
- `0x1005e40e`
- `0x1005e448`
- `0x1005e479`
- `0x1005e538`
- `0x1005e608`
- `0x1005e6a5`
- `0x1005ea5f`
- `0x1005ea83`
- `0x1005eaa6`
- `0x1005eab2`
- `0x1005eac4`
- `0x1005eb30`
- `0x1005f04c`
- `0x1005f058`

## pseudocode

```c
int __cdecl dllmain_crt_process_attach(void *a1, int a2)
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
      ((void (__thiscall *)(_DWORD, void *, int, int))*v4)(*v4, a1, 2, a2);
  }
  ++dword_10066590;
  return 1;
}

```

## disassembly

```asm
0x1005e06b  push    10h
0x1005e06d  push    offset stru_10064D60
0x1005e072  call    __SEH_prolog4
0x1005e077  push    0
0x1005e079  call    ___scrt_initialize_crt
0x1005e07e  pop     ecx
0x1005e07f  test    al, al
0x1005e081  jz      loc_1005E15B
0x1005e087  call    ___scrt_acquire_startup_lock
0x1005e08c  mov     byte ptr [ebp+var_1D], al
0x1005e08f  mov     bl, 1
0x1005e091  mov     [ebp+var_19], bl
0x1005e094  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1005e09b  cmp     ___scrt_current_native_startup_state, 0
0x1005e0a2  jnz     loc_1005E16D
0x1005e0a8  mov     ___scrt_current_native_startup_state, 1
0x1005e0b2  call    ___scrt_dllmain_before_initialize_c
0x1005e0b7  test    al, al
0x1005e0b9  jz      short loc_1005E108
0x1005e0bb  call    __RTC_Initialize
0x1005e0c0  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1005e0c5  call    ___scrt_initialize_default_local_stdio_options
0x1005e0ca  push    offset ___xi_z; Last
0x1005e0cf  push    offset ___xi_a; First
0x1005e0d4  call    __initterm_e
0x1005e0d9  pop     ecx
0x1005e0da  pop     ecx
0x1005e0db  test    eax, eax
0x1005e0dd  jnz     short loc_1005E108
0x1005e0df  call    ___scrt_dllmain_after_initialize_c
0x1005e0e4  test    al, al
0x1005e0e6  jz      short loc_1005E108
0x1005e0e8  push    offset ___xc_z; Last
0x1005e0ed  push    offset ___xc_a; First
0x1005e0f2  call    __initterm
0x1005e0f7  pop     ecx
0x1005e0f8  pop     ecx
0x1005e0f9  mov     ___scrt_current_native_startup_state, 2
0x1005e103  xor     bl, bl
0x1005e105  mov     [ebp+var_19], bl
0x1005e108  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1005e10f  call    loc_1005E151
0x1005e114  test    bl, bl
0x1005e116  jnz     short loc_1005E15B
0x1005e118  call    ___scrt_get_dyn_tls_init_callback
0x1005e11d  mov     esi, eax
0x1005e11f  cmp     dword ptr [esi], 0
0x1005e122  jz      short loc_1005E143
0x1005e124  push    esi
0x1005e125  call    ___scrt_is_nonwritable_in_current_image
0x1005e12a  pop     ecx
0x1005e12b  test    al, al
0x1005e12d  jz      short loc_1005E143
0x1005e12f  push    [ebp+arg_4]
0x1005e132  push    2; unsigned int
0x1005e134  push    [ebp+arg_0]; void *
0x1005e137  mov     esi, [esi]
0x1005e139  mov     ecx, esi
0x1005e13b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005e141  call    esi
0x1005e143  inc     dword_10066590
0x1005e149  xor     eax, eax
0x1005e14b  inc     eax
0x1005e14c  jmp     short loc_1005E15D
0x1005e14e  mov     bl, [ebp+var_19]
0x1005e151  push    [ebp+var_1D]
0x1005e154  call    ___scrt_release_startup_lock
0x1005e159  pop     ecx
0x1005e15a  retn
0x1005e15b  xor     eax, eax
0x1005e15d  mov     ecx, [ebp+ms_exc.registration.Next]
0x1005e160  mov     large fs:0, ecx
0x1005e167  pop     ecx
0x1005e168  pop     edi
0x1005e169  pop     esi
0x1005e16a  pop     ebx
0x1005e16b  leave
0x1005e16c  retn
0x1005e16d  push    7
0x1005e16f  call    ___scrt_fastfail
```
