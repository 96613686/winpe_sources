# __DllMainCRTStartup

- ea: `0x180006b74`
- end: `0x180006d80`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006b30`

## callees

- `0x180005e60`
- `0x180006900`
- `0x180006b74`
- `0x180006dea`
- `0x1800094d0`

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
  if ( (_DWORD)fdwReason || dword_18000E3E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000E3E4 = 1;
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
            if ( dword_18000E3E4 )
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
0x180006b74  mov     [rsp+lpvReserved], r8
0x180006b79  mov     [rsp+arg_8], edx
0x180006b7d  mov     [rsp+arg_0], rcx
0x180006b82  push    rbx
0x180006b83  push    rsi
0x180006b84  push    rdi
0x180006b85  sub     rsp, 0F0h
0x180006b8c  mov     edi, edx
0x180006b8e  mov     rsi, rcx
0x180006b91  mov     ebx, 1
0x180006b96  cmp     edx, ebx
0x180006b98  ja      short loc_180006BA0
0x180006b9a  mov     cs:__native_dllmain_reason, edx
0x180006ba0  test    edx, edx
0x180006ba2  jnz     short loc_180006BB7
0x180006ba4  cmp     cs:dword_18000E3E0, edx
0x180006baa  jnz     short loc_180006BB7
0x180006bac  xor     ebx, ebx
0x180006bae  mov     [rsp+108h+var_E8], ebx
0x180006bb2  jmp     loc_180006D64
0x180006bb7  lea     eax, [rdx-1]
0x180006bba  cmp     eax, 1
0x180006bbd  ja      loc_180006C44
0x180006bc3  mov     rax, cs:_pRawDllMain
0x180006bca  test    rax, rax
0x180006bcd  jz      short loc_180006C05
0x180006bcf  cmp     edx, 1
0x180006bd2  jnz     short loc_180006BDA
0x180006bd4  mov     cs:dword_18000E3E4, edx
0x180006bda  mov     r8, [rsp+108h+lpvReserved]
0x180006be2  call    cs:__guard_dispatch_icall_fptr
0x180006be8  mov     ebx, eax
0x180006bea  mov     [rsp+108h+var_E8], eax
0x180006bee  jmp     short loc_180006C05
0x180006bf0  xor     ebx, ebx
0x180006bf2  mov     [rsp+108h+var_E8], ebx
0x180006bf6  mov     edi, [rsp+108h+arg_8]
0x180006bfd  mov     rsi, [rsp+108h+arg_0]
0x180006c05  test    ebx, ebx
0x180006c07  jz      loc_180006D64
0x180006c0d  mov     r8, [rsp+108h+lpvReserved]
0x180006c15  mov     edx, edi
0x180006c17  mov     rcx, rsi
0x180006c1a  call    _CRT_INIT
0x180006c1f  mov     ebx, eax
0x180006c21  mov     [rsp+108h+var_E8], eax
0x180006c25  jmp     short loc_180006C3C
0x180006c27  xor     ebx, ebx
0x180006c29  mov     [rsp+108h+var_E8], ebx
0x180006c2d  mov     edi, [rsp+108h+arg_8]
0x180006c34  mov     rsi, [rsp+108h+arg_0]
0x180006c3c  test    ebx, ebx
0x180006c3e  jz      loc_180006D64
0x180006c44  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180006c4c  mov     edx, edi; fdwReason
0x180006c4e  mov     rcx, rsi; hinstDLL
0x180006c51  call    DllMain
0x180006c56  mov     ebx, eax
0x180006c58  mov     [rsp+108h+var_E8], eax
0x180006c5c  jmp     short loc_180006C73
0x180006c5e  xor     ebx, ebx
0x180006c60  mov     [rsp+108h+var_E8], ebx
0x180006c64  mov     edi, [rsp+108h+arg_8]
0x180006c6b  mov     rsi, [rsp+108h+arg_0]
0x180006c73  cmp     edi, 1
0x180006c76  jnz     short loc_180006CEF
0x180006c78  test    ebx, ebx
0x180006c7a  jnz     short loc_180006CEF
0x180006c7c  xor     r8d, r8d; lpvReserved
0x180006c7f  xor     edx, edx; fdwReason
0x180006c81  mov     rcx, rsi; hinstDLL
0x180006c84  call    DllMain
0x180006c89  jmp     short loc_180006C9E
0x180006c8b  mov     edi, [rsp+108h+arg_8]
0x180006c92  mov     rsi, [rsp+108h+arg_0]
0x180006c9a  mov     ebx, [rsp+108h+var_E8]
0x180006c9e  xor     r8d, r8d
0x180006ca1  xor     edx, edx
0x180006ca3  mov     rcx, rsi
0x180006ca6  call    _CRT_INIT
0x180006cab  jmp     short loc_180006CC0
0x180006cad  mov     edi, [rsp+108h+arg_8]
0x180006cb4  mov     rsi, [rsp+108h+arg_0]
0x180006cbc  mov     ebx, [rsp+108h+var_E8]
0x180006cc0  mov     rax, cs:_pRawDllMain
0x180006cc7  test    rax, rax
0x180006cca  jz      short loc_180006CEF
0x180006ccc  xor     r8d, r8d
0x180006ccf  xor     edx, edx
0x180006cd1  mov     rcx, rsi
0x180006cd4  call    cs:__guard_dispatch_icall_fptr
0x180006cda  jmp     short loc_180006CEF
0x180006cdc  mov     edi, [rsp+108h+arg_8]
0x180006ce3  mov     rsi, [rsp+108h+arg_0]
0x180006ceb  mov     ebx, [rsp+108h+var_E8]
0x180006cef  test    edi, edi
0x180006cf1  jz      short loc_180006CF8
0x180006cf3  cmp     edi, 3
0x180006cf6  jnz     short loc_180006D64
0x180006cf8  mov     r8, [rsp+108h+lpvReserved]
0x180006d00  mov     edx, edi
0x180006d02  mov     rcx, rsi
0x180006d05  call    _CRT_INIT
0x180006d0a  mov     ebx, eax
0x180006d0c  mov     [rsp+108h+var_E8], eax
0x180006d10  jmp     short loc_180006D27
0x180006d12  xor     ebx, ebx
0x180006d14  mov     [rsp+108h+var_E8], ebx
0x180006d18  mov     edi, [rsp+108h+arg_8]
0x180006d1f  mov     rsi, [rsp+108h+arg_0]
0x180006d27  mov     rax, cs:_pRawDllMain
0x180006d2e  test    rax, rax
0x180006d31  jz      short loc_180006D64
0x180006d33  cmp     cs:dword_18000E3E4, 0
0x180006d3a  jz      short loc_180006D64
0x180006d3c  mov     r8, [rsp+108h+lpvReserved]
0x180006d44  mov     edx, edi
0x180006d46  mov     rcx, rsi
0x180006d49  call    cs:__guard_dispatch_icall_fptr
0x180006d4f  mov     ebx, eax
0x180006d51  mov     [rsp+108h+var_E8], eax
0x180006d55  jmp     short loc_180006D64
0x180006d57  xor     ebx, ebx
0x180006d59  mov     [rsp+108h+var_E8], ebx
0x180006d5d  mov     edi, [rsp+108h+arg_8]
0x180006d64  cmp     edi, 1
0x180006d67  ja      short loc_180006D73
0x180006d69  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180006d73  mov     eax, ebx
0x180006d75  add     rsp, 0F0h
0x180006d7c  pop     rdi
0x180006d7d  pop     rsi
0x180006d7e  pop     rbx
0x180006d7f  retn
0x180009540  push    rbp
0x180009542  sub     rsp, 20h
0x180009546  mov     rbp, rdx
0x180009549  mov     rax, [rcx]
0x18000954c  mov     edx, [rax]
0x18000954e  mov     [rbp+0A8h], rcx
0x180009555  mov     [rbp+28h], edx
0x180009558  mov     eax, [rbp+28h]
0x18000955b  cmp     eax, 0E06D7363h
0x180009560  jnz     short loc_180009576
0x180009562  mov     rdx, [rbp+0A8h]
0x180009569  mov     ecx, [rbp+28h]
0x18000956c  call    _XcptFilter_0
0x180009571  mov     [rbp+30h], eax
0x180009574  jmp     short loc_18000957D
0x180009576  mov     dword ptr [rbp+30h], 0
0x18000957d  mov     eax, [rbp+30h]
0x180009580  add     rsp, 20h
0x180009584  pop     rbp
0x180009585  retn
0x180009587  push    rbp
0x180009589  sub     rsp, 20h
0x18000958d  mov     rbp, rdx
0x180009590  mov     rax, [rcx]
0x180009593  mov     edx, [rax]
0x180009595  mov     [rbp+0B0h], rcx
0x18000959c  mov     [rbp+38h], edx
0x18000959f  mov     eax, [rbp+38h]
0x1800095a2  cmp     eax, 0E06D7363h
0x1800095a7  jnz     short loc_1800095BD
0x1800095a9  mov     rdx, [rbp+0B0h]
0x1800095b0  mov     ecx, [rbp+38h]
0x1800095b3  call    _XcptFilter_0
0x1800095b8  mov     [rbp+40h], eax
0x1800095bb  jmp     short loc_1800095C4
0x1800095bd  mov     dword ptr [rbp+40h], 0
0x1800095c4  mov     eax, [rbp+40h]
0x1800095c7  add     rsp, 20h
0x1800095cb  pop     rbp
0x1800095cc  retn
0x1800095ce  push    rbp
0x1800095d0  sub     rsp, 20h
0x1800095d4  mov     rbp, rdx
0x1800095d7  mov     rax, [rcx]
0x1800095da  mov     edx, [rax]
0x1800095dc  mov     [rbp+0B8h], rcx
0x1800095e3  mov     [rbp+48h], edx
0x1800095e6  mov     eax, [rbp+48h]
0x1800095e9  cmp     eax, 0E06D7363h
0x1800095ee  jnz     short loc_180009604
0x1800095f0  mov     rdx, [rbp+0B8h]
0x1800095f7  mov     ecx, [rbp+48h]
0x1800095fa  call    _XcptFilter_0
0x1800095ff  mov     [rbp+50h], eax
0x180009602  jmp     short loc_18000960B
0x180009604  mov     dword ptr [rbp+50h], 0
0x18000960b  mov     eax, [rbp+50h]
0x18000960e  add     rsp, 20h
0x180009612  pop     rbp
0x180009613  retn
0x180009615  push    rbp
0x180009617  sub     rsp, 20h
0x18000961b  mov     rbp, rdx
0x18000961e  mov     rax, [rcx]
0x180009621  mov     edx, [rax]
0x180009623  mov     [rbp+0C0h], rcx
0x18000962a  mov     [rbp+58h], edx
0x18000962d  mov     eax, [rbp+58h]
0x180009630  cmp     eax, 0E06D7363h
0x180009635  jnz     short loc_18000964B
0x180009637  mov     rdx, [rbp+0C0h]
0x18000963e  mov     ecx, [rbp+58h]
0x180009641  call    _XcptFilter_0
0x180009646  mov     [rbp+60h], eax
0x180009649  jmp     short loc_180009652
0x18000964b  mov     dword ptr [rbp+60h], 0
0x180009652  mov     eax, [rbp+60h]
0x180009655  add     rsp, 20h
0x180009659  pop     rbp
0x18000965a  retn
0x18000965c  push    rbp
0x18000965e  sub     rsp, 20h
0x180009662  mov     rbp, rdx
0x180009665  mov     rax, [rcx]
0x180009668  mov     edx, [rax]
0x18000966a  mov     [rbp+0C8h], rcx
0x180009671  mov     [rbp+68h], edx
0x180009674  mov     eax, [rbp+68h]
0x180009677  cmp     eax, 0E06D7363h
0x18000967c  jnz     short loc_180009692
0x18000967e  mov     rdx, [rbp+0C8h]
0x180009685  mov     ecx, [rbp+68h]
0x180009688  call    _XcptFilter_0
0x18000968d  mov     [rbp+70h], eax
0x180009690  jmp     short loc_180009699
0x180009692  mov     dword ptr [rbp+70h], 0
0x180009699  mov     eax, [rbp+70h]
0x18000969c  add     rsp, 20h
0x1800096a0  pop     rbp
0x1800096a1  retn
0x1800096a3  push    rbp
0x1800096a5  sub     rsp, 20h
0x1800096a9  mov     rbp, rdx
0x1800096ac  mov     rax, [rcx]
0x1800096af  mov     edx, [rax]
0x1800096b1  mov     [rbp+0D0h], rcx
0x1800096b8  mov     [rbp+78h], edx
0x1800096bb  mov     eax, [rbp+78h]
0x1800096be  cmp     eax, 0E06D7363h
0x1800096c3  jnz     short loc_1800096DC
0x1800096c5  mov     rdx, [rbp+0D0h]
0x1800096cc  mov     ecx, [rbp+78h]
0x1800096cf  call    _XcptFilter_0
0x1800096d4  mov     [rbp+80h], eax
0x1800096da  jmp     short loc_1800096E6
0x1800096dc  mov     dword ptr [rbp+80h], 0
0x1800096e6  mov     eax, [rbp+80h]
0x1800096ec  add     rsp, 20h
0x1800096f0  pop     rbp
0x1800096f1  retn
0x1800096f3  push    rbp
0x1800096f5  sub     rsp, 20h
0x1800096f9  mov     rbp, rdx
0x1800096fc  mov     rax, [rcx]
0x1800096ff  mov     edx, [rax]
0x180009701  mov     [rbp+0D8h], rcx
0x180009708  mov     [rbp+88h], edx
0x18000970e  mov     eax, [rbp+88h]
0x180009714  cmp     eax, 0E06D7363h
0x180009719  jnz     short loc_180009735
0x18000971b  mov     rdx, [rbp+0D8h]
0x180009722  mov     ecx, [rbp+88h]
0x180009728  call    _XcptFilter_0
0x18000972d  mov     [rbp+90h], eax
0x180009733  jmp     short loc_18000973F
0x180009735  mov     dword ptr [rbp+90h], 0
0x18000973f  mov     eax, [rbp+90h]
0x180009745  add     rsp, 20h
0x180009749  pop     rbp
0x18000974a  retn
0x18000974c  push    rbp
0x18000974e  sub     rsp, 20h
0x180009752  mov     rbp, rdx
0x180009755  mov     rax, [rcx]
0x180009758  mov     edx, [rax]
0x18000975a  mov     [rbp+0E0h], rcx
0x180009761  mov     [rbp+98h], edx
0x180009767  mov     eax, [rbp+98h]
0x18000976d  cmp     eax, 0E06D7363h
0x180009772  jnz     short loc_18000978E
0x180009774  mov     rdx, [rbp+0E0h]
0x18000977b  mov     ecx, [rbp+98h]
0x180009781  call    _XcptFilter_0
0x180009786  mov     [rbp+0A0h], eax
0x18000978c  jmp     short loc_180009798
0x18000978e  mov     dword ptr [rbp+0A0h], 0
0x180009798  mov     eax, [rbp+0A0h]
0x18000979e  add     rsp, 20h
0x1800097a2  pop     rbp
0x1800097a3  retn
0x1800097a5  push    rbp
0x1800097a7  sub     rsp, 20h
0x1800097ab  mov     rbp, rdx
0x1800097ae  cmp     dword ptr [rbp+118h], 1
0x1800097b5  ja      short loc_1800097C1
0x1800097b7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
