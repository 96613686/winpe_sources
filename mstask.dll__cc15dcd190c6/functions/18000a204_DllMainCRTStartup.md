# __DllMainCRTStartup

- ea: `0x18000a204`
- end: `0x18000a410`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a1c0`

## callees

- `0x1800064f0`
- `0x180009f90`
- `0x18000a204`
- `0x18000a758`
- `0x18001ab00`

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
  if ( (_DWORD)fdwReason || dword_180023680 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180023684 = 1;
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
            if ( dword_180023684 )
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
0x18000a204  mov     [rsp+lpvReserved], r8
0x18000a209  mov     [rsp+arg_8], edx
0x18000a20d  mov     [rsp+arg_0], rcx
0x18000a212  push    rbx
0x18000a213  push    rsi
0x18000a214  push    rdi
0x18000a215  sub     rsp, 0F0h
0x18000a21c  mov     edi, edx
0x18000a21e  mov     rsi, rcx
0x18000a221  mov     ebx, 1
0x18000a226  cmp     edx, ebx
0x18000a228  ja      short loc_18000A230
0x18000a22a  mov     cs:__native_dllmain_reason, edx
0x18000a230  test    edx, edx
0x18000a232  jnz     short loc_18000A247
0x18000a234  cmp     cs:dword_180023680, edx
0x18000a23a  jnz     short loc_18000A247
0x18000a23c  xor     ebx, ebx
0x18000a23e  mov     [rsp+108h+var_E8], ebx
0x18000a242  jmp     loc_18000A3F4
0x18000a247  lea     eax, [rdx-1]
0x18000a24a  cmp     eax, 1
0x18000a24d  ja      loc_18000A2D4
0x18000a253  mov     rax, cs:_pRawDllMain
0x18000a25a  test    rax, rax
0x18000a25d  jz      short loc_18000A295
0x18000a25f  cmp     edx, 1
0x18000a262  jnz     short loc_18000A26A
0x18000a264  mov     cs:dword_180023684, edx
0x18000a26a  mov     r8, [rsp+108h+lpvReserved]
0x18000a272  call    cs:__guard_dispatch_icall_fptr
0x18000a278  mov     ebx, eax
0x18000a27a  mov     [rsp+108h+var_E8], eax
0x18000a27e  jmp     short loc_18000A295
0x18000a280  xor     ebx, ebx
0x18000a282  mov     [rsp+108h+var_E8], ebx
0x18000a286  mov     edi, [rsp+108h+arg_8]
0x18000a28d  mov     rsi, [rsp+108h+arg_0]
0x18000a295  test    ebx, ebx
0x18000a297  jz      loc_18000A3F4
0x18000a29d  mov     r8, [rsp+108h+lpvReserved]
0x18000a2a5  mov     edx, edi
0x18000a2a7  mov     rcx, rsi
0x18000a2aa  call    _CRT_INIT
0x18000a2af  mov     ebx, eax
0x18000a2b1  mov     [rsp+108h+var_E8], eax
0x18000a2b5  jmp     short loc_18000A2CC
0x18000a2b7  xor     ebx, ebx
0x18000a2b9  mov     [rsp+108h+var_E8], ebx
0x18000a2bd  mov     edi, [rsp+108h+arg_8]
0x18000a2c4  mov     rsi, [rsp+108h+arg_0]
0x18000a2cc  test    ebx, ebx
0x18000a2ce  jz      loc_18000A3F4
0x18000a2d4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000a2dc  mov     edx, edi; fdwReason
0x18000a2de  mov     rcx, rsi; hinstDLL
0x18000a2e1  call    DllMain
0x18000a2e6  mov     ebx, eax
0x18000a2e8  mov     [rsp+108h+var_E8], eax
0x18000a2ec  jmp     short loc_18000A303
0x18000a2ee  xor     ebx, ebx
0x18000a2f0  mov     [rsp+108h+var_E8], ebx
0x18000a2f4  mov     edi, [rsp+108h+arg_8]
0x18000a2fb  mov     rsi, [rsp+108h+arg_0]
0x18000a303  cmp     edi, 1
0x18000a306  jnz     short loc_18000A37F
0x18000a308  test    ebx, ebx
0x18000a30a  jnz     short loc_18000A37F
0x18000a30c  xor     r8d, r8d; lpvReserved
0x18000a30f  xor     edx, edx; fdwReason
0x18000a311  mov     rcx, rsi; hinstDLL
0x18000a314  call    DllMain
0x18000a319  jmp     short loc_18000A32E
0x18000a31b  mov     edi, [rsp+108h+arg_8]
0x18000a322  mov     rsi, [rsp+108h+arg_0]
0x18000a32a  mov     ebx, [rsp+108h+var_E8]
0x18000a32e  xor     r8d, r8d
0x18000a331  xor     edx, edx
0x18000a333  mov     rcx, rsi
0x18000a336  call    _CRT_INIT
0x18000a33b  jmp     short loc_18000A350
0x18000a33d  mov     edi, [rsp+108h+arg_8]
0x18000a344  mov     rsi, [rsp+108h+arg_0]
0x18000a34c  mov     ebx, [rsp+108h+var_E8]
0x18000a350  mov     rax, cs:_pRawDllMain
0x18000a357  test    rax, rax
0x18000a35a  jz      short loc_18000A37F
0x18000a35c  xor     r8d, r8d
0x18000a35f  xor     edx, edx
0x18000a361  mov     rcx, rsi
0x18000a364  call    cs:__guard_dispatch_icall_fptr
0x18000a36a  jmp     short loc_18000A37F
0x18000a36c  mov     edi, [rsp+108h+arg_8]
0x18000a373  mov     rsi, [rsp+108h+arg_0]
0x18000a37b  mov     ebx, [rsp+108h+var_E8]
0x18000a37f  test    edi, edi
0x18000a381  jz      short loc_18000A388
0x18000a383  cmp     edi, 3
0x18000a386  jnz     short loc_18000A3F4
0x18000a388  mov     r8, [rsp+108h+lpvReserved]
0x18000a390  mov     edx, edi
0x18000a392  mov     rcx, rsi
0x18000a395  call    _CRT_INIT
0x18000a39a  mov     ebx, eax
0x18000a39c  mov     [rsp+108h+var_E8], eax
0x18000a3a0  jmp     short loc_18000A3B7
0x18000a3a2  xor     ebx, ebx
0x18000a3a4  mov     [rsp+108h+var_E8], ebx
0x18000a3a8  mov     edi, [rsp+108h+arg_8]
0x18000a3af  mov     rsi, [rsp+108h+arg_0]
0x18000a3b7  mov     rax, cs:_pRawDllMain
0x18000a3be  test    rax, rax
0x18000a3c1  jz      short loc_18000A3F4
0x18000a3c3  cmp     cs:dword_180023684, 0
0x18000a3ca  jz      short loc_18000A3F4
0x18000a3cc  mov     r8, [rsp+108h+lpvReserved]
0x18000a3d4  mov     edx, edi
0x18000a3d6  mov     rcx, rsi
0x18000a3d9  call    cs:__guard_dispatch_icall_fptr
0x18000a3df  mov     ebx, eax
0x18000a3e1  mov     [rsp+108h+var_E8], eax
0x18000a3e5  jmp     short loc_18000A3F4
0x18000a3e7  xor     ebx, ebx
0x18000a3e9  mov     [rsp+108h+var_E8], ebx
0x18000a3ed  mov     edi, [rsp+108h+arg_8]
0x18000a3f4  cmp     edi, 1
0x18000a3f7  ja      short loc_18000A403
0x18000a3f9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000a403  mov     eax, ebx
0x18000a405  add     rsp, 0F0h
0x18000a40c  pop     rdi
0x18000a40d  pop     rsi
0x18000a40e  pop     rbx
0x18000a40f  retn
0x18001abf2  push    rbp
0x18001abf4  sub     rsp, 20h
0x18001abf8  mov     rbp, rdx
0x18001abfb  mov     rax, [rcx]
0x18001abfe  mov     edx, [rax]
0x18001ac00  mov     [rbp+0A8h], rcx
0x18001ac07  mov     [rbp+28h], edx
0x18001ac0a  mov     eax, [rbp+28h]
0x18001ac0d  cmp     eax, 0E06D7363h
0x18001ac12  jnz     short loc_18001AC28
0x18001ac14  mov     rdx, [rbp+0A8h]
0x18001ac1b  mov     ecx, [rbp+28h]
0x18001ac1e  call    _XcptFilter_0
0x18001ac23  mov     [rbp+30h], eax
0x18001ac26  jmp     short loc_18001AC2F
0x18001ac28  mov     dword ptr [rbp+30h], 0
0x18001ac2f  mov     eax, [rbp+30h]
0x18001ac32  add     rsp, 20h
0x18001ac36  pop     rbp
0x18001ac37  retn
0x18001ac39  push    rbp
0x18001ac3b  sub     rsp, 20h
0x18001ac3f  mov     rbp, rdx
0x18001ac42  mov     rax, [rcx]
0x18001ac45  mov     edx, [rax]
0x18001ac47  mov     [rbp+0B0h], rcx
0x18001ac4e  mov     [rbp+38h], edx
0x18001ac51  mov     eax, [rbp+38h]
0x18001ac54  cmp     eax, 0E06D7363h
0x18001ac59  jnz     short loc_18001AC6F
0x18001ac5b  mov     rdx, [rbp+0B0h]
0x18001ac62  mov     ecx, [rbp+38h]
0x18001ac65  call    _XcptFilter_0
0x18001ac6a  mov     [rbp+40h], eax
0x18001ac6d  jmp     short loc_18001AC76
0x18001ac6f  mov     dword ptr [rbp+40h], 0
0x18001ac76  mov     eax, [rbp+40h]
0x18001ac79  add     rsp, 20h
0x18001ac7d  pop     rbp
0x18001ac7e  retn
0x18001ac80  push    rbp
0x18001ac82  sub     rsp, 20h
0x18001ac86  mov     rbp, rdx
0x18001ac89  mov     rax, [rcx]
0x18001ac8c  mov     edx, [rax]
0x18001ac8e  mov     [rbp+0B8h], rcx
0x18001ac95  mov     [rbp+48h], edx
0x18001ac98  mov     eax, [rbp+48h]
0x18001ac9b  cmp     eax, 0E06D7363h
0x18001aca0  jnz     short loc_18001ACB6
0x18001aca2  mov     rdx, [rbp+0B8h]
0x18001aca9  mov     ecx, [rbp+48h]
0x18001acac  call    _XcptFilter_0
0x18001acb1  mov     [rbp+50h], eax
0x18001acb4  jmp     short loc_18001ACBD
0x18001acb6  mov     dword ptr [rbp+50h], 0
0x18001acbd  mov     eax, [rbp+50h]
0x18001acc0  add     rsp, 20h
0x18001acc4  pop     rbp
0x18001acc5  retn
0x18001acc7  push    rbp
0x18001acc9  sub     rsp, 20h
0x18001accd  mov     rbp, rdx
0x18001acd0  mov     rax, [rcx]
0x18001acd3  mov     edx, [rax]
0x18001acd5  mov     [rbp+0C0h], rcx
0x18001acdc  mov     [rbp+58h], edx
0x18001acdf  mov     eax, [rbp+58h]
0x18001ace2  cmp     eax, 0E06D7363h
0x18001ace7  jnz     short loc_18001ACFD
0x18001ace9  mov     rdx, [rbp+0C0h]
0x18001acf0  mov     ecx, [rbp+58h]
0x18001acf3  call    _XcptFilter_0
0x18001acf8  mov     [rbp+60h], eax
0x18001acfb  jmp     short loc_18001AD04
0x18001acfd  mov     dword ptr [rbp+60h], 0
0x18001ad04  mov     eax, [rbp+60h]
0x18001ad07  add     rsp, 20h
0x18001ad0b  pop     rbp
0x18001ad0c  retn
0x18001ad0e  push    rbp
0x18001ad10  sub     rsp, 20h
0x18001ad14  mov     rbp, rdx
0x18001ad17  mov     rax, [rcx]
0x18001ad1a  mov     edx, [rax]
0x18001ad1c  mov     [rbp+0C8h], rcx
0x18001ad23  mov     [rbp+68h], edx
0x18001ad26  mov     eax, [rbp+68h]
0x18001ad29  cmp     eax, 0E06D7363h
0x18001ad2e  jnz     short loc_18001AD44
0x18001ad30  mov     rdx, [rbp+0C8h]
0x18001ad37  mov     ecx, [rbp+68h]
0x18001ad3a  call    _XcptFilter_0
0x18001ad3f  mov     [rbp+70h], eax
0x18001ad42  jmp     short loc_18001AD4B
0x18001ad44  mov     dword ptr [rbp+70h], 0
0x18001ad4b  mov     eax, [rbp+70h]
0x18001ad4e  add     rsp, 20h
0x18001ad52  pop     rbp
0x18001ad53  retn
0x18001ad55  push    rbp
0x18001ad57  sub     rsp, 20h
0x18001ad5b  mov     rbp, rdx
0x18001ad5e  mov     rax, [rcx]
0x18001ad61  mov     edx, [rax]
0x18001ad63  mov     [rbp+0D0h], rcx
0x18001ad6a  mov     [rbp+78h], edx
0x18001ad6d  mov     eax, [rbp+78h]
0x18001ad70  cmp     eax, 0E06D7363h
0x18001ad75  jnz     short loc_18001AD8E
0x18001ad77  mov     rdx, [rbp+0D0h]
0x18001ad7e  mov     ecx, [rbp+78h]
0x18001ad81  call    _XcptFilter_0
0x18001ad86  mov     [rbp+80h], eax
0x18001ad8c  jmp     short loc_18001AD98
0x18001ad8e  mov     dword ptr [rbp+80h], 0
0x18001ad98  mov     eax, [rbp+80h]
0x18001ad9e  add     rsp, 20h
0x18001ada2  pop     rbp
0x18001ada3  retn
0x18001ada5  push    rbp
0x18001ada7  sub     rsp, 20h
0x18001adab  mov     rbp, rdx
0x18001adae  mov     rax, [rcx]
0x18001adb1  mov     edx, [rax]
0x18001adb3  mov     [rbp+0D8h], rcx
0x18001adba  mov     [rbp+88h], edx
0x18001adc0  mov     eax, [rbp+88h]
0x18001adc6  cmp     eax, 0E06D7363h
0x18001adcb  jnz     short loc_18001ADE7
0x18001adcd  mov     rdx, [rbp+0D8h]
0x18001add4  mov     ecx, [rbp+88h]
0x18001adda  call    _XcptFilter_0
0x18001addf  mov     [rbp+90h], eax
0x18001ade5  jmp     short loc_18001ADF1
0x18001ade7  mov     dword ptr [rbp+90h], 0
0x18001adf1  mov     eax, [rbp+90h]
0x18001adf7  add     rsp, 20h
0x18001adfb  pop     rbp
0x18001adfc  retn
0x18001adfe  push    rbp
0x18001ae00  sub     rsp, 20h
0x18001ae04  mov     rbp, rdx
0x18001ae07  mov     rax, [rcx]
0x18001ae0a  mov     edx, [rax]
0x18001ae0c  mov     [rbp+0E0h], rcx
0x18001ae13  mov     [rbp+98h], edx
0x18001ae19  mov     eax, [rbp+98h]
0x18001ae1f  cmp     eax, 0E06D7363h
0x18001ae24  jnz     short loc_18001AE40
0x18001ae26  mov     rdx, [rbp+0E0h]
0x18001ae2d  mov     ecx, [rbp+98h]
0x18001ae33  call    _XcptFilter_0
0x18001ae38  mov     [rbp+0A0h], eax
0x18001ae3e  jmp     short loc_18001AE4A
0x18001ae40  mov     dword ptr [rbp+0A0h], 0
0x18001ae4a  mov     eax, [rbp+0A0h]
0x18001ae50  add     rsp, 20h
0x18001ae54  pop     rbp
0x18001ae55  retn
0x18001ae57  push    rbp
0x18001ae59  sub     rsp, 20h
0x18001ae5d  mov     rbp, rdx
0x18001ae60  cmp     dword ptr [rbp+118h], 1
0x18001ae67  ja      short loc_18001AE73
0x18001ae69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
