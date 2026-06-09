# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x180001815`
- `0x180001b60`
- `0x1800054f0`

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
  if ( (_DWORD)fdwReason || dword_18000C120 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C124 = 1;
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
            if ( dword_18000C124 )
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
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_18000C120, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_18000C124, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_18000C124, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180005560  push    rbp
0x180005562  sub     rsp, 20h
0x180005566  mov     rbp, rdx
0x180005569  mov     rax, [rcx]
0x18000556c  mov     edx, [rax]
0x18000556e  mov     [rbp+0A8h], rcx
0x180005575  mov     [rbp+28h], edx
0x180005578  mov     eax, [rbp+28h]
0x18000557b  cmp     eax, 0E06D7363h
0x180005580  jnz     short loc_180005596
0x180005582  mov     rdx, [rbp+0A8h]
0x180005589  mov     ecx, [rbp+28h]
0x18000558c  call    _XcptFilter_0
0x180005591  mov     [rbp+30h], eax
0x180005594  jmp     short loc_18000559D
0x180005596  mov     dword ptr [rbp+30h], 0
0x18000559d  mov     eax, [rbp+30h]
0x1800055a0  add     rsp, 20h
0x1800055a4  pop     rbp
0x1800055a5  retn
0x1800055a7  push    rbp
0x1800055a9  sub     rsp, 20h
0x1800055ad  mov     rbp, rdx
0x1800055b0  mov     rax, [rcx]
0x1800055b3  mov     edx, [rax]
0x1800055b5  mov     [rbp+0B0h], rcx
0x1800055bc  mov     [rbp+38h], edx
0x1800055bf  mov     eax, [rbp+38h]
0x1800055c2  cmp     eax, 0E06D7363h
0x1800055c7  jnz     short loc_1800055DD
0x1800055c9  mov     rdx, [rbp+0B0h]
0x1800055d0  mov     ecx, [rbp+38h]
0x1800055d3  call    _XcptFilter_0
0x1800055d8  mov     [rbp+40h], eax
0x1800055db  jmp     short loc_1800055E4
0x1800055dd  mov     dword ptr [rbp+40h], 0
0x1800055e4  mov     eax, [rbp+40h]
0x1800055e7  add     rsp, 20h
0x1800055eb  pop     rbp
0x1800055ec  retn
0x1800055ee  push    rbp
0x1800055f0  sub     rsp, 20h
0x1800055f4  mov     rbp, rdx
0x1800055f7  mov     rax, [rcx]
0x1800055fa  mov     edx, [rax]
0x1800055fc  mov     [rbp+0B8h], rcx
0x180005603  mov     [rbp+48h], edx
0x180005606  mov     eax, [rbp+48h]
0x180005609  cmp     eax, 0E06D7363h
0x18000560e  jnz     short loc_180005624
0x180005610  mov     rdx, [rbp+0B8h]
0x180005617  mov     ecx, [rbp+48h]
0x18000561a  call    _XcptFilter_0
0x18000561f  mov     [rbp+50h], eax
0x180005622  jmp     short loc_18000562B
0x180005624  mov     dword ptr [rbp+50h], 0
0x18000562b  mov     eax, [rbp+50h]
0x18000562e  add     rsp, 20h
0x180005632  pop     rbp
0x180005633  retn
0x180005635  push    rbp
0x180005637  sub     rsp, 20h
0x18000563b  mov     rbp, rdx
0x18000563e  mov     rax, [rcx]
0x180005641  mov     edx, [rax]
0x180005643  mov     [rbp+0C0h], rcx
0x18000564a  mov     [rbp+58h], edx
0x18000564d  mov     eax, [rbp+58h]
0x180005650  cmp     eax, 0E06D7363h
0x180005655  jnz     short loc_18000566B
0x180005657  mov     rdx, [rbp+0C0h]
0x18000565e  mov     ecx, [rbp+58h]
0x180005661  call    _XcptFilter_0
0x180005666  mov     [rbp+60h], eax
0x180005669  jmp     short loc_180005672
0x18000566b  mov     dword ptr [rbp+60h], 0
0x180005672  mov     eax, [rbp+60h]
0x180005675  add     rsp, 20h
0x180005679  pop     rbp
0x18000567a  retn
0x18000567c  push    rbp
0x18000567e  sub     rsp, 20h
0x180005682  mov     rbp, rdx
0x180005685  mov     rax, [rcx]
0x180005688  mov     edx, [rax]
0x18000568a  mov     [rbp+0C8h], rcx
0x180005691  mov     [rbp+68h], edx
0x180005694  mov     eax, [rbp+68h]
0x180005697  cmp     eax, 0E06D7363h
0x18000569c  jnz     short loc_1800056B2
0x18000569e  mov     rdx, [rbp+0C8h]
0x1800056a5  mov     ecx, [rbp+68h]
0x1800056a8  call    _XcptFilter_0
0x1800056ad  mov     [rbp+70h], eax
0x1800056b0  jmp     short loc_1800056B9
0x1800056b2  mov     dword ptr [rbp+70h], 0
0x1800056b9  mov     eax, [rbp+70h]
0x1800056bc  add     rsp, 20h
0x1800056c0  pop     rbp
0x1800056c1  retn
0x1800056c3  push    rbp
0x1800056c5  sub     rsp, 20h
0x1800056c9  mov     rbp, rdx
0x1800056cc  mov     rax, [rcx]
0x1800056cf  mov     edx, [rax]
0x1800056d1  mov     [rbp+0D0h], rcx
0x1800056d8  mov     [rbp+78h], edx
0x1800056db  mov     eax, [rbp+78h]
0x1800056de  cmp     eax, 0E06D7363h
0x1800056e3  jnz     short loc_1800056FC
0x1800056e5  mov     rdx, [rbp+0D0h]
0x1800056ec  mov     ecx, [rbp+78h]
0x1800056ef  call    _XcptFilter_0
0x1800056f4  mov     [rbp+80h], eax
0x1800056fa  jmp     short loc_180005706
0x1800056fc  mov     dword ptr [rbp+80h], 0
0x180005706  mov     eax, [rbp+80h]
0x18000570c  add     rsp, 20h
0x180005710  pop     rbp
0x180005711  retn
0x180005713  push    rbp
0x180005715  sub     rsp, 20h
0x180005719  mov     rbp, rdx
0x18000571c  mov     rax, [rcx]
0x18000571f  mov     edx, [rax]
0x180005721  mov     [rbp+0D8h], rcx
0x180005728  mov     [rbp+88h], edx
0x18000572e  mov     eax, [rbp+88h]
0x180005734  cmp     eax, 0E06D7363h
0x180005739  jnz     short loc_180005755
0x18000573b  mov     rdx, [rbp+0D8h]
0x180005742  mov     ecx, [rbp+88h]
0x180005748  call    _XcptFilter_0
0x18000574d  mov     [rbp+90h], eax
0x180005753  jmp     short loc_18000575F
0x180005755  mov     dword ptr [rbp+90h], 0
0x18000575f  mov     eax, [rbp+90h]
0x180005765  add     rsp, 20h
0x180005769  pop     rbp
0x18000576a  retn
0x18000576c  push    rbp
0x18000576e  sub     rsp, 20h
0x180005772  mov     rbp, rdx
0x180005775  mov     rax, [rcx]
0x180005778  mov     edx, [rax]
0x18000577a  mov     [rbp+0E0h], rcx
0x180005781  mov     [rbp+98h], edx
0x180005787  mov     eax, [rbp+98h]
0x18000578d  cmp     eax, 0E06D7363h
0x180005792  jnz     short loc_1800057AE
0x180005794  mov     rdx, [rbp+0E0h]
0x18000579b  mov     ecx, [rbp+98h]
0x1800057a1  call    _XcptFilter_0
0x1800057a6  mov     [rbp+0A0h], eax
0x1800057ac  jmp     short loc_1800057B8
0x1800057ae  mov     dword ptr [rbp+0A0h], 0
0x1800057b8  mov     eax, [rbp+0A0h]
0x1800057be  add     rsp, 20h
0x1800057c2  pop     rbp
0x1800057c3  retn
0x1800057c5  push    rbp
0x1800057c7  sub     rsp, 20h
0x1800057cb  mov     rbp, rdx
0x1800057ce  cmp     dword ptr [rbp+118h], 1
0x1800057d5  ja      short loc_1800057E1
0x1800057d7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
