# __DllMainCRTStartup

- ea: `0x180008bc4`
- end: `0x180008dd0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008b80`

## callees

- `0x180008950`
- `0x180008bc4`
- `0x180008dfa`
- `0x180008fd8`
- `0x18000c9b0`

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
  if ( (_DWORD)fdwReason || dword_1800130C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800130C4 = 1;
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
            if ( dword_1800130C4 )
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
0x180008bc4  mov     [rsp+lpvReserved], r8
0x180008bc9  mov     [rsp+arg_8], edx
0x180008bcd  mov     [rsp+arg_0], rcx
0x180008bd2  push    rbx
0x180008bd3  push    rsi
0x180008bd4  push    rdi
0x180008bd5  sub     rsp, 0F0h
0x180008bdc  mov     edi, edx
0x180008bde  mov     rsi, rcx
0x180008be1  mov     ebx, 1
0x180008be6  cmp     edx, ebx
0x180008be8  ja      short loc_180008BF0
0x180008bea  mov     cs:__native_dllmain_reason, edx
0x180008bf0  test    edx, edx
0x180008bf2  jnz     short loc_180008C07
0x180008bf4  cmp     cs:dword_1800130C0, edx
0x180008bfa  jnz     short loc_180008C07
0x180008bfc  xor     ebx, ebx
0x180008bfe  mov     [rsp+108h+var_E8], ebx
0x180008c02  jmp     loc_180008DB4
0x180008c07  lea     eax, [rdx-1]
0x180008c0a  cmp     eax, 1
0x180008c0d  ja      loc_180008C94
0x180008c13  mov     rax, cs:_pRawDllMain
0x180008c1a  test    rax, rax
0x180008c1d  jz      short loc_180008C55
0x180008c1f  cmp     edx, 1
0x180008c22  jnz     short loc_180008C2A
0x180008c24  mov     cs:dword_1800130C4, edx
0x180008c2a  mov     r8, [rsp+108h+lpvReserved]
0x180008c32  call    cs:__guard_dispatch_icall_fptr
0x180008c38  mov     ebx, eax
0x180008c3a  mov     [rsp+108h+var_E8], eax
0x180008c3e  jmp     short loc_180008C55
0x180008c40  xor     ebx, ebx
0x180008c42  mov     [rsp+108h+var_E8], ebx
0x180008c46  mov     edi, [rsp+108h+arg_8]
0x180008c4d  mov     rsi, [rsp+108h+arg_0]
0x180008c55  test    ebx, ebx
0x180008c57  jz      loc_180008DB4
0x180008c5d  mov     r8, [rsp+108h+lpvReserved]
0x180008c65  mov     edx, edi
0x180008c67  mov     rcx, rsi
0x180008c6a  call    _CRT_INIT
0x180008c6f  mov     ebx, eax
0x180008c71  mov     [rsp+108h+var_E8], eax
0x180008c75  jmp     short loc_180008C8C
0x180008c77  xor     ebx, ebx
0x180008c79  mov     [rsp+108h+var_E8], ebx
0x180008c7d  mov     edi, [rsp+108h+arg_8]
0x180008c84  mov     rsi, [rsp+108h+arg_0]
0x180008c8c  test    ebx, ebx
0x180008c8e  jz      loc_180008DB4
0x180008c94  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180008c9c  mov     edx, edi; fdwReason
0x180008c9e  mov     rcx, rsi; hinstDLL
0x180008ca1  call    DllMain
0x180008ca6  mov     ebx, eax
0x180008ca8  mov     [rsp+108h+var_E8], eax
0x180008cac  jmp     short loc_180008CC3
0x180008cae  xor     ebx, ebx
0x180008cb0  mov     [rsp+108h+var_E8], ebx
0x180008cb4  mov     edi, [rsp+108h+arg_8]
0x180008cbb  mov     rsi, [rsp+108h+arg_0]
0x180008cc3  cmp     edi, 1
0x180008cc6  jnz     short loc_180008D3F
0x180008cc8  test    ebx, ebx
0x180008cca  jnz     short loc_180008D3F
0x180008ccc  xor     r8d, r8d; lpvReserved
0x180008ccf  xor     edx, edx; fdwReason
0x180008cd1  mov     rcx, rsi; hinstDLL
0x180008cd4  call    DllMain
0x180008cd9  jmp     short loc_180008CEE
0x180008cdb  mov     edi, [rsp+108h+arg_8]
0x180008ce2  mov     rsi, [rsp+108h+arg_0]
0x180008cea  mov     ebx, [rsp+108h+var_E8]
0x180008cee  xor     r8d, r8d
0x180008cf1  xor     edx, edx
0x180008cf3  mov     rcx, rsi
0x180008cf6  call    _CRT_INIT
0x180008cfb  jmp     short loc_180008D10
0x180008cfd  mov     edi, [rsp+108h+arg_8]
0x180008d04  mov     rsi, [rsp+108h+arg_0]
0x180008d0c  mov     ebx, [rsp+108h+var_E8]
0x180008d10  mov     rax, cs:_pRawDllMain
0x180008d17  test    rax, rax
0x180008d1a  jz      short loc_180008D3F
0x180008d1c  xor     r8d, r8d
0x180008d1f  xor     edx, edx
0x180008d21  mov     rcx, rsi
0x180008d24  call    cs:__guard_dispatch_icall_fptr
0x180008d2a  jmp     short loc_180008D3F
0x180008d2c  mov     edi, [rsp+108h+arg_8]
0x180008d33  mov     rsi, [rsp+108h+arg_0]
0x180008d3b  mov     ebx, [rsp+108h+var_E8]
0x180008d3f  test    edi, edi
0x180008d41  jz      short loc_180008D48
0x180008d43  cmp     edi, 3
0x180008d46  jnz     short loc_180008DB4
0x180008d48  mov     r8, [rsp+108h+lpvReserved]
0x180008d50  mov     edx, edi
0x180008d52  mov     rcx, rsi
0x180008d55  call    _CRT_INIT
0x180008d5a  mov     ebx, eax
0x180008d5c  mov     [rsp+108h+var_E8], eax
0x180008d60  jmp     short loc_180008D77
0x180008d62  xor     ebx, ebx
0x180008d64  mov     [rsp+108h+var_E8], ebx
0x180008d68  mov     edi, [rsp+108h+arg_8]
0x180008d6f  mov     rsi, [rsp+108h+arg_0]
0x180008d77  mov     rax, cs:_pRawDllMain
0x180008d7e  test    rax, rax
0x180008d81  jz      short loc_180008DB4
0x180008d83  cmp     cs:dword_1800130C4, 0
0x180008d8a  jz      short loc_180008DB4
0x180008d8c  mov     r8, [rsp+108h+lpvReserved]
0x180008d94  mov     edx, edi
0x180008d96  mov     rcx, rsi
0x180008d99  call    cs:__guard_dispatch_icall_fptr
0x180008d9f  mov     ebx, eax
0x180008da1  mov     [rsp+108h+var_E8], eax
0x180008da5  jmp     short loc_180008DB4
0x180008da7  xor     ebx, ebx
0x180008da9  mov     [rsp+108h+var_E8], ebx
0x180008dad  mov     edi, [rsp+108h+arg_8]
0x180008db4  cmp     edi, 1
0x180008db7  ja      short loc_180008DC3
0x180008db9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180008dc3  mov     eax, ebx
0x180008dc5  add     rsp, 0F0h
0x180008dcc  pop     rdi
0x180008dcd  pop     rsi
0x180008dce  pop     rbx
0x180008dcf  retn
0x18000ca20  push    rbp
0x18000ca22  sub     rsp, 20h
0x18000ca26  mov     rbp, rdx
0x18000ca29  mov     rax, [rcx]
0x18000ca2c  mov     edx, [rax]
0x18000ca2e  mov     [rbp+0A8h], rcx
0x18000ca35  mov     [rbp+28h], edx
0x18000ca38  mov     eax, [rbp+28h]
0x18000ca3b  cmp     eax, 0E06D7363h
0x18000ca40  jnz     short loc_18000CA56
0x18000ca42  mov     rdx, [rbp+0A8h]
0x18000ca49  mov     ecx, [rbp+28h]
0x18000ca4c  call    _XcptFilter_0
0x18000ca51  mov     [rbp+30h], eax
0x18000ca54  jmp     short loc_18000CA5D
0x18000ca56  mov     dword ptr [rbp+30h], 0
0x18000ca5d  mov     eax, [rbp+30h]
0x18000ca60  add     rsp, 20h
0x18000ca64  pop     rbp
0x18000ca65  retn
0x18000ca67  push    rbp
0x18000ca69  sub     rsp, 20h
0x18000ca6d  mov     rbp, rdx
0x18000ca70  mov     rax, [rcx]
0x18000ca73  mov     edx, [rax]
0x18000ca75  mov     [rbp+0B0h], rcx
0x18000ca7c  mov     [rbp+38h], edx
0x18000ca7f  mov     eax, [rbp+38h]
0x18000ca82  cmp     eax, 0E06D7363h
0x18000ca87  jnz     short loc_18000CA9D
0x18000ca89  mov     rdx, [rbp+0B0h]
0x18000ca90  mov     ecx, [rbp+38h]
0x18000ca93  call    _XcptFilter_0
0x18000ca98  mov     [rbp+40h], eax
0x18000ca9b  jmp     short loc_18000CAA4
0x18000ca9d  mov     dword ptr [rbp+40h], 0
0x18000caa4  mov     eax, [rbp+40h]
0x18000caa7  add     rsp, 20h
0x18000caab  pop     rbp
0x18000caac  retn
0x18000caae  push    rbp
0x18000cab0  sub     rsp, 20h
0x18000cab4  mov     rbp, rdx
0x18000cab7  mov     rax, [rcx]
0x18000caba  mov     edx, [rax]
0x18000cabc  mov     [rbp+0B8h], rcx
0x18000cac3  mov     [rbp+48h], edx
0x18000cac6  mov     eax, [rbp+48h]
0x18000cac9  cmp     eax, 0E06D7363h
0x18000cace  jnz     short loc_18000CAE4
0x18000cad0  mov     rdx, [rbp+0B8h]
0x18000cad7  mov     ecx, [rbp+48h]
0x18000cada  call    _XcptFilter_0
0x18000cadf  mov     [rbp+50h], eax
0x18000cae2  jmp     short loc_18000CAEB
0x18000cae4  mov     dword ptr [rbp+50h], 0
0x18000caeb  mov     eax, [rbp+50h]
0x18000caee  add     rsp, 20h
0x18000caf2  pop     rbp
0x18000caf3  retn
0x18000caf5  push    rbp
0x18000caf7  sub     rsp, 20h
0x18000cafb  mov     rbp, rdx
0x18000cafe  mov     rax, [rcx]
0x18000cb01  mov     edx, [rax]
0x18000cb03  mov     [rbp+0C0h], rcx
0x18000cb0a  mov     [rbp+58h], edx
0x18000cb0d  mov     eax, [rbp+58h]
0x18000cb10  cmp     eax, 0E06D7363h
0x18000cb15  jnz     short loc_18000CB2B
0x18000cb17  mov     rdx, [rbp+0C0h]
0x18000cb1e  mov     ecx, [rbp+58h]
0x18000cb21  call    _XcptFilter_0
0x18000cb26  mov     [rbp+60h], eax
0x18000cb29  jmp     short loc_18000CB32
0x18000cb2b  mov     dword ptr [rbp+60h], 0
0x18000cb32  mov     eax, [rbp+60h]
0x18000cb35  add     rsp, 20h
0x18000cb39  pop     rbp
0x18000cb3a  retn
0x18000cb3c  push    rbp
0x18000cb3e  sub     rsp, 20h
0x18000cb42  mov     rbp, rdx
0x18000cb45  mov     rax, [rcx]
0x18000cb48  mov     edx, [rax]
0x18000cb4a  mov     [rbp+0C8h], rcx
0x18000cb51  mov     [rbp+68h], edx
0x18000cb54  mov     eax, [rbp+68h]
0x18000cb57  cmp     eax, 0E06D7363h
0x18000cb5c  jnz     short loc_18000CB72
0x18000cb5e  mov     rdx, [rbp+0C8h]
0x18000cb65  mov     ecx, [rbp+68h]
0x18000cb68  call    _XcptFilter_0
0x18000cb6d  mov     [rbp+70h], eax
0x18000cb70  jmp     short loc_18000CB79
0x18000cb72  mov     dword ptr [rbp+70h], 0
0x18000cb79  mov     eax, [rbp+70h]
0x18000cb7c  add     rsp, 20h
0x18000cb80  pop     rbp
0x18000cb81  retn
0x18000cb83  push    rbp
0x18000cb85  sub     rsp, 20h
0x18000cb89  mov     rbp, rdx
0x18000cb8c  mov     rax, [rcx]
0x18000cb8f  mov     edx, [rax]
0x18000cb91  mov     [rbp+0D0h], rcx
0x18000cb98  mov     [rbp+78h], edx
0x18000cb9b  mov     eax, [rbp+78h]
0x18000cb9e  cmp     eax, 0E06D7363h
0x18000cba3  jnz     short loc_18000CBBC
0x18000cba5  mov     rdx, [rbp+0D0h]
0x18000cbac  mov     ecx, [rbp+78h]
0x18000cbaf  call    _XcptFilter_0
0x18000cbb4  mov     [rbp+80h], eax
0x18000cbba  jmp     short loc_18000CBC6
0x18000cbbc  mov     dword ptr [rbp+80h], 0
0x18000cbc6  mov     eax, [rbp+80h]
0x18000cbcc  add     rsp, 20h
0x18000cbd0  pop     rbp
0x18000cbd1  retn
0x18000cbd3  push    rbp
0x18000cbd5  sub     rsp, 20h
0x18000cbd9  mov     rbp, rdx
0x18000cbdc  mov     rax, [rcx]
0x18000cbdf  mov     edx, [rax]
0x18000cbe1  mov     [rbp+0D8h], rcx
0x18000cbe8  mov     [rbp+88h], edx
0x18000cbee  mov     eax, [rbp+88h]
0x18000cbf4  cmp     eax, 0E06D7363h
0x18000cbf9  jnz     short loc_18000CC15
0x18000cbfb  mov     rdx, [rbp+0D8h]
0x18000cc02  mov     ecx, [rbp+88h]
0x18000cc08  call    _XcptFilter_0
0x18000cc0d  mov     [rbp+90h], eax
0x18000cc13  jmp     short loc_18000CC1F
0x18000cc15  mov     dword ptr [rbp+90h], 0
0x18000cc1f  mov     eax, [rbp+90h]
0x18000cc25  add     rsp, 20h
0x18000cc29  pop     rbp
0x18000cc2a  retn
0x18000cc2c  push    rbp
0x18000cc2e  sub     rsp, 20h
0x18000cc32  mov     rbp, rdx
0x18000cc35  mov     rax, [rcx]
0x18000cc38  mov     edx, [rax]
0x18000cc3a  mov     [rbp+0E0h], rcx
0x18000cc41  mov     [rbp+98h], edx
0x18000cc47  mov     eax, [rbp+98h]
0x18000cc4d  cmp     eax, 0E06D7363h
0x18000cc52  jnz     short loc_18000CC6E
0x18000cc54  mov     rdx, [rbp+0E0h]
0x18000cc5b  mov     ecx, [rbp+98h]
0x18000cc61  call    _XcptFilter_0
0x18000cc66  mov     [rbp+0A0h], eax
0x18000cc6c  jmp     short loc_18000CC78
0x18000cc6e  mov     dword ptr [rbp+0A0h], 0
0x18000cc78  mov     eax, [rbp+0A0h]
0x18000cc7e  add     rsp, 20h
0x18000cc82  pop     rbp
0x18000cc83  retn
0x18000cc85  push    rbp
0x18000cc87  sub     rsp, 20h
0x18000cc8b  mov     rbp, rdx
0x18000cc8e  cmp     dword ptr [rbp+118h], 1
0x18000cc95  ja      short loc_18000CCA1
0x18000cc97  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
