# dllmain_crt_process_detach

- ea: `0x1001291b`
- end: `0x100129d1`
- name: `dllmain_crt_process_detach`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x100127b0`

## callees

- `0x1001291b`
- `0x10012c1c`
- `0x10012c9b`
- `0x10012d89`
- `0x10012db2`
- `0x10012f32`
- `0x10012f57`
- `0x10012f93`
- `0x10012fd9`
- `0x10013010`

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

  if ( dword_10014950 <= 0 )
    return 0;
  --dword_10014950;
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
    268511650,
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
0x1001291b  push    10h
0x1001291d  push    offset stru_100135C0
0x10012922  call    __SEH_prolog4
0x10012927  mov     eax, dword_10014950
0x1001292c  test    eax, eax
0x1001292e  jg      short loc_10012934
0x10012930  xor     eax, eax
0x10012932  jmp     short loc_100129A4
0x10012934  dec     eax
0x10012935  mov     dword_10014950, eax
0x1001293a  xor     esi, esi
0x1001293c  inc     esi
0x1001293d  mov     [ebp+var_1C], esi
0x10012940  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10012947  call    ___scrt_acquire_startup_lock
0x1001294c  mov     byte ptr [ebp+var_20], al
0x1001294f  mov     [ebp+ms_exc.registration.TryLevel], esi
0x10012952  cmp     ___scrt_current_native_startup_state, 2
0x10012959  jnz     short loc_100129CA
0x1001295b  call    ___scrt_dllmain_uninitialize_c
0x10012960  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x10012965  call    __RTC_Terminate
0x1001296a  mov     ___scrt_current_native_startup_state, 0
0x10012974  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1001297b  call    loc_100129B7
0x10012980  push    0
0x10012982  push    [ebp+arg_0]
0x10012985  call    ___scrt_uninitialize_crt
0x1001298a  pop     ecx
0x1001298b  pop     ecx
0x1001298c  xor     ecx, ecx
0x1001298e  test    al, al
0x10012990  cmovz   esi, ecx
0x10012993  mov     [ebp+var_1C], esi
0x10012996  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1001299d  call    loc_100129C4
0x100129a2  mov     eax, esi
0x100129a4  mov     ecx, [ebp+ms_exc.registration.Next]
0x100129a7  mov     large fs:0, ecx
0x100129ae  pop     ecx
0x100129af  pop     edi
0x100129b0  pop     esi
0x100129b1  pop     ebx
0x100129b2  leave
0x100129b3  retn
0x100129b4  mov     esi, [ebp+var_1C]
0x100129b7  push    [ebp+var_20]
0x100129ba  call    ___scrt_release_startup_lock
0x100129bf  pop     ecx
0x100129c0  retn
0x100129c1  mov     esi, [ebp+var_1C]
0x100129c4  call    ___scrt_dllmain_uninitialize_critical
0x100129c9  retn
0x100129ca  push    7
0x100129cc  call    ___scrt_fastfail
```
