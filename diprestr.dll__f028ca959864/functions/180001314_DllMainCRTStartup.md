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
- `0x1800040dc`
- `0x180006800`

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
  if ( (_DWORD)fdwReason || dword_18000B0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B0A4 = 1;
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
            if ( dword_18000B0A4 )
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
0x180001344  cmp     cs:dword_18000B0A0, edx
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
0x180001374  mov     cs:dword_18000B0A4, edx
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
0x1800014d3  cmp     cs:dword_18000B0A4, 0
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
0x180006870  push    rbp
0x180006872  sub     rsp, 20h
0x180006876  mov     rbp, rdx
0x180006879  mov     rax, [rcx]
0x18000687c  mov     edx, [rax]
0x18000687e  mov     [rbp+0A8h], rcx
0x180006885  mov     [rbp+28h], edx
0x180006888  mov     eax, [rbp+28h]
0x18000688b  cmp     eax, 0E06D7363h
0x180006890  jnz     short loc_1800068A6
0x180006892  mov     rdx, [rbp+0A8h]
0x180006899  mov     ecx, [rbp+28h]
0x18000689c  call    _XcptFilter_0
0x1800068a1  mov     [rbp+30h], eax
0x1800068a4  jmp     short loc_1800068AD
0x1800068a6  mov     dword ptr [rbp+30h], 0
0x1800068ad  mov     eax, [rbp+30h]
0x1800068b0  add     rsp, 20h
0x1800068b4  pop     rbp
0x1800068b5  retn
0x1800068b7  push    rbp
0x1800068b9  sub     rsp, 20h
0x1800068bd  mov     rbp, rdx
0x1800068c0  mov     rax, [rcx]
0x1800068c3  mov     edx, [rax]
0x1800068c5  mov     [rbp+0B0h], rcx
0x1800068cc  mov     [rbp+38h], edx
0x1800068cf  mov     eax, [rbp+38h]
0x1800068d2  cmp     eax, 0E06D7363h
0x1800068d7  jnz     short loc_1800068ED
0x1800068d9  mov     rdx, [rbp+0B0h]
0x1800068e0  mov     ecx, [rbp+38h]
0x1800068e3  call    _XcptFilter_0
0x1800068e8  mov     [rbp+40h], eax
0x1800068eb  jmp     short loc_1800068F4
0x1800068ed  mov     dword ptr [rbp+40h], 0
0x1800068f4  mov     eax, [rbp+40h]
0x1800068f7  add     rsp, 20h
0x1800068fb  pop     rbp
0x1800068fc  retn
0x1800068fe  push    rbp
0x180006900  sub     rsp, 20h
0x180006904  mov     rbp, rdx
0x180006907  mov     rax, [rcx]
0x18000690a  mov     edx, [rax]
0x18000690c  mov     [rbp+0B8h], rcx
0x180006913  mov     [rbp+48h], edx
0x180006916  mov     eax, [rbp+48h]
0x180006919  cmp     eax, 0E06D7363h
0x18000691e  jnz     short loc_180006934
0x180006920  mov     rdx, [rbp+0B8h]
0x180006927  mov     ecx, [rbp+48h]
0x18000692a  call    _XcptFilter_0
0x18000692f  mov     [rbp+50h], eax
0x180006932  jmp     short loc_18000693B
0x180006934  mov     dword ptr [rbp+50h], 0
0x18000693b  mov     eax, [rbp+50h]
0x18000693e  add     rsp, 20h
0x180006942  pop     rbp
0x180006943  retn
0x180006945  push    rbp
0x180006947  sub     rsp, 20h
0x18000694b  mov     rbp, rdx
0x18000694e  mov     rax, [rcx]
0x180006951  mov     edx, [rax]
0x180006953  mov     [rbp+0C0h], rcx
0x18000695a  mov     [rbp+58h], edx
0x18000695d  mov     eax, [rbp+58h]
0x180006960  cmp     eax, 0E06D7363h
0x180006965  jnz     short loc_18000697B
0x180006967  mov     rdx, [rbp+0C0h]
0x18000696e  mov     ecx, [rbp+58h]
0x180006971  call    _XcptFilter_0
0x180006976  mov     [rbp+60h], eax
0x180006979  jmp     short loc_180006982
0x18000697b  mov     dword ptr [rbp+60h], 0
0x180006982  mov     eax, [rbp+60h]
0x180006985  add     rsp, 20h
0x180006989  pop     rbp
0x18000698a  retn
0x18000698c  push    rbp
0x18000698e  sub     rsp, 20h
0x180006992  mov     rbp, rdx
0x180006995  mov     rax, [rcx]
0x180006998  mov     edx, [rax]
0x18000699a  mov     [rbp+0C8h], rcx
0x1800069a1  mov     [rbp+68h], edx
0x1800069a4  mov     eax, [rbp+68h]
0x1800069a7  cmp     eax, 0E06D7363h
0x1800069ac  jnz     short loc_1800069C2
0x1800069ae  mov     rdx, [rbp+0C8h]
0x1800069b5  mov     ecx, [rbp+68h]
0x1800069b8  call    _XcptFilter_0
0x1800069bd  mov     [rbp+70h], eax
0x1800069c0  jmp     short loc_1800069C9
0x1800069c2  mov     dword ptr [rbp+70h], 0
0x1800069c9  mov     eax, [rbp+70h]
0x1800069cc  add     rsp, 20h
0x1800069d0  pop     rbp
0x1800069d1  retn
0x1800069d3  push    rbp
0x1800069d5  sub     rsp, 20h
0x1800069d9  mov     rbp, rdx
0x1800069dc  mov     rax, [rcx]
0x1800069df  mov     edx, [rax]
0x1800069e1  mov     [rbp+0D0h], rcx
0x1800069e8  mov     [rbp+78h], edx
0x1800069eb  mov     eax, [rbp+78h]
0x1800069ee  cmp     eax, 0E06D7363h
0x1800069f3  jnz     short loc_180006A0C
0x1800069f5  mov     rdx, [rbp+0D0h]
0x1800069fc  mov     ecx, [rbp+78h]
0x1800069ff  call    _XcptFilter_0
0x180006a04  mov     [rbp+80h], eax
0x180006a0a  jmp     short loc_180006A16
0x180006a0c  mov     dword ptr [rbp+80h], 0
0x180006a16  mov     eax, [rbp+80h]
0x180006a1c  add     rsp, 20h
0x180006a20  pop     rbp
0x180006a21  retn
0x180006a23  push    rbp
0x180006a25  sub     rsp, 20h
0x180006a29  mov     rbp, rdx
0x180006a2c  mov     rax, [rcx]
0x180006a2f  mov     edx, [rax]
0x180006a31  mov     [rbp+0D8h], rcx
0x180006a38  mov     [rbp+88h], edx
0x180006a3e  mov     eax, [rbp+88h]
0x180006a44  cmp     eax, 0E06D7363h
0x180006a49  jnz     short loc_180006A65
0x180006a4b  mov     rdx, [rbp+0D8h]
0x180006a52  mov     ecx, [rbp+88h]
0x180006a58  call    _XcptFilter_0
0x180006a5d  mov     [rbp+90h], eax
0x180006a63  jmp     short loc_180006A6F
0x180006a65  mov     dword ptr [rbp+90h], 0
0x180006a6f  mov     eax, [rbp+90h]
0x180006a75  add     rsp, 20h
0x180006a79  pop     rbp
0x180006a7a  retn
0x180006a7c  push    rbp
0x180006a7e  sub     rsp, 20h
0x180006a82  mov     rbp, rdx
0x180006a85  mov     rax, [rcx]
0x180006a88  mov     edx, [rax]
0x180006a8a  mov     [rbp+0E0h], rcx
0x180006a91  mov     [rbp+98h], edx
0x180006a97  mov     eax, [rbp+98h]
0x180006a9d  cmp     eax, 0E06D7363h
0x180006aa2  jnz     short loc_180006ABE
0x180006aa4  mov     rdx, [rbp+0E0h]
0x180006aab  mov     ecx, [rbp+98h]
0x180006ab1  call    _XcptFilter_0
0x180006ab6  mov     [rbp+0A0h], eax
0x180006abc  jmp     short loc_180006AC8
0x180006abe  mov     dword ptr [rbp+0A0h], 0
0x180006ac8  mov     eax, [rbp+0A0h]
0x180006ace  add     rsp, 20h
0x180006ad2  pop     rbp
0x180006ad3  retn
0x180006ad5  push    rbp
0x180006ad7  sub     rsp, 20h
0x180006adb  mov     rbp, rdx
0x180006ade  cmp     dword ptr [rbp+118h], 1
0x180006ae5  ja      short loc_180006AF1
0x180006ae7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
