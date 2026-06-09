# __DllMainCRTStartup

- ea: `0x180007ae4`
- end: `0x180007cf0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007aa0`

## callees

- `0x180003220`
- `0x180007870`
- `0x180007ae4`
- `0x180008014`
- `0x18000c070`

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
  if ( (_DWORD)fdwReason || dword_180014240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014244 = 1;
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
            if ( dword_180014244 )
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
0x180007ae4  mov     [rsp+lpvReserved], r8
0x180007ae9  mov     [rsp+arg_8], edx
0x180007aed  mov     [rsp+arg_0], rcx
0x180007af2  push    rbx
0x180007af3  push    rsi
0x180007af4  push    rdi
0x180007af5  sub     rsp, 0F0h
0x180007afc  mov     edi, edx
0x180007afe  mov     rsi, rcx
0x180007b01  mov     ebx, 1
0x180007b06  cmp     edx, ebx
0x180007b08  ja      short loc_180007B10
0x180007b0a  mov     cs:__native_dllmain_reason, edx
0x180007b10  test    edx, edx
0x180007b12  jnz     short loc_180007B27
0x180007b14  cmp     cs:dword_180014240, edx
0x180007b1a  jnz     short loc_180007B27
0x180007b1c  xor     ebx, ebx
0x180007b1e  mov     [rsp+108h+var_E8], ebx
0x180007b22  jmp     loc_180007CD4
0x180007b27  lea     eax, [rdx-1]
0x180007b2a  cmp     eax, 1
0x180007b2d  ja      loc_180007BB4
0x180007b33  mov     rax, cs:_pRawDllMain
0x180007b3a  test    rax, rax
0x180007b3d  jz      short loc_180007B75
0x180007b3f  cmp     edx, 1
0x180007b42  jnz     short loc_180007B4A
0x180007b44  mov     cs:dword_180014244, edx
0x180007b4a  mov     r8, [rsp+108h+lpvReserved]
0x180007b52  call    cs:__guard_dispatch_icall_fptr
0x180007b58  mov     ebx, eax
0x180007b5a  mov     [rsp+108h+var_E8], eax
0x180007b5e  jmp     short loc_180007B75
0x180007b60  xor     ebx, ebx
0x180007b62  mov     [rsp+108h+var_E8], ebx
0x180007b66  mov     edi, [rsp+108h+arg_8]
0x180007b6d  mov     rsi, [rsp+108h+arg_0]
0x180007b75  test    ebx, ebx
0x180007b77  jz      loc_180007CD4
0x180007b7d  mov     r8, [rsp+108h+lpvReserved]
0x180007b85  mov     edx, edi
0x180007b87  mov     rcx, rsi
0x180007b8a  call    _CRT_INIT
0x180007b8f  mov     ebx, eax
0x180007b91  mov     [rsp+108h+var_E8], eax
0x180007b95  jmp     short loc_180007BAC
0x180007b97  xor     ebx, ebx
0x180007b99  mov     [rsp+108h+var_E8], ebx
0x180007b9d  mov     edi, [rsp+108h+arg_8]
0x180007ba4  mov     rsi, [rsp+108h+arg_0]
0x180007bac  test    ebx, ebx
0x180007bae  jz      loc_180007CD4
0x180007bb4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180007bbc  mov     edx, edi; fdwReason
0x180007bbe  mov     rcx, rsi; hinstDLL
0x180007bc1  call    DllMain
0x180007bc6  mov     ebx, eax
0x180007bc8  mov     [rsp+108h+var_E8], eax
0x180007bcc  jmp     short loc_180007BE3
0x180007bce  xor     ebx, ebx
0x180007bd0  mov     [rsp+108h+var_E8], ebx
0x180007bd4  mov     edi, [rsp+108h+arg_8]
0x180007bdb  mov     rsi, [rsp+108h+arg_0]
0x180007be3  cmp     edi, 1
0x180007be6  jnz     short loc_180007C5F
0x180007be8  test    ebx, ebx
0x180007bea  jnz     short loc_180007C5F
0x180007bec  xor     r8d, r8d; lpvReserved
0x180007bef  xor     edx, edx; fdwReason
0x180007bf1  mov     rcx, rsi; hinstDLL
0x180007bf4  call    DllMain
0x180007bf9  jmp     short loc_180007C0E
0x180007bfb  mov     edi, [rsp+108h+arg_8]
0x180007c02  mov     rsi, [rsp+108h+arg_0]
0x180007c0a  mov     ebx, [rsp+108h+var_E8]
0x180007c0e  xor     r8d, r8d
0x180007c11  xor     edx, edx
0x180007c13  mov     rcx, rsi
0x180007c16  call    _CRT_INIT
0x180007c1b  jmp     short loc_180007C30
0x180007c1d  mov     edi, [rsp+108h+arg_8]
0x180007c24  mov     rsi, [rsp+108h+arg_0]
0x180007c2c  mov     ebx, [rsp+108h+var_E8]
0x180007c30  mov     rax, cs:_pRawDllMain
0x180007c37  test    rax, rax
0x180007c3a  jz      short loc_180007C5F
0x180007c3c  xor     r8d, r8d
0x180007c3f  xor     edx, edx
0x180007c41  mov     rcx, rsi
0x180007c44  call    cs:__guard_dispatch_icall_fptr
0x180007c4a  jmp     short loc_180007C5F
0x180007c4c  mov     edi, [rsp+108h+arg_8]
0x180007c53  mov     rsi, [rsp+108h+arg_0]
0x180007c5b  mov     ebx, [rsp+108h+var_E8]
0x180007c5f  test    edi, edi
0x180007c61  jz      short loc_180007C68
0x180007c63  cmp     edi, 3
0x180007c66  jnz     short loc_180007CD4
0x180007c68  mov     r8, [rsp+108h+lpvReserved]
0x180007c70  mov     edx, edi
0x180007c72  mov     rcx, rsi
0x180007c75  call    _CRT_INIT
0x180007c7a  mov     ebx, eax
0x180007c7c  mov     [rsp+108h+var_E8], eax
0x180007c80  jmp     short loc_180007C97
0x180007c82  xor     ebx, ebx
0x180007c84  mov     [rsp+108h+var_E8], ebx
0x180007c88  mov     edi, [rsp+108h+arg_8]
0x180007c8f  mov     rsi, [rsp+108h+arg_0]
0x180007c97  mov     rax, cs:_pRawDllMain
0x180007c9e  test    rax, rax
0x180007ca1  jz      short loc_180007CD4
0x180007ca3  cmp     cs:dword_180014244, 0
0x180007caa  jz      short loc_180007CD4
0x180007cac  mov     r8, [rsp+108h+lpvReserved]
0x180007cb4  mov     edx, edi
0x180007cb6  mov     rcx, rsi
0x180007cb9  call    cs:__guard_dispatch_icall_fptr
0x180007cbf  mov     ebx, eax
0x180007cc1  mov     [rsp+108h+var_E8], eax
0x180007cc5  jmp     short loc_180007CD4
0x180007cc7  xor     ebx, ebx
0x180007cc9  mov     [rsp+108h+var_E8], ebx
0x180007ccd  mov     edi, [rsp+108h+arg_8]
0x180007cd4  cmp     edi, 1
0x180007cd7  ja      short loc_180007CE3
0x180007cd9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180007ce3  mov     eax, ebx
0x180007ce5  add     rsp, 0F0h
0x180007cec  pop     rdi
0x180007ced  pop     rsi
0x180007cee  pop     rbx
0x180007cef  retn
0x18000c1e4  push    rbp
0x18000c1e6  sub     rsp, 20h
0x18000c1ea  mov     rbp, rdx
0x18000c1ed  mov     rax, [rcx]
0x18000c1f0  mov     edx, [rax]
0x18000c1f2  mov     [rbp+0A8h], rcx
0x18000c1f9  mov     [rbp+28h], edx
0x18000c1fc  mov     eax, [rbp+28h]
0x18000c1ff  cmp     eax, 0E06D7363h
0x18000c204  jnz     short loc_18000C21A
0x18000c206  mov     rdx, [rbp+0A8h]
0x18000c20d  mov     ecx, [rbp+28h]
0x18000c210  call    _XcptFilter_0
0x18000c215  mov     [rbp+30h], eax
0x18000c218  jmp     short loc_18000C221
0x18000c21a  mov     dword ptr [rbp+30h], 0
0x18000c221  mov     eax, [rbp+30h]
0x18000c224  add     rsp, 20h
0x18000c228  pop     rbp
0x18000c229  retn
0x18000c22b  push    rbp
0x18000c22d  sub     rsp, 20h
0x18000c231  mov     rbp, rdx
0x18000c234  mov     rax, [rcx]
0x18000c237  mov     edx, [rax]
0x18000c239  mov     [rbp+0B0h], rcx
0x18000c240  mov     [rbp+38h], edx
0x18000c243  mov     eax, [rbp+38h]
0x18000c246  cmp     eax, 0E06D7363h
0x18000c24b  jnz     short loc_18000C261
0x18000c24d  mov     rdx, [rbp+0B0h]
0x18000c254  mov     ecx, [rbp+38h]
0x18000c257  call    _XcptFilter_0
0x18000c25c  mov     [rbp+40h], eax
0x18000c25f  jmp     short loc_18000C268
0x18000c261  mov     dword ptr [rbp+40h], 0
0x18000c268  mov     eax, [rbp+40h]
0x18000c26b  add     rsp, 20h
0x18000c26f  pop     rbp
0x18000c270  retn
0x18000c272  push    rbp
0x18000c274  sub     rsp, 20h
0x18000c278  mov     rbp, rdx
0x18000c27b  mov     rax, [rcx]
0x18000c27e  mov     edx, [rax]
0x18000c280  mov     [rbp+0B8h], rcx
0x18000c287  mov     [rbp+48h], edx
0x18000c28a  mov     eax, [rbp+48h]
0x18000c28d  cmp     eax, 0E06D7363h
0x18000c292  jnz     short loc_18000C2A8
0x18000c294  mov     rdx, [rbp+0B8h]
0x18000c29b  mov     ecx, [rbp+48h]
0x18000c29e  call    _XcptFilter_0
0x18000c2a3  mov     [rbp+50h], eax
0x18000c2a6  jmp     short loc_18000C2AF
0x18000c2a8  mov     dword ptr [rbp+50h], 0
0x18000c2af  mov     eax, [rbp+50h]
0x18000c2b2  add     rsp, 20h
0x18000c2b6  pop     rbp
0x18000c2b7  retn
0x18000c2b9  push    rbp
0x18000c2bb  sub     rsp, 20h
0x18000c2bf  mov     rbp, rdx
0x18000c2c2  mov     rax, [rcx]
0x18000c2c5  mov     edx, [rax]
0x18000c2c7  mov     [rbp+0C0h], rcx
0x18000c2ce  mov     [rbp+58h], edx
0x18000c2d1  mov     eax, [rbp+58h]
0x18000c2d4  cmp     eax, 0E06D7363h
0x18000c2d9  jnz     short loc_18000C2EF
0x18000c2db  mov     rdx, [rbp+0C0h]
0x18000c2e2  mov     ecx, [rbp+58h]
0x18000c2e5  call    _XcptFilter_0
0x18000c2ea  mov     [rbp+60h], eax
0x18000c2ed  jmp     short loc_18000C2F6
0x18000c2ef  mov     dword ptr [rbp+60h], 0
0x18000c2f6  mov     eax, [rbp+60h]
0x18000c2f9  add     rsp, 20h
0x18000c2fd  pop     rbp
0x18000c2fe  retn
0x18000c300  push    rbp
0x18000c302  sub     rsp, 20h
0x18000c306  mov     rbp, rdx
0x18000c309  mov     rax, [rcx]
0x18000c30c  mov     edx, [rax]
0x18000c30e  mov     [rbp+0C8h], rcx
0x18000c315  mov     [rbp+68h], edx
0x18000c318  mov     eax, [rbp+68h]
0x18000c31b  cmp     eax, 0E06D7363h
0x18000c320  jnz     short loc_18000C336
0x18000c322  mov     rdx, [rbp+0C8h]
0x18000c329  mov     ecx, [rbp+68h]
0x18000c32c  call    _XcptFilter_0
0x18000c331  mov     [rbp+70h], eax
0x18000c334  jmp     short loc_18000C33D
0x18000c336  mov     dword ptr [rbp+70h], 0
0x18000c33d  mov     eax, [rbp+70h]
0x18000c340  add     rsp, 20h
0x18000c344  pop     rbp
0x18000c345  retn
0x18000c347  push    rbp
0x18000c349  sub     rsp, 20h
0x18000c34d  mov     rbp, rdx
0x18000c350  mov     rax, [rcx]
0x18000c353  mov     edx, [rax]
0x18000c355  mov     [rbp+0D0h], rcx
0x18000c35c  mov     [rbp+78h], edx
0x18000c35f  mov     eax, [rbp+78h]
0x18000c362  cmp     eax, 0E06D7363h
0x18000c367  jnz     short loc_18000C380
0x18000c369  mov     rdx, [rbp+0D0h]
0x18000c370  mov     ecx, [rbp+78h]
0x18000c373  call    _XcptFilter_0
0x18000c378  mov     [rbp+80h], eax
0x18000c37e  jmp     short loc_18000C38A
0x18000c380  mov     dword ptr [rbp+80h], 0
0x18000c38a  mov     eax, [rbp+80h]
0x18000c390  add     rsp, 20h
0x18000c394  pop     rbp
0x18000c395  retn
0x18000c397  push    rbp
0x18000c399  sub     rsp, 20h
0x18000c39d  mov     rbp, rdx
0x18000c3a0  mov     rax, [rcx]
0x18000c3a3  mov     edx, [rax]
0x18000c3a5  mov     [rbp+0D8h], rcx
0x18000c3ac  mov     [rbp+88h], edx
0x18000c3b2  mov     eax, [rbp+88h]
0x18000c3b8  cmp     eax, 0E06D7363h
0x18000c3bd  jnz     short loc_18000C3D9
0x18000c3bf  mov     rdx, [rbp+0D8h]
0x18000c3c6  mov     ecx, [rbp+88h]
0x18000c3cc  call    _XcptFilter_0
0x18000c3d1  mov     [rbp+90h], eax
0x18000c3d7  jmp     short loc_18000C3E3
0x18000c3d9  mov     dword ptr [rbp+90h], 0
0x18000c3e3  mov     eax, [rbp+90h]
0x18000c3e9  add     rsp, 20h
0x18000c3ed  pop     rbp
0x18000c3ee  retn
0x18000c3f0  push    rbp
0x18000c3f2  sub     rsp, 20h
0x18000c3f6  mov     rbp, rdx
0x18000c3f9  mov     rax, [rcx]
0x18000c3fc  mov     edx, [rax]
0x18000c3fe  mov     [rbp+0E0h], rcx
0x18000c405  mov     [rbp+98h], edx
0x18000c40b  mov     eax, [rbp+98h]
0x18000c411  cmp     eax, 0E06D7363h
0x18000c416  jnz     short loc_18000C432
0x18000c418  mov     rdx, [rbp+0E0h]
0x18000c41f  mov     ecx, [rbp+98h]
0x18000c425  call    _XcptFilter_0
0x18000c42a  mov     [rbp+0A0h], eax
0x18000c430  jmp     short loc_18000C43C
0x18000c432  mov     dword ptr [rbp+0A0h], 0
0x18000c43c  mov     eax, [rbp+0A0h]
0x18000c442  add     rsp, 20h
0x18000c446  pop     rbp
0x18000c447  retn
0x18000c449  push    rbp
0x18000c44b  sub     rsp, 20h
0x18000c44f  mov     rbp, rdx
0x18000c452  cmp     dword ptr [rbp+118h], 1
0x18000c459  ja      short loc_18000C465
0x18000c45b  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
