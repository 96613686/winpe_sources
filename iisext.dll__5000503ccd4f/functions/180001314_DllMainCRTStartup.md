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
- `0x18000174a`
- `0x180001a2c`
- `0x180011220`

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
  if ( (_DWORD)fdwReason || dword_180019220 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180019224 = 1;
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
            if ( dword_180019224 )
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
0x180001344  cmp     cs:dword_180019220, edx
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
0x180001374  mov     cs:dword_180019224, edx
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
0x1800014d3  cmp     cs:dword_180019224, 0
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
0x180011290  push    rbp
0x180011292  sub     rsp, 20h
0x180011296  mov     rbp, rdx
0x180011299  mov     rax, [rcx]
0x18001129c  mov     edx, [rax]
0x18001129e  mov     [rbp+0A8h], rcx
0x1800112a5  mov     [rbp+28h], edx
0x1800112a8  mov     eax, [rbp+28h]
0x1800112ab  cmp     eax, 0E06D7363h
0x1800112b0  jnz     short loc_1800112C6
0x1800112b2  mov     rdx, [rbp+0A8h]
0x1800112b9  mov     ecx, [rbp+28h]
0x1800112bc  call    _XcptFilter_0
0x1800112c1  mov     [rbp+30h], eax
0x1800112c4  jmp     short loc_1800112CD
0x1800112c6  mov     dword ptr [rbp+30h], 0
0x1800112cd  mov     eax, [rbp+30h]
0x1800112d0  add     rsp, 20h
0x1800112d4  pop     rbp
0x1800112d5  retn
0x1800112d7  push    rbp
0x1800112d9  sub     rsp, 20h
0x1800112dd  mov     rbp, rdx
0x1800112e0  mov     rax, [rcx]
0x1800112e3  mov     edx, [rax]
0x1800112e5  mov     [rbp+0B0h], rcx
0x1800112ec  mov     [rbp+38h], edx
0x1800112ef  mov     eax, [rbp+38h]
0x1800112f2  cmp     eax, 0E06D7363h
0x1800112f7  jnz     short loc_18001130D
0x1800112f9  mov     rdx, [rbp+0B0h]
0x180011300  mov     ecx, [rbp+38h]
0x180011303  call    _XcptFilter_0
0x180011308  mov     [rbp+40h], eax
0x18001130b  jmp     short loc_180011314
0x18001130d  mov     dword ptr [rbp+40h], 0
0x180011314  mov     eax, [rbp+40h]
0x180011317  add     rsp, 20h
0x18001131b  pop     rbp
0x18001131c  retn
0x18001131e  push    rbp
0x180011320  sub     rsp, 20h
0x180011324  mov     rbp, rdx
0x180011327  mov     rax, [rcx]
0x18001132a  mov     edx, [rax]
0x18001132c  mov     [rbp+0B8h], rcx
0x180011333  mov     [rbp+48h], edx
0x180011336  mov     eax, [rbp+48h]
0x180011339  cmp     eax, 0E06D7363h
0x18001133e  jnz     short loc_180011354
0x180011340  mov     rdx, [rbp+0B8h]
0x180011347  mov     ecx, [rbp+48h]
0x18001134a  call    _XcptFilter_0
0x18001134f  mov     [rbp+50h], eax
0x180011352  jmp     short loc_18001135B
0x180011354  mov     dword ptr [rbp+50h], 0
0x18001135b  mov     eax, [rbp+50h]
0x18001135e  add     rsp, 20h
0x180011362  pop     rbp
0x180011363  retn
0x180011365  push    rbp
0x180011367  sub     rsp, 20h
0x18001136b  mov     rbp, rdx
0x18001136e  mov     rax, [rcx]
0x180011371  mov     edx, [rax]
0x180011373  mov     [rbp+0C0h], rcx
0x18001137a  mov     [rbp+58h], edx
0x18001137d  mov     eax, [rbp+58h]
0x180011380  cmp     eax, 0E06D7363h
0x180011385  jnz     short loc_18001139B
0x180011387  mov     rdx, [rbp+0C0h]
0x18001138e  mov     ecx, [rbp+58h]
0x180011391  call    _XcptFilter_0
0x180011396  mov     [rbp+60h], eax
0x180011399  jmp     short loc_1800113A2
0x18001139b  mov     dword ptr [rbp+60h], 0
0x1800113a2  mov     eax, [rbp+60h]
0x1800113a5  add     rsp, 20h
0x1800113a9  pop     rbp
0x1800113aa  retn
0x1800113ac  push    rbp
0x1800113ae  sub     rsp, 20h
0x1800113b2  mov     rbp, rdx
0x1800113b5  mov     rax, [rcx]
0x1800113b8  mov     edx, [rax]
0x1800113ba  mov     [rbp+0C8h], rcx
0x1800113c1  mov     [rbp+68h], edx
0x1800113c4  mov     eax, [rbp+68h]
0x1800113c7  cmp     eax, 0E06D7363h
0x1800113cc  jnz     short loc_1800113E2
0x1800113ce  mov     rdx, [rbp+0C8h]
0x1800113d5  mov     ecx, [rbp+68h]
0x1800113d8  call    _XcptFilter_0
0x1800113dd  mov     [rbp+70h], eax
0x1800113e0  jmp     short loc_1800113E9
0x1800113e2  mov     dword ptr [rbp+70h], 0
0x1800113e9  mov     eax, [rbp+70h]
0x1800113ec  add     rsp, 20h
0x1800113f0  pop     rbp
0x1800113f1  retn
0x1800113f3  push    rbp
0x1800113f5  sub     rsp, 20h
0x1800113f9  mov     rbp, rdx
0x1800113fc  mov     rax, [rcx]
0x1800113ff  mov     edx, [rax]
0x180011401  mov     [rbp+0D0h], rcx
0x180011408  mov     [rbp+78h], edx
0x18001140b  mov     eax, [rbp+78h]
0x18001140e  cmp     eax, 0E06D7363h
0x180011413  jnz     short loc_18001142C
0x180011415  mov     rdx, [rbp+0D0h]
0x18001141c  mov     ecx, [rbp+78h]
0x18001141f  call    _XcptFilter_0
0x180011424  mov     [rbp+80h], eax
0x18001142a  jmp     short loc_180011436
0x18001142c  mov     dword ptr [rbp+80h], 0
0x180011436  mov     eax, [rbp+80h]
0x18001143c  add     rsp, 20h
0x180011440  pop     rbp
0x180011441  retn
0x180011443  push    rbp
0x180011445  sub     rsp, 20h
0x180011449  mov     rbp, rdx
0x18001144c  mov     rax, [rcx]
0x18001144f  mov     edx, [rax]
0x180011451  mov     [rbp+0D8h], rcx
0x180011458  mov     [rbp+88h], edx
0x18001145e  mov     eax, [rbp+88h]
0x180011464  cmp     eax, 0E06D7363h
0x180011469  jnz     short loc_180011485
0x18001146b  mov     rdx, [rbp+0D8h]
0x180011472  mov     ecx, [rbp+88h]
0x180011478  call    _XcptFilter_0
0x18001147d  mov     [rbp+90h], eax
0x180011483  jmp     short loc_18001148F
0x180011485  mov     dword ptr [rbp+90h], 0
0x18001148f  mov     eax, [rbp+90h]
0x180011495  add     rsp, 20h
0x180011499  pop     rbp
0x18001149a  retn
0x18001149c  push    rbp
0x18001149e  sub     rsp, 20h
0x1800114a2  mov     rbp, rdx
0x1800114a5  mov     rax, [rcx]
0x1800114a8  mov     edx, [rax]
0x1800114aa  mov     [rbp+0E0h], rcx
0x1800114b1  mov     [rbp+98h], edx
0x1800114b7  mov     eax, [rbp+98h]
0x1800114bd  cmp     eax, 0E06D7363h
0x1800114c2  jnz     short loc_1800114DE
0x1800114c4  mov     rdx, [rbp+0E0h]
0x1800114cb  mov     ecx, [rbp+98h]
0x1800114d1  call    _XcptFilter_0
0x1800114d6  mov     [rbp+0A0h], eax
0x1800114dc  jmp     short loc_1800114E8
0x1800114de  mov     dword ptr [rbp+0A0h], 0
0x1800114e8  mov     eax, [rbp+0A0h]
0x1800114ee  add     rsp, 20h
0x1800114f2  pop     rbp
0x1800114f3  retn
0x1800114f5  push    rbp
0x1800114f7  sub     rsp, 20h
0x1800114fb  mov     rbp, rdx
0x1800114fe  cmp     dword ptr [rbp+118h], 1
0x180011505  ja      short loc_180011511
0x180011507  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
