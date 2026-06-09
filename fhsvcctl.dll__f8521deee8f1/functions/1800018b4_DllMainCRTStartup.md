# __DllMainCRTStartup

- ea: `0x1800018b4`
- end: `0x180001ac0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x180001640`
- `0x1800018b4`
- `0x180001b17`
- `0x1800020c0`
- `0x180004f90`

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
  if ( (_DWORD)fdwReason || dword_18000A160 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000A164 = 1;
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
            if ( dword_18000A164 )
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
0x1800018b4  mov     [rsp+lpvReserved], r8
0x1800018b9  mov     [rsp+arg_8], edx
0x1800018bd  mov     [rsp+arg_0], rcx
0x1800018c2  push    rbx
0x1800018c3  push    rsi
0x1800018c4  push    rdi
0x1800018c5  sub     rsp, 0F0h
0x1800018cc  mov     edi, edx
0x1800018ce  mov     rsi, rcx
0x1800018d1  mov     ebx, 1
0x1800018d6  cmp     edx, ebx
0x1800018d8  ja      short loc_1800018E0
0x1800018da  mov     cs:__native_dllmain_reason, edx
0x1800018e0  test    edx, edx
0x1800018e2  jnz     short loc_1800018F7
0x1800018e4  cmp     cs:dword_18000A160, edx
0x1800018ea  jnz     short loc_1800018F7
0x1800018ec  xor     ebx, ebx
0x1800018ee  mov     [rsp+108h+var_E8], ebx
0x1800018f2  jmp     loc_180001AA4
0x1800018f7  lea     eax, [rdx-1]
0x1800018fa  cmp     eax, 1
0x1800018fd  ja      loc_180001984
0x180001903  mov     rax, cs:_pRawDllMain
0x18000190a  test    rax, rax
0x18000190d  jz      short loc_180001945
0x18000190f  cmp     edx, 1
0x180001912  jnz     short loc_18000191A
0x180001914  mov     cs:dword_18000A164, edx
0x18000191a  mov     r8, [rsp+108h+lpvReserved]
0x180001922  call    cs:__guard_dispatch_icall_fptr
0x180001928  mov     ebx, eax
0x18000192a  mov     [rsp+108h+var_E8], eax
0x18000192e  jmp     short loc_180001945
0x180001930  xor     ebx, ebx
0x180001932  mov     [rsp+108h+var_E8], ebx
0x180001936  mov     edi, [rsp+108h+arg_8]
0x18000193d  mov     rsi, [rsp+108h+arg_0]
0x180001945  test    ebx, ebx
0x180001947  jz      loc_180001AA4
0x18000194d  mov     r8, [rsp+108h+lpvReserved]
0x180001955  mov     edx, edi
0x180001957  mov     rcx, rsi
0x18000195a  call    _CRT_INIT
0x18000195f  mov     ebx, eax
0x180001961  mov     [rsp+108h+var_E8], eax
0x180001965  jmp     short loc_18000197C
0x180001967  xor     ebx, ebx
0x180001969  mov     [rsp+108h+var_E8], ebx
0x18000196d  mov     edi, [rsp+108h+arg_8]
0x180001974  mov     rsi, [rsp+108h+arg_0]
0x18000197c  test    ebx, ebx
0x18000197e  jz      loc_180001AA4
0x180001984  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000198c  mov     edx, edi; fdwReason
0x18000198e  mov     rcx, rsi; hinstDLL
0x180001991  call    DllMain
0x180001996  mov     ebx, eax
0x180001998  mov     [rsp+108h+var_E8], eax
0x18000199c  jmp     short loc_1800019B3
0x18000199e  xor     ebx, ebx
0x1800019a0  mov     [rsp+108h+var_E8], ebx
0x1800019a4  mov     edi, [rsp+108h+arg_8]
0x1800019ab  mov     rsi, [rsp+108h+arg_0]
0x1800019b3  cmp     edi, 1
0x1800019b6  jnz     short loc_180001A2F
0x1800019b8  test    ebx, ebx
0x1800019ba  jnz     short loc_180001A2F
0x1800019bc  xor     r8d, r8d; lpvReserved
0x1800019bf  xor     edx, edx; fdwReason
0x1800019c1  mov     rcx, rsi; hinstDLL
0x1800019c4  call    DllMain
0x1800019c9  jmp     short loc_1800019DE
0x1800019cb  mov     edi, [rsp+108h+arg_8]
0x1800019d2  mov     rsi, [rsp+108h+arg_0]
0x1800019da  mov     ebx, [rsp+108h+var_E8]
0x1800019de  xor     r8d, r8d
0x1800019e1  xor     edx, edx
0x1800019e3  mov     rcx, rsi
0x1800019e6  call    _CRT_INIT
0x1800019eb  jmp     short loc_180001A00
0x1800019ed  mov     edi, [rsp+108h+arg_8]
0x1800019f4  mov     rsi, [rsp+108h+arg_0]
0x1800019fc  mov     ebx, [rsp+108h+var_E8]
0x180001a00  mov     rax, cs:_pRawDllMain
0x180001a07  test    rax, rax
0x180001a0a  jz      short loc_180001A2F
0x180001a0c  xor     r8d, r8d
0x180001a0f  xor     edx, edx
0x180001a11  mov     rcx, rsi
0x180001a14  call    cs:__guard_dispatch_icall_fptr
0x180001a1a  jmp     short loc_180001A2F
0x180001a1c  mov     edi, [rsp+108h+arg_8]
0x180001a23  mov     rsi, [rsp+108h+arg_0]
0x180001a2b  mov     ebx, [rsp+108h+var_E8]
0x180001a2f  test    edi, edi
0x180001a31  jz      short loc_180001A38
0x180001a33  cmp     edi, 3
0x180001a36  jnz     short loc_180001AA4
0x180001a38  mov     r8, [rsp+108h+lpvReserved]
0x180001a40  mov     edx, edi
0x180001a42  mov     rcx, rsi
0x180001a45  call    _CRT_INIT
0x180001a4a  mov     ebx, eax
0x180001a4c  mov     [rsp+108h+var_E8], eax
0x180001a50  jmp     short loc_180001A67
0x180001a52  xor     ebx, ebx
0x180001a54  mov     [rsp+108h+var_E8], ebx
0x180001a58  mov     edi, [rsp+108h+arg_8]
0x180001a5f  mov     rsi, [rsp+108h+arg_0]
0x180001a67  mov     rax, cs:_pRawDllMain
0x180001a6e  test    rax, rax
0x180001a71  jz      short loc_180001AA4
0x180001a73  cmp     cs:dword_18000A164, 0
0x180001a7a  jz      short loc_180001AA4
0x180001a7c  mov     r8, [rsp+108h+lpvReserved]
0x180001a84  mov     edx, edi
0x180001a86  mov     rcx, rsi
0x180001a89  call    cs:__guard_dispatch_icall_fptr
0x180001a8f  mov     ebx, eax
0x180001a91  mov     [rsp+108h+var_E8], eax
0x180001a95  jmp     short loc_180001AA4
0x180001a97  xor     ebx, ebx
0x180001a99  mov     [rsp+108h+var_E8], ebx
0x180001a9d  mov     edi, [rsp+108h+arg_8]
0x180001aa4  cmp     edi, 1
0x180001aa7  ja      short loc_180001AB3
0x180001aa9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ab3  mov     eax, ebx
0x180001ab5  add     rsp, 0F0h
0x180001abc  pop     rdi
0x180001abd  pop     rsi
0x180001abe  pop     rbx
0x180001abf  retn
0x180004fd0  push    rbp
0x180004fd2  sub     rsp, 20h
0x180004fd6  mov     rbp, rdx
0x180004fd9  mov     rax, [rcx]
0x180004fdc  mov     edx, [rax]
0x180004fde  mov     [rbp+0A8h], rcx
0x180004fe5  mov     [rbp+28h], edx
0x180004fe8  mov     eax, [rbp+28h]
0x180004feb  cmp     eax, 0E06D7363h
0x180004ff0  jnz     short loc_180005006
0x180004ff2  mov     rdx, [rbp+0A8h]
0x180004ff9  mov     ecx, [rbp+28h]
0x180004ffc  call    _XcptFilter_0
0x180005001  mov     [rbp+30h], eax
0x180005004  jmp     short loc_18000500D
0x180005006  mov     dword ptr [rbp+30h], 0
0x18000500d  mov     eax, [rbp+30h]
0x180005010  add     rsp, 20h
0x180005014  pop     rbp
0x180005015  retn
0x180005017  push    rbp
0x180005019  sub     rsp, 20h
0x18000501d  mov     rbp, rdx
0x180005020  mov     rax, [rcx]
0x180005023  mov     edx, [rax]
0x180005025  mov     [rbp+0B0h], rcx
0x18000502c  mov     [rbp+38h], edx
0x18000502f  mov     eax, [rbp+38h]
0x180005032  cmp     eax, 0E06D7363h
0x180005037  jnz     short loc_18000504D
0x180005039  mov     rdx, [rbp+0B0h]
0x180005040  mov     ecx, [rbp+38h]
0x180005043  call    _XcptFilter_0
0x180005048  mov     [rbp+40h], eax
0x18000504b  jmp     short loc_180005054
0x18000504d  mov     dword ptr [rbp+40h], 0
0x180005054  mov     eax, [rbp+40h]
0x180005057  add     rsp, 20h
0x18000505b  pop     rbp
0x18000505c  retn
0x18000505e  push    rbp
0x180005060  sub     rsp, 20h
0x180005064  mov     rbp, rdx
0x180005067  mov     rax, [rcx]
0x18000506a  mov     edx, [rax]
0x18000506c  mov     [rbp+0B8h], rcx
0x180005073  mov     [rbp+48h], edx
0x180005076  mov     eax, [rbp+48h]
0x180005079  cmp     eax, 0E06D7363h
0x18000507e  jnz     short loc_180005094
0x180005080  mov     rdx, [rbp+0B8h]
0x180005087  mov     ecx, [rbp+48h]
0x18000508a  call    _XcptFilter_0
0x18000508f  mov     [rbp+50h], eax
0x180005092  jmp     short loc_18000509B
0x180005094  mov     dword ptr [rbp+50h], 0
0x18000509b  mov     eax, [rbp+50h]
0x18000509e  add     rsp, 20h
0x1800050a2  pop     rbp
0x1800050a3  retn
0x1800050a5  push    rbp
0x1800050a7  sub     rsp, 20h
0x1800050ab  mov     rbp, rdx
0x1800050ae  mov     rax, [rcx]
0x1800050b1  mov     edx, [rax]
0x1800050b3  mov     [rbp+0C0h], rcx
0x1800050ba  mov     [rbp+58h], edx
0x1800050bd  mov     eax, [rbp+58h]
0x1800050c0  cmp     eax, 0E06D7363h
0x1800050c5  jnz     short loc_1800050DB
0x1800050c7  mov     rdx, [rbp+0C0h]
0x1800050ce  mov     ecx, [rbp+58h]
0x1800050d1  call    _XcptFilter_0
0x1800050d6  mov     [rbp+60h], eax
0x1800050d9  jmp     short loc_1800050E2
0x1800050db  mov     dword ptr [rbp+60h], 0
0x1800050e2  mov     eax, [rbp+60h]
0x1800050e5  add     rsp, 20h
0x1800050e9  pop     rbp
0x1800050ea  retn
0x1800050ec  push    rbp
0x1800050ee  sub     rsp, 20h
0x1800050f2  mov     rbp, rdx
0x1800050f5  mov     rax, [rcx]
0x1800050f8  mov     edx, [rax]
0x1800050fa  mov     [rbp+0C8h], rcx
0x180005101  mov     [rbp+68h], edx
0x180005104  mov     eax, [rbp+68h]
0x180005107  cmp     eax, 0E06D7363h
0x18000510c  jnz     short loc_180005122
0x18000510e  mov     rdx, [rbp+0C8h]
0x180005115  mov     ecx, [rbp+68h]
0x180005118  call    _XcptFilter_0
0x18000511d  mov     [rbp+70h], eax
0x180005120  jmp     short loc_180005129
0x180005122  mov     dword ptr [rbp+70h], 0
0x180005129  mov     eax, [rbp+70h]
0x18000512c  add     rsp, 20h
0x180005130  pop     rbp
0x180005131  retn
0x180005133  push    rbp
0x180005135  sub     rsp, 20h
0x180005139  mov     rbp, rdx
0x18000513c  mov     rax, [rcx]
0x18000513f  mov     edx, [rax]
0x180005141  mov     [rbp+0D0h], rcx
0x180005148  mov     [rbp+78h], edx
0x18000514b  mov     eax, [rbp+78h]
0x18000514e  cmp     eax, 0E06D7363h
0x180005153  jnz     short loc_18000516C
0x180005155  mov     rdx, [rbp+0D0h]
0x18000515c  mov     ecx, [rbp+78h]
0x18000515f  call    _XcptFilter_0
0x180005164  mov     [rbp+80h], eax
0x18000516a  jmp     short loc_180005176
0x18000516c  mov     dword ptr [rbp+80h], 0
0x180005176  mov     eax, [rbp+80h]
0x18000517c  add     rsp, 20h
0x180005180  pop     rbp
0x180005181  retn
0x180005183  push    rbp
0x180005185  sub     rsp, 20h
0x180005189  mov     rbp, rdx
0x18000518c  mov     rax, [rcx]
0x18000518f  mov     edx, [rax]
0x180005191  mov     [rbp+0D8h], rcx
0x180005198  mov     [rbp+88h], edx
0x18000519e  mov     eax, [rbp+88h]
0x1800051a4  cmp     eax, 0E06D7363h
0x1800051a9  jnz     short loc_1800051C5
0x1800051ab  mov     rdx, [rbp+0D8h]
0x1800051b2  mov     ecx, [rbp+88h]
0x1800051b8  call    _XcptFilter_0
0x1800051bd  mov     [rbp+90h], eax
0x1800051c3  jmp     short loc_1800051CF
0x1800051c5  mov     dword ptr [rbp+90h], 0
0x1800051cf  mov     eax, [rbp+90h]
0x1800051d5  add     rsp, 20h
0x1800051d9  pop     rbp
0x1800051da  retn
0x1800051dc  push    rbp
0x1800051de  sub     rsp, 20h
0x1800051e2  mov     rbp, rdx
0x1800051e5  mov     rax, [rcx]
0x1800051e8  mov     edx, [rax]
0x1800051ea  mov     [rbp+0E0h], rcx
0x1800051f1  mov     [rbp+98h], edx
0x1800051f7  mov     eax, [rbp+98h]
0x1800051fd  cmp     eax, 0E06D7363h
0x180005202  jnz     short loc_18000521E
0x180005204  mov     rdx, [rbp+0E0h]
0x18000520b  mov     ecx, [rbp+98h]
0x180005211  call    _XcptFilter_0
0x180005216  mov     [rbp+0A0h], eax
0x18000521c  jmp     short loc_180005228
0x18000521e  mov     dword ptr [rbp+0A0h], 0
0x180005228  mov     eax, [rbp+0A0h]
0x18000522e  add     rsp, 20h
0x180005232  pop     rbp
0x180005233  retn
0x180005235  push    rbp
0x180005237  sub     rsp, 20h
0x18000523b  mov     rbp, rdx
0x18000523e  cmp     dword ptr [rbp+118h], 1
0x180005245  ja      short loc_180005251
0x180005247  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
