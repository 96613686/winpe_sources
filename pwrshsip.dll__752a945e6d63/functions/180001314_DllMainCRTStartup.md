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
- `0x180005530`

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
  if ( (_DWORD)fdwReason || dword_1800090A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090A4 = 1;
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
            if ( dword_1800090A4 )
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
0x180001344  cmp     cs:dword_1800090A0, edx
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
0x180001374  mov     cs:dword_1800090A4, edx
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
0x1800014d3  cmp     cs:dword_1800090A4, 0
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
0x1800055a0  push    rbp
0x1800055a2  sub     rsp, 20h
0x1800055a6  mov     rbp, rdx
0x1800055a9  mov     rax, [rcx]
0x1800055ac  mov     edx, [rax]
0x1800055ae  mov     [rbp+0A8h], rcx
0x1800055b5  mov     [rbp+28h], edx
0x1800055b8  mov     eax, [rbp+28h]
0x1800055bb  cmp     eax, 0E06D7363h
0x1800055c0  jnz     short loc_1800055D6
0x1800055c2  mov     rdx, [rbp+0A8h]
0x1800055c9  mov     ecx, [rbp+28h]
0x1800055cc  call    _XcptFilter_0
0x1800055d1  mov     [rbp+30h], eax
0x1800055d4  jmp     short loc_1800055DD
0x1800055d6  mov     dword ptr [rbp+30h], 0
0x1800055dd  mov     eax, [rbp+30h]
0x1800055e0  add     rsp, 20h
0x1800055e4  pop     rbp
0x1800055e5  retn
0x1800055e7  push    rbp
0x1800055e9  sub     rsp, 20h
0x1800055ed  mov     rbp, rdx
0x1800055f0  mov     rax, [rcx]
0x1800055f3  mov     edx, [rax]
0x1800055f5  mov     [rbp+0B0h], rcx
0x1800055fc  mov     [rbp+38h], edx
0x1800055ff  mov     eax, [rbp+38h]
0x180005602  cmp     eax, 0E06D7363h
0x180005607  jnz     short loc_18000561D
0x180005609  mov     rdx, [rbp+0B0h]
0x180005610  mov     ecx, [rbp+38h]
0x180005613  call    _XcptFilter_0
0x180005618  mov     [rbp+40h], eax
0x18000561b  jmp     short loc_180005624
0x18000561d  mov     dword ptr [rbp+40h], 0
0x180005624  mov     eax, [rbp+40h]
0x180005627  add     rsp, 20h
0x18000562b  pop     rbp
0x18000562c  retn
0x18000562e  push    rbp
0x180005630  sub     rsp, 20h
0x180005634  mov     rbp, rdx
0x180005637  mov     rax, [rcx]
0x18000563a  mov     edx, [rax]
0x18000563c  mov     [rbp+0B8h], rcx
0x180005643  mov     [rbp+48h], edx
0x180005646  mov     eax, [rbp+48h]
0x180005649  cmp     eax, 0E06D7363h
0x18000564e  jnz     short loc_180005664
0x180005650  mov     rdx, [rbp+0B8h]
0x180005657  mov     ecx, [rbp+48h]
0x18000565a  call    _XcptFilter_0
0x18000565f  mov     [rbp+50h], eax
0x180005662  jmp     short loc_18000566B
0x180005664  mov     dword ptr [rbp+50h], 0
0x18000566b  mov     eax, [rbp+50h]
0x18000566e  add     rsp, 20h
0x180005672  pop     rbp
0x180005673  retn
0x180005675  push    rbp
0x180005677  sub     rsp, 20h
0x18000567b  mov     rbp, rdx
0x18000567e  mov     rax, [rcx]
0x180005681  mov     edx, [rax]
0x180005683  mov     [rbp+0C0h], rcx
0x18000568a  mov     [rbp+58h], edx
0x18000568d  mov     eax, [rbp+58h]
0x180005690  cmp     eax, 0E06D7363h
0x180005695  jnz     short loc_1800056AB
0x180005697  mov     rdx, [rbp+0C0h]
0x18000569e  mov     ecx, [rbp+58h]
0x1800056a1  call    _XcptFilter_0
0x1800056a6  mov     [rbp+60h], eax
0x1800056a9  jmp     short loc_1800056B2
0x1800056ab  mov     dword ptr [rbp+60h], 0
0x1800056b2  mov     eax, [rbp+60h]
0x1800056b5  add     rsp, 20h
0x1800056b9  pop     rbp
0x1800056ba  retn
0x1800056bc  push    rbp
0x1800056be  sub     rsp, 20h
0x1800056c2  mov     rbp, rdx
0x1800056c5  mov     rax, [rcx]
0x1800056c8  mov     edx, [rax]
0x1800056ca  mov     [rbp+0C8h], rcx
0x1800056d1  mov     [rbp+68h], edx
0x1800056d4  mov     eax, [rbp+68h]
0x1800056d7  cmp     eax, 0E06D7363h
0x1800056dc  jnz     short loc_1800056F2
0x1800056de  mov     rdx, [rbp+0C8h]
0x1800056e5  mov     ecx, [rbp+68h]
0x1800056e8  call    _XcptFilter_0
0x1800056ed  mov     [rbp+70h], eax
0x1800056f0  jmp     short loc_1800056F9
0x1800056f2  mov     dword ptr [rbp+70h], 0
0x1800056f9  mov     eax, [rbp+70h]
0x1800056fc  add     rsp, 20h
0x180005700  pop     rbp
0x180005701  retn
0x180005703  push    rbp
0x180005705  sub     rsp, 20h
0x180005709  mov     rbp, rdx
0x18000570c  mov     rax, [rcx]
0x18000570f  mov     edx, [rax]
0x180005711  mov     [rbp+0D0h], rcx
0x180005718  mov     [rbp+78h], edx
0x18000571b  mov     eax, [rbp+78h]
0x18000571e  cmp     eax, 0E06D7363h
0x180005723  jnz     short loc_18000573C
0x180005725  mov     rdx, [rbp+0D0h]
0x18000572c  mov     ecx, [rbp+78h]
0x18000572f  call    _XcptFilter_0
0x180005734  mov     [rbp+80h], eax
0x18000573a  jmp     short loc_180005746
0x18000573c  mov     dword ptr [rbp+80h], 0
0x180005746  mov     eax, [rbp+80h]
0x18000574c  add     rsp, 20h
0x180005750  pop     rbp
0x180005751  retn
0x180005753  push    rbp
0x180005755  sub     rsp, 20h
0x180005759  mov     rbp, rdx
0x18000575c  mov     rax, [rcx]
0x18000575f  mov     edx, [rax]
0x180005761  mov     [rbp+0D8h], rcx
0x180005768  mov     [rbp+88h], edx
0x18000576e  mov     eax, [rbp+88h]
0x180005774  cmp     eax, 0E06D7363h
0x180005779  jnz     short loc_180005795
0x18000577b  mov     rdx, [rbp+0D8h]
0x180005782  mov     ecx, [rbp+88h]
0x180005788  call    _XcptFilter_0
0x18000578d  mov     [rbp+90h], eax
0x180005793  jmp     short loc_18000579F
0x180005795  mov     dword ptr [rbp+90h], 0
0x18000579f  mov     eax, [rbp+90h]
0x1800057a5  add     rsp, 20h
0x1800057a9  pop     rbp
0x1800057aa  retn
0x1800057ac  push    rbp
0x1800057ae  sub     rsp, 20h
0x1800057b2  mov     rbp, rdx
0x1800057b5  mov     rax, [rcx]
0x1800057b8  mov     edx, [rax]
0x1800057ba  mov     [rbp+0E0h], rcx
0x1800057c1  mov     [rbp+98h], edx
0x1800057c7  mov     eax, [rbp+98h]
0x1800057cd  cmp     eax, 0E06D7363h
0x1800057d2  jnz     short loc_1800057EE
0x1800057d4  mov     rdx, [rbp+0E0h]
0x1800057db  mov     ecx, [rbp+98h]
0x1800057e1  call    _XcptFilter_0
0x1800057e6  mov     [rbp+0A0h], eax
0x1800057ec  jmp     short loc_1800057F8
0x1800057ee  mov     dword ptr [rbp+0A0h], 0
0x1800057f8  mov     eax, [rbp+0A0h]
0x1800057fe  add     rsp, 20h
0x180005802  pop     rbp
0x180005803  retn
0x180005805  push    rbp
0x180005807  sub     rsp, 20h
0x18000580b  mov     rbp, rdx
0x18000580e  cmp     dword ptr [rbp+118h], 1
0x180005815  ja      short loc_180005821
0x180005817  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
