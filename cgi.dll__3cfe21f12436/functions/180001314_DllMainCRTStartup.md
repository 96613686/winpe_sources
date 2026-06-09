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
- `0x180006ed0`

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
  if ( (_DWORD)fdwReason || dword_18000D0C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000D0C4 = 1;
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
            if ( dword_18000D0C4 )
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
0x180001344  cmp     cs:dword_18000D0C0, edx
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
0x180001374  mov     cs:dword_18000D0C4, edx
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
0x1800014d3  cmp     cs:dword_18000D0C4, 0
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
0x180006fa0  push    rbp
0x180006fa2  sub     rsp, 20h
0x180006fa6  mov     rbp, rdx
0x180006fa9  mov     rax, [rcx]
0x180006fac  mov     edx, [rax]
0x180006fae  mov     [rbp+0A8h], rcx
0x180006fb5  mov     [rbp+28h], edx
0x180006fb8  mov     eax, [rbp+28h]
0x180006fbb  cmp     eax, 0E06D7363h
0x180006fc0  jnz     short loc_180006FD6
0x180006fc2  mov     rdx, [rbp+0A8h]
0x180006fc9  mov     ecx, [rbp+28h]
0x180006fcc  call    _XcptFilter_0
0x180006fd1  mov     [rbp+30h], eax
0x180006fd4  jmp     short loc_180006FDD
0x180006fd6  mov     dword ptr [rbp+30h], 0
0x180006fdd  mov     eax, [rbp+30h]
0x180006fe0  add     rsp, 20h
0x180006fe4  pop     rbp
0x180006fe5  retn
0x180006fe7  push    rbp
0x180006fe9  sub     rsp, 20h
0x180006fed  mov     rbp, rdx
0x180006ff0  mov     rax, [rcx]
0x180006ff3  mov     edx, [rax]
0x180006ff5  mov     [rbp+0B0h], rcx
0x180006ffc  mov     [rbp+38h], edx
0x180006fff  mov     eax, [rbp+38h]
0x180007002  cmp     eax, 0E06D7363h
0x180007007  jnz     short loc_18000701D
0x180007009  mov     rdx, [rbp+0B0h]
0x180007010  mov     ecx, [rbp+38h]
0x180007013  call    _XcptFilter_0
0x180007018  mov     [rbp+40h], eax
0x18000701b  jmp     short loc_180007024
0x18000701d  mov     dword ptr [rbp+40h], 0
0x180007024  mov     eax, [rbp+40h]
0x180007027  add     rsp, 20h
0x18000702b  pop     rbp
0x18000702c  retn
0x18000702e  push    rbp
0x180007030  sub     rsp, 20h
0x180007034  mov     rbp, rdx
0x180007037  mov     rax, [rcx]
0x18000703a  mov     edx, [rax]
0x18000703c  mov     [rbp+0B8h], rcx
0x180007043  mov     [rbp+48h], edx
0x180007046  mov     eax, [rbp+48h]
0x180007049  cmp     eax, 0E06D7363h
0x18000704e  jnz     short loc_180007064
0x180007050  mov     rdx, [rbp+0B8h]
0x180007057  mov     ecx, [rbp+48h]
0x18000705a  call    _XcptFilter_0
0x18000705f  mov     [rbp+50h], eax
0x180007062  jmp     short loc_18000706B
0x180007064  mov     dword ptr [rbp+50h], 0
0x18000706b  mov     eax, [rbp+50h]
0x18000706e  add     rsp, 20h
0x180007072  pop     rbp
0x180007073  retn
0x180007075  push    rbp
0x180007077  sub     rsp, 20h
0x18000707b  mov     rbp, rdx
0x18000707e  mov     rax, [rcx]
0x180007081  mov     edx, [rax]
0x180007083  mov     [rbp+0C0h], rcx
0x18000708a  mov     [rbp+58h], edx
0x18000708d  mov     eax, [rbp+58h]
0x180007090  cmp     eax, 0E06D7363h
0x180007095  jnz     short loc_1800070AB
0x180007097  mov     rdx, [rbp+0C0h]
0x18000709e  mov     ecx, [rbp+58h]
0x1800070a1  call    _XcptFilter_0
0x1800070a6  mov     [rbp+60h], eax
0x1800070a9  jmp     short loc_1800070B2
0x1800070ab  mov     dword ptr [rbp+60h], 0
0x1800070b2  mov     eax, [rbp+60h]
0x1800070b5  add     rsp, 20h
0x1800070b9  pop     rbp
0x1800070ba  retn
0x1800070bc  push    rbp
0x1800070be  sub     rsp, 20h
0x1800070c2  mov     rbp, rdx
0x1800070c5  mov     rax, [rcx]
0x1800070c8  mov     edx, [rax]
0x1800070ca  mov     [rbp+0C8h], rcx
0x1800070d1  mov     [rbp+68h], edx
0x1800070d4  mov     eax, [rbp+68h]
0x1800070d7  cmp     eax, 0E06D7363h
0x1800070dc  jnz     short loc_1800070F2
0x1800070de  mov     rdx, [rbp+0C8h]
0x1800070e5  mov     ecx, [rbp+68h]
0x1800070e8  call    _XcptFilter_0
0x1800070ed  mov     [rbp+70h], eax
0x1800070f0  jmp     short loc_1800070F9
0x1800070f2  mov     dword ptr [rbp+70h], 0
0x1800070f9  mov     eax, [rbp+70h]
0x1800070fc  add     rsp, 20h
0x180007100  pop     rbp
0x180007101  retn
0x180007103  push    rbp
0x180007105  sub     rsp, 20h
0x180007109  mov     rbp, rdx
0x18000710c  mov     rax, [rcx]
0x18000710f  mov     edx, [rax]
0x180007111  mov     [rbp+0D0h], rcx
0x180007118  mov     [rbp+78h], edx
0x18000711b  mov     eax, [rbp+78h]
0x18000711e  cmp     eax, 0E06D7363h
0x180007123  jnz     short loc_18000713C
0x180007125  mov     rdx, [rbp+0D0h]
0x18000712c  mov     ecx, [rbp+78h]
0x18000712f  call    _XcptFilter_0
0x180007134  mov     [rbp+80h], eax
0x18000713a  jmp     short loc_180007146
0x18000713c  mov     dword ptr [rbp+80h], 0
0x180007146  mov     eax, [rbp+80h]
0x18000714c  add     rsp, 20h
0x180007150  pop     rbp
0x180007151  retn
0x180007153  push    rbp
0x180007155  sub     rsp, 20h
0x180007159  mov     rbp, rdx
0x18000715c  mov     rax, [rcx]
0x18000715f  mov     edx, [rax]
0x180007161  mov     [rbp+0D8h], rcx
0x180007168  mov     [rbp+88h], edx
0x18000716e  mov     eax, [rbp+88h]
0x180007174  cmp     eax, 0E06D7363h
0x180007179  jnz     short loc_180007195
0x18000717b  mov     rdx, [rbp+0D8h]
0x180007182  mov     ecx, [rbp+88h]
0x180007188  call    _XcptFilter_0
0x18000718d  mov     [rbp+90h], eax
0x180007193  jmp     short loc_18000719F
0x180007195  mov     dword ptr [rbp+90h], 0
0x18000719f  mov     eax, [rbp+90h]
0x1800071a5  add     rsp, 20h
0x1800071a9  pop     rbp
0x1800071aa  retn
0x1800071ac  push    rbp
0x1800071ae  sub     rsp, 20h
0x1800071b2  mov     rbp, rdx
0x1800071b5  mov     rax, [rcx]
0x1800071b8  mov     edx, [rax]
0x1800071ba  mov     [rbp+0E0h], rcx
0x1800071c1  mov     [rbp+98h], edx
0x1800071c7  mov     eax, [rbp+98h]
0x1800071cd  cmp     eax, 0E06D7363h
0x1800071d2  jnz     short loc_1800071EE
0x1800071d4  mov     rdx, [rbp+0E0h]
0x1800071db  mov     ecx, [rbp+98h]
0x1800071e1  call    _XcptFilter_0
0x1800071e6  mov     [rbp+0A0h], eax
0x1800071ec  jmp     short loc_1800071F8
0x1800071ee  mov     dword ptr [rbp+0A0h], 0
0x1800071f8  mov     eax, [rbp+0A0h]
0x1800071fe  add     rsp, 20h
0x180007202  pop     rbp
0x180007203  retn
0x180007205  push    rbp
0x180007207  sub     rsp, 20h
0x18000720b  mov     rbp, rdx
0x18000720e  cmp     dword ptr [rbp+118h], 1
0x180007215  ja      short loc_180007221
0x180007217  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
