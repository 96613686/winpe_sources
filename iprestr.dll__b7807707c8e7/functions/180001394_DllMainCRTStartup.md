# __DllMainCRTStartup

- ea: `0x180001394`
- end: `0x1800015a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001350`

## callees

- `0x180001120`
- `0x180001394`
- `0x180001685`
- `0x180001858`
- `0x180004b10`

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
0x180001394  mov     [rsp+lpvReserved], r8
0x180001399  mov     [rsp+arg_8], edx
0x18000139d  mov     [rsp+arg_0], rcx
0x1800013a2  push    rbx
0x1800013a3  push    rsi
0x1800013a4  push    rdi
0x1800013a5  sub     rsp, 0F0h
0x1800013ac  mov     edi, edx
0x1800013ae  mov     rsi, rcx
0x1800013b1  mov     ebx, 1
0x1800013b6  cmp     edx, ebx
0x1800013b8  ja      short loc_1800013C0
0x1800013ba  mov     cs:__native_dllmain_reason, edx
0x1800013c0  test    edx, edx
0x1800013c2  jnz     short loc_1800013D7
0x1800013c4  cmp     cs:dword_1800090A0, edx
0x1800013ca  jnz     short loc_1800013D7
0x1800013cc  xor     ebx, ebx
0x1800013ce  mov     [rsp+108h+var_E8], ebx
0x1800013d2  jmp     loc_180001584
0x1800013d7  lea     eax, [rdx-1]
0x1800013da  cmp     eax, 1
0x1800013dd  ja      loc_180001464
0x1800013e3  mov     rax, cs:_pRawDllMain
0x1800013ea  test    rax, rax
0x1800013ed  jz      short loc_180001425
0x1800013ef  cmp     edx, 1
0x1800013f2  jnz     short loc_1800013FA
0x1800013f4  mov     cs:dword_1800090A4, edx
0x1800013fa  mov     r8, [rsp+108h+lpvReserved]
0x180001402  call    cs:__guard_dispatch_icall_fptr
0x180001408  mov     ebx, eax
0x18000140a  mov     [rsp+108h+var_E8], eax
0x18000140e  jmp     short loc_180001425
0x180001410  xor     ebx, ebx
0x180001412  mov     [rsp+108h+var_E8], ebx
0x180001416  mov     edi, [rsp+108h+arg_8]
0x18000141d  mov     rsi, [rsp+108h+arg_0]
0x180001425  test    ebx, ebx
0x180001427  jz      loc_180001584
0x18000142d  mov     r8, [rsp+108h+lpvReserved]
0x180001435  mov     edx, edi
0x180001437  mov     rcx, rsi
0x18000143a  call    _CRT_INIT
0x18000143f  mov     ebx, eax
0x180001441  mov     [rsp+108h+var_E8], eax
0x180001445  jmp     short loc_18000145C
0x180001447  xor     ebx, ebx
0x180001449  mov     [rsp+108h+var_E8], ebx
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  test    ebx, ebx
0x18000145e  jz      loc_180001584
0x180001464  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000146c  mov     edx, edi; fdwReason
0x18000146e  mov     rcx, rsi; hinstDLL
0x180001471  call    DllMain
0x180001476  mov     ebx, eax
0x180001478  mov     [rsp+108h+var_E8], eax
0x18000147c  jmp     short loc_180001493
0x18000147e  xor     ebx, ebx
0x180001480  mov     [rsp+108h+var_E8], ebx
0x180001484  mov     edi, [rsp+108h+arg_8]
0x18000148b  mov     rsi, [rsp+108h+arg_0]
0x180001493  cmp     edi, 1
0x180001496  jnz     short loc_18000150F
0x180001498  test    ebx, ebx
0x18000149a  jnz     short loc_18000150F
0x18000149c  xor     r8d, r8d; lpvReserved
0x18000149f  xor     edx, edx; fdwReason
0x1800014a1  mov     rcx, rsi; hinstDLL
0x1800014a4  call    DllMain
0x1800014a9  jmp     short loc_1800014BE
0x1800014ab  mov     edi, [rsp+108h+arg_8]
0x1800014b2  mov     rsi, [rsp+108h+arg_0]
0x1800014ba  mov     ebx, [rsp+108h+var_E8]
0x1800014be  xor     r8d, r8d
0x1800014c1  xor     edx, edx
0x1800014c3  mov     rcx, rsi
0x1800014c6  call    _CRT_INIT
0x1800014cb  jmp     short loc_1800014E0
0x1800014cd  mov     edi, [rsp+108h+arg_8]
0x1800014d4  mov     rsi, [rsp+108h+arg_0]
0x1800014dc  mov     ebx, [rsp+108h+var_E8]
0x1800014e0  mov     rax, cs:_pRawDllMain
0x1800014e7  test    rax, rax
0x1800014ea  jz      short loc_18000150F
0x1800014ec  xor     r8d, r8d
0x1800014ef  xor     edx, edx
0x1800014f1  mov     rcx, rsi
0x1800014f4  call    cs:__guard_dispatch_icall_fptr
0x1800014fa  jmp     short loc_18000150F
0x1800014fc  mov     edi, [rsp+108h+arg_8]
0x180001503  mov     rsi, [rsp+108h+arg_0]
0x18000150b  mov     ebx, [rsp+108h+var_E8]
0x18000150f  test    edi, edi
0x180001511  jz      short loc_180001518
0x180001513  cmp     edi, 3
0x180001516  jnz     short loc_180001584
0x180001518  mov     r8, [rsp+108h+lpvReserved]
0x180001520  mov     edx, edi
0x180001522  mov     rcx, rsi
0x180001525  call    _CRT_INIT
0x18000152a  mov     ebx, eax
0x18000152c  mov     [rsp+108h+var_E8], eax
0x180001530  jmp     short loc_180001547
0x180001532  xor     ebx, ebx
0x180001534  mov     [rsp+108h+var_E8], ebx
0x180001538  mov     edi, [rsp+108h+arg_8]
0x18000153f  mov     rsi, [rsp+108h+arg_0]
0x180001547  mov     rax, cs:_pRawDllMain
0x18000154e  test    rax, rax
0x180001551  jz      short loc_180001584
0x180001553  cmp     cs:dword_1800090A4, 0
0x18000155a  jz      short loc_180001584
0x18000155c  mov     r8, [rsp+108h+lpvReserved]
0x180001564  mov     edx, edi
0x180001566  mov     rcx, rsi
0x180001569  call    cs:__guard_dispatch_icall_fptr
0x18000156f  mov     ebx, eax
0x180001571  mov     [rsp+108h+var_E8], eax
0x180001575  jmp     short loc_180001584
0x180001577  xor     ebx, ebx
0x180001579  mov     [rsp+108h+var_E8], ebx
0x18000157d  mov     edi, [rsp+108h+arg_8]
0x180001584  cmp     edi, 1
0x180001587  ja      short loc_180001593
0x180001589  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001593  mov     eax, ebx
0x180001595  add     rsp, 0F0h
0x18000159c  pop     rdi
0x18000159d  pop     rsi
0x18000159e  pop     rbx
0x18000159f  retn
0x180004b80  push    rbp
0x180004b82  sub     rsp, 20h
0x180004b86  mov     rbp, rdx
0x180004b89  mov     rax, [rcx]
0x180004b8c  mov     edx, [rax]
0x180004b8e  mov     [rbp+0A8h], rcx
0x180004b95  mov     [rbp+28h], edx
0x180004b98  mov     eax, [rbp+28h]
0x180004b9b  cmp     eax, 0E06D7363h
0x180004ba0  jnz     short loc_180004BB6
0x180004ba2  mov     rdx, [rbp+0A8h]
0x180004ba9  mov     ecx, [rbp+28h]
0x180004bac  call    _XcptFilter_0
0x180004bb1  mov     [rbp+30h], eax
0x180004bb4  jmp     short loc_180004BBD
0x180004bb6  mov     dword ptr [rbp+30h], 0
0x180004bbd  mov     eax, [rbp+30h]
0x180004bc0  add     rsp, 20h
0x180004bc4  pop     rbp
0x180004bc5  retn
0x180004bc7  push    rbp
0x180004bc9  sub     rsp, 20h
0x180004bcd  mov     rbp, rdx
0x180004bd0  mov     rax, [rcx]
0x180004bd3  mov     edx, [rax]
0x180004bd5  mov     [rbp+0B0h], rcx
0x180004bdc  mov     [rbp+38h], edx
0x180004bdf  mov     eax, [rbp+38h]
0x180004be2  cmp     eax, 0E06D7363h
0x180004be7  jnz     short loc_180004BFD
0x180004be9  mov     rdx, [rbp+0B0h]
0x180004bf0  mov     ecx, [rbp+38h]
0x180004bf3  call    _XcptFilter_0
0x180004bf8  mov     [rbp+40h], eax
0x180004bfb  jmp     short loc_180004C04
0x180004bfd  mov     dword ptr [rbp+40h], 0
0x180004c04  mov     eax, [rbp+40h]
0x180004c07  add     rsp, 20h
0x180004c0b  pop     rbp
0x180004c0c  retn
0x180004c0e  push    rbp
0x180004c10  sub     rsp, 20h
0x180004c14  mov     rbp, rdx
0x180004c17  mov     rax, [rcx]
0x180004c1a  mov     edx, [rax]
0x180004c1c  mov     [rbp+0B8h], rcx
0x180004c23  mov     [rbp+48h], edx
0x180004c26  mov     eax, [rbp+48h]
0x180004c29  cmp     eax, 0E06D7363h
0x180004c2e  jnz     short loc_180004C44
0x180004c30  mov     rdx, [rbp+0B8h]
0x180004c37  mov     ecx, [rbp+48h]
0x180004c3a  call    _XcptFilter_0
0x180004c3f  mov     [rbp+50h], eax
0x180004c42  jmp     short loc_180004C4B
0x180004c44  mov     dword ptr [rbp+50h], 0
0x180004c4b  mov     eax, [rbp+50h]
0x180004c4e  add     rsp, 20h
0x180004c52  pop     rbp
0x180004c53  retn
0x180004c55  push    rbp
0x180004c57  sub     rsp, 20h
0x180004c5b  mov     rbp, rdx
0x180004c5e  mov     rax, [rcx]
0x180004c61  mov     edx, [rax]
0x180004c63  mov     [rbp+0C0h], rcx
0x180004c6a  mov     [rbp+58h], edx
0x180004c6d  mov     eax, [rbp+58h]
0x180004c70  cmp     eax, 0E06D7363h
0x180004c75  jnz     short loc_180004C8B
0x180004c77  mov     rdx, [rbp+0C0h]
0x180004c7e  mov     ecx, [rbp+58h]
0x180004c81  call    _XcptFilter_0
0x180004c86  mov     [rbp+60h], eax
0x180004c89  jmp     short loc_180004C92
0x180004c8b  mov     dword ptr [rbp+60h], 0
0x180004c92  mov     eax, [rbp+60h]
0x180004c95  add     rsp, 20h
0x180004c99  pop     rbp
0x180004c9a  retn
0x180004c9c  push    rbp
0x180004c9e  sub     rsp, 20h
0x180004ca2  mov     rbp, rdx
0x180004ca5  mov     rax, [rcx]
0x180004ca8  mov     edx, [rax]
0x180004caa  mov     [rbp+0C8h], rcx
0x180004cb1  mov     [rbp+68h], edx
0x180004cb4  mov     eax, [rbp+68h]
0x180004cb7  cmp     eax, 0E06D7363h
0x180004cbc  jnz     short loc_180004CD2
0x180004cbe  mov     rdx, [rbp+0C8h]
0x180004cc5  mov     ecx, [rbp+68h]
0x180004cc8  call    _XcptFilter_0
0x180004ccd  mov     [rbp+70h], eax
0x180004cd0  jmp     short loc_180004CD9
0x180004cd2  mov     dword ptr [rbp+70h], 0
0x180004cd9  mov     eax, [rbp+70h]
0x180004cdc  add     rsp, 20h
0x180004ce0  pop     rbp
0x180004ce1  retn
0x180004ce3  push    rbp
0x180004ce5  sub     rsp, 20h
0x180004ce9  mov     rbp, rdx
0x180004cec  mov     rax, [rcx]
0x180004cef  mov     edx, [rax]
0x180004cf1  mov     [rbp+0D0h], rcx
0x180004cf8  mov     [rbp+78h], edx
0x180004cfb  mov     eax, [rbp+78h]
0x180004cfe  cmp     eax, 0E06D7363h
0x180004d03  jnz     short loc_180004D1C
0x180004d05  mov     rdx, [rbp+0D0h]
0x180004d0c  mov     ecx, [rbp+78h]
0x180004d0f  call    _XcptFilter_0
0x180004d14  mov     [rbp+80h], eax
0x180004d1a  jmp     short loc_180004D26
0x180004d1c  mov     dword ptr [rbp+80h], 0
0x180004d26  mov     eax, [rbp+80h]
0x180004d2c  add     rsp, 20h
0x180004d30  pop     rbp
0x180004d31  retn
0x180004d33  push    rbp
0x180004d35  sub     rsp, 20h
0x180004d39  mov     rbp, rdx
0x180004d3c  mov     rax, [rcx]
0x180004d3f  mov     edx, [rax]
0x180004d41  mov     [rbp+0D8h], rcx
0x180004d48  mov     [rbp+88h], edx
0x180004d4e  mov     eax, [rbp+88h]
0x180004d54  cmp     eax, 0E06D7363h
0x180004d59  jnz     short loc_180004D75
0x180004d5b  mov     rdx, [rbp+0D8h]
0x180004d62  mov     ecx, [rbp+88h]
0x180004d68  call    _XcptFilter_0
0x180004d6d  mov     [rbp+90h], eax
0x180004d73  jmp     short loc_180004D7F
0x180004d75  mov     dword ptr [rbp+90h], 0
0x180004d7f  mov     eax, [rbp+90h]
0x180004d85  add     rsp, 20h
0x180004d89  pop     rbp
0x180004d8a  retn
0x180004d8c  push    rbp
0x180004d8e  sub     rsp, 20h
0x180004d92  mov     rbp, rdx
0x180004d95  mov     rax, [rcx]
0x180004d98  mov     edx, [rax]
0x180004d9a  mov     [rbp+0E0h], rcx
0x180004da1  mov     [rbp+98h], edx
0x180004da7  mov     eax, [rbp+98h]
0x180004dad  cmp     eax, 0E06D7363h
0x180004db2  jnz     short loc_180004DCE
0x180004db4  mov     rdx, [rbp+0E0h]
0x180004dbb  mov     ecx, [rbp+98h]
0x180004dc1  call    _XcptFilter_0
0x180004dc6  mov     [rbp+0A0h], eax
0x180004dcc  jmp     short loc_180004DD8
0x180004dce  mov     dword ptr [rbp+0A0h], 0
0x180004dd8  mov     eax, [rbp+0A0h]
0x180004dde  add     rsp, 20h
0x180004de2  pop     rbp
0x180004de3  retn
0x180004de5  push    rbp
0x180004de7  sub     rsp, 20h
0x180004deb  mov     rbp, rdx
0x180004dee  cmp     dword ptr [rbp+118h], 1
0x180004df5  ja      short loc_180004E01
0x180004df7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
