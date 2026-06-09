# dllmain_crt_process_detach

- ea: `0x1005e17b`
- end: `0x1005e231`
- name: `dllmain_crt_process_detach`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1005e010`

## callees

- `0x1005e17b`
- `0x1005e40e`
- `0x1005e4fc`
- `0x1005e525`
- `0x1005e6a5`
- `0x1005e6ca`
- `0x1005ea71`
- `0x1005eab2`
- `0x1005eaf8`
- `0x1005eb30`

## pseudocode

```c
BOOL __cdecl dllmain_crt_process_detach(int a1)
{
  BOOL v2; // esi
  char v3; // [esp+10h] [ebp-20h]

  if ( dword_10066590 <= 0 )
    return 0;
  --dword_10066590;
  v3 = __scrt_acquire_startup_lock();
  if ( __scrt_current_native_startup_state != 2 )
    __scrt_fastfail(7);
  __scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  _RTC_Terminate();
  __scrt_current_native_startup_state = 0;
  __scrt_release_startup_lock(v3);
  v2 = (unsigned __int8)__scrt_uninitialize_crt(a1, 0) != 0;
  __scrt_dllmain_uninitialize_critical(268820994);
  return v2;
}

```

## disassembly

```asm
0x1005e17b  push    10h
0x1005e17d  push    offset stru_10064D80
0x1005e182  call    __SEH_prolog4
0x1005e187  mov     eax, dword_10066590
0x1005e18c  test    eax, eax
0x1005e18e  jg      short loc_1005E194
0x1005e190  xor     eax, eax
0x1005e192  jmp     short loc_1005E204
0x1005e194  dec     eax
0x1005e195  mov     dword_10066590, eax
0x1005e19a  xor     esi, esi
0x1005e19c  inc     esi
0x1005e19d  mov     [ebp+var_1C], esi
0x1005e1a0  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1005e1a7  call    ___scrt_acquire_startup_lock
0x1005e1ac  mov     byte ptr [ebp+var_20], al
0x1005e1af  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1005e1b2  cmp     ___scrt_current_native_startup_state, 2
0x1005e1b9  jnz     short loc_1005E22A
0x1005e1bb  call    ___scrt_dllmain_uninitialize_c
0x1005e1c0  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1005e1c5  call    __RTC_Terminate
0x1005e1ca  mov     ___scrt_current_native_startup_state, 0
0x1005e1d4  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1005e1db  call    loc_1005E217
0x1005e1e0  push    0
0x1005e1e2  push    [ebp+arg_0]
0x1005e1e5  call    ___scrt_uninitialize_crt
0x1005e1ea  pop     ecx
0x1005e1eb  pop     ecx
0x1005e1ec  xor     ecx, ecx
0x1005e1ee  test    al, al
0x1005e1f0  cmovz   esi, ecx
0x1005e1f3  mov     [ebp+var_1C], esi
0x1005e1f6  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1005e1fd  call    loc_1005E224
0x1005e202  mov     eax, esi
0x1005e204  mov     ecx, [ebp+ms_exc.registration.Next]
0x1005e207  mov     large fs:0, ecx
0x1005e20e  pop     ecx
0x1005e20f  pop     edi
0x1005e210  pop     esi
0x1005e211  pop     ebx
0x1005e212  leave
0x1005e213  retn
0x1005e214  mov     esi, [ebp+var_1C]
0x1005e217  push    [ebp+var_20]
0x1005e21a  call    ___scrt_release_startup_lock
0x1005e21f  pop     ecx
0x1005e220  retn
0x1005e221  mov     esi, [ebp+var_1C]
0x1005e224  call    ___scrt_dllmain_uninitialize_critical
0x1005e229  retn
0x1005e22a  push    7
0x1005e22c  call    ___scrt_fastfail
```
