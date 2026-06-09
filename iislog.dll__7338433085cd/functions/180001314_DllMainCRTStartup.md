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
- `0x180001880`
- `0x18000a51c`
- `0x18000ece0`

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
  if ( (_DWORD)fdwReason || dword_180017480 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180017484 = 1;
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
            if ( dword_180017484 )
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
0x180001344  cmp     cs:dword_180017480, edx
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
0x180001374  mov     cs:dword_180017484, edx
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
0x1800014d3  cmp     cs:dword_180017484, 0
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
0x18000edb0  push    rbp
0x18000edb2  sub     rsp, 20h
0x18000edb6  mov     rbp, rdx
0x18000edb9  mov     rax, [rcx]
0x18000edbc  mov     edx, [rax]
0x18000edbe  mov     [rbp+0A8h], rcx
0x18000edc5  mov     [rbp+28h], edx
0x18000edc8  mov     eax, [rbp+28h]
0x18000edcb  cmp     eax, 0E06D7363h
0x18000edd0  jnz     short loc_18000EDE6
0x18000edd2  mov     rdx, [rbp+0A8h]
0x18000edd9  mov     ecx, [rbp+28h]
0x18000eddc  call    _XcptFilter_0
0x18000ede1  mov     [rbp+30h], eax
0x18000ede4  jmp     short loc_18000EDED
0x18000ede6  mov     dword ptr [rbp+30h], 0
0x18000eded  mov     eax, [rbp+30h]
0x18000edf0  add     rsp, 20h
0x18000edf4  pop     rbp
0x18000edf5  retn
0x18000edf7  push    rbp
0x18000edf9  sub     rsp, 20h
0x18000edfd  mov     rbp, rdx
0x18000ee00  mov     rax, [rcx]
0x18000ee03  mov     edx, [rax]
0x18000ee05  mov     [rbp+0B0h], rcx
0x18000ee0c  mov     [rbp+38h], edx
0x18000ee0f  mov     eax, [rbp+38h]
0x18000ee12  cmp     eax, 0E06D7363h
0x18000ee17  jnz     short loc_18000EE2D
0x18000ee19  mov     rdx, [rbp+0B0h]
0x18000ee20  mov     ecx, [rbp+38h]
0x18000ee23  call    _XcptFilter_0
0x18000ee28  mov     [rbp+40h], eax
0x18000ee2b  jmp     short loc_18000EE34
0x18000ee2d  mov     dword ptr [rbp+40h], 0
0x18000ee34  mov     eax, [rbp+40h]
0x18000ee37  add     rsp, 20h
0x18000ee3b  pop     rbp
0x18000ee3c  retn
0x18000ee3e  push    rbp
0x18000ee40  sub     rsp, 20h
0x18000ee44  mov     rbp, rdx
0x18000ee47  mov     rax, [rcx]
0x18000ee4a  mov     edx, [rax]
0x18000ee4c  mov     [rbp+0B8h], rcx
0x18000ee53  mov     [rbp+48h], edx
0x18000ee56  mov     eax, [rbp+48h]
0x18000ee59  cmp     eax, 0E06D7363h
0x18000ee5e  jnz     short loc_18000EE74
0x18000ee60  mov     rdx, [rbp+0B8h]
0x18000ee67  mov     ecx, [rbp+48h]
0x18000ee6a  call    _XcptFilter_0
0x18000ee6f  mov     [rbp+50h], eax
0x18000ee72  jmp     short loc_18000EE7B
0x18000ee74  mov     dword ptr [rbp+50h], 0
0x18000ee7b  mov     eax, [rbp+50h]
0x18000ee7e  add     rsp, 20h
0x18000ee82  pop     rbp
0x18000ee83  retn
0x18000ee85  push    rbp
0x18000ee87  sub     rsp, 20h
0x18000ee8b  mov     rbp, rdx
0x18000ee8e  mov     rax, [rcx]
0x18000ee91  mov     edx, [rax]
0x18000ee93  mov     [rbp+0C0h], rcx
0x18000ee9a  mov     [rbp+58h], edx
0x18000ee9d  mov     eax, [rbp+58h]
0x18000eea0  cmp     eax, 0E06D7363h
0x18000eea5  jnz     short loc_18000EEBB
0x18000eea7  mov     rdx, [rbp+0C0h]
0x18000eeae  mov     ecx, [rbp+58h]
0x18000eeb1  call    _XcptFilter_0
0x18000eeb6  mov     [rbp+60h], eax
0x18000eeb9  jmp     short loc_18000EEC2
0x18000eebb  mov     dword ptr [rbp+60h], 0
0x18000eec2  mov     eax, [rbp+60h]
0x18000eec5  add     rsp, 20h
0x18000eec9  pop     rbp
0x18000eeca  retn
0x18000eecc  push    rbp
0x18000eece  sub     rsp, 20h
0x18000eed2  mov     rbp, rdx
0x18000eed5  mov     rax, [rcx]
0x18000eed8  mov     edx, [rax]
0x18000eeda  mov     [rbp+0C8h], rcx
0x18000eee1  mov     [rbp+68h], edx
0x18000eee4  mov     eax, [rbp+68h]
0x18000eee7  cmp     eax, 0E06D7363h
0x18000eeec  jnz     short loc_18000EF02
0x18000eeee  mov     rdx, [rbp+0C8h]
0x18000eef5  mov     ecx, [rbp+68h]
0x18000eef8  call    _XcptFilter_0
0x18000eefd  mov     [rbp+70h], eax
0x18000ef00  jmp     short loc_18000EF09
0x18000ef02  mov     dword ptr [rbp+70h], 0
0x18000ef09  mov     eax, [rbp+70h]
0x18000ef0c  add     rsp, 20h
0x18000ef10  pop     rbp
0x18000ef11  retn
0x18000ef13  push    rbp
0x18000ef15  sub     rsp, 20h
0x18000ef19  mov     rbp, rdx
0x18000ef1c  mov     rax, [rcx]
0x18000ef1f  mov     edx, [rax]
0x18000ef21  mov     [rbp+0D0h], rcx
0x18000ef28  mov     [rbp+78h], edx
0x18000ef2b  mov     eax, [rbp+78h]
0x18000ef2e  cmp     eax, 0E06D7363h
0x18000ef33  jnz     short loc_18000EF4C
0x18000ef35  mov     rdx, [rbp+0D0h]
0x18000ef3c  mov     ecx, [rbp+78h]
0x18000ef3f  call    _XcptFilter_0
0x18000ef44  mov     [rbp+80h], eax
0x18000ef4a  jmp     short loc_18000EF56
0x18000ef4c  mov     dword ptr [rbp+80h], 0
0x18000ef56  mov     eax, [rbp+80h]
0x18000ef5c  add     rsp, 20h
0x18000ef60  pop     rbp
0x18000ef61  retn
0x18000ef63  push    rbp
0x18000ef65  sub     rsp, 20h
0x18000ef69  mov     rbp, rdx
0x18000ef6c  mov     rax, [rcx]
0x18000ef6f  mov     edx, [rax]
0x18000ef71  mov     [rbp+0D8h], rcx
0x18000ef78  mov     [rbp+88h], edx
0x18000ef7e  mov     eax, [rbp+88h]
0x18000ef84  cmp     eax, 0E06D7363h
0x18000ef89  jnz     short loc_18000EFA5
0x18000ef8b  mov     rdx, [rbp+0D8h]
0x18000ef92  mov     ecx, [rbp+88h]
0x18000ef98  call    _XcptFilter_0
0x18000ef9d  mov     [rbp+90h], eax
0x18000efa3  jmp     short loc_18000EFAF
0x18000efa5  mov     dword ptr [rbp+90h], 0
0x18000efaf  mov     eax, [rbp+90h]
0x18000efb5  add     rsp, 20h
0x18000efb9  pop     rbp
0x18000efba  retn
0x18000efbc  push    rbp
0x18000efbe  sub     rsp, 20h
0x18000efc2  mov     rbp, rdx
0x18000efc5  mov     rax, [rcx]
0x18000efc8  mov     edx, [rax]
0x18000efca  mov     [rbp+0E0h], rcx
0x18000efd1  mov     [rbp+98h], edx
0x18000efd7  mov     eax, [rbp+98h]
0x18000efdd  cmp     eax, 0E06D7363h
0x18000efe2  jnz     short loc_18000EFFE
0x18000efe4  mov     rdx, [rbp+0E0h]
0x18000efeb  mov     ecx, [rbp+98h]
0x18000eff1  call    _XcptFilter_0
0x18000eff6  mov     [rbp+0A0h], eax
0x18000effc  jmp     short loc_18000F008
0x18000effe  mov     dword ptr [rbp+0A0h], 0
0x18000f008  mov     eax, [rbp+0A0h]
0x18000f00e  add     rsp, 20h
0x18000f012  pop     rbp
0x18000f013  retn
0x18000f015  push    rbp
0x18000f017  sub     rsp, 20h
0x18000f01b  mov     rbp, rdx
0x18000f01e  cmp     dword ptr [rbp+118h], 1
0x18000f025  ja      short loc_18000F031
0x18000f027  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
