# __DllMainCRTStartup

- ea: `0x180003a84`
- end: `0x180003c90`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003a40`

## callees

- `0x18000343c`
- `0x180003810`
- `0x180003a84`
- `0x1800040c4`
- `0x18001ccb0`

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
  if ( (_DWORD)fdwReason || dword_180028500 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180028504 = 1;
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
            if ( dword_180028504 )
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
0x180003a84  mov     [rsp+lpvReserved], r8
0x180003a89  mov     [rsp+arg_8], edx
0x180003a8d  mov     [rsp+arg_0], rcx
0x180003a92  push    rbx
0x180003a93  push    rsi
0x180003a94  push    rdi
0x180003a95  sub     rsp, 0F0h
0x180003a9c  mov     edi, edx
0x180003a9e  mov     rsi, rcx
0x180003aa1  mov     ebx, 1
0x180003aa6  cmp     edx, ebx
0x180003aa8  ja      short loc_180003AB0
0x180003aaa  mov     cs:__native_dllmain_reason, edx
0x180003ab0  test    edx, edx
0x180003ab2  jnz     short loc_180003AC7
0x180003ab4  cmp     cs:dword_180028500, edx
0x180003aba  jnz     short loc_180003AC7
0x180003abc  xor     ebx, ebx
0x180003abe  mov     [rsp+108h+var_E8], ebx
0x180003ac2  jmp     loc_180003C74
0x180003ac7  lea     eax, [rdx-1]
0x180003aca  cmp     eax, 1
0x180003acd  ja      loc_180003B54
0x180003ad3  mov     rax, cs:_pRawDllMain
0x180003ada  test    rax, rax
0x180003add  jz      short loc_180003B15
0x180003adf  cmp     edx, 1
0x180003ae2  jnz     short loc_180003AEA
0x180003ae4  mov     cs:dword_180028504, edx
0x180003aea  mov     r8, [rsp+108h+lpvReserved]
0x180003af2  call    cs:__guard_dispatch_icall_fptr
0x180003af8  mov     ebx, eax
0x180003afa  mov     [rsp+108h+var_E8], eax
0x180003afe  jmp     short loc_180003B15
0x180003b00  xor     ebx, ebx
0x180003b02  mov     [rsp+108h+var_E8], ebx
0x180003b06  mov     edi, [rsp+108h+arg_8]
0x180003b0d  mov     rsi, [rsp+108h+arg_0]
0x180003b15  test    ebx, ebx
0x180003b17  jz      loc_180003C74
0x180003b1d  mov     r8, [rsp+108h+lpvReserved]
0x180003b25  mov     edx, edi
0x180003b27  mov     rcx, rsi
0x180003b2a  call    _CRT_INIT
0x180003b2f  mov     ebx, eax
0x180003b31  mov     [rsp+108h+var_E8], eax
0x180003b35  jmp     short loc_180003B4C
0x180003b37  xor     ebx, ebx
0x180003b39  mov     [rsp+108h+var_E8], ebx
0x180003b3d  mov     edi, [rsp+108h+arg_8]
0x180003b44  mov     rsi, [rsp+108h+arg_0]
0x180003b4c  test    ebx, ebx
0x180003b4e  jz      loc_180003C74
0x180003b54  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180003b5c  mov     edx, edi; fdwReason
0x180003b5e  mov     rcx, rsi; hinstDLL
0x180003b61  call    DllMain
0x180003b66  mov     ebx, eax
0x180003b68  mov     [rsp+108h+var_E8], eax
0x180003b6c  jmp     short loc_180003B83
0x180003b6e  xor     ebx, ebx
0x180003b70  mov     [rsp+108h+var_E8], ebx
0x180003b74  mov     edi, [rsp+108h+arg_8]
0x180003b7b  mov     rsi, [rsp+108h+arg_0]
0x180003b83  cmp     edi, 1
0x180003b86  jnz     short loc_180003BFF
0x180003b88  test    ebx, ebx
0x180003b8a  jnz     short loc_180003BFF
0x180003b8c  xor     r8d, r8d; lpvReserved
0x180003b8f  xor     edx, edx; fdwReason
0x180003b91  mov     rcx, rsi; hinstDLL
0x180003b94  call    DllMain
0x180003b99  jmp     short loc_180003BAE
0x180003b9b  mov     edi, [rsp+108h+arg_8]
0x180003ba2  mov     rsi, [rsp+108h+arg_0]
0x180003baa  mov     ebx, [rsp+108h+var_E8]
0x180003bae  xor     r8d, r8d
0x180003bb1  xor     edx, edx
0x180003bb3  mov     rcx, rsi
0x180003bb6  call    _CRT_INIT
0x180003bbb  jmp     short loc_180003BD0
0x180003bbd  mov     edi, [rsp+108h+arg_8]
0x180003bc4  mov     rsi, [rsp+108h+arg_0]
0x180003bcc  mov     ebx, [rsp+108h+var_E8]
0x180003bd0  mov     rax, cs:_pRawDllMain
0x180003bd7  test    rax, rax
0x180003bda  jz      short loc_180003BFF
0x180003bdc  xor     r8d, r8d
0x180003bdf  xor     edx, edx
0x180003be1  mov     rcx, rsi
0x180003be4  call    cs:__guard_dispatch_icall_fptr
0x180003bea  jmp     short loc_180003BFF
0x180003bec  mov     edi, [rsp+108h+arg_8]
0x180003bf3  mov     rsi, [rsp+108h+arg_0]
0x180003bfb  mov     ebx, [rsp+108h+var_E8]
0x180003bff  test    edi, edi
0x180003c01  jz      short loc_180003C08
0x180003c03  cmp     edi, 3
0x180003c06  jnz     short loc_180003C74
0x180003c08  mov     r8, [rsp+108h+lpvReserved]
0x180003c10  mov     edx, edi
0x180003c12  mov     rcx, rsi
0x180003c15  call    _CRT_INIT
0x180003c1a  mov     ebx, eax
0x180003c1c  mov     [rsp+108h+var_E8], eax
0x180003c20  jmp     short loc_180003C37
0x180003c22  xor     ebx, ebx
0x180003c24  mov     [rsp+108h+var_E8], ebx
0x180003c28  mov     edi, [rsp+108h+arg_8]
0x180003c2f  mov     rsi, [rsp+108h+arg_0]
0x180003c37  mov     rax, cs:_pRawDllMain
0x180003c3e  test    rax, rax
0x180003c41  jz      short loc_180003C74
0x180003c43  cmp     cs:dword_180028504, 0
0x180003c4a  jz      short loc_180003C74
0x180003c4c  mov     r8, [rsp+108h+lpvReserved]
0x180003c54  mov     edx, edi
0x180003c56  mov     rcx, rsi
0x180003c59  call    cs:__guard_dispatch_icall_fptr
0x180003c5f  mov     ebx, eax
0x180003c61  mov     [rsp+108h+var_E8], eax
0x180003c65  jmp     short loc_180003C74
0x180003c67  xor     ebx, ebx
0x180003c69  mov     [rsp+108h+var_E8], ebx
0x180003c6d  mov     edi, [rsp+108h+arg_8]
0x180003c74  cmp     edi, 1
0x180003c77  ja      short loc_180003C83
0x180003c79  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180003c83  mov     eax, ebx
0x180003c85  add     rsp, 0F0h
0x180003c8c  pop     rdi
0x180003c8d  pop     rsi
0x180003c8e  pop     rbx
0x180003c8f  retn
0x18001cd80  push    rbp
0x18001cd82  sub     rsp, 20h
0x18001cd86  mov     rbp, rdx
0x18001cd89  mov     rax, [rcx]
0x18001cd8c  mov     edx, [rax]
0x18001cd8e  mov     [rbp+0A8h], rcx
0x18001cd95  mov     [rbp+28h], edx
0x18001cd98  mov     eax, [rbp+28h]
0x18001cd9b  cmp     eax, 0E06D7363h
0x18001cda0  jnz     short loc_18001CDB6
0x18001cda2  mov     rdx, [rbp+0A8h]
0x18001cda9  mov     ecx, [rbp+28h]
0x18001cdac  call    _XcptFilter_0
0x18001cdb1  mov     [rbp+30h], eax
0x18001cdb4  jmp     short loc_18001CDBD
0x18001cdb6  mov     dword ptr [rbp+30h], 0
0x18001cdbd  mov     eax, [rbp+30h]
0x18001cdc0  add     rsp, 20h
0x18001cdc4  pop     rbp
0x18001cdc5  retn
0x18001cdc7  push    rbp
0x18001cdc9  sub     rsp, 20h
0x18001cdcd  mov     rbp, rdx
0x18001cdd0  mov     rax, [rcx]
0x18001cdd3  mov     edx, [rax]
0x18001cdd5  mov     [rbp+0B0h], rcx
0x18001cddc  mov     [rbp+38h], edx
0x18001cddf  mov     eax, [rbp+38h]
0x18001cde2  cmp     eax, 0E06D7363h
0x18001cde7  jnz     short loc_18001CDFD
0x18001cde9  mov     rdx, [rbp+0B0h]
0x18001cdf0  mov     ecx, [rbp+38h]
0x18001cdf3  call    _XcptFilter_0
0x18001cdf8  mov     [rbp+40h], eax
0x18001cdfb  jmp     short loc_18001CE04
0x18001cdfd  mov     dword ptr [rbp+40h], 0
0x18001ce04  mov     eax, [rbp+40h]
0x18001ce07  add     rsp, 20h
0x18001ce0b  pop     rbp
0x18001ce0c  retn
0x18001ce0e  push    rbp
0x18001ce10  sub     rsp, 20h
0x18001ce14  mov     rbp, rdx
0x18001ce17  mov     rax, [rcx]
0x18001ce1a  mov     edx, [rax]
0x18001ce1c  mov     [rbp+0B8h], rcx
0x18001ce23  mov     [rbp+48h], edx
0x18001ce26  mov     eax, [rbp+48h]
0x18001ce29  cmp     eax, 0E06D7363h
0x18001ce2e  jnz     short loc_18001CE44
0x18001ce30  mov     rdx, [rbp+0B8h]
0x18001ce37  mov     ecx, [rbp+48h]
0x18001ce3a  call    _XcptFilter_0
0x18001ce3f  mov     [rbp+50h], eax
0x18001ce42  jmp     short loc_18001CE4B
0x18001ce44  mov     dword ptr [rbp+50h], 0
0x18001ce4b  mov     eax, [rbp+50h]
0x18001ce4e  add     rsp, 20h
0x18001ce52  pop     rbp
0x18001ce53  retn
0x18001ce55  push    rbp
0x18001ce57  sub     rsp, 20h
0x18001ce5b  mov     rbp, rdx
0x18001ce5e  mov     rax, [rcx]
0x18001ce61  mov     edx, [rax]
0x18001ce63  mov     [rbp+0C0h], rcx
0x18001ce6a  mov     [rbp+58h], edx
0x18001ce6d  mov     eax, [rbp+58h]
0x18001ce70  cmp     eax, 0E06D7363h
0x18001ce75  jnz     short loc_18001CE8B
0x18001ce77  mov     rdx, [rbp+0C0h]
0x18001ce7e  mov     ecx, [rbp+58h]
0x18001ce81  call    _XcptFilter_0
0x18001ce86  mov     [rbp+60h], eax
0x18001ce89  jmp     short loc_18001CE92
0x18001ce8b  mov     dword ptr [rbp+60h], 0
0x18001ce92  mov     eax, [rbp+60h]
0x18001ce95  add     rsp, 20h
0x18001ce99  pop     rbp
0x18001ce9a  retn
0x18001ce9c  push    rbp
0x18001ce9e  sub     rsp, 20h
0x18001cea2  mov     rbp, rdx
0x18001cea5  mov     rax, [rcx]
0x18001cea8  mov     edx, [rax]
0x18001ceaa  mov     [rbp+0C8h], rcx
0x18001ceb1  mov     [rbp+68h], edx
0x18001ceb4  mov     eax, [rbp+68h]
0x18001ceb7  cmp     eax, 0E06D7363h
0x18001cebc  jnz     short loc_18001CED2
0x18001cebe  mov     rdx, [rbp+0C8h]
0x18001cec5  mov     ecx, [rbp+68h]
0x18001cec8  call    _XcptFilter_0
0x18001cecd  mov     [rbp+70h], eax
0x18001ced0  jmp     short loc_18001CED9
0x18001ced2  mov     dword ptr [rbp+70h], 0
0x18001ced9  mov     eax, [rbp+70h]
0x18001cedc  add     rsp, 20h
0x18001cee0  pop     rbp
0x18001cee1  retn
0x18001cee3  push    rbp
0x18001cee5  sub     rsp, 20h
0x18001cee9  mov     rbp, rdx
0x18001ceec  mov     rax, [rcx]
0x18001ceef  mov     edx, [rax]
0x18001cef1  mov     [rbp+0D0h], rcx
0x18001cef8  mov     [rbp+78h], edx
0x18001cefb  mov     eax, [rbp+78h]
0x18001cefe  cmp     eax, 0E06D7363h
0x18001cf03  jnz     short loc_18001CF1C
0x18001cf05  mov     rdx, [rbp+0D0h]
0x18001cf0c  mov     ecx, [rbp+78h]
0x18001cf0f  call    _XcptFilter_0
0x18001cf14  mov     [rbp+80h], eax
0x18001cf1a  jmp     short loc_18001CF26
0x18001cf1c  mov     dword ptr [rbp+80h], 0
0x18001cf26  mov     eax, [rbp+80h]
0x18001cf2c  add     rsp, 20h
0x18001cf30  pop     rbp
0x18001cf31  retn
0x18001cf33  push    rbp
0x18001cf35  sub     rsp, 20h
0x18001cf39  mov     rbp, rdx
0x18001cf3c  mov     rax, [rcx]
0x18001cf3f  mov     edx, [rax]
0x18001cf41  mov     [rbp+0D8h], rcx
0x18001cf48  mov     [rbp+88h], edx
0x18001cf4e  mov     eax, [rbp+88h]
0x18001cf54  cmp     eax, 0E06D7363h
0x18001cf59  jnz     short loc_18001CF75
0x18001cf5b  mov     rdx, [rbp+0D8h]
0x18001cf62  mov     ecx, [rbp+88h]
0x18001cf68  call    _XcptFilter_0
0x18001cf6d  mov     [rbp+90h], eax
0x18001cf73  jmp     short loc_18001CF7F
0x18001cf75  mov     dword ptr [rbp+90h], 0
0x18001cf7f  mov     eax, [rbp+90h]
0x18001cf85  add     rsp, 20h
0x18001cf89  pop     rbp
0x18001cf8a  retn
0x18001cf8c  push    rbp
0x18001cf8e  sub     rsp, 20h
0x18001cf92  mov     rbp, rdx
0x18001cf95  mov     rax, [rcx]
0x18001cf98  mov     edx, [rax]
0x18001cf9a  mov     [rbp+0E0h], rcx
0x18001cfa1  mov     [rbp+98h], edx
0x18001cfa7  mov     eax, [rbp+98h]
0x18001cfad  cmp     eax, 0E06D7363h
0x18001cfb2  jnz     short loc_18001CFCE
0x18001cfb4  mov     rdx, [rbp+0E0h]
0x18001cfbb  mov     ecx, [rbp+98h]
0x18001cfc1  call    _XcptFilter_0
0x18001cfc6  mov     [rbp+0A0h], eax
0x18001cfcc  jmp     short loc_18001CFD8
0x18001cfce  mov     dword ptr [rbp+0A0h], 0
0x18001cfd8  mov     eax, [rbp+0A0h]
0x18001cfde  add     rsp, 20h
0x18001cfe2  pop     rbp
0x18001cfe3  retn
0x18001cfe5  push    rbp
0x18001cfe7  sub     rsp, 20h
0x18001cfeb  mov     rbp, rdx
0x18001cfee  cmp     dword ptr [rbp+118h], 1
0x18001cff5  ja      short loc_18001D001
0x18001cff7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
