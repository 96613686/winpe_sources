# __DllMainCRTStartup

- ea: `0x180001df4`
- end: `0x180002000`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001db0`

## callees

- `0x180001b80`
- `0x180001df4`
- `0x18000268e`
- `0x180005e0c`
- `0x18000df80`

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
  if ( (_DWORD)fdwReason || dword_18001758C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180017590 = 1;
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
            if ( dword_180017590 )
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
0x180001df4  mov     [rsp+lpvReserved], r8
0x180001df9  mov     [rsp+arg_8], edx
0x180001dfd  mov     [rsp+arg_0], rcx
0x180001e02  push    rbx
0x180001e03  push    rsi
0x180001e04  push    rdi
0x180001e05  sub     rsp, 0F0h
0x180001e0c  mov     edi, edx
0x180001e0e  mov     rsi, rcx
0x180001e11  mov     ebx, 1
0x180001e16  cmp     edx, ebx
0x180001e18  ja      short loc_180001E20
0x180001e1a  mov     cs:__native_dllmain_reason, edx
0x180001e20  test    edx, edx
0x180001e22  jnz     short loc_180001E37
0x180001e24  cmp     cs:dword_18001758C, edx
0x180001e2a  jnz     short loc_180001E37
0x180001e2c  xor     ebx, ebx
0x180001e2e  mov     [rsp+108h+var_E8], ebx
0x180001e32  jmp     loc_180001FE4
0x180001e37  lea     eax, [rdx-1]
0x180001e3a  cmp     eax, 1
0x180001e3d  ja      loc_180001EC4
0x180001e43  mov     rax, cs:_pRawDllMain
0x180001e4a  test    rax, rax
0x180001e4d  jz      short loc_180001E85
0x180001e4f  cmp     edx, 1
0x180001e52  jnz     short loc_180001E5A
0x180001e54  mov     cs:dword_180017590, edx
0x180001e5a  mov     r8, [rsp+108h+lpvReserved]
0x180001e62  call    cs:__guard_dispatch_icall_fptr
0x180001e68  mov     ebx, eax
0x180001e6a  mov     [rsp+108h+var_E8], eax
0x180001e6e  jmp     short loc_180001E85
0x180001e70  xor     ebx, ebx
0x180001e72  mov     [rsp+108h+var_E8], ebx
0x180001e76  mov     edi, [rsp+108h+arg_8]
0x180001e7d  mov     rsi, [rsp+108h+arg_0]
0x180001e85  test    ebx, ebx
0x180001e87  jz      loc_180001FE4
0x180001e8d  mov     r8, [rsp+108h+lpvReserved]
0x180001e95  mov     edx, edi
0x180001e97  mov     rcx, rsi
0x180001e9a  call    _CRT_INIT
0x180001e9f  mov     ebx, eax
0x180001ea1  mov     [rsp+108h+var_E8], eax
0x180001ea5  jmp     short loc_180001EBC
0x180001ea7  xor     ebx, ebx
0x180001ea9  mov     [rsp+108h+var_E8], ebx
0x180001ead  mov     edi, [rsp+108h+arg_8]
0x180001eb4  mov     rsi, [rsp+108h+arg_0]
0x180001ebc  test    ebx, ebx
0x180001ebe  jz      loc_180001FE4
0x180001ec4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001ecc  mov     edx, edi; fdwReason
0x180001ece  mov     rcx, rsi; hinstDLL
0x180001ed1  call    DllMain
0x180001ed6  mov     ebx, eax
0x180001ed8  mov     [rsp+108h+var_E8], eax
0x180001edc  jmp     short loc_180001EF3
0x180001ede  xor     ebx, ebx
0x180001ee0  mov     [rsp+108h+var_E8], ebx
0x180001ee4  mov     edi, [rsp+108h+arg_8]
0x180001eeb  mov     rsi, [rsp+108h+arg_0]
0x180001ef3  cmp     edi, 1
0x180001ef6  jnz     short loc_180001F6F
0x180001ef8  test    ebx, ebx
0x180001efa  jnz     short loc_180001F6F
0x180001efc  xor     r8d, r8d; lpvReserved
0x180001eff  xor     edx, edx; fdwReason
0x180001f01  mov     rcx, rsi; hinstDLL
0x180001f04  call    DllMain
0x180001f09  jmp     short loc_180001F1E
0x180001f0b  mov     edi, [rsp+108h+arg_8]
0x180001f12  mov     rsi, [rsp+108h+arg_0]
0x180001f1a  mov     ebx, [rsp+108h+var_E8]
0x180001f1e  xor     r8d, r8d
0x180001f21  xor     edx, edx
0x180001f23  mov     rcx, rsi
0x180001f26  call    _CRT_INIT
0x180001f2b  jmp     short loc_180001F40
0x180001f2d  mov     edi, [rsp+108h+arg_8]
0x180001f34  mov     rsi, [rsp+108h+arg_0]
0x180001f3c  mov     ebx, [rsp+108h+var_E8]
0x180001f40  mov     rax, cs:_pRawDllMain
0x180001f47  test    rax, rax
0x180001f4a  jz      short loc_180001F6F
0x180001f4c  xor     r8d, r8d
0x180001f4f  xor     edx, edx
0x180001f51  mov     rcx, rsi
0x180001f54  call    cs:__guard_dispatch_icall_fptr
0x180001f5a  jmp     short loc_180001F6F
0x180001f5c  mov     edi, [rsp+108h+arg_8]
0x180001f63  mov     rsi, [rsp+108h+arg_0]
0x180001f6b  mov     ebx, [rsp+108h+var_E8]
0x180001f6f  test    edi, edi
0x180001f71  jz      short loc_180001F78
0x180001f73  cmp     edi, 3
0x180001f76  jnz     short loc_180001FE4
0x180001f78  mov     r8, [rsp+108h+lpvReserved]
0x180001f80  mov     edx, edi
0x180001f82  mov     rcx, rsi
0x180001f85  call    _CRT_INIT
0x180001f8a  mov     ebx, eax
0x180001f8c  mov     [rsp+108h+var_E8], eax
0x180001f90  jmp     short loc_180001FA7
0x180001f92  xor     ebx, ebx
0x180001f94  mov     [rsp+108h+var_E8], ebx
0x180001f98  mov     edi, [rsp+108h+arg_8]
0x180001f9f  mov     rsi, [rsp+108h+arg_0]
0x180001fa7  mov     rax, cs:_pRawDllMain
0x180001fae  test    rax, rax
0x180001fb1  jz      short loc_180001FE4
0x180001fb3  cmp     cs:dword_180017590, 0
0x180001fba  jz      short loc_180001FE4
0x180001fbc  mov     r8, [rsp+108h+lpvReserved]
0x180001fc4  mov     edx, edi
0x180001fc6  mov     rcx, rsi
0x180001fc9  call    cs:__guard_dispatch_icall_fptr
0x180001fcf  mov     ebx, eax
0x180001fd1  mov     [rsp+108h+var_E8], eax
0x180001fd5  jmp     short loc_180001FE4
0x180001fd7  xor     ebx, ebx
0x180001fd9  mov     [rsp+108h+var_E8], ebx
0x180001fdd  mov     edi, [rsp+108h+arg_8]
0x180001fe4  cmp     edi, 1
0x180001fe7  ja      short loc_180001FF3
0x180001fe9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ff3  mov     eax, ebx
0x180001ff5  add     rsp, 0F0h
0x180001ffc  pop     rdi
0x180001ffd  pop     rsi
0x180001ffe  pop     rbx
0x180001fff  retn
0x18000e092  push    rbp
0x18000e094  sub     rsp, 20h
0x18000e098  mov     rbp, rdx
0x18000e09b  mov     rax, [rcx]
0x18000e09e  mov     edx, [rax]
0x18000e0a0  mov     [rbp+0A8h], rcx
0x18000e0a7  mov     [rbp+28h], edx
0x18000e0aa  mov     eax, [rbp+28h]
0x18000e0ad  cmp     eax, 0E06D7363h
0x18000e0b2  jnz     short loc_18000E0C8
0x18000e0b4  mov     rdx, [rbp+0A8h]
0x18000e0bb  mov     ecx, [rbp+28h]
0x18000e0be  call    _XcptFilter_0
0x18000e0c3  mov     [rbp+30h], eax
0x18000e0c6  jmp     short loc_18000E0CF
0x18000e0c8  mov     dword ptr [rbp+30h], 0
0x18000e0cf  mov     eax, [rbp+30h]
0x18000e0d2  add     rsp, 20h
0x18000e0d6  pop     rbp
0x18000e0d7  retn
0x18000e0d9  push    rbp
0x18000e0db  sub     rsp, 20h
0x18000e0df  mov     rbp, rdx
0x18000e0e2  mov     rax, [rcx]
0x18000e0e5  mov     edx, [rax]
0x18000e0e7  mov     [rbp+0B0h], rcx
0x18000e0ee  mov     [rbp+38h], edx
0x18000e0f1  mov     eax, [rbp+38h]
0x18000e0f4  cmp     eax, 0E06D7363h
0x18000e0f9  jnz     short loc_18000E10F
0x18000e0fb  mov     rdx, [rbp+0B0h]
0x18000e102  mov     ecx, [rbp+38h]
0x18000e105  call    _XcptFilter_0
0x18000e10a  mov     [rbp+40h], eax
0x18000e10d  jmp     short loc_18000E116
0x18000e10f  mov     dword ptr [rbp+40h], 0
0x18000e116  mov     eax, [rbp+40h]
0x18000e119  add     rsp, 20h
0x18000e11d  pop     rbp
0x18000e11e  retn
0x18000e120  push    rbp
0x18000e122  sub     rsp, 20h
0x18000e126  mov     rbp, rdx
0x18000e129  mov     rax, [rcx]
0x18000e12c  mov     edx, [rax]
0x18000e12e  mov     [rbp+0B8h], rcx
0x18000e135  mov     [rbp+48h], edx
0x18000e138  mov     eax, [rbp+48h]
0x18000e13b  cmp     eax, 0E06D7363h
0x18000e140  jnz     short loc_18000E156
0x18000e142  mov     rdx, [rbp+0B8h]
0x18000e149  mov     ecx, [rbp+48h]
0x18000e14c  call    _XcptFilter_0
0x18000e151  mov     [rbp+50h], eax
0x18000e154  jmp     short loc_18000E15D
0x18000e156  mov     dword ptr [rbp+50h], 0
0x18000e15d  mov     eax, [rbp+50h]
0x18000e160  add     rsp, 20h
0x18000e164  pop     rbp
0x18000e165  retn
0x18000e167  push    rbp
0x18000e169  sub     rsp, 20h
0x18000e16d  mov     rbp, rdx
0x18000e170  mov     rax, [rcx]
0x18000e173  mov     edx, [rax]
0x18000e175  mov     [rbp+0C0h], rcx
0x18000e17c  mov     [rbp+58h], edx
0x18000e17f  mov     eax, [rbp+58h]
0x18000e182  cmp     eax, 0E06D7363h
0x18000e187  jnz     short loc_18000E19D
0x18000e189  mov     rdx, [rbp+0C0h]
0x18000e190  mov     ecx, [rbp+58h]
0x18000e193  call    _XcptFilter_0
0x18000e198  mov     [rbp+60h], eax
0x18000e19b  jmp     short loc_18000E1A4
0x18000e19d  mov     dword ptr [rbp+60h], 0
0x18000e1a4  mov     eax, [rbp+60h]
0x18000e1a7  add     rsp, 20h
0x18000e1ab  pop     rbp
0x18000e1ac  retn
0x18000e1ae  push    rbp
0x18000e1b0  sub     rsp, 20h
0x18000e1b4  mov     rbp, rdx
0x18000e1b7  mov     rax, [rcx]
0x18000e1ba  mov     edx, [rax]
0x18000e1bc  mov     [rbp+0C8h], rcx
0x18000e1c3  mov     [rbp+68h], edx
0x18000e1c6  mov     eax, [rbp+68h]
0x18000e1c9  cmp     eax, 0E06D7363h
0x18000e1ce  jnz     short loc_18000E1E4
0x18000e1d0  mov     rdx, [rbp+0C8h]
0x18000e1d7  mov     ecx, [rbp+68h]
0x18000e1da  call    _XcptFilter_0
0x18000e1df  mov     [rbp+70h], eax
0x18000e1e2  jmp     short loc_18000E1EB
0x18000e1e4  mov     dword ptr [rbp+70h], 0
0x18000e1eb  mov     eax, [rbp+70h]
0x18000e1ee  add     rsp, 20h
0x18000e1f2  pop     rbp
0x18000e1f3  retn
0x18000e1f5  push    rbp
0x18000e1f7  sub     rsp, 20h
0x18000e1fb  mov     rbp, rdx
0x18000e1fe  mov     rax, [rcx]
0x18000e201  mov     edx, [rax]
0x18000e203  mov     [rbp+0D0h], rcx
0x18000e20a  mov     [rbp+78h], edx
0x18000e20d  mov     eax, [rbp+78h]
0x18000e210  cmp     eax, 0E06D7363h
0x18000e215  jnz     short loc_18000E22E
0x18000e217  mov     rdx, [rbp+0D0h]
0x18000e21e  mov     ecx, [rbp+78h]
0x18000e221  call    _XcptFilter_0
0x18000e226  mov     [rbp+80h], eax
0x18000e22c  jmp     short loc_18000E238
0x18000e22e  mov     dword ptr [rbp+80h], 0
0x18000e238  mov     eax, [rbp+80h]
0x18000e23e  add     rsp, 20h
0x18000e242  pop     rbp
0x18000e243  retn
0x18000e245  push    rbp
0x18000e247  sub     rsp, 20h
0x18000e24b  mov     rbp, rdx
0x18000e24e  mov     rax, [rcx]
0x18000e251  mov     edx, [rax]
0x18000e253  mov     [rbp+0D8h], rcx
0x18000e25a  mov     [rbp+88h], edx
0x18000e260  mov     eax, [rbp+88h]
0x18000e266  cmp     eax, 0E06D7363h
0x18000e26b  jnz     short loc_18000E287
0x18000e26d  mov     rdx, [rbp+0D8h]
0x18000e274  mov     ecx, [rbp+88h]
0x18000e27a  call    _XcptFilter_0
0x18000e27f  mov     [rbp+90h], eax
0x18000e285  jmp     short loc_18000E291
0x18000e287  mov     dword ptr [rbp+90h], 0
0x18000e291  mov     eax, [rbp+90h]
0x18000e297  add     rsp, 20h
0x18000e29b  pop     rbp
0x18000e29c  retn
0x18000e29e  push    rbp
0x18000e2a0  sub     rsp, 20h
0x18000e2a4  mov     rbp, rdx
0x18000e2a7  mov     rax, [rcx]
0x18000e2aa  mov     edx, [rax]
0x18000e2ac  mov     [rbp+0E0h], rcx
0x18000e2b3  mov     [rbp+98h], edx
0x18000e2b9  mov     eax, [rbp+98h]
0x18000e2bf  cmp     eax, 0E06D7363h
0x18000e2c4  jnz     short loc_18000E2E0
0x18000e2c6  mov     rdx, [rbp+0E0h]
0x18000e2cd  mov     ecx, [rbp+98h]
0x18000e2d3  call    _XcptFilter_0
0x18000e2d8  mov     [rbp+0A0h], eax
0x18000e2de  jmp     short loc_18000E2EA
0x18000e2e0  mov     dword ptr [rbp+0A0h], 0
0x18000e2ea  mov     eax, [rbp+0A0h]
0x18000e2f0  add     rsp, 20h
0x18000e2f4  pop     rbp
0x18000e2f5  retn
0x18000e2f7  push    rbp
0x18000e2f9  sub     rsp, 20h
0x18000e2fd  mov     rbp, rdx
0x18000e300  cmp     dword ptr [rbp+118h], 1
0x18000e307  ja      short loc_18000E313
0x18000e309  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
