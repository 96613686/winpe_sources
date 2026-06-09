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
- `0x1800014d6`
- `0x180001988`
- `0x180003e60`

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
  if ( (_DWORD)fdwReason || dword_1800070E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070E4 = 1;
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
            if ( dword_1800070E4 )
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
0x1800012f4  cmp     cs:dword_1800070E0, edx
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
0x180001324  mov     cs:dword_1800070E4, edx
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
0x180001483  cmp     cs:dword_1800070E4, 0
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
0x180003ea0  push    rbp
0x180003ea2  sub     rsp, 20h
0x180003ea6  mov     rbp, rdx
0x180003ea9  mov     rax, [rcx]
0x180003eac  mov     edx, [rax]
0x180003eae  mov     [rbp+0A8h], rcx
0x180003eb5  mov     [rbp+28h], edx
0x180003eb8  mov     eax, [rbp+28h]
0x180003ebb  cmp     eax, 0E06D7363h
0x180003ec0  jnz     short loc_180003ED6
0x180003ec2  mov     rdx, [rbp+0A8h]
0x180003ec9  mov     ecx, [rbp+28h]
0x180003ecc  call    _XcptFilter_0
0x180003ed1  mov     [rbp+30h], eax
0x180003ed4  jmp     short loc_180003EDD
0x180003ed6  mov     dword ptr [rbp+30h], 0
0x180003edd  mov     eax, [rbp+30h]
0x180003ee0  add     rsp, 20h
0x180003ee4  pop     rbp
0x180003ee5  retn
0x180003ee7  push    rbp
0x180003ee9  sub     rsp, 20h
0x180003eed  mov     rbp, rdx
0x180003ef0  mov     rax, [rcx]
0x180003ef3  mov     edx, [rax]
0x180003ef5  mov     [rbp+0B0h], rcx
0x180003efc  mov     [rbp+38h], edx
0x180003eff  mov     eax, [rbp+38h]
0x180003f02  cmp     eax, 0E06D7363h
0x180003f07  jnz     short loc_180003F1D
0x180003f09  mov     rdx, [rbp+0B0h]
0x180003f10  mov     ecx, [rbp+38h]
0x180003f13  call    _XcptFilter_0
0x180003f18  mov     [rbp+40h], eax
0x180003f1b  jmp     short loc_180003F24
0x180003f1d  mov     dword ptr [rbp+40h], 0
0x180003f24  mov     eax, [rbp+40h]
0x180003f27  add     rsp, 20h
0x180003f2b  pop     rbp
0x180003f2c  retn
0x180003f2e  push    rbp
0x180003f30  sub     rsp, 20h
0x180003f34  mov     rbp, rdx
0x180003f37  mov     rax, [rcx]
0x180003f3a  mov     edx, [rax]
0x180003f3c  mov     [rbp+0B8h], rcx
0x180003f43  mov     [rbp+48h], edx
0x180003f46  mov     eax, [rbp+48h]
0x180003f49  cmp     eax, 0E06D7363h
0x180003f4e  jnz     short loc_180003F64
0x180003f50  mov     rdx, [rbp+0B8h]
0x180003f57  mov     ecx, [rbp+48h]
0x180003f5a  call    _XcptFilter_0
0x180003f5f  mov     [rbp+50h], eax
0x180003f62  jmp     short loc_180003F6B
0x180003f64  mov     dword ptr [rbp+50h], 0
0x180003f6b  mov     eax, [rbp+50h]
0x180003f6e  add     rsp, 20h
0x180003f72  pop     rbp
0x180003f73  retn
0x180003f75  push    rbp
0x180003f77  sub     rsp, 20h
0x180003f7b  mov     rbp, rdx
0x180003f7e  mov     rax, [rcx]
0x180003f81  mov     edx, [rax]
0x180003f83  mov     [rbp+0C0h], rcx
0x180003f8a  mov     [rbp+58h], edx
0x180003f8d  mov     eax, [rbp+58h]
0x180003f90  cmp     eax, 0E06D7363h
0x180003f95  jnz     short loc_180003FAB
0x180003f97  mov     rdx, [rbp+0C0h]
0x180003f9e  mov     ecx, [rbp+58h]
0x180003fa1  call    _XcptFilter_0
0x180003fa6  mov     [rbp+60h], eax
0x180003fa9  jmp     short loc_180003FB2
0x180003fab  mov     dword ptr [rbp+60h], 0
0x180003fb2  mov     eax, [rbp+60h]
0x180003fb5  add     rsp, 20h
0x180003fb9  pop     rbp
0x180003fba  retn
0x180003fbc  push    rbp
0x180003fbe  sub     rsp, 20h
0x180003fc2  mov     rbp, rdx
0x180003fc5  mov     rax, [rcx]
0x180003fc8  mov     edx, [rax]
0x180003fca  mov     [rbp+0C8h], rcx
0x180003fd1  mov     [rbp+68h], edx
0x180003fd4  mov     eax, [rbp+68h]
0x180003fd7  cmp     eax, 0E06D7363h
0x180003fdc  jnz     short loc_180003FF2
0x180003fde  mov     rdx, [rbp+0C8h]
0x180003fe5  mov     ecx, [rbp+68h]
0x180003fe8  call    _XcptFilter_0
0x180003fed  mov     [rbp+70h], eax
0x180003ff0  jmp     short loc_180003FF9
0x180003ff2  mov     dword ptr [rbp+70h], 0
0x180003ff9  mov     eax, [rbp+70h]
0x180003ffc  add     rsp, 20h
0x180004000  pop     rbp
0x180004001  retn
0x180004003  push    rbp
0x180004005  sub     rsp, 20h
0x180004009  mov     rbp, rdx
0x18000400c  mov     rax, [rcx]
0x18000400f  mov     edx, [rax]
0x180004011  mov     [rbp+0D0h], rcx
0x180004018  mov     [rbp+78h], edx
0x18000401b  mov     eax, [rbp+78h]
0x18000401e  cmp     eax, 0E06D7363h
0x180004023  jnz     short loc_18000403C
0x180004025  mov     rdx, [rbp+0D0h]
0x18000402c  mov     ecx, [rbp+78h]
0x18000402f  call    _XcptFilter_0
0x180004034  mov     [rbp+80h], eax
0x18000403a  jmp     short loc_180004046
0x18000403c  mov     dword ptr [rbp+80h], 0
0x180004046  mov     eax, [rbp+80h]
0x18000404c  add     rsp, 20h
0x180004050  pop     rbp
0x180004051  retn
0x180004053  push    rbp
0x180004055  sub     rsp, 20h
0x180004059  mov     rbp, rdx
0x18000405c  mov     rax, [rcx]
0x18000405f  mov     edx, [rax]
0x180004061  mov     [rbp+0D8h], rcx
0x180004068  mov     [rbp+88h], edx
0x18000406e  mov     eax, [rbp+88h]
0x180004074  cmp     eax, 0E06D7363h
0x180004079  jnz     short loc_180004095
0x18000407b  mov     rdx, [rbp+0D8h]
0x180004082  mov     ecx, [rbp+88h]
0x180004088  call    _XcptFilter_0
0x18000408d  mov     [rbp+90h], eax
0x180004093  jmp     short loc_18000409F
0x180004095  mov     dword ptr [rbp+90h], 0
0x18000409f  mov     eax, [rbp+90h]
0x1800040a5  add     rsp, 20h
0x1800040a9  pop     rbp
0x1800040aa  retn
0x1800040ac  push    rbp
0x1800040ae  sub     rsp, 20h
0x1800040b2  mov     rbp, rdx
0x1800040b5  mov     rax, [rcx]
0x1800040b8  mov     edx, [rax]
0x1800040ba  mov     [rbp+0E0h], rcx
0x1800040c1  mov     [rbp+98h], edx
0x1800040c7  mov     eax, [rbp+98h]
0x1800040cd  cmp     eax, 0E06D7363h
0x1800040d2  jnz     short loc_1800040EE
0x1800040d4  mov     rdx, [rbp+0E0h]
0x1800040db  mov     ecx, [rbp+98h]
0x1800040e1  call    _XcptFilter_0
0x1800040e6  mov     [rbp+0A0h], eax
0x1800040ec  jmp     short loc_1800040F8
0x1800040ee  mov     dword ptr [rbp+0A0h], 0
0x1800040f8  mov     eax, [rbp+0A0h]
0x1800040fe  add     rsp, 20h
0x180004102  pop     rbp
0x180004103  retn
0x180004105  push    rbp
0x180004107  sub     rsp, 20h
0x18000410b  mov     rbp, rdx
0x18000410e  cmp     dword ptr [rbp+118h], 1
0x180004115  ja      short loc_180004121
0x180004117  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
