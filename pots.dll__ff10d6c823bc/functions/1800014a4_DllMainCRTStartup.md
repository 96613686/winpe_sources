# __DllMainCRTStartup

- ea: `0x1800014a4`
- end: `0x1800016b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001460`

## callees

- `0x180001230`
- `0x1800014a4`
- `0x1800019d4`
- `0x180001be8`
- `0x180004970`

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
  if ( (_DWORD)fdwReason || dword_1800092A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800092A4 = 1;
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
            if ( dword_1800092A4 )
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
0x1800014a4  mov     [rsp+lpvReserved], r8
0x1800014a9  mov     [rsp+arg_8], edx
0x1800014ad  mov     [rsp+arg_0], rcx
0x1800014b2  push    rbx
0x1800014b3  push    rsi
0x1800014b4  push    rdi
0x1800014b5  sub     rsp, 0F0h
0x1800014bc  mov     edi, edx
0x1800014be  mov     rsi, rcx
0x1800014c1  mov     ebx, 1
0x1800014c6  cmp     edx, ebx
0x1800014c8  ja      short loc_1800014D0
0x1800014ca  mov     cs:__native_dllmain_reason, edx
0x1800014d0  test    edx, edx
0x1800014d2  jnz     short loc_1800014E7
0x1800014d4  cmp     cs:dword_1800092A0, edx
0x1800014da  jnz     short loc_1800014E7
0x1800014dc  xor     ebx, ebx
0x1800014de  mov     [rsp+108h+var_E8], ebx
0x1800014e2  jmp     loc_180001694
0x1800014e7  lea     eax, [rdx-1]
0x1800014ea  cmp     eax, 1
0x1800014ed  ja      loc_180001574
0x1800014f3  mov     rax, cs:_pRawDllMain
0x1800014fa  test    rax, rax
0x1800014fd  jz      short loc_180001535
0x1800014ff  cmp     edx, 1
0x180001502  jnz     short loc_18000150A
0x180001504  mov     cs:dword_1800092A4, edx
0x18000150a  mov     r8, [rsp+108h+lpvReserved]
0x180001512  call    cs:__guard_dispatch_icall_fptr
0x180001518  mov     ebx, eax
0x18000151a  mov     [rsp+108h+var_E8], eax
0x18000151e  jmp     short loc_180001535
0x180001520  xor     ebx, ebx
0x180001522  mov     [rsp+108h+var_E8], ebx
0x180001526  mov     edi, [rsp+108h+arg_8]
0x18000152d  mov     rsi, [rsp+108h+arg_0]
0x180001535  test    ebx, ebx
0x180001537  jz      loc_180001694
0x18000153d  mov     r8, [rsp+108h+lpvReserved]
0x180001545  mov     edx, edi
0x180001547  mov     rcx, rsi
0x18000154a  call    _CRT_INIT
0x18000154f  mov     ebx, eax
0x180001551  mov     [rsp+108h+var_E8], eax
0x180001555  jmp     short loc_18000156C
0x180001557  xor     ebx, ebx
0x180001559  mov     [rsp+108h+var_E8], ebx
0x18000155d  mov     edi, [rsp+108h+arg_8]
0x180001564  mov     rsi, [rsp+108h+arg_0]
0x18000156c  test    ebx, ebx
0x18000156e  jz      loc_180001694
0x180001574  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000157c  mov     edx, edi; fdwReason
0x18000157e  mov     rcx, rsi; hinstDLL
0x180001581  call    DllMain
0x180001586  mov     ebx, eax
0x180001588  mov     [rsp+108h+var_E8], eax
0x18000158c  jmp     short loc_1800015A3
0x18000158e  xor     ebx, ebx
0x180001590  mov     [rsp+108h+var_E8], ebx
0x180001594  mov     edi, [rsp+108h+arg_8]
0x18000159b  mov     rsi, [rsp+108h+arg_0]
0x1800015a3  cmp     edi, 1
0x1800015a6  jnz     short loc_18000161F
0x1800015a8  test    ebx, ebx
0x1800015aa  jnz     short loc_18000161F
0x1800015ac  xor     r8d, r8d; lpvReserved
0x1800015af  xor     edx, edx; fdwReason
0x1800015b1  mov     rcx, rsi; hinstDLL
0x1800015b4  call    DllMain
0x1800015b9  jmp     short loc_1800015CE
0x1800015bb  mov     edi, [rsp+108h+arg_8]
0x1800015c2  mov     rsi, [rsp+108h+arg_0]
0x1800015ca  mov     ebx, [rsp+108h+var_E8]
0x1800015ce  xor     r8d, r8d
0x1800015d1  xor     edx, edx
0x1800015d3  mov     rcx, rsi
0x1800015d6  call    _CRT_INIT
0x1800015db  jmp     short loc_1800015F0
0x1800015dd  mov     edi, [rsp+108h+arg_8]
0x1800015e4  mov     rsi, [rsp+108h+arg_0]
0x1800015ec  mov     ebx, [rsp+108h+var_E8]
0x1800015f0  mov     rax, cs:_pRawDllMain
0x1800015f7  test    rax, rax
0x1800015fa  jz      short loc_18000161F
0x1800015fc  xor     r8d, r8d
0x1800015ff  xor     edx, edx
0x180001601  mov     rcx, rsi
0x180001604  call    cs:__guard_dispatch_icall_fptr
0x18000160a  jmp     short loc_18000161F
0x18000160c  mov     edi, [rsp+108h+arg_8]
0x180001613  mov     rsi, [rsp+108h+arg_0]
0x18000161b  mov     ebx, [rsp+108h+var_E8]
0x18000161f  test    edi, edi
0x180001621  jz      short loc_180001628
0x180001623  cmp     edi, 3
0x180001626  jnz     short loc_180001694
0x180001628  mov     r8, [rsp+108h+lpvReserved]
0x180001630  mov     edx, edi
0x180001632  mov     rcx, rsi
0x180001635  call    _CRT_INIT
0x18000163a  mov     ebx, eax
0x18000163c  mov     [rsp+108h+var_E8], eax
0x180001640  jmp     short loc_180001657
0x180001642  xor     ebx, ebx
0x180001644  mov     [rsp+108h+var_E8], ebx
0x180001648  mov     edi, [rsp+108h+arg_8]
0x18000164f  mov     rsi, [rsp+108h+arg_0]
0x180001657  mov     rax, cs:_pRawDllMain
0x18000165e  test    rax, rax
0x180001661  jz      short loc_180001694
0x180001663  cmp     cs:dword_1800092A4, 0
0x18000166a  jz      short loc_180001694
0x18000166c  mov     r8, [rsp+108h+lpvReserved]
0x180001674  mov     edx, edi
0x180001676  mov     rcx, rsi
0x180001679  call    cs:__guard_dispatch_icall_fptr
0x18000167f  mov     ebx, eax
0x180001681  mov     [rsp+108h+var_E8], eax
0x180001685  jmp     short loc_180001694
0x180001687  xor     ebx, ebx
0x180001689  mov     [rsp+108h+var_E8], ebx
0x18000168d  mov     edi, [rsp+108h+arg_8]
0x180001694  cmp     edi, 1
0x180001697  ja      short loc_1800016A3
0x180001699  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016a3  mov     eax, ebx
0x1800016a5  add     rsp, 0F0h
0x1800016ac  pop     rdi
0x1800016ad  pop     rsi
0x1800016ae  pop     rbx
0x1800016af  retn
0x1800049e0  push    rbp
0x1800049e2  sub     rsp, 20h
0x1800049e6  mov     rbp, rdx
0x1800049e9  mov     rax, [rcx]
0x1800049ec  mov     edx, [rax]
0x1800049ee  mov     [rbp+0A8h], rcx
0x1800049f5  mov     [rbp+28h], edx
0x1800049f8  mov     eax, [rbp+28h]
0x1800049fb  cmp     eax, 0E06D7363h
0x180004a00  jnz     short loc_180004A16
0x180004a02  mov     rdx, [rbp+0A8h]
0x180004a09  mov     ecx, [rbp+28h]
0x180004a0c  call    _XcptFilter_0
0x180004a11  mov     [rbp+30h], eax
0x180004a14  jmp     short loc_180004A1D
0x180004a16  mov     dword ptr [rbp+30h], 0
0x180004a1d  mov     eax, [rbp+30h]
0x180004a20  add     rsp, 20h
0x180004a24  pop     rbp
0x180004a25  retn
0x180004a27  push    rbp
0x180004a29  sub     rsp, 20h
0x180004a2d  mov     rbp, rdx
0x180004a30  mov     rax, [rcx]
0x180004a33  mov     edx, [rax]
0x180004a35  mov     [rbp+0B0h], rcx
0x180004a3c  mov     [rbp+38h], edx
0x180004a3f  mov     eax, [rbp+38h]
0x180004a42  cmp     eax, 0E06D7363h
0x180004a47  jnz     short loc_180004A5D
0x180004a49  mov     rdx, [rbp+0B0h]
0x180004a50  mov     ecx, [rbp+38h]
0x180004a53  call    _XcptFilter_0
0x180004a58  mov     [rbp+40h], eax
0x180004a5b  jmp     short loc_180004A64
0x180004a5d  mov     dword ptr [rbp+40h], 0
0x180004a64  mov     eax, [rbp+40h]
0x180004a67  add     rsp, 20h
0x180004a6b  pop     rbp
0x180004a6c  retn
0x180004a6e  push    rbp
0x180004a70  sub     rsp, 20h
0x180004a74  mov     rbp, rdx
0x180004a77  mov     rax, [rcx]
0x180004a7a  mov     edx, [rax]
0x180004a7c  mov     [rbp+0B8h], rcx
0x180004a83  mov     [rbp+48h], edx
0x180004a86  mov     eax, [rbp+48h]
0x180004a89  cmp     eax, 0E06D7363h
0x180004a8e  jnz     short loc_180004AA4
0x180004a90  mov     rdx, [rbp+0B8h]
0x180004a97  mov     ecx, [rbp+48h]
0x180004a9a  call    _XcptFilter_0
0x180004a9f  mov     [rbp+50h], eax
0x180004aa2  jmp     short loc_180004AAB
0x180004aa4  mov     dword ptr [rbp+50h], 0
0x180004aab  mov     eax, [rbp+50h]
0x180004aae  add     rsp, 20h
0x180004ab2  pop     rbp
0x180004ab3  retn
0x180004ab5  push    rbp
0x180004ab7  sub     rsp, 20h
0x180004abb  mov     rbp, rdx
0x180004abe  mov     rax, [rcx]
0x180004ac1  mov     edx, [rax]
0x180004ac3  mov     [rbp+0C0h], rcx
0x180004aca  mov     [rbp+58h], edx
0x180004acd  mov     eax, [rbp+58h]
0x180004ad0  cmp     eax, 0E06D7363h
0x180004ad5  jnz     short loc_180004AEB
0x180004ad7  mov     rdx, [rbp+0C0h]
0x180004ade  mov     ecx, [rbp+58h]
0x180004ae1  call    _XcptFilter_0
0x180004ae6  mov     [rbp+60h], eax
0x180004ae9  jmp     short loc_180004AF2
0x180004aeb  mov     dword ptr [rbp+60h], 0
0x180004af2  mov     eax, [rbp+60h]
0x180004af5  add     rsp, 20h
0x180004af9  pop     rbp
0x180004afa  retn
0x180004afc  push    rbp
0x180004afe  sub     rsp, 20h
0x180004b02  mov     rbp, rdx
0x180004b05  mov     rax, [rcx]
0x180004b08  mov     edx, [rax]
0x180004b0a  mov     [rbp+0C8h], rcx
0x180004b11  mov     [rbp+68h], edx
0x180004b14  mov     eax, [rbp+68h]
0x180004b17  cmp     eax, 0E06D7363h
0x180004b1c  jnz     short loc_180004B32
0x180004b1e  mov     rdx, [rbp+0C8h]
0x180004b25  mov     ecx, [rbp+68h]
0x180004b28  call    _XcptFilter_0
0x180004b2d  mov     [rbp+70h], eax
0x180004b30  jmp     short loc_180004B39
0x180004b32  mov     dword ptr [rbp+70h], 0
0x180004b39  mov     eax, [rbp+70h]
0x180004b3c  add     rsp, 20h
0x180004b40  pop     rbp
0x180004b41  retn
0x180004b43  push    rbp
0x180004b45  sub     rsp, 20h
0x180004b49  mov     rbp, rdx
0x180004b4c  mov     rax, [rcx]
0x180004b4f  mov     edx, [rax]
0x180004b51  mov     [rbp+0D0h], rcx
0x180004b58  mov     [rbp+78h], edx
0x180004b5b  mov     eax, [rbp+78h]
0x180004b5e  cmp     eax, 0E06D7363h
0x180004b63  jnz     short loc_180004B7C
0x180004b65  mov     rdx, [rbp+0D0h]
0x180004b6c  mov     ecx, [rbp+78h]
0x180004b6f  call    _XcptFilter_0
0x180004b74  mov     [rbp+80h], eax
0x180004b7a  jmp     short loc_180004B86
0x180004b7c  mov     dword ptr [rbp+80h], 0
0x180004b86  mov     eax, [rbp+80h]
0x180004b8c  add     rsp, 20h
0x180004b90  pop     rbp
0x180004b91  retn
0x180004b93  push    rbp
0x180004b95  sub     rsp, 20h
0x180004b99  mov     rbp, rdx
0x180004b9c  mov     rax, [rcx]
0x180004b9f  mov     edx, [rax]
0x180004ba1  mov     [rbp+0D8h], rcx
0x180004ba8  mov     [rbp+88h], edx
0x180004bae  mov     eax, [rbp+88h]
0x180004bb4  cmp     eax, 0E06D7363h
0x180004bb9  jnz     short loc_180004BD5
0x180004bbb  mov     rdx, [rbp+0D8h]
0x180004bc2  mov     ecx, [rbp+88h]
0x180004bc8  call    _XcptFilter_0
0x180004bcd  mov     [rbp+90h], eax
0x180004bd3  jmp     short loc_180004BDF
0x180004bd5  mov     dword ptr [rbp+90h], 0
0x180004bdf  mov     eax, [rbp+90h]
0x180004be5  add     rsp, 20h
0x180004be9  pop     rbp
0x180004bea  retn
0x180004bec  push    rbp
0x180004bee  sub     rsp, 20h
0x180004bf2  mov     rbp, rdx
0x180004bf5  mov     rax, [rcx]
0x180004bf8  mov     edx, [rax]
0x180004bfa  mov     [rbp+0E0h], rcx
0x180004c01  mov     [rbp+98h], edx
0x180004c07  mov     eax, [rbp+98h]
0x180004c0d  cmp     eax, 0E06D7363h
0x180004c12  jnz     short loc_180004C2E
0x180004c14  mov     rdx, [rbp+0E0h]
0x180004c1b  mov     ecx, [rbp+98h]
0x180004c21  call    _XcptFilter_0
0x180004c26  mov     [rbp+0A0h], eax
0x180004c2c  jmp     short loc_180004C38
0x180004c2e  mov     dword ptr [rbp+0A0h], 0
0x180004c38  mov     eax, [rbp+0A0h]
0x180004c3e  add     rsp, 20h
0x180004c42  pop     rbp
0x180004c43  retn
0x180004c45  push    rbp
0x180004c47  sub     rsp, 20h
0x180004c4b  mov     rbp, rdx
0x180004c4e  cmp     dword ptr [rbp+118h], 1
0x180004c55  ja      short loc_180004C61
0x180004c57  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
