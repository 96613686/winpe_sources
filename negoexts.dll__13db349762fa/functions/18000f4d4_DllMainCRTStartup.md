# __DllMainCRTStartup

- ea: `0x18000f4d4`
- end: `0x18000f6e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f490`

## callees

- `0x18000cba0`
- `0x18000f260`
- `0x18000f4d4`
- `0x18000f9d6`
- `0x18001ed60`

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
  if ( (_DWORD)fdwReason || dword_180027380 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180027384 = 1;
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
            if ( dword_180027384 )
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
0x18000f4d4  mov     [rsp+lpvReserved], r8
0x18000f4d9  mov     [rsp+arg_8], edx
0x18000f4dd  mov     [rsp+arg_0], rcx
0x18000f4e2  push    rbx
0x18000f4e3  push    rsi
0x18000f4e4  push    rdi
0x18000f4e5  sub     rsp, 0F0h
0x18000f4ec  mov     edi, edx
0x18000f4ee  mov     rsi, rcx
0x18000f4f1  mov     ebx, 1
0x18000f4f6  cmp     edx, ebx
0x18000f4f8  ja      short loc_18000F500
0x18000f4fa  mov     cs:__native_dllmain_reason, edx
0x18000f500  test    edx, edx
0x18000f502  jnz     short loc_18000F517
0x18000f504  cmp     cs:dword_180027380, edx
0x18000f50a  jnz     short loc_18000F517
0x18000f50c  xor     ebx, ebx
0x18000f50e  mov     [rsp+108h+var_E8], ebx
0x18000f512  jmp     loc_18000F6C4
0x18000f517  lea     eax, [rdx-1]
0x18000f51a  cmp     eax, 1
0x18000f51d  ja      loc_18000F5A4
0x18000f523  mov     rax, cs:_pRawDllMain
0x18000f52a  test    rax, rax
0x18000f52d  jz      short loc_18000F565
0x18000f52f  cmp     edx, 1
0x18000f532  jnz     short loc_18000F53A
0x18000f534  mov     cs:dword_180027384, edx
0x18000f53a  mov     r8, [rsp+108h+lpvReserved]
0x18000f542  call    cs:__guard_dispatch_icall_fptr
0x18000f548  mov     ebx, eax
0x18000f54a  mov     [rsp+108h+var_E8], eax
0x18000f54e  jmp     short loc_18000F565
0x18000f550  xor     ebx, ebx
0x18000f552  mov     [rsp+108h+var_E8], ebx
0x18000f556  mov     edi, [rsp+108h+arg_8]
0x18000f55d  mov     rsi, [rsp+108h+arg_0]
0x18000f565  test    ebx, ebx
0x18000f567  jz      loc_18000F6C4
0x18000f56d  mov     r8, [rsp+108h+lpvReserved]
0x18000f575  mov     edx, edi
0x18000f577  mov     rcx, rsi
0x18000f57a  call    _CRT_INIT
0x18000f57f  mov     ebx, eax
0x18000f581  mov     [rsp+108h+var_E8], eax
0x18000f585  jmp     short loc_18000F59C
0x18000f587  xor     ebx, ebx
0x18000f589  mov     [rsp+108h+var_E8], ebx
0x18000f58d  mov     edi, [rsp+108h+arg_8]
0x18000f594  mov     rsi, [rsp+108h+arg_0]
0x18000f59c  test    ebx, ebx
0x18000f59e  jz      loc_18000F6C4
0x18000f5a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000f5ac  mov     edx, edi; fdwReason
0x18000f5ae  mov     rcx, rsi; hinstDLL
0x18000f5b1  call    DllMain
0x18000f5b6  mov     ebx, eax
0x18000f5b8  mov     [rsp+108h+var_E8], eax
0x18000f5bc  jmp     short loc_18000F5D3
0x18000f5be  xor     ebx, ebx
0x18000f5c0  mov     [rsp+108h+var_E8], ebx
0x18000f5c4  mov     edi, [rsp+108h+arg_8]
0x18000f5cb  mov     rsi, [rsp+108h+arg_0]
0x18000f5d3  cmp     edi, 1
0x18000f5d6  jnz     short loc_18000F64F
0x18000f5d8  test    ebx, ebx
0x18000f5da  jnz     short loc_18000F64F
0x18000f5dc  xor     r8d, r8d; lpvReserved
0x18000f5df  xor     edx, edx; fdwReason
0x18000f5e1  mov     rcx, rsi; hinstDLL
0x18000f5e4  call    DllMain
0x18000f5e9  jmp     short loc_18000F5FE
0x18000f5eb  mov     edi, [rsp+108h+arg_8]
0x18000f5f2  mov     rsi, [rsp+108h+arg_0]
0x18000f5fa  mov     ebx, [rsp+108h+var_E8]
0x18000f5fe  xor     r8d, r8d
0x18000f601  xor     edx, edx
0x18000f603  mov     rcx, rsi
0x18000f606  call    _CRT_INIT
0x18000f60b  jmp     short loc_18000F620
0x18000f60d  mov     edi, [rsp+108h+arg_8]
0x18000f614  mov     rsi, [rsp+108h+arg_0]
0x18000f61c  mov     ebx, [rsp+108h+var_E8]
0x18000f620  mov     rax, cs:_pRawDllMain
0x18000f627  test    rax, rax
0x18000f62a  jz      short loc_18000F64F
0x18000f62c  xor     r8d, r8d
0x18000f62f  xor     edx, edx
0x18000f631  mov     rcx, rsi
0x18000f634  call    cs:__guard_dispatch_icall_fptr
0x18000f63a  jmp     short loc_18000F64F
0x18000f63c  mov     edi, [rsp+108h+arg_8]
0x18000f643  mov     rsi, [rsp+108h+arg_0]
0x18000f64b  mov     ebx, [rsp+108h+var_E8]
0x18000f64f  test    edi, edi
0x18000f651  jz      short loc_18000F658
0x18000f653  cmp     edi, 3
0x18000f656  jnz     short loc_18000F6C4
0x18000f658  mov     r8, [rsp+108h+lpvReserved]
0x18000f660  mov     edx, edi
0x18000f662  mov     rcx, rsi
0x18000f665  call    _CRT_INIT
0x18000f66a  mov     ebx, eax
0x18000f66c  mov     [rsp+108h+var_E8], eax
0x18000f670  jmp     short loc_18000F687
0x18000f672  xor     ebx, ebx
0x18000f674  mov     [rsp+108h+var_E8], ebx
0x18000f678  mov     edi, [rsp+108h+arg_8]
0x18000f67f  mov     rsi, [rsp+108h+arg_0]
0x18000f687  mov     rax, cs:_pRawDllMain
0x18000f68e  test    rax, rax
0x18000f691  jz      short loc_18000F6C4
0x18000f693  cmp     cs:dword_180027384, 0
0x18000f69a  jz      short loc_18000F6C4
0x18000f69c  mov     r8, [rsp+108h+lpvReserved]
0x18000f6a4  mov     edx, edi
0x18000f6a6  mov     rcx, rsi
0x18000f6a9  call    cs:__guard_dispatch_icall_fptr
0x18000f6af  mov     ebx, eax
0x18000f6b1  mov     [rsp+108h+var_E8], eax
0x18000f6b5  jmp     short loc_18000F6C4
0x18000f6b7  xor     ebx, ebx
0x18000f6b9  mov     [rsp+108h+var_E8], ebx
0x18000f6bd  mov     edi, [rsp+108h+arg_8]
0x18000f6c4  cmp     edi, 1
0x18000f6c7  ja      short loc_18000F6D3
0x18000f6c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000f6d3  mov     eax, ebx
0x18000f6d5  add     rsp, 0F0h
0x18000f6dc  pop     rdi
0x18000f6dd  pop     rsi
0x18000f6de  pop     rbx
0x18000f6df  retn
0x18001f00e  push    rbp
0x18001f010  sub     rsp, 20h
0x18001f014  mov     rbp, rdx
0x18001f017  mov     rax, [rcx]
0x18001f01a  mov     edx, [rax]
0x18001f01c  mov     [rbp+0A8h], rcx
0x18001f023  mov     [rbp+28h], edx
0x18001f026  mov     eax, [rbp+28h]
0x18001f029  cmp     eax, 0E06D7363h
0x18001f02e  jnz     short loc_18001F044
0x18001f030  mov     rdx, [rbp+0A8h]
0x18001f037  mov     ecx, [rbp+28h]
0x18001f03a  call    _XcptFilter_0
0x18001f03f  mov     [rbp+30h], eax
0x18001f042  jmp     short loc_18001F04B
0x18001f044  mov     dword ptr [rbp+30h], 0
0x18001f04b  mov     eax, [rbp+30h]
0x18001f04e  add     rsp, 20h
0x18001f052  pop     rbp
0x18001f053  retn
0x18001f055  push    rbp
0x18001f057  sub     rsp, 20h
0x18001f05b  mov     rbp, rdx
0x18001f05e  mov     rax, [rcx]
0x18001f061  mov     edx, [rax]
0x18001f063  mov     [rbp+0B0h], rcx
0x18001f06a  mov     [rbp+38h], edx
0x18001f06d  mov     eax, [rbp+38h]
0x18001f070  cmp     eax, 0E06D7363h
0x18001f075  jnz     short loc_18001F08B
0x18001f077  mov     rdx, [rbp+0B0h]
0x18001f07e  mov     ecx, [rbp+38h]
0x18001f081  call    _XcptFilter_0
0x18001f086  mov     [rbp+40h], eax
0x18001f089  jmp     short loc_18001F092
0x18001f08b  mov     dword ptr [rbp+40h], 0
0x18001f092  mov     eax, [rbp+40h]
0x18001f095  add     rsp, 20h
0x18001f099  pop     rbp
0x18001f09a  retn
0x18001f09c  push    rbp
0x18001f09e  sub     rsp, 20h
0x18001f0a2  mov     rbp, rdx
0x18001f0a5  mov     rax, [rcx]
0x18001f0a8  mov     edx, [rax]
0x18001f0aa  mov     [rbp+0B8h], rcx
0x18001f0b1  mov     [rbp+48h], edx
0x18001f0b4  mov     eax, [rbp+48h]
0x18001f0b7  cmp     eax, 0E06D7363h
0x18001f0bc  jnz     short loc_18001F0D2
0x18001f0be  mov     rdx, [rbp+0B8h]
0x18001f0c5  mov     ecx, [rbp+48h]
0x18001f0c8  call    _XcptFilter_0
0x18001f0cd  mov     [rbp+50h], eax
0x18001f0d0  jmp     short loc_18001F0D9
0x18001f0d2  mov     dword ptr [rbp+50h], 0
0x18001f0d9  mov     eax, [rbp+50h]
0x18001f0dc  add     rsp, 20h
0x18001f0e0  pop     rbp
0x18001f0e1  retn
0x18001f0e3  push    rbp
0x18001f0e5  sub     rsp, 20h
0x18001f0e9  mov     rbp, rdx
0x18001f0ec  mov     rax, [rcx]
0x18001f0ef  mov     edx, [rax]
0x18001f0f1  mov     [rbp+0C0h], rcx
0x18001f0f8  mov     [rbp+58h], edx
0x18001f0fb  mov     eax, [rbp+58h]
0x18001f0fe  cmp     eax, 0E06D7363h
0x18001f103  jnz     short loc_18001F119
0x18001f105  mov     rdx, [rbp+0C0h]
0x18001f10c  mov     ecx, [rbp+58h]
0x18001f10f  call    _XcptFilter_0
0x18001f114  mov     [rbp+60h], eax
0x18001f117  jmp     short loc_18001F120
0x18001f119  mov     dword ptr [rbp+60h], 0
0x18001f120  mov     eax, [rbp+60h]
0x18001f123  add     rsp, 20h
0x18001f127  pop     rbp
0x18001f128  retn
0x18001f12a  push    rbp
0x18001f12c  sub     rsp, 20h
0x18001f130  mov     rbp, rdx
0x18001f133  mov     rax, [rcx]
0x18001f136  mov     edx, [rax]
0x18001f138  mov     [rbp+0C8h], rcx
0x18001f13f  mov     [rbp+68h], edx
0x18001f142  mov     eax, [rbp+68h]
0x18001f145  cmp     eax, 0E06D7363h
0x18001f14a  jnz     short loc_18001F160
0x18001f14c  mov     rdx, [rbp+0C8h]
0x18001f153  mov     ecx, [rbp+68h]
0x18001f156  call    _XcptFilter_0
0x18001f15b  mov     [rbp+70h], eax
0x18001f15e  jmp     short loc_18001F167
0x18001f160  mov     dword ptr [rbp+70h], 0
0x18001f167  mov     eax, [rbp+70h]
0x18001f16a  add     rsp, 20h
0x18001f16e  pop     rbp
0x18001f16f  retn
0x18001f171  push    rbp
0x18001f173  sub     rsp, 20h
0x18001f177  mov     rbp, rdx
0x18001f17a  mov     rax, [rcx]
0x18001f17d  mov     edx, [rax]
0x18001f17f  mov     [rbp+0D0h], rcx
0x18001f186  mov     [rbp+78h], edx
0x18001f189  mov     eax, [rbp+78h]
0x18001f18c  cmp     eax, 0E06D7363h
0x18001f191  jnz     short loc_18001F1AA
0x18001f193  mov     rdx, [rbp+0D0h]
0x18001f19a  mov     ecx, [rbp+78h]
0x18001f19d  call    _XcptFilter_0
0x18001f1a2  mov     [rbp+80h], eax
0x18001f1a8  jmp     short loc_18001F1B4
0x18001f1aa  mov     dword ptr [rbp+80h], 0
0x18001f1b4  mov     eax, [rbp+80h]
0x18001f1ba  add     rsp, 20h
0x18001f1be  pop     rbp
0x18001f1bf  retn
0x18001f1c1  push    rbp
0x18001f1c3  sub     rsp, 20h
0x18001f1c7  mov     rbp, rdx
0x18001f1ca  mov     rax, [rcx]
0x18001f1cd  mov     edx, [rax]
0x18001f1cf  mov     [rbp+0D8h], rcx
0x18001f1d6  mov     [rbp+88h], edx
0x18001f1dc  mov     eax, [rbp+88h]
0x18001f1e2  cmp     eax, 0E06D7363h
0x18001f1e7  jnz     short loc_18001F203
0x18001f1e9  mov     rdx, [rbp+0D8h]
0x18001f1f0  mov     ecx, [rbp+88h]
0x18001f1f6  call    _XcptFilter_0
0x18001f1fb  mov     [rbp+90h], eax
0x18001f201  jmp     short loc_18001F20D
0x18001f203  mov     dword ptr [rbp+90h], 0
0x18001f20d  mov     eax, [rbp+90h]
0x18001f213  add     rsp, 20h
0x18001f217  pop     rbp
0x18001f218  retn
0x18001f21a  push    rbp
0x18001f21c  sub     rsp, 20h
0x18001f220  mov     rbp, rdx
0x18001f223  mov     rax, [rcx]
0x18001f226  mov     edx, [rax]
0x18001f228  mov     [rbp+0E0h], rcx
0x18001f22f  mov     [rbp+98h], edx
0x18001f235  mov     eax, [rbp+98h]
0x18001f23b  cmp     eax, 0E06D7363h
0x18001f240  jnz     short loc_18001F25C
0x18001f242  mov     rdx, [rbp+0E0h]
0x18001f249  mov     ecx, [rbp+98h]
0x18001f24f  call    _XcptFilter_0
0x18001f254  mov     [rbp+0A0h], eax
0x18001f25a  jmp     short loc_18001F266
0x18001f25c  mov     dword ptr [rbp+0A0h], 0
0x18001f266  mov     eax, [rbp+0A0h]
0x18001f26c  add     rsp, 20h
0x18001f270  pop     rbp
0x18001f271  retn
0x18001f273  push    rbp
0x18001f275  sub     rsp, 20h
0x18001f279  mov     rbp, rdx
0x18001f27c  cmp     dword ptr [rbp+118h], 1
0x18001f283  ja      short loc_18001F28F
0x18001f285  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
