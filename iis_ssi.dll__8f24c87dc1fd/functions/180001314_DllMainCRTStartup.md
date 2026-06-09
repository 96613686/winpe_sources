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
- `0x18000173a`
- `0x180001918`
- `0x1800057c0`

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
  if ( (_DWORD)fdwReason || dword_18000A240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000A244 = 1;
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
            if ( dword_18000A244 )
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
0x180001344  cmp     cs:dword_18000A240, edx
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
0x180001374  mov     cs:dword_18000A244, edx
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
0x1800014d3  cmp     cs:dword_18000A244, 0
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
0x180005890  push    rbp
0x180005892  sub     rsp, 20h
0x180005896  mov     rbp, rdx
0x180005899  mov     rax, [rcx]
0x18000589c  mov     edx, [rax]
0x18000589e  mov     [rbp+0A8h], rcx
0x1800058a5  mov     [rbp+28h], edx
0x1800058a8  mov     eax, [rbp+28h]
0x1800058ab  cmp     eax, 0E06D7363h
0x1800058b0  jnz     short loc_1800058C6
0x1800058b2  mov     rdx, [rbp+0A8h]
0x1800058b9  mov     ecx, [rbp+28h]
0x1800058bc  call    _XcptFilter_0
0x1800058c1  mov     [rbp+30h], eax
0x1800058c4  jmp     short loc_1800058CD
0x1800058c6  mov     dword ptr [rbp+30h], 0
0x1800058cd  mov     eax, [rbp+30h]
0x1800058d0  add     rsp, 20h
0x1800058d4  pop     rbp
0x1800058d5  retn
0x1800058d7  push    rbp
0x1800058d9  sub     rsp, 20h
0x1800058dd  mov     rbp, rdx
0x1800058e0  mov     rax, [rcx]
0x1800058e3  mov     edx, [rax]
0x1800058e5  mov     [rbp+0B0h], rcx
0x1800058ec  mov     [rbp+38h], edx
0x1800058ef  mov     eax, [rbp+38h]
0x1800058f2  cmp     eax, 0E06D7363h
0x1800058f7  jnz     short loc_18000590D
0x1800058f9  mov     rdx, [rbp+0B0h]
0x180005900  mov     ecx, [rbp+38h]
0x180005903  call    _XcptFilter_0
0x180005908  mov     [rbp+40h], eax
0x18000590b  jmp     short loc_180005914
0x18000590d  mov     dword ptr [rbp+40h], 0
0x180005914  mov     eax, [rbp+40h]
0x180005917  add     rsp, 20h
0x18000591b  pop     rbp
0x18000591c  retn
0x18000591e  push    rbp
0x180005920  sub     rsp, 20h
0x180005924  mov     rbp, rdx
0x180005927  mov     rax, [rcx]
0x18000592a  mov     edx, [rax]
0x18000592c  mov     [rbp+0B8h], rcx
0x180005933  mov     [rbp+48h], edx
0x180005936  mov     eax, [rbp+48h]
0x180005939  cmp     eax, 0E06D7363h
0x18000593e  jnz     short loc_180005954
0x180005940  mov     rdx, [rbp+0B8h]
0x180005947  mov     ecx, [rbp+48h]
0x18000594a  call    _XcptFilter_0
0x18000594f  mov     [rbp+50h], eax
0x180005952  jmp     short loc_18000595B
0x180005954  mov     dword ptr [rbp+50h], 0
0x18000595b  mov     eax, [rbp+50h]
0x18000595e  add     rsp, 20h
0x180005962  pop     rbp
0x180005963  retn
0x180005965  push    rbp
0x180005967  sub     rsp, 20h
0x18000596b  mov     rbp, rdx
0x18000596e  mov     rax, [rcx]
0x180005971  mov     edx, [rax]
0x180005973  mov     [rbp+0C0h], rcx
0x18000597a  mov     [rbp+58h], edx
0x18000597d  mov     eax, [rbp+58h]
0x180005980  cmp     eax, 0E06D7363h
0x180005985  jnz     short loc_18000599B
0x180005987  mov     rdx, [rbp+0C0h]
0x18000598e  mov     ecx, [rbp+58h]
0x180005991  call    _XcptFilter_0
0x180005996  mov     [rbp+60h], eax
0x180005999  jmp     short loc_1800059A2
0x18000599b  mov     dword ptr [rbp+60h], 0
0x1800059a2  mov     eax, [rbp+60h]
0x1800059a5  add     rsp, 20h
0x1800059a9  pop     rbp
0x1800059aa  retn
0x1800059ac  push    rbp
0x1800059ae  sub     rsp, 20h
0x1800059b2  mov     rbp, rdx
0x1800059b5  mov     rax, [rcx]
0x1800059b8  mov     edx, [rax]
0x1800059ba  mov     [rbp+0C8h], rcx
0x1800059c1  mov     [rbp+68h], edx
0x1800059c4  mov     eax, [rbp+68h]
0x1800059c7  cmp     eax, 0E06D7363h
0x1800059cc  jnz     short loc_1800059E2
0x1800059ce  mov     rdx, [rbp+0C8h]
0x1800059d5  mov     ecx, [rbp+68h]
0x1800059d8  call    _XcptFilter_0
0x1800059dd  mov     [rbp+70h], eax
0x1800059e0  jmp     short loc_1800059E9
0x1800059e2  mov     dword ptr [rbp+70h], 0
0x1800059e9  mov     eax, [rbp+70h]
0x1800059ec  add     rsp, 20h
0x1800059f0  pop     rbp
0x1800059f1  retn
0x1800059f3  push    rbp
0x1800059f5  sub     rsp, 20h
0x1800059f9  mov     rbp, rdx
0x1800059fc  mov     rax, [rcx]
0x1800059ff  mov     edx, [rax]
0x180005a01  mov     [rbp+0D0h], rcx
0x180005a08  mov     [rbp+78h], edx
0x180005a0b  mov     eax, [rbp+78h]
0x180005a0e  cmp     eax, 0E06D7363h
0x180005a13  jnz     short loc_180005A2C
0x180005a15  mov     rdx, [rbp+0D0h]
0x180005a1c  mov     ecx, [rbp+78h]
0x180005a1f  call    _XcptFilter_0
0x180005a24  mov     [rbp+80h], eax
0x180005a2a  jmp     short loc_180005A36
0x180005a2c  mov     dword ptr [rbp+80h], 0
0x180005a36  mov     eax, [rbp+80h]
0x180005a3c  add     rsp, 20h
0x180005a40  pop     rbp
0x180005a41  retn
0x180005a43  push    rbp
0x180005a45  sub     rsp, 20h
0x180005a49  mov     rbp, rdx
0x180005a4c  mov     rax, [rcx]
0x180005a4f  mov     edx, [rax]
0x180005a51  mov     [rbp+0D8h], rcx
0x180005a58  mov     [rbp+88h], edx
0x180005a5e  mov     eax, [rbp+88h]
0x180005a64  cmp     eax, 0E06D7363h
0x180005a69  jnz     short loc_180005A85
0x180005a6b  mov     rdx, [rbp+0D8h]
0x180005a72  mov     ecx, [rbp+88h]
0x180005a78  call    _XcptFilter_0
0x180005a7d  mov     [rbp+90h], eax
0x180005a83  jmp     short loc_180005A8F
0x180005a85  mov     dword ptr [rbp+90h], 0
0x180005a8f  mov     eax, [rbp+90h]
0x180005a95  add     rsp, 20h
0x180005a99  pop     rbp
0x180005a9a  retn
0x180005a9c  push    rbp
0x180005a9e  sub     rsp, 20h
0x180005aa2  mov     rbp, rdx
0x180005aa5  mov     rax, [rcx]
0x180005aa8  mov     edx, [rax]
0x180005aaa  mov     [rbp+0E0h], rcx
0x180005ab1  mov     [rbp+98h], edx
0x180005ab7  mov     eax, [rbp+98h]
0x180005abd  cmp     eax, 0E06D7363h
0x180005ac2  jnz     short loc_180005ADE
0x180005ac4  mov     rdx, [rbp+0E0h]
0x180005acb  mov     ecx, [rbp+98h]
0x180005ad1  call    _XcptFilter_0
0x180005ad6  mov     [rbp+0A0h], eax
0x180005adc  jmp     short loc_180005AE8
0x180005ade  mov     dword ptr [rbp+0A0h], 0
0x180005ae8  mov     eax, [rbp+0A0h]
0x180005aee  add     rsp, 20h
0x180005af2  pop     rbp
0x180005af3  retn
0x180005af5  push    rbp
0x180005af7  sub     rsp, 20h
0x180005afb  mov     rbp, rdx
0x180005afe  cmp     dword ptr [rbp+118h], 1
0x180005b05  ja      short loc_180005B11
0x180005b07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
