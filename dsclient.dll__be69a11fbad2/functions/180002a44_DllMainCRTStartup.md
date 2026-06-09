# __DllMainCRTStartup

- ea: `0x180002a44`
- end: `0x180002c50`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002a00`

## callees

- `0x1800027d0`
- `0x180002a44`
- `0x180002c56`
- `0x180002e28`
- `0x180009990`

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
  if ( (_DWORD)fdwReason || dword_18000F240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F244 = 1;
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
            if ( dword_18000F244 )
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
0x180002a44  mov     [rsp+lpvReserved], r8
0x180002a49  mov     [rsp+arg_8], edx
0x180002a4d  mov     [rsp+arg_0], rcx
0x180002a52  push    rbx
0x180002a53  push    rsi
0x180002a54  push    rdi
0x180002a55  sub     rsp, 0F0h
0x180002a5c  mov     edi, edx
0x180002a5e  mov     rsi, rcx
0x180002a61  mov     ebx, 1
0x180002a66  cmp     edx, ebx
0x180002a68  ja      short loc_180002A70
0x180002a6a  mov     cs:__native_dllmain_reason, edx
0x180002a70  test    edx, edx
0x180002a72  jnz     short loc_180002A87
0x180002a74  cmp     cs:dword_18000F240, edx
0x180002a7a  jnz     short loc_180002A87
0x180002a7c  xor     ebx, ebx
0x180002a7e  mov     [rsp+108h+var_E8], ebx
0x180002a82  jmp     loc_180002C34
0x180002a87  lea     eax, [rdx-1]
0x180002a8a  cmp     eax, 1
0x180002a8d  ja      loc_180002B14
0x180002a93  mov     rax, cs:_pRawDllMain
0x180002a9a  test    rax, rax
0x180002a9d  jz      short loc_180002AD5
0x180002a9f  cmp     edx, 1
0x180002aa2  jnz     short loc_180002AAA
0x180002aa4  mov     cs:dword_18000F244, edx
0x180002aaa  mov     r8, [rsp+108h+lpvReserved]
0x180002ab2  call    cs:__guard_dispatch_icall_fptr
0x180002ab8  mov     ebx, eax
0x180002aba  mov     [rsp+108h+var_E8], eax
0x180002abe  jmp     short loc_180002AD5
0x180002ac0  xor     ebx, ebx
0x180002ac2  mov     [rsp+108h+var_E8], ebx
0x180002ac6  mov     edi, [rsp+108h+arg_8]
0x180002acd  mov     rsi, [rsp+108h+arg_0]
0x180002ad5  test    ebx, ebx
0x180002ad7  jz      loc_180002C34
0x180002add  mov     r8, [rsp+108h+lpvReserved]
0x180002ae5  mov     edx, edi
0x180002ae7  mov     rcx, rsi
0x180002aea  call    _CRT_INIT
0x180002aef  mov     ebx, eax
0x180002af1  mov     [rsp+108h+var_E8], eax
0x180002af5  jmp     short loc_180002B0C
0x180002af7  xor     ebx, ebx
0x180002af9  mov     [rsp+108h+var_E8], ebx
0x180002afd  mov     edi, [rsp+108h+arg_8]
0x180002b04  mov     rsi, [rsp+108h+arg_0]
0x180002b0c  test    ebx, ebx
0x180002b0e  jz      loc_180002C34
0x180002b14  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002b1c  mov     edx, edi; fdwReason
0x180002b1e  mov     rcx, rsi; hinstDLL
0x180002b21  call    DllMain
0x180002b26  mov     ebx, eax
0x180002b28  mov     [rsp+108h+var_E8], eax
0x180002b2c  jmp     short loc_180002B43
0x180002b2e  xor     ebx, ebx
0x180002b30  mov     [rsp+108h+var_E8], ebx
0x180002b34  mov     edi, [rsp+108h+arg_8]
0x180002b3b  mov     rsi, [rsp+108h+arg_0]
0x180002b43  cmp     edi, 1
0x180002b46  jnz     short loc_180002BBF
0x180002b48  test    ebx, ebx
0x180002b4a  jnz     short loc_180002BBF
0x180002b4c  xor     r8d, r8d; lpvReserved
0x180002b4f  xor     edx, edx; fdwReason
0x180002b51  mov     rcx, rsi; hinstDLL
0x180002b54  call    DllMain
0x180002b59  jmp     short loc_180002B6E
0x180002b5b  mov     edi, [rsp+108h+arg_8]
0x180002b62  mov     rsi, [rsp+108h+arg_0]
0x180002b6a  mov     ebx, [rsp+108h+var_E8]
0x180002b6e  xor     r8d, r8d
0x180002b71  xor     edx, edx
0x180002b73  mov     rcx, rsi
0x180002b76  call    _CRT_INIT
0x180002b7b  jmp     short loc_180002B90
0x180002b7d  mov     edi, [rsp+108h+arg_8]
0x180002b84  mov     rsi, [rsp+108h+arg_0]
0x180002b8c  mov     ebx, [rsp+108h+var_E8]
0x180002b90  mov     rax, cs:_pRawDllMain
0x180002b97  test    rax, rax
0x180002b9a  jz      short loc_180002BBF
0x180002b9c  xor     r8d, r8d
0x180002b9f  xor     edx, edx
0x180002ba1  mov     rcx, rsi
0x180002ba4  call    cs:__guard_dispatch_icall_fptr
0x180002baa  jmp     short loc_180002BBF
0x180002bac  mov     edi, [rsp+108h+arg_8]
0x180002bb3  mov     rsi, [rsp+108h+arg_0]
0x180002bbb  mov     ebx, [rsp+108h+var_E8]
0x180002bbf  test    edi, edi
0x180002bc1  jz      short loc_180002BC8
0x180002bc3  cmp     edi, 3
0x180002bc6  jnz     short loc_180002C34
0x180002bc8  mov     r8, [rsp+108h+lpvReserved]
0x180002bd0  mov     edx, edi
0x180002bd2  mov     rcx, rsi
0x180002bd5  call    _CRT_INIT
0x180002bda  mov     ebx, eax
0x180002bdc  mov     [rsp+108h+var_E8], eax
0x180002be0  jmp     short loc_180002BF7
0x180002be2  xor     ebx, ebx
0x180002be4  mov     [rsp+108h+var_E8], ebx
0x180002be8  mov     edi, [rsp+108h+arg_8]
0x180002bef  mov     rsi, [rsp+108h+arg_0]
0x180002bf7  mov     rax, cs:_pRawDllMain
0x180002bfe  test    rax, rax
0x180002c01  jz      short loc_180002C34
0x180002c03  cmp     cs:dword_18000F244, 0
0x180002c0a  jz      short loc_180002C34
0x180002c0c  mov     r8, [rsp+108h+lpvReserved]
0x180002c14  mov     edx, edi
0x180002c16  mov     rcx, rsi
0x180002c19  call    cs:__guard_dispatch_icall_fptr
0x180002c1f  mov     ebx, eax
0x180002c21  mov     [rsp+108h+var_E8], eax
0x180002c25  jmp     short loc_180002C34
0x180002c27  xor     ebx, ebx
0x180002c29  mov     [rsp+108h+var_E8], ebx
0x180002c2d  mov     edi, [rsp+108h+arg_8]
0x180002c34  cmp     edi, 1
0x180002c37  ja      short loc_180002C43
0x180002c39  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002c43  mov     eax, ebx
0x180002c45  add     rsp, 0F0h
0x180002c4c  pop     rdi
0x180002c4d  pop     rsi
0x180002c4e  pop     rbx
0x180002c4f  retn
0x180009b12  push    rbp
0x180009b14  sub     rsp, 20h
0x180009b18  mov     rbp, rdx
0x180009b1b  mov     rax, [rcx]
0x180009b1e  mov     edx, [rax]
0x180009b20  mov     [rbp+0A8h], rcx
0x180009b27  mov     [rbp+28h], edx
0x180009b2a  mov     eax, [rbp+28h]
0x180009b2d  cmp     eax, 0E06D7363h
0x180009b32  jnz     short loc_180009B48
0x180009b34  mov     rdx, [rbp+0A8h]
0x180009b3b  mov     ecx, [rbp+28h]
0x180009b3e  call    _XcptFilter_0
0x180009b43  mov     [rbp+30h], eax
0x180009b46  jmp     short loc_180009B4F
0x180009b48  mov     dword ptr [rbp+30h], 0
0x180009b4f  mov     eax, [rbp+30h]
0x180009b52  add     rsp, 20h
0x180009b56  pop     rbp
0x180009b57  retn
0x180009b59  push    rbp
0x180009b5b  sub     rsp, 20h
0x180009b5f  mov     rbp, rdx
0x180009b62  mov     rax, [rcx]
0x180009b65  mov     edx, [rax]
0x180009b67  mov     [rbp+0B0h], rcx
0x180009b6e  mov     [rbp+38h], edx
0x180009b71  mov     eax, [rbp+38h]
0x180009b74  cmp     eax, 0E06D7363h
0x180009b79  jnz     short loc_180009B8F
0x180009b7b  mov     rdx, [rbp+0B0h]
0x180009b82  mov     ecx, [rbp+38h]
0x180009b85  call    _XcptFilter_0
0x180009b8a  mov     [rbp+40h], eax
0x180009b8d  jmp     short loc_180009B96
0x180009b8f  mov     dword ptr [rbp+40h], 0
0x180009b96  mov     eax, [rbp+40h]
0x180009b99  add     rsp, 20h
0x180009b9d  pop     rbp
0x180009b9e  retn
0x180009ba0  push    rbp
0x180009ba2  sub     rsp, 20h
0x180009ba6  mov     rbp, rdx
0x180009ba9  mov     rax, [rcx]
0x180009bac  mov     edx, [rax]
0x180009bae  mov     [rbp+0B8h], rcx
0x180009bb5  mov     [rbp+48h], edx
0x180009bb8  mov     eax, [rbp+48h]
0x180009bbb  cmp     eax, 0E06D7363h
0x180009bc0  jnz     short loc_180009BD6
0x180009bc2  mov     rdx, [rbp+0B8h]
0x180009bc9  mov     ecx, [rbp+48h]
0x180009bcc  call    _XcptFilter_0
0x180009bd1  mov     [rbp+50h], eax
0x180009bd4  jmp     short loc_180009BDD
0x180009bd6  mov     dword ptr [rbp+50h], 0
0x180009bdd  mov     eax, [rbp+50h]
0x180009be0  add     rsp, 20h
0x180009be4  pop     rbp
0x180009be5  retn
0x180009be7  push    rbp
0x180009be9  sub     rsp, 20h
0x180009bed  mov     rbp, rdx
0x180009bf0  mov     rax, [rcx]
0x180009bf3  mov     edx, [rax]
0x180009bf5  mov     [rbp+0C0h], rcx
0x180009bfc  mov     [rbp+58h], edx
0x180009bff  mov     eax, [rbp+58h]
0x180009c02  cmp     eax, 0E06D7363h
0x180009c07  jnz     short loc_180009C1D
0x180009c09  mov     rdx, [rbp+0C0h]
0x180009c10  mov     ecx, [rbp+58h]
0x180009c13  call    _XcptFilter_0
0x180009c18  mov     [rbp+60h], eax
0x180009c1b  jmp     short loc_180009C24
0x180009c1d  mov     dword ptr [rbp+60h], 0
0x180009c24  mov     eax, [rbp+60h]
0x180009c27  add     rsp, 20h
0x180009c2b  pop     rbp
0x180009c2c  retn
0x180009c2e  push    rbp
0x180009c30  sub     rsp, 20h
0x180009c34  mov     rbp, rdx
0x180009c37  mov     rax, [rcx]
0x180009c3a  mov     edx, [rax]
0x180009c3c  mov     [rbp+0C8h], rcx
0x180009c43  mov     [rbp+68h], edx
0x180009c46  mov     eax, [rbp+68h]
0x180009c49  cmp     eax, 0E06D7363h
0x180009c4e  jnz     short loc_180009C64
0x180009c50  mov     rdx, [rbp+0C8h]
0x180009c57  mov     ecx, [rbp+68h]
0x180009c5a  call    _XcptFilter_0
0x180009c5f  mov     [rbp+70h], eax
0x180009c62  jmp     short loc_180009C6B
0x180009c64  mov     dword ptr [rbp+70h], 0
0x180009c6b  mov     eax, [rbp+70h]
0x180009c6e  add     rsp, 20h
0x180009c72  pop     rbp
0x180009c73  retn
0x180009c75  push    rbp
0x180009c77  sub     rsp, 20h
0x180009c7b  mov     rbp, rdx
0x180009c7e  mov     rax, [rcx]
0x180009c81  mov     edx, [rax]
0x180009c83  mov     [rbp+0D0h], rcx
0x180009c8a  mov     [rbp+78h], edx
0x180009c8d  mov     eax, [rbp+78h]
0x180009c90  cmp     eax, 0E06D7363h
0x180009c95  jnz     short loc_180009CAE
0x180009c97  mov     rdx, [rbp+0D0h]
0x180009c9e  mov     ecx, [rbp+78h]
0x180009ca1  call    _XcptFilter_0
0x180009ca6  mov     [rbp+80h], eax
0x180009cac  jmp     short loc_180009CB8
0x180009cae  mov     dword ptr [rbp+80h], 0
0x180009cb8  mov     eax, [rbp+80h]
0x180009cbe  add     rsp, 20h
0x180009cc2  pop     rbp
0x180009cc3  retn
0x180009cc5  push    rbp
0x180009cc7  sub     rsp, 20h
0x180009ccb  mov     rbp, rdx
0x180009cce  mov     rax, [rcx]
0x180009cd1  mov     edx, [rax]
0x180009cd3  mov     [rbp+0D8h], rcx
0x180009cda  mov     [rbp+88h], edx
0x180009ce0  mov     eax, [rbp+88h]
0x180009ce6  cmp     eax, 0E06D7363h
0x180009ceb  jnz     short loc_180009D07
0x180009ced  mov     rdx, [rbp+0D8h]
0x180009cf4  mov     ecx, [rbp+88h]
0x180009cfa  call    _XcptFilter_0
0x180009cff  mov     [rbp+90h], eax
0x180009d05  jmp     short loc_180009D11
0x180009d07  mov     dword ptr [rbp+90h], 0
0x180009d11  mov     eax, [rbp+90h]
0x180009d17  add     rsp, 20h
0x180009d1b  pop     rbp
0x180009d1c  retn
0x180009d1e  push    rbp
0x180009d20  sub     rsp, 20h
0x180009d24  mov     rbp, rdx
0x180009d27  mov     rax, [rcx]
0x180009d2a  mov     edx, [rax]
0x180009d2c  mov     [rbp+0E0h], rcx
0x180009d33  mov     [rbp+98h], edx
0x180009d39  mov     eax, [rbp+98h]
0x180009d3f  cmp     eax, 0E06D7363h
0x180009d44  jnz     short loc_180009D60
0x180009d46  mov     rdx, [rbp+0E0h]
0x180009d4d  mov     ecx, [rbp+98h]
0x180009d53  call    _XcptFilter_0
0x180009d58  mov     [rbp+0A0h], eax
0x180009d5e  jmp     short loc_180009D6A
0x180009d60  mov     dword ptr [rbp+0A0h], 0
0x180009d6a  mov     eax, [rbp+0A0h]
0x180009d70  add     rsp, 20h
0x180009d74  pop     rbp
0x180009d75  retn
0x180009d77  push    rbp
0x180009d79  sub     rsp, 20h
0x180009d7d  mov     rbp, rdx
0x180009d80  cmp     dword ptr [rbp+118h], 1
0x180009d87  ja      short loc_180009D93
0x180009d89  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
