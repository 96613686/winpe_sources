# dllmain_dispatch

- ea: `0x10035398`
- end: `0x100354a1`
- name: `dllmain_dispatch`
- size: `265`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x100354e0`

## callees

- `0x10006480`
- `0x10035170`
- `0x10035398`
- `0x100354a7`
- `0x10035638`
- `0x10035aa0`

## pseudocode

```c
int __cdecl dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v4; // ebx
  int v5; // esi
  BOOL v6; // eax

  if ( !fdwReason && dword_1003A710 <= 0 )
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
0x10035398  push    0Ch
0x1003539a  push    offset stru_100374D8
0x1003539f  call    __SEH_prolog4
0x100353a4  mov     edi, [ebp+fdwReason]
0x100353a7  test    edi, edi
0x100353a9  jnz     short loc_100353BA
0x100353ab  cmp     dword_1003A710, edi
0x100353b1  jg      short loc_100353BA
0x100353b3  xor     eax, eax
0x100353b5  jmp     loc_10035491
0x100353ba  mov     [ebp+ms_exc.registration.TryLevel], 0
0x100353c1  cmp     edi, 1
0x100353c4  jz      short loc_100353D0
0x100353c6  cmp     edi, 2
0x100353c9  jz      short loc_100353D0
0x100353cb  mov     ebx, [ebp+lpvReserved]
0x100353ce  jmp     short loc_10035401
0x100353d0  mov     ebx, [ebp+lpvReserved]
0x100353d3  push    ebx
0x100353d4  push    edi
0x100353d5  push    [ebp+hinstDLL]
0x100353d8  call    dllmain_raw
0x100353dd  mov     esi, eax
0x100353df  mov     [ebp+var_1C], esi
0x100353e2  test    esi, esi
0x100353e4  jz      loc_10035488
0x100353ea  push    ebx
0x100353eb  push    edi
0x100353ec  push    [ebp+hinstDLL]
0x100353ef  call    dllmain_crt_dispatch
0x100353f4  mov     esi, eax
0x100353f6  mov     [ebp+var_1C], esi
0x100353f9  test    esi, esi
0x100353fb  jz      loc_10035488
0x10035401  push    ebx; lpvReserved
0x10035402  push    edi; fdwReason
0x10035403  push    [ebp+hinstDLL]; hinstDLL
0x10035406  call    _DllMain@12; DllMain(x,x,x)
0x1003540b  mov     esi, eax
0x1003540d  mov     [ebp+var_1C], esi
0x10035410  cmp     edi, 1
0x10035413  jnz     short loc_10035437
0x10035415  test    esi, esi
0x10035417  jnz     short loc_10035437
0x10035419  push    ebx; lpvReserved
0x1003541a  push    eax; fdwReason
0x1003541b  push    [ebp+hinstDLL]; hinstDLL
0x1003541e  call    _DllMain@12; DllMain(x,x,x)
0x10035423  push    ebx
0x10035424  push    esi
0x10035425  push    [ebp+hinstDLL]
0x10035428  call    dllmain_crt_dispatch
0x1003542d  push    ebx
0x1003542e  push    esi
0x1003542f  push    [ebp+hinstDLL]
0x10035432  call    dllmain_raw
0x10035437  test    edi, edi
0x10035439  jz      short loc_10035440
0x1003543b  cmp     edi, 3
0x1003543e  jnz     short loc_10035488
0x10035440  push    ebx
0x10035441  push    edi
0x10035442  push    [ebp+hinstDLL]
0x10035445  call    dllmain_crt_dispatch
0x1003544a  mov     esi, eax
0x1003544c  mov     [ebp+var_1C], esi
0x1003544f  test    esi, esi
0x10035451  jz      short loc_10035488
0x10035453  push    ebx
0x10035454  push    edi
0x10035455  push    [ebp+hinstDLL]
0x10035458  call    dllmain_raw
0x1003545d  mov     esi, eax
0x1003545f  jmp     short loc_10035485
0x10035461  mov     ecx, [ebp+ms_exc.exc_ptr]
0x10035464  mov     eax, [ecx]
0x10035466  push    ecx; ExceptionPtr
0x10035467  push    dword ptr [eax]; ExceptionNum
0x10035469  push    offset dllmain_crt_dispatch; int
0x1003546e  push    [ebp+lpvReserved]; int
0x10035471  push    [ebp+fdwReason]; int
0x10035474  push    [ebp+hinstDLL]; int
0x10035477  call    ___scrt_dllmain_exception_filter
0x1003547c  add     esp, 18h
0x1003547f  retn
0x10035480  mov     esp, [ebp+ms_exc.old_esp]
0x10035483  xor     esi, esi
0x10035485  mov     [ebp+var_1C], esi
0x10035488  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1003548f  mov     eax, esi
0x10035491  mov     ecx, [ebp+ms_exc.registration.Next]
0x10035494  mov     large fs:0, ecx
0x1003549b  pop     ecx
0x1003549c  pop     edi
0x1003549d  pop     esi
0x1003549e  pop     ebx
0x1003549f  leave
0x100354a0  retn
```
