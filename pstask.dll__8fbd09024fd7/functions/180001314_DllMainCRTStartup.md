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
- `0x180002948`
- `0x180002c20`

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
  if ( (_DWORD)fdwReason || dword_1800060A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800060A4 = 1;
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
            if ( dword_1800060A4 )
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
0x180001344  cmp     cs:dword_1800060A0, edx
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
0x180001374  mov     cs:dword_1800060A4, edx
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
0x1800014d3  cmp     cs:dword_1800060A4, 0
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
0x180002c90  push    rbp
0x180002c92  sub     rsp, 20h
0x180002c96  mov     rbp, rdx
0x180002c99  mov     rax, [rcx]
0x180002c9c  mov     edx, [rax]
0x180002c9e  mov     [rbp+0A8h], rcx
0x180002ca5  mov     [rbp+28h], edx
0x180002ca8  mov     eax, [rbp+28h]
0x180002cab  cmp     eax, 0E06D7363h
0x180002cb0  jnz     short loc_180002CC6
0x180002cb2  mov     rdx, [rbp+0A8h]
0x180002cb9  mov     ecx, [rbp+28h]
0x180002cbc  call    _XcptFilter_0
0x180002cc1  mov     [rbp+30h], eax
0x180002cc4  jmp     short loc_180002CCD
0x180002cc6  mov     dword ptr [rbp+30h], 0
0x180002ccd  mov     eax, [rbp+30h]
0x180002cd0  add     rsp, 20h
0x180002cd4  pop     rbp
0x180002cd5  retn
0x180002cd7  push    rbp
0x180002cd9  sub     rsp, 20h
0x180002cdd  mov     rbp, rdx
0x180002ce0  mov     rax, [rcx]
0x180002ce3  mov     edx, [rax]
0x180002ce5  mov     [rbp+0B0h], rcx
0x180002cec  mov     [rbp+38h], edx
0x180002cef  mov     eax, [rbp+38h]
0x180002cf2  cmp     eax, 0E06D7363h
0x180002cf7  jnz     short loc_180002D0D
0x180002cf9  mov     rdx, [rbp+0B0h]
0x180002d00  mov     ecx, [rbp+38h]
0x180002d03  call    _XcptFilter_0
0x180002d08  mov     [rbp+40h], eax
0x180002d0b  jmp     short loc_180002D14
0x180002d0d  mov     dword ptr [rbp+40h], 0
0x180002d14  mov     eax, [rbp+40h]
0x180002d17  add     rsp, 20h
0x180002d1b  pop     rbp
0x180002d1c  retn
0x180002d1e  push    rbp
0x180002d20  sub     rsp, 20h
0x180002d24  mov     rbp, rdx
0x180002d27  mov     rax, [rcx]
0x180002d2a  mov     edx, [rax]
0x180002d2c  mov     [rbp+0B8h], rcx
0x180002d33  mov     [rbp+48h], edx
0x180002d36  mov     eax, [rbp+48h]
0x180002d39  cmp     eax, 0E06D7363h
0x180002d3e  jnz     short loc_180002D54
0x180002d40  mov     rdx, [rbp+0B8h]
0x180002d47  mov     ecx, [rbp+48h]
0x180002d4a  call    _XcptFilter_0
0x180002d4f  mov     [rbp+50h], eax
0x180002d52  jmp     short loc_180002D5B
0x180002d54  mov     dword ptr [rbp+50h], 0
0x180002d5b  mov     eax, [rbp+50h]
0x180002d5e  add     rsp, 20h
0x180002d62  pop     rbp
0x180002d63  retn
0x180002d65  push    rbp
0x180002d67  sub     rsp, 20h
0x180002d6b  mov     rbp, rdx
0x180002d6e  mov     rax, [rcx]
0x180002d71  mov     edx, [rax]
0x180002d73  mov     [rbp+0C0h], rcx
0x180002d7a  mov     [rbp+58h], edx
0x180002d7d  mov     eax, [rbp+58h]
0x180002d80  cmp     eax, 0E06D7363h
0x180002d85  jnz     short loc_180002D9B
0x180002d87  mov     rdx, [rbp+0C0h]
0x180002d8e  mov     ecx, [rbp+58h]
0x180002d91  call    _XcptFilter_0
0x180002d96  mov     [rbp+60h], eax
0x180002d99  jmp     short loc_180002DA2
0x180002d9b  mov     dword ptr [rbp+60h], 0
0x180002da2  mov     eax, [rbp+60h]
0x180002da5  add     rsp, 20h
0x180002da9  pop     rbp
0x180002daa  retn
0x180002dac  push    rbp
0x180002dae  sub     rsp, 20h
0x180002db2  mov     rbp, rdx
0x180002db5  mov     rax, [rcx]
0x180002db8  mov     edx, [rax]
0x180002dba  mov     [rbp+0C8h], rcx
0x180002dc1  mov     [rbp+68h], edx
0x180002dc4  mov     eax, [rbp+68h]
0x180002dc7  cmp     eax, 0E06D7363h
0x180002dcc  jnz     short loc_180002DE2
0x180002dce  mov     rdx, [rbp+0C8h]
0x180002dd5  mov     ecx, [rbp+68h]
0x180002dd8  call    _XcptFilter_0
0x180002ddd  mov     [rbp+70h], eax
0x180002de0  jmp     short loc_180002DE9
0x180002de2  mov     dword ptr [rbp+70h], 0
0x180002de9  mov     eax, [rbp+70h]
0x180002dec  add     rsp, 20h
0x180002df0  pop     rbp
0x180002df1  retn
0x180002df3  push    rbp
0x180002df5  sub     rsp, 20h
0x180002df9  mov     rbp, rdx
0x180002dfc  mov     rax, [rcx]
0x180002dff  mov     edx, [rax]
0x180002e01  mov     [rbp+0D0h], rcx
0x180002e08  mov     [rbp+78h], edx
0x180002e0b  mov     eax, [rbp+78h]
0x180002e0e  cmp     eax, 0E06D7363h
0x180002e13  jnz     short loc_180002E2C
0x180002e15  mov     rdx, [rbp+0D0h]
0x180002e1c  mov     ecx, [rbp+78h]
0x180002e1f  call    _XcptFilter_0
0x180002e24  mov     [rbp+80h], eax
0x180002e2a  jmp     short loc_180002E36
0x180002e2c  mov     dword ptr [rbp+80h], 0
0x180002e36  mov     eax, [rbp+80h]
0x180002e3c  add     rsp, 20h
0x180002e40  pop     rbp
0x180002e41  retn
0x180002e43  push    rbp
0x180002e45  sub     rsp, 20h
0x180002e49  mov     rbp, rdx
0x180002e4c  mov     rax, [rcx]
0x180002e4f  mov     edx, [rax]
0x180002e51  mov     [rbp+0D8h], rcx
0x180002e58  mov     [rbp+88h], edx
0x180002e5e  mov     eax, [rbp+88h]
0x180002e64  cmp     eax, 0E06D7363h
0x180002e69  jnz     short loc_180002E85
0x180002e6b  mov     rdx, [rbp+0D8h]
0x180002e72  mov     ecx, [rbp+88h]
0x180002e78  call    _XcptFilter_0
0x180002e7d  mov     [rbp+90h], eax
0x180002e83  jmp     short loc_180002E8F
0x180002e85  mov     dword ptr [rbp+90h], 0
0x180002e8f  mov     eax, [rbp+90h]
0x180002e95  add     rsp, 20h
0x180002e99  pop     rbp
0x180002e9a  retn
0x180002e9c  push    rbp
0x180002e9e  sub     rsp, 20h
0x180002ea2  mov     rbp, rdx
0x180002ea5  mov     rax, [rcx]
0x180002ea8  mov     edx, [rax]
0x180002eaa  mov     [rbp+0E0h], rcx
0x180002eb1  mov     [rbp+98h], edx
0x180002eb7  mov     eax, [rbp+98h]
0x180002ebd  cmp     eax, 0E06D7363h
0x180002ec2  jnz     short loc_180002EDE
0x180002ec4  mov     rdx, [rbp+0E0h]
0x180002ecb  mov     ecx, [rbp+98h]
0x180002ed1  call    _XcptFilter_0
0x180002ed6  mov     [rbp+0A0h], eax
0x180002edc  jmp     short loc_180002EE8
0x180002ede  mov     dword ptr [rbp+0A0h], 0
0x180002ee8  mov     eax, [rbp+0A0h]
0x180002eee  add     rsp, 20h
0x180002ef2  pop     rbp
0x180002ef3  retn
0x180002ef5  push    rbp
0x180002ef7  sub     rsp, 20h
0x180002efb  mov     rbp, rdx
0x180002efe  cmp     dword ptr [rbp+118h], 1
0x180002f05  ja      short loc_180002F11
0x180002f07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
