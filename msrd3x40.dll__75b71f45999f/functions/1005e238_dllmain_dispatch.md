# dllmain_dispatch

- ea: `0x1005e238`
- end: `0x1005e341`
- name: `dllmain_dispatch`
- size: `265`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1005e380`

## callees

- `0x1004f860`
- `0x1005e010`
- `0x1005e238`
- `0x1005e347`
- `0x1005e4c0`
- `0x1005eb30`

## pseudocode

```c
int __cdecl dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v4; // ebx
  int v5; // esi
  BOOL v6; // eax

  if ( !fdwReason && dword_10066590 <= 0 )
    return 0;
  if ( fdwReason != 1 && fdwReason != 2 )
  {
    v4 = lpvReserved;
LABEL_9:
    v6 = DllMain(hinstDLL, fdwReason, v4);
    v5 = v6;
    if ( fdwReason == 1 && !v6 )
    {
      DllMain(hinstDLL, 0, v4);
      dllmain_crt_dispatch(hinstDLL, 0, (int)v4);
      dllmain_raw(hinstDLL, 0, (int)v4);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, (int)v4);
      if ( v5 )
        return dllmain_raw(hinstDLL, fdwReason, (int)v4);
    }
    return v5;
  }
  v4 = lpvReserved;
  v5 = dllmain_raw(hinstDLL, fdwReason, (int)lpvReserved);
  if ( v5 )
  {
    v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, (int)lpvReserved);
    if ( v5 )
      goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x1005e238  push    0Ch
0x1005e23a  push    offset stru_10064DA8
0x1005e23f  call    __SEH_prolog4
0x1005e244  mov     edi, [ebp+fdwReason]
0x1005e247  test    edi, edi
0x1005e249  jnz     short loc_1005E25A
0x1005e24b  cmp     dword_10066590, edi
0x1005e251  jg      short loc_1005E25A
0x1005e253  xor     eax, eax
0x1005e255  jmp     loc_1005E331
0x1005e25a  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1005e261  cmp     edi, 1
0x1005e264  jz      short loc_1005E270
0x1005e266  cmp     edi, 2
0x1005e269  jz      short loc_1005E270
0x1005e26b  mov     ebx, [ebp+lpvReserved]
0x1005e26e  jmp     short loc_1005E2A1
0x1005e270  mov     ebx, [ebp+lpvReserved]
0x1005e273  push    ebx; int
0x1005e274  push    edi; unsigned int
0x1005e275  push    [ebp+hinstDLL]; void *
0x1005e278  call    dllmain_raw
0x1005e27d  mov     esi, eax
0x1005e27f  mov     [ebp+var_1C], esi
0x1005e282  test    esi, esi
0x1005e284  jz      loc_1005E328
0x1005e28a  push    ebx; int
0x1005e28b  push    edi; int
0x1005e28c  push    [ebp+hinstDLL]; void *
0x1005e28f  call    dllmain_crt_dispatch
0x1005e294  mov     esi, eax
0x1005e296  mov     [ebp+var_1C], esi
0x1005e299  test    esi, esi
0x1005e29b  jz      loc_1005E328
0x1005e2a1  push    ebx; lpvReserved
0x1005e2a2  push    edi; fdwReason
0x1005e2a3  push    [ebp+hinstDLL]; hinstDLL
0x1005e2a6  call    _DllMain@12; DllMain(x,x,x)
0x1005e2ab  mov     esi, eax
0x1005e2ad  mov     [ebp+var_1C], esi
0x1005e2b0  cmp     edi, 1
0x1005e2b3  jnz     short loc_1005E2D7
0x1005e2b5  test    esi, esi
0x1005e2b7  jnz     short loc_1005E2D7
0x1005e2b9  push    ebx; lpvReserved
0x1005e2ba  push    eax; fdwReason
0x1005e2bb  push    [ebp+hinstDLL]; hinstDLL
0x1005e2be  call    _DllMain@12; DllMain(x,x,x)
0x1005e2c3  push    ebx; int
0x1005e2c4  push    esi; int
0x1005e2c5  push    [ebp+hinstDLL]; void *
0x1005e2c8  call    dllmain_crt_dispatch
0x1005e2cd  push    ebx; int
0x1005e2ce  push    esi; unsigned int
0x1005e2cf  push    [ebp+hinstDLL]; void *
0x1005e2d2  call    dllmain_raw
0x1005e2d7  test    edi, edi
0x1005e2d9  jz      short loc_1005E2E0
0x1005e2db  cmp     edi, 3
0x1005e2de  jnz     short loc_1005E328
0x1005e2e0  push    ebx; int
0x1005e2e1  push    edi; int
0x1005e2e2  push    [ebp+hinstDLL]; void *
0x1005e2e5  call    dllmain_crt_dispatch
0x1005e2ea  mov     esi, eax
0x1005e2ec  mov     [ebp+var_1C], esi
0x1005e2ef  test    esi, esi
0x1005e2f1  jz      short loc_1005E328
0x1005e2f3  push    ebx; int
0x1005e2f4  push    edi; unsigned int
0x1005e2f5  push    [ebp+hinstDLL]; void *
0x1005e2f8  call    dllmain_raw
0x1005e2fd  mov     esi, eax
0x1005e2ff  jmp     short loc_1005E325
0x1005e301  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1005e304  mov     eax, [ecx]
0x1005e306  push    ecx; ExceptionPtr
0x1005e307  push    dword ptr [eax]; ExceptionNum
0x1005e309  push    offset dllmain_crt_dispatch; int
0x1005e30e  push    [ebp+lpvReserved]; int
0x1005e311  push    [ebp+fdwReason]; int
0x1005e314  push    [ebp+hinstDLL]; void *
0x1005e317  call    ___scrt_dllmain_exception_filter
0x1005e31c  add     esp, 18h
0x1005e31f  retn
0x1005e320  mov     esp, [ebp+ms_exc.old_esp]
0x1005e323  xor     esi, esi
0x1005e325  mov     [ebp+var_1C], esi
0x1005e328  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1005e32f  mov     eax, esi
0x1005e331  mov     ecx, [ebp+ms_exc.registration.Next]
0x1005e334  mov     large fs:0, ecx
0x1005e33b  pop     ecx
0x1005e33c  pop     edi
0x1005e33d  pop     esi
0x1005e33e  pop     ebx
0x1005e33f  leave
0x1005e340  retn
```
