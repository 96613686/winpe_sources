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
- `0x180002246`
- `0x1800055e8`
- `0x1800087d0`

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
  if ( (_DWORD)fdwReason || dword_18000F20C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F210 = 1;
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
            if ( dword_18000F210 )
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
0x180001ca4  cmp     cs:dword_18000F20C, edx
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
0x180001cd4  mov     cs:dword_18000F210, edx
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
0x180001e33  cmp     cs:dword_18000F210, 0
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
0x18000887f  push    rbp
0x180008881  sub     rsp, 20h
0x180008885  mov     rbp, rdx
0x180008888  mov     rax, [rcx]
0x18000888b  mov     edx, [rax]
0x18000888d  mov     [rbp+0A8h], rcx
0x180008894  mov     [rbp+28h], edx
0x180008897  mov     eax, [rbp+28h]
0x18000889a  cmp     eax, 0E06D7363h
0x18000889f  jnz     short loc_1800088B5
0x1800088a1  mov     rdx, [rbp+0A8h]
0x1800088a8  mov     ecx, [rbp+28h]
0x1800088ab  call    _XcptFilter_0
0x1800088b0  mov     [rbp+30h], eax
0x1800088b3  jmp     short loc_1800088BC
0x1800088b5  mov     dword ptr [rbp+30h], 0
0x1800088bc  mov     eax, [rbp+30h]
0x1800088bf  add     rsp, 20h
0x1800088c3  pop     rbp
0x1800088c4  retn
0x1800088c6  push    rbp
0x1800088c8  sub     rsp, 20h
0x1800088cc  mov     rbp, rdx
0x1800088cf  mov     rax, [rcx]
0x1800088d2  mov     edx, [rax]
0x1800088d4  mov     [rbp+0B0h], rcx
0x1800088db  mov     [rbp+38h], edx
0x1800088de  mov     eax, [rbp+38h]
0x1800088e1  cmp     eax, 0E06D7363h
0x1800088e6  jnz     short loc_1800088FC
0x1800088e8  mov     rdx, [rbp+0B0h]
0x1800088ef  mov     ecx, [rbp+38h]
0x1800088f2  call    _XcptFilter_0
0x1800088f7  mov     [rbp+40h], eax
0x1800088fa  jmp     short loc_180008903
0x1800088fc  mov     dword ptr [rbp+40h], 0
0x180008903  mov     eax, [rbp+40h]
0x180008906  add     rsp, 20h
0x18000890a  pop     rbp
0x18000890b  retn
0x18000890d  push    rbp
0x18000890f  sub     rsp, 20h
0x180008913  mov     rbp, rdx
0x180008916  mov     rax, [rcx]
0x180008919  mov     edx, [rax]
0x18000891b  mov     [rbp+0B8h], rcx
0x180008922  mov     [rbp+48h], edx
0x180008925  mov     eax, [rbp+48h]
0x180008928  cmp     eax, 0E06D7363h
0x18000892d  jnz     short loc_180008943
0x18000892f  mov     rdx, [rbp+0B8h]
0x180008936  mov     ecx, [rbp+48h]
0x180008939  call    _XcptFilter_0
0x18000893e  mov     [rbp+50h], eax
0x180008941  jmp     short loc_18000894A
0x180008943  mov     dword ptr [rbp+50h], 0
0x18000894a  mov     eax, [rbp+50h]
0x18000894d  add     rsp, 20h
0x180008951  pop     rbp
0x180008952  retn
0x180008954  push    rbp
0x180008956  sub     rsp, 20h
0x18000895a  mov     rbp, rdx
0x18000895d  mov     rax, [rcx]
0x180008960  mov     edx, [rax]
0x180008962  mov     [rbp+0C0h], rcx
0x180008969  mov     [rbp+58h], edx
0x18000896c  mov     eax, [rbp+58h]
0x18000896f  cmp     eax, 0E06D7363h
0x180008974  jnz     short loc_18000898A
0x180008976  mov     rdx, [rbp+0C0h]
0x18000897d  mov     ecx, [rbp+58h]
0x180008980  call    _XcptFilter_0
0x180008985  mov     [rbp+60h], eax
0x180008988  jmp     short loc_180008991
0x18000898a  mov     dword ptr [rbp+60h], 0
0x180008991  mov     eax, [rbp+60h]
0x180008994  add     rsp, 20h
0x180008998  pop     rbp
0x180008999  retn
0x18000899b  push    rbp
0x18000899d  sub     rsp, 20h
0x1800089a1  mov     rbp, rdx
0x1800089a4  mov     rax, [rcx]
0x1800089a7  mov     edx, [rax]
0x1800089a9  mov     [rbp+0C8h], rcx
0x1800089b0  mov     [rbp+68h], edx
0x1800089b3  mov     eax, [rbp+68h]
0x1800089b6  cmp     eax, 0E06D7363h
0x1800089bb  jnz     short loc_1800089D1
0x1800089bd  mov     rdx, [rbp+0C8h]
0x1800089c4  mov     ecx, [rbp+68h]
0x1800089c7  call    _XcptFilter_0
0x1800089cc  mov     [rbp+70h], eax
0x1800089cf  jmp     short loc_1800089D8
0x1800089d1  mov     dword ptr [rbp+70h], 0
0x1800089d8  mov     eax, [rbp+70h]
0x1800089db  add     rsp, 20h
0x1800089df  pop     rbp
0x1800089e0  retn
0x1800089e2  push    rbp
0x1800089e4  sub     rsp, 20h
0x1800089e8  mov     rbp, rdx
0x1800089eb  mov     rax, [rcx]
0x1800089ee  mov     edx, [rax]
0x1800089f0  mov     [rbp+0D0h], rcx
0x1800089f7  mov     [rbp+78h], edx
0x1800089fa  mov     eax, [rbp+78h]
0x1800089fd  cmp     eax, 0E06D7363h
0x180008a02  jnz     short loc_180008A1B
0x180008a04  mov     rdx, [rbp+0D0h]
0x180008a0b  mov     ecx, [rbp+78h]
0x180008a0e  call    _XcptFilter_0
0x180008a13  mov     [rbp+80h], eax
0x180008a19  jmp     short loc_180008A25
0x180008a1b  mov     dword ptr [rbp+80h], 0
0x180008a25  mov     eax, [rbp+80h]
0x180008a2b  add     rsp, 20h
0x180008a2f  pop     rbp
0x180008a30  retn
0x180008a32  push    rbp
0x180008a34  sub     rsp, 20h
0x180008a38  mov     rbp, rdx
0x180008a3b  mov     rax, [rcx]
0x180008a3e  mov     edx, [rax]
0x180008a40  mov     [rbp+0D8h], rcx
0x180008a47  mov     [rbp+88h], edx
0x180008a4d  mov     eax, [rbp+88h]
0x180008a53  cmp     eax, 0E06D7363h
0x180008a58  jnz     short loc_180008A74
0x180008a5a  mov     rdx, [rbp+0D8h]
0x180008a61  mov     ecx, [rbp+88h]
0x180008a67  call    _XcptFilter_0
0x180008a6c  mov     [rbp+90h], eax
0x180008a72  jmp     short loc_180008A7E
0x180008a74  mov     dword ptr [rbp+90h], 0
0x180008a7e  mov     eax, [rbp+90h]
0x180008a84  add     rsp, 20h
0x180008a88  pop     rbp
0x180008a89  retn
0x180008a8b  push    rbp
0x180008a8d  sub     rsp, 20h
0x180008a91  mov     rbp, rdx
0x180008a94  mov     rax, [rcx]
0x180008a97  mov     edx, [rax]
0x180008a99  mov     [rbp+0E0h], rcx
0x180008aa0  mov     [rbp+98h], edx
0x180008aa6  mov     eax, [rbp+98h]
0x180008aac  cmp     eax, 0E06D7363h
0x180008ab1  jnz     short loc_180008ACD
0x180008ab3  mov     rdx, [rbp+0E0h]
0x180008aba  mov     ecx, [rbp+98h]
0x180008ac0  call    _XcptFilter_0
0x180008ac5  mov     [rbp+0A0h], eax
0x180008acb  jmp     short loc_180008AD7
0x180008acd  mov     dword ptr [rbp+0A0h], 0
0x180008ad7  mov     eax, [rbp+0A0h]
0x180008add  add     rsp, 20h
0x180008ae1  pop     rbp
0x180008ae2  retn
0x180008ae4  push    rbp
0x180008ae6  sub     rsp, 20h
0x180008aea  mov     rbp, rdx
0x180008aed  cmp     dword ptr [rbp+118h], 1
0x180008af4  ja      short loc_180008B00
0x180008af6  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
