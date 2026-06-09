# OUTPUT_KEY::OUTPUT_KEY(void)

- ea: `0x180005200`
- end: `0x180005267`
- name: `??0OUTPUT_KEY@@QEAA@XZ`
- size: `103`
- prototype: `OUTPUT_KEY *__fastcall(OUTPUT_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f20`
- `0x180004d18`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005224`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000523e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005258`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005224`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000523e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005258`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180005209`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180005209`

## pseudocode

```c
OUTPUT_KEY *__fastcall OUTPUT_KEY::OUTPUT_KEY(OUTPUT_KEY *this)
{
  BUFFER::BUFFER(this);
  *((_DWORD *)this + 12) = 0;
  STRU::STRU((OUTPUT_KEY *)((char *)this + 56), (unsigned __int16 *)this + 56, 0x20u);
  STRU::STRU((OUTPUT_KEY *)((char *)this + 176), (unsigned __int16 *)this + 116, 0x80u);
  STRU::STRU((OUTPUT_KEY *)((char *)this + 488), (unsigned __int16 *)this + 272, 0x80u);
  return this;
}

```

## disassembly

```asm
0x180005200  push    rbx
0x180005202  sub     rsp, 20h
0x180005206  mov     rbx, rcx
0x180005209  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000520f  lea     rdx, [rbx+70h]
0x180005213  mov     dword ptr [rbx+30h], 0
0x18000521a  lea     rcx, [rbx+38h]
0x18000521e  mov     r8d, 20h ; ' '
0x180005224  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000522a  lea     rdx, [rbx+0E8h]
0x180005231  mov     r8d, 80h
0x180005237  lea     rcx, [rbx+0B0h]
0x18000523e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005244  lea     rdx, [rbx+220h]
0x18000524b  mov     r8d, 80h
0x180005251  lea     rcx, [rbx+1E8h]
0x180005258  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000525e  mov     rax, rbx
0x180005261  add     rsp, 20h
0x180005265  pop     rbx
0x180005266  retn
```
