# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180001728`
- `0x180003a80`

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
  if ( (_DWORD)fdwReason || dword_1800080A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800080A4 = 1;
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
            if ( dword_1800080A4 )
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
0x180001344  cmp     cs:dword_1800080A0, edx
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
0x180001374  mov     cs:dword_1800080A4, edx
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
0x1800014d3  cmp     cs:dword_1800080A4, 0
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
0x180003af0  push    rbp
0x180003af2  sub     rsp, 20h
0x180003af6  mov     rbp, rdx
0x180003af9  mov     rax, [rcx]
0x180003afc  mov     edx, [rax]
0x180003afe  mov     [rbp+0A8h], rcx
0x180003b05  mov     [rbp+28h], edx
0x180003b08  mov     eax, [rbp+28h]
0x180003b0b  cmp     eax, 0E06D7363h
0x180003b10  jnz     short loc_180003B26
0x180003b12  mov     rdx, [rbp+0A8h]
0x180003b19  mov     ecx, [rbp+28h]
0x180003b1c  call    _XcptFilter_0
0x180003b21  mov     [rbp+30h], eax
0x180003b24  jmp     short loc_180003B2D
0x180003b26  mov     dword ptr [rbp+30h], 0
0x180003b2d  mov     eax, [rbp+30h]
0x180003b30  add     rsp, 20h
0x180003b34  pop     rbp
0x180003b35  retn
0x180003b37  push    rbp
0x180003b39  sub     rsp, 20h
0x180003b3d  mov     rbp, rdx
0x180003b40  mov     rax, [rcx]
0x180003b43  mov     edx, [rax]
0x180003b45  mov     [rbp+0B0h], rcx
0x180003b4c  mov     [rbp+38h], edx
0x180003b4f  mov     eax, [rbp+38h]
0x180003b52  cmp     eax, 0E06D7363h
0x180003b57  jnz     short loc_180003B6D
0x180003b59  mov     rdx, [rbp+0B0h]
0x180003b60  mov     ecx, [rbp+38h]
0x180003b63  call    _XcptFilter_0
0x180003b68  mov     [rbp+40h], eax
0x180003b6b  jmp     short loc_180003B74
0x180003b6d  mov     dword ptr [rbp+40h], 0
0x180003b74  mov     eax, [rbp+40h]
0x180003b77  add     rsp, 20h
0x180003b7b  pop     rbp
0x180003b7c  retn
0x180003b7e  push    rbp
0x180003b80  sub     rsp, 20h
0x180003b84  mov     rbp, rdx
0x180003b87  mov     rax, [rcx]
0x180003b8a  mov     edx, [rax]
0x180003b8c  mov     [rbp+0B8h], rcx
0x180003b93  mov     [rbp+48h], edx
0x180003b96  mov     eax, [rbp+48h]
0x180003b99  cmp     eax, 0E06D7363h
0x180003b9e  jnz     short loc_180003BB4
0x180003ba0  mov     rdx, [rbp+0B8h]
0x180003ba7  mov     ecx, [rbp+48h]
0x180003baa  call    _XcptFilter_0
0x180003baf  mov     [rbp+50h], eax
0x180003bb2  jmp     short loc_180003BBB
0x180003bb4  mov     dword ptr [rbp+50h], 0
0x180003bbb  mov     eax, [rbp+50h]
0x180003bbe  add     rsp, 20h
0x180003bc2  pop     rbp
0x180003bc3  retn
0x180003bc5  push    rbp
0x180003bc7  sub     rsp, 20h
0x180003bcb  mov     rbp, rdx
0x180003bce  mov     rax, [rcx]
0x180003bd1  mov     edx, [rax]
0x180003bd3  mov     [rbp+0C0h], rcx
0x180003bda  mov     [rbp+58h], edx
0x180003bdd  mov     eax, [rbp+58h]
0x180003be0  cmp     eax, 0E06D7363h
0x180003be5  jnz     short loc_180003BFB
0x180003be7  mov     rdx, [rbp+0C0h]
0x180003bee  mov     ecx, [rbp+58h]
0x180003bf1  call    _XcptFilter_0
0x180003bf6  mov     [rbp+60h], eax
0x180003bf9  jmp     short loc_180003C02
0x180003bfb  mov     dword ptr [rbp+60h], 0
0x180003c02  mov     eax, [rbp+60h]
0x180003c05  add     rsp, 20h
0x180003c09  pop     rbp
0x180003c0a  retn
0x180003c0c  push    rbp
0x180003c0e  sub     rsp, 20h
0x180003c12  mov     rbp, rdx
0x180003c15  mov     rax, [rcx]
0x180003c18  mov     edx, [rax]
0x180003c1a  mov     [rbp+0C8h], rcx
0x180003c21  mov     [rbp+68h], edx
0x180003c24  mov     eax, [rbp+68h]
0x180003c27  cmp     eax, 0E06D7363h
0x180003c2c  jnz     short loc_180003C42
0x180003c2e  mov     rdx, [rbp+0C8h]
0x180003c35  mov     ecx, [rbp+68h]
0x180003c38  call    _XcptFilter_0
0x180003c3d  mov     [rbp+70h], eax
0x180003c40  jmp     short loc_180003C49
0x180003c42  mov     dword ptr [rbp+70h], 0
0x180003c49  mov     eax, [rbp+70h]
0x180003c4c  add     rsp, 20h
0x180003c50  pop     rbp
0x180003c51  retn
0x180003c53  push    rbp
0x180003c55  sub     rsp, 20h
0x180003c59  mov     rbp, rdx
0x180003c5c  mov     rax, [rcx]
0x180003c5f  mov     edx, [rax]
0x180003c61  mov     [rbp+0D0h], rcx
0x180003c68  mov     [rbp+78h], edx
0x180003c6b  mov     eax, [rbp+78h]
0x180003c6e  cmp     eax, 0E06D7363h
0x180003c73  jnz     short loc_180003C8C
0x180003c75  mov     rdx, [rbp+0D0h]
0x180003c7c  mov     ecx, [rbp+78h]
0x180003c7f  call    _XcptFilter_0
0x180003c84  mov     [rbp+80h], eax
0x180003c8a  jmp     short loc_180003C96
0x180003c8c  mov     dword ptr [rbp+80h], 0
0x180003c96  mov     eax, [rbp+80h]
0x180003c9c  add     rsp, 20h
0x180003ca0  pop     rbp
0x180003ca1  retn
0x180003ca3  push    rbp
0x180003ca5  sub     rsp, 20h
0x180003ca9  mov     rbp, rdx
0x180003cac  mov     rax, [rcx]
0x180003caf  mov     edx, [rax]
0x180003cb1  mov     [rbp+0D8h], rcx
0x180003cb8  mov     [rbp+88h], edx
0x180003cbe  mov     eax, [rbp+88h]
0x180003cc4  cmp     eax, 0E06D7363h
0x180003cc9  jnz     short loc_180003CE5
0x180003ccb  mov     rdx, [rbp+0D8h]
0x180003cd2  mov     ecx, [rbp+88h]
0x180003cd8  call    _XcptFilter_0
0x180003cdd  mov     [rbp+90h], eax
0x180003ce3  jmp     short loc_180003CEF
0x180003ce5  mov     dword ptr [rbp+90h], 0
0x180003cef  mov     eax, [rbp+90h]
0x180003cf5  add     rsp, 20h
0x180003cf9  pop     rbp
0x180003cfa  retn
0x180003cfc  push    rbp
0x180003cfe  sub     rsp, 20h
0x180003d02  mov     rbp, rdx
0x180003d05  mov     rax, [rcx]
0x180003d08  mov     edx, [rax]
0x180003d0a  mov     [rbp+0E0h], rcx
0x180003d11  mov     [rbp+98h], edx
0x180003d17  mov     eax, [rbp+98h]
0x180003d1d  cmp     eax, 0E06D7363h
0x180003d22  jnz     short loc_180003D3E
0x180003d24  mov     rdx, [rbp+0E0h]
0x180003d2b  mov     ecx, [rbp+98h]
0x180003d31  call    _XcptFilter_0
0x180003d36  mov     [rbp+0A0h], eax
0x180003d3c  jmp     short loc_180003D48
0x180003d3e  mov     dword ptr [rbp+0A0h], 0
0x180003d48  mov     eax, [rbp+0A0h]
0x180003d4e  add     rsp, 20h
0x180003d52  pop     rbp
0x180003d53  retn
0x180003d55  push    rbp
0x180003d57  sub     rsp, 20h
0x180003d5b  mov     rbp, rdx
0x180003d5e  cmp     dword ptr [rbp+118h], 1
0x180003d65  ja      short loc_180003D71
0x180003d67  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
