# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180002f38`
- `0x180003b00`

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
  if ( (_DWORD)fdwReason || dword_1800080E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800080E4 = 1;
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
            if ( dword_1800080E4 )
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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_1800080E0, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_1800080E4, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_1800080E4, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180003b70  push    rbp
0x180003b72  sub     rsp, 20h
0x180003b76  mov     rbp, rdx
0x180003b79  mov     rax, [rcx]
0x180003b7c  mov     edx, [rax]
0x180003b7e  mov     [rbp+0A8h], rcx
0x180003b85  mov     [rbp+28h], edx
0x180003b88  mov     eax, [rbp+28h]
0x180003b8b  cmp     eax, 0E06D7363h
0x180003b90  jnz     short loc_180003BA6
0x180003b92  mov     rdx, [rbp+0A8h]
0x180003b99  mov     ecx, [rbp+28h]
0x180003b9c  call    _XcptFilter_0
0x180003ba1  mov     [rbp+30h], eax
0x180003ba4  jmp     short loc_180003BAD
0x180003ba6  mov     dword ptr [rbp+30h], 0
0x180003bad  mov     eax, [rbp+30h]
0x180003bb0  add     rsp, 20h
0x180003bb4  pop     rbp
0x180003bb5  retn
0x180003bb7  push    rbp
0x180003bb9  sub     rsp, 20h
0x180003bbd  mov     rbp, rdx
0x180003bc0  mov     rax, [rcx]
0x180003bc3  mov     edx, [rax]
0x180003bc5  mov     [rbp+0B0h], rcx
0x180003bcc  mov     [rbp+38h], edx
0x180003bcf  mov     eax, [rbp+38h]
0x180003bd2  cmp     eax, 0E06D7363h
0x180003bd7  jnz     short loc_180003BED
0x180003bd9  mov     rdx, [rbp+0B0h]
0x180003be0  mov     ecx, [rbp+38h]
0x180003be3  call    _XcptFilter_0
0x180003be8  mov     [rbp+40h], eax
0x180003beb  jmp     short loc_180003BF4
0x180003bed  mov     dword ptr [rbp+40h], 0
0x180003bf4  mov     eax, [rbp+40h]
0x180003bf7  add     rsp, 20h
0x180003bfb  pop     rbp
0x180003bfc  retn
0x180003bfe  push    rbp
0x180003c00  sub     rsp, 20h
0x180003c04  mov     rbp, rdx
0x180003c07  mov     rax, [rcx]
0x180003c0a  mov     edx, [rax]
0x180003c0c  mov     [rbp+0B8h], rcx
0x180003c13  mov     [rbp+48h], edx
0x180003c16  mov     eax, [rbp+48h]
0x180003c19  cmp     eax, 0E06D7363h
0x180003c1e  jnz     short loc_180003C34
0x180003c20  mov     rdx, [rbp+0B8h]
0x180003c27  mov     ecx, [rbp+48h]
0x180003c2a  call    _XcptFilter_0
0x180003c2f  mov     [rbp+50h], eax
0x180003c32  jmp     short loc_180003C3B
0x180003c34  mov     dword ptr [rbp+50h], 0
0x180003c3b  mov     eax, [rbp+50h]
0x180003c3e  add     rsp, 20h
0x180003c42  pop     rbp
0x180003c43  retn
0x180003c45  push    rbp
0x180003c47  sub     rsp, 20h
0x180003c4b  mov     rbp, rdx
0x180003c4e  mov     rax, [rcx]
0x180003c51  mov     edx, [rax]
0x180003c53  mov     [rbp+0C0h], rcx
0x180003c5a  mov     [rbp+58h], edx
0x180003c5d  mov     eax, [rbp+58h]
0x180003c60  cmp     eax, 0E06D7363h
0x180003c65  jnz     short loc_180003C7B
0x180003c67  mov     rdx, [rbp+0C0h]
0x180003c6e  mov     ecx, [rbp+58h]
0x180003c71  call    _XcptFilter_0
0x180003c76  mov     [rbp+60h], eax
0x180003c79  jmp     short loc_180003C82
0x180003c7b  mov     dword ptr [rbp+60h], 0
0x180003c82  mov     eax, [rbp+60h]
0x180003c85  add     rsp, 20h
0x180003c89  pop     rbp
0x180003c8a  retn
0x180003c8c  push    rbp
0x180003c8e  sub     rsp, 20h
0x180003c92  mov     rbp, rdx
0x180003c95  mov     rax, [rcx]
0x180003c98  mov     edx, [rax]
0x180003c9a  mov     [rbp+0C8h], rcx
0x180003ca1  mov     [rbp+68h], edx
0x180003ca4  mov     eax, [rbp+68h]
0x180003ca7  cmp     eax, 0E06D7363h
0x180003cac  jnz     short loc_180003CC2
0x180003cae  mov     rdx, [rbp+0C8h]
0x180003cb5  mov     ecx, [rbp+68h]
0x180003cb8  call    _XcptFilter_0
0x180003cbd  mov     [rbp+70h], eax
0x180003cc0  jmp     short loc_180003CC9
0x180003cc2  mov     dword ptr [rbp+70h], 0
0x180003cc9  mov     eax, [rbp+70h]
0x180003ccc  add     rsp, 20h
0x180003cd0  pop     rbp
0x180003cd1  retn
0x180003cd3  push    rbp
0x180003cd5  sub     rsp, 20h
0x180003cd9  mov     rbp, rdx
0x180003cdc  mov     rax, [rcx]
0x180003cdf  mov     edx, [rax]
0x180003ce1  mov     [rbp+0D0h], rcx
0x180003ce8  mov     [rbp+78h], edx
0x180003ceb  mov     eax, [rbp+78h]
0x180003cee  cmp     eax, 0E06D7363h
0x180003cf3  jnz     short loc_180003D0C
0x180003cf5  mov     rdx, [rbp+0D0h]
0x180003cfc  mov     ecx, [rbp+78h]
0x180003cff  call    _XcptFilter_0
0x180003d04  mov     [rbp+80h], eax
0x180003d0a  jmp     short loc_180003D16
0x180003d0c  mov     dword ptr [rbp+80h], 0
0x180003d16  mov     eax, [rbp+80h]
0x180003d1c  add     rsp, 20h
0x180003d20  pop     rbp
0x180003d21  retn
0x180003d23  push    rbp
0x180003d25  sub     rsp, 20h
0x180003d29  mov     rbp, rdx
0x180003d2c  mov     rax, [rcx]
0x180003d2f  mov     edx, [rax]
0x180003d31  mov     [rbp+0D8h], rcx
0x180003d38  mov     [rbp+88h], edx
0x180003d3e  mov     eax, [rbp+88h]
0x180003d44  cmp     eax, 0E06D7363h
0x180003d49  jnz     short loc_180003D65
0x180003d4b  mov     rdx, [rbp+0D8h]
0x180003d52  mov     ecx, [rbp+88h]
0x180003d58  call    _XcptFilter_0
0x180003d5d  mov     [rbp+90h], eax
0x180003d63  jmp     short loc_180003D6F
0x180003d65  mov     dword ptr [rbp+90h], 0
0x180003d6f  mov     eax, [rbp+90h]
0x180003d75  add     rsp, 20h
0x180003d79  pop     rbp
0x180003d7a  retn
0x180003d7c  push    rbp
0x180003d7e  sub     rsp, 20h
0x180003d82  mov     rbp, rdx
0x180003d85  mov     rax, [rcx]
0x180003d88  mov     edx, [rax]
0x180003d8a  mov     [rbp+0E0h], rcx
0x180003d91  mov     [rbp+98h], edx
0x180003d97  mov     eax, [rbp+98h]
0x180003d9d  cmp     eax, 0E06D7363h
0x180003da2  jnz     short loc_180003DBE
0x180003da4  mov     rdx, [rbp+0E0h]
0x180003dab  mov     ecx, [rbp+98h]
0x180003db1  call    _XcptFilter_0
0x180003db6  mov     [rbp+0A0h], eax
0x180003dbc  jmp     short loc_180003DC8
0x180003dbe  mov     dword ptr [rbp+0A0h], 0
0x180003dc8  mov     eax, [rbp+0A0h]
0x180003dce  add     rsp, 20h
0x180003dd2  pop     rbp
0x180003dd3  retn
0x180003dd5  push    rbp
0x180003dd7  sub     rsp, 20h
0x180003ddb  mov     rbp, rdx
0x180003dde  cmp     dword ptr [rbp+118h], 1
0x180003de5  ja      short loc_180003DF1
0x180003de7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
