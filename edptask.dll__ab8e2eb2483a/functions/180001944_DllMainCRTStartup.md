# __DllMainCRTStartup

- ea: `0x180001944`
- end: `0x180001b50`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x1800016d0`
- `0x180001944`
- `0x180001d1e`
- `0x180002de8`
- `0x180013480`

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
  if ( (_DWORD)fdwReason || dword_18001D41C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001D420 = 1;
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
            if ( dword_18001D420 )
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
0x180001944  mov     [rsp+lpvReserved], r8
0x180001949  mov     [rsp+arg_8], edx
0x18000194d  mov     [rsp+arg_0], rcx
0x180001952  push    rbx
0x180001953  push    rsi
0x180001954  push    rdi
0x180001955  sub     rsp, 0F0h
0x18000195c  mov     edi, edx
0x18000195e  mov     rsi, rcx
0x180001961  mov     ebx, 1
0x180001966  cmp     edx, ebx
0x180001968  ja      short loc_180001970
0x18000196a  mov     cs:__native_dllmain_reason, edx
0x180001970  test    edx, edx
0x180001972  jnz     short loc_180001987
0x180001974  cmp     cs:dword_18001D41C, edx
0x18000197a  jnz     short loc_180001987
0x18000197c  xor     ebx, ebx
0x18000197e  mov     [rsp+108h+var_E8], ebx
0x180001982  jmp     loc_180001B34
0x180001987  lea     eax, [rdx-1]
0x18000198a  cmp     eax, 1
0x18000198d  ja      loc_180001A14
0x180001993  mov     rax, cs:_pRawDllMain
0x18000199a  test    rax, rax
0x18000199d  jz      short loc_1800019D5
0x18000199f  cmp     edx, 1
0x1800019a2  jnz     short loc_1800019AA
0x1800019a4  mov     cs:dword_18001D420, edx
0x1800019aa  mov     r8, [rsp+108h+lpvReserved]
0x1800019b2  call    cs:__guard_dispatch_icall_fptr
0x1800019b8  mov     ebx, eax
0x1800019ba  mov     [rsp+108h+var_E8], eax
0x1800019be  jmp     short loc_1800019D5
0x1800019c0  xor     ebx, ebx
0x1800019c2  mov     [rsp+108h+var_E8], ebx
0x1800019c6  mov     edi, [rsp+108h+arg_8]
0x1800019cd  mov     rsi, [rsp+108h+arg_0]
0x1800019d5  test    ebx, ebx
0x1800019d7  jz      loc_180001B34
0x1800019dd  mov     r8, [rsp+108h+lpvReserved]
0x1800019e5  mov     edx, edi
0x1800019e7  mov     rcx, rsi
0x1800019ea  call    _CRT_INIT
0x1800019ef  mov     ebx, eax
0x1800019f1  mov     [rsp+108h+var_E8], eax
0x1800019f5  jmp     short loc_180001A0C
0x1800019f7  xor     ebx, ebx
0x1800019f9  mov     [rsp+108h+var_E8], ebx
0x1800019fd  mov     edi, [rsp+108h+arg_8]
0x180001a04  mov     rsi, [rsp+108h+arg_0]
0x180001a0c  test    ebx, ebx
0x180001a0e  jz      loc_180001B34
0x180001a14  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a1c  mov     edx, edi; fdwReason
0x180001a1e  mov     rcx, rsi; hinstDLL
0x180001a21  call    DllMain
0x180001a26  mov     ebx, eax
0x180001a28  mov     [rsp+108h+var_E8], eax
0x180001a2c  jmp     short loc_180001A43
0x180001a2e  xor     ebx, ebx
0x180001a30  mov     [rsp+108h+var_E8], ebx
0x180001a34  mov     edi, [rsp+108h+arg_8]
0x180001a3b  mov     rsi, [rsp+108h+arg_0]
0x180001a43  cmp     edi, 1
0x180001a46  jnz     short loc_180001ABF
0x180001a48  test    ebx, ebx
0x180001a4a  jnz     short loc_180001ABF
0x180001a4c  xor     r8d, r8d; lpvReserved
0x180001a4f  xor     edx, edx; fdwReason
0x180001a51  mov     rcx, rsi; hinstDLL
0x180001a54  call    DllMain
0x180001a59  jmp     short loc_180001A6E
0x180001a5b  mov     edi, [rsp+108h+arg_8]
0x180001a62  mov     rsi, [rsp+108h+arg_0]
0x180001a6a  mov     ebx, [rsp+108h+var_E8]
0x180001a6e  xor     r8d, r8d
0x180001a71  xor     edx, edx
0x180001a73  mov     rcx, rsi
0x180001a76  call    _CRT_INIT
0x180001a7b  jmp     short loc_180001A90
0x180001a7d  mov     edi, [rsp+108h+arg_8]
0x180001a84  mov     rsi, [rsp+108h+arg_0]
0x180001a8c  mov     ebx, [rsp+108h+var_E8]
0x180001a90  mov     rax, cs:_pRawDllMain
0x180001a97  test    rax, rax
0x180001a9a  jz      short loc_180001ABF
0x180001a9c  xor     r8d, r8d
0x180001a9f  xor     edx, edx
0x180001aa1  mov     rcx, rsi
0x180001aa4  call    cs:__guard_dispatch_icall_fptr
0x180001aaa  jmp     short loc_180001ABF
0x180001aac  mov     edi, [rsp+108h+arg_8]
0x180001ab3  mov     rsi, [rsp+108h+arg_0]
0x180001abb  mov     ebx, [rsp+108h+var_E8]
0x180001abf  test    edi, edi
0x180001ac1  jz      short loc_180001AC8
0x180001ac3  cmp     edi, 3
0x180001ac6  jnz     short loc_180001B34
0x180001ac8  mov     r8, [rsp+108h+lpvReserved]
0x180001ad0  mov     edx, edi
0x180001ad2  mov     rcx, rsi
0x180001ad5  call    _CRT_INIT
0x180001ada  mov     ebx, eax
0x180001adc  mov     [rsp+108h+var_E8], eax
0x180001ae0  jmp     short loc_180001AF7
0x180001ae2  xor     ebx, ebx
0x180001ae4  mov     [rsp+108h+var_E8], ebx
0x180001ae8  mov     edi, [rsp+108h+arg_8]
0x180001aef  mov     rsi, [rsp+108h+arg_0]
0x180001af7  mov     rax, cs:_pRawDllMain
0x180001afe  test    rax, rax
0x180001b01  jz      short loc_180001B34
0x180001b03  cmp     cs:dword_18001D420, 0
0x180001b0a  jz      short loc_180001B34
0x180001b0c  mov     r8, [rsp+108h+lpvReserved]
0x180001b14  mov     edx, edi
0x180001b16  mov     rcx, rsi
0x180001b19  call    cs:__guard_dispatch_icall_fptr
0x180001b1f  mov     ebx, eax
0x180001b21  mov     [rsp+108h+var_E8], eax
0x180001b25  jmp     short loc_180001B34
0x180001b27  xor     ebx, ebx
0x180001b29  mov     [rsp+108h+var_E8], ebx
0x180001b2d  mov     edi, [rsp+108h+arg_8]
0x180001b34  cmp     edi, 1
0x180001b37  ja      short loc_180001B43
0x180001b39  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b43  mov     eax, ebx
0x180001b45  add     rsp, 0F0h
0x180001b4c  pop     rdi
0x180001b4d  pop     rsi
0x180001b4e  pop     rbx
0x180001b4f  retn
0x180013523  push    rbp
0x180013525  sub     rsp, 20h
0x180013529  mov     rbp, rdx
0x18001352c  mov     rax, [rcx]
0x18001352f  mov     edx, [rax]
0x180013531  mov     [rbp+0A8h], rcx
0x180013538  mov     [rbp+28h], edx
0x18001353b  mov     eax, [rbp+28h]
0x18001353e  cmp     eax, 0E06D7363h
0x180013543  jnz     short loc_180013559
0x180013545  mov     rdx, [rbp+0A8h]
0x18001354c  mov     ecx, [rbp+28h]
0x18001354f  call    _XcptFilter_0
0x180013554  mov     [rbp+30h], eax
0x180013557  jmp     short loc_180013560
0x180013559  mov     dword ptr [rbp+30h], 0
0x180013560  mov     eax, [rbp+30h]
0x180013563  add     rsp, 20h
0x180013567  pop     rbp
0x180013568  retn
0x18001356a  push    rbp
0x18001356c  sub     rsp, 20h
0x180013570  mov     rbp, rdx
0x180013573  mov     rax, [rcx]
0x180013576  mov     edx, [rax]
0x180013578  mov     [rbp+0B0h], rcx
0x18001357f  mov     [rbp+38h], edx
0x180013582  mov     eax, [rbp+38h]
0x180013585  cmp     eax, 0E06D7363h
0x18001358a  jnz     short loc_1800135A0
0x18001358c  mov     rdx, [rbp+0B0h]
0x180013593  mov     ecx, [rbp+38h]
0x180013596  call    _XcptFilter_0
0x18001359b  mov     [rbp+40h], eax
0x18001359e  jmp     short loc_1800135A7
0x1800135a0  mov     dword ptr [rbp+40h], 0
0x1800135a7  mov     eax, [rbp+40h]
0x1800135aa  add     rsp, 20h
0x1800135ae  pop     rbp
0x1800135af  retn
0x1800135b1  push    rbp
0x1800135b3  sub     rsp, 20h
0x1800135b7  mov     rbp, rdx
0x1800135ba  mov     rax, [rcx]
0x1800135bd  mov     edx, [rax]
0x1800135bf  mov     [rbp+0B8h], rcx
0x1800135c6  mov     [rbp+48h], edx
0x1800135c9  mov     eax, [rbp+48h]
0x1800135cc  cmp     eax, 0E06D7363h
0x1800135d1  jnz     short loc_1800135E7
0x1800135d3  mov     rdx, [rbp+0B8h]
0x1800135da  mov     ecx, [rbp+48h]
0x1800135dd  call    _XcptFilter_0
0x1800135e2  mov     [rbp+50h], eax
0x1800135e5  jmp     short loc_1800135EE
0x1800135e7  mov     dword ptr [rbp+50h], 0
0x1800135ee  mov     eax, [rbp+50h]
0x1800135f1  add     rsp, 20h
0x1800135f5  pop     rbp
0x1800135f6  retn
0x1800135f8  push    rbp
0x1800135fa  sub     rsp, 20h
0x1800135fe  mov     rbp, rdx
0x180013601  mov     rax, [rcx]
0x180013604  mov     edx, [rax]
0x180013606  mov     [rbp+0C0h], rcx
0x18001360d  mov     [rbp+58h], edx
0x180013610  mov     eax, [rbp+58h]
0x180013613  cmp     eax, 0E06D7363h
0x180013618  jnz     short loc_18001362E
0x18001361a  mov     rdx, [rbp+0C0h]
0x180013621  mov     ecx, [rbp+58h]
0x180013624  call    _XcptFilter_0
0x180013629  mov     [rbp+60h], eax
0x18001362c  jmp     short loc_180013635
0x18001362e  mov     dword ptr [rbp+60h], 0
0x180013635  mov     eax, [rbp+60h]
0x180013638  add     rsp, 20h
0x18001363c  pop     rbp
0x18001363d  retn
0x18001363f  push    rbp
0x180013641  sub     rsp, 20h
0x180013645  mov     rbp, rdx
0x180013648  mov     rax, [rcx]
0x18001364b  mov     edx, [rax]
0x18001364d  mov     [rbp+0C8h], rcx
0x180013654  mov     [rbp+68h], edx
0x180013657  mov     eax, [rbp+68h]
0x18001365a  cmp     eax, 0E06D7363h
0x18001365f  jnz     short loc_180013675
0x180013661  mov     rdx, [rbp+0C8h]
0x180013668  mov     ecx, [rbp+68h]
0x18001366b  call    _XcptFilter_0
0x180013670  mov     [rbp+70h], eax
0x180013673  jmp     short loc_18001367C
0x180013675  mov     dword ptr [rbp+70h], 0
0x18001367c  mov     eax, [rbp+70h]
0x18001367f  add     rsp, 20h
0x180013683  pop     rbp
0x180013684  retn
0x180013686  push    rbp
0x180013688  sub     rsp, 20h
0x18001368c  mov     rbp, rdx
0x18001368f  mov     rax, [rcx]
0x180013692  mov     edx, [rax]
0x180013694  mov     [rbp+0D0h], rcx
0x18001369b  mov     [rbp+78h], edx
0x18001369e  mov     eax, [rbp+78h]
0x1800136a1  cmp     eax, 0E06D7363h
0x1800136a6  jnz     short loc_1800136BF
0x1800136a8  mov     rdx, [rbp+0D0h]
0x1800136af  mov     ecx, [rbp+78h]
0x1800136b2  call    _XcptFilter_0
0x1800136b7  mov     [rbp+80h], eax
0x1800136bd  jmp     short loc_1800136C9
0x1800136bf  mov     dword ptr [rbp+80h], 0
0x1800136c9  mov     eax, [rbp+80h]
0x1800136cf  add     rsp, 20h
0x1800136d3  pop     rbp
0x1800136d4  retn
0x1800136d6  push    rbp
0x1800136d8  sub     rsp, 20h
0x1800136dc  mov     rbp, rdx
0x1800136df  mov     rax, [rcx]
0x1800136e2  mov     edx, [rax]
0x1800136e4  mov     [rbp+0D8h], rcx
0x1800136eb  mov     [rbp+88h], edx
0x1800136f1  mov     eax, [rbp+88h]
0x1800136f7  cmp     eax, 0E06D7363h
0x1800136fc  jnz     short loc_180013718
0x1800136fe  mov     rdx, [rbp+0D8h]
0x180013705  mov     ecx, [rbp+88h]
0x18001370b  call    _XcptFilter_0
0x180013710  mov     [rbp+90h], eax
0x180013716  jmp     short loc_180013722
0x180013718  mov     dword ptr [rbp+90h], 0
0x180013722  mov     eax, [rbp+90h]
0x180013728  add     rsp, 20h
0x18001372c  pop     rbp
0x18001372d  retn
0x18001372f  push    rbp
0x180013731  sub     rsp, 20h
0x180013735  mov     rbp, rdx
0x180013738  mov     rax, [rcx]
0x18001373b  mov     edx, [rax]
0x18001373d  mov     [rbp+0E0h], rcx
0x180013744  mov     [rbp+98h], edx
0x18001374a  mov     eax, [rbp+98h]
0x180013750  cmp     eax, 0E06D7363h
0x180013755  jnz     short loc_180013771
0x180013757  mov     rdx, [rbp+0E0h]
0x18001375e  mov     ecx, [rbp+98h]
0x180013764  call    _XcptFilter_0
0x180013769  mov     [rbp+0A0h], eax
0x18001376f  jmp     short loc_18001377B
0x180013771  mov     dword ptr [rbp+0A0h], 0
0x18001377b  mov     eax, [rbp+0A0h]
0x180013781  add     rsp, 20h
0x180013785  pop     rbp
0x180013786  retn
0x180013788  push    rbp
0x18001378a  sub     rsp, 20h
0x18001378e  mov     rbp, rdx
0x180013791  cmp     dword ptr [rbp+118h], 1
0x180013798  ja      short loc_1800137A4
0x18001379a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
