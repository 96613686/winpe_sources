# dllmain_dispatch

- ea: `0x18000bcb4`
- end: `0x18000bddb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bdf0`

## callees

- `0x18000bad0`
- `0x18000bcb4`
- `0x18000bf3c`
- `0x18001cf04`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180031370 <= 0 )
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
0x18000bcb4  mov     rax, rsp
0x18000bcb7  mov     [rax+20h], rbx
0x18000bcbb  mov     [rax+18h], r8
0x18000bcbf  mov     [rax+10h], edx
0x18000bcc2  mov     [rax+8], rcx
0x18000bcc6  push    rsi
0x18000bcc7  push    rdi
0x18000bcc8  push    r14
0x18000bcca  sub     rsp, 40h
0x18000bcce  mov     rsi, r8
0x18000bcd1  mov     edi, edx
0x18000bcd3  mov     r14, rcx
0x18000bcd6  test    edx, edx
0x18000bcd8  jnz     short loc_18000BCE9
0x18000bcda  cmp     cs:dword_180031370, edx
0x18000bce0  jg      short loc_18000BCE9
0x18000bce2  xor     eax, eax
0x18000bce4  jmp     loc_18000BDCD
0x18000bce9  lea     eax, [rdx-1]
0x18000bcec  cmp     eax, 1
0x18000bcef  ja      short loc_18000BD30
0x18000bcf1  mov     rax, cs:_pRawDllMain
0x18000bcf8  test    rax, rax
0x18000bcfb  jnz     short loc_18000BD02
0x18000bcfd  lea     ebx, [rax+1]
0x18000bd00  jmp     short loc_18000BD09
0x18000bd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd07  mov     ebx, eax
0x18000bd09  mov     [rsp+58h+var_28], ebx
0x18000bd0d  test    ebx, ebx
0x18000bd0f  jz      loc_18000BDC3
0x18000bd15  mov     r8, rsi
0x18000bd18  mov     edx, edi
0x18000bd1a  mov     rcx, r14
0x18000bd1d  call    dllmain_crt_dispatch
0x18000bd22  mov     ebx, eax
0x18000bd24  mov     [rsp+58h+var_28], eax
0x18000bd28  test    eax, eax
0x18000bd2a  jz      loc_18000BDC3
0x18000bd30  mov     r8, rsi; lpvReserved
0x18000bd33  mov     edx, edi; fdwReason
0x18000bd35  mov     rcx, r14; hinstDLL
0x18000bd38  call    DllMain
0x18000bd3d  mov     ebx, eax
0x18000bd3f  mov     [rsp+58h+var_28], eax
0x18000bd43  cmp     edi, 1
0x18000bd46  jnz     short loc_18000BD7F
0x18000bd48  test    eax, eax
0x18000bd4a  jnz     short loc_18000BD7F
0x18000bd4c  mov     r8, rsi; lpvReserved
0x18000bd4f  xor     edx, edx; fdwReason
0x18000bd51  mov     rcx, r14; hinstDLL
0x18000bd54  call    DllMain
0x18000bd59  mov     r8, rsi
0x18000bd5c  xor     edx, edx
0x18000bd5e  mov     rcx, r14
0x18000bd61  call    dllmain_crt_dispatch
0x18000bd66  mov     rax, cs:_pRawDllMain
0x18000bd6d  test    rax, rax
0x18000bd70  jz      short loc_18000BD7F
0x18000bd72  mov     r8, rsi
0x18000bd75  xor     edx, edx
0x18000bd77  mov     rcx, r14
0x18000bd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd7f  test    edi, edi
0x18000bd81  jz      short loc_18000BD88
0x18000bd83  cmp     edi, 3
0x18000bd86  jnz     short loc_18000BDC3
0x18000bd88  mov     r8, rsi
0x18000bd8b  mov     edx, edi
0x18000bd8d  mov     rcx, r14
0x18000bd90  call    dllmain_crt_dispatch
0x18000bd95  mov     ebx, eax
0x18000bd97  mov     [rsp+58h+var_28], eax
0x18000bd9b  test    eax, eax
0x18000bd9d  jz      short loc_18000BDC3
0x18000bd9f  mov     rax, cs:_pRawDllMain
0x18000bda6  test    rax, rax
0x18000bda9  jnz     short loc_18000BDB0
0x18000bdab  lea     ebx, [rax+1]
0x18000bdae  jmp     short loc_18000BDBF
0x18000bdb0  mov     r8, rsi
0x18000bdb3  mov     edx, edi
0x18000bdb5  mov     rcx, r14
0x18000bdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdbd  mov     ebx, eax
0x18000bdbf  mov     [rsp+58h+var_28], ebx
0x18000bdc3  jmp     short loc_18000BDCB
0x18000bdc5  xor     ebx, ebx
0x18000bdc7  mov     [rsp+58h+var_28], ebx
0x18000bdcb  mov     eax, ebx
0x18000bdcd  mov     rbx, [rsp+58h+arg_18]
0x18000bdd2  add     rsp, 40h
0x18000bdd6  pop     r14
0x18000bdd8  pop     rdi
0x18000bdd9  pop     rsi
0x18000bdda  retn
0x1800216d0  push    rbp
0x1800216d2  sub     rsp, 30h
0x1800216d6  mov     rbp, rdx
0x1800216d9  mov     rax, [rcx]
0x1800216dc  mov     edx, [rax]
0x1800216de  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800216e3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800216e7  lea     r9, dllmain_crt_dispatch; int
0x1800216ee  mov     r8, [rbp+70h]; int
0x1800216f2  mov     edx, [rbp+68h]; int
0x1800216f5  mov     rcx, [rbp+60h]; int
0x1800216f9  call    __scrt_dllmain_exception_filter
0x1800216fe  nop
0x1800216ff  add     rsp, 30h
0x180021703  pop     rbp
0x180021704  retn
```
