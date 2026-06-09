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
- `0x18000180c`
- `0x180001a38`
- `0x180012eb0`

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
  if ( (_DWORD)fdwReason || dword_180019140 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180019144 = 1;
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
            if ( dword_180019144 )
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
0x1800012f4  cmp     cs:dword_180019140, edx
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
0x180001324  mov     cs:dword_180019144, edx
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
0x180001483  cmp     cs:dword_180019144, 0
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
0x180012f53  push    rbp
0x180012f55  sub     rsp, 20h
0x180012f59  mov     rbp, rdx
0x180012f5c  mov     rax, [rcx]
0x180012f5f  mov     edx, [rax]
0x180012f61  mov     [rbp+0A8h], rcx
0x180012f68  mov     [rbp+28h], edx
0x180012f6b  mov     eax, [rbp+28h]
0x180012f6e  cmp     eax, 0E06D7363h
0x180012f73  jnz     short loc_180012F89
0x180012f75  mov     rdx, [rbp+0A8h]
0x180012f7c  mov     ecx, [rbp+28h]
0x180012f7f  call    _XcptFilter_0
0x180012f84  mov     [rbp+30h], eax
0x180012f87  jmp     short loc_180012F90
0x180012f89  mov     dword ptr [rbp+30h], 0
0x180012f90  mov     eax, [rbp+30h]
0x180012f93  add     rsp, 20h
0x180012f97  pop     rbp
0x180012f98  retn
0x180012f9a  push    rbp
0x180012f9c  sub     rsp, 20h
0x180012fa0  mov     rbp, rdx
0x180012fa3  mov     rax, [rcx]
0x180012fa6  mov     edx, [rax]
0x180012fa8  mov     [rbp+0B0h], rcx
0x180012faf  mov     [rbp+38h], edx
0x180012fb2  mov     eax, [rbp+38h]
0x180012fb5  cmp     eax, 0E06D7363h
0x180012fba  jnz     short loc_180012FD0
0x180012fbc  mov     rdx, [rbp+0B0h]
0x180012fc3  mov     ecx, [rbp+38h]
0x180012fc6  call    _XcptFilter_0
0x180012fcb  mov     [rbp+40h], eax
0x180012fce  jmp     short loc_180012FD7
0x180012fd0  mov     dword ptr [rbp+40h], 0
0x180012fd7  mov     eax, [rbp+40h]
0x180012fda  add     rsp, 20h
0x180012fde  pop     rbp
0x180012fdf  retn
0x180012fe1  push    rbp
0x180012fe3  sub     rsp, 20h
0x180012fe7  mov     rbp, rdx
0x180012fea  mov     rax, [rcx]
0x180012fed  mov     edx, [rax]
0x180012fef  mov     [rbp+0B8h], rcx
0x180012ff6  mov     [rbp+48h], edx
0x180012ff9  mov     eax, [rbp+48h]
0x180012ffc  cmp     eax, 0E06D7363h
0x180013001  jnz     short loc_180013017
0x180013003  mov     rdx, [rbp+0B8h]
0x18001300a  mov     ecx, [rbp+48h]
0x18001300d  call    _XcptFilter_0
0x180013012  mov     [rbp+50h], eax
0x180013015  jmp     short loc_18001301E
0x180013017  mov     dword ptr [rbp+50h], 0
0x18001301e  mov     eax, [rbp+50h]
0x180013021  add     rsp, 20h
0x180013025  pop     rbp
0x180013026  retn
0x180013028  push    rbp
0x18001302a  sub     rsp, 20h
0x18001302e  mov     rbp, rdx
0x180013031  mov     rax, [rcx]
0x180013034  mov     edx, [rax]
0x180013036  mov     [rbp+0C0h], rcx
0x18001303d  mov     [rbp+58h], edx
0x180013040  mov     eax, [rbp+58h]
0x180013043  cmp     eax, 0E06D7363h
0x180013048  jnz     short loc_18001305E
0x18001304a  mov     rdx, [rbp+0C0h]
0x180013051  mov     ecx, [rbp+58h]
0x180013054  call    _XcptFilter_0
0x180013059  mov     [rbp+60h], eax
0x18001305c  jmp     short loc_180013065
0x18001305e  mov     dword ptr [rbp+60h], 0
0x180013065  mov     eax, [rbp+60h]
0x180013068  add     rsp, 20h
0x18001306c  pop     rbp
0x18001306d  retn
0x18001306f  push    rbp
0x180013071  sub     rsp, 20h
0x180013075  mov     rbp, rdx
0x180013078  mov     rax, [rcx]
0x18001307b  mov     edx, [rax]
0x18001307d  mov     [rbp+0C8h], rcx
0x180013084  mov     [rbp+68h], edx
0x180013087  mov     eax, [rbp+68h]
0x18001308a  cmp     eax, 0E06D7363h
0x18001308f  jnz     short loc_1800130A5
0x180013091  mov     rdx, [rbp+0C8h]
0x180013098  mov     ecx, [rbp+68h]
0x18001309b  call    _XcptFilter_0
0x1800130a0  mov     [rbp+70h], eax
0x1800130a3  jmp     short loc_1800130AC
0x1800130a5  mov     dword ptr [rbp+70h], 0
0x1800130ac  mov     eax, [rbp+70h]
0x1800130af  add     rsp, 20h
0x1800130b3  pop     rbp
0x1800130b4  retn
0x1800130b6  push    rbp
0x1800130b8  sub     rsp, 20h
0x1800130bc  mov     rbp, rdx
0x1800130bf  mov     rax, [rcx]
0x1800130c2  mov     edx, [rax]
0x1800130c4  mov     [rbp+0D0h], rcx
0x1800130cb  mov     [rbp+78h], edx
0x1800130ce  mov     eax, [rbp+78h]
0x1800130d1  cmp     eax, 0E06D7363h
0x1800130d6  jnz     short loc_1800130EF
0x1800130d8  mov     rdx, [rbp+0D0h]
0x1800130df  mov     ecx, [rbp+78h]
0x1800130e2  call    _XcptFilter_0
0x1800130e7  mov     [rbp+80h], eax
0x1800130ed  jmp     short loc_1800130F9
0x1800130ef  mov     dword ptr [rbp+80h], 0
0x1800130f9  mov     eax, [rbp+80h]
0x1800130ff  add     rsp, 20h
0x180013103  pop     rbp
0x180013104  retn
0x180013106  push    rbp
0x180013108  sub     rsp, 20h
0x18001310c  mov     rbp, rdx
0x18001310f  mov     rax, [rcx]
0x180013112  mov     edx, [rax]
0x180013114  mov     [rbp+0D8h], rcx
0x18001311b  mov     [rbp+88h], edx
0x180013121  mov     eax, [rbp+88h]
0x180013127  cmp     eax, 0E06D7363h
0x18001312c  jnz     short loc_180013148
0x18001312e  mov     rdx, [rbp+0D8h]
0x180013135  mov     ecx, [rbp+88h]
0x18001313b  call    _XcptFilter_0
0x180013140  mov     [rbp+90h], eax
0x180013146  jmp     short loc_180013152
0x180013148  mov     dword ptr [rbp+90h], 0
0x180013152  mov     eax, [rbp+90h]
0x180013158  add     rsp, 20h
0x18001315c  pop     rbp
0x18001315d  retn
0x18001315f  push    rbp
0x180013161  sub     rsp, 20h
0x180013165  mov     rbp, rdx
0x180013168  mov     rax, [rcx]
0x18001316b  mov     edx, [rax]
0x18001316d  mov     [rbp+0E0h], rcx
0x180013174  mov     [rbp+98h], edx
0x18001317a  mov     eax, [rbp+98h]
0x180013180  cmp     eax, 0E06D7363h
0x180013185  jnz     short loc_1800131A1
0x180013187  mov     rdx, [rbp+0E0h]
0x18001318e  mov     ecx, [rbp+98h]
0x180013194  call    _XcptFilter_0
0x180013199  mov     [rbp+0A0h], eax
0x18001319f  jmp     short loc_1800131AB
0x1800131a1  mov     dword ptr [rbp+0A0h], 0
0x1800131ab  mov     eax, [rbp+0A0h]
0x1800131b1  add     rsp, 20h
0x1800131b5  pop     rbp
0x1800131b6  retn
0x1800131b8  push    rbp
0x1800131ba  sub     rsp, 20h
0x1800131be  mov     rbp, rdx
0x1800131c1  cmp     dword ptr [rbp+118h], 1
0x1800131c8  ja      short loc_1800131D4
0x1800131ca  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
