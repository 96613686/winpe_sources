# __DllMainCRTStartup

- ea: `0x180001494`
- end: `0x1800016a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x180001220`
- `0x180001494`
- `0x1800016b2`
- `0x180003564`
- `0x18000d910`

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
  if ( (_DWORD)fdwReason || dword_180013240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180013244 = 1;
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
            if ( dword_180013244 )
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
0x180001494  mov     [rsp+lpvReserved], r8
0x180001499  mov     [rsp+arg_8], edx
0x18000149d  mov     [rsp+arg_0], rcx
0x1800014a2  push    rbx
0x1800014a3  push    rsi
0x1800014a4  push    rdi
0x1800014a5  sub     rsp, 0F0h
0x1800014ac  mov     edi, edx
0x1800014ae  mov     rsi, rcx
0x1800014b1  mov     ebx, 1
0x1800014b6  cmp     edx, ebx
0x1800014b8  ja      short loc_1800014C0
0x1800014ba  mov     cs:__native_dllmain_reason, edx
0x1800014c0  test    edx, edx
0x1800014c2  jnz     short loc_1800014D7
0x1800014c4  cmp     cs:dword_180013240, edx
0x1800014ca  jnz     short loc_1800014D7
0x1800014cc  xor     ebx, ebx
0x1800014ce  mov     [rsp+108h+var_E8], ebx
0x1800014d2  jmp     loc_180001684
0x1800014d7  lea     eax, [rdx-1]
0x1800014da  cmp     eax, 1
0x1800014dd  ja      loc_180001564
0x1800014e3  mov     rax, cs:_pRawDllMain
0x1800014ea  test    rax, rax
0x1800014ed  jz      short loc_180001525
0x1800014ef  cmp     edx, 1
0x1800014f2  jnz     short loc_1800014FA
0x1800014f4  mov     cs:dword_180013244, edx
0x1800014fa  mov     r8, [rsp+108h+lpvReserved]
0x180001502  call    cs:__guard_dispatch_icall_fptr
0x180001508  mov     ebx, eax
0x18000150a  mov     [rsp+108h+var_E8], eax
0x18000150e  jmp     short loc_180001525
0x180001510  xor     ebx, ebx
0x180001512  mov     [rsp+108h+var_E8], ebx
0x180001516  mov     edi, [rsp+108h+arg_8]
0x18000151d  mov     rsi, [rsp+108h+arg_0]
0x180001525  test    ebx, ebx
0x180001527  jz      loc_180001684
0x18000152d  mov     r8, [rsp+108h+lpvReserved]
0x180001535  mov     edx, edi
0x180001537  mov     rcx, rsi
0x18000153a  call    _CRT_INIT
0x18000153f  mov     ebx, eax
0x180001541  mov     [rsp+108h+var_E8], eax
0x180001545  jmp     short loc_18000155C
0x180001547  xor     ebx, ebx
0x180001549  mov     [rsp+108h+var_E8], ebx
0x18000154d  mov     edi, [rsp+108h+arg_8]
0x180001554  mov     rsi, [rsp+108h+arg_0]
0x18000155c  test    ebx, ebx
0x18000155e  jz      loc_180001684
0x180001564  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000156c  mov     edx, edi; fdwReason
0x18000156e  mov     rcx, rsi; hinstDLL
0x180001571  call    DllMain
0x180001576  mov     ebx, eax
0x180001578  mov     [rsp+108h+var_E8], eax
0x18000157c  jmp     short loc_180001593
0x18000157e  xor     ebx, ebx
0x180001580  mov     [rsp+108h+var_E8], ebx
0x180001584  mov     edi, [rsp+108h+arg_8]
0x18000158b  mov     rsi, [rsp+108h+arg_0]
0x180001593  cmp     edi, 1
0x180001596  jnz     short loc_18000160F
0x180001598  test    ebx, ebx
0x18000159a  jnz     short loc_18000160F
0x18000159c  xor     r8d, r8d; lpvReserved
0x18000159f  xor     edx, edx; fdwReason
0x1800015a1  mov     rcx, rsi; hinstDLL
0x1800015a4  call    DllMain
0x1800015a9  jmp     short loc_1800015BE
0x1800015ab  mov     edi, [rsp+108h+arg_8]
0x1800015b2  mov     rsi, [rsp+108h+arg_0]
0x1800015ba  mov     ebx, [rsp+108h+var_E8]
0x1800015be  xor     r8d, r8d
0x1800015c1  xor     edx, edx
0x1800015c3  mov     rcx, rsi
0x1800015c6  call    _CRT_INIT
0x1800015cb  jmp     short loc_1800015E0
0x1800015cd  mov     edi, [rsp+108h+arg_8]
0x1800015d4  mov     rsi, [rsp+108h+arg_0]
0x1800015dc  mov     ebx, [rsp+108h+var_E8]
0x1800015e0  mov     rax, cs:_pRawDllMain
0x1800015e7  test    rax, rax
0x1800015ea  jz      short loc_18000160F
0x1800015ec  xor     r8d, r8d
0x1800015ef  xor     edx, edx
0x1800015f1  mov     rcx, rsi
0x1800015f4  call    cs:__guard_dispatch_icall_fptr
0x1800015fa  jmp     short loc_18000160F
0x1800015fc  mov     edi, [rsp+108h+arg_8]
0x180001603  mov     rsi, [rsp+108h+arg_0]
0x18000160b  mov     ebx, [rsp+108h+var_E8]
0x18000160f  test    edi, edi
0x180001611  jz      short loc_180001618
0x180001613  cmp     edi, 3
0x180001616  jnz     short loc_180001684
0x180001618  mov     r8, [rsp+108h+lpvReserved]
0x180001620  mov     edx, edi
0x180001622  mov     rcx, rsi
0x180001625  call    _CRT_INIT
0x18000162a  mov     ebx, eax
0x18000162c  mov     [rsp+108h+var_E8], eax
0x180001630  jmp     short loc_180001647
0x180001632  xor     ebx, ebx
0x180001634  mov     [rsp+108h+var_E8], ebx
0x180001638  mov     edi, [rsp+108h+arg_8]
0x18000163f  mov     rsi, [rsp+108h+arg_0]
0x180001647  mov     rax, cs:_pRawDllMain
0x18000164e  test    rax, rax
0x180001651  jz      short loc_180001684
0x180001653  cmp     cs:dword_180013244, 0
0x18000165a  jz      short loc_180001684
0x18000165c  mov     r8, [rsp+108h+lpvReserved]
0x180001664  mov     edx, edi
0x180001666  mov     rcx, rsi
0x180001669  call    cs:__guard_dispatch_icall_fptr
0x18000166f  mov     ebx, eax
0x180001671  mov     [rsp+108h+var_E8], eax
0x180001675  jmp     short loc_180001684
0x180001677  xor     ebx, ebx
0x180001679  mov     [rsp+108h+var_E8], ebx
0x18000167d  mov     edi, [rsp+108h+arg_8]
0x180001684  cmp     edi, 1
0x180001687  ja      short loc_180001693
0x180001689  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001693  mov     eax, ebx
0x180001695  add     rsp, 0F0h
0x18000169c  pop     rdi
0x18000169d  pop     rsi
0x18000169e  pop     rbx
0x18000169f  retn
0x18000d9e0  push    rbp
0x18000d9e2  sub     rsp, 20h
0x18000d9e6  mov     rbp, rdx
0x18000d9e9  mov     rax, [rcx]
0x18000d9ec  mov     edx, [rax]
0x18000d9ee  mov     [rbp+0A8h], rcx
0x18000d9f5  mov     [rbp+28h], edx
0x18000d9f8  mov     eax, [rbp+28h]
0x18000d9fb  cmp     eax, 0E06D7363h
0x18000da00  jnz     short loc_18000DA16
0x18000da02  mov     rdx, [rbp+0A8h]
0x18000da09  mov     ecx, [rbp+28h]
0x18000da0c  call    _XcptFilter_0
0x18000da11  mov     [rbp+30h], eax
0x18000da14  jmp     short loc_18000DA1D
0x18000da16  mov     dword ptr [rbp+30h], 0
0x18000da1d  mov     eax, [rbp+30h]
0x18000da20  add     rsp, 20h
0x18000da24  pop     rbp
0x18000da25  retn
0x18000da27  push    rbp
0x18000da29  sub     rsp, 20h
0x18000da2d  mov     rbp, rdx
0x18000da30  mov     rax, [rcx]
0x18000da33  mov     edx, [rax]
0x18000da35  mov     [rbp+0B0h], rcx
0x18000da3c  mov     [rbp+38h], edx
0x18000da3f  mov     eax, [rbp+38h]
0x18000da42  cmp     eax, 0E06D7363h
0x18000da47  jnz     short loc_18000DA5D
0x18000da49  mov     rdx, [rbp+0B0h]
0x18000da50  mov     ecx, [rbp+38h]
0x18000da53  call    _XcptFilter_0
0x18000da58  mov     [rbp+40h], eax
0x18000da5b  jmp     short loc_18000DA64
0x18000da5d  mov     dword ptr [rbp+40h], 0
0x18000da64  mov     eax, [rbp+40h]
0x18000da67  add     rsp, 20h
0x18000da6b  pop     rbp
0x18000da6c  retn
0x18000da6e  push    rbp
0x18000da70  sub     rsp, 20h
0x18000da74  mov     rbp, rdx
0x18000da77  mov     rax, [rcx]
0x18000da7a  mov     edx, [rax]
0x18000da7c  mov     [rbp+0B8h], rcx
0x18000da83  mov     [rbp+48h], edx
0x18000da86  mov     eax, [rbp+48h]
0x18000da89  cmp     eax, 0E06D7363h
0x18000da8e  jnz     short loc_18000DAA4
0x18000da90  mov     rdx, [rbp+0B8h]
0x18000da97  mov     ecx, [rbp+48h]
0x18000da9a  call    _XcptFilter_0
0x18000da9f  mov     [rbp+50h], eax
0x18000daa2  jmp     short loc_18000DAAB
0x18000daa4  mov     dword ptr [rbp+50h], 0
0x18000daab  mov     eax, [rbp+50h]
0x18000daae  add     rsp, 20h
0x18000dab2  pop     rbp
0x18000dab3  retn
0x18000dab5  push    rbp
0x18000dab7  sub     rsp, 20h
0x18000dabb  mov     rbp, rdx
0x18000dabe  mov     rax, [rcx]
0x18000dac1  mov     edx, [rax]
0x18000dac3  mov     [rbp+0C0h], rcx
0x18000daca  mov     [rbp+58h], edx
0x18000dacd  mov     eax, [rbp+58h]
0x18000dad0  cmp     eax, 0E06D7363h
0x18000dad5  jnz     short loc_18000DAEB
0x18000dad7  mov     rdx, [rbp+0C0h]
0x18000dade  mov     ecx, [rbp+58h]
0x18000dae1  call    _XcptFilter_0
0x18000dae6  mov     [rbp+60h], eax
0x18000dae9  jmp     short loc_18000DAF2
0x18000daeb  mov     dword ptr [rbp+60h], 0
0x18000daf2  mov     eax, [rbp+60h]
0x18000daf5  add     rsp, 20h
0x18000daf9  pop     rbp
0x18000dafa  retn
0x18000dafc  push    rbp
0x18000dafe  sub     rsp, 20h
0x18000db02  mov     rbp, rdx
0x18000db05  mov     rax, [rcx]
0x18000db08  mov     edx, [rax]
0x18000db0a  mov     [rbp+0C8h], rcx
0x18000db11  mov     [rbp+68h], edx
0x18000db14  mov     eax, [rbp+68h]
0x18000db17  cmp     eax, 0E06D7363h
0x18000db1c  jnz     short loc_18000DB32
0x18000db1e  mov     rdx, [rbp+0C8h]
0x18000db25  mov     ecx, [rbp+68h]
0x18000db28  call    _XcptFilter_0
0x18000db2d  mov     [rbp+70h], eax
0x18000db30  jmp     short loc_18000DB39
0x18000db32  mov     dword ptr [rbp+70h], 0
0x18000db39  mov     eax, [rbp+70h]
0x18000db3c  add     rsp, 20h
0x18000db40  pop     rbp
0x18000db41  retn
0x18000db43  push    rbp
0x18000db45  sub     rsp, 20h
0x18000db49  mov     rbp, rdx
0x18000db4c  mov     rax, [rcx]
0x18000db4f  mov     edx, [rax]
0x18000db51  mov     [rbp+0D0h], rcx
0x18000db58  mov     [rbp+78h], edx
0x18000db5b  mov     eax, [rbp+78h]
0x18000db5e  cmp     eax, 0E06D7363h
0x18000db63  jnz     short loc_18000DB7C
0x18000db65  mov     rdx, [rbp+0D0h]
0x18000db6c  mov     ecx, [rbp+78h]
0x18000db6f  call    _XcptFilter_0
0x18000db74  mov     [rbp+80h], eax
0x18000db7a  jmp     short loc_18000DB86
0x18000db7c  mov     dword ptr [rbp+80h], 0
0x18000db86  mov     eax, [rbp+80h]
0x18000db8c  add     rsp, 20h
0x18000db90  pop     rbp
0x18000db91  retn
0x18000db93  push    rbp
0x18000db95  sub     rsp, 20h
0x18000db99  mov     rbp, rdx
0x18000db9c  mov     rax, [rcx]
0x18000db9f  mov     edx, [rax]
0x18000dba1  mov     [rbp+0D8h], rcx
0x18000dba8  mov     [rbp+88h], edx
0x18000dbae  mov     eax, [rbp+88h]
0x18000dbb4  cmp     eax, 0E06D7363h
0x18000dbb9  jnz     short loc_18000DBD5
0x18000dbbb  mov     rdx, [rbp+0D8h]
0x18000dbc2  mov     ecx, [rbp+88h]
0x18000dbc8  call    _XcptFilter_0
0x18000dbcd  mov     [rbp+90h], eax
0x18000dbd3  jmp     short loc_18000DBDF
0x18000dbd5  mov     dword ptr [rbp+90h], 0
0x18000dbdf  mov     eax, [rbp+90h]
0x18000dbe5  add     rsp, 20h
0x18000dbe9  pop     rbp
0x18000dbea  retn
0x18000dbec  push    rbp
0x18000dbee  sub     rsp, 20h
0x18000dbf2  mov     rbp, rdx
0x18000dbf5  mov     rax, [rcx]
0x18000dbf8  mov     edx, [rax]
0x18000dbfa  mov     [rbp+0E0h], rcx
0x18000dc01  mov     [rbp+98h], edx
0x18000dc07  mov     eax, [rbp+98h]
0x18000dc0d  cmp     eax, 0E06D7363h
0x18000dc12  jnz     short loc_18000DC2E
0x18000dc14  mov     rdx, [rbp+0E0h]
0x18000dc1b  mov     ecx, [rbp+98h]
0x18000dc21  call    _XcptFilter_0
0x18000dc26  mov     [rbp+0A0h], eax
0x18000dc2c  jmp     short loc_18000DC38
0x18000dc2e  mov     dword ptr [rbp+0A0h], 0
0x18000dc38  mov     eax, [rbp+0A0h]
0x18000dc3e  add     rsp, 20h
0x18000dc42  pop     rbp
0x18000dc43  retn
0x18000dc45  push    rbp
0x18000dc47  sub     rsp, 20h
0x18000dc4b  mov     rbp, rdx
0x18000dc4e  cmp     dword ptr [rbp+118h], 1
0x18000dc55  ja      short loc_18000DC61
0x18000dc57  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
