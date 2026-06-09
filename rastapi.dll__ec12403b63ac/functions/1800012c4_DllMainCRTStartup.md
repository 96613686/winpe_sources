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
- `0x1800014d6`
- `0x18000232c`
- `0x1800292f0`

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
  if ( (_DWORD)fdwReason || dword_18003E4C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003E4C4 = 1;
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
            if ( dword_18003E4C4 )
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
0x1800012f4  cmp     cs:dword_18003E4C0, edx
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
0x180001324  mov     cs:dword_18003E4C4, edx
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
0x180001483  cmp     cs:dword_18003E4C4, 0
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
0x180029360  push    rbp
0x180029362  sub     rsp, 20h
0x180029366  mov     rbp, rdx
0x180029369  mov     rax, [rcx]
0x18002936c  mov     edx, [rax]
0x18002936e  mov     [rbp+0A8h], rcx
0x180029375  mov     [rbp+28h], edx
0x180029378  mov     eax, [rbp+28h]
0x18002937b  cmp     eax, 0E06D7363h
0x180029380  jnz     short loc_180029396
0x180029382  mov     rdx, [rbp+0A8h]
0x180029389  mov     ecx, [rbp+28h]
0x18002938c  call    _XcptFilter_0
0x180029391  mov     [rbp+30h], eax
0x180029394  jmp     short loc_18002939D
0x180029396  mov     dword ptr [rbp+30h], 0
0x18002939d  mov     eax, [rbp+30h]
0x1800293a0  add     rsp, 20h
0x1800293a4  pop     rbp
0x1800293a5  retn
0x1800293a7  push    rbp
0x1800293a9  sub     rsp, 20h
0x1800293ad  mov     rbp, rdx
0x1800293b0  mov     rax, [rcx]
0x1800293b3  mov     edx, [rax]
0x1800293b5  mov     [rbp+0B0h], rcx
0x1800293bc  mov     [rbp+38h], edx
0x1800293bf  mov     eax, [rbp+38h]
0x1800293c2  cmp     eax, 0E06D7363h
0x1800293c7  jnz     short loc_1800293DD
0x1800293c9  mov     rdx, [rbp+0B0h]
0x1800293d0  mov     ecx, [rbp+38h]
0x1800293d3  call    _XcptFilter_0
0x1800293d8  mov     [rbp+40h], eax
0x1800293db  jmp     short loc_1800293E4
0x1800293dd  mov     dword ptr [rbp+40h], 0
0x1800293e4  mov     eax, [rbp+40h]
0x1800293e7  add     rsp, 20h
0x1800293eb  pop     rbp
0x1800293ec  retn
0x1800293ee  push    rbp
0x1800293f0  sub     rsp, 20h
0x1800293f4  mov     rbp, rdx
0x1800293f7  mov     rax, [rcx]
0x1800293fa  mov     edx, [rax]
0x1800293fc  mov     [rbp+0B8h], rcx
0x180029403  mov     [rbp+48h], edx
0x180029406  mov     eax, [rbp+48h]
0x180029409  cmp     eax, 0E06D7363h
0x18002940e  jnz     short loc_180029424
0x180029410  mov     rdx, [rbp+0B8h]
0x180029417  mov     ecx, [rbp+48h]
0x18002941a  call    _XcptFilter_0
0x18002941f  mov     [rbp+50h], eax
0x180029422  jmp     short loc_18002942B
0x180029424  mov     dword ptr [rbp+50h], 0
0x18002942b  mov     eax, [rbp+50h]
0x18002942e  add     rsp, 20h
0x180029432  pop     rbp
0x180029433  retn
0x180029435  push    rbp
0x180029437  sub     rsp, 20h
0x18002943b  mov     rbp, rdx
0x18002943e  mov     rax, [rcx]
0x180029441  mov     edx, [rax]
0x180029443  mov     [rbp+0C0h], rcx
0x18002944a  mov     [rbp+58h], edx
0x18002944d  mov     eax, [rbp+58h]
0x180029450  cmp     eax, 0E06D7363h
0x180029455  jnz     short loc_18002946B
0x180029457  mov     rdx, [rbp+0C0h]
0x18002945e  mov     ecx, [rbp+58h]
0x180029461  call    _XcptFilter_0
0x180029466  mov     [rbp+60h], eax
0x180029469  jmp     short loc_180029472
0x18002946b  mov     dword ptr [rbp+60h], 0
0x180029472  mov     eax, [rbp+60h]
0x180029475  add     rsp, 20h
0x180029479  pop     rbp
0x18002947a  retn
0x18002947c  push    rbp
0x18002947e  sub     rsp, 20h
0x180029482  mov     rbp, rdx
0x180029485  mov     rax, [rcx]
0x180029488  mov     edx, [rax]
0x18002948a  mov     [rbp+0C8h], rcx
0x180029491  mov     [rbp+68h], edx
0x180029494  mov     eax, [rbp+68h]
0x180029497  cmp     eax, 0E06D7363h
0x18002949c  jnz     short loc_1800294B2
0x18002949e  mov     rdx, [rbp+0C8h]
0x1800294a5  mov     ecx, [rbp+68h]
0x1800294a8  call    _XcptFilter_0
0x1800294ad  mov     [rbp+70h], eax
0x1800294b0  jmp     short loc_1800294B9
0x1800294b2  mov     dword ptr [rbp+70h], 0
0x1800294b9  mov     eax, [rbp+70h]
0x1800294bc  add     rsp, 20h
0x1800294c0  pop     rbp
0x1800294c1  retn
0x1800294c3  push    rbp
0x1800294c5  sub     rsp, 20h
0x1800294c9  mov     rbp, rdx
0x1800294cc  mov     rax, [rcx]
0x1800294cf  mov     edx, [rax]
0x1800294d1  mov     [rbp+0D0h], rcx
0x1800294d8  mov     [rbp+78h], edx
0x1800294db  mov     eax, [rbp+78h]
0x1800294de  cmp     eax, 0E06D7363h
0x1800294e3  jnz     short loc_1800294FC
0x1800294e5  mov     rdx, [rbp+0D0h]
0x1800294ec  mov     ecx, [rbp+78h]
0x1800294ef  call    _XcptFilter_0
0x1800294f4  mov     [rbp+80h], eax
0x1800294fa  jmp     short loc_180029506
0x1800294fc  mov     dword ptr [rbp+80h], 0
0x180029506  mov     eax, [rbp+80h]
0x18002950c  add     rsp, 20h
0x180029510  pop     rbp
0x180029511  retn
0x180029513  push    rbp
0x180029515  sub     rsp, 20h
0x180029519  mov     rbp, rdx
0x18002951c  mov     rax, [rcx]
0x18002951f  mov     edx, [rax]
0x180029521  mov     [rbp+0D8h], rcx
0x180029528  mov     [rbp+88h], edx
0x18002952e  mov     eax, [rbp+88h]
0x180029534  cmp     eax, 0E06D7363h
0x180029539  jnz     short loc_180029555
0x18002953b  mov     rdx, [rbp+0D8h]
0x180029542  mov     ecx, [rbp+88h]
0x180029548  call    _XcptFilter_0
0x18002954d  mov     [rbp+90h], eax
0x180029553  jmp     short loc_18002955F
0x180029555  mov     dword ptr [rbp+90h], 0
0x18002955f  mov     eax, [rbp+90h]
0x180029565  add     rsp, 20h
0x180029569  pop     rbp
0x18002956a  retn
0x18002956c  push    rbp
0x18002956e  sub     rsp, 20h
0x180029572  mov     rbp, rdx
0x180029575  mov     rax, [rcx]
0x180029578  mov     edx, [rax]
0x18002957a  mov     [rbp+0E0h], rcx
0x180029581  mov     [rbp+98h], edx
0x180029587  mov     eax, [rbp+98h]
0x18002958d  cmp     eax, 0E06D7363h
0x180029592  jnz     short loc_1800295AE
0x180029594  mov     rdx, [rbp+0E0h]
0x18002959b  mov     ecx, [rbp+98h]
0x1800295a1  call    _XcptFilter_0
0x1800295a6  mov     [rbp+0A0h], eax
0x1800295ac  jmp     short loc_1800295B8
0x1800295ae  mov     dword ptr [rbp+0A0h], 0
0x1800295b8  mov     eax, [rbp+0A0h]
0x1800295be  add     rsp, 20h
0x1800295c2  pop     rbp
0x1800295c3  retn
0x1800295c5  push    rbp
0x1800295c7  sub     rsp, 20h
0x1800295cb  mov     rbp, rdx
0x1800295ce  cmp     dword ptr [rbp+118h], 1
0x1800295d5  ja      short loc_1800295E1
0x1800295d7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
