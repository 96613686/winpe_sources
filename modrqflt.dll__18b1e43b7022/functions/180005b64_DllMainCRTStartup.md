# __DllMainCRTStartup

- ea: `0x180005b64`
- end: `0x180005d70`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005b20`

## callees

- `0x1800058f0`
- `0x180005b64`
- `0x180005d9a`
- `0x180005f78`
- `0x180007c00`

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
  if ( (_DWORD)fdwReason || dword_18000C0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C0A4 = 1;
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
            if ( dword_18000C0A4 )
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
0x180005b64  mov     [rsp+lpvReserved], r8
0x180005b69  mov     [rsp+arg_8], edx
0x180005b6d  mov     [rsp+arg_0], rcx
0x180005b72  push    rbx
0x180005b73  push    rsi
0x180005b74  push    rdi
0x180005b75  sub     rsp, 0F0h
0x180005b7c  mov     edi, edx
0x180005b7e  mov     rsi, rcx
0x180005b81  mov     ebx, 1
0x180005b86  cmp     edx, ebx
0x180005b88  ja      short loc_180005B90
0x180005b8a  mov     cs:__native_dllmain_reason, edx
0x180005b90  test    edx, edx
0x180005b92  jnz     short loc_180005BA7
0x180005b94  cmp     cs:dword_18000C0A0, edx
0x180005b9a  jnz     short loc_180005BA7
0x180005b9c  xor     ebx, ebx
0x180005b9e  mov     [rsp+108h+var_E8], ebx
0x180005ba2  jmp     loc_180005D54
0x180005ba7  lea     eax, [rdx-1]
0x180005baa  cmp     eax, 1
0x180005bad  ja      loc_180005C34
0x180005bb3  mov     rax, cs:_pRawDllMain
0x180005bba  test    rax, rax
0x180005bbd  jz      short loc_180005BF5
0x180005bbf  cmp     edx, 1
0x180005bc2  jnz     short loc_180005BCA
0x180005bc4  mov     cs:dword_18000C0A4, edx
0x180005bca  mov     r8, [rsp+108h+lpvReserved]
0x180005bd2  call    cs:__guard_dispatch_icall_fptr
0x180005bd8  mov     ebx, eax
0x180005bda  mov     [rsp+108h+var_E8], eax
0x180005bde  jmp     short loc_180005BF5
0x180005be0  xor     ebx, ebx
0x180005be2  mov     [rsp+108h+var_E8], ebx
0x180005be6  mov     edi, [rsp+108h+arg_8]
0x180005bed  mov     rsi, [rsp+108h+arg_0]
0x180005bf5  test    ebx, ebx
0x180005bf7  jz      loc_180005D54
0x180005bfd  mov     r8, [rsp+108h+lpvReserved]
0x180005c05  mov     edx, edi
0x180005c07  mov     rcx, rsi
0x180005c0a  call    _CRT_INIT
0x180005c0f  mov     ebx, eax
0x180005c11  mov     [rsp+108h+var_E8], eax
0x180005c15  jmp     short loc_180005C2C
0x180005c17  xor     ebx, ebx
0x180005c19  mov     [rsp+108h+var_E8], ebx
0x180005c1d  mov     edi, [rsp+108h+arg_8]
0x180005c24  mov     rsi, [rsp+108h+arg_0]
0x180005c2c  test    ebx, ebx
0x180005c2e  jz      loc_180005D54
0x180005c34  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180005c3c  mov     edx, edi; fdwReason
0x180005c3e  mov     rcx, rsi; hinstDLL
0x180005c41  call    DllMain
0x180005c46  mov     ebx, eax
0x180005c48  mov     [rsp+108h+var_E8], eax
0x180005c4c  jmp     short loc_180005C63
0x180005c4e  xor     ebx, ebx
0x180005c50  mov     [rsp+108h+var_E8], ebx
0x180005c54  mov     edi, [rsp+108h+arg_8]
0x180005c5b  mov     rsi, [rsp+108h+arg_0]
0x180005c63  cmp     edi, 1
0x180005c66  jnz     short loc_180005CDF
0x180005c68  test    ebx, ebx
0x180005c6a  jnz     short loc_180005CDF
0x180005c6c  xor     r8d, r8d; lpvReserved
0x180005c6f  xor     edx, edx; fdwReason
0x180005c71  mov     rcx, rsi; hinstDLL
0x180005c74  call    DllMain
0x180005c79  jmp     short loc_180005C8E
0x180005c7b  mov     edi, [rsp+108h+arg_8]
0x180005c82  mov     rsi, [rsp+108h+arg_0]
0x180005c8a  mov     ebx, [rsp+108h+var_E8]
0x180005c8e  xor     r8d, r8d
0x180005c91  xor     edx, edx
0x180005c93  mov     rcx, rsi
0x180005c96  call    _CRT_INIT
0x180005c9b  jmp     short loc_180005CB0
0x180005c9d  mov     edi, [rsp+108h+arg_8]
0x180005ca4  mov     rsi, [rsp+108h+arg_0]
0x180005cac  mov     ebx, [rsp+108h+var_E8]
0x180005cb0  mov     rax, cs:_pRawDllMain
0x180005cb7  test    rax, rax
0x180005cba  jz      short loc_180005CDF
0x180005cbc  xor     r8d, r8d
0x180005cbf  xor     edx, edx
0x180005cc1  mov     rcx, rsi
0x180005cc4  call    cs:__guard_dispatch_icall_fptr
0x180005cca  jmp     short loc_180005CDF
0x180005ccc  mov     edi, [rsp+108h+arg_8]
0x180005cd3  mov     rsi, [rsp+108h+arg_0]
0x180005cdb  mov     ebx, [rsp+108h+var_E8]
0x180005cdf  test    edi, edi
0x180005ce1  jz      short loc_180005CE8
0x180005ce3  cmp     edi, 3
0x180005ce6  jnz     short loc_180005D54
0x180005ce8  mov     r8, [rsp+108h+lpvReserved]
0x180005cf0  mov     edx, edi
0x180005cf2  mov     rcx, rsi
0x180005cf5  call    _CRT_INIT
0x180005cfa  mov     ebx, eax
0x180005cfc  mov     [rsp+108h+var_E8], eax
0x180005d00  jmp     short loc_180005D17
0x180005d02  xor     ebx, ebx
0x180005d04  mov     [rsp+108h+var_E8], ebx
0x180005d08  mov     edi, [rsp+108h+arg_8]
0x180005d0f  mov     rsi, [rsp+108h+arg_0]
0x180005d17  mov     rax, cs:_pRawDllMain
0x180005d1e  test    rax, rax
0x180005d21  jz      short loc_180005D54
0x180005d23  cmp     cs:dword_18000C0A4, 0
0x180005d2a  jz      short loc_180005D54
0x180005d2c  mov     r8, [rsp+108h+lpvReserved]
0x180005d34  mov     edx, edi
0x180005d36  mov     rcx, rsi
0x180005d39  call    cs:__guard_dispatch_icall_fptr
0x180005d3f  mov     ebx, eax
0x180005d41  mov     [rsp+108h+var_E8], eax
0x180005d45  jmp     short loc_180005D54
0x180005d47  xor     ebx, ebx
0x180005d49  mov     [rsp+108h+var_E8], ebx
0x180005d4d  mov     edi, [rsp+108h+arg_8]
0x180005d54  cmp     edi, 1
0x180005d57  ja      short loc_180005D63
0x180005d59  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180005d63  mov     eax, ebx
0x180005d65  add     rsp, 0F0h
0x180005d6c  pop     rdi
0x180005d6d  pop     rsi
0x180005d6e  pop     rbx
0x180005d6f  retn
0x180007c70  push    rbp
0x180007c72  sub     rsp, 20h
0x180007c76  mov     rbp, rdx
0x180007c79  mov     rax, [rcx]
0x180007c7c  mov     edx, [rax]
0x180007c7e  mov     [rbp+0A8h], rcx
0x180007c85  mov     [rbp+28h], edx
0x180007c88  mov     eax, [rbp+28h]
0x180007c8b  cmp     eax, 0E06D7363h
0x180007c90  jnz     short loc_180007CA6
0x180007c92  mov     rdx, [rbp+0A8h]
0x180007c99  mov     ecx, [rbp+28h]
0x180007c9c  call    _XcptFilter_0
0x180007ca1  mov     [rbp+30h], eax
0x180007ca4  jmp     short loc_180007CAD
0x180007ca6  mov     dword ptr [rbp+30h], 0
0x180007cad  mov     eax, [rbp+30h]
0x180007cb0  add     rsp, 20h
0x180007cb4  pop     rbp
0x180007cb5  retn
0x180007cb7  push    rbp
0x180007cb9  sub     rsp, 20h
0x180007cbd  mov     rbp, rdx
0x180007cc0  mov     rax, [rcx]
0x180007cc3  mov     edx, [rax]
0x180007cc5  mov     [rbp+0B0h], rcx
0x180007ccc  mov     [rbp+38h], edx
0x180007ccf  mov     eax, [rbp+38h]
0x180007cd2  cmp     eax, 0E06D7363h
0x180007cd7  jnz     short loc_180007CED
0x180007cd9  mov     rdx, [rbp+0B0h]
0x180007ce0  mov     ecx, [rbp+38h]
0x180007ce3  call    _XcptFilter_0
0x180007ce8  mov     [rbp+40h], eax
0x180007ceb  jmp     short loc_180007CF4
0x180007ced  mov     dword ptr [rbp+40h], 0
0x180007cf4  mov     eax, [rbp+40h]
0x180007cf7  add     rsp, 20h
0x180007cfb  pop     rbp
0x180007cfc  retn
0x180007cfe  push    rbp
0x180007d00  sub     rsp, 20h
0x180007d04  mov     rbp, rdx
0x180007d07  mov     rax, [rcx]
0x180007d0a  mov     edx, [rax]
0x180007d0c  mov     [rbp+0B8h], rcx
0x180007d13  mov     [rbp+48h], edx
0x180007d16  mov     eax, [rbp+48h]
0x180007d19  cmp     eax, 0E06D7363h
0x180007d1e  jnz     short loc_180007D34
0x180007d20  mov     rdx, [rbp+0B8h]
0x180007d27  mov     ecx, [rbp+48h]
0x180007d2a  call    _XcptFilter_0
0x180007d2f  mov     [rbp+50h], eax
0x180007d32  jmp     short loc_180007D3B
0x180007d34  mov     dword ptr [rbp+50h], 0
0x180007d3b  mov     eax, [rbp+50h]
0x180007d3e  add     rsp, 20h
0x180007d42  pop     rbp
0x180007d43  retn
0x180007d45  push    rbp
0x180007d47  sub     rsp, 20h
0x180007d4b  mov     rbp, rdx
0x180007d4e  mov     rax, [rcx]
0x180007d51  mov     edx, [rax]
0x180007d53  mov     [rbp+0C0h], rcx
0x180007d5a  mov     [rbp+58h], edx
0x180007d5d  mov     eax, [rbp+58h]
0x180007d60  cmp     eax, 0E06D7363h
0x180007d65  jnz     short loc_180007D7B
0x180007d67  mov     rdx, [rbp+0C0h]
0x180007d6e  mov     ecx, [rbp+58h]
0x180007d71  call    _XcptFilter_0
0x180007d76  mov     [rbp+60h], eax
0x180007d79  jmp     short loc_180007D82
0x180007d7b  mov     dword ptr [rbp+60h], 0
0x180007d82  mov     eax, [rbp+60h]
0x180007d85  add     rsp, 20h
0x180007d89  pop     rbp
0x180007d8a  retn
0x180007d8c  push    rbp
0x180007d8e  sub     rsp, 20h
0x180007d92  mov     rbp, rdx
0x180007d95  mov     rax, [rcx]
0x180007d98  mov     edx, [rax]
0x180007d9a  mov     [rbp+0C8h], rcx
0x180007da1  mov     [rbp+68h], edx
0x180007da4  mov     eax, [rbp+68h]
0x180007da7  cmp     eax, 0E06D7363h
0x180007dac  jnz     short loc_180007DC2
0x180007dae  mov     rdx, [rbp+0C8h]
0x180007db5  mov     ecx, [rbp+68h]
0x180007db8  call    _XcptFilter_0
0x180007dbd  mov     [rbp+70h], eax
0x180007dc0  jmp     short loc_180007DC9
0x180007dc2  mov     dword ptr [rbp+70h], 0
0x180007dc9  mov     eax, [rbp+70h]
0x180007dcc  add     rsp, 20h
0x180007dd0  pop     rbp
0x180007dd1  retn
0x180007dd3  push    rbp
0x180007dd5  sub     rsp, 20h
0x180007dd9  mov     rbp, rdx
0x180007ddc  mov     rax, [rcx]
0x180007ddf  mov     edx, [rax]
0x180007de1  mov     [rbp+0D0h], rcx
0x180007de8  mov     [rbp+78h], edx
0x180007deb  mov     eax, [rbp+78h]
0x180007dee  cmp     eax, 0E06D7363h
0x180007df3  jnz     short loc_180007E0C
0x180007df5  mov     rdx, [rbp+0D0h]
0x180007dfc  mov     ecx, [rbp+78h]
0x180007dff  call    _XcptFilter_0
0x180007e04  mov     [rbp+80h], eax
0x180007e0a  jmp     short loc_180007E16
0x180007e0c  mov     dword ptr [rbp+80h], 0
0x180007e16  mov     eax, [rbp+80h]
0x180007e1c  add     rsp, 20h
0x180007e20  pop     rbp
0x180007e21  retn
0x180007e23  push    rbp
0x180007e25  sub     rsp, 20h
0x180007e29  mov     rbp, rdx
0x180007e2c  mov     rax, [rcx]
0x180007e2f  mov     edx, [rax]
0x180007e31  mov     [rbp+0D8h], rcx
0x180007e38  mov     [rbp+88h], edx
0x180007e3e  mov     eax, [rbp+88h]
0x180007e44  cmp     eax, 0E06D7363h
0x180007e49  jnz     short loc_180007E65
0x180007e4b  mov     rdx, [rbp+0D8h]
0x180007e52  mov     ecx, [rbp+88h]
0x180007e58  call    _XcptFilter_0
0x180007e5d  mov     [rbp+90h], eax
0x180007e63  jmp     short loc_180007E6F
0x180007e65  mov     dword ptr [rbp+90h], 0
0x180007e6f  mov     eax, [rbp+90h]
0x180007e75  add     rsp, 20h
0x180007e79  pop     rbp
0x180007e7a  retn
0x180007e7c  push    rbp
0x180007e7e  sub     rsp, 20h
0x180007e82  mov     rbp, rdx
0x180007e85  mov     rax, [rcx]
0x180007e88  mov     edx, [rax]
0x180007e8a  mov     [rbp+0E0h], rcx
0x180007e91  mov     [rbp+98h], edx
0x180007e97  mov     eax, [rbp+98h]
0x180007e9d  cmp     eax, 0E06D7363h
0x180007ea2  jnz     short loc_180007EBE
0x180007ea4  mov     rdx, [rbp+0E0h]
0x180007eab  mov     ecx, [rbp+98h]
0x180007eb1  call    _XcptFilter_0
0x180007eb6  mov     [rbp+0A0h], eax
0x180007ebc  jmp     short loc_180007EC8
0x180007ebe  mov     dword ptr [rbp+0A0h], 0
0x180007ec8  mov     eax, [rbp+0A0h]
0x180007ece  add     rsp, 20h
0x180007ed2  pop     rbp
0x180007ed3  retn
0x180007ed5  push    rbp
0x180007ed7  sub     rsp, 20h
0x180007edb  mov     rbp, rdx
0x180007ede  cmp     dword ptr [rbp+118h], 1
0x180007ee5  ja      short loc_180007EF1
0x180007ee7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
