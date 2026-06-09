# Wrapper<SString *,&DoNothing<SString *>(SString *),&Delete<SString>(SString *),0,&CompareDefault<SString *>(SString *,SString *),2,1>::~Wrapper<SString *,&DoNothing<SString *>(SString *),&Delete<SString>(SString *),0,&CompareDefault<SString *>(SString *,SString *),2,1>(void)

- ea: `0x140012e68`
- end: `0x140012eb8`
- name: `??1?$Wrapper@PEAVSString@@$1??$DoNothing@PEAVSString@@@@YAXPEAV1@@Z$1??$Delete@VSString@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVSString@@@@YAH00@Z$01$00@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015ca0`
- `0x140015ea1`

## callees

- `0x14000a10c`
- `0x140012e68`
- `0x14001374c`

## pseudocode

```c
void __fastcall Wrapper<SString *,&void DoNothing<SString *>(SString *),&void Delete<SString>(SString *),0,&int CompareDefault<SString *>(SString *,SString *),2,1>::~Wrapper<SString *,&void DoNothing<SString *>(SString *),&void Delete<SString>(SString *),0,&int CompareDefault<SString *>(SString *,SString *),2,1>(
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
0x140012e68  mov     [rsp+arg_8], rbx
0x140012e6d  mov     [rsp+arg_0], rcx
0x140012e72  push    rdi
0x140012e73  sub     rsp, 20h
0x140012e77  mov     rdi, rcx
0x140012e7a  cmp     dword ptr [rcx+8], 0
0x140012e7e  jz      short loc_140012EAD
0x140012e80  mov     rbx, [rcx]
0x140012e83  mov     [rsp+28h+arg_0], rbx
0x140012e88  test    rbx, rbx
0x140012e8b  jz      short loc_140012EA9
0x140012e8d  test    byte ptr [rbx+8], 8
0x140012e91  jz      short loc_140012E9C
0x140012e93  mov     rcx, [rbx+10h]; lpMem
0x140012e97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012e9c  mov     edx, 18h; unsigned __int64
0x140012ea1  mov     rcx, rbx; void *
0x140012ea4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012ea9  and     dword ptr [rdi+8], 0
0x140012ead  mov     rbx, [rsp+28h+arg_8]
0x140012eb2  add     rsp, 20h
0x140012eb6  pop     rdi
0x140012eb7  retn
```
