# __DllMainCRTStartup

- ea: `0x1800158e4`
- end: `0x180015af0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800158a0`

## callees

- `0x180001450`
- `0x180015670`
- `0x1800158e4`
- `0x180015b02`
- `0x180027410`

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
  if ( (_DWORD)fdwReason || dword_180031240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180031244 = 1;
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
            if ( dword_180031244 )
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
0x1800158e4  mov     [rsp+lpvReserved], r8
0x1800158e9  mov     [rsp+arg_8], edx
0x1800158ed  mov     [rsp+arg_0], rcx
0x1800158f2  push    rbx
0x1800158f3  push    rsi
0x1800158f4  push    rdi
0x1800158f5  sub     rsp, 0F0h
0x1800158fc  mov     edi, edx
0x1800158fe  mov     rsi, rcx
0x180015901  mov     ebx, 1
0x180015906  cmp     edx, ebx
0x180015908  ja      short loc_180015910
0x18001590a  mov     cs:__native_dllmain_reason, edx
0x180015910  test    edx, edx
0x180015912  jnz     short loc_180015927
0x180015914  cmp     cs:dword_180031240, edx
0x18001591a  jnz     short loc_180015927
0x18001591c  xor     ebx, ebx
0x18001591e  mov     [rsp+108h+var_E8], ebx
0x180015922  jmp     loc_180015AD4
0x180015927  lea     eax, [rdx-1]
0x18001592a  cmp     eax, 1
0x18001592d  ja      loc_1800159B4
0x180015933  mov     rax, cs:_pRawDllMain
0x18001593a  test    rax, rax
0x18001593d  jz      short loc_180015975
0x18001593f  cmp     edx, 1
0x180015942  jnz     short loc_18001594A
0x180015944  mov     cs:dword_180031244, edx
0x18001594a  mov     r8, [rsp+108h+lpvReserved]
0x180015952  call    cs:__guard_dispatch_icall_fptr
0x180015958  mov     ebx, eax
0x18001595a  mov     [rsp+108h+var_E8], eax
0x18001595e  jmp     short loc_180015975
0x180015960  xor     ebx, ebx
0x180015962  mov     [rsp+108h+var_E8], ebx
0x180015966  mov     edi, [rsp+108h+arg_8]
0x18001596d  mov     rsi, [rsp+108h+arg_0]
0x180015975  test    ebx, ebx
0x180015977  jz      loc_180015AD4
0x18001597d  mov     r8, [rsp+108h+lpvReserved]
0x180015985  mov     edx, edi
0x180015987  mov     rcx, rsi
0x18001598a  call    _CRT_INIT
0x18001598f  mov     ebx, eax
0x180015991  mov     [rsp+108h+var_E8], eax
0x180015995  jmp     short loc_1800159AC
0x180015997  xor     ebx, ebx
0x180015999  mov     [rsp+108h+var_E8], ebx
0x18001599d  mov     edi, [rsp+108h+arg_8]
0x1800159a4  mov     rsi, [rsp+108h+arg_0]
0x1800159ac  test    ebx, ebx
0x1800159ae  jz      loc_180015AD4
0x1800159b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800159bc  mov     edx, edi; fdwReason
0x1800159be  mov     rcx, rsi; hinstDLL
0x1800159c1  call    DllMain
0x1800159c6  mov     ebx, eax
0x1800159c8  mov     [rsp+108h+var_E8], eax
0x1800159cc  jmp     short loc_1800159E3
0x1800159ce  xor     ebx, ebx
0x1800159d0  mov     [rsp+108h+var_E8], ebx
0x1800159d4  mov     edi, [rsp+108h+arg_8]
0x1800159db  mov     rsi, [rsp+108h+arg_0]
0x1800159e3  cmp     edi, 1
0x1800159e6  jnz     short loc_180015A5F
0x1800159e8  test    ebx, ebx
0x1800159ea  jnz     short loc_180015A5F
0x1800159ec  xor     r8d, r8d; lpvReserved
0x1800159ef  xor     edx, edx; fdwReason
0x1800159f1  mov     rcx, rsi; hinstDLL
0x1800159f4  call    DllMain
0x1800159f9  jmp     short loc_180015A0E
0x1800159fb  mov     edi, [rsp+108h+arg_8]
0x180015a02  mov     rsi, [rsp+108h+arg_0]
0x180015a0a  mov     ebx, [rsp+108h+var_E8]
0x180015a0e  xor     r8d, r8d
0x180015a11  xor     edx, edx
0x180015a13  mov     rcx, rsi
0x180015a16  call    _CRT_INIT
0x180015a1b  jmp     short loc_180015A30
0x180015a1d  mov     edi, [rsp+108h+arg_8]
0x180015a24  mov     rsi, [rsp+108h+arg_0]
0x180015a2c  mov     ebx, [rsp+108h+var_E8]
0x180015a30  mov     rax, cs:_pRawDllMain
0x180015a37  test    rax, rax
0x180015a3a  jz      short loc_180015A5F
0x180015a3c  xor     r8d, r8d
0x180015a3f  xor     edx, edx
0x180015a41  mov     rcx, rsi
0x180015a44  call    cs:__guard_dispatch_icall_fptr
0x180015a4a  jmp     short loc_180015A5F
0x180015a4c  mov     edi, [rsp+108h+arg_8]
0x180015a53  mov     rsi, [rsp+108h+arg_0]
0x180015a5b  mov     ebx, [rsp+108h+var_E8]
0x180015a5f  test    edi, edi
0x180015a61  jz      short loc_180015A68
0x180015a63  cmp     edi, 3
0x180015a66  jnz     short loc_180015AD4
0x180015a68  mov     r8, [rsp+108h+lpvReserved]
0x180015a70  mov     edx, edi
0x180015a72  mov     rcx, rsi
0x180015a75  call    _CRT_INIT
0x180015a7a  mov     ebx, eax
0x180015a7c  mov     [rsp+108h+var_E8], eax
0x180015a80  jmp     short loc_180015A97
0x180015a82  xor     ebx, ebx
0x180015a84  mov     [rsp+108h+var_E8], ebx
0x180015a88  mov     edi, [rsp+108h+arg_8]
0x180015a8f  mov     rsi, [rsp+108h+arg_0]
0x180015a97  mov     rax, cs:_pRawDllMain
0x180015a9e  test    rax, rax
0x180015aa1  jz      short loc_180015AD4
0x180015aa3  cmp     cs:dword_180031244, 0
0x180015aaa  jz      short loc_180015AD4
0x180015aac  mov     r8, [rsp+108h+lpvReserved]
0x180015ab4  mov     edx, edi
0x180015ab6  mov     rcx, rsi
0x180015ab9  call    cs:__guard_dispatch_icall_fptr
0x180015abf  mov     ebx, eax
0x180015ac1  mov     [rsp+108h+var_E8], eax
0x180015ac5  jmp     short loc_180015AD4
0x180015ac7  xor     ebx, ebx
0x180015ac9  mov     [rsp+108h+var_E8], ebx
0x180015acd  mov     edi, [rsp+108h+arg_8]
0x180015ad4  cmp     edi, 1
0x180015ad7  ja      short loc_180015AE3
0x180015ad9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180015ae3  mov     eax, ebx
0x180015ae5  add     rsp, 0F0h
0x180015aec  pop     rdi
0x180015aed  pop     rsi
0x180015aee  pop     rbx
0x180015aef  retn
0x180027536  push    rbp
0x180027538  sub     rsp, 20h
0x18002753c  mov     rbp, rdx
0x18002753f  mov     rax, [rcx]
0x180027542  mov     edx, [rax]
0x180027544  mov     [rbp+0A8h], rcx
0x18002754b  mov     [rbp+28h], edx
0x18002754e  mov     eax, [rbp+28h]
0x180027551  cmp     eax, 0E06D7363h
0x180027556  jnz     short loc_18002756C
0x180027558  mov     rdx, [rbp+0A8h]
0x18002755f  mov     ecx, [rbp+28h]
0x180027562  call    _XcptFilter_0
0x180027567  mov     [rbp+30h], eax
0x18002756a  jmp     short loc_180027573
0x18002756c  mov     dword ptr [rbp+30h], 0
0x180027573  mov     eax, [rbp+30h]
0x180027576  add     rsp, 20h
0x18002757a  pop     rbp
0x18002757b  retn
0x18002757d  push    rbp
0x18002757f  sub     rsp, 20h
0x180027583  mov     rbp, rdx
0x180027586  mov     rax, [rcx]
0x180027589  mov     edx, [rax]
0x18002758b  mov     [rbp+0B0h], rcx
0x180027592  mov     [rbp+38h], edx
0x180027595  mov     eax, [rbp+38h]
0x180027598  cmp     eax, 0E06D7363h
0x18002759d  jnz     short loc_1800275B3
0x18002759f  mov     rdx, [rbp+0B0h]
0x1800275a6  mov     ecx, [rbp+38h]
0x1800275a9  call    _XcptFilter_0
0x1800275ae  mov     [rbp+40h], eax
0x1800275b1  jmp     short loc_1800275BA
0x1800275b3  mov     dword ptr [rbp+40h], 0
0x1800275ba  mov     eax, [rbp+40h]
0x1800275bd  add     rsp, 20h
0x1800275c1  pop     rbp
0x1800275c2  retn
0x1800275c4  push    rbp
0x1800275c6  sub     rsp, 20h
0x1800275ca  mov     rbp, rdx
0x1800275cd  mov     rax, [rcx]
0x1800275d0  mov     edx, [rax]
0x1800275d2  mov     [rbp+0B8h], rcx
0x1800275d9  mov     [rbp+48h], edx
0x1800275dc  mov     eax, [rbp+48h]
0x1800275df  cmp     eax, 0E06D7363h
0x1800275e4  jnz     short loc_1800275FA
0x1800275e6  mov     rdx, [rbp+0B8h]
0x1800275ed  mov     ecx, [rbp+48h]
0x1800275f0  call    _XcptFilter_0
0x1800275f5  mov     [rbp+50h], eax
0x1800275f8  jmp     short loc_180027601
0x1800275fa  mov     dword ptr [rbp+50h], 0
0x180027601  mov     eax, [rbp+50h]
0x180027604  add     rsp, 20h
0x180027608  pop     rbp
0x180027609  retn
0x18002760b  push    rbp
0x18002760d  sub     rsp, 20h
0x180027611  mov     rbp, rdx
0x180027614  mov     rax, [rcx]
0x180027617  mov     edx, [rax]
0x180027619  mov     [rbp+0C0h], rcx
0x180027620  mov     [rbp+58h], edx
0x180027623  mov     eax, [rbp+58h]
0x180027626  cmp     eax, 0E06D7363h
0x18002762b  jnz     short loc_180027641
0x18002762d  mov     rdx, [rbp+0C0h]
0x180027634  mov     ecx, [rbp+58h]
0x180027637  call    _XcptFilter_0
0x18002763c  mov     [rbp+60h], eax
0x18002763f  jmp     short loc_180027648
0x180027641  mov     dword ptr [rbp+60h], 0
0x180027648  mov     eax, [rbp+60h]
0x18002764b  add     rsp, 20h
0x18002764f  pop     rbp
0x180027650  retn
0x180027652  push    rbp
0x180027654  sub     rsp, 20h
0x180027658  mov     rbp, rdx
0x18002765b  mov     rax, [rcx]
0x18002765e  mov     edx, [rax]
0x180027660  mov     [rbp+0C8h], rcx
0x180027667  mov     [rbp+68h], edx
0x18002766a  mov     eax, [rbp+68h]
0x18002766d  cmp     eax, 0E06D7363h
0x180027672  jnz     short loc_180027688
0x180027674  mov     rdx, [rbp+0C8h]
0x18002767b  mov     ecx, [rbp+68h]
0x18002767e  call    _XcptFilter_0
0x180027683  mov     [rbp+70h], eax
0x180027686  jmp     short loc_18002768F
0x180027688  mov     dword ptr [rbp+70h], 0
0x18002768f  mov     eax, [rbp+70h]
0x180027692  add     rsp, 20h
0x180027696  pop     rbp
0x180027697  retn
0x180027699  push    rbp
0x18002769b  sub     rsp, 20h
0x18002769f  mov     rbp, rdx
0x1800276a2  mov     rax, [rcx]
0x1800276a5  mov     edx, [rax]
0x1800276a7  mov     [rbp+0D0h], rcx
0x1800276ae  mov     [rbp+78h], edx
0x1800276b1  mov     eax, [rbp+78h]
0x1800276b4  cmp     eax, 0E06D7363h
0x1800276b9  jnz     short loc_1800276D2
0x1800276bb  mov     rdx, [rbp+0D0h]
0x1800276c2  mov     ecx, [rbp+78h]
0x1800276c5  call    _XcptFilter_0
0x1800276ca  mov     [rbp+80h], eax
0x1800276d0  jmp     short loc_1800276DC
0x1800276d2  mov     dword ptr [rbp+80h], 0
0x1800276dc  mov     eax, [rbp+80h]
0x1800276e2  add     rsp, 20h
0x1800276e6  pop     rbp
0x1800276e7  retn
0x1800276e9  push    rbp
0x1800276eb  sub     rsp, 20h
0x1800276ef  mov     rbp, rdx
0x1800276f2  mov     rax, [rcx]
0x1800276f5  mov     edx, [rax]
0x1800276f7  mov     [rbp+0D8h], rcx
0x1800276fe  mov     [rbp+88h], edx
0x180027704  mov     eax, [rbp+88h]
0x18002770a  cmp     eax, 0E06D7363h
0x18002770f  jnz     short loc_18002772B
0x180027711  mov     rdx, [rbp+0D8h]
0x180027718  mov     ecx, [rbp+88h]
0x18002771e  call    _XcptFilter_0
0x180027723  mov     [rbp+90h], eax
0x180027729  jmp     short loc_180027735
0x18002772b  mov     dword ptr [rbp+90h], 0
0x180027735  mov     eax, [rbp+90h]
0x18002773b  add     rsp, 20h
0x18002773f  pop     rbp
0x180027740  retn
0x180027742  push    rbp
0x180027744  sub     rsp, 20h
0x180027748  mov     rbp, rdx
0x18002774b  mov     rax, [rcx]
0x18002774e  mov     edx, [rax]
0x180027750  mov     [rbp+0E0h], rcx
0x180027757  mov     [rbp+98h], edx
0x18002775d  mov     eax, [rbp+98h]
0x180027763  cmp     eax, 0E06D7363h
0x180027768  jnz     short loc_180027784
0x18002776a  mov     rdx, [rbp+0E0h]
0x180027771  mov     ecx, [rbp+98h]
0x180027777  call    _XcptFilter_0
0x18002777c  mov     [rbp+0A0h], eax
0x180027782  jmp     short loc_18002778E
0x180027784  mov     dword ptr [rbp+0A0h], 0
0x18002778e  mov     eax, [rbp+0A0h]
0x180027794  add     rsp, 20h
0x180027798  pop     rbp
0x180027799  retn
0x18002779b  push    rbp
0x18002779d  sub     rsp, 20h
0x1800277a1  mov     rbp, rdx
0x1800277a4  cmp     dword ptr [rbp+118h], 1
0x1800277ab  ja      short loc_1800277B7
0x1800277ad  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
