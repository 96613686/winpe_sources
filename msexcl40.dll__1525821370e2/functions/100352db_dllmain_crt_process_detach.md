# dllmain_crt_process_detach

- ea: `0x100352db`
- end: `0x10035391`
- name: `dllmain_crt_process_detach`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x10035170`

## callees

- `0x100352db`
- `0x10035586`
- `0x10035674`
- `0x1003569d`
- `0x1003581d`
- `0x10035842`
- `0x100359e0`
- `0x10035a21`
- `0x10035a67`
- `0x10035aa0`

## pseudocode

```c
BOOL __cdecl dllmain_crt_process_detach(int a1)
{
  BOOL v2; // esi
  int v3; // [esp+0h] [ebp-30h]
  int v4; // [esp+4h] [ebp-2Ch]
  int v5; // [esp+8h] [ebp-28h]
  int v6; // [esp+Ch] [ebp-24h]
  int v7; // [esp+10h] [ebp-20h]
  int ms_exc; // [esp+18h] [ebp-18h]
  int ms_exc_4; // [esp+1Ch] [ebp-14h]
  int ms_exc_8; // [esp+20h] [ebp-10h]
  int ms_exc_12; // [esp+24h] [ebp-Ch]
  int ms_exc_16; // [esp+28h] [ebp-8h]

  if ( dword_1003A710 <= 0 )
    return 0;
  --dword_1003A710;
  LOBYTE(v7) = __scrt_acquire_startup_lock();
  if ( __scrt_current_native_startup_state != 2 )
    __scrt_fastfail(7);
  __scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  _RTC_Terminate();
  __scrt_current_native_startup_state = 0;
  __scrt_release_startup_lock(v7);
  v2 = (unsigned __int8)__scrt_uninitialize_crt(a1, 0) != 0;
  __scrt_dllmain_uninitialize_critical(
    268653410,
    v3,
    v4,
    v5,
    v6,
    v7,
    v2,
    ms_exc,
    ms_exc_4,
    ms_exc_8,
    ms_exc_12,
    ms_exc_16,
    -2);
  return v2;
}

```

## disassembly

```asm
0x100352db  push    10h
0x100352dd  push    offset stru_100374B0
0x100352e2  call    __SEH_prolog4
0x100352e7  mov     eax, dword_1003A710
0x100352ec  test    eax, eax
0x100352ee  jg      short loc_100352F4
0x100352f0  xor     eax, eax
0x100352f2  jmp     short loc_10035364
0x100352f4  dec     eax
0x100352f5  mov     dword_1003A710, eax
0x100352fa  xor     esi, esi
0x100352fc  inc     esi
0x100352fd  mov     [ebp+var_1C], esi
0x10035300  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10035307  call    ___scrt_acquire_startup_lock
0x1003530c  mov     byte ptr [ebp+var_20], al
0x1003530f  mov     [ebp+ms_exc.registration.TryLevel], esi
0x10035312  cmp     ___scrt_current_native_startup_state, 2
0x10035319  jnz     short loc_1003538A
0x1003531b  call    ___scrt_dllmain_uninitialize_c
0x10035320  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x10035325  call    __RTC_Terminate
0x1003532a  mov     ___scrt_current_native_startup_state, 0
0x10035334  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1003533b  call    loc_10035377
0x10035340  push    0
0x10035342  push    [ebp+arg_0]
0x10035345  call    ___scrt_uninitialize_crt
0x1003534a  pop     ecx
0x1003534b  pop     ecx
0x1003534c  xor     ecx, ecx
0x1003534e  test    al, al
0x10035350  cmovz   esi, ecx
0x10035353  mov     [ebp+var_1C], esi
0x10035356  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003535d  call    loc_10035384
0x10035362  mov     eax, esi
0x10035364  mov     ecx, [ebp+ms_exc.registration.Next]
0x10035367  mov     large fs:0, ecx
0x1003536e  pop     ecx
0x1003536f  pop     edi
0x10035370  pop     esi
0x10035371  pop     ebx
0x10035372  leave
0x10035373  retn
0x10035374  mov     esi, [ebp+var_1C]
0x10035377  push    [ebp+var_20]
0x1003537a  call    ___scrt_release_startup_lock
0x1003537f  pop     ecx
0x10035380  retn
0x10035381  mov     esi, [ebp+var_1C]
0x10035384  call    ___scrt_dllmain_uninitialize_critical
0x10035389  retn
0x1003538a  push    7
0x1003538c  call    ___scrt_fastfail
```
