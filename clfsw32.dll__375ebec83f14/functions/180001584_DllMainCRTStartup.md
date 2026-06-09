# __DllMainCRTStartup

- ea: `0x180001584`
- end: `0x180001790`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001540`

## callees

- `0x180001310`
- `0x180001584`
- `0x1800018af`
- `0x18000ab74`
- `0x180014e40`

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
  if ( (_DWORD)fdwReason || dword_18001D340 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001D344 = 1;
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
            if ( dword_18001D344 )
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
0x180001584  mov     [rsp+lpvReserved], r8
0x180001589  mov     [rsp+arg_8], edx
0x18000158d  mov     [rsp+arg_0], rcx
0x180001592  push    rbx
0x180001593  push    rsi
0x180001594  push    rdi
0x180001595  sub     rsp, 0F0h
0x18000159c  mov     edi, edx
0x18000159e  mov     rsi, rcx
0x1800015a1  mov     ebx, 1
0x1800015a6  cmp     edx, ebx
0x1800015a8  ja      short loc_1800015B0
0x1800015aa  mov     cs:__native_dllmain_reason, edx
0x1800015b0  test    edx, edx
0x1800015b2  jnz     short loc_1800015C7
0x1800015b4  cmp     cs:dword_18001D340, edx
0x1800015ba  jnz     short loc_1800015C7
0x1800015bc  xor     ebx, ebx
0x1800015be  mov     [rsp+108h+var_E8], ebx
0x1800015c2  jmp     loc_180001774
0x1800015c7  lea     eax, [rdx-1]
0x1800015ca  cmp     eax, 1
0x1800015cd  ja      loc_180001654
0x1800015d3  mov     rax, cs:_pRawDllMain
0x1800015da  test    rax, rax
0x1800015dd  jz      short loc_180001615
0x1800015df  cmp     edx, 1
0x1800015e2  jnz     short loc_1800015EA
0x1800015e4  mov     cs:dword_18001D344, edx
0x1800015ea  mov     r8, [rsp+108h+lpvReserved]
0x1800015f2  call    cs:__guard_dispatch_icall_fptr
0x1800015f8  mov     ebx, eax
0x1800015fa  mov     [rsp+108h+var_E8], eax
0x1800015fe  jmp     short loc_180001615
0x180001600  xor     ebx, ebx
0x180001602  mov     [rsp+108h+var_E8], ebx
0x180001606  mov     edi, [rsp+108h+arg_8]
0x18000160d  mov     rsi, [rsp+108h+arg_0]
0x180001615  test    ebx, ebx
0x180001617  jz      loc_180001774
0x18000161d  mov     r8, [rsp+108h+lpvReserved]
0x180001625  mov     edx, edi
0x180001627  mov     rcx, rsi
0x18000162a  call    _CRT_INIT
0x18000162f  mov     ebx, eax
0x180001631  mov     [rsp+108h+var_E8], eax
0x180001635  jmp     short loc_18000164C
0x180001637  xor     ebx, ebx
0x180001639  mov     [rsp+108h+var_E8], ebx
0x18000163d  mov     edi, [rsp+108h+arg_8]
0x180001644  mov     rsi, [rsp+108h+arg_0]
0x18000164c  test    ebx, ebx
0x18000164e  jz      loc_180001774
0x180001654  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000165c  mov     edx, edi; fdwReason
0x18000165e  mov     rcx, rsi; hinstDLL
0x180001661  call    DllMain
0x180001666  mov     ebx, eax
0x180001668  mov     [rsp+108h+var_E8], eax
0x18000166c  jmp     short loc_180001683
0x18000166e  xor     ebx, ebx
0x180001670  mov     [rsp+108h+var_E8], ebx
0x180001674  mov     edi, [rsp+108h+arg_8]
0x18000167b  mov     rsi, [rsp+108h+arg_0]
0x180001683  cmp     edi, 1
0x180001686  jnz     short loc_1800016FF
0x180001688  test    ebx, ebx
0x18000168a  jnz     short loc_1800016FF
0x18000168c  xor     r8d, r8d; lpvReserved
0x18000168f  xor     edx, edx; fdwReason
0x180001691  mov     rcx, rsi; hinstDLL
0x180001694  call    DllMain
0x180001699  jmp     short loc_1800016AE
0x18000169b  mov     edi, [rsp+108h+arg_8]
0x1800016a2  mov     rsi, [rsp+108h+arg_0]
0x1800016aa  mov     ebx, [rsp+108h+var_E8]
0x1800016ae  xor     r8d, r8d
0x1800016b1  xor     edx, edx
0x1800016b3  mov     rcx, rsi
0x1800016b6  call    _CRT_INIT
0x1800016bb  jmp     short loc_1800016D0
0x1800016bd  mov     edi, [rsp+108h+arg_8]
0x1800016c4  mov     rsi, [rsp+108h+arg_0]
0x1800016cc  mov     ebx, [rsp+108h+var_E8]
0x1800016d0  mov     rax, cs:_pRawDllMain
0x1800016d7  test    rax, rax
0x1800016da  jz      short loc_1800016FF
0x1800016dc  xor     r8d, r8d
0x1800016df  xor     edx, edx
0x1800016e1  mov     rcx, rsi
0x1800016e4  call    cs:__guard_dispatch_icall_fptr
0x1800016ea  jmp     short loc_1800016FF
0x1800016ec  mov     edi, [rsp+108h+arg_8]
0x1800016f3  mov     rsi, [rsp+108h+arg_0]
0x1800016fb  mov     ebx, [rsp+108h+var_E8]
0x1800016ff  test    edi, edi
0x180001701  jz      short loc_180001708
0x180001703  cmp     edi, 3
0x180001706  jnz     short loc_180001774
0x180001708  mov     r8, [rsp+108h+lpvReserved]
0x180001710  mov     edx, edi
0x180001712  mov     rcx, rsi
0x180001715  call    _CRT_INIT
0x18000171a  mov     ebx, eax
0x18000171c  mov     [rsp+108h+var_E8], eax
0x180001720  jmp     short loc_180001737
0x180001722  xor     ebx, ebx
0x180001724  mov     [rsp+108h+var_E8], ebx
0x180001728  mov     edi, [rsp+108h+arg_8]
0x18000172f  mov     rsi, [rsp+108h+arg_0]
0x180001737  mov     rax, cs:_pRawDllMain
0x18000173e  test    rax, rax
0x180001741  jz      short loc_180001774
0x180001743  cmp     cs:dword_18001D344, 0
0x18000174a  jz      short loc_180001774
0x18000174c  mov     r8, [rsp+108h+lpvReserved]
0x180001754  mov     edx, edi
0x180001756  mov     rcx, rsi
0x180001759  call    cs:__guard_dispatch_icall_fptr
0x18000175f  mov     ebx, eax
0x180001761  mov     [rsp+108h+var_E8], eax
0x180001765  jmp     short loc_180001774
0x180001767  xor     ebx, ebx
0x180001769  mov     [rsp+108h+var_E8], ebx
0x18000176d  mov     edi, [rsp+108h+arg_8]
0x180001774  cmp     edi, 1
0x180001777  ja      short loc_180001783
0x180001779  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001783  mov     eax, ebx
0x180001785  add     rsp, 0F0h
0x18000178c  pop     rdi
0x18000178d  pop     rsi
0x18000178e  pop     rbx
0x18000178f  retn
0x180014f13  push    rbp
0x180014f15  sub     rsp, 20h
0x180014f19  mov     rbp, rdx
0x180014f1c  mov     rax, [rcx]
0x180014f1f  mov     edx, [rax]
0x180014f21  mov     [rbp+0A8h], rcx
0x180014f28  mov     [rbp+28h], edx
0x180014f2b  mov     eax, [rbp+28h]
0x180014f2e  cmp     eax, 0E06D7363h
0x180014f33  jnz     short loc_180014F49
0x180014f35  mov     rdx, [rbp+0A8h]
0x180014f3c  mov     ecx, [rbp+28h]
0x180014f3f  call    _XcptFilter_0
0x180014f44  mov     [rbp+30h], eax
0x180014f47  jmp     short loc_180014F50
0x180014f49  mov     dword ptr [rbp+30h], 0
0x180014f50  mov     eax, [rbp+30h]
0x180014f53  add     rsp, 20h
0x180014f57  pop     rbp
0x180014f58  retn
0x180014f5a  push    rbp
0x180014f5c  sub     rsp, 20h
0x180014f60  mov     rbp, rdx
0x180014f63  mov     rax, [rcx]
0x180014f66  mov     edx, [rax]
0x180014f68  mov     [rbp+0B0h], rcx
0x180014f6f  mov     [rbp+38h], edx
0x180014f72  mov     eax, [rbp+38h]
0x180014f75  cmp     eax, 0E06D7363h
0x180014f7a  jnz     short loc_180014F90
0x180014f7c  mov     rdx, [rbp+0B0h]
0x180014f83  mov     ecx, [rbp+38h]
0x180014f86  call    _XcptFilter_0
0x180014f8b  mov     [rbp+40h], eax
0x180014f8e  jmp     short loc_180014F97
0x180014f90  mov     dword ptr [rbp+40h], 0
0x180014f97  mov     eax, [rbp+40h]
0x180014f9a  add     rsp, 20h
0x180014f9e  pop     rbp
0x180014f9f  retn
0x180014fa1  push    rbp
0x180014fa3  sub     rsp, 20h
0x180014fa7  mov     rbp, rdx
0x180014faa  mov     rax, [rcx]
0x180014fad  mov     edx, [rax]
0x180014faf  mov     [rbp+0B8h], rcx
0x180014fb6  mov     [rbp+48h], edx
0x180014fb9  mov     eax, [rbp+48h]
0x180014fbc  cmp     eax, 0E06D7363h
0x180014fc1  jnz     short loc_180014FD7
0x180014fc3  mov     rdx, [rbp+0B8h]
0x180014fca  mov     ecx, [rbp+48h]
0x180014fcd  call    _XcptFilter_0
0x180014fd2  mov     [rbp+50h], eax
0x180014fd5  jmp     short loc_180014FDE
0x180014fd7  mov     dword ptr [rbp+50h], 0
0x180014fde  mov     eax, [rbp+50h]
0x180014fe1  add     rsp, 20h
0x180014fe5  pop     rbp
0x180014fe6  retn
0x180014fe8  push    rbp
0x180014fea  sub     rsp, 20h
0x180014fee  mov     rbp, rdx
0x180014ff1  mov     rax, [rcx]
0x180014ff4  mov     edx, [rax]
0x180014ff6  mov     [rbp+0C0h], rcx
0x180014ffd  mov     [rbp+58h], edx
0x180015000  mov     eax, [rbp+58h]
0x180015003  cmp     eax, 0E06D7363h
0x180015008  jnz     short loc_18001501E
0x18001500a  mov     rdx, [rbp+0C0h]
0x180015011  mov     ecx, [rbp+58h]
0x180015014  call    _XcptFilter_0
0x180015019  mov     [rbp+60h], eax
0x18001501c  jmp     short loc_180015025
0x18001501e  mov     dword ptr [rbp+60h], 0
0x180015025  mov     eax, [rbp+60h]
0x180015028  add     rsp, 20h
0x18001502c  pop     rbp
0x18001502d  retn
0x18001502f  push    rbp
0x180015031  sub     rsp, 20h
0x180015035  mov     rbp, rdx
0x180015038  mov     rax, [rcx]
0x18001503b  mov     edx, [rax]
0x18001503d  mov     [rbp+0C8h], rcx
0x180015044  mov     [rbp+68h], edx
0x180015047  mov     eax, [rbp+68h]
0x18001504a  cmp     eax, 0E06D7363h
0x18001504f  jnz     short loc_180015065
0x180015051  mov     rdx, [rbp+0C8h]
0x180015058  mov     ecx, [rbp+68h]
0x18001505b  call    _XcptFilter_0
0x180015060  mov     [rbp+70h], eax
0x180015063  jmp     short loc_18001506C
0x180015065  mov     dword ptr [rbp+70h], 0
0x18001506c  mov     eax, [rbp+70h]
0x18001506f  add     rsp, 20h
0x180015073  pop     rbp
0x180015074  retn
0x180015076  push    rbp
0x180015078  sub     rsp, 20h
0x18001507c  mov     rbp, rdx
0x18001507f  mov     rax, [rcx]
0x180015082  mov     edx, [rax]
0x180015084  mov     [rbp+0D0h], rcx
0x18001508b  mov     [rbp+78h], edx
0x18001508e  mov     eax, [rbp+78h]
0x180015091  cmp     eax, 0E06D7363h
0x180015096  jnz     short loc_1800150AF
0x180015098  mov     rdx, [rbp+0D0h]
0x18001509f  mov     ecx, [rbp+78h]
0x1800150a2  call    _XcptFilter_0
0x1800150a7  mov     [rbp+80h], eax
0x1800150ad  jmp     short loc_1800150B9
0x1800150af  mov     dword ptr [rbp+80h], 0
0x1800150b9  mov     eax, [rbp+80h]
0x1800150bf  add     rsp, 20h
0x1800150c3  pop     rbp
0x1800150c4  retn
0x1800150c6  push    rbp
0x1800150c8  sub     rsp, 20h
0x1800150cc  mov     rbp, rdx
0x1800150cf  mov     rax, [rcx]
0x1800150d2  mov     edx, [rax]
0x1800150d4  mov     [rbp+0D8h], rcx
0x1800150db  mov     [rbp+88h], edx
0x1800150e1  mov     eax, [rbp+88h]
0x1800150e7  cmp     eax, 0E06D7363h
0x1800150ec  jnz     short loc_180015108
0x1800150ee  mov     rdx, [rbp+0D8h]
0x1800150f5  mov     ecx, [rbp+88h]
0x1800150fb  call    _XcptFilter_0
0x180015100  mov     [rbp+90h], eax
0x180015106  jmp     short loc_180015112
0x180015108  mov     dword ptr [rbp+90h], 0
0x180015112  mov     eax, [rbp+90h]
0x180015118  add     rsp, 20h
0x18001511c  pop     rbp
0x18001511d  retn
0x18001511f  push    rbp
0x180015121  sub     rsp, 20h
0x180015125  mov     rbp, rdx
0x180015128  mov     rax, [rcx]
0x18001512b  mov     edx, [rax]
0x18001512d  mov     [rbp+0E0h], rcx
0x180015134  mov     [rbp+98h], edx
0x18001513a  mov     eax, [rbp+98h]
0x180015140  cmp     eax, 0E06D7363h
0x180015145  jnz     short loc_180015161
0x180015147  mov     rdx, [rbp+0E0h]
0x18001514e  mov     ecx, [rbp+98h]
0x180015154  call    _XcptFilter_0
0x180015159  mov     [rbp+0A0h], eax
0x18001515f  jmp     short loc_18001516B
0x180015161  mov     dword ptr [rbp+0A0h], 0
0x18001516b  mov     eax, [rbp+0A0h]
0x180015171  add     rsp, 20h
0x180015175  pop     rbp
0x180015176  retn
0x180015178  push    rbp
0x18001517a  sub     rsp, 20h
0x18001517e  mov     rbp, rdx
0x180015181  cmp     dword ptr [rbp+118h], 1
0x180015188  ja      short loc_180015194
0x18001518a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
