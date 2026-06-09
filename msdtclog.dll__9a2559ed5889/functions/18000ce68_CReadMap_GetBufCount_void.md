# CReadMap::GetBufCount(void)

- ea: `0x18000ce68`
- end: `0x18000cec1`
- name: `?GetBufCount@CReadMap@@QEAAKXZ`
- size: `89`
- prototype: `__int64 __fastcall(CReadMap *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002bf0`
- `0x180002ea0`
- `0x180007d7c`

## callees

- `0x18000c6b8`
- `0x18000ce68`

## pseudocode

```c
__int64 __fastcall CReadMap::GetBufCount(CReadMap *this)
{
  unsigned int v1; // edi
  unsigned int v3; // ecx
  __int64 v4; // rax

  v1 = 0;
  if ( *((_DWORD *)this + 11) )
  {
    CLogStorage::_UnmapBuffer(*((CLogStorage **)this + 22), *((LPCVOID **)this + 4), 0);
    *((_DWORD *)this + 11) = 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v3 = 0;
    do
    {
      v4 = 32LL * v3++;
      v1 += *(_DWORD *)((char *)this + v4 + 60) / *((_DWORD *)this + 46);
    }
    while ( v3 < *((_DWORD *)this + 2) );
  }
  return v1;
}

```

## disassembly

```asm
0x18000ce68  mov     [rsp+arg_0], rbx
0x18000ce6d  push    rdi
0x18000ce6e  sub     rsp, 20h
0x18000ce72  xor     edi, edi
0x18000ce74  mov     rbx, rcx
0x18000ce77  cmp     [rcx+2Ch], edi
0x18000ce7a  jz      short loc_18000CE92
0x18000ce7c  mov     rdx, [rcx+20h]; struct CBuffer *
0x18000ce80  xor     r8d, r8d; int
0x18000ce83  mov     rcx, [rcx+0B0h]; this
0x18000ce8a  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000ce8f  mov     [rbx+2Ch], edi
0x18000ce92  cmp     [rbx+8], edi
0x18000ce95  jbe     short loc_18000CEB4
0x18000ce97  xor     ecx, ecx
0x18000ce99  mov     eax, ecx
0x18000ce9b  xor     edx, edx
0x18000ce9d  shl     rax, 5
0x18000cea1  inc     ecx
0x18000cea3  mov     eax, [rax+rbx+3Ch]
0x18000cea7  div     dword ptr [rbx+0B8h]
0x18000cead  add     edi, eax
0x18000ceaf  cmp     ecx, [rbx+8]
0x18000ceb2  jb      short loc_18000CE99
0x18000ceb4  mov     rbx, [rsp+28h+arg_0]
0x18000ceb9  mov     eax, edi
0x18000cebb  add     rsp, 20h
0x18000cebf  pop     rdi
0x18000cec0  retn
```
