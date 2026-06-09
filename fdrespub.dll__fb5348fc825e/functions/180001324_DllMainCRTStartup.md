# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001530`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800010b0`
- `0x180001324`
- `0x18000155a`
- `0x180001fcc`
- `0x1800052b0`

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
  if ( (_DWORD)fdwReason || dword_18000A160 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000A164 = 1;
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
            if ( dword_18000A164 )
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
0x180001335  sub     rsp, 0F0h
0x18000133c  mov     edi, edx
0x18000133e  mov     rsi, rcx
0x180001341  mov     ebx, 1
0x180001346  cmp     edx, ebx
0x180001348  ja      short loc_180001350
0x18000134a  mov     cs:__native_dllmain_reason, edx
0x180001350  test    edx, edx
0x180001352  jnz     short loc_180001367
0x180001354  cmp     cs:dword_18000A160, edx
0x18000135a  jnz     short loc_180001367
0x18000135c  xor     ebx, ebx
0x18000135e  mov     [rsp+108h+var_E8], ebx
0x180001362  jmp     loc_180001514
0x180001367  lea     eax, [rdx-1]
0x18000136a  cmp     eax, 1
0x18000136d  ja      loc_1800013F4
0x180001373  mov     rax, cs:_pRawDllMain
0x18000137a  test    rax, rax
0x18000137d  jz      short loc_1800013B5
0x18000137f  cmp     edx, 1
0x180001382  jnz     short loc_18000138A
0x180001384  mov     cs:dword_18000A164, edx
0x18000138a  mov     r8, [rsp+108h+lpvReserved]
0x180001392  call    cs:__guard_dispatch_icall_fptr
0x180001398  mov     ebx, eax
0x18000139a  mov     [rsp+108h+var_E8], eax
0x18000139e  jmp     short loc_1800013B5
0x1800013a0  xor     ebx, ebx
0x1800013a2  mov     [rsp+108h+var_E8], ebx
0x1800013a6  mov     edi, [rsp+108h+arg_8]
0x1800013ad  mov     rsi, [rsp+108h+arg_0]
0x1800013b5  test    ebx, ebx
0x1800013b7  jz      loc_180001514
0x1800013bd  mov     r8, [rsp+108h+lpvReserved]
0x1800013c5  mov     edx, edi
0x1800013c7  mov     rcx, rsi
0x1800013ca  call    _CRT_INIT
0x1800013cf  mov     ebx, eax
0x1800013d1  mov     [rsp+108h+var_E8], eax
0x1800013d5  jmp     short loc_1800013EC
0x1800013d7  xor     ebx, ebx
0x1800013d9  mov     [rsp+108h+var_E8], ebx
0x1800013dd  mov     edi, [rsp+108h+arg_8]
0x1800013e4  mov     rsi, [rsp+108h+arg_0]
0x1800013ec  test    ebx, ebx
0x1800013ee  jz      loc_180001514
0x1800013f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013fc  mov     edx, edi; fdwReason
0x1800013fe  mov     rcx, rsi; hinstDLL
0x180001401  call    DllMain
0x180001406  mov     ebx, eax
0x180001408  mov     [rsp+108h+var_E8], eax
0x18000140c  jmp     short loc_180001423
0x18000140e  xor     ebx, ebx
0x180001410  mov     [rsp+108h+var_E8], ebx
0x180001414  mov     edi, [rsp+108h+arg_8]
0x18000141b  mov     rsi, [rsp+108h+arg_0]
0x180001423  cmp     edi, 1
0x180001426  jnz     short loc_18000149F
0x180001428  test    ebx, ebx
0x18000142a  jnz     short loc_18000149F
0x18000142c  xor     r8d, r8d; lpvReserved
0x18000142f  xor     edx, edx; fdwReason
0x180001431  mov     rcx, rsi; hinstDLL
0x180001434  call    DllMain
0x180001439  jmp     short loc_18000144E
0x18000143b  mov     edi, [rsp+108h+arg_8]
0x180001442  mov     rsi, [rsp+108h+arg_0]
0x18000144a  mov     ebx, [rsp+108h+var_E8]
0x18000144e  xor     r8d, r8d
0x180001451  xor     edx, edx
0x180001453  mov     rcx, rsi
0x180001456  call    _CRT_INIT
0x18000145b  jmp     short loc_180001470
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  mov     ebx, [rsp+108h+var_E8]
0x180001470  mov     rax, cs:_pRawDllMain
0x180001477  test    rax, rax
0x18000147a  jz      short loc_18000149F
0x18000147c  xor     r8d, r8d
0x18000147f  xor     edx, edx
0x180001481  mov     rcx, rsi
0x180001484  call    cs:__guard_dispatch_icall_fptr
0x18000148a  jmp     short loc_18000149F
0x18000148c  mov     edi, [rsp+108h+arg_8]
0x180001493  mov     rsi, [rsp+108h+arg_0]
0x18000149b  mov     ebx, [rsp+108h+var_E8]
0x18000149f  test    edi, edi
0x1800014a1  jz      short loc_1800014A8
0x1800014a3  cmp     edi, 3
0x1800014a6  jnz     short loc_180001514
0x1800014a8  mov     r8, [rsp+108h+lpvReserved]
0x1800014b0  mov     edx, edi
0x1800014b2  mov     rcx, rsi
0x1800014b5  call    _CRT_INIT
0x1800014ba  mov     ebx, eax
0x1800014bc  mov     [rsp+108h+var_E8], eax
0x1800014c0  jmp     short loc_1800014D7
0x1800014c2  xor     ebx, ebx
0x1800014c4  mov     [rsp+108h+var_E8], ebx
0x1800014c8  mov     edi, [rsp+108h+arg_8]
0x1800014cf  mov     rsi, [rsp+108h+arg_0]
0x1800014d7  mov     rax, cs:_pRawDllMain
0x1800014de  test    rax, rax
0x1800014e1  jz      short loc_180001514
0x1800014e3  cmp     cs:dword_18000A164, 0
0x1800014ea  jz      short loc_180001514
0x1800014ec  mov     r8, [rsp+108h+lpvReserved]
0x1800014f4  mov     edx, edi
0x1800014f6  mov     rcx, rsi
0x1800014f9  call    cs:__guard_dispatch_icall_fptr
0x1800014ff  mov     ebx, eax
0x180001501  mov     [rsp+108h+var_E8], eax
0x180001505  jmp     short loc_180001514
0x180001507  xor     ebx, ebx
0x180001509  mov     [rsp+108h+var_E8], ebx
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  cmp     edi, 1
0x180001517  ja      short loc_180001523
0x180001519  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001523  mov     eax, ebx
0x180001525  add     rsp, 0F0h
0x18000152c  pop     rdi
0x18000152d  pop     rsi
0x18000152e  pop     rbx
0x18000152f  retn
0x180005320  push    rbp
0x180005322  sub     rsp, 20h
0x180005326  mov     rbp, rdx
0x180005329  mov     rax, [rcx]
0x18000532c  mov     edx, [rax]
0x18000532e  mov     [rbp+0A8h], rcx
0x180005335  mov     [rbp+28h], edx
0x180005338  mov     eax, [rbp+28h]
0x18000533b  cmp     eax, 0E06D7363h
0x180005340  jnz     short loc_180005356
0x180005342  mov     rdx, [rbp+0A8h]
0x180005349  mov     ecx, [rbp+28h]
0x18000534c  call    _XcptFilter_0
0x180005351  mov     [rbp+30h], eax
0x180005354  jmp     short loc_18000535D
0x180005356  mov     dword ptr [rbp+30h], 0
0x18000535d  mov     eax, [rbp+30h]
0x180005360  add     rsp, 20h
0x180005364  pop     rbp
0x180005365  retn
0x180005367  push    rbp
0x180005369  sub     rsp, 20h
0x18000536d  mov     rbp, rdx
0x180005370  mov     rax, [rcx]
0x180005373  mov     edx, [rax]
0x180005375  mov     [rbp+0B0h], rcx
0x18000537c  mov     [rbp+38h], edx
0x18000537f  mov     eax, [rbp+38h]
0x180005382  cmp     eax, 0E06D7363h
0x180005387  jnz     short loc_18000539D
0x180005389  mov     rdx, [rbp+0B0h]
0x180005390  mov     ecx, [rbp+38h]
0x180005393  call    _XcptFilter_0
0x180005398  mov     [rbp+40h], eax
0x18000539b  jmp     short loc_1800053A4
0x18000539d  mov     dword ptr [rbp+40h], 0
0x1800053a4  mov     eax, [rbp+40h]
0x1800053a7  add     rsp, 20h
0x1800053ab  pop     rbp
0x1800053ac  retn
0x1800053ae  push    rbp
0x1800053b0  sub     rsp, 20h
0x1800053b4  mov     rbp, rdx
0x1800053b7  mov     rax, [rcx]
0x1800053ba  mov     edx, [rax]
0x1800053bc  mov     [rbp+0B8h], rcx
0x1800053c3  mov     [rbp+48h], edx
0x1800053c6  mov     eax, [rbp+48h]
0x1800053c9  cmp     eax, 0E06D7363h
0x1800053ce  jnz     short loc_1800053E4
0x1800053d0  mov     rdx, [rbp+0B8h]
0x1800053d7  mov     ecx, [rbp+48h]
0x1800053da  call    _XcptFilter_0
0x1800053df  mov     [rbp+50h], eax
0x1800053e2  jmp     short loc_1800053EB
0x1800053e4  mov     dword ptr [rbp+50h], 0
0x1800053eb  mov     eax, [rbp+50h]
0x1800053ee  add     rsp, 20h
0x1800053f2  pop     rbp
0x1800053f3  retn
0x1800053f5  push    rbp
0x1800053f7  sub     rsp, 20h
0x1800053fb  mov     rbp, rdx
0x1800053fe  mov     rax, [rcx]
0x180005401  mov     edx, [rax]
0x180005403  mov     [rbp+0C0h], rcx
0x18000540a  mov     [rbp+58h], edx
0x18000540d  mov     eax, [rbp+58h]
0x180005410  cmp     eax, 0E06D7363h
0x180005415  jnz     short loc_18000542B
0x180005417  mov     rdx, [rbp+0C0h]
0x18000541e  mov     ecx, [rbp+58h]
0x180005421  call    _XcptFilter_0
0x180005426  mov     [rbp+60h], eax
0x180005429  jmp     short loc_180005432
0x18000542b  mov     dword ptr [rbp+60h], 0
0x180005432  mov     eax, [rbp+60h]
0x180005435  add     rsp, 20h
0x180005439  pop     rbp
0x18000543a  retn
0x18000543c  push    rbp
0x18000543e  sub     rsp, 20h
0x180005442  mov     rbp, rdx
0x180005445  mov     rax, [rcx]
0x180005448  mov     edx, [rax]
0x18000544a  mov     [rbp+0C8h], rcx
0x180005451  mov     [rbp+68h], edx
0x180005454  mov     eax, [rbp+68h]
0x180005457  cmp     eax, 0E06D7363h
0x18000545c  jnz     short loc_180005472
0x18000545e  mov     rdx, [rbp+0C8h]
0x180005465  mov     ecx, [rbp+68h]
0x180005468  call    _XcptFilter_0
0x18000546d  mov     [rbp+70h], eax
0x180005470  jmp     short loc_180005479
0x180005472  mov     dword ptr [rbp+70h], 0
0x180005479  mov     eax, [rbp+70h]
0x18000547c  add     rsp, 20h
0x180005480  pop     rbp
0x180005481  retn
0x180005483  push    rbp
0x180005485  sub     rsp, 20h
0x180005489  mov     rbp, rdx
0x18000548c  mov     rax, [rcx]
0x18000548f  mov     edx, [rax]
0x180005491  mov     [rbp+0D0h], rcx
0x180005498  mov     [rbp+78h], edx
0x18000549b  mov     eax, [rbp+78h]
0x18000549e  cmp     eax, 0E06D7363h
0x1800054a3  jnz     short loc_1800054BC
0x1800054a5  mov     rdx, [rbp+0D0h]
0x1800054ac  mov     ecx, [rbp+78h]
0x1800054af  call    _XcptFilter_0
0x1800054b4  mov     [rbp+80h], eax
0x1800054ba  jmp     short loc_1800054C6
0x1800054bc  mov     dword ptr [rbp+80h], 0
0x1800054c6  mov     eax, [rbp+80h]
0x1800054cc  add     rsp, 20h
0x1800054d0  pop     rbp
0x1800054d1  retn
0x1800054d3  push    rbp
0x1800054d5  sub     rsp, 20h
0x1800054d9  mov     rbp, rdx
0x1800054dc  mov     rax, [rcx]
0x1800054df  mov     edx, [rax]
0x1800054e1  mov     [rbp+0D8h], rcx
0x1800054e8  mov     [rbp+88h], edx
0x1800054ee  mov     eax, [rbp+88h]
0x1800054f4  cmp     eax, 0E06D7363h
0x1800054f9  jnz     short loc_180005515
0x1800054fb  mov     rdx, [rbp+0D8h]
0x180005502  mov     ecx, [rbp+88h]
0x180005508  call    _XcptFilter_0
0x18000550d  mov     [rbp+90h], eax
0x180005513  jmp     short loc_18000551F
0x180005515  mov     dword ptr [rbp+90h], 0
0x18000551f  mov     eax, [rbp+90h]
0x180005525  add     rsp, 20h
0x180005529  pop     rbp
0x18000552a  retn
0x18000552c  push    rbp
0x18000552e  sub     rsp, 20h
0x180005532  mov     rbp, rdx
0x180005535  mov     rax, [rcx]
0x180005538  mov     edx, [rax]
0x18000553a  mov     [rbp+0E0h], rcx
0x180005541  mov     [rbp+98h], edx
0x180005547  mov     eax, [rbp+98h]
0x18000554d  cmp     eax, 0E06D7363h
0x180005552  jnz     short loc_18000556E
0x180005554  mov     rdx, [rbp+0E0h]
0x18000555b  mov     ecx, [rbp+98h]
0x180005561  call    _XcptFilter_0
0x180005566  mov     [rbp+0A0h], eax
0x18000556c  jmp     short loc_180005578
0x18000556e  mov     dword ptr [rbp+0A0h], 0
0x180005578  mov     eax, [rbp+0A0h]
0x18000557e  add     rsp, 20h
0x180005582  pop     rbp
0x180005583  retn
0x180005585  push    rbp
0x180005587  sub     rsp, 20h
0x18000558b  mov     rbp, rdx
0x18000558e  cmp     dword ptr [rbp+118h], 1
0x180005595  ja      short loc_1800055A1
0x180005597  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
