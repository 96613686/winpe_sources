# __DllMainCRTStartup

- ea: `0x180001b64`
- end: `0x180001d70`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001b20`

## callees

- `0x1800018f0`
- `0x180001b64`
- `0x180001d9a`
- `0x180001f78`
- `0x18000d200`

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
  if ( (_DWORD)fdwReason || dword_1800181A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800181A4 = 1;
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
            if ( dword_1800181A4 )
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
0x180001b64  mov     [rsp+lpvReserved], r8
0x180001b69  mov     [rsp+arg_8], edx
0x180001b6d  mov     [rsp+arg_0], rcx
0x180001b72  push    rbx
0x180001b73  push    rsi
0x180001b74  push    rdi
0x180001b75  sub     rsp, 0F0h
0x180001b7c  mov     edi, edx
0x180001b7e  mov     rsi, rcx
0x180001b81  mov     ebx, 1
0x180001b86  cmp     edx, ebx
0x180001b88  ja      short loc_180001B90
0x180001b8a  mov     cs:__native_dllmain_reason, edx
0x180001b90  test    edx, edx
0x180001b92  jnz     short loc_180001BA7
0x180001b94  cmp     cs:dword_1800181A0, edx
0x180001b9a  jnz     short loc_180001BA7
0x180001b9c  xor     ebx, ebx
0x180001b9e  mov     [rsp+108h+var_E8], ebx
0x180001ba2  jmp     loc_180001D54
0x180001ba7  lea     eax, [rdx-1]
0x180001baa  cmp     eax, 1
0x180001bad  ja      loc_180001C34
0x180001bb3  mov     rax, cs:_pRawDllMain
0x180001bba  test    rax, rax
0x180001bbd  jz      short loc_180001BF5
0x180001bbf  cmp     edx, 1
0x180001bc2  jnz     short loc_180001BCA
0x180001bc4  mov     cs:dword_1800181A4, edx
0x180001bca  mov     r8, [rsp+108h+lpvReserved]
0x180001bd2  call    cs:__guard_dispatch_icall_fptr
0x180001bd8  mov     ebx, eax
0x180001bda  mov     [rsp+108h+var_E8], eax
0x180001bde  jmp     short loc_180001BF5
0x180001be0  xor     ebx, ebx
0x180001be2  mov     [rsp+108h+var_E8], ebx
0x180001be6  mov     edi, [rsp+108h+arg_8]
0x180001bed  mov     rsi, [rsp+108h+arg_0]
0x180001bf5  test    ebx, ebx
0x180001bf7  jz      loc_180001D54
0x180001bfd  mov     r8, [rsp+108h+lpvReserved]
0x180001c05  mov     edx, edi
0x180001c07  mov     rcx, rsi
0x180001c0a  call    _CRT_INIT
0x180001c0f  mov     ebx, eax
0x180001c11  mov     [rsp+108h+var_E8], eax
0x180001c15  jmp     short loc_180001C2C
0x180001c17  xor     ebx, ebx
0x180001c19  mov     [rsp+108h+var_E8], ebx
0x180001c1d  mov     edi, [rsp+108h+arg_8]
0x180001c24  mov     rsi, [rsp+108h+arg_0]
0x180001c2c  test    ebx, ebx
0x180001c2e  jz      loc_180001D54
0x180001c34  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001c3c  mov     edx, edi; fdwReason
0x180001c3e  mov     rcx, rsi; hinstDLL
0x180001c41  call    DllMain
0x180001c46  mov     ebx, eax
0x180001c48  mov     [rsp+108h+var_E8], eax
0x180001c4c  jmp     short loc_180001C63
0x180001c4e  xor     ebx, ebx
0x180001c50  mov     [rsp+108h+var_E8], ebx
0x180001c54  mov     edi, [rsp+108h+arg_8]
0x180001c5b  mov     rsi, [rsp+108h+arg_0]
0x180001c63  cmp     edi, 1
0x180001c66  jnz     short loc_180001CDF
0x180001c68  test    ebx, ebx
0x180001c6a  jnz     short loc_180001CDF
0x180001c6c  xor     r8d, r8d; lpvReserved
0x180001c6f  xor     edx, edx; fdwReason
0x180001c71  mov     rcx, rsi; hinstDLL
0x180001c74  call    DllMain
0x180001c79  jmp     short loc_180001C8E
0x180001c7b  mov     edi, [rsp+108h+arg_8]
0x180001c82  mov     rsi, [rsp+108h+arg_0]
0x180001c8a  mov     ebx, [rsp+108h+var_E8]
0x180001c8e  xor     r8d, r8d
0x180001c91  xor     edx, edx
0x180001c93  mov     rcx, rsi
0x180001c96  call    _CRT_INIT
0x180001c9b  jmp     short loc_180001CB0
0x180001c9d  mov     edi, [rsp+108h+arg_8]
0x180001ca4  mov     rsi, [rsp+108h+arg_0]
0x180001cac  mov     ebx, [rsp+108h+var_E8]
0x180001cb0  mov     rax, cs:_pRawDllMain
0x180001cb7  test    rax, rax
0x180001cba  jz      short loc_180001CDF
0x180001cbc  xor     r8d, r8d
0x180001cbf  xor     edx, edx
0x180001cc1  mov     rcx, rsi
0x180001cc4  call    cs:__guard_dispatch_icall_fptr
0x180001cca  jmp     short loc_180001CDF
0x180001ccc  mov     edi, [rsp+108h+arg_8]
0x180001cd3  mov     rsi, [rsp+108h+arg_0]
0x180001cdb  mov     ebx, [rsp+108h+var_E8]
0x180001cdf  test    edi, edi
0x180001ce1  jz      short loc_180001CE8
0x180001ce3  cmp     edi, 3
0x180001ce6  jnz     short loc_180001D54
0x180001ce8  mov     r8, [rsp+108h+lpvReserved]
0x180001cf0  mov     edx, edi
0x180001cf2  mov     rcx, rsi
0x180001cf5  call    _CRT_INIT
0x180001cfa  mov     ebx, eax
0x180001cfc  mov     [rsp+108h+var_E8], eax
0x180001d00  jmp     short loc_180001D17
0x180001d02  xor     ebx, ebx
0x180001d04  mov     [rsp+108h+var_E8], ebx
0x180001d08  mov     edi, [rsp+108h+arg_8]
0x180001d0f  mov     rsi, [rsp+108h+arg_0]
0x180001d17  mov     rax, cs:_pRawDllMain
0x180001d1e  test    rax, rax
0x180001d21  jz      short loc_180001D54
0x180001d23  cmp     cs:dword_1800181A4, 0
0x180001d2a  jz      short loc_180001D54
0x180001d2c  mov     r8, [rsp+108h+lpvReserved]
0x180001d34  mov     edx, edi
0x180001d36  mov     rcx, rsi
0x180001d39  call    cs:__guard_dispatch_icall_fptr
0x180001d3f  mov     ebx, eax
0x180001d41  mov     [rsp+108h+var_E8], eax
0x180001d45  jmp     short loc_180001D54
0x180001d47  xor     ebx, ebx
0x180001d49  mov     [rsp+108h+var_E8], ebx
0x180001d4d  mov     edi, [rsp+108h+arg_8]
0x180001d54  cmp     edi, 1
0x180001d57  ja      short loc_180001D63
0x180001d59  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001d63  mov     eax, ebx
0x180001d65  add     rsp, 0F0h
0x180001d6c  pop     rdi
0x180001d6d  pop     rsi
0x180001d6e  pop     rbx
0x180001d6f  retn
0x18000d2d0  push    rbp
0x18000d2d2  sub     rsp, 20h
0x18000d2d6  mov     rbp, rdx
0x18000d2d9  mov     rax, [rcx]
0x18000d2dc  mov     edx, [rax]
0x18000d2de  mov     [rbp+0A8h], rcx
0x18000d2e5  mov     [rbp+28h], edx
0x18000d2e8  mov     eax, [rbp+28h]
0x18000d2eb  cmp     eax, 0E06D7363h
0x18000d2f0  jnz     short loc_18000D306
0x18000d2f2  mov     rdx, [rbp+0A8h]
0x18000d2f9  mov     ecx, [rbp+28h]
0x18000d2fc  call    _XcptFilter_0
0x18000d301  mov     [rbp+30h], eax
0x18000d304  jmp     short loc_18000D30D
0x18000d306  mov     dword ptr [rbp+30h], 0
0x18000d30d  mov     eax, [rbp+30h]
0x18000d310  add     rsp, 20h
0x18000d314  pop     rbp
0x18000d315  retn
0x18000d317  push    rbp
0x18000d319  sub     rsp, 20h
0x18000d31d  mov     rbp, rdx
0x18000d320  mov     rax, [rcx]
0x18000d323  mov     edx, [rax]
0x18000d325  mov     [rbp+0B0h], rcx
0x18000d32c  mov     [rbp+38h], edx
0x18000d32f  mov     eax, [rbp+38h]
0x18000d332  cmp     eax, 0E06D7363h
0x18000d337  jnz     short loc_18000D34D
0x18000d339  mov     rdx, [rbp+0B0h]
0x18000d340  mov     ecx, [rbp+38h]
0x18000d343  call    _XcptFilter_0
0x18000d348  mov     [rbp+40h], eax
0x18000d34b  jmp     short loc_18000D354
0x18000d34d  mov     dword ptr [rbp+40h], 0
0x18000d354  mov     eax, [rbp+40h]
0x18000d357  add     rsp, 20h
0x18000d35b  pop     rbp
0x18000d35c  retn
0x18000d35e  push    rbp
0x18000d360  sub     rsp, 20h
0x18000d364  mov     rbp, rdx
0x18000d367  mov     rax, [rcx]
0x18000d36a  mov     edx, [rax]
0x18000d36c  mov     [rbp+0B8h], rcx
0x18000d373  mov     [rbp+48h], edx
0x18000d376  mov     eax, [rbp+48h]
0x18000d379  cmp     eax, 0E06D7363h
0x18000d37e  jnz     short loc_18000D394
0x18000d380  mov     rdx, [rbp+0B8h]
0x18000d387  mov     ecx, [rbp+48h]
0x18000d38a  call    _XcptFilter_0
0x18000d38f  mov     [rbp+50h], eax
0x18000d392  jmp     short loc_18000D39B
0x18000d394  mov     dword ptr [rbp+50h], 0
0x18000d39b  mov     eax, [rbp+50h]
0x18000d39e  add     rsp, 20h
0x18000d3a2  pop     rbp
0x18000d3a3  retn
0x18000d3a5  push    rbp
0x18000d3a7  sub     rsp, 20h
0x18000d3ab  mov     rbp, rdx
0x18000d3ae  mov     rax, [rcx]
0x18000d3b1  mov     edx, [rax]
0x18000d3b3  mov     [rbp+0C0h], rcx
0x18000d3ba  mov     [rbp+58h], edx
0x18000d3bd  mov     eax, [rbp+58h]
0x18000d3c0  cmp     eax, 0E06D7363h
0x18000d3c5  jnz     short loc_18000D3DB
0x18000d3c7  mov     rdx, [rbp+0C0h]
0x18000d3ce  mov     ecx, [rbp+58h]
0x18000d3d1  call    _XcptFilter_0
0x18000d3d6  mov     [rbp+60h], eax
0x18000d3d9  jmp     short loc_18000D3E2
0x18000d3db  mov     dword ptr [rbp+60h], 0
0x18000d3e2  mov     eax, [rbp+60h]
0x18000d3e5  add     rsp, 20h
0x18000d3e9  pop     rbp
0x18000d3ea  retn
0x18000d3ec  push    rbp
0x18000d3ee  sub     rsp, 20h
0x18000d3f2  mov     rbp, rdx
0x18000d3f5  mov     rax, [rcx]
0x18000d3f8  mov     edx, [rax]
0x18000d3fa  mov     [rbp+0C8h], rcx
0x18000d401  mov     [rbp+68h], edx
0x18000d404  mov     eax, [rbp+68h]
0x18000d407  cmp     eax, 0E06D7363h
0x18000d40c  jnz     short loc_18000D422
0x18000d40e  mov     rdx, [rbp+0C8h]
0x18000d415  mov     ecx, [rbp+68h]
0x18000d418  call    _XcptFilter_0
0x18000d41d  mov     [rbp+70h], eax
0x18000d420  jmp     short loc_18000D429
0x18000d422  mov     dword ptr [rbp+70h], 0
0x18000d429  mov     eax, [rbp+70h]
0x18000d42c  add     rsp, 20h
0x18000d430  pop     rbp
0x18000d431  retn
0x18000d433  push    rbp
0x18000d435  sub     rsp, 20h
0x18000d439  mov     rbp, rdx
0x18000d43c  mov     rax, [rcx]
0x18000d43f  mov     edx, [rax]
0x18000d441  mov     [rbp+0D0h], rcx
0x18000d448  mov     [rbp+78h], edx
0x18000d44b  mov     eax, [rbp+78h]
0x18000d44e  cmp     eax, 0E06D7363h
0x18000d453  jnz     short loc_18000D46C
0x18000d455  mov     rdx, [rbp+0D0h]
0x18000d45c  mov     ecx, [rbp+78h]
0x18000d45f  call    _XcptFilter_0
0x18000d464  mov     [rbp+80h], eax
0x18000d46a  jmp     short loc_18000D476
0x18000d46c  mov     dword ptr [rbp+80h], 0
0x18000d476  mov     eax, [rbp+80h]
0x18000d47c  add     rsp, 20h
0x18000d480  pop     rbp
0x18000d481  retn
0x18000d483  push    rbp
0x18000d485  sub     rsp, 20h
0x18000d489  mov     rbp, rdx
0x18000d48c  mov     rax, [rcx]
0x18000d48f  mov     edx, [rax]
0x18000d491  mov     [rbp+0D8h], rcx
0x18000d498  mov     [rbp+88h], edx
0x18000d49e  mov     eax, [rbp+88h]
0x18000d4a4  cmp     eax, 0E06D7363h
0x18000d4a9  jnz     short loc_18000D4C5
0x18000d4ab  mov     rdx, [rbp+0D8h]
0x18000d4b2  mov     ecx, [rbp+88h]
0x18000d4b8  call    _XcptFilter_0
0x18000d4bd  mov     [rbp+90h], eax
0x18000d4c3  jmp     short loc_18000D4CF
0x18000d4c5  mov     dword ptr [rbp+90h], 0
0x18000d4cf  mov     eax, [rbp+90h]
0x18000d4d5  add     rsp, 20h
0x18000d4d9  pop     rbp
0x18000d4da  retn
0x18000d4dc  push    rbp
0x18000d4de  sub     rsp, 20h
0x18000d4e2  mov     rbp, rdx
0x18000d4e5  mov     rax, [rcx]
0x18000d4e8  mov     edx, [rax]
0x18000d4ea  mov     [rbp+0E0h], rcx
0x18000d4f1  mov     [rbp+98h], edx
0x18000d4f7  mov     eax, [rbp+98h]
0x18000d4fd  cmp     eax, 0E06D7363h
0x18000d502  jnz     short loc_18000D51E
0x18000d504  mov     rdx, [rbp+0E0h]
0x18000d50b  mov     ecx, [rbp+98h]
0x18000d511  call    _XcptFilter_0
0x18000d516  mov     [rbp+0A0h], eax
0x18000d51c  jmp     short loc_18000D528
0x18000d51e  mov     dword ptr [rbp+0A0h], 0
0x18000d528  mov     eax, [rbp+0A0h]
0x18000d52e  add     rsp, 20h
0x18000d532  pop     rbp
0x18000d533  retn
0x18000d535  push    rbp
0x18000d537  sub     rsp, 20h
0x18000d53b  mov     rbp, rdx
0x18000d53e  cmp     dword ptr [rbp+118h], 1
0x18000d545  ja      short loc_18000D551
0x18000d547  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
