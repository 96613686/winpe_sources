# __DllMainCRTStartup

- ea: `0x1004d142`
- end: `0x1004d3c9`
- name: `__DllMainCRTStartup`
- size: `647`
- prototype: `int __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1004d100`

## callees

- `0x1000f260`
- `0x1001c6d0`
- `0x1004cf0c`
- `0x1004d11c`
- `0x1004d142`
- `0x1004db84`

## pseudocode

```c
int __stdcall _DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v4; // [esp+10h] [ebp-1Ch]

  v4 = 1;
  if ( fdwReason <= 1 )
    __native_dllmain_reason = fdwReason;
  if ( fdwReason || dword_100519E0 )
  {
    if ( fdwReason != 1 && fdwReason != 2 )
      goto LABEL_14;
    if ( _pRawDllMain )
    {
      if ( fdwReason == 1 )
        dword_100519E4 = 1;
      v4 = _pRawDllMain(_pRawDllMain, hinstDLL, fdwReason, lpvReserved);
    }
    if ( v4 )
    {
      v4 = _CRT_INIT(hinstDLL, fdwReason, lpvReserved);
      if ( v4 )
      {
LABEL_14:
        v4 = DllMain(hinstDLL, fdwReason, lpvReserved);
        if ( fdwReason == 1 && !v4 )
        {
          DllMain(hinstDLL, 0, 0);
          _CRT_INIT(hinstDLL, 0, 0);
          if ( _pRawDllMain )
            _pRawDllMain(_pRawDllMain, hinstDLL, 0, 0);
        }
        if ( !fdwReason || fdwReason == 3 )
        {
          v4 = _CRT_INIT(hinstDLL, fdwReason, lpvReserved);
          if ( _pRawDllMain )
          {
            if ( dword_100519E4 )
              v4 = _pRawDllMain(_pRawDllMain, hinstDLL, fdwReason, lpvReserved);
          }
        }
      }
    }
  }
  else
  {
    v4 = 0;
  }
  if ( fdwReason <= 1 )
    __native_dllmain_reason = -1;
  return v4;
}

```

## disassembly

