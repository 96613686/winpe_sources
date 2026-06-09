# BaseWrapper<SString *,FunctionBase<SString *,&DoNothing<SString *>(SString *),&Delete<SString>(SString *),2>,0,&CompareDefault<SString *>(SString *,SString *),2>::~BaseWrapper<SString *,FunctionBase<SString *,&DoNothing<SString *>(SString *),&Delete<SString>(SString *),2>,0,&CompareDefault<SString *>(SString *,SString *),2>(void)

- ea: `0x140012eb8`
- end: `0x140012f08`
- name: `??1?$BaseWrapper@PEAVSString@@V?$FunctionBase@PEAVSString@@$1??$DoNothing@PEAVSString@@@@YAXPEAV1@@Z$1??$Delete@VSString@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVSString@@@@YAHPEAV1@0@Z$01@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015cac`
- `0x140015ead`

## callees

- `0x14000a10c`
- `0x140012eb8`
- `0x14001374c`

## pseudocode

```c
void __fastcall BaseWrapper<SString *,FunctionBase<SString *,&void DoNothing<SString *>(SString *),&void Delete<SString>(SString *),2>,0,&int CompareDefault<SString *>(SString *,SString *),2>::~BaseWrapper<SString *,FunctionBase<SString *,&void DoNothing<SString *>(SString *),&void Delete<SString>(SString *),2>,0,&int CompareDefault<SString *>(SString *,SString *),2>(
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
0x140012eb8  mov     [rsp+arg_8], rbx
0x140012ebd  mov     [rsp+arg_0], rcx
0x140012ec2  push    rdi
0x140012ec3  sub     rsp, 20h
0x140012ec7  mov     rdi, rcx
0x140012eca  cmp     dword ptr [rcx+8], 0
0x140012ece  jz      short loc_140012EFD
0x140012ed0  mov     rbx, [rcx]
0x140012ed3  mov     [rsp+28h+arg_0], rbx
0x140012ed8  test    rbx, rbx
0x140012edb  jz      short loc_140012EF9
0x140012edd  test    byte ptr [rbx+8], 8
0x140012ee1  jz      short loc_140012EEC
0x140012ee3  mov     rcx, [rbx+10h]; lpMem
0x140012ee7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012eec  mov     edx, 18h; unsigned __int64
0x140012ef1  mov     rcx, rbx; void *
0x140012ef4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012ef9  and     dword ptr [rdi+8], 0
0x140012efd  mov     rbx, [rsp+28h+arg_8]
0x140012f02  add     rsp, 20h
0x140012f06  pop     rdi
0x140012f07  retn
```
