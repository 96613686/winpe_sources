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
- `0x180001878`
- `0x180003aec`
- `0x18000acd0`

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
  if ( (_DWORD)fdwReason || dword_1800120C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800120C4 = 1;
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
            if ( dword_1800120C4 )
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
0x180001344  cmp     cs:dword_1800120C0, edx
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
0x180001374  mov     cs:dword_1800120C4, edx
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
0x1800014d3  cmp     cs:dword_1800120C4, 0
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
0x18000ad40  push    rbp
0x18000ad42  sub     rsp, 20h
0x18000ad46  mov     rbp, rdx
0x18000ad49  mov     rax, [rcx]
0x18000ad4c  mov     edx, [rax]
0x18000ad4e  mov     [rbp+0A8h], rcx
0x18000ad55  mov     [rbp+28h], edx
0x18000ad58  mov     eax, [rbp+28h]
0x18000ad5b  cmp     eax, 0E06D7363h
0x18000ad60  jnz     short loc_18000AD76
0x18000ad62  mov     rdx, [rbp+0A8h]
0x18000ad69  mov     ecx, [rbp+28h]
0x18000ad6c  call    _XcptFilter_0
0x18000ad71  mov     [rbp+30h], eax
0x18000ad74  jmp     short loc_18000AD7D
0x18000ad76  mov     dword ptr [rbp+30h], 0
0x18000ad7d  mov     eax, [rbp+30h]
0x18000ad80  add     rsp, 20h
0x18000ad84  pop     rbp
0x18000ad85  retn
0x18000ad87  push    rbp
0x18000ad89  sub     rsp, 20h
0x18000ad8d  mov     rbp, rdx
0x18000ad90  mov     rax, [rcx]
0x18000ad93  mov     edx, [rax]
0x18000ad95  mov     [rbp+0B0h], rcx
0x18000ad9c  mov     [rbp+38h], edx
0x18000ad9f  mov     eax, [rbp+38h]
0x18000ada2  cmp     eax, 0E06D7363h
0x18000ada7  jnz     short loc_18000ADBD
0x18000ada9  mov     rdx, [rbp+0B0h]
0x18000adb0  mov     ecx, [rbp+38h]
0x18000adb3  call    _XcptFilter_0
0x18000adb8  mov     [rbp+40h], eax
0x18000adbb  jmp     short loc_18000ADC4
0x18000adbd  mov     dword ptr [rbp+40h], 0
0x18000adc4  mov     eax, [rbp+40h]
0x18000adc7  add     rsp, 20h
0x18000adcb  pop     rbp
0x18000adcc  retn
0x18000adce  push    rbp
0x18000add0  sub     rsp, 20h
0x18000add4  mov     rbp, rdx
0x18000add7  mov     rax, [rcx]
0x18000adda  mov     edx, [rax]
0x18000addc  mov     [rbp+0B8h], rcx
0x18000ade3  mov     [rbp+48h], edx
0x18000ade6  mov     eax, [rbp+48h]
0x18000ade9  cmp     eax, 0E06D7363h
0x18000adee  jnz     short loc_18000AE04
0x18000adf0  mov     rdx, [rbp+0B8h]
0x18000adf7  mov     ecx, [rbp+48h]
0x18000adfa  call    _XcptFilter_0
0x18000adff  mov     [rbp+50h], eax
0x18000ae02  jmp     short loc_18000AE0B
0x18000ae04  mov     dword ptr [rbp+50h], 0
0x18000ae0b  mov     eax, [rbp+50h]
0x18000ae0e  add     rsp, 20h
0x18000ae12  pop     rbp
0x18000ae13  retn
0x18000ae15  push    rbp
0x18000ae17  sub     rsp, 20h
0x18000ae1b  mov     rbp, rdx
0x18000ae1e  mov     rax, [rcx]
0x18000ae21  mov     edx, [rax]
0x18000ae23  mov     [rbp+0C0h], rcx
0x18000ae2a  mov     [rbp+58h], edx
0x18000ae2d  mov     eax, [rbp+58h]
0x18000ae30  cmp     eax, 0E06D7363h
0x18000ae35  jnz     short loc_18000AE4B
0x18000ae37  mov     rdx, [rbp+0C0h]
0x18000ae3e  mov     ecx, [rbp+58h]
0x18000ae41  call    _XcptFilter_0
0x18000ae46  mov     [rbp+60h], eax
0x18000ae49  jmp     short loc_18000AE52
0x18000ae4b  mov     dword ptr [rbp+60h], 0
0x18000ae52  mov     eax, [rbp+60h]
0x18000ae55  add     rsp, 20h
0x18000ae59  pop     rbp
0x18000ae5a  retn
0x18000ae5c  push    rbp
0x18000ae5e  sub     rsp, 20h
0x18000ae62  mov     rbp, rdx
0x18000ae65  mov     rax, [rcx]
0x18000ae68  mov     edx, [rax]
0x18000ae6a  mov     [rbp+0C8h], rcx
0x18000ae71  mov     [rbp+68h], edx
0x18000ae74  mov     eax, [rbp+68h]
0x18000ae77  cmp     eax, 0E06D7363h
0x18000ae7c  jnz     short loc_18000AE92
0x18000ae7e  mov     rdx, [rbp+0C8h]
0x18000ae85  mov     ecx, [rbp+68h]
0x18000ae88  call    _XcptFilter_0
0x18000ae8d  mov     [rbp+70h], eax
0x18000ae90  jmp     short loc_18000AE99
0x18000ae92  mov     dword ptr [rbp+70h], 0
0x18000ae99  mov     eax, [rbp+70h]
0x18000ae9c  add     rsp, 20h
0x18000aea0  pop     rbp
0x18000aea1  retn
0x18000aea3  push    rbp
0x18000aea5  sub     rsp, 20h
0x18000aea9  mov     rbp, rdx
0x18000aeac  mov     rax, [rcx]
0x18000aeaf  mov     edx, [rax]
0x18000aeb1  mov     [rbp+0D0h], rcx
0x18000aeb8  mov     [rbp+78h], edx
0x18000aebb  mov     eax, [rbp+78h]
0x18000aebe  cmp     eax, 0E06D7363h
0x18000aec3  jnz     short loc_18000AEDC
0x18000aec5  mov     rdx, [rbp+0D0h]
0x18000aecc  mov     ecx, [rbp+78h]
0x18000aecf  call    _XcptFilter_0
0x18000aed4  mov     [rbp+80h], eax
0x18000aeda  jmp     short loc_18000AEE6
0x18000aedc  mov     dword ptr [rbp+80h], 0
0x18000aee6  mov     eax, [rbp+80h]
0x18000aeec  add     rsp, 20h
0x18000aef0  pop     rbp
0x18000aef1  retn
0x18000aef3  push    rbp
0x18000aef5  sub     rsp, 20h
0x18000aef9  mov     rbp, rdx
0x18000aefc  mov     rax, [rcx]
0x18000aeff  mov     edx, [rax]
0x18000af01  mov     [rbp+0D8h], rcx
0x18000af08  mov     [rbp+88h], edx
0x18000af0e  mov     eax, [rbp+88h]
0x18000af14  cmp     eax, 0E06D7363h
0x18000af19  jnz     short loc_18000AF35
0x18000af1b  mov     rdx, [rbp+0D8h]
0x18000af22  mov     ecx, [rbp+88h]
0x18000af28  call    _XcptFilter_0
0x18000af2d  mov     [rbp+90h], eax
0x18000af33  jmp     short loc_18000AF3F
0x18000af35  mov     dword ptr [rbp+90h], 0
0x18000af3f  mov     eax, [rbp+90h]
0x18000af45  add     rsp, 20h
0x18000af49  pop     rbp
0x18000af4a  retn
0x18000af4c  push    rbp
0x18000af4e  sub     rsp, 20h
0x18000af52  mov     rbp, rdx
0x18000af55  mov     rax, [rcx]
0x18000af58  mov     edx, [rax]
0x18000af5a  mov     [rbp+0E0h], rcx
0x18000af61  mov     [rbp+98h], edx
0x18000af67  mov     eax, [rbp+98h]
0x18000af6d  cmp     eax, 0E06D7363h
0x18000af72  jnz     short loc_18000AF8E
0x18000af74  mov     rdx, [rbp+0E0h]
0x18000af7b  mov     ecx, [rbp+98h]
0x18000af81  call    _XcptFilter_0
0x18000af86  mov     [rbp+0A0h], eax
0x18000af8c  jmp     short loc_18000AF98
0x18000af8e  mov     dword ptr [rbp+0A0h], 0
0x18000af98  mov     eax, [rbp+0A0h]
0x18000af9e  add     rsp, 20h
0x18000afa2  pop     rbp
0x18000afa3  retn
0x18000afa5  push    rbp
0x18000afa7  sub     rsp, 20h
0x18000afab  mov     rbp, rdx
0x18000afae  cmp     dword ptr [rbp+118h], 1
0x18000afb5  ja      short loc_18000AFC1
0x18000afb7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
