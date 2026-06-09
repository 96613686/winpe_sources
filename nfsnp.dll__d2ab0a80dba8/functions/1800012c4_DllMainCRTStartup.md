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
- `0x180011be0`

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
  if ( (_DWORD)fdwReason || dword_180018140 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180018144 = 1;
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
            if ( dword_180018144 )
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
0x1800012f4  cmp     cs:dword_180018140, edx
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
0x180001324  mov     cs:dword_180018144, edx
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
0x180001483  cmp     cs:dword_180018144, 0
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
0x180011c83  push    rbp
0x180011c85  sub     rsp, 20h
0x180011c89  mov     rbp, rdx
0x180011c8c  mov     rax, [rcx]
0x180011c8f  mov     edx, [rax]
0x180011c91  mov     [rbp+0A8h], rcx
0x180011c98  mov     [rbp+28h], edx
0x180011c9b  mov     eax, [rbp+28h]
0x180011c9e  cmp     eax, 0E06D7363h
0x180011ca3  jnz     short loc_180011CB9
0x180011ca5  mov     rdx, [rbp+0A8h]
0x180011cac  mov     ecx, [rbp+28h]
0x180011caf  call    _XcptFilter_0
0x180011cb4  mov     [rbp+30h], eax
0x180011cb7  jmp     short loc_180011CC0
0x180011cb9  mov     dword ptr [rbp+30h], 0
0x180011cc0  mov     eax, [rbp+30h]
0x180011cc3  add     rsp, 20h
0x180011cc7  pop     rbp
0x180011cc8  retn
0x180011cca  push    rbp
0x180011ccc  sub     rsp, 20h
0x180011cd0  mov     rbp, rdx
0x180011cd3  mov     rax, [rcx]
0x180011cd6  mov     edx, [rax]
0x180011cd8  mov     [rbp+0B0h], rcx
0x180011cdf  mov     [rbp+38h], edx
0x180011ce2  mov     eax, [rbp+38h]
0x180011ce5  cmp     eax, 0E06D7363h
0x180011cea  jnz     short loc_180011D00
0x180011cec  mov     rdx, [rbp+0B0h]
0x180011cf3  mov     ecx, [rbp+38h]
0x180011cf6  call    _XcptFilter_0
0x180011cfb  mov     [rbp+40h], eax
0x180011cfe  jmp     short loc_180011D07
0x180011d00  mov     dword ptr [rbp+40h], 0
0x180011d07  mov     eax, [rbp+40h]
0x180011d0a  add     rsp, 20h
0x180011d0e  pop     rbp
0x180011d0f  retn
0x180011d11  push    rbp
0x180011d13  sub     rsp, 20h
0x180011d17  mov     rbp, rdx
0x180011d1a  mov     rax, [rcx]
0x180011d1d  mov     edx, [rax]
0x180011d1f  mov     [rbp+0B8h], rcx
0x180011d26  mov     [rbp+48h], edx
0x180011d29  mov     eax, [rbp+48h]
0x180011d2c  cmp     eax, 0E06D7363h
0x180011d31  jnz     short loc_180011D47
0x180011d33  mov     rdx, [rbp+0B8h]
0x180011d3a  mov     ecx, [rbp+48h]
0x180011d3d  call    _XcptFilter_0
0x180011d42  mov     [rbp+50h], eax
0x180011d45  jmp     short loc_180011D4E
0x180011d47  mov     dword ptr [rbp+50h], 0
0x180011d4e  mov     eax, [rbp+50h]
0x180011d51  add     rsp, 20h
0x180011d55  pop     rbp
0x180011d56  retn
0x180011d58  push    rbp
0x180011d5a  sub     rsp, 20h
0x180011d5e  mov     rbp, rdx
0x180011d61  mov     rax, [rcx]
0x180011d64  mov     edx, [rax]
0x180011d66  mov     [rbp+0C0h], rcx
0x180011d6d  mov     [rbp+58h], edx
0x180011d70  mov     eax, [rbp+58h]
0x180011d73  cmp     eax, 0E06D7363h
0x180011d78  jnz     short loc_180011D8E
0x180011d7a  mov     rdx, [rbp+0C0h]
0x180011d81  mov     ecx, [rbp+58h]
0x180011d84  call    _XcptFilter_0
0x180011d89  mov     [rbp+60h], eax
0x180011d8c  jmp     short loc_180011D95
0x180011d8e  mov     dword ptr [rbp+60h], 0
0x180011d95  mov     eax, [rbp+60h]
0x180011d98  add     rsp, 20h
0x180011d9c  pop     rbp
0x180011d9d  retn
0x180011d9f  push    rbp
0x180011da1  sub     rsp, 20h
0x180011da5  mov     rbp, rdx
0x180011da8  mov     rax, [rcx]
0x180011dab  mov     edx, [rax]
0x180011dad  mov     [rbp+0C8h], rcx
0x180011db4  mov     [rbp+68h], edx
0x180011db7  mov     eax, [rbp+68h]
0x180011dba  cmp     eax, 0E06D7363h
0x180011dbf  jnz     short loc_180011DD5
0x180011dc1  mov     rdx, [rbp+0C8h]
0x180011dc8  mov     ecx, [rbp+68h]
0x180011dcb  call    _XcptFilter_0
0x180011dd0  mov     [rbp+70h], eax
0x180011dd3  jmp     short loc_180011DDC
0x180011dd5  mov     dword ptr [rbp+70h], 0
0x180011ddc  mov     eax, [rbp+70h]
0x180011ddf  add     rsp, 20h
0x180011de3  pop     rbp
0x180011de4  retn
0x180011de6  push    rbp
0x180011de8  sub     rsp, 20h
0x180011dec  mov     rbp, rdx
0x180011def  mov     rax, [rcx]
0x180011df2  mov     edx, [rax]
0x180011df4  mov     [rbp+0D0h], rcx
0x180011dfb  mov     [rbp+78h], edx
0x180011dfe  mov     eax, [rbp+78h]
0x180011e01  cmp     eax, 0E06D7363h
0x180011e06  jnz     short loc_180011E1F
0x180011e08  mov     rdx, [rbp+0D0h]
0x180011e0f  mov     ecx, [rbp+78h]
0x180011e12  call    _XcptFilter_0
0x180011e17  mov     [rbp+80h], eax
0x180011e1d  jmp     short loc_180011E29
0x180011e1f  mov     dword ptr [rbp+80h], 0
0x180011e29  mov     eax, [rbp+80h]
0x180011e2f  add     rsp, 20h
0x180011e33  pop     rbp
0x180011e34  retn
0x180011e36  push    rbp
0x180011e38  sub     rsp, 20h
0x180011e3c  mov     rbp, rdx
0x180011e3f  mov     rax, [rcx]
0x180011e42  mov     edx, [rax]
0x180011e44  mov     [rbp+0D8h], rcx
0x180011e4b  mov     [rbp+88h], edx
0x180011e51  mov     eax, [rbp+88h]
0x180011e57  cmp     eax, 0E06D7363h
0x180011e5c  jnz     short loc_180011E78
0x180011e5e  mov     rdx, [rbp+0D8h]
0x180011e65  mov     ecx, [rbp+88h]
0x180011e6b  call    _XcptFilter_0
0x180011e70  mov     [rbp+90h], eax
0x180011e76  jmp     short loc_180011E82
0x180011e78  mov     dword ptr [rbp+90h], 0
0x180011e82  mov     eax, [rbp+90h]
0x180011e88  add     rsp, 20h
0x180011e8c  pop     rbp
0x180011e8d  retn
0x180011e8f  push    rbp
0x180011e91  sub     rsp, 20h
0x180011e95  mov     rbp, rdx
0x180011e98  mov     rax, [rcx]
0x180011e9b  mov     edx, [rax]
0x180011e9d  mov     [rbp+0E0h], rcx
0x180011ea4  mov     [rbp+98h], edx
0x180011eaa  mov     eax, [rbp+98h]
0x180011eb0  cmp     eax, 0E06D7363h
0x180011eb5  jnz     short loc_180011ED1
0x180011eb7  mov     rdx, [rbp+0E0h]
0x180011ebe  mov     ecx, [rbp+98h]
0x180011ec4  call    _XcptFilter_0
0x180011ec9  mov     [rbp+0A0h], eax
0x180011ecf  jmp     short loc_180011EDB
0x180011ed1  mov     dword ptr [rbp+0A0h], 0
0x180011edb  mov     eax, [rbp+0A0h]
0x180011ee1  add     rsp, 20h
0x180011ee5  pop     rbp
0x180011ee6  retn
0x180011ee8  push    rbp
0x180011eea  sub     rsp, 20h
0x180011eee  mov     rbp, rdx
0x180011ef1  cmp     dword ptr [rbp+118h], 1
0x180011ef8  ja      short loc_180011F04
0x180011efa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
