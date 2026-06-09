# std::vector<GUIDVarInfo,std::allocator<GUIDVarInfo>>::~vector<GUIDVarInfo,std::allocator<GUIDVarInfo>>(void)

- ea: `0x18000ca20`
- end: `0x18000ca88`
- name: `??1?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000cb80`
- `0x18000deb0`
- `0x18000df80`
- `0x18000e130`
- `0x18001412c`
- `0x180014145`

## callees

- `0x18000ca20`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ca54`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ca54`

## pseudocode

```c
void __fastcall std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(__int64 a1)
{
  GUIDVarInfo *v1; // rdi
  GUIDVarInfo *v3; // rsi

  v1 = *(GUIDVarInfo **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(GUIDVarInfo **)(a1 + 8);
    while ( v1 != v3 )
    {
      GUIDVarInfo::~GUIDVarInfo(v1);
      v1 = (GUIDVarInfo *)((char *)v1 + 80);
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000ca20  mov     [rsp+arg_0], rbx
0x18000ca25  mov     [rsp+arg_8], rsi
0x18000ca2a  push    rdi
0x18000ca2b  sub     rsp, 20h
0x18000ca2f  mov     rdi, [rcx]
0x18000ca32  mov     rbx, rcx
0x18000ca35  test    rdi, rdi
0x18000ca38  jz      short loc_18000CA77
0x18000ca3a  mov     rsi, [rcx+8]
0x18000ca3e  jmp     short loc_18000CA4C
0x18000ca40  mov     rcx, rdi; this
0x18000ca43  call    ??1GUIDVarInfo@@QEAA@XZ; GUIDVarInfo::~GUIDVarInfo(void)
0x18000ca48  add     rdi, 50h ; 'P'
0x18000ca4c  cmp     rdi, rsi
0x18000ca4f  jnz     short loc_18000CA40
0x18000ca51  mov     rcx, [rbx]
0x18000ca54  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ca5b  nop     dword ptr [rax+rax+00h]
0x18000ca60  mov     qword ptr [rbx], 0
0x18000ca67  mov     qword ptr [rbx+8], 0
0x18000ca6f  mov     qword ptr [rbx+10h], 0
0x18000ca77  mov     rbx, [rsp+28h+arg_0]
0x18000ca7c  mov     rsi, [rsp+28h+arg_8]
0x18000ca81  add     rsp, 20h
0x18000ca85  pop     rdi
0x18000ca86  retn
```
