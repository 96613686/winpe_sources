# __DllMainCRTStartup

- ea: `0x180001484`
- end: `0x180001690`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180001210`
- `0x180001484`
- `0x180001c4d`
- `0x180009bd0`
- `0x180018540`

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
  if ( (_DWORD)fdwReason || dword_1800224E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800224E4 = 1;
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
            if ( dword_1800224E4 )
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
0x180001484  mov     [rsp+lpvReserved], r8
0x180001489  mov     [rsp+arg_8], edx
0x18000148d  mov     [rsp+arg_0], rcx
0x180001492  push    rbx
0x180001493  push    rsi
0x180001494  push    rdi
0x180001495  sub     rsp, 0F0h
0x18000149c  mov     edi, edx
0x18000149e  mov     rsi, rcx
0x1800014a1  mov     ebx, 1
0x1800014a6  cmp     edx, ebx
0x1800014a8  ja      short loc_1800014B0
0x1800014aa  mov     cs:__native_dllmain_reason, edx
0x1800014b0  test    edx, edx
0x1800014b2  jnz     short loc_1800014C7
0x1800014b4  cmp     cs:dword_1800224E0, edx
0x1800014ba  jnz     short loc_1800014C7
0x1800014bc  xor     ebx, ebx
0x1800014be  mov     [rsp+108h+var_E8], ebx
0x1800014c2  jmp     loc_180001674
0x1800014c7  lea     eax, [rdx-1]
0x1800014ca  cmp     eax, 1
0x1800014cd  ja      loc_180001554
0x1800014d3  mov     rax, cs:_pRawDllMain
0x1800014da  test    rax, rax
0x1800014dd  jz      short loc_180001515
0x1800014df  cmp     edx, 1
0x1800014e2  jnz     short loc_1800014EA
0x1800014e4  mov     cs:dword_1800224E4, edx
0x1800014ea  mov     r8, [rsp+108h+lpvReserved]
0x1800014f2  call    cs:__guard_dispatch_icall_fptr
0x1800014f8  mov     ebx, eax
0x1800014fa  mov     [rsp+108h+var_E8], eax
0x1800014fe  jmp     short loc_180001515
0x180001500  xor     ebx, ebx
0x180001502  mov     [rsp+108h+var_E8], ebx
0x180001506  mov     edi, [rsp+108h+arg_8]
0x18000150d  mov     rsi, [rsp+108h+arg_0]
0x180001515  test    ebx, ebx
0x180001517  jz      loc_180001674
0x18000151d  mov     r8, [rsp+108h+lpvReserved]
0x180001525  mov     edx, edi
0x180001527  mov     rcx, rsi
0x18000152a  call    _CRT_INIT
0x18000152f  mov     ebx, eax
0x180001531  mov     [rsp+108h+var_E8], eax
0x180001535  jmp     short loc_18000154C
0x180001537  xor     ebx, ebx
0x180001539  mov     [rsp+108h+var_E8], ebx
0x18000153d  mov     edi, [rsp+108h+arg_8]
0x180001544  mov     rsi, [rsp+108h+arg_0]
0x18000154c  test    ebx, ebx
0x18000154e  jz      loc_180001674
0x180001554  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000155c  mov     edx, edi; fdwReason
0x18000155e  mov     rcx, rsi; hinstDLL
0x180001561  call    DllMain
0x180001566  mov     ebx, eax
0x180001568  mov     [rsp+108h+var_E8], eax
0x18000156c  jmp     short loc_180001583
0x18000156e  xor     ebx, ebx
0x180001570  mov     [rsp+108h+var_E8], ebx
0x180001574  mov     edi, [rsp+108h+arg_8]
0x18000157b  mov     rsi, [rsp+108h+arg_0]
0x180001583  cmp     edi, 1
0x180001586  jnz     short loc_1800015FF
0x180001588  test    ebx, ebx
0x18000158a  jnz     short loc_1800015FF
0x18000158c  xor     r8d, r8d; lpvReserved
0x18000158f  xor     edx, edx; fdwReason
0x180001591  mov     rcx, rsi; hinstDLL
0x180001594  call    DllMain
0x180001599  jmp     short loc_1800015AE
0x18000159b  mov     edi, [rsp+108h+arg_8]
0x1800015a2  mov     rsi, [rsp+108h+arg_0]
0x1800015aa  mov     ebx, [rsp+108h+var_E8]
0x1800015ae  xor     r8d, r8d
0x1800015b1  xor     edx, edx
0x1800015b3  mov     rcx, rsi
0x1800015b6  call    _CRT_INIT
0x1800015bb  jmp     short loc_1800015D0
0x1800015bd  mov     edi, [rsp+108h+arg_8]
0x1800015c4  mov     rsi, [rsp+108h+arg_0]
0x1800015cc  mov     ebx, [rsp+108h+var_E8]
0x1800015d0  mov     rax, cs:_pRawDllMain
0x1800015d7  test    rax, rax
0x1800015da  jz      short loc_1800015FF
0x1800015dc  xor     r8d, r8d
0x1800015df  xor     edx, edx
0x1800015e1  mov     rcx, rsi
0x1800015e4  call    cs:__guard_dispatch_icall_fptr
0x1800015ea  jmp     short loc_1800015FF
0x1800015ec  mov     edi, [rsp+108h+arg_8]
0x1800015f3  mov     rsi, [rsp+108h+arg_0]
0x1800015fb  mov     ebx, [rsp+108h+var_E8]
0x1800015ff  test    edi, edi
0x180001601  jz      short loc_180001608
0x180001603  cmp     edi, 3
0x180001606  jnz     short loc_180001674
0x180001608  mov     r8, [rsp+108h+lpvReserved]
0x180001610  mov     edx, edi
0x180001612  mov     rcx, rsi
0x180001615  call    _CRT_INIT
0x18000161a  mov     ebx, eax
0x18000161c  mov     [rsp+108h+var_E8], eax
0x180001620  jmp     short loc_180001637
0x180001622  xor     ebx, ebx
0x180001624  mov     [rsp+108h+var_E8], ebx
0x180001628  mov     edi, [rsp+108h+arg_8]
0x18000162f  mov     rsi, [rsp+108h+arg_0]
0x180001637  mov     rax, cs:_pRawDllMain
0x18000163e  test    rax, rax
0x180001641  jz      short loc_180001674
0x180001643  cmp     cs:dword_1800224E4, 0
0x18000164a  jz      short loc_180001674
0x18000164c  mov     r8, [rsp+108h+lpvReserved]
0x180001654  mov     edx, edi
0x180001656  mov     rcx, rsi
0x180001659  call    cs:__guard_dispatch_icall_fptr
0x18000165f  mov     ebx, eax
0x180001661  mov     [rsp+108h+var_E8], eax
0x180001665  jmp     short loc_180001674
0x180001667  xor     ebx, ebx
0x180001669  mov     [rsp+108h+var_E8], ebx
0x18000166d  mov     edi, [rsp+108h+arg_8]
0x180001674  cmp     edi, 1
0x180001677  ja      short loc_180001683
0x180001679  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001683  mov     eax, ebx
0x180001685  add     rsp, 0F0h
0x18000168c  pop     rdi
0x18000168d  pop     rsi
0x18000168e  pop     rbx
0x18000168f  retn
0x180018613  push    rbp
0x180018615  sub     rsp, 20h
0x180018619  mov     rbp, rdx
0x18001861c  mov     rax, [rcx]
0x18001861f  mov     edx, [rax]
0x180018621  mov     [rbp+0A8h], rcx
0x180018628  mov     [rbp+28h], edx
0x18001862b  mov     eax, [rbp+28h]
0x18001862e  cmp     eax, 0E06D7363h
0x180018633  jnz     short loc_180018649
0x180018635  mov     rdx, [rbp+0A8h]
0x18001863c  mov     ecx, [rbp+28h]
0x18001863f  call    _XcptFilter_0
0x180018644  mov     [rbp+30h], eax
0x180018647  jmp     short loc_180018650
0x180018649  mov     dword ptr [rbp+30h], 0
0x180018650  mov     eax, [rbp+30h]
0x180018653  add     rsp, 20h
0x180018657  pop     rbp
0x180018658  retn
0x18001865a  push    rbp
0x18001865c  sub     rsp, 20h
0x180018660  mov     rbp, rdx
0x180018663  mov     rax, [rcx]
0x180018666  mov     edx, [rax]
0x180018668  mov     [rbp+0B0h], rcx
0x18001866f  mov     [rbp+38h], edx
0x180018672  mov     eax, [rbp+38h]
0x180018675  cmp     eax, 0E06D7363h
0x18001867a  jnz     short loc_180018690
0x18001867c  mov     rdx, [rbp+0B0h]
0x180018683  mov     ecx, [rbp+38h]
0x180018686  call    _XcptFilter_0
0x18001868b  mov     [rbp+40h], eax
0x18001868e  jmp     short loc_180018697
0x180018690  mov     dword ptr [rbp+40h], 0
0x180018697  mov     eax, [rbp+40h]
0x18001869a  add     rsp, 20h
0x18001869e  pop     rbp
0x18001869f  retn
0x1800186a1  push    rbp
0x1800186a3  sub     rsp, 20h
0x1800186a7  mov     rbp, rdx
0x1800186aa  mov     rax, [rcx]
0x1800186ad  mov     edx, [rax]
0x1800186af  mov     [rbp+0B8h], rcx
0x1800186b6  mov     [rbp+48h], edx
0x1800186b9  mov     eax, [rbp+48h]
0x1800186bc  cmp     eax, 0E06D7363h
0x1800186c1  jnz     short loc_1800186D7
0x1800186c3  mov     rdx, [rbp+0B8h]
0x1800186ca  mov     ecx, [rbp+48h]
0x1800186cd  call    _XcptFilter_0
0x1800186d2  mov     [rbp+50h], eax
0x1800186d5  jmp     short loc_1800186DE
0x1800186d7  mov     dword ptr [rbp+50h], 0
0x1800186de  mov     eax, [rbp+50h]
0x1800186e1  add     rsp, 20h
0x1800186e5  pop     rbp
0x1800186e6  retn
0x1800186e8  push    rbp
0x1800186ea  sub     rsp, 20h
0x1800186ee  mov     rbp, rdx
0x1800186f1  mov     rax, [rcx]
0x1800186f4  mov     edx, [rax]
0x1800186f6  mov     [rbp+0C0h], rcx
0x1800186fd  mov     [rbp+58h], edx
0x180018700  mov     eax, [rbp+58h]
0x180018703  cmp     eax, 0E06D7363h
0x180018708  jnz     short loc_18001871E
0x18001870a  mov     rdx, [rbp+0C0h]
0x180018711  mov     ecx, [rbp+58h]
0x180018714  call    _XcptFilter_0
0x180018719  mov     [rbp+60h], eax
0x18001871c  jmp     short loc_180018725
0x18001871e  mov     dword ptr [rbp+60h], 0
0x180018725  mov     eax, [rbp+60h]
0x180018728  add     rsp, 20h
0x18001872c  pop     rbp
0x18001872d  retn
0x18001872f  push    rbp
0x180018731  sub     rsp, 20h
0x180018735  mov     rbp, rdx
0x180018738  mov     rax, [rcx]
0x18001873b  mov     edx, [rax]
0x18001873d  mov     [rbp+0C8h], rcx
0x180018744  mov     [rbp+68h], edx
0x180018747  mov     eax, [rbp+68h]
0x18001874a  cmp     eax, 0E06D7363h
0x18001874f  jnz     short loc_180018765
0x180018751  mov     rdx, [rbp+0C8h]
0x180018758  mov     ecx, [rbp+68h]
0x18001875b  call    _XcptFilter_0
0x180018760  mov     [rbp+70h], eax
0x180018763  jmp     short loc_18001876C
0x180018765  mov     dword ptr [rbp+70h], 0
0x18001876c  mov     eax, [rbp+70h]
0x18001876f  add     rsp, 20h
0x180018773  pop     rbp
0x180018774  retn
0x180018776  push    rbp
0x180018778  sub     rsp, 20h
0x18001877c  mov     rbp, rdx
0x18001877f  mov     rax, [rcx]
0x180018782  mov     edx, [rax]
0x180018784  mov     [rbp+0D0h], rcx
0x18001878b  mov     [rbp+78h], edx
0x18001878e  mov     eax, [rbp+78h]
0x180018791  cmp     eax, 0E06D7363h
0x180018796  jnz     short loc_1800187AF
0x180018798  mov     rdx, [rbp+0D0h]
0x18001879f  mov     ecx, [rbp+78h]
0x1800187a2  call    _XcptFilter_0
0x1800187a7  mov     [rbp+80h], eax
0x1800187ad  jmp     short loc_1800187B9
0x1800187af  mov     dword ptr [rbp+80h], 0
0x1800187b9  mov     eax, [rbp+80h]
0x1800187bf  add     rsp, 20h
0x1800187c3  pop     rbp
0x1800187c4  retn
0x1800187c6  push    rbp
0x1800187c8  sub     rsp, 20h
0x1800187cc  mov     rbp, rdx
0x1800187cf  mov     rax, [rcx]
0x1800187d2  mov     edx, [rax]
0x1800187d4  mov     [rbp+0D8h], rcx
0x1800187db  mov     [rbp+88h], edx
0x1800187e1  mov     eax, [rbp+88h]
0x1800187e7  cmp     eax, 0E06D7363h
0x1800187ec  jnz     short loc_180018808
0x1800187ee  mov     rdx, [rbp+0D8h]
0x1800187f5  mov     ecx, [rbp+88h]
0x1800187fb  call    _XcptFilter_0
0x180018800  mov     [rbp+90h], eax
0x180018806  jmp     short loc_180018812
0x180018808  mov     dword ptr [rbp+90h], 0
0x180018812  mov     eax, [rbp+90h]
0x180018818  add     rsp, 20h
0x18001881c  pop     rbp
0x18001881d  retn
0x18001881f  push    rbp
0x180018821  sub     rsp, 20h
0x180018825  mov     rbp, rdx
0x180018828  mov     rax, [rcx]
0x18001882b  mov     edx, [rax]
0x18001882d  mov     [rbp+0E0h], rcx
0x180018834  mov     [rbp+98h], edx
0x18001883a  mov     eax, [rbp+98h]
0x180018840  cmp     eax, 0E06D7363h
0x180018845  jnz     short loc_180018861
0x180018847  mov     rdx, [rbp+0E0h]
0x18001884e  mov     ecx, [rbp+98h]
0x180018854  call    _XcptFilter_0
0x180018859  mov     [rbp+0A0h], eax
0x18001885f  jmp     short loc_18001886B
0x180018861  mov     dword ptr [rbp+0A0h], 0
0x18001886b  mov     eax, [rbp+0A0h]
0x180018871  add     rsp, 20h
0x180018875  pop     rbp
0x180018876  retn
0x180018878  push    rbp
0x18001887a  sub     rsp, 20h
0x18001887e  mov     rbp, rdx
0x180018881  cmp     dword ptr [rbp+118h], 1
0x180018888  ja      short loc_180018894
0x18001888a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
