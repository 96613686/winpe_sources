# __DllMainCRTStartup

- ea: `0x18000d2d4`
- end: `0x18000d4e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d290`

## callees

- `0x180007280`
- `0x18000d060`
- `0x18000d2d4`
- `0x18000d6d6`
- `0x18004d0d0`

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
  if ( (_DWORD)fdwReason || dword_1800603A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800603A4 = 1;
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
            if ( dword_1800603A4 )
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
0x18000d2d4  mov     [rsp+lpvReserved], r8
0x18000d2d9  mov     [rsp+arg_8], edx
0x18000d2dd  mov     [rsp+arg_0], rcx
0x18000d2e2  push    rbx
0x18000d2e3  push    rsi
0x18000d2e4  push    rdi
0x18000d2e5  sub     rsp, 0F0h
0x18000d2ec  mov     edi, edx
0x18000d2ee  mov     rsi, rcx
0x18000d2f1  mov     ebx, 1
0x18000d2f6  cmp     edx, ebx
0x18000d2f8  ja      short loc_18000D300
0x18000d2fa  mov     cs:__native_dllmain_reason, edx
0x18000d300  test    edx, edx
0x18000d302  jnz     short loc_18000D317
0x18000d304  cmp     cs:dword_1800603A0, edx
0x18000d30a  jnz     short loc_18000D317
0x18000d30c  xor     ebx, ebx
0x18000d30e  mov     [rsp+108h+var_E8], ebx
0x18000d312  jmp     loc_18000D4C4
0x18000d317  lea     eax, [rdx-1]
0x18000d31a  cmp     eax, 1
0x18000d31d  ja      loc_18000D3A4
0x18000d323  mov     rax, cs:_pRawDllMain
0x18000d32a  test    rax, rax
0x18000d32d  jz      short loc_18000D365
0x18000d32f  cmp     edx, 1
0x18000d332  jnz     short loc_18000D33A
0x18000d334  mov     cs:dword_1800603A4, edx
0x18000d33a  mov     r8, [rsp+108h+lpvReserved]
0x18000d342  call    cs:__guard_dispatch_icall_fptr
0x18000d348  mov     ebx, eax
0x18000d34a  mov     [rsp+108h+var_E8], eax
0x18000d34e  jmp     short loc_18000D365
0x18000d350  xor     ebx, ebx
0x18000d352  mov     [rsp+108h+var_E8], ebx
0x18000d356  mov     edi, [rsp+108h+arg_8]
0x18000d35d  mov     rsi, [rsp+108h+arg_0]
0x18000d365  test    ebx, ebx
0x18000d367  jz      loc_18000D4C4
0x18000d36d  mov     r8, [rsp+108h+lpvReserved]
0x18000d375  mov     edx, edi
0x18000d377  mov     rcx, rsi
0x18000d37a  call    _CRT_INIT
0x18000d37f  mov     ebx, eax
0x18000d381  mov     [rsp+108h+var_E8], eax
0x18000d385  jmp     short loc_18000D39C
0x18000d387  xor     ebx, ebx
0x18000d389  mov     [rsp+108h+var_E8], ebx
0x18000d38d  mov     edi, [rsp+108h+arg_8]
0x18000d394  mov     rsi, [rsp+108h+arg_0]
0x18000d39c  test    ebx, ebx
0x18000d39e  jz      loc_18000D4C4
0x18000d3a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000d3ac  mov     edx, edi; fdwReason
0x18000d3ae  mov     rcx, rsi; hinstDLL
0x18000d3b1  call    DllMain
0x18000d3b6  mov     ebx, eax
0x18000d3b8  mov     [rsp+108h+var_E8], eax
0x18000d3bc  jmp     short loc_18000D3D3
0x18000d3be  xor     ebx, ebx
0x18000d3c0  mov     [rsp+108h+var_E8], ebx
0x18000d3c4  mov     edi, [rsp+108h+arg_8]
0x18000d3cb  mov     rsi, [rsp+108h+arg_0]
0x18000d3d3  cmp     edi, 1
0x18000d3d6  jnz     short loc_18000D44F
0x18000d3d8  test    ebx, ebx
0x18000d3da  jnz     short loc_18000D44F
0x18000d3dc  xor     r8d, r8d; lpvReserved
0x18000d3df  xor     edx, edx; fdwReason
0x18000d3e1  mov     rcx, rsi; hinstDLL
0x18000d3e4  call    DllMain
0x18000d3e9  jmp     short loc_18000D3FE
0x18000d3eb  mov     edi, [rsp+108h+arg_8]
0x18000d3f2  mov     rsi, [rsp+108h+arg_0]
0x18000d3fa  mov     ebx, [rsp+108h+var_E8]
0x18000d3fe  xor     r8d, r8d
0x18000d401  xor     edx, edx
0x18000d403  mov     rcx, rsi
0x18000d406  call    _CRT_INIT
0x18000d40b  jmp     short loc_18000D420
0x18000d40d  mov     edi, [rsp+108h+arg_8]
0x18000d414  mov     rsi, [rsp+108h+arg_0]
0x18000d41c  mov     ebx, [rsp+108h+var_E8]
0x18000d420  mov     rax, cs:_pRawDllMain
0x18000d427  test    rax, rax
0x18000d42a  jz      short loc_18000D44F
0x18000d42c  xor     r8d, r8d
0x18000d42f  xor     edx, edx
0x18000d431  mov     rcx, rsi
0x18000d434  call    cs:__guard_dispatch_icall_fptr
0x18000d43a  jmp     short loc_18000D44F
0x18000d43c  mov     edi, [rsp+108h+arg_8]
0x18000d443  mov     rsi, [rsp+108h+arg_0]
0x18000d44b  mov     ebx, [rsp+108h+var_E8]
0x18000d44f  test    edi, edi
0x18000d451  jz      short loc_18000D458
0x18000d453  cmp     edi, 3
0x18000d456  jnz     short loc_18000D4C4
0x18000d458  mov     r8, [rsp+108h+lpvReserved]
0x18000d460  mov     edx, edi
0x18000d462  mov     rcx, rsi
0x18000d465  call    _CRT_INIT
0x18000d46a  mov     ebx, eax
0x18000d46c  mov     [rsp+108h+var_E8], eax
0x18000d470  jmp     short loc_18000D487
0x18000d472  xor     ebx, ebx
0x18000d474  mov     [rsp+108h+var_E8], ebx
0x18000d478  mov     edi, [rsp+108h+arg_8]
0x18000d47f  mov     rsi, [rsp+108h+arg_0]
0x18000d487  mov     rax, cs:_pRawDllMain
0x18000d48e  test    rax, rax
0x18000d491  jz      short loc_18000D4C4
0x18000d493  cmp     cs:dword_1800603A4, 0
0x18000d49a  jz      short loc_18000D4C4
0x18000d49c  mov     r8, [rsp+108h+lpvReserved]
0x18000d4a4  mov     edx, edi
0x18000d4a6  mov     rcx, rsi
0x18000d4a9  call    cs:__guard_dispatch_icall_fptr
0x18000d4af  mov     ebx, eax
0x18000d4b1  mov     [rsp+108h+var_E8], eax
0x18000d4b5  jmp     short loc_18000D4C4
0x18000d4b7  xor     ebx, ebx
0x18000d4b9  mov     [rsp+108h+var_E8], ebx
0x18000d4bd  mov     edi, [rsp+108h+arg_8]
0x18000d4c4  cmp     edi, 1
0x18000d4c7  ja      short loc_18000D4D3
0x18000d4c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000d4d3  mov     eax, ebx
0x18000d4d5  add     rsp, 0F0h
0x18000d4dc  pop     rdi
0x18000d4dd  pop     rsi
0x18000d4de  pop     rbx
0x18000d4df  retn
0x18004d1a0  push    rbp
0x18004d1a2  sub     rsp, 20h
0x18004d1a6  mov     rbp, rdx
0x18004d1a9  mov     rax, [rcx]
0x18004d1ac  mov     edx, [rax]
0x18004d1ae  mov     [rbp+0A8h], rcx
0x18004d1b5  mov     [rbp+28h], edx
0x18004d1b8  mov     eax, [rbp+28h]
0x18004d1bb  cmp     eax, 0E06D7363h
0x18004d1c0  jnz     short loc_18004D1D6
0x18004d1c2  mov     rdx, [rbp+0A8h]
0x18004d1c9  mov     ecx, [rbp+28h]
0x18004d1cc  call    _XcptFilter_0
0x18004d1d1  mov     [rbp+30h], eax
0x18004d1d4  jmp     short loc_18004D1DD
0x18004d1d6  mov     dword ptr [rbp+30h], 0
0x18004d1dd  mov     eax, [rbp+30h]
0x18004d1e0  add     rsp, 20h
0x18004d1e4  pop     rbp
0x18004d1e5  retn
0x18004d1e7  push    rbp
0x18004d1e9  sub     rsp, 20h
0x18004d1ed  mov     rbp, rdx
0x18004d1f0  mov     rax, [rcx]
0x18004d1f3  mov     edx, [rax]
0x18004d1f5  mov     [rbp+0B0h], rcx
0x18004d1fc  mov     [rbp+38h], edx
0x18004d1ff  mov     eax, [rbp+38h]
0x18004d202  cmp     eax, 0E06D7363h
0x18004d207  jnz     short loc_18004D21D
0x18004d209  mov     rdx, [rbp+0B0h]
0x18004d210  mov     ecx, [rbp+38h]
0x18004d213  call    _XcptFilter_0
0x18004d218  mov     [rbp+40h], eax
0x18004d21b  jmp     short loc_18004D224
0x18004d21d  mov     dword ptr [rbp+40h], 0
0x18004d224  mov     eax, [rbp+40h]
0x18004d227  add     rsp, 20h
0x18004d22b  pop     rbp
0x18004d22c  retn
0x18004d22e  push    rbp
0x18004d230  sub     rsp, 20h
0x18004d234  mov     rbp, rdx
0x18004d237  mov     rax, [rcx]
0x18004d23a  mov     edx, [rax]
0x18004d23c  mov     [rbp+0B8h], rcx
0x18004d243  mov     [rbp+48h], edx
0x18004d246  mov     eax, [rbp+48h]
0x18004d249  cmp     eax, 0E06D7363h
0x18004d24e  jnz     short loc_18004D264
0x18004d250  mov     rdx, [rbp+0B8h]
0x18004d257  mov     ecx, [rbp+48h]
0x18004d25a  call    _XcptFilter_0
0x18004d25f  mov     [rbp+50h], eax
0x18004d262  jmp     short loc_18004D26B
0x18004d264  mov     dword ptr [rbp+50h], 0
0x18004d26b  mov     eax, [rbp+50h]
0x18004d26e  add     rsp, 20h
0x18004d272  pop     rbp
0x18004d273  retn
0x18004d275  push    rbp
0x18004d277  sub     rsp, 20h
0x18004d27b  mov     rbp, rdx
0x18004d27e  mov     rax, [rcx]
0x18004d281  mov     edx, [rax]
0x18004d283  mov     [rbp+0C0h], rcx
0x18004d28a  mov     [rbp+58h], edx
0x18004d28d  mov     eax, [rbp+58h]
0x18004d290  cmp     eax, 0E06D7363h
0x18004d295  jnz     short loc_18004D2AB
0x18004d297  mov     rdx, [rbp+0C0h]
0x18004d29e  mov     ecx, [rbp+58h]
0x18004d2a1  call    _XcptFilter_0
0x18004d2a6  mov     [rbp+60h], eax
0x18004d2a9  jmp     short loc_18004D2B2
0x18004d2ab  mov     dword ptr [rbp+60h], 0
0x18004d2b2  mov     eax, [rbp+60h]
0x18004d2b5  add     rsp, 20h
0x18004d2b9  pop     rbp
0x18004d2ba  retn
0x18004d2bc  push    rbp
0x18004d2be  sub     rsp, 20h
0x18004d2c2  mov     rbp, rdx
0x18004d2c5  mov     rax, [rcx]
0x18004d2c8  mov     edx, [rax]
0x18004d2ca  mov     [rbp+0C8h], rcx
0x18004d2d1  mov     [rbp+68h], edx
0x18004d2d4  mov     eax, [rbp+68h]
0x18004d2d7  cmp     eax, 0E06D7363h
0x18004d2dc  jnz     short loc_18004D2F2
0x18004d2de  mov     rdx, [rbp+0C8h]
0x18004d2e5  mov     ecx, [rbp+68h]
0x18004d2e8  call    _XcptFilter_0
0x18004d2ed  mov     [rbp+70h], eax
0x18004d2f0  jmp     short loc_18004D2F9
0x18004d2f2  mov     dword ptr [rbp+70h], 0
0x18004d2f9  mov     eax, [rbp+70h]
0x18004d2fc  add     rsp, 20h
0x18004d300  pop     rbp
0x18004d301  retn
0x18004d303  push    rbp
0x18004d305  sub     rsp, 20h
0x18004d309  mov     rbp, rdx
0x18004d30c  mov     rax, [rcx]
0x18004d30f  mov     edx, [rax]
0x18004d311  mov     [rbp+0D0h], rcx
0x18004d318  mov     [rbp+78h], edx
0x18004d31b  mov     eax, [rbp+78h]
0x18004d31e  cmp     eax, 0E06D7363h
0x18004d323  jnz     short loc_18004D33C
0x18004d325  mov     rdx, [rbp+0D0h]
0x18004d32c  mov     ecx, [rbp+78h]
0x18004d32f  call    _XcptFilter_0
0x18004d334  mov     [rbp+80h], eax
0x18004d33a  jmp     short loc_18004D346
0x18004d33c  mov     dword ptr [rbp+80h], 0
0x18004d346  mov     eax, [rbp+80h]
0x18004d34c  add     rsp, 20h
0x18004d350  pop     rbp
0x18004d351  retn
0x18004d353  push    rbp
0x18004d355  sub     rsp, 20h
0x18004d359  mov     rbp, rdx
0x18004d35c  mov     rax, [rcx]
0x18004d35f  mov     edx, [rax]
0x18004d361  mov     [rbp+0D8h], rcx
0x18004d368  mov     [rbp+88h], edx
0x18004d36e  mov     eax, [rbp+88h]
0x18004d374  cmp     eax, 0E06D7363h
0x18004d379  jnz     short loc_18004D395
0x18004d37b  mov     rdx, [rbp+0D8h]
0x18004d382  mov     ecx, [rbp+88h]
0x18004d388  call    _XcptFilter_0
0x18004d38d  mov     [rbp+90h], eax
0x18004d393  jmp     short loc_18004D39F
0x18004d395  mov     dword ptr [rbp+90h], 0
0x18004d39f  mov     eax, [rbp+90h]
0x18004d3a5  add     rsp, 20h
0x18004d3a9  pop     rbp
0x18004d3aa  retn
0x18004d3ac  push    rbp
0x18004d3ae  sub     rsp, 20h
0x18004d3b2  mov     rbp, rdx
0x18004d3b5  mov     rax, [rcx]
0x18004d3b8  mov     edx, [rax]
0x18004d3ba  mov     [rbp+0E0h], rcx
0x18004d3c1  mov     [rbp+98h], edx
0x18004d3c7  mov     eax, [rbp+98h]
0x18004d3cd  cmp     eax, 0E06D7363h
0x18004d3d2  jnz     short loc_18004D3EE
0x18004d3d4  mov     rdx, [rbp+0E0h]
0x18004d3db  mov     ecx, [rbp+98h]
0x18004d3e1  call    _XcptFilter_0
0x18004d3e6  mov     [rbp+0A0h], eax
0x18004d3ec  jmp     short loc_18004D3F8
0x18004d3ee  mov     dword ptr [rbp+0A0h], 0
0x18004d3f8  mov     eax, [rbp+0A0h]
0x18004d3fe  add     rsp, 20h
0x18004d402  pop     rbp
0x18004d403  retn
0x18004d405  push    rbp
0x18004d407  sub     rsp, 20h
0x18004d40b  mov     rbp, rdx
0x18004d40e  cmp     dword ptr [rbp+118h], 1
0x18004d415  ja      short loc_18004D421
0x18004d417  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
