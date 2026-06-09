# __DllMainCRTStartup

- ea: `0x180001494`
- end: `0x1800016a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x180001220`
- `0x180001494`
- `0x180001889`
- `0x18000a710`
- `0x18000bc30`

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
  if ( (_DWORD)fdwReason || dword_180015240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180015244 = 1;
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
            if ( dword_180015244 )
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
0x1800014c4  cmp     cs:dword_180015240, edx
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
0x1800014f4  mov     cs:dword_180015244, edx
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
0x180001653  cmp     cs:dword_180015244, 0
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
0x18000bd00  push    rbp
0x18000bd02  sub     rsp, 20h
0x18000bd06  mov     rbp, rdx
0x18000bd09  mov     rax, [rcx]
0x18000bd0c  mov     edx, [rax]
0x18000bd0e  mov     [rbp+0A8h], rcx
0x18000bd15  mov     [rbp+28h], edx
0x18000bd18  mov     eax, [rbp+28h]
0x18000bd1b  cmp     eax, 0E06D7363h
0x18000bd20  jnz     short loc_18000BD36
0x18000bd22  mov     rdx, [rbp+0A8h]
0x18000bd29  mov     ecx, [rbp+28h]
0x18000bd2c  call    _XcptFilter_0
0x18000bd31  mov     [rbp+30h], eax
0x18000bd34  jmp     short loc_18000BD3D
0x18000bd36  mov     dword ptr [rbp+30h], 0
0x18000bd3d  mov     eax, [rbp+30h]
0x18000bd40  add     rsp, 20h
0x18000bd44  pop     rbp
0x18000bd45  retn
0x18000bd47  push    rbp
0x18000bd49  sub     rsp, 20h
0x18000bd4d  mov     rbp, rdx
0x18000bd50  mov     rax, [rcx]
0x18000bd53  mov     edx, [rax]
0x18000bd55  mov     [rbp+0B0h], rcx
0x18000bd5c  mov     [rbp+38h], edx
0x18000bd5f  mov     eax, [rbp+38h]
0x18000bd62  cmp     eax, 0E06D7363h
0x18000bd67  jnz     short loc_18000BD7D
0x18000bd69  mov     rdx, [rbp+0B0h]
0x18000bd70  mov     ecx, [rbp+38h]
0x18000bd73  call    _XcptFilter_0
0x18000bd78  mov     [rbp+40h], eax
0x18000bd7b  jmp     short loc_18000BD84
0x18000bd7d  mov     dword ptr [rbp+40h], 0
0x18000bd84  mov     eax, [rbp+40h]
0x18000bd87  add     rsp, 20h
0x18000bd8b  pop     rbp
0x18000bd8c  retn
0x18000bd8e  push    rbp
0x18000bd90  sub     rsp, 20h
0x18000bd94  mov     rbp, rdx
0x18000bd97  mov     rax, [rcx]
0x18000bd9a  mov     edx, [rax]
0x18000bd9c  mov     [rbp+0B8h], rcx
0x18000bda3  mov     [rbp+48h], edx
0x18000bda6  mov     eax, [rbp+48h]
0x18000bda9  cmp     eax, 0E06D7363h
0x18000bdae  jnz     short loc_18000BDC4
0x18000bdb0  mov     rdx, [rbp+0B8h]
0x18000bdb7  mov     ecx, [rbp+48h]
0x18000bdba  call    _XcptFilter_0
0x18000bdbf  mov     [rbp+50h], eax
0x18000bdc2  jmp     short loc_18000BDCB
0x18000bdc4  mov     dword ptr [rbp+50h], 0
0x18000bdcb  mov     eax, [rbp+50h]
0x18000bdce  add     rsp, 20h
0x18000bdd2  pop     rbp
0x18000bdd3  retn
0x18000bdd5  push    rbp
0x18000bdd7  sub     rsp, 20h
0x18000bddb  mov     rbp, rdx
0x18000bdde  mov     rax, [rcx]
0x18000bde1  mov     edx, [rax]
0x18000bde3  mov     [rbp+0C0h], rcx
0x18000bdea  mov     [rbp+58h], edx
0x18000bded  mov     eax, [rbp+58h]
0x18000bdf0  cmp     eax, 0E06D7363h
0x18000bdf5  jnz     short loc_18000BE0B
0x18000bdf7  mov     rdx, [rbp+0C0h]
0x18000bdfe  mov     ecx, [rbp+58h]
0x18000be01  call    _XcptFilter_0
0x18000be06  mov     [rbp+60h], eax
0x18000be09  jmp     short loc_18000BE12
0x18000be0b  mov     dword ptr [rbp+60h], 0
0x18000be12  mov     eax, [rbp+60h]
0x18000be15  add     rsp, 20h
0x18000be19  pop     rbp
0x18000be1a  retn
0x18000be1c  push    rbp
0x18000be1e  sub     rsp, 20h
0x18000be22  mov     rbp, rdx
0x18000be25  mov     rax, [rcx]
0x18000be28  mov     edx, [rax]
0x18000be2a  mov     [rbp+0C8h], rcx
0x18000be31  mov     [rbp+68h], edx
0x18000be34  mov     eax, [rbp+68h]
0x18000be37  cmp     eax, 0E06D7363h
0x18000be3c  jnz     short loc_18000BE52
0x18000be3e  mov     rdx, [rbp+0C8h]
0x18000be45  mov     ecx, [rbp+68h]
0x18000be48  call    _XcptFilter_0
0x18000be4d  mov     [rbp+70h], eax
0x18000be50  jmp     short loc_18000BE59
0x18000be52  mov     dword ptr [rbp+70h], 0
0x18000be59  mov     eax, [rbp+70h]
0x18000be5c  add     rsp, 20h
0x18000be60  pop     rbp
0x18000be61  retn
0x18000be63  push    rbp
0x18000be65  sub     rsp, 20h
0x18000be69  mov     rbp, rdx
0x18000be6c  mov     rax, [rcx]
0x18000be6f  mov     edx, [rax]
0x18000be71  mov     [rbp+0D0h], rcx
0x18000be78  mov     [rbp+78h], edx
0x18000be7b  mov     eax, [rbp+78h]
0x18000be7e  cmp     eax, 0E06D7363h
0x18000be83  jnz     short loc_18000BE9C
0x18000be85  mov     rdx, [rbp+0D0h]
0x18000be8c  mov     ecx, [rbp+78h]
0x18000be8f  call    _XcptFilter_0
0x18000be94  mov     [rbp+80h], eax
0x18000be9a  jmp     short loc_18000BEA6
0x18000be9c  mov     dword ptr [rbp+80h], 0
0x18000bea6  mov     eax, [rbp+80h]
0x18000beac  add     rsp, 20h
0x18000beb0  pop     rbp
0x18000beb1  retn
0x18000beb3  push    rbp
0x18000beb5  sub     rsp, 20h
0x18000beb9  mov     rbp, rdx
0x18000bebc  mov     rax, [rcx]
0x18000bebf  mov     edx, [rax]
0x18000bec1  mov     [rbp+0D8h], rcx
0x18000bec8  mov     [rbp+88h], edx
0x18000bece  mov     eax, [rbp+88h]
0x18000bed4  cmp     eax, 0E06D7363h
0x18000bed9  jnz     short loc_18000BEF5
0x18000bedb  mov     rdx, [rbp+0D8h]
0x18000bee2  mov     ecx, [rbp+88h]
0x18000bee8  call    _XcptFilter_0
0x18000beed  mov     [rbp+90h], eax
0x18000bef3  jmp     short loc_18000BEFF
0x18000bef5  mov     dword ptr [rbp+90h], 0
0x18000beff  mov     eax, [rbp+90h]
0x18000bf05  add     rsp, 20h
0x18000bf09  pop     rbp
0x18000bf0a  retn
0x18000bf0c  push    rbp
0x18000bf0e  sub     rsp, 20h
0x18000bf12  mov     rbp, rdx
0x18000bf15  mov     rax, [rcx]
0x18000bf18  mov     edx, [rax]
0x18000bf1a  mov     [rbp+0E0h], rcx
0x18000bf21  mov     [rbp+98h], edx
0x18000bf27  mov     eax, [rbp+98h]
0x18000bf2d  cmp     eax, 0E06D7363h
0x18000bf32  jnz     short loc_18000BF4E
0x18000bf34  mov     rdx, [rbp+0E0h]
0x18000bf3b  mov     ecx, [rbp+98h]
0x18000bf41  call    _XcptFilter_0
0x18000bf46  mov     [rbp+0A0h], eax
0x18000bf4c  jmp     short loc_18000BF58
0x18000bf4e  mov     dword ptr [rbp+0A0h], 0
0x18000bf58  mov     eax, [rbp+0A0h]
0x18000bf5e  add     rsp, 20h
0x18000bf62  pop     rbp
0x18000bf63  retn
0x18000bf65  push    rbp
0x18000bf67  sub     rsp, 20h
0x18000bf6b  mov     rbp, rdx
0x18000bf6e  cmp     dword ptr [rbp+118h], 1
0x18000bf75  ja      short loc_18000BF81
0x18000bf77  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
