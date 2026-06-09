# __DllMainCRTStartup

- ea: `0x180005284`
- end: `0x180005490`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005240`

## callees

- `0x180005010`
- `0x180005284`
- `0x1800057b4`
- `0x180005988`
- `0x180006b40`

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
  if ( (_DWORD)fdwReason || dword_18000A0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000A0A4 = 1;
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
            if ( dword_18000A0A4 )
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
0x180005284  mov     [rsp+lpvReserved], r8
0x180005289  mov     [rsp+arg_8], edx
0x18000528d  mov     [rsp+arg_0], rcx
0x180005292  push    rbx
0x180005293  push    rsi
0x180005294  push    rdi
0x180005295  sub     rsp, 0F0h
0x18000529c  mov     edi, edx
0x18000529e  mov     rsi, rcx
0x1800052a1  mov     ebx, 1
0x1800052a6  cmp     edx, ebx
0x1800052a8  ja      short loc_1800052B0
0x1800052aa  mov     cs:__native_dllmain_reason, edx
0x1800052b0  test    edx, edx
0x1800052b2  jnz     short loc_1800052C7
0x1800052b4  cmp     cs:dword_18000A0A0, edx
0x1800052ba  jnz     short loc_1800052C7
0x1800052bc  xor     ebx, ebx
0x1800052be  mov     [rsp+108h+var_E8], ebx
0x1800052c2  jmp     loc_180005474
0x1800052c7  lea     eax, [rdx-1]
0x1800052ca  cmp     eax, 1
0x1800052cd  ja      loc_180005354
0x1800052d3  mov     rax, cs:_pRawDllMain
0x1800052da  test    rax, rax
0x1800052dd  jz      short loc_180005315
0x1800052df  cmp     edx, 1
0x1800052e2  jnz     short loc_1800052EA
0x1800052e4  mov     cs:dword_18000A0A4, edx
0x1800052ea  mov     r8, [rsp+108h+lpvReserved]
0x1800052f2  call    cs:__guard_dispatch_icall_fptr
0x1800052f8  mov     ebx, eax
0x1800052fa  mov     [rsp+108h+var_E8], eax
0x1800052fe  jmp     short loc_180005315
0x180005300  xor     ebx, ebx
0x180005302  mov     [rsp+108h+var_E8], ebx
0x180005306  mov     edi, [rsp+108h+arg_8]
0x18000530d  mov     rsi, [rsp+108h+arg_0]
0x180005315  test    ebx, ebx
0x180005317  jz      loc_180005474
0x18000531d  mov     r8, [rsp+108h+lpvReserved]
0x180005325  mov     edx, edi
0x180005327  mov     rcx, rsi
0x18000532a  call    _CRT_INIT
0x18000532f  mov     ebx, eax
0x180005331  mov     [rsp+108h+var_E8], eax
0x180005335  jmp     short loc_18000534C
0x180005337  xor     ebx, ebx
0x180005339  mov     [rsp+108h+var_E8], ebx
0x18000533d  mov     edi, [rsp+108h+arg_8]
0x180005344  mov     rsi, [rsp+108h+arg_0]
0x18000534c  test    ebx, ebx
0x18000534e  jz      loc_180005474
0x180005354  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000535c  mov     edx, edi; fdwReason
0x18000535e  mov     rcx, rsi; hinstDLL
0x180005361  call    DllMain
0x180005366  mov     ebx, eax
0x180005368  mov     [rsp+108h+var_E8], eax
0x18000536c  jmp     short loc_180005383
0x18000536e  xor     ebx, ebx
0x180005370  mov     [rsp+108h+var_E8], ebx
0x180005374  mov     edi, [rsp+108h+arg_8]
0x18000537b  mov     rsi, [rsp+108h+arg_0]
0x180005383  cmp     edi, 1
0x180005386  jnz     short loc_1800053FF
0x180005388  test    ebx, ebx
0x18000538a  jnz     short loc_1800053FF
0x18000538c  xor     r8d, r8d; lpvReserved
0x18000538f  xor     edx, edx; fdwReason
0x180005391  mov     rcx, rsi; hinstDLL
0x180005394  call    DllMain
0x180005399  jmp     short loc_1800053AE
0x18000539b  mov     edi, [rsp+108h+arg_8]
0x1800053a2  mov     rsi, [rsp+108h+arg_0]
0x1800053aa  mov     ebx, [rsp+108h+var_E8]
0x1800053ae  xor     r8d, r8d
0x1800053b1  xor     edx, edx
0x1800053b3  mov     rcx, rsi
0x1800053b6  call    _CRT_INIT
0x1800053bb  jmp     short loc_1800053D0
0x1800053bd  mov     edi, [rsp+108h+arg_8]
0x1800053c4  mov     rsi, [rsp+108h+arg_0]
0x1800053cc  mov     ebx, [rsp+108h+var_E8]
0x1800053d0  mov     rax, cs:_pRawDllMain
0x1800053d7  test    rax, rax
0x1800053da  jz      short loc_1800053FF
0x1800053dc  xor     r8d, r8d
0x1800053df  xor     edx, edx
0x1800053e1  mov     rcx, rsi
0x1800053e4  call    cs:__guard_dispatch_icall_fptr
0x1800053ea  jmp     short loc_1800053FF
0x1800053ec  mov     edi, [rsp+108h+arg_8]
0x1800053f3  mov     rsi, [rsp+108h+arg_0]
0x1800053fb  mov     ebx, [rsp+108h+var_E8]
0x1800053ff  test    edi, edi
0x180005401  jz      short loc_180005408
0x180005403  cmp     edi, 3
0x180005406  jnz     short loc_180005474
0x180005408  mov     r8, [rsp+108h+lpvReserved]
0x180005410  mov     edx, edi
0x180005412  mov     rcx, rsi
0x180005415  call    _CRT_INIT
0x18000541a  mov     ebx, eax
0x18000541c  mov     [rsp+108h+var_E8], eax
0x180005420  jmp     short loc_180005437
0x180005422  xor     ebx, ebx
0x180005424  mov     [rsp+108h+var_E8], ebx
0x180005428  mov     edi, [rsp+108h+arg_8]
0x18000542f  mov     rsi, [rsp+108h+arg_0]
0x180005437  mov     rax, cs:_pRawDllMain
0x18000543e  test    rax, rax
0x180005441  jz      short loc_180005474
0x180005443  cmp     cs:dword_18000A0A4, 0
0x18000544a  jz      short loc_180005474
0x18000544c  mov     r8, [rsp+108h+lpvReserved]
0x180005454  mov     edx, edi
0x180005456  mov     rcx, rsi
0x180005459  call    cs:__guard_dispatch_icall_fptr
0x18000545f  mov     ebx, eax
0x180005461  mov     [rsp+108h+var_E8], eax
0x180005465  jmp     short loc_180005474
0x180005467  xor     ebx, ebx
0x180005469  mov     [rsp+108h+var_E8], ebx
0x18000546d  mov     edi, [rsp+108h+arg_8]
0x180005474  cmp     edi, 1
0x180005477  ja      short loc_180005483
0x180005479  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180005483  mov     eax, ebx
0x180005485  add     rsp, 0F0h
0x18000548c  pop     rdi
0x18000548d  pop     rsi
0x18000548e  pop     rbx
0x18000548f  retn
0x180006b80  push    rbp
0x180006b82  sub     rsp, 20h
0x180006b86  mov     rbp, rdx
0x180006b89  mov     rax, [rcx]
0x180006b8c  mov     edx, [rax]
0x180006b8e  mov     [rbp+0A8h], rcx
0x180006b95  mov     [rbp+28h], edx
0x180006b98  mov     eax, [rbp+28h]
0x180006b9b  cmp     eax, 0E06D7363h
0x180006ba0  jnz     short loc_180006BB6
0x180006ba2  mov     rdx, [rbp+0A8h]
0x180006ba9  mov     ecx, [rbp+28h]
0x180006bac  call    _XcptFilter_0
0x180006bb1  mov     [rbp+30h], eax
0x180006bb4  jmp     short loc_180006BBD
0x180006bb6  mov     dword ptr [rbp+30h], 0
0x180006bbd  mov     eax, [rbp+30h]
0x180006bc0  add     rsp, 20h
0x180006bc4  pop     rbp
0x180006bc5  retn
0x180006bc7  push    rbp
0x180006bc9  sub     rsp, 20h
0x180006bcd  mov     rbp, rdx
0x180006bd0  mov     rax, [rcx]
0x180006bd3  mov     edx, [rax]
0x180006bd5  mov     [rbp+0B0h], rcx
0x180006bdc  mov     [rbp+38h], edx
0x180006bdf  mov     eax, [rbp+38h]
0x180006be2  cmp     eax, 0E06D7363h
0x180006be7  jnz     short loc_180006BFD
0x180006be9  mov     rdx, [rbp+0B0h]
0x180006bf0  mov     ecx, [rbp+38h]
0x180006bf3  call    _XcptFilter_0
0x180006bf8  mov     [rbp+40h], eax
0x180006bfb  jmp     short loc_180006C04
0x180006bfd  mov     dword ptr [rbp+40h], 0
0x180006c04  mov     eax, [rbp+40h]
0x180006c07  add     rsp, 20h
0x180006c0b  pop     rbp
0x180006c0c  retn
0x180006c0e  push    rbp
0x180006c10  sub     rsp, 20h
0x180006c14  mov     rbp, rdx
0x180006c17  mov     rax, [rcx]
0x180006c1a  mov     edx, [rax]
0x180006c1c  mov     [rbp+0B8h], rcx
0x180006c23  mov     [rbp+48h], edx
0x180006c26  mov     eax, [rbp+48h]
0x180006c29  cmp     eax, 0E06D7363h
0x180006c2e  jnz     short loc_180006C44
0x180006c30  mov     rdx, [rbp+0B8h]
0x180006c37  mov     ecx, [rbp+48h]
0x180006c3a  call    _XcptFilter_0
0x180006c3f  mov     [rbp+50h], eax
0x180006c42  jmp     short loc_180006C4B
0x180006c44  mov     dword ptr [rbp+50h], 0
0x180006c4b  mov     eax, [rbp+50h]
0x180006c4e  add     rsp, 20h
0x180006c52  pop     rbp
0x180006c53  retn
0x180006c55  push    rbp
0x180006c57  sub     rsp, 20h
0x180006c5b  mov     rbp, rdx
0x180006c5e  mov     rax, [rcx]
0x180006c61  mov     edx, [rax]
0x180006c63  mov     [rbp+0C0h], rcx
0x180006c6a  mov     [rbp+58h], edx
0x180006c6d  mov     eax, [rbp+58h]
0x180006c70  cmp     eax, 0E06D7363h
0x180006c75  jnz     short loc_180006C8B
0x180006c77  mov     rdx, [rbp+0C0h]
0x180006c7e  mov     ecx, [rbp+58h]
0x180006c81  call    _XcptFilter_0
0x180006c86  mov     [rbp+60h], eax
0x180006c89  jmp     short loc_180006C92
0x180006c8b  mov     dword ptr [rbp+60h], 0
0x180006c92  mov     eax, [rbp+60h]
0x180006c95  add     rsp, 20h
0x180006c99  pop     rbp
0x180006c9a  retn
0x180006c9c  push    rbp
0x180006c9e  sub     rsp, 20h
0x180006ca2  mov     rbp, rdx
0x180006ca5  mov     rax, [rcx]
0x180006ca8  mov     edx, [rax]
0x180006caa  mov     [rbp+0C8h], rcx
0x180006cb1  mov     [rbp+68h], edx
0x180006cb4  mov     eax, [rbp+68h]
0x180006cb7  cmp     eax, 0E06D7363h
0x180006cbc  jnz     short loc_180006CD2
0x180006cbe  mov     rdx, [rbp+0C8h]
0x180006cc5  mov     ecx, [rbp+68h]
0x180006cc8  call    _XcptFilter_0
0x180006ccd  mov     [rbp+70h], eax
0x180006cd0  jmp     short loc_180006CD9
0x180006cd2  mov     dword ptr [rbp+70h], 0
0x180006cd9  mov     eax, [rbp+70h]
0x180006cdc  add     rsp, 20h
0x180006ce0  pop     rbp
0x180006ce1  retn
0x180006ce3  push    rbp
0x180006ce5  sub     rsp, 20h
0x180006ce9  mov     rbp, rdx
0x180006cec  mov     rax, [rcx]
0x180006cef  mov     edx, [rax]
0x180006cf1  mov     [rbp+0D0h], rcx
0x180006cf8  mov     [rbp+78h], edx
0x180006cfb  mov     eax, [rbp+78h]
0x180006cfe  cmp     eax, 0E06D7363h
0x180006d03  jnz     short loc_180006D1C
0x180006d05  mov     rdx, [rbp+0D0h]
0x180006d0c  mov     ecx, [rbp+78h]
0x180006d0f  call    _XcptFilter_0
0x180006d14  mov     [rbp+80h], eax
0x180006d1a  jmp     short loc_180006D26
0x180006d1c  mov     dword ptr [rbp+80h], 0
0x180006d26  mov     eax, [rbp+80h]
0x180006d2c  add     rsp, 20h
0x180006d30  pop     rbp
0x180006d31  retn
0x180006d33  push    rbp
0x180006d35  sub     rsp, 20h
0x180006d39  mov     rbp, rdx
0x180006d3c  mov     rax, [rcx]
0x180006d3f  mov     edx, [rax]
0x180006d41  mov     [rbp+0D8h], rcx
0x180006d48  mov     [rbp+88h], edx
0x180006d4e  mov     eax, [rbp+88h]
0x180006d54  cmp     eax, 0E06D7363h
0x180006d59  jnz     short loc_180006D75
0x180006d5b  mov     rdx, [rbp+0D8h]
0x180006d62  mov     ecx, [rbp+88h]
0x180006d68  call    _XcptFilter_0
0x180006d6d  mov     [rbp+90h], eax
0x180006d73  jmp     short loc_180006D7F
0x180006d75  mov     dword ptr [rbp+90h], 0
0x180006d7f  mov     eax, [rbp+90h]
0x180006d85  add     rsp, 20h
0x180006d89  pop     rbp
0x180006d8a  retn
0x180006d8c  push    rbp
0x180006d8e  sub     rsp, 20h
0x180006d92  mov     rbp, rdx
0x180006d95  mov     rax, [rcx]
0x180006d98  mov     edx, [rax]
0x180006d9a  mov     [rbp+0E0h], rcx
0x180006da1  mov     [rbp+98h], edx
0x180006da7  mov     eax, [rbp+98h]
0x180006dad  cmp     eax, 0E06D7363h
0x180006db2  jnz     short loc_180006DCE
0x180006db4  mov     rdx, [rbp+0E0h]
0x180006dbb  mov     ecx, [rbp+98h]
0x180006dc1  call    _XcptFilter_0
0x180006dc6  mov     [rbp+0A0h], eax
0x180006dcc  jmp     short loc_180006DD8
0x180006dce  mov     dword ptr [rbp+0A0h], 0
0x180006dd8  mov     eax, [rbp+0A0h]
0x180006dde  add     rsp, 20h
0x180006de2  pop     rbp
0x180006de3  retn
0x180006de5  push    rbp
0x180006de7  sub     rsp, 20h
0x180006deb  mov     rbp, rdx
0x180006dee  cmp     dword ptr [rbp+118h], 1
0x180006df5  ja      short loc_180006E01
0x180006df7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
