# __DllMainCRTStartup

- ea: `0x180002b14`
- end: `0x180002d20`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002ad0`

## callees

- `0x1800028a0`
- `0x180002b14`
- `0x18000354f`
- `0x180013b18`
- `0x18002f150`

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
  if ( (_DWORD)fdwReason || dword_180041C28 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180041C2C = 1;
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
            if ( dword_180041C2C )
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
0x180002b14  mov     [rsp+lpvReserved], r8
0x180002b19  mov     [rsp+arg_8], edx
0x180002b1d  mov     [rsp+arg_0], rcx
0x180002b22  push    rbx
0x180002b23  push    rsi
0x180002b24  push    rdi
0x180002b25  sub     rsp, 0F0h
0x180002b2c  mov     edi, edx
0x180002b2e  mov     rsi, rcx
0x180002b31  mov     ebx, 1
0x180002b36  cmp     edx, ebx
0x180002b38  ja      short loc_180002B40
0x180002b3a  mov     cs:__native_dllmain_reason, edx
0x180002b40  test    edx, edx
0x180002b42  jnz     short loc_180002B57
0x180002b44  cmp     cs:dword_180041C28, edx
0x180002b4a  jnz     short loc_180002B57
0x180002b4c  xor     ebx, ebx
0x180002b4e  mov     [rsp+108h+var_E8], ebx
0x180002b52  jmp     loc_180002D04
0x180002b57  lea     eax, [rdx-1]
0x180002b5a  cmp     eax, 1
0x180002b5d  ja      loc_180002BE4
0x180002b63  mov     rax, cs:_pRawDllMain
0x180002b6a  test    rax, rax
0x180002b6d  jz      short loc_180002BA5
0x180002b6f  cmp     edx, 1
0x180002b72  jnz     short loc_180002B7A
0x180002b74  mov     cs:dword_180041C2C, edx
0x180002b7a  mov     r8, [rsp+108h+lpvReserved]
0x180002b82  call    cs:__guard_dispatch_icall_fptr
0x180002b88  mov     ebx, eax
0x180002b8a  mov     [rsp+108h+var_E8], eax
0x180002b8e  jmp     short loc_180002BA5
0x180002b90  xor     ebx, ebx
0x180002b92  mov     [rsp+108h+var_E8], ebx
0x180002b96  mov     edi, [rsp+108h+arg_8]
0x180002b9d  mov     rsi, [rsp+108h+arg_0]
0x180002ba5  test    ebx, ebx
0x180002ba7  jz      loc_180002D04
0x180002bad  mov     r8, [rsp+108h+lpvReserved]
0x180002bb5  mov     edx, edi
0x180002bb7  mov     rcx, rsi
0x180002bba  call    _CRT_INIT
0x180002bbf  mov     ebx, eax
0x180002bc1  mov     [rsp+108h+var_E8], eax
0x180002bc5  jmp     short loc_180002BDC
0x180002bc7  xor     ebx, ebx
0x180002bc9  mov     [rsp+108h+var_E8], ebx
0x180002bcd  mov     edi, [rsp+108h+arg_8]
0x180002bd4  mov     rsi, [rsp+108h+arg_0]
0x180002bdc  test    ebx, ebx
0x180002bde  jz      loc_180002D04
0x180002be4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180002bec  mov     edx, edi; fdwReason
0x180002bee  mov     rcx, rsi; hinstDLL
0x180002bf1  call    DllMain
0x180002bf6  mov     ebx, eax
0x180002bf8  mov     [rsp+108h+var_E8], eax
0x180002bfc  jmp     short loc_180002C13
0x180002bfe  xor     ebx, ebx
0x180002c00  mov     [rsp+108h+var_E8], ebx
0x180002c04  mov     edi, [rsp+108h+arg_8]
0x180002c0b  mov     rsi, [rsp+108h+arg_0]
0x180002c13  cmp     edi, 1
0x180002c16  jnz     short loc_180002C8F
0x180002c18  test    ebx, ebx
0x180002c1a  jnz     short loc_180002C8F
0x180002c1c  xor     r8d, r8d; lpvReserved
0x180002c1f  xor     edx, edx; fdwReason
0x180002c21  mov     rcx, rsi; hinstDLL
0x180002c24  call    DllMain
0x180002c29  jmp     short loc_180002C3E
0x180002c2b  mov     edi, [rsp+108h+arg_8]
0x180002c32  mov     rsi, [rsp+108h+arg_0]
0x180002c3a  mov     ebx, [rsp+108h+var_E8]
0x180002c3e  xor     r8d, r8d
0x180002c41  xor     edx, edx
0x180002c43  mov     rcx, rsi
0x180002c46  call    _CRT_INIT
0x180002c4b  jmp     short loc_180002C60
0x180002c4d  mov     edi, [rsp+108h+arg_8]
0x180002c54  mov     rsi, [rsp+108h+arg_0]
0x180002c5c  mov     ebx, [rsp+108h+var_E8]
0x180002c60  mov     rax, cs:_pRawDllMain
0x180002c67  test    rax, rax
0x180002c6a  jz      short loc_180002C8F
0x180002c6c  xor     r8d, r8d
0x180002c6f  xor     edx, edx
0x180002c71  mov     rcx, rsi
0x180002c74  call    cs:__guard_dispatch_icall_fptr
0x180002c7a  jmp     short loc_180002C8F
0x180002c7c  mov     edi, [rsp+108h+arg_8]
0x180002c83  mov     rsi, [rsp+108h+arg_0]
0x180002c8b  mov     ebx, [rsp+108h+var_E8]
0x180002c8f  test    edi, edi
0x180002c91  jz      short loc_180002C98
0x180002c93  cmp     edi, 3
0x180002c96  jnz     short loc_180002D04
0x180002c98  mov     r8, [rsp+108h+lpvReserved]
0x180002ca0  mov     edx, edi
0x180002ca2  mov     rcx, rsi
0x180002ca5  call    _CRT_INIT
0x180002caa  mov     ebx, eax
0x180002cac  mov     [rsp+108h+var_E8], eax
0x180002cb0  jmp     short loc_180002CC7
0x180002cb2  xor     ebx, ebx
0x180002cb4  mov     [rsp+108h+var_E8], ebx
0x180002cb8  mov     edi, [rsp+108h+arg_8]
0x180002cbf  mov     rsi, [rsp+108h+arg_0]
0x180002cc7  mov     rax, cs:_pRawDllMain
0x180002cce  test    rax, rax
0x180002cd1  jz      short loc_180002D04
0x180002cd3  cmp     cs:dword_180041C2C, 0
0x180002cda  jz      short loc_180002D04
0x180002cdc  mov     r8, [rsp+108h+lpvReserved]
0x180002ce4  mov     edx, edi
0x180002ce6  mov     rcx, rsi
0x180002ce9  call    cs:__guard_dispatch_icall_fptr
0x180002cef  mov     ebx, eax
0x180002cf1  mov     [rsp+108h+var_E8], eax
0x180002cf5  jmp     short loc_180002D04
0x180002cf7  xor     ebx, ebx
0x180002cf9  mov     [rsp+108h+var_E8], ebx
0x180002cfd  mov     edi, [rsp+108h+arg_8]
0x180002d04  cmp     edi, 1
0x180002d07  ja      short loc_180002D13
0x180002d09  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002d13  mov     eax, ebx
0x180002d15  add     rsp, 0F0h
0x180002d1c  pop     rdi
0x180002d1d  pop     rsi
0x180002d1e  pop     rbx
0x180002d1f  retn
0x18002f229  push    rbp
0x18002f22b  sub     rsp, 20h
0x18002f22f  mov     rbp, rdx
0x18002f232  mov     rax, [rcx]
0x18002f235  mov     edx, [rax]
0x18002f237  mov     [rbp+0A8h], rcx
0x18002f23e  mov     [rbp+28h], edx
0x18002f241  mov     eax, [rbp+28h]
0x18002f244  cmp     eax, 0E06D7363h
0x18002f249  jnz     short loc_18002F25F
0x18002f24b  mov     rdx, [rbp+0A8h]
0x18002f252  mov     ecx, [rbp+28h]
0x18002f255  call    _XcptFilter_0
0x18002f25a  mov     [rbp+30h], eax
0x18002f25d  jmp     short loc_18002F266
0x18002f25f  mov     dword ptr [rbp+30h], 0
0x18002f266  mov     eax, [rbp+30h]
0x18002f269  add     rsp, 20h
0x18002f26d  pop     rbp
0x18002f26e  retn
0x18002f270  push    rbp
0x18002f272  sub     rsp, 20h
0x18002f276  mov     rbp, rdx
0x18002f279  mov     rax, [rcx]
0x18002f27c  mov     edx, [rax]
0x18002f27e  mov     [rbp+0B0h], rcx
0x18002f285  mov     [rbp+38h], edx
0x18002f288  mov     eax, [rbp+38h]
0x18002f28b  cmp     eax, 0E06D7363h
0x18002f290  jnz     short loc_18002F2A6
0x18002f292  mov     rdx, [rbp+0B0h]
0x18002f299  mov     ecx, [rbp+38h]
0x18002f29c  call    _XcptFilter_0
0x18002f2a1  mov     [rbp+40h], eax
0x18002f2a4  jmp     short loc_18002F2AD
0x18002f2a6  mov     dword ptr [rbp+40h], 0
0x18002f2ad  mov     eax, [rbp+40h]
0x18002f2b0  add     rsp, 20h
0x18002f2b4  pop     rbp
0x18002f2b5  retn
0x18002f2b7  push    rbp
0x18002f2b9  sub     rsp, 20h
0x18002f2bd  mov     rbp, rdx
0x18002f2c0  mov     rax, [rcx]
0x18002f2c3  mov     edx, [rax]
0x18002f2c5  mov     [rbp+0B8h], rcx
0x18002f2cc  mov     [rbp+48h], edx
0x18002f2cf  mov     eax, [rbp+48h]
0x18002f2d2  cmp     eax, 0E06D7363h
0x18002f2d7  jnz     short loc_18002F2ED
0x18002f2d9  mov     rdx, [rbp+0B8h]
0x18002f2e0  mov     ecx, [rbp+48h]
0x18002f2e3  call    _XcptFilter_0
0x18002f2e8  mov     [rbp+50h], eax
0x18002f2eb  jmp     short loc_18002F2F4
0x18002f2ed  mov     dword ptr [rbp+50h], 0
0x18002f2f4  mov     eax, [rbp+50h]
0x18002f2f7  add     rsp, 20h
0x18002f2fb  pop     rbp
0x18002f2fc  retn
0x18002f2fe  push    rbp
0x18002f300  sub     rsp, 20h
0x18002f304  mov     rbp, rdx
0x18002f307  mov     rax, [rcx]
0x18002f30a  mov     edx, [rax]
0x18002f30c  mov     [rbp+0C0h], rcx
0x18002f313  mov     [rbp+58h], edx
0x18002f316  mov     eax, [rbp+58h]
0x18002f319  cmp     eax, 0E06D7363h
0x18002f31e  jnz     short loc_18002F334
0x18002f320  mov     rdx, [rbp+0C0h]
0x18002f327  mov     ecx, [rbp+58h]
0x18002f32a  call    _XcptFilter_0
0x18002f32f  mov     [rbp+60h], eax
0x18002f332  jmp     short loc_18002F33B
0x18002f334  mov     dword ptr [rbp+60h], 0
0x18002f33b  mov     eax, [rbp+60h]
0x18002f33e  add     rsp, 20h
0x18002f342  pop     rbp
0x18002f343  retn
0x18002f345  push    rbp
0x18002f347  sub     rsp, 20h
0x18002f34b  mov     rbp, rdx
0x18002f34e  mov     rax, [rcx]
0x18002f351  mov     edx, [rax]
0x18002f353  mov     [rbp+0C8h], rcx
0x18002f35a  mov     [rbp+68h], edx
0x18002f35d  mov     eax, [rbp+68h]
0x18002f360  cmp     eax, 0E06D7363h
0x18002f365  jnz     short loc_18002F37B
0x18002f367  mov     rdx, [rbp+0C8h]
0x18002f36e  mov     ecx, [rbp+68h]
0x18002f371  call    _XcptFilter_0
0x18002f376  mov     [rbp+70h], eax
0x18002f379  jmp     short loc_18002F382
0x18002f37b  mov     dword ptr [rbp+70h], 0
0x18002f382  mov     eax, [rbp+70h]
0x18002f385  add     rsp, 20h
0x18002f389  pop     rbp
0x18002f38a  retn
0x18002f38c  push    rbp
0x18002f38e  sub     rsp, 20h
0x18002f392  mov     rbp, rdx
0x18002f395  mov     rax, [rcx]
0x18002f398  mov     edx, [rax]
0x18002f39a  mov     [rbp+0D0h], rcx
0x18002f3a1  mov     [rbp+78h], edx
0x18002f3a4  mov     eax, [rbp+78h]
0x18002f3a7  cmp     eax, 0E06D7363h
0x18002f3ac  jnz     short loc_18002F3C5
0x18002f3ae  mov     rdx, [rbp+0D0h]
0x18002f3b5  mov     ecx, [rbp+78h]
0x18002f3b8  call    _XcptFilter_0
0x18002f3bd  mov     [rbp+80h], eax
0x18002f3c3  jmp     short loc_18002F3CF
0x18002f3c5  mov     dword ptr [rbp+80h], 0
0x18002f3cf  mov     eax, [rbp+80h]
0x18002f3d5  add     rsp, 20h
0x18002f3d9  pop     rbp
0x18002f3da  retn
0x18002f3dc  push    rbp
0x18002f3de  sub     rsp, 20h
0x18002f3e2  mov     rbp, rdx
0x18002f3e5  mov     rax, [rcx]
0x18002f3e8  mov     edx, [rax]
0x18002f3ea  mov     [rbp+0D8h], rcx
0x18002f3f1  mov     [rbp+88h], edx
0x18002f3f7  mov     eax, [rbp+88h]
0x18002f3fd  cmp     eax, 0E06D7363h
0x18002f402  jnz     short loc_18002F41E
0x18002f404  mov     rdx, [rbp+0D8h]
0x18002f40b  mov     ecx, [rbp+88h]
0x18002f411  call    _XcptFilter_0
0x18002f416  mov     [rbp+90h], eax
0x18002f41c  jmp     short loc_18002F428
0x18002f41e  mov     dword ptr [rbp+90h], 0
0x18002f428  mov     eax, [rbp+90h]
0x18002f42e  add     rsp, 20h
0x18002f432  pop     rbp
0x18002f433  retn
0x18002f435  push    rbp
0x18002f437  sub     rsp, 20h
0x18002f43b  mov     rbp, rdx
0x18002f43e  mov     rax, [rcx]
0x18002f441  mov     edx, [rax]
0x18002f443  mov     [rbp+0E0h], rcx
0x18002f44a  mov     [rbp+98h], edx
0x18002f450  mov     eax, [rbp+98h]
0x18002f456  cmp     eax, 0E06D7363h
0x18002f45b  jnz     short loc_18002F477
0x18002f45d  mov     rdx, [rbp+0E0h]
0x18002f464  mov     ecx, [rbp+98h]
0x18002f46a  call    _XcptFilter_0
0x18002f46f  mov     [rbp+0A0h], eax
0x18002f475  jmp     short loc_18002F481
0x18002f477  mov     dword ptr [rbp+0A0h], 0
0x18002f481  mov     eax, [rbp+0A0h]
0x18002f487  add     rsp, 20h
0x18002f48b  pop     rbp
0x18002f48c  retn
0x18002f48e  push    rbp
0x18002f490  sub     rsp, 20h
0x18002f494  mov     rbp, rdx
0x18002f497  cmp     dword ptr [rbp+118h], 1
0x18002f49e  ja      short loc_18002F4AA
0x18002f4a0  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
