# __DllMainCRTStartup

- ea: `0x1800013d4`
- end: `0x1800015e0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001390`

## callees

- `0x180001050`
- `0x180001160`
- `0x1800013d4`
- `0x180001b85`
- `0x18002f150`

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
  if ( (_DWORD)fdwReason || dword_180045F20 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180045F24 = 1;
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
            if ( dword_180045F24 )
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
0x1800013d4  mov     [rsp+lpvReserved], r8
0x1800013d9  mov     [rsp+arg_8], edx
0x1800013dd  mov     [rsp+arg_0], rcx
0x1800013e2  push    rbx
0x1800013e3  push    rsi
0x1800013e4  push    rdi
0x1800013e5  sub     rsp, 0F0h
0x1800013ec  mov     edi, edx
0x1800013ee  mov     rsi, rcx
0x1800013f1  mov     ebx, 1
0x1800013f6  cmp     edx, ebx
0x1800013f8  ja      short loc_180001400
0x1800013fa  mov     cs:__native_dllmain_reason, edx
0x180001400  test    edx, edx
0x180001402  jnz     short loc_180001417
0x180001404  cmp     cs:dword_180045F20, edx
0x18000140a  jnz     short loc_180001417
0x18000140c  xor     ebx, ebx
0x18000140e  mov     [rsp+108h+var_E8], ebx
0x180001412  jmp     loc_1800015C4
0x180001417  lea     eax, [rdx-1]
0x18000141a  cmp     eax, 1
0x18000141d  ja      loc_1800014A4
0x180001423  mov     rax, cs:_pRawDllMain
0x18000142a  test    rax, rax
0x18000142d  jz      short loc_180001465
0x18000142f  cmp     edx, 1
0x180001432  jnz     short loc_18000143A
0x180001434  mov     cs:dword_180045F24, edx
0x18000143a  mov     r8, [rsp+108h+lpvReserved]
0x180001442  call    cs:__guard_dispatch_icall_fptr
0x180001448  mov     ebx, eax
0x18000144a  mov     [rsp+108h+var_E8], eax
0x18000144e  jmp     short loc_180001465
0x180001450  xor     ebx, ebx
0x180001452  mov     [rsp+108h+var_E8], ebx
0x180001456  mov     edi, [rsp+108h+arg_8]
0x18000145d  mov     rsi, [rsp+108h+arg_0]
0x180001465  test    ebx, ebx
0x180001467  jz      loc_1800015C4
0x18000146d  mov     r8, [rsp+108h+lpvReserved]
0x180001475  mov     edx, edi
0x180001477  mov     rcx, rsi
0x18000147a  call    _CRT_INIT
0x18000147f  mov     ebx, eax
0x180001481  mov     [rsp+108h+var_E8], eax
0x180001485  jmp     short loc_18000149C
0x180001487  xor     ebx, ebx
0x180001489  mov     [rsp+108h+var_E8], ebx
0x18000148d  mov     edi, [rsp+108h+arg_8]
0x180001494  mov     rsi, [rsp+108h+arg_0]
0x18000149c  test    ebx, ebx
0x18000149e  jz      loc_1800015C4
0x1800014a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800014ac  mov     edx, edi; fdwReason
0x1800014ae  mov     rcx, rsi; hinstDLL
0x1800014b1  call    DllMain
0x1800014b6  mov     ebx, eax
0x1800014b8  mov     [rsp+108h+var_E8], eax
0x1800014bc  jmp     short loc_1800014D3
0x1800014be  xor     ebx, ebx
0x1800014c0  mov     [rsp+108h+var_E8], ebx
0x1800014c4  mov     edi, [rsp+108h+arg_8]
0x1800014cb  mov     rsi, [rsp+108h+arg_0]
0x1800014d3  cmp     edi, 1
0x1800014d6  jnz     short loc_18000154F
0x1800014d8  test    ebx, ebx
0x1800014da  jnz     short loc_18000154F
0x1800014dc  xor     r8d, r8d; lpvReserved
0x1800014df  xor     edx, edx; fdwReason
0x1800014e1  mov     rcx, rsi; hinstDLL
0x1800014e4  call    DllMain
0x1800014e9  jmp     short loc_1800014FE
0x1800014eb  mov     edi, [rsp+108h+arg_8]
0x1800014f2  mov     rsi, [rsp+108h+arg_0]
0x1800014fa  mov     ebx, [rsp+108h+var_E8]
0x1800014fe  xor     r8d, r8d
0x180001501  xor     edx, edx
0x180001503  mov     rcx, rsi
0x180001506  call    _CRT_INIT
0x18000150b  jmp     short loc_180001520
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  mov     rsi, [rsp+108h+arg_0]
0x18000151c  mov     ebx, [rsp+108h+var_E8]
0x180001520  mov     rax, cs:_pRawDllMain
0x180001527  test    rax, rax
0x18000152a  jz      short loc_18000154F
0x18000152c  xor     r8d, r8d
0x18000152f  xor     edx, edx
0x180001531  mov     rcx, rsi
0x180001534  call    cs:__guard_dispatch_icall_fptr
0x18000153a  jmp     short loc_18000154F
0x18000153c  mov     edi, [rsp+108h+arg_8]
0x180001543  mov     rsi, [rsp+108h+arg_0]
0x18000154b  mov     ebx, [rsp+108h+var_E8]
0x18000154f  test    edi, edi
0x180001551  jz      short loc_180001558
0x180001553  cmp     edi, 3
0x180001556  jnz     short loc_1800015C4
0x180001558  mov     r8, [rsp+108h+lpvReserved]
0x180001560  mov     edx, edi
0x180001562  mov     rcx, rsi
0x180001565  call    _CRT_INIT
0x18000156a  mov     ebx, eax
0x18000156c  mov     [rsp+108h+var_E8], eax
0x180001570  jmp     short loc_180001587
0x180001572  xor     ebx, ebx
0x180001574  mov     [rsp+108h+var_E8], ebx
0x180001578  mov     edi, [rsp+108h+arg_8]
0x18000157f  mov     rsi, [rsp+108h+arg_0]
0x180001587  mov     rax, cs:_pRawDllMain
0x18000158e  test    rax, rax
0x180001591  jz      short loc_1800015C4
0x180001593  cmp     cs:dword_180045F24, 0
0x18000159a  jz      short loc_1800015C4
0x18000159c  mov     r8, [rsp+108h+lpvReserved]
0x1800015a4  mov     edx, edi
0x1800015a6  mov     rcx, rsi
0x1800015a9  call    cs:__guard_dispatch_icall_fptr
0x1800015af  mov     ebx, eax
0x1800015b1  mov     [rsp+108h+var_E8], eax
0x1800015b5  jmp     short loc_1800015C4
0x1800015b7  xor     ebx, ebx
0x1800015b9  mov     [rsp+108h+var_E8], ebx
0x1800015bd  mov     edi, [rsp+108h+arg_8]
0x1800015c4  cmp     edi, 1
0x1800015c7  ja      short loc_1800015D3
0x1800015c9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015d3  mov     eax, ebx
0x1800015d5  add     rsp, 0F0h
0x1800015dc  pop     rdi
0x1800015dd  pop     rsi
0x1800015de  pop     rbx
0x1800015df  retn
0x18002f224  push    rbp
0x18002f226  sub     rsp, 20h
0x18002f22a  mov     rbp, rdx
0x18002f22d  mov     rax, [rcx]
0x18002f230  mov     edx, [rax]
0x18002f232  mov     [rbp+0A8h], rcx
0x18002f239  mov     [rbp+28h], edx
0x18002f23c  mov     eax, [rbp+28h]
0x18002f23f  cmp     eax, 0E06D7363h
0x18002f244  jnz     short loc_18002F25A
0x18002f246  mov     rdx, [rbp+0A8h]
0x18002f24d  mov     ecx, [rbp+28h]
0x18002f250  call    _XcptFilter_0
0x18002f255  mov     [rbp+30h], eax
0x18002f258  jmp     short loc_18002F261
0x18002f25a  mov     dword ptr [rbp+30h], 0
0x18002f261  mov     eax, [rbp+30h]
0x18002f264  add     rsp, 20h
0x18002f268  pop     rbp
0x18002f269  retn
0x18002f26b  push    rbp
0x18002f26d  sub     rsp, 20h
0x18002f271  mov     rbp, rdx
0x18002f274  mov     rax, [rcx]
0x18002f277  mov     edx, [rax]
0x18002f279  mov     [rbp+0B0h], rcx
0x18002f280  mov     [rbp+38h], edx
0x18002f283  mov     eax, [rbp+38h]
0x18002f286  cmp     eax, 0E06D7363h
0x18002f28b  jnz     short loc_18002F2A1
0x18002f28d  mov     rdx, [rbp+0B0h]
0x18002f294  mov     ecx, [rbp+38h]
0x18002f297  call    _XcptFilter_0
0x18002f29c  mov     [rbp+40h], eax
0x18002f29f  jmp     short loc_18002F2A8
0x18002f2a1  mov     dword ptr [rbp+40h], 0
0x18002f2a8  mov     eax, [rbp+40h]
0x18002f2ab  add     rsp, 20h
0x18002f2af  pop     rbp
0x18002f2b0  retn
0x18002f2b2  push    rbp
0x18002f2b4  sub     rsp, 20h
0x18002f2b8  mov     rbp, rdx
0x18002f2bb  mov     rax, [rcx]
0x18002f2be  mov     edx, [rax]
0x18002f2c0  mov     [rbp+0B8h], rcx
0x18002f2c7  mov     [rbp+48h], edx
0x18002f2ca  mov     eax, [rbp+48h]
0x18002f2cd  cmp     eax, 0E06D7363h
0x18002f2d2  jnz     short loc_18002F2E8
0x18002f2d4  mov     rdx, [rbp+0B8h]
0x18002f2db  mov     ecx, [rbp+48h]
0x18002f2de  call    _XcptFilter_0
0x18002f2e3  mov     [rbp+50h], eax
0x18002f2e6  jmp     short loc_18002F2EF
0x18002f2e8  mov     dword ptr [rbp+50h], 0
0x18002f2ef  mov     eax, [rbp+50h]
0x18002f2f2  add     rsp, 20h
0x18002f2f6  pop     rbp
0x18002f2f7  retn
0x18002f2f9  push    rbp
0x18002f2fb  sub     rsp, 20h
0x18002f2ff  mov     rbp, rdx
0x18002f302  mov     rax, [rcx]
0x18002f305  mov     edx, [rax]
0x18002f307  mov     [rbp+0C0h], rcx
0x18002f30e  mov     [rbp+58h], edx
0x18002f311  mov     eax, [rbp+58h]
0x18002f314  cmp     eax, 0E06D7363h
0x18002f319  jnz     short loc_18002F32F
0x18002f31b  mov     rdx, [rbp+0C0h]
0x18002f322  mov     ecx, [rbp+58h]
0x18002f325  call    _XcptFilter_0
0x18002f32a  mov     [rbp+60h], eax
0x18002f32d  jmp     short loc_18002F336
0x18002f32f  mov     dword ptr [rbp+60h], 0
0x18002f336  mov     eax, [rbp+60h]
0x18002f339  add     rsp, 20h
0x18002f33d  pop     rbp
0x18002f33e  retn
0x18002f340  push    rbp
0x18002f342  sub     rsp, 20h
0x18002f346  mov     rbp, rdx
0x18002f349  mov     rax, [rcx]
0x18002f34c  mov     edx, [rax]
0x18002f34e  mov     [rbp+0C8h], rcx
0x18002f355  mov     [rbp+68h], edx
0x18002f358  mov     eax, [rbp+68h]
0x18002f35b  cmp     eax, 0E06D7363h
0x18002f360  jnz     short loc_18002F376
0x18002f362  mov     rdx, [rbp+0C8h]
0x18002f369  mov     ecx, [rbp+68h]
0x18002f36c  call    _XcptFilter_0
0x18002f371  mov     [rbp+70h], eax
0x18002f374  jmp     short loc_18002F37D
0x18002f376  mov     dword ptr [rbp+70h], 0
0x18002f37d  mov     eax, [rbp+70h]
0x18002f380  add     rsp, 20h
0x18002f384  pop     rbp
0x18002f385  retn
0x18002f387  push    rbp
0x18002f389  sub     rsp, 20h
0x18002f38d  mov     rbp, rdx
0x18002f390  mov     rax, [rcx]
0x18002f393  mov     edx, [rax]
0x18002f395  mov     [rbp+0D0h], rcx
0x18002f39c  mov     [rbp+78h], edx
0x18002f39f  mov     eax, [rbp+78h]
0x18002f3a2  cmp     eax, 0E06D7363h
0x18002f3a7  jnz     short loc_18002F3C0
0x18002f3a9  mov     rdx, [rbp+0D0h]
0x18002f3b0  mov     ecx, [rbp+78h]
0x18002f3b3  call    _XcptFilter_0
0x18002f3b8  mov     [rbp+80h], eax
0x18002f3be  jmp     short loc_18002F3CA
0x18002f3c0  mov     dword ptr [rbp+80h], 0
0x18002f3ca  mov     eax, [rbp+80h]
0x18002f3d0  add     rsp, 20h
0x18002f3d4  pop     rbp
0x18002f3d5  retn
0x18002f3d7  push    rbp
0x18002f3d9  sub     rsp, 20h
0x18002f3dd  mov     rbp, rdx
0x18002f3e0  mov     rax, [rcx]
0x18002f3e3  mov     edx, [rax]
0x18002f3e5  mov     [rbp+0D8h], rcx
0x18002f3ec  mov     [rbp+88h], edx
0x18002f3f2  mov     eax, [rbp+88h]
0x18002f3f8  cmp     eax, 0E06D7363h
0x18002f3fd  jnz     short loc_18002F419
0x18002f3ff  mov     rdx, [rbp+0D8h]
0x18002f406  mov     ecx, [rbp+88h]
0x18002f40c  call    _XcptFilter_0
0x18002f411  mov     [rbp+90h], eax
0x18002f417  jmp     short loc_18002F423
0x18002f419  mov     dword ptr [rbp+90h], 0
0x18002f423  mov     eax, [rbp+90h]
0x18002f429  add     rsp, 20h
0x18002f42d  pop     rbp
0x18002f42e  retn
0x18002f430  push    rbp
0x18002f432  sub     rsp, 20h
0x18002f436  mov     rbp, rdx
0x18002f439  mov     rax, [rcx]
0x18002f43c  mov     edx, [rax]
0x18002f43e  mov     [rbp+0E0h], rcx
0x18002f445  mov     [rbp+98h], edx
0x18002f44b  mov     eax, [rbp+98h]
0x18002f451  cmp     eax, 0E06D7363h
0x18002f456  jnz     short loc_18002F472
0x18002f458  mov     rdx, [rbp+0E0h]
0x18002f45f  mov     ecx, [rbp+98h]
0x18002f465  call    _XcptFilter_0
0x18002f46a  mov     [rbp+0A0h], eax
0x18002f470  jmp     short loc_18002F47C
0x18002f472  mov     dword ptr [rbp+0A0h], 0
0x18002f47c  mov     eax, [rbp+0A0h]
0x18002f482  add     rsp, 20h
0x18002f486  pop     rbp
0x18002f487  retn
0x18002f489  push    rbp
0x18002f48b  sub     rsp, 20h
0x18002f48f  mov     rbp, rdx
0x18002f492  cmp     dword ptr [rbp+118h], 1
0x18002f499  ja      short loc_18002F4A5
0x18002f49b  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
