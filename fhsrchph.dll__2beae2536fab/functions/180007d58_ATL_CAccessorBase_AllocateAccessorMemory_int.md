# ATL::CAccessorBase::AllocateAccessorMemory(int)

- ea: `0x180007d58`
- end: `0x180007da3`
- name: `?AllocateAccessorMemory@CAccessorBase@ATL@@QEAAJH@Z`
- size: `75`
- prototype: `__int64 __fastcall(ATL::CAccessorBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007dac`

## callees

- `0x180001170`
- `0x180007d58`

## pseudocode

```c
__int64 __fastcall ATL::CAccessorBase::AllocateAccessorMemory(ATL::CAccessorBase *this)
{
  ATL::CAccessorBase *v1; // rbx
  unsigned int v2; // edi

  try
  {
    v1 = this;
    v2 = 0;
    *(_QWORD *)this = 0;
    *(_QWORD *)this = operator new[](0x10u);
  }
  catch ( ... )
  {
    v2 = 0;
    v1 = this;
  }
  if ( *(_QWORD *)v1 )
    *((_DWORD *)v1 + 2) = 1;
  else
    return (unsigned int)-2147024882;
  return v2;
}

```

## disassembly

```asm
0x180007d58  mov     [rsp+arg_8], rbx
0x180007d5d  mov     [rsp+arg_0], rcx
0x180007d62  push    rdi
0x180007d63  sub     rsp, 20h
0x180007d67  mov     rbx, rcx
0x180007d6a  xor     edi, edi
0x180007d6c  mov     [rcx], rdi
0x180007d6f  lea     ecx, [rdi+10h]; unsigned __int64
0x180007d72  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007d77  mov     [rbx], rax
0x180007d7a  jmp     short loc_180007D83
0x180007d7c  xor     edi, edi
0x180007d7e  mov     rbx, [rsp+28h+arg_0]
0x180007d83  cmp     [rbx], rdi
0x180007d86  jnz     short loc_180007D8F
0x180007d88  mov     edi, 8007000Eh
0x180007d8d  jmp     short loc_180007D96
0x180007d8f  mov     dword ptr [rbx+8], 1
0x180007d96  mov     eax, edi
0x180007d98  mov     rbx, [rsp+28h+arg_8]
0x180007d9d  add     rsp, 20h
0x180007da1  pop     rdi
0x180007da2  retn
```
