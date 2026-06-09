# __DllMainCRTStartup

- ea: `0x1800039d4`
- end: `0x180003be0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003990`

## callees

- `0x1800036a0`
- `0x180003760`
- `0x1800039d4`
- `0x180003dd6`
- `0x180005790`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800090A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090A4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800090A4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x1800039d4  mov     [rsp+lpvReserved], r8
0x1800039d9  mov     [rsp+arg_8], edx
0x1800039dd  mov     [rsp+arg_0], rcx
0x1800039e2  push    rbx
0x1800039e3  push    rsi
0x1800039e4  push    rdi
0x1800039e5  sub     rsp, 0F0h
0x1800039ec  mov     edi, edx
0x1800039ee  mov     rsi, rcx
0x1800039f1  mov     ebx, 1
0x1800039f6  cmp     edx, ebx
0x1800039f8  ja      short loc_180003A00
0x1800039fa  mov     cs:__native_dllmain_reason, edx
0x180003a00  test    edx, edx
0x180003a02  jnz     short loc_180003A17
0x180003a04  cmp     cs:dword_1800090A0, edx
0x180003a0a  jnz     short loc_180003A17
0x180003a0c  xor     ebx, ebx
0x180003a0e  mov     [rsp+108h+var_E8], ebx
0x180003a12  jmp     loc_180003BC4
0x180003a17  lea     eax, [rdx-1]
0x180003a1a  cmp     eax, 1
0x180003a1d  ja      loc_180003AA4
0x180003a23  mov     rax, cs:_pRawDllMain
0x180003a2a  test    rax, rax
0x180003a2d  jz      short loc_180003A65
0x180003a2f  cmp     edx, 1
0x180003a32  jnz     short loc_180003A3A
0x180003a34  mov     cs:dword_1800090A4, edx
0x180003a3a  mov     r8, [rsp+108h+lpvReserved]
0x180003a42  call    cs:__guard_dispatch_icall_fptr
0x180003a48  mov     ebx, eax
0x180003a4a  mov     [rsp+108h+var_E8], eax
0x180003a4e  jmp     short loc_180003A65
0x180003a50  xor     ebx, ebx
0x180003a52  mov     [rsp+108h+var_E8], ebx
0x180003a56  mov     edi, [rsp+108h+arg_8]
0x180003a5d  mov     rsi, [rsp+108h+arg_0]
0x180003a65  test    ebx, ebx
0x180003a67  jz      loc_180003BC4
0x180003a6d  mov     r8, [rsp+108h+lpvReserved]
0x180003a75  mov     edx, edi
0x180003a77  mov     rcx, rsi
0x180003a7a  call    _CRT_INIT
0x180003a7f  mov     ebx, eax
0x180003a81  mov     [rsp+108h+var_E8], eax
0x180003a85  jmp     short loc_180003A9C
0x180003a87  xor     ebx, ebx
0x180003a89  mov     [rsp+108h+var_E8], ebx
0x180003a8d  mov     edi, [rsp+108h+arg_8]
0x180003a94  mov     rsi, [rsp+108h+arg_0]
0x180003a9c  test    ebx, ebx
0x180003a9e  jz      loc_180003BC4
0x180003aa4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180003aac  mov     edx, edi; fdwReason
0x180003aae  mov     rcx, rsi; hinstDLL
0x180003ab1  call    DllMain
0x180003ab6  mov     ebx, eax
0x180003ab8  mov     [rsp+108h+var_E8], eax
0x180003abc  jmp     short loc_180003AD3
0x180003abe  xor     ebx, ebx
0x180003ac0  mov     [rsp+108h+var_E8], ebx
0x180003ac4  mov     edi, [rsp+108h+arg_8]
0x180003acb  mov     rsi, [rsp+108h+arg_0]
0x180003ad3  cmp     edi, 1
0x180003ad6  jnz     short loc_180003B4F
0x180003ad8  test    ebx, ebx
0x180003ada  jnz     short loc_180003B4F
0x180003adc  xor     r8d, r8d; lpvReserved
0x180003adf  xor     edx, edx; fdwReason
0x180003ae1  mov     rcx, rsi; hinstDLL
0x180003ae4  call    DllMain
0x180003ae9  jmp     short loc_180003AFE
0x180003aeb  mov     edi, [rsp+108h+arg_8]
0x180003af2  mov     rsi, [rsp+108h+arg_0]
0x180003afa  mov     ebx, [rsp+108h+var_E8]
0x180003afe  xor     r8d, r8d
0x180003b01  xor     edx, edx
0x180003b03  mov     rcx, rsi
0x180003b06  call    _CRT_INIT
0x180003b0b  jmp     short loc_180003B20
0x180003b0d  mov     edi, [rsp+108h+arg_8]
0x180003b14  mov     rsi, [rsp+108h+arg_0]
0x180003b1c  mov     ebx, [rsp+108h+var_E8]
0x180003b20  mov     rax, cs:_pRawDllMain
0x180003b27  test    rax, rax
0x180003b2a  jz      short loc_180003B4F
0x180003b2c  xor     r8d, r8d
0x180003b2f  xor     edx, edx
0x180003b31  mov     rcx, rsi
0x180003b34  call    cs:__guard_dispatch_icall_fptr
0x180003b3a  jmp     short loc_180003B4F
0x180003b3c  mov     edi, [rsp+108h+arg_8]
0x180003b43  mov     rsi, [rsp+108h+arg_0]
0x180003b4b  mov     ebx, [rsp+108h+var_E8]
0x180003b4f  test    edi, edi
0x180003b51  jz      short loc_180003B58
0x180003b53  cmp     edi, 3
0x180003b56  jnz     short loc_180003BC4
0x180003b58  mov     r8, [rsp+108h+lpvReserved]
0x180003b60  mov     edx, edi
0x180003b62  mov     rcx, rsi
0x180003b65  call    _CRT_INIT
0x180003b6a  mov     ebx, eax
0x180003b6c  mov     [rsp+108h+var_E8], eax
0x180003b70  jmp     short loc_180003B87
0x180003b72  xor     ebx, ebx
0x180003b74  mov     [rsp+108h+var_E8], ebx
0x180003b78  mov     edi, [rsp+108h+arg_8]
0x180003b7f  mov     rsi, [rsp+108h+arg_0]
0x180003b87  mov     rax, cs:_pRawDllMain
0x180003b8e  test    rax, rax
0x180003b91  jz      short loc_180003BC4
0x180003b93  cmp     cs:dword_1800090A4, 0
0x180003b9a  jz      short loc_180003BC4
0x180003b9c  mov     r8, [rsp+108h+lpvReserved]
0x180003ba4  mov     edx, edi
0x180003ba6  mov     rcx, rsi
0x180003ba9  call    cs:__guard_dispatch_icall_fptr
0x180003baf  mov     ebx, eax
0x180003bb1  mov     [rsp+108h+var_E8], eax
0x180003bb5  jmp     short loc_180003BC4
0x180003bb7  xor     ebx, ebx
0x180003bb9  mov     [rsp+108h+var_E8], ebx
0x180003bbd  mov     edi, [rsp+108h+arg_8]
0x180003bc4  cmp     edi, 1
0x180003bc7  ja      short loc_180003BD3
0x180003bc9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180003bd3  mov     eax, ebx
0x180003bd5  add     rsp, 0F0h
0x180003bdc  pop     rdi
0x180003bdd  pop     rsi
0x180003bde  pop     rbx
0x180003bdf  retn
0x1800057d0  push    rbp
0x1800057d2  sub     rsp, 20h
0x1800057d6  mov     rbp, rdx
0x1800057d9  mov     rax, [rcx]
0x1800057dc  mov     edx, [rax]
0x1800057de  mov     [rbp+0A8h], rcx
0x1800057e5  mov     [rbp+28h], edx
0x1800057e8  mov     eax, [rbp+28h]
0x1800057eb  cmp     eax, 0E06D7363h
0x1800057f0  jnz     short loc_180005806
0x1800057f2  mov     rdx, [rbp+0A8h]
0x1800057f9  mov     ecx, [rbp+28h]
0x1800057fc  call    _XcptFilter_0
0x180005801  mov     [rbp+30h], eax
0x180005804  jmp     short loc_18000580D
0x180005806  mov     dword ptr [rbp+30h], 0
0x18000580d  mov     eax, [rbp+30h]
0x180005810  add     rsp, 20h
0x180005814  pop     rbp
0x180005815  retn
0x180005817  push    rbp
0x180005819  sub     rsp, 20h
0x18000581d  mov     rbp, rdx
0x180005820  mov     rax, [rcx]
0x180005823  mov     edx, [rax]
0x180005825  mov     [rbp+0B0h], rcx
0x18000582c  mov     [rbp+38h], edx
0x18000582f  mov     eax, [rbp+38h]
0x180005832  cmp     eax, 0E06D7363h
0x180005837  jnz     short loc_18000584D
0x180005839  mov     rdx, [rbp+0B0h]
0x180005840  mov     ecx, [rbp+38h]
0x180005843  call    _XcptFilter_0
0x180005848  mov     [rbp+40h], eax
0x18000584b  jmp     short loc_180005854
0x18000584d  mov     dword ptr [rbp+40h], 0
0x180005854  mov     eax, [rbp+40h]
0x180005857  add     rsp, 20h
0x18000585b  pop     rbp
0x18000585c  retn
0x18000585e  push    rbp
0x180005860  sub     rsp, 20h
0x180005864  mov     rbp, rdx
0x180005867  mov     rax, [rcx]
0x18000586a  mov     edx, [rax]
0x18000586c  mov     [rbp+0B8h], rcx
0x180005873  mov     [rbp+48h], edx
0x180005876  mov     eax, [rbp+48h]
0x180005879  cmp     eax, 0E06D7363h
0x18000587e  jnz     short loc_180005894
0x180005880  mov     rdx, [rbp+0B8h]
0x180005887  mov     ecx, [rbp+48h]
0x18000588a  call    _XcptFilter_0
0x18000588f  mov     [rbp+50h], eax
0x180005892  jmp     short loc_18000589B
0x180005894  mov     dword ptr [rbp+50h], 0
0x18000589b  mov     eax, [rbp+50h]
0x18000589e  add     rsp, 20h
0x1800058a2  pop     rbp
0x1800058a3  retn
0x1800058a5  push    rbp
0x1800058a7  sub     rsp, 20h
0x1800058ab  mov     rbp, rdx
0x1800058ae  mov     rax, [rcx]
0x1800058b1  mov     edx, [rax]
0x1800058b3  mov     [rbp+0C0h], rcx
0x1800058ba  mov     [rbp+58h], edx
0x1800058bd  mov     eax, [rbp+58h]
0x1800058c0  cmp     eax, 0E06D7363h
0x1800058c5  jnz     short loc_1800058DB
0x1800058c7  mov     rdx, [rbp+0C0h]
0x1800058ce  mov     ecx, [rbp+58h]
0x1800058d1  call    _XcptFilter_0
0x1800058d6  mov     [rbp+60h], eax
0x1800058d9  jmp     short loc_1800058E2
0x1800058db  mov     dword ptr [rbp+60h], 0
0x1800058e2  mov     eax, [rbp+60h]
0x1800058e5  add     rsp, 20h
0x1800058e9  pop     rbp
0x1800058ea  retn
0x1800058ec  push    rbp
0x1800058ee  sub     rsp, 20h
0x1800058f2  mov     rbp, rdx
0x1800058f5  mov     rax, [rcx]
0x1800058f8  mov     edx, [rax]
0x1800058fa  mov     [rbp+0C8h], rcx
0x180005901  mov     [rbp+68h], edx
0x180005904  mov     eax, [rbp+68h]
0x180005907  cmp     eax, 0E06D7363h
0x18000590c  jnz     short loc_180005922
0x18000590e  mov     rdx, [rbp+0C8h]
0x180005915  mov     ecx, [rbp+68h]
0x180005918  call    _XcptFilter_0
0x18000591d  mov     [rbp+70h], eax
0x180005920  jmp     short loc_180005929
0x180005922  mov     dword ptr [rbp+70h], 0
0x180005929  mov     eax, [rbp+70h]
0x18000592c  add     rsp, 20h
0x180005930  pop     rbp
0x180005931  retn
0x180005933  push    rbp
0x180005935  sub     rsp, 20h
0x180005939  mov     rbp, rdx
0x18000593c  mov     rax, [rcx]
0x18000593f  mov     edx, [rax]
0x180005941  mov     [rbp+0D0h], rcx
0x180005948  mov     [rbp+78h], edx
0x18000594b  mov     eax, [rbp+78h]
0x18000594e  cmp     eax, 0E06D7363h
0x180005953  jnz     short loc_18000596C
0x180005955  mov     rdx, [rbp+0D0h]
0x18000595c  mov     ecx, [rbp+78h]
0x18000595f  call    _XcptFilter_0
0x180005964  mov     [rbp+80h], eax
0x18000596a  jmp     short loc_180005976
0x18000596c  mov     dword ptr [rbp+80h], 0
0x180005976  mov     eax, [rbp+80h]
0x18000597c  add     rsp, 20h
0x180005980  pop     rbp
0x180005981  retn
0x180005983  push    rbp
0x180005985  sub     rsp, 20h
0x180005989  mov     rbp, rdx
0x18000598c  mov     rax, [rcx]
0x18000598f  mov     edx, [rax]
0x180005991  mov     [rbp+0D8h], rcx
0x180005998  mov     [rbp+88h], edx
0x18000599e  mov     eax, [rbp+88h]
0x1800059a4  cmp     eax, 0E06D7363h
0x1800059a9  jnz     short loc_1800059C5
0x1800059ab  mov     rdx, [rbp+0D8h]
0x1800059b2  mov     ecx, [rbp+88h]
0x1800059b8  call    _XcptFilter_0
0x1800059bd  mov     [rbp+90h], eax
0x1800059c3  jmp     short loc_1800059CF
0x1800059c5  mov     dword ptr [rbp+90h], 0
0x1800059cf  mov     eax, [rbp+90h]
0x1800059d5  add     rsp, 20h
0x1800059d9  pop     rbp
0x1800059da  retn
0x1800059dc  push    rbp
0x1800059de  sub     rsp, 20h
0x1800059e2  mov     rbp, rdx
0x1800059e5  mov     rax, [rcx]
0x1800059e8  mov     edx, [rax]
0x1800059ea  mov     [rbp+0E0h], rcx
0x1800059f1  mov     [rbp+98h], edx
0x1800059f7  mov     eax, [rbp+98h]
0x1800059fd  cmp     eax, 0E06D7363h
0x180005a02  jnz     short loc_180005A1E
0x180005a04  mov     rdx, [rbp+0E0h]
0x180005a0b  mov     ecx, [rbp+98h]
0x180005a11  call    _XcptFilter_0
0x180005a16  mov     [rbp+0A0h], eax
0x180005a1c  jmp     short loc_180005A28
0x180005a1e  mov     dword ptr [rbp+0A0h], 0
0x180005a28  mov     eax, [rbp+0A0h]
0x180005a2e  add     rsp, 20h
0x180005a32  pop     rbp
0x180005a33  retn
0x180005a35  push    rbp
0x180005a37  sub     rsp, 20h
0x180005a3b  mov     rbp, rdx
0x180005a3e  cmp     dword ptr [rbp+118h], 1
0x180005a45  ja      short loc_180005A51
0x180005a47  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
