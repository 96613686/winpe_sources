# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180002730`
- `0x180003190`

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
  if ( (_DWORD)fdwReason || dword_180007120 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180007124 = 1;
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
            if ( dword_180007124 )
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
0x180001344  cmp     cs:dword_180007120, edx
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
0x180001374  mov     cs:dword_180007124, edx
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
0x1800014d3  cmp     cs:dword_180007124, 0
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
0x180003200  push    rbp
0x180003202  sub     rsp, 20h
0x180003206  mov     rbp, rdx
0x180003209  mov     rax, [rcx]
0x18000320c  mov     edx, [rax]
0x18000320e  mov     [rbp+0A8h], rcx
0x180003215  mov     [rbp+28h], edx
0x180003218  mov     eax, [rbp+28h]
0x18000321b  cmp     eax, 0E06D7363h
0x180003220  jnz     short loc_180003236
0x180003222  mov     rdx, [rbp+0A8h]
0x180003229  mov     ecx, [rbp+28h]
0x18000322c  call    _XcptFilter_0
0x180003231  mov     [rbp+30h], eax
0x180003234  jmp     short loc_18000323D
0x180003236  mov     dword ptr [rbp+30h], 0
0x18000323d  mov     eax, [rbp+30h]
0x180003240  add     rsp, 20h
0x180003244  pop     rbp
0x180003245  retn
0x180003247  push    rbp
0x180003249  sub     rsp, 20h
0x18000324d  mov     rbp, rdx
0x180003250  mov     rax, [rcx]
0x180003253  mov     edx, [rax]
0x180003255  mov     [rbp+0B0h], rcx
0x18000325c  mov     [rbp+38h], edx
0x18000325f  mov     eax, [rbp+38h]
0x180003262  cmp     eax, 0E06D7363h
0x180003267  jnz     short loc_18000327D
0x180003269  mov     rdx, [rbp+0B0h]
0x180003270  mov     ecx, [rbp+38h]
0x180003273  call    _XcptFilter_0
0x180003278  mov     [rbp+40h], eax
0x18000327b  jmp     short loc_180003284
0x18000327d  mov     dword ptr [rbp+40h], 0
0x180003284  mov     eax, [rbp+40h]
0x180003287  add     rsp, 20h
0x18000328b  pop     rbp
0x18000328c  retn
0x18000328e  push    rbp
0x180003290  sub     rsp, 20h
0x180003294  mov     rbp, rdx
0x180003297  mov     rax, [rcx]
0x18000329a  mov     edx, [rax]
0x18000329c  mov     [rbp+0B8h], rcx
0x1800032a3  mov     [rbp+48h], edx
0x1800032a6  mov     eax, [rbp+48h]
0x1800032a9  cmp     eax, 0E06D7363h
0x1800032ae  jnz     short loc_1800032C4
0x1800032b0  mov     rdx, [rbp+0B8h]
0x1800032b7  mov     ecx, [rbp+48h]
0x1800032ba  call    _XcptFilter_0
0x1800032bf  mov     [rbp+50h], eax
0x1800032c2  jmp     short loc_1800032CB
0x1800032c4  mov     dword ptr [rbp+50h], 0
0x1800032cb  mov     eax, [rbp+50h]
0x1800032ce  add     rsp, 20h
0x1800032d2  pop     rbp
0x1800032d3  retn
0x1800032d5  push    rbp
0x1800032d7  sub     rsp, 20h
0x1800032db  mov     rbp, rdx
0x1800032de  mov     rax, [rcx]
0x1800032e1  mov     edx, [rax]
0x1800032e3  mov     [rbp+0C0h], rcx
0x1800032ea  mov     [rbp+58h], edx
0x1800032ed  mov     eax, [rbp+58h]
0x1800032f0  cmp     eax, 0E06D7363h
0x1800032f5  jnz     short loc_18000330B
0x1800032f7  mov     rdx, [rbp+0C0h]
0x1800032fe  mov     ecx, [rbp+58h]
0x180003301  call    _XcptFilter_0
0x180003306  mov     [rbp+60h], eax
0x180003309  jmp     short loc_180003312
0x18000330b  mov     dword ptr [rbp+60h], 0
0x180003312  mov     eax, [rbp+60h]
0x180003315  add     rsp, 20h
0x180003319  pop     rbp
0x18000331a  retn
0x18000331c  push    rbp
0x18000331e  sub     rsp, 20h
0x180003322  mov     rbp, rdx
0x180003325  mov     rax, [rcx]
0x180003328  mov     edx, [rax]
0x18000332a  mov     [rbp+0C8h], rcx
0x180003331  mov     [rbp+68h], edx
0x180003334  mov     eax, [rbp+68h]
0x180003337  cmp     eax, 0E06D7363h
0x18000333c  jnz     short loc_180003352
0x18000333e  mov     rdx, [rbp+0C8h]
0x180003345  mov     ecx, [rbp+68h]
0x180003348  call    _XcptFilter_0
0x18000334d  mov     [rbp+70h], eax
0x180003350  jmp     short loc_180003359
0x180003352  mov     dword ptr [rbp+70h], 0
0x180003359  mov     eax, [rbp+70h]
0x18000335c  add     rsp, 20h
0x180003360  pop     rbp
0x180003361  retn
0x180003363  push    rbp
0x180003365  sub     rsp, 20h
0x180003369  mov     rbp, rdx
0x18000336c  mov     rax, [rcx]
0x18000336f  mov     edx, [rax]
0x180003371  mov     [rbp+0D0h], rcx
0x180003378  mov     [rbp+78h], edx
0x18000337b  mov     eax, [rbp+78h]
0x18000337e  cmp     eax, 0E06D7363h
0x180003383  jnz     short loc_18000339C
0x180003385  mov     rdx, [rbp+0D0h]
0x18000338c  mov     ecx, [rbp+78h]
0x18000338f  call    _XcptFilter_0
0x180003394  mov     [rbp+80h], eax
0x18000339a  jmp     short loc_1800033A6
0x18000339c  mov     dword ptr [rbp+80h], 0
0x1800033a6  mov     eax, [rbp+80h]
0x1800033ac  add     rsp, 20h
0x1800033b0  pop     rbp
0x1800033b1  retn
0x1800033b3  push    rbp
0x1800033b5  sub     rsp, 20h
0x1800033b9  mov     rbp, rdx
0x1800033bc  mov     rax, [rcx]
0x1800033bf  mov     edx, [rax]
0x1800033c1  mov     [rbp+0D8h], rcx
0x1800033c8  mov     [rbp+88h], edx
0x1800033ce  mov     eax, [rbp+88h]
0x1800033d4  cmp     eax, 0E06D7363h
0x1800033d9  jnz     short loc_1800033F5
0x1800033db  mov     rdx, [rbp+0D8h]
0x1800033e2  mov     ecx, [rbp+88h]
0x1800033e8  call    _XcptFilter_0
0x1800033ed  mov     [rbp+90h], eax
0x1800033f3  jmp     short loc_1800033FF
0x1800033f5  mov     dword ptr [rbp+90h], 0
0x1800033ff  mov     eax, [rbp+90h]
0x180003405  add     rsp, 20h
0x180003409  pop     rbp
0x18000340a  retn
0x18000340c  push    rbp
0x18000340e  sub     rsp, 20h
0x180003412  mov     rbp, rdx
0x180003415  mov     rax, [rcx]
0x180003418  mov     edx, [rax]
0x18000341a  mov     [rbp+0E0h], rcx
0x180003421  mov     [rbp+98h], edx
0x180003427  mov     eax, [rbp+98h]
0x18000342d  cmp     eax, 0E06D7363h
0x180003432  jnz     short loc_18000344E
0x180003434  mov     rdx, [rbp+0E0h]
0x18000343b  mov     ecx, [rbp+98h]
0x180003441  call    _XcptFilter_0
0x180003446  mov     [rbp+0A0h], eax
0x18000344c  jmp     short loc_180003458
0x18000344e  mov     dword ptr [rbp+0A0h], 0
0x180003458  mov     eax, [rbp+0A0h]
0x18000345e  add     rsp, 20h
0x180003462  pop     rbp
0x180003463  retn
0x180003465  push    rbp
0x180003467  sub     rsp, 20h
0x18000346b  mov     rbp, rdx
0x18000346e  cmp     dword ptr [rbp+118h], 1
0x180003475  ja      short loc_180003481
0x180003477  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
