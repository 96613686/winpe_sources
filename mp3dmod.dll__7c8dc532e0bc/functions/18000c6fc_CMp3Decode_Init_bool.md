# CMp3Decode::Init(bool)

- ea: `0x18000c6fc`
- end: `0x18000c779`
- name: `?Init@CMp3Decode@@QEAAX_N@Z`
- size: `125`
- prototype: `void __fastcall(CMp3Decode *__hidden this, bool)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006110`
- `0x18000625c`
- `0x18000c6c0`
- `0x18000cd94`

## callees

- `0x18000c6fc`
- `0x18000c780`
- `0x18000c7d4`
- `0x18000efc8`
- `0x180012010`

## pseudocode

```c
void __fastcall CMp3Decode::Init(CMp3Decode *this, char a2)
{
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 628) + 8LL))((char *)this + 5024);
  if ( a2 )
  {
    memset_0((char *)this + 304, 0, 0x1200u);
    CPolyphase::Init((CMp3Decode *)((char *)this + 4920));
    memset_0((char *)this + 6344, 0, 0x1200u);
    memset_0((char *)this + 10952, 0, 0x1200u);
    CMp3Decode::ZeroPolySpectrum(this);
  }
}

```

## disassembly

```asm
0x18000c6fc  mov     [rsp+arg_0], rbx
0x18000c701  push    rdi
0x18000c702  sub     rsp, 20h
0x18000c706  mov     rdi, rcx
0x18000c709  mov     bl, dl
0x18000c70b  add     rcx, 13A0h
0x18000c712  mov     rax, [rcx]
0x18000c715  mov     rax, [rax+8]
0x18000c719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c71e  test    bl, bl
0x18000c720  jz      short loc_18000C76E
0x18000c722  mov     ebx, 1200h
0x18000c727  lea     rcx, [rdi+130h]; void *
0x18000c72e  mov     r8d, ebx; Size
0x18000c731  xor     edx, edx; Val
0x18000c733  call    memset_0
0x18000c738  lea     rcx, [rdi+1338h]; this
0x18000c73f  call    ?Init@CPolyphase@@QEAAXXZ; CPolyphase::Init(void)
0x18000c744  lea     rcx, [rdi+18C8h]; void *
0x18000c74b  mov     r8d, ebx; Size
0x18000c74e  xor     edx, edx; Val
0x18000c750  call    memset_0
0x18000c755  lea     rcx, [rdi+2AC8h]; void *
0x18000c75c  mov     r8d, ebx; Size
0x18000c75f  xor     edx, edx; Val
0x18000c761  call    memset_0
0x18000c766  mov     rcx, rdi; this
0x18000c769  call    ?ZeroPolySpectrum@CMp3Decode@@IEAAXXZ; CMp3Decode::ZeroPolySpectrum(void)
0x18000c76e  mov     rbx, [rsp+28h+arg_0]
0x18000c773  add     rsp, 20h
0x18000c777  pop     rdi
0x18000c778  retn
```
