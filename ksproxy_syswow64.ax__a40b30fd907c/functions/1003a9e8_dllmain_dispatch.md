# dllmain_dispatch

- ea: `0x1003a9e8`
- end: `0x1003aaf1`
- name: `dllmain_dispatch`
- size: `265`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1003ab30`

## callees

- `0x1000816d`
- `0x1003a7c0`
- `0x1003a9e8`
- `0x1003aaf7`
- `0x1003ad10`
- `0x1003b130`

## pseudocode

```c
int __cdecl dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v4; // ebx
  int v5; // esi
  BOOL v6; // eax

  if ( !fdwReason && dword_1003D210 <= 0 )
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
      dllmain_crt_dispatch((int)hinstDLL, 0, (int)v4);
      dllmain_raw(hinstDLL, 0, v4);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v5 = dllmain_crt_dispatch((int)hinstDLL, fdwReason, (int)v4);
      if ( v5 )
        return dllmain_raw(hinstDLL, fdwReason, v4);
    }
    return v5;
  }
  v4 = lpvReserved;
  v5 = dllmain_raw(hinstDLL, fdwReason, lpvReserved);
  if ( v5 )
  {
    v5 = dllmain_crt_dispatch((int)hinstDLL, fdwReason, (int)lpvReserved);
    if ( v5 )
      goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x1003a9e8  push    0Ch
0x1003a9ea  push    offset stru_1003BDD8
0x1003a9ef  call    __SEH_prolog4
0x1003a9f4  mov     edi, [ebp+fdwReason]
0x1003a9f7  test    edi, edi
0x1003a9f9  jnz     short loc_1003AA0A
0x1003a9fb  cmp     dword_1003D210, edi
0x1003aa01  jg      short loc_1003AA0A
0x1003aa03  xor     eax, eax
0x1003aa05  jmp     loc_1003AAE1
0x1003aa0a  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1003aa11  cmp     edi, 1
0x1003aa14  jz      short loc_1003AA20
0x1003aa16  cmp     edi, 2
0x1003aa19  jz      short loc_1003AA20
0x1003aa1b  mov     ebx, [ebp+lpvReserved]
0x1003aa1e  jmp     short loc_1003AA51
0x1003aa20  mov     ebx, [ebp+lpvReserved]
0x1003aa23  push    ebx
0x1003aa24  push    edi
0x1003aa25  push    [ebp+hinstDLL]
0x1003aa28  call    dllmain_raw
0x1003aa2d  mov     esi, eax
0x1003aa2f  mov     [ebp+var_1C], esi
0x1003aa32  test    esi, esi
0x1003aa34  jz      loc_1003AAD8
0x1003aa3a  push    ebx
0x1003aa3b  push    edi
0x1003aa3c  push    [ebp+hinstDLL]
0x1003aa3f  call    dllmain_crt_dispatch
0x1003aa44  mov     esi, eax
0x1003aa46  mov     [ebp+var_1C], esi
0x1003aa49  test    esi, esi
0x1003aa4b  jz      loc_1003AAD8
0x1003aa51  push    ebx; lpvReserved
0x1003aa52  push    edi; fdwReason
0x1003aa53  push    [ebp+hinstDLL]; hinstDLL
0x1003aa56  call    _DllMain@12; DllMain(x,x,x)
0x1003aa5b  mov     esi, eax
0x1003aa5d  mov     [ebp+var_1C], esi
0x1003aa60  cmp     edi, 1
0x1003aa63  jnz     short loc_1003AA87
0x1003aa65  test    esi, esi
0x1003aa67  jnz     short loc_1003AA87
0x1003aa69  push    ebx; lpvReserved
0x1003aa6a  push    eax; fdwReason
0x1003aa6b  push    [ebp+hinstDLL]; hinstDLL
0x1003aa6e  call    _DllMain@12; DllMain(x,x,x)
0x1003aa73  push    ebx
0x1003aa74  push    esi
0x1003aa75  push    [ebp+hinstDLL]
0x1003aa78  call    dllmain_crt_dispatch
0x1003aa7d  push    ebx
0x1003aa7e  push    esi
0x1003aa7f  push    [ebp+hinstDLL]
0x1003aa82  call    dllmain_raw
0x1003aa87  test    edi, edi
0x1003aa89  jz      short loc_1003AA90
0x1003aa8b  cmp     edi, 3
0x1003aa8e  jnz     short loc_1003AAD8
0x1003aa90  push    ebx
0x1003aa91  push    edi
0x1003aa92  push    [ebp+hinstDLL]
0x1003aa95  call    dllmain_crt_dispatch
0x1003aa9a  mov     esi, eax
0x1003aa9c  mov     [ebp+var_1C], esi
0x1003aa9f  test    esi, esi
0x1003aaa1  jz      short loc_1003AAD8
0x1003aaa3  push    ebx
0x1003aaa4  push    edi
0x1003aaa5  push    [ebp+hinstDLL]
0x1003aaa8  call    dllmain_raw
0x1003aaad  mov     esi, eax
0x1003aaaf  jmp     short loc_1003AAD5
0x1003aab1  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1003aab4  mov     eax, [ecx]
0x1003aab6  push    ecx; ExceptionPtr
0x1003aab7  push    dword ptr [eax]; ExceptionNum
0x1003aab9  push    offset dllmain_crt_dispatch; CD3DSurfaceAllocator *
0x1003aabe  push    [ebp+lpvReserved]; int
0x1003aac1  push    [ebp+fdwReason]; int
0x1003aac4  push    [ebp+hinstDLL]; int
0x1003aac7  call    ___scrt_dllmain_exception_filter
0x1003aacc  add     esp, 18h
0x1003aacf  retn
0x1003aad0  mov     esp, [ebp+ms_exc.old_esp]
0x1003aad3  xor     esi, esi
0x1003aad5  mov     [ebp+var_1C], esi
0x1003aad8  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003aadf  mov     eax, esi
0x1003aae1  mov     ecx, [ebp+ms_exc.registration.Next]
0x1003aae4  mov     large fs:0, ecx
0x1003aaeb  pop     ecx
0x1003aaec  pop     edi
0x1003aaed  pop     esi
0x1003aaee  pop     ebx
0x1003aaef  leave
0x1003aaf0  retn
```
