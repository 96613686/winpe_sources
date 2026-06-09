# __DllMainCRTStartup

- ea: `0x180005764`
- end: `0x180005970`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005720`

## callees

- `0x1800054f0`
- `0x180005764`
- `0x18000599a`
- `0x180005b78`
- `0x180005fd0`

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
  if ( (_DWORD)fdwReason || dword_18000F0C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F0C4 = 1;
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
            if ( dword_18000F0C4 )
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
0x180005764  mov     [rsp+lpvReserved], r8
0x180005769  mov     [rsp+arg_8], edx
0x18000576d  mov     [rsp+arg_0], rcx
0x180005772  push    rbx
0x180005773  push    rsi
0x180005774  push    rdi
0x180005775  sub     rsp, 0F0h
0x18000577c  mov     edi, edx
0x18000577e  mov     rsi, rcx
0x180005781  mov     ebx, 1
0x180005786  cmp     edx, ebx
0x180005788  ja      short loc_180005790
0x18000578a  mov     cs:__native_dllmain_reason, edx
0x180005790  test    edx, edx
0x180005792  jnz     short loc_1800057A7
0x180005794  cmp     cs:dword_18000F0C0, edx
0x18000579a  jnz     short loc_1800057A7
0x18000579c  xor     ebx, ebx
0x18000579e  mov     [rsp+108h+var_E8], ebx
0x1800057a2  jmp     loc_180005954
0x1800057a7  lea     eax, [rdx-1]
0x1800057aa  cmp     eax, 1
0x1800057ad  ja      loc_180005834
0x1800057b3  mov     rax, cs:_pRawDllMain
0x1800057ba  test    rax, rax
0x1800057bd  jz      short loc_1800057F5
0x1800057bf  cmp     edx, 1
0x1800057c2  jnz     short loc_1800057CA
0x1800057c4  mov     cs:dword_18000F0C4, edx
0x1800057ca  mov     r8, [rsp+108h+lpvReserved]
0x1800057d2  call    cs:__guard_dispatch_icall_fptr
0x1800057d8  mov     ebx, eax
0x1800057da  mov     [rsp+108h+var_E8], eax
0x1800057de  jmp     short loc_1800057F5
0x1800057e0  xor     ebx, ebx
0x1800057e2  mov     [rsp+108h+var_E8], ebx
0x1800057e6  mov     edi, [rsp+108h+arg_8]
0x1800057ed  mov     rsi, [rsp+108h+arg_0]
0x1800057f5  test    ebx, ebx
0x1800057f7  jz      loc_180005954
0x1800057fd  mov     r8, [rsp+108h+lpvReserved]
0x180005805  mov     edx, edi
0x180005807  mov     rcx, rsi
0x18000580a  call    _CRT_INIT
0x18000580f  mov     ebx, eax
0x180005811  mov     [rsp+108h+var_E8], eax
0x180005815  jmp     short loc_18000582C
0x180005817  xor     ebx, ebx
0x180005819  mov     [rsp+108h+var_E8], ebx
0x18000581d  mov     edi, [rsp+108h+arg_8]
0x180005824  mov     rsi, [rsp+108h+arg_0]
0x18000582c  test    ebx, ebx
0x18000582e  jz      loc_180005954
0x180005834  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000583c  mov     edx, edi; fdwReason
0x18000583e  mov     rcx, rsi; hinstDLL
0x180005841  call    DllMain
0x180005846  mov     ebx, eax
0x180005848  mov     [rsp+108h+var_E8], eax
0x18000584c  jmp     short loc_180005863
0x18000584e  xor     ebx, ebx
0x180005850  mov     [rsp+108h+var_E8], ebx
0x180005854  mov     edi, [rsp+108h+arg_8]
0x18000585b  mov     rsi, [rsp+108h+arg_0]
0x180005863  cmp     edi, 1
0x180005866  jnz     short loc_1800058DF
0x180005868  test    ebx, ebx
0x18000586a  jnz     short loc_1800058DF
0x18000586c  xor     r8d, r8d; lpvReserved
0x18000586f  xor     edx, edx; fdwReason
0x180005871  mov     rcx, rsi; hinstDLL
0x180005874  call    DllMain
0x180005879  jmp     short loc_18000588E
0x18000587b  mov     edi, [rsp+108h+arg_8]
0x180005882  mov     rsi, [rsp+108h+arg_0]
0x18000588a  mov     ebx, [rsp+108h+var_E8]
0x18000588e  xor     r8d, r8d
0x180005891  xor     edx, edx
0x180005893  mov     rcx, rsi
0x180005896  call    _CRT_INIT
0x18000589b  jmp     short loc_1800058B0
0x18000589d  mov     edi, [rsp+108h+arg_8]
0x1800058a4  mov     rsi, [rsp+108h+arg_0]
0x1800058ac  mov     ebx, [rsp+108h+var_E8]
0x1800058b0  mov     rax, cs:_pRawDllMain
0x1800058b7  test    rax, rax
0x1800058ba  jz      short loc_1800058DF
0x1800058bc  xor     r8d, r8d
0x1800058bf  xor     edx, edx
0x1800058c1  mov     rcx, rsi
0x1800058c4  call    cs:__guard_dispatch_icall_fptr
0x1800058ca  jmp     short loc_1800058DF
0x1800058cc  mov     edi, [rsp+108h+arg_8]
0x1800058d3  mov     rsi, [rsp+108h+arg_0]
0x1800058db  mov     ebx, [rsp+108h+var_E8]
0x1800058df  test    edi, edi
0x1800058e1  jz      short loc_1800058E8
0x1800058e3  cmp     edi, 3
0x1800058e6  jnz     short loc_180005954
0x1800058e8  mov     r8, [rsp+108h+lpvReserved]
0x1800058f0  mov     edx, edi
0x1800058f2  mov     rcx, rsi
0x1800058f5  call    _CRT_INIT
0x1800058fa  mov     ebx, eax
0x1800058fc  mov     [rsp+108h+var_E8], eax
0x180005900  jmp     short loc_180005917
0x180005902  xor     ebx, ebx
0x180005904  mov     [rsp+108h+var_E8], ebx
0x180005908  mov     edi, [rsp+108h+arg_8]
0x18000590f  mov     rsi, [rsp+108h+arg_0]
0x180005917  mov     rax, cs:_pRawDllMain
0x18000591e  test    rax, rax
0x180005921  jz      short loc_180005954
0x180005923  cmp     cs:dword_18000F0C4, 0
0x18000592a  jz      short loc_180005954
0x18000592c  mov     r8, [rsp+108h+lpvReserved]
0x180005934  mov     edx, edi
0x180005936  mov     rcx, rsi
0x180005939  call    cs:__guard_dispatch_icall_fptr
0x18000593f  mov     ebx, eax
0x180005941  mov     [rsp+108h+var_E8], eax
0x180005945  jmp     short loc_180005954
0x180005947  xor     ebx, ebx
0x180005949  mov     [rsp+108h+var_E8], ebx
0x18000594d  mov     edi, [rsp+108h+arg_8]
0x180005954  cmp     edi, 1
0x180005957  ja      short loc_180005963
0x180005959  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180005963  mov     eax, ebx
0x180005965  add     rsp, 0F0h
0x18000596c  pop     rdi
0x18000596d  pop     rsi
0x18000596e  pop     rbx
0x18000596f  retn
0x1800060a0  push    rbp
0x1800060a2  sub     rsp, 20h
0x1800060a6  mov     rbp, rdx
0x1800060a9  mov     rax, [rcx]
0x1800060ac  mov     edx, [rax]
0x1800060ae  mov     [rbp+0A8h], rcx
0x1800060b5  mov     [rbp+28h], edx
0x1800060b8  mov     eax, [rbp+28h]
0x1800060bb  cmp     eax, 0E06D7363h
0x1800060c0  jnz     short loc_1800060D6
0x1800060c2  mov     rdx, [rbp+0A8h]
0x1800060c9  mov     ecx, [rbp+28h]
0x1800060cc  call    _XcptFilter_0
0x1800060d1  mov     [rbp+30h], eax
0x1800060d4  jmp     short loc_1800060DD
0x1800060d6  mov     dword ptr [rbp+30h], 0
0x1800060dd  mov     eax, [rbp+30h]
0x1800060e0  add     rsp, 20h
0x1800060e4  pop     rbp
0x1800060e5  retn
0x1800060e7  push    rbp
0x1800060e9  sub     rsp, 20h
0x1800060ed  mov     rbp, rdx
0x1800060f0  mov     rax, [rcx]
0x1800060f3  mov     edx, [rax]
0x1800060f5  mov     [rbp+0B0h], rcx
0x1800060fc  mov     [rbp+38h], edx
0x1800060ff  mov     eax, [rbp+38h]
0x180006102  cmp     eax, 0E06D7363h
0x180006107  jnz     short loc_18000611D
0x180006109  mov     rdx, [rbp+0B0h]
0x180006110  mov     ecx, [rbp+38h]
0x180006113  call    _XcptFilter_0
0x180006118  mov     [rbp+40h], eax
0x18000611b  jmp     short loc_180006124
0x18000611d  mov     dword ptr [rbp+40h], 0
0x180006124  mov     eax, [rbp+40h]
0x180006127  add     rsp, 20h
0x18000612b  pop     rbp
0x18000612c  retn
0x18000612e  push    rbp
0x180006130  sub     rsp, 20h
0x180006134  mov     rbp, rdx
0x180006137  mov     rax, [rcx]
0x18000613a  mov     edx, [rax]
0x18000613c  mov     [rbp+0B8h], rcx
0x180006143  mov     [rbp+48h], edx
0x180006146  mov     eax, [rbp+48h]
0x180006149  cmp     eax, 0E06D7363h
0x18000614e  jnz     short loc_180006164
0x180006150  mov     rdx, [rbp+0B8h]
0x180006157  mov     ecx, [rbp+48h]
0x18000615a  call    _XcptFilter_0
0x18000615f  mov     [rbp+50h], eax
0x180006162  jmp     short loc_18000616B
0x180006164  mov     dword ptr [rbp+50h], 0
0x18000616b  mov     eax, [rbp+50h]
0x18000616e  add     rsp, 20h
0x180006172  pop     rbp
0x180006173  retn
0x180006175  push    rbp
0x180006177  sub     rsp, 20h
0x18000617b  mov     rbp, rdx
0x18000617e  mov     rax, [rcx]
0x180006181  mov     edx, [rax]
0x180006183  mov     [rbp+0C0h], rcx
0x18000618a  mov     [rbp+58h], edx
0x18000618d  mov     eax, [rbp+58h]
0x180006190  cmp     eax, 0E06D7363h
0x180006195  jnz     short loc_1800061AB
0x180006197  mov     rdx, [rbp+0C0h]
0x18000619e  mov     ecx, [rbp+58h]
0x1800061a1  call    _XcptFilter_0
0x1800061a6  mov     [rbp+60h], eax
0x1800061a9  jmp     short loc_1800061B2
0x1800061ab  mov     dword ptr [rbp+60h], 0
0x1800061b2  mov     eax, [rbp+60h]
0x1800061b5  add     rsp, 20h
0x1800061b9  pop     rbp
0x1800061ba  retn
0x1800061bc  push    rbp
0x1800061be  sub     rsp, 20h
0x1800061c2  mov     rbp, rdx
0x1800061c5  mov     rax, [rcx]
0x1800061c8  mov     edx, [rax]
0x1800061ca  mov     [rbp+0C8h], rcx
0x1800061d1  mov     [rbp+68h], edx
0x1800061d4  mov     eax, [rbp+68h]
0x1800061d7  cmp     eax, 0E06D7363h
0x1800061dc  jnz     short loc_1800061F2
0x1800061de  mov     rdx, [rbp+0C8h]
0x1800061e5  mov     ecx, [rbp+68h]
0x1800061e8  call    _XcptFilter_0
0x1800061ed  mov     [rbp+70h], eax
0x1800061f0  jmp     short loc_1800061F9
0x1800061f2  mov     dword ptr [rbp+70h], 0
0x1800061f9  mov     eax, [rbp+70h]
0x1800061fc  add     rsp, 20h
0x180006200  pop     rbp
0x180006201  retn
0x180006203  push    rbp
0x180006205  sub     rsp, 20h
0x180006209  mov     rbp, rdx
0x18000620c  mov     rax, [rcx]
0x18000620f  mov     edx, [rax]
0x180006211  mov     [rbp+0D0h], rcx
0x180006218  mov     [rbp+78h], edx
0x18000621b  mov     eax, [rbp+78h]
0x18000621e  cmp     eax, 0E06D7363h
0x180006223  jnz     short loc_18000623C
0x180006225  mov     rdx, [rbp+0D0h]
0x18000622c  mov     ecx, [rbp+78h]
0x18000622f  call    _XcptFilter_0
0x180006234  mov     [rbp+80h], eax
0x18000623a  jmp     short loc_180006246
0x18000623c  mov     dword ptr [rbp+80h], 0
0x180006246  mov     eax, [rbp+80h]
0x18000624c  add     rsp, 20h
0x180006250  pop     rbp
0x180006251  retn
0x180006253  push    rbp
0x180006255  sub     rsp, 20h
0x180006259  mov     rbp, rdx
0x18000625c  mov     rax, [rcx]
0x18000625f  mov     edx, [rax]
0x180006261  mov     [rbp+0D8h], rcx
0x180006268  mov     [rbp+88h], edx
0x18000626e  mov     eax, [rbp+88h]
0x180006274  cmp     eax, 0E06D7363h
0x180006279  jnz     short loc_180006295
0x18000627b  mov     rdx, [rbp+0D8h]
0x180006282  mov     ecx, [rbp+88h]
0x180006288  call    _XcptFilter_0
0x18000628d  mov     [rbp+90h], eax
0x180006293  jmp     short loc_18000629F
0x180006295  mov     dword ptr [rbp+90h], 0
0x18000629f  mov     eax, [rbp+90h]
0x1800062a5  add     rsp, 20h
0x1800062a9  pop     rbp
0x1800062aa  retn
0x1800062ac  push    rbp
0x1800062ae  sub     rsp, 20h
0x1800062b2  mov     rbp, rdx
0x1800062b5  mov     rax, [rcx]
0x1800062b8  mov     edx, [rax]
0x1800062ba  mov     [rbp+0E0h], rcx
0x1800062c1  mov     [rbp+98h], edx
0x1800062c7  mov     eax, [rbp+98h]
0x1800062cd  cmp     eax, 0E06D7363h
0x1800062d2  jnz     short loc_1800062EE
0x1800062d4  mov     rdx, [rbp+0E0h]
0x1800062db  mov     ecx, [rbp+98h]
0x1800062e1  call    _XcptFilter_0
0x1800062e6  mov     [rbp+0A0h], eax
0x1800062ec  jmp     short loc_1800062F8
0x1800062ee  mov     dword ptr [rbp+0A0h], 0
0x1800062f8  mov     eax, [rbp+0A0h]
0x1800062fe  add     rsp, 20h
0x180006302  pop     rbp
0x180006303  retn
0x180006305  push    rbp
0x180006307  sub     rsp, 20h
0x18000630b  mov     rbp, rdx
0x18000630e  cmp     dword ptr [rbp+118h], 1
0x180006315  ja      short loc_180006321
0x180006317  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
