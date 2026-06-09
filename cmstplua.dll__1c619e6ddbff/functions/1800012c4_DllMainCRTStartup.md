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
- `0x1800014f5`
- `0x180001a30`
- `0x180002720`

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
0x1800012f4  cmp     cs:dword_1800060A0, edx
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
0x180001324  mov     cs:dword_1800060A4, edx
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
0x180001483  cmp     cs:dword_1800060A4, 0
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
0x180002790  push    rbp
0x180002792  sub     rsp, 20h
0x180002796  mov     rbp, rdx
0x180002799  mov     rax, [rcx]
0x18000279c  mov     edx, [rax]
0x18000279e  mov     [rbp+0A8h], rcx
0x1800027a5  mov     [rbp+28h], edx
0x1800027a8  mov     eax, [rbp+28h]
0x1800027ab  cmp     eax, 0E06D7363h
0x1800027b0  jnz     short loc_1800027C6
0x1800027b2  mov     rdx, [rbp+0A8h]
0x1800027b9  mov     ecx, [rbp+28h]
0x1800027bc  call    _XcptFilter_0
0x1800027c1  mov     [rbp+30h], eax
0x1800027c4  jmp     short loc_1800027CD
0x1800027c6  mov     dword ptr [rbp+30h], 0
0x1800027cd  mov     eax, [rbp+30h]
0x1800027d0  add     rsp, 20h
0x1800027d4  pop     rbp
0x1800027d5  retn
0x1800027d7  push    rbp
0x1800027d9  sub     rsp, 20h
0x1800027dd  mov     rbp, rdx
0x1800027e0  mov     rax, [rcx]
0x1800027e3  mov     edx, [rax]
0x1800027e5  mov     [rbp+0B0h], rcx
0x1800027ec  mov     [rbp+38h], edx
0x1800027ef  mov     eax, [rbp+38h]
0x1800027f2  cmp     eax, 0E06D7363h
0x1800027f7  jnz     short loc_18000280D
0x1800027f9  mov     rdx, [rbp+0B0h]
0x180002800  mov     ecx, [rbp+38h]
0x180002803  call    _XcptFilter_0
0x180002808  mov     [rbp+40h], eax
0x18000280b  jmp     short loc_180002814
0x18000280d  mov     dword ptr [rbp+40h], 0
0x180002814  mov     eax, [rbp+40h]
0x180002817  add     rsp, 20h
0x18000281b  pop     rbp
0x18000281c  retn
0x18000281e  push    rbp
0x180002820  sub     rsp, 20h
0x180002824  mov     rbp, rdx
0x180002827  mov     rax, [rcx]
0x18000282a  mov     edx, [rax]
0x18000282c  mov     [rbp+0B8h], rcx
0x180002833  mov     [rbp+48h], edx
0x180002836  mov     eax, [rbp+48h]
0x180002839  cmp     eax, 0E06D7363h
0x18000283e  jnz     short loc_180002854
0x180002840  mov     rdx, [rbp+0B8h]
0x180002847  mov     ecx, [rbp+48h]
0x18000284a  call    _XcptFilter_0
0x18000284f  mov     [rbp+50h], eax
0x180002852  jmp     short loc_18000285B
0x180002854  mov     dword ptr [rbp+50h], 0
0x18000285b  mov     eax, [rbp+50h]
0x18000285e  add     rsp, 20h
0x180002862  pop     rbp
0x180002863  retn
0x180002865  push    rbp
0x180002867  sub     rsp, 20h
0x18000286b  mov     rbp, rdx
0x18000286e  mov     rax, [rcx]
0x180002871  mov     edx, [rax]
0x180002873  mov     [rbp+0C0h], rcx
0x18000287a  mov     [rbp+58h], edx
0x18000287d  mov     eax, [rbp+58h]
0x180002880  cmp     eax, 0E06D7363h
0x180002885  jnz     short loc_18000289B
0x180002887  mov     rdx, [rbp+0C0h]
0x18000288e  mov     ecx, [rbp+58h]
0x180002891  call    _XcptFilter_0
0x180002896  mov     [rbp+60h], eax
0x180002899  jmp     short loc_1800028A2
0x18000289b  mov     dword ptr [rbp+60h], 0
0x1800028a2  mov     eax, [rbp+60h]
0x1800028a5  add     rsp, 20h
0x1800028a9  pop     rbp
0x1800028aa  retn
0x1800028ac  push    rbp
0x1800028ae  sub     rsp, 20h
0x1800028b2  mov     rbp, rdx
0x1800028b5  mov     rax, [rcx]
0x1800028b8  mov     edx, [rax]
0x1800028ba  mov     [rbp+0C8h], rcx
0x1800028c1  mov     [rbp+68h], edx
0x1800028c4  mov     eax, [rbp+68h]
0x1800028c7  cmp     eax, 0E06D7363h
0x1800028cc  jnz     short loc_1800028E2
0x1800028ce  mov     rdx, [rbp+0C8h]
0x1800028d5  mov     ecx, [rbp+68h]
0x1800028d8  call    _XcptFilter_0
0x1800028dd  mov     [rbp+70h], eax
0x1800028e0  jmp     short loc_1800028E9
0x1800028e2  mov     dword ptr [rbp+70h], 0
0x1800028e9  mov     eax, [rbp+70h]
0x1800028ec  add     rsp, 20h
0x1800028f0  pop     rbp
0x1800028f1  retn
0x1800028f3  push    rbp
0x1800028f5  sub     rsp, 20h
0x1800028f9  mov     rbp, rdx
0x1800028fc  mov     rax, [rcx]
0x1800028ff  mov     edx, [rax]
0x180002901  mov     [rbp+0D0h], rcx
0x180002908  mov     [rbp+78h], edx
0x18000290b  mov     eax, [rbp+78h]
0x18000290e  cmp     eax, 0E06D7363h
0x180002913  jnz     short loc_18000292C
0x180002915  mov     rdx, [rbp+0D0h]
0x18000291c  mov     ecx, [rbp+78h]
0x18000291f  call    _XcptFilter_0
0x180002924  mov     [rbp+80h], eax
0x18000292a  jmp     short loc_180002936
0x18000292c  mov     dword ptr [rbp+80h], 0
0x180002936  mov     eax, [rbp+80h]
0x18000293c  add     rsp, 20h
0x180002940  pop     rbp
0x180002941  retn
0x180002943  push    rbp
0x180002945  sub     rsp, 20h
0x180002949  mov     rbp, rdx
0x18000294c  mov     rax, [rcx]
0x18000294f  mov     edx, [rax]
0x180002951  mov     [rbp+0D8h], rcx
0x180002958  mov     [rbp+88h], edx
0x18000295e  mov     eax, [rbp+88h]
0x180002964  cmp     eax, 0E06D7363h
0x180002969  jnz     short loc_180002985
0x18000296b  mov     rdx, [rbp+0D8h]
0x180002972  mov     ecx, [rbp+88h]
0x180002978  call    _XcptFilter_0
0x18000297d  mov     [rbp+90h], eax
0x180002983  jmp     short loc_18000298F
0x180002985  mov     dword ptr [rbp+90h], 0
0x18000298f  mov     eax, [rbp+90h]
0x180002995  add     rsp, 20h
0x180002999  pop     rbp
0x18000299a  retn
0x18000299c  push    rbp
0x18000299e  sub     rsp, 20h
0x1800029a2  mov     rbp, rdx
0x1800029a5  mov     rax, [rcx]
0x1800029a8  mov     edx, [rax]
0x1800029aa  mov     [rbp+0E0h], rcx
0x1800029b1  mov     [rbp+98h], edx
0x1800029b7  mov     eax, [rbp+98h]
0x1800029bd  cmp     eax, 0E06D7363h
0x1800029c2  jnz     short loc_1800029DE
0x1800029c4  mov     rdx, [rbp+0E0h]
0x1800029cb  mov     ecx, [rbp+98h]
0x1800029d1  call    _XcptFilter_0
0x1800029d6  mov     [rbp+0A0h], eax
0x1800029dc  jmp     short loc_1800029E8
0x1800029de  mov     dword ptr [rbp+0A0h], 0
0x1800029e8  mov     eax, [rbp+0A0h]
0x1800029ee  add     rsp, 20h
0x1800029f2  pop     rbp
0x1800029f3  retn
0x1800029f5  push    rbp
0x1800029f7  sub     rsp, 20h
0x1800029fb  mov     rbp, rdx
0x1800029fe  cmp     dword ptr [rbp+118h], 1
0x180002a05  ja      short loc_180002A11
0x180002a07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
