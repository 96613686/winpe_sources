# __DllMainCRTStartup

- ea: `0x180001c74`
- end: `0x180001e80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001c30`

## callees

- `0x180001a00`
- `0x180001c74`
- `0x180002026`
- `0x180002b4c`
- `0x1800083e0`

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
  if ( (_DWORD)fdwReason || dword_18000E1CC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000E1D0 = 1;
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
            if ( dword_18000E1D0 )
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
0x180001c74  mov     [rsp+lpvReserved], r8
0x180001c79  mov     [rsp+arg_8], edx
0x180001c7d  mov     [rsp+arg_0], rcx
0x180001c82  push    rbx
0x180001c83  push    rsi
0x180001c84  push    rdi
0x180001c85  sub     rsp, 0F0h
0x180001c8c  mov     edi, edx
0x180001c8e  mov     rsi, rcx
0x180001c91  mov     ebx, 1
0x180001c96  cmp     edx, ebx
0x180001c98  ja      short loc_180001CA0
0x180001c9a  mov     cs:__native_dllmain_reason, edx
0x180001ca0  test    edx, edx
0x180001ca2  jnz     short loc_180001CB7
0x180001ca4  cmp     cs:dword_18000E1CC, edx
0x180001caa  jnz     short loc_180001CB7
0x180001cac  xor     ebx, ebx
0x180001cae  mov     [rsp+108h+var_E8], ebx
0x180001cb2  jmp     loc_180001E64
0x180001cb7  lea     eax, [rdx-1]
0x180001cba  cmp     eax, 1
0x180001cbd  ja      loc_180001D44
0x180001cc3  mov     rax, cs:_pRawDllMain
0x180001cca  test    rax, rax
0x180001ccd  jz      short loc_180001D05
0x180001ccf  cmp     edx, 1
0x180001cd2  jnz     short loc_180001CDA
0x180001cd4  mov     cs:dword_18000E1D0, edx
0x180001cda  mov     r8, [rsp+108h+lpvReserved]
0x180001ce2  call    cs:__guard_dispatch_icall_fptr
0x180001ce8  mov     ebx, eax
0x180001cea  mov     [rsp+108h+var_E8], eax
0x180001cee  jmp     short loc_180001D05
0x180001cf0  xor     ebx, ebx
0x180001cf2  mov     [rsp+108h+var_E8], ebx
0x180001cf6  mov     edi, [rsp+108h+arg_8]
0x180001cfd  mov     rsi, [rsp+108h+arg_0]
0x180001d05  test    ebx, ebx
0x180001d07  jz      loc_180001E64
0x180001d0d  mov     r8, [rsp+108h+lpvReserved]
0x180001d15  mov     edx, edi
0x180001d17  mov     rcx, rsi
0x180001d1a  call    _CRT_INIT
0x180001d1f  mov     ebx, eax
0x180001d21  mov     [rsp+108h+var_E8], eax
0x180001d25  jmp     short loc_180001D3C
0x180001d27  xor     ebx, ebx
0x180001d29  mov     [rsp+108h+var_E8], ebx
0x180001d2d  mov     edi, [rsp+108h+arg_8]
0x180001d34  mov     rsi, [rsp+108h+arg_0]
0x180001d3c  test    ebx, ebx
0x180001d3e  jz      loc_180001E64
0x180001d44  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001d4c  mov     edx, edi; fdwReason
0x180001d4e  mov     rcx, rsi; hinstDLL
0x180001d51  call    DllMain
0x180001d56  mov     ebx, eax
0x180001d58  mov     [rsp+108h+var_E8], eax
0x180001d5c  jmp     short loc_180001D73
0x180001d5e  xor     ebx, ebx
0x180001d60  mov     [rsp+108h+var_E8], ebx
0x180001d64  mov     edi, [rsp+108h+arg_8]
0x180001d6b  mov     rsi, [rsp+108h+arg_0]
0x180001d73  cmp     edi, 1
0x180001d76  jnz     short loc_180001DEF
0x180001d78  test    ebx, ebx
0x180001d7a  jnz     short loc_180001DEF
0x180001d7c  xor     r8d, r8d; lpvReserved
0x180001d7f  xor     edx, edx; fdwReason
0x180001d81  mov     rcx, rsi; hinstDLL
0x180001d84  call    DllMain
0x180001d89  jmp     short loc_180001D9E
0x180001d8b  mov     edi, [rsp+108h+arg_8]
0x180001d92  mov     rsi, [rsp+108h+arg_0]
0x180001d9a  mov     ebx, [rsp+108h+var_E8]
0x180001d9e  xor     r8d, r8d
0x180001da1  xor     edx, edx
0x180001da3  mov     rcx, rsi
0x180001da6  call    _CRT_INIT
0x180001dab  jmp     short loc_180001DC0
0x180001dad  mov     edi, [rsp+108h+arg_8]
0x180001db4  mov     rsi, [rsp+108h+arg_0]
0x180001dbc  mov     ebx, [rsp+108h+var_E8]
0x180001dc0  mov     rax, cs:_pRawDllMain
0x180001dc7  test    rax, rax
0x180001dca  jz      short loc_180001DEF
0x180001dcc  xor     r8d, r8d
0x180001dcf  xor     edx, edx
0x180001dd1  mov     rcx, rsi
0x180001dd4  call    cs:__guard_dispatch_icall_fptr
0x180001dda  jmp     short loc_180001DEF
0x180001ddc  mov     edi, [rsp+108h+arg_8]
0x180001de3  mov     rsi, [rsp+108h+arg_0]
0x180001deb  mov     ebx, [rsp+108h+var_E8]
0x180001def  test    edi, edi
0x180001df1  jz      short loc_180001DF8
0x180001df3  cmp     edi, 3
0x180001df6  jnz     short loc_180001E64
0x180001df8  mov     r8, [rsp+108h+lpvReserved]
0x180001e00  mov     edx, edi
0x180001e02  mov     rcx, rsi
0x180001e05  call    _CRT_INIT
0x180001e0a  mov     ebx, eax
0x180001e0c  mov     [rsp+108h+var_E8], eax
0x180001e10  jmp     short loc_180001E27
0x180001e12  xor     ebx, ebx
0x180001e14  mov     [rsp+108h+var_E8], ebx
0x180001e18  mov     edi, [rsp+108h+arg_8]
0x180001e1f  mov     rsi, [rsp+108h+arg_0]
0x180001e27  mov     rax, cs:_pRawDllMain
0x180001e2e  test    rax, rax
0x180001e31  jz      short loc_180001E64
0x180001e33  cmp     cs:dword_18000E1D0, 0
0x180001e3a  jz      short loc_180001E64
0x180001e3c  mov     r8, [rsp+108h+lpvReserved]
0x180001e44  mov     edx, edi
0x180001e46  mov     rcx, rsi
0x180001e49  call    cs:__guard_dispatch_icall_fptr
0x180001e4f  mov     ebx, eax
0x180001e51  mov     [rsp+108h+var_E8], eax
0x180001e55  jmp     short loc_180001E64
0x180001e57  xor     ebx, ebx
0x180001e59  mov     [rsp+108h+var_E8], ebx
0x180001e5d  mov     edi, [rsp+108h+arg_8]
0x180001e64  cmp     edi, 1
0x180001e67  ja      short loc_180001E73
0x180001e69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001e73  mov     eax, ebx
0x180001e75  add     rsp, 0F0h
0x180001e7c  pop     rdi
0x180001e7d  pop     rsi
0x180001e7e  pop     rbx
0x180001e7f  retn
0x18000848f  push    rbp
0x180008491  sub     rsp, 20h
0x180008495  mov     rbp, rdx
0x180008498  mov     rax, [rcx]
0x18000849b  mov     edx, [rax]
0x18000849d  mov     [rbp+0A8h], rcx
0x1800084a4  mov     [rbp+28h], edx
0x1800084a7  mov     eax, [rbp+28h]
0x1800084aa  cmp     eax, 0E06D7363h
0x1800084af  jnz     short loc_1800084C5
0x1800084b1  mov     rdx, [rbp+0A8h]
0x1800084b8  mov     ecx, [rbp+28h]
0x1800084bb  call    _XcptFilter_0
0x1800084c0  mov     [rbp+30h], eax
0x1800084c3  jmp     short loc_1800084CC
0x1800084c5  mov     dword ptr [rbp+30h], 0
0x1800084cc  mov     eax, [rbp+30h]
0x1800084cf  add     rsp, 20h
0x1800084d3  pop     rbp
0x1800084d4  retn
0x1800084d6  push    rbp
0x1800084d8  sub     rsp, 20h
0x1800084dc  mov     rbp, rdx
0x1800084df  mov     rax, [rcx]
0x1800084e2  mov     edx, [rax]
0x1800084e4  mov     [rbp+0B0h], rcx
0x1800084eb  mov     [rbp+38h], edx
0x1800084ee  mov     eax, [rbp+38h]
0x1800084f1  cmp     eax, 0E06D7363h
0x1800084f6  jnz     short loc_18000850C
0x1800084f8  mov     rdx, [rbp+0B0h]
0x1800084ff  mov     ecx, [rbp+38h]
0x180008502  call    _XcptFilter_0
0x180008507  mov     [rbp+40h], eax
0x18000850a  jmp     short loc_180008513
0x18000850c  mov     dword ptr [rbp+40h], 0
0x180008513  mov     eax, [rbp+40h]
0x180008516  add     rsp, 20h
0x18000851a  pop     rbp
0x18000851b  retn
0x18000851d  push    rbp
0x18000851f  sub     rsp, 20h
0x180008523  mov     rbp, rdx
0x180008526  mov     rax, [rcx]
0x180008529  mov     edx, [rax]
0x18000852b  mov     [rbp+0B8h], rcx
0x180008532  mov     [rbp+48h], edx
0x180008535  mov     eax, [rbp+48h]
0x180008538  cmp     eax, 0E06D7363h
0x18000853d  jnz     short loc_180008553
0x18000853f  mov     rdx, [rbp+0B8h]
0x180008546  mov     ecx, [rbp+48h]
0x180008549  call    _XcptFilter_0
0x18000854e  mov     [rbp+50h], eax
0x180008551  jmp     short loc_18000855A
0x180008553  mov     dword ptr [rbp+50h], 0
0x18000855a  mov     eax, [rbp+50h]
0x18000855d  add     rsp, 20h
0x180008561  pop     rbp
0x180008562  retn
0x180008564  push    rbp
0x180008566  sub     rsp, 20h
0x18000856a  mov     rbp, rdx
0x18000856d  mov     rax, [rcx]
0x180008570  mov     edx, [rax]
0x180008572  mov     [rbp+0C0h], rcx
0x180008579  mov     [rbp+58h], edx
0x18000857c  mov     eax, [rbp+58h]
0x18000857f  cmp     eax, 0E06D7363h
0x180008584  jnz     short loc_18000859A
0x180008586  mov     rdx, [rbp+0C0h]
0x18000858d  mov     ecx, [rbp+58h]
0x180008590  call    _XcptFilter_0
0x180008595  mov     [rbp+60h], eax
0x180008598  jmp     short loc_1800085A1
0x18000859a  mov     dword ptr [rbp+60h], 0
0x1800085a1  mov     eax, [rbp+60h]
0x1800085a4  add     rsp, 20h
0x1800085a8  pop     rbp
0x1800085a9  retn
0x1800085ab  push    rbp
0x1800085ad  sub     rsp, 20h
0x1800085b1  mov     rbp, rdx
0x1800085b4  mov     rax, [rcx]
0x1800085b7  mov     edx, [rax]
0x1800085b9  mov     [rbp+0C8h], rcx
0x1800085c0  mov     [rbp+68h], edx
0x1800085c3  mov     eax, [rbp+68h]
0x1800085c6  cmp     eax, 0E06D7363h
0x1800085cb  jnz     short loc_1800085E1
0x1800085cd  mov     rdx, [rbp+0C8h]
0x1800085d4  mov     ecx, [rbp+68h]
0x1800085d7  call    _XcptFilter_0
0x1800085dc  mov     [rbp+70h], eax
0x1800085df  jmp     short loc_1800085E8
0x1800085e1  mov     dword ptr [rbp+70h], 0
0x1800085e8  mov     eax, [rbp+70h]
0x1800085eb  add     rsp, 20h
0x1800085ef  pop     rbp
0x1800085f0  retn
0x1800085f2  push    rbp
0x1800085f4  sub     rsp, 20h
0x1800085f8  mov     rbp, rdx
0x1800085fb  mov     rax, [rcx]
0x1800085fe  mov     edx, [rax]
0x180008600  mov     [rbp+0D0h], rcx
0x180008607  mov     [rbp+78h], edx
0x18000860a  mov     eax, [rbp+78h]
0x18000860d  cmp     eax, 0E06D7363h
0x180008612  jnz     short loc_18000862B
0x180008614  mov     rdx, [rbp+0D0h]
0x18000861b  mov     ecx, [rbp+78h]
0x18000861e  call    _XcptFilter_0
0x180008623  mov     [rbp+80h], eax
0x180008629  jmp     short loc_180008635
0x18000862b  mov     dword ptr [rbp+80h], 0
0x180008635  mov     eax, [rbp+80h]
0x18000863b  add     rsp, 20h
0x18000863f  pop     rbp
0x180008640  retn
0x180008642  push    rbp
0x180008644  sub     rsp, 20h
0x180008648  mov     rbp, rdx
0x18000864b  mov     rax, [rcx]
0x18000864e  mov     edx, [rax]
0x180008650  mov     [rbp+0D8h], rcx
0x180008657  mov     [rbp+88h], edx
0x18000865d  mov     eax, [rbp+88h]
0x180008663  cmp     eax, 0E06D7363h
0x180008668  jnz     short loc_180008684
0x18000866a  mov     rdx, [rbp+0D8h]
0x180008671  mov     ecx, [rbp+88h]
0x180008677  call    _XcptFilter_0
0x18000867c  mov     [rbp+90h], eax
0x180008682  jmp     short loc_18000868E
0x180008684  mov     dword ptr [rbp+90h], 0
0x18000868e  mov     eax, [rbp+90h]
0x180008694  add     rsp, 20h
0x180008698  pop     rbp
0x180008699  retn
0x18000869b  push    rbp
0x18000869d  sub     rsp, 20h
0x1800086a1  mov     rbp, rdx
0x1800086a4  mov     rax, [rcx]
0x1800086a7  mov     edx, [rax]
0x1800086a9  mov     [rbp+0E0h], rcx
0x1800086b0  mov     [rbp+98h], edx
0x1800086b6  mov     eax, [rbp+98h]
0x1800086bc  cmp     eax, 0E06D7363h
0x1800086c1  jnz     short loc_1800086DD
0x1800086c3  mov     rdx, [rbp+0E0h]
0x1800086ca  mov     ecx, [rbp+98h]
0x1800086d0  call    _XcptFilter_0
0x1800086d5  mov     [rbp+0A0h], eax
0x1800086db  jmp     short loc_1800086E7
0x1800086dd  mov     dword ptr [rbp+0A0h], 0
0x1800086e7  mov     eax, [rbp+0A0h]
0x1800086ed  add     rsp, 20h
0x1800086f1  pop     rbp
0x1800086f2  retn
0x1800086f4  push    rbp
0x1800086f6  sub     rsp, 20h
0x1800086fa  mov     rbp, rdx
0x1800086fd  cmp     dword ptr [rbp+118h], 1
0x180008704  ja      short loc_180008710
0x180008706  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
