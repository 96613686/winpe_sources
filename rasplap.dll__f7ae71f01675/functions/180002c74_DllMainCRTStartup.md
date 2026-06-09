# __DllMainCRTStartup

- ea: `0x180002c74`
- end: `0x180002e80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002c30`

## callees

- `0x180001010`
- `0x180002a00`
- `0x180002c74`
- `0x180002ecd`
- `0x18000b140`

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
  if ( (_DWORD)fdwReason || dword_180012260 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180012264 = 1;
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
            if ( dword_180012264 )
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
0x180002c74  mov     [rsp+lpvReserved], r8
0x180002c79  mov     [rsp+arg_8], edx
0x180002c7d  mov     [rsp+arg_0], rcx
0x180002c82  push    rbx
0x180002c83  push    rsi
0x180002c84  push    rdi
0x180002c85  sub     rsp, 0F0h
0x180002c8c  mov     edi, edx
0x180002c8e  mov     rsi, rcx
0x180002c91  mov     ebx, 1
0x180002c96  cmp     edx, ebx
0x180002c98  ja      short loc_180002CA0
0x180002c9a  mov     cs:__native_dllmain_reason, edx
0x180002ca0  test    edx, edx
0x180002ca2  jnz     short loc_180002CB7
0x180002ca4  cmp     cs:dword_180012260, edx
0x180002caa  jnz     short loc_180002CB7
0x180002cac  xor     ebx, ebx
0x180002cae  mov     [rsp+108h+var_E8], ebx
0x180002cb2  jmp     loc_180002E64
0x180002cb7  lea     eax, [rdx-1]
0x180002cba  cmp     eax, 1
0x180002cbd  ja      loc_180002D44
0x180002cc3  mov     rax, cs:_pRawDllMain
0x180002cca  test    rax, rax
0x180002ccd  jz      short loc_180002D05
0x180002ccf  cmp     edx, 1
0x180002cd2  jnz     short loc_180002CDA
0x180002cd4  mov     cs:dword_180012264, edx
0x180002cda  mov     r8, [rsp+108h+lpvReserved]
0x180002ce2  call    cs:__guard_dispatch_icall_fptr
0x180002ce8  mov     ebx, eax
0x180002cea  mov     [rsp+108h+var_E8], eax
0x180002cee  jmp     short loc_180002D05
0x180002cf0  xor     ebx, ebx
0x180002cf2  mov     [rsp+108h+var_E8], ebx
0x180002cf6  mov     edi, [rsp+108h+arg_8]
0x180002cfd  mov     rsi, [rsp+108h+arg_0]
0x180002d05  test    ebx, ebx
0x180002d07  jz      loc_180002E64
0x180002d0d  mov     r8, [rsp+108h+lpvReserved]
0x180002d15  mov     edx, edi
0x180002d17  mov     rcx, rsi
0x180002d1a  call    _CRT_INIT
0x180002d1f  mov     ebx, eax
0x180002d21  mov     [rsp+108h+var_E8], eax
0x180002d25  jmp     short loc_180002D3C
0x180002d27  xor     ebx, ebx
0x180002d29  mov     [rsp+108h+var_E8], ebx
0x180002d2d  mov     edi, [rsp+108h+arg_8]
0x180002d34  mov     rsi, [rsp+108h+arg_0]
0x180002d3c  test    ebx, ebx
0x180002d3e  jz      loc_180002E64
0x180002d44  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002d4c  mov     edx, edi; fdwReason
0x180002d4e  mov     rcx, rsi; hinstDLL
0x180002d51  call    DllMain
0x180002d56  mov     ebx, eax
0x180002d58  mov     [rsp+108h+var_E8], eax
0x180002d5c  jmp     short loc_180002D73
0x180002d5e  xor     ebx, ebx
0x180002d60  mov     [rsp+108h+var_E8], ebx
0x180002d64  mov     edi, [rsp+108h+arg_8]
0x180002d6b  mov     rsi, [rsp+108h+arg_0]
0x180002d73  cmp     edi, 1
0x180002d76  jnz     short loc_180002DEF
0x180002d78  test    ebx, ebx
0x180002d7a  jnz     short loc_180002DEF
0x180002d7c  xor     r8d, r8d; lpvReserved
0x180002d7f  xor     edx, edx; fdwReason
0x180002d81  mov     rcx, rsi; hinstDLL
0x180002d84  call    DllMain
0x180002d89  jmp     short loc_180002D9E
0x180002d8b  mov     edi, [rsp+108h+arg_8]
0x180002d92  mov     rsi, [rsp+108h+arg_0]
0x180002d9a  mov     ebx, [rsp+108h+var_E8]
0x180002d9e  xor     r8d, r8d
0x180002da1  xor     edx, edx
0x180002da3  mov     rcx, rsi
0x180002da6  call    _CRT_INIT
0x180002dab  jmp     short loc_180002DC0
0x180002dad  mov     edi, [rsp+108h+arg_8]
0x180002db4  mov     rsi, [rsp+108h+arg_0]
0x180002dbc  mov     ebx, [rsp+108h+var_E8]
0x180002dc0  mov     rax, cs:_pRawDllMain
0x180002dc7  test    rax, rax
0x180002dca  jz      short loc_180002DEF
0x180002dcc  xor     r8d, r8d
0x180002dcf  xor     edx, edx
0x180002dd1  mov     rcx, rsi
0x180002dd4  call    cs:__guard_dispatch_icall_fptr
0x180002dda  jmp     short loc_180002DEF
0x180002ddc  mov     edi, [rsp+108h+arg_8]
0x180002de3  mov     rsi, [rsp+108h+arg_0]
0x180002deb  mov     ebx, [rsp+108h+var_E8]
0x180002def  test    edi, edi
0x180002df1  jz      short loc_180002DF8
0x180002df3  cmp     edi, 3
0x180002df6  jnz     short loc_180002E64
0x180002df8  mov     r8, [rsp+108h+lpvReserved]
0x180002e00  mov     edx, edi
0x180002e02  mov     rcx, rsi
0x180002e05  call    _CRT_INIT
0x180002e0a  mov     ebx, eax
0x180002e0c  mov     [rsp+108h+var_E8], eax
0x180002e10  jmp     short loc_180002E27
0x180002e12  xor     ebx, ebx
0x180002e14  mov     [rsp+108h+var_E8], ebx
0x180002e18  mov     edi, [rsp+108h+arg_8]
0x180002e1f  mov     rsi, [rsp+108h+arg_0]
0x180002e27  mov     rax, cs:_pRawDllMain
0x180002e2e  test    rax, rax
0x180002e31  jz      short loc_180002E64
0x180002e33  cmp     cs:dword_180012264, 0
0x180002e3a  jz      short loc_180002E64
0x180002e3c  mov     r8, [rsp+108h+lpvReserved]
0x180002e44  mov     edx, edi
0x180002e46  mov     rcx, rsi
0x180002e49  call    cs:__guard_dispatch_icall_fptr
0x180002e4f  mov     ebx, eax
0x180002e51  mov     [rsp+108h+var_E8], eax
0x180002e55  jmp     short loc_180002E64
0x180002e57  xor     ebx, ebx
0x180002e59  mov     [rsp+108h+var_E8], ebx
0x180002e5d  mov     edi, [rsp+108h+arg_8]
0x180002e64  cmp     edi, 1
0x180002e67  ja      short loc_180002E73
0x180002e69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002e73  mov     eax, ebx
0x180002e75  add     rsp, 0F0h
0x180002e7c  pop     rdi
0x180002e7d  pop     rsi
0x180002e7e  pop     rbx
0x180002e7f  retn
0x18000b1b0  push    rbp
0x18000b1b2  sub     rsp, 20h
0x18000b1b6  mov     rbp, rdx
0x18000b1b9  mov     rax, [rcx]
0x18000b1bc  mov     edx, [rax]
0x18000b1be  mov     [rbp+0A8h], rcx
0x18000b1c5  mov     [rbp+28h], edx
0x18000b1c8  mov     eax, [rbp+28h]
0x18000b1cb  cmp     eax, 0E06D7363h
0x18000b1d0  jnz     short loc_18000B1E6
0x18000b1d2  mov     rdx, [rbp+0A8h]
0x18000b1d9  mov     ecx, [rbp+28h]
0x18000b1dc  call    _XcptFilter_0
0x18000b1e1  mov     [rbp+30h], eax
0x18000b1e4  jmp     short loc_18000B1ED
0x18000b1e6  mov     dword ptr [rbp+30h], 0
0x18000b1ed  mov     eax, [rbp+30h]
0x18000b1f0  add     rsp, 20h
0x18000b1f4  pop     rbp
0x18000b1f5  retn
0x18000b1f7  push    rbp
0x18000b1f9  sub     rsp, 20h
0x18000b1fd  mov     rbp, rdx
0x18000b200  mov     rax, [rcx]
0x18000b203  mov     edx, [rax]
0x18000b205  mov     [rbp+0B0h], rcx
0x18000b20c  mov     [rbp+38h], edx
0x18000b20f  mov     eax, [rbp+38h]
0x18000b212  cmp     eax, 0E06D7363h
0x18000b217  jnz     short loc_18000B22D
0x18000b219  mov     rdx, [rbp+0B0h]
0x18000b220  mov     ecx, [rbp+38h]
0x18000b223  call    _XcptFilter_0
0x18000b228  mov     [rbp+40h], eax
0x18000b22b  jmp     short loc_18000B234
0x18000b22d  mov     dword ptr [rbp+40h], 0
0x18000b234  mov     eax, [rbp+40h]
0x18000b237  add     rsp, 20h
0x18000b23b  pop     rbp
0x18000b23c  retn
0x18000b23e  push    rbp
0x18000b240  sub     rsp, 20h
0x18000b244  mov     rbp, rdx
0x18000b247  mov     rax, [rcx]
0x18000b24a  mov     edx, [rax]
0x18000b24c  mov     [rbp+0B8h], rcx
0x18000b253  mov     [rbp+48h], edx
0x18000b256  mov     eax, [rbp+48h]
0x18000b259  cmp     eax, 0E06D7363h
0x18000b25e  jnz     short loc_18000B274
0x18000b260  mov     rdx, [rbp+0B8h]
0x18000b267  mov     ecx, [rbp+48h]
0x18000b26a  call    _XcptFilter_0
0x18000b26f  mov     [rbp+50h], eax
0x18000b272  jmp     short loc_18000B27B
0x18000b274  mov     dword ptr [rbp+50h], 0
0x18000b27b  mov     eax, [rbp+50h]
0x18000b27e  add     rsp, 20h
0x18000b282  pop     rbp
0x18000b283  retn
0x18000b285  push    rbp
0x18000b287  sub     rsp, 20h
0x18000b28b  mov     rbp, rdx
0x18000b28e  mov     rax, [rcx]
0x18000b291  mov     edx, [rax]
0x18000b293  mov     [rbp+0C0h], rcx
0x18000b29a  mov     [rbp+58h], edx
0x18000b29d  mov     eax, [rbp+58h]
0x18000b2a0  cmp     eax, 0E06D7363h
0x18000b2a5  jnz     short loc_18000B2BB
0x18000b2a7  mov     rdx, [rbp+0C0h]
0x18000b2ae  mov     ecx, [rbp+58h]
0x18000b2b1  call    _XcptFilter_0
0x18000b2b6  mov     [rbp+60h], eax
0x18000b2b9  jmp     short loc_18000B2C2
0x18000b2bb  mov     dword ptr [rbp+60h], 0
0x18000b2c2  mov     eax, [rbp+60h]
0x18000b2c5  add     rsp, 20h
0x18000b2c9  pop     rbp
0x18000b2ca  retn
0x18000b2cc  push    rbp
0x18000b2ce  sub     rsp, 20h
0x18000b2d2  mov     rbp, rdx
0x18000b2d5  mov     rax, [rcx]
0x18000b2d8  mov     edx, [rax]
0x18000b2da  mov     [rbp+0C8h], rcx
0x18000b2e1  mov     [rbp+68h], edx
0x18000b2e4  mov     eax, [rbp+68h]
0x18000b2e7  cmp     eax, 0E06D7363h
0x18000b2ec  jnz     short loc_18000B302
0x18000b2ee  mov     rdx, [rbp+0C8h]
0x18000b2f5  mov     ecx, [rbp+68h]
0x18000b2f8  call    _XcptFilter_0
0x18000b2fd  mov     [rbp+70h], eax
0x18000b300  jmp     short loc_18000B309
0x18000b302  mov     dword ptr [rbp+70h], 0
0x18000b309  mov     eax, [rbp+70h]
0x18000b30c  add     rsp, 20h
0x18000b310  pop     rbp
0x18000b311  retn
0x18000b313  push    rbp
0x18000b315  sub     rsp, 20h
0x18000b319  mov     rbp, rdx
0x18000b31c  mov     rax, [rcx]
0x18000b31f  mov     edx, [rax]
0x18000b321  mov     [rbp+0D0h], rcx
0x18000b328  mov     [rbp+78h], edx
0x18000b32b  mov     eax, [rbp+78h]
0x18000b32e  cmp     eax, 0E06D7363h
0x18000b333  jnz     short loc_18000B34C
0x18000b335  mov     rdx, [rbp+0D0h]
0x18000b33c  mov     ecx, [rbp+78h]
0x18000b33f  call    _XcptFilter_0
0x18000b344  mov     [rbp+80h], eax
0x18000b34a  jmp     short loc_18000B356
0x18000b34c  mov     dword ptr [rbp+80h], 0
0x18000b356  mov     eax, [rbp+80h]
0x18000b35c  add     rsp, 20h
0x18000b360  pop     rbp
0x18000b361  retn
0x18000b363  push    rbp
0x18000b365  sub     rsp, 20h
0x18000b369  mov     rbp, rdx
0x18000b36c  mov     rax, [rcx]
0x18000b36f  mov     edx, [rax]
0x18000b371  mov     [rbp+0D8h], rcx
0x18000b378  mov     [rbp+88h], edx
0x18000b37e  mov     eax, [rbp+88h]
0x18000b384  cmp     eax, 0E06D7363h
0x18000b389  jnz     short loc_18000B3A5
0x18000b38b  mov     rdx, [rbp+0D8h]
0x18000b392  mov     ecx, [rbp+88h]
0x18000b398  call    _XcptFilter_0
0x18000b39d  mov     [rbp+90h], eax
0x18000b3a3  jmp     short loc_18000B3AF
0x18000b3a5  mov     dword ptr [rbp+90h], 0
0x18000b3af  mov     eax, [rbp+90h]
0x18000b3b5  add     rsp, 20h
0x18000b3b9  pop     rbp
0x18000b3ba  retn
0x18000b3bc  push    rbp
0x18000b3be  sub     rsp, 20h
0x18000b3c2  mov     rbp, rdx
0x18000b3c5  mov     rax, [rcx]
0x18000b3c8  mov     edx, [rax]
0x18000b3ca  mov     [rbp+0E0h], rcx
0x18000b3d1  mov     [rbp+98h], edx
0x18000b3d7  mov     eax, [rbp+98h]
0x18000b3dd  cmp     eax, 0E06D7363h
0x18000b3e2  jnz     short loc_18000B3FE
0x18000b3e4  mov     rdx, [rbp+0E0h]
0x18000b3eb  mov     ecx, [rbp+98h]
0x18000b3f1  call    _XcptFilter_0
0x18000b3f6  mov     [rbp+0A0h], eax
0x18000b3fc  jmp     short loc_18000B408
0x18000b3fe  mov     dword ptr [rbp+0A0h], 0
0x18000b408  mov     eax, [rbp+0A0h]
0x18000b40e  add     rsp, 20h
0x18000b412  pop     rbp
0x18000b413  retn
0x18000b415  push    rbp
0x18000b417  sub     rsp, 20h
0x18000b41b  mov     rbp, rdx
0x18000b41e  cmp     dword ptr [rbp+118h], 1
0x18000b425  ja      short loc_18000B431
0x18000b427  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
