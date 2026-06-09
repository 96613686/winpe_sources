# __DllMainCRTStartup

- ea: `0x180001444`
- end: `0x180001650`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001400`

## callees

- `0x1800011d0`
- `0x180001444`
- `0x180001b3c`
- `0x180006268`
- `0x18000dd80`

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
  if ( (_DWORD)fdwReason || dword_180019400 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180019404 = 1;
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
            if ( dword_180019404 )
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
0x180001444  mov     [rsp+lpvReserved], r8
0x180001449  mov     [rsp+arg_8], edx
0x18000144d  mov     [rsp+arg_0], rcx
0x180001452  push    rbx
0x180001453  push    rsi
0x180001454  push    rdi
0x180001455  sub     rsp, 0F0h
0x18000145c  mov     edi, edx
0x18000145e  mov     rsi, rcx
0x180001461  mov     ebx, 1
0x180001466  cmp     edx, ebx
0x180001468  ja      short loc_180001470
0x18000146a  mov     cs:__native_dllmain_reason, edx
0x180001470  test    edx, edx
0x180001472  jnz     short loc_180001487
0x180001474  cmp     cs:dword_180019400, edx
0x18000147a  jnz     short loc_180001487
0x18000147c  xor     ebx, ebx
0x18000147e  mov     [rsp+108h+var_E8], ebx
0x180001482  jmp     loc_180001634
0x180001487  lea     eax, [rdx-1]
0x18000148a  cmp     eax, 1
0x18000148d  ja      loc_180001514
0x180001493  mov     rax, cs:_pRawDllMain
0x18000149a  test    rax, rax
0x18000149d  jz      short loc_1800014D5
0x18000149f  cmp     edx, 1
0x1800014a2  jnz     short loc_1800014AA
0x1800014a4  mov     cs:dword_180019404, edx
0x1800014aa  mov     r8, [rsp+108h+lpvReserved]
0x1800014b2  call    cs:__guard_dispatch_icall_fptr
0x1800014b8  mov     ebx, eax
0x1800014ba  mov     [rsp+108h+var_E8], eax
0x1800014be  jmp     short loc_1800014D5
0x1800014c0  xor     ebx, ebx
0x1800014c2  mov     [rsp+108h+var_E8], ebx
0x1800014c6  mov     edi, [rsp+108h+arg_8]
0x1800014cd  mov     rsi, [rsp+108h+arg_0]
0x1800014d5  test    ebx, ebx
0x1800014d7  jz      loc_180001634
0x1800014dd  mov     r8, [rsp+108h+lpvReserved]
0x1800014e5  mov     edx, edi
0x1800014e7  mov     rcx, rsi
0x1800014ea  call    _CRT_INIT
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_18000150C
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  mov     rsi, [rsp+108h+arg_0]
0x18000150c  test    ebx, ebx
0x18000150e  jz      loc_180001634
0x180001514  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000151c  mov     edx, edi; fdwReason
0x18000151e  mov     rcx, rsi; hinstDLL
0x180001521  call    DllMain
0x180001526  mov     ebx, eax
0x180001528  mov     [rsp+108h+var_E8], eax
0x18000152c  jmp     short loc_180001543
0x18000152e  xor     ebx, ebx
0x180001530  mov     [rsp+108h+var_E8], ebx
0x180001534  mov     edi, [rsp+108h+arg_8]
0x18000153b  mov     rsi, [rsp+108h+arg_0]
0x180001543  cmp     edi, 1
0x180001546  jnz     short loc_1800015BF
0x180001548  test    ebx, ebx
0x18000154a  jnz     short loc_1800015BF
0x18000154c  xor     r8d, r8d; lpvReserved
0x18000154f  xor     edx, edx; fdwReason
0x180001551  mov     rcx, rsi; hinstDLL
0x180001554  call    DllMain
0x180001559  jmp     short loc_18000156E
0x18000155b  mov     edi, [rsp+108h+arg_8]
0x180001562  mov     rsi, [rsp+108h+arg_0]
0x18000156a  mov     ebx, [rsp+108h+var_E8]
0x18000156e  xor     r8d, r8d
0x180001571  xor     edx, edx
0x180001573  mov     rcx, rsi
0x180001576  call    _CRT_INIT
0x18000157b  jmp     short loc_180001590
0x18000157d  mov     edi, [rsp+108h+arg_8]
0x180001584  mov     rsi, [rsp+108h+arg_0]
0x18000158c  mov     ebx, [rsp+108h+var_E8]
0x180001590  mov     rax, cs:_pRawDllMain
0x180001597  test    rax, rax
0x18000159a  jz      short loc_1800015BF
0x18000159c  xor     r8d, r8d
0x18000159f  xor     edx, edx
0x1800015a1  mov     rcx, rsi
0x1800015a4  call    cs:__guard_dispatch_icall_fptr
0x1800015aa  jmp     short loc_1800015BF
0x1800015ac  mov     edi, [rsp+108h+arg_8]
0x1800015b3  mov     rsi, [rsp+108h+arg_0]
0x1800015bb  mov     ebx, [rsp+108h+var_E8]
0x1800015bf  test    edi, edi
0x1800015c1  jz      short loc_1800015C8
0x1800015c3  cmp     edi, 3
0x1800015c6  jnz     short loc_180001634
0x1800015c8  mov     r8, [rsp+108h+lpvReserved]
0x1800015d0  mov     edx, edi
0x1800015d2  mov     rcx, rsi
0x1800015d5  call    _CRT_INIT
0x1800015da  mov     ebx, eax
0x1800015dc  mov     [rsp+108h+var_E8], eax
0x1800015e0  jmp     short loc_1800015F7
0x1800015e2  xor     ebx, ebx
0x1800015e4  mov     [rsp+108h+var_E8], ebx
0x1800015e8  mov     edi, [rsp+108h+arg_8]
0x1800015ef  mov     rsi, [rsp+108h+arg_0]
0x1800015f7  mov     rax, cs:_pRawDllMain
0x1800015fe  test    rax, rax
0x180001601  jz      short loc_180001634
0x180001603  cmp     cs:dword_180019404, 0
0x18000160a  jz      short loc_180001634
0x18000160c  mov     r8, [rsp+108h+lpvReserved]
0x180001614  mov     edx, edi
0x180001616  mov     rcx, rsi
0x180001619  call    cs:__guard_dispatch_icall_fptr
0x18000161f  mov     ebx, eax
0x180001621  mov     [rsp+108h+var_E8], eax
0x180001625  jmp     short loc_180001634
0x180001627  xor     ebx, ebx
0x180001629  mov     [rsp+108h+var_E8], ebx
0x18000162d  mov     edi, [rsp+108h+arg_8]
0x180001634  cmp     edi, 1
0x180001637  ja      short loc_180001643
0x180001639  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001643  mov     eax, ebx
0x180001645  add     rsp, 0F0h
0x18000164c  pop     rdi
0x18000164d  pop     rsi
0x18000164e  pop     rbx
0x18000164f  retn
0x18000de23  push    rbp
0x18000de25  sub     rsp, 20h
0x18000de29  mov     rbp, rdx
0x18000de2c  mov     rax, [rcx]
0x18000de2f  mov     edx, [rax]
0x18000de31  mov     [rbp+0A8h], rcx
0x18000de38  mov     [rbp+28h], edx
0x18000de3b  mov     eax, [rbp+28h]
0x18000de3e  cmp     eax, 0E06D7363h
0x18000de43  jnz     short loc_18000DE59
0x18000de45  mov     rdx, [rbp+0A8h]
0x18000de4c  mov     ecx, [rbp+28h]
0x18000de4f  call    _XcptFilter_0
0x18000de54  mov     [rbp+30h], eax
0x18000de57  jmp     short loc_18000DE60
0x18000de59  mov     dword ptr [rbp+30h], 0
0x18000de60  mov     eax, [rbp+30h]
0x18000de63  add     rsp, 20h
0x18000de67  pop     rbp
0x18000de68  retn
0x18000de6a  push    rbp
0x18000de6c  sub     rsp, 20h
0x18000de70  mov     rbp, rdx
0x18000de73  mov     rax, [rcx]
0x18000de76  mov     edx, [rax]
0x18000de78  mov     [rbp+0B0h], rcx
0x18000de7f  mov     [rbp+38h], edx
0x18000de82  mov     eax, [rbp+38h]
0x18000de85  cmp     eax, 0E06D7363h
0x18000de8a  jnz     short loc_18000DEA0
0x18000de8c  mov     rdx, [rbp+0B0h]
0x18000de93  mov     ecx, [rbp+38h]
0x18000de96  call    _XcptFilter_0
0x18000de9b  mov     [rbp+40h], eax
0x18000de9e  jmp     short loc_18000DEA7
0x18000dea0  mov     dword ptr [rbp+40h], 0
0x18000dea7  mov     eax, [rbp+40h]
0x18000deaa  add     rsp, 20h
0x18000deae  pop     rbp
0x18000deaf  retn
0x18000deb1  push    rbp
0x18000deb3  sub     rsp, 20h
0x18000deb7  mov     rbp, rdx
0x18000deba  mov     rax, [rcx]
0x18000debd  mov     edx, [rax]
0x18000debf  mov     [rbp+0B8h], rcx
0x18000dec6  mov     [rbp+48h], edx
0x18000dec9  mov     eax, [rbp+48h]
0x18000decc  cmp     eax, 0E06D7363h
0x18000ded1  jnz     short loc_18000DEE7
0x18000ded3  mov     rdx, [rbp+0B8h]
0x18000deda  mov     ecx, [rbp+48h]
0x18000dedd  call    _XcptFilter_0
0x18000dee2  mov     [rbp+50h], eax
0x18000dee5  jmp     short loc_18000DEEE
0x18000dee7  mov     dword ptr [rbp+50h], 0
0x18000deee  mov     eax, [rbp+50h]
0x18000def1  add     rsp, 20h
0x18000def5  pop     rbp
0x18000def6  retn
0x18000def8  push    rbp
0x18000defa  sub     rsp, 20h
0x18000defe  mov     rbp, rdx
0x18000df01  mov     rax, [rcx]
0x18000df04  mov     edx, [rax]
0x18000df06  mov     [rbp+0C0h], rcx
0x18000df0d  mov     [rbp+58h], edx
0x18000df10  mov     eax, [rbp+58h]
0x18000df13  cmp     eax, 0E06D7363h
0x18000df18  jnz     short loc_18000DF2E
0x18000df1a  mov     rdx, [rbp+0C0h]
0x18000df21  mov     ecx, [rbp+58h]
0x18000df24  call    _XcptFilter_0
0x18000df29  mov     [rbp+60h], eax
0x18000df2c  jmp     short loc_18000DF35
0x18000df2e  mov     dword ptr [rbp+60h], 0
0x18000df35  mov     eax, [rbp+60h]
0x18000df38  add     rsp, 20h
0x18000df3c  pop     rbp
0x18000df3d  retn
0x18000df3f  push    rbp
0x18000df41  sub     rsp, 20h
0x18000df45  mov     rbp, rdx
0x18000df48  mov     rax, [rcx]
0x18000df4b  mov     edx, [rax]
0x18000df4d  mov     [rbp+0C8h], rcx
0x18000df54  mov     [rbp+68h], edx
0x18000df57  mov     eax, [rbp+68h]
0x18000df5a  cmp     eax, 0E06D7363h
0x18000df5f  jnz     short loc_18000DF75
0x18000df61  mov     rdx, [rbp+0C8h]
0x18000df68  mov     ecx, [rbp+68h]
0x18000df6b  call    _XcptFilter_0
0x18000df70  mov     [rbp+70h], eax
0x18000df73  jmp     short loc_18000DF7C
0x18000df75  mov     dword ptr [rbp+70h], 0
0x18000df7c  mov     eax, [rbp+70h]
0x18000df7f  add     rsp, 20h
0x18000df83  pop     rbp
0x18000df84  retn
0x18000df86  push    rbp
0x18000df88  sub     rsp, 20h
0x18000df8c  mov     rbp, rdx
0x18000df8f  mov     rax, [rcx]
0x18000df92  mov     edx, [rax]
0x18000df94  mov     [rbp+0D0h], rcx
0x18000df9b  mov     [rbp+78h], edx
0x18000df9e  mov     eax, [rbp+78h]
0x18000dfa1  cmp     eax, 0E06D7363h
0x18000dfa6  jnz     short loc_18000DFBF
0x18000dfa8  mov     rdx, [rbp+0D0h]
0x18000dfaf  mov     ecx, [rbp+78h]
0x18000dfb2  call    _XcptFilter_0
0x18000dfb7  mov     [rbp+80h], eax
0x18000dfbd  jmp     short loc_18000DFC9
0x18000dfbf  mov     dword ptr [rbp+80h], 0
0x18000dfc9  mov     eax, [rbp+80h]
0x18000dfcf  add     rsp, 20h
0x18000dfd3  pop     rbp
0x18000dfd4  retn
0x18000dfd6  push    rbp
0x18000dfd8  sub     rsp, 20h
0x18000dfdc  mov     rbp, rdx
0x18000dfdf  mov     rax, [rcx]
0x18000dfe2  mov     edx, [rax]
0x18000dfe4  mov     [rbp+0D8h], rcx
0x18000dfeb  mov     [rbp+88h], edx
0x18000dff1  mov     eax, [rbp+88h]
0x18000dff7  cmp     eax, 0E06D7363h
0x18000dffc  jnz     short loc_18000E018
0x18000dffe  mov     rdx, [rbp+0D8h]
0x18000e005  mov     ecx, [rbp+88h]
0x18000e00b  call    _XcptFilter_0
0x18000e010  mov     [rbp+90h], eax
0x18000e016  jmp     short loc_18000E022
0x18000e018  mov     dword ptr [rbp+90h], 0
0x18000e022  mov     eax, [rbp+90h]
0x18000e028  add     rsp, 20h
0x18000e02c  pop     rbp
0x18000e02d  retn
0x18000e02f  push    rbp
0x18000e031  sub     rsp, 20h
0x18000e035  mov     rbp, rdx
0x18000e038  mov     rax, [rcx]
0x18000e03b  mov     edx, [rax]
0x18000e03d  mov     [rbp+0E0h], rcx
0x18000e044  mov     [rbp+98h], edx
0x18000e04a  mov     eax, [rbp+98h]
0x18000e050  cmp     eax, 0E06D7363h
0x18000e055  jnz     short loc_18000E071
0x18000e057  mov     rdx, [rbp+0E0h]
0x18000e05e  mov     ecx, [rbp+98h]
0x18000e064  call    _XcptFilter_0
0x18000e069  mov     [rbp+0A0h], eax
0x18000e06f  jmp     short loc_18000E07B
0x18000e071  mov     dword ptr [rbp+0A0h], 0
0x18000e07b  mov     eax, [rbp+0A0h]
0x18000e081  add     rsp, 20h
0x18000e085  pop     rbp
0x18000e086  retn
0x18000e088  push    rbp
0x18000e08a  sub     rsp, 20h
0x18000e08e  mov     rbp, rdx
0x18000e091  cmp     dword ptr [rbp+118h], 1
0x18000e098  ja      short loc_18000E0A4
0x18000e09a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
