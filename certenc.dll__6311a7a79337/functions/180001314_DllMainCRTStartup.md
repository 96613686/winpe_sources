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
- `0x180001752`
- `0x180007970`
- `0x1800085c0`

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
  if ( (_DWORD)fdwReason || dword_18000F320 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F324 = 1;
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
            if ( dword_18000F324 )
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
0x180001344  cmp     cs:dword_18000F320, edx
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
0x180001374  mov     cs:dword_18000F324, edx
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
0x1800014d3  cmp     cs:dword_18000F324, 0
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
0x180008630  push    rbp
0x180008632  sub     rsp, 20h
0x180008636  mov     rbp, rdx
0x180008639  mov     rax, [rcx]
0x18000863c  mov     edx, [rax]
0x18000863e  mov     [rbp+0A8h], rcx
0x180008645  mov     [rbp+28h], edx
0x180008648  mov     eax, [rbp+28h]
0x18000864b  cmp     eax, 0E06D7363h
0x180008650  jnz     short loc_180008666
0x180008652  mov     rdx, [rbp+0A8h]
0x180008659  mov     ecx, [rbp+28h]
0x18000865c  call    _XcptFilter_0
0x180008661  mov     [rbp+30h], eax
0x180008664  jmp     short loc_18000866D
0x180008666  mov     dword ptr [rbp+30h], 0
0x18000866d  mov     eax, [rbp+30h]
0x180008670  add     rsp, 20h
0x180008674  pop     rbp
0x180008675  retn
0x180008677  push    rbp
0x180008679  sub     rsp, 20h
0x18000867d  mov     rbp, rdx
0x180008680  mov     rax, [rcx]
0x180008683  mov     edx, [rax]
0x180008685  mov     [rbp+0B0h], rcx
0x18000868c  mov     [rbp+38h], edx
0x18000868f  mov     eax, [rbp+38h]
0x180008692  cmp     eax, 0E06D7363h
0x180008697  jnz     short loc_1800086AD
0x180008699  mov     rdx, [rbp+0B0h]
0x1800086a0  mov     ecx, [rbp+38h]
0x1800086a3  call    _XcptFilter_0
0x1800086a8  mov     [rbp+40h], eax
0x1800086ab  jmp     short loc_1800086B4
0x1800086ad  mov     dword ptr [rbp+40h], 0
0x1800086b4  mov     eax, [rbp+40h]
0x1800086b7  add     rsp, 20h
0x1800086bb  pop     rbp
0x1800086bc  retn
0x1800086be  push    rbp
0x1800086c0  sub     rsp, 20h
0x1800086c4  mov     rbp, rdx
0x1800086c7  mov     rax, [rcx]
0x1800086ca  mov     edx, [rax]
0x1800086cc  mov     [rbp+0B8h], rcx
0x1800086d3  mov     [rbp+48h], edx
0x1800086d6  mov     eax, [rbp+48h]
0x1800086d9  cmp     eax, 0E06D7363h
0x1800086de  jnz     short loc_1800086F4
0x1800086e0  mov     rdx, [rbp+0B8h]
0x1800086e7  mov     ecx, [rbp+48h]
0x1800086ea  call    _XcptFilter_0
0x1800086ef  mov     [rbp+50h], eax
0x1800086f2  jmp     short loc_1800086FB
0x1800086f4  mov     dword ptr [rbp+50h], 0
0x1800086fb  mov     eax, [rbp+50h]
0x1800086fe  add     rsp, 20h
0x180008702  pop     rbp
0x180008703  retn
0x180008705  push    rbp
0x180008707  sub     rsp, 20h
0x18000870b  mov     rbp, rdx
0x18000870e  mov     rax, [rcx]
0x180008711  mov     edx, [rax]
0x180008713  mov     [rbp+0C0h], rcx
0x18000871a  mov     [rbp+58h], edx
0x18000871d  mov     eax, [rbp+58h]
0x180008720  cmp     eax, 0E06D7363h
0x180008725  jnz     short loc_18000873B
0x180008727  mov     rdx, [rbp+0C0h]
0x18000872e  mov     ecx, [rbp+58h]
0x180008731  call    _XcptFilter_0
0x180008736  mov     [rbp+60h], eax
0x180008739  jmp     short loc_180008742
0x18000873b  mov     dword ptr [rbp+60h], 0
0x180008742  mov     eax, [rbp+60h]
0x180008745  add     rsp, 20h
0x180008749  pop     rbp
0x18000874a  retn
0x18000874c  push    rbp
0x18000874e  sub     rsp, 20h
0x180008752  mov     rbp, rdx
0x180008755  mov     rax, [rcx]
0x180008758  mov     edx, [rax]
0x18000875a  mov     [rbp+0C8h], rcx
0x180008761  mov     [rbp+68h], edx
0x180008764  mov     eax, [rbp+68h]
0x180008767  cmp     eax, 0E06D7363h
0x18000876c  jnz     short loc_180008782
0x18000876e  mov     rdx, [rbp+0C8h]
0x180008775  mov     ecx, [rbp+68h]
0x180008778  call    _XcptFilter_0
0x18000877d  mov     [rbp+70h], eax
0x180008780  jmp     short loc_180008789
0x180008782  mov     dword ptr [rbp+70h], 0
0x180008789  mov     eax, [rbp+70h]
0x18000878c  add     rsp, 20h
0x180008790  pop     rbp
0x180008791  retn
0x180008793  push    rbp
0x180008795  sub     rsp, 20h
0x180008799  mov     rbp, rdx
0x18000879c  mov     rax, [rcx]
0x18000879f  mov     edx, [rax]
0x1800087a1  mov     [rbp+0D0h], rcx
0x1800087a8  mov     [rbp+78h], edx
0x1800087ab  mov     eax, [rbp+78h]
0x1800087ae  cmp     eax, 0E06D7363h
0x1800087b3  jnz     short loc_1800087CC
0x1800087b5  mov     rdx, [rbp+0D0h]
0x1800087bc  mov     ecx, [rbp+78h]
0x1800087bf  call    _XcptFilter_0
0x1800087c4  mov     [rbp+80h], eax
0x1800087ca  jmp     short loc_1800087D6
0x1800087cc  mov     dword ptr [rbp+80h], 0
0x1800087d6  mov     eax, [rbp+80h]
0x1800087dc  add     rsp, 20h
0x1800087e0  pop     rbp
0x1800087e1  retn
0x1800087e3  push    rbp
0x1800087e5  sub     rsp, 20h
0x1800087e9  mov     rbp, rdx
0x1800087ec  mov     rax, [rcx]
0x1800087ef  mov     edx, [rax]
0x1800087f1  mov     [rbp+0D8h], rcx
0x1800087f8  mov     [rbp+88h], edx
0x1800087fe  mov     eax, [rbp+88h]
0x180008804  cmp     eax, 0E06D7363h
0x180008809  jnz     short loc_180008825
0x18000880b  mov     rdx, [rbp+0D8h]
0x180008812  mov     ecx, [rbp+88h]
0x180008818  call    _XcptFilter_0
0x18000881d  mov     [rbp+90h], eax
0x180008823  jmp     short loc_18000882F
0x180008825  mov     dword ptr [rbp+90h], 0
0x18000882f  mov     eax, [rbp+90h]
0x180008835  add     rsp, 20h
0x180008839  pop     rbp
0x18000883a  retn
0x18000883c  push    rbp
0x18000883e  sub     rsp, 20h
0x180008842  mov     rbp, rdx
0x180008845  mov     rax, [rcx]
0x180008848  mov     edx, [rax]
0x18000884a  mov     [rbp+0E0h], rcx
0x180008851  mov     [rbp+98h], edx
0x180008857  mov     eax, [rbp+98h]
0x18000885d  cmp     eax, 0E06D7363h
0x180008862  jnz     short loc_18000887E
0x180008864  mov     rdx, [rbp+0E0h]
0x18000886b  mov     ecx, [rbp+98h]
0x180008871  call    _XcptFilter_0
0x180008876  mov     [rbp+0A0h], eax
0x18000887c  jmp     short loc_180008888
0x18000887e  mov     dword ptr [rbp+0A0h], 0
0x180008888  mov     eax, [rbp+0A0h]
0x18000888e  add     rsp, 20h
0x180008892  pop     rbp
0x180008893  retn
0x180008895  push    rbp
0x180008897  sub     rsp, 20h
0x18000889b  mov     rbp, rdx
0x18000889e  cmp     dword ptr [rbp+118h], 1
0x1800088a5  ja      short loc_1800088B1
0x1800088a7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
