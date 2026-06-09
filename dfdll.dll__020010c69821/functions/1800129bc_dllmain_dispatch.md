# dllmain_dispatch

- ea: `0x1800129bc`
- end: `0x180012aed`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180012af0`

## callees

- `0x180006160`
- `0x1800127d0`
- `0x180012938`
- `0x1800129bc`
- `0x180012d58`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002DA1C <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x1800129bc  mov     rax, rsp
0x1800129bf  mov     [rax+20h], rbx
0x1800129c3  mov     [rax+18h], r8
0x1800129c7  mov     [rax+10h], edx
0x1800129ca  mov     [rax+8], rcx
0x1800129ce  push    rsi
0x1800129cf  push    rdi
0x1800129d0  push    r14
0x1800129d2  sub     rsp, 40h
0x1800129d6  mov     rsi, r8
0x1800129d9  mov     edi, edx
0x1800129db  mov     r14, rcx
0x1800129de  test    edx, edx
0x1800129e0  jnz     short loc_1800129F1
0x1800129e2  cmp     cs:dword_18002DA1C, edx
0x1800129e8  jg      short loc_1800129F1
0x1800129ea  xor     eax, eax
0x1800129ec  jmp     loc_180012ADF
0x1800129f1  lea     eax, [rdx-1]
0x1800129f4  cmp     eax, 1
0x1800129f7  ja      short loc_180012A3E
0x1800129f9  mov     rax, cs:_pRawDllMain
0x180012a00  test    rax, rax
0x180012a03  jnz     short loc_180012A0F
0x180012a05  mov     [rsp+58h+var_28], 1
0x180012a0d  jmp     short loc_180012A23
0x180012a0f  call    cs:__guard_dispatch_icall_fptr
0x180012a15  mov     ebx, eax
0x180012a17  mov     [rsp+58h+var_28], eax
0x180012a1b  test    eax, eax
0x180012a1d  jz      loc_180012AD5
0x180012a23  mov     r8, rsi
0x180012a26  mov     edx, edi
0x180012a28  mov     rcx, r14
0x180012a2b  call    dllmain_crt_dispatch
0x180012a30  mov     ebx, eax
0x180012a32  mov     [rsp+58h+var_28], eax
0x180012a36  test    eax, eax
0x180012a38  jz      loc_180012AD5
0x180012a3e  mov     r8, rsi; lpvReserved
0x180012a41  mov     edx, edi; fdwReason
0x180012a43  mov     rcx, r14; hinstDLL
0x180012a46  call    DllMain
0x180012a4b  mov     ebx, eax
0x180012a4d  mov     [rsp+58h+var_28], eax
0x180012a51  cmp     edi, 1
0x180012a54  jnz     short loc_180012A8C
0x180012a56  test    eax, eax
0x180012a58  jnz     short loc_180012A8C
0x180012a5a  mov     r8, rsi; lpvReserved
0x180012a5d  xor     edx, edx; fdwReason
0x180012a5f  mov     rcx, r14; hinstDLL
0x180012a62  call    DllMain
0x180012a67  test    rsi, rsi
0x180012a6a  setnz   cl
0x180012a6d  call    dllmain_crt_process_detach
0x180012a72  mov     rax, cs:_pRawDllMain
0x180012a79  test    rax, rax
0x180012a7c  jz      short loc_180012A8C
0x180012a7e  mov     r8, rsi
0x180012a81  xor     edx, edx
0x180012a83  mov     rcx, r14
0x180012a86  call    cs:__guard_dispatch_icall_fptr
0x180012a8c  test    edi, edi
0x180012a8e  jz      short loc_180012A95
0x180012a90  cmp     edi, 3
0x180012a93  jnz     short loc_180012AD5
0x180012a95  mov     r8, rsi
0x180012a98  mov     edx, edi
0x180012a9a  mov     rcx, r14
0x180012a9d  call    dllmain_crt_dispatch
0x180012aa2  mov     ebx, eax
0x180012aa4  mov     [rsp+58h+var_28], eax
0x180012aa8  test    eax, eax
0x180012aaa  jz      short loc_180012AD5
0x180012aac  mov     rax, cs:_pRawDllMain
0x180012ab3  test    rax, rax
0x180012ab6  jnz     short loc_180012AC1
0x180012ab8  lea     ebx, [rax+1]
0x180012abb  mov     [rsp+58h+var_28], ebx
0x180012abf  jmp     short loc_180012AD5
0x180012ac1  mov     r8, rsi
0x180012ac4  mov     edx, edi
0x180012ac6  mov     rcx, r14
0x180012ac9  call    cs:__guard_dispatch_icall_fptr
0x180012acf  mov     ebx, eax
0x180012ad1  mov     [rsp+58h+var_28], eax
0x180012ad5  jmp     short loc_180012ADD
0x180012ad7  xor     ebx, ebx
0x180012ad9  mov     [rsp+58h+var_28], ebx
0x180012add  mov     eax, ebx
0x180012adf  mov     rbx, [rsp+58h+arg_18]
0x180012ae4  add     rsp, 40h
0x180012ae8  pop     r14
0x180012aea  pop     rdi
0x180012aeb  pop     rsi
0x180012aec  retn
0x18001f47e  push    rbp
0x18001f480  sub     rsp, 30h
0x18001f484  mov     rbp, rdx
0x18001f487  mov     rax, [rcx]
0x18001f48a  mov     edx, [rax]
0x18001f48c  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001f491  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001f495  lea     r9, dllmain_crt_dispatch; int
0x18001f49c  mov     r8, [rbp+70h]; int
0x18001f4a0  mov     edx, [rbp+68h]; int
0x18001f4a3  mov     rcx, [rbp+60h]; int
0x18001f4a7  call    __scrt_dllmain_exception_filter
0x18001f4ac  nop
0x18001f4ad  add     rsp, 30h
0x18001f4b1  pop     rbp
0x18001f4b2  retn
```
