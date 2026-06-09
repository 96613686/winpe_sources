# __ExceptionPtr::_CallCopyCtor(void *,void *,unsigned __int64,_s_CatchableType const * const)

- ea: `0x180017f20`
- end: `0x180017fe6`
- name: `?_CallCopyCtor@__ExceptionPtr@@AEBAXPEAX0_KQEBU_s_CatchableType@@@Z`
- size: `198`
- prototype: `void(__ExceptionPtr *__hidden this, void *, void *, unsigned __int64, const struct _s_CatchableType *const)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180017970`
- `0x180018568`

## callees

- `0x18000b350`
- `0x18000c1b4`
- `0x18000c1c4`
- `0x180017f20`
- `0x180079c80`
- `0x18007d020`

## pseudocode

```c
void __fastcall __ExceptionPtr::_CallCopyCtor(
        __ExceptionPtr *this,
        void *a2,
        _QWORD *a3,
        size_t a4,
        const struct _s_CatchableType *const a5)
{
  void *v8; // rbx
  PMD *p_thisDisplacement; // rdx
  void *v10; // rax
  void *v11; // rax

  if ( (a5->properties & 1) == 0 && (v8 = 0, a5->copyFunction) && *((_QWORD *)this + 7) + a5->copyFunction )
  {
    try
    {
      p_thisDisplacement = &a5->thisDisplacement;
      if ( (a5->properties & 4) != 0 )
      {
        v10 = (void *)_AdjustPointer(a3, p_thisDisplacement);
        if ( a5->copyFunction )
          v8 = (void *)(*((_QWORD *)this + 7) + a5->copyFunction);
        _CallMemberFunction2(a2, v8, v10, 1);
      }
      else
      {
        v11 = (void *)_AdjustPointer(a3, p_thisDisplacement);
        if ( a5->copyFunction )
          v8 = (void *)(*((_QWORD *)this + 7) + a5->copyFunction);
        _CallMemberFunction1(a2, v8, v11);
      }
    }
    catch ( ... )
    {
      terminate();
    }
  }
  else
  {
    memmove(a2, a3, a4);
    if ( (a5->properties & 8) != 0 && *a3 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  }
}

```

## disassembly

```asm
0x180017f20  push    rbx
0x180017f22  push    rsi
0x180017f23  push    rdi
0x180017f24  push    r14
0x180017f26  push    r15
0x180017f28  sub     rsp, 30h
0x180017f2c  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180017f35  mov     rsi, r8
0x180017f38  mov     r15, rdx
0x180017f3b  mov     r14, rcx
0x180017f3e  mov     rdi, [rsp+58h+arg_20]
0x180017f46  test    byte ptr [rdi], 1
0x180017f49  jnz     short loc_180017FB3
0x180017f4b  xor     ebx, ebx
0x180017f4d  cmp     [rdi+18h], ebx
0x180017f50  jz      short loc_180017FB3
0x180017f52  movsxd  rax, dword ptr [rdi+18h]
0x180017f56  add     rax, [rcx+38h]
0x180017f5a  jz      short loc_180017FB3
0x180017f5c  lea     rdx, [rdi+8]
0x180017f60  mov     rcx, r8
0x180017f63  test    byte ptr [rdi], 4
0x180017f66  jz      short loc_180017F90
0x180017f68  call    __AdjustPointer
0x180017f6d  cmp     [rdi+18h], ebx
0x180017f70  jz      short loc_180017F7A
0x180017f72  movsxd  rbx, dword ptr [rdi+18h]
0x180017f76  add     rbx, [r14+38h]
0x180017f7a  mov     r9d, 1; int
0x180017f80  mov     r8, rax; void *
0x180017f83  mov     rdx, rbx; void *
0x180017f86  mov     rcx, r15; void *
0x180017f89  call    ?_CallMemberFunction2@@YAXQEAX00H@Z; _CallMemberFunction2(void * const,void * const,void * const,int)
0x180017f8e  jmp     short loc_180017FB1
0x180017f90  call    __AdjustPointer
0x180017f95  cmp     [rdi+18h], ebx
0x180017f98  jz      short loc_180017FA2
0x180017f9a  movsxd  rbx, dword ptr [rdi+18h]
0x180017f9e  add     rbx, [r14+38h]
0x180017fa2  mov     r8, rax; void *
0x180017fa5  mov     rdx, rbx; void *
0x180017fa8  mov     rcx, r15; void *
0x180017fab  call    ?_CallMemberFunction1@@YAXQEAX00@Z; _CallMemberFunction1(void * const,void * const,void * const)
0x180017fb0  nop
0x180017fb1  jmp     short loc_180017FDA
0x180017fb3  mov     r8, r9; Size
0x180017fb6  mov     rdx, rsi; Src
0x180017fb9  mov     rcx, r15; void *
0x180017fbc  call    memmove
0x180017fc1  test    byte ptr [rdi], 8
0x180017fc4  jz      short loc_180017FDA
0x180017fc6  mov     rcx, [rsi]
0x180017fc9  test    rcx, rcx
0x180017fcc  jz      short loc_180017FDA
0x180017fce  mov     rax, [rcx]
0x180017fd1  mov     rax, [rax+8]
0x180017fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fda  add     rsp, 30h
0x180017fde  pop     r15
0x180017fe0  pop     r14
0x180017fe2  pop     rdi
0x180017fe3  pop     rsi
0x180017fe4  pop     rbx
0x180017fe5  retn
```
