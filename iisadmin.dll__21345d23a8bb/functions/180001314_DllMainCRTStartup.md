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
- `0x180002840`
- `0x180004010`

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
0x180004080  push    rbp
0x180004082  sub     rsp, 20h
0x180004086  mov     rbp, rdx
0x180004089  mov     rax, [rcx]
0x18000408c  mov     edx, [rax]
0x18000408e  mov     [rbp+0A8h], rcx
0x180004095  mov     [rbp+28h], edx
0x180004098  mov     eax, [rbp+28h]
0x18000409b  cmp     eax, 0E06D7363h
0x1800040a0  jnz     short loc_1800040B6
0x1800040a2  mov     rdx, [rbp+0A8h]
0x1800040a9  mov     ecx, [rbp+28h]
0x1800040ac  call    _XcptFilter_0
0x1800040b1  mov     [rbp+30h], eax
0x1800040b4  jmp     short loc_1800040BD
0x1800040b6  mov     dword ptr [rbp+30h], 0
0x1800040bd  mov     eax, [rbp+30h]
0x1800040c0  add     rsp, 20h
0x1800040c4  pop     rbp
0x1800040c5  retn
0x1800040c7  push    rbp
0x1800040c9  sub     rsp, 20h
0x1800040cd  mov     rbp, rdx
0x1800040d0  mov     rax, [rcx]
0x1800040d3  mov     edx, [rax]
0x1800040d5  mov     [rbp+0B0h], rcx
0x1800040dc  mov     [rbp+38h], edx
0x1800040df  mov     eax, [rbp+38h]
0x1800040e2  cmp     eax, 0E06D7363h
0x1800040e7  jnz     short loc_1800040FD
0x1800040e9  mov     rdx, [rbp+0B0h]
0x1800040f0  mov     ecx, [rbp+38h]
0x1800040f3  call    _XcptFilter_0
0x1800040f8  mov     [rbp+40h], eax
0x1800040fb  jmp     short loc_180004104
0x1800040fd  mov     dword ptr [rbp+40h], 0
0x180004104  mov     eax, [rbp+40h]
0x180004107  add     rsp, 20h
0x18000410b  pop     rbp
0x18000410c  retn
0x18000410e  push    rbp
0x180004110  sub     rsp, 20h
0x180004114  mov     rbp, rdx
0x180004117  mov     rax, [rcx]
0x18000411a  mov     edx, [rax]
0x18000411c  mov     [rbp+0B8h], rcx
0x180004123  mov     [rbp+48h], edx
0x180004126  mov     eax, [rbp+48h]
0x180004129  cmp     eax, 0E06D7363h
0x18000412e  jnz     short loc_180004144
0x180004130  mov     rdx, [rbp+0B8h]
0x180004137  mov     ecx, [rbp+48h]
0x18000413a  call    _XcptFilter_0
0x18000413f  mov     [rbp+50h], eax
0x180004142  jmp     short loc_18000414B
0x180004144  mov     dword ptr [rbp+50h], 0
0x18000414b  mov     eax, [rbp+50h]
0x18000414e  add     rsp, 20h
0x180004152  pop     rbp
0x180004153  retn
0x180004155  push    rbp
0x180004157  sub     rsp, 20h
0x18000415b  mov     rbp, rdx
0x18000415e  mov     rax, [rcx]
0x180004161  mov     edx, [rax]
0x180004163  mov     [rbp+0C0h], rcx
0x18000416a  mov     [rbp+58h], edx
0x18000416d  mov     eax, [rbp+58h]
0x180004170  cmp     eax, 0E06D7363h
0x180004175  jnz     short loc_18000418B
0x180004177  mov     rdx, [rbp+0C0h]
0x18000417e  mov     ecx, [rbp+58h]
0x180004181  call    _XcptFilter_0
0x180004186  mov     [rbp+60h], eax
0x180004189  jmp     short loc_180004192
0x18000418b  mov     dword ptr [rbp+60h], 0
0x180004192  mov     eax, [rbp+60h]
0x180004195  add     rsp, 20h
0x180004199  pop     rbp
0x18000419a  retn
0x18000419c  push    rbp
0x18000419e  sub     rsp, 20h
0x1800041a2  mov     rbp, rdx
0x1800041a5  mov     rax, [rcx]
0x1800041a8  mov     edx, [rax]
0x1800041aa  mov     [rbp+0C8h], rcx
0x1800041b1  mov     [rbp+68h], edx
0x1800041b4  mov     eax, [rbp+68h]
0x1800041b7  cmp     eax, 0E06D7363h
0x1800041bc  jnz     short loc_1800041D2
0x1800041be  mov     rdx, [rbp+0C8h]
0x1800041c5  mov     ecx, [rbp+68h]
0x1800041c8  call    _XcptFilter_0
0x1800041cd  mov     [rbp+70h], eax
0x1800041d0  jmp     short loc_1800041D9
0x1800041d2  mov     dword ptr [rbp+70h], 0
0x1800041d9  mov     eax, [rbp+70h]
0x1800041dc  add     rsp, 20h
0x1800041e0  pop     rbp
0x1800041e1  retn
0x1800041e3  push    rbp
0x1800041e5  sub     rsp, 20h
0x1800041e9  mov     rbp, rdx
0x1800041ec  mov     rax, [rcx]
0x1800041ef  mov     edx, [rax]
0x1800041f1  mov     [rbp+0D0h], rcx
0x1800041f8  mov     [rbp+78h], edx
0x1800041fb  mov     eax, [rbp+78h]
0x1800041fe  cmp     eax, 0E06D7363h
0x180004203  jnz     short loc_18000421C
0x180004205  mov     rdx, [rbp+0D0h]
0x18000420c  mov     ecx, [rbp+78h]
0x18000420f  call    _XcptFilter_0
0x180004214  mov     [rbp+80h], eax
0x18000421a  jmp     short loc_180004226
0x18000421c  mov     dword ptr [rbp+80h], 0
0x180004226  mov     eax, [rbp+80h]
0x18000422c  add     rsp, 20h
0x180004230  pop     rbp
0x180004231  retn
0x180004233  push    rbp
0x180004235  sub     rsp, 20h
0x180004239  mov     rbp, rdx
0x18000423c  mov     rax, [rcx]
0x18000423f  mov     edx, [rax]
0x180004241  mov     [rbp+0D8h], rcx
0x180004248  mov     [rbp+88h], edx
0x18000424e  mov     eax, [rbp+88h]
0x180004254  cmp     eax, 0E06D7363h
0x180004259  jnz     short loc_180004275
0x18000425b  mov     rdx, [rbp+0D8h]
0x180004262  mov     ecx, [rbp+88h]
0x180004268  call    _XcptFilter_0
0x18000426d  mov     [rbp+90h], eax
0x180004273  jmp     short loc_18000427F
0x180004275  mov     dword ptr [rbp+90h], 0
0x18000427f  mov     eax, [rbp+90h]
0x180004285  add     rsp, 20h
0x180004289  pop     rbp
0x18000428a  retn
0x18000428c  push    rbp
0x18000428e  sub     rsp, 20h
0x180004292  mov     rbp, rdx
0x180004295  mov     rax, [rcx]
0x180004298  mov     edx, [rax]
0x18000429a  mov     [rbp+0E0h], rcx
0x1800042a1  mov     [rbp+98h], edx
0x1800042a7  mov     eax, [rbp+98h]
0x1800042ad  cmp     eax, 0E06D7363h
0x1800042b2  jnz     short loc_1800042CE
0x1800042b4  mov     rdx, [rbp+0E0h]
0x1800042bb  mov     ecx, [rbp+98h]
0x1800042c1  call    _XcptFilter_0
0x1800042c6  mov     [rbp+0A0h], eax
0x1800042cc  jmp     short loc_1800042D8
0x1800042ce  mov     dword ptr [rbp+0A0h], 0
0x1800042d8  mov     eax, [rbp+0A0h]
0x1800042de  add     rsp, 20h
0x1800042e2  pop     rbp
0x1800042e3  retn
0x1800042e5  push    rbp
0x1800042e7  sub     rsp, 20h
0x1800042eb  mov     rbp, rdx
0x1800042ee  cmp     dword ptr [rbp+118h], 1
0x1800042f5  ja      short loc_180004301
0x1800042f7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
