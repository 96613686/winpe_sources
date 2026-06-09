# dllmain_crt_process_detach

- ea: `0x1003a92b`
- end: `0x1003a9e1`
- name: `dllmain_crt_process_detach`
- size: `182`
- prototype: `BOOL __cdecl(int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1003a7c0`

## callees

- `0x1003a92b`
- `0x1003ac5e`
- `0x1003ad4c`
- `0x1003ad75`
- `0x1003aef5`
- `0x1003af1a`
- `0x1003b06b`
- `0x1003b0ac`
- `0x1003b0f2`
- `0x1003b130`

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

  if ( dword_1003D210 <= 0 )
    return 0;
  --dword_1003D210;
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
    268675506,
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
0x1003a92b  push    10h
0x1003a92d  push    offset stru_1003BDB0
0x1003a932  call    __SEH_prolog4
0x1003a937  mov     eax, dword_1003D210
0x1003a93c  test    eax, eax
0x1003a93e  jg      short loc_1003A944
0x1003a940  xor     eax, eax
0x1003a942  jmp     short loc_1003A9B4
0x1003a944  dec     eax
0x1003a945  mov     dword_1003D210, eax
0x1003a94a  xor     esi, esi
0x1003a94c  inc     esi
0x1003a94d  mov     [ebp+var_1C], esi
0x1003a950  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1003a957  call    ___scrt_acquire_startup_lock
0x1003a95c  mov     byte ptr [ebp+var_20], al
0x1003a95f  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1003a962  cmp     ___scrt_current_native_startup_state, 2
0x1003a969  jnz     short loc_1003A9DA
0x1003a96b  call    ___scrt_dllmain_uninitialize_c
0x1003a970  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1003a975  call    __RTC_Terminate
0x1003a97a  mov     ___scrt_current_native_startup_state, 0
0x1003a984  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1003a98b  call    loc_1003A9C7
0x1003a990  push    0
0x1003a992  push    [ebp+arg_0]
0x1003a995  call    ___scrt_uninitialize_crt
0x1003a99a  pop     ecx
0x1003a99b  pop     ecx
0x1003a99c  xor     ecx, ecx
0x1003a99e  test    al, al
0x1003a9a0  cmovz   esi, ecx
0x1003a9a3  mov     [ebp+var_1C], esi
0x1003a9a6  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003a9ad  call    loc_1003A9D4
0x1003a9b2  mov     eax, esi
0x1003a9b4  mov     ecx, [ebp+ms_exc.registration.Next]
0x1003a9b7  mov     large fs:0, ecx
0x1003a9be  pop     ecx
0x1003a9bf  pop     edi
0x1003a9c0  pop     esi
0x1003a9c1  pop     ebx
0x1003a9c2  leave
0x1003a9c3  retn
0x1003a9c4  mov     esi, [ebp+var_1C]
0x1003a9c7  push    [ebp+var_20]
0x1003a9ca  call    ___scrt_release_startup_lock
0x1003a9cf  pop     ecx
0x1003a9d0  retn
0x1003a9d1  mov     esi, [ebp+var_1C]
0x1003a9d4  call    ___scrt_dllmain_uninitialize_critical
0x1003a9d9  retn
0x1003a9da  push    7
0x1003a9dc  call    ___scrt_fastfail
```
