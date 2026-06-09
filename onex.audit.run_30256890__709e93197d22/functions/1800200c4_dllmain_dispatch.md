# dllmain_dispatch

- ea: `0x1800200c4`
- end: `0x1800201eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180020200`

## callees

- `0x180010f20`
- `0x18001fee0`
- `0x1800200c4`
- `0x18002047c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003A290 <= 0 )
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
0x1800200c4  mov     rax, rsp
0x1800200c7  mov     [rax+20h], rbx
0x1800200cb  mov     [rax+18h], r8
0x1800200cf  mov     [rax+10h], edx
0x1800200d2  mov     [rax+8], rcx
0x1800200d6  push    rsi
0x1800200d7  push    rdi
0x1800200d8  push    r14
0x1800200da  sub     rsp, 40h
0x1800200de  mov     rsi, r8
0x1800200e1  mov     edi, edx
0x1800200e3  mov     r14, rcx
0x1800200e6  test    edx, edx
0x1800200e8  jnz     short loc_1800200F9
0x1800200ea  cmp     cs:dword_18003A290, edx
0x1800200f0  jg      short loc_1800200F9
0x1800200f2  xor     eax, eax
0x1800200f4  jmp     loc_1800201DD
0x1800200f9  lea     eax, [rdx-1]
0x1800200fc  cmp     eax, 1
0x1800200ff  ja      short loc_180020140
0x180020101  mov     rax, cs:_pRawDllMain
0x180020108  test    rax, rax
0x18002010b  jnz     short loc_180020112
0x18002010d  lea     ebx, [rax+1]
0x180020110  jmp     short loc_180020119
0x180020112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020117  mov     ebx, eax
0x180020119  mov     [rsp+58h+var_28], ebx
0x18002011d  test    ebx, ebx
0x18002011f  jz      loc_1800201D3
0x180020125  mov     r8, rsi
0x180020128  mov     edx, edi
0x18002012a  mov     rcx, r14
0x18002012d  call    dllmain_crt_dispatch
0x180020132  mov     ebx, eax
0x180020134  mov     [rsp+58h+var_28], eax
0x180020138  test    eax, eax
0x18002013a  jz      loc_1800201D3
0x180020140  mov     r8, rsi; lpvReserved
0x180020143  mov     edx, edi; fdwReason
0x180020145  mov     rcx, r14; hinstDLL
0x180020148  call    DllMain
0x18002014d  mov     ebx, eax
0x18002014f  mov     [rsp+58h+var_28], eax
0x180020153  cmp     edi, 1
0x180020156  jnz     short loc_18002018F
0x180020158  test    eax, eax
0x18002015a  jnz     short loc_18002018F
0x18002015c  mov     r8, rsi; lpvReserved
0x18002015f  xor     edx, edx; fdwReason
0x180020161  mov     rcx, r14; hinstDLL
0x180020164  call    DllMain
0x180020169  mov     r8, rsi
0x18002016c  xor     edx, edx
0x18002016e  mov     rcx, r14
0x180020171  call    dllmain_crt_dispatch
0x180020176  mov     rax, cs:_pRawDllMain
0x18002017d  test    rax, rax
0x180020180  jz      short loc_18002018F
0x180020182  mov     r8, rsi
0x180020185  xor     edx, edx
0x180020187  mov     rcx, r14
0x18002018a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002018f  test    edi, edi
0x180020191  jz      short loc_180020198
0x180020193  cmp     edi, 3
0x180020196  jnz     short loc_1800201D3
0x180020198  mov     r8, rsi
0x18002019b  mov     edx, edi
0x18002019d  mov     rcx, r14
0x1800201a0  call    dllmain_crt_dispatch
0x1800201a5  mov     ebx, eax
0x1800201a7  mov     [rsp+58h+var_28], eax
0x1800201ab  test    eax, eax
0x1800201ad  jz      short loc_1800201D3
0x1800201af  mov     rax, cs:_pRawDllMain
0x1800201b6  test    rax, rax
0x1800201b9  jnz     short loc_1800201C0
0x1800201bb  lea     ebx, [rax+1]
0x1800201be  jmp     short loc_1800201CF
0x1800201c0  mov     r8, rsi
0x1800201c3  mov     edx, edi
0x1800201c5  mov     rcx, r14
0x1800201c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201cd  mov     ebx, eax
0x1800201cf  mov     [rsp+58h+var_28], ebx
0x1800201d3  jmp     short loc_1800201DB
0x1800201d5  xor     ebx, ebx
0x1800201d7  mov     [rsp+58h+var_28], ebx
0x1800201db  mov     eax, ebx
0x1800201dd  mov     rbx, [rsp+58h+arg_18]
0x1800201e2  add     rsp, 40h
0x1800201e6  pop     r14
0x1800201e8  pop     rdi
0x1800201e9  pop     rsi
0x1800201ea  retn
0x18002f7cc  push    rbp
0x18002f7ce  sub     rsp, 30h
0x18002f7d2  mov     rbp, rdx
0x18002f7d5  mov     rax, [rcx]
0x18002f7d8  mov     edx, [rax]
0x18002f7da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002f7df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002f7e3  lea     r9, dllmain_crt_dispatch; int
0x18002f7ea  mov     r8, [rbp+70h]; int
0x18002f7ee  mov     edx, [rbp+68h]; int
0x18002f7f1  mov     rcx, [rbp+60h]; int
0x18002f7f5  call    __scrt_dllmain_exception_filter
0x18002f7fa  nop
0x18002f7fb  add     rsp, 30h
0x18002f7ff  pop     rbp
0x18002f800  retn
```
