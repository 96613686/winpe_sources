# __DllMainCRTStartup

- ea: `0x1800014d4`
- end: `0x1800016e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001490`

## callees

- `0x180001180`
- `0x180001260`
- `0x1800014d4`
- `0x1800017a1`
- `0x18002e150`

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
  if ( (_DWORD)fdwReason || dword_180041E60 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180041E64 = 1;
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
            if ( dword_180041E64 )
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
0x1800014d4  mov     [rsp+lpvReserved], r8
0x1800014d9  mov     [rsp+arg_8], edx
0x1800014dd  mov     [rsp+arg_0], rcx
0x1800014e2  push    rbx
0x1800014e3  push    rsi
0x1800014e4  push    rdi
0x1800014e5  sub     rsp, 0F0h
0x1800014ec  mov     edi, edx
0x1800014ee  mov     rsi, rcx
0x1800014f1  mov     ebx, 1
0x1800014f6  cmp     edx, ebx
0x1800014f8  ja      short loc_180001500
0x1800014fa  mov     cs:__native_dllmain_reason, edx
0x180001500  test    edx, edx
0x180001502  jnz     short loc_180001517
0x180001504  cmp     cs:dword_180041E60, edx
0x18000150a  jnz     short loc_180001517
0x18000150c  xor     ebx, ebx
0x18000150e  mov     [rsp+108h+var_E8], ebx
0x180001512  jmp     loc_1800016C4
0x180001517  lea     eax, [rdx-1]
0x18000151a  cmp     eax, 1
0x18000151d  ja      loc_1800015A4
0x180001523  mov     rax, cs:_pRawDllMain
0x18000152a  test    rax, rax
0x18000152d  jz      short loc_180001565
0x18000152f  cmp     edx, 1
0x180001532  jnz     short loc_18000153A
0x180001534  mov     cs:dword_180041E64, edx
0x18000153a  mov     r8, [rsp+108h+lpvReserved]
0x180001542  call    cs:__guard_dispatch_icall_fptr
0x180001548  mov     ebx, eax
0x18000154a  mov     [rsp+108h+var_E8], eax
0x18000154e  jmp     short loc_180001565
0x180001550  xor     ebx, ebx
0x180001552  mov     [rsp+108h+var_E8], ebx
0x180001556  mov     edi, [rsp+108h+arg_8]
0x18000155d  mov     rsi, [rsp+108h+arg_0]
0x180001565  test    ebx, ebx
0x180001567  jz      loc_1800016C4
0x18000156d  mov     r8, [rsp+108h+lpvReserved]
0x180001575  mov     edx, edi
0x180001577  mov     rcx, rsi
0x18000157a  call    _CRT_INIT
0x18000157f  mov     ebx, eax
0x180001581  mov     [rsp+108h+var_E8], eax
0x180001585  jmp     short loc_18000159C
0x180001587  xor     ebx, ebx
0x180001589  mov     [rsp+108h+var_E8], ebx
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  mov     rsi, [rsp+108h+arg_0]
0x18000159c  test    ebx, ebx
0x18000159e  jz      loc_1800016C4
0x1800015a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800015ac  mov     edx, edi; fdwReason
0x1800015ae  mov     rcx, rsi; hinstDLL
0x1800015b1  call    DllMain
0x1800015b6  mov     ebx, eax
0x1800015b8  mov     [rsp+108h+var_E8], eax
0x1800015bc  jmp     short loc_1800015D3
0x1800015be  xor     ebx, ebx
0x1800015c0  mov     [rsp+108h+var_E8], ebx
0x1800015c4  mov     edi, [rsp+108h+arg_8]
0x1800015cb  mov     rsi, [rsp+108h+arg_0]
0x1800015d3  cmp     edi, 1
0x1800015d6  jnz     short loc_18000164F
0x1800015d8  test    ebx, ebx
0x1800015da  jnz     short loc_18000164F
0x1800015dc  xor     r8d, r8d; lpvReserved
0x1800015df  xor     edx, edx; fdwReason
0x1800015e1  mov     rcx, rsi; hinstDLL
0x1800015e4  call    DllMain
0x1800015e9  jmp     short loc_1800015FE
0x1800015eb  mov     edi, [rsp+108h+arg_8]
0x1800015f2  mov     rsi, [rsp+108h+arg_0]
0x1800015fa  mov     ebx, [rsp+108h+var_E8]
0x1800015fe  xor     r8d, r8d
0x180001601  xor     edx, edx
0x180001603  mov     rcx, rsi
0x180001606  call    _CRT_INIT
0x18000160b  jmp     short loc_180001620
0x18000160d  mov     edi, [rsp+108h+arg_8]
0x180001614  mov     rsi, [rsp+108h+arg_0]
0x18000161c  mov     ebx, [rsp+108h+var_E8]
0x180001620  mov     rax, cs:_pRawDllMain
0x180001627  test    rax, rax
0x18000162a  jz      short loc_18000164F
0x18000162c  xor     r8d, r8d
0x18000162f  xor     edx, edx
0x180001631  mov     rcx, rsi
0x180001634  call    cs:__guard_dispatch_icall_fptr
0x18000163a  jmp     short loc_18000164F
0x18000163c  mov     edi, [rsp+108h+arg_8]
0x180001643  mov     rsi, [rsp+108h+arg_0]
0x18000164b  mov     ebx, [rsp+108h+var_E8]
0x18000164f  test    edi, edi
0x180001651  jz      short loc_180001658
0x180001653  cmp     edi, 3
0x180001656  jnz     short loc_1800016C4
0x180001658  mov     r8, [rsp+108h+lpvReserved]
0x180001660  mov     edx, edi
0x180001662  mov     rcx, rsi
0x180001665  call    _CRT_INIT
0x18000166a  mov     ebx, eax
0x18000166c  mov     [rsp+108h+var_E8], eax
0x180001670  jmp     short loc_180001687
0x180001672  xor     ebx, ebx
0x180001674  mov     [rsp+108h+var_E8], ebx
0x180001678  mov     edi, [rsp+108h+arg_8]
0x18000167f  mov     rsi, [rsp+108h+arg_0]
0x180001687  mov     rax, cs:_pRawDllMain
0x18000168e  test    rax, rax
0x180001691  jz      short loc_1800016C4
0x180001693  cmp     cs:dword_180041E64, 0
0x18000169a  jz      short loc_1800016C4
0x18000169c  mov     r8, [rsp+108h+lpvReserved]
0x1800016a4  mov     edx, edi
0x1800016a6  mov     rcx, rsi
0x1800016a9  call    cs:__guard_dispatch_icall_fptr
0x1800016af  mov     ebx, eax
0x1800016b1  mov     [rsp+108h+var_E8], eax
0x1800016b5  jmp     short loc_1800016C4
0x1800016b7  xor     ebx, ebx
0x1800016b9  mov     [rsp+108h+var_E8], ebx
0x1800016bd  mov     edi, [rsp+108h+arg_8]
0x1800016c4  cmp     edi, 1
0x1800016c7  ja      short loc_1800016D3
0x1800016c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016d3  mov     eax, ebx
0x1800016d5  add     rsp, 0F0h
0x1800016dc  pop     rdi
0x1800016dd  pop     rsi
0x1800016de  pop     rbx
0x1800016df  retn
0x18002e223  push    rbp
0x18002e225  sub     rsp, 20h
0x18002e229  mov     rbp, rdx
0x18002e22c  mov     rax, [rcx]
0x18002e22f  mov     edx, [rax]
0x18002e231  mov     [rbp+0A8h], rcx
0x18002e238  mov     [rbp+28h], edx
0x18002e23b  mov     eax, [rbp+28h]
0x18002e23e  cmp     eax, 0E06D7363h
0x18002e243  jnz     short loc_18002E259
0x18002e245  mov     rdx, [rbp+0A8h]
0x18002e24c  mov     ecx, [rbp+28h]
0x18002e24f  call    _XcptFilter_0
0x18002e254  mov     [rbp+30h], eax
0x18002e257  jmp     short loc_18002E260
0x18002e259  mov     dword ptr [rbp+30h], 0
0x18002e260  mov     eax, [rbp+30h]
0x18002e263  add     rsp, 20h
0x18002e267  pop     rbp
0x18002e268  retn
0x18002e26a  push    rbp
0x18002e26c  sub     rsp, 20h
0x18002e270  mov     rbp, rdx
0x18002e273  mov     rax, [rcx]
0x18002e276  mov     edx, [rax]
0x18002e278  mov     [rbp+0B0h], rcx
0x18002e27f  mov     [rbp+38h], edx
0x18002e282  mov     eax, [rbp+38h]
0x18002e285  cmp     eax, 0E06D7363h
0x18002e28a  jnz     short loc_18002E2A0
0x18002e28c  mov     rdx, [rbp+0B0h]
0x18002e293  mov     ecx, [rbp+38h]
0x18002e296  call    _XcptFilter_0
0x18002e29b  mov     [rbp+40h], eax
0x18002e29e  jmp     short loc_18002E2A7
0x18002e2a0  mov     dword ptr [rbp+40h], 0
0x18002e2a7  mov     eax, [rbp+40h]
0x18002e2aa  add     rsp, 20h
0x18002e2ae  pop     rbp
0x18002e2af  retn
0x18002e2b1  push    rbp
0x18002e2b3  sub     rsp, 20h
0x18002e2b7  mov     rbp, rdx
0x18002e2ba  mov     rax, [rcx]
0x18002e2bd  mov     edx, [rax]
0x18002e2bf  mov     [rbp+0B8h], rcx
0x18002e2c6  mov     [rbp+48h], edx
0x18002e2c9  mov     eax, [rbp+48h]
0x18002e2cc  cmp     eax, 0E06D7363h
0x18002e2d1  jnz     short loc_18002E2E7
0x18002e2d3  mov     rdx, [rbp+0B8h]
0x18002e2da  mov     ecx, [rbp+48h]
0x18002e2dd  call    _XcptFilter_0
0x18002e2e2  mov     [rbp+50h], eax
0x18002e2e5  jmp     short loc_18002E2EE
0x18002e2e7  mov     dword ptr [rbp+50h], 0
0x18002e2ee  mov     eax, [rbp+50h]
0x18002e2f1  add     rsp, 20h
0x18002e2f5  pop     rbp
0x18002e2f6  retn
0x18002e2f8  push    rbp
0x18002e2fa  sub     rsp, 20h
0x18002e2fe  mov     rbp, rdx
0x18002e301  mov     rax, [rcx]
0x18002e304  mov     edx, [rax]
0x18002e306  mov     [rbp+0C0h], rcx
0x18002e30d  mov     [rbp+58h], edx
0x18002e310  mov     eax, [rbp+58h]
0x18002e313  cmp     eax, 0E06D7363h
0x18002e318  jnz     short loc_18002E32E
0x18002e31a  mov     rdx, [rbp+0C0h]
0x18002e321  mov     ecx, [rbp+58h]
0x18002e324  call    _XcptFilter_0
0x18002e329  mov     [rbp+60h], eax
0x18002e32c  jmp     short loc_18002E335
0x18002e32e  mov     dword ptr [rbp+60h], 0
0x18002e335  mov     eax, [rbp+60h]
0x18002e338  add     rsp, 20h
0x18002e33c  pop     rbp
0x18002e33d  retn
0x18002e33f  push    rbp
0x18002e341  sub     rsp, 20h
0x18002e345  mov     rbp, rdx
0x18002e348  mov     rax, [rcx]
0x18002e34b  mov     edx, [rax]
0x18002e34d  mov     [rbp+0C8h], rcx
0x18002e354  mov     [rbp+68h], edx
0x18002e357  mov     eax, [rbp+68h]
0x18002e35a  cmp     eax, 0E06D7363h
0x18002e35f  jnz     short loc_18002E375
0x18002e361  mov     rdx, [rbp+0C8h]
0x18002e368  mov     ecx, [rbp+68h]
0x18002e36b  call    _XcptFilter_0
0x18002e370  mov     [rbp+70h], eax
0x18002e373  jmp     short loc_18002E37C
0x18002e375  mov     dword ptr [rbp+70h], 0
0x18002e37c  mov     eax, [rbp+70h]
0x18002e37f  add     rsp, 20h
0x18002e383  pop     rbp
0x18002e384  retn
0x18002e386  push    rbp
0x18002e388  sub     rsp, 20h
0x18002e38c  mov     rbp, rdx
0x18002e38f  mov     rax, [rcx]
0x18002e392  mov     edx, [rax]
0x18002e394  mov     [rbp+0D0h], rcx
0x18002e39b  mov     [rbp+78h], edx
0x18002e39e  mov     eax, [rbp+78h]
0x18002e3a1  cmp     eax, 0E06D7363h
0x18002e3a6  jnz     short loc_18002E3BF
0x18002e3a8  mov     rdx, [rbp+0D0h]
0x18002e3af  mov     ecx, [rbp+78h]
0x18002e3b2  call    _XcptFilter_0
0x18002e3b7  mov     [rbp+80h], eax
0x18002e3bd  jmp     short loc_18002E3C9
0x18002e3bf  mov     dword ptr [rbp+80h], 0
0x18002e3c9  mov     eax, [rbp+80h]
0x18002e3cf  add     rsp, 20h
0x18002e3d3  pop     rbp
0x18002e3d4  retn
0x18002e3d6  push    rbp
0x18002e3d8  sub     rsp, 20h
0x18002e3dc  mov     rbp, rdx
0x18002e3df  mov     rax, [rcx]
0x18002e3e2  mov     edx, [rax]
0x18002e3e4  mov     [rbp+0D8h], rcx
0x18002e3eb  mov     [rbp+88h], edx
0x18002e3f1  mov     eax, [rbp+88h]
0x18002e3f7  cmp     eax, 0E06D7363h
0x18002e3fc  jnz     short loc_18002E418
0x18002e3fe  mov     rdx, [rbp+0D8h]
0x18002e405  mov     ecx, [rbp+88h]
0x18002e40b  call    _XcptFilter_0
0x18002e410  mov     [rbp+90h], eax
0x18002e416  jmp     short loc_18002E422
0x18002e418  mov     dword ptr [rbp+90h], 0
0x18002e422  mov     eax, [rbp+90h]
0x18002e428  add     rsp, 20h
0x18002e42c  pop     rbp
0x18002e42d  retn
0x18002e42f  push    rbp
0x18002e431  sub     rsp, 20h
0x18002e435  mov     rbp, rdx
0x18002e438  mov     rax, [rcx]
0x18002e43b  mov     edx, [rax]
0x18002e43d  mov     [rbp+0E0h], rcx
0x18002e444  mov     [rbp+98h], edx
0x18002e44a  mov     eax, [rbp+98h]
0x18002e450  cmp     eax, 0E06D7363h
0x18002e455  jnz     short loc_18002E471
0x18002e457  mov     rdx, [rbp+0E0h]
0x18002e45e  mov     ecx, [rbp+98h]
0x18002e464  call    _XcptFilter_0
0x18002e469  mov     [rbp+0A0h], eax
0x18002e46f  jmp     short loc_18002E47B
0x18002e471  mov     dword ptr [rbp+0A0h], 0
0x18002e47b  mov     eax, [rbp+0A0h]
0x18002e481  add     rsp, 20h
0x18002e485  pop     rbp
0x18002e486  retn
0x18002e488  push    rbp
0x18002e48a  sub     rsp, 20h
0x18002e48e  mov     rbp, rdx
0x18002e491  cmp     dword ptr [rbp+118h], 1
0x18002e498  ja      short loc_18002E4A4
0x18002e49a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
