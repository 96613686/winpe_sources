# __DllMainCRTStartup

- ea: `0x180004514`
- end: `0x180004720`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800044d0`

## callees

- `0x1800042a0`
- `0x180004514`
- `0x18000474a`
- `0x180004928`
- `0x180004c50`

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
  if ( (_DWORD)fdwReason || dword_18000D0C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000D0C4 = 1;
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
            if ( dword_18000D0C4 )
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
0x180004514  mov     [rsp+lpvReserved], r8
0x180004519  mov     [rsp+arg_8], edx
0x18000451d  mov     [rsp+arg_0], rcx
0x180004522  push    rbx
0x180004523  push    rsi
0x180004524  push    rdi
0x180004525  sub     rsp, 0F0h
0x18000452c  mov     edi, edx
0x18000452e  mov     rsi, rcx
0x180004531  mov     ebx, 1
0x180004536  cmp     edx, ebx
0x180004538  ja      short loc_180004540
0x18000453a  mov     cs:__native_dllmain_reason, edx
0x180004540  test    edx, edx
0x180004542  jnz     short loc_180004557
0x180004544  cmp     cs:dword_18000D0C0, edx
0x18000454a  jnz     short loc_180004557
0x18000454c  xor     ebx, ebx
0x18000454e  mov     [rsp+108h+var_E8], ebx
0x180004552  jmp     loc_180004704
0x180004557  lea     eax, [rdx-1]
0x18000455a  cmp     eax, 1
0x18000455d  ja      loc_1800045E4
0x180004563  mov     rax, cs:_pRawDllMain
0x18000456a  test    rax, rax
0x18000456d  jz      short loc_1800045A5
0x18000456f  cmp     edx, 1
0x180004572  jnz     short loc_18000457A
0x180004574  mov     cs:dword_18000D0C4, edx
0x18000457a  mov     r8, [rsp+108h+lpvReserved]
0x180004582  call    cs:__guard_dispatch_icall_fptr
0x180004588  mov     ebx, eax
0x18000458a  mov     [rsp+108h+var_E8], eax
0x18000458e  jmp     short loc_1800045A5
0x180004590  xor     ebx, ebx
0x180004592  mov     [rsp+108h+var_E8], ebx
0x180004596  mov     edi, [rsp+108h+arg_8]
0x18000459d  mov     rsi, [rsp+108h+arg_0]
0x1800045a5  test    ebx, ebx
0x1800045a7  jz      loc_180004704
0x1800045ad  mov     r8, [rsp+108h+lpvReserved]
0x1800045b5  mov     edx, edi
0x1800045b7  mov     rcx, rsi
0x1800045ba  call    _CRT_INIT
0x1800045bf  mov     ebx, eax
0x1800045c1  mov     [rsp+108h+var_E8], eax
0x1800045c5  jmp     short loc_1800045DC
0x1800045c7  xor     ebx, ebx
0x1800045c9  mov     [rsp+108h+var_E8], ebx
0x1800045cd  mov     edi, [rsp+108h+arg_8]
0x1800045d4  mov     rsi, [rsp+108h+arg_0]
0x1800045dc  test    ebx, ebx
0x1800045de  jz      loc_180004704
0x1800045e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800045ec  mov     edx, edi; fdwReason
0x1800045ee  mov     rcx, rsi; hinstDLL
0x1800045f1  call    DllMain
0x1800045f6  mov     ebx, eax
0x1800045f8  mov     [rsp+108h+var_E8], eax
0x1800045fc  jmp     short loc_180004613
0x1800045fe  xor     ebx, ebx
0x180004600  mov     [rsp+108h+var_E8], ebx
0x180004604  mov     edi, [rsp+108h+arg_8]
0x18000460b  mov     rsi, [rsp+108h+arg_0]
0x180004613  cmp     edi, 1
0x180004616  jnz     short loc_18000468F
0x180004618  test    ebx, ebx
0x18000461a  jnz     short loc_18000468F
0x18000461c  xor     r8d, r8d; lpvReserved
0x18000461f  xor     edx, edx; fdwReason
0x180004621  mov     rcx, rsi; hinstDLL
0x180004624  call    DllMain
0x180004629  jmp     short loc_18000463E
0x18000462b  mov     edi, [rsp+108h+arg_8]
0x180004632  mov     rsi, [rsp+108h+arg_0]
0x18000463a  mov     ebx, [rsp+108h+var_E8]
0x18000463e  xor     r8d, r8d
0x180004641  xor     edx, edx
0x180004643  mov     rcx, rsi
0x180004646  call    _CRT_INIT
0x18000464b  jmp     short loc_180004660
0x18000464d  mov     edi, [rsp+108h+arg_8]
0x180004654  mov     rsi, [rsp+108h+arg_0]
0x18000465c  mov     ebx, [rsp+108h+var_E8]
0x180004660  mov     rax, cs:_pRawDllMain
0x180004667  test    rax, rax
0x18000466a  jz      short loc_18000468F
0x18000466c  xor     r8d, r8d
0x18000466f  xor     edx, edx
0x180004671  mov     rcx, rsi
0x180004674  call    cs:__guard_dispatch_icall_fptr
0x18000467a  jmp     short loc_18000468F
0x18000467c  mov     edi, [rsp+108h+arg_8]
0x180004683  mov     rsi, [rsp+108h+arg_0]
0x18000468b  mov     ebx, [rsp+108h+var_E8]
0x18000468f  test    edi, edi
0x180004691  jz      short loc_180004698
0x180004693  cmp     edi, 3
0x180004696  jnz     short loc_180004704
0x180004698  mov     r8, [rsp+108h+lpvReserved]
0x1800046a0  mov     edx, edi
0x1800046a2  mov     rcx, rsi
0x1800046a5  call    _CRT_INIT
0x1800046aa  mov     ebx, eax
0x1800046ac  mov     [rsp+108h+var_E8], eax
0x1800046b0  jmp     short loc_1800046C7
0x1800046b2  xor     ebx, ebx
0x1800046b4  mov     [rsp+108h+var_E8], ebx
0x1800046b8  mov     edi, [rsp+108h+arg_8]
0x1800046bf  mov     rsi, [rsp+108h+arg_0]
0x1800046c7  mov     rax, cs:_pRawDllMain
0x1800046ce  test    rax, rax
0x1800046d1  jz      short loc_180004704
0x1800046d3  cmp     cs:dword_18000D0C4, 0
0x1800046da  jz      short loc_180004704
0x1800046dc  mov     r8, [rsp+108h+lpvReserved]
0x1800046e4  mov     edx, edi
0x1800046e6  mov     rcx, rsi
0x1800046e9  call    cs:__guard_dispatch_icall_fptr
0x1800046ef  mov     ebx, eax
0x1800046f1  mov     [rsp+108h+var_E8], eax
0x1800046f5  jmp     short loc_180004704
0x1800046f7  xor     ebx, ebx
0x1800046f9  mov     [rsp+108h+var_E8], ebx
0x1800046fd  mov     edi, [rsp+108h+arg_8]
0x180004704  cmp     edi, 1
0x180004707  ja      short loc_180004713
0x180004709  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180004713  mov     eax, ebx
0x180004715  add     rsp, 0F0h
0x18000471c  pop     rdi
0x18000471d  pop     rsi
0x18000471e  pop     rbx
0x18000471f  retn
0x180004cc0  push    rbp
0x180004cc2  sub     rsp, 20h
0x180004cc6  mov     rbp, rdx
0x180004cc9  mov     rax, [rcx]
0x180004ccc  mov     edx, [rax]
0x180004cce  mov     [rbp+0A8h], rcx
0x180004cd5  mov     [rbp+28h], edx
0x180004cd8  mov     eax, [rbp+28h]
0x180004cdb  cmp     eax, 0E06D7363h
0x180004ce0  jnz     short loc_180004CF6
0x180004ce2  mov     rdx, [rbp+0A8h]
0x180004ce9  mov     ecx, [rbp+28h]
0x180004cec  call    _XcptFilter_0
0x180004cf1  mov     [rbp+30h], eax
0x180004cf4  jmp     short loc_180004CFD
0x180004cf6  mov     dword ptr [rbp+30h], 0
0x180004cfd  mov     eax, [rbp+30h]
0x180004d00  add     rsp, 20h
0x180004d04  pop     rbp
0x180004d05  retn
0x180004d07  push    rbp
0x180004d09  sub     rsp, 20h
0x180004d0d  mov     rbp, rdx
0x180004d10  mov     rax, [rcx]
0x180004d13  mov     edx, [rax]
0x180004d15  mov     [rbp+0B0h], rcx
0x180004d1c  mov     [rbp+38h], edx
0x180004d1f  mov     eax, [rbp+38h]
0x180004d22  cmp     eax, 0E06D7363h
0x180004d27  jnz     short loc_180004D3D
0x180004d29  mov     rdx, [rbp+0B0h]
0x180004d30  mov     ecx, [rbp+38h]
0x180004d33  call    _XcptFilter_0
0x180004d38  mov     [rbp+40h], eax
0x180004d3b  jmp     short loc_180004D44
0x180004d3d  mov     dword ptr [rbp+40h], 0
0x180004d44  mov     eax, [rbp+40h]
0x180004d47  add     rsp, 20h
0x180004d4b  pop     rbp
0x180004d4c  retn
0x180004d4e  push    rbp
0x180004d50  sub     rsp, 20h
0x180004d54  mov     rbp, rdx
0x180004d57  mov     rax, [rcx]
0x180004d5a  mov     edx, [rax]
0x180004d5c  mov     [rbp+0B8h], rcx
0x180004d63  mov     [rbp+48h], edx
0x180004d66  mov     eax, [rbp+48h]
0x180004d69  cmp     eax, 0E06D7363h
0x180004d6e  jnz     short loc_180004D84
0x180004d70  mov     rdx, [rbp+0B8h]
0x180004d77  mov     ecx, [rbp+48h]
0x180004d7a  call    _XcptFilter_0
0x180004d7f  mov     [rbp+50h], eax
0x180004d82  jmp     short loc_180004D8B
0x180004d84  mov     dword ptr [rbp+50h], 0
0x180004d8b  mov     eax, [rbp+50h]
0x180004d8e  add     rsp, 20h
0x180004d92  pop     rbp
0x180004d93  retn
0x180004d95  push    rbp
0x180004d97  sub     rsp, 20h
0x180004d9b  mov     rbp, rdx
0x180004d9e  mov     rax, [rcx]
0x180004da1  mov     edx, [rax]
0x180004da3  mov     [rbp+0C0h], rcx
0x180004daa  mov     [rbp+58h], edx
0x180004dad  mov     eax, [rbp+58h]
0x180004db0  cmp     eax, 0E06D7363h
0x180004db5  jnz     short loc_180004DCB
0x180004db7  mov     rdx, [rbp+0C0h]
0x180004dbe  mov     ecx, [rbp+58h]
0x180004dc1  call    _XcptFilter_0
0x180004dc6  mov     [rbp+60h], eax
0x180004dc9  jmp     short loc_180004DD2
0x180004dcb  mov     dword ptr [rbp+60h], 0
0x180004dd2  mov     eax, [rbp+60h]
0x180004dd5  add     rsp, 20h
0x180004dd9  pop     rbp
0x180004dda  retn
0x180004ddc  push    rbp
0x180004dde  sub     rsp, 20h
0x180004de2  mov     rbp, rdx
0x180004de5  mov     rax, [rcx]
0x180004de8  mov     edx, [rax]
0x180004dea  mov     [rbp+0C8h], rcx
0x180004df1  mov     [rbp+68h], edx
0x180004df4  mov     eax, [rbp+68h]
0x180004df7  cmp     eax, 0E06D7363h
0x180004dfc  jnz     short loc_180004E12
0x180004dfe  mov     rdx, [rbp+0C8h]
0x180004e05  mov     ecx, [rbp+68h]
0x180004e08  call    _XcptFilter_0
0x180004e0d  mov     [rbp+70h], eax
0x180004e10  jmp     short loc_180004E19
0x180004e12  mov     dword ptr [rbp+70h], 0
0x180004e19  mov     eax, [rbp+70h]
0x180004e1c  add     rsp, 20h
0x180004e20  pop     rbp
0x180004e21  retn
0x180004e23  push    rbp
0x180004e25  sub     rsp, 20h
0x180004e29  mov     rbp, rdx
0x180004e2c  mov     rax, [rcx]
0x180004e2f  mov     edx, [rax]
0x180004e31  mov     [rbp+0D0h], rcx
0x180004e38  mov     [rbp+78h], edx
0x180004e3b  mov     eax, [rbp+78h]
0x180004e3e  cmp     eax, 0E06D7363h
0x180004e43  jnz     short loc_180004E5C
0x180004e45  mov     rdx, [rbp+0D0h]
0x180004e4c  mov     ecx, [rbp+78h]
0x180004e4f  call    _XcptFilter_0
0x180004e54  mov     [rbp+80h], eax
0x180004e5a  jmp     short loc_180004E66
0x180004e5c  mov     dword ptr [rbp+80h], 0
0x180004e66  mov     eax, [rbp+80h]
0x180004e6c  add     rsp, 20h
0x180004e70  pop     rbp
0x180004e71  retn
0x180004e73  push    rbp
0x180004e75  sub     rsp, 20h
0x180004e79  mov     rbp, rdx
0x180004e7c  mov     rax, [rcx]
0x180004e7f  mov     edx, [rax]
0x180004e81  mov     [rbp+0D8h], rcx
0x180004e88  mov     [rbp+88h], edx
0x180004e8e  mov     eax, [rbp+88h]
0x180004e94  cmp     eax, 0E06D7363h
0x180004e99  jnz     short loc_180004EB5
0x180004e9b  mov     rdx, [rbp+0D8h]
0x180004ea2  mov     ecx, [rbp+88h]
0x180004ea8  call    _XcptFilter_0
0x180004ead  mov     [rbp+90h], eax
0x180004eb3  jmp     short loc_180004EBF
0x180004eb5  mov     dword ptr [rbp+90h], 0
0x180004ebf  mov     eax, [rbp+90h]
0x180004ec5  add     rsp, 20h
0x180004ec9  pop     rbp
0x180004eca  retn
0x180004ecc  push    rbp
0x180004ece  sub     rsp, 20h
0x180004ed2  mov     rbp, rdx
0x180004ed5  mov     rax, [rcx]
0x180004ed8  mov     edx, [rax]
0x180004eda  mov     [rbp+0E0h], rcx
0x180004ee1  mov     [rbp+98h], edx
0x180004ee7  mov     eax, [rbp+98h]
0x180004eed  cmp     eax, 0E06D7363h
0x180004ef2  jnz     short loc_180004F0E
0x180004ef4  mov     rdx, [rbp+0E0h]
0x180004efb  mov     ecx, [rbp+98h]
0x180004f01  call    _XcptFilter_0
0x180004f06  mov     [rbp+0A0h], eax
0x180004f0c  jmp     short loc_180004F18
0x180004f0e  mov     dword ptr [rbp+0A0h], 0
0x180004f18  mov     eax, [rbp+0A0h]
0x180004f1e  add     rsp, 20h
0x180004f22  pop     rbp
0x180004f23  retn
0x180004f25  push    rbp
0x180004f27  sub     rsp, 20h
0x180004f2b  mov     rbp, rdx
0x180004f2e  cmp     dword ptr [rbp+118h], 1
0x180004f35  ja      short loc_180004F41
0x180004f37  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
