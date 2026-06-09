# CFileStream::CFileStream(CLoader *)

- ea: `0x18000cd7c`
- end: `0x18000cdba`
- name: `??0CFileStream@@QEAA@PEAVCLoader@@@Z`
- size: `62`
- prototype: `CFileStream *__fastcall(CFileStream *__hidden this, struct CLoader *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009844`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000bbc4`
- `0x18000d060`

## callees

- `0x18000cd7c`

## pseudocode

```c
CFileStream *__fastcall CFileStream::CFileStream(CFileStream *this, struct CLoader *a2)
{
  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)this = &CFileStream::`vftable'{for `IStream'};
  *((_QWORD *)this + 1) = &CFileStream::`vftable'{for `IDirectMusicGetLoader'};
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 140);
  return this;
}

```

## disassembly

```asm
0x18000cd7c  mov     dword ptr [rcx+10h], 1
0x18000cd83  lea     rax, ??_7CFileStream@@6BIStream@@@; const CFileStream::`vftable'{for `IStream'}
0x18000cd8a  mov     [rcx], rax
0x18000cd8d  lea     rax, ??_7CFileStream@@6BIDirectMusicGetLoader@@@; const CFileStream::`vftable'{for `IDirectMusicGetLoader'}
0x18000cd94  mov     [rcx+8], rax
0x18000cd98  mov     qword ptr [rcx+220h], 0
0x18000cda3  mov     [rcx+228h], rdx
0x18000cdaa  test    rdx, rdx
0x18000cdad  jz      short loc_18000CDB6
0x18000cdaf  lock inc dword ptr [rdx+230h]
0x18000cdb6  mov     rax, rcx
0x18000cdb9  retn
```
