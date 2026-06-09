# __DllMainCRTStartup

- ea: `0x1800018b4`
- end: `0x180001ac0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x180001640`
- `0x1800018b4`
- `0x180001aea`
- `0x180001cc8`
- `0x180002660`

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
  if ( (_DWORD)fdwReason || dword_1800060A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800060A4 = 1;
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
            if ( dword_1800060A4 )
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
0x1800018e4  cmp     cs:dword_1800060A0, edx
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
0x180001914  mov     cs:dword_1800060A4, edx
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
0x180001a73  cmp     cs:dword_1800060A4, 0
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
0x1800026d0  push    rbp
0x1800026d2  sub     rsp, 20h
0x1800026d6  mov     rbp, rdx
0x1800026d9  mov     rax, [rcx]
0x1800026dc  mov     edx, [rax]
0x1800026de  mov     [rbp+0A8h], rcx
0x1800026e5  mov     [rbp+28h], edx
0x1800026e8  mov     eax, [rbp+28h]
0x1800026eb  cmp     eax, 0E06D7363h
0x1800026f0  jnz     short loc_180002706
0x1800026f2  mov     rdx, [rbp+0A8h]
0x1800026f9  mov     ecx, [rbp+28h]
0x1800026fc  call    _XcptFilter_0
0x180002701  mov     [rbp+30h], eax
0x180002704  jmp     short loc_18000270D
0x180002706  mov     dword ptr [rbp+30h], 0
0x18000270d  mov     eax, [rbp+30h]
0x180002710  add     rsp, 20h
0x180002714  pop     rbp
0x180002715  retn
0x180002717  push    rbp
0x180002719  sub     rsp, 20h
0x18000271d  mov     rbp, rdx
0x180002720  mov     rax, [rcx]
0x180002723  mov     edx, [rax]
0x180002725  mov     [rbp+0B0h], rcx
0x18000272c  mov     [rbp+38h], edx
0x18000272f  mov     eax, [rbp+38h]
0x180002732  cmp     eax, 0E06D7363h
0x180002737  jnz     short loc_18000274D
0x180002739  mov     rdx, [rbp+0B0h]
0x180002740  mov     ecx, [rbp+38h]
0x180002743  call    _XcptFilter_0
0x180002748  mov     [rbp+40h], eax
0x18000274b  jmp     short loc_180002754
0x18000274d  mov     dword ptr [rbp+40h], 0
0x180002754  mov     eax, [rbp+40h]
0x180002757  add     rsp, 20h
0x18000275b  pop     rbp
0x18000275c  retn
0x18000275e  push    rbp
0x180002760  sub     rsp, 20h
0x180002764  mov     rbp, rdx
0x180002767  mov     rax, [rcx]
0x18000276a  mov     edx, [rax]
0x18000276c  mov     [rbp+0B8h], rcx
0x180002773  mov     [rbp+48h], edx
0x180002776  mov     eax, [rbp+48h]
0x180002779  cmp     eax, 0E06D7363h
0x18000277e  jnz     short loc_180002794
0x180002780  mov     rdx, [rbp+0B8h]
0x180002787  mov     ecx, [rbp+48h]
0x18000278a  call    _XcptFilter_0
0x18000278f  mov     [rbp+50h], eax
0x180002792  jmp     short loc_18000279B
0x180002794  mov     dword ptr [rbp+50h], 0
0x18000279b  mov     eax, [rbp+50h]
0x18000279e  add     rsp, 20h
0x1800027a2  pop     rbp
0x1800027a3  retn
0x1800027a5  push    rbp
0x1800027a7  sub     rsp, 20h
0x1800027ab  mov     rbp, rdx
0x1800027ae  mov     rax, [rcx]
0x1800027b1  mov     edx, [rax]
0x1800027b3  mov     [rbp+0C0h], rcx
0x1800027ba  mov     [rbp+58h], edx
0x1800027bd  mov     eax, [rbp+58h]
0x1800027c0  cmp     eax, 0E06D7363h
0x1800027c5  jnz     short loc_1800027DB
0x1800027c7  mov     rdx, [rbp+0C0h]
0x1800027ce  mov     ecx, [rbp+58h]
0x1800027d1  call    _XcptFilter_0
0x1800027d6  mov     [rbp+60h], eax
0x1800027d9  jmp     short loc_1800027E2
0x1800027db  mov     dword ptr [rbp+60h], 0
0x1800027e2  mov     eax, [rbp+60h]
0x1800027e5  add     rsp, 20h
0x1800027e9  pop     rbp
0x1800027ea  retn
0x1800027ec  push    rbp
0x1800027ee  sub     rsp, 20h
0x1800027f2  mov     rbp, rdx
0x1800027f5  mov     rax, [rcx]
0x1800027f8  mov     edx, [rax]
0x1800027fa  mov     [rbp+0C8h], rcx
0x180002801  mov     [rbp+68h], edx
0x180002804  mov     eax, [rbp+68h]
0x180002807  cmp     eax, 0E06D7363h
0x18000280c  jnz     short loc_180002822
0x18000280e  mov     rdx, [rbp+0C8h]
0x180002815  mov     ecx, [rbp+68h]
0x180002818  call    _XcptFilter_0
0x18000281d  mov     [rbp+70h], eax
0x180002820  jmp     short loc_180002829
0x180002822  mov     dword ptr [rbp+70h], 0
0x180002829  mov     eax, [rbp+70h]
0x18000282c  add     rsp, 20h
0x180002830  pop     rbp
0x180002831  retn
0x180002833  push    rbp
0x180002835  sub     rsp, 20h
0x180002839  mov     rbp, rdx
0x18000283c  mov     rax, [rcx]
0x18000283f  mov     edx, [rax]
0x180002841  mov     [rbp+0D0h], rcx
0x180002848  mov     [rbp+78h], edx
0x18000284b  mov     eax, [rbp+78h]
0x18000284e  cmp     eax, 0E06D7363h
0x180002853  jnz     short loc_18000286C
0x180002855  mov     rdx, [rbp+0D0h]
0x18000285c  mov     ecx, [rbp+78h]
0x18000285f  call    _XcptFilter_0
0x180002864  mov     [rbp+80h], eax
0x18000286a  jmp     short loc_180002876
0x18000286c  mov     dword ptr [rbp+80h], 0
0x180002876  mov     eax, [rbp+80h]
0x18000287c  add     rsp, 20h
0x180002880  pop     rbp
0x180002881  retn
0x180002883  push    rbp
0x180002885  sub     rsp, 20h
0x180002889  mov     rbp, rdx
0x18000288c  mov     rax, [rcx]
0x18000288f  mov     edx, [rax]
0x180002891  mov     [rbp+0D8h], rcx
0x180002898  mov     [rbp+88h], edx
0x18000289e  mov     eax, [rbp+88h]
0x1800028a4  cmp     eax, 0E06D7363h
0x1800028a9  jnz     short loc_1800028C5
0x1800028ab  mov     rdx, [rbp+0D8h]
0x1800028b2  mov     ecx, [rbp+88h]
0x1800028b8  call    _XcptFilter_0
0x1800028bd  mov     [rbp+90h], eax
0x1800028c3  jmp     short loc_1800028CF
0x1800028c5  mov     dword ptr [rbp+90h], 0
0x1800028cf  mov     eax, [rbp+90h]
0x1800028d5  add     rsp, 20h
0x1800028d9  pop     rbp
0x1800028da  retn
0x1800028dc  push    rbp
0x1800028de  sub     rsp, 20h
0x1800028e2  mov     rbp, rdx
0x1800028e5  mov     rax, [rcx]
0x1800028e8  mov     edx, [rax]
0x1800028ea  mov     [rbp+0E0h], rcx
0x1800028f1  mov     [rbp+98h], edx
0x1800028f7  mov     eax, [rbp+98h]
0x1800028fd  cmp     eax, 0E06D7363h
0x180002902  jnz     short loc_18000291E
0x180002904  mov     rdx, [rbp+0E0h]
0x18000290b  mov     ecx, [rbp+98h]
0x180002911  call    _XcptFilter_0
0x180002916  mov     [rbp+0A0h], eax
0x18000291c  jmp     short loc_180002928
0x18000291e  mov     dword ptr [rbp+0A0h], 0
0x180002928  mov     eax, [rbp+0A0h]
0x18000292e  add     rsp, 20h
0x180002932  pop     rbp
0x180002933  retn
0x180002935  push    rbp
0x180002937  sub     rsp, 20h
0x18000293b  mov     rbp, rdx
0x18000293e  cmp     dword ptr [rbp+118h], 1
0x180002945  ja      short loc_180002951
0x180002947  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
