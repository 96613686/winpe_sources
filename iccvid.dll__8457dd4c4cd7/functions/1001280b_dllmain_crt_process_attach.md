# dllmain_crt_process_attach

- ea: `0x1001280b`
- end: `0x10012914`
- name: `dllmain_crt_process_attach`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x100127b0`

## callees

- `0x1001280b`
- `0x10012c0a`
- `0x10012c2e`
- `0x10012c9b`
- `0x10012cd5`
- `0x10012d06`
- `0x10012dc5`
- `0x10012e95`
- `0x10012f32`
- `0x10012f87`
- `0x10012f93`
- `0x10012fa5`
- `0x10013010`
- `0x100130b0`
- `0x10013403`
- `0x1001340f`

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
  ++dword_10014950;
  return 1;
}

```

## disassembly

```asm
0x1001280b  push    10h
0x1001280d  push    offset stru_100135A0
0x10012812  call    __SEH_prolog4
0x10012817  push    0
0x10012819  call    ___scrt_initialize_crt
0x1001281e  pop     ecx
0x1001281f  test    al, al
0x10012821  jz      loc_100128FB
0x10012827  call    ___scrt_acquire_startup_lock
0x1001282c  mov     byte ptr [ebp+var_1D], al
0x1001282f  mov     bl, 1
0x10012831  mov     [ebp+var_19], bl
0x10012834  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1001283b  cmp     ___scrt_current_native_startup_state, 0
0x10012842  jnz     loc_1001290D
0x10012848  mov     ___scrt_current_native_startup_state, 1
0x10012852  call    ___scrt_dllmain_before_initialize_c
0x10012857  test    al, al
0x10012859  jz      short loc_100128A8
0x1001285b  call    __RTC_Initialize
0x10012860  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x10012865  call    ___scrt_initialize_default_local_stdio_options
0x1001286a  push    offset ___xi_z; Last
0x1001286f  push    offset ___xi_a; First
0x10012874  call    __initterm_e
0x10012879  pop     ecx
0x1001287a  pop     ecx
0x1001287b  test    eax, eax
0x1001287d  jnz     short loc_100128A8
0x1001287f  call    ___scrt_dllmain_after_initialize_c
0x10012884  test    al, al
0x10012886  jz      short loc_100128A8
0x10012888  push    offset ___xc_z; Last
0x1001288d  push    offset ___xc_a; First
0x10012892  call    __initterm
0x10012897  pop     ecx
0x10012898  pop     ecx
0x10012899  mov     ___scrt_current_native_startup_state, 2
0x100128a3  xor     bl, bl
0x100128a5  mov     [ebp+var_19], bl
0x100128a8  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100128af  call    loc_100128F1
0x100128b4  test    bl, bl
0x100128b6  jnz     short loc_100128FB
0x100128b8  call    ___scrt_get_dyn_tls_init_callback
0x100128bd  mov     esi, eax
0x100128bf  cmp     dword ptr [esi], 0
0x100128c2  jz      short loc_100128E3
0x100128c4  push    esi
0x100128c5  call    ___scrt_is_nonwritable_in_current_image
0x100128ca  pop     ecx
0x100128cb  test    al, al
0x100128cd  jz      short loc_100128E3
0x100128cf  push    [ebp+arg_4]
0x100128d2  push    2
0x100128d4  push    [ebp+arg_0]
0x100128d7  mov     esi, [esi]
0x100128d9  mov     ecx, esi
0x100128db  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100128e1  call    esi
0x100128e3  inc     dword_10014950
0x100128e9  xor     eax, eax
0x100128eb  inc     eax
0x100128ec  jmp     short loc_100128FD
0x100128ee  mov     bl, [ebp+var_19]
0x100128f1  push    [ebp+var_1D]
0x100128f4  call    ___scrt_release_startup_lock
0x100128f9  pop     ecx
0x100128fa  retn
0x100128fb  xor     eax, eax
0x100128fd  mov     ecx, [ebp+ms_exc.registration.Next]
0x10012900  mov     large fs:0, ecx
0x10012907  pop     ecx
0x10012908  pop     edi
0x10012909  pop     esi
0x1001290a  pop     ebx
0x1001290b  leave
0x1001290c  retn
0x1001290d  push    7
0x1001290f  call    ___scrt_fastfail
```
