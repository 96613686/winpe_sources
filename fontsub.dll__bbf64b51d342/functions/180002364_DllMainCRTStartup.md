# __DllMainCRTStartup

- ea: `0x180002364`
- end: `0x180002570`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002320`

## callees

- `0x1800020f0`
- `0x180002364`
- `0x180002576`
- `0x180002760`
- `0x18001ac30`

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
  if ( (_DWORD)fdwReason || dword_1800215A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800215A4 = 1;
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
            if ( dword_1800215A4 )
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
0x180002364  mov     [rsp+lpvReserved], r8
0x180002369  mov     [rsp+arg_8], edx
0x18000236d  mov     [rsp+arg_0], rcx
0x180002372  push    rbx
0x180002373  push    rsi
0x180002374  push    rdi
0x180002375  sub     rsp, 0F0h
0x18000237c  mov     edi, edx
0x18000237e  mov     rsi, rcx
0x180002381  mov     ebx, 1
0x180002386  cmp     edx, ebx
0x180002388  ja      short loc_180002390
0x18000238a  mov     cs:__native_dllmain_reason, edx
0x180002390  test    edx, edx
0x180002392  jnz     short loc_1800023A7
0x180002394  cmp     cs:dword_1800215A0, edx
0x18000239a  jnz     short loc_1800023A7
0x18000239c  xor     ebx, ebx
0x18000239e  mov     [rsp+108h+var_E8], ebx
0x1800023a2  jmp     loc_180002554
0x1800023a7  lea     eax, [rdx-1]
0x1800023aa  cmp     eax, 1
0x1800023ad  ja      loc_180002434
0x1800023b3  mov     rax, cs:_pRawDllMain
0x1800023ba  test    rax, rax
0x1800023bd  jz      short loc_1800023F5
0x1800023bf  cmp     edx, 1
0x1800023c2  jnz     short loc_1800023CA
0x1800023c4  mov     cs:dword_1800215A4, edx
0x1800023ca  mov     r8, [rsp+108h+lpvReserved]
0x1800023d2  call    cs:__guard_dispatch_icall_fptr
0x1800023d8  mov     ebx, eax
0x1800023da  mov     [rsp+108h+var_E8], eax
0x1800023de  jmp     short loc_1800023F5
0x1800023e0  xor     ebx, ebx
0x1800023e2  mov     [rsp+108h+var_E8], ebx
0x1800023e6  mov     edi, [rsp+108h+arg_8]
0x1800023ed  mov     rsi, [rsp+108h+arg_0]
0x1800023f5  test    ebx, ebx
0x1800023f7  jz      loc_180002554
0x1800023fd  mov     r8, [rsp+108h+lpvReserved]
0x180002405  mov     edx, edi
0x180002407  mov     rcx, rsi
0x18000240a  call    _CRT_INIT
0x18000240f  mov     ebx, eax
0x180002411  mov     [rsp+108h+var_E8], eax
0x180002415  jmp     short loc_18000242C
0x180002417  xor     ebx, ebx
0x180002419  mov     [rsp+108h+var_E8], ebx
0x18000241d  mov     edi, [rsp+108h+arg_8]
0x180002424  mov     rsi, [rsp+108h+arg_0]
0x18000242c  test    ebx, ebx
0x18000242e  jz      loc_180002554
0x180002434  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000243c  mov     edx, edi; fdwReason
0x18000243e  mov     rcx, rsi; hinstDLL
0x180002441  call    DllMain
0x180002446  mov     ebx, eax
0x180002448  mov     [rsp+108h+var_E8], eax
0x18000244c  jmp     short loc_180002463
0x18000244e  xor     ebx, ebx
0x180002450  mov     [rsp+108h+var_E8], ebx
0x180002454  mov     edi, [rsp+108h+arg_8]
0x18000245b  mov     rsi, [rsp+108h+arg_0]
0x180002463  cmp     edi, 1
0x180002466  jnz     short loc_1800024DF
0x180002468  test    ebx, ebx
0x18000246a  jnz     short loc_1800024DF
0x18000246c  xor     r8d, r8d; lpvReserved
0x18000246f  xor     edx, edx; fdwReason
0x180002471  mov     rcx, rsi; hinstDLL
0x180002474  call    DllMain
0x180002479  jmp     short loc_18000248E
0x18000247b  mov     edi, [rsp+108h+arg_8]
0x180002482  mov     rsi, [rsp+108h+arg_0]
0x18000248a  mov     ebx, [rsp+108h+var_E8]
0x18000248e  xor     r8d, r8d
0x180002491  xor     edx, edx
0x180002493  mov     rcx, rsi
0x180002496  call    _CRT_INIT
0x18000249b  jmp     short loc_1800024B0
0x18000249d  mov     edi, [rsp+108h+arg_8]
0x1800024a4  mov     rsi, [rsp+108h+arg_0]
0x1800024ac  mov     ebx, [rsp+108h+var_E8]
0x1800024b0  mov     rax, cs:_pRawDllMain
0x1800024b7  test    rax, rax
0x1800024ba  jz      short loc_1800024DF
0x1800024bc  xor     r8d, r8d
0x1800024bf  xor     edx, edx
0x1800024c1  mov     rcx, rsi
0x1800024c4  call    cs:__guard_dispatch_icall_fptr
0x1800024ca  jmp     short loc_1800024DF
0x1800024cc  mov     edi, [rsp+108h+arg_8]
0x1800024d3  mov     rsi, [rsp+108h+arg_0]
0x1800024db  mov     ebx, [rsp+108h+var_E8]
0x1800024df  test    edi, edi
0x1800024e1  jz      short loc_1800024E8
0x1800024e3  cmp     edi, 3
0x1800024e6  jnz     short loc_180002554
0x1800024e8  mov     r8, [rsp+108h+lpvReserved]
0x1800024f0  mov     edx, edi
0x1800024f2  mov     rcx, rsi
0x1800024f5  call    _CRT_INIT
0x1800024fa  mov     ebx, eax
0x1800024fc  mov     [rsp+108h+var_E8], eax
0x180002500  jmp     short loc_180002517
0x180002502  xor     ebx, ebx
0x180002504  mov     [rsp+108h+var_E8], ebx
0x180002508  mov     edi, [rsp+108h+arg_8]
0x18000250f  mov     rsi, [rsp+108h+arg_0]
0x180002517  mov     rax, cs:_pRawDllMain
0x18000251e  test    rax, rax
0x180002521  jz      short loc_180002554
0x180002523  cmp     cs:dword_1800215A4, 0
0x18000252a  jz      short loc_180002554
0x18000252c  mov     r8, [rsp+108h+lpvReserved]
0x180002534  mov     edx, edi
0x180002536  mov     rcx, rsi
0x180002539  call    cs:__guard_dispatch_icall_fptr
0x18000253f  mov     ebx, eax
0x180002541  mov     [rsp+108h+var_E8], eax
0x180002545  jmp     short loc_180002554
0x180002547  xor     ebx, ebx
0x180002549  mov     [rsp+108h+var_E8], ebx
0x18000254d  mov     edi, [rsp+108h+arg_8]
0x180002554  cmp     edi, 1
0x180002557  ja      short loc_180002563
0x180002559  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002563  mov     eax, ebx
0x180002565  add     rsp, 0F0h
0x18000256c  pop     rdi
0x18000256d  pop     rsi
0x18000256e  pop     rbx
0x18000256f  retn
0x18001ad40  push    rbp
0x18001ad42  sub     rsp, 20h
0x18001ad46  mov     rbp, rdx
0x18001ad49  mov     rax, [rcx]
0x18001ad4c  mov     edx, [rax]
0x18001ad4e  mov     [rbp+0A8h], rcx
0x18001ad55  mov     [rbp+28h], edx
0x18001ad58  mov     eax, [rbp+28h]
0x18001ad5b  cmp     eax, 0E06D7363h
0x18001ad60  jnz     short loc_18001AD76
0x18001ad62  mov     rdx, [rbp+0A8h]
0x18001ad69  mov     ecx, [rbp+28h]
0x18001ad6c  call    _XcptFilter_0
0x18001ad71  mov     [rbp+30h], eax
0x18001ad74  jmp     short loc_18001AD7D
0x18001ad76  mov     dword ptr [rbp+30h], 0
0x18001ad7d  mov     eax, [rbp+30h]
0x18001ad80  add     rsp, 20h
0x18001ad84  pop     rbp
0x18001ad85  retn
0x18001ad87  push    rbp
0x18001ad89  sub     rsp, 20h
0x18001ad8d  mov     rbp, rdx
0x18001ad90  mov     rax, [rcx]
0x18001ad93  mov     edx, [rax]
0x18001ad95  mov     [rbp+0B0h], rcx
0x18001ad9c  mov     [rbp+38h], edx
0x18001ad9f  mov     eax, [rbp+38h]
0x18001ada2  cmp     eax, 0E06D7363h
0x18001ada7  jnz     short loc_18001ADBD
0x18001ada9  mov     rdx, [rbp+0B0h]
0x18001adb0  mov     ecx, [rbp+38h]
0x18001adb3  call    _XcptFilter_0
0x18001adb8  mov     [rbp+40h], eax
0x18001adbb  jmp     short loc_18001ADC4
0x18001adbd  mov     dword ptr [rbp+40h], 0
0x18001adc4  mov     eax, [rbp+40h]
0x18001adc7  add     rsp, 20h
0x18001adcb  pop     rbp
0x18001adcc  retn
0x18001adce  push    rbp
0x18001add0  sub     rsp, 20h
0x18001add4  mov     rbp, rdx
0x18001add7  mov     rax, [rcx]
0x18001adda  mov     edx, [rax]
0x18001addc  mov     [rbp+0B8h], rcx
0x18001ade3  mov     [rbp+48h], edx
0x18001ade6  mov     eax, [rbp+48h]
0x18001ade9  cmp     eax, 0E06D7363h
0x18001adee  jnz     short loc_18001AE04
0x18001adf0  mov     rdx, [rbp+0B8h]
0x18001adf7  mov     ecx, [rbp+48h]
0x18001adfa  call    _XcptFilter_0
0x18001adff  mov     [rbp+50h], eax
0x18001ae02  jmp     short loc_18001AE0B
0x18001ae04  mov     dword ptr [rbp+50h], 0
0x18001ae0b  mov     eax, [rbp+50h]
0x18001ae0e  add     rsp, 20h
0x18001ae12  pop     rbp
0x18001ae13  retn
0x18001ae15  push    rbp
0x18001ae17  sub     rsp, 20h
0x18001ae1b  mov     rbp, rdx
0x18001ae1e  mov     rax, [rcx]
0x18001ae21  mov     edx, [rax]
0x18001ae23  mov     [rbp+0C0h], rcx
0x18001ae2a  mov     [rbp+58h], edx
0x18001ae2d  mov     eax, [rbp+58h]
0x18001ae30  cmp     eax, 0E06D7363h
0x18001ae35  jnz     short loc_18001AE4B
0x18001ae37  mov     rdx, [rbp+0C0h]
0x18001ae3e  mov     ecx, [rbp+58h]
0x18001ae41  call    _XcptFilter_0
0x18001ae46  mov     [rbp+60h], eax
0x18001ae49  jmp     short loc_18001AE52
0x18001ae4b  mov     dword ptr [rbp+60h], 0
0x18001ae52  mov     eax, [rbp+60h]
0x18001ae55  add     rsp, 20h
0x18001ae59  pop     rbp
0x18001ae5a  retn
0x18001ae5c  push    rbp
0x18001ae5e  sub     rsp, 20h
0x18001ae62  mov     rbp, rdx
0x18001ae65  mov     rax, [rcx]
0x18001ae68  mov     edx, [rax]
0x18001ae6a  mov     [rbp+0C8h], rcx
0x18001ae71  mov     [rbp+68h], edx
0x18001ae74  mov     eax, [rbp+68h]
0x18001ae77  cmp     eax, 0E06D7363h
0x18001ae7c  jnz     short loc_18001AE92
0x18001ae7e  mov     rdx, [rbp+0C8h]
0x18001ae85  mov     ecx, [rbp+68h]
0x18001ae88  call    _XcptFilter_0
0x18001ae8d  mov     [rbp+70h], eax
0x18001ae90  jmp     short loc_18001AE99
0x18001ae92  mov     dword ptr [rbp+70h], 0
0x18001ae99  mov     eax, [rbp+70h]
0x18001ae9c  add     rsp, 20h
0x18001aea0  pop     rbp
0x18001aea1  retn
0x18001aea3  push    rbp
0x18001aea5  sub     rsp, 20h
0x18001aea9  mov     rbp, rdx
0x18001aeac  mov     rax, [rcx]
0x18001aeaf  mov     edx, [rax]
0x18001aeb1  mov     [rbp+0D0h], rcx
0x18001aeb8  mov     [rbp+78h], edx
0x18001aebb  mov     eax, [rbp+78h]
0x18001aebe  cmp     eax, 0E06D7363h
0x18001aec3  jnz     short loc_18001AEDC
0x18001aec5  mov     rdx, [rbp+0D0h]
0x18001aecc  mov     ecx, [rbp+78h]
0x18001aecf  call    _XcptFilter_0
0x18001aed4  mov     [rbp+80h], eax
0x18001aeda  jmp     short loc_18001AEE6
0x18001aedc  mov     dword ptr [rbp+80h], 0
0x18001aee6  mov     eax, [rbp+80h]
0x18001aeec  add     rsp, 20h
0x18001aef0  pop     rbp
0x18001aef1  retn
0x18001aef3  push    rbp
0x18001aef5  sub     rsp, 20h
0x18001aef9  mov     rbp, rdx
0x18001aefc  mov     rax, [rcx]
0x18001aeff  mov     edx, [rax]
0x18001af01  mov     [rbp+0D8h], rcx
0x18001af08  mov     [rbp+88h], edx
0x18001af0e  mov     eax, [rbp+88h]
0x18001af14  cmp     eax, 0E06D7363h
0x18001af19  jnz     short loc_18001AF35
0x18001af1b  mov     rdx, [rbp+0D8h]
0x18001af22  mov     ecx, [rbp+88h]
0x18001af28  call    _XcptFilter_0
0x18001af2d  mov     [rbp+90h], eax
0x18001af33  jmp     short loc_18001AF3F
0x18001af35  mov     dword ptr [rbp+90h], 0
0x18001af3f  mov     eax, [rbp+90h]
0x18001af45  add     rsp, 20h
0x18001af49  pop     rbp
0x18001af4a  retn
0x18001af4c  push    rbp
0x18001af4e  sub     rsp, 20h
0x18001af52  mov     rbp, rdx
0x18001af55  mov     rax, [rcx]
0x18001af58  mov     edx, [rax]
0x18001af5a  mov     [rbp+0E0h], rcx
0x18001af61  mov     [rbp+98h], edx
0x18001af67  mov     eax, [rbp+98h]
0x18001af6d  cmp     eax, 0E06D7363h
0x18001af72  jnz     short loc_18001AF8E
0x18001af74  mov     rdx, [rbp+0E0h]
0x18001af7b  mov     ecx, [rbp+98h]
0x18001af81  call    _XcptFilter_0
0x18001af86  mov     [rbp+0A0h], eax
0x18001af8c  jmp     short loc_18001AF98
0x18001af8e  mov     dword ptr [rbp+0A0h], 0
0x18001af98  mov     eax, [rbp+0A0h]
0x18001af9e  add     rsp, 20h
0x18001afa2  pop     rbp
0x18001afa3  retn
0x18001afa5  push    rbp
0x18001afa7  sub     rsp, 20h
0x18001afab  mov     rbp, rdx
0x18001afae  cmp     dword ptr [rbp+118h], 1
0x18001afb5  ja      short loc_18001AFC1
0x18001afb7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
