# MakeUniqueNoThrow<CFveUiDispatch>(std::unique_ptr<CFveUiDispatch,std::default_delete<CFveUiDispatch>> &)

- ea: `0x180002f9c`
- end: `0x180002fe2`
- name: `??$MakeUniqueNoThrow@VCFveUiDispatch@@@@YAJAEAV?$unique_ptr@VCFveUiDispatch@@U?$default_delete@VCFveUiDispatch@@@std@@@std@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000355c`

## callees

- `0x180001bd4`
- `0x180001c00`
- `0x180002f9c`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall MakeUniqueNoThrow<CFveUiDispatch>(void **a1)
{
  CFveUiDispatch *v2; // rax
  CFveUiDispatch *v3; // rax
  void *v4; // rcx

  v2 = (CFveUiDispatch *)operator new(0x10u);
  v3 = CFveUiDispatch::CFveUiDispatch(v2);
  v4 = *a1;
  *a1 = v3;
  if ( v4 )
    operator delete(v4, 0x10u);
  return 0;
}

```

## disassembly

```asm
0x180002f9c  mov     [rsp+arg_0], rbx
0x180002fa1  push    rdi
0x180002fa2  sub     rsp, 20h
0x180002fa6  mov     rdi, rcx
0x180002fa9  xor     ebx, ebx
0x180002fab  lea     ecx, [rbx+10h]; Size
0x180002fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002fb3  mov     rcx, rax; this
0x180002fb6  call    ??0CFveUiDispatch@@QEAA@XZ; CFveUiDispatch::CFveUiDispatch(void)
0x180002fbb  mov     rcx, [rdi]; void *
0x180002fbe  mov     [rdi], rax
0x180002fc1  test    rcx, rcx
0x180002fc4  jz      short loc_180002FCF
0x180002fc6  lea     edx, [rbx+10h]; unsigned __int64
0x180002fc9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002fce  nop
0x180002fcf  jmp     short loc_180002FD5
0x180002fd1  mov     ebx, [rsp+28h+arg_8]
0x180002fd5  mov     eax, ebx
0x180002fd7  mov     rbx, [rsp+28h+arg_0]
0x180002fdc  add     rsp, 20h
0x180002fe0  pop     rdi
0x180002fe1  retn
```
