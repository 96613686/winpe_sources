# Helper::SelectedFiles::~SelectedFiles(void)

- ea: `0x180013b7c`
- end: `0x180013bc2`
- name: `??1SelectedFiles@Helper@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(Helper::SelectedFiles *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d338`
- `0x18000f074`
- `0x180014b78`
- `0x180015428`
- `0x180016a70`
- `0x180016fa8`

## callees

- `0x180001340`
- `0x180013b7c`

## pseudocode

```c
void __fastcall Helper::SelectedFiles::~SelectedFiles(Helper::SelectedFiles *this)
{
  __int64 i; // rdi
  void *v3; // rcx

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*((_QWORD *)this + 1) + 8 * i);
      if ( v3 )
        operator delete[](v3);
    }
    operator delete[](*((void **)this + 1));
  }
}

```

## disassembly

```asm
0x180013b7c  mov     [rsp+arg_0], rbx
0x180013b81  push    rdi
0x180013b82  sub     rsp, 20h
0x180013b86  cmp     qword ptr [rcx+8], 0
0x180013b8b  mov     rbx, rcx
0x180013b8e  jz      short loc_180013BB7
0x180013b90  xor     edi, edi
0x180013b92  cmp     [rcx], edi
0x180013b94  jbe     short loc_180013BAE
0x180013b96  mov     rax, [rbx+8]
0x180013b9a  mov     rcx, [rax+rdi*8]; Block
0x180013b9e  test    rcx, rcx
0x180013ba1  jz      short loc_180013BA8
0x180013ba3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180013ba8  inc     edi
0x180013baa  cmp     edi, [rbx]
0x180013bac  jb      short loc_180013B96
0x180013bae  mov     rcx, [rbx+8]; Block
0x180013bb2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180013bb7  mov     rbx, [rsp+28h+arg_0]
0x180013bbc  add     rsp, 20h
0x180013bc0  pop     rdi
0x180013bc1  retn
```
