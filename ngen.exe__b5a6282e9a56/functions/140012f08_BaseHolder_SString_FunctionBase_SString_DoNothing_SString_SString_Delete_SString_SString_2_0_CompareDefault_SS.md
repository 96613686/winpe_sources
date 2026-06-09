# BaseHolder<SString *,FunctionBase<SString *,&DoNothing<SString *>(SString *),&Delete<SString>(SString *),2>,0,&CompareDefault<SString *>(SString *,SString *),2>::~BaseHolder<SString *,FunctionBase<SString *,&DoNothing<SString *>(SString *),&Delete<SString>(SString *),2>,0,&CompareDefault<SString *>(SString *,SString *),2>(void)

- ea: `0x140012f08`
- end: `0x140012f53`
- name: `??1?$BaseHolder@PEAVSString@@V?$FunctionBase@PEAVSString@@$1??$DoNothing@PEAVSString@@@@YAXPEAV1@@Z$1??$Delete@VSString@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVSString@@@@YAHPEAV1@0@Z$01@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015cb8`
- `0x140015eb9`

## callees

- `0x14000a10c`
- `0x140012f08`
- `0x14001374c`

## pseudocode

```c
void __fastcall BaseHolder<SString *,FunctionBase<SString *,&void DoNothing<SString *>(SString *),&void Delete<SString>(SString *),2>,0,&int CompareDefault<SString *>(SString *,SString *),2>::~BaseHolder<SString *,FunctionBase<SString *,&void DoNothing<SString *>(SString *),&void Delete<SString>(SString *),2>,0,&int CompareDefault<SString *>(SString *,SString *),2>(
        __int64 *a1)
{
  __int64 v2; // rbx

  if ( *((_DWORD *)a1 + 2) )
  {
    v2 = *a1;
    if ( *a1 )
    {
      if ( (*(_BYTE *)(v2 + 8) & 8) != 0 )
        operator delete(*(void **)(v2 + 16));
      operator delete((void *)v2, 0x18u);
    }
    *((_DWORD *)a1 + 2) = 0;
  }
}

```

## disassembly

```asm
0x140012f08  mov     [rsp+arg_8], rbx
0x140012f0d  push    rdi
0x140012f0e  sub     rsp, 20h
0x140012f12  mov     rdi, rcx
0x140012f15  cmp     dword ptr [rcx+8], 0
0x140012f19  jz      short loc_140012F48
0x140012f1b  mov     rbx, [rcx]
0x140012f1e  mov     [rsp+28h+arg_0], rbx
0x140012f23  test    rbx, rbx
0x140012f26  jz      short loc_140012F44
0x140012f28  test    byte ptr [rbx+8], 8
0x140012f2c  jz      short loc_140012F37
0x140012f2e  mov     rcx, [rbx+10h]; lpMem
0x140012f32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012f37  mov     edx, 18h; unsigned __int64
0x140012f3c  mov     rcx, rbx; void *
0x140012f3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012f44  and     dword ptr [rdi+8], 0
0x140012f48  mov     rbx, [rsp+28h+arg_8]
0x140012f4d  add     rsp, 20h
0x140012f51  pop     rdi
0x140012f52  retn
```
