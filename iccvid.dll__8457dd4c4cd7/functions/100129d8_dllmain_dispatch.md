# dllmain_dispatch

- ea: `0x100129d8`
- end: `0x10012ae1`
- name: `dllmain_dispatch`
- size: `265`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x10012b20`

## callees

- `0x10009841`
- `0x100127b0`
- `0x100129d8`
- `0x10012ae7`
- `0x10012d4d`
- `0x10013010`

## pseudocode

```c
int __cdecl dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v4; // ebx
  int v5; // esi
  BOOL v6; // eax

  if ( !fdwReason && dword_10014950 <= 0 )
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
      dllmain_crt_dispatch(hinstDLL, 0, v4);
      dllmain_raw(hinstDLL, 0, v4);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, v4);
      if ( v5 )
        return dllmain_raw(hinstDLL, fdwReason, v4);
    }
    return v5;
  }
  v4 = lpvReserved;
  v5 = dllmain_raw(hinstDLL, fdwReason, lpvReserved);
  if ( v5 )
  {
    v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
    if ( v5 )
      goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x100129d8  push    0Ch
0x100129da  push    offset stru_100135E8
0x100129df  call    __SEH_prolog4
0x100129e4  mov     edi, [ebp+fdwReason]
0x100129e7  test    edi, edi
0x100129e9  jnz     short loc_100129FA
0x100129eb  cmp     dword_10014950, edi
0x100129f1  jg      short loc_100129FA
0x100129f3  xor     eax, eax
0x100129f5  jmp     loc_10012AD1
0x100129fa  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10012a01  cmp     edi, 1
0x10012a04  jz      short loc_10012A10
0x10012a06  cmp     edi, 2
0x10012a09  jz      short loc_10012A10
0x10012a0b  mov     ebx, [ebp+lpvReserved]
0x10012a0e  jmp     short loc_10012A41
0x10012a10  mov     ebx, [ebp+lpvReserved]
0x10012a13  push    ebx
0x10012a14  push    edi
0x10012a15  push    [ebp+hinstDLL]
0x10012a18  call    dllmain_raw
0x10012a1d  mov     esi, eax
0x10012a1f  mov     [ebp+var_1C], esi
0x10012a22  test    esi, esi
0x10012a24  jz      loc_10012AC8
0x10012a2a  push    ebx
0x10012a2b  push    edi
0x10012a2c  push    [ebp+hinstDLL]
0x10012a2f  call    dllmain_crt_dispatch
0x10012a34  mov     esi, eax
0x10012a36  mov     [ebp+var_1C], esi
0x10012a39  test    esi, esi
0x10012a3b  jz      loc_10012AC8
0x10012a41  push    ebx; lpvReserved
0x10012a42  push    edi; fdwReason
0x10012a43  push    [ebp+hinstDLL]; hinstDLL
0x10012a46  call    _DllMain@12; DllMain(x,x,x)
0x10012a4b  mov     esi, eax
0x10012a4d  mov     [ebp+var_1C], esi
0x10012a50  cmp     edi, 1
0x10012a53  jnz     short loc_10012A77
0x10012a55  test    esi, esi
0x10012a57  jnz     short loc_10012A77
0x10012a59  push    ebx; lpvReserved
0x10012a5a  push    eax; fdwReason
0x10012a5b  push    [ebp+hinstDLL]; hinstDLL
0x10012a5e  call    _DllMain@12; DllMain(x,x,x)
0x10012a63  push    ebx
0x10012a64  push    esi
0x10012a65  push    [ebp+hinstDLL]
0x10012a68  call    dllmain_crt_dispatch
0x10012a6d  push    ebx
0x10012a6e  push    esi
0x10012a6f  push    [ebp+hinstDLL]
0x10012a72  call    dllmain_raw
0x10012a77  test    edi, edi
0x10012a79  jz      short loc_10012A80
0x10012a7b  cmp     edi, 3
0x10012a7e  jnz     short loc_10012AC8
0x10012a80  push    ebx
0x10012a81  push    edi
0x10012a82  push    [ebp+hinstDLL]
0x10012a85  call    dllmain_crt_dispatch
0x10012a8a  mov     esi, eax
0x10012a8c  mov     [ebp+var_1C], esi
0x10012a8f  test    esi, esi
0x10012a91  jz      short loc_10012AC8
0x10012a93  push    ebx
0x10012a94  push    edi
0x10012a95  push    [ebp+hinstDLL]
0x10012a98  call    dllmain_raw
0x10012a9d  mov     esi, eax
0x10012a9f  jmp     short loc_10012AC5
0x10012aa1  mov     ecx, [ebp+ms_exc.exc_ptr]
0x10012aa4  mov     eax, [ecx]
0x10012aa6  push    ecx; ExceptionPtr
0x10012aa7  push    dword ptr [eax]; ExceptionNum
0x10012aa9  push    offset dllmain_crt_dispatch; int
0x10012aae  push    [ebp+lpvReserved]; int
0x10012ab1  push    [ebp+fdwReason]; int
0x10012ab4  push    [ebp+hinstDLL]; int
0x10012ab7  call    ___scrt_dllmain_exception_filter
0x10012abc  add     esp, 18h
0x10012abf  retn
0x10012ac0  mov     esp, [ebp+ms_exc.old_esp]
0x10012ac3  xor     esi, esi
0x10012ac5  mov     [ebp+var_1C], esi
0x10012ac8  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10012acf  mov     eax, esi
0x10012ad1  mov     ecx, [ebp+ms_exc.registration.Next]
0x10012ad4  mov     large fs:0, ecx
0x10012adb  pop     ecx
0x10012adc  pop     edi
0x10012add  pop     esi
0x10012ade  pop     ebx
0x10012adf  leave
0x10012ae0  retn
```
