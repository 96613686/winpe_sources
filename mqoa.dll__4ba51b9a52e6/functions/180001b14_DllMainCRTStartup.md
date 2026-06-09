# __DllMainCRTStartup

- ea: `0x180001b14`
- end: `0x180001d20`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ad0`

## callees

- `0x180001270`
- `0x1800018a0`
- `0x180001b14`
- `0x1800024cb`
- `0x180027420`

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
  if ( (_DWORD)fdwReason || dword_180037E20 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180037E24 = 1;
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
            if ( dword_180037E24 )
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
0x180001b14  mov     [rsp+lpvReserved], r8
0x180001b19  mov     [rsp+arg_8], edx
0x180001b1d  mov     [rsp+arg_0], rcx
0x180001b22  push    rbx
0x180001b23  push    rsi
0x180001b24  push    rdi
0x180001b25  sub     rsp, 0F0h
0x180001b2c  mov     edi, edx
0x180001b2e  mov     rsi, rcx
0x180001b31  mov     ebx, 1
0x180001b36  cmp     edx, ebx
0x180001b38  ja      short loc_180001B40
0x180001b3a  mov     cs:__native_dllmain_reason, edx
0x180001b40  test    edx, edx
0x180001b42  jnz     short loc_180001B57
0x180001b44  cmp     cs:dword_180037E20, edx
0x180001b4a  jnz     short loc_180001B57
0x180001b4c  xor     ebx, ebx
0x180001b4e  mov     [rsp+108h+var_E8], ebx
0x180001b52  jmp     loc_180001D04
0x180001b57  lea     eax, [rdx-1]
0x180001b5a  cmp     eax, 1
0x180001b5d  ja      loc_180001BE4
0x180001b63  mov     rax, cs:_pRawDllMain
0x180001b6a  test    rax, rax
0x180001b6d  jz      short loc_180001BA5
0x180001b6f  cmp     edx, 1
0x180001b72  jnz     short loc_180001B7A
0x180001b74  mov     cs:dword_180037E24, edx
0x180001b7a  mov     r8, [rsp+108h+lpvReserved]
0x180001b82  call    cs:__guard_dispatch_icall_fptr
0x180001b88  mov     ebx, eax
0x180001b8a  mov     [rsp+108h+var_E8], eax
0x180001b8e  jmp     short loc_180001BA5
0x180001b90  xor     ebx, ebx
0x180001b92  mov     [rsp+108h+var_E8], ebx
0x180001b96  mov     edi, [rsp+108h+arg_8]
0x180001b9d  mov     rsi, [rsp+108h+arg_0]
0x180001ba5  test    ebx, ebx
0x180001ba7  jz      loc_180001D04
0x180001bad  mov     r8, [rsp+108h+lpvReserved]
0x180001bb5  mov     edx, edi
0x180001bb7  mov     rcx, rsi
0x180001bba  call    _CRT_INIT
0x180001bbf  mov     ebx, eax
0x180001bc1  mov     [rsp+108h+var_E8], eax
0x180001bc5  jmp     short loc_180001BDC
0x180001bc7  xor     ebx, ebx
0x180001bc9  mov     [rsp+108h+var_E8], ebx
0x180001bcd  mov     edi, [rsp+108h+arg_8]
0x180001bd4  mov     rsi, [rsp+108h+arg_0]
0x180001bdc  test    ebx, ebx
0x180001bde  jz      loc_180001D04
0x180001be4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001bec  mov     edx, edi; fdwReason
0x180001bee  mov     rcx, rsi; hinstDLL
0x180001bf1  call    DllMain
0x180001bf6  mov     ebx, eax
0x180001bf8  mov     [rsp+108h+var_E8], eax
0x180001bfc  jmp     short loc_180001C13
0x180001bfe  xor     ebx, ebx
0x180001c00  mov     [rsp+108h+var_E8], ebx
0x180001c04  mov     edi, [rsp+108h+arg_8]
0x180001c0b  mov     rsi, [rsp+108h+arg_0]
0x180001c13  cmp     edi, 1
0x180001c16  jnz     short loc_180001C8F
0x180001c18  test    ebx, ebx
0x180001c1a  jnz     short loc_180001C8F
0x180001c1c  xor     r8d, r8d; lpvReserved
0x180001c1f  xor     edx, edx; fdwReason
0x180001c21  mov     rcx, rsi; hinstDLL
0x180001c24  call    DllMain
0x180001c29  jmp     short loc_180001C3E
0x180001c2b  mov     edi, [rsp+108h+arg_8]
0x180001c32  mov     rsi, [rsp+108h+arg_0]
0x180001c3a  mov     ebx, [rsp+108h+var_E8]
0x180001c3e  xor     r8d, r8d
0x180001c41  xor     edx, edx
0x180001c43  mov     rcx, rsi
0x180001c46  call    _CRT_INIT
0x180001c4b  jmp     short loc_180001C60
0x180001c4d  mov     edi, [rsp+108h+arg_8]
0x180001c54  mov     rsi, [rsp+108h+arg_0]
0x180001c5c  mov     ebx, [rsp+108h+var_E8]
0x180001c60  mov     rax, cs:_pRawDllMain
0x180001c67  test    rax, rax
0x180001c6a  jz      short loc_180001C8F
0x180001c6c  xor     r8d, r8d
0x180001c6f  xor     edx, edx
0x180001c71  mov     rcx, rsi
0x180001c74  call    cs:__guard_dispatch_icall_fptr
0x180001c7a  jmp     short loc_180001C8F
0x180001c7c  mov     edi, [rsp+108h+arg_8]
0x180001c83  mov     rsi, [rsp+108h+arg_0]
0x180001c8b  mov     ebx, [rsp+108h+var_E8]
0x180001c8f  test    edi, edi
0x180001c91  jz      short loc_180001C98
0x180001c93  cmp     edi, 3
0x180001c96  jnz     short loc_180001D04
0x180001c98  mov     r8, [rsp+108h+lpvReserved]
0x180001ca0  mov     edx, edi
0x180001ca2  mov     rcx, rsi
0x180001ca5  call    _CRT_INIT
0x180001caa  mov     ebx, eax
0x180001cac  mov     [rsp+108h+var_E8], eax
0x180001cb0  jmp     short loc_180001CC7
0x180001cb2  xor     ebx, ebx
0x180001cb4  mov     [rsp+108h+var_E8], ebx
0x180001cb8  mov     edi, [rsp+108h+arg_8]
0x180001cbf  mov     rsi, [rsp+108h+arg_0]
0x180001cc7  mov     rax, cs:_pRawDllMain
0x180001cce  test    rax, rax
0x180001cd1  jz      short loc_180001D04
0x180001cd3  cmp     cs:dword_180037E24, 0
0x180001cda  jz      short loc_180001D04
0x180001cdc  mov     r8, [rsp+108h+lpvReserved]
0x180001ce4  mov     edx, edi
0x180001ce6  mov     rcx, rsi
0x180001ce9  call    cs:__guard_dispatch_icall_fptr
0x180001cef  mov     ebx, eax
0x180001cf1  mov     [rsp+108h+var_E8], eax
0x180001cf5  jmp     short loc_180001D04
0x180001cf7  xor     ebx, ebx
0x180001cf9  mov     [rsp+108h+var_E8], ebx
0x180001cfd  mov     edi, [rsp+108h+arg_8]
0x180001d04  cmp     edi, 1
0x180001d07  ja      short loc_180001D13
0x180001d09  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001d13  mov     eax, ebx
0x180001d15  add     rsp, 0F0h
0x180001d1c  pop     rdi
0x180001d1d  pop     rsi
0x180001d1e  pop     rbx
0x180001d1f  retn
0x180027506  push    rbp
0x180027508  sub     rsp, 20h
0x18002750c  mov     rbp, rdx
0x18002750f  mov     rax, [rcx]
0x180027512  mov     edx, [rax]
0x180027514  mov     [rbp+0A8h], rcx
0x18002751b  mov     [rbp+28h], edx
0x18002751e  mov     eax, [rbp+28h]
0x180027521  cmp     eax, 0E06D7363h
0x180027526  jnz     short loc_18002753C
0x180027528  mov     rdx, [rbp+0A8h]
0x18002752f  mov     ecx, [rbp+28h]
0x180027532  call    _XcptFilter_0
0x180027537  mov     [rbp+30h], eax
0x18002753a  jmp     short loc_180027543
0x18002753c  mov     dword ptr [rbp+30h], 0
0x180027543  mov     eax, [rbp+30h]
0x180027546  add     rsp, 20h
0x18002754a  pop     rbp
0x18002754b  retn
0x18002754d  push    rbp
0x18002754f  sub     rsp, 20h
0x180027553  mov     rbp, rdx
0x180027556  mov     rax, [rcx]
0x180027559  mov     edx, [rax]
0x18002755b  mov     [rbp+0B0h], rcx
0x180027562  mov     [rbp+38h], edx
0x180027565  mov     eax, [rbp+38h]
0x180027568  cmp     eax, 0E06D7363h
0x18002756d  jnz     short loc_180027583
0x18002756f  mov     rdx, [rbp+0B0h]
0x180027576  mov     ecx, [rbp+38h]
0x180027579  call    _XcptFilter_0
0x18002757e  mov     [rbp+40h], eax
0x180027581  jmp     short loc_18002758A
0x180027583  mov     dword ptr [rbp+40h], 0
0x18002758a  mov     eax, [rbp+40h]
0x18002758d  add     rsp, 20h
0x180027591  pop     rbp
0x180027592  retn
0x180027594  push    rbp
0x180027596  sub     rsp, 20h
0x18002759a  mov     rbp, rdx
0x18002759d  mov     rax, [rcx]
0x1800275a0  mov     edx, [rax]
0x1800275a2  mov     [rbp+0B8h], rcx
0x1800275a9  mov     [rbp+48h], edx
0x1800275ac  mov     eax, [rbp+48h]
0x1800275af  cmp     eax, 0E06D7363h
0x1800275b4  jnz     short loc_1800275CA
0x1800275b6  mov     rdx, [rbp+0B8h]
0x1800275bd  mov     ecx, [rbp+48h]
0x1800275c0  call    _XcptFilter_0
0x1800275c5  mov     [rbp+50h], eax
0x1800275c8  jmp     short loc_1800275D1
0x1800275ca  mov     dword ptr [rbp+50h], 0
0x1800275d1  mov     eax, [rbp+50h]
0x1800275d4  add     rsp, 20h
0x1800275d8  pop     rbp
0x1800275d9  retn
0x1800275db  push    rbp
0x1800275dd  sub     rsp, 20h
0x1800275e1  mov     rbp, rdx
0x1800275e4  mov     rax, [rcx]
0x1800275e7  mov     edx, [rax]
0x1800275e9  mov     [rbp+0C0h], rcx
0x1800275f0  mov     [rbp+58h], edx
0x1800275f3  mov     eax, [rbp+58h]
0x1800275f6  cmp     eax, 0E06D7363h
0x1800275fb  jnz     short loc_180027611
0x1800275fd  mov     rdx, [rbp+0C0h]
0x180027604  mov     ecx, [rbp+58h]
0x180027607  call    _XcptFilter_0
0x18002760c  mov     [rbp+60h], eax
0x18002760f  jmp     short loc_180027618
0x180027611  mov     dword ptr [rbp+60h], 0
0x180027618  mov     eax, [rbp+60h]
0x18002761b  add     rsp, 20h
0x18002761f  pop     rbp
0x180027620  retn
0x180027622  push    rbp
0x180027624  sub     rsp, 20h
0x180027628  mov     rbp, rdx
0x18002762b  mov     rax, [rcx]
0x18002762e  mov     edx, [rax]
0x180027630  mov     [rbp+0C8h], rcx
0x180027637  mov     [rbp+68h], edx
0x18002763a  mov     eax, [rbp+68h]
0x18002763d  cmp     eax, 0E06D7363h
0x180027642  jnz     short loc_180027658
0x180027644  mov     rdx, [rbp+0C8h]
0x18002764b  mov     ecx, [rbp+68h]
0x18002764e  call    _XcptFilter_0
0x180027653  mov     [rbp+70h], eax
0x180027656  jmp     short loc_18002765F
0x180027658  mov     dword ptr [rbp+70h], 0
0x18002765f  mov     eax, [rbp+70h]
0x180027662  add     rsp, 20h
0x180027666  pop     rbp
0x180027667  retn
0x180027669  push    rbp
0x18002766b  sub     rsp, 20h
0x18002766f  mov     rbp, rdx
0x180027672  mov     rax, [rcx]
0x180027675  mov     edx, [rax]
0x180027677  mov     [rbp+0D0h], rcx
0x18002767e  mov     [rbp+78h], edx
0x180027681  mov     eax, [rbp+78h]
0x180027684  cmp     eax, 0E06D7363h
0x180027689  jnz     short loc_1800276A2
0x18002768b  mov     rdx, [rbp+0D0h]
0x180027692  mov     ecx, [rbp+78h]
0x180027695  call    _XcptFilter_0
0x18002769a  mov     [rbp+80h], eax
0x1800276a0  jmp     short loc_1800276AC
0x1800276a2  mov     dword ptr [rbp+80h], 0
0x1800276ac  mov     eax, [rbp+80h]
0x1800276b2  add     rsp, 20h
0x1800276b6  pop     rbp
0x1800276b7  retn
0x1800276b9  push    rbp
0x1800276bb  sub     rsp, 20h
0x1800276bf  mov     rbp, rdx
0x1800276c2  mov     rax, [rcx]
0x1800276c5  mov     edx, [rax]
0x1800276c7  mov     [rbp+0D8h], rcx
0x1800276ce  mov     [rbp+88h], edx
0x1800276d4  mov     eax, [rbp+88h]
0x1800276da  cmp     eax, 0E06D7363h
0x1800276df  jnz     short loc_1800276FB
0x1800276e1  mov     rdx, [rbp+0D8h]
0x1800276e8  mov     ecx, [rbp+88h]
0x1800276ee  call    _XcptFilter_0
0x1800276f3  mov     [rbp+90h], eax
0x1800276f9  jmp     short loc_180027705
0x1800276fb  mov     dword ptr [rbp+90h], 0
0x180027705  mov     eax, [rbp+90h]
0x18002770b  add     rsp, 20h
0x18002770f  pop     rbp
0x180027710  retn
0x180027712  push    rbp
0x180027714  sub     rsp, 20h
0x180027718  mov     rbp, rdx
0x18002771b  mov     rax, [rcx]
0x18002771e  mov     edx, [rax]
0x180027720  mov     [rbp+0E0h], rcx
0x180027727  mov     [rbp+98h], edx
0x18002772d  mov     eax, [rbp+98h]
0x180027733  cmp     eax, 0E06D7363h
0x180027738  jnz     short loc_180027754
0x18002773a  mov     rdx, [rbp+0E0h]
0x180027741  mov     ecx, [rbp+98h]
0x180027747  call    _XcptFilter_0
0x18002774c  mov     [rbp+0A0h], eax
0x180027752  jmp     short loc_18002775E
0x180027754  mov     dword ptr [rbp+0A0h], 0
0x18002775e  mov     eax, [rbp+0A0h]
0x180027764  add     rsp, 20h
0x180027768  pop     rbp
0x180027769  retn
0x18002776b  push    rbp
0x18002776d  sub     rsp, 20h
0x180027771  mov     rbp, rdx
0x180027774  cmp     dword ptr [rbp+118h], 1
0x18002777b  ja      short loc_180027787
0x18002777d  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
