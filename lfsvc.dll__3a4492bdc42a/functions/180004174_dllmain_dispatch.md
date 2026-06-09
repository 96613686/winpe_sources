# dllmain_dispatch

- ea: `0x180004174`
- end: `0x18000429b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800042b0`

## callees

- `0x180003f90`
- `0x180004174`
- `0x180004450`
- `0x18000a58c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800122D0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x180004174  mov     rax, rsp
0x180004177  mov     [rax+20h], rbx
0x18000417b  mov     [rax+18h], r8
0x18000417f  mov     [rax+10h], edx
0x180004182  mov     [rax+8], rcx
0x180004186  push    rsi
0x180004187  push    rdi
0x180004188  push    r14
0x18000418a  sub     rsp, 40h
0x18000418e  mov     rsi, r8
0x180004191  mov     edi, edx
0x180004193  mov     r14, rcx
0x180004196  test    edx, edx
0x180004198  jnz     short loc_1800041A9
0x18000419a  cmp     cs:dword_1800122D0, edx
0x1800041a0  jg      short loc_1800041A9
0x1800041a2  xor     eax, eax
0x1800041a4  jmp     loc_18000428D
0x1800041a9  lea     eax, [rdx-1]
0x1800041ac  cmp     eax, 1
0x1800041af  ja      short loc_1800041F0
0x1800041b1  mov     rax, cs:_pRawDllMain
0x1800041b8  test    rax, rax
0x1800041bb  jnz     short loc_1800041C2
0x1800041bd  lea     ebx, [rax+1]
0x1800041c0  jmp     short loc_1800041C9
0x1800041c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c7  mov     ebx, eax
0x1800041c9  mov     [rsp+58h+var_28], ebx
0x1800041cd  test    ebx, ebx
0x1800041cf  jz      loc_180004283
0x1800041d5  mov     r8, rsi
0x1800041d8  mov     edx, edi
0x1800041da  mov     rcx, r14
0x1800041dd  call    dllmain_crt_dispatch
0x1800041e2  mov     ebx, eax
0x1800041e4  mov     [rsp+58h+var_28], eax
0x1800041e8  test    eax, eax
0x1800041ea  jz      loc_180004283
0x1800041f0  mov     r8, rsi; lpvReserved
0x1800041f3  mov     edx, edi; fdwReason
0x1800041f5  mov     rcx, r14; hinstDLL
0x1800041f8  call    DllMain
0x1800041fd  mov     ebx, eax
0x1800041ff  mov     [rsp+58h+var_28], eax
0x180004203  cmp     edi, 1
0x180004206  jnz     short loc_18000423F
0x180004208  test    eax, eax
0x18000420a  jnz     short loc_18000423F
0x18000420c  mov     r8, rsi; lpvReserved
0x18000420f  xor     edx, edx; fdwReason
0x180004211  mov     rcx, r14; hinstDLL
0x180004214  call    DllMain
0x180004219  mov     r8, rsi
0x18000421c  xor     edx, edx
0x18000421e  mov     rcx, r14
0x180004221  call    dllmain_crt_dispatch
0x180004226  mov     rax, cs:_pRawDllMain
0x18000422d  test    rax, rax
0x180004230  jz      short loc_18000423F
0x180004232  mov     r8, rsi
0x180004235  xor     edx, edx
0x180004237  mov     rcx, r14
0x18000423a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000423f  test    edi, edi
0x180004241  jz      short loc_180004248
0x180004243  cmp     edi, 3
0x180004246  jnz     short loc_180004283
0x180004248  mov     r8, rsi
0x18000424b  mov     edx, edi
0x18000424d  mov     rcx, r14
0x180004250  call    dllmain_crt_dispatch
0x180004255  mov     ebx, eax
0x180004257  mov     [rsp+58h+var_28], eax
0x18000425b  test    eax, eax
0x18000425d  jz      short loc_180004283
0x18000425f  mov     rax, cs:_pRawDllMain
0x180004266  test    rax, rax
0x180004269  jnz     short loc_180004270
0x18000426b  lea     ebx, [rax+1]
0x18000426e  jmp     short loc_18000427F
0x180004270  mov     r8, rsi
0x180004273  mov     edx, edi
0x180004275  mov     rcx, r14
0x180004278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427d  mov     ebx, eax
0x18000427f  mov     [rsp+58h+var_28], ebx
0x180004283  jmp     short loc_18000428B
0x180004285  xor     ebx, ebx
0x180004287  mov     [rsp+58h+var_28], ebx
0x18000428b  mov     eax, ebx
0x18000428d  mov     rbx, [rsp+58h+arg_18]
0x180004292  add     rsp, 40h
0x180004296  pop     r14
0x180004298  pop     rdi
0x180004299  pop     rsi
0x18000429a  retn
0x18000b4d8  push    rbp
0x18000b4da  sub     rsp, 30h
0x18000b4de  mov     rbp, rdx
0x18000b4e1  mov     rax, [rcx]
0x18000b4e4  mov     edx, [rax]
0x18000b4e6  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000b4eb  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000b4ef  lea     r9, dllmain_crt_dispatch; int
0x18000b4f6  mov     r8, [rbp+70h]; int
0x18000b4fa  mov     edx, [rbp+68h]; int
0x18000b4fd  mov     rcx, [rbp+60h]; int
0x18000b501  call    __scrt_dllmain_exception_filter
0x18000b506  nop
0x18000b507  add     rsp, 30h
0x18000b50b  pop     rbp
0x18000b50c  retn
```
