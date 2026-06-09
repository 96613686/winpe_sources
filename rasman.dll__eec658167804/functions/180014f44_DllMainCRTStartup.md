# __DllMainCRTStartup

- ea: `0x180014f44`
- end: `0x180015150`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014f00`

## callees

- `0x180001500`
- `0x180014cd0`
- `0x180014f44`
- `0x180015162`
- `0x180026440`

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
  if ( (_DWORD)fdwReason || dword_180030240 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180030244 = 1;
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
            if ( dword_180030244 )
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
0x180014f44  mov     [rsp+lpvReserved], r8
0x180014f49  mov     [rsp+arg_8], edx
0x180014f4d  mov     [rsp+arg_0], rcx
0x180014f52  push    rbx
0x180014f53  push    rsi
0x180014f54  push    rdi
0x180014f55  sub     rsp, 0F0h
0x180014f5c  mov     edi, edx
0x180014f5e  mov     rsi, rcx
0x180014f61  mov     ebx, 1
0x180014f66  cmp     edx, ebx
0x180014f68  ja      short loc_180014F70
0x180014f6a  mov     cs:__native_dllmain_reason, edx
0x180014f70  test    edx, edx
0x180014f72  jnz     short loc_180014F87
0x180014f74  cmp     cs:dword_180030240, edx
0x180014f7a  jnz     short loc_180014F87
0x180014f7c  xor     ebx, ebx
0x180014f7e  mov     [rsp+108h+var_E8], ebx
0x180014f82  jmp     loc_180015134
0x180014f87  lea     eax, [rdx-1]
0x180014f8a  cmp     eax, 1
0x180014f8d  ja      loc_180015014
0x180014f93  mov     rax, cs:_pRawDllMain
0x180014f9a  test    rax, rax
0x180014f9d  jz      short loc_180014FD5
0x180014f9f  cmp     edx, 1
0x180014fa2  jnz     short loc_180014FAA
0x180014fa4  mov     cs:dword_180030244, edx
0x180014faa  mov     r8, [rsp+108h+lpvReserved]
0x180014fb2  call    cs:__guard_dispatch_icall_fptr
0x180014fb8  mov     ebx, eax
0x180014fba  mov     [rsp+108h+var_E8], eax
0x180014fbe  jmp     short loc_180014FD5
0x180014fc0  xor     ebx, ebx
0x180014fc2  mov     [rsp+108h+var_E8], ebx
0x180014fc6  mov     edi, [rsp+108h+arg_8]
0x180014fcd  mov     rsi, [rsp+108h+arg_0]
0x180014fd5  test    ebx, ebx
0x180014fd7  jz      loc_180015134
0x180014fdd  mov     r8, [rsp+108h+lpvReserved]
0x180014fe5  mov     edx, edi
0x180014fe7  mov     rcx, rsi
0x180014fea  call    _CRT_INIT
0x180014fef  mov     ebx, eax
0x180014ff1  mov     [rsp+108h+var_E8], eax
0x180014ff5  jmp     short loc_18001500C
0x180014ff7  xor     ebx, ebx
0x180014ff9  mov     [rsp+108h+var_E8], ebx
0x180014ffd  mov     edi, [rsp+108h+arg_8]
0x180015004  mov     rsi, [rsp+108h+arg_0]
0x18001500c  test    ebx, ebx
0x18001500e  jz      loc_180015134
0x180015014  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18001501c  mov     edx, edi; fdwReason
0x18001501e  mov     rcx, rsi; hinstDLL
0x180015021  call    DllMain
0x180015026  mov     ebx, eax
0x180015028  mov     [rsp+108h+var_E8], eax
0x18001502c  jmp     short loc_180015043
0x18001502e  xor     ebx, ebx
0x180015030  mov     [rsp+108h+var_E8], ebx
0x180015034  mov     edi, [rsp+108h+arg_8]
0x18001503b  mov     rsi, [rsp+108h+arg_0]
0x180015043  cmp     edi, 1
0x180015046  jnz     short loc_1800150BF
0x180015048  test    ebx, ebx
0x18001504a  jnz     short loc_1800150BF
0x18001504c  xor     r8d, r8d; lpvReserved
0x18001504f  xor     edx, edx; fdwReason
0x180015051  mov     rcx, rsi; hinstDLL
0x180015054  call    DllMain
0x180015059  jmp     short loc_18001506E
0x18001505b  mov     edi, [rsp+108h+arg_8]
0x180015062  mov     rsi, [rsp+108h+arg_0]
0x18001506a  mov     ebx, [rsp+108h+var_E8]
0x18001506e  xor     r8d, r8d
0x180015071  xor     edx, edx
0x180015073  mov     rcx, rsi
0x180015076  call    _CRT_INIT
0x18001507b  jmp     short loc_180015090
0x18001507d  mov     edi, [rsp+108h+arg_8]
0x180015084  mov     rsi, [rsp+108h+arg_0]
0x18001508c  mov     ebx, [rsp+108h+var_E8]
0x180015090  mov     rax, cs:_pRawDllMain
0x180015097  test    rax, rax
0x18001509a  jz      short loc_1800150BF
0x18001509c  xor     r8d, r8d
0x18001509f  xor     edx, edx
0x1800150a1  mov     rcx, rsi
0x1800150a4  call    cs:__guard_dispatch_icall_fptr
0x1800150aa  jmp     short loc_1800150BF
0x1800150ac  mov     edi, [rsp+108h+arg_8]
0x1800150b3  mov     rsi, [rsp+108h+arg_0]
0x1800150bb  mov     ebx, [rsp+108h+var_E8]
0x1800150bf  test    edi, edi
0x1800150c1  jz      short loc_1800150C8
0x1800150c3  cmp     edi, 3
0x1800150c6  jnz     short loc_180015134
0x1800150c8  mov     r8, [rsp+108h+lpvReserved]
0x1800150d0  mov     edx, edi
0x1800150d2  mov     rcx, rsi
0x1800150d5  call    _CRT_INIT
0x1800150da  mov     ebx, eax
0x1800150dc  mov     [rsp+108h+var_E8], eax
0x1800150e0  jmp     short loc_1800150F7
0x1800150e2  xor     ebx, ebx
0x1800150e4  mov     [rsp+108h+var_E8], ebx
0x1800150e8  mov     edi, [rsp+108h+arg_8]
0x1800150ef  mov     rsi, [rsp+108h+arg_0]
0x1800150f7  mov     rax, cs:_pRawDllMain
0x1800150fe  test    rax, rax
0x180015101  jz      short loc_180015134
0x180015103  cmp     cs:dword_180030244, 0
0x18001510a  jz      short loc_180015134
0x18001510c  mov     r8, [rsp+108h+lpvReserved]
0x180015114  mov     edx, edi
0x180015116  mov     rcx, rsi
0x180015119  call    cs:__guard_dispatch_icall_fptr
0x18001511f  mov     ebx, eax
0x180015121  mov     [rsp+108h+var_E8], eax
0x180015125  jmp     short loc_180015134
0x180015127  xor     ebx, ebx
0x180015129  mov     [rsp+108h+var_E8], ebx
0x18001512d  mov     edi, [rsp+108h+arg_8]
0x180015134  cmp     edi, 1
0x180015137  ja      short loc_180015143
0x180015139  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180015143  mov     eax, ebx
0x180015145  add     rsp, 0F0h
0x18001514c  pop     rdi
0x18001514d  pop     rsi
0x18001514e  pop     rbx
0x18001514f  retn
0x18002654a  push    rbp
0x18002654c  sub     rsp, 20h
0x180026550  mov     rbp, rdx
0x180026553  mov     rax, [rcx]
0x180026556  mov     edx, [rax]
0x180026558  mov     [rbp+0A8h], rcx
0x18002655f  mov     [rbp+28h], edx
0x180026562  mov     eax, [rbp+28h]
0x180026565  cmp     eax, 0E06D7363h
0x18002656a  jnz     short loc_180026580
0x18002656c  mov     rdx, [rbp+0A8h]
0x180026573  mov     ecx, [rbp+28h]
0x180026576  call    _XcptFilter_0
0x18002657b  mov     [rbp+30h], eax
0x18002657e  jmp     short loc_180026587
0x180026580  mov     dword ptr [rbp+30h], 0
0x180026587  mov     eax, [rbp+30h]
0x18002658a  add     rsp, 20h
0x18002658e  pop     rbp
0x18002658f  retn
0x180026591  push    rbp
0x180026593  sub     rsp, 20h
0x180026597  mov     rbp, rdx
0x18002659a  mov     rax, [rcx]
0x18002659d  mov     edx, [rax]
0x18002659f  mov     [rbp+0B0h], rcx
0x1800265a6  mov     [rbp+38h], edx
0x1800265a9  mov     eax, [rbp+38h]
0x1800265ac  cmp     eax, 0E06D7363h
0x1800265b1  jnz     short loc_1800265C7
0x1800265b3  mov     rdx, [rbp+0B0h]
0x1800265ba  mov     ecx, [rbp+38h]
0x1800265bd  call    _XcptFilter_0
0x1800265c2  mov     [rbp+40h], eax
0x1800265c5  jmp     short loc_1800265CE
0x1800265c7  mov     dword ptr [rbp+40h], 0
0x1800265ce  mov     eax, [rbp+40h]
0x1800265d1  add     rsp, 20h
0x1800265d5  pop     rbp
0x1800265d6  retn
0x1800265d8  push    rbp
0x1800265da  sub     rsp, 20h
0x1800265de  mov     rbp, rdx
0x1800265e1  mov     rax, [rcx]
0x1800265e4  mov     edx, [rax]
0x1800265e6  mov     [rbp+0B8h], rcx
0x1800265ed  mov     [rbp+48h], edx
0x1800265f0  mov     eax, [rbp+48h]
0x1800265f3  cmp     eax, 0E06D7363h
0x1800265f8  jnz     short loc_18002660E
0x1800265fa  mov     rdx, [rbp+0B8h]
0x180026601  mov     ecx, [rbp+48h]
0x180026604  call    _XcptFilter_0
0x180026609  mov     [rbp+50h], eax
0x18002660c  jmp     short loc_180026615
0x18002660e  mov     dword ptr [rbp+50h], 0
0x180026615  mov     eax, [rbp+50h]
0x180026618  add     rsp, 20h
0x18002661c  pop     rbp
0x18002661d  retn
0x18002661f  push    rbp
0x180026621  sub     rsp, 20h
0x180026625  mov     rbp, rdx
0x180026628  mov     rax, [rcx]
0x18002662b  mov     edx, [rax]
0x18002662d  mov     [rbp+0C0h], rcx
0x180026634  mov     [rbp+58h], edx
0x180026637  mov     eax, [rbp+58h]
0x18002663a  cmp     eax, 0E06D7363h
0x18002663f  jnz     short loc_180026655
0x180026641  mov     rdx, [rbp+0C0h]
0x180026648  mov     ecx, [rbp+58h]
0x18002664b  call    _XcptFilter_0
0x180026650  mov     [rbp+60h], eax
0x180026653  jmp     short loc_18002665C
0x180026655  mov     dword ptr [rbp+60h], 0
0x18002665c  mov     eax, [rbp+60h]
0x18002665f  add     rsp, 20h
0x180026663  pop     rbp
0x180026664  retn
0x180026666  push    rbp
0x180026668  sub     rsp, 20h
0x18002666c  mov     rbp, rdx
0x18002666f  mov     rax, [rcx]
0x180026672  mov     edx, [rax]
0x180026674  mov     [rbp+0C8h], rcx
0x18002667b  mov     [rbp+68h], edx
0x18002667e  mov     eax, [rbp+68h]
0x180026681  cmp     eax, 0E06D7363h
0x180026686  jnz     short loc_18002669C
0x180026688  mov     rdx, [rbp+0C8h]
0x18002668f  mov     ecx, [rbp+68h]
0x180026692  call    _XcptFilter_0
0x180026697  mov     [rbp+70h], eax
0x18002669a  jmp     short loc_1800266A3
0x18002669c  mov     dword ptr [rbp+70h], 0
0x1800266a3  mov     eax, [rbp+70h]
0x1800266a6  add     rsp, 20h
0x1800266aa  pop     rbp
0x1800266ab  retn
0x1800266ad  push    rbp
0x1800266af  sub     rsp, 20h
0x1800266b3  mov     rbp, rdx
0x1800266b6  mov     rax, [rcx]
0x1800266b9  mov     edx, [rax]
0x1800266bb  mov     [rbp+0D0h], rcx
0x1800266c2  mov     [rbp+78h], edx
0x1800266c5  mov     eax, [rbp+78h]
0x1800266c8  cmp     eax, 0E06D7363h
0x1800266cd  jnz     short loc_1800266E6
0x1800266cf  mov     rdx, [rbp+0D0h]
0x1800266d6  mov     ecx, [rbp+78h]
0x1800266d9  call    _XcptFilter_0
0x1800266de  mov     [rbp+80h], eax
0x1800266e4  jmp     short loc_1800266F0
0x1800266e6  mov     dword ptr [rbp+80h], 0
0x1800266f0  mov     eax, [rbp+80h]
0x1800266f6  add     rsp, 20h
0x1800266fa  pop     rbp
0x1800266fb  retn
0x1800266fd  push    rbp
0x1800266ff  sub     rsp, 20h
0x180026703  mov     rbp, rdx
0x180026706  mov     rax, [rcx]
0x180026709  mov     edx, [rax]
0x18002670b  mov     [rbp+0D8h], rcx
0x180026712  mov     [rbp+88h], edx
0x180026718  mov     eax, [rbp+88h]
0x18002671e  cmp     eax, 0E06D7363h
0x180026723  jnz     short loc_18002673F
0x180026725  mov     rdx, [rbp+0D8h]
0x18002672c  mov     ecx, [rbp+88h]
0x180026732  call    _XcptFilter_0
0x180026737  mov     [rbp+90h], eax
0x18002673d  jmp     short loc_180026749
0x18002673f  mov     dword ptr [rbp+90h], 0
0x180026749  mov     eax, [rbp+90h]
0x18002674f  add     rsp, 20h
0x180026753  pop     rbp
0x180026754  retn
0x180026756  push    rbp
0x180026758  sub     rsp, 20h
0x18002675c  mov     rbp, rdx
0x18002675f  mov     rax, [rcx]
0x180026762  mov     edx, [rax]
0x180026764  mov     [rbp+0E0h], rcx
0x18002676b  mov     [rbp+98h], edx
0x180026771  mov     eax, [rbp+98h]
0x180026777  cmp     eax, 0E06D7363h
0x18002677c  jnz     short loc_180026798
0x18002677e  mov     rdx, [rbp+0E0h]
0x180026785  mov     ecx, [rbp+98h]
0x18002678b  call    _XcptFilter_0
0x180026790  mov     [rbp+0A0h], eax
0x180026796  jmp     short loc_1800267A2
0x180026798  mov     dword ptr [rbp+0A0h], 0
0x1800267a2  mov     eax, [rbp+0A0h]
0x1800267a8  add     rsp, 20h
0x1800267ac  pop     rbp
0x1800267ad  retn
0x1800267af  push    rbp
0x1800267b1  sub     rsp, 20h
0x1800267b5  mov     rbp, rdx
0x1800267b8  cmp     dword ptr [rbp+118h], 1
0x1800267bf  ja      short loc_1800267CB
0x1800267c1  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
