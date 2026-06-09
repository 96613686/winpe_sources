# dllmain_dispatch

- ea: `0x180006194`
- end: `0x1800062bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800062d0`

## callees

- `0x180005fb0`
- `0x180006194`
- `0x180006520`
- `0x180015154`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180031330 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, fdwReason, lpvReserved);
        else
          return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180006194  mov     rax, rsp
0x180006197  mov     [rax+20h], rbx
0x18000619b  mov     [rax+18h], r8
0x18000619f  mov     [rax+10h], edx
0x1800061a2  mov     [rax+8], rcx
0x1800061a6  push    rsi
0x1800061a7  push    rdi
0x1800061a8  push    r14
0x1800061aa  sub     rsp, 40h
0x1800061ae  mov     rsi, r8
0x1800061b1  mov     edi, edx
0x1800061b3  mov     r14, rcx
0x1800061b6  test    edx, edx
0x1800061b8  jnz     short loc_1800061C9
0x1800061ba  cmp     cs:dword_180031330, edx
0x1800061c0  jg      short loc_1800061C9
0x1800061c2  xor     eax, eax
0x1800061c4  jmp     loc_1800062AD
0x1800061c9  lea     eax, [rdx-1]
0x1800061cc  cmp     eax, 1
0x1800061cf  ja      short loc_180006210
0x1800061d1  mov     rax, cs:_pRawDllMain
0x1800061d8  test    rax, rax
0x1800061db  jnz     short loc_1800061E2
0x1800061dd  lea     ebx, [rax+1]
0x1800061e0  jmp     short loc_1800061E9
0x1800061e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e7  mov     ebx, eax
0x1800061e9  mov     [rsp+58h+var_28], ebx
0x1800061ed  test    ebx, ebx
0x1800061ef  jz      loc_1800062A3
0x1800061f5  mov     r8, rsi
0x1800061f8  mov     edx, edi
0x1800061fa  mov     rcx, r14
0x1800061fd  call    dllmain_crt_dispatch
0x180006202  mov     ebx, eax
0x180006204  mov     [rsp+58h+var_28], eax
0x180006208  test    eax, eax
0x18000620a  jz      loc_1800062A3
0x180006210  mov     r8, rsi; lpvReserved
0x180006213  mov     edx, edi; fdwReason
0x180006215  mov     rcx, r14; hinstDLL
0x180006218  call    DllMain
0x18000621d  mov     ebx, eax
0x18000621f  mov     [rsp+58h+var_28], eax
0x180006223  cmp     edi, 1
0x180006226  jnz     short loc_18000625F
0x180006228  test    eax, eax
0x18000622a  jnz     short loc_18000625F
0x18000622c  mov     r8, rsi; lpvReserved
0x18000622f  xor     edx, edx; fdwReason
0x180006231  mov     rcx, r14; hinstDLL
0x180006234  call    DllMain
0x180006239  mov     r8, rsi
0x18000623c  xor     edx, edx
0x18000623e  mov     rcx, r14
0x180006241  call    dllmain_crt_dispatch
0x180006246  mov     rax, cs:_pRawDllMain
0x18000624d  test    rax, rax
0x180006250  jz      short loc_18000625F
0x180006252  mov     r8, rsi
0x180006255  xor     edx, edx
0x180006257  mov     rcx, r14
0x18000625a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000625f  test    edi, edi
0x180006261  jz      short loc_180006268
0x180006263  cmp     edi, 3
0x180006266  jnz     short loc_1800062A3
0x180006268  mov     r8, rsi
0x18000626b  mov     edx, edi
0x18000626d  mov     rcx, r14
0x180006270  call    dllmain_crt_dispatch
0x180006275  mov     ebx, eax
0x180006277  mov     [rsp+58h+var_28], eax
0x18000627b  test    eax, eax
0x18000627d  jz      short loc_1800062A3
0x18000627f  mov     rax, cs:_pRawDllMain
0x180006286  test    rax, rax
0x180006289  jnz     short loc_180006290
0x18000628b  lea     ebx, [rax+1]
0x18000628e  jmp     short loc_18000629F
0x180006290  mov     r8, rsi
0x180006293  mov     edx, edi
0x180006295  mov     rcx, r14
0x180006298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000629d  mov     ebx, eax
0x18000629f  mov     [rsp+58h+var_28], ebx
0x1800062a3  jmp     short loc_1800062AB
0x1800062a5  xor     ebx, ebx
0x1800062a7  mov     [rsp+58h+var_28], ebx
0x1800062ab  mov     eax, ebx
0x1800062ad  mov     rbx, [rsp+58h+arg_18]
0x1800062b2  add     rsp, 40h
0x1800062b6  pop     r14
0x1800062b8  pop     rdi
0x1800062b9  pop     rsi
0x1800062ba  retn
0x18001ea4c  push    rbp
0x18001ea4e  sub     rsp, 30h
0x18001ea52  mov     rbp, rdx
0x18001ea55  mov     rax, [rcx]
0x18001ea58  mov     edx, [rax]
0x18001ea5a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001ea5f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001ea63  lea     r9, dllmain_crt_dispatch; int
0x18001ea6a  mov     r8, [rbp+70h]; int
0x18001ea6e  mov     edx, [rbp+68h]; int
0x18001ea71  mov     rcx, [rbp+60h]; int
0x18001ea75  call    __scrt_dllmain_exception_filter
0x18001ea7a  nop
0x18001ea7b  add     rsp, 30h
0x18001ea7f  pop     rbp
0x18001ea80  retn
```
