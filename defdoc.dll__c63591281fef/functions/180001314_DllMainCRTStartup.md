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
- `0x180003310`

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
0x180001344  cmp     cs:dword_1800070A0, edx
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
0x180001374  mov     cs:dword_1800070A4, edx
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
0x1800014d3  cmp     cs:dword_1800070A4, 0
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
0x1800033e0  push    rbp
0x1800033e2  sub     rsp, 20h
0x1800033e6  mov     rbp, rdx
0x1800033e9  mov     rax, [rcx]
0x1800033ec  mov     edx, [rax]
0x1800033ee  mov     [rbp+0A8h], rcx
0x1800033f5  mov     [rbp+28h], edx
0x1800033f8  mov     eax, [rbp+28h]
0x1800033fb  cmp     eax, 0E06D7363h
0x180003400  jnz     short loc_180003416
0x180003402  mov     rdx, [rbp+0A8h]
0x180003409  mov     ecx, [rbp+28h]
0x18000340c  call    _XcptFilter_0
0x180003411  mov     [rbp+30h], eax
0x180003414  jmp     short loc_18000341D
0x180003416  mov     dword ptr [rbp+30h], 0
0x18000341d  mov     eax, [rbp+30h]
0x180003420  add     rsp, 20h
0x180003424  pop     rbp
0x180003425  retn
0x180003427  push    rbp
0x180003429  sub     rsp, 20h
0x18000342d  mov     rbp, rdx
0x180003430  mov     rax, [rcx]
0x180003433  mov     edx, [rax]
0x180003435  mov     [rbp+0B0h], rcx
0x18000343c  mov     [rbp+38h], edx
0x18000343f  mov     eax, [rbp+38h]
0x180003442  cmp     eax, 0E06D7363h
0x180003447  jnz     short loc_18000345D
0x180003449  mov     rdx, [rbp+0B0h]
0x180003450  mov     ecx, [rbp+38h]
0x180003453  call    _XcptFilter_0
0x180003458  mov     [rbp+40h], eax
0x18000345b  jmp     short loc_180003464
0x18000345d  mov     dword ptr [rbp+40h], 0
0x180003464  mov     eax, [rbp+40h]
0x180003467  add     rsp, 20h
0x18000346b  pop     rbp
0x18000346c  retn
0x18000346e  push    rbp
0x180003470  sub     rsp, 20h
0x180003474  mov     rbp, rdx
0x180003477  mov     rax, [rcx]
0x18000347a  mov     edx, [rax]
0x18000347c  mov     [rbp+0B8h], rcx
0x180003483  mov     [rbp+48h], edx
0x180003486  mov     eax, [rbp+48h]
0x180003489  cmp     eax, 0E06D7363h
0x18000348e  jnz     short loc_1800034A4
0x180003490  mov     rdx, [rbp+0B8h]
0x180003497  mov     ecx, [rbp+48h]
0x18000349a  call    _XcptFilter_0
0x18000349f  mov     [rbp+50h], eax
0x1800034a2  jmp     short loc_1800034AB
0x1800034a4  mov     dword ptr [rbp+50h], 0
0x1800034ab  mov     eax, [rbp+50h]
0x1800034ae  add     rsp, 20h
0x1800034b2  pop     rbp
0x1800034b3  retn
0x1800034b5  push    rbp
0x1800034b7  sub     rsp, 20h
0x1800034bb  mov     rbp, rdx
0x1800034be  mov     rax, [rcx]
0x1800034c1  mov     edx, [rax]
0x1800034c3  mov     [rbp+0C0h], rcx
0x1800034ca  mov     [rbp+58h], edx
0x1800034cd  mov     eax, [rbp+58h]
0x1800034d0  cmp     eax, 0E06D7363h
0x1800034d5  jnz     short loc_1800034EB
0x1800034d7  mov     rdx, [rbp+0C0h]
0x1800034de  mov     ecx, [rbp+58h]
0x1800034e1  call    _XcptFilter_0
0x1800034e6  mov     [rbp+60h], eax
0x1800034e9  jmp     short loc_1800034F2
0x1800034eb  mov     dword ptr [rbp+60h], 0
0x1800034f2  mov     eax, [rbp+60h]
0x1800034f5  add     rsp, 20h
0x1800034f9  pop     rbp
0x1800034fa  retn
0x1800034fc  push    rbp
0x1800034fe  sub     rsp, 20h
0x180003502  mov     rbp, rdx
0x180003505  mov     rax, [rcx]
0x180003508  mov     edx, [rax]
0x18000350a  mov     [rbp+0C8h], rcx
0x180003511  mov     [rbp+68h], edx
0x180003514  mov     eax, [rbp+68h]
0x180003517  cmp     eax, 0E06D7363h
0x18000351c  jnz     short loc_180003532
0x18000351e  mov     rdx, [rbp+0C8h]
0x180003525  mov     ecx, [rbp+68h]
0x180003528  call    _XcptFilter_0
0x18000352d  mov     [rbp+70h], eax
0x180003530  jmp     short loc_180003539
0x180003532  mov     dword ptr [rbp+70h], 0
0x180003539  mov     eax, [rbp+70h]
0x18000353c  add     rsp, 20h
0x180003540  pop     rbp
0x180003541  retn
0x180003543  push    rbp
0x180003545  sub     rsp, 20h
0x180003549  mov     rbp, rdx
0x18000354c  mov     rax, [rcx]
0x18000354f  mov     edx, [rax]
0x180003551  mov     [rbp+0D0h], rcx
0x180003558  mov     [rbp+78h], edx
0x18000355b  mov     eax, [rbp+78h]
0x18000355e  cmp     eax, 0E06D7363h
0x180003563  jnz     short loc_18000357C
0x180003565  mov     rdx, [rbp+0D0h]
0x18000356c  mov     ecx, [rbp+78h]
0x18000356f  call    _XcptFilter_0
0x180003574  mov     [rbp+80h], eax
0x18000357a  jmp     short loc_180003586
0x18000357c  mov     dword ptr [rbp+80h], 0
0x180003586  mov     eax, [rbp+80h]
0x18000358c  add     rsp, 20h
0x180003590  pop     rbp
0x180003591  retn
0x180003593  push    rbp
0x180003595  sub     rsp, 20h
0x180003599  mov     rbp, rdx
0x18000359c  mov     rax, [rcx]
0x18000359f  mov     edx, [rax]
0x1800035a1  mov     [rbp+0D8h], rcx
0x1800035a8  mov     [rbp+88h], edx
0x1800035ae  mov     eax, [rbp+88h]
0x1800035b4  cmp     eax, 0E06D7363h
0x1800035b9  jnz     short loc_1800035D5
0x1800035bb  mov     rdx, [rbp+0D8h]
0x1800035c2  mov     ecx, [rbp+88h]
0x1800035c8  call    _XcptFilter_0
0x1800035cd  mov     [rbp+90h], eax
0x1800035d3  jmp     short loc_1800035DF
0x1800035d5  mov     dword ptr [rbp+90h], 0
0x1800035df  mov     eax, [rbp+90h]
0x1800035e5  add     rsp, 20h
0x1800035e9  pop     rbp
0x1800035ea  retn
0x1800035ec  push    rbp
0x1800035ee  sub     rsp, 20h
0x1800035f2  mov     rbp, rdx
0x1800035f5  mov     rax, [rcx]
0x1800035f8  mov     edx, [rax]
0x1800035fa  mov     [rbp+0E0h], rcx
0x180003601  mov     [rbp+98h], edx
0x180003607  mov     eax, [rbp+98h]
0x18000360d  cmp     eax, 0E06D7363h
0x180003612  jnz     short loc_18000362E
0x180003614  mov     rdx, [rbp+0E0h]
0x18000361b  mov     ecx, [rbp+98h]
0x180003621  call    _XcptFilter_0
0x180003626  mov     [rbp+0A0h], eax
0x18000362c  jmp     short loc_180003638
0x18000362e  mov     dword ptr [rbp+0A0h], 0
0x180003638  mov     eax, [rbp+0A0h]
0x18000363e  add     rsp, 20h
0x180003642  pop     rbp
0x180003643  retn
0x180003645  push    rbp
0x180003647  sub     rsp, 20h
0x18000364b  mov     rbp, rdx
0x18000364e  cmp     dword ptr [rbp+118h], 1
0x180003655  ja      short loc_180003661
0x180003657  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
