# __DllMainCRTStartup

- ea: `0x1002e384`
- end: `0x1002e492`
- name: `__DllMainCRTStartup`
- size: `270`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1002e361`

## callees

- `0x10015000`
- `0x1002e1ef`
- `0x1002e384`
- `0x1002e492`
- `0x10034c80`
- `0x10034cc5`

## pseudocode

```c
int __cdecl _DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // eax
  BOOL v4; // eax
  int v5; // edi

  v3 = 1;
  if ( !fdwReason && !dword_10044700 )
    return 0;
  if ( fdwReason == 1 || fdwReason == 2 )
  {
    if ( _pRawDllMain )
      v3 = _pRawDllMain(hinstDLL, fdwReason, lpvReserved);
    if ( !v3 || !_CRT_INIT((int)hinstDLL, fdwReason, (int)lpvReserved) )
      return 0;
  }
  v4 = DllMain(hinstDLL, fdwReason, lpvReserved);
  v5 = v4;
  if ( fdwReason == 1 && !v4 )
  {
    DllMain(hinstDLL, 0, lpvReserved);
    _CRT_INIT((int)hinstDLL, 0, (int)lpvReserved);
    if ( _pRawDllMain )
      _pRawDllMain(hinstDLL, 0, lpvReserved);
  }
  if ( !fdwReason || fdwReason == 3 )
  {
    v5 = _CRT_INIT((int)hinstDLL, fdwReason, (int)lpvReserved) != 0 ? v5 : 0;
    if ( v5 )
    {
      if ( _pRawDllMain )
        return _pRawDllMain(hinstDLL, fdwReason, lpvReserved);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1002e384  push    0Ch
0x1002e386  push    offset stru_1003CF30
0x1002e38b  call    __SEH_prolog4
0x1002e390  xor     eax, eax
0x1002e392  inc     eax
0x1002e393  mov     esi, [ebp+fdwReason]
0x1002e396  test    esi, esi
0x1002e398  jnz     short loc_1002E3A6
0x1002e39a  cmp     dword_10044700, esi
0x1002e3a0  jz      loc_1002E48A
0x1002e3a6  and     [ebp+ms_exc.registration.TryLevel], 0
0x1002e3aa  cmp     esi, 1
0x1002e3ad  jz      short loc_1002E3B4
0x1002e3af  cmp     esi, 2
0x1002e3b2  jnz     short loc_1002E3E9
0x1002e3b4  mov     ecx, ds:__pRawDllMain
0x1002e3ba  test    ecx, ecx
0x1002e3bc  jz      short loc_1002E3CA
0x1002e3be  push    [ebp+lpvReserved]
0x1002e3c1  push    esi
0x1002e3c2  push    [ebp+hinstDLL]
0x1002e3c5  call    ecx ; __pRawDllMain
0x1002e3c7  mov     [ebp+var_1C], eax
0x1002e3ca  test    eax, eax
0x1002e3cc  jz      loc_1002E483
0x1002e3d2  push    [ebp+lpvReserved]
0x1002e3d5  push    esi
0x1002e3d6  push    [ebp+hinstDLL]
0x1002e3d9  call    __CRT_INIT@12
0x1002e3de  mov     [ebp+var_1C], eax
0x1002e3e1  test    eax, eax
0x1002e3e3  jz      loc_1002E483
0x1002e3e9  mov     ebx, [ebp+lpvReserved]
0x1002e3ec  push    ebx; lpvReserved
0x1002e3ed  push    esi; fdwReason
0x1002e3ee  push    [ebp+hinstDLL]; hinstDLL
0x1002e3f1  call    _DllMain@12
0x1002e3f6  mov     edi, eax
0x1002e3f8  mov     [ebp+var_1C], edi
0x1002e3fb  cmp     esi, 1
0x1002e3fe  jnz     short loc_1002E428
0x1002e400  test    edi, edi
0x1002e402  jnz     short loc_1002E428
0x1002e404  push    ebx; lpvReserved
0x1002e405  push    eax; fdwReason
0x1002e406  push    [ebp+hinstDLL]; hinstDLL
0x1002e409  call    _DllMain@12
0x1002e40e  push    ebx
0x1002e40f  push    edi
0x1002e410  push    [ebp+hinstDLL]
0x1002e413  call    __CRT_INIT@12
0x1002e418  mov     eax, ds:__pRawDllMain
0x1002e41d  test    eax, eax
0x1002e41f  jz      short loc_1002E428
0x1002e421  push    ebx
0x1002e422  push    edi
0x1002e423  push    [ebp+hinstDLL]
0x1002e426  call    eax ; __pRawDllMain
0x1002e428  test    esi, esi
0x1002e42a  jz      short loc_1002E431
0x1002e42c  cmp     esi, 3
0x1002e42f  jnz     short loc_1002E45B
0x1002e431  push    ebx
0x1002e432  push    esi
0x1002e433  push    [ebp+hinstDLL]
0x1002e436  call    __CRT_INIT@12
0x1002e43b  neg     eax
0x1002e43d  sbb     eax, eax
0x1002e43f  and     edi, eax
0x1002e441  mov     [ebp+var_1C], edi
0x1002e444  jz      short loc_1002E45B
0x1002e446  mov     eax, ds:__pRawDllMain
0x1002e44b  test    eax, eax
0x1002e44d  jz      short loc_1002E45B
0x1002e44f  push    ebx
0x1002e450  push    esi
0x1002e451  push    [ebp+hinstDLL]
0x1002e454  call    eax ; __pRawDllMain
0x1002e456  mov     edi, eax
0x1002e458  mov     [ebp+var_1C], edi
0x1002e45b  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1002e462  mov     eax, edi
0x1002e464  jmp     short loc_1002E48C
0x1002e466  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1002e469  mov     eax, [ecx]
0x1002e46b  push    ecx
0x1002e46c  push    dword ptr [eax]
0x1002e46e  push    [ebp+lpvReserved]
0x1002e471  push    [ebp+fdwReason]
0x1002e474  push    [ebp+hinstDLL]
0x1002e477  call    ___DllXcptFilter
0x1002e47c  add     esp, 14h
0x1002e47f  retn
0x1002e480  mov     esp, [ebp+ms_exc.old_esp]
0x1002e483  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1002e48a  xor     eax, eax
0x1002e48c  call    __SEH_epilog4
0x1002e491  retn
```
