# MakeUniqueNoThrow<CFveUiClassFactory>(std::unique_ptr<CFveUiClassFactory,std::default_delete<CFveUiClassFactory>> &)

- ea: `0x180002f50`
- end: `0x180002f96`
- name: `??$MakeUniqueNoThrow@VCFveUiClassFactory@@@@YAJAEAV?$unique_ptr@VCFveUiClassFactory@@U?$default_delete@VCFveUiClassFactory@@@std@@@std@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003220`

## callees

- `0x180001bd4`
- `0x180001c00`
- `0x180002f50`
- `0x180002fe8`

## pseudocode

```c
__int64 __fastcall MakeUniqueNoThrow<CFveUiClassFactory>(void **a1)
{
  unsigned int v2; // ebx
  CFveUiClassFactory *v3; // rax
  CFveUiClassFactory *v4; // rax
  void *v5; // rcx

  try
  {
    v2 = 0;
    v3 = (CFveUiClassFactory *)operator new(0x10u);
    v4 = CFveUiClassFactory::CFveUiClassFactory(v3);
    v5 = *a1;
    *a1 = v4;
    if ( v5 )
      operator delete(v5, 0x10u);
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  v2 = 0;
}

```

## disassembly

```asm
0x180002f50  mov     [rsp+arg_0], rbx
0x180002f55  push    rdi
0x180002f56  sub     rsp, 20h
0x180002f5a  mov     rdi, rcx
0x180002f5d  xor     ebx, ebx
0x180002f5f  lea     ecx, [rbx+10h]; Size
0x180002f62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002f67  mov     rcx, rax; this
0x180002f6a  call    ??0CFveUiClassFactory@@QEAA@XZ; CFveUiClassFactory::CFveUiClassFactory(void)
0x180002f6f  mov     rcx, [rdi]; void *
0x180002f72  mov     [rdi], rax
0x180002f75  test    rcx, rcx
0x180002f78  jz      short loc_180002F83
0x180002f7a  lea     edx, [rbx+10h]; unsigned __int64
0x180002f7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002f82  nop
0x180002f83  jmp     short loc_180002F89
0x180002f85  mov     ebx, [rsp+28h+arg_8]
0x180002f89  mov     eax, ebx
0x180002f8b  mov     rbx, [rsp+28h+arg_0]
0x180002f90  add     rsp, 20h
0x180002f94  pop     rdi
0x180002f95  retn
```
