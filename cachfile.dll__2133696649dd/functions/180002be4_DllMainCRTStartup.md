# __DllMainCRTStartup

- ea: `0x180002be4`
- end: `0x180002df0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002ba0`

## callees

- `0x180002970`
- `0x180002be4`
- `0x180002e1a`
- `0x180002ff8`
- `0x180003cb0`

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
  if ( (_DWORD)fdwReason || dword_1800080A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800080A4 = 1;
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
            if ( dword_1800080A4 )
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
0x180002be4  mov     [rsp+lpvReserved], r8
0x180002be9  mov     [rsp+arg_8], edx
0x180002bed  mov     [rsp+arg_0], rcx
0x180002bf2  push    rbx
0x180002bf3  push    rsi
0x180002bf4  push    rdi
0x180002bf5  sub     rsp, 0F0h
0x180002bfc  mov     edi, edx
0x180002bfe  mov     rsi, rcx
0x180002c01  mov     ebx, 1
0x180002c06  cmp     edx, ebx
0x180002c08  ja      short loc_180002C10
0x180002c0a  mov     cs:__native_dllmain_reason, edx
0x180002c10  test    edx, edx
0x180002c12  jnz     short loc_180002C27
0x180002c14  cmp     cs:dword_1800080A0, edx
0x180002c1a  jnz     short loc_180002C27
0x180002c1c  xor     ebx, ebx
0x180002c1e  mov     [rsp+108h+var_E8], ebx
0x180002c22  jmp     loc_180002DD4
0x180002c27  lea     eax, [rdx-1]
0x180002c2a  cmp     eax, 1
0x180002c2d  ja      loc_180002CB4
0x180002c33  mov     rax, cs:_pRawDllMain
0x180002c3a  test    rax, rax
0x180002c3d  jz      short loc_180002C75
0x180002c3f  cmp     edx, 1
0x180002c42  jnz     short loc_180002C4A
0x180002c44  mov     cs:dword_1800080A4, edx
0x180002c4a  mov     r8, [rsp+108h+lpvReserved]
0x180002c52  call    cs:__guard_dispatch_icall_fptr
0x180002c58  mov     ebx, eax
0x180002c5a  mov     [rsp+108h+var_E8], eax
0x180002c5e  jmp     short loc_180002C75
0x180002c60  xor     ebx, ebx
0x180002c62  mov     [rsp+108h+var_E8], ebx
0x180002c66  mov     edi, [rsp+108h+arg_8]
0x180002c6d  mov     rsi, [rsp+108h+arg_0]
0x180002c75  test    ebx, ebx
0x180002c77  jz      loc_180002DD4
0x180002c7d  mov     r8, [rsp+108h+lpvReserved]
0x180002c85  mov     edx, edi
0x180002c87  mov     rcx, rsi
0x180002c8a  call    _CRT_INIT
0x180002c8f  mov     ebx, eax
0x180002c91  mov     [rsp+108h+var_E8], eax
0x180002c95  jmp     short loc_180002CAC
0x180002c97  xor     ebx, ebx
0x180002c99  mov     [rsp+108h+var_E8], ebx
0x180002c9d  mov     edi, [rsp+108h+arg_8]
0x180002ca4  mov     rsi, [rsp+108h+arg_0]
0x180002cac  test    ebx, ebx
0x180002cae  jz      loc_180002DD4
0x180002cb4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002cbc  mov     edx, edi; fdwReason
0x180002cbe  mov     rcx, rsi; hinstDLL
0x180002cc1  call    DllMain
0x180002cc6  mov     ebx, eax
0x180002cc8  mov     [rsp+108h+var_E8], eax
0x180002ccc  jmp     short loc_180002CE3
0x180002cce  xor     ebx, ebx
0x180002cd0  mov     [rsp+108h+var_E8], ebx
0x180002cd4  mov     edi, [rsp+108h+arg_8]
0x180002cdb  mov     rsi, [rsp+108h+arg_0]
0x180002ce3  cmp     edi, 1
0x180002ce6  jnz     short loc_180002D5F
0x180002ce8  test    ebx, ebx
0x180002cea  jnz     short loc_180002D5F
0x180002cec  xor     r8d, r8d; lpvReserved
0x180002cef  xor     edx, edx; fdwReason
0x180002cf1  mov     rcx, rsi; hinstDLL
0x180002cf4  call    DllMain
0x180002cf9  jmp     short loc_180002D0E
0x180002cfb  mov     edi, [rsp+108h+arg_8]
0x180002d02  mov     rsi, [rsp+108h+arg_0]
0x180002d0a  mov     ebx, [rsp+108h+var_E8]
0x180002d0e  xor     r8d, r8d
0x180002d11  xor     edx, edx
0x180002d13  mov     rcx, rsi
0x180002d16  call    _CRT_INIT
0x180002d1b  jmp     short loc_180002D30
0x180002d1d  mov     edi, [rsp+108h+arg_8]
0x180002d24  mov     rsi, [rsp+108h+arg_0]
0x180002d2c  mov     ebx, [rsp+108h+var_E8]
0x180002d30  mov     rax, cs:_pRawDllMain
0x180002d37  test    rax, rax
0x180002d3a  jz      short loc_180002D5F
0x180002d3c  xor     r8d, r8d
0x180002d3f  xor     edx, edx
0x180002d41  mov     rcx, rsi
0x180002d44  call    cs:__guard_dispatch_icall_fptr
0x180002d4a  jmp     short loc_180002D5F
0x180002d4c  mov     edi, [rsp+108h+arg_8]
0x180002d53  mov     rsi, [rsp+108h+arg_0]
0x180002d5b  mov     ebx, [rsp+108h+var_E8]
0x180002d5f  test    edi, edi
0x180002d61  jz      short loc_180002D68
0x180002d63  cmp     edi, 3
0x180002d66  jnz     short loc_180002DD4
0x180002d68  mov     r8, [rsp+108h+lpvReserved]
0x180002d70  mov     edx, edi
0x180002d72  mov     rcx, rsi
0x180002d75  call    _CRT_INIT
0x180002d7a  mov     ebx, eax
0x180002d7c  mov     [rsp+108h+var_E8], eax
0x180002d80  jmp     short loc_180002D97
0x180002d82  xor     ebx, ebx
0x180002d84  mov     [rsp+108h+var_E8], ebx
0x180002d88  mov     edi, [rsp+108h+arg_8]
0x180002d8f  mov     rsi, [rsp+108h+arg_0]
0x180002d97  mov     rax, cs:_pRawDllMain
0x180002d9e  test    rax, rax
0x180002da1  jz      short loc_180002DD4
0x180002da3  cmp     cs:dword_1800080A4, 0
0x180002daa  jz      short loc_180002DD4
0x180002dac  mov     r8, [rsp+108h+lpvReserved]
0x180002db4  mov     edx, edi
0x180002db6  mov     rcx, rsi
0x180002db9  call    cs:__guard_dispatch_icall_fptr
0x180002dbf  mov     ebx, eax
0x180002dc1  mov     [rsp+108h+var_E8], eax
0x180002dc5  jmp     short loc_180002DD4
0x180002dc7  xor     ebx, ebx
0x180002dc9  mov     [rsp+108h+var_E8], ebx
0x180002dcd  mov     edi, [rsp+108h+arg_8]
0x180002dd4  cmp     edi, 1
0x180002dd7  ja      short loc_180002DE3
0x180002dd9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002de3  mov     eax, ebx
0x180002de5  add     rsp, 0F0h
0x180002dec  pop     rdi
0x180002ded  pop     rsi
0x180002dee  pop     rbx
0x180002def  retn
0x180003d20  push    rbp
0x180003d22  sub     rsp, 20h
0x180003d26  mov     rbp, rdx
0x180003d29  mov     rax, [rcx]
0x180003d2c  mov     edx, [rax]
0x180003d2e  mov     [rbp+0A8h], rcx
0x180003d35  mov     [rbp+28h], edx
0x180003d38  mov     eax, [rbp+28h]
0x180003d3b  cmp     eax, 0E06D7363h
0x180003d40  jnz     short loc_180003D56
0x180003d42  mov     rdx, [rbp+0A8h]
0x180003d49  mov     ecx, [rbp+28h]
0x180003d4c  call    _XcptFilter_0
0x180003d51  mov     [rbp+30h], eax
0x180003d54  jmp     short loc_180003D5D
0x180003d56  mov     dword ptr [rbp+30h], 0
0x180003d5d  mov     eax, [rbp+30h]
0x180003d60  add     rsp, 20h
0x180003d64  pop     rbp
0x180003d65  retn
0x180003d67  push    rbp
0x180003d69  sub     rsp, 20h
0x180003d6d  mov     rbp, rdx
0x180003d70  mov     rax, [rcx]
0x180003d73  mov     edx, [rax]
0x180003d75  mov     [rbp+0B0h], rcx
0x180003d7c  mov     [rbp+38h], edx
0x180003d7f  mov     eax, [rbp+38h]
0x180003d82  cmp     eax, 0E06D7363h
0x180003d87  jnz     short loc_180003D9D
0x180003d89  mov     rdx, [rbp+0B0h]
0x180003d90  mov     ecx, [rbp+38h]
0x180003d93  call    _XcptFilter_0
0x180003d98  mov     [rbp+40h], eax
0x180003d9b  jmp     short loc_180003DA4
0x180003d9d  mov     dword ptr [rbp+40h], 0
0x180003da4  mov     eax, [rbp+40h]
0x180003da7  add     rsp, 20h
0x180003dab  pop     rbp
0x180003dac  retn
0x180003dae  push    rbp
0x180003db0  sub     rsp, 20h
0x180003db4  mov     rbp, rdx
0x180003db7  mov     rax, [rcx]
0x180003dba  mov     edx, [rax]
0x180003dbc  mov     [rbp+0B8h], rcx
0x180003dc3  mov     [rbp+48h], edx
0x180003dc6  mov     eax, [rbp+48h]
0x180003dc9  cmp     eax, 0E06D7363h
0x180003dce  jnz     short loc_180003DE4
0x180003dd0  mov     rdx, [rbp+0B8h]
0x180003dd7  mov     ecx, [rbp+48h]
0x180003dda  call    _XcptFilter_0
0x180003ddf  mov     [rbp+50h], eax
0x180003de2  jmp     short loc_180003DEB
0x180003de4  mov     dword ptr [rbp+50h], 0
0x180003deb  mov     eax, [rbp+50h]
0x180003dee  add     rsp, 20h
0x180003df2  pop     rbp
0x180003df3  retn
0x180003df5  push    rbp
0x180003df7  sub     rsp, 20h
0x180003dfb  mov     rbp, rdx
0x180003dfe  mov     rax, [rcx]
0x180003e01  mov     edx, [rax]
0x180003e03  mov     [rbp+0C0h], rcx
0x180003e0a  mov     [rbp+58h], edx
0x180003e0d  mov     eax, [rbp+58h]
0x180003e10  cmp     eax, 0E06D7363h
0x180003e15  jnz     short loc_180003E2B
0x180003e17  mov     rdx, [rbp+0C0h]
0x180003e1e  mov     ecx, [rbp+58h]
0x180003e21  call    _XcptFilter_0
0x180003e26  mov     [rbp+60h], eax
0x180003e29  jmp     short loc_180003E32
0x180003e2b  mov     dword ptr [rbp+60h], 0
0x180003e32  mov     eax, [rbp+60h]
0x180003e35  add     rsp, 20h
0x180003e39  pop     rbp
0x180003e3a  retn
0x180003e3c  push    rbp
0x180003e3e  sub     rsp, 20h
0x180003e42  mov     rbp, rdx
0x180003e45  mov     rax, [rcx]
0x180003e48  mov     edx, [rax]
0x180003e4a  mov     [rbp+0C8h], rcx
0x180003e51  mov     [rbp+68h], edx
0x180003e54  mov     eax, [rbp+68h]
0x180003e57  cmp     eax, 0E06D7363h
0x180003e5c  jnz     short loc_180003E72
0x180003e5e  mov     rdx, [rbp+0C8h]
0x180003e65  mov     ecx, [rbp+68h]
0x180003e68  call    _XcptFilter_0
0x180003e6d  mov     [rbp+70h], eax
0x180003e70  jmp     short loc_180003E79
0x180003e72  mov     dword ptr [rbp+70h], 0
0x180003e79  mov     eax, [rbp+70h]
0x180003e7c  add     rsp, 20h
0x180003e80  pop     rbp
0x180003e81  retn
0x180003e83  push    rbp
0x180003e85  sub     rsp, 20h
0x180003e89  mov     rbp, rdx
0x180003e8c  mov     rax, [rcx]
0x180003e8f  mov     edx, [rax]
0x180003e91  mov     [rbp+0D0h], rcx
0x180003e98  mov     [rbp+78h], edx
0x180003e9b  mov     eax, [rbp+78h]
0x180003e9e  cmp     eax, 0E06D7363h
0x180003ea3  jnz     short loc_180003EBC
0x180003ea5  mov     rdx, [rbp+0D0h]
0x180003eac  mov     ecx, [rbp+78h]
0x180003eaf  call    _XcptFilter_0
0x180003eb4  mov     [rbp+80h], eax
0x180003eba  jmp     short loc_180003EC6
0x180003ebc  mov     dword ptr [rbp+80h], 0
0x180003ec6  mov     eax, [rbp+80h]
0x180003ecc  add     rsp, 20h
0x180003ed0  pop     rbp
0x180003ed1  retn
0x180003ed3  push    rbp
0x180003ed5  sub     rsp, 20h
0x180003ed9  mov     rbp, rdx
0x180003edc  mov     rax, [rcx]
0x180003edf  mov     edx, [rax]
0x180003ee1  mov     [rbp+0D8h], rcx
0x180003ee8  mov     [rbp+88h], edx
0x180003eee  mov     eax, [rbp+88h]
0x180003ef4  cmp     eax, 0E06D7363h
0x180003ef9  jnz     short loc_180003F15
0x180003efb  mov     rdx, [rbp+0D8h]
0x180003f02  mov     ecx, [rbp+88h]
0x180003f08  call    _XcptFilter_0
0x180003f0d  mov     [rbp+90h], eax
0x180003f13  jmp     short loc_180003F1F
0x180003f15  mov     dword ptr [rbp+90h], 0
0x180003f1f  mov     eax, [rbp+90h]
0x180003f25  add     rsp, 20h
0x180003f29  pop     rbp
0x180003f2a  retn
0x180003f2c  push    rbp
0x180003f2e  sub     rsp, 20h
0x180003f32  mov     rbp, rdx
0x180003f35  mov     rax, [rcx]
0x180003f38  mov     edx, [rax]
0x180003f3a  mov     [rbp+0E0h], rcx
0x180003f41  mov     [rbp+98h], edx
0x180003f47  mov     eax, [rbp+98h]
0x180003f4d  cmp     eax, 0E06D7363h
0x180003f52  jnz     short loc_180003F6E
0x180003f54  mov     rdx, [rbp+0E0h]
0x180003f5b  mov     ecx, [rbp+98h]
0x180003f61  call    _XcptFilter_0
0x180003f66  mov     [rbp+0A0h], eax
0x180003f6c  jmp     short loc_180003F78
0x180003f6e  mov     dword ptr [rbp+0A0h], 0
0x180003f78  mov     eax, [rbp+0A0h]
0x180003f7e  add     rsp, 20h
0x180003f82  pop     rbp
0x180003f83  retn
0x180003f85  push    rbp
0x180003f87  sub     rsp, 20h
0x180003f8b  mov     rbp, rdx
0x180003f8e  cmp     dword ptr [rbp+118h], 1
0x180003f95  ja      short loc_180003FA1
0x180003f97  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
