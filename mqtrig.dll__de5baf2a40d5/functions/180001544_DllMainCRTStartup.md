# __DllMainCRTStartup

- ea: `0x180001544`
- end: `0x180001750`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001500`

## callees

- `0x1800012d0`
- `0x180001544`
- `0x180001df7`
- `0x18000fcf0`
- `0x18001e3f0`

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
  if ( (_DWORD)fdwReason || dword_18002C5C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002C5C4 = 1;
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
            if ( dword_18002C5C4 )
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
0x180001544  mov     [rsp+lpvReserved], r8
0x180001549  mov     [rsp+arg_8], edx
0x18000154d  mov     [rsp+arg_0], rcx
0x180001552  push    rbx
0x180001553  push    rsi
0x180001554  push    rdi
0x180001555  sub     rsp, 0F0h
0x18000155c  mov     edi, edx
0x18000155e  mov     rsi, rcx
0x180001561  mov     ebx, 1
0x180001566  cmp     edx, ebx
0x180001568  ja      short loc_180001570
0x18000156a  mov     cs:__native_dllmain_reason, edx
0x180001570  test    edx, edx
0x180001572  jnz     short loc_180001587
0x180001574  cmp     cs:dword_18002C5C0, edx
0x18000157a  jnz     short loc_180001587
0x18000157c  xor     ebx, ebx
0x18000157e  mov     [rsp+108h+var_E8], ebx
0x180001582  jmp     loc_180001734
0x180001587  lea     eax, [rdx-1]
0x18000158a  cmp     eax, 1
0x18000158d  ja      loc_180001614
0x180001593  mov     rax, cs:_pRawDllMain
0x18000159a  test    rax, rax
0x18000159d  jz      short loc_1800015D5
0x18000159f  cmp     edx, 1
0x1800015a2  jnz     short loc_1800015AA
0x1800015a4  mov     cs:dword_18002C5C4, edx
0x1800015aa  mov     r8, [rsp+108h+lpvReserved]
0x1800015b2  call    cs:__guard_dispatch_icall_fptr
0x1800015b8  mov     ebx, eax
0x1800015ba  mov     [rsp+108h+var_E8], eax
0x1800015be  jmp     short loc_1800015D5
0x1800015c0  xor     ebx, ebx
0x1800015c2  mov     [rsp+108h+var_E8], ebx
0x1800015c6  mov     edi, [rsp+108h+arg_8]
0x1800015cd  mov     rsi, [rsp+108h+arg_0]
0x1800015d5  test    ebx, ebx
0x1800015d7  jz      loc_180001734
0x1800015dd  mov     r8, [rsp+108h+lpvReserved]
0x1800015e5  mov     edx, edi
0x1800015e7  mov     rcx, rsi
0x1800015ea  call    _CRT_INIT
0x1800015ef  mov     ebx, eax
0x1800015f1  mov     [rsp+108h+var_E8], eax
0x1800015f5  jmp     short loc_18000160C
0x1800015f7  xor     ebx, ebx
0x1800015f9  mov     [rsp+108h+var_E8], ebx
0x1800015fd  mov     edi, [rsp+108h+arg_8]
0x180001604  mov     rsi, [rsp+108h+arg_0]
0x18000160c  test    ebx, ebx
0x18000160e  jz      loc_180001734
0x180001614  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000161c  mov     edx, edi; fdwReason
0x18000161e  mov     rcx, rsi; hinstDLL
0x180001621  call    DllMain
0x180001626  mov     ebx, eax
0x180001628  mov     [rsp+108h+var_E8], eax
0x18000162c  jmp     short loc_180001643
0x18000162e  xor     ebx, ebx
0x180001630  mov     [rsp+108h+var_E8], ebx
0x180001634  mov     edi, [rsp+108h+arg_8]
0x18000163b  mov     rsi, [rsp+108h+arg_0]
0x180001643  cmp     edi, 1
0x180001646  jnz     short loc_1800016BF
0x180001648  test    ebx, ebx
0x18000164a  jnz     short loc_1800016BF
0x18000164c  xor     r8d, r8d; lpvReserved
0x18000164f  xor     edx, edx; fdwReason
0x180001651  mov     rcx, rsi; hinstDLL
0x180001654  call    DllMain
0x180001659  jmp     short loc_18000166E
0x18000165b  mov     edi, [rsp+108h+arg_8]
0x180001662  mov     rsi, [rsp+108h+arg_0]
0x18000166a  mov     ebx, [rsp+108h+var_E8]
0x18000166e  xor     r8d, r8d
0x180001671  xor     edx, edx
0x180001673  mov     rcx, rsi
0x180001676  call    _CRT_INIT
0x18000167b  jmp     short loc_180001690
0x18000167d  mov     edi, [rsp+108h+arg_8]
0x180001684  mov     rsi, [rsp+108h+arg_0]
0x18000168c  mov     ebx, [rsp+108h+var_E8]
0x180001690  mov     rax, cs:_pRawDllMain
0x180001697  test    rax, rax
0x18000169a  jz      short loc_1800016BF
0x18000169c  xor     r8d, r8d
0x18000169f  xor     edx, edx
0x1800016a1  mov     rcx, rsi
0x1800016a4  call    cs:__guard_dispatch_icall_fptr
0x1800016aa  jmp     short loc_1800016BF
0x1800016ac  mov     edi, [rsp+108h+arg_8]
0x1800016b3  mov     rsi, [rsp+108h+arg_0]
0x1800016bb  mov     ebx, [rsp+108h+var_E8]
0x1800016bf  test    edi, edi
0x1800016c1  jz      short loc_1800016C8
0x1800016c3  cmp     edi, 3
0x1800016c6  jnz     short loc_180001734
0x1800016c8  mov     r8, [rsp+108h+lpvReserved]
0x1800016d0  mov     edx, edi
0x1800016d2  mov     rcx, rsi
0x1800016d5  call    _CRT_INIT
0x1800016da  mov     ebx, eax
0x1800016dc  mov     [rsp+108h+var_E8], eax
0x1800016e0  jmp     short loc_1800016F7
0x1800016e2  xor     ebx, ebx
0x1800016e4  mov     [rsp+108h+var_E8], ebx
0x1800016e8  mov     edi, [rsp+108h+arg_8]
0x1800016ef  mov     rsi, [rsp+108h+arg_0]
0x1800016f7  mov     rax, cs:_pRawDllMain
0x1800016fe  test    rax, rax
0x180001701  jz      short loc_180001734
0x180001703  cmp     cs:dword_18002C5C4, 0
0x18000170a  jz      short loc_180001734
0x18000170c  mov     r8, [rsp+108h+lpvReserved]
0x180001714  mov     edx, edi
0x180001716  mov     rcx, rsi
0x180001719  call    cs:__guard_dispatch_icall_fptr
0x18000171f  mov     ebx, eax
0x180001721  mov     [rsp+108h+var_E8], eax
0x180001725  jmp     short loc_180001734
0x180001727  xor     ebx, ebx
0x180001729  mov     [rsp+108h+var_E8], ebx
0x18000172d  mov     edi, [rsp+108h+arg_8]
0x180001734  cmp     edi, 1
0x180001737  ja      short loc_180001743
0x180001739  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001743  mov     eax, ebx
0x180001745  add     rsp, 0F0h
0x18000174c  pop     rdi
0x18000174d  pop     rsi
0x18000174e  pop     rbx
0x18000174f  retn
0x18001e4a5  push    rbp
0x18001e4a7  sub     rsp, 20h
0x18001e4ab  mov     rbp, rdx
0x18001e4ae  mov     rax, [rcx]
0x18001e4b1  mov     edx, [rax]
0x18001e4b3  mov     [rbp+0A8h], rcx
0x18001e4ba  mov     [rbp+28h], edx
0x18001e4bd  mov     eax, [rbp+28h]
0x18001e4c0  cmp     eax, 0E06D7363h
0x18001e4c5  jnz     short loc_18001E4DB
0x18001e4c7  mov     rdx, [rbp+0A8h]
0x18001e4ce  mov     ecx, [rbp+28h]
0x18001e4d1  call    _XcptFilter_0
0x18001e4d6  mov     [rbp+30h], eax
0x18001e4d9  jmp     short loc_18001E4E2
0x18001e4db  mov     dword ptr [rbp+30h], 0
0x18001e4e2  mov     eax, [rbp+30h]
0x18001e4e5  add     rsp, 20h
0x18001e4e9  pop     rbp
0x18001e4ea  retn
0x18001e4ec  push    rbp
0x18001e4ee  sub     rsp, 20h
0x18001e4f2  mov     rbp, rdx
0x18001e4f5  mov     rax, [rcx]
0x18001e4f8  mov     edx, [rax]
0x18001e4fa  mov     [rbp+0B0h], rcx
0x18001e501  mov     [rbp+38h], edx
0x18001e504  mov     eax, [rbp+38h]
0x18001e507  cmp     eax, 0E06D7363h
0x18001e50c  jnz     short loc_18001E522
0x18001e50e  mov     rdx, [rbp+0B0h]
0x18001e515  mov     ecx, [rbp+38h]
0x18001e518  call    _XcptFilter_0
0x18001e51d  mov     [rbp+40h], eax
0x18001e520  jmp     short loc_18001E529
0x18001e522  mov     dword ptr [rbp+40h], 0
0x18001e529  mov     eax, [rbp+40h]
0x18001e52c  add     rsp, 20h
0x18001e530  pop     rbp
0x18001e531  retn
0x18001e533  push    rbp
0x18001e535  sub     rsp, 20h
0x18001e539  mov     rbp, rdx
0x18001e53c  mov     rax, [rcx]
0x18001e53f  mov     edx, [rax]
0x18001e541  mov     [rbp+0B8h], rcx
0x18001e548  mov     [rbp+48h], edx
0x18001e54b  mov     eax, [rbp+48h]
0x18001e54e  cmp     eax, 0E06D7363h
0x18001e553  jnz     short loc_18001E569
0x18001e555  mov     rdx, [rbp+0B8h]
0x18001e55c  mov     ecx, [rbp+48h]
0x18001e55f  call    _XcptFilter_0
0x18001e564  mov     [rbp+50h], eax
0x18001e567  jmp     short loc_18001E570
0x18001e569  mov     dword ptr [rbp+50h], 0
0x18001e570  mov     eax, [rbp+50h]
0x18001e573  add     rsp, 20h
0x18001e577  pop     rbp
0x18001e578  retn
0x18001e57a  push    rbp
0x18001e57c  sub     rsp, 20h
0x18001e580  mov     rbp, rdx
0x18001e583  mov     rax, [rcx]
0x18001e586  mov     edx, [rax]
0x18001e588  mov     [rbp+0C0h], rcx
0x18001e58f  mov     [rbp+58h], edx
0x18001e592  mov     eax, [rbp+58h]
0x18001e595  cmp     eax, 0E06D7363h
0x18001e59a  jnz     short loc_18001E5B0
0x18001e59c  mov     rdx, [rbp+0C0h]
0x18001e5a3  mov     ecx, [rbp+58h]
0x18001e5a6  call    _XcptFilter_0
0x18001e5ab  mov     [rbp+60h], eax
0x18001e5ae  jmp     short loc_18001E5B7
0x18001e5b0  mov     dword ptr [rbp+60h], 0
0x18001e5b7  mov     eax, [rbp+60h]
0x18001e5ba  add     rsp, 20h
0x18001e5be  pop     rbp
0x18001e5bf  retn
0x18001e5c1  push    rbp
0x18001e5c3  sub     rsp, 20h
0x18001e5c7  mov     rbp, rdx
0x18001e5ca  mov     rax, [rcx]
0x18001e5cd  mov     edx, [rax]
0x18001e5cf  mov     [rbp+0C8h], rcx
0x18001e5d6  mov     [rbp+68h], edx
0x18001e5d9  mov     eax, [rbp+68h]
0x18001e5dc  cmp     eax, 0E06D7363h
0x18001e5e1  jnz     short loc_18001E5F7
0x18001e5e3  mov     rdx, [rbp+0C8h]
0x18001e5ea  mov     ecx, [rbp+68h]
0x18001e5ed  call    _XcptFilter_0
0x18001e5f2  mov     [rbp+70h], eax
0x18001e5f5  jmp     short loc_18001E5FE
0x18001e5f7  mov     dword ptr [rbp+70h], 0
0x18001e5fe  mov     eax, [rbp+70h]
0x18001e601  add     rsp, 20h
0x18001e605  pop     rbp
0x18001e606  retn
0x18001e608  push    rbp
0x18001e60a  sub     rsp, 20h
0x18001e60e  mov     rbp, rdx
0x18001e611  mov     rax, [rcx]
0x18001e614  mov     edx, [rax]
0x18001e616  mov     [rbp+0D0h], rcx
0x18001e61d  mov     [rbp+78h], edx
0x18001e620  mov     eax, [rbp+78h]
0x18001e623  cmp     eax, 0E06D7363h
0x18001e628  jnz     short loc_18001E641
0x18001e62a  mov     rdx, [rbp+0D0h]
0x18001e631  mov     ecx, [rbp+78h]
0x18001e634  call    _XcptFilter_0
0x18001e639  mov     [rbp+80h], eax
0x18001e63f  jmp     short loc_18001E64B
0x18001e641  mov     dword ptr [rbp+80h], 0
0x18001e64b  mov     eax, [rbp+80h]
0x18001e651  add     rsp, 20h
0x18001e655  pop     rbp
0x18001e656  retn
0x18001e658  push    rbp
0x18001e65a  sub     rsp, 20h
0x18001e65e  mov     rbp, rdx
0x18001e661  mov     rax, [rcx]
0x18001e664  mov     edx, [rax]
0x18001e666  mov     [rbp+0D8h], rcx
0x18001e66d  mov     [rbp+88h], edx
0x18001e673  mov     eax, [rbp+88h]
0x18001e679  cmp     eax, 0E06D7363h
0x18001e67e  jnz     short loc_18001E69A
0x18001e680  mov     rdx, [rbp+0D8h]
0x18001e687  mov     ecx, [rbp+88h]
0x18001e68d  call    _XcptFilter_0
0x18001e692  mov     [rbp+90h], eax
0x18001e698  jmp     short loc_18001E6A4
0x18001e69a  mov     dword ptr [rbp+90h], 0
0x18001e6a4  mov     eax, [rbp+90h]
0x18001e6aa  add     rsp, 20h
0x18001e6ae  pop     rbp
0x18001e6af  retn
0x18001e6b1  push    rbp
0x18001e6b3  sub     rsp, 20h
0x18001e6b7  mov     rbp, rdx
0x18001e6ba  mov     rax, [rcx]
0x18001e6bd  mov     edx, [rax]
0x18001e6bf  mov     [rbp+0E0h], rcx
0x18001e6c6  mov     [rbp+98h], edx
0x18001e6cc  mov     eax, [rbp+98h]
0x18001e6d2  cmp     eax, 0E06D7363h
0x18001e6d7  jnz     short loc_18001E6F3
0x18001e6d9  mov     rdx, [rbp+0E0h]
0x18001e6e0  mov     ecx, [rbp+98h]
0x18001e6e6  call    _XcptFilter_0
0x18001e6eb  mov     [rbp+0A0h], eax
0x18001e6f1  jmp     short loc_18001E6FD
0x18001e6f3  mov     dword ptr [rbp+0A0h], 0
0x18001e6fd  mov     eax, [rbp+0A0h]
0x18001e703  add     rsp, 20h
0x18001e707  pop     rbp
0x18001e708  retn
0x18001e70a  push    rbp
0x18001e70c  sub     rsp, 20h
0x18001e710  mov     rbp, rdx
0x18001e713  cmp     dword ptr [rbp+118h], 1
0x18001e71a  ja      short loc_18001E726
0x18001e71c  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
