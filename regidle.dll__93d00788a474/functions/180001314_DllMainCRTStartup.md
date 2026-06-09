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
- `0x180002478`
- `0x180002a10`

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
0x180002a80  push    rbp
0x180002a82  sub     rsp, 20h
0x180002a86  mov     rbp, rdx
0x180002a89  mov     rax, [rcx]
0x180002a8c  mov     edx, [rax]
0x180002a8e  mov     [rbp+0A8h], rcx
0x180002a95  mov     [rbp+28h], edx
0x180002a98  mov     eax, [rbp+28h]
0x180002a9b  cmp     eax, 0E06D7363h
0x180002aa0  jnz     short loc_180002AB6
0x180002aa2  mov     rdx, [rbp+0A8h]
0x180002aa9  mov     ecx, [rbp+28h]
0x180002aac  call    _XcptFilter_0
0x180002ab1  mov     [rbp+30h], eax
0x180002ab4  jmp     short loc_180002ABD
0x180002ab6  mov     dword ptr [rbp+30h], 0
0x180002abd  mov     eax, [rbp+30h]
0x180002ac0  add     rsp, 20h
0x180002ac4  pop     rbp
0x180002ac5  retn
0x180002ac7  push    rbp
0x180002ac9  sub     rsp, 20h
0x180002acd  mov     rbp, rdx
0x180002ad0  mov     rax, [rcx]
0x180002ad3  mov     edx, [rax]
0x180002ad5  mov     [rbp+0B0h], rcx
0x180002adc  mov     [rbp+38h], edx
0x180002adf  mov     eax, [rbp+38h]
0x180002ae2  cmp     eax, 0E06D7363h
0x180002ae7  jnz     short loc_180002AFD
0x180002ae9  mov     rdx, [rbp+0B0h]
0x180002af0  mov     ecx, [rbp+38h]
0x180002af3  call    _XcptFilter_0
0x180002af8  mov     [rbp+40h], eax
0x180002afb  jmp     short loc_180002B04
0x180002afd  mov     dword ptr [rbp+40h], 0
0x180002b04  mov     eax, [rbp+40h]
0x180002b07  add     rsp, 20h
0x180002b0b  pop     rbp
0x180002b0c  retn
0x180002b0e  push    rbp
0x180002b10  sub     rsp, 20h
0x180002b14  mov     rbp, rdx
0x180002b17  mov     rax, [rcx]
0x180002b1a  mov     edx, [rax]
0x180002b1c  mov     [rbp+0B8h], rcx
0x180002b23  mov     [rbp+48h], edx
0x180002b26  mov     eax, [rbp+48h]
0x180002b29  cmp     eax, 0E06D7363h
0x180002b2e  jnz     short loc_180002B44
0x180002b30  mov     rdx, [rbp+0B8h]
0x180002b37  mov     ecx, [rbp+48h]
0x180002b3a  call    _XcptFilter_0
0x180002b3f  mov     [rbp+50h], eax
0x180002b42  jmp     short loc_180002B4B
0x180002b44  mov     dword ptr [rbp+50h], 0
0x180002b4b  mov     eax, [rbp+50h]
0x180002b4e  add     rsp, 20h
0x180002b52  pop     rbp
0x180002b53  retn
0x180002b55  push    rbp
0x180002b57  sub     rsp, 20h
0x180002b5b  mov     rbp, rdx
0x180002b5e  mov     rax, [rcx]
0x180002b61  mov     edx, [rax]
0x180002b63  mov     [rbp+0C0h], rcx
0x180002b6a  mov     [rbp+58h], edx
0x180002b6d  mov     eax, [rbp+58h]
0x180002b70  cmp     eax, 0E06D7363h
0x180002b75  jnz     short loc_180002B8B
0x180002b77  mov     rdx, [rbp+0C0h]
0x180002b7e  mov     ecx, [rbp+58h]
0x180002b81  call    _XcptFilter_0
0x180002b86  mov     [rbp+60h], eax
0x180002b89  jmp     short loc_180002B92
0x180002b8b  mov     dword ptr [rbp+60h], 0
0x180002b92  mov     eax, [rbp+60h]
0x180002b95  add     rsp, 20h
0x180002b99  pop     rbp
0x180002b9a  retn
0x180002b9c  push    rbp
0x180002b9e  sub     rsp, 20h
0x180002ba2  mov     rbp, rdx
0x180002ba5  mov     rax, [rcx]
0x180002ba8  mov     edx, [rax]
0x180002baa  mov     [rbp+0C8h], rcx
0x180002bb1  mov     [rbp+68h], edx
0x180002bb4  mov     eax, [rbp+68h]
0x180002bb7  cmp     eax, 0E06D7363h
0x180002bbc  jnz     short loc_180002BD2
0x180002bbe  mov     rdx, [rbp+0C8h]
0x180002bc5  mov     ecx, [rbp+68h]
0x180002bc8  call    _XcptFilter_0
0x180002bcd  mov     [rbp+70h], eax
0x180002bd0  jmp     short loc_180002BD9
0x180002bd2  mov     dword ptr [rbp+70h], 0
0x180002bd9  mov     eax, [rbp+70h]
0x180002bdc  add     rsp, 20h
0x180002be0  pop     rbp
0x180002be1  retn
0x180002be3  push    rbp
0x180002be5  sub     rsp, 20h
0x180002be9  mov     rbp, rdx
0x180002bec  mov     rax, [rcx]
0x180002bef  mov     edx, [rax]
0x180002bf1  mov     [rbp+0D0h], rcx
0x180002bf8  mov     [rbp+78h], edx
0x180002bfb  mov     eax, [rbp+78h]
0x180002bfe  cmp     eax, 0E06D7363h
0x180002c03  jnz     short loc_180002C1C
0x180002c05  mov     rdx, [rbp+0D0h]
0x180002c0c  mov     ecx, [rbp+78h]
0x180002c0f  call    _XcptFilter_0
0x180002c14  mov     [rbp+80h], eax
0x180002c1a  jmp     short loc_180002C26
0x180002c1c  mov     dword ptr [rbp+80h], 0
0x180002c26  mov     eax, [rbp+80h]
0x180002c2c  add     rsp, 20h
0x180002c30  pop     rbp
0x180002c31  retn
0x180002c33  push    rbp
0x180002c35  sub     rsp, 20h
0x180002c39  mov     rbp, rdx
0x180002c3c  mov     rax, [rcx]
0x180002c3f  mov     edx, [rax]
0x180002c41  mov     [rbp+0D8h], rcx
0x180002c48  mov     [rbp+88h], edx
0x180002c4e  mov     eax, [rbp+88h]
0x180002c54  cmp     eax, 0E06D7363h
0x180002c59  jnz     short loc_180002C75
0x180002c5b  mov     rdx, [rbp+0D8h]
0x180002c62  mov     ecx, [rbp+88h]
0x180002c68  call    _XcptFilter_0
0x180002c6d  mov     [rbp+90h], eax
0x180002c73  jmp     short loc_180002C7F
0x180002c75  mov     dword ptr [rbp+90h], 0
0x180002c7f  mov     eax, [rbp+90h]
0x180002c85  add     rsp, 20h
0x180002c89  pop     rbp
0x180002c8a  retn
0x180002c8c  push    rbp
0x180002c8e  sub     rsp, 20h
0x180002c92  mov     rbp, rdx
0x180002c95  mov     rax, [rcx]
0x180002c98  mov     edx, [rax]
0x180002c9a  mov     [rbp+0E0h], rcx
0x180002ca1  mov     [rbp+98h], edx
0x180002ca7  mov     eax, [rbp+98h]
0x180002cad  cmp     eax, 0E06D7363h
0x180002cb2  jnz     short loc_180002CCE
0x180002cb4  mov     rdx, [rbp+0E0h]
0x180002cbb  mov     ecx, [rbp+98h]
0x180002cc1  call    _XcptFilter_0
0x180002cc6  mov     [rbp+0A0h], eax
0x180002ccc  jmp     short loc_180002CD8
0x180002cce  mov     dword ptr [rbp+0A0h], 0
0x180002cd8  mov     eax, [rbp+0A0h]
0x180002cde  add     rsp, 20h
0x180002ce2  pop     rbp
0x180002ce3  retn
0x180002ce5  push    rbp
0x180002ce7  sub     rsp, 20h
0x180002ceb  mov     rbp, rdx
0x180002cee  cmp     dword ptr [rbp+118h], 1
0x180002cf5  ja      short loc_180002D01
0x180002cf7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
