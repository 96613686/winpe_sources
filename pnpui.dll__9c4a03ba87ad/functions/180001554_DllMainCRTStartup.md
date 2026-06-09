# __DllMainCRTStartup

- ea: `0x180001554`
- end: `0x180001760`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001510`

## callees

- `0x1800012e0`
- `0x180001554`
- `0x180001870`
- `0x18000c598`
- `0x18000cd50`

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
  if ( (_DWORD)fdwReason || dword_1800142C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800142C4 = 1;
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
            if ( dword_1800142C4 )
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
0x180001554  mov     [rsp+lpvReserved], r8
0x180001559  mov     [rsp+arg_8], edx
0x18000155d  mov     [rsp+arg_0], rcx
0x180001562  push    rbx
0x180001563  push    rsi
0x180001564  push    rdi
0x180001565  sub     rsp, 0F0h
0x18000156c  mov     edi, edx
0x18000156e  mov     rsi, rcx
0x180001571  mov     ebx, 1
0x180001576  cmp     edx, ebx
0x180001578  ja      short loc_180001580
0x18000157a  mov     cs:__native_dllmain_reason, edx
0x180001580  test    edx, edx
0x180001582  jnz     short loc_180001597
0x180001584  cmp     cs:dword_1800142C0, edx
0x18000158a  jnz     short loc_180001597
0x18000158c  xor     ebx, ebx
0x18000158e  mov     [rsp+108h+var_E8], ebx
0x180001592  jmp     loc_180001744
0x180001597  lea     eax, [rdx-1]
0x18000159a  cmp     eax, 1
0x18000159d  ja      loc_180001624
0x1800015a3  mov     rax, cs:_pRawDllMain
0x1800015aa  test    rax, rax
0x1800015ad  jz      short loc_1800015E5
0x1800015af  cmp     edx, 1
0x1800015b2  jnz     short loc_1800015BA
0x1800015b4  mov     cs:dword_1800142C4, edx
0x1800015ba  mov     r8, [rsp+108h+lpvReserved]
0x1800015c2  call    cs:__guard_dispatch_icall_fptr
0x1800015c8  mov     ebx, eax
0x1800015ca  mov     [rsp+108h+var_E8], eax
0x1800015ce  jmp     short loc_1800015E5
0x1800015d0  xor     ebx, ebx
0x1800015d2  mov     [rsp+108h+var_E8], ebx
0x1800015d6  mov     edi, [rsp+108h+arg_8]
0x1800015dd  mov     rsi, [rsp+108h+arg_0]
0x1800015e5  test    ebx, ebx
0x1800015e7  jz      loc_180001744
0x1800015ed  mov     r8, [rsp+108h+lpvReserved]
0x1800015f5  mov     edx, edi
0x1800015f7  mov     rcx, rsi
0x1800015fa  call    _CRT_INIT
0x1800015ff  mov     ebx, eax
0x180001601  mov     [rsp+108h+var_E8], eax
0x180001605  jmp     short loc_18000161C
0x180001607  xor     ebx, ebx
0x180001609  mov     [rsp+108h+var_E8], ebx
0x18000160d  mov     edi, [rsp+108h+arg_8]
0x180001614  mov     rsi, [rsp+108h+arg_0]
0x18000161c  test    ebx, ebx
0x18000161e  jz      loc_180001744
0x180001624  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000162c  mov     edx, edi; fdwReason
0x18000162e  mov     rcx, rsi; hinstDLL
0x180001631  call    DllMain
0x180001636  mov     ebx, eax
0x180001638  mov     [rsp+108h+var_E8], eax
0x18000163c  jmp     short loc_180001653
0x18000163e  xor     ebx, ebx
0x180001640  mov     [rsp+108h+var_E8], ebx
0x180001644  mov     edi, [rsp+108h+arg_8]
0x18000164b  mov     rsi, [rsp+108h+arg_0]
0x180001653  cmp     edi, 1
0x180001656  jnz     short loc_1800016CF
0x180001658  test    ebx, ebx
0x18000165a  jnz     short loc_1800016CF
0x18000165c  xor     r8d, r8d; lpvReserved
0x18000165f  xor     edx, edx; fdwReason
0x180001661  mov     rcx, rsi; hinstDLL
0x180001664  call    DllMain
0x180001669  jmp     short loc_18000167E
0x18000166b  mov     edi, [rsp+108h+arg_8]
0x180001672  mov     rsi, [rsp+108h+arg_0]
0x18000167a  mov     ebx, [rsp+108h+var_E8]
0x18000167e  xor     r8d, r8d
0x180001681  xor     edx, edx
0x180001683  mov     rcx, rsi
0x180001686  call    _CRT_INIT
0x18000168b  jmp     short loc_1800016A0
0x18000168d  mov     edi, [rsp+108h+arg_8]
0x180001694  mov     rsi, [rsp+108h+arg_0]
0x18000169c  mov     ebx, [rsp+108h+var_E8]
0x1800016a0  mov     rax, cs:_pRawDllMain
0x1800016a7  test    rax, rax
0x1800016aa  jz      short loc_1800016CF
0x1800016ac  xor     r8d, r8d
0x1800016af  xor     edx, edx
0x1800016b1  mov     rcx, rsi
0x1800016b4  call    cs:__guard_dispatch_icall_fptr
0x1800016ba  jmp     short loc_1800016CF
0x1800016bc  mov     edi, [rsp+108h+arg_8]
0x1800016c3  mov     rsi, [rsp+108h+arg_0]
0x1800016cb  mov     ebx, [rsp+108h+var_E8]
0x1800016cf  test    edi, edi
0x1800016d1  jz      short loc_1800016D8
0x1800016d3  cmp     edi, 3
0x1800016d6  jnz     short loc_180001744
0x1800016d8  mov     r8, [rsp+108h+lpvReserved]
0x1800016e0  mov     edx, edi
0x1800016e2  mov     rcx, rsi
0x1800016e5  call    _CRT_INIT
0x1800016ea  mov     ebx, eax
0x1800016ec  mov     [rsp+108h+var_E8], eax
0x1800016f0  jmp     short loc_180001707
0x1800016f2  xor     ebx, ebx
0x1800016f4  mov     [rsp+108h+var_E8], ebx
0x1800016f8  mov     edi, [rsp+108h+arg_8]
0x1800016ff  mov     rsi, [rsp+108h+arg_0]
0x180001707  mov     rax, cs:_pRawDllMain
0x18000170e  test    rax, rax
0x180001711  jz      short loc_180001744
0x180001713  cmp     cs:dword_1800142C4, 0
0x18000171a  jz      short loc_180001744
0x18000171c  mov     r8, [rsp+108h+lpvReserved]
0x180001724  mov     edx, edi
0x180001726  mov     rcx, rsi
0x180001729  call    cs:__guard_dispatch_icall_fptr
0x18000172f  mov     ebx, eax
0x180001731  mov     [rsp+108h+var_E8], eax
0x180001735  jmp     short loc_180001744
0x180001737  xor     ebx, ebx
0x180001739  mov     [rsp+108h+var_E8], ebx
0x18000173d  mov     edi, [rsp+108h+arg_8]
0x180001744  cmp     edi, 1
0x180001747  ja      short loc_180001753
0x180001749  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001753  mov     eax, ebx
0x180001755  add     rsp, 0F0h
0x18000175c  pop     rdi
0x18000175d  pop     rsi
0x18000175e  pop     rbx
0x18000175f  retn
0x18000ce20  push    rbp
0x18000ce22  sub     rsp, 20h
0x18000ce26  mov     rbp, rdx
0x18000ce29  mov     rax, [rcx]
0x18000ce2c  mov     edx, [rax]
0x18000ce2e  mov     [rbp+0A8h], rcx
0x18000ce35  mov     [rbp+28h], edx
0x18000ce38  mov     eax, [rbp+28h]
0x18000ce3b  cmp     eax, 0E06D7363h
0x18000ce40  jnz     short loc_18000CE56
0x18000ce42  mov     rdx, [rbp+0A8h]
0x18000ce49  mov     ecx, [rbp+28h]
0x18000ce4c  call    _XcptFilter_0
0x18000ce51  mov     [rbp+30h], eax
0x18000ce54  jmp     short loc_18000CE5D
0x18000ce56  mov     dword ptr [rbp+30h], 0
0x18000ce5d  mov     eax, [rbp+30h]
0x18000ce60  add     rsp, 20h
0x18000ce64  pop     rbp
0x18000ce65  retn
0x18000ce67  push    rbp
0x18000ce69  sub     rsp, 20h
0x18000ce6d  mov     rbp, rdx
0x18000ce70  mov     rax, [rcx]
0x18000ce73  mov     edx, [rax]
0x18000ce75  mov     [rbp+0B0h], rcx
0x18000ce7c  mov     [rbp+38h], edx
0x18000ce7f  mov     eax, [rbp+38h]
0x18000ce82  cmp     eax, 0E06D7363h
0x18000ce87  jnz     short loc_18000CE9D
0x18000ce89  mov     rdx, [rbp+0B0h]
0x18000ce90  mov     ecx, [rbp+38h]
0x18000ce93  call    _XcptFilter_0
0x18000ce98  mov     [rbp+40h], eax
0x18000ce9b  jmp     short loc_18000CEA4
0x18000ce9d  mov     dword ptr [rbp+40h], 0
0x18000cea4  mov     eax, [rbp+40h]
0x18000cea7  add     rsp, 20h
0x18000ceab  pop     rbp
0x18000ceac  retn
0x18000ceae  push    rbp
0x18000ceb0  sub     rsp, 20h
0x18000ceb4  mov     rbp, rdx
0x18000ceb7  mov     rax, [rcx]
0x18000ceba  mov     edx, [rax]
0x18000cebc  mov     [rbp+0B8h], rcx
0x18000cec3  mov     [rbp+48h], edx
0x18000cec6  mov     eax, [rbp+48h]
0x18000cec9  cmp     eax, 0E06D7363h
0x18000cece  jnz     short loc_18000CEE4
0x18000ced0  mov     rdx, [rbp+0B8h]
0x18000ced7  mov     ecx, [rbp+48h]
0x18000ceda  call    _XcptFilter_0
0x18000cedf  mov     [rbp+50h], eax
0x18000cee2  jmp     short loc_18000CEEB
0x18000cee4  mov     dword ptr [rbp+50h], 0
0x18000ceeb  mov     eax, [rbp+50h]
0x18000ceee  add     rsp, 20h
0x18000cef2  pop     rbp
0x18000cef3  retn
0x18000cef5  push    rbp
0x18000cef7  sub     rsp, 20h
0x18000cefb  mov     rbp, rdx
0x18000cefe  mov     rax, [rcx]
0x18000cf01  mov     edx, [rax]
0x18000cf03  mov     [rbp+0C0h], rcx
0x18000cf0a  mov     [rbp+58h], edx
0x18000cf0d  mov     eax, [rbp+58h]
0x18000cf10  cmp     eax, 0E06D7363h
0x18000cf15  jnz     short loc_18000CF2B
0x18000cf17  mov     rdx, [rbp+0C0h]
0x18000cf1e  mov     ecx, [rbp+58h]
0x18000cf21  call    _XcptFilter_0
0x18000cf26  mov     [rbp+60h], eax
0x18000cf29  jmp     short loc_18000CF32
0x18000cf2b  mov     dword ptr [rbp+60h], 0
0x18000cf32  mov     eax, [rbp+60h]
0x18000cf35  add     rsp, 20h
0x18000cf39  pop     rbp
0x18000cf3a  retn
0x18000cf3c  push    rbp
0x18000cf3e  sub     rsp, 20h
0x18000cf42  mov     rbp, rdx
0x18000cf45  mov     rax, [rcx]
0x18000cf48  mov     edx, [rax]
0x18000cf4a  mov     [rbp+0C8h], rcx
0x18000cf51  mov     [rbp+68h], edx
0x18000cf54  mov     eax, [rbp+68h]
0x18000cf57  cmp     eax, 0E06D7363h
0x18000cf5c  jnz     short loc_18000CF72
0x18000cf5e  mov     rdx, [rbp+0C8h]
0x18000cf65  mov     ecx, [rbp+68h]
0x18000cf68  call    _XcptFilter_0
0x18000cf6d  mov     [rbp+70h], eax
0x18000cf70  jmp     short loc_18000CF79
0x18000cf72  mov     dword ptr [rbp+70h], 0
0x18000cf79  mov     eax, [rbp+70h]
0x18000cf7c  add     rsp, 20h
0x18000cf80  pop     rbp
0x18000cf81  retn
0x18000cf83  push    rbp
0x18000cf85  sub     rsp, 20h
0x18000cf89  mov     rbp, rdx
0x18000cf8c  mov     rax, [rcx]
0x18000cf8f  mov     edx, [rax]
0x18000cf91  mov     [rbp+0D0h], rcx
0x18000cf98  mov     [rbp+78h], edx
0x18000cf9b  mov     eax, [rbp+78h]
0x18000cf9e  cmp     eax, 0E06D7363h
0x18000cfa3  jnz     short loc_18000CFBC
0x18000cfa5  mov     rdx, [rbp+0D0h]
0x18000cfac  mov     ecx, [rbp+78h]
0x18000cfaf  call    _XcptFilter_0
0x18000cfb4  mov     [rbp+80h], eax
0x18000cfba  jmp     short loc_18000CFC6
0x18000cfbc  mov     dword ptr [rbp+80h], 0
0x18000cfc6  mov     eax, [rbp+80h]
0x18000cfcc  add     rsp, 20h
0x18000cfd0  pop     rbp
0x18000cfd1  retn
0x18000cfd3  push    rbp
0x18000cfd5  sub     rsp, 20h
0x18000cfd9  mov     rbp, rdx
0x18000cfdc  mov     rax, [rcx]
0x18000cfdf  mov     edx, [rax]
0x18000cfe1  mov     [rbp+0D8h], rcx
0x18000cfe8  mov     [rbp+88h], edx
0x18000cfee  mov     eax, [rbp+88h]
0x18000cff4  cmp     eax, 0E06D7363h
0x18000cff9  jnz     short loc_18000D015
0x18000cffb  mov     rdx, [rbp+0D8h]
0x18000d002  mov     ecx, [rbp+88h]
0x18000d008  call    _XcptFilter_0
0x18000d00d  mov     [rbp+90h], eax
0x18000d013  jmp     short loc_18000D01F
0x18000d015  mov     dword ptr [rbp+90h], 0
0x18000d01f  mov     eax, [rbp+90h]
0x18000d025  add     rsp, 20h
0x18000d029  pop     rbp
0x18000d02a  retn
0x18000d02c  push    rbp
0x18000d02e  sub     rsp, 20h
0x18000d032  mov     rbp, rdx
0x18000d035  mov     rax, [rcx]
0x18000d038  mov     edx, [rax]
0x18000d03a  mov     [rbp+0E0h], rcx
0x18000d041  mov     [rbp+98h], edx
0x18000d047  mov     eax, [rbp+98h]
0x18000d04d  cmp     eax, 0E06D7363h
0x18000d052  jnz     short loc_18000D06E
0x18000d054  mov     rdx, [rbp+0E0h]
0x18000d05b  mov     ecx, [rbp+98h]
0x18000d061  call    _XcptFilter_0
0x18000d066  mov     [rbp+0A0h], eax
0x18000d06c  jmp     short loc_18000D078
0x18000d06e  mov     dword ptr [rbp+0A0h], 0
0x18000d078  mov     eax, [rbp+0A0h]
0x18000d07e  add     rsp, 20h
0x18000d082  pop     rbp
0x18000d083  retn
0x18000d085  push    rbp
0x18000d087  sub     rsp, 20h
0x18000d08b  mov     rbp, rdx
0x18000d08e  cmp     dword ptr [rbp+118h], 1
0x18000d095  ja      short loc_18000D0A1
0x18000d097  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
