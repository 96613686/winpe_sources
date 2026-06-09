# _CWriteMap::CopyRecord_::_1_::catch$0

- ea: `0x180014254`
- end: `0x1800142b2`
- name: `_CWriteMap::CopyRecord_::_1_::catch$0`
- size: `94`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000a990`
- `0x18001266c`
- `0x180014254`

## pseudocode

```c
void __fastcall __noreturn CWriteMap::CopyRecord_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int v3; // ebx
  __int64 v4; // rdi

  v3 = *(_DWORD *)(a2 + 136) - 1;
  if ( v3 >= 0 )
  {
    v4 = *(_QWORD *)(a2 + 112);
    do
    {
      if ( *(_QWORD *)(32LL * v3 + v4 + 104) )
        CLogStorage::PutWriteBuffer(*(CLogStorage **)(v4 + 32), *(struct CBuffer **)(32LL * v3 + v4 + 104));
      --v3;
    }
    while ( v3 >= 0 );
  }
  *(_DWORD *)(a2 + 64) = *(_DWORD *)(a2 + 72);
  throw (ulong *)(a2 + 64);
}

```

## disassembly

```asm
0x180014254  mov     [rsp+arg_8], rdx
0x180014259  push    rbx
0x18001425a  push    rbp
0x18001425b  push    rdi
0x18001425c  sub     rsp, 30h
0x180014260  mov     rbp, rdx
0x180014263  mov     ebx, [rbp+88h]
0x180014269  sub     ebx, 1
0x18001426c  js      short loc_18001429B
0x18001426e  mov     rdi, [rbp+70h]
0x180014272  movsxd  rax, ebx
0x180014275  shl     rax, 5
0x180014279  cmp     qword ptr [rax+rdi+68h], 0
0x18001427f  jz      short loc_180014296
0x180014281  movsxd  rdx, ebx
0x180014284  shl     rdx, 5
0x180014288  mov     rdx, [rdx+rdi+68h]; struct CBuffer *
0x18001428d  mov     rcx, [rdi+20h]; this
0x180014291  call    ?PutWriteBuffer@CLogStorage@@QEAAXPEAVCBuffer@@@Z; CLogStorage::PutWriteBuffer(CBuffer *)
0x180014296  sub     ebx, 1
0x180014299  jns     short loc_180014272
0x18001429b  mov     eax, [rbp+48h]
0x18001429e  mov     [rbp+40h], eax
0x1800142a1  lea     rdx, _TI1K; pThrowInfo
0x1800142a8  lea     rcx, [rbp+40h]; pExceptionObject
0x1800142ac  call    _CxxThrowException_0
```
