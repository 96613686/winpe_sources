# __DllMainCRTStartup

- ea: `0x18000a2b4`
- end: `0x18000a4c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a270`

## callees

- `0x1800099f0`
- `0x18000a040`
- `0x18000a2b4`
- `0x18000a6c5`
- `0x180011ef0`

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
  if ( (_DWORD)fdwReason || dword_18001A0E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001A0E4 = 1;
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
            if ( dword_18001A0E4 )
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
0x18000a2b4  mov     [rsp+lpvReserved], r8
0x18000a2b9  mov     [rsp+arg_8], edx
0x18000a2bd  mov     [rsp+arg_0], rcx
0x18000a2c2  push    rbx
0x18000a2c3  push    rsi
0x18000a2c4  push    rdi
0x18000a2c5  sub     rsp, 0F0h
0x18000a2cc  mov     edi, edx
0x18000a2ce  mov     rsi, rcx
0x18000a2d1  mov     ebx, 1
0x18000a2d6  cmp     edx, ebx
0x18000a2d8  ja      short loc_18000A2E0
0x18000a2da  mov     cs:__native_dllmain_reason, edx
0x18000a2e0  test    edx, edx
0x18000a2e2  jnz     short loc_18000A2F7
0x18000a2e4  cmp     cs:dword_18001A0E0, edx
0x18000a2ea  jnz     short loc_18000A2F7
0x18000a2ec  xor     ebx, ebx
0x18000a2ee  mov     [rsp+108h+var_E8], ebx
0x18000a2f2  jmp     loc_18000A4A4
0x18000a2f7  lea     eax, [rdx-1]
0x18000a2fa  cmp     eax, 1
0x18000a2fd  ja      loc_18000A384
0x18000a303  mov     rax, cs:_pRawDllMain
0x18000a30a  test    rax, rax
0x18000a30d  jz      short loc_18000A345
0x18000a30f  cmp     edx, 1
0x18000a312  jnz     short loc_18000A31A
0x18000a314  mov     cs:dword_18001A0E4, edx
0x18000a31a  mov     r8, [rsp+108h+lpvReserved]
0x18000a322  call    cs:__guard_dispatch_icall_fptr
0x18000a328  mov     ebx, eax
0x18000a32a  mov     [rsp+108h+var_E8], eax
0x18000a32e  jmp     short loc_18000A345
0x18000a330  xor     ebx, ebx
0x18000a332  mov     [rsp+108h+var_E8], ebx
0x18000a336  mov     edi, [rsp+108h+arg_8]
0x18000a33d  mov     rsi, [rsp+108h+arg_0]
0x18000a345  test    ebx, ebx
0x18000a347  jz      loc_18000A4A4
0x18000a34d  mov     r8, [rsp+108h+lpvReserved]
0x18000a355  mov     edx, edi
0x18000a357  mov     rcx, rsi
0x18000a35a  call    _CRT_INIT
0x18000a35f  mov     ebx, eax
0x18000a361  mov     [rsp+108h+var_E8], eax
0x18000a365  jmp     short loc_18000A37C
0x18000a367  xor     ebx, ebx
0x18000a369  mov     [rsp+108h+var_E8], ebx
0x18000a36d  mov     edi, [rsp+108h+arg_8]
0x18000a374  mov     rsi, [rsp+108h+arg_0]
0x18000a37c  test    ebx, ebx
0x18000a37e  jz      loc_18000A4A4
0x18000a384  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000a38c  mov     edx, edi; fdwReason
0x18000a38e  mov     rcx, rsi; hinstDLL
0x18000a391  call    DllMain
0x18000a396  mov     ebx, eax
0x18000a398  mov     [rsp+108h+var_E8], eax
0x18000a39c  jmp     short loc_18000A3B3
0x18000a39e  xor     ebx, ebx
0x18000a3a0  mov     [rsp+108h+var_E8], ebx
0x18000a3a4  mov     edi, [rsp+108h+arg_8]
0x18000a3ab  mov     rsi, [rsp+108h+arg_0]
0x18000a3b3  cmp     edi, 1
0x18000a3b6  jnz     short loc_18000A42F
0x18000a3b8  test    ebx, ebx
0x18000a3ba  jnz     short loc_18000A42F
0x18000a3bc  xor     r8d, r8d; lpvReserved
0x18000a3bf  xor     edx, edx; fdwReason
0x18000a3c1  mov     rcx, rsi; hinstDLL
0x18000a3c4  call    DllMain
0x18000a3c9  jmp     short loc_18000A3DE
0x18000a3cb  mov     edi, [rsp+108h+arg_8]
0x18000a3d2  mov     rsi, [rsp+108h+arg_0]
0x18000a3da  mov     ebx, [rsp+108h+var_E8]
0x18000a3de  xor     r8d, r8d
0x18000a3e1  xor     edx, edx
0x18000a3e3  mov     rcx, rsi
0x18000a3e6  call    _CRT_INIT
0x18000a3eb  jmp     short loc_18000A400
0x18000a3ed  mov     edi, [rsp+108h+arg_8]
0x18000a3f4  mov     rsi, [rsp+108h+arg_0]
0x18000a3fc  mov     ebx, [rsp+108h+var_E8]
0x18000a400  mov     rax, cs:_pRawDllMain
0x18000a407  test    rax, rax
0x18000a40a  jz      short loc_18000A42F
0x18000a40c  xor     r8d, r8d
0x18000a40f  xor     edx, edx
0x18000a411  mov     rcx, rsi
0x18000a414  call    cs:__guard_dispatch_icall_fptr
0x18000a41a  jmp     short loc_18000A42F
0x18000a41c  mov     edi, [rsp+108h+arg_8]
0x18000a423  mov     rsi, [rsp+108h+arg_0]
0x18000a42b  mov     ebx, [rsp+108h+var_E8]
0x18000a42f  test    edi, edi
0x18000a431  jz      short loc_18000A438
0x18000a433  cmp     edi, 3
0x18000a436  jnz     short loc_18000A4A4
0x18000a438  mov     r8, [rsp+108h+lpvReserved]
0x18000a440  mov     edx, edi
0x18000a442  mov     rcx, rsi
0x18000a445  call    _CRT_INIT
0x18000a44a  mov     ebx, eax
0x18000a44c  mov     [rsp+108h+var_E8], eax
0x18000a450  jmp     short loc_18000A467
0x18000a452  xor     ebx, ebx
0x18000a454  mov     [rsp+108h+var_E8], ebx
0x18000a458  mov     edi, [rsp+108h+arg_8]
0x18000a45f  mov     rsi, [rsp+108h+arg_0]
0x18000a467  mov     rax, cs:_pRawDllMain
0x18000a46e  test    rax, rax
0x18000a471  jz      short loc_18000A4A4
0x18000a473  cmp     cs:dword_18001A0E4, 0
0x18000a47a  jz      short loc_18000A4A4
0x18000a47c  mov     r8, [rsp+108h+lpvReserved]
0x18000a484  mov     edx, edi
0x18000a486  mov     rcx, rsi
0x18000a489  call    cs:__guard_dispatch_icall_fptr
0x18000a48f  mov     ebx, eax
0x18000a491  mov     [rsp+108h+var_E8], eax
0x18000a495  jmp     short loc_18000A4A4
0x18000a497  xor     ebx, ebx
0x18000a499  mov     [rsp+108h+var_E8], ebx
0x18000a49d  mov     edi, [rsp+108h+arg_8]
0x18000a4a4  cmp     edi, 1
0x18000a4a7  ja      short loc_18000A4B3
0x18000a4a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18000a4b3  mov     eax, ebx
0x18000a4b5  add     rsp, 0F0h
0x18000a4bc  pop     rdi
0x18000a4bd  pop     rsi
0x18000a4be  pop     rbx
0x18000a4bf  retn
0x1800120fa  push    rbp
0x1800120fc  sub     rsp, 20h
0x180012100  mov     rbp, rdx
0x180012103  mov     rax, [rcx]
0x180012106  mov     edx, [rax]
0x180012108  mov     [rbp+0A8h], rcx
0x18001210f  mov     [rbp+28h], edx
0x180012112  mov     eax, [rbp+28h]
0x180012115  cmp     eax, 0E06D7363h
0x18001211a  jnz     short loc_180012130
0x18001211c  mov     rdx, [rbp+0A8h]
0x180012123  mov     ecx, [rbp+28h]
0x180012126  call    _XcptFilter_0
0x18001212b  mov     [rbp+30h], eax
0x18001212e  jmp     short loc_180012137
0x180012130  mov     dword ptr [rbp+30h], 0
0x180012137  mov     eax, [rbp+30h]
0x18001213a  add     rsp, 20h
0x18001213e  pop     rbp
0x18001213f  retn
0x180012141  push    rbp
0x180012143  sub     rsp, 20h
0x180012147  mov     rbp, rdx
0x18001214a  mov     rax, [rcx]
0x18001214d  mov     edx, [rax]
0x18001214f  mov     [rbp+0B0h], rcx
0x180012156  mov     [rbp+38h], edx
0x180012159  mov     eax, [rbp+38h]
0x18001215c  cmp     eax, 0E06D7363h
0x180012161  jnz     short loc_180012177
0x180012163  mov     rdx, [rbp+0B0h]
0x18001216a  mov     ecx, [rbp+38h]
0x18001216d  call    _XcptFilter_0
0x180012172  mov     [rbp+40h], eax
0x180012175  jmp     short loc_18001217E
0x180012177  mov     dword ptr [rbp+40h], 0
0x18001217e  mov     eax, [rbp+40h]
0x180012181  add     rsp, 20h
0x180012185  pop     rbp
0x180012186  retn
0x180012188  push    rbp
0x18001218a  sub     rsp, 20h
0x18001218e  mov     rbp, rdx
0x180012191  mov     rax, [rcx]
0x180012194  mov     edx, [rax]
0x180012196  mov     [rbp+0B8h], rcx
0x18001219d  mov     [rbp+48h], edx
0x1800121a0  mov     eax, [rbp+48h]
0x1800121a3  cmp     eax, 0E06D7363h
0x1800121a8  jnz     short loc_1800121BE
0x1800121aa  mov     rdx, [rbp+0B8h]
0x1800121b1  mov     ecx, [rbp+48h]
0x1800121b4  call    _XcptFilter_0
0x1800121b9  mov     [rbp+50h], eax
0x1800121bc  jmp     short loc_1800121C5
0x1800121be  mov     dword ptr [rbp+50h], 0
0x1800121c5  mov     eax, [rbp+50h]
0x1800121c8  add     rsp, 20h
0x1800121cc  pop     rbp
0x1800121cd  retn
0x1800121cf  push    rbp
0x1800121d1  sub     rsp, 20h
0x1800121d5  mov     rbp, rdx
0x1800121d8  mov     rax, [rcx]
0x1800121db  mov     edx, [rax]
0x1800121dd  mov     [rbp+0C0h], rcx
0x1800121e4  mov     [rbp+58h], edx
0x1800121e7  mov     eax, [rbp+58h]
0x1800121ea  cmp     eax, 0E06D7363h
0x1800121ef  jnz     short loc_180012205
0x1800121f1  mov     rdx, [rbp+0C0h]
0x1800121f8  mov     ecx, [rbp+58h]
0x1800121fb  call    _XcptFilter_0
0x180012200  mov     [rbp+60h], eax
0x180012203  jmp     short loc_18001220C
0x180012205  mov     dword ptr [rbp+60h], 0
0x18001220c  mov     eax, [rbp+60h]
0x18001220f  add     rsp, 20h
0x180012213  pop     rbp
0x180012214  retn
0x180012216  push    rbp
0x180012218  sub     rsp, 20h
0x18001221c  mov     rbp, rdx
0x18001221f  mov     rax, [rcx]
0x180012222  mov     edx, [rax]
0x180012224  mov     [rbp+0C8h], rcx
0x18001222b  mov     [rbp+68h], edx
0x18001222e  mov     eax, [rbp+68h]
0x180012231  cmp     eax, 0E06D7363h
0x180012236  jnz     short loc_18001224C
0x180012238  mov     rdx, [rbp+0C8h]
0x18001223f  mov     ecx, [rbp+68h]
0x180012242  call    _XcptFilter_0
0x180012247  mov     [rbp+70h], eax
0x18001224a  jmp     short loc_180012253
0x18001224c  mov     dword ptr [rbp+70h], 0
0x180012253  mov     eax, [rbp+70h]
0x180012256  add     rsp, 20h
0x18001225a  pop     rbp
0x18001225b  retn
0x18001225d  push    rbp
0x18001225f  sub     rsp, 20h
0x180012263  mov     rbp, rdx
0x180012266  mov     rax, [rcx]
0x180012269  mov     edx, [rax]
0x18001226b  mov     [rbp+0D0h], rcx
0x180012272  mov     [rbp+78h], edx
0x180012275  mov     eax, [rbp+78h]
0x180012278  cmp     eax, 0E06D7363h
0x18001227d  jnz     short loc_180012296
0x18001227f  mov     rdx, [rbp+0D0h]
0x180012286  mov     ecx, [rbp+78h]
0x180012289  call    _XcptFilter_0
0x18001228e  mov     [rbp+80h], eax
0x180012294  jmp     short loc_1800122A0
0x180012296  mov     dword ptr [rbp+80h], 0
0x1800122a0  mov     eax, [rbp+80h]
0x1800122a6  add     rsp, 20h
0x1800122aa  pop     rbp
0x1800122ab  retn
0x1800122ad  push    rbp
0x1800122af  sub     rsp, 20h
0x1800122b3  mov     rbp, rdx
0x1800122b6  mov     rax, [rcx]
0x1800122b9  mov     edx, [rax]
0x1800122bb  mov     [rbp+0D8h], rcx
0x1800122c2  mov     [rbp+88h], edx
0x1800122c8  mov     eax, [rbp+88h]
0x1800122ce  cmp     eax, 0E06D7363h
0x1800122d3  jnz     short loc_1800122EF
0x1800122d5  mov     rdx, [rbp+0D8h]
0x1800122dc  mov     ecx, [rbp+88h]
0x1800122e2  call    _XcptFilter_0
0x1800122e7  mov     [rbp+90h], eax
0x1800122ed  jmp     short loc_1800122F9
0x1800122ef  mov     dword ptr [rbp+90h], 0
0x1800122f9  mov     eax, [rbp+90h]
0x1800122ff  add     rsp, 20h
0x180012303  pop     rbp
0x180012304  retn
0x180012306  push    rbp
0x180012308  sub     rsp, 20h
0x18001230c  mov     rbp, rdx
0x18001230f  mov     rax, [rcx]
0x180012312  mov     edx, [rax]
0x180012314  mov     [rbp+0E0h], rcx
0x18001231b  mov     [rbp+98h], edx
0x180012321  mov     eax, [rbp+98h]
0x180012327  cmp     eax, 0E06D7363h
0x18001232c  jnz     short loc_180012348
0x18001232e  mov     rdx, [rbp+0E0h]
0x180012335  mov     ecx, [rbp+98h]
0x18001233b  call    _XcptFilter_0
0x180012340  mov     [rbp+0A0h], eax
0x180012346  jmp     short loc_180012352
0x180012348  mov     dword ptr [rbp+0A0h], 0
0x180012352  mov     eax, [rbp+0A0h]
0x180012358  add     rsp, 20h
0x18001235c  pop     rbp
0x18001235d  retn
0x18001235f  push    rbp
0x180012361  sub     rsp, 20h
0x180012365  mov     rbp, rdx
0x180012368  cmp     dword ptr [rbp+118h], 1
0x18001236f  ja      short loc_18001237B
0x180012371  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
