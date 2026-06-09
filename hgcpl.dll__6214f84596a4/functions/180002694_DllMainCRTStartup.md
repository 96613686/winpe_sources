# __DllMainCRTStartup

- ea: `0x180002694`
- end: `0x1800028a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002650`

## callees

- `0x180002420`
- `0x180002694`
- `0x180002d54`
- `0x18000e584`
- `0x180018ac0`

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
  if ( (_DWORD)fdwReason || dword_180029F00 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180029F04 = 1;
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
            if ( dword_180029F04 )
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
0x180002694  mov     [rsp+lpvReserved], r8
0x180002699  mov     [rsp+arg_8], edx
0x18000269d  mov     [rsp+arg_0], rcx
0x1800026a2  push    rbx
0x1800026a3  push    rsi
0x1800026a4  push    rdi
0x1800026a5  sub     rsp, 0F0h
0x1800026ac  mov     edi, edx
0x1800026ae  mov     rsi, rcx
0x1800026b1  mov     ebx, 1
0x1800026b6  cmp     edx, ebx
0x1800026b8  ja      short loc_1800026C0
0x1800026ba  mov     cs:__native_dllmain_reason, edx
0x1800026c0  test    edx, edx
0x1800026c2  jnz     short loc_1800026D7
0x1800026c4  cmp     cs:dword_180029F00, edx
0x1800026ca  jnz     short loc_1800026D7
0x1800026cc  xor     ebx, ebx
0x1800026ce  mov     [rsp+108h+var_E8], ebx
0x1800026d2  jmp     loc_180002884
0x1800026d7  lea     eax, [rdx-1]
0x1800026da  cmp     eax, 1
0x1800026dd  ja      loc_180002764
0x1800026e3  mov     rax, cs:_pRawDllMain
0x1800026ea  test    rax, rax
0x1800026ed  jz      short loc_180002725
0x1800026ef  cmp     edx, 1
0x1800026f2  jnz     short loc_1800026FA
0x1800026f4  mov     cs:dword_180029F04, edx
0x1800026fa  mov     r8, [rsp+108h+lpvReserved]
0x180002702  call    cs:__guard_dispatch_icall_fptr
0x180002708  mov     ebx, eax
0x18000270a  mov     [rsp+108h+var_E8], eax
0x18000270e  jmp     short loc_180002725
0x180002710  xor     ebx, ebx
0x180002712  mov     [rsp+108h+var_E8], ebx
0x180002716  mov     edi, [rsp+108h+arg_8]
0x18000271d  mov     rsi, [rsp+108h+arg_0]
0x180002725  test    ebx, ebx
0x180002727  jz      loc_180002884
0x18000272d  mov     r8, [rsp+108h+lpvReserved]
0x180002735  mov     edx, edi
0x180002737  mov     rcx, rsi
0x18000273a  call    _CRT_INIT
0x18000273f  mov     ebx, eax
0x180002741  mov     [rsp+108h+var_E8], eax
0x180002745  jmp     short loc_18000275C
0x180002747  xor     ebx, ebx
0x180002749  mov     [rsp+108h+var_E8], ebx
0x18000274d  mov     edi, [rsp+108h+arg_8]
0x180002754  mov     rsi, [rsp+108h+arg_0]
0x18000275c  test    ebx, ebx
0x18000275e  jz      loc_180002884
0x180002764  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000276c  mov     edx, edi; fdwReason
0x18000276e  mov     rcx, rsi; hinstDLL
0x180002771  call    DllMain
0x180002776  mov     ebx, eax
0x180002778  mov     [rsp+108h+var_E8], eax
0x18000277c  jmp     short loc_180002793
0x18000277e  xor     ebx, ebx
0x180002780  mov     [rsp+108h+var_E8], ebx
0x180002784  mov     edi, [rsp+108h+arg_8]
0x18000278b  mov     rsi, [rsp+108h+arg_0]
0x180002793  cmp     edi, 1
0x180002796  jnz     short loc_18000280F
0x180002798  test    ebx, ebx
0x18000279a  jnz     short loc_18000280F
0x18000279c  xor     r8d, r8d; lpvReserved
0x18000279f  xor     edx, edx; fdwReason
0x1800027a1  mov     rcx, rsi; hinstDLL
0x1800027a4  call    DllMain
0x1800027a9  jmp     short loc_1800027BE
0x1800027ab  mov     edi, [rsp+108h+arg_8]
0x1800027b2  mov     rsi, [rsp+108h+arg_0]
0x1800027ba  mov     ebx, [rsp+108h+var_E8]
0x1800027be  xor     r8d, r8d
0x1800027c1  xor     edx, edx
0x1800027c3  mov     rcx, rsi
0x1800027c6  call    _CRT_INIT
0x1800027cb  jmp     short loc_1800027E0
0x1800027cd  mov     edi, [rsp+108h+arg_8]
0x1800027d4  mov     rsi, [rsp+108h+arg_0]
0x1800027dc  mov     ebx, [rsp+108h+var_E8]
0x1800027e0  mov     rax, cs:_pRawDllMain
0x1800027e7  test    rax, rax
0x1800027ea  jz      short loc_18000280F
0x1800027ec  xor     r8d, r8d
0x1800027ef  xor     edx, edx
0x1800027f1  mov     rcx, rsi
0x1800027f4  call    cs:__guard_dispatch_icall_fptr
0x1800027fa  jmp     short loc_18000280F
0x1800027fc  mov     edi, [rsp+108h+arg_8]
0x180002803  mov     rsi, [rsp+108h+arg_0]
0x18000280b  mov     ebx, [rsp+108h+var_E8]
0x18000280f  test    edi, edi
0x180002811  jz      short loc_180002818
0x180002813  cmp     edi, 3
0x180002816  jnz     short loc_180002884
0x180002818  mov     r8, [rsp+108h+lpvReserved]
0x180002820  mov     edx, edi
0x180002822  mov     rcx, rsi
0x180002825  call    _CRT_INIT
0x18000282a  mov     ebx, eax
0x18000282c  mov     [rsp+108h+var_E8], eax
0x180002830  jmp     short loc_180002847
0x180002832  xor     ebx, ebx
0x180002834  mov     [rsp+108h+var_E8], ebx
0x180002838  mov     edi, [rsp+108h+arg_8]
0x18000283f  mov     rsi, [rsp+108h+arg_0]
0x180002847  mov     rax, cs:_pRawDllMain
0x18000284e  test    rax, rax
0x180002851  jz      short loc_180002884
0x180002853  cmp     cs:dword_180029F04, 0
0x18000285a  jz      short loc_180002884
0x18000285c  mov     r8, [rsp+108h+lpvReserved]
0x180002864  mov     edx, edi
0x180002866  mov     rcx, rsi
0x180002869  call    cs:__guard_dispatch_icall_fptr
0x18000286f  mov     ebx, eax
0x180002871  mov     [rsp+108h+var_E8], eax
0x180002875  jmp     short loc_180002884
0x180002877  xor     ebx, ebx
0x180002879  mov     [rsp+108h+var_E8], ebx
0x18000287d  mov     edi, [rsp+108h+arg_8]
0x180002884  cmp     edi, 1
0x180002887  ja      short loc_180002893
0x180002889  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002893  mov     eax, ebx
0x180002895  add     rsp, 0F0h
0x18000289c  pop     rdi
0x18000289d  pop     rsi
0x18000289e  pop     rbx
0x18000289f  retn
0x180018b90  push    rbp
0x180018b92  sub     rsp, 20h
0x180018b96  mov     rbp, rdx
0x180018b99  mov     rax, [rcx]
0x180018b9c  mov     edx, [rax]
0x180018b9e  mov     [rbp+0A8h], rcx
0x180018ba5  mov     [rbp+28h], edx
0x180018ba8  mov     eax, [rbp+28h]
0x180018bab  cmp     eax, 0E06D7363h
0x180018bb0  jnz     short loc_180018BC6
0x180018bb2  mov     rdx, [rbp+0A8h]
0x180018bb9  mov     ecx, [rbp+28h]
0x180018bbc  call    _XcptFilter_0
0x180018bc1  mov     [rbp+30h], eax
0x180018bc4  jmp     short loc_180018BCD
0x180018bc6  mov     dword ptr [rbp+30h], 0
0x180018bcd  mov     eax, [rbp+30h]
0x180018bd0  add     rsp, 20h
0x180018bd4  pop     rbp
0x180018bd5  retn
0x180018bd7  push    rbp
0x180018bd9  sub     rsp, 20h
0x180018bdd  mov     rbp, rdx
0x180018be0  mov     rax, [rcx]
0x180018be3  mov     edx, [rax]
0x180018be5  mov     [rbp+0B0h], rcx
0x180018bec  mov     [rbp+38h], edx
0x180018bef  mov     eax, [rbp+38h]
0x180018bf2  cmp     eax, 0E06D7363h
0x180018bf7  jnz     short loc_180018C0D
0x180018bf9  mov     rdx, [rbp+0B0h]
0x180018c00  mov     ecx, [rbp+38h]
0x180018c03  call    _XcptFilter_0
0x180018c08  mov     [rbp+40h], eax
0x180018c0b  jmp     short loc_180018C14
0x180018c0d  mov     dword ptr [rbp+40h], 0
0x180018c14  mov     eax, [rbp+40h]
0x180018c17  add     rsp, 20h
0x180018c1b  pop     rbp
0x180018c1c  retn
0x180018c1e  push    rbp
0x180018c20  sub     rsp, 20h
0x180018c24  mov     rbp, rdx
0x180018c27  mov     rax, [rcx]
0x180018c2a  mov     edx, [rax]
0x180018c2c  mov     [rbp+0B8h], rcx
0x180018c33  mov     [rbp+48h], edx
0x180018c36  mov     eax, [rbp+48h]
0x180018c39  cmp     eax, 0E06D7363h
0x180018c3e  jnz     short loc_180018C54
0x180018c40  mov     rdx, [rbp+0B8h]
0x180018c47  mov     ecx, [rbp+48h]
0x180018c4a  call    _XcptFilter_0
0x180018c4f  mov     [rbp+50h], eax
0x180018c52  jmp     short loc_180018C5B
0x180018c54  mov     dword ptr [rbp+50h], 0
0x180018c5b  mov     eax, [rbp+50h]
0x180018c5e  add     rsp, 20h
0x180018c62  pop     rbp
0x180018c63  retn
0x180018c65  push    rbp
0x180018c67  sub     rsp, 20h
0x180018c6b  mov     rbp, rdx
0x180018c6e  mov     rax, [rcx]
0x180018c71  mov     edx, [rax]
0x180018c73  mov     [rbp+0C0h], rcx
0x180018c7a  mov     [rbp+58h], edx
0x180018c7d  mov     eax, [rbp+58h]
0x180018c80  cmp     eax, 0E06D7363h
0x180018c85  jnz     short loc_180018C9B
0x180018c87  mov     rdx, [rbp+0C0h]
0x180018c8e  mov     ecx, [rbp+58h]
0x180018c91  call    _XcptFilter_0
0x180018c96  mov     [rbp+60h], eax
0x180018c99  jmp     short loc_180018CA2
0x180018c9b  mov     dword ptr [rbp+60h], 0
0x180018ca2  mov     eax, [rbp+60h]
0x180018ca5  add     rsp, 20h
0x180018ca9  pop     rbp
0x180018caa  retn
0x180018cac  push    rbp
0x180018cae  sub     rsp, 20h
0x180018cb2  mov     rbp, rdx
0x180018cb5  mov     rax, [rcx]
0x180018cb8  mov     edx, [rax]
0x180018cba  mov     [rbp+0C8h], rcx
0x180018cc1  mov     [rbp+68h], edx
0x180018cc4  mov     eax, [rbp+68h]
0x180018cc7  cmp     eax, 0E06D7363h
0x180018ccc  jnz     short loc_180018CE2
0x180018cce  mov     rdx, [rbp+0C8h]
0x180018cd5  mov     ecx, [rbp+68h]
0x180018cd8  call    _XcptFilter_0
0x180018cdd  mov     [rbp+70h], eax
0x180018ce0  jmp     short loc_180018CE9
0x180018ce2  mov     dword ptr [rbp+70h], 0
0x180018ce9  mov     eax, [rbp+70h]
0x180018cec  add     rsp, 20h
0x180018cf0  pop     rbp
0x180018cf1  retn
0x180018cf3  push    rbp
0x180018cf5  sub     rsp, 20h
0x180018cf9  mov     rbp, rdx
0x180018cfc  mov     rax, [rcx]
0x180018cff  mov     edx, [rax]
0x180018d01  mov     [rbp+0D0h], rcx
0x180018d08  mov     [rbp+78h], edx
0x180018d0b  mov     eax, [rbp+78h]
0x180018d0e  cmp     eax, 0E06D7363h
0x180018d13  jnz     short loc_180018D2C
0x180018d15  mov     rdx, [rbp+0D0h]
0x180018d1c  mov     ecx, [rbp+78h]
0x180018d1f  call    _XcptFilter_0
0x180018d24  mov     [rbp+80h], eax
0x180018d2a  jmp     short loc_180018D36
0x180018d2c  mov     dword ptr [rbp+80h], 0
0x180018d36  mov     eax, [rbp+80h]
0x180018d3c  add     rsp, 20h
0x180018d40  pop     rbp
0x180018d41  retn
0x180018d43  push    rbp
0x180018d45  sub     rsp, 20h
0x180018d49  mov     rbp, rdx
0x180018d4c  mov     rax, [rcx]
0x180018d4f  mov     edx, [rax]
0x180018d51  mov     [rbp+0D8h], rcx
0x180018d58  mov     [rbp+88h], edx
0x180018d5e  mov     eax, [rbp+88h]
0x180018d64  cmp     eax, 0E06D7363h
0x180018d69  jnz     short loc_180018D85
0x180018d6b  mov     rdx, [rbp+0D8h]
0x180018d72  mov     ecx, [rbp+88h]
0x180018d78  call    _XcptFilter_0
0x180018d7d  mov     [rbp+90h], eax
0x180018d83  jmp     short loc_180018D8F
0x180018d85  mov     dword ptr [rbp+90h], 0
0x180018d8f  mov     eax, [rbp+90h]
0x180018d95  add     rsp, 20h
0x180018d99  pop     rbp
0x180018d9a  retn
0x180018d9c  push    rbp
0x180018d9e  sub     rsp, 20h
0x180018da2  mov     rbp, rdx
0x180018da5  mov     rax, [rcx]
0x180018da8  mov     edx, [rax]
0x180018daa  mov     [rbp+0E0h], rcx
0x180018db1  mov     [rbp+98h], edx
0x180018db7  mov     eax, [rbp+98h]
0x180018dbd  cmp     eax, 0E06D7363h
0x180018dc2  jnz     short loc_180018DDE
0x180018dc4  mov     rdx, [rbp+0E0h]
0x180018dcb  mov     ecx, [rbp+98h]
0x180018dd1  call    _XcptFilter_0
0x180018dd6  mov     [rbp+0A0h], eax
0x180018ddc  jmp     short loc_180018DE8
0x180018dde  mov     dword ptr [rbp+0A0h], 0
0x180018de8  mov     eax, [rbp+0A0h]
0x180018dee  add     rsp, 20h
0x180018df2  pop     rbp
0x180018df3  retn
0x180018df5  push    rbp
0x180018df7  sub     rsp, 20h
0x180018dfb  mov     rbp, rdx
0x180018dfe  cmp     dword ptr [rbp+118h], 1
0x180018e05  ja      short loc_180018E11
0x180018e07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
