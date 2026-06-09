# dllmain_crt_process_attach

- ea: `0x100351cb`
- end: `0x100352d4`
- name: `dllmain_crt_process_attach`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x10035170`

## callees

- `0x100351cb`
- `0x10035586`
- `0x100355c0`
- `0x100355f1`
- `0x100356b0`
- `0x10035780`
- `0x1003581d`
- `0x100359ce`
- `0x100359f2`
- `0x10035a15`
- `0x10035a21`
- `0x10035a33`
- `0x10035aa0`
- `0x10035b40`
- `0x10035e87`
- `0x10035e93`

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
  ++dword_1003A710;
  return 1;
}

```

## disassembly

```asm
0x100351cb  push    10h
0x100351cd  push    offset stru_10037490
0x100351d2  call    __SEH_prolog4
0x100351d7  push    0
0x100351d9  call    ___scrt_initialize_crt
0x100351de  pop     ecx
0x100351df  test    al, al
0x100351e1  jz      loc_100352BB
0x100351e7  call    ___scrt_acquire_startup_lock
0x100351ec  mov     byte ptr [ebp+var_1D], al
0x100351ef  mov     bl, 1
0x100351f1  mov     [ebp+var_19], bl
0x100351f4  mov     [ebp+ms_exc.registration.TryLevel], 0
0x100351fb  cmp     ___scrt_current_native_startup_state, 0
0x10035202  jnz     loc_100352CD
0x10035208  mov     ___scrt_current_native_startup_state, 1
0x10035212  call    ___scrt_dllmain_before_initialize_c
0x10035217  test    al, al
0x10035219  jz      short loc_10035268
0x1003521b  call    __RTC_Initialize
0x10035220  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x10035225  call    ___scrt_initialize_default_local_stdio_options
0x1003522a  push    offset ___xi_z; Last
0x1003522f  push    offset ___xi_a; First
0x10035234  call    __initterm_e
0x10035239  pop     ecx
0x1003523a  pop     ecx
0x1003523b  test    eax, eax
0x1003523d  jnz     short loc_10035268
0x1003523f  call    ___scrt_dllmain_after_initialize_c
0x10035244  test    al, al
0x10035246  jz      short loc_10035268
0x10035248  push    offset ___xc_z; Last
0x1003524d  push    offset ___xc_a; First
0x10035252  call    __initterm
0x10035257  pop     ecx
0x10035258  pop     ecx
0x10035259  mov     ___scrt_current_native_startup_state, 2
0x10035263  xor     bl, bl
0x10035265  mov     [ebp+var_19], bl
0x10035268  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003526f  call    loc_100352B1
0x10035274  test    bl, bl
0x10035276  jnz     short loc_100352BB
0x10035278  call    ___scrt_get_dyn_tls_init_callback
0x1003527d  mov     esi, eax
0x1003527f  cmp     dword ptr [esi], 0
0x10035282  jz      short loc_100352A3
0x10035284  push    esi
0x10035285  call    ___scrt_is_nonwritable_in_current_image
0x1003528a  pop     ecx
0x1003528b  test    al, al
0x1003528d  jz      short loc_100352A3
0x1003528f  push    [ebp+arg_4]
0x10035292  push    2
0x10035294  push    [ebp+arg_0]
0x10035297  mov     esi, [esi]
0x10035299  mov     ecx, esi
0x1003529b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100352a1  call    esi
0x100352a3  inc     dword_1003A710
0x100352a9  xor     eax, eax
0x100352ab  inc     eax
0x100352ac  jmp     short loc_100352BD
0x100352ae  mov     bl, [ebp+var_19]
0x100352b1  push    [ebp+var_1D]
0x100352b4  call    ___scrt_release_startup_lock
0x100352b9  pop     ecx
0x100352ba  retn
0x100352bb  xor     eax, eax
0x100352bd  mov     ecx, [ebp+ms_exc.registration.Next]
0x100352c0  mov     large fs:0, ecx
0x100352c7  pop     ecx
0x100352c8  pop     edi
0x100352c9  pop     esi
0x100352ca  pop     ebx
0x100352cb  leave
0x100352cc  retn
0x100352cd  push    7
0x100352cf  call    ___scrt_fastfail
```
