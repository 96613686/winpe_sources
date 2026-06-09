# __DllMainCRTStartup

- ea: `0x180005d14`
- end: `0x180005f20`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005cd0`

## callees

- `0x180005aa0`
- `0x180005d14`
- `0x180005f4a`
- `0x180006128`
- `0x180008c30`

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
  if ( (_DWORD)fdwReason || dword_18000E0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000E0A4 = 1;
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
            if ( dword_18000E0A4 )
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
0x180005d14  mov     [rsp+lpvReserved], r8
0x180005d19  mov     [rsp+arg_8], edx
0x180005d1d  mov     [rsp+arg_0], rcx
0x180005d22  push    rbx
0x180005d23  push    rsi
0x180005d24  push    rdi
0x180005d25  sub     rsp, 0F0h
0x180005d2c  mov     edi, edx
0x180005d2e  mov     rsi, rcx
0x180005d31  mov     ebx, 1
0x180005d36  cmp     edx, ebx
0x180005d38  ja      short loc_180005D40
0x180005d3a  mov     cs:__native_dllmain_reason, edx
0x180005d40  test    edx, edx
0x180005d42  jnz     short loc_180005D57
0x180005d44  cmp     cs:dword_18000E0A0, edx
0x180005d4a  jnz     short loc_180005D57
0x180005d4c  xor     ebx, ebx
0x180005d4e  mov     [rsp+108h+var_E8], ebx
0x180005d52  jmp     loc_180005F04
0x180005d57  lea     eax, [rdx-1]
0x180005d5a  cmp     eax, 1
0x180005d5d  ja      loc_180005DE4
0x180005d63  mov     rax, cs:_pRawDllMain
0x180005d6a  test    rax, rax
0x180005d6d  jz      short loc_180005DA5
0x180005d6f  cmp     edx, 1
0x180005d72  jnz     short loc_180005D7A
0x180005d74  mov     cs:dword_18000E0A4, edx
0x180005d7a  mov     r8, [rsp+108h+lpvReserved]
0x180005d82  call    cs:__guard_dispatch_icall_fptr
0x180005d88  mov     ebx, eax
0x180005d8a  mov     [rsp+108h+var_E8], eax
0x180005d8e  jmp     short loc_180005DA5
0x180005d90  xor     ebx, ebx
0x180005d92  mov     [rsp+108h+var_E8], ebx
0x180005d96  mov     edi, [rsp+108h+arg_8]
0x180005d9d  mov     rsi, [rsp+108h+arg_0]
0x180005da5  test    ebx, ebx
0x180005da7  jz      loc_180005F04
0x180005dad  mov     r8, [rsp+108h+lpvReserved]
0x180005db5  mov     edx, edi
0x180005db7  mov     rcx, rsi
0x180005dba  call    _CRT_INIT
0x180005dbf  mov     ebx, eax
0x180005dc1  mov     [rsp+108h+var_E8], eax
0x180005dc5  jmp     short loc_180005DDC
0x180005dc7  xor     ebx, ebx
0x180005dc9  mov     [rsp+108h+var_E8], ebx
0x180005dcd  mov     edi, [rsp+108h+arg_8]
0x180005dd4  mov     rsi, [rsp+108h+arg_0]
0x180005ddc  test    ebx, ebx
0x180005dde  jz      loc_180005F04
0x180005de4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180005dec  mov     edx, edi; fdwReason
0x180005dee  mov     rcx, rsi; hinstDLL
0x180005df1  call    DllMain
0x180005df6  mov     ebx, eax
0x180005df8  mov     [rsp+108h+var_E8], eax
0x180005dfc  jmp     short loc_180005E13
0x180005dfe  xor     ebx, ebx
0x180005e00  mov     [rsp+108h+var_E8], ebx
0x180005e04  mov     edi, [rsp+108h+arg_8]
0x180005e0b  mov     rsi, [rsp+108h+arg_0]
0x180005e13  cmp     edi, 1
0x180005e16  jnz     short loc_180005E8F
0x180005e18  test    ebx, ebx
0x180005e1a  jnz     short loc_180005E8F
0x180005e1c  xor     r8d, r8d; lpvReserved
0x180005e1f  xor     edx, edx; fdwReason
0x180005e21  mov     rcx, rsi; hinstDLL
0x180005e24  call    DllMain
0x180005e29  jmp     short loc_180005E3E
0x180005e2b  mov     edi, [rsp+108h+arg_8]
0x180005e32  mov     rsi, [rsp+108h+arg_0]
0x180005e3a  mov     ebx, [rsp+108h+var_E8]
0x180005e3e  xor     r8d, r8d
0x180005e41  xor     edx, edx
0x180005e43  mov     rcx, rsi
0x180005e46  call    _CRT_INIT
0x180005e4b  jmp     short loc_180005E60
0x180005e4d  mov     edi, [rsp+108h+arg_8]
0x180005e54  mov     rsi, [rsp+108h+arg_0]
0x180005e5c  mov     ebx, [rsp+108h+var_E8]
0x180005e60  mov     rax, cs:_pRawDllMain
0x180005e67  test    rax, rax
0x180005e6a  jz      short loc_180005E8F
0x180005e6c  xor     r8d, r8d
0x180005e6f  xor     edx, edx
0x180005e71  mov     rcx, rsi
0x180005e74  call    cs:__guard_dispatch_icall_fptr
0x180005e7a  jmp     short loc_180005E8F
0x180005e7c  mov     edi, [rsp+108h+arg_8]
0x180005e83  mov     rsi, [rsp+108h+arg_0]
0x180005e8b  mov     ebx, [rsp+108h+var_E8]
0x180005e8f  test    edi, edi
0x180005e91  jz      short loc_180005E98
0x180005e93  cmp     edi, 3
0x180005e96  jnz     short loc_180005F04
0x180005e98  mov     r8, [rsp+108h+lpvReserved]
0x180005ea0  mov     edx, edi
0x180005ea2  mov     rcx, rsi
0x180005ea5  call    _CRT_INIT
0x180005eaa  mov     ebx, eax
0x180005eac  mov     [rsp+108h+var_E8], eax
0x180005eb0  jmp     short loc_180005EC7
0x180005eb2  xor     ebx, ebx
0x180005eb4  mov     [rsp+108h+var_E8], ebx
0x180005eb8  mov     edi, [rsp+108h+arg_8]
0x180005ebf  mov     rsi, [rsp+108h+arg_0]
0x180005ec7  mov     rax, cs:_pRawDllMain
0x180005ece  test    rax, rax
0x180005ed1  jz      short loc_180005F04
0x180005ed3  cmp     cs:dword_18000E0A4, 0
0x180005eda  jz      short loc_180005F04
0x180005edc  mov     r8, [rsp+108h+lpvReserved]
0x180005ee4  mov     edx, edi
0x180005ee6  mov     rcx, rsi
0x180005ee9  call    cs:__guard_dispatch_icall_fptr
0x180005eef  mov     ebx, eax
0x180005ef1  mov     [rsp+108h+var_E8], eax
0x180005ef5  jmp     short loc_180005F04
0x180005ef7  xor     ebx, ebx
0x180005ef9  mov     [rsp+108h+var_E8], ebx
0x180005efd  mov     edi, [rsp+108h+arg_8]
0x180005f04  cmp     edi, 1
0x180005f07  ja      short loc_180005F13
0x180005f09  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180005f13  mov     eax, ebx
0x180005f15  add     rsp, 0F0h
0x180005f1c  pop     rdi
0x180005f1d  pop     rsi
0x180005f1e  pop     rbx
0x180005f1f  retn
0x180008ca0  push    rbp
0x180008ca2  sub     rsp, 20h
0x180008ca6  mov     rbp, rdx
0x180008ca9  mov     rax, [rcx]
0x180008cac  mov     edx, [rax]
0x180008cae  mov     [rbp+0A8h], rcx
0x180008cb5  mov     [rbp+28h], edx
0x180008cb8  mov     eax, [rbp+28h]
0x180008cbb  cmp     eax, 0E06D7363h
0x180008cc0  jnz     short loc_180008CD6
0x180008cc2  mov     rdx, [rbp+0A8h]
0x180008cc9  mov     ecx, [rbp+28h]
0x180008ccc  call    _XcptFilter_0
0x180008cd1  mov     [rbp+30h], eax
0x180008cd4  jmp     short loc_180008CDD
0x180008cd6  mov     dword ptr [rbp+30h], 0
0x180008cdd  mov     eax, [rbp+30h]
0x180008ce0  add     rsp, 20h
0x180008ce4  pop     rbp
0x180008ce5  retn
0x180008ce7  push    rbp
0x180008ce9  sub     rsp, 20h
0x180008ced  mov     rbp, rdx
0x180008cf0  mov     rax, [rcx]
0x180008cf3  mov     edx, [rax]
0x180008cf5  mov     [rbp+0B0h], rcx
0x180008cfc  mov     [rbp+38h], edx
0x180008cff  mov     eax, [rbp+38h]
0x180008d02  cmp     eax, 0E06D7363h
0x180008d07  jnz     short loc_180008D1D
0x180008d09  mov     rdx, [rbp+0B0h]
0x180008d10  mov     ecx, [rbp+38h]
0x180008d13  call    _XcptFilter_0
0x180008d18  mov     [rbp+40h], eax
0x180008d1b  jmp     short loc_180008D24
0x180008d1d  mov     dword ptr [rbp+40h], 0
0x180008d24  mov     eax, [rbp+40h]
0x180008d27  add     rsp, 20h
0x180008d2b  pop     rbp
0x180008d2c  retn
0x180008d2e  push    rbp
0x180008d30  sub     rsp, 20h
0x180008d34  mov     rbp, rdx
0x180008d37  mov     rax, [rcx]
0x180008d3a  mov     edx, [rax]
0x180008d3c  mov     [rbp+0B8h], rcx
0x180008d43  mov     [rbp+48h], edx
0x180008d46  mov     eax, [rbp+48h]
0x180008d49  cmp     eax, 0E06D7363h
0x180008d4e  jnz     short loc_180008D64
0x180008d50  mov     rdx, [rbp+0B8h]
0x180008d57  mov     ecx, [rbp+48h]
0x180008d5a  call    _XcptFilter_0
0x180008d5f  mov     [rbp+50h], eax
0x180008d62  jmp     short loc_180008D6B
0x180008d64  mov     dword ptr [rbp+50h], 0
0x180008d6b  mov     eax, [rbp+50h]
0x180008d6e  add     rsp, 20h
0x180008d72  pop     rbp
0x180008d73  retn
0x180008d75  push    rbp
0x180008d77  sub     rsp, 20h
0x180008d7b  mov     rbp, rdx
0x180008d7e  mov     rax, [rcx]
0x180008d81  mov     edx, [rax]
0x180008d83  mov     [rbp+0C0h], rcx
0x180008d8a  mov     [rbp+58h], edx
0x180008d8d  mov     eax, [rbp+58h]
0x180008d90  cmp     eax, 0E06D7363h
0x180008d95  jnz     short loc_180008DAB
0x180008d97  mov     rdx, [rbp+0C0h]
0x180008d9e  mov     ecx, [rbp+58h]
0x180008da1  call    _XcptFilter_0
0x180008da6  mov     [rbp+60h], eax
0x180008da9  jmp     short loc_180008DB2
0x180008dab  mov     dword ptr [rbp+60h], 0
0x180008db2  mov     eax, [rbp+60h]
0x180008db5  add     rsp, 20h
0x180008db9  pop     rbp
0x180008dba  retn
0x180008dbc  push    rbp
0x180008dbe  sub     rsp, 20h
0x180008dc2  mov     rbp, rdx
0x180008dc5  mov     rax, [rcx]
0x180008dc8  mov     edx, [rax]
0x180008dca  mov     [rbp+0C8h], rcx
0x180008dd1  mov     [rbp+68h], edx
0x180008dd4  mov     eax, [rbp+68h]
0x180008dd7  cmp     eax, 0E06D7363h
0x180008ddc  jnz     short loc_180008DF2
0x180008dde  mov     rdx, [rbp+0C8h]
0x180008de5  mov     ecx, [rbp+68h]
0x180008de8  call    _XcptFilter_0
0x180008ded  mov     [rbp+70h], eax
0x180008df0  jmp     short loc_180008DF9
0x180008df2  mov     dword ptr [rbp+70h], 0
0x180008df9  mov     eax, [rbp+70h]
0x180008dfc  add     rsp, 20h
0x180008e00  pop     rbp
0x180008e01  retn
0x180008e03  push    rbp
0x180008e05  sub     rsp, 20h
0x180008e09  mov     rbp, rdx
0x180008e0c  mov     rax, [rcx]
0x180008e0f  mov     edx, [rax]
0x180008e11  mov     [rbp+0D0h], rcx
0x180008e18  mov     [rbp+78h], edx
0x180008e1b  mov     eax, [rbp+78h]
0x180008e1e  cmp     eax, 0E06D7363h
0x180008e23  jnz     short loc_180008E3C
0x180008e25  mov     rdx, [rbp+0D0h]
0x180008e2c  mov     ecx, [rbp+78h]
0x180008e2f  call    _XcptFilter_0
0x180008e34  mov     [rbp+80h], eax
0x180008e3a  jmp     short loc_180008E46
0x180008e3c  mov     dword ptr [rbp+80h], 0
0x180008e46  mov     eax, [rbp+80h]
0x180008e4c  add     rsp, 20h
0x180008e50  pop     rbp
0x180008e51  retn
0x180008e53  push    rbp
0x180008e55  sub     rsp, 20h
0x180008e59  mov     rbp, rdx
0x180008e5c  mov     rax, [rcx]
0x180008e5f  mov     edx, [rax]
0x180008e61  mov     [rbp+0D8h], rcx
0x180008e68  mov     [rbp+88h], edx
0x180008e6e  mov     eax, [rbp+88h]
0x180008e74  cmp     eax, 0E06D7363h
0x180008e79  jnz     short loc_180008E95
0x180008e7b  mov     rdx, [rbp+0D8h]
0x180008e82  mov     ecx, [rbp+88h]
0x180008e88  call    _XcptFilter_0
0x180008e8d  mov     [rbp+90h], eax
0x180008e93  jmp     short loc_180008E9F
0x180008e95  mov     dword ptr [rbp+90h], 0
0x180008e9f  mov     eax, [rbp+90h]
0x180008ea5  add     rsp, 20h
0x180008ea9  pop     rbp
0x180008eaa  retn
0x180008eac  push    rbp
0x180008eae  sub     rsp, 20h
0x180008eb2  mov     rbp, rdx
0x180008eb5  mov     rax, [rcx]
0x180008eb8  mov     edx, [rax]
0x180008eba  mov     [rbp+0E0h], rcx
0x180008ec1  mov     [rbp+98h], edx
0x180008ec7  mov     eax, [rbp+98h]
0x180008ecd  cmp     eax, 0E06D7363h
0x180008ed2  jnz     short loc_180008EEE
0x180008ed4  mov     rdx, [rbp+0E0h]
0x180008edb  mov     ecx, [rbp+98h]
0x180008ee1  call    _XcptFilter_0
0x180008ee6  mov     [rbp+0A0h], eax
0x180008eec  jmp     short loc_180008EF8
0x180008eee  mov     dword ptr [rbp+0A0h], 0
0x180008ef8  mov     eax, [rbp+0A0h]
0x180008efe  add     rsp, 20h
0x180008f02  pop     rbp
0x180008f03  retn
0x180008f05  push    rbp
0x180008f07  sub     rsp, 20h
0x180008f0b  mov     rbp, rdx
0x180008f0e  cmp     dword ptr [rbp+118h], 1
0x180008f15  ja      short loc_180008F21
0x180008f17  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
