# __DllMainCRTStartup

- ea: `0x18001ce44`
- end: `0x18001d050`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001ce00`

## callees

- `0x1800198c4`
- `0x18001cbd0`
- `0x18001ce44`
- `0x18001d066`
- `0x18003d080`

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
  if ( (_DWORD)fdwReason || dword_1800430A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800430A4 = 1;
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
            if ( dword_1800430A4 )
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
0x18001ce44  mov     [rsp+lpvReserved], r8
0x18001ce49  mov     [rsp+arg_8], edx
0x18001ce4d  mov     [rsp+arg_0], rcx
0x18001ce52  push    rbx
0x18001ce53  push    rsi
0x18001ce54  push    rdi
0x18001ce55  sub     rsp, 0F0h
0x18001ce5c  mov     edi, edx
0x18001ce5e  mov     rsi, rcx
0x18001ce61  mov     ebx, 1
0x18001ce66  cmp     edx, ebx
0x18001ce68  ja      short loc_18001CE70
0x18001ce6a  mov     cs:__native_dllmain_reason, edx
0x18001ce70  test    edx, edx
0x18001ce72  jnz     short loc_18001CE87
0x18001ce74  cmp     cs:dword_1800430A0, edx
0x18001ce7a  jnz     short loc_18001CE87
0x18001ce7c  xor     ebx, ebx
0x18001ce7e  mov     [rsp+108h+var_E8], ebx
0x18001ce82  jmp     loc_18001D034
0x18001ce87  lea     eax, [rdx-1]
0x18001ce8a  cmp     eax, 1
0x18001ce8d  ja      loc_18001CF14
0x18001ce93  mov     rax, cs:_pRawDllMain
0x18001ce9a  test    rax, rax
0x18001ce9d  jz      short loc_18001CED5
0x18001ce9f  cmp     edx, 1
0x18001cea2  jnz     short loc_18001CEAA
0x18001cea4  mov     cs:dword_1800430A4, edx
0x18001ceaa  mov     r8, [rsp+108h+lpvReserved]
0x18001ceb2  call    cs:__guard_dispatch_icall_fptr
0x18001ceb8  mov     ebx, eax
0x18001ceba  mov     [rsp+108h+var_E8], eax
0x18001cebe  jmp     short loc_18001CED5
0x18001cec0  xor     ebx, ebx
0x18001cec2  mov     [rsp+108h+var_E8], ebx
0x18001cec6  mov     edi, [rsp+108h+arg_8]
0x18001cecd  mov     rsi, [rsp+108h+arg_0]
0x18001ced5  test    ebx, ebx
0x18001ced7  jz      loc_18001D034
0x18001cedd  mov     r8, [rsp+108h+lpvReserved]
0x18001cee5  mov     edx, edi
0x18001cee7  mov     rcx, rsi
0x18001ceea  call    _CRT_INIT
0x18001ceef  mov     ebx, eax
0x18001cef1  mov     [rsp+108h+var_E8], eax
0x18001cef5  jmp     short loc_18001CF0C
0x18001cef7  xor     ebx, ebx
0x18001cef9  mov     [rsp+108h+var_E8], ebx
0x18001cefd  mov     edi, [rsp+108h+arg_8]
0x18001cf04  mov     rsi, [rsp+108h+arg_0]
0x18001cf0c  test    ebx, ebx
0x18001cf0e  jz      loc_18001D034
0x18001cf14  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18001cf1c  mov     edx, edi; fdwReason
0x18001cf1e  mov     rcx, rsi; hinstDLL
0x18001cf21  call    DllMain
0x18001cf26  mov     ebx, eax
0x18001cf28  mov     [rsp+108h+var_E8], eax
0x18001cf2c  jmp     short loc_18001CF43
0x18001cf2e  xor     ebx, ebx
0x18001cf30  mov     [rsp+108h+var_E8], ebx
0x18001cf34  mov     edi, [rsp+108h+arg_8]
0x18001cf3b  mov     rsi, [rsp+108h+arg_0]
0x18001cf43  cmp     edi, 1
0x18001cf46  jnz     short loc_18001CFBF
0x18001cf48  test    ebx, ebx
0x18001cf4a  jnz     short loc_18001CFBF
0x18001cf4c  xor     r8d, r8d; lpvReserved
0x18001cf4f  xor     edx, edx; fdwReason
0x18001cf51  mov     rcx, rsi; hinstDLL
0x18001cf54  call    DllMain
0x18001cf59  jmp     short loc_18001CF6E
0x18001cf5b  mov     edi, [rsp+108h+arg_8]
0x18001cf62  mov     rsi, [rsp+108h+arg_0]
0x18001cf6a  mov     ebx, [rsp+108h+var_E8]
0x18001cf6e  xor     r8d, r8d
0x18001cf71  xor     edx, edx
0x18001cf73  mov     rcx, rsi
0x18001cf76  call    _CRT_INIT
0x18001cf7b  jmp     short loc_18001CF90
0x18001cf7d  mov     edi, [rsp+108h+arg_8]
0x18001cf84  mov     rsi, [rsp+108h+arg_0]
0x18001cf8c  mov     ebx, [rsp+108h+var_E8]
0x18001cf90  mov     rax, cs:_pRawDllMain
0x18001cf97  test    rax, rax
0x18001cf9a  jz      short loc_18001CFBF
0x18001cf9c  xor     r8d, r8d
0x18001cf9f  xor     edx, edx
0x18001cfa1  mov     rcx, rsi
0x18001cfa4  call    cs:__guard_dispatch_icall_fptr
0x18001cfaa  jmp     short loc_18001CFBF
0x18001cfac  mov     edi, [rsp+108h+arg_8]
0x18001cfb3  mov     rsi, [rsp+108h+arg_0]
0x18001cfbb  mov     ebx, [rsp+108h+var_E8]
0x18001cfbf  test    edi, edi
0x18001cfc1  jz      short loc_18001CFC8
0x18001cfc3  cmp     edi, 3
0x18001cfc6  jnz     short loc_18001D034
0x18001cfc8  mov     r8, [rsp+108h+lpvReserved]
0x18001cfd0  mov     edx, edi
0x18001cfd2  mov     rcx, rsi
0x18001cfd5  call    _CRT_INIT
0x18001cfda  mov     ebx, eax
0x18001cfdc  mov     [rsp+108h+var_E8], eax
0x18001cfe0  jmp     short loc_18001CFF7
0x18001cfe2  xor     ebx, ebx
0x18001cfe4  mov     [rsp+108h+var_E8], ebx
0x18001cfe8  mov     edi, [rsp+108h+arg_8]
0x18001cfef  mov     rsi, [rsp+108h+arg_0]
0x18001cff7  mov     rax, cs:_pRawDllMain
0x18001cffe  test    rax, rax
0x18001d001  jz      short loc_18001D034
0x18001d003  cmp     cs:dword_1800430A4, 0
0x18001d00a  jz      short loc_18001D034
0x18001d00c  mov     r8, [rsp+108h+lpvReserved]
0x18001d014  mov     edx, edi
0x18001d016  mov     rcx, rsi
0x18001d019  call    cs:__guard_dispatch_icall_fptr
0x18001d01f  mov     ebx, eax
0x18001d021  mov     [rsp+108h+var_E8], eax
0x18001d025  jmp     short loc_18001D034
0x18001d027  xor     ebx, ebx
0x18001d029  mov     [rsp+108h+var_E8], ebx
0x18001d02d  mov     edi, [rsp+108h+arg_8]
0x18001d034  cmp     edi, 1
0x18001d037  ja      short loc_18001D043
0x18001d039  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18001d043  mov     eax, ebx
0x18001d045  add     rsp, 0F0h
0x18001d04c  pop     rdi
0x18001d04d  pop     rsi
0x18001d04e  pop     rbx
0x18001d04f  retn
0x18003d181  push    rbp
0x18003d183  sub     rsp, 20h
0x18003d187  mov     rbp, rdx
0x18003d18a  mov     rax, [rcx]
0x18003d18d  mov     edx, [rax]
0x18003d18f  mov     [rbp+0A8h], rcx
0x18003d196  mov     [rbp+28h], edx
0x18003d199  mov     eax, [rbp+28h]
0x18003d19c  cmp     eax, 0E06D7363h
0x18003d1a1  jnz     short loc_18003D1B7
0x18003d1a3  mov     rdx, [rbp+0A8h]
0x18003d1aa  mov     ecx, [rbp+28h]
0x18003d1ad  call    _XcptFilter_0
0x18003d1b2  mov     [rbp+30h], eax
0x18003d1b5  jmp     short loc_18003D1BE
0x18003d1b7  mov     dword ptr [rbp+30h], 0
0x18003d1be  mov     eax, [rbp+30h]
0x18003d1c1  add     rsp, 20h
0x18003d1c5  pop     rbp
0x18003d1c6  retn
0x18003d1c8  push    rbp
0x18003d1ca  sub     rsp, 20h
0x18003d1ce  mov     rbp, rdx
0x18003d1d1  mov     rax, [rcx]
0x18003d1d4  mov     edx, [rax]
0x18003d1d6  mov     [rbp+0B0h], rcx
0x18003d1dd  mov     [rbp+38h], edx
0x18003d1e0  mov     eax, [rbp+38h]
0x18003d1e3  cmp     eax, 0E06D7363h
0x18003d1e8  jnz     short loc_18003D1FE
0x18003d1ea  mov     rdx, [rbp+0B0h]
0x18003d1f1  mov     ecx, [rbp+38h]
0x18003d1f4  call    _XcptFilter_0
0x18003d1f9  mov     [rbp+40h], eax
0x18003d1fc  jmp     short loc_18003D205
0x18003d1fe  mov     dword ptr [rbp+40h], 0
0x18003d205  mov     eax, [rbp+40h]
0x18003d208  add     rsp, 20h
0x18003d20c  pop     rbp
0x18003d20d  retn
0x18003d20f  push    rbp
0x18003d211  sub     rsp, 20h
0x18003d215  mov     rbp, rdx
0x18003d218  mov     rax, [rcx]
0x18003d21b  mov     edx, [rax]
0x18003d21d  mov     [rbp+0B8h], rcx
0x18003d224  mov     [rbp+48h], edx
0x18003d227  mov     eax, [rbp+48h]
0x18003d22a  cmp     eax, 0E06D7363h
0x18003d22f  jnz     short loc_18003D245
0x18003d231  mov     rdx, [rbp+0B8h]
0x18003d238  mov     ecx, [rbp+48h]
0x18003d23b  call    _XcptFilter_0
0x18003d240  mov     [rbp+50h], eax
0x18003d243  jmp     short loc_18003D24C
0x18003d245  mov     dword ptr [rbp+50h], 0
0x18003d24c  mov     eax, [rbp+50h]
0x18003d24f  add     rsp, 20h
0x18003d253  pop     rbp
0x18003d254  retn
0x18003d256  push    rbp
0x18003d258  sub     rsp, 20h
0x18003d25c  mov     rbp, rdx
0x18003d25f  mov     rax, [rcx]
0x18003d262  mov     edx, [rax]
0x18003d264  mov     [rbp+0C0h], rcx
0x18003d26b  mov     [rbp+58h], edx
0x18003d26e  mov     eax, [rbp+58h]
0x18003d271  cmp     eax, 0E06D7363h
0x18003d276  jnz     short loc_18003D28C
0x18003d278  mov     rdx, [rbp+0C0h]
0x18003d27f  mov     ecx, [rbp+58h]
0x18003d282  call    _XcptFilter_0
0x18003d287  mov     [rbp+60h], eax
0x18003d28a  jmp     short loc_18003D293
0x18003d28c  mov     dword ptr [rbp+60h], 0
0x18003d293  mov     eax, [rbp+60h]
0x18003d296  add     rsp, 20h
0x18003d29a  pop     rbp
0x18003d29b  retn
0x18003d29d  push    rbp
0x18003d29f  sub     rsp, 20h
0x18003d2a3  mov     rbp, rdx
0x18003d2a6  mov     rax, [rcx]
0x18003d2a9  mov     edx, [rax]
0x18003d2ab  mov     [rbp+0C8h], rcx
0x18003d2b2  mov     [rbp+68h], edx
0x18003d2b5  mov     eax, [rbp+68h]
0x18003d2b8  cmp     eax, 0E06D7363h
0x18003d2bd  jnz     short loc_18003D2D3
0x18003d2bf  mov     rdx, [rbp+0C8h]
0x18003d2c6  mov     ecx, [rbp+68h]
0x18003d2c9  call    _XcptFilter_0
0x18003d2ce  mov     [rbp+70h], eax
0x18003d2d1  jmp     short loc_18003D2DA
0x18003d2d3  mov     dword ptr [rbp+70h], 0
0x18003d2da  mov     eax, [rbp+70h]
0x18003d2dd  add     rsp, 20h
0x18003d2e1  pop     rbp
0x18003d2e2  retn
0x18003d2e4  push    rbp
0x18003d2e6  sub     rsp, 20h
0x18003d2ea  mov     rbp, rdx
0x18003d2ed  mov     rax, [rcx]
0x18003d2f0  mov     edx, [rax]
0x18003d2f2  mov     [rbp+0D0h], rcx
0x18003d2f9  mov     [rbp+78h], edx
0x18003d2fc  mov     eax, [rbp+78h]
0x18003d2ff  cmp     eax, 0E06D7363h
0x18003d304  jnz     short loc_18003D31D
0x18003d306  mov     rdx, [rbp+0D0h]
0x18003d30d  mov     ecx, [rbp+78h]
0x18003d310  call    _XcptFilter_0
0x18003d315  mov     [rbp+80h], eax
0x18003d31b  jmp     short loc_18003D327
0x18003d31d  mov     dword ptr [rbp+80h], 0
0x18003d327  mov     eax, [rbp+80h]
0x18003d32d  add     rsp, 20h
0x18003d331  pop     rbp
0x18003d332  retn
0x18003d334  push    rbp
0x18003d336  sub     rsp, 20h
0x18003d33a  mov     rbp, rdx
0x18003d33d  mov     rax, [rcx]
0x18003d340  mov     edx, [rax]
0x18003d342  mov     [rbp+0D8h], rcx
0x18003d349  mov     [rbp+88h], edx
0x18003d34f  mov     eax, [rbp+88h]
0x18003d355  cmp     eax, 0E06D7363h
0x18003d35a  jnz     short loc_18003D376
0x18003d35c  mov     rdx, [rbp+0D8h]
0x18003d363  mov     ecx, [rbp+88h]
0x18003d369  call    _XcptFilter_0
0x18003d36e  mov     [rbp+90h], eax
0x18003d374  jmp     short loc_18003D380
0x18003d376  mov     dword ptr [rbp+90h], 0
0x18003d380  mov     eax, [rbp+90h]
0x18003d386  add     rsp, 20h
0x18003d38a  pop     rbp
0x18003d38b  retn
0x18003d38d  push    rbp
0x18003d38f  sub     rsp, 20h
0x18003d393  mov     rbp, rdx
0x18003d396  mov     rax, [rcx]
0x18003d399  mov     edx, [rax]
0x18003d39b  mov     [rbp+0E0h], rcx
0x18003d3a2  mov     [rbp+98h], edx
0x18003d3a8  mov     eax, [rbp+98h]
0x18003d3ae  cmp     eax, 0E06D7363h
0x18003d3b3  jnz     short loc_18003D3CF
0x18003d3b5  mov     rdx, [rbp+0E0h]
0x18003d3bc  mov     ecx, [rbp+98h]
0x18003d3c2  call    _XcptFilter_0
0x18003d3c7  mov     [rbp+0A0h], eax
0x18003d3cd  jmp     short loc_18003D3D9
0x18003d3cf  mov     dword ptr [rbp+0A0h], 0
0x18003d3d9  mov     eax, [rbp+0A0h]
0x18003d3df  add     rsp, 20h
0x18003d3e3  pop     rbp
0x18003d3e4  retn
0x18003d3e6  push    rbp
0x18003d3e8  sub     rsp, 20h
0x18003d3ec  mov     rbp, rdx
0x18003d3ef  cmp     dword ptr [rbp+118h], 1
0x18003d3f6  ja      short loc_18003D402
0x18003d3f8  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
