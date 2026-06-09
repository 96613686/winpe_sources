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
- `0x180001560`
- `0x180001738`
- `0x18000ee50`

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
  if ( (_DWORD)fdwReason || dword_180017660 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180017664 = 1;
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
            if ( dword_180017664 )
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
0x180001344  cmp     cs:dword_180017660, edx
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
0x180001374  mov     cs:dword_180017664, edx
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
0x1800014d3  cmp     cs:dword_180017664, 0
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
0x18000eec0  push    rbp
0x18000eec2  sub     rsp, 20h
0x18000eec6  mov     rbp, rdx
0x18000eec9  mov     rax, [rcx]
0x18000eecc  mov     edx, [rax]
0x18000eece  mov     [rbp+0A8h], rcx
0x18000eed5  mov     [rbp+28h], edx
0x18000eed8  mov     eax, [rbp+28h]
0x18000eedb  cmp     eax, 0E06D7363h
0x18000eee0  jnz     short loc_18000EEF6
0x18000eee2  mov     rdx, [rbp+0A8h]
0x18000eee9  mov     ecx, [rbp+28h]
0x18000eeec  call    _XcptFilter_0
0x18000eef1  mov     [rbp+30h], eax
0x18000eef4  jmp     short loc_18000EEFD
0x18000eef6  mov     dword ptr [rbp+30h], 0
0x18000eefd  mov     eax, [rbp+30h]
0x18000ef00  add     rsp, 20h
0x18000ef04  pop     rbp
0x18000ef05  retn
0x18000ef07  push    rbp
0x18000ef09  sub     rsp, 20h
0x18000ef0d  mov     rbp, rdx
0x18000ef10  mov     rax, [rcx]
0x18000ef13  mov     edx, [rax]
0x18000ef15  mov     [rbp+0B0h], rcx
0x18000ef1c  mov     [rbp+38h], edx
0x18000ef1f  mov     eax, [rbp+38h]
0x18000ef22  cmp     eax, 0E06D7363h
0x18000ef27  jnz     short loc_18000EF3D
0x18000ef29  mov     rdx, [rbp+0B0h]
0x18000ef30  mov     ecx, [rbp+38h]
0x18000ef33  call    _XcptFilter_0
0x18000ef38  mov     [rbp+40h], eax
0x18000ef3b  jmp     short loc_18000EF44
0x18000ef3d  mov     dword ptr [rbp+40h], 0
0x18000ef44  mov     eax, [rbp+40h]
0x18000ef47  add     rsp, 20h
0x18000ef4b  pop     rbp
0x18000ef4c  retn
0x18000ef4e  push    rbp
0x18000ef50  sub     rsp, 20h
0x18000ef54  mov     rbp, rdx
0x18000ef57  mov     rax, [rcx]
0x18000ef5a  mov     edx, [rax]
0x18000ef5c  mov     [rbp+0B8h], rcx
0x18000ef63  mov     [rbp+48h], edx
0x18000ef66  mov     eax, [rbp+48h]
0x18000ef69  cmp     eax, 0E06D7363h
0x18000ef6e  jnz     short loc_18000EF84
0x18000ef70  mov     rdx, [rbp+0B8h]
0x18000ef77  mov     ecx, [rbp+48h]
0x18000ef7a  call    _XcptFilter_0
0x18000ef7f  mov     [rbp+50h], eax
0x18000ef82  jmp     short loc_18000EF8B
0x18000ef84  mov     dword ptr [rbp+50h], 0
0x18000ef8b  mov     eax, [rbp+50h]
0x18000ef8e  add     rsp, 20h
0x18000ef92  pop     rbp
0x18000ef93  retn
0x18000ef95  push    rbp
0x18000ef97  sub     rsp, 20h
0x18000ef9b  mov     rbp, rdx
0x18000ef9e  mov     rax, [rcx]
0x18000efa1  mov     edx, [rax]
0x18000efa3  mov     [rbp+0C0h], rcx
0x18000efaa  mov     [rbp+58h], edx
0x18000efad  mov     eax, [rbp+58h]
0x18000efb0  cmp     eax, 0E06D7363h
0x18000efb5  jnz     short loc_18000EFCB
0x18000efb7  mov     rdx, [rbp+0C0h]
0x18000efbe  mov     ecx, [rbp+58h]
0x18000efc1  call    _XcptFilter_0
0x18000efc6  mov     [rbp+60h], eax
0x18000efc9  jmp     short loc_18000EFD2
0x18000efcb  mov     dword ptr [rbp+60h], 0
0x18000efd2  mov     eax, [rbp+60h]
0x18000efd5  add     rsp, 20h
0x18000efd9  pop     rbp
0x18000efda  retn
0x18000efdc  push    rbp
0x18000efde  sub     rsp, 20h
0x18000efe2  mov     rbp, rdx
0x18000efe5  mov     rax, [rcx]
0x18000efe8  mov     edx, [rax]
0x18000efea  mov     [rbp+0C8h], rcx
0x18000eff1  mov     [rbp+68h], edx
0x18000eff4  mov     eax, [rbp+68h]
0x18000eff7  cmp     eax, 0E06D7363h
0x18000effc  jnz     short loc_18000F012
0x18000effe  mov     rdx, [rbp+0C8h]
0x18000f005  mov     ecx, [rbp+68h]
0x18000f008  call    _XcptFilter_0
0x18000f00d  mov     [rbp+70h], eax
0x18000f010  jmp     short loc_18000F019
0x18000f012  mov     dword ptr [rbp+70h], 0
0x18000f019  mov     eax, [rbp+70h]
0x18000f01c  add     rsp, 20h
0x18000f020  pop     rbp
0x18000f021  retn
0x18000f023  push    rbp
0x18000f025  sub     rsp, 20h
0x18000f029  mov     rbp, rdx
0x18000f02c  mov     rax, [rcx]
0x18000f02f  mov     edx, [rax]
0x18000f031  mov     [rbp+0D0h], rcx
0x18000f038  mov     [rbp+78h], edx
0x18000f03b  mov     eax, [rbp+78h]
0x18000f03e  cmp     eax, 0E06D7363h
0x18000f043  jnz     short loc_18000F05C
0x18000f045  mov     rdx, [rbp+0D0h]
0x18000f04c  mov     ecx, [rbp+78h]
0x18000f04f  call    _XcptFilter_0
0x18000f054  mov     [rbp+80h], eax
0x18000f05a  jmp     short loc_18000F066
0x18000f05c  mov     dword ptr [rbp+80h], 0
0x18000f066  mov     eax, [rbp+80h]
0x18000f06c  add     rsp, 20h
0x18000f070  pop     rbp
0x18000f071  retn
0x18000f073  push    rbp
0x18000f075  sub     rsp, 20h
0x18000f079  mov     rbp, rdx
0x18000f07c  mov     rax, [rcx]
0x18000f07f  mov     edx, [rax]
0x18000f081  mov     [rbp+0D8h], rcx
0x18000f088  mov     [rbp+88h], edx
0x18000f08e  mov     eax, [rbp+88h]
0x18000f094  cmp     eax, 0E06D7363h
0x18000f099  jnz     short loc_18000F0B5
0x18000f09b  mov     rdx, [rbp+0D8h]
0x18000f0a2  mov     ecx, [rbp+88h]
0x18000f0a8  call    _XcptFilter_0
0x18000f0ad  mov     [rbp+90h], eax
0x18000f0b3  jmp     short loc_18000F0BF
0x18000f0b5  mov     dword ptr [rbp+90h], 0
0x18000f0bf  mov     eax, [rbp+90h]
0x18000f0c5  add     rsp, 20h
0x18000f0c9  pop     rbp
0x18000f0ca  retn
0x18000f0cc  push    rbp
0x18000f0ce  sub     rsp, 20h
0x18000f0d2  mov     rbp, rdx
0x18000f0d5  mov     rax, [rcx]
0x18000f0d8  mov     edx, [rax]
0x18000f0da  mov     [rbp+0E0h], rcx
0x18000f0e1  mov     [rbp+98h], edx
0x18000f0e7  mov     eax, [rbp+98h]
0x18000f0ed  cmp     eax, 0E06D7363h
0x18000f0f2  jnz     short loc_18000F10E
0x18000f0f4  mov     rdx, [rbp+0E0h]
0x18000f0fb  mov     ecx, [rbp+98h]
0x18000f101  call    _XcptFilter_0
0x18000f106  mov     [rbp+0A0h], eax
0x18000f10c  jmp     short loc_18000F118
0x18000f10e  mov     dword ptr [rbp+0A0h], 0
0x18000f118  mov     eax, [rbp+0A0h]
0x18000f11e  add     rsp, 20h
0x18000f122  pop     rbp
0x18000f123  retn
0x18000f125  push    rbp
0x18000f127  sub     rsp, 20h
0x18000f12b  mov     rbp, rdx
0x18000f12e  cmp     dword ptr [rbp+118h], 1
0x18000f135  ja      short loc_18000F141
0x18000f137  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
