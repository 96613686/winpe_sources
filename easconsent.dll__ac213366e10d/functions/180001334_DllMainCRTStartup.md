# __DllMainCRTStartup

- ea: `0x180001334`
- end: `0x180001540`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012f0`

## callees

- `0x1800010c0`
- `0x180001334`
- `0x180001641`
- `0x180003028`
- `0x180003140`

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
  if ( (_DWORD)fdwReason || dword_1800070A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070A4 = 1;
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
            if ( dword_1800070A4 )
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
0x180001334  mov     [rsp+lpvReserved], r8
0x180001339  mov     [rsp+arg_8], edx
0x18000133d  mov     [rsp+arg_0], rcx
0x180001342  push    rbx
0x180001343  push    rsi
0x180001344  push    rdi
0x180001345  sub     rsp, 0F0h
0x18000134c  mov     edi, edx
0x18000134e  mov     rsi, rcx
0x180001351  mov     ebx, 1
0x180001356  cmp     edx, ebx
0x180001358  ja      short loc_180001360
0x18000135a  mov     cs:__native_dllmain_reason, edx
0x180001360  test    edx, edx
0x180001362  jnz     short loc_180001377
0x180001364  cmp     cs:dword_1800070A0, edx
0x18000136a  jnz     short loc_180001377
0x18000136c  xor     ebx, ebx
0x18000136e  mov     [rsp+108h+var_E8], ebx
0x180001372  jmp     loc_180001524
0x180001377  lea     eax, [rdx-1]
0x18000137a  cmp     eax, 1
0x18000137d  ja      loc_180001404
0x180001383  mov     rax, cs:_pRawDllMain
0x18000138a  test    rax, rax
0x18000138d  jz      short loc_1800013C5
0x18000138f  cmp     edx, 1
0x180001392  jnz     short loc_18000139A
0x180001394  mov     cs:dword_1800070A4, edx
0x18000139a  mov     r8, [rsp+108h+lpvReserved]
0x1800013a2  call    cs:__guard_dispatch_icall_fptr
0x1800013a8  mov     ebx, eax
0x1800013aa  mov     [rsp+108h+var_E8], eax
0x1800013ae  jmp     short loc_1800013C5
0x1800013b0  xor     ebx, ebx
0x1800013b2  mov     [rsp+108h+var_E8], ebx
0x1800013b6  mov     edi, [rsp+108h+arg_8]
0x1800013bd  mov     rsi, [rsp+108h+arg_0]
0x1800013c5  test    ebx, ebx
0x1800013c7  jz      loc_180001524
0x1800013cd  mov     r8, [rsp+108h+lpvReserved]
0x1800013d5  mov     edx, edi
0x1800013d7  mov     rcx, rsi
0x1800013da  call    _CRT_INIT
0x1800013df  mov     ebx, eax
0x1800013e1  mov     [rsp+108h+var_E8], eax
0x1800013e5  jmp     short loc_1800013FC
0x1800013e7  xor     ebx, ebx
0x1800013e9  mov     [rsp+108h+var_E8], ebx
0x1800013ed  mov     edi, [rsp+108h+arg_8]
0x1800013f4  mov     rsi, [rsp+108h+arg_0]
0x1800013fc  test    ebx, ebx
0x1800013fe  jz      loc_180001524
0x180001404  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000140c  mov     edx, edi; fdwReason
0x18000140e  mov     rcx, rsi; hinstDLL
0x180001411  call    DllMain
0x180001416  mov     ebx, eax
0x180001418  mov     [rsp+108h+var_E8], eax
0x18000141c  jmp     short loc_180001433
0x18000141e  xor     ebx, ebx
0x180001420  mov     [rsp+108h+var_E8], ebx
0x180001424  mov     edi, [rsp+108h+arg_8]
0x18000142b  mov     rsi, [rsp+108h+arg_0]
0x180001433  cmp     edi, 1
0x180001436  jnz     short loc_1800014AF
0x180001438  test    ebx, ebx
0x18000143a  jnz     short loc_1800014AF
0x18000143c  xor     r8d, r8d; lpvReserved
0x18000143f  xor     edx, edx; fdwReason
0x180001441  mov     rcx, rsi; hinstDLL
0x180001444  call    DllMain
0x180001449  jmp     short loc_18000145E
0x18000144b  mov     edi, [rsp+108h+arg_8]
0x180001452  mov     rsi, [rsp+108h+arg_0]
0x18000145a  mov     ebx, [rsp+108h+var_E8]
0x18000145e  xor     r8d, r8d
0x180001461  xor     edx, edx
0x180001463  mov     rcx, rsi
0x180001466  call    _CRT_INIT
0x18000146b  jmp     short loc_180001480
0x18000146d  mov     edi, [rsp+108h+arg_8]
0x180001474  mov     rsi, [rsp+108h+arg_0]
0x18000147c  mov     ebx, [rsp+108h+var_E8]
0x180001480  mov     rax, cs:_pRawDllMain
0x180001487  test    rax, rax
0x18000148a  jz      short loc_1800014AF
0x18000148c  xor     r8d, r8d
0x18000148f  xor     edx, edx
0x180001491  mov     rcx, rsi
0x180001494  call    cs:__guard_dispatch_icall_fptr
0x18000149a  jmp     short loc_1800014AF
0x18000149c  mov     edi, [rsp+108h+arg_8]
0x1800014a3  mov     rsi, [rsp+108h+arg_0]
0x1800014ab  mov     ebx, [rsp+108h+var_E8]
0x1800014af  test    edi, edi
0x1800014b1  jz      short loc_1800014B8
0x1800014b3  cmp     edi, 3
0x1800014b6  jnz     short loc_180001524
0x1800014b8  mov     r8, [rsp+108h+lpvReserved]
0x1800014c0  mov     edx, edi
0x1800014c2  mov     rcx, rsi
0x1800014c5  call    _CRT_INIT
0x1800014ca  mov     ebx, eax
0x1800014cc  mov     [rsp+108h+var_E8], eax
0x1800014d0  jmp     short loc_1800014E7
0x1800014d2  xor     ebx, ebx
0x1800014d4  mov     [rsp+108h+var_E8], ebx
0x1800014d8  mov     edi, [rsp+108h+arg_8]
0x1800014df  mov     rsi, [rsp+108h+arg_0]
0x1800014e7  mov     rax, cs:_pRawDllMain
0x1800014ee  test    rax, rax
0x1800014f1  jz      short loc_180001524
0x1800014f3  cmp     cs:dword_1800070A4, 0
0x1800014fa  jz      short loc_180001524
0x1800014fc  mov     r8, [rsp+108h+lpvReserved]
0x180001504  mov     edx, edi
0x180001506  mov     rcx, rsi
0x180001509  call    cs:__guard_dispatch_icall_fptr
0x18000150f  mov     ebx, eax
0x180001511  mov     [rsp+108h+var_E8], eax
0x180001515  jmp     short loc_180001524
0x180001517  xor     ebx, ebx
0x180001519  mov     [rsp+108h+var_E8], ebx
0x18000151d  mov     edi, [rsp+108h+arg_8]
0x180001524  cmp     edi, 1
0x180001527  ja      short loc_180001533
0x180001529  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001533  mov     eax, ebx
0x180001535  add     rsp, 0F0h
0x18000153c  pop     rdi
0x18000153d  pop     rsi
0x18000153e  pop     rbx
0x18000153f  retn
0x1800031b0  push    rbp
0x1800031b2  sub     rsp, 20h
0x1800031b6  mov     rbp, rdx
0x1800031b9  mov     rax, [rcx]
0x1800031bc  mov     edx, [rax]
0x1800031be  mov     [rbp+0A8h], rcx
0x1800031c5  mov     [rbp+28h], edx
0x1800031c8  mov     eax, [rbp+28h]
0x1800031cb  cmp     eax, 0E06D7363h
0x1800031d0  jnz     short loc_1800031E6
0x1800031d2  mov     rdx, [rbp+0A8h]
0x1800031d9  mov     ecx, [rbp+28h]
0x1800031dc  call    _XcptFilter_0
0x1800031e1  mov     [rbp+30h], eax
0x1800031e4  jmp     short loc_1800031ED
0x1800031e6  mov     dword ptr [rbp+30h], 0
0x1800031ed  mov     eax, [rbp+30h]
0x1800031f0  add     rsp, 20h
0x1800031f4  pop     rbp
0x1800031f5  retn
0x1800031f7  push    rbp
0x1800031f9  sub     rsp, 20h
0x1800031fd  mov     rbp, rdx
0x180003200  mov     rax, [rcx]
0x180003203  mov     edx, [rax]
0x180003205  mov     [rbp+0B0h], rcx
0x18000320c  mov     [rbp+38h], edx
0x18000320f  mov     eax, [rbp+38h]
0x180003212  cmp     eax, 0E06D7363h
0x180003217  jnz     short loc_18000322D
0x180003219  mov     rdx, [rbp+0B0h]
0x180003220  mov     ecx, [rbp+38h]
0x180003223  call    _XcptFilter_0
0x180003228  mov     [rbp+40h], eax
0x18000322b  jmp     short loc_180003234
0x18000322d  mov     dword ptr [rbp+40h], 0
0x180003234  mov     eax, [rbp+40h]
0x180003237  add     rsp, 20h
0x18000323b  pop     rbp
0x18000323c  retn
0x18000323e  push    rbp
0x180003240  sub     rsp, 20h
0x180003244  mov     rbp, rdx
0x180003247  mov     rax, [rcx]
0x18000324a  mov     edx, [rax]
0x18000324c  mov     [rbp+0B8h], rcx
0x180003253  mov     [rbp+48h], edx
0x180003256  mov     eax, [rbp+48h]
0x180003259  cmp     eax, 0E06D7363h
0x18000325e  jnz     short loc_180003274
0x180003260  mov     rdx, [rbp+0B8h]
0x180003267  mov     ecx, [rbp+48h]
0x18000326a  call    _XcptFilter_0
0x18000326f  mov     [rbp+50h], eax
0x180003272  jmp     short loc_18000327B
0x180003274  mov     dword ptr [rbp+50h], 0
0x18000327b  mov     eax, [rbp+50h]
0x18000327e  add     rsp, 20h
0x180003282  pop     rbp
0x180003283  retn
0x180003285  push    rbp
0x180003287  sub     rsp, 20h
0x18000328b  mov     rbp, rdx
0x18000328e  mov     rax, [rcx]
0x180003291  mov     edx, [rax]
0x180003293  mov     [rbp+0C0h], rcx
0x18000329a  mov     [rbp+58h], edx
0x18000329d  mov     eax, [rbp+58h]
0x1800032a0  cmp     eax, 0E06D7363h
0x1800032a5  jnz     short loc_1800032BB
0x1800032a7  mov     rdx, [rbp+0C0h]
0x1800032ae  mov     ecx, [rbp+58h]
0x1800032b1  call    _XcptFilter_0
0x1800032b6  mov     [rbp+60h], eax
0x1800032b9  jmp     short loc_1800032C2
0x1800032bb  mov     dword ptr [rbp+60h], 0
0x1800032c2  mov     eax, [rbp+60h]
0x1800032c5  add     rsp, 20h
0x1800032c9  pop     rbp
0x1800032ca  retn
0x1800032cc  push    rbp
0x1800032ce  sub     rsp, 20h
0x1800032d2  mov     rbp, rdx
0x1800032d5  mov     rax, [rcx]
0x1800032d8  mov     edx, [rax]
0x1800032da  mov     [rbp+0C8h], rcx
0x1800032e1  mov     [rbp+68h], edx
0x1800032e4  mov     eax, [rbp+68h]
0x1800032e7  cmp     eax, 0E06D7363h
0x1800032ec  jnz     short loc_180003302
0x1800032ee  mov     rdx, [rbp+0C8h]
0x1800032f5  mov     ecx, [rbp+68h]
0x1800032f8  call    _XcptFilter_0
0x1800032fd  mov     [rbp+70h], eax
0x180003300  jmp     short loc_180003309
0x180003302  mov     dword ptr [rbp+70h], 0
0x180003309  mov     eax, [rbp+70h]
0x18000330c  add     rsp, 20h
0x180003310  pop     rbp
0x180003311  retn
0x180003313  push    rbp
0x180003315  sub     rsp, 20h
0x180003319  mov     rbp, rdx
0x18000331c  mov     rax, [rcx]
0x18000331f  mov     edx, [rax]
0x180003321  mov     [rbp+0D0h], rcx
0x180003328  mov     [rbp+78h], edx
0x18000332b  mov     eax, [rbp+78h]
0x18000332e  cmp     eax, 0E06D7363h
0x180003333  jnz     short loc_18000334C
0x180003335  mov     rdx, [rbp+0D0h]
0x18000333c  mov     ecx, [rbp+78h]
0x18000333f  call    _XcptFilter_0
0x180003344  mov     [rbp+80h], eax
0x18000334a  jmp     short loc_180003356
0x18000334c  mov     dword ptr [rbp+80h], 0
0x180003356  mov     eax, [rbp+80h]
0x18000335c  add     rsp, 20h
0x180003360  pop     rbp
0x180003361  retn
0x180003363  push    rbp
0x180003365  sub     rsp, 20h
0x180003369  mov     rbp, rdx
0x18000336c  mov     rax, [rcx]
0x18000336f  mov     edx, [rax]
0x180003371  mov     [rbp+0D8h], rcx
0x180003378  mov     [rbp+88h], edx
0x18000337e  mov     eax, [rbp+88h]
0x180003384  cmp     eax, 0E06D7363h
0x180003389  jnz     short loc_1800033A5
0x18000338b  mov     rdx, [rbp+0D8h]
0x180003392  mov     ecx, [rbp+88h]
0x180003398  call    _XcptFilter_0
0x18000339d  mov     [rbp+90h], eax
0x1800033a3  jmp     short loc_1800033AF
0x1800033a5  mov     dword ptr [rbp+90h], 0
0x1800033af  mov     eax, [rbp+90h]
0x1800033b5  add     rsp, 20h
0x1800033b9  pop     rbp
0x1800033ba  retn
0x1800033bc  push    rbp
0x1800033be  sub     rsp, 20h
0x1800033c2  mov     rbp, rdx
0x1800033c5  mov     rax, [rcx]
0x1800033c8  mov     edx, [rax]
0x1800033ca  mov     [rbp+0E0h], rcx
0x1800033d1  mov     [rbp+98h], edx
0x1800033d7  mov     eax, [rbp+98h]
0x1800033dd  cmp     eax, 0E06D7363h
0x1800033e2  jnz     short loc_1800033FE
0x1800033e4  mov     rdx, [rbp+0E0h]
0x1800033eb  mov     ecx, [rbp+98h]
0x1800033f1  call    _XcptFilter_0
0x1800033f6  mov     [rbp+0A0h], eax
0x1800033fc  jmp     short loc_180003408
0x1800033fe  mov     dword ptr [rbp+0A0h], 0
0x180003408  mov     eax, [rbp+0A0h]
0x18000340e  add     rsp, 20h
0x180003412  pop     rbp
0x180003413  retn
0x180003415  push    rbp
0x180003417  sub     rsp, 20h
0x18000341b  mov     rbp, rdx
0x18000341e  cmp     dword ptr [rbp+118h], 1
0x180003425  ja      short loc_180003431
0x180003427  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
