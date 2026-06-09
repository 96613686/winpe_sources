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
- `0x1800034c8`
- `0x18000a1e0`

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
  if ( (_DWORD)fdwReason || dword_180011140 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180011144 = 1;
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
            if ( dword_180011144 )
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
0x180001344  cmp     cs:dword_180011140, edx
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
0x180001374  mov     cs:dword_180011144, edx
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
0x1800014d3  cmp     cs:dword_180011144, 0
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
0x18000a2b0  push    rbp
0x18000a2b2  sub     rsp, 20h
0x18000a2b6  mov     rbp, rdx
0x18000a2b9  mov     rax, [rcx]
0x18000a2bc  mov     edx, [rax]
0x18000a2be  mov     [rbp+0A8h], rcx
0x18000a2c5  mov     [rbp+28h], edx
0x18000a2c8  mov     eax, [rbp+28h]
0x18000a2cb  cmp     eax, 0E06D7363h
0x18000a2d0  jnz     short loc_18000A2E6
0x18000a2d2  mov     rdx, [rbp+0A8h]
0x18000a2d9  mov     ecx, [rbp+28h]
0x18000a2dc  call    _XcptFilter_0
0x18000a2e1  mov     [rbp+30h], eax
0x18000a2e4  jmp     short loc_18000A2ED
0x18000a2e6  mov     dword ptr [rbp+30h], 0
0x18000a2ed  mov     eax, [rbp+30h]
0x18000a2f0  add     rsp, 20h
0x18000a2f4  pop     rbp
0x18000a2f5  retn
0x18000a2f7  push    rbp
0x18000a2f9  sub     rsp, 20h
0x18000a2fd  mov     rbp, rdx
0x18000a300  mov     rax, [rcx]
0x18000a303  mov     edx, [rax]
0x18000a305  mov     [rbp+0B0h], rcx
0x18000a30c  mov     [rbp+38h], edx
0x18000a30f  mov     eax, [rbp+38h]
0x18000a312  cmp     eax, 0E06D7363h
0x18000a317  jnz     short loc_18000A32D
0x18000a319  mov     rdx, [rbp+0B0h]
0x18000a320  mov     ecx, [rbp+38h]
0x18000a323  call    _XcptFilter_0
0x18000a328  mov     [rbp+40h], eax
0x18000a32b  jmp     short loc_18000A334
0x18000a32d  mov     dword ptr [rbp+40h], 0
0x18000a334  mov     eax, [rbp+40h]
0x18000a337  add     rsp, 20h
0x18000a33b  pop     rbp
0x18000a33c  retn
0x18000a33e  push    rbp
0x18000a340  sub     rsp, 20h
0x18000a344  mov     rbp, rdx
0x18000a347  mov     rax, [rcx]
0x18000a34a  mov     edx, [rax]
0x18000a34c  mov     [rbp+0B8h], rcx
0x18000a353  mov     [rbp+48h], edx
0x18000a356  mov     eax, [rbp+48h]
0x18000a359  cmp     eax, 0E06D7363h
0x18000a35e  jnz     short loc_18000A374
0x18000a360  mov     rdx, [rbp+0B8h]
0x18000a367  mov     ecx, [rbp+48h]
0x18000a36a  call    _XcptFilter_0
0x18000a36f  mov     [rbp+50h], eax
0x18000a372  jmp     short loc_18000A37B
0x18000a374  mov     dword ptr [rbp+50h], 0
0x18000a37b  mov     eax, [rbp+50h]
0x18000a37e  add     rsp, 20h
0x18000a382  pop     rbp
0x18000a383  retn
0x18000a385  push    rbp
0x18000a387  sub     rsp, 20h
0x18000a38b  mov     rbp, rdx
0x18000a38e  mov     rax, [rcx]
0x18000a391  mov     edx, [rax]
0x18000a393  mov     [rbp+0C0h], rcx
0x18000a39a  mov     [rbp+58h], edx
0x18000a39d  mov     eax, [rbp+58h]
0x18000a3a0  cmp     eax, 0E06D7363h
0x18000a3a5  jnz     short loc_18000A3BB
0x18000a3a7  mov     rdx, [rbp+0C0h]
0x18000a3ae  mov     ecx, [rbp+58h]
0x18000a3b1  call    _XcptFilter_0
0x18000a3b6  mov     [rbp+60h], eax
0x18000a3b9  jmp     short loc_18000A3C2
0x18000a3bb  mov     dword ptr [rbp+60h], 0
0x18000a3c2  mov     eax, [rbp+60h]
0x18000a3c5  add     rsp, 20h
0x18000a3c9  pop     rbp
0x18000a3ca  retn
0x18000a3cc  push    rbp
0x18000a3ce  sub     rsp, 20h
0x18000a3d2  mov     rbp, rdx
0x18000a3d5  mov     rax, [rcx]
0x18000a3d8  mov     edx, [rax]
0x18000a3da  mov     [rbp+0C8h], rcx
0x18000a3e1  mov     [rbp+68h], edx
0x18000a3e4  mov     eax, [rbp+68h]
0x18000a3e7  cmp     eax, 0E06D7363h
0x18000a3ec  jnz     short loc_18000A402
0x18000a3ee  mov     rdx, [rbp+0C8h]
0x18000a3f5  mov     ecx, [rbp+68h]
0x18000a3f8  call    _XcptFilter_0
0x18000a3fd  mov     [rbp+70h], eax
0x18000a400  jmp     short loc_18000A409
0x18000a402  mov     dword ptr [rbp+70h], 0
0x18000a409  mov     eax, [rbp+70h]
0x18000a40c  add     rsp, 20h
0x18000a410  pop     rbp
0x18000a411  retn
0x18000a413  push    rbp
0x18000a415  sub     rsp, 20h
0x18000a419  mov     rbp, rdx
0x18000a41c  mov     rax, [rcx]
0x18000a41f  mov     edx, [rax]
0x18000a421  mov     [rbp+0D0h], rcx
0x18000a428  mov     [rbp+78h], edx
0x18000a42b  mov     eax, [rbp+78h]
0x18000a42e  cmp     eax, 0E06D7363h
0x18000a433  jnz     short loc_18000A44C
0x18000a435  mov     rdx, [rbp+0D0h]
0x18000a43c  mov     ecx, [rbp+78h]
0x18000a43f  call    _XcptFilter_0
0x18000a444  mov     [rbp+80h], eax
0x18000a44a  jmp     short loc_18000A456
0x18000a44c  mov     dword ptr [rbp+80h], 0
0x18000a456  mov     eax, [rbp+80h]
0x18000a45c  add     rsp, 20h
0x18000a460  pop     rbp
0x18000a461  retn
0x18000a463  push    rbp
0x18000a465  sub     rsp, 20h
0x18000a469  mov     rbp, rdx
0x18000a46c  mov     rax, [rcx]
0x18000a46f  mov     edx, [rax]
0x18000a471  mov     [rbp+0D8h], rcx
0x18000a478  mov     [rbp+88h], edx
0x18000a47e  mov     eax, [rbp+88h]
0x18000a484  cmp     eax, 0E06D7363h
0x18000a489  jnz     short loc_18000A4A5
0x18000a48b  mov     rdx, [rbp+0D8h]
0x18000a492  mov     ecx, [rbp+88h]
0x18000a498  call    _XcptFilter_0
0x18000a49d  mov     [rbp+90h], eax
0x18000a4a3  jmp     short loc_18000A4AF
0x18000a4a5  mov     dword ptr [rbp+90h], 0
0x18000a4af  mov     eax, [rbp+90h]
0x18000a4b5  add     rsp, 20h
0x18000a4b9  pop     rbp
0x18000a4ba  retn
0x18000a4bc  push    rbp
0x18000a4be  sub     rsp, 20h
0x18000a4c2  mov     rbp, rdx
0x18000a4c5  mov     rax, [rcx]
0x18000a4c8  mov     edx, [rax]
0x18000a4ca  mov     [rbp+0E0h], rcx
0x18000a4d1  mov     [rbp+98h], edx
0x18000a4d7  mov     eax, [rbp+98h]
0x18000a4dd  cmp     eax, 0E06D7363h
0x18000a4e2  jnz     short loc_18000A4FE
0x18000a4e4  mov     rdx, [rbp+0E0h]
0x18000a4eb  mov     ecx, [rbp+98h]
0x18000a4f1  call    _XcptFilter_0
0x18000a4f6  mov     [rbp+0A0h], eax
0x18000a4fc  jmp     short loc_18000A508
0x18000a4fe  mov     dword ptr [rbp+0A0h], 0
0x18000a508  mov     eax, [rbp+0A0h]
0x18000a50e  add     rsp, 20h
0x18000a512  pop     rbp
0x18000a513  retn
0x18000a515  push    rbp
0x18000a517  sub     rsp, 20h
0x18000a51b  mov     rbp, rdx
0x18000a51e  cmp     dword ptr [rbp+118h], 1
0x18000a525  ja      short loc_18000A531
0x18000a527  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
