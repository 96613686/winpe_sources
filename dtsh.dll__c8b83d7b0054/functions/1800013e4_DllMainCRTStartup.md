# __DllMainCRTStartup

- ea: `0x1800013e4`
- end: `0x1800015f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800013a0`

## callees

- `0x180001170`
- `0x1800013e4`
- `0x1800016f9`
- `0x180004478`
- `0x180004960`

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
  if ( (_DWORD)fdwReason || dword_180009180 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180009184 = 1;
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
            if ( dword_180009184 )
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
0x1800013e4  mov     [rsp+lpvReserved], r8
0x1800013e9  mov     [rsp+arg_8], edx
0x1800013ed  mov     [rsp+arg_0], rcx
0x1800013f2  push    rbx
0x1800013f3  push    rsi
0x1800013f4  push    rdi
0x1800013f5  sub     rsp, 0F0h
0x1800013fc  mov     edi, edx
0x1800013fe  mov     rsi, rcx
0x180001401  mov     ebx, 1
0x180001406  cmp     edx, ebx
0x180001408  ja      short loc_180001410
0x18000140a  mov     cs:__native_dllmain_reason, edx
0x180001410  test    edx, edx
0x180001412  jnz     short loc_180001427
0x180001414  cmp     cs:dword_180009180, edx
0x18000141a  jnz     short loc_180001427
0x18000141c  xor     ebx, ebx
0x18000141e  mov     [rsp+108h+var_E8], ebx
0x180001422  jmp     loc_1800015D4
0x180001427  lea     eax, [rdx-1]
0x18000142a  cmp     eax, 1
0x18000142d  ja      loc_1800014B4
0x180001433  mov     rax, cs:_pRawDllMain
0x18000143a  test    rax, rax
0x18000143d  jz      short loc_180001475
0x18000143f  cmp     edx, 1
0x180001442  jnz     short loc_18000144A
0x180001444  mov     cs:dword_180009184, edx
0x18000144a  mov     r8, [rsp+108h+lpvReserved]
0x180001452  call    cs:__guard_dispatch_icall_fptr
0x180001458  mov     ebx, eax
0x18000145a  mov     [rsp+108h+var_E8], eax
0x18000145e  jmp     short loc_180001475
0x180001460  xor     ebx, ebx
0x180001462  mov     [rsp+108h+var_E8], ebx
0x180001466  mov     edi, [rsp+108h+arg_8]
0x18000146d  mov     rsi, [rsp+108h+arg_0]
0x180001475  test    ebx, ebx
0x180001477  jz      loc_1800015D4
0x18000147d  mov     r8, [rsp+108h+lpvReserved]
0x180001485  mov     edx, edi
0x180001487  mov     rcx, rsi
0x18000148a  call    _CRT_INIT
0x18000148f  mov     ebx, eax
0x180001491  mov     [rsp+108h+var_E8], eax
0x180001495  jmp     short loc_1800014AC
0x180001497  xor     ebx, ebx
0x180001499  mov     [rsp+108h+var_E8], ebx
0x18000149d  mov     edi, [rsp+108h+arg_8]
0x1800014a4  mov     rsi, [rsp+108h+arg_0]
0x1800014ac  test    ebx, ebx
0x1800014ae  jz      loc_1800015D4
0x1800014b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800014bc  mov     edx, edi; fdwReason
0x1800014be  mov     rcx, rsi; hinstDLL
0x1800014c1  call    DllMain
0x1800014c6  mov     ebx, eax
0x1800014c8  mov     [rsp+108h+var_E8], eax
0x1800014cc  jmp     short loc_1800014E3
0x1800014ce  xor     ebx, ebx
0x1800014d0  mov     [rsp+108h+var_E8], ebx
0x1800014d4  mov     edi, [rsp+108h+arg_8]
0x1800014db  mov     rsi, [rsp+108h+arg_0]
0x1800014e3  cmp     edi, 1
0x1800014e6  jnz     short loc_18000155F
0x1800014e8  test    ebx, ebx
0x1800014ea  jnz     short loc_18000155F
0x1800014ec  xor     r8d, r8d; lpvReserved
0x1800014ef  xor     edx, edx; fdwReason
0x1800014f1  mov     rcx, rsi; hinstDLL
0x1800014f4  call    DllMain
0x1800014f9  jmp     short loc_18000150E
0x1800014fb  mov     edi, [rsp+108h+arg_8]
0x180001502  mov     rsi, [rsp+108h+arg_0]
0x18000150a  mov     ebx, [rsp+108h+var_E8]
0x18000150e  xor     r8d, r8d
0x180001511  xor     edx, edx
0x180001513  mov     rcx, rsi
0x180001516  call    _CRT_INIT
0x18000151b  jmp     short loc_180001530
0x18000151d  mov     edi, [rsp+108h+arg_8]
0x180001524  mov     rsi, [rsp+108h+arg_0]
0x18000152c  mov     ebx, [rsp+108h+var_E8]
0x180001530  mov     rax, cs:_pRawDllMain
0x180001537  test    rax, rax
0x18000153a  jz      short loc_18000155F
0x18000153c  xor     r8d, r8d
0x18000153f  xor     edx, edx
0x180001541  mov     rcx, rsi
0x180001544  call    cs:__guard_dispatch_icall_fptr
0x18000154a  jmp     short loc_18000155F
0x18000154c  mov     edi, [rsp+108h+arg_8]
0x180001553  mov     rsi, [rsp+108h+arg_0]
0x18000155b  mov     ebx, [rsp+108h+var_E8]
0x18000155f  test    edi, edi
0x180001561  jz      short loc_180001568
0x180001563  cmp     edi, 3
0x180001566  jnz     short loc_1800015D4
0x180001568  mov     r8, [rsp+108h+lpvReserved]
0x180001570  mov     edx, edi
0x180001572  mov     rcx, rsi
0x180001575  call    _CRT_INIT
0x18000157a  mov     ebx, eax
0x18000157c  mov     [rsp+108h+var_E8], eax
0x180001580  jmp     short loc_180001597
0x180001582  xor     ebx, ebx
0x180001584  mov     [rsp+108h+var_E8], ebx
0x180001588  mov     edi, [rsp+108h+arg_8]
0x18000158f  mov     rsi, [rsp+108h+arg_0]
0x180001597  mov     rax, cs:_pRawDllMain
0x18000159e  test    rax, rax
0x1800015a1  jz      short loc_1800015D4
0x1800015a3  cmp     cs:dword_180009184, 0
0x1800015aa  jz      short loc_1800015D4
0x1800015ac  mov     r8, [rsp+108h+lpvReserved]
0x1800015b4  mov     edx, edi
0x1800015b6  mov     rcx, rsi
0x1800015b9  call    cs:__guard_dispatch_icall_fptr
0x1800015bf  mov     ebx, eax
0x1800015c1  mov     [rsp+108h+var_E8], eax
0x1800015c5  jmp     short loc_1800015D4
0x1800015c7  xor     ebx, ebx
0x1800015c9  mov     [rsp+108h+var_E8], ebx
0x1800015cd  mov     edi, [rsp+108h+arg_8]
0x1800015d4  cmp     edi, 1
0x1800015d7  ja      short loc_1800015E3
0x1800015d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015e3  mov     eax, ebx
0x1800015e5  add     rsp, 0F0h
0x1800015ec  pop     rdi
0x1800015ed  pop     rsi
0x1800015ee  pop     rbx
0x1800015ef  retn
0x1800049d0  push    rbp
0x1800049d2  sub     rsp, 20h
0x1800049d6  mov     rbp, rdx
0x1800049d9  mov     rax, [rcx]
0x1800049dc  mov     edx, [rax]
0x1800049de  mov     [rbp+0A8h], rcx
0x1800049e5  mov     [rbp+28h], edx
0x1800049e8  mov     eax, [rbp+28h]
0x1800049eb  cmp     eax, 0E06D7363h
0x1800049f0  jnz     short loc_180004A06
0x1800049f2  mov     rdx, [rbp+0A8h]
0x1800049f9  mov     ecx, [rbp+28h]
0x1800049fc  call    _XcptFilter_0
0x180004a01  mov     [rbp+30h], eax
0x180004a04  jmp     short loc_180004A0D
0x180004a06  mov     dword ptr [rbp+30h], 0
0x180004a0d  mov     eax, [rbp+30h]
0x180004a10  add     rsp, 20h
0x180004a14  pop     rbp
0x180004a15  retn
0x180004a17  push    rbp
0x180004a19  sub     rsp, 20h
0x180004a1d  mov     rbp, rdx
0x180004a20  mov     rax, [rcx]
0x180004a23  mov     edx, [rax]
0x180004a25  mov     [rbp+0B0h], rcx
0x180004a2c  mov     [rbp+38h], edx
0x180004a2f  mov     eax, [rbp+38h]
0x180004a32  cmp     eax, 0E06D7363h
0x180004a37  jnz     short loc_180004A4D
0x180004a39  mov     rdx, [rbp+0B0h]
0x180004a40  mov     ecx, [rbp+38h]
0x180004a43  call    _XcptFilter_0
0x180004a48  mov     [rbp+40h], eax
0x180004a4b  jmp     short loc_180004A54
0x180004a4d  mov     dword ptr [rbp+40h], 0
0x180004a54  mov     eax, [rbp+40h]
0x180004a57  add     rsp, 20h
0x180004a5b  pop     rbp
0x180004a5c  retn
0x180004a5e  push    rbp
0x180004a60  sub     rsp, 20h
0x180004a64  mov     rbp, rdx
0x180004a67  mov     rax, [rcx]
0x180004a6a  mov     edx, [rax]
0x180004a6c  mov     [rbp+0B8h], rcx
0x180004a73  mov     [rbp+48h], edx
0x180004a76  mov     eax, [rbp+48h]
0x180004a79  cmp     eax, 0E06D7363h
0x180004a7e  jnz     short loc_180004A94
0x180004a80  mov     rdx, [rbp+0B8h]
0x180004a87  mov     ecx, [rbp+48h]
0x180004a8a  call    _XcptFilter_0
0x180004a8f  mov     [rbp+50h], eax
0x180004a92  jmp     short loc_180004A9B
0x180004a94  mov     dword ptr [rbp+50h], 0
0x180004a9b  mov     eax, [rbp+50h]
0x180004a9e  add     rsp, 20h
0x180004aa2  pop     rbp
0x180004aa3  retn
0x180004aa5  push    rbp
0x180004aa7  sub     rsp, 20h
0x180004aab  mov     rbp, rdx
0x180004aae  mov     rax, [rcx]
0x180004ab1  mov     edx, [rax]
0x180004ab3  mov     [rbp+0C0h], rcx
0x180004aba  mov     [rbp+58h], edx
0x180004abd  mov     eax, [rbp+58h]
0x180004ac0  cmp     eax, 0E06D7363h
0x180004ac5  jnz     short loc_180004ADB
0x180004ac7  mov     rdx, [rbp+0C0h]
0x180004ace  mov     ecx, [rbp+58h]
0x180004ad1  call    _XcptFilter_0
0x180004ad6  mov     [rbp+60h], eax
0x180004ad9  jmp     short loc_180004AE2
0x180004adb  mov     dword ptr [rbp+60h], 0
0x180004ae2  mov     eax, [rbp+60h]
0x180004ae5  add     rsp, 20h
0x180004ae9  pop     rbp
0x180004aea  retn
0x180004aec  push    rbp
0x180004aee  sub     rsp, 20h
0x180004af2  mov     rbp, rdx
0x180004af5  mov     rax, [rcx]
0x180004af8  mov     edx, [rax]
0x180004afa  mov     [rbp+0C8h], rcx
0x180004b01  mov     [rbp+68h], edx
0x180004b04  mov     eax, [rbp+68h]
0x180004b07  cmp     eax, 0E06D7363h
0x180004b0c  jnz     short loc_180004B22
0x180004b0e  mov     rdx, [rbp+0C8h]
0x180004b15  mov     ecx, [rbp+68h]
0x180004b18  call    _XcptFilter_0
0x180004b1d  mov     [rbp+70h], eax
0x180004b20  jmp     short loc_180004B29
0x180004b22  mov     dword ptr [rbp+70h], 0
0x180004b29  mov     eax, [rbp+70h]
0x180004b2c  add     rsp, 20h
0x180004b30  pop     rbp
0x180004b31  retn
0x180004b33  push    rbp
0x180004b35  sub     rsp, 20h
0x180004b39  mov     rbp, rdx
0x180004b3c  mov     rax, [rcx]
0x180004b3f  mov     edx, [rax]
0x180004b41  mov     [rbp+0D0h], rcx
0x180004b48  mov     [rbp+78h], edx
0x180004b4b  mov     eax, [rbp+78h]
0x180004b4e  cmp     eax, 0E06D7363h
0x180004b53  jnz     short loc_180004B6C
0x180004b55  mov     rdx, [rbp+0D0h]
0x180004b5c  mov     ecx, [rbp+78h]
0x180004b5f  call    _XcptFilter_0
0x180004b64  mov     [rbp+80h], eax
0x180004b6a  jmp     short loc_180004B76
0x180004b6c  mov     dword ptr [rbp+80h], 0
0x180004b76  mov     eax, [rbp+80h]
0x180004b7c  add     rsp, 20h
0x180004b80  pop     rbp
0x180004b81  retn
0x180004b83  push    rbp
0x180004b85  sub     rsp, 20h
0x180004b89  mov     rbp, rdx
0x180004b8c  mov     rax, [rcx]
0x180004b8f  mov     edx, [rax]
0x180004b91  mov     [rbp+0D8h], rcx
0x180004b98  mov     [rbp+88h], edx
0x180004b9e  mov     eax, [rbp+88h]
0x180004ba4  cmp     eax, 0E06D7363h
0x180004ba9  jnz     short loc_180004BC5
0x180004bab  mov     rdx, [rbp+0D8h]
0x180004bb2  mov     ecx, [rbp+88h]
0x180004bb8  call    _XcptFilter_0
0x180004bbd  mov     [rbp+90h], eax
0x180004bc3  jmp     short loc_180004BCF
0x180004bc5  mov     dword ptr [rbp+90h], 0
0x180004bcf  mov     eax, [rbp+90h]
0x180004bd5  add     rsp, 20h
0x180004bd9  pop     rbp
0x180004bda  retn
0x180004bdc  push    rbp
0x180004bde  sub     rsp, 20h
0x180004be2  mov     rbp, rdx
0x180004be5  mov     rax, [rcx]
0x180004be8  mov     edx, [rax]
0x180004bea  mov     [rbp+0E0h], rcx
0x180004bf1  mov     [rbp+98h], edx
0x180004bf7  mov     eax, [rbp+98h]
0x180004bfd  cmp     eax, 0E06D7363h
0x180004c02  jnz     short loc_180004C1E
0x180004c04  mov     rdx, [rbp+0E0h]
0x180004c0b  mov     ecx, [rbp+98h]
0x180004c11  call    _XcptFilter_0
0x180004c16  mov     [rbp+0A0h], eax
0x180004c1c  jmp     short loc_180004C28
0x180004c1e  mov     dword ptr [rbp+0A0h], 0
0x180004c28  mov     eax, [rbp+0A0h]
0x180004c2e  add     rsp, 20h
0x180004c32  pop     rbp
0x180004c33  retn
0x180004c35  push    rbp
0x180004c37  sub     rsp, 20h
0x180004c3b  mov     rbp, rdx
0x180004c3e  cmp     dword ptr [rbp+118h], 1
0x180004c45  ja      short loc_180004C51
0x180004c47  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