```asm
0x1004d142  push    0Ch
0x1004d144  push    offset stru_10050338
0x1004d149  call    __SEH_prolog4
0x1004d14e  mov     [ebp+var_1C], 1
0x1004d155  xor     esi, esi
0x1004d157  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d15a  mov     eax, [ebp+fdwReason]
0x1004d15d  cmp     eax, 1
0x1004d160  ja      short loc_1004D167
0x1004d162  mov     ___native_dllmain_reason, eax
0x1004d167  cmp     [ebp+fdwReason], 0
0x1004d16b  jnz     short loc_1004D17E
0x1004d16d  cmp     dword_100519E0, 0
0x1004d174  jnz     short loc_1004D17E
0x1004d176  mov     [ebp+var_1C], esi
0x1004d179  jmp     loc_1004D397
0x1004d17e  mov     eax, [ebp+fdwReason]
0x1004d181  cmp     eax, 1
0x1004d184  jz      short loc_1004D18F
0x1004d186  cmp     eax, 2
0x1004d189  jnz     loc_1004D22C
0x1004d18f  mov     edi, __pRawDllMain
0x1004d195  test    edi, edi
0x1004d197  jz      short loc_1004D1E3
0x1004d199  mov     [ebp+ms_exc.registration.TryLevel], 1
0x1004d1a0  cmp     [ebp+fdwReason], 1
0x1004d1a4  jnz     short loc_1004D1B0
0x1004d1a6  mov     dword_100519E4, 1
0x1004d1b0  push    [ebp+lpvReserved]
0x1004d1b3  push    [ebp+fdwReason]
0x1004d1b6  push    [ebp+hinstDLL]
0x1004d1b9  mov     ecx, edi
0x1004d1bb  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004d1c1  call    edi ; __pRawDllMain
0x1004d1c3  mov     [ebp+var_1C], eax
0x1004d1c6  jmp     short loc_1004D1E0
0x1004d1c8  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d1cb  mov     eax, [ecx]
0x1004d1cd  push    ecx
0x1004d1ce  push    dword ptr [eax]
0x1004d1d0  call    ___CppXcptFilter
0x1004d1d5  pop     ecx
0x1004d1d6  pop     ecx
0x1004d1d7  retn
0x1004d1d8  mov     esp, [ebp+ms_exc.old_esp]
0x1004d1db  xor     esi, esi
0x1004d1dd  mov     [ebp+var_1C], esi
0x1004d1e0  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d1e3  cmp     [ebp+var_1C], 0
0x1004d1e7  jz      loc_1004D397
0x1004d1ed  mov     [ebp+ms_exc.registration.TryLevel], 2
0x1004d1f4  push    [ebp+lpvReserved]
0x1004d1f7  push    [ebp+fdwReason]
0x1004d1fa  push    [ebp+hinstDLL]
0x1004d1fd  call    __CRT_INIT@12; _CRT_INIT(x,x,x)
0x1004d202  mov     [ebp+var_1C], eax
0x1004d205  jmp     short loc_1004D21F
0x1004d207  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d20a  mov     eax, [ecx]
0x1004d20c  push    ecx
0x1004d20d  push    dword ptr [eax]
0x1004d20f  call    ___CppXcptFilter
0x1004d214  pop     ecx
0x1004d215  pop     ecx
0x1004d216  retn
0x1004d217  mov     esp, [ebp+ms_exc.old_esp]
0x1004d21a  xor     esi, esi
0x1004d21c  mov     [ebp+var_1C], esi
0x1004d21f  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d222  cmp     [ebp+var_1C], 0
0x1004d226  jz      loc_1004D397
0x1004d22c  mov     [ebp+ms_exc.registration.TryLevel], 3
0x1004d233  push    [ebp+lpvReserved]; lpvReserved
0x1004d236  push    [ebp+fdwReason]; fdwReason
0x1004d239  push    [ebp+hinstDLL]; hinstDLL
0x1004d23c  call    _DllMain@12; DllMain(x,x,x)
0x1004d241  mov     [ebp+var_1C], eax
0x1004d244  jmp     short loc_1004D25E
0x1004d246  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d249  mov     eax, [ecx]
0x1004d24b  push    ecx
0x1004d24c  push    dword ptr [eax]
0x1004d24e  call    ___CppXcptFilter
0x1004d253  pop     ecx
0x1004d254  pop     ecx
0x1004d255  retn
0x1004d256  mov     esp, [ebp+ms_exc.old_esp]
0x1004d259  xor     esi, esi
0x1004d25b  mov     [ebp+var_1C], esi
0x1004d25e  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d261  cmp     [ebp+fdwReason], 1
0x1004d265  jnz     loc_1004D305
0x1004d26b  cmp     [ebp+var_1C], 0
0x1004d26f  jnz     loc_1004D305
0x1004d275  mov     [ebp+ms_exc.registration.TryLevel], 4
0x1004d27c  push    esi; lpvReserved
0x1004d27d  push    esi; fdwReason
0x1004d27e  push    [ebp+hinstDLL]; hinstDLL
0x1004d281  call    _DllMain@12; DllMain(x,x,x)
0x1004d286  jmp     short loc_1004D29D
0x1004d288  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d28b  mov     eax, [ecx]
0x1004d28d  push    ecx
0x1004d28e  push    dword ptr [eax]
0x1004d290  call    ___CppXcptFilter
0x1004d295  pop     ecx
0x1004d296  pop     ecx
0x1004d297  retn
0x1004d298  mov     esp, [ebp+ms_exc.old_esp]
0x1004d29b  xor     esi, esi
0x1004d29d  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d2a0  mov     [ebp+ms_exc.registration.TryLevel], 5
0x1004d2a7  push    esi
0x1004d2a8  push    esi
0x1004d2a9  push    [ebp+hinstDLL]
0x1004d2ac  call    __CRT_INIT@12; _CRT_INIT(x,x,x)
0x1004d2b1  jmp     short loc_1004D2C8
0x1004d2b3  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d2b6  mov     eax, [ecx]
0x1004d2b8  push    ecx
0x1004d2b9  push    dword ptr [eax]
0x1004d2bb  call    ___CppXcptFilter
0x1004d2c0  pop     ecx
0x1004d2c1  pop     ecx
0x1004d2c2  retn
0x1004d2c3  mov     esp, [ebp+ms_exc.old_esp]
0x1004d2c6  xor     esi, esi
0x1004d2c8  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d2cb  mov     edi, __pRawDllMain
0x1004d2d1  test    edi, edi
0x1004d2d3  jz      short loc_1004D305
0x1004d2d5  mov     [ebp+ms_exc.registration.TryLevel], 6
0x1004d2dc  push    esi
0x1004d2dd  push    esi
0x1004d2de  push    [ebp+hinstDLL]
0x1004d2e1  mov     ecx, edi
0x1004d2e3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004d2e9  call    edi ; __pRawDllMain
0x1004d2eb  jmp     short loc_1004D302
0x1004d2ed  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d2f0  mov     eax, [ecx]
0x1004d2f2  push    ecx
0x1004d2f3  push    dword ptr [eax]
0x1004d2f5  call    ___CppXcptFilter
0x1004d2fa  pop     ecx
0x1004d2fb  pop     ecx
0x1004d2fc  retn
0x1004d2fd  mov     esp, [ebp+ms_exc.old_esp]
0x1004d300  xor     esi, esi
0x1004d302  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d305  mov     eax, [ebp+fdwReason]
0x1004d308  test    eax, eax
0x1004d30a  jz      short loc_1004D315
0x1004d30c  cmp     eax, 3
0x1004d30f  jnz     loc_1004D397
0x1004d315  mov     [ebp+ms_exc.registration.TryLevel], 7
0x1004d31c  push    [ebp+lpvReserved]
0x1004d31f  push    [ebp+fdwReason]
0x1004d322  push    [ebp+hinstDLL]
0x1004d325  call    __CRT_INIT@12; _CRT_INIT(x,x,x)
0x1004d32a  mov     [ebp+var_1C], eax
0x1004d32d  jmp     short loc_1004D347
0x1004d32f  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d332  mov     eax, [ecx]
0x1004d334  push    ecx
0x1004d335  push    dword ptr [eax]
0x1004d337  call    ___CppXcptFilter
0x1004d33c  pop     ecx
0x1004d33d  pop     ecx
0x1004d33e  retn
0x1004d33f  mov     esp, [ebp+ms_exc.old_esp]
0x1004d342  xor     esi, esi
0x1004d344  mov     [ebp+var_1C], esi
0x1004d347  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d34a  mov     edi, __pRawDllMain
0x1004d350  test    edi, edi
0x1004d352  jz      short loc_1004D397
0x1004d354  cmp     dword_100519E4, 0
0x1004d35b  jz      short loc_1004D397
0x1004d35d  mov     [ebp+ms_exc.registration.TryLevel], 8
0x1004d364  push    [ebp+lpvReserved]
0x1004d367  push    [ebp+fdwReason]
0x1004d36a  push    [ebp+hinstDLL]
0x1004d36d  mov     ecx, edi
0x1004d36f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004d375  call    edi ; __pRawDllMain
0x1004d377  mov     [ebp+var_1C], eax
0x1004d37a  jmp     short loc_1004D394
0x1004d37c  mov     ecx, [ebp+ms_exc.exc_ptr]
0x1004d37f  mov     eax, [ecx]
0x1004d381  push    ecx
0x1004d382  push    dword ptr [eax]
0x1004d384  call    ___CppXcptFilter
0x1004d389  pop     ecx
0x1004d38a  pop     ecx
0x1004d38b  retn
0x1004d38c  mov     esp, [ebp+ms_exc.old_esp]
0x1004d38f  xor     esi, esi
0x1004d391  mov     [ebp+var_1C], esi
0x1004d394  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1004d397  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1004d39e  call    loc_1004D3B8
0x1004d3a3  mov     eax, [ebp+var_1C]
0x1004d3a6  mov     ecx, [ebp+ms_exc.registration.Next]
0x1004d3a9  mov     large fs:0, ecx
0x1004d3b0  pop     ecx
0x1004d3b1  pop     edi
0x1004d3b2  pop     esi
0x1004d3b3  pop     ebx
0x1004d3b4  leave
0x1004d3b5  retn    0Ch
0x1004d3b8  cmp     [ebp+fdwReason], 1
0x1004d3bc  ja      short loc_1004D3C8
0x1004d3be  mov     ___native_dllmain_reason, 0FFFFFFFFh
0x1004d3c8  retn
```
