# dllmain_dispatch

- ea: `0x180013f94`
- end: `0x1800140bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800140d0`

## callees

- `0x180013414`
- `0x180013db0`
- `0x180013f94`
- `0x180014270`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003DF10 <= 0 )
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
0x180013f94  mov     rax, rsp
0x180013f97  mov     [rax+20h], rbx
0x180013f9b  mov     [rax+18h], r8
0x180013f9f  mov     [rax+10h], edx
0x180013fa2  mov     [rax+8], rcx
0x180013fa6  push    rsi
0x180013fa7  push    rdi
0x180013fa8  push    r14
0x180013faa  sub     rsp, 40h
0x180013fae  mov     rsi, r8
0x180013fb1  mov     edi, edx
0x180013fb3  mov     r14, rcx
0x180013fb6  test    edx, edx
0x180013fb8  jnz     short loc_180013FC9
0x180013fba  cmp     cs:dword_18003DF10, edx
0x180013fc0  jg      short loc_180013FC9
0x180013fc2  xor     eax, eax
0x180013fc4  jmp     loc_1800140AD
0x180013fc9  lea     eax, [rdx-1]
0x180013fcc  cmp     eax, 1
0x180013fcf  ja      short loc_180014010
0x180013fd1  mov     rax, cs:_pRawDllMain
0x180013fd8  test    rax, rax
0x180013fdb  jnz     short loc_180013FE2
0x180013fdd  lea     ebx, [rax+1]
0x180013fe0  jmp     short loc_180013FE9
0x180013fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe7  mov     ebx, eax
0x180013fe9  mov     [rsp+58h+var_28], ebx
0x180013fed  test    ebx, ebx
0x180013fef  jz      loc_1800140A3
0x180013ff5  mov     r8, rsi
0x180013ff8  mov     edx, edi
0x180013ffa  mov     rcx, r14
0x180013ffd  call    dllmain_crt_dispatch
0x180014002  mov     ebx, eax
0x180014004  mov     [rsp+58h+var_28], eax
0x180014008  test    eax, eax
0x18001400a  jz      loc_1800140A3
0x180014010  mov     r8, rsi; lpvReserved
0x180014013  mov     edx, edi; fdwReason
0x180014015  mov     rcx, r14; hinstDLL
0x180014018  call    DllMain
0x18001401d  mov     ebx, eax
0x18001401f  mov     [rsp+58h+var_28], eax
0x180014023  cmp     edi, 1
0x180014026  jnz     short loc_18001405F
0x180014028  test    eax, eax
0x18001402a  jnz     short loc_18001405F
0x18001402c  mov     r8, rsi; lpvReserved
0x18001402f  xor     edx, edx; fdwReason
0x180014031  mov     rcx, r14; hinstDLL
0x180014034  call    DllMain
0x180014039  mov     r8, rsi
0x18001403c  xor     edx, edx
0x18001403e  mov     rcx, r14
0x180014041  call    dllmain_crt_dispatch
0x180014046  mov     rax, cs:_pRawDllMain
0x18001404d  test    rax, rax
0x180014050  jz      short loc_18001405F
0x180014052  mov     r8, rsi
0x180014055  xor     edx, edx
0x180014057  mov     rcx, r14
0x18001405a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001405f  test    edi, edi
0x180014061  jz      short loc_180014068
0x180014063  cmp     edi, 3
0x180014066  jnz     short loc_1800140A3
0x180014068  mov     r8, rsi
0x18001406b  mov     edx, edi
0x18001406d  mov     rcx, r14
0x180014070  call    dllmain_crt_dispatch
0x180014075  mov     ebx, eax
0x180014077  mov     [rsp+58h+var_28], eax
0x18001407b  test    eax, eax
0x18001407d  jz      short loc_1800140A3
0x18001407f  mov     rax, cs:_pRawDllMain
0x180014086  test    rax, rax
0x180014089  jnz     short loc_180014090
0x18001408b  lea     ebx, [rax+1]
0x18001408e  jmp     short loc_18001409F
0x180014090  mov     r8, rsi
0x180014093  mov     edx, edi
0x180014095  mov     rcx, r14
0x180014098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001409d  mov     ebx, eax
0x18001409f  mov     [rsp+58h+var_28], ebx
0x1800140a3  jmp     short loc_1800140AB
0x1800140a5  xor     ebx, ebx
0x1800140a7  mov     [rsp+58h+var_28], ebx
0x1800140ab  mov     eax, ebx
0x1800140ad  mov     rbx, [rsp+58h+arg_18]
0x1800140b2  add     rsp, 40h
0x1800140b6  pop     r14
0x1800140b8  pop     rdi
0x1800140b9  pop     rsi
0x1800140ba  retn
0x180023ad1  push    rbp
0x180023ad3  sub     rsp, 30h
0x180023ad7  mov     rbp, rdx
0x180023ada  mov     rax, [rcx]
0x180023add  mov     edx, [rax]
0x180023adf  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180023ae4  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180023ae8  lea     r9, dllmain_crt_dispatch; int
0x180023aef  mov     r8, [rbp+70h]; int
0x180023af3  mov     edx, [rbp+68h]; int
0x180023af6  mov     rcx, [rbp+60h]; int
0x180023afa  call    __scrt_dllmain_exception_filter
0x180023aff  nop
0x180023b00  add     rsp, 30h
0x180023b04  pop     rbp
0x180023b05  retn
```
