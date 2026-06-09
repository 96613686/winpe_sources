# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001531`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x18000109c`
- `0x180001324`
- `0x18000156a`
- `0x180001fe4`
- `0x180003010`

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
0x180001324  mov     [rsp+lpvReserved], r8
0x180001329  mov     [rsp+arg_8], edx
0x18000132d  mov     [rsp+arg_0], rcx
0x180001332  push    rbx
0x180001333  push    rsi
0x180001334  push    rdi
0x180001335  sub     rsp, 150h
0x18000133c  mov     edi, edx
0x18000133e  mov     rsi, rcx
0x180001341  mov     ebx, 1
0x180001346  mov     [rsp+168h+var_148], ebx
0x18000134a  cmp     edx, ebx
0x18000134c  ja      short loc_180001354
0x18000134e  mov     cs:__native_dllmain_reason, edx
0x180001354  test    edx, edx
0x180001356  jnz     short loc_18000136B
0x180001358  cmp     cs:dword_1800060A0, edx
0x18000135e  jnz     short loc_18000136B
0x180001360  xor     ebx, ebx
0x180001362  mov     [rsp+168h+var_148], ebx
0x180001366  jmp     loc_180001515
0x18000136b  lea     eax, [rdx-1]
0x18000136e  cmp     eax, 1
0x180001371  ja      loc_1800013F7
0x180001377  mov     rax, cs:_pRawDllMain
0x18000137e  test    rax, rax
0x180001381  jz      short loc_1800013B8
0x180001383  cmp     edx, 1
0x180001386  jnz     short loc_18000138E
0x180001388  mov     cs:dword_1800060A4, edx
0x18000138e  mov     r8, [rsp+168h+lpvReserved]
0x180001396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000139b  mov     ebx, eax
0x18000139d  mov     [rsp+168h+var_148], eax
0x1800013a1  jmp     short loc_1800013B8
0x1800013a3  xor     ebx, ebx
0x1800013a5  mov     [rsp+168h+var_148], ebx
0x1800013a9  mov     edi, [rsp+168h+arg_8]
0x1800013b0  mov     rsi, [rsp+168h+arg_0]
0x1800013b8  test    ebx, ebx
0x1800013ba  jz      loc_180001515
0x1800013c0  mov     r8, [rsp+168h+lpvReserved]
0x1800013c8  mov     edx, edi
0x1800013ca  mov     rcx, rsi
0x1800013cd  call    _CRT_INIT
0x1800013d2  mov     ebx, eax
0x1800013d4  mov     [rsp+168h+var_148], eax
0x1800013d8  jmp     short loc_1800013EF
0x1800013da  xor     ebx, ebx
0x1800013dc  mov     [rsp+168h+var_148], ebx
0x1800013e0  mov     edi, [rsp+168h+arg_8]
0x1800013e7  mov     rsi, [rsp+168h+arg_0]
0x1800013ef  test    ebx, ebx
0x1800013f1  jz      loc_180001515
0x1800013f7  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x1800013ff  mov     edx, edi; fdwReason
0x180001401  mov     rcx, rsi; hinstDLL
0x180001404  call    DllMain
0x180001409  mov     ebx, eax
0x18000140b  mov     [rsp+168h+var_148], eax
0x18000140f  jmp     short loc_180001426
0x180001411  xor     ebx, ebx
0x180001413  mov     [rsp+168h+var_148], ebx
0x180001417  mov     edi, [rsp+168h+arg_8]
0x18000141e  mov     rsi, [rsp+168h+arg_0]
0x180001426  cmp     edi, 1
0x180001429  jnz     short loc_1800014A1
0x18000142b  test    ebx, ebx
0x18000142d  jnz     short loc_1800014A1
0x18000142f  xor     r8d, r8d; lpvReserved
0x180001432  xor     edx, edx; fdwReason
0x180001434  mov     rcx, rsi; hinstDLL
0x180001437  call    DllMain
0x18000143c  jmp     short loc_180001451
0x18000143e  mov     edi, [rsp+168h+arg_8]
0x180001445  mov     rsi, [rsp+168h+arg_0]
0x18000144d  mov     ebx, [rsp+168h+var_148]
0x180001451  xor     r8d, r8d
0x180001454  xor     edx, edx
0x180001456  mov     rcx, rsi
0x180001459  call    _CRT_INIT
0x18000145e  jmp     short loc_180001473
0x180001460  mov     edi, [rsp+168h+arg_8]
0x180001467  mov     rsi, [rsp+168h+arg_0]
0x18000146f  mov     ebx, [rsp+168h+var_148]
0x180001473  mov     rax, cs:_pRawDllMain
0x18000147a  test    rax, rax
0x18000147d  jz      short loc_1800014A1
0x18000147f  xor     r8d, r8d
0x180001482  xor     edx, edx
0x180001484  mov     rcx, rsi
0x180001487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000148c  jmp     short loc_1800014A1
0x18000148e  mov     edi, [rsp+168h+arg_8]
0x180001495  mov     rsi, [rsp+168h+arg_0]
0x18000149d  mov     ebx, [rsp+168h+var_148]
0x1800014a1  test    edi, edi
0x1800014a3  jz      short loc_1800014AA
0x1800014a5  cmp     edi, 3
0x1800014a8  jnz     short loc_180001515
0x1800014aa  mov     r8, [rsp+168h+lpvReserved]
0x1800014b2  mov     edx, edi
0x1800014b4  mov     rcx, rsi
0x1800014b7  call    _CRT_INIT
0x1800014bc  mov     ebx, eax
0x1800014be  mov     [rsp+168h+var_148], eax
0x1800014c2  jmp     short loc_1800014D9
0x1800014c4  xor     ebx, ebx
0x1800014c6  mov     [rsp+168h+var_148], ebx
0x1800014ca  mov     edi, [rsp+168h+arg_8]
0x1800014d1  mov     rsi, [rsp+168h+arg_0]
0x1800014d9  mov     rax, cs:_pRawDllMain
0x1800014e0  test    rax, rax
0x1800014e3  jz      short loc_180001515
0x1800014e5  cmp     cs:dword_1800060A4, 0
0x1800014ec  jz      short loc_180001515
0x1800014ee  mov     r8, [rsp+168h+lpvReserved]
0x1800014f6  mov     edx, edi
0x1800014f8  mov     rcx, rsi
0x1800014fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001500  mov     ebx, eax
0x180001502  mov     [rsp+168h+var_148], eax
0x180001506  jmp     short loc_180001515
0x180001508  xor     ebx, ebx
0x18000150a  mov     [rsp+168h+var_148], ebx
0x18000150e  mov     edi, [rsp+168h+arg_8]
0x180001515  cmp     edi, 1
0x180001518  ja      short loc_180001524
0x18000151a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001524  mov     eax, ebx
0x180001526  add     rsp, 150h
0x18000152d  pop     rdi
0x18000152e  pop     rsi
0x18000152f  pop     rbx
0x180001530  retn
0x1800020b0  push    rbp
0x1800020b2  sub     rsp, 20h
0x1800020b6  mov     rbp, rdx
0x1800020b9  mov     [rbp+108h], rcx
0x1800020c0  mov     rax, [rcx]
0x1800020c3  mov     edx, [rax]
0x1800020c5  mov     [rbp+0A4h], edx
0x1800020cb  mov     [rbp+0C8h], rcx
0x1800020d2  mov     [rbp+28h], edx
0x1800020d5  mov     eax, [rbp+28h]
0x1800020d8  cmp     eax, 0E06D7363h
0x1800020dd  jnz     short loc_1800020F3
0x1800020df  mov     rdx, [rbp+0C8h]
0x1800020e6  mov     ecx, [rbp+28h]
0x1800020e9  call    _XcptFilter_0
0x1800020ee  mov     [rbp+30h], eax
0x1800020f1  jmp     short loc_1800020FA
0x1800020f3  mov     dword ptr [rbp+30h], 0
0x1800020fa  mov     eax, [rbp+30h]
0x1800020fd  add     rsp, 20h
0x180002101  pop     rbp
0x180002102  retn
0x180002104  push    rbp
0x180002106  sub     rsp, 20h
0x18000210a  mov     rbp, rdx
0x18000210d  mov     [rbp+110h], rcx
0x180002114  mov     rax, [rcx]
0x180002117  mov     edx, [rax]
0x180002119  mov     [rbp+0A8h], edx
0x18000211f  mov     [rbp+0D0h], rcx
0x180002126  mov     [rbp+38h], edx
0x180002129  mov     eax, [rbp+38h]
0x18000212c  cmp     eax, 0E06D7363h
0x180002131  jnz     short loc_180002147
0x180002133  mov     rdx, [rbp+0D0h]
0x18000213a  mov     ecx, [rbp+38h]
0x18000213d  call    _XcptFilter_0
0x180002142  mov     [rbp+40h], eax
0x180002145  jmp     short loc_18000214E
0x180002147  mov     dword ptr [rbp+40h], 0
0x18000214e  mov     eax, [rbp+40h]
0x180002151  add     rsp, 20h
0x180002155  pop     rbp
0x180002156  retn
0x180002158  push    rbp
0x18000215a  sub     rsp, 20h
0x18000215e  mov     rbp, rdx
0x180002161  mov     [rbp+118h], rcx
0x180002168  mov     rax, [rcx]
0x18000216b  mov     edx, [rax]
0x18000216d  mov     [rbp+0ACh], edx
0x180002173  mov     [rbp+0D8h], rcx
0x18000217a  mov     [rbp+48h], edx
0x18000217d  mov     eax, [rbp+48h]
0x180002180  cmp     eax, 0E06D7363h
0x180002185  jnz     short loc_18000219B
0x180002187  mov     rdx, [rbp+0D8h]
0x18000218e  mov     ecx, [rbp+48h]
0x180002191  call    _XcptFilter_0
0x180002196  mov     [rbp+50h], eax
0x180002199  jmp     short loc_1800021A2
0x18000219b  mov     dword ptr [rbp+50h], 0
0x1800021a2  mov     eax, [rbp+50h]
0x1800021a5  add     rsp, 20h
0x1800021a9  pop     rbp
0x1800021aa  retn
0x1800021ac  push    rbp
0x1800021ae  sub     rsp, 20h
0x1800021b2  mov     rbp, rdx
0x1800021b5  mov     [rbp+120h], rcx
0x1800021bc  mov     rax, [rcx]
0x1800021bf  mov     edx, [rax]
0x1800021c1  mov     [rbp+0B0h], edx
0x1800021c7  mov     [rbp+0E0h], rcx
0x1800021ce  mov     [rbp+58h], edx
0x1800021d1  mov     eax, [rbp+58h]
0x1800021d4  cmp     eax, 0E06D7363h
0x1800021d9  jnz     short loc_1800021EF
0x1800021db  mov     rdx, [rbp+0E0h]
0x1800021e2  mov     ecx, [rbp+58h]
0x1800021e5  call    _XcptFilter_0
0x1800021ea  mov     [rbp+60h], eax
0x1800021ed  jmp     short loc_1800021F6
0x1800021ef  mov     dword ptr [rbp+60h], 0
0x1800021f6  mov     eax, [rbp+60h]
0x1800021f9  add     rsp, 20h
0x1800021fd  pop     rbp
0x1800021fe  retn
0x180002200  push    rbp
0x180002202  sub     rsp, 20h
0x180002206  mov     rbp, rdx
0x180002209  mov     [rbp+128h], rcx
0x180002210  mov     rax, [rcx]
0x180002213  mov     edx, [rax]
0x180002215  mov     [rbp+0B4h], edx
0x18000221b  mov     [rbp+0E8h], rcx
0x180002222  mov     [rbp+68h], edx
0x180002225  mov     eax, [rbp+68h]
0x180002228  cmp     eax, 0E06D7363h
0x18000222d  jnz     short loc_180002243
0x18000222f  mov     rdx, [rbp+0E8h]
0x180002236  mov     ecx, [rbp+68h]
0x180002239  call    _XcptFilter_0
0x18000223e  mov     [rbp+70h], eax
0x180002241  jmp     short loc_18000224A
0x180002243  mov     dword ptr [rbp+70h], 0
0x18000224a  mov     eax, [rbp+70h]
0x18000224d  add     rsp, 20h
0x180002251  pop     rbp
0x180002252  retn
0x180002254  push    rbp
0x180002256  sub     rsp, 20h
0x18000225a  mov     rbp, rdx
0x18000225d  mov     [rbp+130h], rcx
0x180002264  mov     rax, [rcx]
0x180002267  mov     edx, [rax]
0x180002269  mov     [rbp+0B8h], edx
0x18000226f  mov     [rbp+0F0h], rcx
0x180002276  mov     [rbp+78h], edx
0x180002279  mov     eax, [rbp+78h]
0x18000227c  cmp     eax, 0E06D7363h
0x180002281  jnz     short loc_18000229A
0x180002283  mov     rdx, [rbp+0F0h]
0x18000228a  mov     ecx, [rbp+78h]
0x18000228d  call    _XcptFilter_0
0x180002292  mov     [rbp+80h], eax
0x180002298  jmp     short loc_1800022A4
0x18000229a  mov     dword ptr [rbp+80h], 0
0x1800022a4  mov     eax, [rbp+80h]
0x1800022aa  add     rsp, 20h
0x1800022ae  pop     rbp
0x1800022af  retn
0x1800022b1  push    rbp
0x1800022b3  sub     rsp, 20h
0x1800022b7  mov     rbp, rdx
0x1800022ba  mov     [rbp+138h], rcx
0x1800022c1  mov     rax, [rcx]
0x1800022c4  mov     edx, [rax]
0x1800022c6  mov     [rbp+0BCh], edx
0x1800022cc  mov     [rbp+0F8h], rcx
0x1800022d3  mov     [rbp+88h], edx
0x1800022d9  mov     eax, [rbp+88h]
0x1800022df  cmp     eax, 0E06D7363h
0x1800022e4  jnz     short loc_180002300
0x1800022e6  mov     rdx, [rbp+0F8h]
0x1800022ed  mov     ecx, [rbp+88h]
0x1800022f3  call    _XcptFilter_0
0x1800022f8  mov     [rbp+90h], eax
0x1800022fe  jmp     short loc_18000230A
0x180002300  mov     dword ptr [rbp+90h], 0
0x18000230a  mov     eax, [rbp+90h]
0x180002310  add     rsp, 20h
0x180002314  pop     rbp
0x180002315  retn
0x180002317  push    rbp
0x180002319  sub     rsp, 20h
0x18000231d  mov     rbp, rdx
0x180002320  mov     [rbp+140h], rcx
0x180002327  mov     rax, [rcx]
0x18000232a  mov     edx, [rax]
0x18000232c  mov     [rbp+0C0h], edx
0x180002332  mov     [rbp+100h], rcx
0x180002339  mov     [rbp+98h], edx
0x18000233f  mov     eax, [rbp+98h]
0x180002345  cmp     eax, 0E06D7363h
  ... truncated ...
```
