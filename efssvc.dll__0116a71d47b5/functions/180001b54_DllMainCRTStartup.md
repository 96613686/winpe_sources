# __DllMainCRTStartup

- ea: `0x180001b54`
- end: `0x180001d60`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001b10`

## callees

- `0x1800018e0`
- `0x180001b54`
- `0x180001d8a`
- `0x180001f68`
- `0x18000c400`

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
  if ( (_DWORD)fdwReason || dword_1800171A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800171A4 = 1;
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
            if ( dword_1800171A4 )
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
0x180001b54  mov     [rsp+lpvReserved], r8
0x180001b59  mov     [rsp+arg_8], edx
0x180001b5d  mov     [rsp+arg_0], rcx
0x180001b62  push    rbx
0x180001b63  push    rsi
0x180001b64  push    rdi
0x180001b65  sub     rsp, 0F0h
0x180001b6c  mov     edi, edx
0x180001b6e  mov     rsi, rcx
0x180001b71  mov     ebx, 1
0x180001b76  cmp     edx, ebx
0x180001b78  ja      short loc_180001B80
0x180001b7a  mov     cs:__native_dllmain_reason, edx
0x180001b80  test    edx, edx
0x180001b82  jnz     short loc_180001B97
0x180001b84  cmp     cs:dword_1800171A0, edx
0x180001b8a  jnz     short loc_180001B97
0x180001b8c  xor     ebx, ebx
0x180001b8e  mov     [rsp+108h+var_E8], ebx
0x180001b92  jmp     loc_180001D44
0x180001b97  lea     eax, [rdx-1]
0x180001b9a  cmp     eax, 1
0x180001b9d  ja      loc_180001C24
0x180001ba3  mov     rax, cs:_pRawDllMain
0x180001baa  test    rax, rax
0x180001bad  jz      short loc_180001BE5
0x180001baf  cmp     edx, 1
0x180001bb2  jnz     short loc_180001BBA
0x180001bb4  mov     cs:dword_1800171A4, edx
0x180001bba  mov     r8, [rsp+108h+lpvReserved]
0x180001bc2  call    cs:__guard_dispatch_icall_fptr
0x180001bc8  mov     ebx, eax
0x180001bca  mov     [rsp+108h+var_E8], eax
0x180001bce  jmp     short loc_180001BE5
0x180001bd0  xor     ebx, ebx
0x180001bd2  mov     [rsp+108h+var_E8], ebx
0x180001bd6  mov     edi, [rsp+108h+arg_8]
0x180001bdd  mov     rsi, [rsp+108h+arg_0]
0x180001be5  test    ebx, ebx
0x180001be7  jz      loc_180001D44
0x180001bed  mov     r8, [rsp+108h+lpvReserved]
0x180001bf5  mov     edx, edi
0x180001bf7  mov     rcx, rsi
0x180001bfa  call    _CRT_INIT
0x180001bff  mov     ebx, eax
0x180001c01  mov     [rsp+108h+var_E8], eax
0x180001c05  jmp     short loc_180001C1C
0x180001c07  xor     ebx, ebx
0x180001c09  mov     [rsp+108h+var_E8], ebx
0x180001c0d  mov     edi, [rsp+108h+arg_8]
0x180001c14  mov     rsi, [rsp+108h+arg_0]
0x180001c1c  test    ebx, ebx
0x180001c1e  jz      loc_180001D44
0x180001c24  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001c2c  mov     edx, edi; fdwReason
0x180001c2e  mov     rcx, rsi; hinstDLL
0x180001c31  call    DllMain
0x180001c36  mov     ebx, eax
0x180001c38  mov     [rsp+108h+var_E8], eax
0x180001c3c  jmp     short loc_180001C53
0x180001c3e  xor     ebx, ebx
0x180001c40  mov     [rsp+108h+var_E8], ebx
0x180001c44  mov     edi, [rsp+108h+arg_8]
0x180001c4b  mov     rsi, [rsp+108h+arg_0]
0x180001c53  cmp     edi, 1
0x180001c56  jnz     short loc_180001CCF
0x180001c58  test    ebx, ebx
0x180001c5a  jnz     short loc_180001CCF
0x180001c5c  xor     r8d, r8d; lpvReserved
0x180001c5f  xor     edx, edx; fdwReason
0x180001c61  mov     rcx, rsi; hinstDLL
0x180001c64  call    DllMain
0x180001c69  jmp     short loc_180001C7E
0x180001c6b  mov     edi, [rsp+108h+arg_8]
0x180001c72  mov     rsi, [rsp+108h+arg_0]
0x180001c7a  mov     ebx, [rsp+108h+var_E8]
0x180001c7e  xor     r8d, r8d
0x180001c81  xor     edx, edx
0x180001c83  mov     rcx, rsi
0x180001c86  call    _CRT_INIT
0x180001c8b  jmp     short loc_180001CA0
0x180001c8d  mov     edi, [rsp+108h+arg_8]
0x180001c94  mov     rsi, [rsp+108h+arg_0]
0x180001c9c  mov     ebx, [rsp+108h+var_E8]
0x180001ca0  mov     rax, cs:_pRawDllMain
0x180001ca7  test    rax, rax
0x180001caa  jz      short loc_180001CCF
0x180001cac  xor     r8d, r8d
0x180001caf  xor     edx, edx
0x180001cb1  mov     rcx, rsi
0x180001cb4  call    cs:__guard_dispatch_icall_fptr
0x180001cba  jmp     short loc_180001CCF
0x180001cbc  mov     edi, [rsp+108h+arg_8]
0x180001cc3  mov     rsi, [rsp+108h+arg_0]
0x180001ccb  mov     ebx, [rsp+108h+var_E8]
0x180001ccf  test    edi, edi
0x180001cd1  jz      short loc_180001CD8
0x180001cd3  cmp     edi, 3
0x180001cd6  jnz     short loc_180001D44
0x180001cd8  mov     r8, [rsp+108h+lpvReserved]
0x180001ce0  mov     edx, edi
0x180001ce2  mov     rcx, rsi
0x180001ce5  call    _CRT_INIT
0x180001cea  mov     ebx, eax
0x180001cec  mov     [rsp+108h+var_E8], eax
0x180001cf0  jmp     short loc_180001D07
0x180001cf2  xor     ebx, ebx
0x180001cf4  mov     [rsp+108h+var_E8], ebx
0x180001cf8  mov     edi, [rsp+108h+arg_8]
0x180001cff  mov     rsi, [rsp+108h+arg_0]
0x180001d07  mov     rax, cs:_pRawDllMain
0x180001d0e  test    rax, rax
0x180001d11  jz      short loc_180001D44
0x180001d13  cmp     cs:dword_1800171A4, 0
0x180001d1a  jz      short loc_180001D44
0x180001d1c  mov     r8, [rsp+108h+lpvReserved]
0x180001d24  mov     edx, edi
0x180001d26  mov     rcx, rsi
0x180001d29  call    cs:__guard_dispatch_icall_fptr
0x180001d2f  mov     ebx, eax
0x180001d31  mov     [rsp+108h+var_E8], eax
0x180001d35  jmp     short loc_180001D44
0x180001d37  xor     ebx, ebx
0x180001d39  mov     [rsp+108h+var_E8], ebx
0x180001d3d  mov     edi, [rsp+108h+arg_8]
0x180001d44  cmp     edi, 1
0x180001d47  ja      short loc_180001D53
0x180001d49  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001d53  mov     eax, ebx
0x180001d55  add     rsp, 0F0h
0x180001d5c  pop     rdi
0x180001d5d  pop     rsi
0x180001d5e  pop     rbx
0x180001d5f  retn
0x18000c4d0  push    rbp
0x18000c4d2  sub     rsp, 20h
0x18000c4d6  mov     rbp, rdx
0x18000c4d9  mov     rax, [rcx]
0x18000c4dc  mov     edx, [rax]
0x18000c4de  mov     [rbp+0A8h], rcx
0x18000c4e5  mov     [rbp+28h], edx
0x18000c4e8  mov     eax, [rbp+28h]
0x18000c4eb  cmp     eax, 0E06D7363h
0x18000c4f0  jnz     short loc_18000C506
0x18000c4f2  mov     rdx, [rbp+0A8h]
0x18000c4f9  mov     ecx, [rbp+28h]
0x18000c4fc  call    _XcptFilter_0
0x18000c501  mov     [rbp+30h], eax
0x18000c504  jmp     short loc_18000C50D
0x18000c506  mov     dword ptr [rbp+30h], 0
0x18000c50d  mov     eax, [rbp+30h]
0x18000c510  add     rsp, 20h
0x18000c514  pop     rbp
0x18000c515  retn
0x18000c517  push    rbp
0x18000c519  sub     rsp, 20h
0x18000c51d  mov     rbp, rdx
0x18000c520  mov     rax, [rcx]
0x18000c523  mov     edx, [rax]
0x18000c525  mov     [rbp+0B0h], rcx
0x18000c52c  mov     [rbp+38h], edx
0x18000c52f  mov     eax, [rbp+38h]
0x18000c532  cmp     eax, 0E06D7363h
0x18000c537  jnz     short loc_18000C54D
0x18000c539  mov     rdx, [rbp+0B0h]
0x18000c540  mov     ecx, [rbp+38h]
0x18000c543  call    _XcptFilter_0
0x18000c548  mov     [rbp+40h], eax
0x18000c54b  jmp     short loc_18000C554
0x18000c54d  mov     dword ptr [rbp+40h], 0
0x18000c554  mov     eax, [rbp+40h]
0x18000c557  add     rsp, 20h
0x18000c55b  pop     rbp
0x18000c55c  retn
0x18000c55e  push    rbp
0x18000c560  sub     rsp, 20h
0x18000c564  mov     rbp, rdx
0x18000c567  mov     rax, [rcx]
0x18000c56a  mov     edx, [rax]
0x18000c56c  mov     [rbp+0B8h], rcx
0x18000c573  mov     [rbp+48h], edx
0x18000c576  mov     eax, [rbp+48h]
0x18000c579  cmp     eax, 0E06D7363h
0x18000c57e  jnz     short loc_18000C594
0x18000c580  mov     rdx, [rbp+0B8h]
0x18000c587  mov     ecx, [rbp+48h]
0x18000c58a  call    _XcptFilter_0
0x18000c58f  mov     [rbp+50h], eax
0x18000c592  jmp     short loc_18000C59B
0x18000c594  mov     dword ptr [rbp+50h], 0
0x18000c59b  mov     eax, [rbp+50h]
0x18000c59e  add     rsp, 20h
0x18000c5a2  pop     rbp
0x18000c5a3  retn
0x18000c5a5  push    rbp
0x18000c5a7  sub     rsp, 20h
0x18000c5ab  mov     rbp, rdx
0x18000c5ae  mov     rax, [rcx]
0x18000c5b1  mov     edx, [rax]
0x18000c5b3  mov     [rbp+0C0h], rcx
0x18000c5ba  mov     [rbp+58h], edx
0x18000c5bd  mov     eax, [rbp+58h]
0x18000c5c0  cmp     eax, 0E06D7363h
0x18000c5c5  jnz     short loc_18000C5DB
0x18000c5c7  mov     rdx, [rbp+0C0h]
0x18000c5ce  mov     ecx, [rbp+58h]
0x18000c5d1  call    _XcptFilter_0
0x18000c5d6  mov     [rbp+60h], eax
0x18000c5d9  jmp     short loc_18000C5E2
0x18000c5db  mov     dword ptr [rbp+60h], 0
0x18000c5e2  mov     eax, [rbp+60h]
0x18000c5e5  add     rsp, 20h
0x18000c5e9  pop     rbp
0x18000c5ea  retn
0x18000c5ec  push    rbp
0x18000c5ee  sub     rsp, 20h
0x18000c5f2  mov     rbp, rdx
0x18000c5f5  mov     rax, [rcx]
0x18000c5f8  mov     edx, [rax]
0x18000c5fa  mov     [rbp+0C8h], rcx
0x18000c601  mov     [rbp+68h], edx
0x18000c604  mov     eax, [rbp+68h]
0x18000c607  cmp     eax, 0E06D7363h
0x18000c60c  jnz     short loc_18000C622
0x18000c60e  mov     rdx, [rbp+0C8h]
0x18000c615  mov     ecx, [rbp+68h]
0x18000c618  call    _XcptFilter_0
0x18000c61d  mov     [rbp+70h], eax
0x18000c620  jmp     short loc_18000C629
0x18000c622  mov     dword ptr [rbp+70h], 0
0x18000c629  mov     eax, [rbp+70h]
0x18000c62c  add     rsp, 20h
0x18000c630  pop     rbp
0x18000c631  retn
0x18000c633  push    rbp
0x18000c635  sub     rsp, 20h
0x18000c639  mov     rbp, rdx
0x18000c63c  mov     rax, [rcx]
0x18000c63f  mov     edx, [rax]
0x18000c641  mov     [rbp+0D0h], rcx
0x18000c648  mov     [rbp+78h], edx
0x18000c64b  mov     eax, [rbp+78h]
0x18000c64e  cmp     eax, 0E06D7363h
0x18000c653  jnz     short loc_18000C66C
0x18000c655  mov     rdx, [rbp+0D0h]
0x18000c65c  mov     ecx, [rbp+78h]
0x18000c65f  call    _XcptFilter_0
0x18000c664  mov     [rbp+80h], eax
0x18000c66a  jmp     short loc_18000C676
0x18000c66c  mov     dword ptr [rbp+80h], 0
0x18000c676  mov     eax, [rbp+80h]
0x18000c67c  add     rsp, 20h
0x18000c680  pop     rbp
0x18000c681  retn
0x18000c683  push    rbp
0x18000c685  sub     rsp, 20h
0x18000c689  mov     rbp, rdx
0x18000c68c  mov     rax, [rcx]
0x18000c68f  mov     edx, [rax]
0x18000c691  mov     [rbp+0D8h], rcx
0x18000c698  mov     [rbp+88h], edx
0x18000c69e  mov     eax, [rbp+88h]
0x18000c6a4  cmp     eax, 0E06D7363h
0x18000c6a9  jnz     short loc_18000C6C5
0x18000c6ab  mov     rdx, [rbp+0D8h]
0x18000c6b2  mov     ecx, [rbp+88h]
0x18000c6b8  call    _XcptFilter_0
0x18000c6bd  mov     [rbp+90h], eax
0x18000c6c3  jmp     short loc_18000C6CF
0x18000c6c5  mov     dword ptr [rbp+90h], 0
0x18000c6cf  mov     eax, [rbp+90h]
0x18000c6d5  add     rsp, 20h
0x18000c6d9  pop     rbp
0x18000c6da  retn
0x18000c6dc  push    rbp
0x18000c6de  sub     rsp, 20h
0x18000c6e2  mov     rbp, rdx
0x18000c6e5  mov     rax, [rcx]
0x18000c6e8  mov     edx, [rax]
0x18000c6ea  mov     [rbp+0E0h], rcx
0x18000c6f1  mov     [rbp+98h], edx
0x18000c6f7  mov     eax, [rbp+98h]
0x18000c6fd  cmp     eax, 0E06D7363h
0x18000c702  jnz     short loc_18000C71E
0x18000c704  mov     rdx, [rbp+0E0h]
0x18000c70b  mov     ecx, [rbp+98h]
0x18000c711  call    _XcptFilter_0
0x18000c716  mov     [rbp+0A0h], eax
0x18000c71c  jmp     short loc_18000C728
0x18000c71e  mov     dword ptr [rbp+0A0h], 0
0x18000c728  mov     eax, [rbp+0A0h]
0x18000c72e  add     rsp, 20h
0x18000c732  pop     rbp
0x18000c733  retn
0x18000c735  push    rbp
0x18000c737  sub     rsp, 20h
0x18000c73b  mov     rbp, rdx
0x18000c73e  cmp     dword ptr [rbp+118h], 1
0x18000c745  ja      short loc_18000C751
0x18000c747  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
