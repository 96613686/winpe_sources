# dllmain_dispatch

- ea: `0x180007154`
- end: `0x18000727b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180007290`

## callees

- `0x180004060`
- `0x180006f70`
- `0x180007154`
- `0x1800074e4`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800120D0 <= 0 )
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
0x180007154  mov     rax, rsp
0x180007157  mov     [rax+20h], rbx
0x18000715b  mov     [rax+18h], r8
0x18000715f  mov     [rax+10h], edx
0x180007162  mov     [rax+8], rcx
0x180007166  push    rsi
0x180007167  push    rdi
0x180007168  push    r14
0x18000716a  sub     rsp, 40h
0x18000716e  mov     rsi, r8
0x180007171  mov     edi, edx
0x180007173  mov     r14, rcx
0x180007176  test    edx, edx
0x180007178  jnz     short loc_180007189
0x18000717a  cmp     cs:dword_1800120D0, edx
0x180007180  jg      short loc_180007189
0x180007182  xor     eax, eax
0x180007184  jmp     loc_18000726D
0x180007189  lea     eax, [rdx-1]
0x18000718c  cmp     eax, 1
0x18000718f  ja      short loc_1800071D0
0x180007191  mov     rax, cs:_pRawDllMain
0x180007198  test    rax, rax
0x18000719b  jnz     short loc_1800071A2
0x18000719d  lea     ebx, [rax+1]
0x1800071a0  jmp     short loc_1800071A9
0x1800071a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a7  mov     ebx, eax
0x1800071a9  mov     [rsp+58h+var_28], ebx
0x1800071ad  test    ebx, ebx
0x1800071af  jz      loc_180007263
0x1800071b5  mov     r8, rsi
0x1800071b8  mov     edx, edi
0x1800071ba  mov     rcx, r14
0x1800071bd  call    dllmain_crt_dispatch
0x1800071c2  mov     ebx, eax
0x1800071c4  mov     [rsp+58h+var_28], eax
0x1800071c8  test    eax, eax
0x1800071ca  jz      loc_180007263
0x1800071d0  mov     r8, rsi; lpvReserved
0x1800071d3  mov     edx, edi; fdwReason
0x1800071d5  mov     rcx, r14; hinstDLL
0x1800071d8  call    DllMain
0x1800071dd  mov     ebx, eax
0x1800071df  mov     [rsp+58h+var_28], eax
0x1800071e3  cmp     edi, 1
0x1800071e6  jnz     short loc_18000721F
0x1800071e8  test    eax, eax
0x1800071ea  jnz     short loc_18000721F
0x1800071ec  mov     r8, rsi; lpvReserved
0x1800071ef  xor     edx, edx; fdwReason
0x1800071f1  mov     rcx, r14; hinstDLL
0x1800071f4  call    DllMain
0x1800071f9  mov     r8, rsi
0x1800071fc  xor     edx, edx
0x1800071fe  mov     rcx, r14
0x180007201  call    dllmain_crt_dispatch
0x180007206  mov     rax, cs:_pRawDllMain
0x18000720d  test    rax, rax
0x180007210  jz      short loc_18000721F
0x180007212  mov     r8, rsi
0x180007215  xor     edx, edx
0x180007217  mov     rcx, r14
0x18000721a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000721f  test    edi, edi
0x180007221  jz      short loc_180007228
0x180007223  cmp     edi, 3
0x180007226  jnz     short loc_180007263
0x180007228  mov     r8, rsi
0x18000722b  mov     edx, edi
0x18000722d  mov     rcx, r14
0x180007230  call    dllmain_crt_dispatch
0x180007235  mov     ebx, eax
0x180007237  mov     [rsp+58h+var_28], eax
0x18000723b  test    eax, eax
0x18000723d  jz      short loc_180007263
0x18000723f  mov     rax, cs:_pRawDllMain
0x180007246  test    rax, rax
0x180007249  jnz     short loc_180007250
0x18000724b  lea     ebx, [rax+1]
0x18000724e  jmp     short loc_18000725F
0x180007250  mov     r8, rsi
0x180007253  mov     edx, edi
0x180007255  mov     rcx, r14
0x180007258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000725d  mov     ebx, eax
0x18000725f  mov     [rsp+58h+var_28], ebx
0x180007263  jmp     short loc_18000726B
0x180007265  xor     ebx, ebx
0x180007267  mov     [rsp+58h+var_28], ebx
0x18000726b  mov     eax, ebx
0x18000726d  mov     rbx, [rsp+58h+arg_18]
0x180007272  add     rsp, 40h
0x180007276  pop     r14
0x180007278  pop     rdi
0x180007279  pop     rsi
0x18000727a  retn
0x18000beac  push    rbp
0x18000beae  sub     rsp, 30h
0x18000beb2  mov     rbp, rdx
0x18000beb5  mov     rax, [rcx]
0x18000beb8  mov     edx, [rax]
0x18000beba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000bebf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000bec3  lea     r9, dllmain_crt_dispatch; int
0x18000beca  mov     r8, [rbp+70h]; int
0x18000bece  mov     edx, [rbp+68h]; int
0x18000bed1  mov     rcx, [rbp+60h]; int
0x18000bed5  call    __scrt_dllmain_exception_filter
0x18000beda  nop
0x18000bedb  add     rsp, 30h
0x18000bedf  pop     rbp
0x18000bee0  retn
```
