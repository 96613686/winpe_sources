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
- `0x180003630`

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
0x1800036a0  push    rbp
0x1800036a2  sub     rsp, 20h
0x1800036a6  mov     rbp, rdx
0x1800036a9  mov     rax, [rcx]
0x1800036ac  mov     edx, [rax]
0x1800036ae  mov     [rbp+0A8h], rcx
0x1800036b5  mov     [rbp+28h], edx
0x1800036b8  mov     eax, [rbp+28h]
0x1800036bb  cmp     eax, 0E06D7363h
0x1800036c0  jnz     short loc_1800036D6
0x1800036c2  mov     rdx, [rbp+0A8h]
0x1800036c9  mov     ecx, [rbp+28h]
0x1800036cc  call    _XcptFilter_0
0x1800036d1  mov     [rbp+30h], eax
0x1800036d4  jmp     short loc_1800036DD
0x1800036d6  mov     dword ptr [rbp+30h], 0
0x1800036dd  mov     eax, [rbp+30h]
0x1800036e0  add     rsp, 20h
0x1800036e4  pop     rbp
0x1800036e5  retn
0x1800036e7  push    rbp
0x1800036e9  sub     rsp, 20h
0x1800036ed  mov     rbp, rdx
0x1800036f0  mov     rax, [rcx]
0x1800036f3  mov     edx, [rax]
0x1800036f5  mov     [rbp+0B0h], rcx
0x1800036fc  mov     [rbp+38h], edx
0x1800036ff  mov     eax, [rbp+38h]
0x180003702  cmp     eax, 0E06D7363h
0x180003707  jnz     short loc_18000371D
0x180003709  mov     rdx, [rbp+0B0h]
0x180003710  mov     ecx, [rbp+38h]
0x180003713  call    _XcptFilter_0
0x180003718  mov     [rbp+40h], eax
0x18000371b  jmp     short loc_180003724
0x18000371d  mov     dword ptr [rbp+40h], 0
0x180003724  mov     eax, [rbp+40h]
0x180003727  add     rsp, 20h
0x18000372b  pop     rbp
0x18000372c  retn
0x18000372e  push    rbp
0x180003730  sub     rsp, 20h
0x180003734  mov     rbp, rdx
0x180003737  mov     rax, [rcx]
0x18000373a  mov     edx, [rax]
0x18000373c  mov     [rbp+0B8h], rcx
0x180003743  mov     [rbp+48h], edx
0x180003746  mov     eax, [rbp+48h]
0x180003749  cmp     eax, 0E06D7363h
0x18000374e  jnz     short loc_180003764
0x180003750  mov     rdx, [rbp+0B8h]
0x180003757  mov     ecx, [rbp+48h]
0x18000375a  call    _XcptFilter_0
0x18000375f  mov     [rbp+50h], eax
0x180003762  jmp     short loc_18000376B
0x180003764  mov     dword ptr [rbp+50h], 0
0x18000376b  mov     eax, [rbp+50h]
0x18000376e  add     rsp, 20h
0x180003772  pop     rbp
0x180003773  retn
0x180003775  push    rbp
0x180003777  sub     rsp, 20h
0x18000377b  mov     rbp, rdx
0x18000377e  mov     rax, [rcx]
0x180003781  mov     edx, [rax]
0x180003783  mov     [rbp+0C0h], rcx
0x18000378a  mov     [rbp+58h], edx
0x18000378d  mov     eax, [rbp+58h]
0x180003790  cmp     eax, 0E06D7363h
0x180003795  jnz     short loc_1800037AB
0x180003797  mov     rdx, [rbp+0C0h]
0x18000379e  mov     ecx, [rbp+58h]
0x1800037a1  call    _XcptFilter_0
0x1800037a6  mov     [rbp+60h], eax
0x1800037a9  jmp     short loc_1800037B2
0x1800037ab  mov     dword ptr [rbp+60h], 0
0x1800037b2  mov     eax, [rbp+60h]
0x1800037b5  add     rsp, 20h
0x1800037b9  pop     rbp
0x1800037ba  retn
0x1800037bc  push    rbp
0x1800037be  sub     rsp, 20h
0x1800037c2  mov     rbp, rdx
0x1800037c5  mov     rax, [rcx]
0x1800037c8  mov     edx, [rax]
0x1800037ca  mov     [rbp+0C8h], rcx
0x1800037d1  mov     [rbp+68h], edx
0x1800037d4  mov     eax, [rbp+68h]
0x1800037d7  cmp     eax, 0E06D7363h
0x1800037dc  jnz     short loc_1800037F2
0x1800037de  mov     rdx, [rbp+0C8h]
0x1800037e5  mov     ecx, [rbp+68h]
0x1800037e8  call    _XcptFilter_0
0x1800037ed  mov     [rbp+70h], eax
0x1800037f0  jmp     short loc_1800037F9
0x1800037f2  mov     dword ptr [rbp+70h], 0
0x1800037f9  mov     eax, [rbp+70h]
0x1800037fc  add     rsp, 20h
0x180003800  pop     rbp
0x180003801  retn
0x180003803  push    rbp
0x180003805  sub     rsp, 20h
0x180003809  mov     rbp, rdx
0x18000380c  mov     rax, [rcx]
0x18000380f  mov     edx, [rax]
0x180003811  mov     [rbp+0D0h], rcx
0x180003818  mov     [rbp+78h], edx
0x18000381b  mov     eax, [rbp+78h]
0x18000381e  cmp     eax, 0E06D7363h
0x180003823  jnz     short loc_18000383C
0x180003825  mov     rdx, [rbp+0D0h]
0x18000382c  mov     ecx, [rbp+78h]
0x18000382f  call    _XcptFilter_0
0x180003834  mov     [rbp+80h], eax
0x18000383a  jmp     short loc_180003846
0x18000383c  mov     dword ptr [rbp+80h], 0
0x180003846  mov     eax, [rbp+80h]
0x18000384c  add     rsp, 20h
0x180003850  pop     rbp
0x180003851  retn
0x180003853  push    rbp
0x180003855  sub     rsp, 20h
0x180003859  mov     rbp, rdx
0x18000385c  mov     rax, [rcx]
0x18000385f  mov     edx, [rax]
0x180003861  mov     [rbp+0D8h], rcx
0x180003868  mov     [rbp+88h], edx
0x18000386e  mov     eax, [rbp+88h]
0x180003874  cmp     eax, 0E06D7363h
0x180003879  jnz     short loc_180003895
0x18000387b  mov     rdx, [rbp+0D8h]
0x180003882  mov     ecx, [rbp+88h]
0x180003888  call    _XcptFilter_0
0x18000388d  mov     [rbp+90h], eax
0x180003893  jmp     short loc_18000389F
0x180003895  mov     dword ptr [rbp+90h], 0
0x18000389f  mov     eax, [rbp+90h]
0x1800038a5  add     rsp, 20h
0x1800038a9  pop     rbp
0x1800038aa  retn
0x1800038ac  push    rbp
0x1800038ae  sub     rsp, 20h
0x1800038b2  mov     rbp, rdx
0x1800038b5  mov     rax, [rcx]
0x1800038b8  mov     edx, [rax]
0x1800038ba  mov     [rbp+0E0h], rcx
0x1800038c1  mov     [rbp+98h], edx
0x1800038c7  mov     eax, [rbp+98h]
0x1800038cd  cmp     eax, 0E06D7363h
0x1800038d2  jnz     short loc_1800038EE
0x1800038d4  mov     rdx, [rbp+0E0h]
0x1800038db  mov     ecx, [rbp+98h]
0x1800038e1  call    _XcptFilter_0
0x1800038e6  mov     [rbp+0A0h], eax
0x1800038ec  jmp     short loc_1800038F8
0x1800038ee  mov     dword ptr [rbp+0A0h], 0
0x1800038f8  mov     eax, [rbp+0A0h]
0x1800038fe  add     rsp, 20h
0x180003902  pop     rbp
0x180003903  retn
0x180003905  push    rbp
0x180003907  sub     rsp, 20h
0x18000390b  mov     rbp, rdx
0x18000390e  cmp     dword ptr [rbp+118h], 1
0x180003915  ja      short loc_180003921
0x180003917  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
