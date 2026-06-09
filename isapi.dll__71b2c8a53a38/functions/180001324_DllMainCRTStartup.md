# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001530`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800010b0`
- `0x180001324`
- `0x18000174a`
- `0x180001928`
- `0x180012500`

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
  if ( (_DWORD)fdwReason || dword_1800201C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800201C4 = 1;
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
            if ( dword_1800201C4 )
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
0x180001324  mov     [rsp+lpvReserved], r8
0x180001329  mov     [rsp+arg_8], edx
0x18000132d  mov     [rsp+arg_0], rcx
0x180001332  push    rbx
0x180001333  push    rsi
0x180001334  push    rdi
0x180001335  sub     rsp, 0F0h
0x18000133c  mov     edi, edx
0x18000133e  mov     rsi, rcx
0x180001341  mov     ebx, 1
0x180001346  cmp     edx, ebx
0x180001348  ja      short loc_180001350
0x18000134a  mov     cs:__native_dllmain_reason, edx
0x180001350  test    edx, edx
0x180001352  jnz     short loc_180001367
0x180001354  cmp     cs:dword_1800201C0, edx
0x18000135a  jnz     short loc_180001367
0x18000135c  xor     ebx, ebx
0x18000135e  mov     [rsp+108h+var_E8], ebx
0x180001362  jmp     loc_180001514
0x180001367  lea     eax, [rdx-1]
0x18000136a  cmp     eax, 1
0x18000136d  ja      loc_1800013F4
0x180001373  mov     rax, cs:_pRawDllMain
0x18000137a  test    rax, rax
0x18000137d  jz      short loc_1800013B5
0x18000137f  cmp     edx, 1
0x180001382  jnz     short loc_18000138A
0x180001384  mov     cs:dword_1800201C4, edx
0x18000138a  mov     r8, [rsp+108h+lpvReserved]
0x180001392  call    cs:__guard_dispatch_icall_fptr
0x180001398  mov     ebx, eax
0x18000139a  mov     [rsp+108h+var_E8], eax
0x18000139e  jmp     short loc_1800013B5
0x1800013a0  xor     ebx, ebx
0x1800013a2  mov     [rsp+108h+var_E8], ebx
0x1800013a6  mov     edi, [rsp+108h+arg_8]
0x1800013ad  mov     rsi, [rsp+108h+arg_0]
0x1800013b5  test    ebx, ebx
0x1800013b7  jz      loc_180001514
0x1800013bd  mov     r8, [rsp+108h+lpvReserved]
0x1800013c5  mov     edx, edi
0x1800013c7  mov     rcx, rsi
0x1800013ca  call    _CRT_INIT
0x1800013cf  mov     ebx, eax
0x1800013d1  mov     [rsp+108h+var_E8], eax
0x1800013d5  jmp     short loc_1800013EC
0x1800013d7  xor     ebx, ebx
0x1800013d9  mov     [rsp+108h+var_E8], ebx
0x1800013dd  mov     edi, [rsp+108h+arg_8]
0x1800013e4  mov     rsi, [rsp+108h+arg_0]
0x1800013ec  test    ebx, ebx
0x1800013ee  jz      loc_180001514
0x1800013f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013fc  mov     edx, edi; fdwReason
0x1800013fe  mov     rcx, rsi; hinstDLL
0x180001401  call    DllMain
0x180001406  mov     ebx, eax
0x180001408  mov     [rsp+108h+var_E8], eax
0x18000140c  jmp     short loc_180001423
0x18000140e  xor     ebx, ebx
0x180001410  mov     [rsp+108h+var_E8], ebx
0x180001414  mov     edi, [rsp+108h+arg_8]
0x18000141b  mov     rsi, [rsp+108h+arg_0]
0x180001423  cmp     edi, 1
0x180001426  jnz     short loc_18000149F
0x180001428  test    ebx, ebx
0x18000142a  jnz     short loc_18000149F
0x18000142c  xor     r8d, r8d; lpvReserved
0x18000142f  xor     edx, edx; fdwReason
0x180001431  mov     rcx, rsi; hinstDLL
0x180001434  call    DllMain
0x180001439  jmp     short loc_18000144E
0x18000143b  mov     edi, [rsp+108h+arg_8]
0x180001442  mov     rsi, [rsp+108h+arg_0]
0x18000144a  mov     ebx, [rsp+108h+var_E8]
0x18000144e  xor     r8d, r8d
0x180001451  xor     edx, edx
0x180001453  mov     rcx, rsi
0x180001456  call    _CRT_INIT
0x18000145b  jmp     short loc_180001470
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  mov     ebx, [rsp+108h+var_E8]
0x180001470  mov     rax, cs:_pRawDllMain
0x180001477  test    rax, rax
0x18000147a  jz      short loc_18000149F
0x18000147c  xor     r8d, r8d
0x18000147f  xor     edx, edx
0x180001481  mov     rcx, rsi
0x180001484  call    cs:__guard_dispatch_icall_fptr
0x18000148a  jmp     short loc_18000149F
0x18000148c  mov     edi, [rsp+108h+arg_8]
0x180001493  mov     rsi, [rsp+108h+arg_0]
0x18000149b  mov     ebx, [rsp+108h+var_E8]
0x18000149f  test    edi, edi
0x1800014a1  jz      short loc_1800014A8
0x1800014a3  cmp     edi, 3
0x1800014a6  jnz     short loc_180001514
0x1800014a8  mov     r8, [rsp+108h+lpvReserved]
0x1800014b0  mov     edx, edi
0x1800014b2  mov     rcx, rsi
0x1800014b5  call    _CRT_INIT
0x1800014ba  mov     ebx, eax
0x1800014bc  mov     [rsp+108h+var_E8], eax
0x1800014c0  jmp     short loc_1800014D7
0x1800014c2  xor     ebx, ebx
0x1800014c4  mov     [rsp+108h+var_E8], ebx
0x1800014c8  mov     edi, [rsp+108h+arg_8]
0x1800014cf  mov     rsi, [rsp+108h+arg_0]
0x1800014d7  mov     rax, cs:_pRawDllMain
0x1800014de  test    rax, rax
0x1800014e1  jz      short loc_180001514
0x1800014e3  cmp     cs:dword_1800201C4, 0
0x1800014ea  jz      short loc_180001514
0x1800014ec  mov     r8, [rsp+108h+lpvReserved]
0x1800014f4  mov     edx, edi
0x1800014f6  mov     rcx, rsi
0x1800014f9  call    cs:__guard_dispatch_icall_fptr
0x1800014ff  mov     ebx, eax
0x180001501  mov     [rsp+108h+var_E8], eax
0x180001505  jmp     short loc_180001514
0x180001507  xor     ebx, ebx
0x180001509  mov     [rsp+108h+var_E8], ebx
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  cmp     edi, 1
0x180001517  ja      short loc_180001523
0x180001519  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001523  mov     eax, ebx
0x180001525  add     rsp, 0F0h
0x18000152c  pop     rdi
0x18000152d  pop     rsi
0x18000152e  pop     rbx
0x18000152f  retn
0x180012570  push    rbp
0x180012572  sub     rsp, 20h
0x180012576  mov     rbp, rdx
0x180012579  mov     rax, [rcx]
0x18001257c  mov     edx, [rax]
0x18001257e  mov     [rbp+0A8h], rcx
0x180012585  mov     [rbp+28h], edx
0x180012588  mov     eax, [rbp+28h]
0x18001258b  cmp     eax, 0E06D7363h
0x180012590  jnz     short loc_1800125A6
0x180012592  mov     rdx, [rbp+0A8h]
0x180012599  mov     ecx, [rbp+28h]
0x18001259c  call    _XcptFilter_0
0x1800125a1  mov     [rbp+30h], eax
0x1800125a4  jmp     short loc_1800125AD
0x1800125a6  mov     dword ptr [rbp+30h], 0
0x1800125ad  mov     eax, [rbp+30h]
0x1800125b0  add     rsp, 20h
0x1800125b4  pop     rbp
0x1800125b5  retn
0x1800125b7  push    rbp
0x1800125b9  sub     rsp, 20h
0x1800125bd  mov     rbp, rdx
0x1800125c0  mov     rax, [rcx]
0x1800125c3  mov     edx, [rax]
0x1800125c5  mov     [rbp+0B0h], rcx
0x1800125cc  mov     [rbp+38h], edx
0x1800125cf  mov     eax, [rbp+38h]
0x1800125d2  cmp     eax, 0E06D7363h
0x1800125d7  jnz     short loc_1800125ED
0x1800125d9  mov     rdx, [rbp+0B0h]
0x1800125e0  mov     ecx, [rbp+38h]
0x1800125e3  call    _XcptFilter_0
0x1800125e8  mov     [rbp+40h], eax
0x1800125eb  jmp     short loc_1800125F4
0x1800125ed  mov     dword ptr [rbp+40h], 0
0x1800125f4  mov     eax, [rbp+40h]
0x1800125f7  add     rsp, 20h
0x1800125fb  pop     rbp
0x1800125fc  retn
0x1800125fe  push    rbp
0x180012600  sub     rsp, 20h
0x180012604  mov     rbp, rdx
0x180012607  mov     rax, [rcx]
0x18001260a  mov     edx, [rax]
0x18001260c  mov     [rbp+0B8h], rcx
0x180012613  mov     [rbp+48h], edx
0x180012616  mov     eax, [rbp+48h]
0x180012619  cmp     eax, 0E06D7363h
0x18001261e  jnz     short loc_180012634
0x180012620  mov     rdx, [rbp+0B8h]
0x180012627  mov     ecx, [rbp+48h]
0x18001262a  call    _XcptFilter_0
0x18001262f  mov     [rbp+50h], eax
0x180012632  jmp     short loc_18001263B
0x180012634  mov     dword ptr [rbp+50h], 0
0x18001263b  mov     eax, [rbp+50h]
0x18001263e  add     rsp, 20h
0x180012642  pop     rbp
0x180012643  retn
0x180012645  push    rbp
0x180012647  sub     rsp, 20h
0x18001264b  mov     rbp, rdx
0x18001264e  mov     rax, [rcx]
0x180012651  mov     edx, [rax]
0x180012653  mov     [rbp+0C0h], rcx
0x18001265a  mov     [rbp+58h], edx
0x18001265d  mov     eax, [rbp+58h]
0x180012660  cmp     eax, 0E06D7363h
0x180012665  jnz     short loc_18001267B
0x180012667  mov     rdx, [rbp+0C0h]
0x18001266e  mov     ecx, [rbp+58h]
0x180012671  call    _XcptFilter_0
0x180012676  mov     [rbp+60h], eax
0x180012679  jmp     short loc_180012682
0x18001267b  mov     dword ptr [rbp+60h], 0
0x180012682  mov     eax, [rbp+60h]
0x180012685  add     rsp, 20h
0x180012689  pop     rbp
0x18001268a  retn
0x18001268c  push    rbp
0x18001268e  sub     rsp, 20h
0x180012692  mov     rbp, rdx
0x180012695  mov     rax, [rcx]
0x180012698  mov     edx, [rax]
0x18001269a  mov     [rbp+0C8h], rcx
0x1800126a1  mov     [rbp+68h], edx
0x1800126a4  mov     eax, [rbp+68h]
0x1800126a7  cmp     eax, 0E06D7363h
0x1800126ac  jnz     short loc_1800126C2
0x1800126ae  mov     rdx, [rbp+0C8h]
0x1800126b5  mov     ecx, [rbp+68h]
0x1800126b8  call    _XcptFilter_0
0x1800126bd  mov     [rbp+70h], eax
0x1800126c0  jmp     short loc_1800126C9
0x1800126c2  mov     dword ptr [rbp+70h], 0
0x1800126c9  mov     eax, [rbp+70h]
0x1800126cc  add     rsp, 20h
0x1800126d0  pop     rbp
0x1800126d1  retn
0x1800126d3  push    rbp
0x1800126d5  sub     rsp, 20h
0x1800126d9  mov     rbp, rdx
0x1800126dc  mov     rax, [rcx]
0x1800126df  mov     edx, [rax]
0x1800126e1  mov     [rbp+0D0h], rcx
0x1800126e8  mov     [rbp+78h], edx
0x1800126eb  mov     eax, [rbp+78h]
0x1800126ee  cmp     eax, 0E06D7363h
0x1800126f3  jnz     short loc_18001270C
0x1800126f5  mov     rdx, [rbp+0D0h]
0x1800126fc  mov     ecx, [rbp+78h]
0x1800126ff  call    _XcptFilter_0
0x180012704  mov     [rbp+80h], eax
0x18001270a  jmp     short loc_180012716
0x18001270c  mov     dword ptr [rbp+80h], 0
0x180012716  mov     eax, [rbp+80h]
0x18001271c  add     rsp, 20h
0x180012720  pop     rbp
0x180012721  retn
0x180012723  push    rbp
0x180012725  sub     rsp, 20h
0x180012729  mov     rbp, rdx
0x18001272c  mov     rax, [rcx]
0x18001272f  mov     edx, [rax]
0x180012731  mov     [rbp+0D8h], rcx
0x180012738  mov     [rbp+88h], edx
0x18001273e  mov     eax, [rbp+88h]
0x180012744  cmp     eax, 0E06D7363h
0x180012749  jnz     short loc_180012765
0x18001274b  mov     rdx, [rbp+0D8h]
0x180012752  mov     ecx, [rbp+88h]
0x180012758  call    _XcptFilter_0
0x18001275d  mov     [rbp+90h], eax
0x180012763  jmp     short loc_18001276F
0x180012765  mov     dword ptr [rbp+90h], 0
0x18001276f  mov     eax, [rbp+90h]
0x180012775  add     rsp, 20h
0x180012779  pop     rbp
0x18001277a  retn
0x18001277c  push    rbp
0x18001277e  sub     rsp, 20h
0x180012782  mov     rbp, rdx
0x180012785  mov     rax, [rcx]
0x180012788  mov     edx, [rax]
0x18001278a  mov     [rbp+0E0h], rcx
0x180012791  mov     [rbp+98h], edx
0x180012797  mov     eax, [rbp+98h]
0x18001279d  cmp     eax, 0E06D7363h
0x1800127a2  jnz     short loc_1800127BE
0x1800127a4  mov     rdx, [rbp+0E0h]
0x1800127ab  mov     ecx, [rbp+98h]
0x1800127b1  call    _XcptFilter_0
0x1800127b6  mov     [rbp+0A0h], eax
0x1800127bc  jmp     short loc_1800127C8
0x1800127be  mov     dword ptr [rbp+0A0h], 0
0x1800127c8  mov     eax, [rbp+0A0h]
0x1800127ce  add     rsp, 20h
0x1800127d2  pop     rbp
0x1800127d3  retn
0x1800127d5  push    rbp
0x1800127d7  sub     rsp, 20h
0x1800127db  mov     rbp, rdx
0x1800127de  cmp     dword ptr [rbp+118h], 1
0x1800127e5  ja      short loc_1800127F1
0x1800127e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
